# Art::TextLayoutRichEditImpl::GetRectanglesOfRange(Art::TextRange const &,Ofc::TArray<GEL::Rect> &,bool,bool)

- ea: `0x1801b4690`
- end: `0x1801b4dfe`
- name: `?GetRectanglesOfRange@TextLayoutRichEditImpl@Art@@UEBAXAEBUTextRange@2@AEAV?$TArray@URect@GEL@@@Ofc@@_N2@Z`
- size: `1902`
- prototype: `__int64 __usercall@<rax>(Art::TextLayoutRichEditImpl *this@<rcx>, struct Art::TextRange *@<rdx>, char)`
- caller_count: `3`
- callee_count: `17`
- tags: ``

## callers

- `0x180190930`
- `0x1801b34b0`
- `0x1803bba70`

## callees

- `0x180006390`
- `0x180019a9c`
- `0x18009767c`
- `0x1800b98d0`
- `0x1800d0e74`
- `0x1800f9cc0`
- `0x1801b4690`
- `0x180239330`
- `0x180277090`
- `0x180279030`
- `0x180279050`
- `0x1802c8bdc`
- `0x18032e130`
- `0x1803bc890`
- `0x1804599f0`
- `0x1806bc4f0`
- `0x18097912c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801b471b`
- `KERNEL32!GetCurrentThreadId` at `0x1801b471b`
- `KERNEL32!ResetEvent` at `0x1801b4bb0`
- `KERNEL32!ResetEvent` at `0x1801b4bb0`
- `KERNEL32!SetEvent` at `0x1801b4d6e`
- `KERNEL32!SetEvent` at `0x1801b4d6e`
- `KERNEL32!WaitForSingleObjectEx` at `0x1801b4bd4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1801b4bd4`
- `MSVCP140!_Mtx_unlock` at `0x1801b4794`
- `MSVCP140!_Mtx_unlock` at `0x1801b4b73`
- `MSVCP140!_Mtx_unlock` at `0x1801b4bc0`
- `MSVCP140!_Mtx_unlock` at `0x1801b4794`
- `MSVCP140!_Mtx_unlock` at `0x1801b4b73`
- `MSVCP140!_Mtx_unlock` at `0x1801b4bc0`
- `MSVCP140!_Mtx_lock` at `0x1801b4732`
- `MSVCP140!_Mtx_lock` at `0x1801b4ab3`
- `MSVCP140!_Mtx_lock` at `0x1801b4732`
- `MSVCP140!_Mtx_lock` at `0x1801b4ab3`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4bf5`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c01`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c14`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c20`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4bf5`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c01`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c14`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801b4c20`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4d7e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4d94`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4daa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4ddb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4d7e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4d94`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4daa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801b4ddb`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801b4907`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801b4907`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1801b496c`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1801b496c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b49a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b4cb3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b4dc8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b49a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b4cb3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801b4dc8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801b4a0e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801b4a0e`

## pseudocode

```c

```
