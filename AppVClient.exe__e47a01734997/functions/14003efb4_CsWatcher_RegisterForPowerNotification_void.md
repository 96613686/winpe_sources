# CsWatcher::RegisterForPowerNotification(void *)

- ea: `0x14003efb4`
- end: `0x14003f1fb`
- name: `?RegisterForPowerNotification@CsWatcher@@QEAA_KPEAX@Z`
- size: `583`
- prototype: `unsigned __int64 __fastcall(CsWatcher *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000f3b4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140018bec`
- `0x14003efb4`
- `0x140040b48`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14003f0ef`
- `KERNEL32!GetProcAddress` at `0x14003f0ef`
- `KERNEL32!FreeLibrary` at `0x14003f07a`
- `KERNEL32!FreeLibrary` at `0x14003f15a`
- `KERNEL32!FreeLibrary` at `0x14003f07a`
- `KERNEL32!FreeLibrary` at `0x14003f15a`
- `KERNEL32!GetLastError` at `0x14003f0ce`
- `KERNEL32!GetLastError` at `0x14003f131`
- `KERNEL32!GetLastError` at `0x14003f1ba`
- `KERNEL32!GetLastError` at `0x14003f0ce`
- `KERNEL32!GetLastError` at `0x14003f131`
- `KERNEL32!GetLastError` at `0x14003f1ba`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003efe7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f0a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f104`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f18d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003efe7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f0a1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f104`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003f18d`

## string_xrefs

- `0x14003f045`: `User32.dll`

## pseudocode

```c

```
