# CmsBlockRefcount::ProcessDeleteQueueEntry(CmsTransactionCore *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,_SmsQuickIndex *,void *)

- ea: `0x1400c1ba0`
- end: `0x1400c26ae`
- name: `?ProcessDeleteQueueEntry@CmsBlockRefcount@@CAJPEAVCmsTransactionCore@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z`
- size: `2830`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionCore *@<rcx>, struct CmsContainerRangeMap *@<rdx>, struct _SmsContainerRangeMapListHead *@<r8>, struct _SmsQuickIndex *@<r9>, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140012ec0`
- `0x140018810`
- `0x140024c60`
- `0x14004d8a8`
- `0x14006a090`
- `0x140078210`
- `0x140078ce0`
- `0x140095e10`
- `0x14009d210`
- `0x1400c1ba0`
- `0x1400cd630`
- `0x1400ceda0`
- `0x1400f910c`
- `0x1400fa8c4`
- `0x1401410f4`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400c2508`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c1e9c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c1eb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c248c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c24a2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c1e9c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c1eb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c248c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c24a2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c2033`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c2033`
- `ntoskrnl!ExAllocatePool2` at `0x1400c20b0`
- `ntoskrnl!ExAllocatePool2` at `0x1400c20b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c1ff9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c1ff9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400c2041`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400c2041`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400c207b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400c207b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1d8d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1e6a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1f48`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c22ac`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c245a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1d8d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1e6a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c1f48`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c22ac`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c245a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c1d70`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c228f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c1d70`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c228f`

## string_xrefs

- `0x1400c26a1`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::ProcessDeleteQueueEntry(
        struct CmsTransactionCore *a1,
        struct CmsContainerRangeMap *a2,
        struct _SmsContainerRangeMapListHead *a3,
        struct _SmsQuickIndex *a4,
        volatile signed __int64 *a5)
{
  int v5; // r14d
  struct CmsTransactionCore *v6; // rbx
  __int64 v7; // rcx
  struct _SmsContainerRangeMapListHead *v8; // rsi
  struct _SmsContainerRangeMapListHead *v9; // r13
  unsigned __int8 v10; // al
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 result; // rax
  __int64 v14; // rcx
  int NextRange; // r12d
  __int64 *v16; // r15
  bool v17; // zf
  signed __int64 *v18; // rcx
  char v19; // cl
  __int64 v20; // rax
  __int64 v21; // r15
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // r14
  __int64 v24; // rcx
  signed __int16 v25; // ax
  signed __int16 v26; // ax
  signed __int16 v27; // tt
  void *v28; // rdx
  signed __int64 *v29; // r15
  __int64 v30; // r14
  _WORD *v31; // r15
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rbx
  unsigned int *v34; // rsi
  __int64 v35; // r9
  struct _NPAGED_LOOKASIDE_LIST *v36; // rcx
  void *v37; // rax
  int v38; // ecx
  signed __int64 v39; // rbx
  unsigned __int64 v40; // rdx
  __int64 Pool2; // rax
  __int16 v42; // dx
  unsigned __int64 v43; // r10
  __int16 v44; // cx
  __int16 v45; // ax
  __int64 v46; // rax
  char *v47; // rsi
  struct CmsTransactionCore *v48; // rdx
  _BYTE *v49; // r14
  _DWORD *v50; // r15
  __int16 v51; // r10
  signed __int64 v52; // rax
  signed __int64 v53; // rax
  __int64 v54; // rsi
  __int64 v55; // r13
  unsigned __int64 v56; // r14
  unsigned __int64 v57; // r15
  unsigned __int64 v58; // rbx
  unsigned __int64 v59; // r10
  unsigned __int64 v60; // rsi
  volatile signed __int32 *v61; // r9
  __int64 v62; // rax
  __int64 v63; // r8
  signed __int16 v64; // ax
  signed __int16 v65; // tt
  __int16 v66; // bx
  __int16 v67; // ax
  __int64 *v68; // r15
  void *v69; // rdx
  unsigned __int64 v70; // r13
  signed __int64 v71; // rax
  signed __int64 v72; // r14
  __int64 v73; // rsi
  struct _SmsContainerRangeMapListHead *v74; // rbx
  int v75; // eax
  struct _SmsContainerRangeMapListHead *v76; // rsi
  signed __int64 v77; // rax
  signed __int64 v78; // rax
  unsigned __int8 v79[4]; // [rsp+40h] [rbp-A1h] BYREF
  unsigned __int16 v80[2]; // [rsp+44h] [rbp-9Dh] BYREF
  int v81; // [rsp+48h] [rbp-99h]
  struct _SmsContainerRangeMapListHead *v82; // [rsp+50h] [rbp-91h] BYREF
  __int16 v83; // [rsp+58h] [rbp-89h]
  unsigned __int64 v84; // [rsp+60h] [rbp-81h] BYREF
  unsigned __int64 v85; // [rsp+68h] [rbp-79h]
  PVOID Entry; // [rsp+70h] [rbp-71h] BYREF
  __int64 *v87; // [rsp+78h] [rbp-69h]
  unsigned __int64 v88; // [rsp+80h] [rbp-61h] BYREF
  __int64 v89; // [rsp+88h] [rbp-59h]
  __int64 v90; // [rsp+90h] [rbp-51h]
  signed __int64 *v91; // [rsp+98h] [rbp-49h]
  struct _SmsContainerRangeMapListHead *v92; // [rsp+A0h] [rbp-41h] BYREF
  unsigned __int64 v93; // [rsp+A8h] [rbp-39h]
  __int64 v94; // [rsp+B0h] [rbp-31h]
  CmsVolume *v95; // [rsp+B8h] [rbp-29h]
  signed __int64 *v96; // [rsp+C0h] [rbp-21h]
  _BYTE v97[24]; // [rsp+D0h] [rbp-11h] BYREF
  __int16 v98; // [rsp+E8h] [rbp+7h]
  char v99; // [rsp+EAh] [rbp+9h]
  int v100; // [rsp+F8h] [rbp+17h]

  v5 = 0;
  v6 = a1;
  v7 = *((_QWORD *)a1 + 1);
  v8 = a3;
  v95 = (CmsVolume *)v7;
  v92 = 0;
  v80[0] = 0;
  v9 = *(struct _SmsContainerRangeMapListHead **)(v7 + 3304);
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v84 = 0;
  v85 = 0;
  v10 = *(_BYTE *)(v7 + 88);
  v82 = v9;
  v79[0] = 0;
  if ( v10 == 2 )
    v10 = (*(_DWORD *)(v7 + 64) != 12) + 1;
  v11 = *((_QWORD *)a3 + 2);
  v12 = 0;
  Entry = 0;
  v90 = *(_QWORD *)(v7 + 8LL * v10 + 3552);
  result = CmsContainerRangeMap::InitializeContainerRangeMapListHead(&v92, v11, 0, 0);
  NextRange = result;
  if ( (int)result < 0 )
    return result;
  v91 = 0;
  v81 = 0;
  CmsVolume::BeginTopLevelActionInternal(v14, v6, v97, 0, 0, 0);
  v16 = (__int64 *)*((_QWORD *)v8 + 3);
  v87 = v16;
  if ( !v16 )
  {
LABEL_144:
    v76 = v92;
    goto LABEL_145;
  }
  do
  {
    v17 = (*((_BYTE *)v16 + 14) & 1) == 0;
    v18 = v16;
    v96 = v16;
    if ( !v17 )
      goto LABEL_39;
    v19 = *((_BYTE *)a2 + 52);
    v94 = 0;
    v20 = *((unsigned __int16 *)v16 + 5);
    v93 = (*((_QWORD *)v8 + 2) << v19) | (unsigned __int16)v16[1] & (unsigned __int64)((1 << v19) - 1);
    v88 = v93;
    v89 = v20;
    if ( !v20 )
      goto LABEL_35;
    while ( 1 )
    {
      NextRange = CmsBlockRefcount::GetNextRange(
                    v9,
                    v6,
                    (const struct _RANGE *)&v88,
                    (struct _RANGE *)&v84,
                    v80,
                    v79,
                    0,
                    (struct CmsRefcountCacheEntry **)&Entry);
      if ( NextRange < 0 )
        goto LABEL_32;
      while ( !v80[0] && v79[0] )
      {
        v12 = (char *)Entry;
        v21 = *((_QWORD *)v6 + 1);
        v22 = v84 - *((_QWORD *)Entry + 2);
        v23 = v22 + v85;
        if ( !*((_QWORD *)Entry + 9) )
        {
          ExAcquirePushLockExclusiveEx((char *)Entry + 56, 0);
          NextRange = CmsRefcountCacheEntry::AllocateArray((CmsRefcountCacheEntry *)v12);
          ExReleasePushLockEx(v12 + 56, 0);
          if ( NextRange < 0 )
            goto LABEL_33;
        }
        for ( ; v22 < v23; ++v22 )
        {
          do
          {
            v24 = *((_QWORD *)v12 + 9);
            v25 = *(_WORD *)(v24 + 2 * v22);
          }
          while ( v25 < 0
               && v25 != _InterlockedCompareExchange16(
                           (volatile signed __int16 *)(v24 + 2 * v22),
                           v25 & 0x3FFF | 0x4000,
                           v25) );
        }
        if ( (v12[50] & 4) != 0 )
        {
          _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
        }
        else
        {
          _m_prefetchw(v12 + 50);
          v26 = *((_WORD *)v12 + 25);
          do
          {
            v27 = v26;
            v26 = _InterlockedCompareExchange16((volatile signed __int16 *)v12 + 25, v26 | 4, v26);
          }
          while ( v27 != v26 );
          _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
          if ( (v26 & 4) == 0 )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 17);
        }
        if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v12, (union _SLIST_HEADER *)v9 + 5) )
          _InterlockedIncrement((volatile signed __int32 *)v9 + 16);
        if ( (*(_DWORD *)(*(_QWORD *)(v21 + 1664) + 120LL) & 0x100) != 0 )
          MsKmeLogOverwriteOrFree(*(struct _VCB *const *)(v21 + 48), (const struct _RANGE *)&v84);
        ExReleasePushLockEx(v12 + 56, 0);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)v12 + 24, 0xFFFFu) == 1 && v12 )
        {
          v28 = (void *)*((_QWORD *)v12 + 9);
          if ( v28 )
            ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::ArraysLookasideList, v28);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v12);
        }
        v6 = a1;
        Entry = 0;
        NextRange = CmsBlockRefcount::GetNextRange(
                      v9,
                      a1,
                      (const struct _RANGE *)&v88,
                      (struct _RANGE *)&v84,
                      v80,
                      v79,
                      0,
                      (struct CmsRefcountCacheEntry **)&Entry);
        if ( NextRange < 0 )
          goto LABEL_32;
      }
      v12 = (char *)Entry;
      if ( v80[0] )
        break;
      v30 = v89;
      if ( v85 != v89 )
      {
        v31 = v87;
        if ( (*((_BYTE *)v87 + 12) & 4) != 0 )
        {
          if ( *(_WORD *)(v90 + 8) )
            v32 = (unsigned __int64)(unsigned int)(v85 << *((_DWORD *)v95 + 16)) >> ((unsigned __int8)*(_WORD *)(v90 + 20)
                                                                                   - *(_BYTE *)(v90 + 12));
          else
            LODWORD(v32) = 0;
        }
        else
        {
          LODWORD(v32) = 0;
        }
        v33 = (unsigned int)(v32 + 16);
        v34 = (unsigned int *)(qword_1402694B0 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
        if ( v33 > *v34 )
        {
          v34 = 0;
          v40 = v33 + 16;
        }
        else
        {
          if ( *((_BYTE *)v34 + 8) )
          {
            v36 = (struct _NPAGED_LOOKASIDE_LIST *)(v34 + 16);
            if ( *((_BYTE *)v34 + 9) )
              v37 = ExAllocateFromNPagedLookasideList(v36);
            else
              v37 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v36);
LABEL_57:
            v39 = (signed __int64)v37;
            if ( !v37 )
            {
              v40 = v34[1];
              goto LABEL_62;
            }
LABEL_64:
            *(_QWORD *)v39 = v34;
            v39 += 16LL;
LABEL_65:
            if ( !v39 )
            {
              NextRange = -1073741670;
LABEL_32:
              v12 = (char *)Entry;
              goto LABEL_33;
            }
            v42 = v85;
            NextRange = 0;
            v43 = v93;
            *(_WORD *)(v39 + 8) = v84 + v31[4] - v93;
            v44 = 0;
            *(_WORD *)(v39 + 14) = 0;
            *(_WORD *)(v39 + 10) = v42;
            if ( (_DWORD)v32 )
              v44 = 4;
            v45 = 0;
            if ( (_DWORD)v32 )
              v45 = 2;
            *(_WORD *)(v39 + 12) = v45 | v44;
            if ( (_DWORD)v32 )
            {
              v46 = v90;
              v47 = (char *)(v31 + 8);
              v48 = a1;
              v49 = (_BYTE *)(v90 + 20);
              v50 = (_DWORD *)(v90 + 12);
              if ( *(_WORD *)(v90 + 8) )
              {
                memmove(
                  (void *)(v39 + 16),
                  &v47[(unsigned __int64)(unsigned int)((v84 - v43) << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> *v49 << *v50],
                  (unsigned __int64)(unsigned int)(v85 << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> ((unsigned __int8)*(_WORD *)v49 - (unsigned __int8)*v50));
                v48 = a1;
                v46 = v90;
              }
              if ( *(_WORD *)(v46 + 8) )
              {
                v51 = *(_WORD *)v49;
                v30 = v89;
                memmove(
                  v47,
                  &v47[(unsigned __int64)(unsigned int)(v85 << *(_DWORD *)(*((_QWORD *)v48 + 1) + 64LL)) >> v51 << *v50],
                  (unsigned __int64)(unsigned int)((v89 - v85) << *(_DWORD *)(*((_QWORD *)v48 + 1) + 64LL)) >> ((unsigned __int8)v51 - (unsigned __int8)*v50));
                v31 = v87;
LABEL_77:
                v31[5] -= v85;
                v31[4] += v85;
                ++v81;
                _m_prefetchw((char *)a3 + 24);
                do
                {
                  v52 = *((_QWORD *)a3 + 3);
                  *(_QWORD *)v39 = v52;
                  v53 = _InterlockedCompareExchange64((volatile signed __int64 *)a3 + 3, v39, v52);
                }
                while ( v53 != *(_QWORD *)v39 );
                if ( !v53 )
                  *((_QWORD *)a3 + 4) = v39;
                if ( (*(_BYTE *)(v39 + 12) & 2) != 0 )
                  _InterlockedOr((volatile signed __int32 *)a3 + 11, 1u);
                _InterlockedIncrement((volatile signed __int32 *)a3 + 10);
                _InterlockedIncrement64((volatile signed __int64 *)a2 + 4);
                if ( !v91 )
                  v91 = (signed __int64 *)v39;
LABEL_110:
                v6 = a1;
                goto LABEL_111;
              }
              v31 = v87;
            }
            v30 = v89;
            goto LABEL_77;
          }
          if ( (int)*((_QWORD *)v34 + 11) > (int)HIDWORD(*((_QWORD *)v34 + 11)) )
          {
            v38 = _InterlockedDecrement((volatile signed __int32 *)v34 + 22);
            if ( v38 >= (int)v34[23] && v38 >= 0 )
            {
              v37 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34 + 4);
              goto LABEL_57;
            }
            _InterlockedIncrement((volatile signed __int32 *)v34 + 22);
          }
          v40 = v34[1];
        }
LABEL_62:
        Pool2 = ExAllocatePool2(66, v40, 1766871885, v35);
        v39 = Pool2;
        if ( (Pool2 & 0xF) != 0 )
          MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
        if ( Pool2 )
          goto LABEL_64;
        goto LABEL_65;
      }
LABEL_111:
      if ( v12 )
      {
        ExReleasePushLockEx(v12 + 56, 0);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)v12 + 24, 0xFFFFu) == 1 )
        {
          v69 = (void *)*((_QWORD *)v12 + 9);
          if ( v69 )
            ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::ArraysLookasideList, v69);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v12);
        }
        v12 = 0;
        Entry = 0;
      }
      v89 = v30 - v85;
      v93 += v85;
      v88 = v93;
      if ( v30 == v85 )
        goto LABEL_33;
    }
    NextRange = 0;
    v54 = *((_QWORD *)Entry + 2);
    v55 = *(_QWORD *)v9;
    v56 = v85;
    v57 = v84;
    if ( !*((_QWORD *)Entry + 9) )
    {
      ExAcquirePushLockExclusiveEx((char *)Entry + 56, 0);
      NextRange = CmsRefcountCacheEntry::AllocateArray((CmsRefcountCacheEntry *)v12);
      ExReleasePushLockEx(v12 + 56, 0);
      if ( NextRange < 0 )
      {
        v9 = v82;
LABEL_102:
        if ( NextRange < 0 )
          goto LABEL_33;
        v66 = v85;
        v30 = v89;
        if ( v85 == v89 )
        {
          v67 = *((_WORD *)v87 + 7);
          LOBYTE(v67) = v67 | 1;
          v83 = v67;
          *((_WORD *)v87 + 7) = v67;
        }
        else
        {
          v68 = v87;
          if ( (*((_BYTE *)v87 + 12) & 4) != 0 && *(_WORD *)(v90 + 8) )
          {
            memmove(
              v87 + 2,
              (char *)v87
            + ((unsigned __int64)(unsigned int)(v85 << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> *(_WORD *)(v90 + 20) << *(_DWORD *)(v90 + 12))
            + 16,
              (unsigned __int64)(unsigned int)((v89 - v85) << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> ((unsigned __int8)*(_WORD *)(v90 + 20) - (unsigned __int8)*(_DWORD *)(v90 + 12)));
            v66 = v85;
          }
          *((_WORD *)v68 + 5) -= v66;
          *((_WORD *)v68 + 4) += v85;
        }
        v94 += v85;
        goto LABEL_110;
      }
    }
    v58 = v57 - v54;
    v59 = v58;
    v60 = v56 + v57 - v54;
    if ( v58 >= v60 )
    {
LABEL_92:
      if ( (v12[50] & 4) != 0 )
      {
        _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
      }
      else
      {
        _m_prefetchw(v12 + 50);
        v64 = *((_WORD *)v12 + 25);
        do
        {
          v65 = v64;
          v64 = _InterlockedCompareExchange16((volatile signed __int16 *)v12 + 25, v64 | 4, v64);
        }
        while ( v65 != v64 );
        _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
        if ( (v64 & 4) == 0 )
        {
          v9 = v82;
          _InterlockedIncrement((volatile signed __int32 *)v82 + 17);
LABEL_95:
          if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v12, (union _SLIST_HEADER *)v9 + 5) )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 16);
          goto LABEL_102;
        }
      }
      v9 = v82;
      goto LABEL_95;
    }
    v61 = (volatile signed __int32 *)(v12 + 64);
    while ( 1 )
    {
      v62 = *((_QWORD *)v12 + 9);
      v63 = *(__int16 *)(v62 + 2 * v59);
      if ( (v63 & 0x1FFF) == 0 )
        break;
      v61 = (volatile signed __int32 *)(v12 + 64);
      if ( (_WORD)v63 == _InterlockedCompareExchange16((volatile signed __int16 *)(v62 + 2 * v59), v63 - 1, v63) )
      {
        NextRange = 0;
        v61 = (volatile signed __int32 *)(v12 + 64);
        ++v59;
        _InterlockedDecrement((volatile signed __int32 *)v12 + 16);
        if ( v59 >= v60 )
          goto LABEL_92;
      }
    }
    while ( v59 > v58 )
    {
      --v59;
      _InterlockedIncrement16((volatile signed __int16 *)(*((_QWORD *)v12 + 9) + 2 * v59));
      _InterlockedIncrement(v61);
    }
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    MsKmeBlockRefCountUnderflowEventNotification(
      *(struct _VCB **)(v55 + 48),
      0x47400602C9uLL,
      v63,
      v59,
      v57,
      v56,
      v58,
      v60);
    NextRange = -1073741675;
LABEL_33:
    v9 = v82;
    v16 = v87;
    v8 = a3;
    v6 = a1;
    v5 = v81;
    if ( v94 )
      _InterlockedAdd64((volatile signed __int64 *)v95 + 468, -v94);
LABEL_35:
    if ( v12 )
    {
      ExReleasePushLockEx(v12 + 56, 0);
      CmsRefcountCacheEntry::Release(v12);
      v12 = 0;
      Entry = 0;
    }
    if ( NextRange < 0 )
    {
      v29 = v91;
      goto LABEL_126;
    }
    v18 = v96;
LABEL_39:
    v16 = (__int64 *)*v16;
    ++v5;
    v87 = v16;
    v81 = v5;
    v91 = v18;
  }
  while ( v16 );
  v29 = v18;
  v81 = v5;
LABEL_126:
  if ( v5 <= 0 )
    goto LABEL_144;
  v70 = v81;
  *((_DWORD *)v8 + 10) -= v81;
  v71 = *v29;
  v72 = *((_QWORD *)v8 + 3);
  *((_QWORD *)v8 + 3) = *v29;
  if ( !v71 )
    *((_QWORD *)v8 + 4) = 0;
  _InterlockedAdd64((volatile signed __int64 *)a2 + 4, -(int)v70);
  v73 = *((_QWORD *)v8 + 2);
  v82 = 0;
  if ( (int)CmsContainerRangeMap::InitializeMapIfRequired((CmsContainerRangeMap *)a5) < 0 )
    goto LABEL_144;
  if ( (int)CmsHashTableLite::PinInIndex<1>(a5, v73, &v82, 0) >= 0 )
  {
    v76 = v92;
    v74 = v82;
  }
  else
  {
    v74 = v92;
    v82 = v92;
    v75 = CmsHashTableLite::AddToIndex<1>(a5, v92, 0);
    if ( v75 == -1073741771 )
    {
      CmsLookasides::Free(v74);
      CmsHashTableLite::PinInIndex<1>(a5, v73, &v82, 0);
      v74 = v82;
      goto LABEL_133;
    }
    if ( v75 < 0 )
    {
      CmsLookasides::Free(v74);
      v76 = 0;
      goto LABEL_145;
    }
LABEL_133:
    v76 = 0;
  }
  if ( (*((_DWORD *)a3 + 11) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)v74 + 11, 1u);
  _m_prefetchw((char *)v74 + 24);
  do
  {
    v77 = *((_QWORD *)v74 + 3);
    *v29 = v77;
    v78 = _InterlockedCompareExchange64((volatile signed __int64 *)v74 + 3, v72, v77);
  }
  while ( v78 != *v29 );
  if ( !v78 )
    *((_QWORD *)v74 + 4) = v29;
  _InterlockedAdd((volatile signed __int32 *)v74 + 10, v70);
  _InterlockedAdd64(a5 + 4, v70);
LABEL_145:
  CmsVolume::CommitTopLevelAction(v95, a1, (struct _SmsTopLevelAction *)v97, 0);
  if ( v76 )
    CmsLookasides::Free(v76);
  return (unsigned int)NextRange;
}

```

## disassembly

```asm
0x1400c1ba0  mov     [rsp-8+arg_10], r8
0x1400c1ba5  mov     [rsp-8+arg_8], rdx
0x1400c1baa  mov     [rsp-8+arg_0], rcx
0x1400c1baf  push    rbp
0x1400c1bb0  push    rbx
0x1400c1bb1  push    rsi
0x1400c1bb2  push    rdi
0x1400c1bb3  push    r12
0x1400c1bb5  push    r13
0x1400c1bb7  push    r14
0x1400c1bb9  lea     rbp, [rsp-1Fh]
0x1400c1bbe  sub     rsp, 100h
0x1400c1bc5  xor     r14d, r14d
0x1400c1bc8  mov     rbx, rcx
0x1400c1bcb  mov     rcx, [rcx+8]
0x1400c1bcf  mov     rsi, r8
0x1400c1bd2  mov     [rbp+4Fh+var_78], rcx
0x1400c1bd6  mov     [rbp+4Fh+var_90], r14
0x1400c1bda  mov     [rsp+130h+var_EC], r14w
0x1400c1be0  mov     r13, [rcx+0CE8h]
0x1400c1be7  mov     [rbp+4Fh+var_48], r14w
0x1400c1bec  mov     [rbp+4Fh+var_46], r14b
0x1400c1bf0  mov     [rbp+4Fh+var_38], r14d
0x1400c1bf4  mov     [rsp+130h+var_D0], r14
0x1400c1bf9  mov     [rbp+4Fh+var_C8], r14
0x1400c1bfd  movzx   eax, byte ptr [rcx+58h]
0x1400c1c01  mov     [rsp+130h+var_E0], r13
0x1400c1c06  mov     [rsp+130h+var_F0], r14b
0x1400c1c0b  cmp     al, 2
0x1400c1c0d  jnz     short loc_1400C1C18
0x1400c1c0f  cmp     dword ptr [rcx+40h], 0Ch
0x1400c1c13  setnz   al
0x1400c1c16  inc     al
0x1400c1c18  mov     rdx, [rsi+10h]; unsigned __int64
0x1400c1c1c  xor     r9d, r9d; int *
0x1400c1c1f  movzx   eax, al
0x1400c1c22  xor     r8d, r8d; unsigned __int8
0x1400c1c25  mov     rdi, r14
0x1400c1c28  mov     [rbp+4Fh+Entry], r14
0x1400c1c2c  mov     rcx, [rcx+rax*8+0DE0h]
0x1400c1c34  mov     [rbp+4Fh+var_A0], rcx
0x1400c1c38  lea     rcx, [rbp+4Fh+var_90]; struct _SmsContainerRangeMapListHead **
0x1400c1c3c  call    ?InitializeContainerRangeMapListHead@CmsContainerRangeMap@@SAJPEAPEAU_SmsContainerRangeMapListHead@@_KEPEAJ@Z; CmsContainerRangeMap::InitializeContainerRangeMapListHead(_SmsContainerRangeMapListHead * *,unsigned __int64,uchar,long *)
0x1400c1c41  mov     r12d, eax
0x1400c1c44  test    eax, eax
0x1400c1c46  js      loc_1400C268E
0x1400c1c4c  mov     byte ptr [rsp+130h+var_108], dil
0x1400c1c51  lea     r8, [rbp+4Fh+var_60]
0x1400c1c55  xor     r9d, r9d
0x1400c1c58  mov     byte ptr [rsp+130h+var_110], dil
0x1400c1c5d  mov     rdx, rbx
0x1400c1c60  mov     [rsp+130h+arg_18], r15
0x1400c1c68  mov     [rbp+4Fh+var_98], r14
0x1400c1c6c  mov     [rsp+130h+var_E8], r14d
0x1400c1c71  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x1400c1c76  mov     r15, [rsi+18h]
0x1400c1c7a  mov     [rbp+4Fh+var_B8], r15
0x1400c1c7e  test    r15, r15
0x1400c1c81  jz      loc_1400C265E
0x1400c1c87  nop     word ptr [rax+rax+00000000h]
0x1400c1c90  test    byte ptr [r15+0Eh], 1
0x1400c1c95  mov     rcx, r15
0x1400c1c98  mov     [rbp+4Fh+var_70], rcx
0x1400c1c9c  jnz     loc_1400C1F6F
0x1400c1ca2  mov     rax, [rbp+4Fh+arg_8]
0x1400c1ca6  movzx   ecx, byte ptr [rax+34h]
0x1400c1caa  xor     eax, eax
0x1400c1cac  mov     [rbp+4Fh+var_80], rax
0x1400c1cb0  mov     eax, 1
0x1400c1cb5  shl     eax, cl
0x1400c1cb7  dec     eax
0x1400c1cb9  movsxd  rdx, eax
0x1400c1cbc  movzx   eax, word ptr [r15+8]
0x1400c1cc1  and     rdx, rax
0x1400c1cc4  mov     rax, [rsi+10h]
0x1400c1cc8  shl     rax, cl
0x1400c1ccb  or      rdx, rax
0x1400c1cce  movzx   eax, word ptr [r15+0Ah]
0x1400c1cd3  mov     [rbp+4Fh+var_88], rdx
0x1400c1cd7  mov     [rbp+4Fh+var_B0], rdx
0x1400c1cdb  mov     [rbp+4Fh+var_A8], rax
0x1400c1cdf  test    rax, rax
0x1400c1ce2  jz      loc_1400C1F3D
0x1400c1ce8  xor     esi, esi
0x1400c1cea  nop     word ptr [rax+rax+00h]
0x1400c1cf0  lea     rax, [rbp+4Fh+Entry]
0x1400c1cf4  mov     rdx, rbx; struct CmsTransactionContext *
0x1400c1cf7  mov     [rsp+130h+var_F8], rax; struct CmsRefcountCacheEntry **
0x1400c1cfc  lea     r9, [rsp+130h+var_D0]; struct _RANGE *
0x1400c1d01  lea     rax, [rsp+130h+var_F0]
0x1400c1d06  mov     [rsp+130h+var_100], rsi; unsigned __int8 *
0x1400c1d0b  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x1400c1d10  lea     r8, [rbp+4Fh+var_B0]; struct _RANGE *
0x1400c1d14  lea     rax, [rsp+130h+var_EC]
0x1400c1d19  mov     rcx, r13; this
0x1400c1d1c  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400c1d21  call    ?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z; CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)
0x1400c1d26  mov     r12d, eax
0x1400c1d29  test    eax, eax
0x1400c1d2b  js      loc_1400C1F09
0x1400c1d31  movzx   eax, [rsp+130h+var_EC]
0x1400c1d36  test    ax, ax
0x1400c1d39  jnz     loc_1400C1F98
0x1400c1d3f  cmp     [rsp+130h+var_F0], al
0x1400c1d43  jz      loc_1400C1F98
0x1400c1d49  mov     rdi, [rbp+4Fh+Entry]
0x1400c1d4d  xor     r12d, r12d
0x1400c1d50  mov     rsi, [rsp+130h+var_D0]
0x1400c1d55  mov     r14, [rbp+4Fh+var_C8]
0x1400c1d59  mov     r15, [rbx+8]
0x1400c1d5d  sub     rsi, [rdi+10h]
0x1400c1d61  add     r14, rsi
0x1400c1d64  cmp     [rdi+48h], r12
0x1400c1d68  jnz     short loc_1400C1DA2
0x1400c1d6a  xor     edx, edx
0x1400c1d6c  lea     rcx, [rdi+38h]
0x1400c1d70  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c1d77  nop     dword ptr [rax+rax+00h]
0x1400c1d7c  mov     rcx, rdi; this
0x1400c1d7f  call    ?AllocateArray@CmsRefcountCacheEntry@@QEAAJXZ; CmsRefcountCacheEntry::AllocateArray(void)
0x1400c1d84  xor     edx, edx
0x1400c1d86  lea     rcx, [rdi+38h]
0x1400c1d8a  mov     r12d, eax
0x1400c1d8d  call    cs:__imp_ExReleasePushLockEx
0x1400c1d94  nop     dword ptr [rax+rax+00h]
0x1400c1d99  test    r12d, r12d
0x1400c1d9c  js      loc_1400C1F0D
0x1400c1da2  cmp     rsi, r14
0x1400c1da5  jnb     short loc_1400C1DE8
0x1400c1da7  nop     word ptr [rax+rax+00000000h]
0x1400c1db0  xor     r12d, r12d
0x1400c1db3  mov     r8d, 3FFFh
0x1400c1db9  mov     r9d, 4000h
0x1400c1dbf  nop
0x1400c1dc0  mov     rcx, [rdi+48h]
0x1400c1dc4  movzx   eax, word ptr [rcx+rsi*2]
0x1400c1dc8  test    ax, ax
0x1400c1dcb  jns     short loc_1400C1DE0
0x1400c1dcd  movzx   edx, ax
0x1400c1dd0  and     dx, r8w
0x1400c1dd4  or      dx, r9w
0x1400c1dd8  lock cmpxchg [rcx+rsi*2], dx
0x1400c1dde  jnz     short loc_1400C1DC0
0x1400c1de0  inc     rsi
0x1400c1de3  cmp     rsi, r14
0x1400c1de6  jb      short loc_1400C1DB0
0x1400c1de8  test    byte ptr [rdi+32h], 4
0x1400c1dec  nop
0x1400c1ded  jz      short loc_1400C1DF7
0x1400c1def  lock and word ptr [rdi+32h], 0FFF7h
0x1400c1df5  jmp     short loc_1400C1E25
0x1400c1df7  prefetchw byte ptr [rdi+32h]
0x1400c1dfb  movzx   eax, word ptr [rdi+32h]
0x1400c1dff  nop
0x1400c1e00  movzx   ecx, ax
0x1400c1e03  or      cx, 4
0x1400c1e07  lock cmpxchg [rdi+32h], cx
0x1400c1e0d  jnz     short loc_1400C1E00
0x1400c1e0f  nop
0x1400c1e10  nop
0x1400c1e11  lock and word ptr [rdi+32h], 0FFF7h
0x1400c1e17  nop
0x1400c1e18  bt      ax, 2
0x1400c1e1d  jb      short loc_1400C1E26
0x1400c1e1f  nop
0x1400c1e20  lock inc dword ptr [r13+44h]
0x1400c1e25  nop
0x1400c1e26  lea     rdx, [r13+50h]; union _SLIST_HEADER *
0x1400c1e2a  mov     rcx, rdi; this
0x1400c1e2d  call    ?AddForProcessing@CmsRefcountCacheEntry@@QEAAEPEAT_SLIST_HEADER@@@Z; CmsRefcountCacheEntry::AddForProcessing(_SLIST_HEADER *)
0x1400c1e32  test    al, al
0x1400c1e34  jz      short loc_1400C1E3D
0x1400c1e36  nop
0x1400c1e37  lock inc dword ptr [r13+40h]
0x1400c1e3c  nop
0x1400c1e3d  mov     rax, [r15+680h]
0x1400c1e44  test    dword ptr [rax+78h], 100h
0x1400c1e4b  jz      short loc_1400C1E5B
0x1400c1e4d  mov     rcx, [r15+30h]; struct _VCB *
0x1400c1e51  lea     rdx, [rsp+130h+var_D0]; struct _RANGE *
0x1400c1e56  call    ?MsKmeLogOverwriteOrFree@@YAXQEAU_VCB@@PEBU_RANGE@@@Z; MsKmeLogOverwriteOrFree(_VCB * const,_RANGE const *)
0x1400c1e5b  test    r12d, r12d
0x1400c1e5e  js      loc_1400C1F0D
0x1400c1e64  lea     rcx, [rdi+38h]
0x1400c1e68  xor     edx, edx
0x1400c1e6a  call    cs:__imp_ExReleasePushLockEx
0x1400c1e71  nop     dword ptr [rax+rax+00h]
0x1400c1e76  mov     eax, 0FFFFFFFFh
0x1400c1e7b  lock xadd [rdi+30h], ax
0x1400c1e81  cmp     ax, 1
0x1400c1e85  jnz     short loc_1400C1EBE
0x1400c1e87  test    rdi, rdi
0x1400c1e8a  jz      short loc_1400C1EBE
0x1400c1e8c  mov     rdx, [rdi+48h]; Entry
0x1400c1e90  test    rdx, rdx
0x1400c1e93  jz      short loc_1400C1EA8
0x1400c1e95  lea     rcx, ?ArraysLookasideList@CmsRefcountCacheEntry@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400c1e9c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400c1ea3  nop     dword ptr [rax+rax+00h]
0x1400c1ea8  mov     rdx, rdi; Entry
0x1400c1eab  lea     rcx, ?EntriesLookasideList@CmsRefcountCacheEntry@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400c1eb2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400c1eb9  nop     dword ptr [rax+rax+00h]
0x1400c1ebe  mov     rbx, [rbp+4Fh+arg_0]
0x1400c1ec2  lea     rax, [rbp+4Fh+Entry]
0x1400c1ec6  mov     [rsp+130h+var_F8], rax; struct CmsRefcountCacheEntry **
0x1400c1ecb  lea     r9, [rsp+130h+var_D0]; struct _RANGE *
0x1400c1ed0  xor     esi, esi
0x1400c1ed2  lea     rax, [rsp+130h+var_F0]
0x1400c1ed7  mov     [rsp+130h+var_100], rsi; unsigned __int8 *
0x1400c1edc  lea     r8, [rbp+4Fh+var_B0]; struct _RANGE *
0x1400c1ee0  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x1400c1ee5  mov     rdx, rbx; struct CmsTransactionContext *
0x1400c1ee8  lea     rax, [rsp+130h+var_EC]
0x1400c1eed  mov     [rbp+4Fh+Entry], rsi
0x1400c1ef1  mov     rcx, r13; this
0x1400c1ef4  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400c1ef9  call    ?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z; CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)
0x1400c1efe  mov     r12d, eax
0x1400c1f01  test    eax, eax
0x1400c1f03  jns     loc_1400C1D31
0x1400c1f09  mov     rdi, [rbp+4Fh+Entry]
0x1400c1f0d  mov     rax, [rbp+4Fh+var_80]
0x1400c1f11  mov     r13, [rsp+130h+var_E0]
0x1400c1f16  mov     r15, [rbp+4Fh+var_B8]
0x1400c1f1a  mov     rsi, [rbp+4Fh+arg_10]
0x1400c1f1e  mov     rbx, [rbp+4Fh+arg_0]
0x1400c1f22  mov     r14d, [rsp+130h+var_E8]
0x1400c1f27  test    rax, rax
0x1400c1f2a  jz      short loc_1400C1F3D
0x1400c1f2c  mov     rcx, [rbp+4Fh+var_78]
0x1400c1f30  nop
0x1400c1f31  neg     rax
0x1400c1f34  lock add [rcx+0EA0h], rax
0x1400c1f3c  nop
0x1400c1f3d  test    rdi, rdi
0x1400c1f40  jz      short loc_1400C1F62
0x1400c1f42  lea     rcx, [rdi+38h]
0x1400c1f46  xor     edx, edx
0x1400c1f48  call    cs:__imp_ExReleasePushLockEx
0x1400c1f4f  nop     dword ptr [rax+rax+00h]
0x1400c1f54  mov     rcx, rdi; Entry
0x1400c1f57  call    ?Release@CmsRefcountCacheEntry@@QEAAXXZ; CmsRefcountCacheEntry::Release(void)
0x1400c1f5c  xor     edi, edi
0x1400c1f5e  mov     [rbp+4Fh+Entry], rdi
0x1400c1f62  test    r12d, r12d
0x1400c1f65  js      loc_1400C254A
0x1400c1f6b  mov     rcx, [rbp+4Fh+var_70]
0x1400c1f6f  mov     r15, [r15]
0x1400c1f72  inc     r14d
0x1400c1f75  mov     [rbp+4Fh+var_B8], r15
0x1400c1f79  mov     [rsp+130h+var_E8], r14d
0x1400c1f7e  mov     [rbp+4Fh+var_98], rcx
0x1400c1f82  test    r15, r15
0x1400c1f85  jnz     loc_1400C1C90
0x1400c1f8b  mov     r15, rcx
0x1400c1f8e  mov     [rsp+130h+var_E8], r14d
0x1400c1f93  jmp     loc_1400C254E
0x1400c1f98  mov     rdi, [rbp+4Fh+Entry]
0x1400c1f9c  test    ax, ax
0x1400c1f9f  jnz     loc_1400C226E
0x1400c1fa5  mov     r14, [rbp+4Fh+var_A8]
0x1400c1fa9  cmp     [rbp+4Fh+var_C8], r14
0x1400c1fad  jz      loc_1400C244F
0x1400c1fb3  mov     r15, [rbp+4Fh+var_B8]
0x1400c1fb7  test    byte ptr [r15+0Ch], 4
0x1400c1fbc  jz      short loc_1400C1FF0
0x1400c1fbe  mov     r14, [rbp+4Fh+var_A0]
0x1400c1fc2  cmp     [r14+8], ax
0x1400c1fc7  jnz     short loc_1400C1FCE
0x1400c1fc9  mov     r14, rsi
0x1400c1fcc  jmp     short loc_1400C1FF3
0x1400c1fce  movzx   edx, word ptr [r14+14h]
0x1400c1fd3  sub     edx, [r14+0Ch]
0x1400c1fd7  mov     rax, [rbp+4Fh+var_78]
0x1400c1fdb  mov     r14, [rbp+4Fh+var_C8]
0x1400c1fdf  mov     ecx, [rax+40h]
0x1400c1fe2  shl     r14, cl
0x1400c1fe5  movzx   ecx, dl
0x1400c1fe8  mov     r14d, r14d
0x1400c1feb  shr     r14, cl
0x1400c1fee  jmp     short loc_1400C1FF3
0x1400c1ff0  mov     r14d, esi
0x1400c1ff3  xor     ecx, ecx; ProcNumber
0x1400c1ff5  lea     ebx, [r14+10h]
0x1400c1ff9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c2000  nop     dword ptr [rax+rax+00h]
0x1400c2005  xor     edx, edx
0x1400c2007  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400c200d  lea     rsi, [rdx+rdx*2]
0x1400c2011  shl     rsi, 6
0x1400c2015  add     rsi, cs:qword_1402694B0
0x1400c201c  mov     eax, [rsi]
0x1400c201e  cmp     rbx, rax
0x1400c2021  ja      short loc_1400C209F
0x1400c2023  cmp     byte ptr [rsi+8], 0
0x1400c2027  jz      short loc_1400C204F
0x1400c2029  cmp     byte ptr [rsi+9], 0
0x1400c202d  lea     rcx, [rsi+40h]; Lookaside
0x1400c2031  jz      short loc_1400C2041
  ... truncated ...
```
