# BampReleaseThrottlingLockExclusive

- ea: `0x140012c50`
- end: `0x140012c7b`
- name: `BampReleaseThrottlingLockExclusive`
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

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012c69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012c69`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012c5d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012c5d`

## pseudocode

```c
void BampReleaseThrottlingLockExclusive()
{
  ExReleasePushLockExclusiveEx(&BampThrottlingLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140012c50  sub     rsp, 28h
0x140012c54  xor     edx, edx
0x140012c56  lea     rcx, BampThrottlingLock
0x140012c5d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012c64  nop     dword ptr [rax+rax+00h]
0x140012c69  call    cs:__imp_KeLeaveCriticalRegion
0x140012c70  nop     dword ptr [rax+rax+00h]
0x140012c75  add     rsp, 28h
0x140012c79  retn
```
