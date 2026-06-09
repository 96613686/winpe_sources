# CComponentBaselineHelper::GetPatchAddedComponentVersion(IMsiString const &,IMsiString const &,ulong *,ulong *)

- ea: `0x180205d3c`
- end: `0x180206143`
- name: `?GetPatchAddedComponentVersion@CComponentBaselineHelper@@AEAA_NAEBVIMsiString@@0PEAK1@Z`
- size: `1031`
- prototype: `bool __fastcall(CComponentBaselineHelper *__hidden this, const struct IMsiString *, const struct IMsiString *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cfb90`

## callees

- `0x180015950`
- `0x180019b60`
- `0x180019bb4`
- `0x18004295c`
- `0x18004b560`
- `0x180050cf0`
- `0x1800616e0`
- `0x1800629b4`
- `0x180079dd0`
- `0x1800ae018`
- `0x180205d3c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180205e10`
- `KERNEL32!InitializeCriticalSection` at `0x180205e33`
- `KERNEL32!InitializeCriticalSection` at `0x180205e10`
- `KERNEL32!InitializeCriticalSection` at `0x180205e33`
- `KERNEL32!GlobalFree` at `0x180206025`
- `KERNEL32!GlobalFree` at `0x180206043`
- `KERNEL32!GlobalFree` at `0x180206063`
- `KERNEL32!GlobalFree` at `0x18020607d`
- `KERNEL32!GlobalFree` at `0x1802060e7`
- `KERNEL32!GlobalFree` at `0x180206101`
- `KERNEL32!GlobalFree` at `0x180206025`
- `KERNEL32!GlobalFree` at `0x180206043`
- `KERNEL32!GlobalFree` at `0x180206063`
- `KERNEL32!GlobalFree` at `0x18020607d`
- `KERNEL32!GlobalFree` at `0x1802060e7`
- `KERNEL32!GlobalFree` at `0x180206101`

## string_xrefs

- `0x180205f6b`: `ComponentVersion`

## pseudocode

```c

```
