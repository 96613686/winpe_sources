# BampReleaseThrottlingLockShared

- ea: `0x1400102d4`
- end: `0x1400102ff`
- name: `BampReleaseThrottlingLockShared`
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

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400102e1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400102e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400102ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400102ed`

## pseudocode

```c
void BampReleaseThrottlingLockShared()
{
  ExReleasePushLockSharedEx(&BampThrottlingLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400102d4  sub     rsp, 28h
0x1400102d8  xor     edx, edx
0x1400102da  lea     rcx, BampThrottlingLock
0x1400102e1  call    cs:__imp_ExReleasePushLockSharedEx
0x1400102e8  nop     dword ptr [rax+rax+00h]
0x1400102ed  call    cs:__imp_KeLeaveCriticalRegion
0x1400102f4  nop     dword ptr [rax+rax+00h]
0x1400102f9  add     rsp, 28h
0x1400102fd  retn
```
