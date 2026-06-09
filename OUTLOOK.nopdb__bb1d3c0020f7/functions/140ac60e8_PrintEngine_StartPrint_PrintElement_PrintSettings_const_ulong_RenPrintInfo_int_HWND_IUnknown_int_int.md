# PrintEngine::StartPrint(PrintElement *,PrintSettings const *,ulong,RenPrintInfo *,int,HWND__ *,IUnknown *,int,int)

- ea: `0x140ac60e8`
- end: `0x140ac6e6b`
- name: `?StartPrint@PrintEngine@@SAXPEAVPrintElement@@PEBUPrintSettings@@KPEAURenPrintInfo@@HPEAUHWND__@@PEAUIUnknown@@HH@Z`
- size: `3459`
- prototype: `void __fastcall(struct PrintElement *, const struct PrintSettings *, unsigned int, struct RenPrintInfo *, int, HWND hWnd, struct IUnknown *, int, int)`
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x141615dc4`

## callees

- `0x14002a6c0`
- `0x14004aa90`
- `0x140076984`
- `0x1400d3df0`
- `0x1400d3e20`
- `0x1400d4d1c`
- `0x1400d7910`
- `0x1400dd680`
- `0x1400dd710`
- `0x140106cfc`
- `0x1401757a4`
- `0x140177e30`
- `0x1401a4f84`
- `0x1401c2500`
- `0x1402cb400`
- `0x1403450b0`
- `0x140503f00`
- `0x140504770`
- `0x140509800`
- `0x140509860`
- `0x140572f74`
- `0x1405a77b4`
- `0x1407e99f0`
- `0x1408c6640`
- `0x140ac6060`
- `0x140ac60e8`
- `0x140ac6e6c`
- `0x140ac6ef8`
- `0x140ac6f90`
- `0x140ac71ac`
- `0x140ac7248`
- `0x140ac7708`
- `0x140ac7a80`
- `0x140ac7c88`
- `0x140ac822c`
- `0x140ac8364`
- `0x140ac853c`
- `0x140e604f0`
- `0x140e7d580`
- `0x140ec1e24`
- `0x141170e78`
- `0x1411d7828`
- `0x141612e78`
- `0x14161ccd0`
- `0x14161cf04`
- `0x14161d204`
- `0x14161eca8`
- `0x14161f2e4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140ac6943`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140ac6943`
- `KERNEL32!GetLastError` at `0x140ac6a55`
- `KERNEL32!GetLastError` at `0x140ac6a55`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ac62b7`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ac62b7`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac63d5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac640d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac695a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac63d5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac640d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac695a`
- `GDI32!StartDocW` at `0x140ac6a4a`
- `GDI32!StartDocW` at `0x140ac6a4a`
- `GDI32!SetAbortProc` at `0x140ac6a38`
- `GDI32!SetAbortProc` at `0x140ac6a38`
- `GDI32!StartPage` at `0x140ac6bc6`
- `GDI32!StartPage` at `0x140ac6bc6`
- `GDI32!EndDoc` at `0x140ac6cc6`
- `GDI32!EndDoc` at `0x140ac6cc6`
- `GDI32!EndPage` at `0x140ac6c21`
- `GDI32!EndPage` at `0x140ac6c21`
- `ole32!CoTaskMemFree` at `0x140ac6d6a`
- `ole32!CoTaskMemFree` at `0x140ac6e35`
- `ole32!CoTaskMemFree` at `0x140ac6d6a`
- `ole32!CoTaskMemFree` at `0x140ac6e35`
- `USER32!UpdateWindow` at `0x140ac69a7`
- `USER32!UpdateWindow` at `0x140ac69a7`
- `USER32!ShowWindow` at `0x140ac6994`
- `USER32!ShowWindow` at `0x140ac6994`
- `USER32!EnableWindow` at `0x140ac6299`
- `USER32!EnableWindow` at `0x140ac6315`
- `USER32!EnableWindow` at `0x140ac66e2`
- `USER32!EnableWindow` at `0x140ac69f5`
- `USER32!EnableWindow` at `0x140ac6d24`
- `USER32!EnableWindow` at `0x140ac6299`
- `USER32!EnableWindow` at `0x140ac6315`
- `USER32!EnableWindow` at `0x140ac66e2`
- `USER32!EnableWindow` at `0x140ac69f5`
- `USER32!EnableWindow` at `0x140ac6d24`
- `USER32!SetDlgItemTextW` at `0x140ac6911`
- `USER32!SetDlgItemTextW` at `0x140ac6981`
- `USER32!SetDlgItemTextW` at `0x140ac6911`
- `USER32!SetDlgItemTextW` at `0x140ac6981`
- `USER32!SetDlgItemTextA` at `0x140ac6c01`
- `USER32!SetDlgItemTextA` at `0x140ac6c01`
- `USER32!SetCursor` at `0x140ac6720`
- `USER32!SetCursor` at `0x140ac69da`
- `USER32!SetCursor` at `0x140ac6c9e`
- `USER32!SetCursor` at `0x140ac6d60`
- `USER32!SetCursor` at `0x140ac6dd3`
- `USER32!SetCursor` at `0x140ac6e11`
- `USER32!SetCursor` at `0x140ac6720`
- `USER32!SetCursor` at `0x140ac69da`
- `USER32!SetCursor` at `0x140ac6c9e`
- `USER32!SetCursor` at `0x140ac6d60`
- `USER32!SetCursor` at `0x140ac6dd3`
- `USER32!SetCursor` at `0x140ac6e11`
- `MSO!__imp_?ShouldBlockPrintToFile@Printing@Mso@@YA_NPEAUISession@Clp@2@PEAUIUnknown@@PEAUIMsoDrmDocument@@PEB_W_N4PEBU_msoreg@@@Z` at `0x140ac64c6`
- `MSO!__imp_?ShouldBlockPrintToFile@Printing@Mso@@YA_NPEAUISession@Clp@2@PEAUIUnknown@@PEAUIMsoDrmDocument@@PEB_W_N4PEBU_msoreg@@@Z` at `0x140ac64c6`
- `Mso98Win32Client!__imp_?MsoPlaySound@@YAJH@Z` at `0x140ac6cd1`
- `Mso98Win32Client!__imp_?MsoPlaySound@@YAJH@Z` at `0x140ac6cd1`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140ac627a`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140ac627a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140ac678a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140ac678a`

## pseudocode

```c

```
