# AfdTLInspectEventHandler

- ea: `0x14004d5b0`
- end: `0x14004da56`
- name: `AfdTLInspectEventHandler`
- size: `1190`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002440`
- `0x140003670`
- `0x1400044fc`
- `0x140004c10`
- `0x140005b60`
- `0x14000f390`
- `0x14000f450`
- `0x140013030`
- `0x1400137a0`
- `0x140015990`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001c708`
- `0x140036dcc`
- `0x14004d5b0`
- `0x140072980`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004d8e4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004d8e4`
- `ntoskrnl!IofCompleteRequest` at `0x14004d90c`
- `ntoskrnl!IofCompleteRequest` at `0x14004d90c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004d8d5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004d8d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d8b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d8b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d825`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d920`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d825`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d920`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d6d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d6d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d77e`

## pseudocode

```c
__int64 __fastcall AfdTLInspectEventHandler(__int64 a1, __int64 a2)
{
  char v4; // si
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  unsigned int v7; // r14d
  size_t v8; // r12
  PSLIST_ENTRY FreeConnection; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  size_t v12; // r15
  void *PoolPriority; // rax
  _DWORD *v14; // r14
  size_t v15; // r13
  size_t v16; // r8
  __int64 v17; // r13
  __int64 v18; // rcx
  void *ZeroedFromLookasideList; // rax
  _DWORD *v20; // r14
  size_t v21; // r15
  _QWORD **v22; // r15
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // r14
  char v26; // r12
  __int64 result; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  char v30; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  int v32; // eax
  signed __int64 v33; // rax
  bool v34; // cc
  signed __int64 v35; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-20h] BYREF
  __int64 Irql; // [rsp+80h] [rbp+40h] BYREF
  __int64 v38; // [rsp+88h] [rbp+48h]

  v38 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = 1;
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1032, 31, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
  _m_prefetchw((const void *)(a1 + 64));
  v5 = *(_QWORD *)(a1 + 64);
  do
  {
    if ( (unsigned __int64)(v5 + 1) <= 1 )
    {
      if ( v5 )
        __fastfail(0xEu);
      v4 = 0;
      goto LABEL_64;
    }
    v6 = v5;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v5 + 1, v5);
  }
  while ( v6 != v5 );
  if ( *(_BYTE *)(a1 + 2) == 6 || (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
  {
    if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
      WPP_SF_q(776, 32, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
    goto LABEL_64;
  }
  v7 = SOCKADDR_SIZE(**(_WORD **)(a2 + 24));
  v8 = SOCKADDR_SIZE(**(_WORD **)(a2 + 16));
  FreeConnection = AfdGetFreeConnection(a1, 0, &Irql);
  v11 = (__int64)FreeConnection;
  if ( !FreeConnection )
  {
LABEL_64:
    result = 2;
    goto LABEL_65;
  }
  v12 = v7;
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_q(1032, 33, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, FreeConnection);
  PoolPriority = *(void **)(v11 + 152);
  v14 = (_DWORD *)(v11 + 160);
  if ( !PoolPriority )
  {
LABEL_17:
    v15 = v12;
    if ( (unsigned int)v12 > (unsigned int)AfdStandardAddressLength )
      PoolPriority = (void *)AfdAllocatePoolPriority(64, v12, 1382311489, 0);
    else
      PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v10, v12);
    *(_QWORD *)(v11 + 152) = PoolPriority;
    if ( PoolPriority )
      goto LABEL_22;
LABEL_53:
    v32 = *(_DWORD *)(v11 + 4);
    if ( (v32 & 0x40000) != 0 )
    {
      *(_DWORD *)(v11 + 4) = v32 & 0xFFFBFFFF;
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 176));
    }
    v33 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v11 + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v34 = v33 <= 1;
    v35 = v33 - 1;
    if ( v34 )
    {
      if ( v35 )
        __fastfail(0xEu);
      AfdCloseConnection(v11);
    }
    goto LABEL_64;
  }
  if ( *v14 < (unsigned int)v12 )
  {
    if ( *v14 > (unsigned int)AfdStandardAddressLength )
      ExFreePoolWithTag(*(PVOID *)(v11 + 152), 0x52646641u);
    else
      PplFreeToLookasideList((__int64)PplAddressPool, *(void **)(v11 + 152));
    *(_QWORD *)(v11 + 152) = 0;
    *v14 = 0;
    goto LABEL_17;
  }
  v15 = (int)v12;
LABEL_22:
  v16 = v15;
  *v14 = v12;
  v17 = v38;
  memmove(PoolPriority, *(const void **)(v38 + 24), v16);
  ZeroedFromLookasideList = *(void **)(v11 + 224);
  v20 = (_DWORD *)(v11 + 168);
  if ( !ZeroedFromLookasideList )
  {
LABEL_28:
    v21 = v8;
    if ( (unsigned int)v8 > (unsigned int)AfdStandardAddressLength )
      ZeroedFromLookasideList = (void *)AfdAllocatePoolPriority(64, v8, 1382311489, 0);
    else
      ZeroedFromLookasideList = (void *)AfdAllocateZeroedFromLookasideList(v18, v8);
    *(_QWORD *)(v11 + 224) = ZeroedFromLookasideList;
    if ( ZeroedFromLookasideList )
      goto LABEL_33;
    goto LABEL_53;
  }
  if ( *v20 < (unsigned int)v8 )
  {
    if ( *v20 > (unsigned int)AfdStandardAddressLength )
      ExFreePoolWithTag(*(PVOID *)(v11 + 224), 0x52646641u);
    else
      PplFreeToLookasideList((__int64)PplAddressPool, *(void **)(v11 + 224));
    *(_QWORD *)(v11 + 224) = 0;
    *v20 = 0;
    goto LABEL_28;
  }
  v21 = (int)v8;
LABEL_33:
  *v20 = v8;
  memmove(ZeroedFromLookasideList, *(const void **)(v17 + 16), v21);
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 64)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(v11 + 8) = a1;
  AfdAddConnectedReference(v11);
  *(_WORD *)(v11 + 2) = 1;
  *(_OWORD *)(v11 + 56) = *(_OWORD *)v17;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  v22 = (_QWORD **)(a1 + 128);
  while ( 1 )
  {
    v23 = *v22;
    if ( *v22 == v22 )
      break;
    if ( (_QWORD **)v23[1] != v22 )
      goto LABEL_49;
    v24 = (_QWORD *)*v23;
    if ( *(_QWORD **)(*v23 + 8LL) != v23 )
      goto LABEL_49;
    *v22 = v24;
    v25 = v23 - 21;
    v24[1] = v22;
    *v23 = 0;
    v26 = *(_BYTE *)(v23[2] + 1LL);
    if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_q(1032, 34, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, v25);
    if ( (int)AfdServiceWaitForListen((PIRP)v25, v11, &LockHandle, 1) >= 0 )
    {
      result = 1;
      if ( v26 != 32 )
        result = 3;
      goto LABEL_65;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( !_InterlockedExchange64(v25 + 13, 0) )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    AFDETW_TRACEWAITLISTEN(1, 6222, a1, *((unsigned int *)v25 + 12));
    IofCompleteRequest((PIRP)v25, AfdPriorityBoost);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  }
  v28 = *(_QWORD **)(a1 + 104);
  if ( *v28 != a1 + 96 )
LABEL_49:
    __fastfail(3u);
  *(_QWORD *)(v11 + 176) = a1 + 96;
  *(_QWORD *)(v11 + 184) = v28;
  *v28 = v11 + 176;
  *(_QWORD *)(a1 + 104) = v11 + 176;
  AfdIndicateEventSelectEvent(a1, 128, 0);
  AfdNotifySockEventsChangedUnderLock(a1, 128, 0);
  v30 = AfdIndicatePollEvent(v29, 128, 0, &LockHandle);
  p_LockHandle = &LockHandle;
  if ( v30 )
    p_LockHandle = 0;
  AfdNotifySockIndicateEventsUnlock(a1, p_LockHandle, 0);
  result = 3;
LABEL_65:
  *(_DWORD *)(v38 + 32) = result;
  if ( v4 )
    return AfdDereferenceEndpoint(a1);
  return result;
}

```

## disassembly

```asm
0x14004d5b0  mov     [rsp-38h+arg_10], rbx
0x14004d5b5  mov     [rsp-38h+arg_8], rdx
0x14004d5ba  push    rbp
0x14004d5bb  push    rsi
0x14004d5bc  push    rdi
0x14004d5bd  push    r12
0x14004d5bf  push    r13
0x14004d5c1  push    r14
0x14004d5c3  push    r15
0x14004d5c5  mov     rbp, rsp
0x14004d5c8  sub     rsp, 40h
0x14004d5cc  xorps   xmm0, xmm0
0x14004d5cf  xor     eax, eax
0x14004d5d1  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004d5d5  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14004d5d9  mov     r13, rdx
0x14004d5dc  mov     rdi, rcx
0x14004d5df  lea     esi, [rax+1]
0x14004d5e2  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d5e9  jz      short loc_14004D602
0x14004d5eb  lea     edx, [rax+1Fh]
0x14004d5ee  mov     ecx, 408h
0x14004d5f3  mov     r9, rdi
0x14004d5f6  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d5fd  call    WPP_SF_q
0x14004d602  prefetchw byte ptr [rdi+40h]
0x14004d606  mov     rax, [rdi+40h]
0x14004d60a  lea     rcx, [rax+1]
0x14004d60e  cmp     rcx, rsi
0x14004d611  jbe     loc_14004DA18
0x14004d617  lock cmpxchg [rdi+40h], rcx
0x14004d61d  jnz     short loc_14004D60A
0x14004d61f  cmp     byte ptr [rdi+2], 6
0x14004d623  jz      loc_14004D9F4
0x14004d629  mov     eax, [rdi+8]
0x14004d62c  bt      eax, 0Bh
0x14004d630  jb      loc_14004D9F4
0x14004d636  mov     rcx, [r13+18h]
0x14004d63a  movzx   ecx, word ptr [rcx]; af
0x14004d63d  call    SOCKADDR_SIZE
0x14004d642  mov     rcx, [r13+10h]
0x14004d646  movzx   r14d, al
0x14004d64a  movzx   ecx, word ptr [rcx]; af
0x14004d64d  call    SOCKADDR_SIZE
0x14004d652  mov     rcx, rdi
0x14004d655  movzx   r12d, al
0x14004d659  lea     r8, [rbp+Irql]
0x14004d65d  xor     edx, edx
0x14004d65f  call    AfdGetFreeConnection
0x14004d664  mov     rbx, rax
0x14004d667  test    rax, rax
0x14004d66a  jz      loc_14004DA24
0x14004d670  mov     r15d, r14d
0x14004d673  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d67a  jz      short loc_14004D695
0x14004d67c  mov     edx, 21h ; '!'
0x14004d681  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d688  mov     ecx, 408h
0x14004d68d  mov     r9, rax
0x14004d690  call    WPP_SF_q
0x14004d695  mov     rax, [rbx+98h]
0x14004d69c  lea     r14, [rbx+0A0h]
0x14004d6a3  test    rax, rax
0x14004d6a6  jz      short loc_14004D6EF
0x14004d6a8  mov     ecx, [r14]
0x14004d6ab  cmp     ecx, r15d
0x14004d6ae  jnb     short loc_14004D705
0x14004d6b0  cmp     ecx, cs:AfdStandardAddressLength
0x14004d6b6  ja      short loc_14004D6C9
0x14004d6b8  mov     rcx, cs:PplAddressPool
0x14004d6bf  mov     rdx, rax
0x14004d6c2  call    PplFreeToLookasideList
0x14004d6c7  jmp     short loc_14004D6DD
0x14004d6c9  mov     edx, 52646641h; Tag
0x14004d6ce  mov     rcx, rax; P
0x14004d6d1  call    cs:__imp_ExFreePoolWithTag
0x14004d6d8  nop     dword ptr [rax+rax+00h]
0x14004d6dd  mov     qword ptr [rbx+98h], 0
0x14004d6e8  mov     dword ptr [r14], 0
0x14004d6ef  cmp     r15d, cs:AfdStandardAddressLength
0x14004d6f6  mov     r13, r15
0x14004d6f9  mov     rdx, r15
0x14004d6fc  ja      short loc_14004D70A
0x14004d6fe  call    AfdAllocateZeroedFromLookasideList
0x14004d703  jmp     short loc_14004D71C
0x14004d705  movsxd  r13, r15d
0x14004d708  jmp     short loc_14004D72C
0x14004d70a  xor     r9d, r9d
0x14004d70d  mov     r8d, 52646641h
0x14004d713  lea     ecx, [r9+40h]
0x14004d717  call    AfdAllocatePoolPriority
0x14004d71c  mov     [rbx+98h], rax
0x14004d723  test    rax, rax
0x14004d726  jz      loc_14004D9B6
0x14004d72c  mov     r8, r13; Size
0x14004d72f  mov     [r14], r15d
0x14004d732  mov     r13, [rbp+arg_8]
0x14004d736  mov     rcx, rax; void *
0x14004d739  mov     rdx, [r13+18h]; Src
0x14004d73d  call    memmove
0x14004d742  mov     rax, [rbx+0E0h]
0x14004d749  lea     r14, [rbx+0A8h]
0x14004d750  test    rax, rax
0x14004d753  jz      short loc_14004D79C
0x14004d755  mov     ecx, [r14]
0x14004d758  cmp     ecx, r12d
0x14004d75b  jnb     short loc_14004D7B2
0x14004d75d  cmp     ecx, cs:AfdStandardAddressLength
0x14004d763  ja      short loc_14004D776
0x14004d765  mov     rcx, cs:PplAddressPool
0x14004d76c  mov     rdx, rax
0x14004d76f  call    PplFreeToLookasideList
0x14004d774  jmp     short loc_14004D78A
0x14004d776  mov     edx, 52646641h; Tag
0x14004d77b  mov     rcx, rax; P
0x14004d77e  call    cs:__imp_ExFreePoolWithTag
0x14004d785  nop     dword ptr [rax+rax+00h]
0x14004d78a  mov     qword ptr [rbx+0E0h], 0
0x14004d795  mov     dword ptr [r14], 0
0x14004d79c  cmp     r12d, cs:AfdStandardAddressLength
0x14004d7a3  mov     r15, r12
0x14004d7a6  mov     rdx, r12
0x14004d7a9  ja      short loc_14004D7B7
0x14004d7ab  call    AfdAllocateZeroedFromLookasideList
0x14004d7b0  jmp     short loc_14004D7C9
0x14004d7b2  movsxd  r15, r12d
0x14004d7b5  jmp     short loc_14004D7D9
0x14004d7b7  xor     r9d, r9d
0x14004d7ba  mov     r8d, 52646641h
0x14004d7c0  lea     ecx, [r9+40h]
0x14004d7c4  call    AfdAllocatePoolPriority
0x14004d7c9  mov     [rbx+0E0h], rax
0x14004d7d0  test    rax, rax
0x14004d7d3  jz      loc_14004D9B6
0x14004d7d9  mov     [r14], r12d
0x14004d7dc  mov     r8, r15; Size
0x14004d7df  mov     rdx, [r13+10h]; Src
0x14004d7e3  mov     rcx, rax; void *
0x14004d7e6  call    memmove
0x14004d7eb  mov     rax, rsi
0x14004d7ee  lock xadd [rdi+40h], rax
0x14004d7f4  add     rax, rsi
0x14004d7f7  cmp     rax, rsi
0x14004d7fa  jg      short loc_14004D803
0x14004d7fc  mov     ecx, 0Eh
0x14004d801  int     29h; Win8: RtlFailFast(ecx)
0x14004d803  mov     rcx, rbx
0x14004d806  mov     [rbx+8], rdi
0x14004d80a  call    AfdAddConnectedReference
0x14004d80f  mov     [rbx+2], si
0x14004d813  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004d817  movups  xmm0, xmmword ptr [r13+0]
0x14004d81c  lea     rcx, [rdi+38h]; SpinLock
0x14004d820  movdqu  xmmword ptr [rbx+38h], xmm0
0x14004d825  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004d82c  nop     dword ptr [rax+rax+00h]
0x14004d831  lea     r15, [rdi+80h]
0x14004d838  mov     rax, [r15]
0x14004d83b  cmp     rax, r15
0x14004d83e  jz      loc_14004D944
0x14004d844  cmp     [rax+8], r15
0x14004d848  jnz     loc_14004D951
0x14004d84e  mov     rcx, [rax]
0x14004d851  cmp     [rcx+8], rax
0x14004d855  jnz     loc_14004D951
0x14004d85b  mov     [r15], rcx
0x14004d85e  lea     r14, [rax-0A8h]
0x14004d865  mov     [rcx+8], r15
0x14004d869  mov     qword ptr [rax], 0
0x14004d870  mov     rax, [r14+0B8h]
0x14004d877  mov     r12b, [rax+1]
0x14004d87b  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d882  jz      short loc_14004D89D
0x14004d884  mov     edx, 22h ; '"'
0x14004d889  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d890  mov     ecx, 408h
0x14004d895  mov     r9, r14
0x14004d898  call    WPP_SF_q
0x14004d89d  mov     r9b, sil
0x14004d8a0  lea     r8, [rbp+LockHandle]
0x14004d8a4  mov     rdx, rbx
0x14004d8a7  mov     rcx, r14; Irp
0x14004d8aa  call    AfdServiceWaitForListen
0x14004d8af  test    eax, eax
0x14004d8b1  jns     short loc_14004D931
0x14004d8b3  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004d8b7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004d8be  nop     dword ptr [rax+rax+00h]
0x14004d8c3  xor     eax, eax
0x14004d8c5  xchg    rax, [r14+68h]
0x14004d8c9  test    rax, rax
0x14004d8cc  jnz     short loc_14004D8F0
0x14004d8ce  lea     rcx, [rbp+Irql]; Irql
0x14004d8d2  mov     byte ptr [rbp+Irql], al
0x14004d8d5  call    cs:__imp_IoAcquireCancelSpinLock
0x14004d8dc  nop     dword ptr [rax+rax+00h]
0x14004d8e1  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004d8e4  call    cs:__imp_IoReleaseCancelSpinLock
0x14004d8eb  nop     dword ptr [rax+rax+00h]
0x14004d8f0  mov     r9d, [r14+30h]
0x14004d8f4  mov     r8, rdi
0x14004d8f7  mov     edx, 184Eh
0x14004d8fc  mov     ecx, esi
0x14004d8fe  call    AFDETW_TRACEWAITLISTEN
0x14004d903  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004d909  mov     rcx, r14; Irp
0x14004d90c  call    cs:__imp_IofCompleteRequest
0x14004d913  nop     dword ptr [rax+rax+00h]
0x14004d918  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004d91c  lea     rcx, [rdi+38h]; SpinLock
0x14004d920  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004d927  nop     dword ptr [rax+rax+00h]
0x14004d92c  jmp     loc_14004D838
0x14004d931  cmp     r12b, 20h ; ' '
0x14004d935  mov     eax, esi
0x14004d937  mov     ecx, 3
0x14004d93c  cmovnz  eax, ecx
0x14004d93f  jmp     loc_14004DA29
0x14004d944  lea     rcx, [rdi+60h]
0x14004d948  mov     rdx, [rcx+8]
0x14004d94c  cmp     [rdx], rcx
0x14004d94f  jz      short loc_14004D958
0x14004d951  mov     ecx, 3
0x14004d956  int     29h; Win8: RtlFailFast(ecx)
0x14004d958  lea     rax, [rbx+0B0h]
0x14004d95f  xor     r8d, r8d
0x14004d962  mov     [rax], rcx
0x14004d965  mov     ebx, 80h
0x14004d96a  mov     [rax+8], rdx
0x14004d96e  mov     [rdx], rax
0x14004d971  mov     edx, ebx
0x14004d973  mov     [rcx+8], rax
0x14004d977  mov     rcx, rdi
0x14004d97a  call    AfdIndicateEventSelectEvent
0x14004d97f  xor     r8d, r8d
0x14004d982  mov     edx, ebx
0x14004d984  mov     rcx, rdi
0x14004d987  call    AfdNotifySockEventsChangedUnderLock
0x14004d98c  xor     r8d, r8d
0x14004d98f  lea     r9, [rbp+LockHandle]
0x14004d993  mov     edx, ebx
0x14004d995  call    AfdIndicatePollEvent
0x14004d99a  xor     ecx, ecx
0x14004d99c  lea     rdx, [rbp+LockHandle]
0x14004d9a0  test    al, al
0x14004d9a2  cmovnz  rdx, rcx
0x14004d9a6  xor     r8d, r8d
0x14004d9a9  mov     rcx, rdi
0x14004d9ac  call    AfdNotifySockIndicateEventsUnlock
0x14004d9b1  lea     eax, [rbx-7Dh]
0x14004d9b4  jmp     short loc_14004DA29
0x14004d9b6  mov     eax, [rbx+4]
0x14004d9b9  bt      eax, 12h
0x14004d9bd  jnb     short loc_14004D9CD
0x14004d9bf  btr     eax, 12h
0x14004d9c3  mov     [rbx+4], eax
0x14004d9c6  lock dec dword ptr [rdi+0B0h]
0x14004d9cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004d9d1  lock xadd [rbx+30h], rax
0x14004d9d7  sub     rax, rsi
0x14004d9da  jg      short loc_14004DA24
0x14004d9dc  test    rax, rax
0x14004d9df  jnz     short loc_14004D9EB
0x14004d9e1  mov     rcx, rbx
0x14004d9e4  call    AfdCloseConnection
0x14004d9e9  jmp     short loc_14004DA24
0x14004d9eb  mov     ecx, 0Eh
0x14004d9f0  int     29h; Win8: RtlFailFast(ecx)
0x14004d9f2  jmp     short loc_14004DA24
0x14004d9f4  test    byte ptr cs:xmmword_1400875D0+9, sil
0x14004d9fb  jz      short loc_14004DA24
0x14004d9fd  mov     edx, 20h ; ' '
0x14004da02  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004da09  mov     ecx, 308h
0x14004da0e  mov     r9, rdi
0x14004da11  call    WPP_SF_q
0x14004da16  jmp     short loc_14004DA24
0x14004da18  jz      short loc_14004DA21
0x14004da1a  mov     ecx, 0Eh
0x14004da1f  int     29h; Win8: RtlFailFast(ecx)
0x14004da21  xor     sil, sil
0x14004da24  mov     eax, 2
0x14004da29  mov     rcx, [rbp+arg_8]
0x14004da2d  mov     [rcx+20h], eax
0x14004da30  test    sil, sil
0x14004da33  jz      short loc_14004DA3D
0x14004da35  mov     rcx, rdi
0x14004da38  call    AfdDereferenceEndpoint
0x14004da3d  mov     rbx, [rsp+40h+arg_10]
0x14004da45  add     rsp, 40h
0x14004da49  pop     r15
0x14004da4b  pop     r14
0x14004da4d  pop     r13
0x14004da4f  pop     r12
0x14004da51  pop     rdi
0x14004da52  pop     rsi
0x14004da53  pop     rbp
0x14004da54  retn
```
