# CmsBPlusTable::DiscardPagesWorker(void *)

- ea: `0x140017870`
- end: `0x140018357`
- name: `?DiscardPagesWorker@CmsBPlusTable@@SAXPEAX@Z`
- size: `2791`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014750`
- `0x140016440`
- `0x14001712c`
- `0x140017370`
- `0x14001738c`
- `0x1400173c0`
- `0x140017870`
- `0x140047288`
- `0x140047730`
- `0x140047b2c`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140017f69`
- `ntoskrnl!KeSetEvent` at `0x140017f69`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017f3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017f3e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400182ab`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400182ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400178cd`
- `ntoskrnl!ExAllocatePool2` at `0x1400178cd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140017890`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140017890`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9734`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9734`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400180f4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400180f4`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140017d91`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140017d91`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f977c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f977c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400182c9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400182c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018346`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018346`

## string_xrefs

- `0x1400178e4`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::DiscardPagesWorker(_QWORD *a1)
{
  __int64 v1; // rsi
  _QWORD *v2; // r14
  __int64 v3; // rdi
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY v7; // rbx
  int v8; // ecx
  _QWORD *i; // rdx
  _QWORD *v10; // rbx
  _QWORD *v11; // r8
  _QWORD *v12; // r11
  _QWORD *v13; // r10
  _QWORD *v14; // r9
  bool v15; // zf
  __int64 **j; // rax
  struct CmsTransactionCore *v17; // r13
  int v18; // r15d
  __int64 *v19; // r10
  __int64 *v20; // rsi
  __int64 *v21; // r15
  __int64 v22; // r13
  _QWORD *v23; // r10
  unsigned int v24; // r12d
  unsigned int v25; // edi
  int v26; // eax
  volatile signed __int32 *v27; // r14
  __int64 *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r13
  __int64 v32; // rbp
  __int64 v33; // r13
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // ecx
  unsigned int v37; // eax
  signed __int64 v38; // rdx
  signed __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // ebp
  unsigned int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // r9d
  int v46; // ecx
  unsigned int v47; // r11d
  unsigned int v48; // eax
  struct _FILE_OBJECT *v49; // r10
  signed __int64 v50; // rdx
  unsigned int v51; // eax
  struct _FILE_OBJECT *v52; // rbp
  struct _FILE_OBJECT *v53; // rcx
  unsigned __int64 v54; // rcx
  unsigned int m; // r9d
  __int64 v56; // rcx
  unsigned int k; // r9d
  unsigned int v58; // r12d
  __int64 v59; // rax
  __int64 v60; // rbp
  int v61; // r14d
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // r12
  int v65; // ecx
  unsigned __int64 v66; // r8
  unsigned int v67; // eax
  int v68; // ecx
  struct _FILE_OBJECT *v69; // rbp
  __int64 v70; // rbx
  struct _SLIST_ENTRY *v71; // r12
  __int64 v72; // rdi
  __int64 v73; // rbx
  struct _SLIST_ENTRY *Next; // rbx
  struct _PAGED_LOOKASIDE_LIST *v75; // rcx
  struct _SLIST_ENTRY *v76; // rdx
  __int64 *v77; // rcx
  __int64 **v78; // rax
  __int64 v79; // rbx
  unsigned int v80; // r9d
  CmsVolume *v81; // r14
  __int64 *v82; // rbx
  unsigned int v83; // ebp
  __int64 *v84; // rdi
  __int64 *v85; // rdi
  int *v86; // rcx
  int v87; // r8d
  int *v88; // rdx
  int v89; // eax
  __int64 *v90; // r10
  __int64 *v91; // r8
  __int64 *v92; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v93; // rcx
  struct _SLIST_ENTRY *v94; // rax
  __int64 v95; // rcx
  struct CmsTransactionCore *v96; // [rsp+30h] [rbp-B8h]
  PSLIST_ENTRY v97; // [rsp+38h] [rbp-B0h]
  __int64 v98; // [rsp+40h] [rbp-A8h]
  unsigned __int64 v99; // [rsp+48h] [rbp-A0h]
  __int64 v100; // [rsp+48h] [rbp-A0h]
  struct _FILE_OBJECT *v101[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 *v102; // [rsp+60h] [rbp-88h]
  unsigned int v103; // [rsp+68h] [rbp-80h]
  union _LARGE_INTEGER v104; // [rsp+70h] [rbp-78h] BYREF
  struct _FILE_OBJECT *v105; // [rsp+78h] [rbp-70h]
  __int64 *v106; // [rsp+80h] [rbp-68h]
  struct _FILE_OBJECT *v107[2]; // [rsp+88h] [rbp-60h] BYREF
  _QWORD *v108; // [rsp+98h] [rbp-50h]
  int v110; // [rsp+F8h] [rbp+10h]
  unsigned int v111; // [rsp+100h] [rbp+18h]
  int v112; // [rsp+108h] [rbp+20h]

  v1 = *a1;
  v2 = a1;
  v3 = qword_140269408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v3 < 0xDD0u )
  {
    v3 = 0;
    v5 = 3552;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v3 + 8) )
  {
    v93 = (struct _NPAGED_LOOKASIDE_LIST *)(v3 + 64);
    if ( *(_BYTE *)(v3 + 9) )
      v94 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v93);
    else
      v94 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v93);
    v7 = v94;
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v94->Next + 1);
LABEL_149:
    if ( v7 )
    {
LABEL_150:
      v71 = v7 + 1;
      v7->Next = (struct _SLIST_ENTRY *)v3;
      v97 = v7 + 1;
      if ( v7 == (PSLIST_ENTRY)-16LL )
        goto LABEL_104;
      v85 = v2 + 123;
      *((_QWORD *)&v7[1].Next + 1) = v1;
      v71->Next = (struct _SLIST_ENTRY *)0x8000;
      v92 = (__int64 *)v2[123];
      v106 = v2 + 123;
      v96 = (struct CmsTransactionCore *)&v7[1];
      if ( v92 == v2 + 123 || (__int64 *)*v92 == v85 )
      {
        v97 = v7 + 1;
        v17 = (struct CmsTransactionCore *)&v7[1];
      }
      else
      {
        v2[124] = v92;
        v90 = v92;
        v91 = (__int64 *)*v92;
        if ( (__int64 *)*v92 == v85 )
        {
          v97 = v7 + 1;
        }
        else
        {
          do
          {
            if ( *(v92 - 9) - *(v91 - 9) > 0 )
            {
              v90[1] = (__int64)v91;
              v90 = v91;
              *v92 = 0;
            }
            v92 = v91;
            v91 = (__int64 *)*v91;
          }
          while ( v91 != v85 );
        }
        if ( (__int64 *)v2[124] == v90 )
        {
          v17 = (struct CmsTransactionCore *)&v7[1];
          v2[124] = v92;
        }
        else
        {
          *v92 = 0;
          v90[1] = 0;
          for ( i = (_QWORD *)v2[124]; i[1]; i = (_QWORD *)v2[124] )
          {
            v10 = v2 + 123;
            do
            {
              v11 = (_QWORD *)i[1];
              v12 = (_QWORD *)v11[1];
              if ( (__int64)(*(i - 9) - *(v11 - 9)) <= 0 )
              {
                v13 = i;
                i = (_QWORD *)*i;
              }
              else
              {
                v13 = (_QWORD *)i[1];
                v11 = (_QWORD *)*v11;
              }
              v14 = v13;
              v15 = i == 0;
              if ( i )
              {
                do
                {
                  if ( !v11 )
                    break;
                  if ( (__int64)(*(i - 9) - *(v11 - 9)) > 0 )
                  {
                    *v14 = v11;
                    v14 = v11;
                    v11 = (_QWORD *)*v11;
                  }
                  else
                  {
                    *v14 = i;
                    v14 = i;
                    i = (_QWORD *)*i;
                  }
                }
                while ( i );
                v15 = i == 0;
              }
              if ( v15 )
                i = v11;
              *v14 = i;
              v10[1] = v13;
              v13[1] = v12;
              if ( !v12 )
                break;
              v10 = v13;
              i = v12;
            }
            while ( v12[1] );
          }
          *v85 = (__int64)i;
          for ( j = (__int64 **)(v2 + 123); i; i = (_QWORD *)*i )
          {
            i[1] = j;
            j = (__int64 **)i;
          }
          v17 = v96;
          *j = v85;
          v2[124] = j;
        }
      }
      v71->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v71->Next | 0x800);
      v18 = -1;
      v110 = -1;
LABEL_32:
      v19 = (__int64 *)*v85;
      v102 = v19;
      if ( v19 != v85 && v18 )
      {
        v20 = v19 - 9;
        if ( (v19[60] & 0x10) == 0 )
          goto LABEL_110;
        v21 = (__int64 *)*v19;
        if ( (__int64 *)*v19 == v85 )
        {
LABEL_109:
          v18 = v110;
LABEL_110:
          v77 = (__int64 *)*v19;
          if ( *(__int64 **)(*v19 + 8) != v19 || (v78 = (__int64 **)v19[1], *v78 != v19) )
            __fastfail(3u);
          *v78 = v77;
          v77[1] = (__int64)v78;
          --v18;
          v19[1] = 0;
          *v19 = 0;
          v79 = v20[12];
          v110 = v18;
          if ( (v20[69] & 0x40) != 0 )
          {
            CmsVolumeContainer::SetContainerStationaryVolatile(
              *(CmsVolumeContainer **)(*((_QWORD *)&v71->Next + 1) + 3272LL),
              (struct CmsTransactionContext *)v71,
              (union _LCN_TUPLE *)v20,
              0,
              0);
            _InterlockedAnd((volatile signed __int32 *)v20 + 138, 0xFFFFFFBF);
          }
          _InterlockedExchange64(v20 + 42, 0);
          if ( v20[43] )
            _InterlockedExchange64(v20 + 43, 1);
          _InterlockedAnd((volatile signed __int32 *)v20 + 138, 0xFFFF5FF7);
          v80 = 10;
          v81 = *(CmsVolume **)(*(_QWORD *)(v79 + 112) + 16LL);
          while ( 1 )
          {
            while ( 1 )
            {
              v82 = 0;
              v83 = v80;
              v84 = (_QWORD *)v20[38];
              if ( v84 )
                break;
LABEL_118:
              CmsVolume::UnpinInternal(v81, (struct CmsTransactionCore *)v71, (struct SmsPage *)v20, v80);
              v20 = v82;
              v80 = v83;
              if ( !v82 )
              {
                v85 = v106;
                goto LABEL_32;
              }
            }
            v86 = (int *)(v20 + 39);
            if ( (v80 & 1) != 0 && (v87 = *v86, *((_DWORD *)v20 + 96) == *v86) )
            {
              v88 = (int *)v20 + 79;
              v82 = (_QWORD *)v20[38];
              if ( (v80 & 4) == 0 )
                goto LABEL_139;
              v89 = *v88;
              if ( *((_DWORD *)v20 + 97) != *v88 )
              {
                v83 = v80 & 0xFFFFFFFB;
                goto LABEL_139;
              }
            }
            else
            {
              if ( (v80 & 4) == 0 )
                goto LABEL_118;
              v88 = (int *)v20 + 79;
              v89 = *((_DWORD *)v20 + 79);
              if ( *((_DWORD *)v20 + 97) != v89 )
                goto LABEL_118;
              v87 = *v86;
              v82 = (_QWORD *)v20[38];
            }
            *v88 = v89 - 1;
LABEL_139:
            *v86 = v87 - 1;
            if ( v87 != 1 )
              goto LABEL_118;
            v20[38] = 0;
            CmsVolume::UnpinInternal(v81, v17, (struct SmsPage *)v20, v80);
            v20 = v84;
            v80 = v83;
          }
        }
        v22 = *((_QWORD *)&v71->Next + 1);
        v23 = &v71->Next + 1;
        v24 = *((_DWORD *)v20 + 94);
        v25 = 1;
        v26 = v110;
        v98 = v22;
        v108 = v23;
        while ( 1 )
        {
          v112 = v26;
          if ( !v26 )
            goto LABEL_78;
          v27 = (volatile signed __int32 *)(v21 + 60);
          if ( (v21[60] & 0x30) != 0x10 )
            goto LABEL_78;
          if ( v20[14] )
            goto LABEL_78;
          v28 = v21 - 9;
          if ( v21[5] )
            goto LABEL_78;
          v29 = v20[13];
          if ( !v29 )
            goto LABEL_78;
          v30 = v28[13];
          if ( !v30 )
            goto LABEL_78;
          if ( v20[1] )
          {
            v56 = *v20;
            for ( k = 1; ; ++k )
            {
              ++v56;
              if ( k >= 4 )
                break;
              if ( v20[k] != v56 )
                goto LABEL_78;
            }
          }
          if ( v28[1] )
          {
            v54 = *v28;
            for ( m = 1; ; ++m )
            {
              ++v54;
              if ( m >= 4 )
                break;
              if ( v28[m] != v54 )
                goto LABEL_78;
            }
          }
          if ( ((*(_BYTE *)(*(_QWORD *)(v20[12] + 32) + 16LL) & 4) != 0) != ((*(_BYTE *)(*(_QWORD *)(v28[12] + 32) + 16LL)
                                                                            & 4) != 0)
            || v29 + (v24 << *(_DWORD *)(v22 + 64)) != v30
            || ((v30 ^ v29) & 0xFFFFFFFFFFFC0000uLL) != 0 )
          {
            goto LABEL_78;
          }
          v21 = (__int64 *)*v21;
          v31 = 400;
          v32 = *v20;
          if ( (*(_BYTE *)(*(_QWORD *)(v20[12] + 32) + 16LL) & 4) == 0 )
            v31 = 296;
          v33 = *v23 + v31;
          v111 = *((_DWORD *)v28 + 94);
          v99 = *v28;
          v15 = *(_BYTE *)(v33 + 48) == 0;
          *(_OWORD *)v101 = 0;
          v103 = 0;
          *(_OWORD *)v107 = 0;
          if ( !v15 )
          {
            v34 = *(unsigned int *)(*(_QWORD *)(v33 + 56) + 84LL);
            v32 = -v34 & ((unsigned __int64)v32 >> 1) | (unsigned int)v32 & ((_DWORD)v34 - 1);
          }
          v35 = CmsBlockCache::PrepareInstanceForCaching((CmsBlockCache *)v33, v32, &v101[1]);
          if ( v35 < 0 )
          {
            v41 = v103;
            v105 = v101[0];
          }
          else
          {
            v36 = *(_DWORD *)(v33 + 24);
            v37 = v32 >> v36;
            v105 = (struct _FILE_OBJECT *)(v32 - ((unsigned __int64)v37 << v36));
            v38 = ((unsigned __int64)(v37 + 1) << v36) - 1;
            v39 = v32 + v24;
            v40 = v38 - v32;
            v41 = v24;
            v42 = v40 + 1;
            if ( v39 > v38 )
              v41 = v42;
          }
          if ( v41 < v24 || v35 < 0 )
            goto LABEL_122;
          if ( *(_BYTE *)(v33 + 48) )
          {
            v43 = *(unsigned int *)(*(_QWORD *)(v33 + 56) + 84LL);
            v44 = -v43 & (v99 >> 1) | (unsigned int)v99 & ((_DWORD)v43 - 1);
          }
          else
          {
            v44 = v99;
          }
          v100 = v44;
          v45 = CmsBlockCache::PrepareInstanceForCaching((CmsBlockCache *)v33, v44, &v107[1]);
          if ( v45 < 0 )
          {
            v49 = v107[0];
            v47 = v111;
          }
          else
          {
            v46 = *(_DWORD *)(v33 + 24);
            v47 = v111;
            v41 = v111;
            v48 = v100 >> v46;
            v49 = (struct _FILE_OBJECT *)(v100 - ((unsigned __int64)v48 << v46));
            v50 = ((unsigned __int64)(v48 + 1) << v46) - 1;
            v51 = ((v48 + 1) << v46) - v100;
            if ( v100 + v111 > v50 )
              v41 = v51;
          }
          if ( v41 < v47 || v45 < 0 )
            break;
          v52 = v101[1];
          if ( v107[1] != v101[1] || (struct _FILE_OBJECT *)((char *)v105 + v24) != v49 )
          {
            if ( v107[1] )
              MsKmeDereferenceObject(v107[1]);
            if ( v52 )
            {
              v53 = v52;
              goto LABEL_69;
            }
            goto LABEL_97;
          }
          if ( v107[1] )
            MsKmeDereferenceObject(v107[1]);
          if ( v52 )
            MsKmeDereferenceObject(v52);
          v24 += *((_DWORD *)v28 + 94);
          ++v25;
          _InterlockedOr(v27, 0x20u);
          if ( v21 == v106 )
            goto LABEL_97;
          v26 = v112 - 1;
          v23 = v108;
          v22 = v98;
        }
        if ( v107[1] )
          MsKmeDereferenceObject(v107[1]);
LABEL_122:
        v53 = v101[1];
        if ( v101[1] )
LABEL_69:
          MsKmeDereferenceObject(v53);
LABEL_97:
        v22 = v98;
LABEL_78:
        if ( v25 > 1 )
        {
          v58 = v24 << *(_DWORD *)(v22 + 64);
          _InterlockedOr((volatile signed __int32 *)v20 + 138, 0x20u);
          v104.QuadPart = 0;
          v59 = v20[12];
          v60 = v22 + 400;
          *(_OWORD *)v101 = 0;
          if ( (*(_BYTE *)(*(_QWORD *)(v59 + 32) + 16LL) & 4) == 0 )
            v60 = v22 + 296;
          v61 = *(_DWORD *)(v22 + 64);
          MmSetAddressRangeModified((PVOID)v20[13], v58);
          if ( *(_BYTE *)(v60 + 48) )
          {
            v62 = *(unsigned int *)(*(_QWORD *)(v60 + 56) + 84LL);
            v63 = -v62 & ((unsigned __int64)*v20 >> 1) | (unsigned int)*v20 & ((_DWORD)v62 - 1);
          }
          else
          {
            v63 = *v20;
          }
          if ( (int)CmsBlockCache::PrepareInstanceForCaching((CmsBlockCache *)v60, v63, &v101[1]) >= 0 )
          {
            v64 = v58 >> v61;
            v65 = *(_DWORD *)(v60 + 24);
            v66 = v63 - ((unsigned __int64)(unsigned int)(v63 >> v65) << v65);
            if ( v63 + v64 <= (__int64)(((unsigned __int64)((unsigned int)(v63 >> v65) + 1) << v65) - 1) )
            {
              v67 = v64;
              goto LABEL_86;
            }
            v67 = (((unsigned int)(v63 >> v65) + 1) << v65) - v63;
            if ( v67 >= (unsigned int)v64 )
            {
LABEL_86:
              v68 = *(_DWORD *)(v22 + 64);
              v69 = v101[1];
              v70 = (__int64)v20;
              v104.QuadPart = v66 << v68;
              MsKmeFlushCache(v101[1], &v104, v67 << v68, 0);
              do
              {
                _InterlockedAnd((volatile signed __int32 *)(v70 + 552), 0xFFFFFFEF);
                v70 = *(_QWORD *)(v70 + 72) - 72LL;
                --v25;
              }
              while ( v25 );
              if ( v69 )
                MsKmeDereferenceObject(v69);
              v71 = v97;
              v17 = v96;
              goto LABEL_108;
            }
          }
          if ( v101[1] )
            MsKmeDereferenceObject(v101[1]);
        }
        v17 = v96;
        v71 = v97;
LABEL_108:
        v19 = v102;
        goto LABEL_109;
      }
      CmsTransactionContext::Commit((CmsTransactionContext *)v71, 0, 0, 0);
      v72 = *((_QWORD *)&v71->Next + 1);
      v73 = (__int64)v71->Next & 0x10000000;
      CmsTransactionContext::~CmsTransactionContext((CmsTransactionContext *)v71);
      if ( v73 )
      {
        CmsReservedPool::FreeToPool((CmsReservedPool *)(v72 + 160), v71);
        v2 = a1;
        goto LABEL_104;
      }
      Next = v71[-1].Next;
      if ( !Next )
        goto LABEL_162;
      if ( *((_BYTE *)&Next->Next + 8) )
      {
        v75 = (struct _PAGED_LOOKASIDE_LIST *)&Next[4];
        v76 = v71 - 1;
        if ( !*((_BYTE *)&Next->Next + 9) )
        {
          ExFreeToPagedLookasideList(v75, v76);
          v2 = a1;
          goto LABEL_104;
        }
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v75, v76);
        goto LABEL_103;
      }
      v95 = *((_QWORD *)&Next[5].Next + 1);
      if ( (int)v95 < SLODWORD(Next[5].Next) || SHIDWORD(v95) >= (int)v95 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)&Next[4], v71 - 1);
        _InterlockedIncrement((volatile signed __int32 *)&Next[5].Next + 2);
      }
      else
      {
LABEL_162:
        ExFreePoolWithTag(&v71[-1], 0);
      }
LABEL_103:
      v2 = a1;
      goto LABEL_104;
    }
    goto LABEL_9;
  }
  if ( (int)*(_QWORD *)(v3 + 88) > (int)HIDWORD(*(_QWORD *)(v3 + 88)) )
  {
    v8 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 88));
    if ( v8 >= *(_DWORD *)(v3 + 92) && v8 >= 0 )
    {
      v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v3 + 64));
      goto LABEL_149;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 88));
  }
LABEL_9:
  v5 = *(unsigned int *)(v3 + 4);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v5, 1766871885, v4);
  v7 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
  {
    CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(Pool2 + 16));
    goto LABEL_150;
  }
LABEL_104:
  KeSetEvent((PRKEVENT)v2 + 40, 0, 0);
}

```

## disassembly

```asm
0x140017870  mov     [rsp+arg_0], rcx
0x140017875  push    rbx
0x140017876  push    rbp
0x140017877  push    rsi
0x140017878  push    rdi
0x140017879  push    r12
0x14001787b  push    r13
0x14001787d  push    r14
0x14001787f  push    r15
0x140017881  sub     rsp, 0A8h
0x140017888  mov     rsi, [rcx]
0x14001788b  mov     r14, rcx
0x14001788e  xor     ecx, ecx; ProcNumber
0x140017890  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140017897  nop     dword ptr [rax+rax+00h]
0x14001789c  xor     edx, edx
0x14001789e  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400178a4  lea     rdi, [rdx+rdx*2]
0x1400178a8  shl     rdi, 6
0x1400178ac  add     rdi, cs:qword_140269408
0x1400178b3  cmp     dword ptr [rdi], 0DD0h
0x1400178b9  jnb     short loc_1400178F1
0x1400178bb  xor     edi, edi
0x1400178bd  mov     edx, 0DE0h
0x1400178c2  mov     ecx, 42h ; 'B'
0x1400178c7  mov     r8d, 6950534Dh
0x1400178cd  call    cs:__imp_ExAllocatePool2
0x1400178d4  nop     dword ptr [rax+rax+00h]
0x1400178d9  mov     rbx, rax
0x1400178dc  test    al, 0Fh
0x1400178de  jz      loc_1401F9752
0x1400178e4  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400178eb  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400178f1  cmp     byte ptr [rdi+8], 0
0x1400178f5  jnz     loc_14001829D
0x1400178fb  mov     rcx, [rdi+58h]
0x1400178ff  mov     rax, rcx
0x140017902  shr     rax, 20h
0x140017906  cmp     ecx, eax
0x140017908  jle     short loc_140017929
0x14001790a  nop
0x14001790b  mov     ecx, 0FFFFFFFFh
0x140017910  lock xadd [rdi+58h], ecx
0x140017915  nop
0x140017916  dec     ecx
0x140017918  mov     eax, [rdi+5Ch]
0x14001791b  cmp     ecx, eax
0x14001791d  jge     loc_1400182BD
0x140017923  nop
0x140017924  lock inc dword ptr [rdi+58h]
0x140017928  nop
0x140017929  mov     edx, [rdi+4]
0x14001792c  jmp     short loc_1400178C2
0x14001792e  mov     qword ptr [rdx], 0
0x140017935  mov     qword ptr [r10+8], 0
0x14001793d  mov     rdx, [rdi+8]
0x140017941  cmp     qword ptr [rdx+8], 0
0x140017946  jz      short loc_1400179C6
0x140017948  mov     rbx, rdi
0x14001794b  nop     dword ptr [rax+rax+00h]
0x140017950  mov     r8, [rdx+8]
0x140017954  mov     rcx, [rdx-48h]
0x140017958  sub     rcx, [r8-48h]
0x14001795c  mov     r11, [r8+8]
0x140017960  test    rcx, rcx
0x140017963  jle     loc_1400179F9
0x140017969  mov     r10, r8
0x14001796c  mov     r8, [r8]
0x14001796f  mov     r9, r10
0x140017972  test    rdx, rdx
0x140017975  jz      short loc_14001799A
0x140017977  test    r8, r8
0x14001797a  jz      short loc_140017997
0x14001797c  mov     rcx, [rdx-48h]
0x140017980  sub     rcx, [r8-48h]
0x140017984  test    rcx, rcx
0x140017987  jg      short loc_1400179EE
0x140017989  mov     [r9], rdx
0x14001798c  mov     r9, rdx
0x14001798f  mov     rdx, [rdx]
0x140017992  test    rdx, rdx
0x140017995  jnz     short loc_140017977
0x140017997  test    rdx, rdx
0x14001799a  cmovz   rdx, r8
0x14001799e  mov     [r9], rdx
0x1400179a1  mov     [rbx+8], r10
0x1400179a5  mov     [r10+8], r11
0x1400179a9  test    r11, r11
0x1400179ac  jz      short loc_1400179BB
0x1400179ae  cmp     qword ptr [r11+8], 0
0x1400179b3  mov     rbx, r10
0x1400179b6  mov     rdx, r11
0x1400179b9  jnz     short loc_140017950
0x1400179bb  mov     rdx, [rdi+8]
0x1400179bf  cmp     qword ptr [rdx+8], 0
0x1400179c4  jnz     short loc_140017948
0x1400179c6  mov     [rdi], rdx
0x1400179c9  mov     rax, rdi
0x1400179cc  test    rdx, rdx
0x1400179cf  jz      short loc_1400179E0
0x1400179d1  mov     [rdx+8], rax
0x1400179d5  mov     rax, rdx
0x1400179d8  mov     rdx, [rdx]
0x1400179db  test    rdx, rdx
0x1400179de  jnz     short loc_1400179D1
0x1400179e0  mov     r13, [rsp+0E8h+var_B8]
0x1400179e5  mov     [rax], rdi
0x1400179e8  mov     [rdi+8], rax
0x1400179ec  jmp     short loc_140017A0C
0x1400179ee  mov     [r9], r8
0x1400179f1  mov     r9, r8
0x1400179f4  mov     r8, [r8]
0x1400179f7  jmp     short loc_140017992
0x1400179f9  mov     r10, rdx
0x1400179fc  mov     rdx, [rdx]
0x1400179ff  jmp     loc_14001796F
0x140017a04  mov     [rsp+0E8h+var_B0], r12
0x140017a09  mov     r13, r12
0x140017a0c  or      qword ptr [r12], 800h
0x140017a14  mov     r15d, 0FFFFFFFFh
0x140017a1a  mov     [rsp+0E8h+arg_8], r15d
0x140017a22  mov     r10, [rdi]
0x140017a25  mov     r11d, 128h
0x140017a2b  mov     [rsp+0E8h+var_88], r10
0x140017a30  cmp     r10, rdi
0x140017a33  jz      loc_140017EE3
0x140017a39  test    r15d, r15d
0x140017a3c  jz      loc_140017EE3
0x140017a42  lea     rsi, [r10-48h]
0x140017a46  mov     eax, [rsi+228h]
0x140017a4c  test    al, 10h
0x140017a4e  jz      loc_140017FB0
0x140017a54  mov     r15, [r10]
0x140017a57  cmp     r15, rdi
0x140017a5a  jz      loc_140017FA8
0x140017a60  mov     r13, [r12+8]
0x140017a65  lea     r10, [r12+8]
0x140017a6a  mov     r12d, [rsi+178h]
0x140017a71  mov     edi, 1
0x140017a76  mov     eax, [rsp+0E8h+arg_8]
0x140017a7d  mov     [rsp+0E8h+var_A8], r13
0x140017a82  mov     [rsp+0E8h+var_50], r10
0x140017a8a  mov     [rsp+0E8h+arg_18], eax
0x140017a91  test    eax, eax
0x140017a93  jz      loc_140017D41
0x140017a99  lea     r14, [r15+1E0h]
0x140017aa0  mov     eax, [r14]
0x140017aa3  and     al, 30h
0x140017aa5  cmp     al, 10h
0x140017aa7  jnz     loc_140017D41
0x140017aad  cmp     qword ptr [rsi+70h], 0
0x140017ab2  jnz     loc_140017D41
0x140017ab8  cmp     qword ptr [r15+28h], 0
0x140017abd  lea     rbx, [r15-48h]
0x140017ac1  jnz     loc_140017D41
0x140017ac7  mov     rdx, [rsi+68h]
0x140017acb  test    rdx, rdx
0x140017ace  jz      loc_140017D41
0x140017ad4  mov     r8, [rbx+68h]
0x140017ad8  test    r8, r8
0x140017adb  jz      loc_140017D41
0x140017ae1  cmp     qword ptr [rsi+8], 0
0x140017ae6  jnz     loc_140017D1D
0x140017aec  cmp     qword ptr [rbx+8], 0
0x140017af1  jnz     loc_140017CF9
0x140017af7  mov     rax, [rsi+60h]
0x140017afb  mov     rcx, [rax+20h]
0x140017aff  mov     rax, [rbx+60h]
0x140017b03  movzx   r9d, byte ptr [rcx+10h]
0x140017b08  mov     rcx, [rax+20h]
0x140017b0c  shr     r9b, 2
0x140017b10  and     r9b, 1
0x140017b14  movzx   eax, byte ptr [rcx+10h]
0x140017b18  shr     al, 2
0x140017b1b  and     al, 1
0x140017b1d  cmp     r9b, al
0x140017b20  jnz     loc_140017D41
0x140017b26  mov     ecx, [r13+40h]
0x140017b2a  mov     eax, r12d
0x140017b2d  shl     eax, cl
0x140017b2f  mov     ecx, eax
0x140017b31  add     rcx, rdx
0x140017b34  cmp     rcx, r8
0x140017b37  jnz     loc_140017D41
0x140017b3d  xor     rdx, r8
0x140017b40  test    rdx, 0FFFFFFFFFFFC0000h
0x140017b47  jnz     loc_140017D41
0x140017b4d  mov     eax, [rbx+178h]
0x140017b53  test    r9b, r9b
0x140017b56  mov     r15, [r15]
0x140017b59  mov     r13d, 190h
0x140017b5f  mov     rbp, [rsi]
0x140017b62  cmovz   r13, r11
0x140017b66  add     r13, [r10]
0x140017b69  xorps   xmm0, xmm0
0x140017b6c  mov     [rsp+0E8h+arg_10], eax
0x140017b73  xorps   xmm1, xmm1
0x140017b76  mov     rax, [rbx]
0x140017b79  mov     [rsp+0E8h+var_A0], rax
0x140017b7e  cmp     byte ptr [r13+30h], 0
0x140017b83  movdqu  xmmword ptr [rsp+0E8h+var_98], xmm0
0x140017b89  mov     [rsp+0E8h+var_80], 0
0x140017b91  movdqu  xmmword ptr [rsp+0E8h+var_60], xmm1
0x140017b9a  jz      short loc_140017BBD
0x140017b9c  mov     rax, [r13+38h]
0x140017ba0  mov     edx, [rax+54h]
0x140017ba3  mov     eax, ebp
0x140017ba5  shr     rbp, 1
0x140017ba8  lea     ecx, [rdx-1]
0x140017bab  neg     rdx
0x140017bae  and     rcx, rax
0x140017bb1  mov     rax, rbp
0x140017bb4  and     rax, rdx
0x140017bb7  mov     rbp, rcx
0x140017bba  or      rbp, rax
0x140017bbd  lea     r8, [rsp+0E8h+var_98+8]; struct _FILE_OBJECT **
0x140017bc2  mov     rdx, rbp; __int64
0x140017bc5  mov     rcx, r13; this
0x140017bc8  call    ?PrepareInstanceForCaching@CmsBlockCache@@AEAAJ_JPEAPEAU_FILE_OBJECT@@@Z; CmsBlockCache::PrepareInstanceForCaching(__int64,_FILE_OBJECT * *)
0x140017bcd  mov     r8d, eax
0x140017bd0  test    eax, eax
0x140017bd2  js      loc_1400180CC
0x140017bd8  mov     ecx, [r13+18h]
0x140017bdc  mov     rdx, rbp
0x140017bdf  sar     rdx, cl
0x140017be2  mov     r9, rbp
0x140017be5  mov     eax, edx
0x140017be7  mov     edx, edx
0x140017be9  shl     rdx, cl
0x140017bec  sub     r9, rdx
0x140017bef  lea     edx, [rax+1]
0x140017bf2  mov     [rsp+0E8h+var_70], r9
0x140017bf7  shl     rdx, cl
0x140017bfa  dec     rdx
0x140017bfd  mov     ecx, r12d
0x140017c00  add     rcx, rbp
0x140017c03  mov     eax, edx
0x140017c05  sub     eax, ebp
0x140017c07  mov     ebp, r12d
0x140017c0a  inc     eax
0x140017c0c  cmp     rcx, rdx
0x140017c0f  cmovg   ebp, eax
0x140017c12  cmp     ebp, r12d
0x140017c15  jb      loc_1400180B9
0x140017c1b  test    r8d, r8d
0x140017c1e  js      loc_1400180B9
0x140017c24  cmp     byte ptr [r13+30h], 0
0x140017c29  jz      loc_140018143
0x140017c2f  mov     rax, [r13+38h]
0x140017c33  mov     r8, [rsp+0E8h+var_A0]
0x140017c38  mov     ecx, [rax+54h]
0x140017c3b  mov     eax, r8d
0x140017c3e  shr     r8, 1
0x140017c41  lea     edx, [rcx-1]
0x140017c44  neg     rcx
0x140017c47  and     r8, rcx
0x140017c4a  and     rdx, rax
0x140017c4d  or      rdx, r8; __int64
0x140017c50  lea     r8, [rsp+0E8h+var_60+8]; struct _FILE_OBJECT **
0x140017c58  mov     [rsp+0E8h+var_A0], rdx
0x140017c5d  mov     rcx, r13; this
0x140017c60  call    ?PrepareInstanceForCaching@CmsBlockCache@@AEAAJ_JPEAPEAU_FILE_OBJECT@@@Z; CmsBlockCache::PrepareInstanceForCaching(__int64,_FILE_OBJECT * *)
0x140017c65  mov     r9d, eax
0x140017c68  test    eax, eax
0x140017c6a  js      loc_1400180DF
0x140017c70  mov     r8, [rsp+0E8h+var_A0]
0x140017c75  mov     ecx, [r13+18h]
0x140017c79  mov     rdx, r8
0x140017c7c  mov     r11d, [rsp+0E8h+arg_10]
0x140017c84  mov     r10, r8
0x140017c87  sar     rdx, cl
0x140017c8a  mov     ebp, r11d
0x140017c8d  mov     eax, edx
0x140017c8f  mov     edx, edx
0x140017c91  shl     rdx, cl
0x140017c94  sub     r10, rdx
0x140017c97  lea     edx, [rax+1]
0x140017c9a  shl     rdx, cl
0x140017c9d  lea     rcx, [r8+r11]
0x140017ca1  dec     rdx
0x140017ca4  mov     eax, edx
0x140017ca6  sub     eax, r8d
0x140017ca9  inc     eax
0x140017cab  cmp     rcx, rdx
0x140017cae  cmovg   ebp, eax
0x140017cb1  cmp     ebp, r11d
0x140017cb4  jb      loc_1400180A7
0x140017cba  test    r9d, r9d
0x140017cbd  js      loc_1400180A7
0x140017cc3  mov     rcx, [rsp+0E8h+var_60+8]; struct _FILE_OBJECT *
0x140017ccb  mov     rbp, [rsp+0E8h+var_98+8]
0x140017cd0  cmp     rcx, rbp
0x140017cd3  jz      loc_140017E7F
0x140017cd9  test    rcx, rcx
0x140017cdc  jz      short loc_140017CE3
0x140017cde  call    ?MsKmeDereferenceObject@@YAXPEAU_FILE_OBJECT@@@Z; MsKmeDereferenceObject(_FILE_OBJECT *)
0x140017ce3  test    rbp, rbp
0x140017ce6  jz      loc_140017ED9
0x140017cec  mov     rcx, rbp; struct _FILE_OBJECT *
0x140017cef  call    ?MsKmeDereferenceObject@@YAXPEAU_FILE_OBJECT@@@Z; MsKmeDereferenceObject(_FILE_OBJECT *)
  ... truncated ...
```
