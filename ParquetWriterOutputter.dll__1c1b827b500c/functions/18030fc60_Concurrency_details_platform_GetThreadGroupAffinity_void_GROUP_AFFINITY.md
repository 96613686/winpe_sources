# Concurrency::details::platform::__GetThreadGroupAffinity(void *,_GROUP_AFFINITY *)

- ea: `0x18030fc60`
- end: `0x18030fccb`
- name: `?__GetThreadGroupAffinity@platform@details@Concurrency@@YAHPEAXPEAU_GROUP_AFFINITY@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(Concurrency::details::platform *__hidden this, void *, struct _GROUP_AFFINITY *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180310584`

## callees

- `0x18030fc60`
- `0x18030fec8`
- `0x180312b78`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18030fc94`
- `KERNEL32!GetCurrentProcess` at `0x18030fc94`
- `KERNEL32!GetProcessAffinityMask` at `0x18030fca7`
- `KERNEL32!GetProcessAffinityMask` at `0x18030fca7`

## pseudocode

```c

```
