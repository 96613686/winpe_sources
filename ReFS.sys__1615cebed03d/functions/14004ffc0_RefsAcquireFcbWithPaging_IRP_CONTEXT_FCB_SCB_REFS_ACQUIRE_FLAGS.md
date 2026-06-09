# RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)

- ea: `0x14004ffc0`
- end: `0x140050b52`
- name: `?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z`
- size: `2962`
- prototype: ``
- caller_count: `35`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14004ecd0`
- `0x14009c3f0`
- `0x1400dbe04`
- `0x1400eb52c`
- `0x1400f01fc`
- `0x1400f6650`
- `0x1400fbdd8`
- `0x1401098a0`
- `0x140114dc0`
- `0x140291a00`
- `0x140298564`
- `0x14029bf9c`
- `0x1402a1e94`
- `0x1402ac480`
- `0x1402b0518`
- `0x1402b412c`
- `0x1402ba50c`
- `0x1402c3664`
- `0x1402c7d04`
- `0x1402c8380`
- `0x1402c90a0`
- `0x1402d2d88`
- `0x1402d390c`
- `0x1402d3dcc`
- `0x1402ff3f0`
- `0x140300990`
- `0x1403058c0`
- `0x1403078a0`
- `0x14030d820`
- `0x140319010`
- `0x14031cca8`
- `0x14031fa40`
- `0x14032afc0`
- `0x1403387e8`
- `0x14033c460`

## callees

- `0x140036670`
- `0x14004ffc0`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x1400d220c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140050568`
- `ntoskrnl!KeDelayExecutionThread` at `0x140050787`
- `ntoskrnl!KeDelayExecutionThread` at `0x140050568`
- `ntoskrnl!KeDelayExecutionThread` at `0x140050787`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400503b8`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140050464`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400503b8`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140050464`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400506da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400506da`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140050119`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140050119`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14005060e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14005060e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005061d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005061d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005065d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005065d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140050669`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140050669`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400502ed`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400504f5`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400502ed`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400504f5`
- `ntoskrnl!ExReleaseFastResource` at `0x140050314`
- `ntoskrnl!ExReleaseFastResource` at `0x140050531`
- `ntoskrnl!ExReleaseFastResource` at `0x140050b13`
- `ntoskrnl!ExReleaseFastResource` at `0x140050314`
- `ntoskrnl!ExReleaseFastResource` at `0x140050531`
- `ntoskrnl!ExReleaseFastResource` at `0x140050b13`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050a8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050b37`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050a8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050b37`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140050152`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140050152`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005082a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005082a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005075f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005075f`

## pseudocode

```c
__int64 __fastcall RefsAcquireFcbWithPaging(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // edi
  __int64 v5; // r12
  unsigned __int8 v8; // dl
  __int64 v9; // rax
  __int64 v10; // r13
  __int64 v11; // r15
  __int64 *v12; // rbx
  struct _KTHREAD *CurrentThread; // r12
  unsigned int i; // edx
  __int64 v15; // rcx
  _QWORD *j; // rcx
  unsigned int k; // edx
  BOOLEAN v18; // al
  _QWORD *v19; // rcx
  unsigned int v20; // r8d
  unsigned __int8 v21; // bl
  __int64 v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // r12
  _QWORD *v25; // rax
  _QWORD *jj; // r15
  __int64 v27; // r15
  __int64 v28; // r8
  _QWORD *v29; // rbx
  struct _KTHREAD *v30; // r9
  unsigned int n; // edx
  __int64 v32; // rcx
  _QWORD *ii; // rcx
  unsigned int v34; // r15d
  int v35; // r12d
  unsigned __int8 v36; // bl
  __int64 v37; // rcx
  unsigned int v38; // r8d
  _QWORD *v39; // rax
  __int64 v40; // rdx
  unsigned int v41; // ebx
  __int64 v42; // rcx
  unsigned int v43; // r8d
  char IsFastResourceHeldExclusive; // al
  int v45; // ecx
  _QWORD *v46; // rbx
  _QWORD *v47; // r13
  __int64 v48; // rcx
  struct _FAST_MUTEX *v49; // rbx
  _QWORD *v50; // rcx
  _QWORD *v51; // rax
  unsigned int v52; // eax
  _QWORD *m; // rax
  char *PoolWithTag; // rax
  _QWORD *kk; // rax
  _QWORD *v56; // rdx
  _QWORD *v57; // rax
  bool v58; // zf
  unsigned int v59; // ebx
  __int64 v61; // rdx
  struct _ERESOURCE *v62; // rcx
  __int64 v63; // rdx
  BOOLEAN v64; // [rsp+20h] [rbp-B8h]
  unsigned __int8 v65; // [rsp+21h] [rbp-B7h]
  char v66; // [rsp+22h] [rbp-B6h]
  _QWORD *v67; // [rsp+60h] [rbp-78h]

  v4 = a4;
  v5 = a3;
  v66 = 0;
  if ( (a4 & 2) != 0 )
  {
    v8 = 0;
  }
  else if ( (a4 & 4) != 0 )
  {
    v8 = 1;
  }
  else
  {
    v8 = *(_BYTE *)(a1 + 8) & 1;
  }
  v65 = v8;
  if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 )
    v4 = a4 | 0x10;
  v9 = *(_QWORD *)(a1 + 56);
  if ( v9 && (v4 & 0x20) == 0 )
  {
    if ( *(_WORD *)v9 != 2050 )
      v9 = *(_QWORD *)(v9 + 136);
    v61 = *(_QWORD *)(a1 + 104);
    v62 = *(struct _ERESOURCE **)(v9 + 96);
    if ( *(struct _ERESOURCE **)(v61 + 336) != v62 || (v63 = v61 + 248, !*(_DWORD *)(v63 + 72)) )
      v63 = 0;
    if ( v63 )
    {
      v58 = (*(_DWORD *)(v63 + 72))-- == 1;
      if ( v58 )
      {
        *(_DWORD *)(v63 + 76) &= ~2u;
        ExReleaseFastResource(v62, v63);
      }
    }
    else
    {
      ExReleaseResourceLite(v62);
    }
    *(_QWORD *)(a1 + 56) = 0;
    v8 = v65;
  }
  while ( 1 )
  {
    if ( (v4 & 0x10) != 0 && *(_QWORD *)(a2 + 96) )
    {
      if ( *(_WORD *)a2 == 2050 )
        v42 = a2;
      else
        v42 = *(_QWORD *)(a2 + 136);
      if ( !(unsigned __int8)ExAcquireFastResourceExclusive(*(_QWORD *)(v42 + 96), 0, v8) )
      {
        if ( (v4 & 2) != 0 )
          return 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x34Bu);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741608, v43);
        goto LABEL_188;
      }
      if ( (v4 & 0x20) == 0 )
        *(_QWORD *)(a1 + 56) = a2;
      v66 = 1;
    }
    if ( (v4 & 8) != 0 )
    {
      if ( (v4 & 2) != 0 )
      {
        v64 = 0;
      }
      else if ( (v4 & 4) != 0 )
      {
        v64 = 1;
      }
      else
      {
        v64 = *(_BYTE *)(a1 + 8) & 1;
      }
      if ( *(_WORD *)a2 == 2050 )
        v10 = a2;
      else
        v10 = *(_QWORD *)(a2 + 136);
      v11 = *(_QWORD *)(v10 + 88) + 64LL;
      v12 = 0;
      if ( a1 )
      {
        CurrentThread = KeGetCurrentThread();
        for ( i = 0; ; ++i )
        {
          if ( i >= 2 )
            goto LABEL_18;
          v15 = 112LL * i;
          if ( *(_QWORD *)(v15 + a1 + 352) == v11 && *(struct _KTHREAD **)(v15 + a1 + 360) == CurrentThread )
            break;
        }
        v12 = (__int64 *)(v15 + a1 + 352);
LABEL_18:
        if ( !v12 )
        {
          for ( j = *(_QWORD **)(a1 + 576); ; j = (_QWORD *)*j )
          {
            if ( j == (_QWORD *)(a1 + 576) )
              goto LABEL_21;
            if ( *(j - 12) == v11 && (struct _KTHREAD *)*(j - 11) == CurrentThread )
              break;
          }
          v12 = j - 12;
        }
LABEL_21:
        if ( !v12 )
        {
          for ( k = 0; ; ++k )
          {
            if ( k >= 2 )
              goto LABEL_26;
            if ( !*(_QWORD *)(a1 + 112LL * k + 352) )
              break;
          }
          v12 = (__int64 *)(a1 + 112LL * k + 352);
LABEL_26:
          if ( v12 )
            goto LABEL_27;
          for ( m = *(_QWORD **)(a1 + 576); ; m = (_QWORD *)*m )
          {
            if ( m == (_QWORD *)(a1 + 576) )
              goto LABEL_139;
            if ( !*(m - 12) )
              break;
          }
          v12 = m - 12;
LABEL_139:
          if ( v12 )
            goto LABEL_27;
          while ( 1 )
          {
            PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x70u, 0x73466552u);
            v12 = (__int64 *)PoolWithTag;
            if ( PoolWithTag )
              break;
            KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)&Interval);
          }
          *((_DWORD *)PoolWithTag + 4) = 0;
          v56 = *(_QWORD **)(a1 + 584);
          if ( *v56 != a1 + 576 )
LABEL_83:
            __fastfail(3u);
          v57 = PoolWithTag + 96;
          *v57 = a1 + 576;
          v57[1] = v56;
          *v56 = v57;
          *(_QWORD *)(a1 + 584) = v57;
          ++*(_DWORD *)(a1 + 592);
          if ( v12 )
          {
LABEL_27:
            ExInitializeFastOwnerEntry(v12 + 3);
            *v12 = v11;
            v12[1] = (__int64)CurrentThread;
          }
        }
        v5 = a3;
      }
      if ( v12 )
      {
        ++*((_DWORD *)v12 + 4);
        v18 = ExAcquireFastResourceShared(*(_QWORD *)(v10 + 88) + 64LL, v12 + 3, v64);
        if ( v18 )
        {
LABEL_31:
          if ( (v4 & 1) != 0 || (*(_BYTE *)(a2 + 8) & 1) == 0 && (!v5 || (*(_DWORD *)(v5 + 300) & 0x40) == 0) )
          {
            if ( *(_QWORD *)(a2 + 64) )
              ++*(_WORD *)(a2 + 28);
            v21 = 1;
            goto LABEL_38;
          }
LABEL_188:
          RefsReleaseResource(a1, a2);
          v59 = -1073741533;
          goto LABEL_190;
        }
        v58 = (*((_DWORD *)v12 + 4))-- == 1;
        if ( v58 )
        {
          v19 = 0;
          *v12 = 0;
          v12[1] = 0;
        }
      }
      else
      {
        v18 = ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v10 + 88) + 64LL), v64);
      }
      if ( !v18 )
      {
        if ( (v4 & 2) != 0 )
          goto LABEL_157;
        v59 = -1073741608;
LABEL_190:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids, v59);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v59, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x546u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v59, v20);
        __debugbreak();
      }
      goto LABEL_31;
    }
    v34 = 1;
    v35 = 0;
    if ( (v4 & 2) != 0 )
    {
      v36 = 0;
    }
    else
    {
      if ( (v4 & 4) != 0 )
      {
        v36 = 1;
        goto LABEL_77;
      }
      v36 = *(_BYTE *)(a1 + 8) & 1;
      if ( v36 )
        goto LABEL_77;
    }
    if ( (v4 & 0x40) != 0 )
      v34 = 10;
    while ( 1 )
    {
LABEL_77:
      if ( *(_WORD *)a2 == 2050 )
        v37 = a2;
      else
        v37 = *(_QWORD *)(a2 + 136);
      if ( (unsigned __int8)ExAcquireFastResourceExclusive(*(_QWORD *)(v37 + 88) + 64LL, 0, v36) )
      {
        if ( (v4 & 1) == 0
          && ((*(_BYTE *)(a2 + 8) & 1) != 0 || a3 && (*(_DWORD *)(a3 + 300) & 0x40) != 0)
          && ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
        {
          RefsReleaseResource(a1, a2);
          v41 = -1073741533;
LABEL_172:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids, v41);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v41, (struct _IRP_CONTEXT *)a1, "ResrcSup.c", 0x4C0u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v41, v38);
          __debugbreak();
        }
        v19 = (_QWORD *)(a2 + 64);
        if ( !*(_QWORD *)(a2 + 64) )
        {
          v39 = (_QWORD *)(a1 + 112);
          v40 = *(_QWORD *)(a1 + 112);
          if ( *(_QWORD *)(v40 + 8) != a1 + 112 )
            goto LABEL_83;
          *v19 = v40;
          *(_QWORD *)(a2 + 72) = v39;
          *(_QWORD *)(v40 + 8) = v19;
          *v39 = v19;
        }
        ++*(_WORD *)(a2 + 28);
        v21 = 1;
        goto LABEL_38;
      }
      if ( ++v35 >= v34 )
        break;
      KeDelayExecutionThread(0, 0, &RefsShortDelay);
    }
    if ( (v4 & 2) == 0 )
    {
      v41 = -1073741608;
      goto LABEL_172;
    }
LABEL_157:
    v21 = 0;
LABEL_38:
    if ( !v21 )
      break;
    if ( (v4 & 0x10) == 0 || v66 || !*(_QWORD *)(a2 + 96) )
      return 1;
    if ( !*(_QWORD *)(a2 + 64) )
      goto LABEL_55;
    if ( *(_WORD *)(a2 + 28) != 1 )
    {
LABEL_54:
      --*(_WORD *)(a2 + 28);
LABEL_55:
      if ( *(_WORD *)a2 == 2050 )
        v27 = a2;
      else
        v27 = *(_QWORD *)(a2 + 136);
      v28 = *(_QWORD *)(v27 + 88) + 64LL;
      v29 = 0;
      if ( !a1 )
        goto LABEL_69;
      v30 = KeGetCurrentThread();
      for ( n = 0; n < 2; ++n )
      {
        v32 = 112LL * n;
        if ( *(_QWORD *)(v32 + a1 + 352) == v28 && *(struct _KTHREAD **)(v32 + a1 + 360) == v30 )
        {
          v29 = (_QWORD *)(v32 + a1 + 352);
          break;
        }
      }
      if ( v29 )
        goto LABEL_106;
      for ( ii = *(_QWORD **)(a1 + 576); ii != (_QWORD *)(a1 + 576); ii = (_QWORD *)*ii )
      {
        if ( *(ii - 12) == v28 && (struct _KTHREAD *)*(ii - 11) == v30 )
        {
          v29 = ii - 12;
          break;
        }
      }
      if ( v29 )
      {
LABEL_106:
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*(_QWORD *)(v27 + 88) + 64LL);
        v45 = *((_DWORD *)v29 + 4);
        if ( !IsFastResourceHeldExclusive || v45 )
        {
          *((_DWORD *)v29 + 4) = v45 - 1;
          if ( v45 == 1 )
          {
            *v29 = 0;
            v29[1] = 0;
          }
        }
        ExReleaseFastResource(*(_QWORD *)(v27 + 88) + 64LL, v29 + 3);
      }
      else
      {
LABEL_69:
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v27 + 88) + 64LL) && a1 )
          ExReleaseFastResource(*(_QWORD *)(v27 + 88) + 64LL, 0);
        else
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v27 + 88) + 64LL));
      }
      goto LABEL_71;
    }
    v22 = *(_QWORD *)(a1 + 24);
    if ( !v22 || !*(_QWORD *)(v22 + 144) || (*(_DWORD *)(a2 + 8) & 0x8000LL) != 0 && (*(_DWORD *)(a1 + 4) & 0x1000) == 0 )
    {
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a2 + 64);
      *(_QWORD *)(a2 + 72) = 0;
      *v23 = 0;
      v24 = (_QWORD *)(a1 + 640);
      v25 = *(_QWORD **)(a1 + 640);
      jj = 0;
      if ( v25 == (_QWORD *)(a1 + 640) )
        goto LABEL_53;
      while ( 1 )
      {
        if ( v25 == v24 )
          goto LABEL_53;
        if ( *((_WORD *)v25 - 4) == 2087 )
          break;
        v25 = (_QWORD *)*v25;
      }
      for ( jj = v25 - 1; ; jj = v46 )
      {
LABEL_53:
        while ( 2 )
        {
          if ( !jj )
            goto LABEL_54;
          v46 = 0;
          v67 = 0;
          v47 = jj + 1;
          if ( (_QWORD *)*v24 != v24 )
          {
            for ( kk = (_QWORD *)*v47; ; kk = (_QWORD *)*kk )
            {
              v47 = jj + 1;
              if ( kk == v24 )
                break;
              if ( *((_WORD *)kk - 4) == 2087 )
              {
                v46 = kk - 1;
                v67 = kk - 1;
                break;
              }
            }
          }
          v48 = jj[6];
          if ( v48 )
          {
            if ( a2 && *(_QWORD *)(v48 + 136) != a2 )
            {
              jj = v46;
              continue;
            }
            if ( ((*(_DWORD *)(v48 + 152) & 0x2000) != 0 || (*(_DWORD *)(v48 + 300) & 0x40) != 0)
              && (*(_DWORD *)(v48 + 152) & 0x2000) != 0 )
            {
              _InterlockedAnd((volatile signed __int32 *)(v48 + 152), 0xFFFFDFFF);
            }
            v49 = *(struct _FAST_MUTEX **)(jj[6] + 48LL);
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v49);
            _InterlockedIncrement((volatile signed __int32 *)(jj[6] + 172LL));
            *(_QWORD *)(jj[6] + 280LL) = 0;
            ++*(_DWORD *)(jj[6] + 172LL);
            ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(jj[6] + 48LL));
            KeLeaveGuardedRegion();
            v46 = v67;
          }
          break;
        }
        v50 = (_QWORD *)*v47;
        if ( *(_QWORD **)(*v47 + 8LL) != v47 )
          goto LABEL_83;
        v51 = (_QWORD *)v47[1];
        if ( (_QWORD *)*v51 != v47 )
          goto LABEL_83;
        *v51 = v50;
        v50[1] = v51;
        if ( jj != (_QWORD *)(a1 + 728) )
        {
          v52 = *((_DWORD *)jj - 2);
          if ( v52 >= RefsNumberProcessors )
            v52 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v52], jj - 1);
        }
      }
    }
LABEL_71:
    v8 = v65;
    v5 = a3;
  }
  if ( v66 )
    RefsAcquireFcbWithPaging_::_2_::_lambda_1_::operator()(v19, a1, a2, v4);
  return v21;
}

```

## disassembly

```asm
0x14004ffc0  mov     [rsp+arg_18], r9d
0x14004ffc5  mov     [rsp+arg_10], r8
0x14004ffca  mov     [rsp+arg_8], rdx
0x14004ffcf  mov     [rsp+arg_0], rcx
0x14004ffd4  push    rbx
0x14004ffd5  push    rsi
0x14004ffd6  push    rdi
0x14004ffd7  push    r12
0x14004ffd9  push    r13
0x14004ffdb  push    r14
0x14004ffdd  push    r15
0x14004ffdf  sub     rsp, 0A0h
0x14004ffe6  mov     edi, r9d
0x14004ffe9  mov     r12, r8
0x14004ffec  mov     r14, rdx
0x14004ffef  mov     rsi, rcx
0x14004fff2  mov     [rsp+0D8h+var_B6], 0
0x14004fff7  test    r9b, 2
0x14004fffb  jz      loc_140050AB7
0x140050001  xor     dl, dl
0x140050003  mov     [rsp+0D8h+var_B7], dl
0x140050007  test    dword ptr [rcx+4], 10000h
0x14005000e  jz      short loc_14005001A
0x140050010  or      edi, 10h
0x140050013  mov     [rsp+0D8h+arg_18], edi
0x14005001a  mov     rax, [rcx+38h]
0x14005001e  test    rax, rax
0x140050021  jnz     loc_140050AD0
0x140050027  mov     r8d, 802h
0x14005002d  jmp     loc_140050333
0x140050032  test    r13d, r13d
0x140050035  jz      loc_1400501AF
0x14005003b  mov     [rsp+0D8h+var_B8], 0
0x140050040  mov     [rsp+0D8h+var_50], r14
0x140050048  cmp     [r14], r8w
0x14005004c  jnz     loc_1400504D1
0x140050052  mov     r13, r14
0x140050055  mov     r15, [r13+58h]
0x140050059  add     r15, 40h ; '@'
0x14005005d  mov     [rsp+0D8h+var_B0], 0
0x140050066  xor     ebx, ebx
0x140050068  test    rsi, rsi
0x14005006b  jz      loc_140050134
0x140050071  mov     r12, gs:188h
0x14005007a  mov     [rsp+0D8h+var_80], rbx
0x14005007f  mov     r8, gs:188h
0x140050088  xor     edx, edx
0x14005008a  mov     [rsp+0D8h+var_A8], edx
0x14005008e  cmp     edx, 2
0x140050091  jnb     short loc_1400500BE
0x140050093  mov     eax, edx
0x140050095  imul    rcx, rax, 70h ; 'p'
0x140050099  lea     rax, [rsi+160h]
0x1400500a0  add     rax, rcx
0x1400500a3  cmp     [rax], r15
0x1400500a6  jz      short loc_1400500AC
0x1400500a8  inc     edx
0x1400500aa  jmp     short loc_14005008A
0x1400500ac  cmp     [rcx+rsi+168h], r8
0x1400500b4  jnz     short loc_1400500A8
0x1400500b6  mov     rbx, rax
0x1400500b9  mov     [rsp+0D8h+var_80], rax
0x1400500be  test    rbx, rbx
0x1400500c1  jnz     short loc_1400500D6
0x1400500c3  lea     rax, [rsi+240h]
0x1400500ca  mov     rcx, [rax]
0x1400500cd  cmp     rcx, rax
0x1400500d0  jnz     loc_1400507E7
0x1400500d6  mov     [rsp+0D8h+var_B0], rbx
0x1400500db  test    rbx, rbx
0x1400500de  jnz     short loc_14005012C
0x1400500e0  xor     edx, edx
0x1400500e2  mov     [rsp+0D8h+var_A4], edx
0x1400500e6  cmp     edx, 2
0x1400500e9  jnb     short loc_14005010C
0x1400500eb  mov     eax, edx
0x1400500ed  imul    rax, 70h ; 'p'
0x1400500f1  add     rax, 160h
0x1400500f7  add     rax, rsi
0x1400500fa  cmp     qword ptr [rax], 0
0x1400500fe  jnz     loc_1400504E6
0x140050104  mov     rbx, rax
0x140050107  mov     [rsp+0D8h+var_B0], rax
0x14005010c  test    rbx, rbx
0x14005010f  jz      loc_140050720
0x140050115  lea     rcx, [rbx+18h]
0x140050119  call    cs:__imp_ExInitializeFastOwnerEntry
0x140050120  nop     dword ptr [rax+rax+00h]
0x140050125  mov     [rbx], r15
0x140050128  mov     [rbx+8], r12
0x14005012c  mov     r12, [rsp+0D8h+arg_10]
0x140050134  test    rbx, rbx
0x140050137  jz      loc_14005081D
0x14005013d  inc     dword ptr [rbx+10h]
0x140050140  lea     rdx, [rbx+18h]
0x140050144  mov     rcx, [r13+58h]
0x140050148  add     rcx, 40h ; '@'
0x14005014c  movzx   r8d, [rsp+0D8h+var_B8]
0x140050152  call    cs:__imp_ExAcquireFastResourceShared
0x140050159  nop     dword ptr [rax+rax+00h]
0x14005015e  test    al, al
0x140050160  jz      loc_14005096F
0x140050166  test    dil, 1
0x14005016a  jnz     short loc_14005018C
0x14005016c  test    byte ptr [r14+8], 1
0x140050171  jnz     loc_1400509ED
0x140050177  test    r12, r12
0x14005017a  jz      short loc_14005018C
0x14005017c  mov     eax, [r12+12Ch]
0x140050184  test    al, 40h
0x140050186  jnz     loc_1400509ED
0x14005018c  cmp     qword ptr [r14+40h], 0
0x140050191  jnz     loc_140050542
0x140050197  mov     bl, 1
0x140050199  test    bl, bl
0x14005019b  jz      loc_1400507C9
0x1400501a1  cmp     dword ptr [rsp+0D8h+var_90], 0
0x1400501a6  jnz     short loc_1400501C8
0x1400501a8  mov     bl, 1
0x1400501aa  jmp     loc_140050AA0
0x1400501af  test    dil, 4
0x1400501b3  jnz     loc_140050813
0x1400501b9  movzx   eax, byte ptr [rsi+8]
0x1400501bd  and     al, 1
0x1400501bf  mov     [rsp+0D8h+var_B8], al
0x1400501c3  jmp     loc_140050040
0x1400501c8  cmp     [rsp+0D8h+var_B6], 0
0x1400501cd  jnz     short loc_1400501A8
0x1400501cf  cmp     qword ptr [r14+60h], 0
0x1400501d4  jz      short loc_1400501A8
0x1400501d6  lea     rcx, [r14+40h]
0x1400501da  cmp     qword ptr [rcx], 0
0x1400501de  jz      short loc_140050253
0x1400501e0  cmp     word ptr [r14+1Ch], 1
0x1400501e6  jnz     short loc_140050249
0x1400501e8  mov     rax, [rsi+18h]
0x1400501ec  test    rax, rax
0x1400501ef  jnz     loc_1400506F1
0x1400501f5  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x1400501fa  xor     r9d, r9d
0x1400501fd  mov     [r14+48h], r9
0x140050201  mov     [rcx], r9
0x140050204  lea     r12, [rsi+280h]
0x14005020b  mov     rax, [r12]
0x14005020f  mov     r15d, r9d
0x140050212  cmp     rax, r12
0x140050215  jz      short loc_140050240
0x140050217  mov     [rsp+0D8h+var_60], r9
0x14005021c  mov     edx, 827h
0x140050221  cmp     rax, r12
0x140050224  jz      short loc_140050240
0x140050226  lea     rcx, [rax-8]
0x14005022a  cmp     [rcx], dx
0x14005022d  jnz     loc_1400507F8
0x140050233  mov     r15, rcx
0x140050236  mov     [rsp+0D8h+var_60], rcx
0x14005023b  nop     dword ptr [rax+rax+00h]
0x140050240  test    r15, r15
0x140050243  jnz     loc_1400505A8
0x140050249  mov     eax, 0FFFFh
0x14005024e  add     [r14+1Ch], ax
0x140050253  mov     [rsp+0D8h+var_40], r14
0x14005025b  mov     eax, 802h
0x140050260  cmp     [r14], ax
0x140050264  jnz     loc_14005057F
0x14005026a  mov     r15, r14
0x14005026d  mov     r8, [r15+58h]
0x140050271  add     r8, 40h ; '@'
0x140050275  xor     ebx, ebx
0x140050277  mov     [rsp+0D8h+var_70], rbx
0x14005027c  test    rsi, rsi
0x14005027f  jz      short loc_1400502E5
0x140050281  mov     r9, gs:188h
0x14005028a  xor     edx, edx
0x14005028c  mov     [rsp+0D8h+var_88], edx
0x140050290  cmp     edx, 2
0x140050293  jnb     short loc_1400502C0
0x140050295  mov     eax, edx
0x140050297  imul    rcx, rax, 70h ; 'p'
0x14005029b  lea     rax, [rsi+160h]
0x1400502a2  add     rax, rcx
0x1400502a5  cmp     [rax], r8
0x1400502a8  jz      short loc_1400502AE
0x1400502aa  inc     edx
0x1400502ac  jmp     short loc_14005028C
0x1400502ae  cmp     [rcx+rsi+168h], r9
0x1400502b6  jnz     short loc_1400502AA
0x1400502b8  mov     rbx, rax
0x1400502bb  mov     [rsp+0D8h+var_70], rax
0x1400502c0  test    rbx, rbx
0x1400502c3  jnz     loc_1400504ED
0x1400502c9  lea     rax, [rsi+240h]
0x1400502d0  mov     rcx, [rax]
0x1400502d3  cmp     rcx, rax
0x1400502d6  jnz     loc_14005089E
0x1400502dc  test    rbx, rbx
0x1400502df  jnz     loc_1400504ED
0x1400502e5  mov     rcx, [r15+58h]
0x1400502e9  add     rcx, 40h ; '@'
0x1400502ed  call    cs:__imp_ExIsFastResourceHeldExclusive
0x1400502f4  nop     dword ptr [rax+rax+00h]
0x1400502f9  test    al, al
0x1400502fb  jz      loc_140050A87
0x140050301  test    rsi, rsi
0x140050304  jz      loc_140050A87
0x14005030a  mov     rcx, [r15+58h]
0x14005030e  add     rcx, 40h ; '@'
0x140050312  xor     edx, edx
0x140050314  call    cs:__imp_ExReleaseFastResource
0x14005031b  nop     dword ptr [rax+rax+00h]
0x140050320  movzx   edx, [rsp+0D8h+var_B7]
0x140050325  mov     r8d, 802h
0x14005032b  mov     r12, [rsp+0D8h+arg_10]
0x140050333  mov     ecx, 0Ah
0x140050338  mov     ebx, 0C00000D8h
0x14005033d  mov     eax, edi
0x14005033f  and     eax, 10h
0x140050342  mov     dword ptr [rsp+0D8h+var_90], eax
0x140050346  jnz     loc_14005043A
0x14005034c  mov     r13d, edi
0x14005034f  and     r13d, 2
0x140050353  mov     [rsp+0D8h+var_A0], r13d
0x140050358  test    dil, 8
0x14005035c  jnz     loc_140050032
0x140050362  mov     r15d, 1
0x140050368  mov     [rsp+0D8h+var_9C], r15d
0x14005036d  xor     r12d, r12d
0x140050370  mov     [rsp+0D8h+var_98], r12d
0x140050375  test    r13d, r13d
0x140050378  jnz     loc_1400504BD
0x14005037e  test    dil, 4
0x140050382  jnz     loc_1400504DD
0x140050388  movzx   ebx, byte ptr [rsi+8]
0x14005038c  and     bl, r15b
0x14005038f  jz      loc_1400504BF
0x140050395  mov     [rsp+0D8h+var_48], r14
0x14005039d  cmp     [r14], r8w
0x1400503a1  jnz     loc_1400504B1
0x1400503a7  mov     rcx, r14
0x1400503aa  mov     rcx, [rcx+58h]
0x1400503ae  add     rcx, 40h ; '@'
0x1400503b2  movzx   r8d, bl
0x1400503b6  xor     edx, edx
0x1400503b8  call    cs:__imp_ExAcquireFastResourceExclusive
0x1400503bf  nop     dword ptr [rax+rax+00h]
0x1400503c4  test    al, al
0x1400503c6  jz      loc_14005054C
0x1400503cc  test    dil, 1
0x1400503d0  jz      short loc_1400503F8
0x1400503d2  lea     rcx, [r14+40h]
0x1400503d6  cmp     qword ptr [rcx], 0
0x1400503da  jnz     loc_1400504A5
0x1400503e0  lea     rax, [rsi+70h]
0x1400503e4  mov     rdx, [rax]
0x1400503e7  cmp     [rdx+8], rax
0x1400503eb  jz      loc_140050497
0x1400503f1  mov     ecx, 3
0x1400503f6  int     29h; Win8: RtlFailFast(ecx)
0x1400503f8  test    byte ptr [r14+8], 1
0x1400503fd  jnz     short loc_140050416
0x1400503ff  mov     rax, [rsp+0D8h+arg_10]
0x140050407  test    rax, rax
0x14005040a  jz      short loc_1400503D2
0x14005040c  mov     eax, [rax+12Ch]
0x140050412  test    al, 40h
0x140050414  jz      short loc_1400503D2
0x140050416  movzx   eax, byte ptr [rsi+28h]
0x14005041a  sub     al, 2
0x14005041c  test    al, 0EFh
0x14005041e  jz      short loc_1400503D2
0x140050420  mov     [rsp+0D8h+var_90], r14
0x140050425  mov     rdx, r14
0x140050428  mov     rcx, rsi
0x14005042b  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140050430  mov     ebx, 0C0000123h
0x140050435  jmp     loc_140050908
0x14005043a  cmp     qword ptr [r14+60h], 0
0x14005043f  jz      loc_14005034C
0x140050445  mov     [rsp+0D8h+var_58], r14
0x14005044d  cmp     [r14], r8w
0x140050451  jnz     loc_14005058B
0x140050457  mov     rcx, r14
0x14005045a  movzx   r8d, dl
0x14005045e  xor     edx, edx
0x140050460  mov     rcx, [rcx+60h]
0x140050464  call    cs:__imp_ExAcquireFastResourceExclusive
0x14005046b  nop     dword ptr [rax+rax+00h]
0x140050470  test    al, al
0x140050472  jz      loc_140050597
0x140050478  test    dil, 20h
0x14005047c  jnz     short loc_140050482
0x14005047e  mov     [rsi+38h], r14
0x140050482  mov     [rsp+0D8h+var_B6], 1
0x140050487  mov     ecx, 0Ah
0x14005048c  mov     r8d, 802h
0x140050492  jmp     loc_14005034C
0x140050497  mov     [rcx], rdx
0x14005049a  mov     [rcx+8], rax
0x14005049e  mov     [rdx+8], rcx
0x1400504a2  mov     [rax], rcx
  ... truncated ...
```
