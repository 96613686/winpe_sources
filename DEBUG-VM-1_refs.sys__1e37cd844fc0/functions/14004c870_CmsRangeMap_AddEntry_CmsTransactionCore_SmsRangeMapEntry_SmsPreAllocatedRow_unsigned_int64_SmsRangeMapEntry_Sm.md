# CmsRangeMap::AddEntry(CmsTransactionCore *,SmsRangeMapEntry *,_SmsPreAllocatedRow *,unsigned __int64 *,SmsRangeMapEntry *,_SmsQuickIndex *,_RTL_AVL_ENTRY * *)

- ea: `0x14004c870`
- end: `0x14004d85f`
- name: `?AddEntry@CmsRangeMap@@UEAAJPEAVCmsTransactionCore@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@PEA_K1PEAU_SmsQuickIndex@@PEAPEAU_RTL_AVL_ENTRY@@@Z`
- size: `4079`
- prototype: `__int64 __fastcall(CmsRangeMap *__hidden this, struct CmsTransactionCore *, struct SmsRangeMapEntry *, struct _SmsPreAllocatedRow *, unsigned __int64 *, struct SmsRangeMapEntry *, struct _SmsQuickIndex *, struct _RTL_AVL_ENTRY **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x14004b5b0`
- `0x14004b8d0`
- `0x14004c580`
- `0x14004c870`
- `0x14009cee0`
- `0x1400ceda0`
- `0x1401f3fc0`
- `0x1401f40a0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d752`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d78f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d752`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d78f`
- `ntoskrnl!ExAllocatePool2` at `0x14004d2cf`
- `ntoskrnl!ExAllocatePool2` at `0x14004d3ff`
- `ntoskrnl!ExAllocatePool2` at `0x14004d4a1`
- `ntoskrnl!ExAllocatePool2` at `0x14004d2cf`
- `ntoskrnl!ExAllocatePool2` at `0x14004d3ff`
- `ntoskrnl!ExAllocatePool2` at `0x14004d4a1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d28e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d3ce`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d28e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004d3ce`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd307`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd319`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd307`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd319`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004d76f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004d7ac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004d76f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004d7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ccee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ccee`

## string_xrefs

- `0x1401fd32b`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeMap::AddEntry(
        CmsRangeMap *this,
        struct CmsTransactionCore *a2,
        struct SmsRangeMapEntry *a3,
        struct _SmsPreAllocatedRow *a4,
        unsigned __int64 *a5,
        struct SmsRangeMapEntry *a6,
        __m128i *a7,
        struct _RTL_AVL_ENTRY **a8)
{
  unsigned __int64 v8; // r14
  char v9; // r11
  unsigned __int64 v10; // r10
  unsigned __int64 v12; // r15
  struct SmsRangeMapEntry *v13; // rbx
  __m128i v14; // xmm3
  __m128i v15; // xmm4
  struct _RTL_AVL_ENTRY *v16; // r9
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rsi
  int v19; // r11d
  __m128i v20; // xmm6
  __m128i v21; // xmm7
  unsigned __int64 *v22; // rdx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r8
  unsigned __int64 *v25; // rax
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rax
  __int32 v28; // eax
  unsigned __int64 v29; // rbx
  unsigned __int64 *v30; // r13
  char v31; // r8
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  _QWORD *v36; // rdx
  __m128i v37; // xmm8
  __m128i v38; // xmm9
  char v39; // r10
  int v40; // edi
  unsigned __int64 v41; // r15
  unsigned __int64 *v42; // r8
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rdx
  int v46; // ebx
  struct SmsRangeMapEntry *v47; // rax
  __int16 v49; // r14
  struct _RTL_AVL_ENTRY *v50; // r15
  char v51; // r9
  struct _SmsPreAllocatedRow *v52; // r8
  struct CmsTransactionCore *v53; // r11
  unsigned __int64 v54; // r14
  unsigned int v55; // edx
  unsigned int v56; // eax
  unsigned __int8 v57; // dl
  char *v58; // rcx
  char *v59; // rcx
  char *v60; // rax
  __int64 v61; // rcx
  struct _RTL_AVL_ENTRY **v62; // rdx
  CmsRangeMap *v63; // r10
  unsigned __int64 *v64; // r12
  int v65; // eax
  __int32 v66; // eax
  _QWORD *v67; // rcx
  struct _RTL_AVL_ENTRY *v68; // rax
  _QWORD **v69; // rax
  _QWORD *v70; // rdx
  unsigned __int64 v71; // rax
  _QWORD *v72; // rax
  _QWORD *v73; // rcx
  _QWORD *v74; // rdx
  int v75; // r12d
  __int64 v76; // rax
  __int128 v77; // xmm2
  _OWORD *v78; // rax
  __int32 v79; // eax
  unsigned __int64 v80; // rcx
  __int16 v81; // r15
  char v82; // r12
  unsigned int v83; // eax
  unsigned __int64 v84; // rbx
  __int64 v85; // r9
  unsigned int *v86; // r14
  unsigned __int64 v87; // rdx
  __int64 Pool2; // rax
  _WORD *v89; // rbx
  unsigned __int64 v90; // rdx
  unsigned __int64 *v91; // rax
  __int64 v92; // r9
  __int64 v93; // r14
  unsigned __int64 v94; // rdx
  __int64 v95; // rax
  int v96; // ecx
  int v97; // ecx
  unsigned __int64 v98; // rdx
  unsigned __int64 *v99; // rax
  unsigned __int64 v100; // rax
  __int64 v101; // r14
  unsigned __int64 v102; // rax
  struct _RTL_AVL_ENTRY *v103; // rax
  struct _NPAGED_LOOKASIDE_LIST *v104; // rcx
  _WORD *v105; // rax
  struct _NPAGED_LOOKASIDE_LIST *v106; // rcx
  _WORD *v107; // rax
  unsigned __int64 i; // rdx
  bool v109; // zf
  char v110; // cl
  char v111; // al
  char v112; // [rsp+20h] [rbp-E0h]
  char v113; // [rsp+21h] [rbp-DFh]
  int v114; // [rsp+24h] [rbp-DCh]
  int v115; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v116; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v117; // [rsp+38h] [rbp-C8h]
  __m128i v118; // [rsp+40h] [rbp-C0h]
  __m128i v119; // [rsp+40h] [rbp-C0h]
  __m128i v120; // [rsp+40h] [rbp-C0h]
  __m128i v121; // [rsp+40h] [rbp-C0h]
  __m128i v122; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v124; // [rsp+68h] [rbp-98h]
  unsigned __int64 v125; // [rsp+70h] [rbp-90h]
  int v126; // [rsp+78h] [rbp-88h]
  __m128i v128; // [rsp+88h] [rbp-78h]
  __m128i v129; // [rsp+88h] [rbp-78h]
  __m128i v130; // [rsp+98h] [rbp-68h]
  __m128i v131; // [rsp+98h] [rbp-68h]
  struct _RTL_AVL_ENTRY *v132; // [rsp+A8h] [rbp-58h]
  __int64 v133; // [rsp+A8h] [rbp-58h]
  __int128 v134; // [rsp+D0h] [rbp-30h] BYREF
  void *Src[2]; // [rsp+E0h] [rbp-20h]
  struct _SmsPreAllocatedRow *v136; // [rsp+F0h] [rbp-10h]
  struct _RTL_AVL_ENTRY **v137; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v138; // [rsp+100h] [rbp+0h]
  struct SmsRangeMapEntry *v139; // [rsp+108h] [rbp+8h]
  int v140; // [rsp+120h] [rbp+20h]
  __int16 epi16; // [rsp+124h] [rbp+24h]
  __int16 v142; // [rsp+126h] [rbp+26h]
  unsigned __int64 v143; // [rsp+128h] [rbp+28h]
  int v144; // [rsp+130h] [rbp+30h]
  int v145; // [rsp+134h] [rbp+34h]
  unsigned __int64 *v146; // [rsp+138h] [rbp+38h]
  PVOID P; // [rsp+140h] [rbp+40h]
  char v148; // [rsp+148h] [rbp+48h]
  int v149; // [rsp+14Ch] [rbp+4Ch]
  char v150; // [rsp+150h] [rbp+50h] BYREF

  v8 = *(_QWORD *)a3;
  v9 = 0;
  v10 = *((_QWORD *)a3 + 2);
  v12 = *((_QWORD *)a3 + 1);
  v13 = a3;
  v139 = a6;
  v14 = 0;
  v15 = 0;
  v137 = a8;
  P = &v150;
  v134 = 0;
  v136 = a4;
  v16 = this;
  v140 = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v143 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v142 = 0;
  v145 = HIDWORD(a6);
  v138 = a5;
  v149 = 32;
  v144 = 0;
  v146 = 0;
  v148 = 0;
  v124 = v8;
  v117 = v10;
  v112 = 0;
  v113 = 0;
  v122 = 0;
  if ( a5 )
    *a5 = 0;
  v125 = v12;
  if ( a4 )
  {
    *(_OWORD *)*((_QWORD *)a4 + 1) = *(_OWORD *)a3;
    v76 = *((_QWORD *)a4 + 3);
    *(_OWORD *)v76 = *(_OWORD *)a3;
    *(_QWORD *)(v76 + 16) = *((_QWORD *)a3 + 2);
    a3 = (struct SmsRangeMapEntry *)*((_QWORD *)a4 + 1);
    v77 = *(_OWORD *)a4;
    *(_OWORD *)Src = *((_OWORD *)a4 + 1);
    v134 = v77;
  }
  else
  {
    *((_QWORD *)&v134 + 1) = a3;
    LODWORD(v134) = 16;
    Src[1] = a3;
    LODWORD(Src[0]) = 24;
  }
  v114 = 2;
  if ( !a7 )
  {
    v17 = *((_QWORD *)this + 3);
    v116 = v17;
    if ( !v17 )
    {
      v18 = 0;
      v19 = 0;
      goto LABEL_8;
    }
    v24 = *(_QWORD *)a3;
    while ( 1 )
    {
      while ( 1 )
      {
        v25 = v17 ? (unsigned __int64 *)(v17 + *(unsigned __int8 *)(v17 + 26)) : 0LL;
        if ( v24 >= *v25 )
          break;
        v27 = *(_QWORD *)(v17 + 8);
        if ( !v27 )
        {
          v18 = 0;
          v121.m128i_i64[0] = 0;
          v19 = 2;
          v122.m128i_i32[0] = 2;
          v121.m128i_i64[1] = v17;
          v20 = v121;
          v122.m128i_i32[1] = *((_DWORD *)this + 12);
          v21 = v122;
          v115 = 2;
          goto LABEL_93;
        }
        v17 = *(_QWORD *)(v17 + 8);
        v116 = v27;
      }
      v18 = v17;
      if ( v24 < *v25 + v25[1] )
        break;
      v26 = *(_QWORD *)(v17 + 16);
      if ( !v26 )
      {
        v18 = 0;
        v19 = 3;
LABEL_8:
        v122.m128i_i32[1] = *((_DWORD *)this + 12);
        v118.m128i_i64[0] = 0;
        v118.m128i_i64[1] = v17;
        v20 = v118;
        v122.m128i_i32[0] = v19;
        v21 = v122;
        v115 = v19;
LABEL_219:
        v116 = v17;
LABEL_93:
        v30 = 0;
        v113 = 0;
LABEL_94:
        v131 = v21;
        if ( !v17 )
          goto LABEL_175;
        v67 = (_QWORD *)v17;
        if ( v19 == 1 )
        {
          v68 = *(struct _RTL_AVL_ENTRY **)(v17 + 8);
          if ( !v68 )
          {
            v69 = *(_QWORD ***)v17;
            if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) == v17 )
            {
              do
              {
                v70 = *v69;
                v67 = v69;
                v69 = (_QWORD **)v70;
              }
              while ( (_QWORD *)v70[1] == v67 );
            }
            else
            {
              v70 = *(_QWORD **)v17;
            }
            if ( (_QWORD *)v70[2] != v67 || (_QWORD *)*v70 == v70 )
              v67 = 0;
            else
              v67 = v70;
LABEL_137:
            if ( v67 )
            {
LABEL_138:
              v9 = v112;
              v140 = *((unsigned __int8 *)v67 + 27);
              v131.m128i_i32[0] = 1;
              v15 = v131;
              v143 = (unsigned __int64)v67 + *((unsigned __int8 *)v67 + 26);
              epi16 = 0;
              v144 = *((unsigned __int16 *)v67 + 15);
              v22 = (_QWORD *)((char *)v67 + *((unsigned __int8 *)v67 + 26));
              v129.m128i_i64[1] = (__int64)v67;
              v146 = v22;
              v129.m128i_i64[0] = (__int64)v67;
              v14 = v129;
              v23 = *v22;
              goto LABEL_139;
            }
LABEL_175:
            v9 = v112;
            v117 = v10;
LABEL_142:
            v29 = v8;
            goto LABEL_143;
          }
          for ( ; *((_QWORD *)v68 + 2); v68 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v68 + 2) )
            ;
        }
        else
        {
          if ( v19 != 2 )
            goto LABEL_138;
          v68 = RealPredecessor((struct _RTL_AVL_ENTRY *)v17);
        }
        v67 = v68;
        goto LABEL_137;
      }
      v17 = *(_QWORD *)(v17 + 16);
      v116 = v26;
    }
    v119.m128i_i64[0] = v17;
    v119.m128i_i64[1] = v17;
    v116 = v17;
    v115 = 1;
    v122.m128i_i32[0] = 1;
    v20 = v119;
    if ( !v17 )
    {
      v19 = 1;
      v122.m128i_i32[1] = *((_DWORD *)this + 12);
      v21 = v122;
      goto LABEL_219;
    }
    v140 = *(unsigned __int8 *)(v17 + 27);
    v143 = v17 + *(unsigned __int8 *)(v17 + 26);
    epi16 = 0;
    v144 = *(unsigned __int16 *)(v17 + 30);
    v28 = *((_DWORD *)this + 12);
    v22 = (unsigned __int64 *)(v17 + *(unsigned __int8 *)(v17 + 26));
    v146 = v22;
    v122.m128i_i32[1] = v28;
    v21 = v122;
    v23 = *v22;
    goto LABEL_25;
  }
  v20 = *a7;
  v21 = a7[1];
  v122.m128i_i64[1] = v21.m128i_i64[1];
  if ( !a7->m128i_i64[0] )
  {
    v112 = 1;
LABEL_133:
    v19 = _mm_cvtsi128_si32(v21);
    v30 = 0;
    v17 = _mm_srli_si128(v20, 8).m128i_u64[0];
    v113 = 1;
    v116 = v17;
    v18 = a7->m128i_i64[0];
    v114 = 2;
    v115 = v19;
    goto LABEL_94;
  }
  v22 = (unsigned __int64 *)(a7->m128i_i64[0] + *(unsigned __int8 *)(a7->m128i_i64[0] + 26));
  if ( !v22 )
  {
LABEL_59:
    v112 = 1;
    if ( v22 )
    {
      v19 = _mm_cvtsi128_si32(v21);
      v18 = a7->m128i_i64[0];
      v17 = _mm_srli_si128(v20, 8).m128i_u64[0];
      v115 = v19;
      goto LABEL_219;
    }
    goto LABEL_133;
  }
  v23 = *v22;
  v16 = *(struct _RTL_AVL_ENTRY **)v13;
  if ( *v22 + v22[1] != *(_QWORD *)v13 )
  {
    if ( v23 <= (unsigned __int64)v16 )
    {
      v115 = v21.m128i_i32[0];
      v18 = a7->m128i_i64[0];
      v17 = _mm_srli_si128(v20, 8).m128i_u64[0];
      v116 = v17;
LABEL_25:
      v16 = (struct _RTL_AVL_ENTRY *)(v22[1] + v23);
      if ( v12 + v8 > (unsigned __int64)v16 )
      {
        v22[1] = v12 + v8 - v23;
        v100 = v8 + v12 - (_QWORD)v16;
        v12 = v12 + v8 - v23;
        v125 = v100;
      }
      else
      {
        v125 = 0;
        v12 = v22[1];
      }
      v29 = *v22;
      v30 = v22;
      v31 = 0;
      v124 = *v22;
      v117 = v22[2];
      v114 = 2;
      v130 = v21;
      goto LABEL_28;
    }
    goto LABEL_59;
  }
  v114 = 2;
  v30 = 0;
  v17 = _mm_srli_si128(v20, 8).m128i_u64[0];
  v115 = v21.m128i_i32[0];
  v116 = v17;
  v18 = a7->m128i_i64[0];
LABEL_139:
  v16 = (struct _RTL_AVL_ENTRY *)v22[1];
  if ( (unsigned __int64)v16 + v23 < v8 )
    goto LABEL_142;
  v80 = v22[2];
  if ( *((_BYTE *)this + 56) )
  {
    if ( v80 != *((_QWORD *)v13 + 2) )
      goto LABEL_142;
  }
  else if ( v8 + v80 - v23 != *((_QWORD *)v13 + 2) )
  {
    goto LABEL_142;
  }
  v29 = *v22;
  v101 = v8 - ((_QWORD)v16 + v23);
  v117 = v22[2];
  v30 = v22;
  v124 = *v22;
  v102 = v12 + v101;
  v12 += (unsigned __int64)v16 + v101;
  v125 = v102;
  v22[1] = v12;
  if ( a7 )
  {
    *a7 = v14;
    a7[1] = v15;
  }
LABEL_143:
  v31 = v113;
  v37 = v20;
  v38 = v21;
  v128.m128i_i64[0] = v20.m128i_i64[0];
  v130 = v21;
  if ( v9 && !v113 )
  {
    v126 = v21.m128i_i32[0];
    v32 = _mm_srli_si128(v20, 8).m128i_u64[0];
    goto LABEL_37;
  }
LABEL_28:
  v32 = v17;
  if ( v17 )
  {
    if ( ((v115 - 1) & 0xFFFFFFFD) != 0 )
      goto LABEL_36;
    v33 = *(_QWORD *)(v17 + 16);
    if ( v33 )
    {
      for ( ; *(_QWORD *)(v33 + 8); v33 = *(_QWORD *)(v33 + 8) )
        ;
      v32 = v33;
    }
    else
    {
      v34 = *(_QWORD **)v17;
      if ( *(_QWORD *)(*(_QWORD *)v17 + 16LL) == v17 )
      {
        do
        {
          v35 = (_QWORD *)*v34;
          v36 = v34;
          v34 = v35;
        }
        while ( (_QWORD *)v35[2] == v36 );
      }
      else
      {
        v35 = *(_QWORD **)v17;
        v36 = (_QWORD *)v17;
      }
      v32 = 0;
      if ( (_QWORD *)v35[1] == v36 )
        v32 = (unsigned __int64)v35;
    }
    if ( v32 )
    {
LABEL_36:
      v128.m128i_i64[1] = v32;
      v128.m128i_i64[0] = v32;
      v37 = v128;
      v130.m128i_i32[0] = 1;
      v38 = v130;
      v126 = 1;
      v140 = *(unsigned __int8 *)(v32 + 27);
      v143 = v32 + *(unsigned __int8 *)(v32 + 26);
      epi16 = 0;
      v144 = *(unsigned __int16 *)(v32 + 30);
      v146 = (unsigned __int64 *)(v32 + *(unsigned __int8 *)(v32 + 26));
LABEL_37:
      v16 = 0;
      v39 = 0;
      v40 = v126;
      v41 = v29 + v12;
      v132 = 0;
      while ( 1 )
      {
        if ( !v9 || v31 )
        {
          v42 = v146;
        }
        else
        {
          if ( v18 )
            v42 = (unsigned __int64 *)(v18 + *(unsigned __int8 *)(v18 + 26));
          else
            v42 = 0;
          v112 = 0;
        }
        v43 = *v42;
        if ( v41 < *v42 )
        {
LABEL_45:
          v17 = v116;
          goto LABEL_46;
        }
        v44 = v41 - v43;
        v16 = (struct _RTL_AVL_ENTRY *)(v42[1] + v43);
        if ( (unsigned __int64)v16 <= v41 )
          v44 = v42[1];
        v125 -= v44;
        if ( *((_BYTE *)this + 56) )
        {
          if ( v117 != v42[2] )
            goto LABEL_45;
          v45 = v43 - v29;
        }
        else
        {
          v45 = v43 - v29;
          if ( v45 + v117 != v42[2] )
            goto LABEL_45;
        }
        if ( v30 )
        {
          if ( (unsigned __int64)v16 > v41 )
            v30[1] += (unsigned __int64)v16 - v41;
          v39 = 1;
          v16 = (struct _RTL_AVL_ENTRY *)_mm_srli_si128(v37, 8).m128i_u64[0];
          v132 = v16;
        }
        else
        {
          *v42 = v29;
          v103 = (struct _RTL_AVL_ENTRY *)v41;
          v30 = v42;
          if ( (unsigned __int64)v16 > v41 )
            v103 = v16;
          v42[1] = (unsigned __int64)v103 - v29;
          if ( !*((_BYTE *)this + 56) )
            v42[2] -= v45;
          v16 = v132;
          if ( a7 )
          {
            *a7 = v37;
            a7[1] = v38;
          }
        }
        if ( !v32 )
          goto LABEL_187;
        if ( ((v40 - 1) & 0xFFFFFFFD) == 0 )
        {
          v71 = *(_QWORD *)(v32 + 16);
          if ( v71 )
          {
            for ( ; *(_QWORD *)(v71 + 8); v71 = *(_QWORD *)(v71 + 8) )
              ;
            v32 = v71;
          }
          else
          {
            v72 = *(_QWORD **)v32;
            if ( *(_QWORD *)(*(_QWORD *)v32 + 16LL) == v32 )
            {
              do
              {
                v73 = (_QWORD *)*v72;
                v74 = v72;
                v72 = v73;
              }
              while ( (_QWORD *)v73[2] == v74 );
            }
            else
            {
              v73 = *(_QWORD **)v32;
              v74 = (_QWORD *)v32;
            }
            v32 = 0;
            if ( (_QWORD *)v73[1] == v74 )
              v32 = (unsigned __int64)v73;
          }
          if ( !v32 )
            break;
        }
        v40 = 1;
        v140 = *(unsigned __int8 *)(v32 + 27);
        v130.m128i_i32[0] = 1;
        v38 = v130;
        v143 = v32 + *(unsigned __int8 *)(v32 + 26);
        epi16 = 0;
        v144 = *(unsigned __int16 *)(v32 + 30);
        v128.m128i_i64[1] = v32;
        v128.m128i_i64[0] = v32;
        v75 = 0;
        v37 = v128;
        v146 = (unsigned __int64 *)(v32 + *(unsigned __int8 *)(v32 + 26));
LABEL_114:
        if ( v39 )
        {
          ++*((_DWORD *)this + 11);
          DeleteNodeFromTree((CmsRangeMap *)((char *)this + 8), v16, 1u);
          --*((_DWORD *)this + 10);
          CmsAvlTableLite::FreeIndexEntry(v132);
          ++*((_DWORD *)this + 12);
          v29 = v124;
          v39 = 0;
        }
        v9 = v112;
        v31 = v113;
        if ( v75 < 0 )
          goto LABEL_45;
      }
      v37 = (__m128i)v128.m128i_u64[0];
LABEL_187:
      v75 = -1073741772;
      goto LABEL_114;
    }
  }
LABEL_46:
  if ( v30 )
  {
    v46 = 0;
    if ( v137 )
      *v137 = (struct _RTL_AVL_ENTRY *)(v30 - 4);
LABEL_49:
    if ( v138 )
      *v138 = v125;
    if ( v30 )
    {
      v47 = v139;
      if ( v139 )
      {
        *(_OWORD *)v139 = *(_OWORD *)v30;
        *((_QWORD *)v47 + 2) = v30[2];
      }
    }
    goto LABEL_54;
  }
  v49 = 0x8000;
  if ( v136 )
  {
    v50 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v136 + 4);
    v46 = 0;
    v133 = (__int64)v50;
    v51 = 0;
    v52 = v136;
    goto LABEL_63;
  }
  v81 = (__int16)Src[0];
  v82 = v134;
  v83 = ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32;
  v84 = v83;
  if ( v83 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v83 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v86 = (unsigned int *)(qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v84 > *v86 )
      {
        v86 = 0;
        v87 = v84 + 16;
        goto LABEL_150;
      }
      if ( !*((_BYTE *)v86 + 8) )
      {
        if ( (int)*((_QWORD *)v86 + 11) > (int)HIDWORD(*((_QWORD *)v86 + 11)) )
        {
          v96 = _InterlockedDecrement((volatile signed __int32 *)v86 + 22);
          if ( v96 >= (int)v86[23] && v96 >= 0 )
          {
            v105 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v86 + 4);
            goto LABEL_208;
          }
          _InterlockedIncrement((volatile signed __int32 *)v86 + 22);
        }
LABEL_183:
        v87 = v86[1];
LABEL_150:
        Pool2 = ExAllocatePool2(66, v87, 1766871885, v85);
        v89 = (_WORD *)Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_210:
            v49 = 0x2000;
            goto LABEL_211;
          }
LABEL_209:
          *(_QWORD *)v89 = v86;
          v89 += 8;
          goto LABEL_210;
        }
LABEL_252:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v104 = (struct _NPAGED_LOOKASIDE_LIST *)(v86 + 16);
      if ( *((_BYTE *)v86 + 9) )
        v105 = ExAllocateFromNPagedLookasideList(v104);
      else
        v105 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v104);
LABEL_208:
      v89 = v105;
      if ( v105 )
        goto LABEL_209;
      goto LABEL_183;
    }
    KeGetCurrentProcessorNumberEx(0);
    v93 = qword_140269460;
    if ( v84 > *(unsigned int *)qword_140269460 )
    {
      v93 = 0;
      v94 = v84 + 16;
      goto LABEL_172;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v97 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v97 >= *(_DWORD *)(v93 + 92) && v97 >= 0 )
        {
          v107 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v93 + 64));
          goto LABEL_213;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v93 + 88));
      }
LABEL_192:
      v94 = *(unsigned int *)(v93 + 4);
LABEL_172:
      v95 = ExAllocatePool2(66, v94, 1766871885, v92);
      v89 = (_WORD *)v95;
      if ( (v95 & 0xF) != 0 )
        goto LABEL_252;
      if ( !v95 )
      {
LABEL_215:
        v49 = 0x4000;
LABEL_211:
        if ( v89 )
        {
          v133 = (__int64)v89;
          goto LABEL_185;
        }
        goto LABEL_194;
      }
LABEL_214:
      *(_QWORD *)v89 = v93;
      v89 += 8;
      goto LABEL_215;
    }
    v106 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v107 = ExAllocateFromNPagedLookasideList(v106);
    else
      v107 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v106);
LABEL_213:
    v89 = v107;
    if ( v107 )
      goto LABEL_214;
    goto LABEL_192;
  }
  v133 = ExAllocatePool2(66, ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32, 1766871885, v16);
  v89 = (_WORD *)v133;
  if ( v133 )
  {
LABEL_185:
    v89[14] = 0;
    memmove(v89 + 16, Src[1], LODWORD(Src[0]));
    *((_BYTE *)v89 + 26) = 32;
    v52 = (struct _SmsPreAllocatedRow *)&v134;
    v89[14] |= v49;
    v51 = 1;
    v89[15] = v81;
    v50 = (struct _RTL_AVL_ENTRY *)v133;
    *((_BYTE *)v89 + 27) = v82;
    v46 = 0;
LABEL_63:
    v53 = a2;
    v54 = 0;
    v55 = *((unsigned __int8 *)a2 + 96);
    v56 = 5;
    if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
      v56 = 2;
    if ( v55 < v56 )
    {
      v57 = v55 + 1;
      *((_BYTE *)a2 + 96) = v57;
      if ( v57 <= 2u )
        v58 = (char *)a2 - 24;
      else
        v58 = (char *)a2 + 784;
      v59 = &v58[40 * v57];
      *(_QWORD *)v59 = v52;
      *((_WORD *)v59 + 16) = 0;
      *((_QWORD *)v59 + 1) = &CmsRangeMap::PropertyDef;
      *((_QWORD *)v59 + 2) = &off_140207A20;
      LOBYTE(v55) = *((_BYTE *)a2 + 96);
    }
    if ( v51 )
    {
      if ( (unsigned __int8)v55 <= 2u )
        v60 = (char *)a2 + 9;
      else
        v60 = (char *)a2 + 817;
      v60[40 * (unsigned __int8)v55] = 1;
    }
    v61 = *((unsigned __int8 *)a2 + 96);
    v62 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v61);
    if ( (unsigned __int8)v61 > 2u )
      v62 += 101;
    v63 = this;
    *v62 = v50;
    v64 = (unsigned __int64 *)((char *)this + 24);
    if ( v17 )
    {
      if ( !v18 )
      {
        v65 = v115;
        v54 = v17;
        v114 = v115;
        goto LABEL_128;
      }
      if ( *v64 )
      {
        v90 = **((_QWORD **)v52 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v91 = v18 ? (unsigned __int64 *)(v18 + *(unsigned __int8 *)(v18 + 26)) : 0LL;
            if ( v90 < *v91 )
              break;
            if ( v90 < v91[1] + *v91 )
              goto LABEL_205;
            if ( !*(_QWORD *)(v18 + 16) )
              goto LABEL_162;
            v18 = *(_QWORD *)(v18 + 16);
          }
          if ( !*(_QWORD *)(v18 + 8) )
            break;
          v18 = *(_QWORD *)(v18 + 8);
        }
        v54 = v18;
        v65 = 2;
LABEL_80:
        v18 = 0;
        goto LABEL_81;
      }
    }
    else
    {
      v18 = *v64;
      if ( *v64 )
      {
        v98 = **((_QWORD **)v52 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v99 = v18 ? (unsigned __int64 *)(v18 + *(unsigned __int8 *)(v18 + 26)) : 0LL;
            if ( v98 >= *v99 )
              break;
            if ( !*(_QWORD *)(v18 + 8) )
            {
              v54 = v18;
              v65 = 2;
              goto LABEL_79;
            }
            v18 = *(_QWORD *)(v18 + 8);
          }
          if ( v98 < v99[1] + *v99 )
            break;
          if ( !*(_QWORD *)(v18 + 16) )
          {
LABEL_162:
            v54 = v18;
            v65 = 3;
            goto LABEL_79;
          }
          v18 = *(_QWORD *)(v18 + 16);
        }
LABEL_205:
        v65 = 1;
        v54 = v18;
        v114 = 1;
LABEL_81:
        if ( v18 )
        {
          v66 = *((_DWORD *)this + 12);
          --*((_BYTE *)a2 + 96);
          v120.m128i_i64[0] = v18;
          v120.m128i_i64[1] = v18;
          v122.m128i_i32[0] = 3;
          v122.m128i_i32[1] = v66;
          if ( v50 && v51 )
            CmsAvlTableLite::FreeIndexEntry(v50);
          v46 = -1073741771;
LABEL_84:
          v21 = v122;
          v20 = v120;
          goto LABEL_85;
        }
LABEL_128:
        ++*((_DWORD *)this + 12);
        if ( v65 != 1 )
        {
          v78 = (_OWORD *)((__int64 (__fastcall *)(char *, _QWORD, struct CmsTransactionCore *))qword_1402692F0)(
                            (char *)this + 8,
                            0,
                            a2);
          v63 = this;
          if ( v78 )
          {
            *v78 = 0;
            *(_OWORD *)((char *)v78 + 10) = 0;
            ++*((_DWORD *)this + 10);
            if ( v114 )
            {
              if ( v114 == 2 )
                *(_QWORD *)(v54 + 8) = v78;
              else
                *(_QWORD *)(v54 + 16) = v78;
              *(_QWORD *)v78 = v54;
              *((_BYTE *)this + 32) = -1;
              for ( i = *(_QWORD *)v78; ; v54 = i )
              {
                v109 = *(_QWORD *)(i + 8) == (_QWORD)v78;
                v110 = -1;
                v111 = *(_BYTE *)(v54 + 24);
                if ( !v109 )
                  v110 = 1;
                if ( v111 )
                  break;
                i = *(_QWORD *)v54;
                v78 = (_OWORD *)v54;
                *(_BYTE *)(v54 + 24) = v110;
              }
              v50 = (struct _RTL_AVL_ENTRY *)v133;
              if ( v111 == v110 )
              {
                RebalanceNode((struct _RTL_AVL_ENTRY *)v54);
                v63 = this;
              }
              else
              {
                *(_BYTE *)(v54 + 24) = 0;
              }
            }
            else
            {
              *v64 = (unsigned __int64)v78;
              *(_QWORD *)v78 = (char *)this + 8;
            }
          }
          v53 = a2;
        }
        v79 = *((_DWORD *)v63 + 12);
        v18 = (unsigned __int64)v50;
        --*((_BYTE *)v53 + 96);
        v122.m128i_i32[1] = v79;
        v120.m128i_i64[0] = (__int64)v50;
        v120.m128i_i64[1] = (__int64)v50;
        v122.m128i_i32[0] = 1;
        goto LABEL_84;
      }
    }
    v65 = 0;
LABEL_79:
    v114 = v65;
    goto LABEL_80;
  }
LABEL_194:
  v46 = -1073741670;
LABEL_85:
  if ( a7 )
  {
    *a7 = v20;
    a7[1] = v21;
  }
  if ( v136 && v46 >= 0 )
    *((_QWORD *)v136 + 4) = 0;
  if ( v137 )
    *v137 = (struct _RTL_AVL_ENTRY *)v18;
  if ( v46 >= 0 )
    goto LABEL_49;
LABEL_54:
  if ( (v148 & 1) != 0 && P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x14004c870  push    rbp
0x14004c872  push    rbx
0x14004c873  push    rdi
0x14004c874  push    r12
0x14004c876  push    r13
0x14004c878  push    r14
0x14004c87a  push    r15
0x14004c87c  lea     rbp, [rsp-0C0h]
0x14004c884  sub     rsp, 1C0h
0x14004c88b  mov     rax, cs:__security_cookie
0x14004c892  xor     rax, rsp
0x14004c895  mov     [rbp+0F0h+var_80], rax
0x14004c899  mov     rax, [rbp+0F0h+arg_28]
0x14004c8a0  xorps   xmm0, xmm0
0x14004c8a3  mov     r14, [r8]
0x14004c8a6  xor     r11b, r11b
0x14004c8a9  mov     r10, [r8+10h]
0x14004c8ad  mov     rdi, r9
0x14004c8b0  mov     r15, [r8+8]
0x14004c8b4  mov     rbx, r8
0x14004c8b7  mov     [rbp+0F0h+var_E8], rax
0x14004c8bb  xorps   xmm3, xmm3
0x14004c8be  mov     rax, [rbp+0F0h+arg_38]
0x14004c8c5  xorps   xmm4, xmm4
0x14004c8c8  mov     [rbp+0F0h+var_F8], rax
0x14004c8cc  lea     rax, [rbp+0F0h+var_A0]
0x14004c8d0  movups  xmmword ptr [rbp+0F0h+var_148], xmm0
0x14004c8d4  mov     [rbp+0F0h+P], rax
0x14004c8d8  pextrw  eax, xmm0, 2
0x14004c8dd  movups  [rbp+0F0h+var_120], xmm0
0x14004c8e1  mov     [rbp+0F0h+var_100], r9
0x14004c8e5  mov     r9, rcx
0x14004c8e8  movss   [rbp+0F0h+var_D0], xmm0
0x14004c8ed  mov     [rbp+0F0h+var_CC], ax
0x14004c8f1  movzx   eax, word ptr [rbp+0F0h+var_148+6]
0x14004c8f5  psrldq  xmm0, 8
0x14004c8fa  mov     [rbp+0F0h+var_170], rdx
0x14004c8fe  mov     rdx, [rbp+0F0h+arg_20]
0x14004c905  mov     [rsp+1F0h+var_190], rcx
0x14004c90a  mov     rcx, [rbp+0F0h+arg_30]
0x14004c911  movq    [rbp+0F0h+var_C8], xmm0
0x14004c916  xorps   xmm0, xmm0
0x14004c919  mov     [rbp+0F0h+var_CA], ax
0x14004c91d  mov     eax, dword ptr [rbp+0F0h+var_E8+4]
0x14004c920  mov     [rbp+0F0h+var_BC], eax
0x14004c923  mov     [rbp+0F0h+var_128], rcx
0x14004c927  mov     [rbp+0F0h+var_F0], rdx
0x14004c92b  mov     [rbp+0F0h+var_A4], 20h ; ' '
0x14004c932  mov     [rbp+0F0h+var_C0], 0
0x14004c939  mov     [rbp+0F0h+var_B8], 0
0x14004c941  mov     [rbp+0F0h+var_A8], 0
0x14004c945  mov     [rsp+1F0h+var_188], r14
0x14004c94a  mov     [rsp+1F0h+var_1B8], r10
0x14004c94f  mov     [rsp+1F0h+var_1D0], r11b
0x14004c954  mov     [rsp+1F0h+var_1CF], r11b
0x14004c959  movups  [rsp+1F0h+var_1B0], xmm0
0x14004c95e  movups  [rsp+1F0h+var_1A0], xmm0
0x14004c963  movups  xmmword ptr [rbp+0F0h+var_148], xmm0
0x14004c967  test    rdx, rdx
0x14004c96a  jnz     loc_14004D624
0x14004c970  mov     [rsp+1F0h+var_180], r15
0x14004c975  test    rdi, rdi
0x14004c978  jnz     loc_14004D094
0x14004c97e  mov     qword ptr [rbp+0F0h+var_120+8], rbx
0x14004c982  mov     dword ptr [rbp+0F0h+var_120], 10h
0x14004c989  mov     [rbp+0F0h+Src+8], rbx
0x14004c98d  mov     dword ptr [rbp+0F0h+Src], 18h
0x14004c994  mov     [rsp+1F0h+arg_10], rsi
0x14004c99c  mov     r13d, 2
0x14004c9a2  movaps  [rsp+1F0h+var_40], xmm6
0x14004c9aa  mov     r12d, 1
0x14004c9b0  movaps  [rsp+1F0h+var_50], xmm7
0x14004c9b8  movaps  [rsp+1F0h+var_60], xmm8
0x14004c9c1  movaps  [rsp+1F0h+var_70], xmm9
0x14004c9ca  mov     [rsp+1F0h+var_1CC], r13d
0x14004c9cf  test    rcx, rcx
0x14004c9d2  jnz     short loc_14004CA16
0x14004c9d4  mov     rdi, [r9+18h]
0x14004c9d8  mov     [rsp+1F0h+var_1C0], rdi
0x14004c9dd  test    rdi, rdi
0x14004c9e0  jnz     loc_14004CA82
0x14004c9e6  xor     esi, esi
0x14004c9e8  xor     r11d, r11d
0x14004c9eb  mov     eax, [r9+30h]
0x14004c9ef  mov     dword ptr [rsp+1F0h+var_1A0+4], eax
0x14004c9f3  mov     qword ptr [rsp+1F0h+var_1B0], rsi
0x14004c9f8  mov     qword ptr [rsp+1F0h+var_1B0+8], rdi
0x14004c9fd  movups  xmm6, [rsp+1F0h+var_1B0]
0x14004ca02  mov     dword ptr [rsp+1F0h+var_1A0], r11d
0x14004ca07  movups  xmm7, [rsp+1F0h+var_1A0]
0x14004ca0c  mov     [rsp+1F0h+var_1C8], r11d
0x14004ca11  jmp     loc_14004D68B
0x14004ca16  movups  xmm6, xmmword ptr [rcx]
0x14004ca19  movups  xmm7, xmmword ptr [rcx+10h]
0x14004ca1d  mov     rcx, [rcx]
0x14004ca20  movups  [rsp+1F0h+var_1B0], xmm6
0x14004ca25  movups  [rsp+1F0h+var_1A0], xmm7
0x14004ca2a  test    rcx, rcx
0x14004ca2d  jz      loc_14004D136
0x14004ca33  movzx   edx, byte ptr [rcx+1Ah]
0x14004ca37  add     rdx, rcx
0x14004ca3a  jz      loc_14004CD41
0x14004ca40  mov     r8, [rdx]
0x14004ca43  mov     rcx, [rdx+8]
0x14004ca47  mov     r9, [rbx]
0x14004ca4a  add     rcx, r8
0x14004ca4d  cmp     rcx, r9
0x14004ca50  jz      loc_14004D630
0x14004ca56  cmp     r8, r9
0x14004ca59  ja      loc_14004CD41
0x14004ca5f  movdqa  xmm0, xmm6
0x14004ca63  movss   [rsp+1F0h+var_1C8], xmm7
0x14004ca69  psrldq  xmm0, 8
0x14004ca6e  movq    rsi, xmm6
0x14004ca73  movq    rdi, xmm0
0x14004ca78  mov     [rsp+1F0h+var_1C0], rdi
0x14004ca7d  jmp     loc_14004CB3B
0x14004ca82  mov     r8, [r8]
0x14004ca85  test    rdi, rdi
0x14004ca88  jz      loc_14004D3C7
0x14004ca8e  movzx   eax, byte ptr [rdi+1Ah]
0x14004ca92  add     rax, rdi
0x14004ca95  mov     rdx, [rax]
0x14004ca98  cmp     r8, rdx
0x14004ca9b  jb      short loc_14004CAC3
0x14004ca9d  mov     rax, [rax+8]
0x14004caa1  mov     rsi, rdi
0x14004caa4  add     rax, rdx
0x14004caa7  cmp     r8, rax
0x14004caaa  jb      short loc_14004CADA
0x14004caac  mov     rax, [rdi+10h]
0x14004cab0  test    rax, rax
0x14004cab3  jz      loc_14004CD34
0x14004cab9  mov     rdi, rax
0x14004cabc  mov     [rsp+1F0h+var_1C0], rax
0x14004cac1  jmp     short loc_14004CA85
0x14004cac3  mov     rax, [rdi+8]
0x14004cac7  test    rax, rax
0x14004caca  jz      loc_14004CEE0
0x14004cad0  mov     rdi, rax
0x14004cad3  mov     [rsp+1F0h+var_1C0], rax
0x14004cad8  jmp     short loc_14004CA85
0x14004cada  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x14004cadf  mov     qword ptr [rsp+1F0h+var_1B0+8], rdi
0x14004cae4  mov     [rsp+1F0h+var_1C0], rdi
0x14004cae9  mov     [rsp+1F0h+var_1C8], r12d
0x14004caee  mov     dword ptr [rsp+1F0h+var_1A0], r12d
0x14004caf3  movups  xmm6, [rsp+1F0h+var_1B0]
0x14004caf8  test    rdi, rdi
0x14004cafb  jz      loc_14004D67B
0x14004cb01  movzx   eax, byte ptr [rdi+1Bh]
0x14004cb05  mov     [rbp+0F0h+var_D0], eax
0x14004cb08  movzx   eax, byte ptr [rdi+1Ah]
0x14004cb0c  add     rax, rdi
0x14004cb0f  mov     [rbp+0F0h+var_C8], rax
0x14004cb13  xor     eax, eax
0x14004cb15  mov     [rbp+0F0h+var_CC], ax
0x14004cb19  movzx   eax, word ptr [rdi+1Eh]
0x14004cb1d  mov     [rbp+0F0h+var_C0], eax
0x14004cb20  movzx   edx, byte ptr [rdi+1Ah]
0x14004cb24  mov     eax, [r9+30h]
0x14004cb28  add     rdx, rdi
0x14004cb2b  mov     [rbp+0F0h+var_B8], rdx
0x14004cb2f  mov     dword ptr [rsp+1F0h+var_1A0+4], eax
0x14004cb33  movups  xmm7, [rsp+1F0h+var_1A0]
0x14004cb38  mov     r8, [rdx]
0x14004cb3b  mov     rax, [rdx+8]
0x14004cb3f  lea     rcx, [r15+r14]
0x14004cb43  lea     r9, [rax+r8]
0x14004cb47  cmp     rcx, r9
0x14004cb4a  ja      loc_14004D65E
0x14004cb50  mov     [rsp+1F0h+var_180], 0
0x14004cb59  mov     r15, rax
0x14004cb5c  mov     rbx, [rdx]
0x14004cb5f  mov     r13, rdx
0x14004cb62  mov     rcx, [rdx+10h]
0x14004cb66  xor     r8b, r8b
0x14004cb69  mov     [rsp+1F0h+var_188], rbx
0x14004cb6e  mov     [rsp+1F0h+var_1B8], rcx
0x14004cb73  movups  [rbp+0F0h+var_168], xmm6
0x14004cb77  mov     [rsp+1F0h+var_1CC], 2
0x14004cb7f  movups  [rbp+0F0h+var_158], xmm7
0x14004cb83  mov     r14, rdi
0x14004cb86  test    rdi, rdi
0x14004cb89  jz      loc_14004CC94
0x14004cb8f  mov     eax, [rsp+1F0h+var_1C8]
0x14004cb93  dec     eax
0x14004cb95  test    eax, 0FFFFFFFDh
0x14004cb9a  jnz     short loc_14004CBD9
0x14004cb9c  mov     rax, [rdi+10h]
0x14004cba0  test    rax, rax
0x14004cba3  jnz     loc_14004D07A
0x14004cba9  mov     rax, [rdi]
0x14004cbac  cmp     [rax+10h], rdi
0x14004cbb0  jnz     loc_14004D04A
0x14004cbb6  mov     rcx, [rax]
0x14004cbb9  mov     rdx, rax
0x14004cbbc  mov     rax, rcx
0x14004cbbf  cmp     [rcx+10h], rdx
0x14004cbc3  jz      short loc_14004CBB6
0x14004cbc5  xor     r14d, r14d
0x14004cbc8  cmp     [rcx+8], rdx
0x14004cbcc  cmovz   r14, rcx
0x14004cbd0  test    r14, r14
0x14004cbd3  jz      loc_14004CC94
0x14004cbd9  mov     r12d, 1
0x14004cbdf  mov     qword ptr [rbp+0F0h+var_168+8], r14
0x14004cbe3  mov     eax, r12d
0x14004cbe6  mov     qword ptr [rbp+0F0h+var_168], r14
0x14004cbea  movups  xmm8, [rbp+0F0h+var_168]
0x14004cbef  mov     dword ptr [rbp+0F0h+var_158], eax
0x14004cbf2  movups  xmm9, [rbp+0F0h+var_158]
0x14004cbf7  mov     [rsp+1F0h+var_178], eax
0x14004cbfb  movzx   eax, byte ptr [r14+1Bh]
0x14004cc00  mov     [rbp+0F0h+var_D0], eax
0x14004cc03  movzx   eax, byte ptr [r14+1Ah]
0x14004cc08  add     rax, r14
0x14004cc0b  mov     [rbp+0F0h+var_C8], rax
0x14004cc0f  xor     eax, eax
0x14004cc11  mov     [rbp+0F0h+var_CC], ax
0x14004cc15  movzx   eax, word ptr [r14+1Eh]
0x14004cc1a  mov     [rbp+0F0h+var_C0], eax
0x14004cc1d  movzx   eax, byte ptr [r14+1Ah]
0x14004cc22  add     rax, r14
0x14004cc25  mov     [rbp+0F0h+var_B8], rax
0x14004cc29  mov     r9, [rbp+0F0h+var_148+8]
0x14004cc2d  xor     r10b, r10b
0x14004cc30  mov     edi, [rsp+1F0h+var_178]
0x14004cc34  add     r15, rbx
0x14004cc37  mov     [rbp+0F0h+var_148], r9
0x14004cc3b  test    r11b, r11b
0x14004cc3e  jnz     loc_14004D055
0x14004cc44  mov     r8, [rbp+0F0h+var_B8]
0x14004cc48  mov     rdx, [r8]
0x14004cc4b  cmp     r15, rdx
0x14004cc4e  jb      short loc_14004CC8F
0x14004cc50  mov     rcx, [r8+8]
0x14004cc54  mov     rax, r15
0x14004cc57  mov     r11, [rsp+1F0h+var_190]
0x14004cc5c  sub     rax, rdx
0x14004cc5f  lea     r9, [rcx+rdx]
0x14004cc63  cmp     r9, r15
0x14004cc66  cmovbe  rax, rcx
0x14004cc6a  sub     [rsp+1F0h+var_180], rax
0x14004cc6f  cmp     byte ptr [r11+38h], 0
0x14004cc74  mov     rax, [rsp+1F0h+var_1B8]
0x14004cc79  jnz     loc_14004D6FA
0x14004cc7f  sub     rdx, rbx
0x14004cc82  add     rax, rdx
0x14004cc85  cmp     rax, [r8+10h]
0x14004cc89  jz      loc_14004CF5F
0x14004cc8f  mov     rdi, [rsp+1F0h+var_1C0]
0x14004cc94  movaps  xmm9, [rsp+1F0h+var_70]
0x14004cc9d  movaps  xmm8, [rsp+1F0h+var_60]
0x14004cca6  test    r13, r13
0x14004cca9  jz      loc_14004CD71
0x14004ccaf  mov     rcx, [rbp+0F0h+var_F8]
0x14004ccb3  xor     ebx, ebx
0x14004ccb5  test    rcx, rcx
0x14004ccb8  jnz     loc_14004D82E
0x14004ccbe  mov     rax, [rbp+0F0h+var_F0]
0x14004ccc2  test    rax, rax
0x14004ccc5  jnz     loc_14004D83A
0x14004cccb  test    r13, r13
0x14004ccce  jz      short loc_14004CCDD
0x14004ccd0  mov     rax, [rbp+0F0h+var_E8]
0x14004ccd4  test    rax, rax
0x14004ccd7  jnz     loc_14004D847
0x14004ccdd  test    [rbp+0F0h+var_A8], 1
0x14004cce1  jz      short loc_14004CCFA
0x14004cce3  mov     rcx, [rbp+0F0h+P]; P
0x14004cce7  test    rcx, rcx
0x14004ccea  jz      short loc_14004CCFA
0x14004ccec  xor     edx, edx; Tag
0x14004ccee  call    cs:__imp_ExFreePoolWithTag
0x14004ccf5  nop     dword ptr [rax+rax+00h]
0x14004ccfa  movaps  xmm7, [rsp+1F0h+var_50]
0x14004cd02  mov     eax, ebx
0x14004cd04  movaps  xmm6, [rsp+1F0h+var_40]
0x14004cd0c  mov     rsi, [rsp+1F0h+arg_10]
0x14004cd14  mov     rcx, [rbp+0F0h+var_80]
0x14004cd18  xor     rcx, rsp; StackCookie
0x14004cd1b  call    __security_check_cookie
0x14004cd20  add     rsp, 1C0h
0x14004cd27  pop     r15
0x14004cd29  pop     r14
0x14004cd2b  pop     r13
0x14004cd2d  pop     r12
0x14004cd2f  pop     rdi
0x14004cd30  pop     rbx
0x14004cd31  pop     rbp
0x14004cd32  retn
0x14004cd34  xor     esi, esi
0x14004cd36  mov     r11d, 3
0x14004cd3c  jmp     loc_14004C9EB
0x14004cd41  mov     [rsp+1F0h+var_1D0], r12b
0x14004cd46  test    rdx, rdx
0x14004cd49  jz      loc_14004D13B
0x14004cd4f  movd    r11d, xmm7
0x14004cd54  movdqa  xmm0, xmm6
  ... truncated ...
```
