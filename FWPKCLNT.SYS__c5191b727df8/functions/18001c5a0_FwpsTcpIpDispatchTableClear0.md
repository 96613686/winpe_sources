# FwpsTcpIpDispatchTableClear0

- ea: `0x18001c5a0`
- end: `0x18001c633`
- name: `FwpsTcpIpDispatchTableClear0`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180007a1c`
- `0x180007a98`
- `0x18001c5a0`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001c5cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18001c5cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18001c5fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18001c5fa`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c60d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18001c60d`

## pseudocode

```c
void *FwpsTcpIpDispatchTableClear0()
{
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  FwppL2WaitForIdle(&gFwpTcpIp);
  KeAcquireInStackQueuedSpinLock(&qword_1800482C0, &LockHandle);
  while ( (__int64 *)qword_1800482C8 != &qword_1800482C8 )
    FwppInjectSessionAbort(qword_1800482C8 - 8);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExDeleteNPagedLookasideList(&stru_180048240);
  return memset(qword_180048208, 0, 0x178u);
}

```

## disassembly

```asm
0x18001c5a0  sub     rsp, 48h
0x18001c5a4  xorps   xmm0, xmm0
0x18001c5a7  lea     rcx, gFwpTcpIp
0x18001c5ae  xor     eax, eax
0x18001c5b0  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x18001c5b5  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x18001c5ba  call    FwppL2WaitForIdle
0x18001c5bf  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x18001c5c4  lea     rcx, qword_1800482C0; SpinLock
0x18001c5cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x18001c5d2  nop     dword ptr [rax+rax+00h]
0x18001c5d7  mov     rcx, cs:qword_1800482C8
0x18001c5de  lea     rax, qword_1800482C8
0x18001c5e5  cmp     rcx, rax
0x18001c5e8  jz      short loc_18001C5F5
0x18001c5ea  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001c5ee  call    FwppInjectSessionAbort
0x18001c5f3  jmp     short loc_18001C5D7
0x18001c5f5  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x18001c5fa  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x18001c601  nop     dword ptr [rax+rax+00h]
0x18001c606  lea     rcx, stru_180048240; Lookaside
0x18001c60d  call    cs:__imp_ExDeleteNPagedLookasideList
0x18001c614  nop     dword ptr [rax+rax+00h]
0x18001c619  mov     rcx, cs:qword_180048208; void *
0x18001c620  xor     edx, edx; Val
0x18001c622  mov     r8d, 178h; Size
0x18001c628  call    memset
0x18001c62d  add     rsp, 48h
0x18001c631  retn
```
