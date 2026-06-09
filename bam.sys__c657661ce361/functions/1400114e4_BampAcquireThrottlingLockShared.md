# BampAcquireThrottlingLockShared

- ea: `0x1400114e4`
- end: `0x14001150f`
- name: `BampAcquireThrottlingLockShared`
- size: `43`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c5b0`
- `0x140010274`
- `0x14001202c`
- `0x140012eec`
- `0x140014648`
- `0x140014f90`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400114e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400114e8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400114fd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400114fd`

## pseudocode

```c
__int64 BampAcquireThrottlingLockShared()
{
  KeEnterCriticalRegion();
  return ExAcquirePushLockSharedEx(&BampThrottlingLock, 0);
}

```

## disassembly

```asm
0x1400114e4  sub     rsp, 28h
0x1400114e8  call    cs:__imp_KeEnterCriticalRegion
0x1400114ef  nop     dword ptr [rax+rax+00h]
0x1400114f4  xor     edx, edx
0x1400114f6  lea     rcx, BampThrottlingLock
0x1400114fd  call    cs:__imp_ExAcquirePushLockSharedEx
0x140011504  nop     dword ptr [rax+rax+00h]
0x140011509  add     rsp, 28h
0x14001150d  retn
```
