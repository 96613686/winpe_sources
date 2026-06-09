# BampReleaseThrottledProcessLock

- ea: `0x140010760`
- end: `0x140010790`
- name: `BampReleaseThrottledProcessLock`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c3f0`
- `0x14000c6f0`
- `0x14000c990`
- `0x140010308`
- `0x14001044c`
- `0x1400105b0`
- `0x1400108a8`
- `0x14001202c`
- `0x140012eec`
- `0x140014180`
- `0x140014648`
- `0x14001474c`
- `0x140014f90`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001077e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001077e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010772`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010772`

## pseudocode

```c
void __fastcall BampReleaseThrottledProcessLock(__int64 a1)
{
  *(_QWORD *)(a1 + 24) = 0;
  ExReleasePushLockExclusiveEx(a1 + 16, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140010760  sub     rsp, 28h
0x140010764  mov     qword ptr [rcx+18h], 0
0x14001076c  xor     edx, edx
0x14001076e  add     rcx, 10h
0x140010772  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010779  nop     dword ptr [rax+rax+00h]
0x14001077e  call    cs:__imp_KeLeaveCriticalRegion
0x140010785  nop     dword ptr [rax+rax+00h]
0x14001078a  add     rsp, 28h
0x14001078e  retn
```
