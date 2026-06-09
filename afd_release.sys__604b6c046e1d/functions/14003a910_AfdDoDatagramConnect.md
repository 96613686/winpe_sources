# AfdDoDatagramConnect

- ea: `0x14003a910`
- end: `0x14003ae28`
- name: `AfdDoDatagramConnect`
- size: `1304`
- prototype: `NTSTATUS __fastcall(_QWORD *, IRP *, __int64, unsigned int, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400398b0`

## callees

- `0x140003670`
- `0x14000f450`
- `0x14000fcd0`
- `0x140013030`
- `0x1400137a0`
- `0x140015990`
- `0x14001b0d0`
- `0x14001b0f8`
- `0x14001b800`
- `0x140026e80`
- `0x140030950`
- `0x14003a910`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003aac8`
- `ntoskrnl!IofCompleteRequest` at `0x14003ad05`
- `ntoskrnl!IofCompleteRequest` at `0x14003aac8`
- `ntoskrnl!IofCompleteRequest` at `0x14003ad05`
- `ntoskrnl!ObfDereferenceObject` at `0x14003acca`
- `ntoskrnl!ObfDereferenceObject` at `0x14003acca`
- `ntoskrnl!IofCallDriver` at `0x14003ae00`
- `ntoskrnl!IofCallDriver` at `0x14003ae00`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab52`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a9bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a9bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ace4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ace4`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab09`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab7c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab09`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ab7c`
- `NDIS!NdisReleaseRWLock` at `0x14003abca`
- `NDIS!NdisReleaseRWLock` at `0x14003abca`

## pseudocode

```c
NTSTATUS __fastcall AfdDoDatagramConnect(_QWORD *a1, IRP *a2, __int64 a3, unsigned int a4, char a5)
{
  __int64 v5; // rbx
  struct _IRP *MasterIrp; // r13
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  char v14; // r14
  unsigned int v15; // eax
  struct _EX_RUNDOWN_REF *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ebx
  IRP *v20; // rcx
  LIST_ENTRY *p_ThreadListEntry; // r14
  void *v23; // r12
  size_t Flink_low; // rdx
  __int64 PoolPriority; // rax
  struct _NDIS_RW_LOCK_EX *v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  char v29; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  int v31; // ebx
  CCHAR v32; // dl
  struct _DEVICE_OBJECT *v33; // r12
  unsigned int v34; // eax
  int v35; // ecx
  __int64 v36; // rax
  struct _FILE_OBJECT *v37; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v39; // rdx
  unsigned int v40; // [rsp+38h] [rbp-61h]
  __int64 v41; // [rsp+40h] [rbp-59h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v43[16]; // [rsp+68h] [rbp-31h] BYREF
  struct _FILE_OBJECT *Objecta; // [rsp+F8h] [rbp+5Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v47; // [rsp+110h] [rbp+77h]

  v47 = a4;
  v5 = a1[3];
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), 4, 0) )
  {
    v10 = 1;
    if ( (unsigned __int8)(*(_BYTE *)(v5 + 2) - 3) > 1u )
    {
      v9 = -1073741811;
      v11 = 5501;
LABEL_5:
      v10 = 0;
      v12 = 0;
LABEL_30:
      AFDETW_TRACECONNECT(v10, v11, v5, v9, v12);
      _InterlockedExchange((volatile __int32 *)(v5 + 368), 0);
      goto LABEL_31;
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
    v13 = *(unsigned int *)(v5 + 192);
    v14 = a5;
    *(_DWORD *)(v5 + 8) &= 0xFFF0FFFF;
    *(_DWORD *)(v5 + 192) = v13 ^ ((unsigned __int8)v13 ^ (unsigned __int8)(16 * v14)) & 0x10;
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
    {
      memset(v43, 0, 0x50u);
      AFDETW_TRACECONNECT(0, 5502, v5, 0, a3);
      v15 = *(_DWORD *)(v5 + 72) & 0xFFFFFEFF;
      *(_DWORD *)(v5 + 436) = 0;
      *(_DWORD *)(v5 + 72) = v15;
      AfdNotifySockEventsChangedUnderLock(v5, 0, 256);
      AfdNotifySockIndicateEventsUnlock(v16, &LockHandle, 0);
      a2->Tail.Overlay.DriverContext[2] = 0;
      v17 = *(_QWORD *)(v5 + 24);
      v18 = *(_QWORD *)(v5 + 16);
      v43[0] = AfdTLDgramConnectComplete;
      v43[1] = a2;
      v43[2] = 0xFFFD00000000LL;
      LODWORD(v43[3]) = v14 != 0 ? 40 : 28;
      v43[5] = v47;
      v43[4] = a3;
      v19 = AfdTLIoControl(*(__int64 (__fastcall **)(__int64, __int64))(v17 + 8), v18, (__int64)v43, v5);
      v20 = a2;
      if ( v19 == 259 )
      {
        if ( AfdTLPendRequest((__int64)a2, v43[8], 1) )
          return v19;
        v20 = a2;
      }
      IofCompleteRequest(v20, AfdPriorityBoost);
      return v19;
    }
    if ( *(_QWORD *)(v5 + 184)
      && (p_ThreadListEntry = &MasterIrp->ThreadListEntry,
          *(_DWORD *)(v5 + 176) >= LODWORD(MasterIrp->ThreadListEntry.Flink)) )
    {
      v40 = 0;
      v23 = 0;
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 1u);
    }
    else
    {
      p_ThreadListEntry = &MasterIrp->ThreadListEntry;
      Flink_low = SLODWORD(MasterIrp->ThreadListEntry.Flink);
      if ( LODWORD(MasterIrp->ThreadListEntry.Flink) > (unsigned int)AfdStandardAddressLength )
        PoolPriority = AfdAllocatePoolPriority(64, Flink_low, 1382311489, 0);
      else
        PoolPriority = (__int64)AfdAllocateZeroedFromLookasideList(v13, Flink_low);
      v41 = PoolPriority;
      if ( !PoolPriority )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v11 = 5503;
        v9 = -1073741670;
        goto LABEL_5;
      }
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 1u);
      v23 = *(void **)(v5 + 184);
      v40 = *(_DWORD *)(v5 + 176);
      *(_QWORD *)(v5 + 184) = v41;
    }
    memmove(*(void **)(v5 + 184), MasterIrp->ThreadListEntry.Blink, SLODWORD(p_ThreadListEntry->Flink));
    v26 = *(struct _NDIS_RW_LOCK_EX **)(v5 + 168);
    *(_DWORD *)(v5 + 176) = p_ThreadListEntry->Flink;
    NdisReleaseRWLock(v26, &LockState);
    AFDETW_TRACECONNECT(0, 5504, v5, 0, *(_QWORD *)(v5 + 184));
    if ( v23 )
    {
      if ( v40 > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(v23, 0x52646641u);
      else
        PplFreeToLookasideList((__int64)PplAddressPool, v23);
    }
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x8000) == 0 )
    {
      v27 = *(_DWORD *)(v5 + 8) | 0x2000000;
      *(_BYTE *)(v5 + 2) = 4;
      *(_DWORD *)(v5 + 8) = v27;
      AfdIndicateEventSelectEvent(v5, 68, 0);
      AfdNotifySockEventsChangedUnderLock(v5, 4, 0);
      v29 = AfdIndicatePollEvent(v28, 0x44u, 0, &LockHandle);
      p_LockHandle = &LockHandle;
      if ( v29 )
        p_LockHandle = 0;
      AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v5, p_LockHandle, 0);
      v12 = *(_QWORD *)(v5 + 184);
      v11 = 5505;
      v9 = 0;
      goto LABEL_30;
    }
    v33 = *(struct _DEVICE_OBJECT **)(v5 + 40);
    Objecta = *(struct _FILE_OBJECT **)(v5 + 24);
    v34 = *(_DWORD *)(v5 + 72) & 0xFFFFFEFF;
    *(_DWORD *)(v5 + 436) = 0;
    *(_DWORD *)(v5 + 72) = v34;
    AfdNotifySockEventsChangedUnderLock(v5, 0, 256);
    v35 = *(_DWORD *)(v5 + 8);
    if ( (v35 & 0x400000) != 0 )
    {
      if ( AfdTdi_TA6toTA4_InPlace((__int64)MasterIrp->ThreadListEntry.Blink, p_ThreadListEntry) )
      {
        v36 = *(_QWORD *)(v5 + 280);
        v37 = *(struct _FILE_OBJECT **)(v36 + 8);
        v33 = *(struct _DEVICE_OBJECT **)(v36 + 16);
        *(_DWORD *)(v5 + 192) |= 0x20u;
LABEL_41:
        AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v5, &LockHandle, 0);
        CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartDgConnect;
        CurrentStackLocation[-1].Context = (PVOID)v5;
        CurrentStackLocation[-1].Control = -32;
        v39 = a2->Tail.Overlay.CurrentStackLocation;
        v39[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)&MasterIrp->IoStatus;
        v39[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&AfdInfiniteTimeout;
        *(_WORD *)&v39[-1].MajorFunction = 783;
        v39[-1].DeviceObject = v33;
        v39[-1].FileObject = v37;
        v39[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)MasterIrp;
        _InterlockedAdd((volatile signed __int32 *)(v5 + 248), 1u);
        return IofCallDriver(v33, a2);
      }
      *(_DWORD *)(v5 + 192) = *(_DWORD *)(v5 + 192) & 0xFFFFFF9F | 0x40;
    }
    else if ( (v35 & 0x200000) != 0 )
    {
      AfdTdi_TA6toTA4_InPlace((__int64)MasterIrp->ThreadListEntry.Blink, p_ThreadListEntry);
    }
    v37 = Objecta;
    goto LABEL_41;
  }
  v9 = -1073741811;
  AFDETW_TRACECONNECT(0, 5500, v5, 3221225485LL, 0);
LABEL_31:
  v31 = *(_DWORD *)(v5 + 8);
  ObfDereferenceObject(a1);
  if ( (v31 & 0x100) == 0 )
  {
    ExFreePoolWithTag(MasterIrp, 0x49646641u);
    a2->AssociatedIrp.MasterIrp = 0;
  }
  v32 = AfdPriorityBoost;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v9;
  IofCompleteRequest(a2, v32);
  return v9;
}

```

## disassembly

```asm
0x14003a910  mov     rax, rsp
0x14003a913  mov     [rax+18h], rbx
0x14003a917  mov     [rax+20h], r9d
0x14003a91b  mov     [rax+8], rcx
0x14003a91f  push    rbp
0x14003a920  push    rsi
0x14003a921  push    rdi
0x14003a922  push    r12
0x14003a924  push    r13
0x14003a926  push    r14
0x14003a928  push    r15
0x14003a92a  lea     rbp, [rax-57h]
0x14003a92e  sub     rsp, 0B0h
0x14003a935  mov     rbx, [rcx+18h]
0x14003a939  xorps   xmm0, xmm0
0x14003a93c  mov     r13, [rdx+18h]
0x14003a940  xor     ecx, ecx
0x14003a942  mov     qword ptr [rbp+4Fh+LockHandle.OldIrql], rcx
0x14003a946  mov     r12, r8
0x14003a949  mov     word ptr [rbp+4Fh+LockState.OldIrql], cx
0x14003a94d  mov     rsi, rdx
0x14003a950  mov     [rbp+4Fh+LockState.Flags], cl
0x14003a953  xor     eax, eax
0x14003a955  mov     ecx, 4
0x14003a95a  movups  xmmword ptr [rbp+4Fh+LockHandle.LockQueue.Next], xmm0
0x14003a95e  lock cmpxchg [rbx+170h], ecx
0x14003a966  jz      short loc_14003A98C
0x14003a968  xor     edi, edi
0x14003a96a  mov     r14d, 0C000000Dh
0x14003a970  mov     r9d, r14d
0x14003a973  mov     [rsp+20h], rdi
0x14003a978  mov     r8, rbx
0x14003a97b  mov     edx, 157Ch
0x14003a980  xor     ecx, ecx
0x14003a982  call    AFDETW_TRACECONNECT
0x14003a987  jmp     loc_14003ACC3
0x14003a98c  mov     al, [rbx+2]
0x14003a98f  mov     r15d, 1
0x14003a995  sub     al, 3
0x14003a997  cmp     al, r15b
0x14003a99a  jbe     short loc_14003A9B4
0x14003a99c  xor     edi, edi
0x14003a99e  mov     r14d, 0C000000Dh
0x14003a9a4  mov     edx, 157Dh
0x14003a9a9  mov     r15d, edi
0x14003a9ac  mov     rax, rdi
0x14003a9af  jmp     loc_14003ACA8
0x14003a9b4  lea     rcx, [rbx+38h]; SpinLock
0x14003a9b8  lea     rdx, [rbp+4Fh+LockHandle]; LockHandle
0x14003a9bc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003a9c3  nop     dword ptr [rax+rax+00h]
0x14003a9c8  mov     ecx, [rbx+0C0h]
0x14003a9ce  mov     eax, [rbx+8]
0x14003a9d1  movzx   r14d, [rbp+4Fh+arg_20]
0x14003a9d6  and     eax, 0FFF0FFFFh
0x14003a9db  mov     [rbx+8], eax
0x14003a9de  mov     eax, r14d
0x14003a9e1  shl     eax, 4
0x14003a9e4  xor     eax, ecx
0x14003a9e6  and     eax, 10h
0x14003a9e9  xor     eax, ecx
0x14003a9eb  mov     [rbx+0C0h], eax
0x14003a9f1  mov     eax, [rbx+8]
0x14003a9f4  bt      eax, 8
0x14003a9f8  jnb     loc_14003AADB
0x14003a9fe  xor     edx, edx; Val
0x14003aa00  lea     rcx, [rbp+4Fh+var_80]; void *
0x14003aa04  lea     r8d, [rdx+50h]; Size
0x14003aa08  call    memset
0x14003aa0d  xor     r9d, r9d
0x14003aa10  mov     [rsp+20h], r12
0x14003aa15  mov     r8, rbx
0x14003aa18  mov     edx, 157Eh
0x14003aa1d  xor     ecx, ecx
0x14003aa1f  call    AFDETW_TRACECONNECT
0x14003aa24  mov     eax, [rbx+48h]
0x14003aa27  xor     edi, edi
0x14003aa29  btr     eax, 8
0x14003aa2d  mov     [rbx+1B4h], edi
0x14003aa33  xor     edx, edx
0x14003aa35  mov     [rbx+48h], eax
0x14003aa38  mov     r8d, 100h
0x14003aa3e  mov     rcx, rbx
0x14003aa41  call    AfdNotifySockEventsChangedUnderLock
0x14003aa46  xor     r8d, r8d
0x14003aa49  lea     rdx, [rbp+4Fh+LockHandle]
0x14003aa4d  call    AfdNotifySockIndicateEventsUnlock
0x14003aa52  mov     [rsi+88h], rdi
0x14003aa59  lea     rax, AfdTLDgramConnectComplete
0x14003aa60  mov     rcx, [rbx+18h]
0x14003aa64  lea     r8, [rbp+4Fh+var_80]
0x14003aa68  mov     rdx, [rbx+10h]
0x14003aa6c  neg     r14b
0x14003aa6f  mov     [rbp+4Fh+var_80], rax
0x14003aa73  mov     r9, rbx
0x14003aa76  sbb     eax, eax
0x14003aa78  mov     [rbp+4Fh+var_78], rsi
0x14003aa7c  and     eax, 0Ch
0x14003aa7f  mov     [rbp+4Fh+var_70], edi
0x14003aa82  add     eax, 1Ch
0x14003aa85  mov     [rbp+4Fh+var_6C], 0FFFDh
0x14003aa8c  mov     [rbp+4Fh+var_68], eax
0x14003aa8f  mov     eax, [rbp+4Fh+arg_18]
0x14003aa92  mov     [rbp+4Fh+var_58], rax
0x14003aa96  mov     [rbp+4Fh+var_60], r12
0x14003aa9a  mov     rcx, [rcx+8]
0x14003aa9e  call    AfdTLIoControl
0x14003aaa3  mov     ebx, eax
0x14003aaa5  mov     rcx, rsi
0x14003aaa8  cmp     eax, 103h
0x14003aaad  jnz     short loc_14003AAC2
0x14003aaaf  mov     rdx, [rbp+4Fh+var_40]
0x14003aab3  mov     r8b, r15b
0x14003aab6  call    AfdTLPendRequest
0x14003aabb  test    al, al
0x14003aabd  jnz     short loc_14003AAD4
0x14003aabf  mov     rcx, rsi; Irp
0x14003aac2  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14003aac8  call    cs:__imp_IofCompleteRequest
0x14003aacf  nop     dword ptr [rax+rax+00h]
0x14003aad4  mov     eax, ebx
0x14003aad6  jmp     loc_14003AE0C
0x14003aadb  xor     edi, edi
0x14003aadd  cmp     [rbx+0B8h], rdi
0x14003aae4  jz      short loc_14003AB1A
0x14003aae6  lea     r14, [r13+20h]
0x14003aaea  mov     eax, [r14]
0x14003aaed  cmp     [rbx+0B0h], eax
0x14003aaf3  jb      short loc_14003AB1A
0x14003aaf5  mov     rcx, [rbx+0A8h]; Lock
0x14003aafc  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003ab00  mov     r8b, r15b; Flags
0x14003ab03  mov     [rbp+4Fh+var_B0], edi
0x14003ab06  mov     r12d, edi
0x14003ab09  call    cs:__imp_NdisAcquireRWLockWrite
0x14003ab10  nop     dword ptr [rax+rax+00h]
0x14003ab15  jmp     loc_14003ABA3
0x14003ab1a  lea     r14, [r13+20h]
0x14003ab1e  movsxd  rax, dword ptr [r14]
0x14003ab21  cmp     eax, cs:AfdStandardAddressLength
0x14003ab27  mov     rdx, rax
0x14003ab2a  ja      short loc_14003AB33
0x14003ab2c  call    AfdAllocateZeroedFromLookasideList
0x14003ab31  jmp     short loc_14003AB45
0x14003ab33  xor     r9d, r9d
0x14003ab36  mov     r8d, 52646641h
0x14003ab3c  lea     ecx, [r9+40h]
0x14003ab40  call    AfdAllocatePoolPriority
0x14003ab45  mov     [rbp+4Fh+var_A8], rax
0x14003ab49  test    rax, rax
0x14003ab4c  jnz     short loc_14003AB6E
0x14003ab4e  lea     rcx, [rbp+4Fh+LockHandle]; LockHandle
0x14003ab52  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ab59  nop     dword ptr [rax+rax+00h]
0x14003ab5e  mov     edx, 157Fh
0x14003ab63  mov     r14d, 0C000009Ah
0x14003ab69  jmp     loc_14003A9A9
0x14003ab6e  mov     rcx, [rbx+0A8h]; Lock
0x14003ab75  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003ab79  mov     r8b, r15b; Flags
0x14003ab7c  call    cs:__imp_NdisAcquireRWLockWrite
0x14003ab83  nop     dword ptr [rax+rax+00h]
0x14003ab88  mov     eax, [rbx+0B0h]
0x14003ab8e  mov     r12, [rbx+0B8h]
0x14003ab95  mov     [rbp+4Fh+var_B0], eax
0x14003ab98  mov     rax, [rbp+4Fh+var_A8]
0x14003ab9c  mov     [rbx+0B8h], rax
0x14003aba3  movsxd  r8, dword ptr [r14]; Size
0x14003aba6  mov     rdx, [r13+28h]; Src
0x14003abaa  mov     rcx, [rbx+0B8h]; void *
0x14003abb1  call    memmove
0x14003abb6  mov     eax, [r14]
0x14003abb9  lea     rdx, [rbp+4Fh+LockState]; LockState
0x14003abbd  mov     rcx, [rbx+0A8h]; Lock
0x14003abc4  mov     [rbx+0B0h], eax
0x14003abca  call    cs:__imp_NdisReleaseRWLock
0x14003abd1  nop     dword ptr [rax+rax+00h]
0x14003abd6  mov     rax, [rbx+0B8h]
0x14003abdd  xor     r9d, r9d
0x14003abe0  mov     r8, rbx
0x14003abe3  mov     [rsp+20h], rax
0x14003abe8  mov     edx, 1580h
0x14003abed  xor     ecx, ecx
0x14003abef  call    AFDETW_TRACECONNECT
0x14003abf4  test    r12, r12
0x14003abf7  jz      short loc_14003AC29
0x14003abf9  mov     eax, [rbp+4Fh+var_B0]
0x14003abfc  cmp     eax, cs:AfdStandardAddressLength
0x14003ac02  ja      short loc_14003AC15
0x14003ac04  mov     rcx, cs:PplAddressPool
0x14003ac0b  mov     rdx, r12
0x14003ac0e  call    PplFreeToLookasideList
0x14003ac13  jmp     short loc_14003AC29
0x14003ac15  mov     edx, 52646641h; Tag
0x14003ac1a  mov     rcx, r12; P
0x14003ac1d  call    cs:__imp_ExFreePoolWithTag
0x14003ac24  nop     dword ptr [rax+rax+00h]
0x14003ac29  mov     eax, [rbx+8]
0x14003ac2c  mov     ecx, 100h
0x14003ac31  test    ecx, eax
0x14003ac33  jnz     loc_14003AD19
0x14003ac39  test    dword ptr [rbx+10h], 8000h
0x14003ac40  jnz     loc_14003AD19
0x14003ac46  mov     eax, [rbx+8]
0x14003ac49  xor     r8d, r8d
0x14003ac4c  bts     eax, 19h
0x14003ac50  mov     byte ptr [rbx+2], 4
0x14003ac54  mov     rcx, rbx
0x14003ac57  mov     [rbx+8], eax
0x14003ac5a  lea     r14d, [r8+44h]
0x14003ac5e  mov     edx, r14d
0x14003ac61  call    AfdIndicateEventSelectEvent
0x14003ac66  xor     r8d, r8d
0x14003ac69  lea     edx, [r14-40h]
0x14003ac6d  mov     rcx, rbx
0x14003ac70  call    AfdNotifySockEventsChangedUnderLock
0x14003ac75  xor     r8d, r8d
0x14003ac78  lea     r9, [rbp+4Fh+LockHandle]
0x14003ac7c  mov     edx, r14d
0x14003ac7f  call    AfdIndicatePollEvent
0x14003ac84  test    al, al
0x14003ac86  lea     rdx, [rbp+4Fh+LockHandle]
0x14003ac8a  mov     rcx, rbx
0x14003ac8d  cmovnz  rdx, rdi
0x14003ac91  xor     r8d, r8d
0x14003ac94  call    AfdNotifySockIndicateEventsUnlock
0x14003ac99  mov     rax, [rbx+0B8h]
0x14003aca0  mov     edx, 1581h
0x14003aca5  mov     r14d, edi
0x14003aca8  mov     r9d, r14d
0x14003acab  mov     [rsp+20h], rax
0x14003acb0  mov     r8, rbx
0x14003acb3  mov     ecx, r15d
0x14003acb6  call    AFDETW_TRACECONNECT
0x14003acbb  mov     eax, edi
0x14003acbd  xchg    eax, [rbx+170h]
0x14003acc3  mov     rcx, [rbp+4Fh+Object]; Object
0x14003acc7  mov     ebx, [rbx+8]
0x14003acca  call    cs:__imp_ObfDereferenceObject
0x14003acd1  nop     dword ptr [rax+rax+00h]
0x14003acd6  bt      ebx, 8
0x14003acda  jb      short loc_14003ACF4
0x14003acdc  mov     edx, 49646641h; Tag
0x14003ace1  mov     rcx, r13; P
0x14003ace4  call    cs:__imp_ExFreePoolWithTag
0x14003aceb  nop     dword ptr [rax+rax+00h]
0x14003acf0  mov     [rsi+18h], rdi
0x14003acf4  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14003acfa  mov     rcx, rsi; Irp
0x14003acfd  mov     [rsi+38h], rdi
0x14003ad01  mov     [rsi+30h], r14d
0x14003ad05  call    cs:__imp_IofCompleteRequest
0x14003ad0c  nop     dword ptr [rax+rax+00h]
0x14003ad11  mov     eax, r14d
0x14003ad14  jmp     loc_14003AE0C
0x14003ad19  mov     rax, [rbx+18h]
0x14003ad1d  mov     r8d, ecx
0x14003ad20  mov     r12, [rbx+28h]
0x14003ad24  xor     edx, edx
0x14003ad26  mov     [rbp+4Fh+Object], rax
0x14003ad2a  mov     rcx, rbx
0x14003ad2d  mov     eax, [rbx+48h]
0x14003ad30  btr     eax, 8
0x14003ad34  mov     [rbx+1B4h], edi
0x14003ad3a  mov     [rbx+48h], eax
0x14003ad3d  call    AfdNotifySockEventsChangedUnderLock
0x14003ad42  mov     ecx, [rbx+8]
0x14003ad45  bt      ecx, 16h
0x14003ad49  jnb     short loc_14003AD87
0x14003ad4b  mov     rcx, [r13+28h]
0x14003ad4f  mov     rdx, r14
0x14003ad52  call    AfdTdi_TA6toTA4_InPlace
0x14003ad57  test    al, al
0x14003ad59  jz      short loc_14003AD73
0x14003ad5b  mov     rax, [rbx+118h]
0x14003ad62  mov     rdi, [rax+8]
0x14003ad66  mov     r12, [rax+10h]
0x14003ad6a  or      dword ptr [rbx+0C0h], 20h
0x14003ad71  jmp     short loc_14003AD9D
0x14003ad73  mov     eax, [rbx+0C0h]
0x14003ad79  and     eax, 0FFFFFFDFh
0x14003ad7c  or      eax, 40h
0x14003ad7f  mov     [rbx+0C0h], eax
0x14003ad85  jmp     short loc_14003AD99
0x14003ad87  bt      ecx, 15h
0x14003ad8b  jnb     short loc_14003AD99
0x14003ad8d  mov     rcx, [r13+28h]
0x14003ad91  mov     rdx, r14
0x14003ad94  call    AfdTdi_TA6toTA4_InPlace
0x14003ad99  mov     rdi, [rbp+4Fh+Object]
0x14003ad9d  xor     r8d, r8d
0x14003ada0  lea     rdx, [rbp+4Fh+LockHandle]
0x14003ada4  mov     rcx, rbx
0x14003ada7  call    AfdNotifySockIndicateEventsUnlock
0x14003adac  mov     rax, [rsi+0B8h]
0x14003adb3  lea     rcx, AfdRestartDgConnect
0x14003adba  mov     [rax-10h], rcx
0x14003adbe  mov     [rax-8], rbx
0x14003adc2  mov     byte ptr [rax-45h], 0E0h
0x14003adc6  lea     rax, [r13+30h]
  ... truncated ...
```
