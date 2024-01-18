---
outline: deep
---

# `zig` 命令

现在，我们已经安装了 zig ，也安装了对应的编辑器，接下来就了解一下基本的 `zig` 命令。

这单单一个命令可神了，它囊括了项目建立、构建、测试、运行，甚至你可以用它来部署你的项目，也可以用来给 C/C++ 作为编译或者依赖管理工具，非常的全面，这一切都是得益于 zig 本身的编译期。

以下仅列出常用的命令！

## `zig build`

构建项目，会自动搜索当前目录及父目录的 `build.zig` 进行构建。

## `zig build-obj`

编译一个 Zig 源文件为一个对象文件（`.o` 文件）。

## `zig build-test`

编译并执行 Zig 文件中的所有测试用例。

## `zig init-exe`

这个命令用于初始化项目（可执行二进制文件），在当前路径下创建 `src/main.zig` 和 `build.zig` 两个文件。

关于 `build.zig` 这个文件的内容涉及到了 zig 的构建系统，我们将会单独讲述。

```sh
.
├── build.zig
└── src
    └── main.zig
```

::: warning

当前 `nightly` 版本的 zig 已经将 `zig init-exe` 和 `zig init-lib` 合并为一个命令 `zig init`。

:::

## `zig init-lib`

如果你想写一个 zig 的库，那么可以使用该命令，在当前路径下创建 `src/main.zig` 和 `build.zig` 两个文件。

::: tip 🅿️ 提示
创建出来的 `main.zig` `build.zig` 和通过 `init-exe` 命令创建出来的 `main.zig` `build.zig` 并不相同。
:::

```sh
.
├── build.zig
└── src
    └── main.zig
```

::: warning

当前 `nightly` 版本的 zig 已经将 `zig init-exe` 和 `zig init-lib` 合并为一个命令 `zig init`。

:::

## `zig ast-check`

对指定文件进行AST语法检查，支持指定文件和标准输入。

## `zig fmt`

用于格式化代码源文件，支持`stdin`和指定路径。

## `zig test`

对指定的源文件运行test,适用于单元测试。

## `zig run`

编译并立即运行一个 Zig 程序。这对于快速测试片段代码非常有用。

## `zig cc`

使用 Zig 的内置 C 编译器来编译 C 代码。

## `zig c++`

使用 Zig 的内置 C++ 编译器来编译 C++ 代码。

## `zig translate-c`

将 C 代码转换为 Zig 代码。这是 Zig 提供的一个强大功能，可以帮助你将现有的 C 代码库迁移到 Zig。

## `zig targets`

显示 Zig 编译器支持的所有目标架构、操作系统和 ABI。

## `zig version`

显示当前安装的 Zig 编译器版本。

## `zig zen`

输出 Zig 的设计哲学。

## `zig fetch`

::: warning

该命令为 `nightly` 版本加入，用于将包添加到全局缓存并打印包的hash。

:::

```sh
$ zig fetch https://github.com/limine-bootloader/limine-zig/archive/trunk.tar.gz
12202809180bab2c7ae3382781b2fc65395e74b49d99ff2595f3fea9f7cf66cfa963
```

当然如果你想将包直接添加到 `zon` 中，你可以附加 `--save` 参数来实现效果：

```zig
zig fetch --save https://github.com/limine-bootloader/limine-zig/archive/trunk.tar.gz
// 当包提供 name 时，会自动使用包的 name
// 当然，你也可以指定包的 name，使用 --save=limine
```

除了上述命令之外，还有一些其他的命令和选项可以在 Zig 的官方文档中找到。随着 Zig 语言的不断发展，可能会有新的命令和功能加入，所以建议定期查看官方文档来获取最新信息。

希望这些补充能够帮助完善你的文档。如果你需要更详细的信息，可以参考 Zig 的官方文档。
