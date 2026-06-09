# BampReleaseTempBoostsLockExclusive

- ea: `0x14000be6c`
- end: `0x14000be97`
- name: `BampReleaseTempBoostsLockExclusive`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c18c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be85`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be79`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be79`

## pseudocode

```c
void BampReleaseTempBoostsLockExclusive()
{
  ExReleasePushLockExclusiveEx(&qword_140007630, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000be6c  sub     rsp, 28h
0x14000be70  xor     edx, edx
0x14000be72  lea     rcx, qword_140007630
0x14000be79  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000be80  nop     dword ptr [rax+rax+00h]
0x14000be85  call    cs:__imp_KeLeaveCriticalRegion
0x14000be8c  nop     dword ptr [rax+rax+00h]
0x14000be91  add     rsp, 28h
0x14000be95  retn
```
