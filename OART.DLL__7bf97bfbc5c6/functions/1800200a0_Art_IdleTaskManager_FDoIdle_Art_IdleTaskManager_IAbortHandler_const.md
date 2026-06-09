# Art::IdleTaskManager::FDoIdle(Art::IdleTaskManager::IAbortHandler const &)

- ea: `0x1800200a0`
- end: `0x180020ad1`
- name: `?FDoIdle@IdleTaskManager@Art@@QEAA_NAEBVIAbortHandler@12@@Z`
- size: `2609`
- prototype: `bool __fastcall(Art::IdleTaskManager *__hidden this, const struct Art::IdleTaskManager::IAbortHandler *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x18001e680`

## callees

- `0x18000ded0`
- `0x18001fdc0`
- `0x1800200a0`
- `0x180020ad4`
- `0x180020b04`
- `0x180020cd0`
- `0x180024a90`
- `0x180037400`
- `0x1800454d0`
- `0x180065990`
- `0x18006a868`
- `0x18006d020`
- `0x180070fe0`
- `0x180071720`
- `0x1800a241c`
- `0x18020df88`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a59d4`
- `0x1806a5c5c`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180020281`
- `KERNEL32!GetTickCount64` at `0x1800202bf`
- `KERNEL32!GetTickCount64` at `0x18002033f`
- `KERNEL32!GetTickCount64` at `0x180020281`
- `KERNEL32!GetTickCount64` at `0x1800202bf`
- `KERNEL32!GetTickCount64` at `0x18002033f`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180020483`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x180020483`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1800204ed`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x1800204ed`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180020840`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18002084e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180020aae`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180020840`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18002084e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180020aae`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180020631`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180020631`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1800208b2`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180020923`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1800208b2`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180020923`

## string_xrefs

- `0x18002098f`: `iTask out of range`
- `0x180020947`: `iTask`
- `0x180020155`: `Task Count`
- `0x18002019c`: `Running tasks list is not empty.`

## pseudocode

```c

```
