# Art::TextLayoutRichEditImpl::GetRectanglesOfRange(Art::TextRange const &,Ofc::TArray<GEL::Rect> &,bool,bool)

- ea: `0x180274c30`
- end: `0x1802753c4`
- name: `?GetRectanglesOfRange@TextLayoutRichEditImpl@Art@@UEBAXAEBUTextRange@2@AEAV?$TArray@URect@GEL@@@Ofc@@_N2@Z`
- size: `1940`
- prototype: `__int64 __usercall@<rax>(Art::TextLayoutRichEditImpl *this@<rcx>, struct Art::TextRange *@<rdx>, char)`
- caller_count: `3`
- callee_count: `17`
- tags: ``

## callers

- `0x1801680c0`
- `0x180274890`
- `0x180274a10`

## callees

- `0x180037610`
- `0x18006d020`
- `0x18006d0d0`
- `0x180070fe0`
- `0x180071720`
- `0x18008f8d0`
- `0x1800902e8`
- `0x1800df110`
- `0x18016b110`
- `0x18016c960`
- `0x1801ed08c`
- `0x180274c30`
- `0x1802753c4`
- `0x1802755f4`
- `0x180275a78`
- `0x1806a5084`
- `0x18096d83c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180274cbb`
- `KERNEL32!GetCurrentThreadId` at `0x180274cbb`
- `KERNEL32!ResetEvent` at `0x180274fc7`
- `KERNEL32!ResetEvent` at `0x180274fc7`
- `KERNEL32!SetEvent` at `0x180275337`
- `KERNEL32!SetEvent` at `0x180275337`
- `KERNEL32!WaitForSingleObjectEx` at `0x180274feb`
- `KERNEL32!WaitForSingleObjectEx` at `0x180274feb`
- `MSVCP140!_Mtx_unlock` at `0x180274d34`
- `MSVCP140!_Mtx_unlock` at `0x180274fd7`
- `MSVCP140!_Mtx_unlock` at `0x18027518e`
- `MSVCP140!_Mtx_unlock` at `0x180274d34`
- `MSVCP140!_Mtx_unlock` at `0x180274fd7`
- `MSVCP140!_Mtx_unlock` at `0x18027518e`
- `MSVCP140!_Mtx_lock` at `0x180274cd2`
- `MSVCP140!_Mtx_lock` at `0x1802750ce`
- `MSVCP140!_Mtx_lock` at `0x180274cd2`
- `MSVCP140!_Mtx_lock` at `0x1802750ce`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180274fa0`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180274fac`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1802751dd`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1802751e9`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180274fa0`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180274fac`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1802751dd`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1802751e9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180275347`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18027535d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180275373`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802753a1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180275347`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18027535d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180275373`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802753a1`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180274ea3`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180274ea3`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x180274f08`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x180274f08`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180274f3e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18027527c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18027538e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180274f3e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18027527c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18027538e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180275023`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180275023`

## pseudocode

```c

```
