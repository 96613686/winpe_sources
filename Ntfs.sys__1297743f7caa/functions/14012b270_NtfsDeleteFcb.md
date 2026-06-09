# NtfsDeleteFcb

- ea: `0x14012b270`
- end: `0x14012bab9`
- name: `NtfsDeleteFcb`
- size: `2121`
- prototype: ``
- caller_count: `11`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140029d80`
- `0x14010802c`
- `0x14012a140`
- `0x140195b64`
- `0x1401961bc`
- `0x1401ff4b0`
- `0x1402562e4`
- `0x1402564ec`
- `0x1402565fc`
- `0x140256690`
- `0x140268348`

## callees

- `0x140021910`
- `0x140025b70`
- `0x140025df0`
- `0x140029140`
- `0x1400b84ec`
- `0x14012a000`
- `0x14012b270`
- `0x14012bb48`
- `0x140140b00`
- `0x140140fac`
- `0x140196e80`
- `0x14025125c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b2d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b2d7`
- `ntoskrnl!CcUnmapFileOffsetFromSystemCache` at `0x14012b7ec`
- `ntoskrnl!CcUnmapFileOffsetFromSystemCache` at `0x14012b7ec`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b47b`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b762`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b47b`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b762`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x14012b6a9`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x14012b6a9`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14012b30c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14012b30c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402c767b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402c767b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b346`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b346`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b49a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b6e0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b804`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012ba47`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b49a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b6e0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b804`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012ba47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b5fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b873`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b8b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b9be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ba12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b5fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b873`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b8b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b9be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ba12`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012b859`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012b859`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012b88d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c76ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012b88d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c76ae`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b54d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b9da`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b54d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b9da`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b5c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b7b5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b965`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b5c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b7b5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b965`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1402c7660`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1402c7660`

## pseudocode

```c
void __fastcall NtfsDeleteFcb(__int64 a1, _QWORD *a2, unsigned __int64 *a3)
{
  __int64 v5; // rbp
  __int64 v6; // rcx
  char v7; // r12
  __int64 v8; // r13
  unsigned __int64 *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rdx
  _QWORD *v18; // r14
  __int64 v19; // rax
  __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rcx
  void *v23; // rcx
  char *v24; // rdi
  struct _LOOKASIDE_LIST_EX *v25; // rcx
  char *v26; // r8
  _QWORD *v27; // r9
  char *i; // rcx
  __int64 v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  unsigned int *v33; // rbp
  __int64 v34; // r14
  __int64 v35; // rcx
  __int16 *v36; // r8
  __int16 v37; // cx
  volatile signed __int32 *v38; // rcx
  signed __int32 v39; // eax
  bool v40; // cc
  signed __int32 v41; // eax
  _QWORD *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  _BYTE *v47; // rcx
  _DWORD *v48; // rcx
  int v49; // eax
  void *v50; // rdx
  __int64 v51; // rcx
  _DWORD *v52; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  void *v56; // rcx
  int v57; // ebp
  __int64 v58; // r15
  __int64 v59; // rcx
  _QWORD *v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  _QWORD *v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rcx
  struct _ERESOURCE *v70; // rcx
  unsigned int v71; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v72; // [rsp+78h] [rbp+10h] BYREF
  __int64 v73; // [rsp+80h] [rbp+18h]
  __int64 v74; // [rsp+88h] [rbp+20h]

  v74 = *(_QWORD *)(a1 + 16);
  if ( (v74 & 0x20) == 0 )
  {
    v5 = *a2;
    v6 = *a2;
LABEL_3:
    v7 = 0;
    goto LABEL_4;
  }
  v6 = *a2;
  v5 = *a2;
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x2000000) == 0 )
    goto LABEL_3;
  v7 = 1;
LABEL_4:
  v8 = *(_QWORD *)(v6 + 96);
  v9 = &v72;
  LOBYTE(v72) = 0;
  LOBYTE(v71) = 0;
  if ( a3 )
    v9 = a3;
  v73 = v8;
  if ( !*(_BYTE *)v9 )
  {
    ExAcquirePushLockExclusiveEx(v8 + 656, 0);
    *(_BYTE *)v9 = 1;
    v5 = *a2;
  }
  if ( !v7 && (*(_DWORD *)(v5 + 4) & 0x40) != 0 )
  {
    v10 = *(_QWORD *)(v5 + 96);
    RtlAvlRemoveNode(v10 + 1344, *(_QWORD *)(v5 + 104) + 256LL);
    --*(_DWORD *)(v10 + 1352);
    *(_DWORD *)(v5 + 4) &= ~0x40u;
    LOBYTE(v71) = 1;
  }
  v11 = *(_QWORD *)(*a2 + 328LL);
  if ( v11 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v11 + 136), 1u);
    v56 = *(void **)(v11 + 152);
    if ( v56 )
    {
      ExFreePoolWithTag(v56, 0);
      *(_QWORD *)(v11 + 152) = 0;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v11 + 136));
  }
  ExReleasePushLockEx(v8 + 656, 0);
  *(_BYTE *)v9 = 0;
  NtfsFreeSnapshotsForFcb(a1, *a2);
  v12 = *a2;
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x800000) != 0 )
    TxfSearchingForSystemRoot = 1;
  if ( !v7 )
  {
    v13 = v12 + 80;
    v14 = *(_QWORD *)(v12 + 80);
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 8) != v13 )
        goto LABEL_94;
      v15 = *(_QWORD **)(v13 + 8);
      if ( *v15 != v13 )
        goto LABEL_94;
      *v15 = v14;
      *(_QWORD *)(v14 + 8) = v15;
      *(_QWORD *)(*a2 + 80LL) = 0;
    }
  }
  v16 = a1;
  v17 = 1805;
  do
  {
    v18 = *(_QWORD **)(v16 + 40);
    if ( v18 )
    {
      v57 = *(unsigned __int16 *)(v16 + 34);
      v58 = *a2;
      if ( v57 == 1 )
        v18 = (_QWORD *)(v16 + 40);
      do
      {
        v59 = *v18;
        if ( *v18 && v59 == v58 )
        {
          if ( *(_WORD *)v59 == 1805 )
          {
            NtfsReleaseQuotaControl(v16, *v18);
          }
          else
          {
            if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v59 + 104) + 64LL))
              && ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v18 + 104LL) + 64LL)) == 1 )
            {
              NtfsFreeSnapshotsForFcb(v16, *v18);
            }
            v69 = *v18;
            if ( *(_WORD *)*v18 == 1794 )
              v70 = (struct _ERESOURCE *)(*(_QWORD *)(v69 + 104) + 64LL);
            else
              v70 = *(struct _ERESOURCE **)(v69 + 8);
            ExReleaseResourceLite(v70);
          }
          *v18 = 0;
          v17 = 1805;
          if ( *(_WORD *)(v16 + 34) == 1 )
            *(_WORD *)(v16 + 34) = 0;
        }
        ++v18;
        --v57;
      }
      while ( v57 );
    }
    v19 = *(_QWORD *)(v16 + 144);
    if ( v16 == v19 )
      break;
    v16 = *(_QWORD *)(v16 + 144);
  }
  while ( v19 );
  v20 = v73;
  if ( *(int *)(*a2 + 176LL) < 0 )
    *(_DWORD *)(a1 + 436) &= ~0x8000u;
  if ( !v7 )
  {
    if ( *(_QWORD *)(a1 + 48) == *a2 )
      *(_QWORD *)(a1 + 48) = 0;
    if ( *(_QWORD *)(a1 + 56) == *a2 )
      *(_QWORD *)(a1 + 56) = 0;
    v21 = *(_QWORD *)(a1 + 144);
    if ( v21 )
    {
      if ( *(_QWORD *)(v21 + 48) == *a2 )
        *(_QWORD *)(v21 + 48) = 0;
      v22 = *(_QWORD *)(a1 + 144);
      if ( *(_QWORD *)(v22 + 56) == *a2 )
        *(_QWORD *)(v22 + 56) = 0;
    }
    if ( **(_WORD **)(*a2 + 104LL) == 1861 )
    {
      v23 = *(void **)(*a2 + 112LL);
      if ( v23 )
      {
        NtfsFreeEresource(v23);
        *(_QWORD *)(*a2 + 112LL) = 0;
      }
    }
    v24 = *(char **)(*a2 + 104LL);
    ExReinitializeResourceLite((PERESOURCE)(v24 + 64));
    if ( *(_WORD *)v24 == 1861 )
    {
      v25 = &NtfsFcbNonpagedIndexLookasideList;
    }
    else
    {
      ExReinitializeResourceLite((PERESOURCE)(v24 + 280));
      v25 = &NtfsFcbNonpagedDataLookasideList;
    }
    ExFreeToLookasideListEx(v25, v24);
    *(_QWORD *)(*a2 + 104LL) = 0;
  }
  if ( *(_QWORD *)(*a2 + 296LL) )
  {
    v26 = (char *)(a1 + 232);
    v27 = 0;
    for ( i = (char *)(a1 + 232); *((_QWORD *)i + 1) != *a2; i = *(char **)i )
    {
      v17 = *(_QWORD *)i;
      if ( !*(_QWORD *)i )
        goto LABEL_44;
      v27 = i;
    }
    if ( i == v26 )
    {
      *(_OWORD *)(i + 8) = 0;
      *(_OWORD *)(i + 24) = 0;
    }
    else
    {
      *v27 = *(_QWORD *)i;
      ExFreePoolWithTag(i, 0);
    }
LABEL_44:
    if ( !*(_QWORD *)(*(_QWORD *)(*a2 + 296LL) + 32LL) )
      goto LABEL_45;
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*a2 + 96LL) + 1992LL));
    v65 = *(_QWORD *)(*a2 + 296LL);
    v66 = *(_QWORD *)(v65 + 32);
    v67 = v65 + 32;
    if ( !v66 )
      goto LABEL_115;
    if ( *(_QWORD *)(v66 + 8) != v67 )
      goto LABEL_94;
    v60 = *(_QWORD **)(v67 + 8);
    if ( *v60 != v67 )
      goto LABEL_94;
    *v60 = v66;
    *(_QWORD *)(v66 + 8) = v60;
    v61 = *(_QWORD *)(*a2 + 296LL);
    v62 = *(_QWORD *)(v61 + 16);
    v63 = v61 + 16;
    if ( !v62 )
    {
LABEL_115:
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*a2 + 96LL) + 1992LL));
LABEL_45:
      v29 = *a2;
      --*(_DWORD *)(*(_QWORD *)(*a2 + 296LL) + 4LL);
      v30 = *(_QWORD *)(v29 + 296);
      if ( !*(_DWORD *)(v30 + 4) )
      {
        v51 = *(_QWORD *)(v30 + 48);
        if ( v51 )
        {
          if ( (*(_DWORD *)(v51 + 144) & 1) != 0 )
            FsLibRangeTrackUninitialize(v51, v17, v26, v27);
          v52 = *(_DWORD **)(*(_QWORD *)(v29 + 296) + 48LL);
          if ( (v52[36] & 8) == 0 )
            ExFreePoolWithTag(v52, 0);
        }
        ExFreePoolWithTag(*(PVOID *)(v29 + 296), 0);
        *(_QWORD *)(v29 + 296) = 0;
      }
      *(_QWORD *)(*a2 + 296LL) = 0;
      goto LABEL_47;
    }
    if ( *(_QWORD *)(v62 + 8) == v63 )
    {
      v64 = *(_QWORD **)(v63 + 8);
      if ( *v64 == v63 )
      {
        *v64 = v62;
        *(_QWORD *)(v62 + 8) = v64;
        *(_QWORD *)(*(_QWORD *)(*a2 + 296LL) + 16LL) = 0;
        goto LABEL_115;
      }
    }
LABEL_94:
    __fastfail(3u);
  }
LABEL_47:
  v31 = *a2;
  v32 = *(void **)(*a2 + 328LL);
  if ( v32 )
  {
    TxfDereferenceTxfFcb(v32);
    *(_QWORD *)(*a2 + 328LL) = 0;
    v31 = *a2;
  }
  if ( (_BYTE)v71 )
  {
    v71 = 0;
    v33 = (unsigned int *)(v31 + 8);
    LODWORD(v72) = 0;
    ExAcquireFastMutex((PFAST_MUTEX)(v20 + 7400));
    NtfsGetArrayAndCounterIdx(v20 + 7400, v33, &v71, &v72);
    if ( v71 != -1
      && (_DWORD)v72 != -1
      && (v34 = *(_QWORD *)(v20 + 7480) + 16LL * v71, (v35 = *(_QWORD *)(v34 + 8)) != 0)
      && (v36 = (__int16 *)(v35 + 2LL * (unsigned int)v72), (v37 = *v36) != 0)
      && (*v36 = v37 - 1, v37 == 1) )
    {
      if ( (v74 & 0x8000) != 0 )
      {
        v72 = (unsigned __int64)*v33 << *(_BYTE *)(v20 + 492);
        if ( (*(_WORD *)v34)-- == 1 )
        {
          ExFreeToLookasideListEx(&NtfsMftViewReferenceLookasideList, *(PVOID *)(v34 + 8));
          *(_QWORD *)(v34 + 8) = 0;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(v20 + 7400));
        v54 = *(_QWORD *)(v20 + 48);
        if ( v54 )
        {
          v55 = *(_QWORD *)(v54 + 280);
          if ( v55 )
            CcUnmapFileOffsetFromSystemCache(v55, &v72, 0x40000, 0);
        }
      }
      else
      {
        --*(_WORD *)v34;
        NtfsMftViewAddToDelayedUnmap(v20, v33);
      }
    }
    else
    {
      ExReleaseFastMutex((PFAST_MUTEX)(v20 + 7400));
    }
  }
  v38 = *(volatile signed __int32 **)(*a2 + 208LL);
  if ( v38 )
  {
    *(_QWORD *)(*a2 + 208LL) = 0;
    v39 = _InterlockedExchangeAdd(v38, 0xFFFFFFFF);
    v40 = v39 <= 1;
    v41 = v39 - 1;
    if ( v40 )
    {
      if ( v41 )
        __fastfail(0xEu);
      ExFreePoolWithTag((PVOID)v38, 0);
    }
  }
  v42 = (_QWORD *)(*a2 + 120LL);
  if ( *v42 )
    NtfsDereferenceQuotaControlBlock(v20, v42, 0);
  v43 = NtfsAddStructToRollbackList(a1, 1827, *a2, 0);
  if ( v43 )
    NtfsProcessRollbackStruct(a1, v43, 16);
  v44 = *(_QWORD *)(a1 + 144);
  if ( a1 != v44 )
  {
    v68 = NtfsAddStructToRollbackList(v44, 1827, *a2, 0);
    if ( v68 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v68, 16);
  }
  v45 = *a2;
  v46 = *(_QWORD *)(*a2 + 320LL);
  if ( v46 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v46 + 36));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(*a2 + 320LL) + 64LL), 0xFFFFFFFF) == 1 )
      TxfDeleteTxfRmcb(*(char **)(*a2 + 320LL));
    *(_QWORD *)(*a2 + 320LL) = 0;
    v45 = *a2;
  }
  if ( !v7 )
  {
    v47 = *(_BYTE **)(v45 + 304);
    if ( v47 )
      *v47 = 1;
  }
  if ( (*(_DWORD *)(*a2 + 4LL) & 4) == 0 )
    FsRtlTeardownPerFileContexts((PVOID *)(*a2 + 336LL));
  v48 = (_DWORD *)*a2;
  v49 = *(_DWORD *)(*a2 + 4LL);
  if ( v7 )
  {
    v48[1] = v49 | 0x4000000;
  }
  else if ( (v49 & 2) != 0 )
  {
    ExFreePoolWithTag(v48, 0);
  }
  else
  {
    v50 = (void *)*a2;
    if ( (v49 & 0x400) != 0 )
      ExFreeToLookasideListEx(&NtfsFcbIndexLookasideList, v50);
    else
      ExFreeToLookasideListEx(&NtfsFcbDataLookasideList, v50);
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x14012b270  push    rbx
0x14012b272  push    rbp
0x14012b273  push    rsi
0x14012b274  push    rdi
0x14012b275  push    r12
0x14012b277  push    r13
0x14012b279  push    r14
0x14012b27b  push    r15
0x14012b27d  sub     rsp, 28h
0x14012b281  mov     r15, [rcx+10h]
0x14012b285  mov     rbx, rdx
0x14012b288  mov     [rsp+68h+arg_18], r15
0x14012b290  mov     rsi, rcx
0x14012b293  test    r15b, 20h
0x14012b297  jnz     loc_14012B835
0x14012b29d  mov     rbp, [rdx]
0x14012b2a0  mov     rcx, rbp
0x14012b2a3  xor     r12b, r12b
0x14012b2a6  mov     r13, [rcx+60h]
0x14012b2aa  lea     r14, [rsp+68h+arg_8]
0x14012b2af  test    r8, r8
0x14012b2b2  mov     byte ptr [rsp+68h+arg_8], 0
0x14012b2b7  mov     byte ptr [rsp+68h+arg_0], 0
0x14012b2bc  cmovnz  r14, r8
0x14012b2c0  mov     [rsp+68h+arg_10], r13
0x14012b2c8  cmp     byte ptr [r14], 0
0x14012b2cc  jnz     short loc_14012B2EA
0x14012b2ce  lea     rcx, [r13+290h]
0x14012b2d5  xor     edx, edx
0x14012b2d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012b2de  nop     dword ptr [rax+rax+00h]
0x14012b2e3  mov     byte ptr [r14], 1
0x14012b2e7  mov     rbp, [rbx]
0x14012b2ea  test    r12b, r12b
0x14012b2ed  jnz     short loc_14012B327
0x14012b2ef  mov     eax, [rbp+4]
0x14012b2f2  test    al, 40h
0x14012b2f4  jz      short loc_14012B327
0x14012b2f6  mov     rdi, [rbp+60h]
0x14012b2fa  mov     rdx, [rbp+68h]
0x14012b2fe  add     rdx, 100h
0x14012b305  lea     rcx, [rdi+540h]
0x14012b30c  call    cs:__imp_RtlAvlRemoveNode
0x14012b313  nop     dword ptr [rax+rax+00h]
0x14012b318  dec     dword ptr [rdi+548h]
0x14012b31e  and     dword ptr [rbp+4], 0FFFFFFBFh
0x14012b322  mov     byte ptr [rsp+68h+arg_0], 1
0x14012b327  mov     rax, [rbx]
0x14012b32a  xor     r15d, r15d
0x14012b32d  mov     rdi, [rax+148h]
0x14012b334  test    rdi, rdi
0x14012b337  jnz     loc_14012B850
0x14012b33d  lea     rcx, [r13+290h]
0x14012b344  xor     edx, edx
0x14012b346  call    cs:__imp_ExReleasePushLockEx
0x14012b34d  nop     dword ptr [rax+rax+00h]
0x14012b352  mov     [r14], r15b
0x14012b355  mov     rcx, rsi
0x14012b358  mov     rdx, [rbx]
0x14012b35b  call    NtfsFreeSnapshotsForFcb
0x14012b360  mov     rcx, [rbx]
0x14012b363  test    dword ptr [rcx+4], 800000h
0x14012b36a  jz      short loc_14012B373
0x14012b36c  mov     cs:TxfSearchingForSystemRoot, 1
0x14012b373  test    r12b, r12b
0x14012b376  jnz     short loc_14012B3AA
0x14012b378  lea     rax, [rcx+50h]
0x14012b37c  mov     rcx, [rcx+50h]
0x14012b380  test    rcx, rcx
0x14012b383  jz      short loc_14012B3AA
0x14012b385  cmp     [rcx+8], rax
0x14012b389  jnz     loc_14012B82E
0x14012b38f  mov     rdx, [rax+8]
0x14012b393  cmp     [rdx], rax
0x14012b396  jnz     loc_14012B82E
0x14012b39c  mov     [rdx], rcx
0x14012b39f  mov     [rcx+8], rdx
0x14012b3a3  mov     rax, [rbx]
0x14012b3a6  mov     [rax+50h], r15
0x14012b3aa  mov     rdi, rsi
0x14012b3ad  mov     edx, 70Dh
0x14012b3b2  mov     r13d, 702h
0x14012b3b8  mov     r14, [rdi+28h]
0x14012b3bc  lea     rax, [rdi+28h]
0x14012b3c0  test    r14, r14
0x14012b3c3  jnz     loc_14012B8CE
0x14012b3c9  mov     rax, [rdi+90h]
0x14012b3d0  cmp     rdi, rax
0x14012b3d3  jnz     loc_14012B89E
0x14012b3d9  mov     rax, [rbx]
0x14012b3dc  mov     r13, [rsp+68h+arg_10]
0x14012b3e4  cmp     dword ptr [rax+0B0h], 0
0x14012b3eb  jge     short loc_14012B3F7
0x14012b3ed  and     dword ptr [rsi+1B4h], 0FFFF7FFFh
0x14012b3f7  xor     r15d, r15d
0x14012b3fa  test    r12b, r12b
0x14012b3fd  jnz     loc_14012B4AD
0x14012b403  mov     rax, [rbx]
0x14012b406  cmp     [rsi+30h], rax
0x14012b40a  jnz     short loc_14012B410
0x14012b40c  mov     [rsi+30h], r15
0x14012b410  mov     rax, [rbx]
0x14012b413  cmp     [rsi+38h], rax
0x14012b417  jnz     short loc_14012B41D
0x14012b419  mov     [rsi+38h], r15
0x14012b41d  mov     rcx, [rsi+90h]
0x14012b424  test    rcx, rcx
0x14012b427  jz      short loc_14012B44A
0x14012b429  mov     rax, [rbx]
0x14012b42c  cmp     [rcx+30h], rax
0x14012b430  jnz     short loc_14012B436
0x14012b432  mov     [rcx+30h], r15
0x14012b436  mov     rcx, [rsi+90h]
0x14012b43d  mov     rax, [rbx]
0x14012b440  cmp     [rcx+38h], rax
0x14012b444  jz      loc_14012B999
0x14012b44a  mov     rcx, [rbx]
0x14012b44d  mov     ebp, 745h
0x14012b452  mov     rax, [rcx+68h]
0x14012b456  cmp     [rax], bp
0x14012b459  jnz     short loc_14012B470
0x14012b45b  mov     rcx, [rcx+70h]; P
0x14012b45f  test    rcx, rcx
0x14012b462  jz      short loc_14012B470
0x14012b464  call    NtfsFreeEresource
0x14012b469  mov     rax, [rbx]
0x14012b46c  mov     [rax+70h], r15
0x14012b470  mov     rax, [rbx]
0x14012b473  mov     rdi, [rax+68h]
0x14012b477  lea     rcx, [rdi+40h]; Resource
0x14012b47b  call    cs:__imp_ExReinitializeResourceLite
0x14012b482  nop     dword ptr [rax+rax+00h]
0x14012b487  cmp     [rdi], bp
0x14012b48a  jnz     loc_14012B75B
0x14012b490  lea     rcx, NtfsFcbNonpagedIndexLookasideList; Lookaside
0x14012b497  mov     rdx, rdi; Entry
0x14012b49a  call    cs:__imp_ExFreeToLookasideListEx
0x14012b4a1  nop     dword ptr [rax+rax+00h]
0x14012b4a6  mov     rax, [rbx]
0x14012b4a9  mov     [rax+68h], r15
0x14012b4ad  mov     rax, [rbx]
0x14012b4b0  cmp     qword ptr [rax+128h], 0
0x14012b4b8  jz      short loc_14012B51A
0x14012b4ba  lea     r8, [rsi+0E8h]
0x14012b4c1  mov     r9, r15
0x14012b4c4  mov     rcx, r8; P
0x14012b4c7  cmp     [rcx+8], rax
0x14012b4cb  jz      loc_14012B9AD
0x14012b4d1  mov     rdx, [rcx]
0x14012b4d4  test    rdx, rdx
0x14012b4d7  jnz     loc_14012B9A2
0x14012b4dd  mov     rcx, [rbx]
0x14012b4e0  mov     rax, [rcx+128h]
0x14012b4e7  cmp     qword ptr [rax+20h], 0
0x14012b4ec  jnz     loc_14012B9CF
0x14012b4f2  mov     rdi, [rbx]
0x14012b4f5  mov     rax, [rdi+128h]
0x14012b4fc  dec     dword ptr [rax+4]
0x14012b4ff  mov     rcx, [rdi+128h]
0x14012b506  cmp     dword ptr [rcx+4], 0
0x14012b50a  jz      loc_14012B701
0x14012b510  mov     rax, [rbx]
0x14012b513  mov     [rax+128h], r15
0x14012b51a  mov     rax, [rbx]
0x14012b51d  mov     rcx, [rax+148h]
0x14012b524  test    rcx, rcx
0x14012b527  jnz     loc_14012B815
0x14012b52d  cmp     byte ptr [rsp+68h+arg_0], 0
0x14012b532  jz      loc_14012B5CC
0x14012b538  lea     rcx, [r13+1CE8h]; FastMutex
0x14012b53f  mov     [rsp+68h+arg_0], r15d
0x14012b544  lea     rbp, [rax+8]
0x14012b548  mov     dword ptr [rsp+68h+arg_8], r15d
0x14012b54d  call    cs:__imp_ExAcquireFastMutex
0x14012b554  nop     dword ptr [rax+rax+00h]
0x14012b559  lea     r9, [rsp+68h+arg_8]
0x14012b55e  mov     rdx, rbp
0x14012b561  lea     r8, [rsp+68h+arg_0]
0x14012b566  lea     rcx, [r13+1CE8h]
0x14012b56d  call    NtfsGetArrayAndCounterIdx
0x14012b572  mov     ecx, [rsp+68h+arg_0]
0x14012b576  cmp     ecx, 0FFFFFFFFh
0x14012b579  jz      short loc_14012B5B9
0x14012b57b  mov     edx, dword ptr [rsp+68h+arg_8]
0x14012b57f  cmp     edx, 0FFFFFFFFh
0x14012b582  jz      short loc_14012B5B9
0x14012b584  mov     r14d, ecx
0x14012b587  shl     r14, 4
0x14012b58b  add     r14, [r13+1D38h]
0x14012b592  mov     rcx, [r14+8]
0x14012b596  test    rcx, rcx
0x14012b599  jz      short loc_14012B5B9
0x14012b59b  lea     r8, [rcx+rdx*2]
0x14012b59f  movzx   ecx, word ptr [rcx+rdx*2]
0x14012b5a3  test    cx, cx
0x14012b5a6  jz      short loc_14012B5B9
0x14012b5a8  lea     eax, [rcx-1]
0x14012b5ab  mov     [r8], ax
0x14012b5af  cmp     cx, 1
0x14012b5b3  jz      loc_14012B77A
0x14012b5b9  lea     rcx, [r13+1CE8h]; FastMutex
0x14012b5c0  call    cs:__imp_ExReleaseFastMutex
0x14012b5c7  nop     dword ptr [rax+rax+00h]
0x14012b5cc  mov     rax, [rbx]
0x14012b5cf  mov     edi, 0FFFFFFFFh
0x14012b5d4  mov     rcx, [rax+0D0h]; P
0x14012b5db  test    rcx, rcx
0x14012b5de  jz      short loc_14012B608
0x14012b5e0  mov     [rax+0D0h], r15
0x14012b5e7  mov     eax, edi
0x14012b5e9  lock xadd [rcx], eax
0x14012b5ed  sub     eax, 1
0x14012b5f0  jg      short loc_14012B608
0x14012b5f2  test    eax, eax
0x14012b5f4  jnz     loc_14012B8C2
0x14012b5fa  xor     edx, edx; Tag
0x14012b5fc  call    cs:__imp_ExFreePoolWithTag
0x14012b603  nop     dword ptr [rax+rax+00h]
0x14012b608  mov     rdx, [rbx]
0x14012b60b  add     rdx, 78h ; 'x'
0x14012b60f  cmp     qword ptr [rdx], 0
0x14012b613  jz      short loc_14012B620
0x14012b615  xor     r8d, r8d
0x14012b618  mov     rcx, r13
0x14012b61b  call    NtfsDereferenceQuotaControlBlock
0x14012b620  mov     r8, [rbx]
0x14012b623  mov     edx, 723h
0x14012b628  xor     r9d, r9d
0x14012b62b  mov     rcx, rsi
0x14012b62e  call    NtfsAddStructToRollbackList
0x14012b633  test    rax, rax
0x14012b636  jnz     loc_14012BA5C
0x14012b63c  mov     rcx, [rsi+90h]
0x14012b643  cmp     rsi, rcx
0x14012b646  jnz     loc_14012BA72
0x14012b64c  mov     rax, [rbx]
0x14012b64f  mov     rcx, [rax+140h]
0x14012b656  test    rcx, rcx
0x14012b659  jz      short loc_14012B684
0x14012b65b  lock dec dword ptr [rcx+24h]
0x14012b65f  mov     rax, [rbx]
0x14012b662  mov     rcx, [rax+140h]
0x14012b669  lock xadd [rcx+40h], edi
0x14012b66e  cmp     edi, 1
0x14012b671  jz      loc_14012BAA5
0x14012b677  mov     rax, [rbx]
0x14012b67a  mov     [rax+140h], r15
0x14012b681  mov     rax, [rbx]
0x14012b684  test    r12b, r12b
0x14012b687  jnz     short loc_14012B698
0x14012b689  mov     rcx, [rax+130h]
0x14012b690  test    rcx, rcx
0x14012b693  jz      short loc_14012B698
0x14012b695  mov     byte ptr [rcx], 1
0x14012b698  mov     rcx, [rbx]
0x14012b69b  mov     eax, [rcx+4]
0x14012b69e  test    al, 4
0x14012b6a0  jnz     short loc_14012B6B5
0x14012b6a2  add     rcx, 150h; PerFileContextPointer
0x14012b6a9  call    cs:__imp_FsRtlTeardownPerFileContexts
0x14012b6b0  nop     dword ptr [rax+rax+00h]
0x14012b6b5  mov     rcx, [rbx]; P
0x14012b6b8  mov     eax, [rcx+4]
0x14012b6bb  test    r12b, r12b
0x14012b6be  jnz     loc_14012B752
0x14012b6c4  test    al, 2
0x14012b6c6  jnz     loc_14012B8AF
0x14012b6cc  mov     rdx, rcx; Entry
0x14012b6cf  bt      eax, 0Ah
0x14012b6d3  jnb     loc_14012B7FD
0x14012b6d9  lea     rcx, NtfsFcbIndexLookasideList; Lookaside
0x14012b6e0  call    cs:__imp_ExFreeToLookasideListEx
0x14012b6e7  nop     dword ptr [rax+rax+00h]
0x14012b6ec  mov     [rbx], r15
0x14012b6ef  add     rsp, 28h
0x14012b6f3  pop     r15
0x14012b6f5  pop     r14
0x14012b6f7  pop     r13
0x14012b6f9  pop     r12
0x14012b6fb  pop     rdi
0x14012b6fc  pop     rsi
0x14012b6fd  pop     rbp
0x14012b6fe  pop     rbx
0x14012b6ff  retn
0x14012b701  mov     rcx, [rcx+30h]
0x14012b705  test    rcx, rcx
0x14012b708  jz      short loc_14012B731
0x14012b70a  mov     eax, [rcx+90h]
0x14012b710  test    al, 1
0x14012b712  jnz     loc_14012BA06
0x14012b718  mov     rax, [rdi+128h]
0x14012b71f  mov     rcx, [rax+30h]; P
0x14012b723  mov     eax, [rcx+90h]
0x14012b729  test    al, 8
0x14012b72b  jz      loc_14012BA10
0x14012b731  mov     rcx, [rdi+128h]; P
0x14012b738  xor     edx, edx; Tag
0x14012b73a  call    cs:__imp_ExFreePoolWithTag
0x14012b741  nop     dword ptr [rax+rax+00h]
0x14012b746  mov     [rdi+128h], r15
  ... truncated ...
```
