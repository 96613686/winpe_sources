# Jot::CSectionTabBase::PaintTextLabel(HDC__ *,MsoCF::String<MsoCF::WzTraits>,tagRECT const &,ulong,bool,bool,bool,bool)

- ea: `0x14003e740`
- end: `0x14003ebab`
- name: `?PaintTextLabel@CSectionTabBase@Jot@@IEAAXPEAUHDC__@@V?$String@UWzTraits@MsoCF@@@MsoCF@@AEBUtagRECT@@K_N333@Z`
- size: `1131`
- prototype: `__int64 __usercall@<rax>(Jot::DPIUtils *this@<rcx>, Jot::NavigationUI *@<rdx>, unsigned int, char, char, char, char)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x14003d9d0`

## callees

- `0x140038780`
- `0x140038838`
- `0x140038908`
- `0x14003e740`
- `0x14003ebac`
- `0x14003f250`
- `0x140048b00`
- `0x140049270`
- `0x1400492bc`
- `0x140050d50`
- `0x140051700`
- `0x140056ac0`
- `0x140057580`
- `0x14005867c`
- `0x1400a4408`
- `0x1400b71fc`
- `0x1400bb738`
- `0x1400c967c`
- `0x1400f0864`
- `0x14014b030`
- `0x14014cc28`

## import_xrefs

- `onmain!?IsColoredEmojiSectionTabRenderingEnabled@Jot@@YAAEBVTriggeredFeatureGate@Optimized@AB@Mso@@XZ` at `0x14003e857`
- `onmain!?IsColoredEmojiSectionTabRenderingEnabled@Jot@@YAAEBVTriggeredFeatureGate@Optimized@AB@Mso@@XZ` at `0x14003e857`
- `onmain!?TheMainApp@Jot@@YAPEAUAMainApp@1@XZ` at `0x14003e786`
- `onmain!?TheMainApp@Jot@@YAPEAUAMainApp@1@XZ` at `0x14003e7aa`
- `onmain!?TheMainApp@Jot@@YAPEAUAMainApp@1@XZ` at `0x14003e786`
- `onmain!?TheMainApp@Jot@@YAPEAUAMainApp@1@XZ` at `0x14003e7aa`
- `GDI32!SelectObject` at `0x14003e7f6`
- `GDI32!SelectObject` at `0x14003eb76`
- `GDI32!SelectObject` at `0x14003e7f6`
- `GDI32!SelectObject` at `0x14003eb76`
- `mso40uiWin32Client!__imp_?PaintText@Element@NetUI@@IEAAXAEBVPaintContext@@PEB_WAEAUtagRECT@@_N@Z` at `0x14003eabf`
- `mso40uiWin32Client!__imp_?PaintText@Element@NetUI@@IEAAXAEBVPaintContext@@PEB_WAEAUtagRECT@@_N@Z` at `0x14003eabf`
- `mso40uiWin32Client!__imp_?FromDibHDC@PaintContext@@SA?AV?$optional@VPaintContext@@@std@@PEAUHDC__@@@Z` at `0x14003ea60`
- `mso40uiWin32Client!__imp_?FromDibHDC@PaintContext@@SA?AV?$optional@VPaintContext@@@std@@PEAUHDC__@@@Z` at `0x14003ea9f`
- `mso40uiWin32Client!__imp_?FromDibHDC@PaintContext@@SA?AV?$optional@VPaintContext@@@std@@PEAUHDC__@@@Z` at `0x14003ea60`
- `mso40uiWin32Client!__imp_?FromDibHDC@PaintContext@@SA?AV?$optional@VPaintContext@@@std@@PEAUHDC__@@@Z` at `0x14003ea9f`
- `mso40uiWin32Client!__imp_?SetTextAlign@Element@NetUI@@QEAAJH@Z` at `0x14003e812`
- `mso40uiWin32Client!__imp_?SetTextAlign@Element@NetUI@@QEAAJH@Z` at `0x14003e812`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x14003e8b7`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x14003e8b7`
- `mso40uiWin32Client!__imp_?SetDirection@Element@NetUI@@QEAAJH@Z` at `0x14003e829`
- `mso40uiWin32Client!__imp_?SetDirection@Element@NetUI@@QEAAJH@Z` at `0x14003e829`
- `mso40uiWin32Client!__imp_?CreateTextProperties@FormattedText@Mso@@YA?AV?$TCntPtr@UITextProperties@FormattedText@Mso@@@2@AEBUTextPropertyParameters@12@@Z` at `0x14003e97d`
- `mso40uiWin32Client!__imp_?CreateTextProperties@FormattedText@Mso@@YA?AV?$TCntPtr@UITextProperties@FormattedText@Mso@@@2@AEBUTextPropertyParameters@12@@Z` at `0x14003e97d`
- `mso40uiWin32Client!__imp_?PaintTextContent@Element@NetUI@@IEAAXAEBVPaintContext@@AEAUtagRECT@@PEB_WPEBUPropertyInfo@2@_N@Z` at `0x14003ea85`
- `mso40uiWin32Client!__imp_?PaintTextContent@Element@NetUI@@IEAAXAEBVPaintContext@@AEAUtagRECT@@PEB_WPEBUPropertyInfo@2@_N@Z` at `0x14003ea85`
- `mso40uiWin32Client!__imp_?TextPropertiesFromTextStyle@NetUI@@YAXAEAUTextPropertyParameters@FormattedText@Mso@@AEBUITextStyle@TextStyles@4@HPEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@4@V?$optional@UColor@TextStyles@Mso@@@std@@PEB_W@Z` at `0x14003e912`
- `mso40uiWin32Client!__imp_?TextPropertiesFromTextStyle@NetUI@@YAXAEAUTextPropertyParameters@FormattedText@Mso@@AEBUITextStyle@TextStyles@4@HPEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@4@V?$optional@UColor@TextStyles@Mso@@@std@@PEB_W@Z` at `0x14003e912`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14003ea50`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14003ea50`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14003e798`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14003e798`

## pseudocode

```c

```
