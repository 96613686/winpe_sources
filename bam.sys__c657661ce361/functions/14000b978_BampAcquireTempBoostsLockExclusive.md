# BampAcquireTempBoostsLockExclusive

- ea: `0x14000b978`
- end: `0x14000b9a3`
- name: `BampAcquireTempBoostsLockExclusive`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c18c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b97c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b97c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b991`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b991`

## pseudocode

```c
__int64 BampAcquireTempBoostsLockExclusive()
{
  KeEnterCriticalRegion();
  return ExAcquirePushLockExclusiveEx(&qword_140007630, 0);
}

```

## disassembly

```asm
0x14000b978  sub     rsp, 28h
0x14000b97c  call    cs:__imp_KeEnterCriticalRegion
0x14000b983  nop     dword ptr [rax+rax+00h]
0x14000b988  xor     edx, edx
0x14000b98a  lea     rcx, qword_140007630
0x14000b991  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b998  nop     dword ptr [rax+rax+00h]
0x14000b99d  add     rsp, 28h
0x14000b9a1  retn
```
