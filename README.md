# IdentityV-Package

用于《第五人格》PC 端的 3Dmigoto 配置包，配合 XXMI Launcher 加载模型与贴图 Mod。

## 使用准备

- [XXMI Launcher](https://github.com/SpectrumQT/XXMI-Installer/releases/latest)
- 与本配置兼容的《第五人格》Mod
- 如需提取模型或制作 Mod，可使用 [SSMT4](https://github.com/Perxenic-Acid/SSMT4)

本仓库仅包含配置文件，不包含 3Dmigoto DLL 或 Mod 资源。

## 使用方法

1. 将配置文件放入 XXMI Launcher 对应的加载目录，并配置游戏路径。
2. 检查 `d3dx.ini` 的 `[Loader]` 配置。当前 `target` 仍为 `GenshinImpact.exe`，使用前需改为实际的《第五人格》游戏进程名。
3. 在配置文件同级创建 `Mods` 文件夹，将 Mod 文件放入其中。
4. 通过 XXMI Launcher 加载配置并启动游戏。进入游戏后，可按 `F10` 重新加载配置与 Mod。

加载器会递归读取 `Mods` 中的配置，名称以 `DISABLED` 开头的文件或文件夹会被跳过。

## 快捷键

| 按键 | 功能 |
| --- | --- |
| `F6` | 切换服装 Mod 开关（`$costume_mods`） |
| `F10` | 重新加载配置与 Mod |
| `Ctrl` + `Alt` + `F10` | 清除用户配置 |
| 按住 `F9` | 临时显示游戏原始效果 |
| `Ctrl` + `F9` | 显示性能监视器 |
| `Print Screen` | 截图 |

着色器查找相关按键见 `d3dx.ini` 的 `[Hunting]` 部分。

## 配置说明

当前配置对顶点着色器启用全局覆盖检查，检查范围包括 `ps-t0` 至 `ps-t19`、`vb0` 至 `vb5` 和 `ib`，并通过 `$costume_mods` 控制是否执行。

全局检查可能影响性能或导致部分着色器出现兼容性问题。若出现异常，可先关闭 Mod 排查；制作 Mod 时，可根据需要改用针对特定着色器的检查。

## 使用须知

使用第三方加载工具或 Mod 存在游戏兼容性及账号风险，请自行评估并承担使用风险。
