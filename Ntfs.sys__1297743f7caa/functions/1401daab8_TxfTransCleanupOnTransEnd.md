# TxfTransCleanupOnTransEnd

- ea: `0x1401daab8`
- end: `0x1401db1ac`
- name: `TxfTransCleanupOnTransEnd`
- size: `1780`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bbf04`
- `0x140133f80`
- `0x1401d2fa0`
- `0x1401d6108`
- `0x1401da26c`

## callees

- `0x140010be0`
- `0x140037120`
- `0x140038f8c`
- `0x14004173c`
- `0x1400f871c`
- `0x140140fac`
- `0x1401c2b38`
- `0x1401d4f90`
- `0x1401d94d4`
- `0x1401d96e0`
- `0x1401d9714`
- `0x1401d978c`
- `0x1401daab8`
- `0x1401db1b4`
- `0x1401db5d8`
- `0x1401dbe24`
- `0x14028aa10`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402cd5f6`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402cd5f6`
- `ntoskrnl!qsort` at `0x1401dab86`
- `ntoskrnl!qsort` at `0x1401dab86`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dafd3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db02c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db081`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cd585`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dafd3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db02c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db081`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cd585`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401dabdf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd5a5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd64f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401dabdf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd5a5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd64f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401daca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db0a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db0de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401daca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db0a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db0de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401dab37`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401db129`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402cd625`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401dab37`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401db129`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402cd625`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dabb3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dabb3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401daf65`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401daf65`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401daf80`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401daf80`

## pseudocode

```c
void __fastcall TxfTransCleanupOnTransEnd(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 v5; // r14
  unsigned int v6; // ebp
  int v7; // r13d
  void *v10; // rcx
  _QWORD **v11; // r15
  _QWORD *i; // rbx
  _QWORD *v13; // rsi
  __int64 v14; // rbx
  unsigned int j; // ebx
  __int64 v16; // rcx
  _QWORD *v17; // r12
  _QWORD *v18; // rsi
  int v19; // r15d
  _DWORD *v20; // rax
  _QWORD *v21; // rdx
  void *v22; // rcx
  __int64 v23; // rbp
  __int64 v24; // r12
  int v25; // eax
  __int64 k; // rbx
  __int64 v27; // rax
  __int64 v28; // rbx
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rbp
  _QWORD *v32; // rcx
  _QWORD *v33; // r8
  _QWORD *v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD **v37; // rbx
  _QWORD *v38; // rdx
  int v39; // r8d
  _QWORD **v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  _QWORD *v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rax
  _QWORD *v46; // rbx
  _QWORD *v47; // rax
  void *v48; // rcx
  _QWORD *v49; // rbx
  __int64 v50; // r8
  void *v51; // r15
  _QWORD *v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rdx
  void *v55; // rbx
  struct _FAST_MUTEX *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // [rsp+20h] [rbp-58h]
  _QWORD *v61; // [rsp+30h] [rbp-48h]
  __int64 v63; // [rsp+88h] [rbp+10h]

  v5 = *(_QWORD *)(a2 + 208);
  v6 = 0;
  v63 = 0;
  v60 = 0;
  v7 = a3;
  if ( (_DWORD)a3 || a4 )
    TxfTransCleanupTxfWriterInformation(a1, a2, 1);
  v10 = *(void **)(a2 + 400);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0);
    *(_QWORD *)(a2 + 400) = 0;
    *(_WORD *)(a2 + 412) = 0;
    *(_WORD *)(a2 + 408) = 0;
  }
  LOBYTE(a3) = 1;
  TxfCloseHandlesForTransaction(a1, a2, a3);
  TxfCleanupNoRenameListAtEndOfTrans(a2);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 96LL));
  v11 = (_QWORD **)(a2 + 192);
  for ( i = *(_QWORD **)(a2 + 192); i != v11; i = (_QWORD *)*i )
    ExAcquireResourceExclusiveLite((PERESOURCE)i[8], 1u);
  v13 = (_QWORD *)(a2 + 144);
  qsort(*(void **)(a2 + 144), *(unsigned int *)(a2 + 152), 0x10u, TxfCompareTxfScbPtrForDirNotify);
  if ( *(_DWORD *)(a2 + 152) )
  {
    do
    {
      v14 = *(_QWORD *)(*v13 + 16LL * v6);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v14 + 64) + 136LL), 1u);
      TxfDeleteIsoNamesForTransaction(a1, v14, a2);
      ++v6;
    }
    while ( v6 < *(_DWORD *)(a2 + 152) );
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 96LL));
  for ( j = 0; j < *(_DWORD *)(a2 + 152); ++j )
    TxfDereferenceTxfScb(*(PVOID *)(*v13 + 16LL * j));
  TxfSortedArrayDeallocate(a2 + 144);
  v17 = *v11;
  v61 = *v11;
  if ( *v11 != v11 )
  {
    do
    {
      v18 = v17 - 9;
      v19 = *((_DWORD *)v17 - 17);
      *((_DWORD *)v18 + 5) = 0;
      *((_DWORD *)v18 + 1) = v19 & 0xE9F80603;
      if ( v7 )
      {
        if ( (v19 & 0x200000) == 0 && (v19 & 0x80000) != 0 )
        {
          *((_DWORD *)v18 + 1) = v19 & 0xE9F00603;
          *(_QWORD *)(v18[6] + 48LL) = 0;
        }
      }
      else
      {
        v49 = v18 + 6;
        if ( (v19 & 0x100000) != 0 )
        {
          ExFreePoolWithTag(*(PVOID *)(*v49 + 56LL), 0);
          *(_OWORD *)(*v49 + 48LL) = 0;
        }
        if ( (*((_DWORD *)v18 + 1) & 0x80000) != 0 )
          *(_QWORD *)(*v49 + 48LL) = 0;
        *((_DWORD *)v18 + 1) &= 0xFFE7FFFF;
      }
      if ( v18[8] )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 16) + 6312LL));
        while ( 1 )
        {
          v52 = (_QWORD *)v18[8];
          if ( !v52 )
            break;
          if ( *v52 )
          {
            LOBYTE(v50) = 1;
            *(_QWORD *)(*v52 + 16LL) -= v52[1];
            TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(v5 + 16), *v52, v50);
          }
          v18[8] = v52[2];
          ExFreeToLookasideListEx(&TxfFcbQuotaInfoLookasideList, v52);
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 16) + 6312LL));
      }
      v20 = (_DWORD *)v18[6];
      if ( v20 )
      {
        *v20 = 0;
        *(CLFS_LSN *)(v18[6] + 40LL) = CLFS_LSN_INVALID_EXT;
      }
      TxfDeleteSavedDeletedLinkList(v17 - 9);
      if ( (v19 & 8) != 0 )
      {
        v21 = (_QWORD *)v18[11];
        if ( !*((_WORD *)v21 + 38) )
        {
          v44 = *v21;
          if ( *(_QWORD **)(*v21 + 8LL) != v21 )
            goto LABEL_72;
          v45 = (_QWORD *)v21[1];
          if ( (_QWORD *)*v45 != v21 )
            goto LABEL_72;
          *v45 = v44;
          *(_QWORD *)(v44 + 8) = v45;
          ExFreeToLookasideListEx(&TxfFcbInfoLookasideList, v21);
        }
      }
      v22 = (void *)v18[19];
      *((_DWORD *)v18 + 37) = 0;
      if ( v22 )
      {
        ExFreePoolWithTag(v22, 0);
        v18[19] = 0;
      }
      v23 = v18[4];
      if ( v23 )
      {
        v24 = v63;
        do
        {
          v25 = *(_DWORD *)(v23 + 24);
          if ( (v25 & 0x4000) == 0 )
            *(_DWORD *)(v23 + 36) = 0;
          if ( (v25 & 2) != 0 || !v7 && !a4 && (v19 & 0x100) == 0 && *(_DWORD *)(v23 + 4) == 128 && (v25 & 1) != 0 )
            *(_DWORD *)(v23 + 24) = v25 & 0xFFFFFFF9 | 4;
          for ( k = *(_QWORD *)(v23 + 56); k; k = *(_QWORD *)(k + 32) )
          {
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFFEB);
            if ( (*(_DWORD *)(k + 8) & 2) == 0 )
              break;
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFFFD);
            _InterlockedOr((volatile signed __int32 *)(k + 8), 1u);
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFF7F);
            if ( !v7 )
              _InterlockedOr((volatile signed __int32 *)(k + 8), 0x40u);
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFBFF);
            _InterlockedOr((volatile signed __int32 *)(k + 8), 0x200u);
            *(_QWORD *)(k + 280) = *(_QWORD *)(a2 + 40);
            if ( !v7 )
            {
              ExAcquireFastMutex(*(PFAST_MUTEX *)(k + 256));
              _InterlockedOr((volatile signed __int32 *)(k + 8), 0x800u);
              ExReleaseFastMutex(*(PFAST_MUTEX *)(k + 256));
            }
            if ( !*(_WORD *)(k + 304) )
            {
              if ( v7 && _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 132), 4, 4) == 2 )
                ++*(_DWORD *)(v23 + 40);
              *(_QWORD *)(k + 64) = v24;
              v24 = k;
              *(_QWORD *)(k + 72) = *(_QWORD *)(v23 + 56);
              v27 = v60;
              if ( !v60 )
                v27 = k;
              v60 = v27;
              break;
            }
            _InterlockedDecrement((volatile signed __int32 *)(k + 4));
            _InterlockedOr((volatile signed __int32 *)(k + 8), 0x2000u);
          }
          v28 = *(_QWORD *)(v23 + 72);
          if ( v7 )
          {
            v41 = *(_QWORD *)(v23 + 112);
            if ( v41 )
            {
              if ( *(_QWORD *)(*(_QWORD *)v41 + 16LL) )
                *(_DWORD *)(v23 + 24) |= 0x1000u;
            }
          }
          v29 = *(_DWORD *)(v23 + 24);
          *(_DWORD *)(v23 + 24) = v29 & 0xFFFFF246;
          if ( (v29 & 0x100) != 0 )
            TxfDereferenceTxfScb((PVOID)v23);
          v23 = v28;
        }
        while ( v28 );
        v63 = v24;
        v17 = v61;
      }
      v30 = v18[6];
      if ( v30 )
      {
        v31 = *(_QWORD *)(v30 + 8);
        if ( v31 )
        {
          v51 = *(void **)(v30 + 16);
          *(_QWORD *)(v30 + 16) = 0;
          *(_QWORD *)(v18[6] + 8LL) = 0;
          do
          {
            v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 328) + 48LL) + 32LL);
            if ( v53 )
              *(_QWORD *)(v53 + 16) = *(_QWORD *)(a2 + 40);
            v54 = *(_QWORD *)(*(_QWORD *)(v31 + 328) + 48LL);
            v31 = *(_QWORD *)(v54 + 8);
            v55 = *(void **)(v54 + 16);
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            ObDereferenceObjectDeferDelete(v51);
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v51 = v55;
          }
          while ( v31 );
        }
      }
      *((_DWORD *)v18 + 1) &= ~1u;
      v18[3] = 0;
      v32 = (_QWORD *)*v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 || (v33 = v17 + 1, v34 = (_QWORD *)v17[1], (_QWORD *)*v34 != v17) )
LABEL_72:
        __fastfail(3u);
      *v34 = v32;
      v35 = v17;
      v32[1] = v34;
      v17 = v32;
      v61 = v32;
      *v33 = v35;
      *v35 = v35;
      TxfDereferenceTxfFcb(v18);
    }
    while ( v17 != (_QWORD *)(a2 + 192) );
  }
  *(_DWORD *)(a2 + 372) = 0;
  TxfRemoveViewIndexEntriesForTransaction(v16, *(_QWORD *)(v5 + 16) + 5864LL, a2);
  TxfRemoveViewIndexEntriesForTransaction(v36, *(_QWORD *)(v5 + 16) + 5968LL, a2);
  if ( *(_QWORD *)(a2 + 336) )
    TxfReleaseTempTxLock();
  if ( *(_QWORD *)(a2 + 344) )
    TxfReleaseTempTxLock();
  v37 = (_QWORD **)(a2 + 320);
  while ( 1 )
  {
    v38 = *v37;
    if ( *v37 == v37 )
      break;
    v42 = *v38;
    if ( *(_QWORD **)(*v38 + 8LL) != v38 )
      goto LABEL_72;
    v43 = (_QWORD *)v38[1];
    if ( (_QWORD *)*v43 != v38 )
      goto LABEL_72;
    *v43 = v42;
    *(_QWORD *)(v42 + 8) = v43;
    ExFreeToLookasideListEx(&TxfSavepointLookasideList, v38 - 4);
  }
  if ( v7 || (v39 = a4) != 0 )
  {
    if ( *(__int64 *)(a2 + 360) > 0 )
      TxfReleaseSpaceForAbortPriv(*(_QWORD *)(a2 + 208), a2);
    v39 = a4;
  }
  v40 = (_QWORD **)(a2 + 176);
  if ( *v40 != v40 )
  {
    if ( v39 )
    {
      while ( 1 )
      {
        v46 = *v40;
        if ( *v40 == v40 )
          break;
        if ( (_QWORD **)v46[1] != v40 )
          goto LABEL_72;
        v47 = (_QWORD *)*v46;
        if ( *(_QWORD **)(*v46 + 8LL) != v46 )
          goto LABEL_72;
        *v40 = v47;
        v47[1] = v40;
        v48 = (void *)v46[4];
        if ( v48 )
          TxfDereferenceTxfFcb(v48);
        ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v46);
      }
    }
    else
    {
      TxfPostDeletedLinks(v5, v40);
    }
  }
  if ( v63 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 800LL));
    *(_QWORD *)(v60 + 64) = *(_QWORD *)(v5 + 704);
    v56 = (struct _FAST_MUTEX *)(*(_QWORD *)(v5 + 24) + 800LL);
    *(_QWORD *)(v5 + 704) = v63;
    ExReleaseFastMutexUnsafe(v56);
    if ( a5 )
    {
      TxfProcessTxfVscbDereferencesForEOT(v5);
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)(v5 + 136), 0x80u);
      TxfQueueDelayedRmWorkItem(v5, v57, v58, v59);
    }
  }
}

```

## disassembly

```asm
0x1401daab8  mov     [rsp+arg_10], rbx
0x1401daabd  mov     [rsp+arg_18], r9d
0x1401daac2  mov     [rsp+arg_0], rcx
0x1401daac7  push    rbp
0x1401daac8  push    rsi
0x1401daac9  push    rdi
0x1401daaca  push    r12
0x1401daacc  push    r13
0x1401daace  push    r14
0x1401daad0  push    r15
0x1401daad2  sub     rsp, 40h
0x1401daad6  mov     r14, [rdx+0D0h]
0x1401daadd  xor     ebp, ebp
0x1401daadf  mov     [rsp+78h+arg_8], rbp
0x1401daae7  mov     eax, r9d
0x1401daaea  mov     [rsp+78h+var_58], rbp
0x1401daaef  mov     r13d, r8d
0x1401daaf2  mov     rdi, rdx
0x1401daaf5  mov     r12, rcx
0x1401daaf8  test    r8d, r8d
0x1401daafb  jnz     loc_1401DB08F
0x1401dab01  test    eax, eax
0x1401dab03  jnz     loc_1401DB08F
0x1401dab09  mov     rcx, [rdi+190h]; P
0x1401dab10  test    rcx, rcx
0x1401dab13  jnz     loc_1401DB09F
0x1401dab19  mov     r8b, 1
0x1401dab1c  mov     rdx, rdi
0x1401dab1f  mov     rcx, r12
0x1401dab22  call    TxfCloseHandlesForTransaction
0x1401dab27  mov     rcx, rdi
0x1401dab2a  call    TxfCleanupNoRenameListAtEndOfTrans
0x1401dab2f  mov     rcx, [r14+18h]
0x1401dab33  add     rcx, 60h ; '`'; FastMutex
0x1401dab37  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401dab3e  nop     dword ptr [rax+rax+00h]
0x1401dab43  lea     r15, [rdi+0C0h]
0x1401dab4a  mov     rbx, [r15]
0x1401dab4d  jmp     short loc_1401DAB64
0x1401dab4f  mov     rcx, [rbx+40h]; Resource
0x1401dab53  mov     dl, 1; Wait
0x1401dab55  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401dab5c  nop     dword ptr [rax+rax+00h]
0x1401dab61  mov     rbx, [rbx]
0x1401dab64  cmp     rbx, r15
0x1401dab67  jnz     short loc_1401DAB4F
0x1401dab69  mov     edx, [rdi+98h]; NumOfElements
0x1401dab6f  lea     rsi, [rdi+90h]
0x1401dab76  mov     rcx, [rsi]; Base
0x1401dab79  lea     r9, TxfCompareTxfScbPtrForDirNotify; PtFuncCompare
0x1401dab80  mov     r8d, 10h; SizeOfElements
0x1401dab86  call    cs:__imp_qsort
0x1401dab8d  nop     dword ptr [rax+rax+00h]
0x1401dab92  cmp     [rdi+98h], ebp
0x1401dab98  jbe     short loc_1401DABD7
0x1401dab9a  mov     rax, [rsi]
0x1401dab9d  mov     dl, 1; Wait
0x1401dab9f  mov     ecx, ebp
0x1401daba1  add     rcx, rcx
0x1401daba4  mov     rbx, [rax+rcx*8]
0x1401daba8  mov     rcx, [rbx+40h]
0x1401dabac  mov     rcx, [rcx+88h]; Resource
0x1401dabb3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401dabba  nop     dword ptr [rax+rax+00h]
0x1401dabbf  mov     r8, rdi
0x1401dabc2  mov     rdx, rbx
0x1401dabc5  mov     rcx, r12
0x1401dabc8  call    TxfDeleteIsoNamesForTransaction
0x1401dabcd  inc     ebp
0x1401dabcf  cmp     ebp, [rdi+98h]
0x1401dabd5  jb      short loc_1401DAB9A
0x1401dabd7  mov     rcx, [r14+18h]
0x1401dabdb  add     rcx, 60h ; '`'; FastMutex
0x1401dabdf  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401dabe6  nop     dword ptr [rax+rax+00h]
0x1401dabeb  xor     ebp, ebp
0x1401dabed  mov     ebx, ebp
0x1401dabef  cmp     [rdi+98h], ebp
0x1401dabf5  jbe     short loc_1401DAC14
0x1401dabf7  mov     rcx, [rsi]
0x1401dabfa  mov     dl, 1
0x1401dabfc  mov     eax, ebx
0x1401dabfe  add     rax, rax
0x1401dac01  mov     rcx, [rcx+rax*8]
0x1401dac05  call    TxfDereferenceTxfScb
0x1401dac0a  inc     ebx
0x1401dac0c  cmp     ebx, [rdi+98h]
0x1401dac12  jb      short loc_1401DABF7
0x1401dac14  mov     rcx, rsi
0x1401dac17  call    TxfSortedArrayDeallocate
0x1401dac1c  mov     r12, [r15]
0x1401dac1f  mov     [rsp+78h+var_48], r12
0x1401dac24  cmp     r12, r15
0x1401dac27  jz      loc_1401DAE51
0x1401dac2d  lea     rsi, [r12-48h]
0x1401dac32  mov     r15d, [rsi+4]
0x1401dac36  mov     eax, r15d
0x1401dac39  and     eax, 0E9F80603h
0x1401dac3e  mov     [rsp+78h+var_50], rsi
0x1401dac43  mov     [rsi+14h], ebp
0x1401dac46  mov     [rsi+4], eax
0x1401dac49  test    r13d, r13d
0x1401dac4c  jz      loc_1401DB0C7
0x1401dac52  bt      r15d, 15h
0x1401dac57  jnb     loc_1401DB0F9
0x1401dac5d  cmp     [rsi+40h], rbp
0x1401dac61  jnz     loc_1401DB11E
0x1401dac67  mov     rax, [rsi+30h]
0x1401dac6b  test    rax, rax
0x1401dac6e  jnz     loc_1401DB13B
0x1401dac74  mov     rcx, rsi
0x1401dac77  call    TxfDeleteSavedDeletedLinkList
0x1401dac7c  test    r15b, 8
0x1401dac80  jz      short loc_1401DAC90
0x1401dac82  mov     rdx, [rsi+58h]; Entry
0x1401dac86  cmp     [rdx+4Ch], bp
0x1401dac8a  jz      loc_1401DB00C
0x1401dac90  mov     rcx, [rsi+98h]; P
0x1401dac97  mov     [rsi+94h], ebp
0x1401dac9d  test    rcx, rcx
0x1401daca0  jz      short loc_1401DACB7
0x1401daca2  xor     edx, edx; Tag
0x1401daca4  call    cs:__imp_ExFreePoolWithTag
0x1401dacab  nop     dword ptr [rax+rax+00h]
0x1401dacb0  mov     [rsi+98h], rbp
0x1401dacb7  mov     rbp, [rsi+20h]
0x1401dacbb  xor     ecx, ecx
0x1401dacbd  test    rbp, rbp
0x1401dacc0  jz      loc_1401DADDB
0x1401dacc6  mov     esi, [rsp+78h+arg_18]
0x1401daccd  mov     r12, [rsp+78h+arg_8]
0x1401dacd5  mov     eax, [rbp+18h]
0x1401dacd8  bt      eax, 0Eh
0x1401dacdc  jb      short loc_1401DACE1
0x1401dacde  mov     [rbp+24h], ecx
0x1401dace1  test    al, 2
0x1401dace3  jnz     loc_1401DAF2C
0x1401dace9  test    r13d, r13d
0x1401dacec  jz      loc_1401DAF04
0x1401dacf2  mov     rbx, [rbp+38h]
0x1401dacf6  test    rbx, rbx
0x1401dacf9  jz      loc_1401DAD99
0x1401dacff  lock and dword ptr [rbx+8], 0FFFFFFEBh
0x1401dad04  mov     eax, [rbx+8]
0x1401dad07  test    al, 2
0x1401dad09  jz      loc_1401DAD99
0x1401dad0f  lock and dword ptr [rbx+8], 0FFFFFFFDh
0x1401dad14  lock or dword ptr [rbx+8], 1
0x1401dad19  lock and dword ptr [rbx+8], 0FFFFFF7Fh
0x1401dad21  test    r13d, r13d
0x1401dad24  jnz     short loc_1401DAD2B
0x1401dad26  lock or dword ptr [rbx+8], 40h
0x1401dad2b  lock and dword ptr [rbx+8], 0FFFFFBFFh
0x1401dad33  lock or dword ptr [rbx+8], 200h
0x1401dad3b  mov     rax, [rdi+28h]
0x1401dad3f  mov     [rbx+118h], rax
0x1401dad46  test    r13d, r13d
0x1401dad49  jz      loc_1401DAF5E
0x1401dad4f  cmp     [rbx+130h], cx
0x1401dad56  jnz     loc_1401DAF93
0x1401dad5c  test    r13d, r13d
0x1401dad5f  jz      short loc_1401DAD79
0x1401dad61  mov     edx, 4
0x1401dad66  mov     eax, edx
0x1401dad68  lock cmpxchg [r14+84h], edx
0x1401dad71  cmp     eax, 2
0x1401dad74  jnz     short loc_1401DAD79
0x1401dad76  inc     dword ptr [rbp+28h]
0x1401dad79  mov     [rbx+40h], r12
0x1401dad7d  mov     r12, rbx
0x1401dad80  mov     rax, [rbp+38h]
0x1401dad84  mov     [rbx+48h], rax
0x1401dad88  mov     rax, [rsp+78h+var_58]
0x1401dad8d  test    rax, rax
0x1401dad90  cmovz   rax, rbx
0x1401dad94  mov     [rsp+78h+var_58], rax
0x1401dad99  mov     rbx, [rbp+48h]
0x1401dad9d  test    r13d, r13d
0x1401dada0  jnz     loc_1401DAF3A
0x1401dada6  mov     edx, [rbp+18h]
0x1401dada9  mov     eax, edx
0x1401dadab  and     eax, 0FFFFF246h
0x1401dadb0  mov     [rbp+18h], eax
0x1401dadb3  bt      edx, 8
0x1401dadb7  jb      loc_1401DB151
0x1401dadbd  mov     rbp, rbx
0x1401dadc0  test    rbx, rbx
0x1401dadc3  jnz     loc_1401DACD5
0x1401dadc9  mov     rsi, [rsp+78h+var_50]
0x1401dadce  mov     [rsp+78h+arg_8], r12
0x1401dadd6  mov     r12, [rsp+78h+var_48]
0x1401daddb  mov     rax, [rsi+30h]
0x1401daddf  xor     ebp, ebp
0x1401dade1  test    rax, rax
0x1401dade4  jz      short loc_1401DADF8
0x1401dade6  mov     rbp, [rax+8]
0x1401dadea  xor     r8d, r8d
0x1401daded  test    rbp, rbp
0x1401dadf0  jnz     loc_1401DB162
0x1401dadf6  xor     ebp, ebp
0x1401dadf8  and     dword ptr [rsi+4], 0FFFFFFFEh
0x1401dadfc  mov     [rsi+18h], rbp
0x1401dae00  mov     rcx, [r12]
0x1401dae04  cmp     [rcx+8], r12
0x1401dae08  jnz     loc_1401DAFA8
0x1401dae0e  lea     r8, [r12+8]
0x1401dae13  mov     rdx, [r8]
0x1401dae16  cmp     [rdx], r12
0x1401dae19  jnz     loc_1401DAFA8
0x1401dae1f  mov     [rdx], rcx
0x1401dae22  mov     rax, r12
0x1401dae25  mov     [rcx+8], rdx
0x1401dae29  mov     r12, rcx
0x1401dae2c  mov     [rsp+78h+var_48], rcx
0x1401dae31  mov     dl, 1
0x1401dae33  mov     rcx, rsi
0x1401dae36  mov     [r8], rax
0x1401dae39  mov     [rax], rax
0x1401dae3c  call    TxfDereferenceTxfFcb
0x1401dae41  lea     rax, [rdi+0C0h]
0x1401dae48  cmp     r12, rax
0x1401dae4b  jnz     loc_1401DAC2D
0x1401dae51  mov     [rdi+174h], ebp
0x1401dae57  mov     r8, rdi
0x1401dae5a  mov     rdx, [r14+10h]
0x1401dae5e  add     rdx, 16E8h
0x1401dae65  call    TxfRemoveViewIndexEntriesForTransaction
0x1401dae6a  mov     rdx, [r14+10h]
0x1401dae6e  mov     r8, rdi
0x1401dae71  add     rdx, 1750h
0x1401dae78  call    TxfRemoveViewIndexEntriesForTransaction
0x1401dae7d  lea     rcx, [rdi+150h]
0x1401dae84  cmp     [rcx], rbp
0x1401dae87  jnz     loc_1401DB17F
0x1401dae8d  lea     rcx, [rdi+158h]
0x1401dae94  cmp     [rcx], rbp
0x1401dae97  jnz     loc_1401DB189
0x1401dae9d  lea     rbx, [rdi+140h]
0x1401daea4  mov     rdx, [rbx]
0x1401daea7  cmp     rdx, rbx
0x1401daeaa  jnz     loc_1401DAFAF
0x1401daeb0  test    r13d, r13d
0x1401daeb3  jnz     loc_1401DAFE4
0x1401daeb9  mov     r8d, [rsp+78h+arg_18]
0x1401daec1  test    r8d, r8d
0x1401daec4  jnz     loc_1401DAFE4
0x1401daeca  add     rdi, 0B0h
0x1401daed1  cmp     [rdi], rdi
0x1401daed4  jnz     loc_1401DB193
0x1401daeda  mov     rbx, [rsp+78h+arg_8]
0x1401daee2  test    rbx, rbx
0x1401daee5  jnz     loc_1402CD619
0x1401daeeb  mov     rbx, [rsp+78h+arg_10]
0x1401daef3  add     rsp, 40h
0x1401daef7  pop     r15
0x1401daef9  pop     r14
0x1401daefb  pop     r13
0x1401daefd  pop     r12
0x1401daeff  pop     rdi
0x1401daf00  pop     rsi
0x1401daf01  pop     rbp
0x1401daf02  retn
0x1401daf04  test    esi, esi
0x1401daf06  jnz     loc_1401DACF2
0x1401daf0c  bt      r15d, 8
0x1401daf11  jb      loc_1401DACF2
0x1401daf17  cmp     dword ptr [rbp+4], 80h
0x1401daf1e  jnz     loc_1401DACF2
0x1401daf24  test    al, 1
0x1401daf26  jz      loc_1401DACF2
0x1401daf2c  and     eax, 0FFFFFFFDh
0x1401daf2f  or      eax, 4
0x1401daf32  mov     [rbp+18h], eax
0x1401daf35  jmp     loc_1401DACF2
0x1401daf3a  mov     rax, [rbp+70h]
0x1401daf3e  test    rax, rax
0x1401daf41  jz      loc_1401DADA6
0x1401daf47  mov     rax, [rax]
0x1401daf4a  cmp     [rax+10h], rcx
0x1401daf4e  jz      loc_1401DADA6
0x1401daf54  bts     dword ptr [rbp+18h], 0Ch
0x1401daf59  jmp     loc_1401DADA6
0x1401daf5e  mov     rcx, [rbx+100h]; FastMutex
0x1401daf65  call    cs:__imp_ExAcquireFastMutex
0x1401daf6c  nop     dword ptr [rax+rax+00h]
0x1401daf71  lock or dword ptr [rbx+8], 800h
0x1401daf79  mov     rcx, [rbx+100h]; FastMutex
0x1401daf80  call    cs:__imp_ExReleaseFastMutex
0x1401daf87  nop     dword ptr [rax+rax+00h]
0x1401daf8c  xor     ecx, ecx
0x1401daf8e  jmp     loc_1401DAD4F
0x1401daf93  lock dec dword ptr [rbx+4]
0x1401daf97  lock or dword ptr [rbx+8], 2000h
0x1401daf9f  mov     rbx, [rbx+20h]
0x1401dafa3  jmp     loc_1401DACF6
0x1401dafa8  mov     ecx, 3
0x1401dafad  int     29h; Win8: RtlFailFast(ecx)
0x1401dafaf  mov     rax, [rdx]
0x1401dafb2  cmp     [rax+8], rdx
0x1401dafb6  jnz     short loc_1401DAFA8
  ... truncated ...
```
