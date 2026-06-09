# StdTableView::PaintTextField(int,FieldInfo *,GridWndAttr &,CellStyle &,CDC *,IPropertyAccess *,CRect &,EPaintTextFlags,long,wchar_t const *,bool)

- ea: `0x1402f7a04`
- end: `0x1402f88e4`
- name: `?PaintTextField@StdTableView@@IEAAJHPEAVFieldInfo@@AEAVGridWndAttr@@AEAUCellStyle@@PEAVCDC@@PEAUIPropertyAccess@@AEAVCRect@@W4EPaintTextFlags@@JPEB_W_N@Z`
- size: `3808`
- prototype: ``
- caller_count: `3`
- callee_count: `40`
- tags: ``

## callers

- `0x1402f4ee0`
- `0x140a900c0`
- `0x140cf17a0`

## callees

- `0x14004355c`
- `0x1400448c0`
- `0x14004956c`
- `0x1400496f0`
- `0x1400496f8`
- `0x140049730`
- `0x14004a100`
- `0x140053620`
- `0x1400b506c`
- `0x1400d2400`
- `0x1400d2670`
- `0x1400dd0ac`
- `0x1400dd670`
- `0x1400dd700`
- `0x1400e3914`
- `0x14010a0e0`
- `0x14010abac`
- `0x14010ac00`
- `0x14010afb4`
- `0x140122864`
- `0x140173ff0`
- `0x140174300`
- `0x140256424`
- `0x140256ed8`
- `0x140257218`
- `0x1402b9770`
- `0x1402f7a04`
- `0x1402f88f0`
- `0x1405049f0`
- `0x1405e2108`
- `0x14065836c`
- `0x1407e9990`
- `0x14088a8e0`
- `0x14088adf8`
- `0x140949b38`
- `0x140a8fef0`
- `0x140a8ff50`
- `0x140a8ffe8`
- `0x140ccfbd0`
- `0x140e4c9c8`

## import_xrefs

- `OLMAPI32!ReportVTPResult` at `0x1402f7da8`
- `OLMAPI32!ReportVTPResult` at `0x1402f855e`
- `OLMAPI32!ReportVTPResult` at `0x1402f7da8`
- `OLMAPI32!ReportVTPResult` at `0x1402f855e`
- `OLMAPI32!AllowHxfVTPReports` at `0x1402f8377`
- `OLMAPI32!AllowHxfVTPReports` at `0x1402f8377`
- `OLMAPI32!FIsFeatureEnabled` at `0x1402f7bf0`
- `OLMAPI32!FIsFeatureEnabled` at `0x1402f7bf0`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f7ecc`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f8071`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f873a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f7ecc`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f8071`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f873a`
- `GDI32!SelectObject` at `0x1402f7df1`
- `GDI32!SelectObject` at `0x1402f7df1`
- `GDI32!GetCurrentObject` at `0x1402f802e`
- `GDI32!GetCurrentObject` at `0x1402f802e`
- `OLEAUT32!__imp_VariantInit` at `0x1402f7a91`
- `OLEAUT32!__imp_VariantInit` at `0x1402f7a91`
- `OLEAUT32!__imp_VariantClear` at `0x1402f7dd5`
- `OLEAUT32!__imp_VariantClear` at `0x1402f7dd5`
- `USER32!SetRectEmpty` at `0x1402f7c18`
- `USER32!SetRectEmpty` at `0x1402f80c5`
- `USER32!SetRectEmpty` at `0x1402f81b3`
- `USER32!SetRectEmpty` at `0x1402f7c18`
- `USER32!SetRectEmpty` at `0x1402f80c5`
- `USER32!SetRectEmpty` at `0x1402f81b3`
- `USER32!InflateRect` at `0x1402f85e5`
- `USER32!InflateRect` at `0x1402f85e5`
- `USER32!CopyRect` at `0x1402f811b`
- `USER32!CopyRect` at `0x1402f8227`
- `USER32!CopyRect` at `0x1402f811b`
- `USER32!CopyRect` at `0x1402f8227`
- `MSO!__imp_MsoDrawTextW` at `0x1402f7c53`
- `MSO!__imp_MsoDrawTextW` at `0x1402f7e89`
- `MSO!__imp_MsoDrawTextW` at `0x1402f8108`
- `MSO!__imp_MsoDrawTextW` at `0x1402f821a`
- `MSO!__imp_MsoDrawTextW` at `0x1402f82b4`
- `MSO!__imp_MsoDrawTextW` at `0x1402f83bf`
- `MSO!__imp_MsoDrawTextW` at `0x1402f7c53`
- `MSO!__imp_MsoDrawTextW` at `0x1402f7e89`
- `MSO!__imp_MsoDrawTextW` at `0x1402f8108`
- `MSO!__imp_MsoDrawTextW` at `0x1402f821a`
- `MSO!__imp_MsoDrawTextW` at `0x1402f82b4`
- `MSO!__imp_MsoDrawTextW` at `0x1402f83bf`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f8311`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f84af`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f8311`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f84af`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f8785`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f8785`
- `Mso20Win32Client!__imp_MsoFAlphaWch` at `0x1402f84e4`
- `Mso20Win32Client!__imp_MsoFAlphaWch` at `0x1402f8537`
- `Mso20Win32Client!__imp_MsoFAlphaWch` at `0x1402f84e4`
- `Mso20Win32Client!__imp_MsoFAlphaWch` at `0x1402f8537`
- `Mso20Win32Client!__imp_?MsoUsrFromWch@@YAH_W@Z` at `0x1402f8503`
- `Mso20Win32Client!__imp_?MsoUsrFromWch@@YAH_W@Z` at `0x1402f857a`
- `Mso20Win32Client!__imp_?MsoUsrFromWch@@YAH_W@Z` at `0x1402f8503`
- `Mso20Win32Client!__imp_?MsoUsrFromWch@@YAH_W@Z` at `0x1402f857a`

## pseudocode

```c

```
