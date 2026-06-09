# BampReleaseThrottlingWorkerLock

- ea: `0x1400113f0`
- end: `0x140011426`
- name: `BampReleaseThrottlingWorkerLock`
- size: `54`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b008`
- `0x14000b2f0`
- `0x14000c18c`
- `0x14000c83c`
- `0x14000c990`
- `0x14000ce58`
- `0x140010274`
- `0x140010308`
- `0x1400110d8`
- `0x14001474c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011414`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011414`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011408`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011408`

## pseudocode

```c
void BampReleaseThrottlingWorkerLock()
{
  qword_140007590 = 0;
  ExReleasePushLockExclusiveEx(&qword_140007588, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400113f0  sub     rsp, 28h
0x1400113f4  xor     edx, edx
0x1400113f6  mov     cs:qword_140007590, 0
0x140011401  lea     rcx, qword_140007588
0x140011408  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001140f  nop     dword ptr [rax+rax+00h]
0x140011414  call    cs:__imp_KeLeaveCriticalRegion
0x14001141b  nop     dword ptr [rax+rax+00h]
0x140011420  add     rsp, 28h
0x140011424  retn
```
