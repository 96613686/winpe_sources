# MpWatchDog::CheckCoreSvcDevMode

- ea: `0x1400814f4`
- end: `0x1400816a3`
- name: `MpWatchDog::CheckCoreSvcDevMode`
- size: `431`
- prototype: `bool __fastcall(__int64, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400833d4`

## callees

- `0x14000b630`
- `0x14000b66c`
- `0x14000db9c`
- `0x140013110`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400814f4`
- `0x1400f4ea8`
- `0x1400f5268`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400815b6`
- `KERNEL32!CloseHandle` at `0x14008167c`
- `KERNEL32!CloseHandle` at `0x1400815b6`
- `KERNEL32!CloseHandle` at `0x14008167c`
- `KERNEL32!FreeLibrary` at `0x140081628`
- `KERNEL32!FreeLibrary` at `0x140081628`

## string_xrefs

- `0x140081522`: `MsMpLics.dll`

## pseudocode

```c

```
