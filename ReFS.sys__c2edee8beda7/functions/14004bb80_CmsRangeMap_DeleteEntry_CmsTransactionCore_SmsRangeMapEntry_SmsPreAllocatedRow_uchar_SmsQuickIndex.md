# CmsRangeMap::DeleteEntry(CmsTransactionCore *,SmsRangeMapEntry *,_SmsPreAllocatedRow *,uchar,_SmsQuickIndex *)

- ea: `0x14004bb80`
- end: `0x14004c56f`
- name: `?DeleteEntry@CmsRangeMap@@UEAAJPEAVCmsTransactionCore@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@EPEAU_SmsQuickIndex@@@Z`
- size: `2543`
- prototype: `__int64 __fastcall(CmsRangeMap *__hidden this, struct CmsTransactionCore *, struct SmsRangeMapEntry *, struct _SmsPreAllocatedRow *, unsigned __int8, struct _SmsQuickIndex *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x14004b5b0`
- `0x14004b8d0`
- `0x14004bb80`
- `0x14004c580`
- `0x14004dd04`
- `0x1400ceda0`
- `0x1401f3fc0`
- `0x1401f40a0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c4c4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c4c4`
- `ntoskrnl!ExAllocatePool2` at `0x14004bf19`
- `ntoskrnl!ExAllocatePool2` at `0x14004c074`
- `ntoskrnl!ExAllocatePool2` at `0x14004bf19`
- `ntoskrnl!ExAllocatePool2` at `0x14004c074`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004bed7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004bed7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd26a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd26a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004c4e1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004c4e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bdb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bf85`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bdb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bf85`

## string_xrefs

- `0x14004bf30`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeMap::DeleteEntry(
        CmsRangeMap *this,
        struct CmsTransactionCore *a2,
        struct SmsRangeMapEntry *a3,
        unsigned __int64 a4,
        unsigned __int8 a5,
        struct _SmsQuickIndex *a6)
{
  struct _SmsPreAllocatedRow *v6; // rdi
  _BYTE *v8; // r8
  struct SmsRangeMapEntry *v10; // rdx
  __m128i v11; // xmm6
  __int128 v12; // xmm7
  _QWORD *v13; // rsi
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  _QWORD *v18; // r8
  unsigned __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rbx
  unsigned int v23; // r12d
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  char *v27; // rdi
  __int64 v29; // r13
  unsigned __int64 v30; // rdx
  __int64 v31; // r13
  bool v32; // zf
  __int64 v33; // r9
  unsigned int *v34; // r13
  __int64 v35; // rdx
  __int64 v36; // rax
  PSLIST_ENTRY v37; // rdi
  unsigned __int64 v38; // rdx
  unsigned __int64 *v39; // rax
  __int64 v40; // rax
  __int128 v41; // xmm0
  unsigned __int64 *v42; // rax
  struct _SmsPreAllocatedRow *v43; // r8
  char v44; // r11
  __int64 v45; // rax
  struct _RTL_AVL_ENTRY *v46; // r10
  __int128 v47; // xmm1
  __int16 v48; // r13
  unsigned __int64 v49; // rdi
  int v50; // r9d
  unsigned int v51; // edx
  unsigned int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rax
  char *v55; // rcx
  char *v56; // rcx
  struct CmsTransactionCore *v57; // r11
  char *v58; // rax
  __int64 v59; // rcx
  struct _RTL_AVL_ENTRY **v60; // rdx
  unsigned __int64 v61; // rdx
  unsigned __int64 *v62; // rax
  CmsRangeMap *v63; // r15
  _QWORD *v64; // rsi
  _OWORD *v65; // rax
  _OWORD *v66; // rcx
  struct _SmsPreAllocatedRow *v67; // rax
  unsigned __int64 v68; // rax
  int v69; // ecx
  unsigned __int64 v70; // rdx
  unsigned __int64 *v71; // rax
  unsigned __int64 v72; // rax
  struct _NPAGED_LOOKASIDE_LIST *v73; // rcx
  struct _SLIST_ENTRY *v74; // rax
  unsigned __int64 i; // rdx
  char v76; // al
  char v77; // cl
  char v78; // [rsp+20h] [rbp-E0h]
  __int64 v79; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+28h] [rbp-D8h]
  int v82; // [rsp+38h] [rbp-C8h]
  char *v83; // [rsp+38h] [rbp-C8h]
  __m128i v84; // [rsp+40h] [rbp-C0h]
  __m128i v85; // [rsp+40h] [rbp-C0h]
  __m128i v86; // [rsp+40h] [rbp-C0h]
  __int128 v87; // [rsp+50h] [rbp-B0h]
  __int64 Pool2; // [rsp+68h] [rbp-98h]
  __int128 v90; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-78h]
  __int128 v92; // [rsp+98h] [rbp-68h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h]
  struct _SmsPreAllocatedRow *v94; // [rsp+B0h] [rbp-50h]
  int v95; // [rsp+C0h] [rbp-40h]
  __int16 epi16; // [rsp+C4h] [rbp-3Ch]
  __int16 v97; // [rsp+C6h] [rbp-3Ah]
  unsigned __int64 v98; // [rsp+C8h] [rbp-38h]
  int v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+D4h] [rbp-2Ch]
  _QWORD *v101; // [rsp+D8h] [rbp-28h]
  PVOID P; // [rsp+E0h] [rbp-20h]
  unsigned __int8 v103; // [rsp+E8h] [rbp-18h]
  int v104; // [rsp+ECh] [rbp-14h]
  _BYTE v105[32]; // [rsp+F0h] [rbp-10h] BYREF

  v94 = (struct _SmsPreAllocatedRow *)a4;
  v6 = (struct _SmsPreAllocatedRow *)a4;
  LOBYTE(a4) = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v8 = v105;
  v97 = 0;
  v90 = 0;
  v100 = HIDWORD(v94);
  v95 = 0;
  v98 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  P = v105;
  v104 = 32;
  v99 = 0;
  v101 = 0;
  v103 = 0;
  v92 = 0u;
  v93 = 0;
  v87 = 0;
  if ( v6 )
  {
    *(_OWORD *)*((_QWORD *)v6 + 1) = *(_OWORD *)a3;
    v40 = *((_QWORD *)v6 + 3);
    *(_OWORD *)v40 = *(_OWORD *)a3;
    *(_QWORD *)(v40 + 16) = *((_QWORD *)a3 + 2);
    v10 = (struct SmsRangeMapEntry *)*((_QWORD *)v6 + 1);
    v41 = *((_OWORD *)v6 + 1);
    a4 = v103;
    v8 = P;
    v90 = *(_OWORD *)v6;
    *(_OWORD *)Src = v41;
  }
  else
  {
    v10 = a3;
    LODWORD(v90) = 16;
    *((_QWORD *)&v90 + 1) = a3;
    Src[1] = a3;
    LODWORD(Src[0]) = 24;
  }
  if ( a6 )
  {
    v11 = *(__m128i *)a6;
    v12 = *((_OWORD *)a6 + 1);
    *((_QWORD *)&v87 + 1) = *((_QWORD *)&v12 + 1);
    if ( *(_QWORD *)a6 )
      v13 = (_QWORD *)(*(_QWORD *)a6 + *(unsigned __int8 *)(*(_QWORD *)a6 + 26LL));
    else
      v13 = 0;
    v14 = (_QWORD *)*((_QWORD *)a6 + 1);
    if ( v14 )
    {
      if ( ((*((_DWORD *)a6 + 4) - 1) & 0xFFFFFFFD) != 0 )
        goto LABEL_14;
      v15 = (_QWORD *)v14[2];
      if ( v15 )
      {
        for ( ; v15[1]; v15 = (_QWORD *)v15[1] )
          ;
        v14 = v15;
      }
      else
      {
        v16 = (_QWORD *)*v14;
        if ( *(_QWORD **)(*v14 + 16LL) == v14 )
        {
          do
          {
            v17 = (_QWORD *)*v16;
            v18 = v16;
            v16 = v17;
          }
          while ( (_QWORD *)v17[2] == v18 );
        }
        else
        {
          v17 = (_QWORD *)*v14;
          v18 = (_QWORD *)*((_QWORD *)a6 + 1);
        }
        v14 = 0;
        if ( (_QWORD *)v17[1] == v18 )
          v14 = v17;
      }
      if ( v14 )
      {
LABEL_14:
        *((_DWORD *)a6 + 4) = 1;
        *((_QWORD *)a6 + 1) = v14;
        v95 = *((unsigned __int8 *)v14 + 27);
        v19 = (unsigned __int64)v14 + *((unsigned __int8 *)v14 + 26);
        epi16 = 0;
        v98 = v19;
        v99 = *((unsigned __int16 *)v14 + 15);
        v20 = *((unsigned __int8 *)v14 + 26);
        *(_QWORD *)a6 = v14;
        v101 = (_QWORD *)((char *)v14 + v20);
LABEL_15:
        v82 = v12;
        v21 = v11.m128i_i64[0];
        v22 = _mm_srli_si128(v11, 8).m128i_u64[0];
        goto LABEL_16;
      }
      *((_QWORD *)a6 + 1) = 0;
    }
    *(_QWORD *)a6 = 0;
    goto LABEL_15;
  }
  v22 = *((_QWORD *)this + 3);
  if ( !v22 )
  {
LABEL_43:
    if ( (a4 & 1) != 0 && v8 )
      ExFreePoolWithTag(v8, 0);
    return 3221225524LL;
  }
  v38 = *(_QWORD *)v10;
  while ( 1 )
  {
    v39 = (unsigned __int64 *)(v22 + *(unsigned __int8 *)(v22 + 26));
    if ( v38 < *v39 )
    {
      v22 = *(_QWORD *)(v22 + 8);
      goto LABEL_42;
    }
    v21 = v22;
    if ( v38 < v39[1] + *v39 )
      break;
    v22 = *(_QWORD *)(v22 + 16);
LABEL_42:
    if ( !v22 )
      goto LABEL_43;
  }
  v6 = v94;
  v95 = *(unsigned __int8 *)(v22 + 27);
  v72 = v22 + *(unsigned __int8 *)(v22 + 26);
  epi16 = 0;
  v98 = v72;
  v99 = *(unsigned __int16 *)(v22 + 30);
  v13 = (_QWORD *)(v22 + *(unsigned __int8 *)(v22 + 26));
  v86.m128i_i64[0] = v22;
  LODWORD(v87) = 1;
  v86.m128i_i64[1] = v22;
  v11 = v86;
  DWORD1(v87) = *((_DWORD *)this + 12);
  v12 = v87;
  v101 = v13;
  v82 = 1;
LABEL_16:
  v23 = 0;
  v24 = *v13;
  v25 = *((_QWORD *)a3 + 1);
  if ( *v13 != *(_QWORD *)a3 )
  {
    v29 = v13[1];
    v30 = *(_QWORD *)a3 + v25;
    ++*((_DWORD *)this + 11);
    v31 = v24 + v29;
    v79 = v31;
    if ( v31 == v30 )
    {
      v13[1] -= *((_QWORD *)a3 + 1);
      goto LABEL_19;
    }
    v13[1] = *(_QWORD *)a3 - *v13;
    *(_QWORD *)&v92 = v30;
    v32 = *((_BYTE *)this + 56) == 0;
    *((_QWORD *)&v92 + 1) = v31 - v30;
    if ( v32 )
      v93 = v13[2] + v30 - *v13;
    else
      v93 = v13[2];
    if ( v6 )
    {
      v42 = (unsigned __int64 *)*((_QWORD *)v6 + 1);
      v43 = v6;
      v44 = 0;
      *v42 = v30;
      v42[1] = v31 - v30;
      v45 = *((_QWORD *)v6 + 3);
      *(_OWORD *)v45 = v92;
      *(_QWORD *)(v45 + 16) = v93;
      v46 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v6 + 4);
      v47 = *((_OWORD *)v6 + 1);
      Pool2 = (__int64)v46;
      v90 = *(_OWORD *)v6;
      *(_OWORD *)Src = v47;
      goto LABEL_61;
    }
    LODWORD(v90) = 16;
    *((_QWORD *)&v90 + 1) = &v92;
    Src[1] = &v92;
    LODWORD(Src[0]) = 24;
    if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x38 )
    {
      Pool2 = ExAllocatePool2(66, 56, 1766871885, a4);
      v37 = (PSLIST_ENTRY)Pool2;
      if ( Pool2 )
      {
        v48 = 0x8000;
LABEL_60:
        *((_WORD *)&v37[1].Next + 6) = 0;
        memmove(&v37[2], Src[1], LODWORD(Src[0]));
        v46 = (struct _RTL_AVL_ENTRY *)Pool2;
        v43 = (struct _SmsPreAllocatedRow *)&v90;
        *((_WORD *)&v37[1].Next + 5) = 4128;
        v44 = 1;
        *((_WORD *)&v37[1].Next + 6) |= v48;
        v31 = v79;
        *((_WORD *)&v37[1].Next + 7) = 24;
LABEL_61:
        v49 = 0;
        v50 = 2;
        v78 = v44;
        v80 = 2;
        v51 = *((unsigned __int8 *)a2 + 96);
        v52 = 5;
        if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
          v52 = 2;
        if ( v51 < v52 )
        {
          v53 = (unsigned __int8)(v51 + 1);
          v54 = 5 * v53;
          *((_BYTE *)a2 + 96) = v53;
          if ( (unsigned __int8)v53 <= 2u )
            v55 = (char *)a2 - 24;
          else
            v55 = (char *)a2 + 784;
          v56 = &v55[8 * v54];
          *(_QWORD *)v56 = v43;
          *((_WORD *)v56 + 16) = 0;
          *((_QWORD *)v56 + 1) = &CmsRangeMap::PropertyDef;
          *((_QWORD *)v56 + 2) = &off_140207A20;
          LOBYTE(v51) = *((_BYTE *)a2 + 96);
        }
        v32 = v44 == 0;
        v57 = a2;
        if ( !v32 )
        {
          if ( (unsigned __int8)v51 <= 2u )
            v58 = (char *)a2 + 9;
          else
            v58 = (char *)a2 + 817;
          v58[40 * (unsigned __int8)v51] = 1;
        }
        v59 = *((unsigned __int8 *)a2 + 96);
        v60 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v59);
        if ( (unsigned __int8)v59 > 2u )
          v60 += 101;
        *v60 = v46;
        if ( v22 )
        {
          if ( !v21 )
          {
            v63 = this;
            v49 = v22;
            v50 = v82;
            v80 = v82;
            v64 = (_QWORD *)((char *)this + 24);
            goto LABEL_87;
          }
          v83 = (char *)this + 24;
          if ( *((_QWORD *)this + 3) )
          {
            v49 = v21;
            v61 = **((_QWORD **)v43 + 1);
            while ( 1 )
            {
              while ( 1 )
              {
                v62 = v49 ? (unsigned __int64 *)(v49 + *(unsigned __int8 *)(v49 + 26)) : 0LL;
                if ( v61 >= *v62 )
                  break;
                if ( !*(_QWORD *)(v49 + 8) )
                  goto LABEL_93;
                v49 = *(_QWORD *)(v49 + 8);
              }
              if ( v61 < v62[1] + *v62 )
                break;
              if ( !*(_QWORD *)(v49 + 16) )
              {
                v63 = this;
                v50 = 3;
                v80 = 3;
                v68 = 0;
                goto LABEL_98;
              }
              v49 = *(_QWORD *)(v49 + 16);
            }
            v50 = 1;
            v68 = v49;
            v80 = 1;
          }
          else
          {
            v50 = 0;
            v80 = 0;
LABEL_93:
            v68 = 0;
          }
          v63 = this;
        }
        else
        {
          v63 = this;
          v83 = (char *)this + 24;
          if ( *((_QWORD *)this + 3) )
          {
            v49 = *((_QWORD *)this + 3);
            v70 = **((_QWORD **)v43 + 1);
            while ( 1 )
            {
              while ( 1 )
              {
                v71 = v49 ? (unsigned __int64 *)(v49 + *(unsigned __int8 *)(v49 + 26)) : 0LL;
                if ( v70 >= *v71 )
                  break;
                if ( !*(_QWORD *)(v49 + 8) )
                  goto LABEL_96;
                v49 = *(_QWORD *)(v49 + 8);
              }
              if ( v70 < v71[1] + *v71 )
                break;
              if ( !*(_QWORD *)(v49 + 16) )
              {
                v50 = 3;
                goto LABEL_96;
              }
              v49 = *(_QWORD *)(v49 + 16);
            }
            v50 = 1;
            v68 = v49;
          }
          else
          {
            v50 = 0;
LABEL_96:
            v68 = 0;
          }
          v80 = v50;
        }
LABEL_98:
        if ( v68 )
        {
          v85.m128i_i64[0] = v68;
          v85.m128i_i64[1] = v68;
          DWORD1(v87) = *((_DWORD *)v63 + 12);
          LODWORD(v87) = 3;
          --*((_BYTE *)a2 + 96);
          if ( v46 && v78 )
            CmsAvlTableLite::FreeIndexEntry(v46);
          v12 = v87;
          v23 = -1073741771;
          v11 = v85;
          goto LABEL_101;
        }
        v64 = v83;
        v57 = a2;
LABEL_87:
        ++*((_DWORD *)v63 + 12);
        if ( v50 != 1 )
        {
          v65 = (_OWORD *)((__int64 (__fastcall *)(char *, _QWORD, struct CmsTransactionCore *))qword_1402692F0)(
                            (char *)v63 + 8,
                            0,
                            v57);
          v66 = v65;
          if ( v65 )
          {
            *v65 = 0;
            *(_OWORD *)((char *)v65 + 10) = 0;
            ++*((_DWORD *)v63 + 10);
            if ( v80 )
            {
              if ( v80 == 2 )
                *(_QWORD *)(v49 + 8) = v65;
              else
                *(_QWORD *)(v49 + 16) = v65;
              *(_QWORD *)v65 = v49;
              *((_BYTE *)v63 + 32) = -1;
              for ( i = *(_QWORD *)v65; ; v49 = i )
              {
                v32 = *(_QWORD *)(i + 8) == (_QWORD)v66;
                v76 = -1;
                v77 = *(_BYTE *)(v49 + 24);
                if ( !v32 )
                  v76 = 1;
                if ( v77 )
                  break;
                i = *(_QWORD *)v49;
                v66 = (_OWORD *)v49;
                *(_BYTE *)(v49 + 24) = v76;
              }
              if ( v77 == v76 )
                RebalanceNode((struct _RTL_AVL_ENTRY *)v49);
              else
                *(_BYTE *)(v49 + 24) = 0;
            }
            else
            {
              *v64 = v65;
              *(_QWORD *)v65 = (char *)v63 + 8;
            }
          }
          v46 = (struct _RTL_AVL_ENTRY *)Pool2;
        }
        DWORD1(v87) = *((_DWORD *)v63 + 12);
        v67 = v94;
        v84.m128i_i64[0] = (__int64)v46;
        --*((_BYTE *)a2 + 96);
        v84.m128i_i64[1] = (__int64)v46;
        LODWORD(v87) = 1;
        v12 = v87;
        v11 = v84;
        if ( v67 )
          *((_QWORD *)v67 + 4) = 0;
LABEL_102:
        if ( a6 )
          goto LABEL_26;
        goto LABEL_19;
      }
LABEL_144:
      v63 = this;
      v23 = -1073741670;
LABEL_101:
      v13[1] = v31 - *v13;
      --*((_DWORD *)v63 + 11);
      goto LABEL_102;
    }
    if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 < 0x38 )
    {
      v37 = CmsLookasides::Allocate(0x38u, 0xCu, 0);
      v48 = 0x4000;
LABEL_109:
      if ( v37 )
      {
        Pool2 = (__int64)v37;
        goto LABEL_60;
      }
      v31 = v79;
      goto LABEL_144;
    }
    v34 = (unsigned int *)(qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( *v34 < 0x38uLL )
    {
      v34 = 0;
      v35 = 72;
      goto LABEL_35;
    }
    if ( !*((_BYTE *)v34 + 8) )
    {
      if ( (int)*((_QWORD *)v34 + 11) > (int)HIDWORD(*((_QWORD *)v34 + 11)) )
      {
        v69 = _InterlockedDecrement((volatile signed __int32 *)v34 + 22);
        if ( v69 >= (int)v34[23] && v69 >= 0 )
        {
          v74 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34 + 4);
          goto LABEL_106;
        }
        _InterlockedIncrement((volatile signed __int32 *)v34 + 22);
      }
LABEL_115:
      v35 = v34[1];
LABEL_35:
      v36 = ExAllocatePool2(66, v35, 1766871885, v33);
      v37 = (PSLIST_ENTRY)v36;
      if ( (v36 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !v36 )
        goto LABEL_108;
      goto LABEL_107;
    }
    v73 = (struct _NPAGED_LOOKASIDE_LIST *)(v34 + 16);
    if ( *((_BYTE *)v34 + 9) )
      v74 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v73);
    else
      v74 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v73);
LABEL_106:
    v37 = v74;
    if ( v74 )
    {
LABEL_107:
      v37->Next = (struct _SLIST_ENTRY *)v34;
      ++v37;
LABEL_108:
      v48 = 0x2000;
      goto LABEL_109;
    }
    goto LABEL_115;
  }
  v26 = v13[1];
  if ( v26 <= v25 )
  {
    ++*((_DWORD *)this + 11);
    v27 = (char *)this + 8;
    DeleteNodeFromTree((CmsRangeMap *)((char *)this + 8), (struct _RTL_AVL_ENTRY *)v22, 1u);
    --*((_DWORD *)v27 + 8);
    CmsAvlTableLite::FreeIndexEntry((struct _RTL_AVL_ENTRY *)v22);
    ++*((_DWORD *)v27 + 10);
    goto LABEL_19;
  }
  *v13 = v24 + v25;
  v13[1] = v26 - v25;
  if ( !*((_BYTE *)this + 56) )
    v13[2] += v25;
  ++*((_DWORD *)this + 11);
  if ( a6 )
  {
LABEL_26:
    *(__m128i *)a6 = v11;
    *((_OWORD *)a6 + 1) = v12;
  }
LABEL_19:
  if ( (v103 & 1) != 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  return v23;
}

```

## disassembly

```asm
0x14004bb80  push    rbp
0x14004bb82  push    rdi
0x14004bb83  push    r12
0x14004bb85  push    r13
0x14004bb87  push    r14
0x14004bb89  lea     rbp, [rsp-50h]
0x14004bb8e  sub     rsp, 150h
0x14004bb95  mov     rax, cs:__security_cookie
0x14004bb9c  xor     rax, rsp
0x14004bb9f  mov     [rbp+70h+var_60], rax
0x14004bba3  mov     r14, [rbp+70h+arg_28]
0x14004bbaa  xorps   xmm0, xmm0
0x14004bbad  pextrw  eax, xmm0, 2
0x14004bbb2  xor     r13d, r13d
0x14004bbb5  mov     [rbp+70h+var_C0], r9
0x14004bbb9  movups  [rsp+170h+var_108], xmm0
0x14004bbbe  mov     rdi, r9
0x14004bbc1  xor     r9b, r9b
0x14004bbc4  mov     [rbp+70h+var_AC], ax
0x14004bbc8  mov     r10, r8
0x14004bbcb  movzx   eax, word ptr [rsp+170h+var_108+6]
0x14004bbd0  lea     r8, [rbp+70h+var_80]
0x14004bbd4  mov     [rbp+70h+var_AA], ax
0x14004bbd8  mov     r11, rcx
0x14004bbdb  mov     eax, dword ptr [rbp+70h+var_C0+4]
0x14004bbde  movups  [rsp+170h+var_F8], xmm0
0x14004bbe3  mov     [rbp+70h+var_9C], eax
0x14004bbe6  xor     eax, eax
0x14004bbe8  movss   [rbp+70h+var_B0], xmm0
0x14004bbed  psrldq  xmm0, 8
0x14004bbf2  movq    [rbp+70h+var_A8], xmm0
0x14004bbf7  xorps   xmm0, xmm0
0x14004bbfa  mov     [rsp+170h+var_140], rdx
0x14004bbff  mov     [rsp+170h+var_110], rcx
0x14004bc04  mov     [rbp+70h+P], r8
0x14004bc08  mov     [rbp+70h+var_84], 20h ; ' '
0x14004bc0f  mov     [rbp+70h+var_A0], r13d
0x14004bc13  mov     [rbp+70h+var_98], r13
0x14004bc17  mov     [rbp+70h+var_88], r9b
0x14004bc1b  mov     qword ptr [rbp+70h+var_D8], r13
0x14004bc1f  mov     qword ptr [rbp+70h+var_D8+8], r13
0x14004bc23  mov     [rbp+70h+var_C8], rax
0x14004bc27  movups  [rsp+170h+var_130], xmm0
0x14004bc2c  movups  [rsp+170h+var_120], xmm0
0x14004bc31  test    rdi, rdi
0x14004bc34  jnz     loc_14004BFE2
0x14004bc3a  mov     rdx, r10
0x14004bc3d  mov     dword ptr [rsp+170h+var_F8], 10h
0x14004bc45  mov     qword ptr [rbp+70h+var_F8+8], rdx
0x14004bc49  mov     [rbp+70h+Src+8], r10
0x14004bc4d  mov     dword ptr [rbp+70h+Src], 18h
0x14004bc54  mov     [rsp+170h+arg_10], rbx
0x14004bc5c  mov     r12d, 1
0x14004bc62  mov     [rsp+170h+var_28], rsi
0x14004bc6a  mov     [rsp+170h+var_30], r15
0x14004bc72  movaps  [rsp+170h+var_40], xmm6
0x14004bc7a  movaps  [rsp+170h+var_50], xmm7
0x14004bc82  test    r14, r14
0x14004bc85  jz      loc_14004BF3D
0x14004bc8b  movups  xmm6, xmmword ptr [r14]
0x14004bc8f  mov     rax, [r14]
0x14004bc92  movups  xmm7, xmmword ptr [r14+10h]
0x14004bc97  movups  [rsp+170h+var_130], xmm6
0x14004bc9c  movups  [rsp+170h+var_120], xmm7
0x14004bca1  test    rax, rax
0x14004bca4  jz      loc_14004BFC1
0x14004bcaa  movzx   esi, byte ptr [rax+1Ah]
0x14004bcae  add     rsi, rax
0x14004bcb1  mov     rcx, [r14+8]
0x14004bcb5  test    rcx, rcx
0x14004bcb8  jz      loc_14004BFDA
0x14004bcbe  mov     eax, [r14+10h]
0x14004bcc2  dec     eax
0x14004bcc4  test    eax, 0FFFFFFFDh
0x14004bcc9  jnz     short loc_14004BD08
0x14004bccb  mov     rax, [rcx+10h]
0x14004bccf  test    rax, rax
0x14004bcd2  jnz     loc_14004BFA9
0x14004bcd8  mov     rax, [rcx]
0x14004bcdb  cmp     [rax+10h], rcx
0x14004bcdf  jnz     loc_14004BF9E
0x14004bce5  mov     rdx, [rax]
0x14004bce8  mov     r8, rax
0x14004bceb  mov     rax, rdx
0x14004bcee  cmp     [rdx+10h], r8
0x14004bcf2  jz      short loc_14004BCE5
0x14004bcf4  cmp     [rdx+8], r8
0x14004bcf8  mov     rcx, r13
0x14004bcfb  cmovz   rcx, rdx
0x14004bcff  test    rcx, rcx
0x14004bd02  jz      loc_14004BFD6
0x14004bd08  mov     [r14+10h], r12d
0x14004bd0c  mov     [r14+8], rcx
0x14004bd10  movzx   eax, byte ptr [rcx+1Bh]
0x14004bd14  mov     [rbp+70h+var_B0], eax
0x14004bd17  movzx   eax, byte ptr [rcx+1Ah]
0x14004bd1b  add     rax, rcx
0x14004bd1e  mov     [rbp+70h+var_AC], r13w
0x14004bd23  mov     [rbp+70h+var_A8], rax
0x14004bd27  movzx   eax, word ptr [rcx+1Eh]
0x14004bd2b  mov     [rbp+70h+var_A0], eax
0x14004bd2e  movzx   eax, byte ptr [rcx+1Ah]
0x14004bd32  add     rax, rcx
0x14004bd35  mov     [r14], rcx
0x14004bd38  mov     [rbp+70h+var_98], rax
0x14004bd3c  movdqa  xmm0, xmm6
0x14004bd40  movss   dword ptr [rsp+170h+var_138], xmm7
0x14004bd46  psrldq  xmm0, 8
0x14004bd4b  movq    r15, xmm6
0x14004bd50  movq    rbx, xmm0
0x14004bd55  mov     rcx, [r10]
0x14004bd58  mov     r12d, r13d
0x14004bd5b  mov     r8, [rsi]
0x14004bd5e  mov     rdx, [r10+8]
0x14004bd62  cmp     r8, rcx
0x14004bd65  jnz     loc_14004BE39
0x14004bd6b  mov     rcx, [rsi+8]
0x14004bd6f  cmp     rcx, rdx
0x14004bd72  ja      loc_14004BE06
0x14004bd78  inc     dword ptr [r11+2Ch]
0x14004bd7c  lea     rdi, [r11+8]
0x14004bd80  mov     rcx, rdi; struct _MS_AVL_TABLE *
0x14004bd83  mov     r8b, 1; unsigned __int8
0x14004bd86  mov     rdx, rbx; struct _RTL_AVL_ENTRY *
0x14004bd89  call    ?DeleteNodeFromTree@@YAXPEAU_MS_AVL_TABLE@@PEAU_RTL_AVL_ENTRY@@E@Z; DeleteNodeFromTree(_MS_AVL_TABLE *,_RTL_AVL_ENTRY *,uchar)
0x14004bd8e  mov     eax, [rdi+20h]
0x14004bd91  mov     rcx, rbx; struct _RTL_AVL_ENTRY *
0x14004bd94  dec     eax
0x14004bd96  mov     [rdi+20h], eax
0x14004bd99  call    ?FreeIndexEntry@CmsAvlTableLite@@CAXPEAU_RTL_AVL_ENTRY@@@Z; CmsAvlTableLite::FreeIndexEntry(_RTL_AVL_ENTRY *)
0x14004bd9e  inc     dword ptr [rdi+28h]
0x14004bda1  test    [rbp+70h+var_88], 1
0x14004bda5  jz      short loc_14004BDBE
0x14004bda7  mov     rcx, [rbp+70h+P]; P
0x14004bdab  test    rcx, rcx
0x14004bdae  jz      short loc_14004BDBE
0x14004bdb0  xor     edx, edx; Tag
0x14004bdb2  call    cs:__imp_ExFreePoolWithTag
0x14004bdb9  nop     dword ptr [rax+rax+00h]
0x14004bdbe  mov     eax, r12d
0x14004bdc1  movaps  xmm7, [rsp+170h+var_50]
0x14004bdc9  movaps  xmm6, [rsp+170h+var_40]
0x14004bdd1  mov     r15, [rsp+170h+var_30]
0x14004bdd9  mov     rsi, [rsp+170h+var_28]
0x14004bde1  mov     rbx, [rsp+170h+arg_10]
0x14004bde9  mov     rcx, [rbp+70h+var_60]
0x14004bded  xor     rcx, rsp; StackCookie
0x14004bdf0  call    __security_check_cookie
0x14004bdf5  add     rsp, 150h
0x14004bdfc  pop     r14
0x14004bdfe  pop     r13
0x14004be00  pop     r12
0x14004be02  pop     rdi
0x14004be03  pop     rbp
0x14004be04  retn
0x14004be06  sub     rcx, rdx
0x14004be09  lea     rax, [r8+rdx]
0x14004be0d  mov     [rsi], rax
0x14004be10  mov     [rsi+8], rcx
0x14004be14  cmp     [r11+38h], r13b
0x14004be18  jz      loc_14004C3B1
0x14004be1e  inc     dword ptr [r11+2Ch]
0x14004be22  test    r14, r14
0x14004be25  jz      loc_14004BDA1
0x14004be2b  movups  xmmword ptr [r14], xmm6
0x14004be2f  movups  xmmword ptr [r14+10h], xmm7
0x14004be34  jmp     loc_14004BDA1
0x14004be39  mov     r13, [rsi+8]
0x14004be3d  add     rdx, rcx
0x14004be40  inc     dword ptr [r11+2Ch]
0x14004be44  add     r13, r8
0x14004be47  mov     [rsp+170h+var_148], r13
0x14004be4c  cmp     r13, rdx
0x14004be4f  jz      loc_14004BFC9
0x14004be55  mov     rcx, [r10]
0x14004be58  sub     rcx, [rsi]
0x14004be5b  mov     [rsi+8], rcx
0x14004be5f  mov     rcx, r13
0x14004be62  sub     rcx, rdx
0x14004be65  mov     qword ptr [rbp+70h+var_D8], rdx
0x14004be69  cmp     byte ptr [r11+38h], 0
0x14004be6e  mov     qword ptr [rbp+70h+var_D8+8], rcx
0x14004be72  mov     r8, [rsi+10h]
0x14004be76  jnz     loc_14004C4AC
0x14004be7c  mov     rax, rdx
0x14004be7f  sub     rax, [rsi]
0x14004be82  add     rax, r8
0x14004be85  mov     [rbp+70h+var_C8], rax
0x14004be89  test    rdi, rdi
0x14004be8c  jnz     loc_14004C025
0x14004be92  lea     rax, [rbp+70h+var_D8]
0x14004be96  mov     dword ptr [rsp+170h+var_F8], 10h
0x14004be9e  mov     qword ptr [rbp+70h+var_F8+8], rax
0x14004bea2  lea     rax, [rbp+70h+var_D8]
0x14004bea6  mov     [rbp+70h+Src+8], rax
0x14004beaa  mov     eax, 18h
0x14004beaf  mov     dword ptr [rbp+70h+Src], eax
0x14004beb2  add     eax, 7
0x14004beb5  and     eax, 0FFFFFFF8h
0x14004beb8  add     eax, 20h ; ' '
0x14004bebb  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14004bec1  mov     edi, eax
0x14004bec3  ja      loc_14004C066
0x14004bec9  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14004becf  ja      loc_14004C329
0x14004bed5  xor     ecx, ecx; ProcNumber
0x14004bed7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004bede  nop     dword ptr [rax+rax+00h]
0x14004bee3  xor     edx, edx
0x14004bee5  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14004beeb  lea     r13, [rdx+rdx*2]
0x14004beef  shl     r13, 6
0x14004bef3  add     r13, cs:qword_140269458
0x14004befa  mov     eax, [r13+0]
0x14004befe  cmp     rdi, rax
0x14004bf01  jbe     loc_14004C36C
0x14004bf07  xor     r13d, r13d
0x14004bf0a  lea     rdx, [rdi+10h]
0x14004bf0e  mov     ecx, 42h ; 'B'
0x14004bf13  mov     r8d, 6950534Dh
0x14004bf19  call    cs:__imp_ExAllocatePool2
0x14004bf20  nop     dword ptr [rax+rax+00h]
0x14004bf25  mov     rdi, rax
0x14004bf28  test    al, 0Fh
0x14004bf2a  jz      loc_1401FD27C
0x14004bf30  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14004bf37  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14004bf3d  mov     rbx, [rcx+18h]
0x14004bf41  mov     edi, 0C0000034h
0x14004bf46  test    rbx, rbx
0x14004bf49  jz      short loc_14004BF76
0x14004bf4b  mov     rdx, [rdx]
0x14004bf4e  movzx   eax, byte ptr [rbx+1Ah]
0x14004bf52  add     rax, rbx
0x14004bf55  mov     rcx, [rax]
0x14004bf58  cmp     rdx, rcx
0x14004bf5b  jb      short loc_14004BF98
0x14004bf5d  add     rcx, [rax+8]
0x14004bf61  mov     r15, rbx
0x14004bf64  cmp     rdx, rcx
0x14004bf67  jb      loc_14004C42A
0x14004bf6d  mov     rbx, [rbx+10h]
0x14004bf71  test    rbx, rbx
0x14004bf74  jnz     short loc_14004BF4E
0x14004bf76  test    r12b, r9b
0x14004bf79  jz      short loc_14004BF91
0x14004bf7b  test    r8, r8
0x14004bf7e  jz      short loc_14004BF91
0x14004bf80  xor     edx, edx; Tag
0x14004bf82  mov     rcx, r8; P
0x14004bf85  call    cs:__imp_ExFreePoolWithTag
0x14004bf8c  nop     dword ptr [rax+rax+00h]
0x14004bf91  mov     eax, edi
0x14004bf93  jmp     loc_14004BDC1
0x14004bf98  mov     rbx, [rbx+8]
0x14004bf9c  jmp     short loc_14004BF71
0x14004bf9e  mov     rdx, rax
0x14004bfa1  mov     r8, rcx
0x14004bfa4  jmp     loc_14004BCF4
0x14004bfa9  cmp     [rax+8], r13
0x14004bfad  jz      short loc_14004BFB9
0x14004bfaf  mov     rax, [rax+8]
0x14004bfb3  cmp     [rax+8], r13
0x14004bfb7  jnz     short loc_14004BFAF
0x14004bfb9  mov     rcx, rax
0x14004bfbc  jmp     loc_14004BCFF
0x14004bfc1  mov     rsi, r13
0x14004bfc4  jmp     loc_14004BCB1
0x14004bfc9  mov     rax, [r10+8]
0x14004bfcd  sub     [rsi+8], rax
0x14004bfd1  jmp     loc_14004BDA1
0x14004bfd6  mov     [r14+8], r13
0x14004bfda  mov     [r14], r13
0x14004bfdd  jmp     loc_14004BD3C
0x14004bfe2  mov     rax, [rdi+8]
0x14004bfe6  movups  xmm0, xmmword ptr [r10]
0x14004bfea  movups  xmmword ptr [rax], xmm0
0x14004bfed  mov     rax, [rdi+18h]
0x14004bff1  movups  xmm0, xmmword ptr [r10]
0x14004bff5  movups  xmmword ptr [rax], xmm0
0x14004bff8  movsd   xmm1, qword ptr [r10+10h]
0x14004bffe  movsd   qword ptr [rax+10h], xmm1
0x14004c003  movups  xmm2, xmmword ptr [rdi]
0x14004c006  mov     rdx, [rdi+8]
0x14004c00a  movups  xmm0, xmmword ptr [rdi+10h]
0x14004c00e  movzx   r9d, [rbp+70h+var_88]
0x14004c013  mov     r8, [rbp+70h+P]
0x14004c017  movups  [rsp+170h+var_F8], xmm2
0x14004c01c  movups  xmmword ptr [rbp+70h+Src], xmm0
0x14004c020  jmp     loc_14004BC54
0x14004c025  mov     rax, [rdi+8]
0x14004c029  mov     r8, rdi
0x14004c02c  xor     r11b, r11b
0x14004c02f  mov     [rax], rdx
0x14004c032  mov     [rax+8], rcx
0x14004c036  movups  xmm0, [rbp+70h+var_D8]
0x14004c03a  mov     rax, [rdi+18h]
0x14004c03e  movups  xmmword ptr [rax], xmm0
0x14004c041  movsd   xmm1, [rbp+70h+var_C8]
0x14004c046  movsd   qword ptr [rax+10h], xmm1
  ... truncated ...
```
