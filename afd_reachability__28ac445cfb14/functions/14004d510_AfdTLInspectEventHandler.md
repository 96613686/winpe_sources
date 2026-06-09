# AfdTLInspectEventHandler

- ea: `0x14004d510`
- end: `0x14004d9b6`
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
- `0x140036dac`
- `0x14004d510`
- `0x140072800`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004d844`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004d844`
- `ntoskrnl!IofCompleteRequest` at `0x14004d86c`
- `ntoskrnl!IofCompleteRequest` at `0x14004d86c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004d835`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004d835`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d817`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004d817`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d785`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d880`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d785`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004d880`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d631`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d6de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d631`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d6de`

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
0x14004d510  mov     [rsp-38h+arg_10], rbx
0x14004d515  mov     [rsp-38h+arg_8], rdx
0x14004d51a  push    rbp
0x14004d51b  push    rsi
0x14004d51c  push    rdi
0x14004d51d  push    r12
0x14004d51f  push    r13
0x14004d521  push    r14
0x14004d523  push    r15
0x14004d525  mov     rbp, rsp
0x14004d528  sub     rsp, 40h
0x14004d52c  xorps   xmm0, xmm0
0x14004d52f  xor     eax, eax
0x14004d531  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14004d535  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14004d539  mov     r13, rdx
0x14004d53c  mov     rdi, rcx
0x14004d53f  lea     esi, [rax+1]
0x14004d542  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d549  jz      short loc_14004D562
0x14004d54b  lea     edx, [rax+1Fh]
0x14004d54e  mov     ecx, 408h
0x14004d553  mov     r9, rdi
0x14004d556  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d55d  call    WPP_SF_q
0x14004d562  prefetchw byte ptr [rdi+40h]
0x14004d566  mov     rax, [rdi+40h]
0x14004d56a  lea     rcx, [rax+1]
0x14004d56e  cmp     rcx, rsi
0x14004d571  jbe     loc_14004D978
0x14004d577  lock cmpxchg [rdi+40h], rcx
0x14004d57d  jnz     short loc_14004D56A
0x14004d57f  cmp     byte ptr [rdi+2], 6
0x14004d583  jz      loc_14004D954
0x14004d589  mov     eax, [rdi+8]
0x14004d58c  bt      eax, 0Bh
0x14004d590  jb      loc_14004D954
0x14004d596  mov     rcx, [r13+18h]
0x14004d59a  movzx   ecx, word ptr [rcx]; af
0x14004d59d  call    SOCKADDR_SIZE
0x14004d5a2  mov     rcx, [r13+10h]
0x14004d5a6  movzx   r14d, al
0x14004d5aa  movzx   ecx, word ptr [rcx]; af
0x14004d5ad  call    SOCKADDR_SIZE
0x14004d5b2  mov     rcx, rdi
0x14004d5b5  movzx   r12d, al
0x14004d5b9  lea     r8, [rbp+Irql]
0x14004d5bd  xor     edx, edx
0x14004d5bf  call    AfdGetFreeConnection
0x14004d5c4  mov     rbx, rax
0x14004d5c7  test    rax, rax
0x14004d5ca  jz      loc_14004D984
0x14004d5d0  mov     r15d, r14d
0x14004d5d3  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d5da  jz      short loc_14004D5F5
0x14004d5dc  mov     edx, 21h ; '!'
0x14004d5e1  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d5e8  mov     ecx, 408h
0x14004d5ed  mov     r9, rax
0x14004d5f0  call    WPP_SF_q
0x14004d5f5  mov     rax, [rbx+98h]
0x14004d5fc  lea     r14, [rbx+0A0h]
0x14004d603  test    rax, rax
0x14004d606  jz      short loc_14004D64F
0x14004d608  mov     ecx, [r14]
0x14004d60b  cmp     ecx, r15d
0x14004d60e  jnb     short loc_14004D665
0x14004d610  cmp     ecx, cs:AfdStandardAddressLength
0x14004d616  ja      short loc_14004D629
0x14004d618  mov     rcx, cs:PplAddressPool
0x14004d61f  mov     rdx, rax
0x14004d622  call    PplFreeToLookasideList
0x14004d627  jmp     short loc_14004D63D
0x14004d629  mov     edx, 52646641h; Tag
0x14004d62e  mov     rcx, rax; P
0x14004d631  call    cs:__imp_ExFreePoolWithTag
0x14004d638  nop     dword ptr [rax+rax+00h]
0x14004d63d  mov     qword ptr [rbx+98h], 0
0x14004d648  mov     dword ptr [r14], 0
0x14004d64f  cmp     r15d, cs:AfdStandardAddressLength
0x14004d656  mov     r13, r15
0x14004d659  mov     rdx, r15
0x14004d65c  ja      short loc_14004D66A
0x14004d65e  call    AfdAllocateZeroedFromLookasideList
0x14004d663  jmp     short loc_14004D67C
0x14004d665  movsxd  r13, r15d
0x14004d668  jmp     short loc_14004D68C
0x14004d66a  xor     r9d, r9d
0x14004d66d  mov     r8d, 52646641h
0x14004d673  lea     ecx, [r9+40h]
0x14004d677  call    AfdAllocatePoolPriority
0x14004d67c  mov     [rbx+98h], rax
0x14004d683  test    rax, rax
0x14004d686  jz      loc_14004D916
0x14004d68c  mov     r8, r13; Size
0x14004d68f  mov     [r14], r15d
0x14004d692  mov     r13, [rbp+arg_8]
0x14004d696  mov     rcx, rax; void *
0x14004d699  mov     rdx, [r13+18h]; Src
0x14004d69d  call    memmove
0x14004d6a2  mov     rax, [rbx+0E0h]
0x14004d6a9  lea     r14, [rbx+0A8h]
0x14004d6b0  test    rax, rax
0x14004d6b3  jz      short loc_14004D6FC
0x14004d6b5  mov     ecx, [r14]
0x14004d6b8  cmp     ecx, r12d
0x14004d6bb  jnb     short loc_14004D712
0x14004d6bd  cmp     ecx, cs:AfdStandardAddressLength
0x14004d6c3  ja      short loc_14004D6D6
0x14004d6c5  mov     rcx, cs:PplAddressPool
0x14004d6cc  mov     rdx, rax
0x14004d6cf  call    PplFreeToLookasideList
0x14004d6d4  jmp     short loc_14004D6EA
0x14004d6d6  mov     edx, 52646641h; Tag
0x14004d6db  mov     rcx, rax; P
0x14004d6de  call    cs:__imp_ExFreePoolWithTag
0x14004d6e5  nop     dword ptr [rax+rax+00h]
0x14004d6ea  mov     qword ptr [rbx+0E0h], 0
0x14004d6f5  mov     dword ptr [r14], 0
0x14004d6fc  cmp     r12d, cs:AfdStandardAddressLength
0x14004d703  mov     r15, r12
0x14004d706  mov     rdx, r12
0x14004d709  ja      short loc_14004D717
0x14004d70b  call    AfdAllocateZeroedFromLookasideList
0x14004d710  jmp     short loc_14004D729
0x14004d712  movsxd  r15, r12d
0x14004d715  jmp     short loc_14004D739
0x14004d717  xor     r9d, r9d
0x14004d71a  mov     r8d, 52646641h
0x14004d720  lea     ecx, [r9+40h]
0x14004d724  call    AfdAllocatePoolPriority
0x14004d729  mov     [rbx+0E0h], rax
0x14004d730  test    rax, rax
0x14004d733  jz      loc_14004D916
0x14004d739  mov     [r14], r12d
0x14004d73c  mov     r8, r15; Size
0x14004d73f  mov     rdx, [r13+10h]; Src
0x14004d743  mov     rcx, rax; void *
0x14004d746  call    memmove
0x14004d74b  mov     rax, rsi
0x14004d74e  lock xadd [rdi+40h], rax
0x14004d754  add     rax, rsi
0x14004d757  cmp     rax, rsi
0x14004d75a  jg      short loc_14004D763
0x14004d75c  mov     ecx, 0Eh
0x14004d761  int     29h; Win8: RtlFailFast(ecx)
0x14004d763  mov     rcx, rbx
0x14004d766  mov     [rbx+8], rdi
0x14004d76a  call    AfdAddConnectedReference
0x14004d76f  mov     [rbx+2], si
0x14004d773  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004d777  movups  xmm0, xmmword ptr [r13+0]
0x14004d77c  lea     rcx, [rdi+38h]; SpinLock
0x14004d780  movdqu  xmmword ptr [rbx+38h], xmm0
0x14004d785  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004d78c  nop     dword ptr [rax+rax+00h]
0x14004d791  lea     r15, [rdi+80h]
0x14004d798  mov     rax, [r15]
0x14004d79b  cmp     rax, r15
0x14004d79e  jz      loc_14004D8A4
0x14004d7a4  cmp     [rax+8], r15
0x14004d7a8  jnz     loc_14004D8B1
0x14004d7ae  mov     rcx, [rax]
0x14004d7b1  cmp     [rcx+8], rax
0x14004d7b5  jnz     loc_14004D8B1
0x14004d7bb  mov     [r15], rcx
0x14004d7be  lea     r14, [rax-0A8h]
0x14004d7c5  mov     [rcx+8], r15
0x14004d7c9  mov     qword ptr [rax], 0
0x14004d7d0  mov     rax, [r14+0B8h]
0x14004d7d7  mov     r12b, [rax+1]
0x14004d7db  test    byte ptr cs:xmmword_1400875E0+1, sil
0x14004d7e2  jz      short loc_14004D7FD
0x14004d7e4  mov     edx, 22h ; '"'
0x14004d7e9  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d7f0  mov     ecx, 408h
0x14004d7f5  mov     r9, r14
0x14004d7f8  call    WPP_SF_q
0x14004d7fd  mov     r9b, sil
0x14004d800  lea     r8, [rbp+LockHandle]
0x14004d804  mov     rdx, rbx
0x14004d807  mov     rcx, r14; Irp
0x14004d80a  call    AfdServiceWaitForListen
0x14004d80f  test    eax, eax
0x14004d811  jns     short loc_14004D891
0x14004d813  lea     rcx, [rbp+LockHandle]; LockHandle
0x14004d817  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004d81e  nop     dword ptr [rax+rax+00h]
0x14004d823  xor     eax, eax
0x14004d825  xchg    rax, [r14+68h]
0x14004d829  test    rax, rax
0x14004d82c  jnz     short loc_14004D850
0x14004d82e  lea     rcx, [rbp+Irql]; Irql
0x14004d832  mov     byte ptr [rbp+Irql], al
0x14004d835  call    cs:__imp_IoAcquireCancelSpinLock
0x14004d83c  nop     dword ptr [rax+rax+00h]
0x14004d841  mov     cl, byte ptr [rbp+Irql]; Irql
0x14004d844  call    cs:__imp_IoReleaseCancelSpinLock
0x14004d84b  nop     dword ptr [rax+rax+00h]
0x14004d850  mov     r9d, [r14+30h]
0x14004d854  mov     r8, rdi
0x14004d857  mov     edx, 184Eh
0x14004d85c  mov     ecx, esi
0x14004d85e  call    AFDETW_TRACEWAITLISTEN
0x14004d863  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004d869  mov     rcx, r14; Irp
0x14004d86c  call    cs:__imp_IofCompleteRequest
0x14004d873  nop     dword ptr [rax+rax+00h]
0x14004d878  lea     rdx, [rbp+LockHandle]; LockHandle
0x14004d87c  lea     rcx, [rdi+38h]; SpinLock
0x14004d880  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004d887  nop     dword ptr [rax+rax+00h]
0x14004d88c  jmp     loc_14004D798
0x14004d891  cmp     r12b, 20h ; ' '
0x14004d895  mov     eax, esi
0x14004d897  mov     ecx, 3
0x14004d89c  cmovnz  eax, ecx
0x14004d89f  jmp     loc_14004D989
0x14004d8a4  lea     rcx, [rdi+60h]
0x14004d8a8  mov     rdx, [rcx+8]
0x14004d8ac  cmp     [rdx], rcx
0x14004d8af  jz      short loc_14004D8B8
0x14004d8b1  mov     ecx, 3
0x14004d8b6  int     29h; Win8: RtlFailFast(ecx)
0x14004d8b8  lea     rax, [rbx+0B0h]
0x14004d8bf  xor     r8d, r8d
0x14004d8c2  mov     [rax], rcx
0x14004d8c5  mov     ebx, 80h
0x14004d8ca  mov     [rax+8], rdx
0x14004d8ce  mov     [rdx], rax
0x14004d8d1  mov     edx, ebx
0x14004d8d3  mov     [rcx+8], rax
0x14004d8d7  mov     rcx, rdi
0x14004d8da  call    AfdIndicateEventSelectEvent
0x14004d8df  xor     r8d, r8d
0x14004d8e2  mov     edx, ebx
0x14004d8e4  mov     rcx, rdi
0x14004d8e7  call    AfdNotifySockEventsChangedUnderLock
0x14004d8ec  xor     r8d, r8d
0x14004d8ef  lea     r9, [rbp+LockHandle]
0x14004d8f3  mov     edx, ebx
0x14004d8f5  call    AfdIndicatePollEvent
0x14004d8fa  xor     ecx, ecx
0x14004d8fc  lea     rdx, [rbp+LockHandle]
0x14004d900  test    al, al
0x14004d902  cmovnz  rdx, rcx
0x14004d906  xor     r8d, r8d
0x14004d909  mov     rcx, rdi
0x14004d90c  call    AfdNotifySockIndicateEventsUnlock
0x14004d911  lea     eax, [rbx-7Dh]
0x14004d914  jmp     short loc_14004D989
0x14004d916  mov     eax, [rbx+4]
0x14004d919  bt      eax, 12h
0x14004d91d  jnb     short loc_14004D92D
0x14004d91f  btr     eax, 12h
0x14004d923  mov     [rbx+4], eax
0x14004d926  lock dec dword ptr [rdi+0B0h]
0x14004d92d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004d931  lock xadd [rbx+30h], rax
0x14004d937  sub     rax, rsi
0x14004d93a  jg      short loc_14004D984
0x14004d93c  test    rax, rax
0x14004d93f  jnz     short loc_14004D94B
0x14004d941  mov     rcx, rbx
0x14004d944  call    AfdCloseConnection
0x14004d949  jmp     short loc_14004D984
0x14004d94b  mov     ecx, 0Eh
0x14004d950  int     29h; Win8: RtlFailFast(ecx)
0x14004d952  jmp     short loc_14004D984
0x14004d954  test    byte ptr cs:xmmword_1400875D0+9, sil
0x14004d95b  jz      short loc_14004D984
0x14004d95d  mov     edx, 20h ; ' '
0x14004d962  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004d969  mov     ecx, 308h
0x14004d96e  mov     r9, rdi
0x14004d971  call    WPP_SF_q
0x14004d976  jmp     short loc_14004D984
0x14004d978  jz      short loc_14004D981
0x14004d97a  mov     ecx, 0Eh
0x14004d97f  int     29h; Win8: RtlFailFast(ecx)
0x14004d981  xor     sil, sil
0x14004d984  mov     eax, 2
0x14004d989  mov     rcx, [rbp+arg_8]
0x14004d98d  mov     [rcx+20h], eax
0x14004d990  test    sil, sil
0x14004d993  jz      short loc_14004D99D
0x14004d995  mov     rcx, rdi
0x14004d998  call    AfdDereferenceEndpoint
0x14004d99d  mov     rbx, [rsp+40h+arg_10]
0x14004d9a5  add     rsp, 40h
0x14004d9a9  pop     r15
0x14004d9ab  pop     r14
0x14004d9ad  pop     r13
0x14004d9af  pop     r12
0x14004d9b1  pop     rdi
0x14004d9b2  pop     rsi
0x14004d9b3  pop     rbp
0x14004d9b4  retn
```
