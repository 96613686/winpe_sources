# ExplorerFrame::ShowFolder(_GUID,wchar_t const *,__MIDL___MIDL_itf_xtypes_0000_0000_0001 *,int,int,ulong,__MIDL___MIDL_itf_xtypes_0000_0000_0001 * *,IUnknown * *)

- ea: `0x1400aca90`
- end: `0x1400ae81a`
- name: `?ShowFolder@ExplorerFrame@@UEAAJU_GUID@@PEB_WPEAU__MIDL___MIDL_itf_xtypes_0000_0000_0001@@HHKPEAPEAU3@PEAPEAUIUnknown@@@Z`
- size: `7562`
- prototype: `__int64 __usercall@<rax>(ExplorerFrame *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, const wchar_t *@<r8>, struct __MIDL___MIDL_itf_xtypes_0000_0000_0001 *@<r9>, int, int, unsigned int, struct __MIDL___MIDL_itf_xtypes_0000_0000_0001 **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `82`
- tags: `registry_config, service_task`

## callees

- `0x1400255e8`
- `0x14002cd54`
- `0x140031560`
- `0x140034230`
- `0x14004d6f0`
- `0x140052cc0`
- `0x140057a00`
- `0x14007d9f8`
- `0x14008a5f0`
- `0x140093e50`
- `0x14009bcdc`
- `0x1400a7ab0`
- `0x1400ab20c`
- `0x1400ac1ec`
- `0x1400ac3f0`
- `0x1400ac6a0`
- `0x1400aca90`
- `0x1400ae81c`
- `0x1400ae87c`
- `0x1400aeb54`
- `0x1400aedb0`
- `0x1400aeddc`
- `0x1400aedf4`
- `0x1400aee70`
- `0x1400aef6c`
- `0x1400af384`
- `0x1400af4d0`
- `0x1400af56c`
- `0x1400af5e4`
- `0x1400af7ac`
- `0x1400c25a0`
- `0x1400d3df0`
- `0x1400d3e20`
- `0x1400da630`
- `0x1400da638`
- `0x1400dd0bc`
- `0x1400dd630`
- `0x1400e2bf8`
- `0x1400f05c8`
- `0x1400f1480`
- `0x1400f5678`
- `0x1400fbf14`
- `0x140103f1c`
- `0x140108700`
- `0x14012c7b0`
- `0x14012d708`
- `0x14014cb74`
- `0x14015aa30`
- `0x1401c3f5c`
- `0x1401cecb8`

## import_xrefs

- `OLMAPI32!ReportVTPResult` at `0x1400ae80e`
- `OLMAPI32!ReportVTPResult` at `0x1400ae80e`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400acdfc`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad0a8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad516`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad7b5`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad7c8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ae0e3`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400acdfc`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad0a8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad516`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad7b5`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ad7c8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1400ae0e3`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ad30d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae15f`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae4fe`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae543`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae590`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ad30d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae15f`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae4fe`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae543`
- `OLMAPI32!EtwTraceErrorTag` at `0x1400ae590`
- `ole32!CoTaskMemFree` at `0x1400ad479`
- `ole32!CoTaskMemFree` at `0x1400ad482`
- `ole32!CoTaskMemFree` at `0x1400ad479`
- `ole32!CoTaskMemFree` at `0x1400ad482`
- `USER32!ShowWindow` at `0x1400acdad`
- `USER32!ShowWindow` at `0x1400acdad`
- `USER32!IsWindowEnabled` at `0x1400acc31`
- `USER32!IsWindowEnabled` at `0x1400acc31`
- `USER32!DestroyWindow` at `0x1400ae780`
- `USER32!DestroyWindow` at `0x1400ae780`
- `USER32!SetForegroundWindow` at `0x1400adba6`
- `USER32!SetForegroundWindow` at `0x1400adba6`
- `USER32!SetFocus` at `0x1400adbcd`
- `USER32!SetFocus` at `0x1400adbcd`
- `Mso98Win32Client!__imp_?HrStartTransaction@OCE@@YAJPEAUHWND__@@W4TransactionType@1@@Z` at `0x1400acc6a`
- `Mso98Win32Client!__imp_?HrStartTransaction@OCE@@YAJPEAUHWND__@@W4TransactionType@1@@Z` at `0x1400acc6a`
- `Mso98Win32Client!__imp_?MsoIsMainWindowVisible@@YAHPEAUHWND__@@@Z` at `0x1400ad5be`
- `Mso98Win32Client!__imp_?MsoIsMainWindowVisible@@YAHPEAUHWND__@@@Z` at `0x1400ad5be`
- `mso40uiWin32Client!__imp_?MsoStartupHwnd@@YAPEAUHWND__@@XZ` at `0x1400ae6a8`
- `mso40uiWin32Client!__imp_?MsoStartupHwnd@@YAPEAUHWND__@@XZ` at `0x1400ae6a8`
- `mso40uiWin32Client!__imp_?MsoFActiveSplash@@YA_NXZ` at `0x1400acc3f`
- `mso40uiWin32Client!__imp_?MsoFActiveSplash@@YA_NXZ` at `0x1400acc3f`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400acc77`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400acc77`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400ae2be`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400ae2be`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1400ad455`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1400ad455`
- `Mso20Win32Client!__imp_REFTRACK_AddRefEx` at `0x1400ae24b`
- `Mso20Win32Client!__imp_REFTRACK_AddRefEx` at `0x1400ae24b`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2b1`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2cb`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2d8`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2b1`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2cb`
- `Mso20Win32Client!__imp_?MsoRegDeleteValue@@YAJPEBU_msoreg@@@Z` at `0x1400ae2d8`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400ae2ea`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400ae49b`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400ae2ea`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400ae49b`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1400acb22`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1400acb22`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1400aceb2`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1400aceb2`

## pseudocode

```c

```
