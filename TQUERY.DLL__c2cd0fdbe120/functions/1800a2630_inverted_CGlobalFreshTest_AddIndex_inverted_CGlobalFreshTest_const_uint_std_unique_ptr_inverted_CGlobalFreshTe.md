# inverted::CGlobalFreshTest::_AddIndex(inverted::CGlobalFreshTest const &,uint,std::unique_ptr<inverted::CGlobalFreshTest::CIndexInfo,std::default_delete<inverted::CGlobalFreshTest::CIndexInfo>> &,bool)

- ea: `0x1800a2630`
- end: `0x1800a33bd`
- name: `?_AddIndex@CGlobalFreshTest@inverted@@IEAAXAEBV12@IAEAV?$unique_ptr@VCIndexInfo@CGlobalFreshTest@inverted@@U?$default_delete@VCIndexInfo@CGlobalFreshTest@inverted@@@std@@@std@@_N@Z`
- size: `3469`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1800a1624`

## callees

- `0x180030114`
- `0x1800324c8`
- `0x180047e78`
- `0x180048b10`
- `0x180048bc8`
- `0x18004d9d8`
- `0x180050858`
- `0x1800a2630`
- `0x1800a33c4`
- `0x1800a33f4`
- `0x1800a34f4`
- `0x1800a3984`
- `0x1801183f0`
- `0x18013e868`
- `0x1801470d4`
- `0x180147190`
- `0x180188d90`
- `0x180189cce`
- `0x180217128`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a316b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a316b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a29c5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2cc6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2d11`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2e40`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a301f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a29c5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2cc6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2d11`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a2e40`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a301f`

## string_xrefs

- `0x1800a29e3`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800a2ce4`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800a2d2f`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800a2e5e`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800a303d`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall inverted::CGlobalFreshTest::_AddIndex(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4, char a5)
{
  __int64 v6; // r13
  _QWORD *v7; // r8
  unsigned int *v8; // rbx
  int *v9; // r14
  __int128 v10; // rdi
  _BYTE *v11; // r15
  __int64 v12; // r12
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // r15d
  unsigned int **v17; // r15
  unsigned int v18; // edi
  unsigned int v19; // edx
  unsigned int v20; // eax
  __int64 *v21; // r12
  unsigned int *v22; // r13
  __int64 v23; // rdi
  __int64 v24; // rax
  void **v25; // rax
  void *v26; // rsi
  unsigned __int64 v27; // rdx
  char v28; // di
  __int64 v29; // rax
  unsigned int *v30; // r8
  __int64 v31; // rdx
  unsigned int v32; // r13d
  unsigned int v33; // r12d
  unsigned int **v34; // r8
  unsigned int v35; // edx
  unsigned int v36; // eax
  __int64 **v37; // rax
  unsigned int *v38; // r13
  __int64 v39; // r12
  __int64 v40; // rax
  void **v41; // rax
  __int64 *v42; // r13
  unsigned __int64 v43; // rdx
  char v44; // r12
  __int64 v45; // rax
  unsigned int *v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  const char *v49; // r9
  unsigned int v50; // ecx
  int v51; // r12d
  char v52; // r13
  unsigned int v53; // edx
  __int64 *v54; // rax
  __int64 v55; // r12
  __int64 v56; // rax
  void **v57; // rax
  void *v58; // r13
  __int64 *v59; // r12
  unsigned __int64 v60; // rdx
  char v61; // r13
  __int64 v62; // rax
  unsigned int v63; // r9d
  unsigned int v64; // r13d
  unsigned int v65; // r8d
  __int64 v66; // r10
  __int64 v67; // rax
  __int64 *v68; // rax
  __int64 v69; // r12
  __int64 v70; // rax
  void **v71; // rax
  void *v72; // r13
  __int64 *v73; // r12
  unsigned __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  const char *v79; // r9
  __int64 v80; // r8
  const char *v81; // r9
  int v82; // ecx
  unsigned int v83; // r15d
  __int64 result; // rax
  __int64 v85; // r8
  void *v86; // rax
  const char *v87; // r9
  unsigned int v88; // ecx
  __int64 v89; // rax
  __int64 v90; // r13
  unsigned int v91; // edx
  __int64 *v92; // rax
  __int64 v93; // r12
  __int64 v94; // rax
  __int64 *v95; // rax
  int v96; // ecx
  int v97; // ecx
  __int64 *v98; // r12
  unsigned __int64 v99; // rdx
  __int64 v100; // rax
  __int64 v101; // r8
  const char *v102; // r9
  _QWORD *v103; // rax
  __int64 **v104; // rdx
  unsigned __int64 v105; // rdx
  _QWORD *v106; // rdx
  unsigned __int64 v107; // rdx
  _QWORD *v108; // rax
  _QWORD *v109; // rdx
  unsigned __int64 v110; // rdx
  _QWORD *v111; // rax
  _QWORD *v112; // rdx
  unsigned __int64 v113; // rdx
  _QWORD *v114; // rax
  __int64 *v115; // rdx
  unsigned __int64 v116; // rdx
  unsigned int v117; // [rsp+30h] [rbp-D0h]
  unsigned int v118; // [rsp+30h] [rbp-D0h]
  __int64 *v119; // [rsp+38h] [rbp-C8h] BYREF
  void *v120; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v121; // [rsp+48h] [rbp-B8h]
  unsigned int v122; // [rsp+50h] [rbp-B0h]
  _BYTE *v123; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v124; // [rsp+60h] [rbp-A0h]
  unsigned int v125; // [rsp+64h] [rbp-9Ch]
  __int64 v126; // [rsp+68h] [rbp-98h]
  __int64 v127; // [rsp+70h] [rbp-90h]
  unsigned int v128; // [rsp+78h] [rbp-88h]
  __int64 v129; // [rsp+80h] [rbp-80h]
  __int64 **v130; // [rsp+88h] [rbp-78h]
  unsigned int v131; // [rsp+90h] [rbp-70h] BYREF
  __int16 v132; // [rsp+94h] [rbp-6Ch]
  unsigned int v133; // [rsp+98h] [rbp-68h]
  __int64 v134; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v135; // [rsp+A4h] [rbp-5Ch]
  unsigned int v136; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v137; // [rsp+ACh] [rbp-54h]
  unsigned int v138; // [rsp+B0h] [rbp-50h]
  __int128 v139; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v140; // [rsp+C8h] [rbp-38h]
  _QWORD *v141; // [rsp+D0h] [rbp-30h]
  _BYTE v142[128]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v141 = a4;
  v122 = a3;
  v6 = a1;
  v127 = a1;
  v7 = (_QWORD *)(*a4 + 8LL);
  v139 = 0;
  v140 = 0;
  std::vector<inverted::CWIDPID>::_Construct_n<inverted::CWIDPID * const &,inverted::CWIDPID * const &>(
    &v139,
    (__int64)(v7[1] - *v7) >> 3);
  *(_DWORD *)(v6 + 168) = *(_DWORD *)(a2 + 168);
  *(_DWORD *)(v6 + 172) = *(_DWORD *)(a2 + 172);
  v8 = *(unsigned int **)(a2 + 232);
  v9 = *(int **)(a2 + 240);
  v10 = v139;
  sparse_bit_allocator<unsigned __int64>::sparse_bit_allocator<unsigned __int64>(v142, 0, 64);
  v123 = 0;
  v124 = -1;
  v125 = -1;
  v126 = 0;
  dynamic_sparse_bit<unsigned __int64>::Empty(&v123);
  v11 = v142;
  v123 = v142;
  v12 = v6 + 232;
  v129 = v6 + 232;
  while ( (_QWORD)v10 != *((_QWORD *)&v10 + 1) && v8 != (unsigned int *)v9 )
  {
    v32 = *(_DWORD *)v10;
    v128 = v32;
    v33 = *v8;
    v117 = *v8;
    if ( v32 < *v8 )
    {
      v13 = v127 + 232;
      LODWORD(v134) = v32;
      WORD2(v134) = *(_WORD *)(v10 + 4);
      v14 = v122;
      v135 = v122;
      v15 = *(_QWORD *)(v127 + 240);
      if ( v15 == *(_QWORD *)(v127 + 248) )
      {
        std::vector<inverted::CGlobalFreshTest::CReIndexed>::_Emplace_reallocate<inverted::CGlobalFreshTest::CReIndexed const &>(
          v13,
          v15,
          &v134);
      }
      else
      {
        *(_QWORD *)v15 = v134;
        *(_DWORD *)(v15 + 8) = v14;
        *(_QWORD *)(v13 + 8) += 12LL;
      }
      *(_QWORD *)&v10 = v10 + 8;
      v12 = v129;
      goto LABEL_5;
    }
    if ( v32 <= v33 )
    {
      v51 = *(unsigned __int16 *)(v10 + 4);
      LODWORD(v121) = v51;
      v136 = v32;
      v137 = v51;
      v138 = v122;
      std::vector<inverted::CGlobalFreshTest::CReIndexed>::push_back(v129, &v136);
      *(_QWORD *)&v10 = v10 + 8;
      if ( (_WORD)v51 )
      {
        v52 = v51;
        LODWORD(v130) = (unsigned __int16)v51;
        v53 = (unsigned __int16)v51 >> v11[20];
        v118 = v124;
        if ( v53 < v124 )
        {
          v54 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v123);
        }
        else
        {
          if ( v53 < v125 )
          {
            v54 = (__int64 *)(v126 + 8LL * (v53 - v124));
            goto LABEL_50;
          }
          v54 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v123);
        }
        v11 = v123;
        v118 = v124;
LABEL_50:
        v119 = v54;
        if ( *v54 )
        {
          v59 = v119;
        }
        else
        {
          v55 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v11 + 48);
          v56 = *(_QWORD *)(v55 + 24);
          if ( *(_QWORD *)(v55 + 16) == v56 )
          {
            v80 = *(unsigned int *)(v55 + 8);
            if ( (unsigned int)v80 < *((_DWORD *)v11 + 7) )
            {
              v58 = (void *)(*(_QWORD *)v55 + 8 * v80);
              v96 = v80 + *((_DWORD *)v11 + 2);
            }
            else
            {
              v58 = _aligned_malloc(8LL * *((unsigned int *)v11 + 7), *((unsigned int *)v11 + 8));
              v120 = v58;
              if ( !v58 )
                wil::details::in1diag3::_Throw_NullAlloc(
                  retaddr,
                  (void *)0x430,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                  v81);
              v111 = (_QWORD *)(v55 + 40);
              v112 = *(_QWORD **)(v55 + 48);
              if ( v112 == *(_QWORD **)(v55 + 56) )
              {
                std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                  v111,
                  v112,
                  &v120);
                v58 = v120;
                v111 = (_QWORD *)(v55 + 40);
              }
              else
              {
                *v112 = v58;
                *(_QWORD *)(v55 + 48) += 8LL;
              }
              v113 = *((unsigned int *)v11 + 6) * ((__int64)(*(_QWORD *)(v55 + 48) - *v111) >> 3);
              v120 = (void *)v113;
              if ( v113 > (__int64)(*(_QWORD *)(v55 + 32) - *(_QWORD *)(v55 + 16)) >> 3 )
              {
                if ( v113 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_145:
                  std::_Xlength_error("vector too long");
                std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v55 + 16, &v120);
              }
              *(_QWORD *)v55 = v58;
              v96 = *((_DWORD *)v11 + 2);
            }
            *(_DWORD *)(v55 + 8) = v96;
          }
          else
          {
            v57 = (void **)(v56 - 8);
            v58 = *v57;
            *(_QWORD *)(v55 + 24) = v57;
          }
          v59 = v119;
          *v119 = (__int64)v58;
          memset_0(v58, 0, *((unsigned int *)v11 + 1));
          v52 = (char)v130;
        }
        v60 = ((unsigned __int64)(unsigned __int16)v121 >> 6) & *((unsigned int *)v11 + 4);
        v61 = v52 & 0x3F;
        v62 = *(_QWORD *)(*v59 + 8 * v60);
        if ( (v62 & (1LL << v61)) == 0 )
          *(_QWORD *)(*v59 + 8 * v60) = (1LL << v61) | v62;
        v12 = v129;
        while ( 2 )
        {
          if ( (_QWORD)v10 == *((_QWORD *)&v10 + 1) || *(_DWORD *)v10 != v128 )
          {
            v63 = v118;
            while ( 1 )
            {
              v64 = *((unsigned __int16 *)v8 + 2);
              LODWORD(v121) = v64;
              v65 = v64 >> *((_DWORD *)v11 + 5);
              if ( v65 < v63 )
                goto LABEL_129;
              if ( v65 >= v125 )
                break;
              v66 = *(_QWORD *)(v126 + 8LL * (v65 - v63));
              if ( !v66 )
                break;
              v67 = *(_QWORD *)(v66 + 8 * (((unsigned __int64)v64 >> 6) & *((unsigned int *)v11 + 4)));
              if ( !_bittest64(&v67, v64 & 0x3F) )
                break;
LABEL_76:
              v8 += 3;
              if ( v8 == (unsigned int *)v9 || *v8 != v128 )
              {
                dynamic_sparse_bit<unsigned __int64>::Empty(&v123);
                v11 = v123;
                goto LABEL_5;
              }
            }
            if ( v65 < v63 )
            {
LABEL_129:
              v68 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v123);
            }
            else
            {
              if ( v65 < v125 )
              {
                v68 = (__int64 *)(v126 + 8LL * (v65 - v63));
LABEL_67:
                v119 = v68;
                if ( *v68 )
                {
                  v73 = v119;
                }
                else
                {
                  v69 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v11 + 48);
                  v70 = *(_QWORD *)(v69 + 24);
                  if ( *(_QWORD *)(v69 + 16) == v70 )
                  {
                    v78 = *(unsigned int *)(v69 + 8);
                    if ( (unsigned int)v78 < *((_DWORD *)v11 + 7) )
                    {
                      v72 = (void *)(*(_QWORD *)v69 + 8 * v78);
                      v82 = v78 + *((_DWORD *)v11 + 2);
                    }
                    else
                    {
                      v72 = _aligned_malloc(8LL * *((unsigned int *)v11 + 7), *((unsigned int *)v11 + 8));
                      v120 = v72;
                      if ( !v72 )
                        wil::details::in1diag3::_Throw_NullAlloc(
                          retaddr,
                          (void *)0x430,
                          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                          v79);
                      v108 = (_QWORD *)(v69 + 40);
                      v109 = *(_QWORD **)(v69 + 48);
                      if ( v109 == *(_QWORD **)(v69 + 56) )
                      {
                        std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                          v108,
                          v109,
                          &v120);
                        v72 = v120;
                        v108 = (_QWORD *)(v69 + 40);
                      }
                      else
                      {
                        *v109 = v72;
                        *(_QWORD *)(v69 + 48) += 8LL;
                      }
                      v110 = *((unsigned int *)v11 + 6) * ((__int64)(*(_QWORD *)(v69 + 48) - *v108) >> 3);
                      v120 = (void *)v110;
                      if ( v110 > (__int64)(*(_QWORD *)(v69 + 32) - *(_QWORD *)(v69 + 16)) >> 3 )
                      {
                        if ( v110 > 0x1FFFFFFFFFFFFFFFLL )
                          goto LABEL_145;
                        std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v69 + 16, &v120);
                      }
                      *(_QWORD *)v69 = v72;
                      v82 = *((_DWORD *)v11 + 2);
                    }
                    *(_DWORD *)(v69 + 8) = v82;
                  }
                  else
                  {
                    v71 = (void **)(v70 - 8);
                    v72 = *v71;
                    *(_QWORD *)(v69 + 24) = v71;
                  }
                  v73 = v119;
                  *v119 = (__int64)v72;
                  memset_0(v72, 0, *((unsigned int *)v11 + 1));
                  v64 = (unsigned int)v121;
                }
                v74 = ((unsigned __int64)v64 >> 6) & *((unsigned int *)v11 + 4);
                v75 = 1LL << (v64 & 0x3F);
                v76 = *(_QWORD *)(*v73 + 8 * v74);
                if ( (v76 & v75) == 0 )
                  *(_QWORD *)(*v73 + 8 * v74) = v75 | v76;
                v12 = v129;
                v77 = *(_QWORD *)(v129 + 8);
                if ( v77 == *(_QWORD *)(v129 + 16) )
                {
                  std::vector<inverted::CGlobalFreshTest::CReIndexed>::_Emplace_reallocate<inverted::CGlobalFreshTest::CReIndexed const &>(
                    v129,
                    v77,
                    v8);
                }
                else
                {
                  *(_QWORD *)v77 = *(_QWORD *)v8;
                  *(_DWORD *)(v77 + 8) = v8[2];
                  *(_QWORD *)(v12 + 8) += 12LL;
                }
                v63 = v118;
                goto LABEL_76;
              }
              v68 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v123);
            }
            v11 = v123;
            v118 = v124;
            goto LABEL_67;
          }
          LODWORD(v90) = *(unsigned __int16 *)(v10 + 4);
          LODWORD(v121) = v90;
          v91 = (unsigned int)v90 >> v11[20];
          if ( v91 < v118 )
          {
            v92 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v123);
          }
          else
          {
            if ( v91 < v125 )
            {
              v92 = (__int64 *)(v126 + 8LL * (v91 - v118));
LABEL_113:
              v119 = v92;
              if ( *v92 )
              {
                v98 = v119;
              }
              else
              {
                v93 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v11 + 48);
                v94 = *(_QWORD *)(v93 + 24);
                if ( *(_QWORD *)(v93 + 16) == v94 )
                {
                  v101 = *(unsigned int *)(v93 + 8);
                  if ( (unsigned int)v101 < *((_DWORD *)v11 + 7) )
                  {
                    v90 = *(_QWORD *)v93 + 8 * v101;
                    v97 = v101 + *((_DWORD *)v11 + 2);
                  }
                  else
                  {
                    v90 = (__int64)_aligned_malloc(8LL * *((unsigned int *)v11 + 7), *((unsigned int *)v11 + 8));
                    v120 = (void *)v90;
                    if ( !v90 )
                      wil::details::in1diag3::_Throw_NullAlloc(
                        retaddr,
                        (void *)0x430,
                        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                        v102);
                    v114 = (_QWORD *)(v93 + 40);
                    v115 = *(__int64 **)(v93 + 48);
                    if ( v115 == *(__int64 **)(v93 + 56) )
                    {
                      std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                        v114,
                        v115,
                        &v120);
                      v90 = (__int64)v120;
                      v114 = (_QWORD *)(v93 + 40);
                    }
                    else
                    {
                      *v115 = v90;
                      *(_QWORD *)(v93 + 48) += 8LL;
                    }
                    v116 = *((unsigned int *)v11 + 6) * ((__int64)(*(_QWORD *)(v93 + 48) - *v114) >> 3);
                    v120 = (void *)v116;
                    if ( v116 > (__int64)(*(_QWORD *)(v93 + 32) - *(_QWORD *)(v93 + 16)) >> 3 )
                    {
                      if ( v116 > 0x1FFFFFFFFFFFFFFFLL )
                        goto LABEL_145;
                      std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v93 + 16, &v120);
                    }
                    *(_QWORD *)v93 = v90;
                    v97 = *((_DWORD *)v11 + 2);
                  }
                  *(_DWORD *)(v93 + 8) = v97;
                }
                else
                {
                  v95 = (__int64 *)(v94 - 8);
                  v90 = *v95;
                  *(_QWORD *)(v93 + 24) = v95;
                }
                v98 = v119;
                *v119 = v90;
                memset_0((void *)v90, 0, *((unsigned int *)v11 + 1));
                LOWORD(v90) = (_WORD)v121;
              }
              v99 = ((unsigned __int64)(unsigned __int16)v90 >> 6) & *((unsigned int *)v11 + 4);
              v100 = *(_QWORD *)(*v98 + 8 * v99);
              if ( (v100 & (1LL << v90)) == 0 )
                *(_QWORD *)(*v98 + 8 * v99) = (1LL << v90) | v100;
              v131 = v128;
              v132 = v90;
              v133 = v122;
              v12 = v129;
              std::vector<inverted::CGlobalFreshTest::CReIndexed>::push_back(v129, &v131);
              *(_QWORD *)&v10 = v10 + 8;
              continue;
            }
            v92 = (__int64 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v123);
          }
          break;
        }
        v11 = v123;
        v118 = v124;
        goto LABEL_113;
      }
      do
      {
        v8 += 3;
        v12 = v129;
      }
      while ( v8 != (unsigned int *)v9 && *v8 == v32 );
LABEL_5:
      v6 = v127;
    }
    else
    {
      v6 = v127;
      v34 = (unsigned int **)(v127 + 176);
      v119 = (__int64 *)(v127 + 176);
      v35 = v33 >> *(_DWORD *)(*(_QWORD *)(v127 + 176) + 20LL);
      v36 = *(_DWORD *)(v127 + 184);
      if ( v35 < v36 )
      {
        v37 = (__int64 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v127 + 176);
      }
      else
      {
        if ( v35 < *(_DWORD *)(v127 + 188) )
        {
          v37 = (__int64 **)(*(_QWORD *)(v127 + 192) + 8LL * (v35 - v36));
          goto LABEL_27;
        }
        v37 = (__int64 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v127 + 176);
      }
      v34 = (unsigned int **)v119;
LABEL_27:
      v130 = v37;
      if ( !*v37 )
      {
        v38 = *v34;
        v121 = v38;
        v39 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v38 + 12);
        v40 = *(_QWORD *)(v39 + 24);
        if ( *(_QWORD *)(v39 + 16) == v40 )
        {
          v48 = *(unsigned int *)(v39 + 8);
          if ( (unsigned int)v48 < v38[7] )
          {
            v42 = (__int64 *)(*(_QWORD *)v39 + 8 * v48);
            v50 = v48 + v121[2];
          }
          else
          {
            v42 = (__int64 *)_aligned_malloc(8LL * v38[7], v38[8]);
            v119 = v42;
            if ( !v42 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v49);
            v103 = (_QWORD *)(v39 + 40);
            v104 = *(__int64 ***)(v39 + 48);
            if ( v104 == *(__int64 ***)(v39 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v103,
                v104,
                &v119);
              v42 = v119;
              v103 = (_QWORD *)(v39 + 40);
            }
            else
            {
              *v104 = v42;
              *(_QWORD *)(v39 + 48) += 8LL;
            }
            v105 = v121[6] * ((__int64)(*(_QWORD *)(v39 + 48) - *v103) >> 3);
            v120 = (void *)v105;
            if ( v105 > (__int64)(*(_QWORD *)(v39 + 32) - *(_QWORD *)(v39 + 16)) >> 3 )
            {
              if ( v105 > 0x1FFFFFFFFFFFFFFFLL )
                goto LABEL_145;
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v39 + 16, &v120);
            }
            *(_QWORD *)v39 = v42;
            v50 = v121[2];
          }
          *(_DWORD *)(v39 + 8) = v50;
        }
        else
        {
          v41 = (void **)(v40 - 8);
          v42 = (__int64 *)*v41;
          *(_QWORD *)(v39 + 24) = v41;
        }
        *v130 = v42;
        memset_0(v42, 0, v121[1]);
        v33 = v117;
        v6 = v127;
      }
      v43 = ((unsigned __int64)v33 >> 6) & *(unsigned int *)(*(_QWORD *)(v6 + 176) + 16LL);
      v44 = v33 & 0x3F;
      v45 = (*v130)[v43];
      if ( (v45 & (1LL << v44)) == 0 )
        (*v130)[v43] = (1LL << v44) | v45;
      v46 = v8;
      v8 += 3;
      v47 = *(_QWORD *)(v6 + 240);
      if ( v47 == *(_QWORD *)(v6 + 248) )
      {
        std::vector<inverted::CGlobalFreshTest::CReIndexed>::_Emplace_reallocate<inverted::CGlobalFreshTest::CReIndexed const &>(
          v6 + 232,
          v47,
          v46);
      }
      else
      {
        *(_QWORD *)v47 = *(_QWORD *)v46;
        *(_DWORD *)(v47 + 8) = v46[2];
        *(_QWORD *)(v6 + 240) += 12LL;
      }
      v12 = v6 + 232;
    }
  }
  v16 = v122;
  while ( (_QWORD)v10 != *((_QWORD *)&v10 + 1) )
  {
    v131 = *(_DWORD *)v10;
    v132 = *(_WORD *)(v10 + 4);
    v133 = v16;
    std::vector<inverted::CGlobalFreshTest::CReIndexed>::push_back(v12, &v131);
    *(_QWORD *)&v10 = v10 + 8;
  }
  while ( v8 != (unsigned int *)v9 )
  {
    v17 = (unsigned int **)(v6 + 176);
    v18 = *v8;
    LODWORD(v121) = v18;
    v19 = v18 >> *(_DWORD *)(*(_QWORD *)(v6 + 176) + 20LL);
    v20 = *(_DWORD *)(v6 + 184);
    if ( v19 < v20 )
    {
      v89 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6 + 176);
    }
    else
    {
      if ( v19 < *(_DWORD *)(v6 + 188) )
      {
        v21 = (__int64 *)(*(_QWORD *)(v6 + 192) + 8LL * (v19 - v20));
        goto LABEL_13;
      }
      v89 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6 + 176);
    }
    v21 = (__int64 *)v89;
LABEL_13:
    v119 = v21;
    if ( !*v21 )
    {
      v22 = *v17;
      v23 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*v17 + 12);
      v24 = *(_QWORD *)(v23 + 24);
      if ( *(_QWORD *)(v23 + 16) == v24 )
      {
        v85 = *(unsigned int *)(v23 + 8);
        if ( (unsigned int)v85 < v22[7] )
        {
          v26 = (void *)(*(_QWORD *)v23 + 8 * v85);
          v88 = v85 + v22[2];
        }
        else
        {
          v86 = _aligned_malloc(8LL * v22[7], v22[8]);
          v26 = v86;
          v120 = v86;
          if ( !v86 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v87);
          v106 = *(_QWORD **)(v23 + 48);
          if ( v106 == *(_QWORD **)(v23 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v23 + 40,
              v106,
              &v120);
            v26 = v120;
          }
          else
          {
            *v106 = v86;
            *(_QWORD *)(v23 + 48) += 8LL;
          }
          v107 = v22[6] * ((__int64)(*(_QWORD *)(v23 + 48) - *(_QWORD *)(v23 + 40)) >> 3);
          v120 = (void *)v107;
          if ( v107 > (__int64)(*(_QWORD *)(v23 + 32) - *(_QWORD *)(v23 + 16)) >> 3 )
          {
            if ( v107 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_145;
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v23 + 16, &v120);
          }
          *(_QWORD *)v23 = v26;
          v88 = v22[2];
          v21 = v119;
        }
        *(_DWORD *)(v23 + 8) = v88;
      }
      else
      {
        v25 = (void **)(v24 - 8);
        v26 = *v25;
        *(_QWORD *)(v23 + 24) = v25;
      }
      *v21 = (__int64)v26;
      memset_0(v26, 0, v22[1]);
      v18 = (unsigned int)v121;
      v6 = v127;
    }
    v27 = ((unsigned __int64)v18 >> 6) & (*v17)[4];
    v28 = v18 & 0x3F;
    v29 = *(_QWORD *)(*v21 + 8 * v27);
    if ( (v29 & (1LL << v28)) == 0 )
      *(_QWORD *)(*v21 + 8 * v27) = (1LL << v28) | v29;
    v30 = v8;
    v8 += 3;
    v31 = *(_QWORD *)(v6 + 240);
    if ( v31 == *(_QWORD *)(v6 + 248) )
    {
      std::vector<inverted::CGlobalFreshTest::CReIndexed>::_Emplace_reallocate<inverted::CGlobalFreshTest::CReIndexed const &>(
        v6 + 232,
        v31,
        v30);
    }
    else
    {
      *(_QWORD *)v31 = *(_QWORD *)v30;
      *(_DWORD *)(v31 + 8) = v30[2];
      *(_QWORD *)(v6 + 240) += 12LL;
    }
  }
  v83 = v122;
  if ( v122 < *(_DWORD *)(v6 + 168) )
    *(_DWORD *)(v6 + 168) = v122;
  if ( v83 > *(_DWORD *)(v6 + 172) )
    *(_DWORD *)(v6 + 172) = v83;
  inverted::CGlobalFreshTest::CIndices::_AddIndex(v6 + 256, v141);
  if ( a5 )
    inverted::CGlobalFreshTest::CIndices::Save((inverted::CGlobalFreshTest::CIndices *)(v6 + 256));
  _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::clear(&v123);
  result = sparse_bit_allocator<unsigned __int64>::~sparse_bit_allocator<unsigned __int64>(v142);
  if ( (_QWORD)v139 )
    return std::_Deallocate<16>(v139, (v140 - v139) & 0xFFFFFFFFFFFFFFF8uLL);
  return result;
}

```

## disassembly

```asm
0x1800a2630  mov     [rsp-8+arg_8], rbx
0x1800a2635  push    rbp
0x1800a2636  push    rsi
0x1800a2637  push    rdi
0x1800a2638  push    r12
0x1800a263a  push    r13
0x1800a263c  push    r14
0x1800a263e  push    r15
0x1800a2640  lea     rbp, [rsp-70h]
0x1800a2645  sub     rsp, 170h
0x1800a264c  mov     rax, cs:__security_cookie
0x1800a2653  xor     rax, rsp
0x1800a2656  mov     [rbp+0A0h+var_40], rax
0x1800a265a  mov     [rbp+0A0h+var_D0], r9
0x1800a265e  mov     [rsp+1A0h+var_150], r8d
0x1800a2663  mov     r14, rdx
0x1800a2666  mov     r13, rcx
0x1800a2669  mov     [rsp+1A0h+var_130], rcx
0x1800a266e  mov     r8, [r9]
0x1800a2671  add     r8, 8
0x1800a2675  xorps   xmm0, xmm0
0x1800a2678  movdqu  [rbp+0A0h+var_E8], xmm0
0x1800a267d  xor     r15d, r15d
0x1800a2680  mov     [rbp+0A0h+var_D8], r15
0x1800a2684  lea     r9, [r8+8]
0x1800a2688  mov     rdx, [r9]
0x1800a268b  sub     rdx, [r8]
0x1800a268e  sar     rdx, 3
0x1800a2692  lea     rcx, [rbp+0A0h+var_E8]
0x1800a2696  call    ??$_Construct_n@AEBQEAVCWIDPID@inverted@@AEBQEAV12@@?$vector@VCWIDPID@inverted@@V?$allocator@VCWIDPID@inverted@@@std@@@std@@AEAAX_KAEBQEAVCWIDPID@inverted@@1@Z; std::vector<inverted::CWIDPID>::_Construct_n<inverted::CWIDPID * const &,inverted::CWIDPID * const &>(unsigned __int64,inverted::CWIDPID * const &,inverted::CWIDPID * const &)
0x1800a269b  nop
0x1800a269c  mov     eax, [r14+0A8h]
0x1800a26a3  mov     [r13+0A8h], eax
0x1800a26aa  mov     eax, [r14+0ACh]
0x1800a26b1  mov     [r13+0ACh], eax
0x1800a26b8  mov     rbx, [r14+0E8h]
0x1800a26bf  mov     r14, [r14+0F0h]
0x1800a26c6  mov     rdi, qword ptr [rbp+0A0h+var_E8]
0x1800a26ca  mov     rsi, qword ptr [rbp+0A0h+var_E8+8]
0x1800a26ce  xor     edx, edx
0x1800a26d0  lea     r8d, [r15+40h]
0x1800a26d4  lea     rcx, [rbp+0A0h+var_C0]
0x1800a26d8  call    ??0?$sparse_bit_allocator@_K@@QEAA@KKKK@Z; sparse_bit_allocator<unsigned __int64>::sparse_bit_allocator<unsigned __int64>(ulong,ulong,ulong,ulong)
0x1800a26dd  nop
0x1800a26de  mov     [rsp+1A0h+var_148], r15
0x1800a26e3  or      eax, 0FFFFFFFFh
0x1800a26e6  mov     [rsp+1A0h+var_140], eax
0x1800a26ea  mov     [rsp+1A0h+var_13C], eax
0x1800a26ee  mov     [rsp+1A0h+var_138], r15
0x1800a26f3  lea     rcx, [rsp+1A0h+var_148]
0x1800a26f8  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x1800a26fd  lea     r15, [rbp+0A0h+var_C0]
0x1800a2701  mov     [rsp+1A0h+var_148], r15
0x1800a2706  lea     r12, [r13+0E8h]
0x1800a270d  mov     [rbp+0A0h+var_120], r12
0x1800a2711  jmp     short loc_1800A275E
0x1800a2713  mov     rcx, [rsp+1A0h+var_130]
0x1800a2718  add     rcx, 0E8h
0x1800a271f  mov     dword ptr [rbp+0A0h+var_104], r13d
0x1800a2723  movzx   eax, word ptr [rdi+4]
0x1800a2727  mov     word ptr [rbp+0A0h+var_104+4], ax
0x1800a272b  mov     eax, [rsp+1A0h+var_150]
0x1800a272f  mov     [rbp+0A0h+var_FC], eax
0x1800a2732  mov     rdx, [rcx+8]
0x1800a2736  cmp     rdx, [rcx+10h]
0x1800a273a  jz      loc_1800A32FF
0x1800a2740  movsd   xmm0, [rbp+0A0h+var_104]
0x1800a2745  movsd   qword ptr [rdx], xmm0
0x1800a2749  mov     [rdx+8], eax
0x1800a274c  add     qword ptr [rcx+8], 0Ch
0x1800a2751  add     rdi, 8
0x1800a2755  mov     r12, [rbp+0A0h+var_120]
0x1800a2759  mov     r13, [rsp+1A0h+var_130]
0x1800a275e  cmp     rdi, rsi
0x1800a2761  jnz     loc_1800A2872
0x1800a2767  mov     r15d, [rsp+1A0h+var_150]
0x1800a276c  cmp     rdi, rsi
0x1800a276f  jnz     loc_1800A2EB8
0x1800a2775  cmp     rbx, r14
0x1800a2778  jz      loc_1800A2D89
0x1800a277e  lea     r15, [r13+0B0h]
0x1800a2785  mov     edi, [rbx]
0x1800a2787  mov     dword ptr [rsp+1A0h+var_158], edi
0x1800a278b  mov     rcx, [r15]
0x1800a278e  mov     ecx, [rcx+14h]
0x1800a2791  mov     edx, edi
0x1800a2793  shr     edx, cl
0x1800a2795  mov     eax, [r13+0B8h]
0x1800a279c  cmp     edx, eax
0x1800a279e  jb      loc_1800A2E9E
0x1800a27a4  cmp     edx, [r15+0Ch]
0x1800a27a8  jnb     loc_1800A2EAE
0x1800a27ae  sub     edx, eax
0x1800a27b0  mov     rax, [r15+10h]
0x1800a27b4  lea     r12, [rax+rdx*8]
0x1800a27b8  mov     [rsp+1A0h+var_168], r12
0x1800a27bd  cmp     qword ptr [r12], 0
0x1800a27c2  jnz     short loc_1800A2807
0x1800a27c4  mov     r13, [r15]
0x1800a27c7  lea     rcx, [r13+30h]
0x1800a27cb  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800a27d0  mov     rdi, rax
0x1800a27d3  mov     rax, [rax+18h]
0x1800a27d7  cmp     [rdi+10h], rax
0x1800a27db  jz      loc_1800A2E2A
0x1800a27e1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a27e5  mov     rsi, [rax]
0x1800a27e8  mov     [rdi+18h], rax
0x1800a27ec  mov     [r12], rsi
0x1800a27f0  mov     r8d, [r13+4]; Size
0x1800a27f4  xor     edx, edx; Val
0x1800a27f6  mov     rcx, rsi; void *
0x1800a27f9  call    memset_0
0x1800a27fe  mov     edi, dword ptr [rsp+1A0h+var_158]
0x1800a2802  mov     r13, [rsp+1A0h+var_130]
0x1800a2807  mov     rax, [r15]
0x1800a280a  mov     edx, [rax+10h]
0x1800a280d  mov     eax, edi
0x1800a280f  shr     rax, 6
0x1800a2813  and     rdx, rax
0x1800a2816  mov     r9, [r12]
0x1800a281a  and     edi, 3Fh
0x1800a281d  mov     r8d, 1
0x1800a2823  mov     cl, dil
0x1800a2826  shl     r8, cl
0x1800a2829  mov     rax, [r9+rdx*8]
0x1800a282d  test    r8, rax
0x1800a2830  jnz     short loc_1800A2839
0x1800a2832  or      rax, r8
0x1800a2835  mov     [r9+rdx*8], rax
0x1800a2839  mov     r8, rbx
0x1800a283c  add     rbx, 0Ch
0x1800a2840  lea     r12, [r13+0E8h]
0x1800a2847  mov     rdx, [r12+8]
0x1800a284c  cmp     rdx, [r12+10h]
0x1800a2851  jz      loc_1800A33AF
0x1800a2857  movsd   xmm0, qword ptr [r8]
0x1800a285c  movsd   qword ptr [rdx], xmm0
0x1800a2860  mov     eax, [r8+8]
0x1800a2864  mov     [rdx+8], eax
0x1800a2867  add     qword ptr [r12+8], 0Ch
0x1800a286d  jmp     loc_1800A2775
0x1800a2872  cmp     rbx, r14
0x1800a2875  jz      loc_1800A2767
0x1800a287b  mov     r13d, [rdi]
0x1800a287e  mov     [rsp+1A0h+var_128], r13d
0x1800a2883  mov     r12d, [rbx]
0x1800a2886  mov     [rsp+1A0h+var_170], r12d
0x1800a288b  cmp     r13d, r12d
0x1800a288e  jb      loc_1800A2713
0x1800a2894  jbe     loc_1800A2A46
0x1800a289a  mov     r13, [rsp+1A0h+var_130]
0x1800a289f  lea     r8, [r13+0B0h]
0x1800a28a6  mov     [rsp+1A0h+var_168], r8
0x1800a28ab  mov     rcx, [r8]
0x1800a28ae  mov     ecx, [rcx+14h]
0x1800a28b1  mov     edx, r12d
0x1800a28b4  shr     edx, cl
0x1800a28b6  mov     eax, [r13+0B8h]
0x1800a28bd  cmp     edx, eax
0x1800a28bf  jb      loc_1800A2A2A
0x1800a28c5  cmp     edx, [r8+0Ch]
0x1800a28c9  jnb     loc_1800A2A3C
0x1800a28cf  sub     edx, eax
0x1800a28d1  mov     rax, [r8+10h]
0x1800a28d5  lea     rax, [rax+rdx*8]
0x1800a28d9  mov     [rbp+0A0h+var_118], rax
0x1800a28dd  cmp     qword ptr [rax], 0
0x1800a28e1  jnz     short loc_1800A2936
0x1800a28e3  mov     r13, [r8]
0x1800a28e6  mov     [rsp+1A0h+var_158], r13
0x1800a28eb  lea     rcx, [r13+30h]
0x1800a28ef  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800a28f4  mov     r12, rax
0x1800a28f7  mov     rax, [rax+18h]
0x1800a28fb  cmp     [r12+10h], rax
0x1800a2900  jz      loc_1800A29AE
0x1800a2906  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a290a  mov     r13, [rax]
0x1800a290d  mov     [r12+18h], rax
0x1800a2912  mov     rax, [rbp+0A0h+var_118]
0x1800a2916  mov     [rax], r13
0x1800a2919  mov     rax, [rsp+1A0h+var_158]
0x1800a291e  mov     r8d, [rax+4]; Size
0x1800a2922  xor     edx, edx; Val
0x1800a2924  mov     rcx, r13; void *
0x1800a2927  call    memset_0
0x1800a292c  mov     r12d, [rsp+1A0h+var_170]
0x1800a2931  mov     r13, [rsp+1A0h+var_130]
0x1800a2936  mov     rax, [r13+0B0h]
0x1800a293d  mov     edx, [rax+10h]
0x1800a2940  mov     eax, r12d
0x1800a2943  shr     rax, 6
0x1800a2947  and     rdx, rax
0x1800a294a  mov     rax, [rbp+0A0h+var_118]
0x1800a294e  mov     r9, [rax]
0x1800a2951  and     r12d, 3Fh
0x1800a2955  mov     r8d, 1
0x1800a295b  mov     cl, r12b
0x1800a295e  shl     r8, cl
0x1800a2961  mov     rax, [r9+rdx*8]
0x1800a2965  test    r8, rax
0x1800a2968  jnz     short loc_1800A2971
0x1800a296a  or      rax, r8
0x1800a296d  mov     [r9+rdx*8], rax
0x1800a2971  lea     rcx, [r13+0E8h]
0x1800a2978  mov     r8, rbx
0x1800a297b  add     rbx, 0Ch
0x1800a297f  mov     rdx, [rcx+8]
0x1800a2983  cmp     rdx, [rcx+10h]
0x1800a2987  jz      loc_1800A3329
0x1800a298d  movsd   xmm0, qword ptr [r8]
0x1800a2992  movsd   qword ptr [rdx], xmm0
0x1800a2996  mov     eax, [r8+8]
0x1800a299a  mov     [rdx+8], eax
0x1800a299d  add     qword ptr [rcx+8], 0Ch
0x1800a29a2  lea     r12, [r13+0E8h]
0x1800a29a9  jmp     loc_1800A275E
0x1800a29ae  mov     r8d, [r12+8]
0x1800a29b3  cmp     r8d, [r13+1Ch]
0x1800a29b7  jb      short loc_1800A29F5
0x1800a29b9  mov     edx, [r13+20h]; Alignment
0x1800a29bd  mov     ecx, [r13+1Ch]
0x1800a29c1  shl     rcx, 3; Size
0x1800a29c5  call    cs:__imp__aligned_malloc
0x1800a29cb  mov     r13, rax
0x1800a29ce  mov     [rsp+1A0h+var_168], rax
0x1800a29d3  mov     rcx, [rbp+0A8h]; this
0x1800a29da  test    rax, rax
0x1800a29dd  jnz     loc_1800A30FF
0x1800a29e3  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800a29ea  mov     edx, 430h; void *
0x1800a29ef  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a29f5  mov     rcx, [r12]
0x1800a29f9  lea     r13, [rcx+r8*8]
0x1800a29fd  mov     rax, [rsp+1A0h+var_158]
0x1800a2a02  mov     ecx, [rax+8]
0x1800a2a05  add     ecx, r8d
0x1800a2a08  jmp     short loc_1800A2A20
0x1800a2a0a  lea     rdx, [rsp+1A0h+var_160]
0x1800a2a0f  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800a2a14  mov     [r12], r13
0x1800a2a18  mov     rax, [rsp+1A0h+var_158]
0x1800a2a1d  mov     ecx, [rax+8]
0x1800a2a20  mov     [r12+8], ecx
0x1800a2a25  jmp     loc_1800A2912
0x1800a2a2a  mov     rcx, r8
0x1800a2a2d  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800a2a32  mov     r8, [rsp+1A0h+var_168]
0x1800a2a37  jmp     loc_1800A28D9
0x1800a2a3c  mov     rcx, r8
0x1800a2a3f  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800a2a44  jmp     short loc_1800A2A32
0x1800a2a46  movzx   r12d, word ptr [rdi+4]
0x1800a2a4b  mov     dword ptr [rsp+1A0h+var_158], r12d
0x1800a2a50  mov     [rbp+0A0h+var_F8], r13d
0x1800a2a54  mov     [rbp+0A0h+var_F4], r12w
0x1800a2a59  mov     eax, [rsp+1A0h+var_150]
0x1800a2a5d  mov     [rbp+0A0h+var_F0], eax
0x1800a2a60  lea     rdx, [rbp+0A0h+var_F8]
0x1800a2a64  mov     rcx, [rbp+0A0h+var_120]
0x1800a2a68  call    ?push_back@?$vector@VCReIndexed@CGlobalFreshTest@inverted@@V?$allocator@VCReIndexed@CGlobalFreshTest@inverted@@@std@@@std@@QEAAX$$QEAVCReIndexed@CGlobalFreshTest@inverted@@@Z; std::vector<inverted::CGlobalFreshTest::CReIndexed>::push_back(inverted::CGlobalFreshTest::CReIndexed &&)
0x1800a2a6d  add     rdi, 8
0x1800a2a71  test    r12w, r12w
0x1800a2a75  jz      loc_1800A2D41
0x1800a2a7b  movzx   r13d, r12w
0x1800a2a7f  mov     dword ptr [rbp+0A0h+var_118], r13d
0x1800a2a83  mov     cl, [r15+14h]
0x1800a2a87  mov     edx, r13d
0x1800a2a8a  shr     edx, cl
0x1800a2a8c  mov     r8d, [rsp+1A0h+var_140]
0x1800a2a91  mov     [rsp+1A0h+var_170], r8d
0x1800a2a96  cmp     edx, r8d
0x1800a2a99  jb      loc_1800A3091
0x1800a2a9f  cmp     edx, [rsp+1A0h+var_13C]
0x1800a2aa3  jnb     loc_1800A30AD
0x1800a2aa9  sub     edx, r8d
0x1800a2aac  mov     rax, [rsp+1A0h+var_138]
0x1800a2ab1  lea     rax, [rax+rdx*8]
0x1800a2ab5  mov     [rsp+1A0h+var_168], rax
0x1800a2aba  cmp     qword ptr [rax], 0
0x1800a2abe  jnz     loc_1800A30C3
0x1800a2ac4  lea     rcx, [r15+30h]
0x1800a2ac8  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800a2acd  mov     r12, rax
0x1800a2ad0  mov     rax, [rax+18h]
0x1800a2ad4  cmp     [r12+10h], rax
0x1800a2ad9  jz      loc_1800A2CF6
0x1800a2adf  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a2ae3  mov     r13, [rax]
0x1800a2ae6  mov     [r12+18h], rax
0x1800a2aeb  mov     r12, [rsp+1A0h+var_168]
0x1800a2af0  mov     [r12], r13
0x1800a2af4  mov     r8d, [r15+4]; Size
0x1800a2af8  xor     edx, edx; Val
0x1800a2afa  mov     rcx, r13; void *
0x1800a2afd  call    memset_0
0x1800a2b02  mov     r13d, dword ptr [rbp+0A0h+var_118]
0x1800a2b06  mov     edx, [r15+10h]
0x1800a2b0a  movzx   eax, word ptr [rsp+1A0h+var_158]
  ... truncated ...
```
