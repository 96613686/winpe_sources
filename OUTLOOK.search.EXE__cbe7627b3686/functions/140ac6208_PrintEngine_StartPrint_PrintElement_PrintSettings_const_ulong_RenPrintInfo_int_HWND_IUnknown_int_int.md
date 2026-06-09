# PrintEngine::StartPrint(PrintElement *,PrintSettings const *,ulong,RenPrintInfo *,int,HWND__ *,IUnknown *,int,int)

- ea: `0x140ac6208`
- end: `0x140ac6f8b`
- name: `?StartPrint@PrintEngine@@SAXPEAVPrintElement@@PEBUPrintSettings@@KPEAURenPrintInfo@@HPEAUHWND__@@PEAUIUnknown@@HH@Z`
- size: `3459`
- prototype: `void __fastcall(struct PrintElement *, const struct PrintSettings *, unsigned int, struct RenPrintInfo *, int, HWND hWnd, struct IUnknown *, int, int)`
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x141615e84`

## callees

- `0x14002a6c0`
- `0x14004aa50`
- `0x1400769d4`
- `0x1400d3de0`
- `0x1400d3e10`
- `0x1400d4d0c`
- `0x1400d7900`
- `0x1400dd670`
- `0x1400dd700`
- `0x140106d8c`
- `0x1401757e4`
- `0x140177e70`
- `0x1401a4fa4`
- `0x1401c2520`
- `0x1402cbc80`
- `0x1403459e0`
- `0x1405049f0`
- `0x140505260`
- `0x14050a2e0`
- `0x14050a340`
- `0x14057363c`
- `0x1405a6e64`
- `0x1407e9990`
- `0x1408c6620`
- `0x140ac6180`
- `0x140ac6208`
- `0x140ac6f8c`
- `0x140ac7018`
- `0x140ac70b0`
- `0x140ac72cc`
- `0x140ac7368`
- `0x140ac7828`
- `0x140ac7ba0`
- `0x140ac7da8`
- `0x140ac834c`
- `0x140ac8484`
- `0x140ac865c`
- `0x140e605a0`
- `0x140e7d630`
- `0x140ec1ed4`
- `0x141170f38`
- `0x1411d78e8`
- `0x141612f38`
- `0x14161cd90`
- `0x14161cfc4`
- `0x14161d2c4`
- `0x14161ed68`
- `0x14161f3a4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140ac6a63`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140ac6a63`
- `KERNEL32!GetLastError` at `0x140ac6b75`
- `KERNEL32!GetLastError` at `0x140ac6b75`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ac63d7`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ac63d7`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac64f5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac652d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac6a7a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac64f5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac652d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ac6a7a`
- `GDI32!StartDocW` at `0x140ac6b6a`
- `GDI32!StartDocW` at `0x140ac6b6a`
- `GDI32!SetAbortProc` at `0x140ac6b58`
- `GDI32!SetAbortProc` at `0x140ac6b58`
- `GDI32!StartPage` at `0x140ac6ce6`
- `GDI32!StartPage` at `0x140ac6ce6`
- `GDI32!EndDoc` at `0x140ac6de6`
- `GDI32!EndDoc` at `0x140ac6de6`
- `GDI32!EndPage` at `0x140ac6d41`
- `GDI32!EndPage` at `0x140ac6d41`
- `ole32!CoTaskMemFree` at `0x140ac6e8a`
- `ole32!CoTaskMemFree` at `0x140ac6f55`
- `ole32!CoTaskMemFree` at `0x140ac6e8a`
- `ole32!CoTaskMemFree` at `0x140ac6f55`
- `USER32!UpdateWindow` at `0x140ac6ac7`
- `USER32!UpdateWindow` at `0x140ac6ac7`
- `USER32!ShowWindow` at `0x140ac6ab4`
- `USER32!ShowWindow` at `0x140ac6ab4`
- `USER32!EnableWindow` at `0x140ac63b9`
- `USER32!EnableWindow` at `0x140ac6435`
- `USER32!EnableWindow` at `0x140ac6802`
- `USER32!EnableWindow` at `0x140ac6b15`
- `USER32!EnableWindow` at `0x140ac6e44`
- `USER32!EnableWindow` at `0x140ac63b9`
- `USER32!EnableWindow` at `0x140ac6435`
- `USER32!EnableWindow` at `0x140ac6802`
- `USER32!EnableWindow` at `0x140ac6b15`
- `USER32!EnableWindow` at `0x140ac6e44`
- `USER32!SetDlgItemTextW` at `0x140ac6a31`
- `USER32!SetDlgItemTextW` at `0x140ac6aa1`
- `USER32!SetDlgItemTextW` at `0x140ac6a31`
- `USER32!SetDlgItemTextW` at `0x140ac6aa1`
- `USER32!SetDlgItemTextA` at `0x140ac6d21`
- `USER32!SetDlgItemTextA` at `0x140ac6d21`
- `USER32!SetCursor` at `0x140ac6840`
- `USER32!SetCursor` at `0x140ac6afa`
- `USER32!SetCursor` at `0x140ac6dbe`
- `USER32!SetCursor` at `0x140ac6e80`
- `USER32!SetCursor` at `0x140ac6ef3`
- `USER32!SetCursor` at `0x140ac6f31`
- `USER32!SetCursor` at `0x140ac6840`
- `USER32!SetCursor` at `0x140ac6afa`
- `USER32!SetCursor` at `0x140ac6dbe`
- `USER32!SetCursor` at `0x140ac6e80`
- `USER32!SetCursor` at `0x140ac6ef3`
- `USER32!SetCursor` at `0x140ac6f31`
- `MSO!__imp_?ShouldBlockPrintToFile@Printing@Mso@@YA_NPEAUISession@Clp@2@PEAUIUnknown@@PEAUIMsoDrmDocument@@PEB_W_N4PEBU_msoreg@@@Z` at `0x140ac65e6`
- `MSO!__imp_?ShouldBlockPrintToFile@Printing@Mso@@YA_NPEAUISession@Clp@2@PEAUIUnknown@@PEAUIMsoDrmDocument@@PEB_W_N4PEBU_msoreg@@@Z` at `0x140ac65e6`
- `Mso98Win32Client!__imp_?MsoPlaySound@@YAJH@Z` at `0x140ac6df1`
- `Mso98Win32Client!__imp_?MsoPlaySound@@YAJH@Z` at `0x140ac6df1`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140ac639a`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140ac639a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140ac68aa`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140ac68aa`

## pseudocode

```c

```
