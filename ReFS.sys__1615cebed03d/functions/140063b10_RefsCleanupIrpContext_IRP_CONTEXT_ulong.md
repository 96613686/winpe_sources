# RefsCleanupIrpContext(_IRP_CONTEXT *,ulong)

- ea: `0x140063b10`
- end: `0x140064474`
- name: `?RefsCleanupIrpContext@@YAXPEAU_IRP_CONTEXT@@K@Z`
- size: `2404`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned int)`
- caller_count: `33`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b1b0`
- `0x1400639e0`
- `0x1400b905c`
- `0x1400f5a90`
- `0x1400f966c`
- `0x1400f9998`
- `0x1400fac00`
- `0x1400fb7c4`
- `0x1400fba90`
- `0x1400fbbf8`
- `0x1400fbdd8`
- `0x1400fc5a8`
- `0x1400fc740`
- `0x140290034`
- `0x14029c790`
- `0x1402c8d84`
- `0x1402c9570`
- `0x1402c9800`
- `0x1402cde00`
- `0x1402cdf80`
- `0x1402d15d0`
- `0x1402d7904`
- `0x1402ed020`
- `0x1402ed150`
- `0x1403053a0`
- `0x140313620`
- `0x140318070`
- `0x140328fd0`
- `0x1403297e0`
- `0x14032afc0`
- `0x14032d490`
- `0x140332720`
- `0x14033a7a8`

## callees

- `0x140063b10`
- `0x1400cedec`
- `0x140323140`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140063db8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140063db8`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140063dd0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140063dd0`
- `ntoskrnl!KeSetEvent` at `0x14006408a`
- `ntoskrnl!KeSetEvent` at `0x14006408a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063d65`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006400a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064289`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063d65`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006400a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064289`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140064434`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140064434`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140063f55`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14006403f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400641cd`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140063f55`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14006403f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400641cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140063f64`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006404e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400641dc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140063f64`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006404e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400641dc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140063fa0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140064128`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006421c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140063fa0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140064128`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006421c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140063fac`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140064134`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140064228`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140063fac`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140064134`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140064228`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140063dff`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140063dff`
- `ntoskrnl!ExReleaseFastResource` at `0x140063e22`
- `ntoskrnl!ExReleaseFastResource` at `0x140063e84`
- `ntoskrnl!ExReleaseFastResource` at `0x140064108`
- `ntoskrnl!ExReleaseFastResource` at `0x1400643cc`
- `ntoskrnl!ExReleaseFastResource` at `0x140063e22`
- `ntoskrnl!ExReleaseFastResource` at `0x140063e84`
- `ntoskrnl!ExReleaseFastResource` at `0x140064108`
- `ntoskrnl!ExReleaseFastResource` at `0x1400643cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400642ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400643e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400642ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400643e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063da7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064410`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064449`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006445c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063da7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064410`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064449`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006445c`

## pseudocode

```c
void __fastcall RefsCleanupIrpContext(PSECURITY_SUBJECT_CONTEXT *a1, int a2)
{
  PSECURITY_SUBJECT_CONTEXT v3; // rsi
  PSECURITY_SUBJECT_CONTEXT *v4; // r13
  int v5; // eax
  struct _IRP_CONTEXT *v6; // rbx
  __int16 v7; // r12
  char *v8; // rbp
  struct _IRP_CONTEXT *v9; // rcx
  PSECURITY_SUBJECT_CONTEXT v10; // rax
  __int16 v11; // r8
  struct _IRP_CONTEXT *v12; // r15
  _QWORD *v13; // rcx
  struct _IRP_CONTEXT *v14; // rax
  char *v15; // r15
  PSECURITY_SUBJECT_CONTEXT *v16; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v18; // r8
  unsigned int j; // edx
  __int64 v20; // rcx
  PSECURITY_SUBJECT_CONTEXT *v21; // rax
  struct _IRP_CONTEXT *v22; // rsi
  struct _IRP_CONTEXT *v23; // rax
  PSECURITY_SUBJECT_CONTEXT *v24; // rbp
  PSECURITY_SUBJECT_CONTEXT *n; // rcx
  int v26; // ecx
  unsigned __int64 v27; // rax
  _QWORD **v28; // rbx
  _QWORD *v29; // rcx
  bool v30; // zf
  int v31; // eax
  PSECURITY_SUBJECT_CONTEXT v32; // rcx
  unsigned int v33; // eax
  struct _NPAGED_LOOKASIDE_LIST *v34; // r9
  _QWORD *v35; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  struct _IRP_CONTEXT *k; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v40; // rcx
  int v41; // ecx
  unsigned int v42; // ecx
  struct _IRP_CONTEXT **v43; // r15
  PSECURITY_SUBJECT_CONTEXT *v44; // r12
  PSECURITY_SUBJECT_CONTEXT v45; // rcx
  struct _FAST_MUTEX *v46; // rbx
  struct _IRP_CONTEXT *v47; // rcx
  struct _IRP_CONTEXT **v48; // rax
  unsigned int v49; // eax
  struct _FAST_MUTEX *PrimaryToken; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v51; // rcx
  _QWORD *ClientToken; // rcx
  __int64 v53; // rcx
  struct _IRP_CONTEXT *m; // rax
  PSECURITY_SUBJECT_CONTEXT v55; // rdx
  struct _ERESOURCE *v56; // rcx
  PVOID *p_ProcessAuditId; // rdx
  struct _IRP_CONTEXT **v58; // r12
  struct _IRP_CONTEXT *i; // rax
  PSECURITY_SUBJECT_CONTEXT v60; // rcx
  struct _FAST_MUTEX *v61; // rsi
  struct _IRP_CONTEXT *v62; // rcx
  struct _IRP_CONTEXT **v63; // rax
  unsigned int v64; // eax
  __int16 v65; // [rsp+70h] [rbp+8h]
  struct _IRP_CONTEXT *v67; // [rsp+80h] [rbp+18h]
  PSECURITY_SUBJECT_CONTEXT *v68; // [rsp+88h] [rbp+20h]

  if ( a1[6] )
    RefsReleaseSharedResources((struct _IRP_CONTEXT *)a1);
  v3 = a1[7];
  v4 = 0;
  if ( !v3 )
    goto LABEL_4;
  if ( LOWORD(v3->ClientToken) != 2050 )
  {
    a1[7] = 0;
    PrimaryToken = (struct _FAST_MUTEX *)v3[1].PrimaryToken;
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(PrimaryToken);
    v51 = v3 + 14;
    if ( v51->ClientToken == v51 )
    {
      v3[13].ProcessAuditId = 0;
    }
    else
    {
      ClientToken = v51->ClientToken;
      v3[13].ProcessAuditId = (PVOID)((unsigned __int64)v3[13].ProcessAuditId | 3);
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(ClientToken);
      *(_QWORD *)(v53 + 8) = 0;
      *(_QWORD *)v53 = 0;
      KeSetEvent((PRKEVENT)(v53 + 16), 0, 0);
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)v3[1].PrimaryToken);
    KeLeaveGuardedRegion();
LABEL_105:
    a1[7] = 0;
    goto LABEL_4;
  }
  v55 = a1[13];
  v56 = (struct _ERESOURCE *)v3[3].ClientToken;
  if ( v55[10].PrimaryToken != v56 || !LODWORD(v55[10].ClientToken) || (p_ProcessAuditId = &v55[7].ProcessAuditId) == 0 )
  {
    ExReleaseResourceLite(v56);
    a1[7] = 0;
    goto LABEL_4;
  }
  v30 = (*((_DWORD *)p_ProcessAuditId + 18))-- == 1;
  if ( !v30 )
    goto LABEL_105;
  *((_DWORD *)p_ProcessAuditId + 19) &= ~2u;
  ExReleaseFastResource(v56, p_ProcessAuditId);
  a1[7] = 0;
LABEL_4:
  v5 = *((_DWORD *)a1 + 1);
  if ( (v5 & 0x2000) != 0 )
  {
    *((_DWORD *)a1 + 1) = v5 & 0xFFFFCFFF;
    ExReleaseFastResource(&a1[8][37].ProcessAuditId, 0);
  }
  v6 = (struct _IRP_CONTEXT *)a1[14];
  while ( v6 != (struct _IRP_CONTEXT *)(a1 + 14) )
  {
    v7 = *((_WORD *)v6 - 18);
    v8 = (char *)v6 - 64;
    v9 = v6;
    v67 = v6;
    v6 = *(struct _IRP_CONTEXT **)v6;
    v65 = v7;
    while ( 2 )
    {
      if ( !*(_QWORD *)v9 )
        goto LABEL_19;
      if ( *((_WORD *)v8 + 14) != 1 )
        goto LABEL_18;
      v10 = a1[3];
      if ( v10 && v10[4].PrimaryToken && ((*((_DWORD *)v8 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
        goto LABEL_60;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v9);
      v12 = (struct _IRP_CONTEXT *)(a1 + 80);
      v13[1] = 0;
      *v13 = 0;
      v14 = (struct _IRP_CONTEXT *)a1[80];
      if ( v14 == (struct _IRP_CONTEXT *)(a1 + 80) )
        goto LABEL_18;
      while ( v14 != v12 )
      {
        if ( *((_WORD *)v14 - 4) == v11 )
        {
          v4 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v14 - 8);
          break;
        }
        v14 = *(struct _IRP_CONTEXT **)v14;
      }
      if ( !v4 )
        goto LABEL_17;
      do
      {
        v58 = (struct _IRP_CONTEXT **)(v4 + 1);
        v68 = 0;
        if ( *(struct _IRP_CONTEXT **)v12 != v12 )
        {
          for ( i = *v58; ; i = *(struct _IRP_CONTEXT **)i )
          {
            v58 = (struct _IRP_CONTEXT **)(v4 + 1);
            if ( i == v12 )
              break;
            if ( *((_WORD *)i - 4) == v11 )
            {
              v68 = (PSECURITY_SUBJECT_CONTEXT *)((char *)i - 8);
              break;
            }
          }
        }
        v60 = v4[6];
        if ( v60 )
        {
          if ( *(char **)&v60[4].ImpersonationLevel != v8 )
            goto LABEL_122;
          if ( (((__int64)v60[4].ProcessAuditId & 0x2000) != 0 || (*(&v60[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v60[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v60[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v61 = (struct _FAST_MUTEX *)v4[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v61);
          _InterlockedIncrement((volatile signed __int32 *)&v4[6][5].ImpersonationLevel + 1);
          v4[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v4[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v4[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v62 = *v58;
        if ( *((struct _IRP_CONTEXT ***)*v58 + 1) != v58 )
          goto LABEL_130;
        v63 = (struct _IRP_CONTEXT **)v58[1];
        if ( *v63 != (struct _IRP_CONTEXT *)v58 )
          goto LABEL_130;
        *v63 = v62;
        *((_QWORD *)v62 + 1) = v63;
        if ( v4 != a1 + 91 )
        {
          v64 = *((_DWORD *)v4 - 2);
          if ( v64 >= RefsNumberProcessors )
            v64 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v64], v4 - 1);
        }
LABEL_122:
        v11 = 2087;
        v4 = v68;
      }
      while ( v68 );
      v7 = v65;
LABEL_17:
      v4 = 0;
LABEL_18:
      --*((_WORD *)v8 + 14);
LABEL_19:
      if ( *(_WORD *)v8 == 2050 )
        v15 = v8;
      else
        v15 = (char *)*((_QWORD *)v8 + 17);
      v16 = 0;
      CurrentThread = KeGetCurrentThread();
      v18 = *((_QWORD *)v15 + 11) + 64LL;
      for ( j = 0; j < 2; ++j )
      {
        v20 = 14LL * j;
        v21 = &a1[v20 + 44];
        if ( *v21 == (PSECURITY_SUBJECT_CONTEXT)v18 && a1[v20 + 45] == (PSECURITY_SUBJECT_CONTEXT)CurrentThread )
        {
          v16 = &a1[v20 + 44];
          if ( v21 )
            goto LABEL_56;
          break;
        }
      }
      for ( k = (struct _IRP_CONTEXT *)a1[72]; k != (struct _IRP_CONTEXT *)(a1 + 72); k = *(struct _IRP_CONTEXT **)k )
      {
        if ( *((_QWORD *)k - 12) == v18 && *((struct _KTHREAD **)k - 11) == CurrentThread )
        {
          v16 = (PSECURITY_SUBJECT_CONTEXT *)((char *)k - 96);
          break;
        }
      }
LABEL_56:
      IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v18);
      if ( v16 )
      {
        v41 = *((_DWORD *)v16 + 4);
        if ( IsFastResourceHeldExclusive )
        {
          if ( v41 )
          {
            *((_DWORD *)v16 + 4) = v41 - 1;
            if ( v41 == 1 )
            {
LABEL_64:
              *v16 = 0;
              v16[1] = 0;
            }
          }
        }
        else
        {
          *((_DWORD *)v16 + 4) = v41 - 1;
          if ( v41 == 1 )
            goto LABEL_64;
        }
        ExReleaseFastResource(*((_QWORD *)v15 + 11) + 64LL, v16 + 3);
        goto LABEL_59;
      }
      v40 = (struct _ERESOURCE *)(*((_QWORD *)v15 + 11) + 64LL);
      if ( IsFastResourceHeldExclusive )
        ExReleaseFastResource(v40, 0);
      else
        ExReleaseResourceLite(v40);
LABEL_59:
      v9 = v67;
LABEL_60:
      v30 = v7-- == 1;
      v65 = v7;
      if ( !v30 )
        continue;
      break;
    }
  }
  v22 = (struct _IRP_CONTEXT *)(a1 + 80);
  v23 = (struct _IRP_CONTEXT *)a1[80];
  if ( v23 != (struct _IRP_CONTEXT *)(a1 + 80) )
  {
    v24 = 0;
    while ( v23 != v22 )
    {
      if ( *((_WORD *)v23 - 4) == 2087 )
      {
        v24 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v23 - 8);
        break;
      }
      v23 = *(struct _IRP_CONTEXT **)v23;
    }
    if ( v24 )
    {
      while ( 1 )
      {
        v43 = (struct _IRP_CONTEXT **)(v24 + 1);
        v44 = 0;
        if ( *(struct _IRP_CONTEXT **)v22 != v22 )
        {
          for ( m = *v43; ; m = *(struct _IRP_CONTEXT **)m )
          {
            v43 = (struct _IRP_CONTEXT **)(v24 + 1);
            if ( m == v22 )
              break;
            if ( *((_WORD *)m - 4) == 2087 )
            {
              v44 = (PSECURITY_SUBJECT_CONTEXT *)((char *)m - 8);
              break;
            }
          }
        }
        v45 = v24[6];
        if ( v45 )
        {
          if ( (((__int64)v45[4].ProcessAuditId & 0x2000) != 0 || (*(&v45[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v45[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v45[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v46 = (struct _FAST_MUTEX *)v24[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v46);
          _InterlockedIncrement((volatile signed __int32 *)&v24[6][5].ImpersonationLevel + 1);
          v24[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v24[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v24[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v47 = *v43;
        if ( *((struct _IRP_CONTEXT ***)*v43 + 1) != v43
          || (v48 = (struct _IRP_CONTEXT **)v43[1], *v48 != (struct _IRP_CONTEXT *)v43) )
        {
LABEL_130:
          __fastfail(3u);
        }
        *v48 = v47;
        *((_QWORD *)v47 + 1) = v48;
        if ( v24 != a1 + 91 )
        {
          v49 = *((_DWORD *)v24 - 2);
          if ( v49 >= RefsNumberProcessors )
            v49 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v49], v24 - 1);
        }
        if ( !v44 )
          break;
        v24 = v44;
      }
    }
  }
  for ( n = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; n; n = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
  {
    a1[75] = *n;
    ExFreePoolWithTag(n, 0);
  }
  v26 = *((_DWORD *)a1 + 1);
  if ( (v26 & 0x400) != 0 || (v27 = (unsigned __int64)a1[1], (v27 & 0x10000) != 0) )
  {
    if ( (v26 & 0x40000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v26 & 0xFFFBFBFF;
    }
    else
    {
      if ( a2 )
        v42 = v26 & 0xBFF9C0C5;
      else
        v42 = v26 & 0xF779C0CD;
      *((_DWORD *)a1 + 1) = v42;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
    }
    *((_DWORD *)a1 + 4) = 0;
  }
  else
  {
    if ( (v27 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v27 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v28 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v29 = *v28;
      if ( *v28 == v28 )
        break;
      if ( (_QWORD **)v29[1] != v28 )
        goto LABEL_130;
      v35 = (_QWORD *)*v29;
      if ( *(_QWORD **)(*v29 + 8LL) != v29 )
        goto LABEL_130;
      *v28 = v35;
      v35[1] = v28;
      ExFreePoolWithTag(v29 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v30 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v30 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v31 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v31 & 0x100000LL) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp(MdlAddress);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v32 = a1[89];
    if ( v32 )
    {
      ExFreePoolWithTag(v32, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000LL) != 0 )
    {
      v33 = *((_DWORD *)a1 - 2);
      if ( *((_WORD *)a1 + 1) == 1664 )
      {
        v34 = RefsIrpAndIoContextLookasideList;
        if ( v33 >= RefsNumberProcessors )
          goto LABEL_75;
      }
      else
      {
        v34 = RefsIrpContextLookasideList;
        if ( v33 < RefsNumberProcessors )
          goto LABEL_49;
LABEL_75:
        v33 %= RefsNumberProcessors;
      }
LABEL_49:
      ExFreeToNPagedLookasideList(&v34[(unsigned __int64)v33], a1 - 1);
    }
  }
}

```

## disassembly

```asm
0x140063b10  mov     [rsp+arg_8], edx
0x140063b14  push    rbx
0x140063b15  push    rbp
0x140063b16  push    rsi
0x140063b17  push    rdi
0x140063b18  push    r12
0x140063b1a  push    r13
0x140063b1c  push    r14
0x140063b1e  push    r15
0x140063b20  sub     rsp, 28h
0x140063b24  cmp     qword ptr [rcx+30h], 0
0x140063b29  mov     rdi, rcx
0x140063b2c  jz      short loc_140063B33
0x140063b2e  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x140063b33  mov     rsi, [rdi+38h]
0x140063b37  xor     r13d, r13d
0x140063b3a  mov     r15d, 802h
0x140063b40  test    rsi, rsi
0x140063b43  jnz     loc_14006402D
0x140063b49  mov     eax, [rdi+4]
0x140063b4c  bt      eax, 0Dh
0x140063b50  jb      loc_1400643B7
0x140063b56  mov     rbx, [rdi+70h]
0x140063b5a  lea     r14, [rdi+70h]
0x140063b5e  mov     r8d, 827h
0x140063b64  cmp     rbx, r14
0x140063b67  jz      loc_140063C3E
0x140063b6d  movzx   r12d, word ptr [rbx-24h]
0x140063b72  lea     rbp, [rbx-40h]
0x140063b76  mov     rcx, rbx
0x140063b79  mov     [rsp+68h+arg_10], rbx
0x140063b81  mov     rbx, [rbx]
0x140063b84  mov     eax, 0FFFFh
0x140063b89  mov     [rsp+68h+arg_0], r12w
0x140063b8f  cmp     qword ptr [rcx], 0
0x140063b93  jz      short loc_140063BF3
0x140063b95  cmp     word ptr [rbp+1Ch], 1
0x140063b9a  jnz     short loc_140063BEF
0x140063b9c  mov     rax, [rdi+18h]
0x140063ba0  test    rax, rax
0x140063ba3  jnz     loc_1400642CF
0x140063ba9  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140063bae  lea     r15, [rdi+280h]
0x140063bb5  mov     [rcx+8], r13
0x140063bb9  mov     [rcx], r13
0x140063bbc  mov     rax, [r15]
0x140063bbf  cmp     rax, r15
0x140063bc2  jz      short loc_140063BE4
0x140063bc4  cmp     rax, r15
0x140063bc7  jz      short loc_140063BD8
0x140063bc9  cmp     [rax-8], r8w
0x140063bce  jnz     loc_140064317
0x140063bd4  lea     r13, [rax-8]
0x140063bd8  test    r13, r13
0x140063bdb  jnz     loc_140064150
0x140063be1  xor     r13d, r13d
0x140063be4  mov     eax, 0FFFFh
0x140063be9  mov     r15d, 802h
0x140063bef  add     [rbp+1Ch], ax
0x140063bf3  cmp     [rbp+0], r15w
0x140063bf8  jnz     loc_140063EFA
0x140063bfe  mov     r15, rbp
0x140063c01  mov     r8, [r15+58h]
0x140063c05  mov     rsi, r13
0x140063c08  mov     r9, gs:188h
0x140063c11  add     r8, 40h ; '@'
0x140063c15  mov     edx, r13d
0x140063c18  cmp     edx, 2
0x140063c1b  jnb     loc_140063DE9
0x140063c21  mov     eax, edx
0x140063c23  imul    rcx, rax, 70h ; 'p'
0x140063c27  lea     rax, [rdi+160h]
0x140063c2e  add     rax, rcx
0x140063c31  cmp     [rax], r8
0x140063c34  jz      loc_140063EC1
0x140063c3a  inc     edx
0x140063c3c  jmp     short loc_140063C18
0x140063c3e  lea     rsi, [rdi+280h]
0x140063c45  mov     rax, [rsi]
0x140063c48  cmp     rax, rsi
0x140063c4b  jz      short loc_140063C6D
0x140063c4d  mov     rbp, r13
0x140063c50  cmp     rax, rsi
0x140063c53  jz      short loc_140063C64
0x140063c55  cmp     [rax-8], r8w
0x140063c5a  jnz     loc_1400642FD
0x140063c60  lea     rbp, [rax-8]
0x140063c64  test    rbp, rbp
0x140063c67  jnz     loc_140063F10
0x140063c6d  mov     rcx, [rdi+258h]; P
0x140063c74  test    rcx, rcx
0x140063c77  jnz     loc_140064404
0x140063c7d  mov     ecx, [rdi+4]
0x140063c80  bt      ecx, 0Ah
0x140063c84  jb      loc_140063E92
0x140063c8a  mov     rax, [rdi+8]
0x140063c8e  bt      rax, 10h
0x140063c93  jb      loc_140063E92
0x140063c99  bt      rax, 29h ; ')'
0x140063c9e  jnb     short loc_140063CB8
0x140063ca0  and     dword ptr [rdi+0ECh], 0FFFFFFFEh
0x140063ca7  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x140063cb1  and     rax, rcx
0x140063cb4  mov     [rdi+8], rax
0x140063cb8  cmp     qword ptr [rdi+150h], 0
0x140063cc0  jz      short loc_140063CD0
0x140063cc2  and     dword ptr [rdi+144h], 0FFFFFFFEh
0x140063cc9  mov     [rdi+150h], r13
0x140063cd0  lea     rbx, [rdi+240h]
0x140063cd7  mov     rcx, [rbx]
0x140063cda  cmp     rcx, rbx
0x140063cdd  jnz     loc_140063D83
0x140063ce3  mov     [rdi+160h], r13
0x140063cea  mov     [r14+160h], r13
0x140063cf1  test    byte ptr [rdi+8], 20h
0x140063cf5  mov     [rdi+250h], r13d
0x140063cfc  jnz     loc_14006442D
0x140063d02  mov     eax, [rdi+8]
0x140063d05  mov     [rdi+90h], r13
0x140063d0c  bt      rax, 14h
0x140063d11  jb      loc_140063DB8
0x140063d17  mov     rcx, [rdi+2C8h]; P
0x140063d1e  test    rcx, rcx
0x140063d21  jnz     loc_14006445A
0x140063d27  mov     eax, [rdi+8]
0x140063d2a  bt      rax, 13h
0x140063d2f  jnb     short loc_140063D71
0x140063d31  mov     eax, [rdi-8]
0x140063d34  mov     ecx, 680h
0x140063d39  cmp     [rdi+2], cx
0x140063d3d  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140063d43  jz      loc_140063EE0
0x140063d49  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x140063d50  cmp     eax, ecx
0x140063d52  jnb     loc_140063EEF
0x140063d58  mov     ecx, eax
0x140063d5a  lea     rdx, [rdi-8]; Entry
0x140063d5e  shl     rcx, 7
0x140063d62  add     rcx, r9; Lookaside
0x140063d65  call    cs:__imp_ExFreeToNPagedLookasideList
0x140063d6c  nop     dword ptr [rax+rax+00h]
0x140063d71  add     rsp, 28h
0x140063d75  pop     r15
0x140063d77  pop     r14
0x140063d79  pop     r13
0x140063d7b  pop     r12
0x140063d7d  pop     rdi
0x140063d7e  pop     rsi
0x140063d7f  pop     rbp
0x140063d80  pop     rbx
0x140063d81  retn
0x140063d83  cmp     [rcx+8], rbx
0x140063d87  jnz     loc_140064305
0x140063d8d  mov     rax, [rcx]
0x140063d90  cmp     [rax+8], rcx
0x140063d94  jnz     loc_140064305
0x140063d9a  mov     [rbx], rax
0x140063d9d  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x140063da1  xor     edx, edx; Tag
0x140063da3  mov     [rax+8], rbx
0x140063da7  call    cs:__imp_ExFreePoolWithTag
0x140063dae  nop     dword ptr [rax+rax+00h]
0x140063db3  jmp     loc_140063CD7
0x140063db8  call    cs:__imp_IoGetTopLevelIrp
0x140063dbf  nop     dword ptr [rax+rax+00h]
0x140063dc4  mov     rcx, [rax+8]; Irp
0x140063dc8  mov     [rax+4], r13d
0x140063dcc  mov     [rax+10h], r13
0x140063dd0  call    cs:__imp_IoSetTopLevelIrp
0x140063dd7  nop     dword ptr [rax+rax+00h]
0x140063ddc  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x140063de4  jmp     loc_140063D17
0x140063de9  lea     rax, [rdi+240h]
0x140063df0  mov     rcx, [rax]
0x140063df3  cmp     rcx, rax
0x140063df6  jnz     loc_14006436A
0x140063dfc  mov     rcx, r8
0x140063dff  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140063e06  nop     dword ptr [rax+rax+00h]
0x140063e0b  test    rsi, rsi
0x140063e0e  jnz     short loc_140063E5C
0x140063e10  mov     rcx, [r15+58h]
0x140063e14  add     rcx, 40h ; '@'; Resource
0x140063e18  test    al, al
0x140063e1a  jz      loc_1400643E8
0x140063e20  xor     edx, edx
0x140063e22  call    cs:__imp_ExReleaseFastResource
0x140063e29  nop     dword ptr [rax+rax+00h]
0x140063e2e  mov     rcx, [rsp+68h+arg_10]
0x140063e36  mov     r15d, 802h
0x140063e3c  mov     r8d, 827h
0x140063e42  mov     eax, 0FFFFh
0x140063e47  add     r12w, ax
0x140063e4b  mov     [rsp+68h+arg_0], r12w
0x140063e51  jz      loc_140063B64
0x140063e57  jmp     loc_140063B8F
0x140063e5c  mov     ecx, [rsi+10h]
0x140063e5f  test    al, al
0x140063e61  jnz     loc_140064347
0x140063e67  lea     eax, [rcx-1]
0x140063e6a  mov     [rsi+10h], eax
0x140063e6d  test    eax, eax
0x140063e6f  jnz     short loc_140063E78
0x140063e71  mov     [rsi], r13
0x140063e74  mov     [rsi+8], r13
0x140063e78  mov     rcx, [r15+58h]
0x140063e7c  lea     rdx, [rsi+18h]
0x140063e80  add     rcx, 40h ; '@'
0x140063e84  call    cs:__imp_ExReleaseFastResource
0x140063e8b  nop     dword ptr [rax+rax+00h]
0x140063e90  jmp     short loc_140063E2E
0x140063e92  bt      ecx, 12h
0x140063e96  jb      loc_1400640C1
0x140063e9c  cmp     [rsp+68h+arg_8], 0
0x140063ea1  jz      loc_14006430C
0x140063ea7  and     ecx, 0BFF9C0C5h
0x140063ead  mov     [rdi+4], ecx
0x140063eb0  and     qword ptr [rdi+8], 0FFFFFFFFFFFFFBFFh
0x140063eb8  mov     [rdi+10h], r13d
0x140063ebc  jmp     loc_140063D71
0x140063ec1  cmp     [rcx+rdi+168h], r9
0x140063ec9  jnz     loc_140063C3A
0x140063ecf  mov     rsi, rax
0x140063ed2  test    rax, rax
0x140063ed5  jnz     loc_140063DFC
0x140063edb  jmp     loc_140063DE9
0x140063ee0  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x140063ee7  cmp     eax, ecx
0x140063ee9  jb      loc_140063D58
0x140063eef  xor     edx, edx
0x140063ef1  div     ecx
0x140063ef3  mov     eax, edx
0x140063ef5  jmp     loc_140063D58
0x140063efa  mov     r15, [rbp+88h]
0x140063f01  jmp     loc_140063C01
0x140063f10  lea     r15, [rbp+8]
0x140063f14  mov     r12, r13
0x140063f17  cmp     [rsi], rsi
0x140063f1a  jnz     loc_14006409B
0x140063f20  mov     rcx, [rbp+30h]
0x140063f24  test    rcx, rcx
0x140063f27  jz      loc_140063FB8
0x140063f2d  mov     edx, [rcx+98h]
0x140063f33  and     edx, 2000h
0x140063f39  jnz     loc_14006431F
0x140063f3f  mov     eax, [rcx+12Ch]
0x140063f45  test    al, 40h
0x140063f47  jnz     loc_14006431F
0x140063f4d  mov     rax, [rbp+30h]
0x140063f51  mov     rbx, [rax+30h]
0x140063f55  call    cs:__imp_KeEnterGuardedRegion
0x140063f5c  nop     dword ptr [rax+rax+00h]
0x140063f61  mov     rcx, rbx; FastMutex
0x140063f64  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140063f6b  nop     dword ptr [rax+rax+00h]
0x140063f70  mov     rax, [rbp+30h]
0x140063f74  lock inc dword ptr [rax+0ACh]
0x140063f7b  mov     rax, [rbp+30h]
0x140063f7f  mov     [rax+118h], r13
0x140063f86  mov     rcx, [rbp+30h]
0x140063f8a  mov     eax, [rcx+0ACh]
0x140063f90  inc     eax
0x140063f92  mov     [rcx+0ACh], eax
0x140063f98  mov     rcx, [rbp+30h]
0x140063f9c  mov     rcx, [rcx+30h]; FastMutex
0x140063fa0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140063fa7  nop     dword ptr [rax+rax+00h]
0x140063fac  call    cs:__imp_KeLeaveGuardedRegion
0x140063fb3  nop     dword ptr [rax+rax+00h]
0x140063fb8  mov     rcx, [r15]
0x140063fbb  cmp     [rcx+8], r15
0x140063fbf  jnz     loc_140064305
0x140063fc5  mov     rax, [r15+8]
0x140063fc9  cmp     [rax], r15
0x140063fcc  jnz     loc_140064305
0x140063fd2  mov     [rax], rcx
0x140063fd5  mov     [rcx+8], rax
0x140063fd9  lea     rax, [rdi+2D8h]
0x140063fe0  cmp     rbp, rax
0x140063fe3  jz      short loc_140064016
0x140063fe5  mov     eax, [rbp-8]
0x140063fe8  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140063fee  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x140063ff5  cmp     eax, ecx
0x140063ff7  jnb     loc_1400643F9
0x140063ffd  mov     ecx, eax
0x140063fff  lea     rdx, [rbp-8]; Entry
0x140064003  shl     rcx, 7
0x140064007  add     rcx, r8; Lookaside
0x14006400a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064011  nop     dword ptr [rax+rax+00h]
0x140064016  test    r12, r12
0x140064019  jz      loc_140063C6D
0x14006401f  mov     rbp, r12
0x140064022  mov     r8d, 827h
0x140064028  jmp     loc_140063F10
0x14006402d  cmp     [rsi], r15w
0x140064031  jz      loc_1400640CF
0x140064037  mov     [rdi+38h], r13
0x14006403b  mov     rbx, [rsi+30h]
  ... truncated ...
```
