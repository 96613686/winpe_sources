# AfdRestartDelayedAcceptListen

- ea: `0x14004c770`
- end: `0x14004ccd4`
- name: `AfdRestartDelayedAcceptListen`
- size: `1380`
- prototype: ``
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
- `0x140036dcc`
- `0x140044a30`
- `0x14004c770`
- `0x14004f6d4`
- `0x1400504cc`
- `0x140072980`
- `0x14009304c`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14004c86d`
- `ntoskrnl!IoFreeIrp` at `0x14004c86d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c814`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004cb7c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c814`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004cb7c`
- `ntoskrnl!IofCompleteRequest` at `0x14004cba5`
- `ntoskrnl!IofCompleteRequest` at `0x14004cba5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c805`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004cb6d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c805`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004cb6d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c7f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c85a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c9fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004caba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004cb4f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c7f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c85a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c9fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004caba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004cb4f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c7e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c822`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c8fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cbb8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c7e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c822`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c8fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004cbb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c95f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c95f`

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
  __int64 v18; // rdx
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
        PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v14, 34);
      *(_DWORD *)(a3 + 160) = 34;
    }
    else
    {
      v18 = *(int *)(v15 + 208);
      if ( *(_DWORD *)(v15 + 208) > (unsigned int)AfdStandardAddressLength )
        PoolPriority = (void *)AfdAllocatePoolPriority(64, v18, 1382311489, 0);
      else
        PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v14, v18);
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
  v30 = AfdIndicatePollEvent(v29, 128, 0, &LockHandle);
  p_LockHandle = &LockHandle;
  if ( v30 )
    p_LockHandle = 0;
  AfdNotifySockIndicateEventsUnlock(v3, p_LockHandle, 0);
  if ( *(int *)(v3 + 176) > 0 || (*(_DWORD *)(v3 + 8) & 0x400000) != 0 && *(int *)(*(_QWORD *)(v3 + 280) + 48LL) > 0 )
    AfdInitiateListenBacklogReplenish(v3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14004c770  mov     [rsp-28h+arg_0], rbx
0x14004c775  mov     [rsp-28h+arg_8], rsi
0x14004c77a  push    rbp
0x14004c77b  push    rdi
0x14004c77c  push    r13
0x14004c77e  push    r14
0x14004c780  push    r15
0x14004c782  mov     rbp, rsp
0x14004c785  sub     rsp, 50h
0x14004c789  mov     rsi, [r8+8]
0x14004c78d  xorps   xmm0, xmm0
0x14004c790  xor     eax, eax
0x14004c792  mov     rdi, r8
0x14004c795  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004c799  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14004c79d  mov     r14, rdx
0x14004c7a0  lea     r13d, [rax+1]
0x14004c7a4  test    byte ptr cs:xmmword_1400875E0+1, r13b
0x14004c7ab  jz      short loc_14004C7CC
0x14004c7ad  lea     edx, [rax+13h]
0x14004c7b0  mov     ecx, 408h
0x14004c7b5  mov     eax, [r14+30h]
0x14004c7b9  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004c7c0  mov     r9, rsi
0x14004c7c3  mov     [rsp+50h+var_30], eax
0x14004c7c7  call    WPP_SF_qD
0x14004c7cc  xor     eax, eax
0x14004c7ce  lea     r15, [rsi+38h]
0x14004c7d2  xchg    rax, [rdi+28h]
0x14004c7d6  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004c7da  mov     rcx, r15; SpinLock
0x14004c7dd  test    rax, rax
0x14004c7e0  jnz     short loc_14004C822
0x14004c7e2  mov     byte ptr [rbp+Irql], al
0x14004c7e5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c7ec  nop     dword ptr [rax+rax+00h]
0x14004c7f1  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c7f5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004c7fc  nop     dword ptr [rax+rax+00h]
0x14004c801  lea     rcx, [rbp+Irql]; Irql
0x14004c805  call    cs:__imp_IoAcquireCancelSpinLock
0x14004c80c  nop     dword ptr [rax+rax+00h]
0x14004c811  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004c814  call    cs:__imp_IoReleaseCancelSpinLock
0x14004c81b  nop     dword ptr [rax+rax+00h]
0x14004c820  jmp     short loc_14004C866
0x14004c822  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c829  nop     dword ptr [rax+rax+00h]
0x14004c82e  lea     rax, [rdi+0B0h]
0x14004c835  mov     rdx, [rax]
0x14004c838  cmp     [rdx+8], rax
0x14004c83c  jnz     loc_14004CCCD
0x14004c842  mov     rcx, [rax+8]
0x14004c846  cmp     [rcx], rax
0x14004c849  jnz     loc_14004CCCD
0x14004c84f  mov     [rcx], rdx
0x14004c852  mov     [rdx+8], rcx
0x14004c856  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c85a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004c861  nop     dword ptr [rax+rax+00h]
0x14004c866  mov     ebx, [r14+30h]
0x14004c86a  mov     rcx, r14; Irp
0x14004c86d  call    cs:__imp_IoFreeIrp
0x14004c874  nop     dword ptr [rax+rax+00h]
0x14004c879  test    ebx, ebx
0x14004c87b  jns     short loc_14004C8D6
0x14004c87d  mov     eax, [rdi+4]
0x14004c880  test    al, 2
0x14004c882  jz      short loc_14004C89A
0x14004c884  mov     eax, [rsi+8]
0x14004c887  bt      eax, 16h
0x14004c88b  jnb     short loc_14004C89A
0x14004c88d  mov     rsi, [rsi+118h]
0x14004c894  add     rsi, 30h ; '0'
0x14004c898  jmp     short loc_14004C8A1
0x14004c89a  add     rsi, 0B0h
0x14004c8a1  lock add [rsi], r13d
0x14004c8a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004c8a9  lock xadd [rdi+30h], rax
0x14004c8af  sub     rax, r13
0x14004c8b2  jg      loc_14004CCAE
0x14004c8b8  test    rax, rax
0x14004c8bb  jnz     short loc_14004C8CA
0x14004c8bd  mov     rcx, rdi
0x14004c8c0  call    AfdCloseConnection
0x14004c8c5  jmp     loc_14004CCAE
0x14004c8ca  mov     ecx, 0Eh
0x14004c8cf  int     29h; Win8: RtlFailFast(ecx)
0x14004c8d1  jmp     loc_14004CCAE
0x14004c8d6  mov     rcx, rdi
0x14004c8d9  call    AfdAddConnectedReference
0x14004c8de  cmp     byte ptr [rsi+2], 6
0x14004c8e2  jz      loc_14004CC5C
0x14004c8e8  mov     eax, [rsi+8]
0x14004c8eb  bt      eax, 0Bh
0x14004c8ef  jb      loc_14004CC5C
0x14004c8f5  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004c8f9  mov     rcx, r15; SpinLock
0x14004c8fc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004c903  nop     dword ptr [rax+rax+00h]
0x14004c908  mov     rbx, [rdi+0E0h]
0x14004c90f  mov     rax, [rdi+98h]
0x14004c916  mov     [rbp+Irql], rbx
0x14004c91a  cmp     rax, [rbx+0D8h]
0x14004c921  jz      loc_14004CA34
0x14004c927  test    rax, rax
0x14004c92a  jz      short loc_14004C976
0x14004c92c  mov     ecx, [rdi+0A0h]
0x14004c932  cmp     ecx, [rbx+0D0h]
0x14004c938  jnb     loc_14004CA1E
0x14004c93e  cmp     ecx, cs:AfdStandardAddressLength
0x14004c944  ja      short loc_14004C957
0x14004c946  mov     rcx, cs:PplAddressPool
0x14004c94d  mov     rdx, rax
0x14004c950  call    PplFreeToLookasideList
0x14004c955  jmp     short loc_14004C96B
0x14004c957  mov     edx, 52646641h; Tag
0x14004c95c  mov     rcx, rax; P
0x14004c95f  call    cs:__imp_ExFreePoolWithTag
0x14004c966  nop     dword ptr [rax+rax+00h]
0x14004c96b  mov     qword ptr [rdi+98h], 0
0x14004c976  mov     eax, [rdi+4]
0x14004c979  test    al, 2
0x14004c97b  jz      short loc_14004C9BA
0x14004c97d  cmp     dword ptr [rbx+0D0h], 16h
0x14004c984  jnz     short loc_14004C9BA
0x14004c986  mov     r14d, 22h ; '"'
0x14004c98c  cmp     cs:AfdStandardAddressLength, r14d
0x14004c993  mov     edx, r14d
0x14004c996  jb      short loc_14004C99F
0x14004c998  call    AfdAllocateZeroedFromLookasideList
0x14004c99d  jmp     short loc_14004C9B1
0x14004c99f  xor     r9d, r9d
0x14004c9a2  mov     r8d, 52646641h
0x14004c9a8  lea     ecx, [r9+40h]
0x14004c9ac  call    AfdAllocatePoolPriority
0x14004c9b1  mov     [rdi+0A0h], r14d
0x14004c9b8  jmp     short loc_14004C9E5
0x14004c9ba  movsxd  rax, dword ptr [rbx+0D0h]
0x14004c9c1  cmp     eax, cs:AfdStandardAddressLength
0x14004c9c7  mov     rdx, rax
0x14004c9ca  ja      short loc_14004C9D3
0x14004c9cc  call    AfdAllocateZeroedFromLookasideList
0x14004c9d1  jmp     short loc_14004C9E5
0x14004c9d3  xor     r9d, r9d
0x14004c9d6  mov     r8d, 52646641h
0x14004c9dc  lea     ecx, [r9+40h]
0x14004c9e0  call    AfdAllocatePoolPriority
0x14004c9e5  mov     [rdi+98h], rax
0x14004c9ec  test    rax, rax
0x14004c9ef  jnz     short loc_14004CA1E
0x14004c9f1  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004c9f5  mov     [rdi+0A0h], eax
0x14004c9fb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ca02  nop     dword ptr [rax+rax+00h]
0x14004ca07  test    byte ptr cs:xmmword_1400875D0+9, r13b
0x14004ca0e  jz      loc_14004CC7E
0x14004ca14  mov     edx, 15h
0x14004ca19  jmp     loc_14004CC6A
0x14004ca1e  movsxd  r8, dword ptr [rbx+0D0h]; Size
0x14004ca25  mov     rcx, rax; void *
0x14004ca28  mov     rdx, [rbx+0D8h]; Src
0x14004ca2f  call    memmove
0x14004ca34  mov     eax, [rdi+4]
0x14004ca37  lea     r14, [rdi+0A0h]
0x14004ca3e  test    al, 2
0x14004ca40  jz      short loc_14004CA55
0x14004ca42  mov     rcx, [rdi+98h]; void *
0x14004ca49  mov     rdx, r14
0x14004ca4c  call    AfdTdi_TA4toTA6_InPlace
0x14004ca51  test    al, al
0x14004ca53  jnz     short loc_14004CA5E
0x14004ca55  mov     eax, [rbx+0D0h]
0x14004ca5b  mov     [r14], eax
0x14004ca5e  mov     r8, [rbx+0B8h]
0x14004ca65  test    r8, r8
0x14004ca68  jz      short loc_14004CA8C
0x14004ca6a  mov     r9d, [rbx+0B0h]
0x14004ca71  test    r9d, r9d
0x14004ca74  jle     short loc_14004CA8C
0x14004ca76  mov     edx, 1204Bh
0x14004ca7b  lea     rcx, [rbp+Irql]
0x14004ca7f  call    AfdSaveReceivedConnectData
0x14004ca84  test    eax, eax
0x14004ca86  js      short loc_14004CAB6
0x14004ca88  mov     rbx, [rbp+Irql]
0x14004ca8c  mov     r8, [rbx+0C8h]
0x14004ca93  test    r8, r8
0x14004ca96  jz      short loc_14004CACB
0x14004ca98  mov     r9d, [rbx+0C0h]
0x14004ca9f  test    r9d, r9d
0x14004caa2  jle     short loc_14004CACB
0x14004caa4  mov     edx, 1204Fh
0x14004caa9  lea     rcx, [rbp+Irql]
0x14004caad  call    AfdSaveReceivedConnectData
0x14004cab2  test    eax, eax
0x14004cab4  jns     short loc_14004CACB
0x14004cab6  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004caba  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004cac1  nop     dword ptr [rax+rax+00h]
0x14004cac6  jmp     loc_14004CC7E
0x14004cacb  mov     [rdi+2], r13w
0x14004cad0  lea     r14, [rsi+80h]
0x14004cad7  mov     rax, [r14]
0x14004cada  cmp     rax, r14
0x14004cadd  jz      loc_14004CBC9
0x14004cae3  cmp     [rax+8], r14
0x14004cae7  jnz     loc_14004CCCD
0x14004caed  mov     rcx, [rax]
0x14004caf0  cmp     [rcx+8], rax
0x14004caf4  jnz     loc_14004CCCD
0x14004cafa  mov     [r14], rcx
0x14004cafd  lea     rbx, [rax-0A8h]
0x14004cb04  mov     [rcx+8], r14
0x14004cb08  mov     qword ptr [rax], 0
0x14004cb0f  test    byte ptr cs:xmmword_1400875E0+1, r13b
0x14004cb16  jz      short loc_14004CB31
0x14004cb18  mov     edx, 16h
0x14004cb1d  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004cb24  mov     ecx, 408h
0x14004cb29  mov     r9, rbx
0x14004cb2c  call    WPP_SF_q
0x14004cb31  xor     r9d, r9d
0x14004cb34  lea     r8, [rbp+LockHandle]
0x14004cb38  mov     rdx, rdi
0x14004cb3b  mov     rcx, rbx; Irp
0x14004cb3e  call    AfdServiceWaitForListen
0x14004cb43  test    eax, eax
0x14004cb45  jns     loc_14004CCAE
0x14004cb4b  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004cb4f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004cb56  nop     dword ptr [rax+rax+00h]
0x14004cb5b  xor     eax, eax
0x14004cb5d  xchg    rax, [rbx+68h]
0x14004cb61  test    rax, rax
0x14004cb64  jnz     short loc_14004CB88
0x14004cb66  lea     rcx, [rbp+Irql]; Irql
0x14004cb6a  mov     byte ptr [rbp+Irql], al
0x14004cb6d  call    cs:__imp_IoAcquireCancelSpinLock
0x14004cb74  nop     dword ptr [rax+rax+00h]
0x14004cb79  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004cb7c  call    cs:__imp_IoReleaseCancelSpinLock
0x14004cb83  nop     dword ptr [rax+rax+00h]
0x14004cb88  mov     r9d, [rbx+30h]
0x14004cb8c  mov     r8, rsi
0x14004cb8f  mov     edx, 1850h
0x14004cb94  mov     ecx, r13d
0x14004cb97  call    AFDETW_TRACEWAITLISTEN
0x14004cb9c  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004cba2  mov     rcx, rbx; Irp
0x14004cba5  call    cs:__imp_IofCompleteRequest
0x14004cbac  nop     dword ptr [rax+rax+00h]
0x14004cbb1  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004cbb5  mov     rcx, r15; SpinLock
0x14004cbb8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004cbbf  nop     dword ptr [rax+rax+00h]
0x14004cbc4  jmp     loc_14004CAD7
0x14004cbc9  lea     rcx, [rsi+60h]
0x14004cbcd  mov     rdx, [rcx+8]
0x14004cbd1  cmp     [rdx], rcx
0x14004cbd4  jnz     loc_14004CCCD
0x14004cbda  lea     rax, [rdi+0B0h]
0x14004cbe1  mov     ebx, 80h
0x14004cbe6  mov     [rax], rcx
0x14004cbe9  xor     r8d, r8d
0x14004cbec  mov     [rax+8], rdx
0x14004cbf0  mov     [rdx], rax
0x14004cbf3  mov     edx, ebx
0x14004cbf5  mov     [rcx+8], rax
0x14004cbf9  mov     rcx, rsi
0x14004cbfc  call    AfdIndicateEventSelectEvent
0x14004cc01  xor     r8d, r8d
0x14004cc04  mov     edx, ebx
0x14004cc06  mov     rcx, rsi
0x14004cc09  call    AfdNotifySockEventsChangedUnderLock
0x14004cc0e  xor     r8d, r8d
0x14004cc11  lea     r9, [rbp+LockHandle]
0x14004cc15  mov     edx, ebx
0x14004cc17  call    AfdIndicatePollEvent
0x14004cc1c  xor     ecx, ecx
0x14004cc1e  lea     rdx, [rbp+LockHandle]
0x14004cc22  test    al, al
0x14004cc24  cmovnz  rdx, rcx
0x14004cc28  xor     r8d, r8d
0x14004cc2b  mov     rcx, rsi
0x14004cc2e  call    AfdNotifySockIndicateEventsUnlock
0x14004cc33  cmp     dword ptr [rsi+0B0h], 0
0x14004cc3a  jg      short loc_14004CC52
0x14004cc3c  mov     eax, [rsi+8]
0x14004cc3f  bt      eax, 16h
0x14004cc43  jnb     short loc_14004CCAE
0x14004cc45  mov     rax, [rsi+118h]
0x14004cc4c  cmp     dword ptr [rax+30h], 0
0x14004cc50  jle     short loc_14004CCAE
0x14004cc52  mov     rcx, rsi
0x14004cc55  call    AfdInitiateListenBacklogReplenish
0x14004cc5a  jmp     short loc_14004CCAE
0x14004cc5c  test    byte ptr cs:xmmword_1400875D0+9, r13b
0x14004cc63  jz      short loc_14004CC7E
0x14004cc65  mov     edx, 14h
  ... truncated ...
```
