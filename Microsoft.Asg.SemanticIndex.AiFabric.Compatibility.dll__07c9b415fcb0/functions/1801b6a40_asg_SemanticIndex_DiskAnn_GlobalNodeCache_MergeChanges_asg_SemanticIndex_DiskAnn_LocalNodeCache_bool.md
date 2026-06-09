# asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(asg::SemanticIndex::DiskAnn::LocalNodeCache &&,bool)

- ea: `0x1801b6a40`
- end: `0x1801b7950`
- name: `?MergeChanges@GlobalNodeCache@DiskAnn@SemanticIndex@asg@@QEAAX$$QEAVLocalNodeCache@234@_N@Z`
- size: `3856`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018d8e0`
- `0x18018dd10`

## callees

- `0x180006220`
- `0x180006b60`
- `0x180006e30`
- `0x180007ba0`
- `0x18002b520`
- `0x18002db00`
- `0x18003f180`
- `0x180078ed0`
- `0x1801b57d0`
- `0x1801b58a0`
- `0x1801b5a60`
- `0x1801b5d50`
- `0x1801b6a40`
- `0x1801b7cc0`
- `0x1801d2a80`
- `0x1801d2aa0`
- `0x1801d2ac0`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x180206ec0`

## string_xrefs

- `0x1801b78ed`: `auto __cdecl asg::SemanticIndex::SelectTopK<struct std::pair<unsigned int,unsigned int>,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>>(class std::vector<struct std::pair<unsigned int,unsigned int>,class std::allocator<struct std::pair<unsigned int,unsigned int> > > &,unsigned __int64,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>,enum asg::SemanticIndex::TopKMethod)`
- `0x1801b7920`: `auto __cdecl asg::SemanticIndex::SelectTopK<struct std::pair<unsigned int,unsigned int>,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>>(class std::vector<struct std::pair<unsigned int,unsigned int>,class std::allocator<struct std::pair<unsigned int,unsigned int> > > &,unsigned __int64,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>,enum asg::SemanticIndex::TopKMethod)`
- `0x1801b784f`: `C:\__w\1\s\src\SemanticIndex\internal\libSemanticSearch\DiskAnn\GraphNodeCache.cpp`
- `0x1801b787d`: `C:\__w\1\s\src\SemanticIndex\internal\libSemanticSearch\DiskAnn\GraphNodeCache.cpp`
- `0x1801b78ab`: `C:\__w\1\s\src\SemanticIndex\internal\libSemanticSearch\DiskAnn\GraphNodeCache.cpp`
- `0x1801b785a`: `void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::DiskAnn::LocalNodeCache &&,bool)`
- `0x1801b7888`: `void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::DiskAnn::LocalNodeCache &&,bool)`
- `0x1801b78b6`: `void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::DiskAnn::LocalNodeCache &&,bool)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(__int64 a1, __int64 a2, char a3)
{
  unsigned __int64 *v4; // rsi
  _Smtx_t *v5; // rdi
  _Smtx_t *v6; // rcx
  _Smtx_t **v7; // rax
  char v8; // bl
  unsigned __int8 v9; // r15
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  _QWORD *v17; // rax
  void *v18; // rax
  _QWORD *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r15
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r12
  __int64 v26; // rax
  _QWORD *v27; // rbx
  __int64 v28; // r14
  int v29; // esi
  __int64 v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // ecx
  int v33; // eax
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  int v36; // r11d
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  __int64 v39; // r8
  int v40; // edx
  _QWORD *v41; // rdx
  __int64 v42; // rbx
  unsigned __int64 *v43; // r12
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // r14
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rsi
  char v51; // r9
  unsigned int v52; // r8d
  int v53; // r10d
  __int64 **v54; // rcx
  __int64 *i; // rax
  unsigned int v56; // edx
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // r9
  __int64 v59; // r11
  _QWORD *v60; // rcx
  unsigned __int64 v61; // r10
  _QWORD *v62; // rax
  __int64 v63; // rdx
  __int64 **v64; // rdi
  __int64 *v65; // rbx
  __int64 **v66; // rax
  unsigned __int64 v67; // rsi
  size_t v68; // rsi
  unsigned __int8 *v69; // rcx
  unsigned __int64 v70; // rdx
  unsigned __int8 *v71; // r8
  unsigned __int64 j; // r9
  unsigned __int64 v73; // rax
  __int64 v74; // r15
  unsigned __int64 v75; // rbx
  int v76; // eax
  int v77; // eax
  int v78; // eax
  int *v79; // rbx
  _QWORD *v80; // r14
  char *v81; // r12
  __int64 v82; // r15
  _DWORD *v83; // r13
  __int64 v84; // r10
  __int64 v85; // r11
  _Smtx_t *v86; // rax
  __int64 v87; // r9
  __int64 k; // rdx
  unsigned int v89; // r8d
  __int64 v90; // rdx
  int *m; // rdi
  int v92; // ecx
  int v93; // ecx
  _Smtx_t *v94; // rax
  __int64 v95; // r8
  __int64 v96; // rdx
  char *v97; // rbx
  char *v98; // rdx
  signed __int64 v99; // rsi
  signed __int64 v100; // r10
  __int64 v101; // rdi
  _Smtx_t *v102; // rax
  __int64 v103; // r9
  __int64 n; // r8
  unsigned int v105; // r11d
  __int64 v106; // r8
  char *v107; // rsi
  __int64 v108; // r14
  __int64 v109; // r9
  unsigned __int8 *v110; // r8
  unsigned __int8 *ii; // rdx
  unsigned __int8 *v112; // rax
  int v113; // edx
  int v114; // edx
  __int64 v115; // rdx
  unsigned __int8 *v116; // rbx
  __int64 v117; // r14
  unsigned __int8 *v118; // rdi
  __int64 v119; // r13
  __int64 v120; // rax
  unsigned __int64 v121; // r8
  unsigned __int64 v122; // r10
  __int64 v123; // rsi
  _QWORD *v124; // rcx
  unsigned __int64 v125; // r11
  _QWORD *v126; // r9
  __int64 v127; // rdx
  void *v128; // r8
  double v129; // xmm0_8
  unsigned __int64 v130; // rcx
  double v131; // xmm1_8
  double v132; // xmm0_8
  unsigned __int64 v133; // rax
  unsigned __int64 v134; // rcx
  __int64 v135; // r15
  unsigned __int8 **v136; // rdi
  unsigned __int8 *v137; // rbx
  __int64 v138; // rdx
  __int64 v139; // rax
  __int64 v140; // rcx
  volatile signed __int32 *v141; // rsi
  _QWORD **v142; // rdi
  _QWORD *v143; // rcx
  _QWORD *v144; // rbx
  int Reserved; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v146; // [rsp+30h] [rbp-D0h]
  __int64 v147; // [rsp+38h] [rbp-C8h] BYREF
  _Smtx_t *v148; // [rsp+40h] [rbp-C0h] BYREF
  const char *v149; // [rsp+48h] [rbp-B8h]
  const char *v150; // [rsp+50h] [rbp-B0h]
  __int64 v151; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v152; // [rsp+68h] [rbp-98h]
  _Smtx_t *v153; // [rsp+70h] [rbp-90h] BYREF
  bool v154; // [rsp+78h] [rbp-88h]
  void *v155[2]; // [rsp+80h] [rbp-80h]
  __int128 v156; // [rsp+90h] [rbp-70h] BYREF
  __int128 v157; // [rsp+A0h] [rbp-60h]
  __int128 v158; // [rsp+B0h] [rbp-50h]
  _Smtx_t *v159; // [rsp+C0h] [rbp-40h]
  __int128 v160; // [rsp+C8h] [rbp-38h]
  void *Block[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v162; // [rsp+F0h] [rbp-10h]

  v151 = a2;
  v4 = (unsigned __int64 *)a1;
  v152 = (unsigned __int64 *)a1;
  LODWORD(v147) = 0;
  if ( *(_DWORD *)(a2 + 144) != *(_DWORD *)(a1 + 176) )
  {
    Block[0] = (void *)0x90000000CLL;
    Block[1] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\GraphNodeCache.cpp";
    v162 = "void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::DiskAnn::Lo"
           "calNodeCache &&,bool)";
    asg::details::AsgAssertFail(Block);
  }
  v160 = 0;
  v5 = (_Smtx_t *)(a1 + 248);
  v159 = (_Smtx_t *)(a1 + 248);
  v6 = (_Smtx_t *)(a1 + 248);
  if ( a3 )
  {
    v153 = v5;
    v154 = Smtx_try_lock_exclusive(v6) != 0;
    v7 = &v153;
    v8 = 1;
  }
  else
  {
    v148 = v5;
    Smtx_lock_exclusive(v6);
    LOBYTE(v149) = 1;
    v7 = &v148;
    v8 = 2;
  }
  *(_QWORD *)&v160 = v5;
  v9 = *((_BYTE *)v7 + 8);
  v146 = v9;
  BYTE8(v160) = v9;
  *v7 = 0;
  *((_BYTE *)v7 + 8) = 0;
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    if ( (_BYTE)v149 )
      Smtx_unlock_exclusive(v148);
  }
  if ( (v8 & 1) != 0 && v154 )
    Smtx_unlock_exclusive(v153);
  if ( v9 )
  {
    v4[1] = *(_QWORD *)a2;
    *((_DWORD *)v4 + 4) = *(_DWORD *)(a2 + 8);
    if ( v4 + 3 != (unsigned __int64 *)(a2 + 80) )
    {
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::clear(v4 + 3);
      *((_DWORD *)v4 + 6) = *(_DWORD *)(a2 + 80);
      v10 = v4[4];
      v4[4] = *(_QWORD *)(a2 + 88);
      *(_QWORD *)(a2 + 88) = v10;
      v11 = v4[5];
      v4[5] = *(_QWORD *)(a2 + 96);
      *(_QWORD *)(a2 + 96) = v11;
      v12 = v4[6];
      v4[6] = *(_QWORD *)(a2 + 104);
      *(_QWORD *)(a2 + 104) = v12;
      v13 = v4[7];
      v4[7] = *(_QWORD *)(a2 + 112);
      *(_QWORD *)(a2 + 112) = v13;
      v14 = v4[8];
      v4[8] = *(_QWORD *)(a2 + 120);
      *(_QWORD *)(a2 + 120) = v14;
      v15 = v4[9];
      v4[9] = *(_QWORD *)(a2 + 128);
      *(_QWORD *)(a2 + 128) = v15;
      v16 = v4[10];
      v4[10] = *(_QWORD *)(a2 + 136);
      *(_QWORD *)(a2 + 136) = v16;
    }
    *(_OWORD *)v155 = 0;
    v156 = 0;
    v158 = 0;
    LODWORD(v155[0]) = *(_DWORD *)(a2 + 160);
    *(_QWORD *)&v156 = 0;
    v17 = operator new(0x18u);
    *v17 = v17;
    v17[1] = v17;
    v155[1] = v17;
    *((_QWORD *)&v156 + 1) = 0;
    v157 = 0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(
      (char *)&v156 + 8,
      16,
      v17);
    v18 = v155[1];
    v155[1] = *(void **)(a2 + 168);
    v19 = v155[1];
    *(_QWORD *)(a2 + 168) = v18;
    v20 = v156;
    *(_QWORD *)&v156 = *(_QWORD *)(a2 + 176);
    *(_QWORD *)(a2 + 176) = v20;
    v21 = *((_QWORD *)&v156 + 1);
    v22 = *(_QWORD *)(a2 + 184);
    *((_QWORD *)&v156 + 1) = v22;
    *(_QWORD *)(a2 + 184) = v21;
    v23 = v157;
    *(_QWORD *)&v157 = *(_QWORD *)(a2 + 192);
    *(_QWORD *)(a2 + 192) = v23;
    v24 = *((_QWORD *)&v157 + 1);
    *((_QWORD *)&v157 + 1) = *(_QWORD *)(a2 + 200);
    *(_QWORD *)(a2 + 200) = v24;
    v25 = *(_QWORD *)(a2 + 208);
    *(_QWORD *)(a2 + 208) = 7;
    *(_QWORD *)&v158 = v25;
    v26 = *(_QWORD *)(a2 + 216);
    *(_QWORD *)(a2 + 216) = 8;
    *((_QWORD *)&v158 + 1) = v26;
    v27 = (_QWORD *)*v19;
    if ( (_QWORD *)*v19 != v19 )
    {
      v28 = (__int64)(v4 + 23);
      do
      {
        v29 = *((_DWORD *)v27 + 5);
        v30 = std::_Hash<std::_Umap_traits<unsigned int,unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned int>>,0>>::_Try_emplace<unsigned int const &,>(
                v28,
                (__int64)&v148,
                (unsigned __int8 *)v27 + 16);
        v31 = *(_QWORD *)v30;
        v32 = *(_DWORD *)(*(_QWORD *)v30 + 20LL);
        v33 = v29 + v32;
        if ( v32 >= ~v29 )
          v33 = -1;
        *(_DWORD *)(v31 + 20) = v33;
        v27 = (_QWORD *)*v27;
      }
      while ( v27 != v19 );
      v4 = v152;
    }
    v34 = (_QWORD *)v4[24];
    v35 = (_QWORD *)*v34;
    if ( (_QWORD *)*v34 != v34 )
    {
      while ( 1 )
      {
        v36 = *((_DWORD *)v35 + 5);
        if ( v36 )
          break;
LABEL_32:
        v35 = (_QWORD *)*v35;
        if ( v35 == v34 )
          goto LABEL_33;
      }
      _mm_lfence();
      v37 = *((unsigned __int8 *)v35 + 19);
      v38 = 2
          * (v25
           & (0x100000001B3LL
            * (v37
             ^ (0x100000001B3LL
              * (*((unsigned __int8 *)v35 + 18)
               ^ (0x100000001B3LL
                * (*((unsigned __int8 *)v35 + 17)
                 ^ (0x100000001B3LL * (*((unsigned __int8 *)v35 + 16) ^ 0xCBF29CE484222325uLL)))))))));
      v39 = *(_QWORD *)(v22
                      + 16
                      * (v25
                       & (0x100000001B3LL
                        * (v37
                         ^ (0x100000001B3LL
                          * (*((unsigned __int8 *)v35 + 18)
                           ^ (0x100000001B3LL
                            * (*((unsigned __int8 *)v35 + 17)
                             ^ (0x100000001B3LL * (*((unsigned __int8 *)v35 + 16) ^ 0xCBF29CE484222325uLL)))))))))
                      + 8);
      if ( (_QWORD *)v39 != v19 )
      {
        v40 = *((_DWORD *)v35 + 4);
        if ( v40 == *(_DWORD *)(v39 + 16) )
        {
LABEL_28:
          v41 = v19;
          if ( v39 )
            v41 = (_QWORD *)v39;
          if ( v41 == v19 )
            *((_DWORD *)v35 + 5) = v36 - 1;
          goto LABEL_32;
        }
        while ( v39 != *(_QWORD *)(v22 + 8 * v38) )
        {
          v39 = *(_QWORD *)(v39 + 8);
          if ( v40 == *(_DWORD *)(v39 + 16) )
            goto LABEL_28;
        }
      }
      v39 = 0;
      goto LABEL_28;
    }
LABEL_33:
    v42 = 0;
    v147 = 0;
    v43 = v152;
    v44 = *v152;
    v45 = v152[25];
    if ( v45 <= *v152 )
      goto LABEL_161;
    _mm_lfence();
    v46 = v45 - v44;
    if ( (unsigned int)asg::SemanticIndex::SelectTopKMethod(v45 - v44, v45, 0xCBF29CE484222325uLL) == 1 )
    {
      v50 = v151;
      if ( v46 )
      {
        while ( 1 )
        {
          --v46;
          v51 = 0;
          v52 = -1;
          v53 = 0;
          v54 = (__int64 **)v43[24];
          for ( i = *v54; i != (__int64 *)v54; v52 = v56 )
          {
            v56 = *((_DWORD *)i + 5);
            if ( v56 < v52 )
            {
              v51 = 1;
              v53 = *((_DWORD *)i + 4);
            }
            i = (__int64 *)*i;
            if ( v56 >= v52 )
              v56 = v52;
          }
          if ( !v51 )
          {
            Block[0] = (void *)0x1500000045LL;
            Block[1] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\GraphNodeCache.cpp";
            v162 = "void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::Dis"
                   "kAnn::LocalNodeCache &&,bool)";
            asg::details::AsgAssertFail(Block);
          }
          LODWORD(v147) = v53;
          v42 += std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(
                   v43 + 11,
                   &v147);
          _mm_lfence();
          v57 = 2
              * (v43[29]
               & (0x100000001B3LL
                * (BYTE3(v147)
                 ^ (0x100000001B3LL
                  * (BYTE2(v147)
                   ^ (0x100000001B3LL
                    * (BYTE1(v147) ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL)))))))));
          v58 = v43[26];
          v59 = *(_QWORD *)(v58
                          + 16
                          * (v43[29]
                           & (0x100000001B3LL
                            * (BYTE3(v147)
                             ^ (0x100000001B3LL
                              * (BYTE2(v147)
                               ^ (0x100000001B3LL
                                * (BYTE1(v147) ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL)))))))))
                          + 8);
          v60 = (_QWORD *)v59;
          v61 = v43[24];
          if ( v59 == v61 )
            goto LABEL_48;
          if ( (_DWORD)v147 != *(_DWORD *)(v59 + 16) )
            break;
LABEL_49:
          if ( v60 )
          {
            v62 = *(_QWORD **)(v58
                             + 16
                             * (v43[29]
                              & (0x100000001B3LL
                               * (BYTE3(v147)
                                ^ (0x100000001B3LL
                                 * (BYTE2(v147)
                                  ^ (0x100000001B3LL
                                   * (BYTE1(v147) ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL))))))))));
            if ( (_QWORD *)v59 == v60 )
            {
              if ( v62 == v60 )
                *(_QWORD *)(v58
                          + 16
                          * (v43[29]
                           & (0x100000001B3LL
                            * (BYTE3(v147)
                             ^ (0x100000001B3LL
                              * (BYTE2(v147)
                               ^ (0x100000001B3LL
                                * (BYTE1(v147) ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL)))))))))) = v61;
              else
                v61 = v60[1];
              *(_QWORD *)(v58 + 8 * v57 + 8) = v61;
            }
            else if ( v62 == v60 )
            {
              *(_QWORD *)(v58
                        + 16
                        * (v43[29]
                         & (0x100000001B3LL
                          * (BYTE3(v147)
                           ^ (0x100000001B3LL
                            * (BYTE2(v147)
                             ^ (0x100000001B3LL
                              * (BYTE1(v147) ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL)))))))))) = *v60;
            }
            v63 = *v60;
            --v43[25];
            *(_QWORD *)v60[1] = v63;
            *(_QWORD *)(v63 + 8) = v60[1];
            operator delete(v60);
          }
          std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(
            v50 + 16,
            &v147);
          if ( !v46 )
            goto LABEL_162;
        }
        while ( v60 != *(_QWORD **)(v58
                                  + 16
                                  * (v43[29]
                                   & (0x100000001B3LL
                                    * (BYTE3(v147)
                                     ^ (0x100000001B3LL
                                      * (BYTE2(v147)
                                       ^ (0x100000001B3LL
                                        * (BYTE1(v147)
                                         ^ (0x100000001B3LL * ((unsigned __int8)v147 ^ 0xCBF29CE484222325uLL)))))))))) )
        {
          v60 = (_QWORD *)v60[1];
          if ( (_DWORD)v147 == *((_DWORD *)v60 + 4) )
            goto LABEL_49;
        }
LABEL_48:
        v60 = 0;
        goto LABEL_49;
      }
      goto LABEL_162;
    }
    *(_OWORD *)Block = 0;
    v162 = 0;
    v64 = (__int64 **)v43[24];
    v65 = *v64;
    *(_OWORD *)Block = 0;
    v66 = (__int64 **)v65;
    v67 = 0;
    if ( v65 == (__int64 *)v64 )
      goto LABEL_67;
    do
    {
      ++v67;
      v66 = (__int64 **)*v66;
    }
    while ( v66 != v64 );
    if ( !v67 )
    {
LABEL_67:
      v69 = (unsigned __int8 *)Block[1];
    }
    else
    {
      if ( v67 > 0x1FFFFFFFFFFFFFFFLL )
        std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
          v48,
          v47,
          v49);
      _mm_lfence();
      v68 = 8 * v67;
      v69 = (unsigned __int8 *)std::_Allocate<16,std::_Default_allocate_traits>(v68);
      Block[0] = v69;
      Block[1] = v69;
      v162 = (const char *)&v69[v68];
      do
      {
        *(_DWORD *)v69 = *((_DWORD *)v65 + 4);
        *((_DWORD *)v69 + 1) = *((_DWORD *)v65 + 5);
        v69 += 8;
        v65 = (__int64 *)*v65;
      }
      while ( v65 != (__int64 *)v64 );
      Block[1] = v69;
    }
    v70 = *v43 / 0xA;
    v71 = (unsigned __int8 *)Block[0];
    for ( j = 0; v71 != v69; v71 += 8 )
    {
      v73 = j + 1;
      if ( *((_DWORD *)v71 + 1) )
        v73 = j;
      j = v73;
    }
    if ( j < v70 )
      v70 = j;
    v74 = v70 + v46;
    v75 = ((char *)v69 - (char *)Block[0]) >> 3;
    if ( v75 < v70 + v46 )
      v74 = ((char *)v69 - (char *)Block[0]) >> 3;
    v153 = (_Smtx_t *)v74;
    if ( v75 > 1 )
    {
      _mm_lfence();
      v76 = asg::SemanticIndex::SelectTopKMethod(v74, ((char *)v69 - (char *)Block[0]) >> 3, v71) - 1;
      if ( v76 )
      {
        v77 = v76 - 1;
        if ( v77 )
        {
          v78 = v77 - 1;
          if ( v78 )
          {
            if ( v78 != 1 )
            {
              v148 = (_Smtx_t *)0x110000008DLL;
              v149 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\include\\SemanticIndex\\SelectTopK.h";
              v150 = "auto __cdecl asg::SemanticIndex::SelectTopK<struct std::pair<unsigned int,unsigned int>,class asg::"
                     "SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>>(class std::vector<struct std::pa"
                     "ir<unsigned int,unsigned int>,class std::allocator<struct std::pair<unsigned int,unsigned int> > > "
                     "&,unsigned __int64,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>,enu"
                     "m asg::SemanticIndex::TopKMethod)";
              asg::details::AsgAssertFail(&v148);
            }
            v79 = (int *)((char *)Block[0] + 8 * (v75 - v74));
            v80 = Block[1];
            v81 = (char *)((char *)Block[1] - (char *)v79);
            v82 = ((char *)Block[1] - (char *)v79) >> 3;
            if ( (_Smtx_t *)v82 != v153 )
            {
              v148 = (_Smtx_t *)0x15000000CCLL;
              v149 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\include\\SemanticIndex\\SelectTopK.h";
              v150 = "auto __cdecl asg::SemanticIndex::SelectTopK<struct std::pair<unsigned int,unsigned int>,class asg::"
                     "SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>>(class std::vector<struct std::pa"
                     "ir<unsigned int,unsigned int>,class std::allocator<struct std::pair<unsigned int,unsigned int> > > "
                     "&,unsigned __int64,class asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges::<lambda_2>,enu"
                     "m asg::SemanticIndex::TopKMethod)";
              asg::details::AsgAssertFail(&v148);
            }
            _mm_lfence();
            v83 = Block[1];
            v84 = ((char *)Block[1] - (char *)v79) >> 4;
            if ( v84 > 0 )
            {
              v85 = (v82 - 1) >> 1;
              do
              {
                --v84;
                v86 = *(_Smtx_t **)&v79[2 * v84];
                v148 = v86;
                v87 = v84;
                for ( k = v84; k < v85; v87 = k )
                {
                  k = 2 * k + (v79[4 * k + 5] > (unsigned int)v79[4 * k + 3]) + 1LL;
                  v79[2 * v87] = v79[2 * k];
                  v79[2 * v87 + 1] = v79[2 * k + 1];
                }
                if ( v87 == v85 && (v82 & 1) == 0 )
                {
                  v79[2 * v87] = v79[2 * v82 - 2];
                  v79[2 * v87 + 1] = v79[2 * v82 - 1];
                  v87 = v82 - 1;
                }
                v89 = HIDWORD(v148);
                if ( v84 < v87 )
                {
                  do
                  {
                    v90 = (v87 - 1) >> 1;
                    if ( v79[2 * v90 + 1] > v89 )
                      break;
                    v79[2 * v87] = v79[2 * v90];
                    v79[2 * v87 + 1] = v79[2 * v90 + 1];
                    v87 = (v87 - 1) >> 1;
                  }
                  while ( v84 < v90 );
                }
                v79[2 * v87] = (int)v86;
                v79[2 * v87 + 1] = v89;
              }
              while ( v84 > 0 );
            }
            for ( m = (int *)Block[0]; m < v79; m += 2 )
            {
              if ( m[1] <= (unsigned int)v79[1] )
              {
                if ( v82 >= 2 )
                {
                  _mm_lfence();
                  v148 = (_Smtx_t *)*(v80 - 1);
                  *((_DWORD *)v80 - 2) = *v79;
                  *((_DWORD *)v80 - 1) = v79[1];
                  LOBYTE(Reserved) = v146;
                  std::_Pop_heap_hole_by_index_std::pair_unsigned_int_unsigned_int____std::pair_unsigned_int_unsigned_int___asg::SemanticIndex::SelectTopK_std::pair_unsigned_int_unsigned_int___asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges_::_33_::_lambda_2____::_21_::MinCompare_(
                    v79,
                    0,
                    (__int64)(v81 - 8) >> 3,
                    &v148,
                    Reserved);
                }
                v92 = *m;
                *m = *(v83 - 2);
                *(v83 - 2) = v92;
                v93 = m[1];
                m[1] = *(v83 - 1);
                *(v83 - 1) = v93;
                if ( v82 >= 2 )
                {
                  v94 = (_Smtx_t *)*(v80 - 1);
                  v148 = v94;
                  v95 = v82 - 1;
                  do
                  {
                    v96 = (v95 - 1) >> 1;
                    if ( (unsigned int)v79[2 * v96 + 1] > HIDWORD(v94) )
                      break;
                    v79[2 * v95] = v79[2 * v96];
                    v79[2 * v95 + 1] = v79[2 * v96 + 1];
                    v95 = (v95 - 1) >> 1;
                  }
                  while ( v96 > 0 );
                  *(_QWORD *)&v79[2 * v95] = v94;
                }
              }
            }
            std::ranges::_Sort_fn::_Sort_common_std::pair_unsigned_int_unsigned_int_____asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges_::_33_::_lambda_2__std::identity_(
              (_DWORD)v79,
              (_DWORD)v80,
              v82,
              v146,
              0);
            v74 = (__int64)v153;
            v43 = v152;
          }
          else
          {
            v97 = (char *)Block[0];
            v69 = (unsigned __int8 *)Block[1];
            v98 = (char *)Block[1];
            v99 = ((char *)Block[1] - (char *)Block[0]) >> 3;
            v100 = ((char *)Block[1] - (char *)Block[0]) >> 4;
            if ( v100 > 0 )
            {
              v101 = (v99 - 1) >> 1;
              do
              {
                --v100;
                v102 = *(_Smtx_t **)&v97[8 * v100];
                v148 = v102;
                v103 = v100;
                for ( n = v100; n < v101; v103 = n )
                {
                  n = 2LL - (*(_DWORD *)&v97[16 * n + 12] < *(_DWORD *)&v97[16 * n + 20]) + 2 * n;
                  *(_DWORD *)&v97[8 * v103] = *(_DWORD *)&v97[8 * n];
                  *(_DWORD *)&v97[8 * v103 + 4] = *(_DWORD *)&v97[8 * n + 4];
                }
                if ( v103 == v101 && (v99 & 1) == 0 )
                {
                  *(_DWORD *)&v97[8 * v103] = *(_DWORD *)&v97[8 * v99 - 8];
                  *(_DWORD *)&v97[8 * v103 + 4] = *(_DWORD *)&v97[8 * v99 - 4];
                  v103 = v99 - 1;
                }
                v105 = HIDWORD(v148);
                if ( v100 < v103 )
                {
                  do
                  {
                    v106 = (v103 - 1) >> 1;
                    if ( *(_DWORD *)&v97[8 * v106 + 4] <= v105 )
                      break;
                    *(_DWORD *)&v97[8 * v103] = *(_DWORD *)&v97[8 * v106];
                    *(_DWORD *)&v97[8 * v103 + 4] = *(_DWORD *)&v97[8 * v106 + 4];
                    v103 = (v103 - 1) >> 1;
                  }
                  while ( v100 < v106 );
                }
                *(_DWORD *)&v97[8 * v103] = (_DWORD)v102;
                *(_DWORD *)&v97[8 * v103 + 4] = v105;
              }
              while ( v100 > 0 );
              v69 = (unsigned __int8 *)Block[1];
            }
            if ( !v74 )
              goto LABEL_135;
            v107 = v98 - 8;
            v108 = v74;
            do
            {
              if ( (__int64)((unsigned __int64)&v107[8LL - (_QWORD)v97] & 0xFFFFFFFFFFFFFFF8uLL) >= 16 )
              {
                _mm_lfence();
                v148 = *(_Smtx_t **)v107;
                *(_DWORD *)v107 = *(_DWORD *)v97;
                *((_DWORD *)v107 + 1) = *((_DWORD *)v97 + 1);
                LOBYTE(Reserved) = v146;
                std::_Pop_heap_hole_by_index_std::pair_unsigned_int_unsigned_int____std::pair_unsigned_int_unsigned_int___asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges_::_33_::_lambda_2___(
                  v97,
                  0,
                  (v107 - v97) >> 3,
                  &v148,
                  Reserved);
              }
              v107 -= 8;
              --v108;
            }
            while ( v108 );
          }
        }
        else
        {
          std::ranges::_Sort_fn::_Sort_common_std::pair_unsigned_int_unsigned_int_____asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges_::_33_::_lambda_2__std::identity_(
            Block[0],
            Block[1],
            ((char *)Block[1] - (char *)Block[0]) >> 3,
            v146,
            0);
        }
        goto LABEL_134;
      }
      v69 = (unsigned __int8 *)Block[1];
      if ( v74 )
      {
        v109 = v74;
        do
        {
          v110 = (unsigned __int8 *)Block[0];
          if ( Block[0] != v69 )
          {
            for ( ii = (unsigned __int8 *)Block[0] + 8; ii != v69; ii += 8 )
            {
              if ( *((_DWORD *)v110 + 1) > *((_DWORD *)ii + 1) )
                v110 = ii;
            }
          }
          v112 = v69 - 8;
          v69 = v112;
          if ( v110 != v112 )
          {
            v113 = *(_DWORD *)v110;
            *(_DWORD *)v110 = *(_DWORD *)v112;
            *(_DWORD *)v112 = v113;
            v114 = *((_DWORD *)v110 + 1);
            *((_DWORD *)v110 + 1) = *((_DWORD *)v112 + 1);
            *((_DWORD *)v112 + 1) = v114;
          }
          --v109;
        }
        while ( v109 );
LABEL_134:
        v69 = (unsigned __int8 *)Block[1];
      }
    }
LABEL_135:
    v115 = ((char *)v69 - (char *)Block[0]) >> 3;
    if ( v115 - v74 < v115 )
      v115 = (((char *)v69 - (char *)Block[0]) >> 3) - v74;
    v116 = (unsigned __int8 *)Block[0] + 8 * v115;
    if ( v69 != v116 )
    {
      v117 = v151;
      v118 = v69 - 8;
      v119 = v147;
      while ( 1 )
      {
        v119 += std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(
                  v43 + 11,
                  v118);
        _mm_lfence();
        v120 = v118[3];
        v121 = v43[29]
             & (0x100000001B3LL
              * (v120
               ^ (0x100000001B3LL
                * (v118[2] ^ (0x100000001B3LL * (v118[1] ^ (0x100000001B3LL * (*v118 ^ 0xCBF29CE484222325uLL))))))));
        v122 = v43[26];
        v123 = *(_QWORD *)(v122 + 16 * v121 + 8);
        v124 = (_QWORD *)v123;
        v125 = v43[24];
        if ( v123 == v125 )
          goto LABEL_144;
        if ( *(_DWORD *)v118 != *(_DWORD *)(v123 + 16) )
          break;
LABEL_145:
        if ( v124 )
        {
          v126 = *(_QWORD **)(v122 + 16 * v121);
          if ( (_QWORD *)v123 == v124 )
          {
            if ( v126 == v124 )
              *(_QWORD *)(v122 + 16 * v121) = v125;
            else
              v125 = v124[1];
            *(_QWORD *)(v122 + 16 * v121 + 8) = v125;
          }
          else if ( v126 == v124 )
          {
            *(_QWORD *)(v122 + 16 * v121) = *v124;
          }
          v127 = *v124;
          --v43[25];
          *(_QWORD *)v124[1] = v127;
          *(_QWORD *)(v127 + 8) = v124[1];
          operator delete(v124);
        }
        std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(
          v117 + 16,
          v118);
        v118 -= 8;
        if ( v118 + 8 == v116 )
        {
          v147 = v119;
          goto LABEL_156;
        }
      }
      while ( v124 != *(_QWORD **)(v122
                                 + 16
                                 * (v43[29]
                                  & (0x100000001B3LL
                                   * (v120
                                    ^ (0x100000001B3LL
                                     * (v118[2]
                                      ^ (0x100000001B3LL
                                       * (v118[1] ^ (0x100000001B3LL * (*v118 ^ 0xCBF29CE484222325uLL)))))))))) )
      {
        v124 = (_QWORD *)v124[1];
        if ( *(_DWORD *)v118 == *((_DWORD *)v124 + 4) )
          goto LABEL_145;
      }
LABEL_144:
      v124 = 0;
      goto LABEL_145;
    }
LABEL_156:
    v128 = Block[0];
    if ( Block[0] )
    {
      if ( (((char *)v162 - (char *)Block[0]) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
      {
        _mm_lfence();
        v128 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v128 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v128);
    }
    v42 = v147;
LABEL_161:
    v50 = v151;
LABEL_162:
    if ( v42 < 0 )
      v129 = (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1))
           + (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1));
    else
      v129 = (double)(int)v42;
    v130 = *v43;
    if ( (*v43 & 0x8000000000000000uLL) != 0LL )
      v131 = (double)(int)(*(_DWORD *)v43 & 1 | (v130 >> 1)) + (double)(int)(*(_DWORD *)v43 & 1 | (v130 >> 1));
    else
      v131 = (double)(int)v130;
    v132 = v129 / v131 * 100.0;
    v133 = 0;
    if ( v132 >= 9.223372036854776e18 )
    {
      v132 = v132 - 9.223372036854776e18;
      if ( v132 < 9.223372036854776e18 )
        v133 = 0x8000000000000000uLL;
    }
    v134 = v133 + (unsigned int)(int)v132;
    if ( v134 > 0x63 )
      v134 = 99;
    ++*(_QWORD *)(v43[19] + 8 * v134);
    v135 = v50 + 16;
    v136 = *(unsigned __int8 ***)(v50 + 24);
    v137 = *v136;
    if ( *v136 != (unsigned __int8 *)v136 )
    {
      do
      {
        v138 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::_Try_emplace<unsigned int const &,>(
                            (__int64)(v43 + 11),
                            (__int64)&v148,
                            v137 + 16);
        v139 = *((_QWORD *)v137 + 4);
        if ( v139 )
          _InterlockedIncrement((volatile signed __int32 *)(v139 + 8));
        v140 = *((_QWORD *)v137 + 4);
        *(_QWORD *)(v138 + 24) = *((_QWORD *)v137 + 3);
        v141 = *(volatile signed __int32 **)(v138 + 32);
        *(_QWORD *)(v138 + 32) = v140;
        if ( v141 )
        {
          if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v141)(v141);
            if ( _InterlockedExchangeAdd(v141 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v141 + 8LL))(v141);
          }
        }
        v137 = *(unsigned __int8 **)v137;
      }
      while ( v137 != (unsigned __int8 *)v136 );
      v50 = v151;
    }
    if ( v43[13] != v43[25] )
    {
      Block[0] = (void *)0x90000007DLL;
      Block[1] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\GraphNodeCache.cpp";
      v162 = "void __cdecl asg::SemanticIndex::DiskAnn::GlobalNodeCache::MergeChanges(class asg::SemanticIndex::DiskAnn::"
             "LocalNodeCache &&,bool)";
      asg::details::AsgAssertFail(Block);
    }
    v148 = 0;
    *(_QWORD *)v50 = 0;
    *(_DWORD *)(v50 + 8) = 0;
    std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::clear(v50 + 80);
    std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::clear(v135);
    std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v156 + 8);
    v142 = (_QWORD **)v155[1];
    **((_QWORD **)v155[1] + 1) = 0;
    v143 = *v142;
    if ( *v142 )
    {
      do
      {
        v144 = (_QWORD *)*v143;
        operator delete(v143);
        v143 = v144;
      }
      while ( v144 );
    }
    operator delete(v142);
    v5 = v159;
    v9 = v146;
  }
  if ( v9 )
    Smtx_unlock_exclusive(v5);
}

```

## disassembly

```asm
0x1801b6a40  mov     [rsp-8+arg_10], rbx
0x1801b6a45  push    rbp
0x1801b6a46  push    rsi
0x1801b6a47  push    rdi
0x1801b6a48  push    r12
0x1801b6a4a  push    r13
0x1801b6a4c  push    r14
0x1801b6a4e  push    r15
0x1801b6a50  lea     rbp, [rsp-10h]
0x1801b6a55  sub     rsp, 110h
0x1801b6a5c  mov     rax, cs:__security_cookie
0x1801b6a63  xor     rax, rsp
0x1801b6a66  mov     [rbp+40h+var_40], rax
0x1801b6a6a  mov     r14, rdx
0x1801b6a6d  mov     [rsp+140h+var_E0], rdx
0x1801b6a72  mov     rsi, rcx
0x1801b6a75  mov     [rsp+140h+var_D8], rcx
0x1801b6a7a  xor     r12d, r12d
0x1801b6a7d  mov     dword ptr [rsp+140h+var_108], r12d
0x1801b6a82  mov     eax, [rcx+0B0h]
0x1801b6a88  cmp     [rdx+90h], eax
0x1801b6a8e  jnz     loc_1801B786F
0x1801b6a94  xorps   xmm0, xmm0
0x1801b6a97  movups  [rbp+40h+var_78], xmm0
0x1801b6a9b  lea     rdi, [rcx+0F8h]
0x1801b6aa2  mov     [rbp+40h+var_80], rdi
0x1801b6aa6  mov     rcx, rdi; _Smtx_t *
0x1801b6aa9  test    r8b, r8b
0x1801b6aac  jz      short loc_1801B6ACB
0x1801b6aae  mov     [rsp+140h+var_D0], rdi
0x1801b6ab3  call    _Smtx_try_lock_exclusive
0x1801b6ab8  test    eax, eax
0x1801b6aba  setnz   [rsp+140h+var_C8]
0x1801b6abf  lea     rax, [rsp+140h+var_D0]
0x1801b6ac4  mov     ebx, 1
0x1801b6ac9  jmp     short loc_1801B6AE4
0x1801b6acb  mov     [rsp+140h+var_100], rdi
0x1801b6ad0  call    _Smtx_lock_exclusive
0x1801b6ad5  mov     byte ptr [rsp+140h+var_F8], 1
0x1801b6ada  lea     rax, [rsp+140h+var_100]
0x1801b6adf  mov     ebx, 2
0x1801b6ae4  mov     qword ptr [rbp+40h+var_78], rdi
0x1801b6ae8  movzx   r15d, byte ptr [rax+8]
0x1801b6aed  mov     [rsp+140h+var_110], r15b
0x1801b6af2  mov     byte ptr [rbp+40h+var_78+8], r15b
0x1801b6af6  mov     [rax], r12
0x1801b6af9  mov     [rax+8], r12b
0x1801b6afd  test    bl, 2
0x1801b6b00  jz      short loc_1801B6B16
0x1801b6b02  and     ebx, 0FFFFFFFDh
0x1801b6b05  cmp     byte ptr [rsp+140h+var_F8], 0
0x1801b6b0a  jz      short loc_1801B6B16
0x1801b6b0c  mov     rcx, [rsp+140h+var_100]; _Smtx_t *
0x1801b6b11  call    _Smtx_unlock_exclusive
0x1801b6b16  test    bl, 1
0x1801b6b19  jz      short loc_1801B6B2C
0x1801b6b1b  cmp     [rsp+140h+var_C8], 0
0x1801b6b20  jz      short loc_1801B6B2C
0x1801b6b22  mov     rcx, [rsp+140h+var_D0]; _Smtx_t *
0x1801b6b27  call    _Smtx_unlock_exclusive
0x1801b6b2c  test    r15b, r15b
0x1801b6b2f  jz      loc_1801B780D
0x1801b6b35  movsd   xmm0, qword ptr [r14]
0x1801b6b3a  movsd   qword ptr [rsi+8], xmm0
0x1801b6b3f  mov     eax, [r14+8]
0x1801b6b43  mov     [rsi+10h], eax
0x1801b6b46  lea     rdi, [r14+50h]
0x1801b6b4a  lea     rbx, [rsi+18h]
0x1801b6b4e  cmp     rbx, rdi
0x1801b6b51  jz      short loc_1801B6BCF
0x1801b6b53  mov     rcx, rbx
0x1801b6b56  call    ?clear@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::clear(void)
0x1801b6b5b  mov     eax, [rdi]
0x1801b6b5d  mov     [rbx], eax
0x1801b6b5f  mov     rcx, [rbx+8]
0x1801b6b63  mov     rax, [rdi+8]
0x1801b6b67  mov     [rbx+8], rax
0x1801b6b6b  mov     [rdi+8], rcx
0x1801b6b6f  mov     rcx, [rbx+10h]
0x1801b6b73  mov     rax, [rdi+10h]
0x1801b6b77  mov     [rbx+10h], rax
0x1801b6b7b  mov     [rdi+10h], rcx
0x1801b6b7f  mov     rcx, [rbx+18h]
0x1801b6b83  mov     rax, [rdi+18h]
0x1801b6b87  mov     [rbx+18h], rax
0x1801b6b8b  mov     [rdi+18h], rcx
0x1801b6b8f  mov     rcx, [rbx+20h]
0x1801b6b93  mov     rax, [rdi+20h]
0x1801b6b97  mov     [rbx+20h], rax
0x1801b6b9b  mov     [rdi+20h], rcx
0x1801b6b9f  mov     rcx, [rbx+28h]
0x1801b6ba3  mov     rax, [rdi+28h]
0x1801b6ba7  mov     [rbx+28h], rax
0x1801b6bab  mov     [rdi+28h], rcx
0x1801b6baf  mov     rcx, [rbx+30h]
0x1801b6bb3  mov     rax, [rdi+30h]
0x1801b6bb7  mov     [rbx+30h], rax
0x1801b6bbb  mov     [rdi+30h], rcx
0x1801b6bbf  mov     rcx, [rbx+38h]
0x1801b6bc3  mov     rax, [rdi+38h]
0x1801b6bc7  mov     [rbx+38h], rax
0x1801b6bcb  mov     [rdi+38h], rcx
0x1801b6bcf  xorps   xmm0, xmm0
0x1801b6bd2  movups  xmmword ptr [rbp+40h+var_C0], xmm0
0x1801b6bd6  movups  [rbp+40h+var_B0], xmm0
0x1801b6bda  movups  [rbp+40h+var_90], xmm0
0x1801b6bde  mov     eax, [r14+0A0h]
0x1801b6be5  mov     dword ptr [rbp+40h+var_C0], eax
0x1801b6be8  mov     qword ptr [rbp+40h+var_B0], r12
0x1801b6bec  mov     ecx, 18h; Size
0x1801b6bf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801b6bf6  mov     [rax], rax
0x1801b6bf9  mov     [rax+8], rax
0x1801b6bfd  mov     [rbp+40h+var_C0+8], rax
0x1801b6c01  mov     qword ptr [rbp+40h+var_B0+8], r12
0x1801b6c05  xorps   xmm0, xmm0
0x1801b6c08  movdqa  [rbp+40h+var_A0], xmm0
0x1801b6c0d  mov     r8, rax
0x1801b6c10  mov     edx, 10h
0x1801b6c15  lea     rcx, [rbp+40h+var_B0+8]
0x1801b6c19  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UTextRegionStream@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UTextRegionStream@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>)
0x1801b6c1e  mov     rax, [rbp+40h+var_C0+8]
0x1801b6c22  mov     rdi, [r14+0A8h]
0x1801b6c29  mov     [rbp+40h+var_C0+8], rdi
0x1801b6c2d  mov     [r14+0A8h], rax
0x1801b6c34  mov     rcx, qword ptr [rbp+40h+var_B0]
0x1801b6c38  mov     rax, [r14+0B0h]
0x1801b6c3f  mov     qword ptr [rbp+40h+var_B0], rax
0x1801b6c43  mov     [r14+0B0h], rcx
0x1801b6c4a  mov     rax, qword ptr [rbp+40h+var_B0+8]
0x1801b6c4e  mov     r15, [r14+0B8h]
0x1801b6c55  mov     qword ptr [rbp+40h+var_B0+8], r15
0x1801b6c59  mov     [r14+0B8h], rax
0x1801b6c60  mov     rcx, qword ptr [rbp+40h+var_A0]
0x1801b6c64  mov     rax, [r14+0C0h]
0x1801b6c6b  mov     qword ptr [rbp+40h+var_A0], rax
0x1801b6c6f  mov     [r14+0C0h], rcx
0x1801b6c76  mov     rcx, qword ptr [rbp+40h+var_A0+8]
0x1801b6c7a  mov     rax, [r14+0C8h]
0x1801b6c81  mov     qword ptr [rbp+40h+var_A0+8], rax
0x1801b6c85  mov     [r14+0C8h], rcx
0x1801b6c8c  mov     r12, [r14+0D0h]
0x1801b6c93  mov     qword ptr [r14+0D0h], 7
0x1801b6c9e  mov     qword ptr [rbp+40h+var_90], r12
0x1801b6ca2  mov     rax, [r14+0D8h]
0x1801b6ca9  mov     r13d, 8
0x1801b6caf  mov     [r14+0D8h], r13
0x1801b6cb6  mov     qword ptr [rbp+40h+var_90+8], rax
0x1801b6cba  mov     rbx, [rdi]
0x1801b6cbd  cmp     rbx, rdi
0x1801b6cc0  jz      short loc_1801B6D0B
0x1801b6cc2  lea     r14, [rsi+0B8h]
0x1801b6cc9  nop     dword ptr [rax+00000000h]
0x1801b6cd0  lea     r8, [rbx+10h]
0x1801b6cd4  mov     esi, [r8+4]
0x1801b6cd8  lea     rdx, [rsp+140h+var_100]
0x1801b6cdd  mov     rcx, r14
0x1801b6ce0  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IIV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBII@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBII@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,uint>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x1801b6ce5  mov     rdx, [rax]
0x1801b6ce8  mov     ecx, [rdx+14h]
0x1801b6ceb  mov     eax, esi
0x1801b6ced  not     eax
0x1801b6cef  cmp     ecx, eax
0x1801b6cf1  lea     eax, [rsi+rcx]
0x1801b6cf4  jb      short loc_1801B6CFB
0x1801b6cf6  mov     eax, 0FFFFFFFFh
0x1801b6cfb  mov     [rdx+14h], eax
0x1801b6cfe  mov     rbx, [rbx]
0x1801b6d01  cmp     rbx, rdi
0x1801b6d04  jnz     short loc_1801B6CD0
0x1801b6d06  mov     rsi, [rsp+140h+var_D8]
0x1801b6d0b  mov     rcx, [rsi+0C0h]
0x1801b6d12  mov     rax, [rcx]
0x1801b6d15  mov     r8, 0CBF29CE484222325h
0x1801b6d1f  cmp     rax, rcx
0x1801b6d22  jz      loc_1801B6DD6
0x1801b6d28  mov     r13, 100000001B3h
0x1801b6d32  mov     r11d, [rax+14h]
0x1801b6d36  test    r11d, r11d
0x1801b6d39  jz      loc_1801B6DC4
0x1801b6d3f  lfence
0x1801b6d42  movzx   r9d, byte ptr [rax+10h]
0x1801b6d47  xor     r9, r8
0x1801b6d4a  imul    r9, r13
0x1801b6d4e  movzx   edx, byte ptr [rax+11h]
0x1801b6d52  xor     r9, rdx
0x1801b6d55  imul    r9, r13
0x1801b6d59  movzx   edx, byte ptr [rax+12h]
0x1801b6d5d  xor     r9, rdx
0x1801b6d60  imul    r9, r13
0x1801b6d64  movzx   edx, byte ptr [rax+13h]
0x1801b6d68  xor     r9, rdx
0x1801b6d6b  imul    r9, r13
0x1801b6d6f  and     r9, r12
0x1801b6d72  add     r9, r9
0x1801b6d75  mov     r8, [r15+r9*8+8]
0x1801b6d7a  cmp     r8, rdi
0x1801b6d7d  jz      short loc_1801B6DA1
0x1801b6d7f  mov     r10, [r15+r9*8]
0x1801b6d83  mov     edx, [rax+10h]
0x1801b6d86  cmp     edx, [r8+10h]
0x1801b6d8a  jz      short loc_1801B6DA4
0x1801b6d8c  nop     dword ptr [rax+00h]
0x1801b6d90  cmp     r8, r10
0x1801b6d93  jz      short loc_1801B6DA1
0x1801b6d95  mov     r8, [r8+8]
0x1801b6d99  cmp     edx, [r8+10h]
0x1801b6d9d  jnz     short loc_1801B6D90
0x1801b6d9f  jmp     short loc_1801B6DA4
0x1801b6da1  xor     r8d, r8d
0x1801b6da4  mov     rdx, rdi
0x1801b6da7  test    r8, r8
0x1801b6daa  cmovnz  rdx, r8
0x1801b6dae  mov     r8, 0CBF29CE484222325h
0x1801b6db8  cmp     rdx, rdi
0x1801b6dbb  jnz     short loc_1801B6DC4
0x1801b6dbd  lea     edx, [r11-1]
0x1801b6dc1  mov     [rax+14h], edx
0x1801b6dc4  mov     rax, [rax]
0x1801b6dc7  cmp     rax, rcx
0x1801b6dca  jnz     loc_1801B6D32
0x1801b6dd0  mov     r13d, 8
0x1801b6dd6  xor     ebx, ebx
0x1801b6dd8  mov     [rsp+140h+var_108], rbx
0x1801b6ddd  mov     r12, [rsp+140h+var_D8]
0x1801b6de2  mov     rax, [r12]
0x1801b6de6  mov     rdx, [r12+0C8h]
0x1801b6dee  cmp     rdx, rax
0x1801b6df1  jbe     loc_1801B7656
0x1801b6df7  lfence
0x1801b6dfa  mov     r14, rdx
0x1801b6dfd  sub     r14, rax
0x1801b6e00  mov     rcx, r14
0x1801b6e03  call    ?SelectTopKMethod@SemanticIndex@asg@@YA?AW4TopKMethod@12@_K0@Z; asg::SemanticIndex::SelectTopKMethod(unsigned __int64,unsigned __int64)
0x1801b6e08  cmp     eax, 1
0x1801b6e0b  jnz     loc_1801B6F89
0x1801b6e11  mov     rsi, [rsp+140h+var_E0]
0x1801b6e16  test    r14, r14
0x1801b6e19  jz      loc_1801B765B
0x1801b6e1f  mov     rdi, 0CBF29CE484222325h
0x1801b6e29  nop     dword ptr [rax+00000000h]
0x1801b6e30  dec     r14
0x1801b6e33  xor     r9b, r9b
0x1801b6e36  mov     r8d, 0FFFFFFFFh
0x1801b6e3c  xor     r10d, r10d
0x1801b6e3f  mov     rcx, [r12+0C0h]
0x1801b6e47  mov     rax, [rcx]
0x1801b6e4a  cmp     rax, rcx
0x1801b6e4d  jz      short loc_1801B6E6E
0x1801b6e4f  nop
0x1801b6e50  mov     edx, [rax+14h]
0x1801b6e53  cmp     edx, r8d
0x1801b6e56  jnb     short loc_1801B6E5F
0x1801b6e58  mov     r9b, 1
0x1801b6e5b  mov     r10d, [rax+10h]
0x1801b6e5f  mov     rax, [rax]
0x1801b6e62  cmovnb  edx, r8d
0x1801b6e66  mov     r8d, edx
0x1801b6e69  cmp     rax, rcx
0x1801b6e6c  jnz     short loc_1801B6E50
0x1801b6e6e  test    r9b, r9b
0x1801b6e71  jz      loc_1801B789D
0x1801b6e77  mov     dword ptr [rsp+140h+var_108], r10d
0x1801b6e7c  lea     rcx, [r12+58h]
0x1801b6e81  lea     rdx, [rsp+140h+var_108]
0x1801b6e86  call    ?erase@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(uint const &)
0x1801b6e8b  add     rbx, rax
0x1801b6e8e  lfence
0x1801b6e91  mov     r8d, dword ptr [rsp+140h+var_108]
0x1801b6e96  movzx   edx, r8b
0x1801b6e9a  xor     rdx, rdi
0x1801b6e9d  mov     rcx, 100000001B3h
0x1801b6ea7  imul    rdx, rcx
0x1801b6eab  movzx   eax, byte ptr [rsp+140h+var_108+1]
0x1801b6eb0  xor     rdx, rax
0x1801b6eb3  imul    rdx, rcx
0x1801b6eb7  movzx   eax, byte ptr [rsp+140h+var_108+2]
0x1801b6ebc  xor     rdx, rax
0x1801b6ebf  imul    rdx, rcx
0x1801b6ec3  movzx   eax, byte ptr [rsp+140h+var_108+3]
0x1801b6ec8  xor     rdx, rax
0x1801b6ecb  imul    rdx, rcx
0x1801b6ecf  and     rdx, [r12+0E8h]
0x1801b6ed7  add     rdx, rdx
0x1801b6eda  mov     r9, [r12+0D0h]
0x1801b6ee2  mov     r11, [r9+rdx*8+8]
0x1801b6ee7  mov     rcx, r11
0x1801b6eea  mov     r10, [r12+0C0h]
0x1801b6ef2  cmp     r11, r10
0x1801b6ef5  jz      short loc_1801B6F12
0x1801b6ef7  mov     rax, [r9+rdx*8]
0x1801b6efb  cmp     r8d, [r11+10h]
0x1801b6eff  jz      short loc_1801B6F14
0x1801b6f01  cmp     rcx, rax
0x1801b6f04  jz      short loc_1801B6F12
0x1801b6f06  mov     rcx, [rcx+8]
0x1801b6f0a  cmp     r8d, [rcx+10h]
0x1801b6f0e  jnz     short loc_1801B6F01
0x1801b6f10  jmp     short loc_1801B6F14
0x1801b6f12  xor     ecx, ecx; Block
  ... truncated ...
```
