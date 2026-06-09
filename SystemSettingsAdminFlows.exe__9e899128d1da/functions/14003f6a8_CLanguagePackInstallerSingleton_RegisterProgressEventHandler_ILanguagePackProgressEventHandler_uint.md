# CLanguagePackInstallerSingleton::RegisterProgressEventHandler(ILanguagePackProgressEventHandler *,uint *)

- ea: `0x14003f6a8`
- end: `0x14003f8c6`
- name: `?RegisterProgressEventHandler@CLanguagePackInstallerSingleton@@QEAAJPEAUILanguagePackProgressEventHandler@@PEAI@Z`
- size: `542`
- prototype: `__int64 __fastcall(CLanguagePackInstallerSingleton *__hidden this, struct ILanguagePackProgressEventHandler *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14003df90`

## callees

- `0x14000e624`
- `0x14001a27c`
- `0x14003e03c`
- `0x14003e75c`
- `0x14003f000`
- `0x14003f6a8`
- `0x1400406d4`
- `0x140041054`
- `0x14007d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14003f790`
- `KERNEL32!EnterCriticalSection` at `0x14003f790`
- `KERNEL32!TlsGetValue` at `0x14003f6d3`
- `KERNEL32!TlsGetValue` at `0x14003f6d3`
- `KERNEL32!TlsSetValue` at `0x14003f701`
- `KERNEL32!TlsSetValue` at `0x14003f701`

## pseudocode

```c

```
