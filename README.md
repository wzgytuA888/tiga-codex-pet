# Tiga / 迪迦 Codex Pet

当前公开版本：**v1.0.1**

这是一个适用于 Codex 的 Q 版 Tiga 主题自定义宠物包。角色采用银色头冠、暖白发光眼、红紫银身体纹样、金色胸甲和胸口计时器，并覆盖 Codex 固定的九种宠物状态。

![Tiga animation contact sheet](contact-sheet.png)

## 安装

把以下两个文件复制到 Codex 宠物目录中的 `tiga` 文件夹：

- `pet.json`
- `spritesheet.webp`

Windows 默认位置通常为：

```text
%USERPROFILE%\.codex\pets\tiga
```

## v1.0.1 修复

- 修复全部 57 个已使用动画帧的脸部、额头、下颌和外轮廓透明穿孔。
- 还原误抠除区域的颜色和实心 alpha，保留正常肢体间隙与动作轮廓。
- 清理低透明边缘的白色 matte：检测像素由 10,157 降至 105。
- 对 `alpha=0`、`alpha≤8`、`alpha≤63` 三档封闭空洞复检，结果均为 0。
- 在黑色、洋红和白色背景下完成逐帧视觉 QA，九个动作 GIF 均通过。

## 图集合同

- 图集：1536×1872 RGBA WebP
- 布局：8 列 × 9 行
- 单元格：192×208
- 未使用格：完全透明

| 行 | 状态 | 帧数 | 动作 |
|---:|---|---:|---|
| 0 | `idle` | 6 | 呼吸、轻微起伏与眨眼 |
| 1 | `running-right` | 8 | 右向交替步态 |
| 2 | `running-left` | 8 | 左向交替步态 |
| 3 | `waving` | 4 | 举手问候 |
| 4 | `jumping` | 5 | 蓄势、腾空、下降与落地 |
| 5 | `failed` | 8 | 低头、计时器警告、重新振作 |
| 6 | `waiting` | 6 | 思考与等待用户输入 |
| 7 | `running` | 6 | 任务处理中与左右扫描 |
| 8 | `review` | 6 | 专注检查与收势 |

## 验证

- `inspect_frames.py --require-components`：0 errors，0 warnings
- `validate_atlas.py`：通过
- 尺寸与 RGBA 格式正确
- 透明 RGB 残留：0
- 所有已使用格非空，所有未使用格完全透明
- 最终视觉 QA：通过

详细修复指标见 [`repair-report.json`](repair-report.json)，版本记录见 [`CHANGELOG.md`](CHANGELOG.md)。

## 说明

这是一个非官方、非商业的粉丝创作项目，与圆谷制作及相关权利方无隶属或授权关系。角色名称与原始设计归各自权利方所有。
