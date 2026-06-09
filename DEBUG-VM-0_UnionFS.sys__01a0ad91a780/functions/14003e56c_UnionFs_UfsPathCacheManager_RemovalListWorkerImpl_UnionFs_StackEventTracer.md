# UnionFs::UfsPathCacheManager::RemovalListWorkerImpl(UnionFs::StackEventTracer &)

- ea: `0x14003e56c`
- end: `0x14003ea75`
- name: `?RemovalListWorkerImpl@UfsPathCacheManager@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z`
- size: `1289`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003e500`

## callees

- `0x14000f81c`
- `0x14000ffd4`
- `0x14002b278`
- `0x14003b848`
- `0x14003c70c`
- `0x14003de40`
- `0x14003e1ac`
- `0x14003e56c`
- `0x140056974`
- `0x140056c44`
- `0x140056c7c`
- `0x140079c90`
- `0x140079cc4`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003e9a6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003e9a6`
- `ntoskrnl!KeClearEvent` at `0x14003e9d3`
- `ntoskrnl!KeClearEvent` at `0x14003e9d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e9e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ea45`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e9e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ea45`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003e77c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003e77c`
- `ntoskrnl!KeSetEvent` at `0x14003ea2b`
- `ntoskrnl!KeSetEvent` at `0x14003ea2b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e611`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e94e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e611`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e94e`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003ea13`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003ea13`

## string_xrefs

- `0x14003e6ce`: `Could not DeleteEntry for item removal`
- `0x14003e6eb`: `UnionFs::UfsPathCacheManager::RemovalListWorkerImpl`
- `0x14003e8fa`: `UnionFs::UfsPathCacheManager::RemovalListWorkerImpl`
- `0x14003e8e9`: `ORIGIN: Inserting into CachesOverThreshold`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCacheManager::RemovalListWorkerImpl(
        PKSPIN_LOCK SpinLock,
        struct UnionFs::StackEventTracer *a2)
{
  bool v3; // zf
  _QWORD *v5; // rdx
  void *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  signed __int32 v9; // edx
  signed __int32 v10; // eax
  utl::_RefCountBase *v11; // rdi
  int v12; // eax
  unsigned int v13; // r14d
  _QWORD *v14; // rbx
  char v15; // r13
  const struct std::nothrow_t *v16; // rdx
  char *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  unsigned __int64 v20; // r12
  PKSPIN_LOCK v21; // r14
  unsigned __int64 *v22; // rax
  unsigned __int64 *v23; // rbx
  struct _KSPIN_LOCK_QUEUE *v24; // rcx
  struct _KSPIN_LOCK_QUEUE *v25; // r8
  char v26; // r14
  unsigned __int64 *v27; // rax
  struct _FAST_MUTEX *v28; // rcx
  char *v30; // [rsp+28h] [rbp-48h]
  char *v31; // [rsp+30h] [rbp-40h]
  PVOID Entry; // [rsp+38h] [rbp-38h] BYREF
  PVOID *p_Entry; // [rsp+40h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-28h] BYREF
  PKSPIN_LOCK v35; // [rsp+60h] [rbp-10h] BYREF
  char v36; // [rsp+68h] [rbp-8h]
  PFAST_MUTEX FastMutex; // [rsp+B0h] [rbp+40h] BYREF
  PFAST_MUTEX v38; // [rsp+C0h] [rbp+50h] BYREF
  FsFltWil::Details *v39; // [rsp+C8h] [rbp+58h] BYREF

  v35 = SpinLock;
  ++*((_DWORD *)SpinLock + 66);
  v3 = *((_DWORD *)SpinLock + 54) == 0;
  v36 = 1;
  if ( !v3 )
  {
    p_Entry = &Entry;
    Entry = &Entry;
    FsFltWil::AcquireFastMutex(&FastMutex, SpinLock + 20);
    v5 = (_QWORD *)SpinLock[18];
    p_Entry = (PVOID *)SpinLock[19];
    SpinLock[19] = (KSPIN_LOCK)(SpinLock + 18);
    SpinLock[18] = (KSPIN_LOCK)(SpinLock + 18);
    Entry = v5;
    *((_DWORD *)SpinLock + 54) = 0;
    v5[1] = &Entry;
    *p_Entry = &Entry;
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    while ( 1 )
    {
      while ( 1 )
      {
        v6 = Entry;
        if ( Entry == &Entry )
          goto LABEL_25;
        if ( *((PVOID **)Entry + 1) != &Entry || (v7 = *(_QWORD *)Entry, *(PVOID *)(*(_QWORD *)Entry + 8LL) != Entry) )
          __fastfail(3u);
        Entry = *(PVOID *)Entry;
        *(_QWORD *)(v7 + 8) = &Entry;
        v8 = *((_QWORD *)v6 + 6);
        FastMutex = (PFAST_MUTEX)v6;
        if ( v8 )
        {
          v9 = *(_DWORD *)(v8 + 8);
          if ( v9 )
            break;
        }
LABEL_23:
        UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem((UnionFs::UfsPathCacheListItem *)v6);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v6);
      }
      while ( 1 )
      {
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        if ( v9 == v10 )
          break;
        v9 = v10;
        if ( !v10 )
          goto LABEL_23;
      }
      v11 = (utl::_RefCountBase *)*((_QWORD *)v6 + 6);
      if ( !*((_QWORD *)v6 + 5) )
      {
        if ( v11 )
          utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)v6 + 6));
        goto LABEL_23;
      }
      v30 = 0;
      v12 = UnionFs::UfsPathCache::DeleteEntry(*((_QWORD *)v6 + 2), *((_QWORD *)v6 + 3), *((_QWORD *)v6 + 4), a2, 0);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -1073741275 )
        {
          *(_DWORD *)a2 = 0;
          *((_WORD *)a2 + 274) = 0;
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("Could not DeleteEntry for item removal");
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)v13,
            (int)a2,
            (struct UnionFs::StackEventTracer *)0x436001101C4LL,
            (unsigned __int64)"UnionFs::UfsPathCacheManager::RemovalListWorkerImpl",
            "PUSH: Deleting entry",
            0);
          UnionFs::StackEventTracer::LogError(a2);
          *(_DWORD *)a2 = 0;
          *((_WORD *)a2 + 274) = 0;
          UnionFs::UfsPathCacheManager::AddToRemovalList(SpinLock, &FastMutex);
          v6 = FastMutex;
        }
      }
      if ( v11 )
        utl::_RefCountBase::_DecStrong(v11);
      if ( v6 )
        goto LABEL_23;
    }
  }
LABEL_25:
  v14 = UnionFs::g_FilterState;
  v15 = 0;
  FsFltWil::AcquirePushLockShared(&v39, (char *)UnionFs::g_FilterState + 64);
  v17 = (char *)(v14 + 4);
  v18 = v14[6];
  v31 = (char *)(v14 + 4);
  while ( (char *)v18 != v17 )
  {
    v19 = *(_QWORD *)(v18 + 40);
    if ( *(_DWORD *)(v19 + 28) == 2 )
      v20 = *(_QWORD *)(*(_QWORD *)(v19 + 32) + 16LL);
    else
      v20 = *((_QWORD *)UnionFs::g_FilterState + 10);
    if ( *(_DWORD *)(v20 + 224) <= *((_DWORD *)SpinLock + 101) )
      goto LABEL_55;
    FsFltWil::AcquireFastMutex(&v38, SpinLock + 39);
    v21 = SpinLock + 35;
    if ( (PKSPIN_LOCK)SpinLock[37] == SpinLock + 35 )
    {
      v22 = (unsigned __int64 *)operator new(0x20u, v16);
      v23 = v22;
      if ( !v22 )
        goto LABEL_49;
      v22[3] = v20;
      *v22 = (unsigned __int64)v21 | 1;
      v22[1] = (unsigned __int64)&utl::_TreeSentinel;
      v22[2] = (unsigned __int64)&utl::_TreeSentinel;
      *v21 = (KSPIN_LOCK)v22;
      SpinLock[36] = (KSPIN_LOCK)v22;
      SpinLock[37] = (KSPIN_LOCK)v22;
      ++SpinLock[38];
    }
    else
    {
      v24 = (struct _KSPIN_LOCK_QUEUE *)*v21;
      v23 = 0;
      do
      {
        if ( (volatile PKSPIN_LOCK)v20 >= v24[1].Lock )
        {
          v23 = (unsigned __int64 *)v24;
          LOBYTE(v16) = 1;
        }
        else
        {
          LOBYTE(v16) = 0;
        }
        v25 = v24;
        v24 = (struct _KSPIN_LOCK_QUEUE *)*((_QWORD *)&v24->Lock + (unsigned __int8)v16);
      }
      while ( v24 != (struct _KSPIN_LOCK_QUEUE *)&utl::_TreeSentinel );
      if ( v23 && v23[3] < v20 )
        v23 = 0;
      LockHandle.LockQueue.Next = v25;
      LOBYTE(LockHandle.LockQueue.Lock) = (_BYTE)v16;
      if ( v23 )
      {
        v26 = 0;
        goto LABEL_47;
      }
      v27 = (unsigned __int64 *)operator new(0x20u, v16);
      v23 = v27;
      if ( !v27 )
      {
LABEL_49:
        v26 = 0;
LABEL_50:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a2,
          (struct UnionFs::StackEventTracer *)0x431001101F0LL,
          (unsigned __int64)"UnionFs::UfsPathCacheManager::RemovalListWorkerImpl",
          "ORIGIN: Inserting into CachesOverThreshold",
          v30);
        UnionFs::StackEventTracer::LogError(a2);
        *(_DWORD *)a2 = 0;
        *((_WORD *)a2 + 274) = 0;
        goto LABEL_51;
      }
      v27[3] = v20;
      utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::_InsertAt(
        SpinLock + 35,
        &LockHandle,
        v27);
    }
    v26 = 1;
LABEL_47:
    if ( !v23 )
      goto LABEL_50;
LABEL_51:
    v28 = v38;
    if ( v26 )
      v15 = 1;
    v38 = 0;
    if ( v28 )
      ExReleaseFastMutex(v28);
LABEL_55:
    LOBYTE(v16) = 1;
    v18 = utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(v18, v16);
    v17 = v31;
  }
  if ( v39 )
    FsFltWil::Details::ReleasePushLockShared(v39, (unsigned __int64 *)v16);
  if ( v15 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
    if ( !*((_BYTE *)SpinLock + 8) || _InterlockedCompareExchange((volatile signed __int32 *)SpinLock + 92, 1, 0) )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    else
    {
      KeClearEvent((PRKEVENT)(SpinLock + 47));
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( FltQueueGenericWorkItem(
             (PFLT_GENERIC_WORKITEM)SpinLock[34],
             *(PVOID *)UnionFs::g_FilterState,
             UnionFs::UfsPathCacheManager::TrimmerWorker,
             DelayedWorkQueue,
             0) < 0 )
      {
        KeSetEvent((PRKEVENT)(SpinLock + 47), 0, 0);
        _InterlockedExchange((volatile __int32 *)SpinLock + 92, 0);
      }
    }
  }
  wil::details::lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___::_lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___(&v35);
  return 0;
}

```

## disassembly

```asm
0x14003e56c  mov     [rsp-38h+arg_8], rbx
0x14003e571  push    rbp
0x14003e572  push    rsi
0x14003e573  push    rdi
0x14003e574  push    r12
0x14003e576  push    r13
0x14003e578  push    r14
0x14003e57a  push    r15
0x14003e57c  mov     rbp, rsp
0x14003e57f  sub     rsp, 70h
0x14003e583  mov     r12d, 1
0x14003e589  mov     [rbp+var_10], rcx
0x14003e58d  add     [rcx+108h], r12d
0x14003e594  mov     r15, rdx
0x14003e597  cmp     dword ptr [rcx+0D8h], 0
0x14003e59e  mov     rsi, rcx
0x14003e5a1  mov     [rbp+var_8], r12b
0x14003e5a5  jbe     loc_14003E794
0x14003e5ab  lea     rax, [rbp+Entry]
0x14003e5af  mov     [rbp+var_30], rax
0x14003e5b3  lea     rdx, [rcx+0A0h]
0x14003e5ba  lea     rax, [rbp+Entry]
0x14003e5be  lea     rcx, [rbp+FastMutex]
0x14003e5c2  mov     [rbp+Entry], rax
0x14003e5c6  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14003e5cb  mov     rax, [rsi+98h]
0x14003e5d2  lea     rcx, [rsi+90h]
0x14003e5d9  mov     rdx, [rcx]
0x14003e5dc  mov     [rbp+var_30], rax
0x14003e5e0  lea     rax, [rbp+Entry]
0x14003e5e4  mov     [rcx+8], rcx
0x14003e5e8  mov     [rcx], rcx
0x14003e5eb  lea     rcx, [rbp+Entry]
0x14003e5ef  mov     [rbp+Entry], rdx
0x14003e5f3  mov     dword ptr [rsi+0D8h], 0
0x14003e5fd  mov     [rdx+8], rax
0x14003e601  mov     rax, [rbp+var_30]
0x14003e605  mov     [rax], rcx
0x14003e608  mov     rcx, [rbp+FastMutex]; FastMutex
0x14003e60c  test    rcx, rcx
0x14003e60f  jz      short loc_14003E61D
0x14003e611  call    cs:__imp_ExReleaseFastMutex
0x14003e618  nop     dword ptr [rax+rax+00h]
0x14003e61d  mov     rbx, [rbp+Entry]
0x14003e621  lea     rax, [rbp+Entry]
0x14003e625  cmp     rbx, rax
0x14003e628  jz      loc_14003E794
0x14003e62e  lea     rax, [rbp+Entry]
0x14003e632  cmp     [rbx+8], rax
0x14003e636  jnz     loc_14003E78D
0x14003e63c  mov     rax, [rbx]
0x14003e63f  cmp     [rax+8], rbx
0x14003e643  jnz     loc_14003E78D
0x14003e649  mov     [rbp+Entry], rax
0x14003e64d  lea     rcx, [rbp+Entry]
0x14003e651  mov     [rax+8], rcx
0x14003e655  mov     r8, [rbx+30h]
0x14003e659  mov     [rbp+FastMutex], rbx
0x14003e65d  test    r8, r8
0x14003e660  jz      loc_14003E763
0x14003e666  mov     edx, [r8+8]
0x14003e66a  test    edx, edx
0x14003e66c  jz      loc_14003E763
0x14003e672  lea     ecx, [rdx+1]
0x14003e675  mov     eax, edx
0x14003e677  lock cmpxchg [r8+8], ecx
0x14003e67d  cmp     edx, eax
0x14003e67f  jz      short loc_14003E68C
0x14003e681  mov     edx, eax
0x14003e683  test    eax, eax
0x14003e685  jnz     short loc_14003E672
0x14003e687  jmp     loc_14003E763
0x14003e68c  cmp     qword ptr [rbx+28h], 0
0x14003e691  mov     rdi, [rbx+30h]
0x14003e695  jz      loc_14003E756
0x14003e69b  mov     r8, [rbx+20h]
0x14003e69f  mov     r9, r15
0x14003e6a2  mov     rdx, [rbx+18h]
0x14003e6a6  mov     rcx, [rbx+10h]
0x14003e6aa  mov     [rsp+70h+var_48], 0; char *
0x14003e6b3  mov     dword ptr [rsp+70h+Context], 0
0x14003e6bb  call    ?DeleteEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEBVUfsUnionCtx@2@@Z; UnionFs::UfsPathCache::DeleteEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::UfsUnionCtx const *)
0x14003e6c0  mov     r14d, eax
0x14003e6c3  test    eax, eax
0x14003e6c5  jns     short loc_14003E73E
0x14003e6c7  cmp     eax, 0C0000225h
0x14003e6cc  jz      short loc_14003E72D
0x14003e6ce  lea     rcx, aCouldNotDelete; "Could not DeleteEntry for item removal"
0x14003e6d5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003e6da  lea     rax, aPushDeletingEn; "PUSH: Deleting entry"
0x14003e6e1  mov     r8, 436001101C4h; struct UnionFs::StackEventTracer *
0x14003e6eb  lea     r9, aUnionfsUfspath_74; "UnionFs::UfsPathCacheManager::RemovalLi"...
0x14003e6f2  mov     [rsp+70h+Context], rax; char *
0x14003e6f7  mov     rdx, r15; int
0x14003e6fa  mov     ecx, r14d; this
0x14003e6fd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e702  mov     rcx, r15; this
0x14003e705  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14003e70a  xor     eax, eax
0x14003e70c  mov     dword ptr [r15], 0
0x14003e713  lea     rdx, [rbp+FastMutex]
0x14003e717  mov     [r15+224h], ax
0x14003e71f  mov     rcx, rsi
0x14003e722  call    ?AddToRemovalList@UfsPathCacheManager@UnionFs@@QEAAX$$QEAV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsPathCacheManager::AddToRemovalList(utl::unique_ptr<UnionFs::UfsPathCacheListItem,utl::default_delete<UnionFs::UfsPathCacheListItem>> &&)
0x14003e727  mov     rbx, [rbp+FastMutex]
0x14003e72b  jmp     short loc_14003E73E
0x14003e72d  xor     eax, eax
0x14003e72f  mov     dword ptr [r15], 0
0x14003e736  mov     [r15+224h], ax
0x14003e73e  test    rdi, rdi
0x14003e741  jz      short loc_14003E74B
0x14003e743  mov     rcx, rdi; this
0x14003e746  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003e74b  test    rbx, rbx
0x14003e74e  jz      loc_14003E61D
0x14003e754  jmp     short loc_14003E763
0x14003e756  test    rdi, rdi
0x14003e759  jz      short loc_14003E763
0x14003e75b  mov     rcx, rdi; this
0x14003e75e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003e763  mov     rcx, rbx; this
0x14003e766  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003e76b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e772  mov     rdx, rbx; Entry
0x14003e775  add     rcx, 3E0h; Lookaside
0x14003e77c  call    cs:__imp_ExFreeToLookasideListEx
0x14003e783  nop     dword ptr [rax+rax+00h]
0x14003e788  jmp     loc_14003E61D
0x14003e78d  mov     ecx, 3
0x14003e792  int     29h; Win8: RtlFailFast(ecx)
0x14003e794  mov     rbx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e79b  lea     rcx, [rbp+arg_18]
0x14003e79f  xor     r13b, r13b
0x14003e7a2  lea     rdx, [rbx+40h]
0x14003e7a6  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14003e7ab  lea     rax, [rbx+20h]
0x14003e7af  mov     rdi, [rax+10h]
0x14003e7b3  mov     [rbp+var_40], rax
0x14003e7b7  cmp     rdi, rax
0x14003e7ba  jz      loc_14003E979
0x14003e7c0  mov     rax, [rdi+28h]
0x14003e7c4  cmp     dword ptr [rax+1Ch], 2
0x14003e7c8  jnz     short loc_14003E7D4
0x14003e7ca  mov     rax, [rax+20h]
0x14003e7ce  mov     r12, [rax+10h]
0x14003e7d2  jmp     short loc_14003E7DF
0x14003e7d4  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e7db  mov     r12, [rax+50h]
0x14003e7df  mov     eax, [rsi+194h]
0x14003e7e5  nop
0x14003e7e6  cmp     [r12+0E0h], eax
0x14003e7ee  jbe     loc_14003E95C
0x14003e7f4  lea     rdx, [rsi+138h]
0x14003e7fb  lea     rcx, [rbp+arg_10]
0x14003e7ff  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14003e804  lea     r14, [rsi+118h]
0x14003e80b  cmp     [r14+10h], r14
0x14003e80f  jnz     short loc_14003E858
0x14003e811  mov     ecx, 20h ; ' '; unsigned __int64
0x14003e816  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e81b  mov     rbx, rax
0x14003e81e  test    rax, rax
0x14003e821  jz      loc_14003E8E6
0x14003e827  mov     [rax+18h], r12
0x14003e82b  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14003e832  mov     rax, r14
0x14003e835  or      rax, 1
0x14003e839  mov     [rbx], rax
0x14003e83c  mov     [rbx+8], rcx
0x14003e840  mov     [rbx+10h], rcx
0x14003e844  mov     [r14], rbx
0x14003e847  mov     [r14+8], rbx
0x14003e84b  mov     [r14+10h], rbx
0x14003e84f  inc     qword ptr [r14+18h]
0x14003e853  jmp     loc_14003E8DC
0x14003e858  mov     rcx, [r14]
0x14003e85b  xor     ebx, ebx
0x14003e85d  cmp     r12, [rcx+18h]
0x14003e861  jnb     short loc_14003E867
0x14003e863  xor     dl, dl
0x14003e865  jmp     short loc_14003E86C
0x14003e867  mov     rbx, rcx
0x14003e86a  mov     dl, 1; struct std::nothrow_t *
0x14003e86c  movzx   eax, dl
0x14003e86f  mov     r8, rcx
0x14003e872  mov     rcx, [rcx+rax*8+8]
0x14003e877  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14003e87e  cmp     rcx, rax
0x14003e881  jnz     short loc_14003E85D
0x14003e883  test    rbx, rbx
0x14003e886  jz      short loc_14003E892
0x14003e888  xor     eax, eax
0x14003e88a  cmp     [rbx+18h], r12
0x14003e88e  cmovb   rbx, rax
0x14003e892  mov     eax, dword ptr [rbp+LockHandle.LockQueue.Lock+1]
0x14003e895  mov     dword ptr [rbp+LockHandle.LockQueue.Lock+1], eax
0x14003e898  movzx   eax, word ptr [rbp+LockHandle.LockQueue.Lock+5]
0x14003e89c  mov     word ptr [rbp+LockHandle.LockQueue.Lock+5], ax
0x14003e8a0  mov     al, byte ptr [rbp+LockHandle.LockQueue.Lock+7]
0x14003e8a3  mov     byte ptr [rbp+LockHandle.LockQueue.Lock+7], al
0x14003e8a6  mov     [rbp+LockHandle.LockQueue.Next], r8
0x14003e8aa  mov     byte ptr [rbp+LockHandle.LockQueue.Lock], dl
0x14003e8ad  test    rbx, rbx
0x14003e8b0  jz      short loc_14003E8B7
0x14003e8b2  xor     r14b, r14b
0x14003e8b5  jmp     short loc_14003E8DF
0x14003e8b7  mov     ecx, 20h ; ' '; unsigned __int64
0x14003e8bc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e8c1  mov     rbx, rax
0x14003e8c4  test    rax, rax
0x14003e8c7  jz      short loc_14003E8E6
0x14003e8c9  mov     r8, rax
0x14003e8cc  mov     [rax+18h], r12
0x14003e8d0  lea     rdx, [rbp+LockHandle]
0x14003e8d4  mov     rcx, r14
0x14003e8d7  call    ?_InsertAt@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@UGuidComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@3@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>> *,bool> const &,utl::_TreeNode<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>> *)
0x14003e8dc  mov     r14b, 1
0x14003e8df  test    rbx, rbx
0x14003e8e2  jnz     short loc_14003E92C
0x14003e8e4  jmp     short loc_14003E8E9
0x14003e8e6  xor     r14b, r14b
0x14003e8e9  lea     rax, aOriginInsertin_0; "ORIGIN: Inserting into CachesOverThresh"...
0x14003e8f0  mov     r8, 431001101F0h; struct UnionFs::StackEventTracer *
0x14003e8fa  lea     r9, aUnionfsUfspath_74; "UnionFs::UfsPathCacheManager::RemovalLi"...
0x14003e901  mov     [rsp+70h+Context], rax; char *
0x14003e906  mov     rdx, r15; int
0x14003e909  mov     ecx, 0C000009Ah; this
0x14003e90e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e913  mov     rcx, r15; this
0x14003e916  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14003e91b  xor     eax, eax
0x14003e91d  mov     dword ptr [r15], 0
0x14003e924  mov     [r15+224h], ax
0x14003e92c  mov     rcx, [rbp+arg_10]; FastMutex
0x14003e930  test    r14b, r14b
0x14003e933  movzx   r13d, r13b
0x14003e937  mov     r12d, 1
0x14003e93d  cmovnz  r13d, r12d
0x14003e941  mov     [rbp+arg_10], 0
0x14003e949  test    rcx, rcx
0x14003e94c  jz      short loc_14003E962
0x14003e94e  call    cs:__imp_ExReleaseFastMutex
0x14003e955  nop     dword ptr [rax+rax+00h]
0x14003e95a  jmp     short loc_14003E962
0x14003e95c  mov     r12d, 1
0x14003e962  mov     dl, r12b
0x14003e965  mov     rcx, rdi
0x14003e968  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(bool)
0x14003e96d  mov     rdi, rax
0x14003e970  mov     rax, [rbp+var_40]
0x14003e974  jmp     loc_14003E7B7
0x14003e979  cmp     [rbp+arg_18], 0
0x14003e97e  jz      short loc_14003E989
0x14003e980  mov     rcx, [rbp+arg_18]; this
0x14003e984  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14003e989  test    r13b, r13b
0x14003e98c  jz      loc_14003EA51
0x14003e992  xorps   xmm0, xmm0
0x14003e995  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003e999  xor     eax, eax
0x14003e99b  mov     rcx, rsi; SpinLock
0x14003e99e  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14003e9a2  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14003e9a6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003e9ad  nop     dword ptr [rax+rax+00h]
0x14003e9b2  cmp     byte ptr [rsi+8], 0
0x14003e9b6  jz      loc_14003EA41
0x14003e9bc  xor     eax, eax
0x14003e9be  lock cmpxchg [rsi+170h], r12d
0x14003e9c7  jnz     short loc_14003EA41
0x14003e9c9  lea     rbx, [rsi+178h]
0x14003e9d0  mov     rcx, rbx; Event
0x14003e9d3  call    cs:__imp_KeClearEvent
0x14003e9da  nop     dword ptr [rax+rax+00h]
0x14003e9df  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003e9e3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003e9ea  nop     dword ptr [rax+rax+00h]
0x14003e9ef  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e9f6  lea     r8, ?TrimmerWorker@UfsPathCacheManager@UnionFs@@CAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x14003e9fd  mov     rcx, [rsi+110h]; FltWorkItem
0x14003ea04  mov     r9d, r12d; QueueType
0x14003ea07  mov     [rsp+70h+Context], 0; Context
0x14003ea10  mov     rdx, [rdx]; FltObject
0x14003ea13  call    cs:__imp_FltQueueGenericWorkItem
0x14003ea1a  nop     dword ptr [rax+rax+00h]
0x14003ea1f  test    eax, eax
0x14003ea21  jns     short loc_14003EA51
0x14003ea23  xor     r8d, r8d; Wait
0x14003ea26  xor     edx, edx; Increment
0x14003ea28  mov     rcx, rbx; Event
0x14003ea2b  call    cs:__imp_KeSetEvent
0x14003ea32  nop     dword ptr [rax+rax+00h]
0x14003ea37  xor     eax, eax
0x14003ea39  xchg    eax, [rsi+170h]
0x14003ea3f  jmp     short loc_14003EA51
0x14003ea41  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003ea45  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ea4c  nop     dword ptr [rax+rax+00h]
0x14003ea51  lea     rcx, [rbp+var_10]
0x14003ea55  call    wil__details__lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f______lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___
  ... truncated ...
```
