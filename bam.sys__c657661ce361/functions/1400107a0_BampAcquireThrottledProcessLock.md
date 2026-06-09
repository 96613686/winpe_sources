# BampAcquireThrottledProcessLock

- ea: `0x1400107a0`
- end: `0x1400107db`
- name: `BampAcquireThrottledProcessLock`
- size: `59`
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

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400107a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400107a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400107bb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400107bb`

## pseudocode

```c
struct _KTHREAD *__fastcall BampAcquireThrottledProcessLock(__int64 a1)
{
  struct _KTHREAD *result; // rax

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 16, 0);
  result = KeGetCurrentThread();
  *(_QWORD *)(a1 + 24) = result;
  return result;
}

```

## disassembly

```asm
0x1400107a0  push    rbx
0x1400107a2  sub     rsp, 20h
0x1400107a6  mov     rbx, rcx
0x1400107a9  call    cs:__imp_KeEnterCriticalRegion
0x1400107b0  nop     dword ptr [rax+rax+00h]
0x1400107b5  lea     rcx, [rbx+10h]
0x1400107b9  xor     edx, edx
0x1400107bb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400107c2  nop     dword ptr [rax+rax+00h]
0x1400107c7  mov     rax, gs:188h
0x1400107d0  mov     [rbx+18h], rax
0x1400107d4  add     rsp, 20h
0x1400107d8  pop     rbx
0x1400107d9  retn
```
