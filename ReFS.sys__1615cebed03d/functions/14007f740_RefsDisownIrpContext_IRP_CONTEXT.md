# RefsDisownIrpContext(_IRP_CONTEXT *)

- ea: `0x14007f740`
- end: `0x14007ffdf`
- name: `?RefsDisownIrpContext@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `2207`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140329ca0`
- `0x14033046c`

## callees

- `0x14007f740`
- `0x1400cedec`
- `0x140323140`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f8f3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f913`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f9b6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f8f3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f913`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007f9b6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007f92c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007f92c`
- `ntoskrnl!KeSetEvent` at `0x14007fc2f`
- `ntoskrnl!KeSetEvent` at `0x14007fc2f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007fbac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007fdf6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007fbac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007fdf6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007faf5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007fbe4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007fd39`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007faf5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007fbe4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14007fd39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fb04`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fbf3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fd48`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fb04`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fbf3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007fd48`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fb42`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fc3f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fd86`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fb42`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fc3f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007fd86`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fb4e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fc4b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fd92`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fb4e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fc4b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14007fd92`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14007f9f0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14007f9f0`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fa13`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fa72`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fcc2`
- `ntoskrnl!ExReleaseFastResource` at `0x14007ff74`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fa13`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fa72`
- `ntoskrnl!ExReleaseFastResource` at `0x14007fcc2`
- `ntoskrnl!ExReleaseFastResource` at `0x14007ff74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007fe24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ff93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007fe24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ff93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f99d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f99d`

## pseudocode

```c
void __fastcall RefsDisownIrpContext(struct _IRP_CONTEXT *a1)
{
  __int64 v2; // rsi
  char *v3; // r10
  int v4; // eax
  struct _IRP_CONTEXT *v5; // rbx
  __int16 v6; // r13
  char *v7; // rbp
  struct _IRP_CONTEXT *v8; // r12
  __int64 v9; // rax
  __int16 v10; // r8
  struct _IRP_CONTEXT *v11; // r15
  struct _IRP_CONTEXT *v12; // rax
  char *v13; // r13
  char *v14; // r15
  char *v15; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v17; // r8
  unsigned int i; // edx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  struct _IRP_CONTEXT *v21; // rsi
  struct _IRP_CONTEXT *v22; // rax
  _QWORD *v23; // rbp
  __int64 v24; // rax
  _QWORD **v25; // rbx
  _QWORD *v26; // rcx
  unsigned __int64 v27; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  _QWORD *v30; // rax
  struct _IRP_CONTEXT *j; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v33; // rcx
  bool v34; // zf
  int v35; // ecx
  struct _IRP_CONTEXT **v36; // r15
  _QWORD *v37; // r12
  __int64 v38; // rcx
  struct _FAST_MUTEX *v39; // rbx
  struct _IRP_CONTEXT *v40; // rax
  struct _IRP_CONTEXT **v41; // rcx
  unsigned int v42; // eax
  struct _FAST_MUTEX *v43; // rbx
  _QWORD *v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rcx
  struct _IRP_CONTEXT *m; // rax
  __int64 v48; // rdx
  struct _ERESOURCE *v49; // rcx
  __int64 v50; // rdx
  struct _IRP_CONTEXT **v51; // rax
  __int64 v52; // rcx
  struct _FAST_MUTEX *v53; // rsi
  struct _IRP_CONTEXT *v54; // rdx
  struct _IRP_CONTEXT **v55; // rcx
  unsigned int v56; // eax
  struct _IRP_CONTEXT *k; // rcx
  __int16 v58; // [rsp+60h] [rbp+8h]
  struct _IRP_CONTEXT **v59; // [rsp+68h] [rbp+10h]
  char *v60; // [rsp+70h] [rbp+18h]

  if ( *((_QWORD *)a1 + 6) )
    RefsReleaseSharedResources(a1);
  v2 = *((_QWORD *)a1 + 7);
  v3 = 0;
  if ( !v2 )
    goto LABEL_4;
  if ( *(_WORD *)v2 == 2050 )
  {
    v48 = *((_QWORD *)a1 + 13);
    v49 = *(struct _ERESOURCE **)(v2 + 96);
    if ( *(struct _ERESOURCE **)(v48 + 336) != v49 || !*(_DWORD *)(v48 + 320) || (v50 = v48 + 248) == 0 )
    {
      ExReleaseResourceLite(v49);
      v3 = 0;
      *((_QWORD *)a1 + 7) = 0;
      goto LABEL_4;
    }
    v34 = (*(_DWORD *)(v50 + 72))-- == 1;
    if ( v34 )
    {
      *(_DWORD *)(v50 + 76) &= ~2u;
      ExReleaseFastResource(v49, v50);
      v3 = 0;
      *((_QWORD *)a1 + 7) = 0;
      goto LABEL_4;
    }
  }
  else
  {
    *((_QWORD *)a1 + 7) = 0;
    v43 = *(struct _FAST_MUTEX **)(v2 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v43);
    v44 = (_QWORD *)(v2 + 448);
    if ( (_QWORD *)*v44 == v44 )
    {
      *(_QWORD *)(v2 + 440) = 0;
    }
    else
    {
      v45 = (_QWORD *)*v44;
      *(_QWORD *)(v2 + 440) |= 3uLL;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v45);
      *(_QWORD *)(v46 + 8) = 0;
      *(_QWORD *)v46 = 0;
      KeSetEvent((PRKEVENT)(v46 + 16), 0, 0);
    }
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v2 + 48));
    KeLeaveGuardedRegion();
    v3 = 0;
  }
  *((_QWORD *)a1 + 7) = 0;
LABEL_4:
  v4 = *((_DWORD *)a1 + 1);
  if ( (v4 & 0x2000) != 0 )
  {
    *((_DWORD *)a1 + 1) = v4 & 0xFFFFCFFF;
    ExReleaseFastResource(*((_QWORD *)a1 + 8) + 1208LL, 0);
    v3 = 0;
  }
  v5 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 14);
LABEL_7:
  if ( v5 != (struct _IRP_CONTEXT *)((char *)a1 + 112) )
  {
    v6 = *((_WORD *)v5 - 18);
    v7 = (char *)v5 - 64;
    v8 = v5;
    v58 = v6;
    v5 = *(struct _IRP_CONTEXT **)v5;
    while ( !*(_QWORD *)v8 )
    {
LABEL_20:
      if ( *(_WORD *)v7 == 2050 )
        v14 = v7;
      else
        v14 = (char *)*((_QWORD *)v7 + 17);
      v15 = v3;
      CurrentThread = KeGetCurrentThread();
      v17 = *((_QWORD *)v14 + 11) + 64LL;
      for ( i = (unsigned int)v3; i < 2; ++i )
      {
        v19 = 112LL * i;
        v20 = (_QWORD *)((char *)a1 + v19 + 352);
        if ( *v20 == v17 && *(struct _KTHREAD **)((char *)a1 + v19 + 360) == CurrentThread )
        {
          v15 = (char *)a1 + v19 + 352;
          if ( v20 )
            goto LABEL_50;
          break;
        }
      }
      for ( j = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 72);
            j != (struct _IRP_CONTEXT *)((char *)a1 + 576);
            j = *(struct _IRP_CONTEXT **)j )
      {
        if ( *((_QWORD *)j - 12) == v17 && *((struct _KTHREAD **)j - 11) == CurrentThread )
        {
          v15 = (char *)j - 96;
          break;
        }
      }
LABEL_50:
      IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v17);
      if ( !v15 )
      {
        v33 = (struct _ERESOURCE *)(*((_QWORD *)v14 + 11) + 64LL);
        if ( IsFastResourceHeldExclusive )
          ExReleaseFastResource(v33, 0);
        else
          ExReleaseResourceLite(v33);
        goto LABEL_53;
      }
      v35 = *((_DWORD *)v15 + 4);
      if ( IsFastResourceHeldExclusive )
      {
        if ( !v35 )
          goto LABEL_59;
        *((_DWORD *)v15 + 4) = v35 - 1;
        if ( v35 != 1 )
          goto LABEL_59;
LABEL_58:
        *(_QWORD *)v15 = 0;
        *((_QWORD *)v15 + 1) = 0;
        goto LABEL_59;
      }
      *((_DWORD *)v15 + 4) = v35 - 1;
      if ( v35 == 1 )
        goto LABEL_58;
LABEL_59:
      ExReleaseFastResource(*((_QWORD *)v14 + 11) + 64LL, v15 + 24);
LABEL_53:
      v3 = 0;
LABEL_54:
      v34 = v6-- == 1;
      v58 = v6;
      if ( v34 )
        goto LABEL_7;
    }
    if ( *((_WORD *)v7 + 14) != 1 )
      goto LABEL_19;
    v9 = *((_QWORD *)a1 + 3);
    if ( v9 && *(_QWORD *)(v9 + 144) && ((*((_DWORD *)v7 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
      goto LABEL_54;
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v8);
    v11 = (struct _IRP_CONTEXT *)((char *)a1 + 640);
    *((_QWORD *)v8 + 1) = v3;
    *(_QWORD *)v8 = v3;
    v12 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 80);
    if ( v12 == (struct _IRP_CONTEXT *)((char *)a1 + 640) )
    {
LABEL_19:
      --*((_WORD *)v7 + 14);
      goto LABEL_20;
    }
    v13 = v3;
    while ( v12 != v11 )
    {
      if ( *((_WORD *)v12 - 4) == v10 )
      {
        v13 = (char *)v12 - 8;
        break;
      }
      v12 = *(struct _IRP_CONTEXT **)v12;
    }
    if ( !v13 )
    {
LABEL_18:
      v6 = v58;
      goto LABEL_19;
    }
    while ( 1 )
    {
      v51 = (struct _IRP_CONTEXT **)(v13 + 8);
      v60 = v3;
      v59 = (struct _IRP_CONTEXT **)(v13 + 8);
      if ( *(struct _IRP_CONTEXT **)v11 != v11 )
      {
        for ( k = *v51; ; k = *(struct _IRP_CONTEXT **)k )
        {
          v59 = (struct _IRP_CONTEXT **)(v13 + 8);
          v51 = (struct _IRP_CONTEXT **)(v13 + 8);
          if ( k == v11 )
            break;
          if ( *((_WORD *)k - 4) == v10 )
          {
            v60 = (char *)k - 8;
            v51 = (struct _IRP_CONTEXT **)(v13 + 8);
            v59 = (struct _IRP_CONTEXT **)(v13 + 8);
            break;
          }
        }
      }
      v52 = *((_QWORD *)v13 + 6);
      if ( v52 )
      {
        if ( *(char **)(v52 + 136) != v7 )
          goto LABEL_103;
        if ( ((*(_DWORD *)(v52 + 152) & 0x2000) != 0 || (*(_DWORD *)(v52 + 300) & 0x40) != 0)
          && (*(_DWORD *)(v52 + 152) & 0x2000) != 0 )
        {
          _InterlockedAnd((volatile signed __int32 *)(v52 + 152), 0xFFFFDFFF);
        }
        v53 = *(struct _FAST_MUTEX **)(*((_QWORD *)v13 + 6) + 48LL);
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe(v53);
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v13 + 6) + 172LL));
        *(_QWORD *)(*((_QWORD *)v13 + 6) + 280LL) = 0;
        ++*(_DWORD *)(*((_QWORD *)v13 + 6) + 172LL);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*((_QWORD *)v13 + 6) + 48LL));
        KeLeaveGuardedRegion();
        v51 = v59;
      }
      v54 = *v51;
      if ( *((struct _IRP_CONTEXT ***)*v51 + 1) != v51 )
        goto LABEL_112;
      v55 = (struct _IRP_CONTEXT **)v51[1];
      if ( *v55 != (struct _IRP_CONTEXT *)v51 )
        goto LABEL_112;
      *v55 = v54;
      *((_QWORD *)v54 + 1) = v55;
      if ( v13 != (char *)a1 + 728 )
      {
        v56 = *((_DWORD *)v13 - 2);
        if ( v56 >= RefsNumberProcessors )
          v56 %= RefsNumberProcessors;
        ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v56], v13 - 8);
      }
LABEL_103:
      v3 = 0;
      v13 = v60;
      v10 = 2087;
      if ( !v60 )
        goto LABEL_18;
    }
  }
  v21 = (struct _IRP_CONTEXT *)((char *)a1 + 640);
  v22 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 80);
  if ( v22 != (struct _IRP_CONTEXT *)((char *)a1 + 640) )
  {
    v23 = 0;
    while ( v22 != v21 )
    {
      if ( *((_WORD *)v22 - 4) == 2087 )
      {
        v23 = (_QWORD *)((char *)v22 - 8);
        break;
      }
      v22 = *(struct _IRP_CONTEXT **)v22;
    }
    if ( v23 )
    {
      while ( 1 )
      {
        v36 = (struct _IRP_CONTEXT **)(v23 + 1);
        v37 = 0;
        if ( *(struct _IRP_CONTEXT **)v21 != v21 )
        {
          for ( m = *v36; ; m = *(struct _IRP_CONTEXT **)m )
          {
            v36 = (struct _IRP_CONTEXT **)(v23 + 1);
            if ( m == v21 )
              break;
            if ( *((_WORD *)m - 4) == 2087 )
            {
              v37 = (_QWORD *)((char *)m - 8);
              break;
            }
          }
        }
        v38 = v23[6];
        if ( v38 )
        {
          if ( ((*(_DWORD *)(v38 + 152) & 0x2000) != 0 || (*(_DWORD *)(v38 + 300) & 0x40) != 0)
            && (*(_DWORD *)(v38 + 152) & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)(v38 + 152), 0xFFFFDFFF);
          }
          v39 = *(struct _FAST_MUTEX **)(v23[6] + 48LL);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v39);
          _InterlockedIncrement((volatile signed __int32 *)(v23[6] + 172LL));
          *(_QWORD *)(v23[6] + 280LL) = 0;
          ++*(_DWORD *)(v23[6] + 172LL);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v23[6] + 48LL));
          KeLeaveGuardedRegion();
        }
        v40 = *v36;
        if ( *((struct _IRP_CONTEXT ***)*v36 + 1) != v36
          || (v41 = (struct _IRP_CONTEXT **)v36[1], *v41 != (struct _IRP_CONTEXT *)v36) )
        {
LABEL_112:
          __fastfail(3u);
        }
        *v41 = v40;
        *((_QWORD *)v40 + 1) = v41;
        if ( v23 != (_QWORD *)((char *)a1 + 728) )
        {
          v42 = *((_DWORD *)v23 - 2);
          if ( v42 >= RefsNumberProcessors )
            v42 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v42], v23 - 1);
        }
        if ( !v37 )
          break;
        v23 = v37;
      }
    }
  }
  v24 = *((_QWORD *)a1 + 1);
  if ( (v24 & 0x20000000000LL) != 0 )
  {
    *((_DWORD *)a1 + 59) &= ~1u;
    *((_QWORD *)a1 + 1) = v24 & 0xFFFFFDFFFFFFFFFFuLL;
  }
  if ( *((_QWORD *)a1 + 42) )
  {
    *((_DWORD *)a1 + 81) &= ~1u;
    *((_QWORD *)a1 + 42) = 0;
  }
  v25 = (_QWORD **)((char *)a1 + 576);
  while ( 1 )
  {
    v26 = *v25;
    if ( *v25 == v25 )
      break;
    if ( (_QWORD **)v26[1] != v25 )
      goto LABEL_112;
    v30 = (_QWORD *)*v26;
    if ( *(_QWORD **)(*v26 + 8LL) != v26 )
      goto LABEL_112;
    *v25 = v30;
    v30[1] = v25;
    ExFreePoolWithTag(v26 - 12, 0);
  }
  *((_QWORD *)a1 + 44) = 0;
  *((_QWORD *)a1 + 58) = 0;
  *((_DWORD *)a1 + 148) = 0;
  if ( a1 != *((struct _IRP_CONTEXT **)a1 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    *((_QWORD *)a1 + 1) |= 0x2000uLL;
    if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)7 )
      *((_QWORD *)a1 + 1) |= 0x400000uLL;
  }
  v27 = *((_QWORD *)a1 + 1);
  if ( (v27 & 0x100000) != 0 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
    *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
    *(_QWORD *)&TopLevelIrp->Flags = 0;
    IoSetTopLevelIrp(MdlAddress);
    v27 = *((_QWORD *)a1 + 1) & 0xFFFFFFFFFFEFFFFFuLL;
  }
  *((_DWORD *)a1 + 1) &= ~0x40u;
  *((_QWORD *)a1 + 1) = v27 & 0xFFFFFBFEFFFFFFFFuLL | 0x40000000000LL;
}

```

## disassembly

```asm
0x14007f740  mov     [rsp+arg_18], rbx
0x14007f745  push    rbp
0x14007f746  push    rsi
0x14007f747  push    rdi
0x14007f748  push    r12
0x14007f74a  push    r13
0x14007f74c  push    r14
0x14007f74e  push    r15
0x14007f750  sub     rsp, 20h
0x14007f754  cmp     qword ptr [rcx+30h], 0
0x14007f759  mov     rdi, rcx
0x14007f75c  jz      short loc_14007F763
0x14007f75e  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x14007f763  mov     rsi, [rdi+38h]
0x14007f767  xor     r10d, r10d
0x14007f76a  mov     r15d, 802h
0x14007f770  test    rsi, rsi
0x14007f773  jnz     loc_14007FBD2
0x14007f779  mov     eax, [rdi+4]
0x14007f77c  bt      eax, 0Dh
0x14007f780  jb      loc_14007FF5F
0x14007f786  mov     rbx, [rdi+70h]
0x14007f78a  lea     r14, [rdi+70h]
0x14007f78e  mov     r8d, 827h
0x14007f794  cmp     rbx, r14
0x14007f797  jz      loc_14007F872
0x14007f79d  movzx   r13d, word ptr [rbx-24h]
0x14007f7a2  lea     rbp, [rbx-40h]
0x14007f7a6  mov     r12, rbx
0x14007f7a9  mov     [rsp+58h+arg_0], r13w
0x14007f7af  mov     rbx, [rbx]
0x14007f7b2  mov     eax, 0FFFFh
0x14007f7b7  cmp     qword ptr [r12], 0
0x14007f7bc  jz      short loc_14007F827
0x14007f7be  cmp     word ptr [rbp+1Ch], 1
0x14007f7c3  jnz     short loc_14007F823
0x14007f7c5  mov     rax, [rdi+18h]
0x14007f7c9  test    rax, rax
0x14007f7cc  jnz     loc_14007FE4A
0x14007f7d2  mov     rcx, r12
0x14007f7d5  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x14007f7da  lea     r15, [rdi+280h]
0x14007f7e1  mov     [r12+8], r10
0x14007f7e6  mov     [r12], r10
0x14007f7ea  mov     rax, [r15]
0x14007f7ed  cmp     rax, r15
0x14007f7f0  jz      short loc_14007F818
0x14007f7f2  mov     r13, r10
0x14007f7f5  cmp     rax, r15
0x14007f7f8  jz      short loc_14007F809
0x14007f7fa  cmp     [rax-8], r8w
0x14007f7ff  jnz     loc_14007FEBF
0x14007f805  lea     r13, [rax-8]
0x14007f809  test    r13, r13
0x14007f80c  jnz     loc_14007FCE0
0x14007f812  movzx   r13d, [rsp+58h+arg_0]
0x14007f818  mov     eax, 0FFFFh
0x14007f81d  mov     r15d, 802h
0x14007f823  add     [rbp+1Ch], ax
0x14007f827  cmp     [rbp+0], r15w
0x14007f82c  jnz     loc_14007FA9F
0x14007f832  mov     r15, rbp
0x14007f835  mov     r8, [r15+58h]
0x14007f839  mov     rsi, r10
0x14007f83c  mov     r9, gs:188h
0x14007f845  add     r8, 40h ; '@'
0x14007f849  mov     edx, r10d
0x14007f84c  cmp     edx, 2
0x14007f84f  jnb     loc_14007F9DA
0x14007f855  mov     eax, edx
0x14007f857  imul    rcx, rax, 70h ; 'p'
0x14007f85b  lea     rax, [rdi+160h]
0x14007f862  add     rax, rcx
0x14007f865  cmp     [rax], r8
0x14007f868  jz      loc_14007FA80
0x14007f86e  inc     edx
0x14007f870  jmp     short loc_14007F84C
0x14007f872  lea     rsi, [rdi+280h]
0x14007f879  mov     rax, [rsi]
0x14007f87c  cmp     rax, rsi
0x14007f87f  jz      short loc_14007F8A1
0x14007f881  mov     rbp, r10
0x14007f884  cmp     rax, rsi
0x14007f887  jz      short loc_14007F898
0x14007f889  cmp     [rax-8], r8w
0x14007f88e  jnz     loc_14007FE78
0x14007f894  lea     rbp, [rax-8]
0x14007f898  test    rbp, rbp
0x14007f89b  jnz     loc_14007FAB0
0x14007f8a1  mov     rax, [rdi+8]
0x14007f8a5  bt      rax, 29h ; ')'
0x14007f8aa  jb      loc_14007FFAF
0x14007f8b0  cmp     qword ptr [rdi+150h], 0
0x14007f8b8  jnz     loc_14007FFCC
0x14007f8be  lea     rbx, [rdi+240h]
0x14007f8c5  mov     rcx, [rbx]
0x14007f8c8  cmp     rcx, rbx
0x14007f8cb  jnz     loc_14007F979
0x14007f8d1  xor     r10d, r10d
0x14007f8d4  mov     [rdi+160h], r10
0x14007f8db  mov     [r14+160h], r10
0x14007f8e2  mov     [rdi+250h], r10d
0x14007f8e9  cmp     rdi, [rdi+68h]
0x14007f8ed  jnz     loc_14007F9AE
0x14007f8f3  call    cs:__imp_IoGetTopLevelIrp
0x14007f8fa  nop     dword ptr [rax+rax+00h]
0x14007f8ff  cmp     byte ptr [rax], 0
0x14007f902  jz      loc_14007F9AE
0x14007f908  mov     rax, [rdi+8]
0x14007f90c  bt      rax, 14h
0x14007f911  jnb     short loc_14007F941
0x14007f913  call    cs:__imp_IoGetTopLevelIrp
0x14007f91a  nop     dword ptr [rax+rax+00h]
0x14007f91f  xor     edx, edx
0x14007f921  mov     rcx, [rax+8]; Irp
0x14007f925  mov     [rax+4], edx
0x14007f928  mov     [rax+10h], rdx
0x14007f92c  call    cs:__imp_IoSetTopLevelIrp
0x14007f933  nop     dword ptr [rax+rax+00h]
0x14007f938  mov     rax, [rdi+8]
0x14007f93c  btr     rax, 14h
0x14007f941  and     dword ptr [rdi+4], 0FFFFFFBFh
0x14007f945  mov     rcx, 0FFFFFFFEFFFFFFFFh
0x14007f94f  mov     rbx, [rsp+58h+arg_18]
0x14007f954  and     rax, rcx
0x14007f957  mov     rcx, 40000000000h
0x14007f961  or      rax, rcx
0x14007f964  mov     [rdi+8], rax
0x14007f968  add     rsp, 20h
0x14007f96c  pop     r15
0x14007f96e  pop     r14
0x14007f970  pop     r13
0x14007f972  pop     r12
0x14007f974  pop     rdi
0x14007f975  pop     rsi
0x14007f976  pop     rbp
0x14007f977  retn
0x14007f979  cmp     [rcx+8], rbx
0x14007f97d  jnz     loc_14007FE80
0x14007f983  mov     rax, [rcx]
0x14007f986  cmp     [rax+8], rcx
0x14007f98a  jnz     loc_14007FE80
0x14007f990  mov     [rbx], rax
0x14007f993  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14007f997  xor     edx, edx; Tag
0x14007f999  mov     [rax+8], rbx
0x14007f99d  call    cs:__imp_ExFreePoolWithTag
0x14007f9a4  nop     dword ptr [rax+rax+00h]
0x14007f9a9  jmp     loc_14007F8C5
0x14007f9ae  or      qword ptr [rdi+8], 2000h
0x14007f9b6  call    cs:__imp_IoGetTopLevelIrp
0x14007f9bd  nop     dword ptr [rax+rax+00h]
0x14007f9c2  cmp     qword ptr [rax+8], 7
0x14007f9c7  jnz     loc_14007F908
0x14007f9cd  or      qword ptr [rdi+8], 400000h
0x14007f9d5  jmp     loc_14007F908
0x14007f9da  lea     rax, [rdi+240h]
0x14007f9e1  mov     rcx, [rax]
0x14007f9e4  cmp     rcx, rax
0x14007f9e7  jnz     loc_14007FF12
0x14007f9ed  mov     rcx, r8
0x14007f9f0  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14007f9f7  nop     dword ptr [rax+rax+00h]
0x14007f9fc  test    rsi, rsi
0x14007f9ff  jnz     short loc_14007FA48
0x14007fa01  mov     rcx, [r15+58h]
0x14007fa05  add     rcx, 40h ; '@'; Resource
0x14007fa09  test    al, al
0x14007fa0b  jz      loc_14007FF93
0x14007fa11  xor     edx, edx
0x14007fa13  call    cs:__imp_ExReleaseFastResource
0x14007fa1a  nop     dword ptr [rax+rax+00h]
0x14007fa1f  xor     r10d, r10d
0x14007fa22  mov     r15d, 802h
0x14007fa28  mov     r8d, 827h
0x14007fa2e  mov     eax, 0FFFFh
0x14007fa33  add     r13w, ax
0x14007fa37  mov     [rsp+58h+arg_0], r13w
0x14007fa3d  jz      loc_14007F794
0x14007fa43  jmp     loc_14007F7B7
0x14007fa48  mov     ecx, [rsi+10h]
0x14007fa4b  test    al, al
0x14007fa4d  jnz     loc_14007FEEF
0x14007fa53  lea     eax, [rcx-1]
0x14007fa56  mov     [rsi+10h], eax
0x14007fa59  test    eax, eax
0x14007fa5b  jnz     short loc_14007FA66
0x14007fa5d  xor     edx, edx
0x14007fa5f  mov     [rsi], rdx
0x14007fa62  mov     [rsi+8], rdx
0x14007fa66  mov     rcx, [r15+58h]
0x14007fa6a  lea     rdx, [rsi+18h]
0x14007fa6e  add     rcx, 40h ; '@'
0x14007fa72  call    cs:__imp_ExReleaseFastResource
0x14007fa79  nop     dword ptr [rax+rax+00h]
0x14007fa7e  jmp     short loc_14007FA1F
0x14007fa80  cmp     [rcx+rdi+168h], r9
0x14007fa88  jnz     loc_14007F86E
0x14007fa8e  mov     rsi, rax
0x14007fa91  test    rax, rax
0x14007fa94  jnz     loc_14007F9ED
0x14007fa9a  jmp     loc_14007F9DA
0x14007fa9f  mov     r15, [rbp+88h]
0x14007faa6  jmp     loc_14007F835
0x14007fab0  lea     r15, [rbp+8]
0x14007fab4  mov     r12, r10
0x14007fab7  cmp     [rsi], rsi
0x14007faba  jnz     loc_14007FC63
0x14007fac0  mov     rcx, [rbp+30h]
0x14007fac4  test    rcx, rcx
0x14007fac7  jz      loc_14007FB5A
0x14007facd  mov     edx, [rcx+98h]
0x14007fad3  and     edx, 2000h
0x14007fad9  jnz     loc_14007FEC7
0x14007fadf  mov     eax, [rcx+12Ch]
0x14007fae5  test    al, 40h
0x14007fae7  jnz     loc_14007FEC7
0x14007faed  mov     rax, [rbp+30h]
0x14007faf1  mov     rbx, [rax+30h]
0x14007faf5  call    cs:__imp_KeEnterGuardedRegion
0x14007fafc  nop     dword ptr [rax+rax+00h]
0x14007fb01  mov     rcx, rbx; FastMutex
0x14007fb04  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14007fb0b  nop     dword ptr [rax+rax+00h]
0x14007fb10  mov     rax, [rbp+30h]
0x14007fb14  lock inc dword ptr [rax+0ACh]
0x14007fb1b  mov     rax, [rbp+30h]
0x14007fb1f  xor     edx, edx
0x14007fb21  mov     [rax+118h], rdx
0x14007fb28  mov     rcx, [rbp+30h]
0x14007fb2c  mov     eax, [rcx+0ACh]
0x14007fb32  inc     eax
0x14007fb34  mov     [rcx+0ACh], eax
0x14007fb3a  mov     rcx, [rbp+30h]
0x14007fb3e  mov     rcx, [rcx+30h]; FastMutex
0x14007fb42  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14007fb49  nop     dword ptr [rax+rax+00h]
0x14007fb4e  call    cs:__imp_KeLeaveGuardedRegion
0x14007fb55  nop     dword ptr [rax+rax+00h]
0x14007fb5a  mov     rax, [r15]
0x14007fb5d  cmp     [rax+8], r15
0x14007fb61  jnz     loc_14007FE80
0x14007fb67  mov     rcx, [r15+8]
0x14007fb6b  cmp     [rcx], r15
0x14007fb6e  jnz     loc_14007FE80
0x14007fb74  mov     [rcx], rax
0x14007fb77  mov     [rax+8], rcx
0x14007fb7b  lea     rax, [rdi+2D8h]
0x14007fb82  cmp     rbp, rax
0x14007fb85  jz      short loc_14007FBB8
0x14007fb87  mov     eax, [rbp-8]
0x14007fb8a  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14007fb90  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x14007fb97  cmp     eax, ecx
0x14007fb99  jnb     loc_14007FFA4
0x14007fb9f  mov     ecx, eax
0x14007fba1  lea     rdx, [rbp-8]; Entry
0x14007fba5  shl     rcx, 7
0x14007fba9  add     rcx, r8; Lookaside
0x14007fbac  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007fbb3  nop     dword ptr [rax+rax+00h]
0x14007fbb8  xor     r10d, r10d
0x14007fbbb  test    r12, r12
0x14007fbbe  jz      loc_14007F8A1
0x14007fbc4  mov     rbp, r12
0x14007fbc7  mov     r8d, 827h
0x14007fbcd  jmp     loc_14007FAB0
0x14007fbd2  cmp     [rsi], r15w
0x14007fbd6  jz      loc_14007FC89
0x14007fbdc  mov     [rdi+38h], r10
0x14007fbe0  mov     rbx, [rsi+30h]
0x14007fbe4  call    cs:__imp_KeEnterGuardedRegion
0x14007fbeb  nop     dword ptr [rax+rax+00h]
0x14007fbf0  mov     rcx, rbx; FastMutex
0x14007fbf3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14007fbfa  nop     dword ptr [rax+rax+00h]
0x14007fbff  lea     rcx, [rsi+1C0h]
0x14007fc06  cmp     [rcx], rcx
0x14007fc09  jz      loc_14007FE3C
0x14007fc0f  mov     rcx, [rcx]
0x14007fc12  or      qword ptr [rsi+1B8h], 3
0x14007fc1a  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x14007fc1f  xor     edx, edx; Increment
0x14007fc21  xor     r8d, r8d; Wait
0x14007fc24  mov     [rcx+8], rdx
0x14007fc28  mov     [rcx], rdx
0x14007fc2b  add     rcx, 10h; Event
0x14007fc2f  call    cs:__imp_KeSetEvent
0x14007fc36  nop     dword ptr [rax+rax+00h]
0x14007fc3b  mov     rcx, [rsi+30h]; FastMutex
0x14007fc3f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14007fc46  nop     dword ptr [rax+rax+00h]
0x14007fc4b  call    cs:__imp_KeLeaveGuardedRegion
0x14007fc52  nop     dword ptr [rax+rax+00h]
0x14007fc57  xor     r10d, r10d
0x14007fc5a  mov     [rdi+38h], r10
0x14007fc5e  jmp     loc_14007F779
0x14007fc63  mov     rax, [r15]
0x14007fc66  mov     rcx, r15
0x14007fc69  mov     r15, rcx
  ... truncated ...
```
