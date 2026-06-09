# AfdRestartDelayedAcceptListen

- ea: `0x14004c6d0`
- end: `0x14004cc34`
- name: `AfdRestartDelayedAcceptListen`
- size: `1380`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002440`
- `0x140003670`
- `0x140004c10`
- `0x14000f450`
- `0x140013030`
- `0x1400137a0`
- `0x140015990`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001c708`
- `0x14002dc3c`
- `0x140036dac`
- `0x140044a10`
- `0x14004c6d0`
- `0x14004f634`
- `0x14005042c`
- `0x140072800`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14004c7cd`
- `ntoskrnl!IoFreeIrp` at `0x14004c7cd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c774`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004cadc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c774`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004cadc`
- `ntoskrnl!IofCompleteRequest` at `0x14004cb05`
- `ntoskrnl!IofCompleteRequest` at `0x14004cb05`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c765`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004cacd`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c765`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004cacd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c755`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c7ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c95b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ca1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004caaf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c755`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c7ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c95b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ca1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004caaf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c782`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c85c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cb18`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c782`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c85c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c8bf`

## pseudocode

```c
__int64 __fastcall AfdRestartDelayedAcceptListen(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rsi
  KSPIN_LOCK *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  int Status; // ebx
  volatile signed __int32 *v10; // rsi
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  void *PoolPriority; // rax
  unsigned int v17; // ecx
  size_t v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  _QWORD **v24; // r14
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  _QWORD *v27; // rbx
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  char v30; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  volatile signed __int32 *v32; // rsi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF
  __int64 Irql; // [rsp+90h] [rbp+40h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qD(1032, 19, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, v3, a2->IoStatus.Status);
  v6 = (KSPIN_LOCK *)(v3 + 56);
  if ( _InterlockedExchange64((volatile __int64 *)(a3 + 40), 0) )
  {
    KeAcquireInStackQueuedSpinLock(v6, &LockHandle);
    v7 = *(_QWORD *)(a3 + 176);
    if ( *(_QWORD *)(v7 + 8) != a3 + 176 )
      goto LABEL_76;
    v8 = *(_QWORD **)(a3 + 184);
    if ( *v8 != a3 + 176 )
      goto LABEL_76;
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    LOBYTE(Irql) = 0;
    KeAcquireInStackQueuedSpinLock(v6, &LockHandle);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IoAcquireCancelSpinLock((PKIRQL)&Irql);
    IoReleaseCancelSpinLock(Irql);
  }
  Status = a2->IoStatus.Status;
  IoFreeIrp(a2);
  if ( Status < 0 )
  {
    if ( (*(_DWORD *)(a3 + 4) & 2) != 0 && (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
      v10 = (volatile signed __int32 *)(*(_QWORD *)(v3 + 280) + 48LL);
    else
      v10 = (volatile signed __int32 *)(v3 + 176);
    _InterlockedAdd(v10, 1u);
    v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a3 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v12 = v11 <= 1;
    v13 = v11 - 1;
    if ( v12 )
    {
      if ( v13 )
        __fastfail(0xEu);
      AfdCloseConnection(a3);
    }
    return 3221225494LL;
  }
  AfdAddConnectedReference(a3);
  if ( *(_BYTE *)(v3 + 2) == 6 || (*(_DWORD *)(v3 + 8) & 0x800) != 0 )
  {
    if ( (BYTE9(xmmword_1400875D0) & 1) == 0 )
      goto LABEL_70;
    v19 = 20;
LABEL_69:
    WPP_SF_q(776, v19, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, v3);
LABEL_70:
    if ( (*(_DWORD *)(a3 + 4) & 2) != 0 && (*(_DWORD *)(v3 + 8) & 0x400000) != 0 )
      v32 = (volatile signed __int32 *)(*(_QWORD *)(v3 + 280) + 48LL);
    else
      v32 = (volatile signed __int32 *)(v3 + 176);
    _InterlockedAdd(v32, 1u);
    AfdAbortConnection(a3);
    return 3221225494LL;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
  v15 = *(_QWORD *)(a3 + 224);
  PoolPriority = *(void **)(a3 + 152);
  Irql = v15;
  if ( PoolPriority == *(void **)(v15 + 216) )
    goto LABEL_39;
  if ( !PoolPriority )
    goto LABEL_26;
  v17 = *(_DWORD *)(a3 + 160);
  if ( v17 < *(_DWORD *)(v15 + 208) )
  {
    if ( v17 > (unsigned int)AfdStandardAddressLength )
      ExFreePoolWithTag(PoolPriority, 0x52646641u);
    else
      PplFreeToLookasideList((__int64)PplAddressPool, PoolPriority);
    *(_QWORD *)(a3 + 152) = 0;
LABEL_26:
    if ( (*(_DWORD *)(a3 + 4) & 2) != 0 && *(_DWORD *)(v15 + 208) == 22 )
    {
      if ( (unsigned int)AfdStandardAddressLength < 0x22 )
        PoolPriority = (void *)AfdAllocatePoolPriority(64, 34, 1382311489, 0);
      else
        PoolPriority = AfdAllocateZeroedFromLookasideList(v14, 0x22u);
      *(_DWORD *)(a3 + 160) = 34;
    }
    else
    {
      v18 = *(int *)(v15 + 208);
      if ( *(_DWORD *)(v15 + 208) > (unsigned int)AfdStandardAddressLength )
        PoolPriority = (void *)AfdAllocatePoolPriority(64, v18, 1382311489, 0);
      else
        PoolPriority = AfdAllocateZeroedFromLookasideList(v14, v18);
    }
    *(_QWORD *)(a3 + 152) = PoolPriority;
    if ( !PoolPriority )
    {
      *(_DWORD *)(a3 + 160) = 0;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( (BYTE9(xmmword_1400875D0) & 1) == 0 )
        goto LABEL_70;
      v19 = 21;
      goto LABEL_69;
    }
  }
  memmove(PoolPriority, *(const void **)(v15 + 216), *(int *)(v15 + 208));
LABEL_39:
  if ( (*(_DWORD *)(a3 + 4) & 2) == 0 || !(unsigned __int8)AfdTdi_TA4toTA6_InPlace(*(void **)(a3 + 152)) )
    *(_DWORD *)(a3 + 160) = *(_DWORD *)(v15 + 208);
  v20 = *(_QWORD *)(v15 + 184);
  if ( v20 )
  {
    v21 = *(unsigned int *)(v15 + 176);
    if ( (int)v21 > 0 )
    {
      if ( (int)AfdSaveReceivedConnectData(&Irql, 73803, v20, v21) < 0 )
      {
LABEL_49:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        goto LABEL_70;
      }
      v15 = Irql;
    }
  }
  v22 = *(_QWORD *)(v15 + 200);
  if ( v22 )
  {
    v23 = *(unsigned int *)(v15 + 192);
    if ( (int)v23 > 0 && (int)AfdSaveReceivedConnectData(&Irql, 73807, v22, v23) < 0 )
      goto LABEL_49;
  }
  *(_WORD *)(a3 + 2) = 1;
  v24 = (_QWORD **)(v3 + 128);
  while ( 1 )
  {
    v25 = *v24;
    if ( *v24 == v24 )
      break;
    if ( (_QWORD **)v25[1] != v24 )
      goto LABEL_76;
    v26 = (_QWORD *)*v25;
    if ( *(_QWORD **)(*v25 + 8LL) != v25 )
      goto LABEL_76;
    *v24 = v26;
    v27 = v25 - 21;
    v26[1] = v24;
    *v25 = 0;
    if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_q(1032, 22, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, v25 - 21);
    if ( (int)AfdServiceWaitForListen((PIRP)v27, a3, &LockHandle, 0) >= 0 )
      return 3221225494LL;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( !_InterlockedExchange64(v27 + 13, 0) )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    AFDETW_TRACEWAITLISTEN(1, 6224, v3, *((unsigned int *)v27 + 12));
    IofCompleteRequest((PIRP)v27, AfdPriorityBoost);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
  }
  v28 = *(_QWORD **)(v3 + 104);
  if ( *v28 != v3 + 96 )
LABEL_76:
    __fastfail(3u);
  *(_QWORD *)(a3 + 176) = v3 + 96;
  *(_QWORD *)(a3 + 184) = v28;
  *v28 = a3 + 176;
  *(_QWORD *)(v3 + 104) = a3 + 176;
  AfdIndicateEventSelectEvent(v3, 128, 0);
  AfdNotifySockEventsChangedUnderLock(v3, 128, 0);
  v30 = AfdIndicatePollEvent(v29, 0x80u, 0, &LockHandle);
  p_LockHandle = &LockHandle;
  if ( v30 )
    p_LockHandle = 0;
  AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v3, p_LockHandle, 0);
  if ( *(int *)(v3 + 176) > 0 || (*(_DWORD *)(v3 + 8) & 0x400000) != 0 && *(int *)(*(_QWORD *)(v3 + 280) + 48LL) > 0 )
    AfdInitiateListenBacklogReplenish(v3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14004c6d0  mov     [rsp-28h+arg_0], rbx
0x14004c6d5  mov     [rsp-28h+arg_8], rsi
0x14004c6da  push    rbp
0x14004c6db  push    rdi
0x14004c6dc  push    r13
0x14004c6de  push    r14
0x14004c6e0  push    r15
0x14004c6e2  mov     rbp, rsp
0x14004c6e5  sub     rsp, 50h
0x14004c6e9  mov     rsi, [r8+8]
0x14004c6ed  xorps   xmm0, xmm0
0x14004c6f0  xor     eax, eax
0x14004c6f2  mov     rdi, r8
0x14004c6f5  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004c6f9  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14004c6fd  mov     r14, rdx
0x14004c700  lea     r13d, [rax+1]
0x14004c704  test    byte ptr cs:xmmword_1400875E0+1, r13b
0x14004c70b  jz      short loc_14004C72C
0x14004c70d  lea     edx, [rax+13h]
0x14004c710  mov     ecx, 408h
0x14004c715  mov     eax, [r14+30h]
0x14004c719  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004c720  mov     r9, rsi
0x14004c723  mov     [rsp+50h+var_30], eax
0x14004c727  call    WPP_SF_qD
0x14004c72c  xor     eax, eax
0x14004c72e  lea     r15, [rsi+38h]
0x14004c732  xchg    rax, [rdi+28h]
0x14004c736  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004c73a  mov     rcx, r15; SpinLock
0x14004c73d  test    rax, rax
0x14004c740  jnz     short loc_14004C782
0x14004c742  mov     byte ptr [rbp+Irql], al
0x14004c745  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c74c  nop     dword ptr [rax+rax+00h]
0x14004c751  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c755  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004c75c  nop     dword ptr [rax+rax+00h]
0x14004c761  lea     rcx, [rbp+Irql]; Irql
0x14004c765  call    cs:__imp_IoAcquireCancelSpinLock
0x14004c76c  nop     dword ptr [rax+rax+00h]
0x14004c771  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004c774  call    cs:__imp_IoReleaseCancelSpinLock
0x14004c77b  nop     dword ptr [rax+rax+00h]
0x14004c780  jmp     short loc_14004C7C6
0x14004c782  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c789  nop     dword ptr [rax+rax+00h]
0x14004c78e  lea     rax, [rdi+0B0h]
0x14004c795  mov     rdx, [rax]
0x14004c798  cmp     [rdx+8], rax
0x14004c79c  jnz     loc_14004CC2D
0x14004c7a2  mov     rcx, [rax+8]
0x14004c7a6  cmp     [rcx], rax
0x14004c7a9  jnz     loc_14004CC2D
0x14004c7af  mov     [rcx], rdx
0x14004c7b2  mov     [rdx+8], rcx
0x14004c7b6  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c7ba  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004c7c1  nop     dword ptr [rax+rax+00h]
0x14004c7c6  mov     ebx, [r14+30h]
0x14004c7ca  mov     rcx, r14; Irp
0x14004c7cd  call    cs:__imp_IoFreeIrp
0x14004c7d4  nop     dword ptr [rax+rax+00h]
0x14004c7d9  test    ebx, ebx
0x14004c7db  jns     short loc_14004C836
0x14004c7dd  mov     eax, [rdi+4]
0x14004c7e0  test    al, 2
0x14004c7e2  jz      short loc_14004C7FA
0x14004c7e4  mov     eax, [rsi+8]
0x14004c7e7  bt      eax, 16h
0x14004c7eb  jnb     short loc_14004C7FA
0x14004c7ed  mov     rsi, [rsi+118h]
0x14004c7f4  add     rsi, 30h ; '0'
0x14004c7f8  jmp     short loc_14004C801
0x14004c7fa  add     rsi, 0B0h
0x14004c801  lock add [rsi], r13d
0x14004c805  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004c809  lock xadd [rdi+30h], rax
0x14004c80f  sub     rax, r13
0x14004c812  jg      loc_14004CC0E
0x14004c818  test    rax, rax
0x14004c81b  jnz     short loc_14004C82A
0x14004c81d  mov     rcx, rdi
0x14004c820  call    AfdCloseConnection
0x14004c825  jmp     loc_14004CC0E
0x14004c82a  mov     ecx, 0Eh
0x14004c82f  int     29h; Win8: RtlFailFast(ecx)
0x14004c831  jmp     loc_14004CC0E
0x14004c836  mov     rcx, rdi
0x14004c839  call    AfdAddConnectedReference
0x14004c83e  cmp     byte ptr [rsi+2], 6
0x14004c842  jz      loc_14004CBBC
0x14004c848  mov     eax, [rsi+8]
0x14004c84b  bt      eax, 0Bh
0x14004c84f  jb      loc_14004CBBC
0x14004c855  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004c859  mov     rcx, r15; SpinLock
0x14004c85c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c863  nop     dword ptr [rax+rax+00h]
0x14004c868  mov     rbx, [rdi+0E0h]
0x14004c86f  mov     rax, [rdi+98h]
0x14004c876  mov     [rbp+Irql], rbx
0x14004c87a  cmp     rax, [rbx+0D8h]
0x14004c881  jz      loc_14004C994
0x14004c887  test    rax, rax
0x14004c88a  jz      short loc_14004C8D6
0x14004c88c  mov     ecx, [rdi+0A0h]
0x14004c892  cmp     ecx, [rbx+0D0h]
0x14004c898  jnb     loc_14004C97E
0x14004c89e  cmp     ecx, cs:AfdStandardAddressLength
0x14004c8a4  ja      short loc_14004C8B7
0x14004c8a6  mov     rcx, cs:PplAddressPool
0x14004c8ad  mov     rdx, rax
0x14004c8b0  call    PplFreeToLookasideList
0x14004c8b5  jmp     short loc_14004C8CB
0x14004c8b7  mov     edx, 52646641h; Tag
0x14004c8bc  mov     rcx, rax; P
0x14004c8bf  call    cs:__imp_ExFreePoolWithTag
0x14004c8c6  nop     dword ptr [rax+rax+00h]
0x14004c8cb  mov     qword ptr [rdi+98h], 0
0x14004c8d6  mov     eax, [rdi+4]
0x14004c8d9  test    al, 2
0x14004c8db  jz      short loc_14004C91A
0x14004c8dd  cmp     dword ptr [rbx+0D0h], 16h
0x14004c8e4  jnz     short loc_14004C91A
0x14004c8e6  mov     r14d, 22h ; '"'
0x14004c8ec  cmp     cs:AfdStandardAddressLength, r14d
0x14004c8f3  mov     edx, r14d
0x14004c8f6  jb      short loc_14004C8FF
0x14004c8f8  call    AfdAllocateZeroedFromLookasideList
0x14004c8fd  jmp     short loc_14004C911
0x14004c8ff  xor     r9d, r9d
0x14004c902  mov     r8d, 52646641h
0x14004c908  lea     ecx, [r9+40h]
0x14004c90c  call    AfdAllocatePoolPriority
0x14004c911  mov     [rdi+0A0h], r14d
0x14004c918  jmp     short loc_14004C945
0x14004c91a  movsxd  rax, dword ptr [rbx+0D0h]
0x14004c921  cmp     eax, cs:AfdStandardAddressLength
0x14004c927  mov     rdx, rax
0x14004c92a  ja      short loc_14004C933
0x14004c92c  call    AfdAllocateZeroedFromLookasideList
0x14004c931  jmp     short loc_14004C945
0x14004c933  xor     r9d, r9d
0x14004c936  mov     r8d, 52646641h
0x14004c93c  lea     ecx, [r9+40h]
0x14004c940  call    AfdAllocatePoolPriority
0x14004c945  mov     [rdi+98h], rax
0x14004c94c  test    rax, rax
0x14004c94f  jnz     short loc_14004C97E
0x14004c951  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c955  mov     [rdi+0A0h], eax
0x14004c95b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004c962  nop     dword ptr [rax+rax+00h]
0x14004c967  test    byte ptr cs:xmmword_1400875D0+9, r13b
0x14004c96e  jz      loc_14004CBDE
0x14004c974  mov     edx, 15h
0x14004c979  jmp     loc_14004CBCA
0x14004c97e  movsxd  r8, dword ptr [rbx+0D0h]; Size
0x14004c985  mov     rcx, rax; void *
0x14004c988  mov     rdx, [rbx+0D8h]; Src
0x14004c98f  call    memmove
0x14004c994  mov     eax, [rdi+4]
0x14004c997  lea     r14, [rdi+0A0h]
0x14004c99e  test    al, 2
0x14004c9a0  jz      short loc_14004C9B5
0x14004c9a2  mov     rcx, [rdi+98h]; void *
0x14004c9a9  mov     rdx, r14
0x14004c9ac  call    AfdTdi_TA4toTA6_InPlace
0x14004c9b1  test    al, al
0x14004c9b3  jnz     short loc_14004C9BE
0x14004c9b5  mov     eax, [rbx+0D0h]
0x14004c9bb  mov     [r14], eax
0x14004c9be  mov     r8, [rbx+0B8h]
0x14004c9c5  test    r8, r8
0x14004c9c8  jz      short loc_14004C9EC
0x14004c9ca  mov     r9d, [rbx+0B0h]
0x14004c9d1  test    r9d, r9d
0x14004c9d4  jle     short loc_14004C9EC
0x14004c9d6  mov     edx, 1204Bh
0x14004c9db  lea     rcx, [rbp+Irql]
0x14004c9df  call    AfdSaveReceivedConnectData
0x14004c9e4  test    eax, eax
0x14004c9e6  js      short loc_14004CA16
0x14004c9e8  mov     rbx, [rbp+Irql]
0x14004c9ec  mov     r8, [rbx+0C8h]
0x14004c9f3  test    r8, r8
0x14004c9f6  jz      short loc_14004CA2B
0x14004c9f8  mov     r9d, [rbx+0C0h]
0x14004c9ff  test    r9d, r9d
0x14004ca02  jle     short loc_14004CA2B
0x14004ca04  mov     edx, 1204Fh
0x14004ca09  lea     rcx, [rbp+Irql]
0x14004ca0d  call    AfdSaveReceivedConnectData
0x14004ca12  test    eax, eax
0x14004ca14  jns     short loc_14004CA2B
0x14004ca16  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004ca1a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ca21  nop     dword ptr [rax+rax+00h]
0x14004ca26  jmp     loc_14004CBDE
0x14004ca2b  mov     [rdi+2], r13w
0x14004ca30  lea     r14, [rsi+80h]
0x14004ca37  mov     rax, [r14]
0x14004ca3a  cmp     rax, r14
0x14004ca3d  jz      loc_14004CB29
0x14004ca43  cmp     [rax+8], r14
0x14004ca47  jnz     loc_14004CC2D
0x14004ca4d  mov     rcx, [rax]
0x14004ca50  cmp     [rcx+8], rax
0x14004ca54  jnz     loc_14004CC2D
0x14004ca5a  mov     [r14], rcx
0x14004ca5d  lea     rbx, [rax-0A8h]
0x14004ca64  mov     [rcx+8], r14
0x14004ca68  mov     qword ptr [rax], 0
0x14004ca6f  test    byte ptr cs:xmmword_1400875E0+1, r13b
0x14004ca76  jz      short loc_14004CA91
0x14004ca78  mov     edx, 16h
0x14004ca7d  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004ca84  mov     ecx, 408h
0x14004ca89  mov     r9, rbx
0x14004ca8c  call    WPP_SF_q
0x14004ca91  xor     r9d, r9d
0x14004ca94  lea     r8, [rbp+LockHandle]
0x14004ca98  mov     rdx, rdi
0x14004ca9b  mov     rcx, rbx; Irp
0x14004ca9e  call    AfdServiceWaitForListen
0x14004caa3  test    eax, eax
0x14004caa5  jns     loc_14004CC0E
0x14004caab  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004caaf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004cab6  nop     dword ptr [rax+rax+00h]
0x14004cabb  xor     eax, eax
0x14004cabd  xchg    rax, [rbx+68h]
0x14004cac1  test    rax, rax
0x14004cac4  jnz     short loc_14004CAE8
0x14004cac6  lea     rcx, [rbp+Irql]; Irql
0x14004caca  mov     byte ptr [rbp+Irql], al
0x14004cacd  call    cs:__imp_IoAcquireCancelSpinLock
0x14004cad4  nop     dword ptr [rax+rax+00h]
0x14004cad9  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004cadc  call    cs:__imp_IoReleaseCancelSpinLock
0x14004cae3  nop     dword ptr [rax+rax+00h]
0x14004cae8  mov     r9d, [rbx+30h]
0x14004caec  mov     r8, rsi
0x14004caef  mov     edx, 1850h
0x14004caf4  mov     ecx, r13d
0x14004caf7  call    AFDETW_TRACEWAITLISTEN
0x14004cafc  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004cb02  mov     rcx, rbx; Irp
0x14004cb05  call    cs:__imp_IofCompleteRequest
0x14004cb0c  nop     dword ptr [rax+rax+00h]
0x14004cb11  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004cb15  mov     rcx, r15; SpinLock
0x14004cb18  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004cb1f  nop     dword ptr [rax+rax+00h]
0x14004cb24  jmp     loc_14004CA37
0x14004cb29  lea     rcx, [rsi+60h]
0x14004cb2d  mov     rdx, [rcx+8]
0x14004cb31  cmp     [rdx], rcx
0x14004cb34  jnz     loc_14004CC2D
0x14004cb3a  lea     rax, [rdi+0B0h]
0x14004cb41  mov     ebx, 80h
0x14004cb46  mov     [rax], rcx
0x14004cb49  xor     r8d, r8d
0x14004cb4c  mov     [rax+8], rdx
0x14004cb50  mov     [rdx], rax
0x14004cb53  mov     edx, ebx
0x14004cb55  mov     [rcx+8], rax
0x14004cb59  mov     rcx, rsi
0x14004cb5c  call    AfdIndicateEventSelectEvent
0x14004cb61  xor     r8d, r8d
0x14004cb64  mov     edx, ebx
0x14004cb66  mov     rcx, rsi
0x14004cb69  call    AfdNotifySockEventsChangedUnderLock
0x14004cb6e  xor     r8d, r8d
0x14004cb71  lea     r9, [rbp+LockHandle]
0x14004cb75  mov     edx, ebx
0x14004cb77  call    AfdIndicatePollEvent
0x14004cb7c  xor     ecx, ecx
0x14004cb7e  lea     rdx, [rbp+LockHandle]
0x14004cb82  test    al, al
0x14004cb84  cmovnz  rdx, rcx
0x14004cb88  xor     r8d, r8d
0x14004cb8b  mov     rcx, rsi
0x14004cb8e  call    AfdNotifySockIndicateEventsUnlock
0x14004cb93  cmp     dword ptr [rsi+0B0h], 0
0x14004cb9a  jg      short loc_14004CBB2
0x14004cb9c  mov     eax, [rsi+8]
0x14004cb9f  bt      eax, 16h
0x14004cba3  jnb     short loc_14004CC0E
0x14004cba5  mov     rax, [rsi+118h]
0x14004cbac  cmp     dword ptr [rax+30h], 0
0x14004cbb0  jle     short loc_14004CC0E
0x14004cbb2  mov     rcx, rsi
0x14004cbb5  call    AfdInitiateListenBacklogReplenish
0x14004cbba  jmp     short loc_14004CC0E
0x14004cbbc  test    byte ptr cs:xmmword_1400875D0+9, r13b
0x14004cbc3  jz      short loc_14004CBDE
0x14004cbc5  mov     edx, 14h
  ... truncated ...
```
