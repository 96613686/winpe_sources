# LfsWriteLogRecordIntoLogPage

- ea: `0x1401b2db0`
- end: `0x1401b39df`
- name: `LfsWriteLogRecordIntoLogPage`
- size: `3119`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401b2880`
- `0x1401b40d0`

## callees

- `0x140027f08`
- `0x14002f140`
- `0x14004134c`
- `0x140059440`
- `0x140059740`
- `0x1401b2db0`
- `0x1401b39f0`
- `0x1401b3c58`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401b3939`
- `ntoskrnl!KeSetEvent` at `0x1401b3939`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b2e19`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b2e19`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b3692`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b36f7`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b3692`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b36f7`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401b36a1`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401b36a1`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401b36d5`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401b36d5`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b30d1`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b30d1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b2f9c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b30ad`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b3979`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b2f9c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b30ad`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b3979`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b38e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b38e8`
- `ntoskrnl!KeInitializeEvent` at `0x1401b35c6`
- `ntoskrnl!KeInitializeEvent` at `0x1401b35c6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3619`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b36b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b38b7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3619`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b36b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b38b7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401b35f9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401b35f9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b30f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b3902`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b30f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b3902`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b30e5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b30e5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b30bd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b35de`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b30bd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b35de`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b3961`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b3961`
- `ntoskrnl!ExRaiseStatus` at `0x1401b398c`
- `ntoskrnl!ExRaiseStatus` at `0x1401b39be`
- `ntoskrnl!ExRaiseStatus` at `0x1401b398c`
- `ntoskrnl!ExRaiseStatus` at `0x1401b39be`

## pseudocode

```c
__int64 __fastcall LfsWriteLogRecordIntoLogPage(
        __int64 a1,
        __int64 a2,
        int a3,
        char **a4,
        int a5,
        _DWORD *a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        int a9,
        unsigned __int16 a10,
        unsigned __int64 *a11)
{
  int v11; // edi
  char **v13; // r14
  char **i; // rcx
  __int64 *v16; // rsi
  __int64 v17; // rbx
  int v18; // esi
  int v19; // r15d
  unsigned int v20; // esi
  unsigned __int16 v21; // r12
  int v22; // esi
  __int64 v23; // r8
  __int64 v24; // r10
  __int64 v25; // r13
  unsigned __int64 v26; // rdx
  int v27; // r9d
  __int16 v28; // cx
  unsigned int v29; // esi
  unsigned __int64 *v30; // rbx
  unsigned int v31; // r15d
  __int64 v32; // rax
  unsigned __int64 v33; // rsi
  _DWORD *v34; // rax
  int v35; // eax
  unsigned int v36; // esi
  int v37; // ebx
  __int64 v38; // rcx
  char v40; // r15
  __int64 Lbcb; // r8
  _DWORD *v42; // rdx
  unsigned int v43; // ebx
  __int16 v44; // r15
  __int64 *v45; // rax
  unsigned int v46; // ecx
  unsigned int v47; // r9d
  __int64 v48; // r12
  unsigned int v49; // r9d
  int v50; // r8d
  unsigned __int64 v51; // rbx
  __int64 v52; // rax
  unsigned __int64 *v53; // r15
  _DWORD *v54; // rax
  int v55; // eax
  unsigned int v56; // r13d
  unsigned int v57; // r8d
  char *v58; // r11
  int v59; // edx
  int v60; // r9d
  int v61; // r10d
  _QWORD *v62; // r8
  unsigned int v63; // eax
  void *v64; // r9
  unsigned int v65; // ecx
  char *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // r9
  unsigned int v69; // ecx
  __int64 v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 *v73; // rax
  struct _ERESOURCE *v74; // rcx
  BOOLEAN IsResourceAcquiredExclusiveLite; // r12
  __int64 v76; // rcx
  unsigned int v77; // ecx
  KPRIORITY v78; // r12d
  __int64 v79; // r9
  _DWORD *v80; // rax
  __int64 v81; // rcx
  __int64 *v82; // rax
  __int64 v83; // rcx
  _QWORD *v84; // rax
  _QWORD *v85; // rcx
  __int64 v86; // r11
  _QWORD *j; // rax
  _QWORD *v88; // rcx
  struct _ERESOURCE *v89; // rcx
  struct _KEVENT *v90; // rcx
  char *v91; // [rsp+30h] [rbp-A8h]
  __int64 v92; // [rsp+38h] [rbp-A0h]
  unsigned int v93; // [rsp+40h] [rbp-98h]
  int v94; // [rsp+44h] [rbp-94h]
  int v95; // [rsp+48h] [rbp-90h]
  unsigned int v96; // [rsp+4Ch] [rbp-8Ch]
  __int128 v97; // [rsp+50h] [rbp-88h] BYREF
  _BYTE Event[32]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v99; // [rsp+80h] [rbp-58h]
  unsigned int v100; // [rsp+E0h] [rbp+8h]
  int v101; // [rsp+E0h] [rbp+8h]
  unsigned int v103; // [rsp+E8h] [rbp+10h]
  unsigned int v104; // [rsp+E8h] [rbp+10h]
  NTSTATUS Status; // [rsp+F0h] [rbp+18h] BYREF
  unsigned __int64 v106; // [rsp+F8h] [rbp+20h]

  v11 = 0;
  Status = 0;
  v13 = a4;
  for ( i = a4; a3; i += 2 )
  {
    --a3;
    if ( *i )
      v11 += (*((_DWORD *)i + 2) + 7) & 0xFFFFFFF8;
  }
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
  v16 = (__int64 *)(a1 + 144);
  v17 = *(_QWORD *)(a1 + 144);
  if ( v17 != a1 + 144 )
  {
    v18 = *(_DWORD *)(a1 + 40);
    v19 = *(_DWORD *)(a1 + 44) & *(_DWORD *)(v17 + 40);
    if ( v19 )
      v20 = v18 - v19;
    else
      v20 = v18 - *(_DWORD *)(a1 + 80);
    if ( v11 + (unsigned int)*(unsigned __int16 *)(a1 + 96) <= v20 )
    {
      v21 = a10;
      v100 = LfsVerifyLogSpaceAvail(a1, a2, v11, a9, a10 & 1, (__int64)&Status);
      if ( Status )
      {
        ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
        ExRaiseStatus(Status);
      }
      v22 = v20 - *(unsigned __int16 *)(a1 + 96);
      if ( !v19 )
      {
        *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
        *(_DWORD *)(v17 + 40) += *(_DWORD *)(a1 + 80);
        v19 = *(_DWORD *)(a1 + 80);
      }
      v23 = *(unsigned int *)(v17 + 40);
      v24 = *(_QWORD *)(v17 + 48);
      v25 = v24 + (unsigned int)(*(_DWORD *)(v17 + 40) - v19);
      v26 = ((unsigned __int64)(v23 + *(_QWORD *)(v17 + 16)) >> 3) + (*(_QWORD *)(v17 + 32) << *(_DWORD *)(a1 + 124));
      v106 = v26;
      if ( a5 == 2 && *(__int16 *)(a1 + 422) > 1 )
        *(_DWORD *)(v25 + 16) |= 2u;
      v27 = *(unsigned __int16 *)(a1 + 96);
      *(_DWORD *)(v17 + 80) |= 1u;
      *(_DWORD *)(v17 + 40) += v27 + v11;
      *(_DWORD *)(v25 + 16) |= 1u;
      *(_QWORD *)(v17 + 72) = v26;
      if ( (*(_DWORD *)(a1 + 428) & 8) != 0 )
      {
        *(_QWORD *)(v25 + 32) = v26;
        v28 = *(_WORD *)(a1 + 44) & *(_WORD *)(v17 + 40);
        *(_WORD *)(v25 + 24) = v28;
        if ( !v28 )
          *(_WORD *)(v25 + 24) = 4096;
      }
      *(_QWORD *)(v17 + 64) = v26;
      v29 = v22 - v11;
      *(_QWORD *)(v25 + 8) = v26;
      if ( v29 >= *(unsigned __int16 *)(a1 + 96) )
        goto LABEL_17;
      v77 = v29 + *(_DWORD *)(v17 + 40);
      if ( v77 < *(_DWORD *)(v17 + 24) )
      {
        *(_DWORD *)(v17 + 40) = v77;
LABEL_17:
        v30 = (unsigned __int64 *)(v24 + v23);
        v31 = v27 + v19;
        **(_QWORD **)(a1 + 200) = v26;
        v32 = *(_QWORD *)(a1 + 200);
        *(_DWORD *)(a1 + 548) = 1;
        *(_DWORD *)(v32 + 32) = v11;
        if ( (*(_DWORD *)(a1 + 428) & 4) != 0 )
          *(_DWORD *)(a1 + 428) &= ~4u;
        ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
        v33 = v106;
        *a11 = v106;
        memset(v30, 0, *(unsigned __int16 *)(a1 + 96));
        v30[1] = a8;
        v30[2] = a7;
        v34 = a6;
        *v30 = v33;
        if ( v34 )
          *((_DWORD *)v30 + 9) = *v34;
        *((_DWORD *)v30 + 6) = v11;
        v35 = *(_DWORD *)(a2 + 32);
        *((_WORD *)v30 + 20) |= (v21 >> 1) & 6;
        *((_DWORD *)v30 + 7) = v35;
        for ( *((_DWORD *)v30 + 8) = a5; v11; v13 += 2 )
        {
          if ( *v13 )
          {
            v36 = *((_DWORD *)v13 + 2);
            v37 = -v36 & 7;
            memmove((void *)(v25 + v31), *v13, v36);
            v31 += v36 + v37;
            v11 -= v36 + v37;
          }
        }
        v38 = *(unsigned int *)(a1 + 428);
        if ( (v38 & 0x4000000) != 0 )
          LfsComputeLogPageChecksum(v38, v25, *(unsigned int *)(a1 + 40));
        return v100;
      }
      v84 = (_QWORD *)(a1 + 144);
      v85 = *(_QWORD **)(a1 + 144);
      if ( v85[1] == a1 + 144 )
      {
        v86 = *v85;
        if ( *(_QWORD **)(*v85 + 8LL) == v85 )
        {
          *v84 = v86;
          *(_QWORD *)(v86 + 8) = v84;
          *(_DWORD *)(v17 + 84) &= ~2u;
          *(_DWORD *)(v17 + 40) += v29;
          goto LABEL_17;
        }
      }
LABEL_54:
      __fastfail(3u);
    }
    v16 = (__int64 *)(a1 + 144);
  }
  ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
  if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a2 + 56)) )
  {
    if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a2 + 56)) )
      ExReleaseResourceLite(*(PERESOURCE *)(a2 + 56));
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a2 + 56), 1u);
  }
  v40 = a10;
  v96 = LfsVerifyLogSpaceAvail(a1, a2, v11, a9, a10 & 1, (__int64)&Status);
  if ( Status )
    ExRaiseStatus(Status);
  v42 = (_DWORD *)*v16;
  v43 = v11 + *(unsigned __int16 *)(a1 + 96);
  if ( (__int64 *)*v16 != v16
    && v43 > v42[6] - v42[10]
    && (*(_DWORD *)(a1 + 428) & 8) == 0
    && v42[10] != *(_DWORD *)(a1 + 80) )
  {
    v80 = (_DWORD *)*v16;
    if ( *(__int64 **)(*v16 + 8) != v16 )
      goto LABEL_54;
    v81 = *(_QWORD *)v80;
    if ( *(_DWORD **)(*(_QWORD *)v80 + 8LL) != v80 )
      goto LABEL_54;
    *v16 = v81;
    *(_QWORD *)(v81 + 8) = v16;
    v42[21] &= ~2u;
  }
  v44 = v40 & 2;
  Status = v43;
LABEL_37:
  v45 = (__int64 *)*v16;
  while ( 1 )
  {
    if ( v45 == v16 )
    {
      LOBYTE(Lbcb) = v44 != 0;
      Lbcb = LfsAllocateLbcb(a1, 1, Lbcb, 0);
      if ( !Lbcb )
      {
        v72 = LfsLiMax;
        v99 = 0;
        v97 = 0;
        memset(Event, 0, sizeof(Event));
        v73 = *(__int64 **)(a1 + 200);
        if ( LfsLiMax > *v73 )
          v72 = *v73;
        KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
        v74 = *(struct _ERESOURCE **)(a1 + 456);
        *(_QWORD *)&Event[24] = v72;
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(v74);
        while ( 1 )
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
          v76 = *(_QWORD *)(a1 + 456);
          if ( v72 <= *(_QWORD *)(a1 + 280) )
          {
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v76 + 120));
LABEL_90:
            v43 = Status;
            goto LABEL_37;
          }
          if ( !*(_DWORD *)(v76 + 176) )
            break;
          for ( j = *(_QWORD **)(a1 + 472); j != (_QWORD *)(a1 + 472); j = (_QWORD *)*j )
          {
            if ( j[5] > v72 )
              break;
          }
          v88 = (_QWORD *)j[1];
          if ( (_QWORD *)*v88 != j )
            goto LABEL_54;
          *((_QWORD *)&v97 + 1) = j[1];
          *(_QWORD *)&v97 = j;
          *v88 = &v97;
          j[1] = &v97;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 464));
          LfsReleaseLfcb(a1);
          KeWaitForSingleObject(Event, Executive, 0, 0, 0);
          v89 = *(struct _ERESOURCE **)(a1 + 456);
          if ( IsResourceAcquiredExclusiveLite )
            ExAcquireResourceExclusiveLite(v89, 1u);
          else
            ExAcquireResourceSharedLite(v89, 1u);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 464), 0xFFFFFFFF) == 1 )
          {
            v90 = *(struct _KEVENT **)(a1 + 608);
            if ( v90 )
              KeSetEvent(v90, 0, 0);
          }
        }
        *(_DWORD *)(v76 + 176) = 1;
        *(_QWORD *)(a1 + 504) = KeGetCurrentThread();
        v78 = KeSetPriorityThread(KeGetCurrentThread(), 16);
        PsEnterPriorityRegion();
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
        LOBYTE(v79) = 1;
        LfsFlushLfcbOnNewStack(a1, v72, 0, v79);
        PsLeavePriorityRegion();
        if ( v78 == 16 )
          goto LABEL_90;
        KeSetPriorityThread(KeGetCurrentThread(), v78);
        v43 = Status;
        goto LABEL_37;
      }
    }
    else
    {
      Lbcb = (__int64)(v45 - 3);
    }
    v46 = *(_DWORD *)(Lbcb + 48) - *(_DWORD *)(Lbcb + 64);
    v47 = *(_DWORD *)(a1 + 40);
    if ( v46 >= v47 )
      v46 -= *(_DWORD *)(a1 + 80) * (v46 / v47);
    if ( v46 >= v43 )
      break;
    v45 = *(__int64 **)(Lbcb + 24);
    v43 -= v46;
  }
  v48 = *v16 - 24;
  v95 = v11;
  v49 = *(_DWORD *)(v48 + 64);
  v50 = *(_DWORD *)(a1 + 44) & v49;
  if ( v50 )
  {
    LOBYTE(Status) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
    *(_DWORD *)(v48 + 64) += *(_DWORD *)(a1 + 80);
    v49 = *(_DWORD *)(v48 + 64);
    v50 = *(_DWORD *)(a1 + 80);
    LOBYTE(Status) = 1;
  }
  v103 = *(_DWORD *)(a1 + 40) - v50;
  v51 = (((unsigned __int64)v49 + *(_QWORD *)(v48 + 40)) >> 3) + (*(_QWORD *)(v48 + 56) << *(_DWORD *)(a1 + 124));
  v52 = *(_QWORD *)(v48 + 72);
  v92 = v52 + v49 - v50;
  v53 = (unsigned __int64 *)(v52 + v49);
  if ( a5 == 2 && *(__int16 *)(a1 + 422) > 1 )
    *(_DWORD *)(v52 + v49 - v50 + 16) |= 2u;
  memset(v53, 0, *(unsigned __int16 *)(a1 + 96));
  v53[1] = a8;
  v53[2] = a7;
  v54 = a6;
  *v53 = v51;
  if ( v54 )
    *((_DWORD *)v53 + 9) = *v54;
  *((_DWORD *)v53 + 6) = v11;
  *((_DWORD *)v53 + 7) = *(_DWORD *)(a2 + 32);
  *((_DWORD *)v53 + 8) = a5;
  *((_WORD *)v53 + 20) |= (a10 >> 1) & 6;
  if ( v11 + (unsigned int)*(unsigned __int16 *)(a1 + 96) > v103 )
    *((_WORD *)v53 + 20) |= 1u;
  v55 = *(unsigned __int16 *)(a1 + 96);
  *(_DWORD *)(v48 + 64) += v55;
  v56 = v103 - v55;
  v57 = *((_DWORD *)v13 + 2);
  v58 = *v13;
  v59 = -v57 & 7;
  LODWORD(v106) = *(unsigned __int16 *)(a1 + 96);
  v91 = v58;
  v104 = v57;
  v101 = v59;
  if ( v11 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( !v58 )
          {
            v57 = *((_DWORD *)v13 + 6);
            v13 += 2;
            v104 = v57;
            v59 = -v57 & 7;
            v58 = *v13;
            v101 = v59;
            v91 = *v13;
            goto LABEL_75;
          }
          v60 = *(_DWORD *)(v48 + 64);
          v61 = *(_DWORD *)(a1 + 44);
          if ( (*(_DWORD *)(v48 + 108) & 4) != 0 )
          {
            v63 = *(_DWORD *)(v48 + 64);
          }
          else
          {
            v62 = *(_QWORD **)(a1 + 136);
            if ( *v62 != a1 + 128 )
              goto LABEL_54;
            *(_QWORD *)(v48 + 16) = v62;
            *(_QWORD *)(v48 + 8) = a1 + 128;
            *v62 = v48 + 8;
            v57 = v104;
            *(_QWORD *)(a1 + 136) = v48 + 8;
            *(_DWORD *)(v48 + 108) |= 4u;
            v63 = *(_DWORD *)(v48 + 64);
          }
          if ( !(_DWORD)v106 && (v61 & v60) == 0 )
          {
            *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
            *(_DWORD *)(v48 + 64) += *(_DWORD *)(a1 + 80);
            v63 = *(_DWORD *)(v48 + 64);
            LOBYTE(Status) = 1;
          }
          v64 = (void *)(v63 + *(_QWORD *)(v48 + 72));
          LODWORD(v106) = 0;
          if ( v57 > v56 )
          {
            v94 = 0;
            v65 = v56;
            v93 = v56;
            v91 = &v58[v56];
            v104 = v57 - v56;
          }
          else
          {
            v94 = v59;
            v65 = v57;
            v93 = v57;
            if ( v11 != v59 + v57 )
            {
              v66 = v13[2];
              v13 += 2;
              v91 = v66;
              v104 = *((_DWORD *)v13 + 2);
              v101 = -v104 & 7;
            }
          }
          memmove(v64, v58, v65);
          v67 = v93;
          v68 = v92;
          v11 -= v94 + v93;
          v56 -= v94 + v93;
          *(_DWORD *)(v48 + 64) += v94 + v93;
          if ( (_BYTE)Status && !v56 )
            *(_DWORD *)(v92 + 16) &= ~1u;
          if ( !v11 )
          {
            *(_DWORD *)(v48 + 104) |= 1u;
            *(_DWORD *)(v92 + 16) |= 1u;
            *(_QWORD *)(v48 + 96) = v51;
            if ( (*(_DWORD *)(a1 + 428) & 8) != 0 )
            {
              *(_QWORD *)(v92 + 32) = v51;
              v67 = *(unsigned __int16 *)(a1 + 44);
              LOWORD(v67) = *(_WORD *)(v48 + 64) & v67;
              *(_WORD *)(v92 + 24) = v67;
              if ( !(_WORD)v67 )
                *(_WORD *)(v92 + 24) = 4096;
            }
          }
          if ( !v56 )
            break;
          v59 = v101;
          v57 = v104;
          v58 = v91;
        }
        while ( v11 );
        *(_QWORD *)(v48 + 88) = v51;
        *(_QWORD *)(v92 + 8) = v51;
        if ( (*(_DWORD *)(a1 + 428) & 0x4000000) != 0 )
        {
          LfsComputeLogPageChecksum(v67, v92, *(unsigned int *)(a1 + 40));
          v68 = v92;
        }
        if ( v56 < *(unsigned __int16 *)(a1 + 96) )
          break;
LABEL_74:
        v58 = v91;
        v57 = v104;
        v59 = v101;
LABEL_75:
        if ( !v11 )
          goto LABEL_76;
      }
      v69 = v56 + *(_DWORD *)(v48 + 64);
      if ( v69 < *(_DWORD *)(v48 + 48) )
      {
        v70 = *(unsigned int *)(a1 + 40);
        *(_DWORD *)(v48 + 64) = v69;
        v56 = *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 80);
        v92 = v70 + v68;
        goto LABEL_74;
      }
      v82 = (__int64 *)*v16;
      if ( *(__int64 **)(*v16 + 8) != v16 )
        goto LABEL_54;
      v83 = *v82;
      if ( *(__int64 **)(*v82 + 8) != v82 )
        goto LABEL_54;
      *v16 = v83;
      *(_QWORD *)(v83 + 8) = v16;
      *(_DWORD *)(v48 + 108) &= ~2u;
      *(_DWORD *)(v48 + 64) += v56;
      if ( !v11 )
        break;
      v48 = *v16 - 24;
      v56 = *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 80);
      v59 = v101;
      v57 = v104;
      v58 = v91;
      v92 = *(_QWORD *)(v48 + 72);
    }
  }
LABEL_76:
  *a11 = v51;
  **(_QWORD **)(a1 + 200) = v51;
  v71 = *(_QWORD *)(a1 + 200);
  *(_DWORD *)(a1 + 548) = 1;
  *(_DWORD *)(v71 + 32) = v95;
  if ( (*(_DWORD *)(a1 + 428) & 4) != 0 )
    *(_DWORD *)(a1 + 428) &= ~4u;
  return v96;
}

```

## disassembly

```asm
0x1401b2db0  mov     [rsp+arg_8], rdx
0x1401b2db5  push    rbx
0x1401b2db6  push    rbp
0x1401b2db7  push    rsi
0x1401b2db8  push    rdi
0x1401b2db9  push    r13
0x1401b2dbb  push    r14
0x1401b2dbd  sub     rsp, 0A8h
0x1401b2dc4  xor     edi, edi
0x1401b2dc6  mov     [rsp+0D8h+Status], 0
0x1401b2dd1  mov     rbp, rcx
0x1401b2dd4  mov     r14, r9
0x1401b2dd7  mov     r13, rdx
0x1401b2dda  mov     rcx, r9
0x1401b2ddd  test    r8d, r8d
0x1401b2de0  jz      short loc_1401B2DFF
0x1401b2de2  dec     r8d
0x1401b2de5  cmp     qword ptr [rcx], 0
0x1401b2de9  jz      short loc_1401B2DF6
0x1401b2deb  mov     eax, [rcx+8]
0x1401b2dee  add     eax, 7
0x1401b2df1  and     eax, 0FFFFFFF8h
0x1401b2df4  add     edi, eax
0x1401b2df6  add     rcx, 10h
0x1401b2dfa  test    r8d, r8d
0x1401b2dfd  jnz     short loc_1401B2DE2
0x1401b2dff  mov     rcx, [rdx+38h]
0x1401b2e03  xor     edx, edx
0x1401b2e05  add     rcx, 68h ; 'h'
0x1401b2e09  mov     [rsp+0D8h+var_38], r12
0x1401b2e11  mov     [rsp+0D8h+var_40], r15
0x1401b2e19  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401b2e20  nop     dword ptr [rax+rax+00h]
0x1401b2e25  lea     rsi, [rbp+90h]
0x1401b2e2c  mov     rbx, [rsi]
0x1401b2e2f  cmp     rbx, rsi
0x1401b2e32  jz      loc_1401B30A3
0x1401b2e38  mov     r15d, [rbx+28h]
0x1401b2e3c  mov     esi, [rbp+28h]
0x1401b2e3f  and     r15d, [rbp+2Ch]
0x1401b2e43  jz      loc_1401B3554
0x1401b2e49  sub     esi, r15d
0x1401b2e4c  movzx   eax, word ptr [rbp+60h]
0x1401b2e50  add     eax, edi
0x1401b2e52  cmp     eax, esi
0x1401b2e54  ja      loc_1401B309C
0x1401b2e5a  movzx   r12d, [rsp+0D8h+arg_48]
0x1401b2e63  lea     rcx, [rsp+0D8h+Status]
0x1401b2e6b  mov     r9d, [rsp+0D8h+arg_40]
0x1401b2e73  movzx   eax, r12b
0x1401b2e77  mov     [rsp+0D8h+var_B0], rcx
0x1401b2e7c  and     al, 1
0x1401b2e7e  mov     r8d, edi
0x1401b2e81  mov     byte ptr [rsp+0D8h+Timeout], al
0x1401b2e85  mov     rdx, r13
0x1401b2e88  mov     rcx, rbp
0x1401b2e8b  call    LfsVerifyLogSpaceAvail
0x1401b2e90  cmp     [rsp+0D8h+Status], 0
0x1401b2e98  mov     [rsp+0D8h+arg_0], eax
0x1401b2e9f  jnz     loc_1401B396F
0x1401b2ea5  movzx   eax, word ptr [rbp+60h]
0x1401b2ea9  sub     esi, eax
0x1401b2eab  test    r15d, r15d
0x1401b2eae  jnz     short loc_1401B2EC8
0x1401b2eb0  mov     rax, [rbp+198h]
0x1401b2eb7  sub     [rbp+190h], rax
0x1401b2ebe  mov     eax, [rbp+50h]
0x1401b2ec1  add     [rbx+28h], eax
0x1401b2ec4  mov     r15d, [rbp+50h]
0x1401b2ec8  mov     r8d, [rbx+28h]
0x1401b2ecc  mov     rax, [rbx+10h]
0x1401b2ed0  mov     r13d, r8d
0x1401b2ed3  mov     rdx, [rbx+20h]
0x1401b2ed7  add     rax, r8
0x1401b2eda  mov     ecx, [rbp+7Ch]
0x1401b2edd  sub     r13d, r15d
0x1401b2ee0  mov     r10, [rbx+30h]
0x1401b2ee4  shr     rax, 3
0x1401b2ee8  add     r13, r10
0x1401b2eeb  shl     rdx, cl
0x1401b2eee  add     rdx, rax
0x1401b2ef1  cmp     [rsp+0D8h+arg_20], 2
0x1401b2ef9  mov     [rsp+0D8h+arg_18], rdx
0x1401b2f01  jz      loc_1401B37EF
0x1401b2f07  movzx   r9d, word ptr [rbp+60h]
0x1401b2f0c  or      dword ptr [rbx+50h], 1
0x1401b2f10  lea     eax, [r9+rdi]
0x1401b2f14  add     [rbx+28h], eax
0x1401b2f17  or      dword ptr [r13+10h], 1
0x1401b2f1c  mov     [rbx+48h], rdx
0x1401b2f20  mov     eax, [rbp+1ACh]
0x1401b2f26  test    al, 8
0x1401b2f28  jz      short loc_1401B2F41
0x1401b2f2a  mov     [r13+20h], rdx
0x1401b2f2e  movzx   ecx, word ptr [rbx+28h]
0x1401b2f32  and     cx, [rbp+2Ch]
0x1401b2f36  mov     [r13+18h], cx
0x1401b2f3b  jz      loc_1401B3090
0x1401b2f41  mov     [rbx+40h], rdx
0x1401b2f45  sub     esi, edi
0x1401b2f47  mov     [r13+8], rdx
0x1401b2f4b  movzx   eax, word ptr [rbp+60h]
0x1401b2f4f  cmp     esi, eax
0x1401b2f51  jb      loc_1401B3631
0x1401b2f57  mov     rax, [rbp+0C8h]
0x1401b2f5e  lea     rbx, [r10+r8]
0x1401b2f62  add     r15d, r9d
0x1401b2f65  mov     [rax], rdx
0x1401b2f68  mov     rax, [rbp+0C8h]
0x1401b2f6f  mov     dword ptr [rbp+224h], 1
0x1401b2f79  mov     [rax+20h], edi
0x1401b2f7c  mov     eax, [rbp+1ACh]
0x1401b2f82  test    al, 4
0x1401b2f84  jnz     loc_1401B3999
0x1401b2f8a  mov     rcx, [rsp+0D8h+arg_8]
0x1401b2f92  xor     edx, edx
0x1401b2f94  mov     rcx, [rcx+38h]
0x1401b2f98  add     rcx, 68h ; 'h'
0x1401b2f9c  call    cs:__imp_ExReleasePushLockEx
0x1401b2fa3  nop     dword ptr [rax+rax+00h]
0x1401b2fa8  mov     rax, [rsp+0D8h+arg_50]
0x1401b2fb0  xor     edx, edx; Val
0x1401b2fb2  mov     rsi, [rsp+0D8h+arg_18]
0x1401b2fba  mov     rcx, rbx; void *
0x1401b2fbd  mov     [rax], rsi
0x1401b2fc0  movzx   r8d, word ptr [rbp+60h]; Size
0x1401b2fc5  call    memset
0x1401b2fca  mov     rax, [rsp+0D8h+arg_38]
0x1401b2fd2  mov     [rbx+8], rax
0x1401b2fd6  mov     rax, [rsp+0D8h+arg_30]
0x1401b2fde  mov     [rbx+10h], rax
0x1401b2fe2  mov     rax, [rsp+0D8h+arg_28]
0x1401b2fea  mov     [rbx], rsi
0x1401b2fed  test    rax, rax
0x1401b2ff0  jz      short loc_1401B2FF7
0x1401b2ff2  mov     eax, [rax]
0x1401b2ff4  mov     [rbx+24h], eax
0x1401b2ff7  mov     rax, [rsp+0D8h+arg_8]
0x1401b2fff  shr     r12w, 1
0x1401b3003  and     r12w, 6
0x1401b3008  mov     [rbx+18h], edi
0x1401b300b  mov     eax, [rax+20h]
0x1401b300e  or      [rbx+28h], r12w
0x1401b3013  mov     [rbx+1Ch], eax
0x1401b3016  mov     eax, [rsp+0D8h+arg_20]
0x1401b301d  mov     [rbx+20h], eax
0x1401b3020  test    edi, edi
0x1401b3022  jz      short loc_1401B3058
0x1401b3024  mov     rdx, [r14]; Src
0x1401b3027  test    rdx, rdx
0x1401b302a  jz      short loc_1401B3050
0x1401b302c  mov     esi, [r14+8]
0x1401b3030  mov     ebx, esi
0x1401b3032  mov     ecx, r15d
0x1401b3035  neg     ebx
0x1401b3037  mov     r8d, esi; Size
0x1401b303a  add     rcx, r13; void *
0x1401b303d  and     ebx, 7
0x1401b3040  call    memmove
0x1401b3045  lea     eax, [rsi+rbx]
0x1401b3048  add     r15d, eax
0x1401b304b  lea     eax, [rsi+rbx]
0x1401b304e  sub     edi, eax
0x1401b3050  add     r14, 10h
0x1401b3054  test    edi, edi
0x1401b3056  jnz     short loc_1401B3024
0x1401b3058  mov     ecx, [rbp+1ACh]
0x1401b305e  bt      ecx, 1Ah
0x1401b3062  jb      loc_1401B39AD
0x1401b3068  mov     eax, [rsp+0D8h+arg_0]
0x1401b306f  mov     r15, [rsp+0D8h+var_40]
0x1401b3077  mov     r12, [rsp+0D8h+var_38]
0x1401b307f  add     rsp, 0A8h
0x1401b3086  pop     r14
0x1401b3088  pop     r13
0x1401b308a  pop     rdi
0x1401b308b  pop     rsi
0x1401b308c  pop     rbp
0x1401b308d  pop     rbx
0x1401b308e  retn
0x1401b3090  mov     word ptr [r13+18h], 1000h
0x1401b3097  jmp     loc_1401B2F41
0x1401b309c  lea     rsi, [rbp+90h]
0x1401b30a3  mov     rcx, [r13+38h]
0x1401b30a7  xor     edx, edx
0x1401b30a9  add     rcx, 68h ; 'h'
0x1401b30ad  call    cs:__imp_ExReleasePushLockEx
0x1401b30b4  nop     dword ptr [rax+rax+00h]
0x1401b30b9  mov     rcx, [r13+38h]; Resource
0x1401b30bd  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401b30c4  nop     dword ptr [rax+rax+00h]
0x1401b30c9  test    al, al
0x1401b30cb  jnz     short loc_1401B3103
0x1401b30cd  mov     rcx, [r13+38h]; Resource
0x1401b30d1  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b30d8  nop     dword ptr [rax+rax+00h]
0x1401b30dd  test    eax, eax
0x1401b30df  jz      short loc_1401B30F1
0x1401b30e1  mov     rcx, [r13+38h]; Resource
0x1401b30e5  call    cs:__imp_ExReleaseResourceLite
0x1401b30ec  nop     dword ptr [rax+rax+00h]
0x1401b30f1  mov     rcx, [r13+38h]; Resource
0x1401b30f5  mov     dl, 1; Wait
0x1401b30f7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401b30fe  nop     dword ptr [rax+rax+00h]
0x1401b3103  movzx   r15d, [rsp+0D8h+arg_48]
0x1401b310c  lea     rcx, [rsp+0D8h+Status]
0x1401b3114  mov     r9d, [rsp+0D8h+arg_40]
0x1401b311c  movzx   eax, r15b
0x1401b3120  mov     [rsp+0D8h+var_B0], rcx
0x1401b3125  and     al, 1
0x1401b3127  mov     r8d, edi
0x1401b312a  mov     byte ptr [rsp+0D8h+Timeout], al
0x1401b312e  mov     rdx, r13
0x1401b3131  mov     rcx, rbp
0x1401b3134  call    LfsVerifyLogSpaceAvail
0x1401b3139  mov     ecx, [rsp+0D8h+Status]; Status
0x1401b3140  mov     [rsp+0D8h+var_8C], eax
0x1401b3144  test    ecx, ecx
0x1401b3146  jnz     loc_1401B39BE
0x1401b314c  movzx   ebx, word ptr [rbp+60h]
0x1401b3150  mov     rdx, [rsi]
0x1401b3153  add     ebx, edi
0x1401b3155  cmp     rdx, rsi
0x1401b3158  jz      short loc_1401B3168
0x1401b315a  mov     ecx, [rdx+18h]
0x1401b315d  sub     ecx, [rdx+28h]
0x1401b3160  cmp     ebx, ecx
0x1401b3162  ja      loc_1401B371A
0x1401b3168  and     r15w, 2
0x1401b316d  mov     [rsp+0D8h+Status], ebx
0x1401b3174  mov     rax, [rsi]
0x1401b3177  cmp     rax, rsi
0x1401b317a  jz      loc_1401B355C
0x1401b3180  lea     r8, [rax-18h]
0x1401b3184  mov     ecx, [r8+30h]
0x1401b3188  sub     ecx, [r8+40h]
0x1401b318c  mov     r9d, [rbp+28h]
0x1401b3190  cmp     ecx, r9d
0x1401b3193  jb      short loc_1401B31A2
0x1401b3195  xor     edx, edx
0x1401b3197  mov     eax, ecx
0x1401b3199  div     r9d
0x1401b319c  imul    eax, [rbp+50h]
0x1401b31a0  sub     ecx, eax
0x1401b31a2  cmp     ecx, ebx
0x1401b31a4  jb      loc_1401B370F
0x1401b31aa  mov     r12, [rsi]
0x1401b31ad  sub     r12, 18h
0x1401b31b1  mov     [rsp+0D8h+var_90], edi
0x1401b31b5  mov     r9d, [r12+40h]
0x1401b31ba  mov     r8d, r9d
0x1401b31bd  and     r8d, [rbp+2Ch]
0x1401b31c1  jnz     loc_1401B3336
0x1401b31c7  mov     rax, [rbp+198h]
0x1401b31ce  sub     [rbp+190h], rax
0x1401b31d5  mov     eax, [rbp+50h]
0x1401b31d8  add     [r12+40h], eax
0x1401b31dd  mov     r9d, [r12+40h]
0x1401b31e2  mov     r8d, [rbp+50h]
0x1401b31e6  mov     byte ptr [rsp+0D8h+Status], 1
0x1401b31ee  mov     eax, [rbp+28h]
0x1401b31f1  mov     ecx, [rbp+7Ch]
0x1401b31f4  sub     eax, r8d
0x1401b31f7  mov     rbx, [r12+38h]
0x1401b31fc  mov     dword ptr [rsp+0D8h+arg_8], eax
0x1401b3203  mov     rax, [r12+28h]
0x1401b3208  shl     rbx, cl
0x1401b320b  mov     edx, r9d
0x1401b320e  sub     r9d, r8d
0x1401b3211  add     rax, rdx
0x1401b3214  mov     ecx, r9d
0x1401b3217  shr     rax, 3
0x1401b321b  add     rbx, rax
0x1401b321e  mov     rax, [r12+48h]
0x1401b3223  add     rcx, rax
0x1401b3226  cmp     [rsp+0D8h+arg_20], 2
0x1401b322e  mov     [rsp+0D8h+var_A0], rcx
0x1401b3233  lea     r15, [rax+rdx]
0x1401b3237  jz      loc_1401B394A
0x1401b323d  movzx   r8d, word ptr [rbp+60h]; Size
0x1401b3242  xor     edx, edx; Val
0x1401b3244  mov     rcx, r15; void *
0x1401b3247  call    memset
0x1401b324c  mov     rax, [rsp+0D8h+arg_38]
0x1401b3254  mov     [r15+8], rax
0x1401b3258  mov     rax, [rsp+0D8h+arg_30]
0x1401b3260  mov     [r15+10h], rax
0x1401b3264  mov     rax, [rsp+0D8h+arg_28]
0x1401b326c  mov     [r15], rbx
0x1401b326f  test    rax, rax
0x1401b3272  jz      short loc_1401B327A
0x1401b3274  mov     eax, [rax]
0x1401b3276  mov     [r15+24h], eax
0x1401b327a  mov     [r15+18h], edi
0x1401b327e  mov     eax, [r13+20h]
0x1401b3282  mov     r13d, dword ptr [rsp+0D8h+arg_8]
0x1401b328a  mov     [r15+1Ch], eax
0x1401b328e  mov     eax, [rsp+0D8h+arg_20]
0x1401b3295  mov     [r15+20h], eax
  ... truncated ...
```
