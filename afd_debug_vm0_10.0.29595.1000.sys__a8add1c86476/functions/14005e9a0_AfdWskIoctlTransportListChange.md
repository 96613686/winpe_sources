# AfdWskIoctlTransportListChange

- ea: `0x14005e9a0`
- end: `0x14005eb96`
- name: `AfdWskIoctlTransportListChange`
- size: `502`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x14005e9a0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14005e9f2`
- `ntoskrnl!KfRaiseIrql` at `0x14005e9f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005eae3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005eb55`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005eae3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005eb55`
- `ntoskrnl!KeLowerIrql` at `0x14005eb0a`
- `ntoskrnl!KeLowerIrql` at `0x14005eb7c`
- `ntoskrnl!KeLowerIrql` at `0x14005eb0a`
- `ntoskrnl!KeLowerIrql` at `0x14005eb7c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005ea25`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005ea25`
- `ntoskrnl!IofCompleteRequest` at `0x14005eb23`
- `ntoskrnl!IofCompleteRequest` at `0x14005eb23`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ea10`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ea10`
- `NDIS!NdisReleaseRWLock` at `0x14005eafb`
- `NDIS!NdisReleaseRWLock` at `0x14005eb6d`
- `NDIS!NdisReleaseRWLock` at `0x14005eafb`
- `NDIS!NdisReleaseRWLock` at `0x14005eb6d`

## pseudocode

```c
__int64 __fastcall AfdWskIoctlTransportListChange(PIRP Irp, __int64 a2)
{
  KSPIN_LOCK *v2; // r14
  union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *p_Tail; // rbx
  KSPIN_LOCK *v4; // rdi
  KIRQL v6; // bp
  union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 **v7; // rcx
  KSPIN_LOCK **v8; // rcx
  KSPIN_LOCK v9; // rax
  KSPIN_LOCK *v10; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(KSPIN_LOCK **)(a2 + 32);
  p_Tail = &Irp->Tail;
  Irp->Tail.Overlay.DriverContext[3] = Irp;
  v4 = (KSPIN_LOCK *)(a2 + 8);
  Irp->Tail.Overlay.DriverContext[2] = v2;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_QWORD *)(a2 + 32) = &Irp->Tail;
  *(_QWORD *)(a2 + 24) = AfdWskCleanupTransportChangeReq;
  LockHandle.LockQueue = 0;
  v6 = KfRaiseIrql(2u);
  NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 1u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel(v2 + 3, &LockHandle);
  v7 = (union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 **)qword_140087B58;
  if ( *(__int64 **)qword_140087B58 != &AfdWskTransportListChangeReqList )
    goto LABEL_11;
  p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)&AfdWskTransportListChangeReqList;
  p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)v7;
  *v7 = p_Tail;
  qword_140087B58 = (__int64)p_Tail;
  v8 = (KSPIN_LOCK **)v2[8];
  if ( *v8 != v2 + 7 )
    goto LABEL_11;
  *v4 = (KSPIN_LOCK)(v2 + 7);
  v4[1] = (KSPIN_LOCK)v8;
  *v8 = v4;
  v2[8] = (KSPIN_LOCK)v4;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdWskCancelTransportChangeReq);
  if ( Irp->Cancel && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
  {
    v9 = *v4;
    if ( *(KSPIN_LOCK **)(*v4 + 8) == v4 )
    {
      v10 = (KSPIN_LOCK *)v4[1];
      if ( (KSPIN_LOCK *)*v10 == v4 )
      {
        *v10 = v9;
        *(_QWORD *)(v9 + 8) = v10;
        Flink = p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
        if ( (union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *)p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Flink->Blink == p_Tail )
        {
          Blink = p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
          if ( (union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *)Blink->Flink == p_Tail )
          {
            Blink->Flink = Flink;
            Flink->Blink = Blink;
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
            NdisReleaseRWLock(AfdTlTransportLock, &LockState);
            KeLowerIrql(v6);
            Irp->IoStatus.Status = -1073741536;
            IofCompleteRequest(Irp, 0);
            return 3221225760LL;
          }
        }
      }
    }
LABEL_11:
    __fastfail(3u);
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  NdisReleaseRWLock(AfdTlTransportLock, &LockState);
  KeLowerIrql(v6);
  return 259;
}

```

## disassembly

```asm
0x14005e9a0  mov     [rsp+arg_8], rbx
0x14005e9a5  mov     [rsp+arg_10], rbp
0x14005e9aa  push    rsi
0x14005e9ab  push    rdi
0x14005e9ac  push    r14
0x14005e9ae  sub     rsp, 40h
0x14005e9b2  mov     r14, [rdx+20h]
0x14005e9b6  lea     rbx, [rcx+78h]
0x14005e9ba  xor     eax, eax
0x14005e9bc  mov     [rbx+18h], rcx
0x14005e9c0  lea     rdi, [rdx+8]
0x14005e9c4  mov     [rbx+10h], r14
0x14005e9c8  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14005e9cd  mov     rsi, rcx
0x14005e9d0  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14005e9d5  xorps   xmm0, xmm0
0x14005e9d8  mov     [rsp+58h+LockState.Flags], al
0x14005e9dc  mov     cl, 2; NewIrql
0x14005e9de  lea     rax, AfdWskCleanupTransportChangeReq
0x14005e9e5  mov     [rdi+18h], rbx
0x14005e9e9  mov     [rdi+10h], rax
0x14005e9ed  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14005e9f2  call    cs:__imp_KfRaiseIrql
0x14005e9f9  nop     dword ptr [rax+rax+00h]
0x14005e9fe  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005ea05  lea     rdx, [rsp+58h+LockState]; LockState
0x14005ea0a  mov     r8b, 1; Flags
0x14005ea0d  mov     bpl, al
0x14005ea10  call    cs:__imp_NdisAcquireRWLockWrite
0x14005ea17  nop     dword ptr [rax+rax+00h]
0x14005ea1c  lea     rcx, [r14+18h]; SpinLock
0x14005ea20  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14005ea25  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005ea2c  nop     dword ptr [rax+rax+00h]
0x14005ea31  mov     rcx, cs:qword_140087B58
0x14005ea38  lea     rax, AfdWskTransportListChangeReqList
0x14005ea3f  cmp     [rcx], rax
0x14005ea42  jnz     loc_14005EB8F
0x14005ea48  mov     [rbx], rax
0x14005ea4b  lea     rax, [r14+38h]
0x14005ea4f  mov     [rbx+8], rcx
0x14005ea53  mov     [rcx], rbx
0x14005ea56  mov     cs:qword_140087B58, rbx
0x14005ea5d  mov     rcx, [rax+8]
0x14005ea61  cmp     [rcx], rax
0x14005ea64  jnz     loc_14005EB8F
0x14005ea6a  mov     [rdi], rax
0x14005ea6d  mov     [rdi+8], rcx
0x14005ea71  mov     [rcx], rdi
0x14005ea74  mov     [rax+8], rdi
0x14005ea78  lea     rax, AfdWskCancelTransportChangeReq
0x14005ea7f  xchg    rax, [rsi+68h]
0x14005ea83  cmp     byte ptr [rsi+44h], 0
0x14005ea87  jz      loc_14005EB45
0x14005ea8d  xor     eax, eax
0x14005ea8f  xchg    rax, [rsi+68h]
0x14005ea93  test    rax, rax
0x14005ea96  jz      loc_14005EB45
0x14005ea9c  mov     rax, [rdi]
0x14005ea9f  cmp     [rax+8], rdi
0x14005eaa3  jnz     loc_14005EB8F
0x14005eaa9  mov     rcx, [rdi+8]
0x14005eaad  cmp     [rcx], rdi
0x14005eab0  jnz     loc_14005EB8F
0x14005eab6  mov     [rcx], rax
0x14005eab9  mov     [rax+8], rcx
0x14005eabd  mov     rcx, [rbx]
0x14005eac0  cmp     [rcx+8], rbx
0x14005eac4  jnz     loc_14005EB8F
0x14005eaca  mov     rax, [rbx+8]
0x14005eace  cmp     [rax], rbx
0x14005ead1  jnz     loc_14005EB8F
0x14005ead7  mov     [rax], rcx
0x14005eada  mov     [rcx+8], rax
0x14005eade  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14005eae3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005eaea  nop     dword ptr [rax+rax+00h]
0x14005eaef  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005eaf6  lea     rdx, [rsp+58h+LockState]; LockState
0x14005eafb  call    cs:__imp_NdisReleaseRWLock
0x14005eb02  nop     dword ptr [rax+rax+00h]
0x14005eb07  mov     cl, bpl; NewIrql
0x14005eb0a  call    cs:__imp_KeLowerIrql
0x14005eb11  nop     dword ptr [rax+rax+00h]
0x14005eb16  mov     ebx, 0C0000120h
0x14005eb1b  xor     edx, edx; PriorityBoost
0x14005eb1d  mov     rcx, rsi; Irp
0x14005eb20  mov     [rsi+30h], ebx
0x14005eb23  call    cs:__imp_IofCompleteRequest
0x14005eb2a  nop     dword ptr [rax+rax+00h]
0x14005eb2f  mov     eax, ebx
0x14005eb31  mov     rbx, [rsp+58h+arg_8]
0x14005eb36  mov     rbp, [rsp+58h+arg_10]
0x14005eb3b  add     rsp, 40h
0x14005eb3f  pop     r14
0x14005eb41  pop     rdi
0x14005eb42  pop     rsi
0x14005eb43  retn
0x14005eb45  mov     rax, [rsi+0B8h]
0x14005eb4c  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14005eb51  or      byte ptr [rax+3], 1
0x14005eb55  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005eb5c  nop     dword ptr [rax+rax+00h]
0x14005eb61  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005eb68  lea     rdx, [rsp+58h+LockState]; LockState
0x14005eb6d  call    cs:__imp_NdisReleaseRWLock
0x14005eb74  nop     dword ptr [rax+rax+00h]
0x14005eb79  mov     cl, bpl; NewIrql
0x14005eb7c  call    cs:__imp_KeLowerIrql
0x14005eb83  nop     dword ptr [rax+rax+00h]
0x14005eb88  mov     eax, 103h
0x14005eb8d  jmp     short loc_14005EB31
0x14005eb8f  mov     ecx, 3
0x14005eb94  int     29h; Win8: RtlFailFast(ecx)
```
