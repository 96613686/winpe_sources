# USBSTOR_SyncCompletionRoutine

- ea: `0x14000c6e0`
- end: `0x14000c7b0`
- name: `USBSTOR_SyncCompletionRoutine`
- size: `208`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000c6e0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000c788`
- `ntoskrnl!KeSetEvent` at `0x14000c788`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c71a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000c71a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c774`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000c774`

## pseudocode

```c
__int64 __fastcall USBSTOR_SyncCompletionRoutine(PDEVICE_OBJECT DeviceObject, PIRP Irp, struct _KEVENT *Context)
{
  __int64 Status; // rbx
  __int64 v7; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    Status = Irp->IoStatus.Status;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 542262099;
    *(_QWORD *)(qword_14001A190 + 8) = DeviceObject;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = Status;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v7 = qword_14001A198 - 32;
    else
      v7 = qword_14001A190 - 32;
    qword_14001A190 = v7;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  KeSetEvent(Context, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000c6e0  push    rbx
0x14000c6e2  push    rbp
0x14000c6e3  push    rsi
0x14000c6e4  push    rdi
0x14000c6e5  sub     rsp, 48h
0x14000c6e9  xor     eax, eax
0x14000c6eb  xorps   xmm0, xmm0
0x14000c6ee  cmp     cs:P, rax
0x14000c6f5  mov     rdi, r8
0x14000c6f8  mov     rsi, rdx
0x14000c6fb  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14000c700  mov     rbp, rcx
0x14000c703  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14000c708  jz      short loc_14000C780
0x14000c70a  movsxd  rbx, dword ptr [rdx+30h]
0x14000c70e  lea     rcx, SpinLock; SpinLock
0x14000c715  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x14000c71a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000c721  nop     dword ptr [rax+rax+00h]
0x14000c726  mov     rax, cs:qword_14001A190
0x14000c72d  mov     dword ptr [rax], 20524353h
0x14000c733  mov     rax, cs:qword_14001A190
0x14000c73a  mov     [rax+8], rbp
0x14000c73e  mov     rax, cs:qword_14001A190
0x14000c745  mov     [rax+10h], rsi
0x14000c749  mov     rax, cs:qword_14001A190
0x14000c750  mov     [rax+18h], rbx
0x14000c754  mov     rax, cs:qword_14001A190
0x14000c75b  cmp     rax, cs:P
0x14000c762  jbe     short loc_14000C7A3
0x14000c764  sub     rax, 20h ; ' '
0x14000c768  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14000c76d  mov     cs:qword_14001A190, rax
0x14000c774  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000c77b  nop     dword ptr [rax+rax+00h]
0x14000c780  xor     r8d, r8d; Wait
0x14000c783  xor     edx, edx; Increment
0x14000c785  mov     rcx, rdi; Event
0x14000c788  call    cs:__imp_KeSetEvent
0x14000c78f  nop     dword ptr [rax+rax+00h]
0x14000c794  mov     eax, 0C0000016h
0x14000c799  add     rsp, 48h
0x14000c79d  pop     rdi
0x14000c79e  pop     rsi
0x14000c79f  pop     rbp
0x14000c7a0  pop     rbx
0x14000c7a1  retn
0x14000c7a3  mov     rax, cs:qword_14001A198
0x14000c7aa  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000c7ae  jmp     short loc_14000C768
```
