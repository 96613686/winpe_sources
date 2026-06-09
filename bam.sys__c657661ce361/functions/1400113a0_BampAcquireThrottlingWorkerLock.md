# BampAcquireThrottlingWorkerLock

- ea: `0x1400113a0`
- end: `0x1400113db`
- name: `BampAcquireThrottlingWorkerLock`
- size: `59`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b008`
- `0x14000b2f0`
- `0x14000c18c`
- `0x14000c83c`
- `0x14000c990`
- `0x14000ce58`
- `0x14000f280`
- `0x1400100b0`
- `0x140010274`
- `0x140010308`
- `0x140010990`
- `0x1400110d8`
- `0x14001474c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400113a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400113a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400113b9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400113b9`

## pseudocode

```c
struct _KTHREAD *BampAcquireThrottlingWorkerLock()
{
  struct _KTHREAD *result; // rax

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&qword_140007588, 0);
  result = KeGetCurrentThread();
  qword_140007590 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x1400113a0  sub     rsp, 28h
0x1400113a4  call    cs:__imp_KeEnterCriticalRegion
0x1400113ab  nop     dword ptr [rax+rax+00h]
0x1400113b0  xor     edx, edx
0x1400113b2  lea     rcx, qword_140007588
0x1400113b9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400113c0  nop     dword ptr [rax+rax+00h]
0x1400113c5  mov     rax, gs:188h
0x1400113ce  mov     cs:qword_140007590, rax
0x1400113d5  add     rsp, 28h
0x1400113d9  retn
```
