# MpWatchDogCounters::CMpGenericMemoryCounter::ValidateAndUpdateCounterValue(MpWatchDog::ProcessInfo const *,unsigned __int64 *)

- ea: `0x1400dc0f0`
- end: `0x1400dc31c`
- name: `?ValidateAndUpdateCounterValue@CMpGenericMemoryCounter@MpWatchDogCounters@@IEAAXPEBVProcessInfo@MpWatchDog@@PEA_K@Z`
- size: `556`
- prototype: `void __fastcall(MpWatchDogCounters::CMpGenericMemoryCounter *__hidden this, const struct MpWatchDog::ProcessInfo *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400dbdd0`

## callees

- `0x140013ab0`
- `0x14003a5c0`
- `0x14008d178`
- `0x1400bb460`
- `0x1400dc0f0`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `KERNEL32!K32GetProcessMemoryInfo` at `0x1400dc1d8`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1400dc1d8`
- `KERNEL32!CloseHandle` at `0x1400dc26e`
- `KERNEL32!CloseHandle` at `0x1400dc26e`

## pseudocode

```c

```
