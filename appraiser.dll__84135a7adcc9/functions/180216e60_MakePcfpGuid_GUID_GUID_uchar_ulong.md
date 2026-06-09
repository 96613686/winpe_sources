# MakePcfpGuid(_GUID *,_GUID *,uchar *,ulong)

- ea: `0x180216e60`
- end: `0x180217095`
- name: `?MakePcfpGuid@@YAJPEAU_GUID@@0PEAEK@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct _GUID *, PUCHAR pbInput, PUCHAR, ULONG cbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180216a8c`

## callees

- `0x18000a927`
- `0x180216e60`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180216f03`
- `KERNEL32!GetProcessHeap` at `0x180216fd7`
- `KERNEL32!GetProcessHeap` at `0x18021702d`
- `KERNEL32!GetProcessHeap` at `0x18021705d`
- `KERNEL32!GetProcessHeap` at `0x180216f03`
- `KERNEL32!GetProcessHeap` at `0x180216fd7`
- `KERNEL32!GetProcessHeap` at `0x18021702d`
- `KERNEL32!GetProcessHeap` at `0x18021705d`
- `KERNEL32!HeapAlloc` at `0x180216f11`
- `KERNEL32!HeapAlloc` at `0x180216fe5`
- `KERNEL32!HeapAlloc` at `0x180216f11`
- `KERNEL32!HeapAlloc` at `0x180216fe5`
- `KERNEL32!HeapFree` at `0x18021703b`
- `KERNEL32!HeapFree` at `0x18021706b`
- `KERNEL32!HeapFree` at `0x18021703b`
- `KERNEL32!HeapFree` at `0x18021706b`
- `bcrypt!BCryptDestroyHash` at `0x18021704a`
- `bcrypt!BCryptDestroyHash` at `0x18021704a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180216eba`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180216eba`
- `bcrypt!BCryptGetProperty` at `0x180216ef0`
- `bcrypt!BCryptGetProperty` at `0x180216fc8`
- `bcrypt!BCryptGetProperty` at `0x180216ef0`
- `bcrypt!BCryptGetProperty` at `0x180216fc8`
- `bcrypt!BCryptHashData` at `0x180216f72`
- `bcrypt!BCryptHashData` at `0x180216f94`
- `bcrypt!BCryptHashData` at `0x180216f72`
- `bcrypt!BCryptHashData` at `0x180216f94`
- `bcrypt!BCryptFinishHash` at `0x180217005`
- `bcrypt!BCryptFinishHash` at `0x180217005`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18021707c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18021707c`
- `bcrypt!BCryptCreateHash` at `0x180216f51`
- `bcrypt!BCryptCreateHash` at `0x180216f51`

## pseudocode

```c

```
