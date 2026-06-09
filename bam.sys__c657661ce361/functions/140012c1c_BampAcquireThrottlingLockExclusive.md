# BampAcquireThrottlingLockExclusive

- ea: `0x140012c1c`
- end: `0x140012c47`
- name: `BampAcquireThrottlingLockExclusive`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c83c`
- `0x140012450`
- `0x14001474c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140012c20`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012c20`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012c35`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012c35`

## pseudocode

```c
__int64 BampAcquireThrottlingLockExclusive()
{
  KeEnterCriticalRegion();
  return ExAcquirePushLockExclusiveEx(&BampThrottlingLock, 0);
}

```

## disassembly

```asm
0x140012c1c  sub     rsp, 28h
0x140012c20  call    cs:__imp_KeEnterCriticalRegion
0x140012c27  nop     dword ptr [rax+rax+00h]
0x140012c2c  xor     edx, edx
0x140012c2e  lea     rcx, BampThrottlingLock
0x140012c35  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012c3c  nop     dword ptr [rax+rax+00h]
0x140012c41  add     rsp, 28h
0x140012c45  retn
```
