# AfdWskIoctlTransportListChange

- ea: `0x14005e800`
- end: `0x14005e9f6`
- name: `AfdWskIoctlTransportListChange`
- size: `502`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x14005e800`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14005e852`
- `ntoskrnl!KfRaiseIrql` at `0x14005e852`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005e943`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005e9b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005e943`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005e9b5`
- `ntoskrnl!KeLowerIrql` at `0x14005e96a`
- `ntoskrnl!KeLowerIrql` at `0x14005e9dc`
- `ntoskrnl!KeLowerIrql` at `0x14005e96a`
- `ntoskrnl!KeLowerIrql` at `0x14005e9dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005e885`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005e885`
- `ntoskrnl!IofCompleteRequest` at `0x14005e983`
- `ntoskrnl!IofCompleteRequest` at `0x14005e983`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e870`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e870`
- `NDIS!NdisReleaseRWLock` at `0x14005e95b`
- `NDIS!NdisReleaseRWLock` at `0x14005e9cd`
- `NDIS!NdisReleaseRWLock` at `0x14005e95b`
- `NDIS!NdisReleaseRWLock` at `0x14005e9cd`

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
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdWskCancelTransportChangeReq);
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
0x14005e800  mov     [rsp+arg_8], rbx
0x14005e805  mov     [rsp+arg_10], rbp
0x14005e80a  push    rsi
0x14005e80b  push    rdi
0x14005e80c  push    r14
0x14005e80e  sub     rsp, 40h
0x14005e812  mov     r14, [rdx+20h]
0x14005e816  lea     rbx, [rcx+78h]
0x14005e81a  xor     eax, eax
0x14005e81c  mov     [rbx+18h], rcx
0x14005e820  lea     rdi, [rdx+8]
0x14005e824  mov     [rbx+10h], r14
0x14005e828  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14005e82d  mov     rsi, rcx
0x14005e830  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14005e835  xorps   xmm0, xmm0
0x14005e838  mov     [rsp+58h+LockState.Flags], al
0x14005e83c  mov     cl, 2; NewIrql
0x14005e83e  lea     rax, AfdWskCleanupTransportChangeReq
0x14005e845  mov     [rdi+18h], rbx
0x14005e849  mov     [rdi+10h], rax
0x14005e84d  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14005e852  call    cs:__imp_KfRaiseIrql
0x14005e859  nop     dword ptr [rax+rax+00h]
0x14005e85e  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e865  lea     rdx, [rsp+58h+LockState]; LockState
0x14005e86a  mov     r8b, 1; Flags
0x14005e86d  mov     bpl, al
0x14005e870  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e877  nop     dword ptr [rax+rax+00h]
0x14005e87c  lea     rcx, [r14+18h]; SpinLock
0x14005e880  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14005e885  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005e88c  nop     dword ptr [rax+rax+00h]
0x14005e891  mov     rcx, cs:qword_140087B58
0x14005e898  lea     rax, AfdWskTransportListChangeReqList
0x14005e89f  cmp     [rcx], rax
0x14005e8a2  jnz     loc_14005E9EF
0x14005e8a8  mov     [rbx], rax
0x14005e8ab  lea     rax, [r14+38h]
0x14005e8af  mov     [rbx+8], rcx
0x14005e8b3  mov     [rcx], rbx
0x14005e8b6  mov     cs:qword_140087B58, rbx
0x14005e8bd  mov     rcx, [rax+8]
0x14005e8c1  cmp     [rcx], rax
0x14005e8c4  jnz     loc_14005E9EF
0x14005e8ca  mov     [rdi], rax
0x14005e8cd  mov     [rdi+8], rcx
0x14005e8d1  mov     [rcx], rdi
0x14005e8d4  mov     [rax+8], rdi
0x14005e8d8  lea     rax, AfdWskCancelTransportChangeReq
0x14005e8df  xchg    rax, [rsi+68h]
0x14005e8e3  cmp     byte ptr [rsi+44h], 0
0x14005e8e7  jz      loc_14005E9A5
0x14005e8ed  xor     eax, eax
0x14005e8ef  xchg    rax, [rsi+68h]
0x14005e8f3  test    rax, rax
0x14005e8f6  jz      loc_14005E9A5
0x14005e8fc  mov     rax, [rdi]
0x14005e8ff  cmp     [rax+8], rdi
0x14005e903  jnz     loc_14005E9EF
0x14005e909  mov     rcx, [rdi+8]
0x14005e90d  cmp     [rcx], rdi
0x14005e910  jnz     loc_14005E9EF
0x14005e916  mov     [rcx], rax
0x14005e919  mov     [rax+8], rcx
0x14005e91d  mov     rcx, [rbx]
0x14005e920  cmp     [rcx+8], rbx
0x14005e924  jnz     loc_14005E9EF
0x14005e92a  mov     rax, [rbx+8]
0x14005e92e  cmp     [rax], rbx
0x14005e931  jnz     loc_14005E9EF
0x14005e937  mov     [rax], rcx
0x14005e93a  mov     [rcx+8], rax
0x14005e93e  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14005e943  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005e94a  nop     dword ptr [rax+rax+00h]
0x14005e94f  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e956  lea     rdx, [rsp+58h+LockState]; LockState
0x14005e95b  call    cs:__imp_NdisReleaseRWLock
0x14005e962  nop     dword ptr [rax+rax+00h]
0x14005e967  mov     cl, bpl; NewIrql
0x14005e96a  call    cs:__imp_KeLowerIrql
0x14005e971  nop     dword ptr [rax+rax+00h]
0x14005e976  mov     ebx, 0C0000120h
0x14005e97b  xor     edx, edx; PriorityBoost
0x14005e97d  mov     rcx, rsi; Irp
0x14005e980  mov     [rsi+30h], ebx
0x14005e983  call    cs:__imp_IofCompleteRequest
0x14005e98a  nop     dword ptr [rax+rax+00h]
0x14005e98f  mov     eax, ebx
0x14005e991  mov     rbx, [rsp+58h+arg_8]
0x14005e996  mov     rbp, [rsp+58h+arg_10]
0x14005e99b  add     rsp, 40h
0x14005e99f  pop     r14
0x14005e9a1  pop     rdi
0x14005e9a2  pop     rsi
0x14005e9a3  retn
0x14005e9a5  mov     rax, [rsi+0B8h]
0x14005e9ac  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14005e9b1  or      byte ptr [rax+3], 1
0x14005e9b5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14005e9bc  nop     dword ptr [rax+rax+00h]
0x14005e9c1  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e9c8  lea     rdx, [rsp+58h+LockState]; LockState
0x14005e9cd  call    cs:__imp_NdisReleaseRWLock
0x14005e9d4  nop     dword ptr [rax+rax+00h]
0x14005e9d9  mov     cl, bpl; NewIrql
0x14005e9dc  call    cs:__imp_KeLowerIrql
0x14005e9e3  nop     dword ptr [rax+rax+00h]
0x14005e9e8  mov     eax, 103h
0x14005e9ed  jmp     short loc_14005E991
0x14005e9ef  mov     ecx, 3
0x14005e9f4  int     29h; Win8: RtlFailFast(ecx)
```
