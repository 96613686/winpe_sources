# USBSTOR_SyncSendUsbRequest

- ea: `0x140001950`
- end: `0x140001dd8`
- name: `USBSTOR_SyncSendUsbRequest`
- size: `1160`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400012d0`
- `0x140001510`
- `0x140020f40`
- `0x140026cec`
- `0x1400279c0`
- `0x140027f04`

## callees

- `0x140001950`
- `0x140003630`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x140001d6f`
- `ntoskrnl!IoCancelIrp` at `0x140001d6f`
- `ntoskrnl!IoFreeIrp` at `0x140001ab3`
- `ntoskrnl!IoFreeIrp` at `0x140001ab3`
- `ntoskrnl!IofCallDriver` at `0x140001a97`
- `ntoskrnl!IofCallDriver` at `0x140001a97`
- `ntoskrnl!KeInitializeEvent` at `0x1400019a4`
- `ntoskrnl!KeInitializeEvent` at `0x1400019a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c38`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d8c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c38`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d8c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400019ea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001ae4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001bb2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001c74`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400019ea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001ae4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001bb2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001c74`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001a47`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001b44`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001c0f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001ccd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001a47`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001b44`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001c0f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001ccd`
- `ntoskrnl!IoAllocateIrp` at `0x1400019ba`
- `ntoskrnl!IoAllocateIrp` at `0x1400019ba`

## pseudocode

```c
__int64 __fastcall USBSTOR_SyncSendUsbRequest(__int64 a1, ULONG_PTR a2)
{
  __int64 v4; // r14
  PIRP Irp; // rbx
  __int64 v6; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  NTSTATUS Status; // edi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v13; // rdi
  __int64 v14; // rax
  NTSTATUS v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rax
  _KEVENT Event; // [rsp+30h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-18h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+90h] [rbp+30h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x99u,
      (__int64)WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  v4 = *(_QWORD *)(a1 + 64);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v4 + 24) + 76LL), 0);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1381323603;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = a2;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v6 = qword_14001A198 - 32;
    else
      v6 = qword_14001A190 - 32;
    qword_14001A190 = v6;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( !Irp )
    return 3221225626LL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = a2;
  v8 = Irp->Tail.Overlay.CurrentStackLocation;
  v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_SyncCompletionRoutine;
  v8[-1].Context = &Event;
  v8[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v4 + 24), Irp);
  if ( Status == 259 )
  {
    Timeout.QuadPart = 0;
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      v13 = *(_QWORD *)(v4 + 24);
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1886745459;
      *(_QWORD *)(qword_14001A190 + 8) = v13;
      *(_QWORD *)(qword_14001A190 + 16) = Irp;
      *(_QWORD *)(qword_14001A190 + 24) = 0;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v14 = qword_14001A198 - 32;
      else
        v14 = qword_14001A190 - 32;
      qword_14001A190 = v14;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    Timeout.QuadPart = -50000000;
    v15 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
    v16 = *(_QWORD *)(v4 + 24);
    if ( v15 == 258 )
    {
      USBSTOR_LogEntry(829715315, *(_QWORD *)(v4 + 24), (__int64)Irp, 0);
      Status = -1073741643;
      IoCancelIrp(Irp);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      USBSTOR_LogEntry(846492531, *(_QWORD *)(v4 + 24), (__int64)Irp, 0);
    }
    else
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1668641651;
        *(_QWORD *)(qword_14001A190 + 8) = v16;
        *(_QWORD *)(qword_14001A190 + 16) = Irp;
        *(_QWORD *)(qword_14001A190 + 24) = 0;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v17 = qword_14001A198 - 32;
        else
          v17 = qword_14001A190 - 32;
        qword_14001A190 = v17;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      Status = Irp->IoStatus.Status;
    }
  }
  IoFreeIrp(Irp);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v10 = *(int *)(a2 + 4);
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1920299891;
    *(_QWORD *)(qword_14001A190 + 8) = Status;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = v10;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v11 = qword_14001A198 - 32;
    else
      v11 = qword_14001A190 - 32;
    qword_14001A190 = v11;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x9Au,
      (__int64)WPP_354602438fa331ce245c005e63ec86c9_Traceguids,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140001950  mov     [rsp-28h+arg_10], rbx
0x140001955  push    rbp
0x140001956  push    rsi
0x140001957  push    rdi
0x140001958  push    r14
0x14000195a  push    r15
0x14000195c  mov     rbp, rsp
0x14000195f  sub     rsp, 60h
0x140001963  xorps   xmm0, xmm0
0x140001966  xor     eax, eax
0x140001968  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14000196c  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x140001970  mov     rsi, rdx
0x140001973  mov     rdi, rcx
0x140001976  mov     rcx, cs:WPP_GLOBAL_Control
0x14000197d  lea     r15, WPP_GLOBAL_Control
0x140001984  cmp     rcx, r15
0x140001987  jz      short loc_140001994
0x140001989  mov     eax, [rcx+2Ch]
0x14000198c  test    al, 1
0x14000198e  jnz     loc_140001D30
0x140001994  mov     r14, [rdi+40h]
0x140001998  lea     rcx, [rbp+Event]; Event
0x14000199c  xor     r8d, r8d; State
0x14000199f  mov     edx, 1; Type
0x1400019a4  call    cs:__imp_KeInitializeEvent
0x1400019ab  nop     dword ptr [rax+rax+00h]
0x1400019b0  mov     rcx, [r14+18h]
0x1400019b4  xor     edx, edx; ChargeQuota
0x1400019b6  movzx   ecx, byte ptr [rcx+4Ch]; StackSize
0x1400019ba  call    cs:__imp_IoAllocateIrp
0x1400019c1  nop     dword ptr [rax+rax+00h]
0x1400019c6  mov     rbx, rax
0x1400019c9  xorps   xmm0, xmm0
0x1400019cc  xor     eax, eax
0x1400019ce  cmp     cs:P, rax
0x1400019d5  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400019d9  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400019dd  jz      short loc_140001A53
0x1400019df  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400019e3  lea     rcx, SpinLock; SpinLock
0x1400019ea  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400019f1  nop     dword ptr [rax+rax+00h]
0x1400019f6  mov     rax, cs:qword_14001A190
0x1400019fd  mov     dword ptr [rax], 52555353h
0x140001a03  mov     rax, cs:qword_14001A190
0x140001a0a  mov     [rax+8], rdi
0x140001a0e  mov     rax, cs:qword_14001A190
0x140001a15  mov     [rax+10h], rbx
0x140001a19  mov     rax, cs:qword_14001A190
0x140001a20  mov     [rax+18h], rsi
0x140001a24  mov     rax, cs:qword_14001A190
0x140001a2b  cmp     rax, cs:P
0x140001a32  jbe     loc_140001CF3
0x140001a38  sub     rax, 20h ; ' '
0x140001a3c  lea     rcx, [rbp+LockHandle]; LockHandle
0x140001a40  mov     cs:qword_14001A190, rax
0x140001a47  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001a4e  nop     dword ptr [rax+rax+00h]
0x140001a53  test    rbx, rbx
0x140001a56  jz      loc_140001CE9
0x140001a5c  mov     rax, [rbx+0B8h]
0x140001a63  lea     rcx, USBSTOR_SyncCompletionRoutine
0x140001a6a  mov     rdx, rbx; Irp
0x140001a6d  mov     byte ptr [rax-48h], 0Fh
0x140001a71  mov     dword ptr [rax-30h], 220003h
0x140001a78  mov     [rax-40h], rsi
0x140001a7c  mov     rax, [rbx+0B8h]
0x140001a83  mov     [rax-10h], rcx
0x140001a87  lea     rcx, [rbp+Event]
0x140001a8b  mov     [rax-8], rcx
0x140001a8f  mov     byte ptr [rax-45h], 0E0h
0x140001a93  mov     rcx, [r14+18h]; DeviceObject
0x140001a97  call    cs:__imp_IofCallDriver
0x140001a9e  nop     dword ptr [rax+rax+00h]
0x140001aa3  mov     edi, eax
0x140001aa5  cmp     eax, 103h
0x140001aaa  jz      loc_140001B7E
0x140001ab0  mov     rcx, rbx; Irp
0x140001ab3  call    cs:__imp_IoFreeIrp
0x140001aba  nop     dword ptr [rax+rax+00h]
0x140001abf  xor     eax, eax
0x140001ac1  xorps   xmm0, xmm0
0x140001ac4  cmp     cs:P, rax
0x140001acb  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140001acf  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140001ad3  jz      short loc_140001B50
0x140001ad5  movsxd  rbx, dword ptr [rsi+4]
0x140001ad9  lea     rdx, [rbp+LockHandle]; LockHandle
0x140001add  lea     rcx, SpinLock; SpinLock
0x140001ae4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001aeb  nop     dword ptr [rax+rax+00h]
0x140001af0  mov     rax, cs:qword_14001A190
0x140001af7  movsxd  rcx, edi
0x140001afa  mov     dword ptr [rax], 72757373h
0x140001b00  mov     rax, cs:qword_14001A190
0x140001b07  mov     [rax+8], rcx
0x140001b0b  mov     rax, cs:qword_14001A190
0x140001b12  mov     [rax+10h], rsi
0x140001b16  mov     rax, cs:qword_14001A190
0x140001b1d  mov     [rax+18h], rbx
0x140001b21  mov     rax, cs:qword_14001A190
0x140001b28  cmp     rax, cs:P
0x140001b2f  jbe     loc_140001D03
0x140001b35  sub     rax, 20h ; ' '
0x140001b39  lea     rcx, [rbp+LockHandle]; LockHandle
0x140001b3d  mov     cs:qword_14001A190, rax
0x140001b44  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001b4b  nop     dword ptr [rax+rax+00h]
0x140001b50  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b57  cmp     rcx, r15
0x140001b5a  jz      short loc_140001B67
0x140001b5c  mov     eax, [rcx+2Ch]
0x140001b5f  test    al, 1
0x140001b61  jnz     loc_140001DB1
0x140001b67  mov     eax, edi
0x140001b69  mov     rbx, [rsp+60h+arg_10]
0x140001b71  add     rsp, 60h
0x140001b75  pop     r15
0x140001b77  pop     r14
0x140001b79  pop     rdi
0x140001b7a  pop     rsi
0x140001b7b  pop     rbp
0x140001b7c  retn
0x140001b7e  xor     eax, eax
0x140001b80  mov     [rsp+60h+arg_8], r12
0x140001b88  xor     r12d, r12d
0x140001b8b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140001b8f  cmp     cs:P, rax
0x140001b96  xorps   xmm0, xmm0
0x140001b99  mov     qword ptr [rbp+arg_0], r12
0x140001b9d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140001ba1  jz      short loc_140001C1B
0x140001ba3  mov     rdi, [r14+18h]
0x140001ba7  lea     rdx, [rbp+LockHandle]; LockHandle
0x140001bab  lea     rcx, SpinLock; SpinLock
0x140001bb2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001bb9  nop     dword ptr [rax+rax+00h]
0x140001bbe  mov     rax, cs:qword_14001A190
0x140001bc5  mov     dword ptr [rax], 70757373h
0x140001bcb  mov     rax, cs:qword_14001A190
0x140001bd2  mov     [rax+8], rdi
0x140001bd6  mov     rax, cs:qword_14001A190
0x140001bdd  mov     [rax+10h], rbx
0x140001be1  mov     rax, cs:qword_14001A190
0x140001be8  mov     [rax+18h], r12
0x140001bec  mov     rax, cs:qword_14001A190
0x140001bf3  cmp     rax, cs:P
0x140001bfa  jbe     loc_140001D13
0x140001c00  sub     rax, 20h ; ' '
0x140001c04  lea     rcx, [rbp+LockHandle]; LockHandle
0x140001c08  mov     cs:qword_14001A190, rax
0x140001c0f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001c16  nop     dword ptr [rax+rax+00h]
0x140001c1b  lea     rax, [rbp+arg_0]
0x140001c1f  mov     qword ptr [rbp+arg_0], 0FFFFFFFFFD050F80h
0x140001c27  xor     r9d, r9d; Alertable
0x140001c2a  mov     [rsp+60h+Timeout], rax; Timeout
0x140001c2f  xor     r8d, r8d; WaitMode
0x140001c32  lea     rcx, [rbp+Event]; Object
0x140001c36  xor     edx, edx; WaitReason
0x140001c38  call    cs:__imp_KeWaitForSingleObject
0x140001c3f  nop     dword ptr [rax+rax+00h]
0x140001c44  mov     rdi, [r14+18h]
0x140001c48  cmp     eax, 102h
0x140001c4d  jz      loc_140001D54
0x140001c53  xor     eax, eax
0x140001c55  xorps   xmm0, xmm0
0x140001c58  cmp     cs:P, rax
0x140001c5f  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140001c63  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140001c67  jz      short loc_140001CD9
0x140001c69  lea     rdx, [rbp+LockHandle]; LockHandle
0x140001c6d  lea     rcx, SpinLock; SpinLock
0x140001c74  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001c7b  nop     dword ptr [rax+rax+00h]
0x140001c80  mov     rax, cs:qword_14001A190
0x140001c87  mov     dword ptr [rax], 63757373h
0x140001c8d  mov     rax, cs:qword_14001A190
0x140001c94  mov     [rax+8], rdi
0x140001c98  mov     rax, cs:qword_14001A190
0x140001c9f  mov     [rax+10h], rbx
0x140001ca3  mov     rax, cs:qword_14001A190
0x140001caa  mov     [rax+18h], r12
0x140001cae  mov     rax, cs:qword_14001A190
0x140001cb5  cmp     rax, cs:P
0x140001cbc  jbe     short loc_140001D23
0x140001cbe  sub     rax, 20h ; ' '
0x140001cc2  lea     rcx, [rbp+LockHandle]; LockHandle
0x140001cc6  mov     cs:qword_14001A190, rax
0x140001ccd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001cd4  nop     dword ptr [rax+rax+00h]
0x140001cd9  mov     edi, [rbx+30h]
0x140001cdc  mov     r12, [rsp+60h+arg_8]
0x140001ce4  jmp     loc_140001AB0
0x140001ce9  mov     eax, 0C000009Ah
0x140001cee  jmp     loc_140001B69
0x140001cf3  mov     rax, cs:qword_14001A198
0x140001cfa  add     rax, 0FFFFFFFFFFFFFFE0h
0x140001cfe  jmp     loc_140001A3C
0x140001d03  mov     rax, cs:qword_14001A198
0x140001d0a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140001d0e  jmp     loc_140001B39
0x140001d13  mov     rax, cs:qword_14001A198
0x140001d1a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140001d1e  jmp     loc_140001C04
0x140001d23  mov     rax, cs:qword_14001A198
0x140001d2a  add     rax, 0FFFFFFFFFFFFFFE0h
0x140001d2e  jmp     short loc_140001CC2
0x140001d30  cmp     byte ptr [rcx+29h], 4
0x140001d34  jb      loc_140001994
0x140001d3a  mov     rcx, [rcx+18h]
0x140001d3e  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140001d45  mov     edx, 99h
0x140001d4a  call    WPP_SF_
0x140001d4f  jmp     loc_140001994
0x140001d54  xor     r9d, r9d
0x140001d57  mov     r8, rbx
0x140001d5a  mov     rdx, rdi
0x140001d5d  mov     ecx, 31747373h
0x140001d62  call    USBSTOR_LogEntry
0x140001d67  mov     rcx, rbx; Irp
0x140001d6a  mov     edi, 0C00000B5h
0x140001d6f  call    cs:__imp_IoCancelIrp
0x140001d76  nop     dword ptr [rax+rax+00h]
0x140001d7b  xor     r9d, r9d; Alertable
0x140001d7e  mov     [rsp+60h+Timeout], r12; Timeout
0x140001d83  xor     r8d, r8d; WaitMode
0x140001d86  lea     rcx, [rbp+Event]; Object
0x140001d8a  xor     edx, edx; WaitReason
0x140001d8c  call    cs:__imp_KeWaitForSingleObject
0x140001d93  nop     dword ptr [rax+rax+00h]
0x140001d98  mov     rdx, [r14+18h]
0x140001d9c  xor     r9d, r9d
0x140001d9f  mov     r8, rbx
0x140001da2  mov     ecx, 32747373h
0x140001da7  call    USBSTOR_LogEntry
0x140001dac  jmp     loc_140001CDC
0x140001db1  cmp     byte ptr [rcx+29h], 4
0x140001db5  jb      loc_140001B67
0x140001dbb  mov     rcx, [rcx+18h]
0x140001dbf  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140001dc6  mov     edx, 9Ah
0x140001dcb  mov     r9d, edi
0x140001dce  call    WPP_SF_d
0x140001dd3  jmp     loc_140001B67
```
