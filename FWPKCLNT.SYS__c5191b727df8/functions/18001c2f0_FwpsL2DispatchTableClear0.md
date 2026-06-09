# FwpsL2DispatchTableClear0

- ea: `0x18001c2f0`
- end: `0x18001c381`
- name: `FwpsL2DispatchTableClear0`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180007a1c`
- `0x180007a98`
- `0x18001c2f0`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001c31b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001c31b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18001c34a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18001c34a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c35d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c35d`

## pseudocode

```c
void *FwpsL2DispatchTableClear0()
{
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  FwppL2WaitForIdle(&gFwpL2);
  KeAcquireInStackQueuedSpinLock(&qword_1800481C0, &LockHandle);
  while ( (__int64 *)qword_1800481C8 != &qword_1800481C8 )
    FwppInjectSessionAbort(qword_1800481C8 - 8);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExDeleteNPagedLookasideList(&stru_180048140);
  return memset(qword_180048108, 0, 0x60u);
}

```

## disassembly

```asm
0x18001c2f0  sub     rsp, 48h
0x18001c2f4  xorps   xmm0, xmm0
0x18001c2f7  lea     rcx, gFwpL2
0x18001c2fe  xor     eax, eax
0x18001c300  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x18001c305  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x18001c30a  call    FwppL2WaitForIdle
0x18001c30f  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x18001c314  lea     rcx, qword_1800481C0; SpinLock
0x18001c31b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x18001c322  nop     dword ptr [rax+rax+00h]
0x18001c327  mov     rcx, cs:qword_1800481C8
0x18001c32e  lea     rax, qword_1800481C8
0x18001c335  cmp     rcx, rax
0x18001c338  jz      short loc_18001C345
0x18001c33a  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001c33e  call    FwppInjectSessionAbort
0x18001c343  jmp     short loc_18001C327
0x18001c345  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x18001c34a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x18001c351  nop     dword ptr [rax+rax+00h]
0x18001c356  lea     rcx, stru_180048140; Lookaside
0x18001c35d  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c364  nop     dword ptr [rax+rax+00h]
0x18001c369  mov     rcx, cs:qword_180048108; void *
0x18001c370  xor     edx, edx; Val
0x18001c372  lea     r8d, [rdx+60h]; Size
0x18001c376  call    memset
0x18001c37b  add     rsp, 48h
0x18001c37f  retn
```
