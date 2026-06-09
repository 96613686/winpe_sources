# asg::SemanticIndex::DiskAnn::Index::FindNearestNodes(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,unsigned __int64,asg::SemanticIndex::DiskAnn::GraphContinuationData *,bool,std::optional<uint>)

- ea: `0x1801b0040`
- end: `0x1801b0da7`
- name: `?FindNearestNodes@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$vector@UNeighbor@DiskAnn@SemanticIndex@asg@@V?$allocator@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@@std@@AEAVOperationState@234@IV?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@6@_KPEAUGraphContinuationData@234@_NV?$optional@I@6@@Z`
- size: `3431`
- prototype: `__int64 __usercall@<rax>(asg::SemanticIndex::DiskAnn::Index *this@<rcx>, __int64, __int64, __int64, char, char)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b0fb0`
- `0x1801b3bb0`

## callees

- `0x180006220`
- `0x180006410`
- `0x180006e30`
- `0x1800076f0`
- `0x180007b20`
- `0x180007ba0`
- `0x1800140b0`
- `0x1800178d0`
- `0x18002c570`
- `0x180030ee0`
- `0x180042c30`
- `0x180043b70`
- `0x180078ed0`
- `0x180089c30`
- `0x180091bd0`
- `0x180091c60`
- `0x18019a1b0`
- `0x1801aafe0`
- `0x1801ab730`
- `0x1801acab0`
- `0x1801acf20`
- `0x1801af490`
- `0x1801afc60`
- `0x1801b0040`
- `0x1801b13c0`
- `0x1801b2800`
- `0x1801b4d80`
- `0x1801b4f10`
- `0x1801d1320`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x180206ec0`
- `0x1802421a0`

## string_xrefs

- `0x1801b0d1f`: `void __cdecl asg::SemanticIndex::DiskAnn::GraphContinuationData::UpdateWithNewSearchResults(const class std::unordered_set<unsigned int,struct std::hash<unsigned int>,struct std::equal_to<unsigned int>,class std::allocator<unsigned int> > &,class std::unordered_set<struct asg::SemanticIndex::DiskAnn::QueryDistance,struct std::hash<struct asg::SemanticIndex::DiskAnn::QueryDistance>,struct std::equal_to<struct asg::SemanticIndex::DiskAnn::QueryDistance>,class std::allocator<struct asg::SemanticInd`
- `0x1801b0d52`: `class std::vector<struct asg::SemanticIndex::DiskAnn::Neighbor,class std::allocator<struct asg::SemanticIndex::DiskAnn::Neighbor> > __cdecl asg::SemanticIndex::DiskAnn::Index::FindNearestNodes(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >,unsigned __int64,struct asg::SemanticIndex::DiskAnn::GraphContinuationData *,bool,class std::optional<unsigned int>) const`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall asg::SemanticIndex::DiskAnn::Index::FindNearestNodes(
        asg::SemanticIndex::DiskAnn::Index *this,
        _QWORD *a2,
        const struct asg::SemanticIndex::DiskAnn::OperationState *a3,
        int a4,
        const struct asg::SemanticRegistry::IVectorData **a5,
        unsigned __int64 a6,
        __int64 a7,
        char a8,
        char a9)
{
  const struct asg::SemanticIndex::DiskAnn::OperationState *v9; // r13
  _QWORD *v10; // rsi
  asg::SemanticIndex::DiskAnn::Index *v11; // r14
  unsigned int v12; // r15d
  _QWORD *v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rdi
  _QWORD *v16; // rbx
  std::_Ref_count_base **v17; // rdi
  std::_Ref_count_base *v18; // rbx
  __int64 ***v19; // rdi
  __int64 **i; // rbx
  __m128i v21; // xmm6
  std::_Ref_count_base *v22; // rbx
  __int64 v23; // rax
  std::_Ref_count_base *v24; // rdi
  float v25; // xmm0_4
  _QWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r11
  unsigned __int64 v30; // rdx
  __int64 v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // r9
  __int64 v34; // r11
  __m128 v35; // xmm6
  void *v36; // rdi
  signed __int64 v37; // rbx
  unsigned __int64 v38; // rsi
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r15
  size_t v42; // r15
  _QWORD *v43; // r14
  __int64 v44; // rbx
  const void *v45; // rdx
  _QWORD *v46; // rcx
  char *v47; // r8
  void *v48; // rcx
  volatile signed __int32 *v49; // rbx
  unsigned __int8 *v50; // rbx
  unsigned __int8 *j; // rdi
  _QWORD *v52; // rax
  void *v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rbx
  void *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  _QWORD **v68; // rcx
  _QWORD *v69; // rcx
  _QWORD *v70; // rbx
  volatile signed __int64 *v71; // rcx
  _QWORD *v72; // rdx
  void *v73; // rcx
  void *v74; // rax
  _QWORD **v75; // rcx
  _QWORD *v76; // rcx
  _QWORD *v77; // rbx
  _QWORD **v78; // rcx
  _QWORD *v79; // rcx
  _QWORD *v80; // rbx
  void *v81; // rcx
  volatile signed __int32 *v82; // rbx
  _QWORD *v84; // rbx
  __int64 v85; // rdx
  __m128i v86; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v87; // [rsp+40h] [rbp-C0h] BYREF
  int v88; // [rsp+44h] [rbp-BCh]
  const char *v89; // [rsp+48h] [rbp-B8h] BYREF
  const char *v90; // [rsp+50h] [rbp-B0h]
  __m128i v91; // [rsp+60h] [rbp-A0h] BYREF
  int v92; // [rsp+70h] [rbp-90h] BYREF
  void *v93; // [rsp+78h] [rbp-88h]
  __int64 v94; // [rsp+80h] [rbp-80h]
  __int128 v95; // [rsp+88h] [rbp-78h] BYREF
  __int64 v96; // [rsp+98h] [rbp-68h]
  __int64 v97; // [rsp+A0h] [rbp-60h]
  __int64 v98; // [rsp+A8h] [rbp-58h]
  __m128i *v99; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v100; // [rsp+B8h] [rbp-48h]
  const struct asg::SemanticIndex::DiskAnn::OperationState *v101; // [rsp+C0h] [rbp-40h]
  const struct asg::SemanticRegistry::IVectorData **v102; // [rsp+C8h] [rbp-38h]
  asg::SemanticIndex::DiskAnn::Index *v103; // [rsp+D0h] [rbp-30h]
  _BYTE v104[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v105[16]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v106[2]; // [rsp+100h] [rbp+0h] BYREF
  void *Src[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v108; // [rsp+120h] [rbp+20h]
  unsigned int v109; // [rsp+128h] [rbp+28h] BYREF
  std::_Ref_count_base *v110[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v111[24]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v112; // [rsp+158h] [rbp+58h]
  void *v113[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v114; // [rsp+170h] [rbp+70h] BYREF
  __int128 v115; // [rsp+180h] [rbp+80h]
  __int128 v116; // [rsp+190h] [rbp+90h]
  char *v117; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE *v118; // [rsp+1A8h] [rbp+A8h]
  _QWORD *v119; // [rsp+1B0h] [rbp+B0h]
  void **v120; // [rsp+1B8h] [rbp+B8h]
  void *v121[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v122[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  void *Block[2]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v124[3]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v125[56]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE *v126; // [rsp+278h] [rbp+178h]
  _BYTE v127[96]; // [rsp+280h] [rbp+180h] BYREF

  v9 = a3;
  v101 = a3;
  v10 = a2;
  v100 = a2;
  v11 = this;
  v103 = this;
  LODWORD(v99) = a4;
  v102 = a5;
  v106[1] = a5;
  v106[0] = a7;
  v12 = 0;
  asg::SemanticIndex::DiskAnn::Checkpoint(v127, *((_QWORD *)a3 + 4), 6);
  *(_OWORD *)Src = 0;
  v108 = 0;
  memset(v111, 0, sizeof(v111));
  v112 = 0;
  *(_OWORD *)v121 = 0;
  memset(v122, 0, sizeof(v122));
  std::unordered_set<unsigned int>::unordered_set<unsigned int>(v121);
  std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::reserve(
    v121,
    3 * a6 + *((_QWORD *)v11 + 2));
  std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::reserve(Src, 3 * a6 + *((_QWORD *)v11 + 2));
  if ( a6 > (v112 - *(_QWORD *)&v111[8]) >> 4 )
  {
    _mm_lfence();
    std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::reserve(&v111[8], a6);
  }
  v109 = 0;
  v115 = 0;
  v116 = 0;
  v113[0] = 0;
  v113[1] = 0;
  v114 = 0u;
  v13 = operator new(0x18u);
  *v13 = v13;
  v13[1] = v13;
  v113[1] = v13;
  *((_QWORD *)&v114 + 1) = 0;
  v115 = 0;
  *(_QWORD *)&v116 = 7;
  *((_QWORD *)&v116 + 1) = 8;
  LODWORD(v113[0]) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
    (char *)&v114 + 8,
    16,
    v13);
  v117 = &a9;
  v118 = v111;
  v119 = v106;
  v120 = v113;
  v14 = v106[0];
  if ( v106[0] )
  {
    v15 = *(_QWORD **)(v106[0] + 136LL);
    v16 = (_QWORD *)*v15;
    if ( (_QWORD *)*v15 != v15 )
    {
      do
      {
        LODWORD(v110[0]) = *((_DWORD *)v16 + 4);
        std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int>(
          (__int64)v121,
          (__int64)&v91,
          (unsigned __int8 *)v110);
        v16 = (_QWORD *)*v16;
      }
      while ( v16 != v15 );
      v14 = v106[0];
    }
    v17 = *(std::_Ref_count_base ***)(v14 + 8);
    v18 = *v17;
    if ( *v17 != (std::_Ref_count_base *)v17 )
    {
      do
      {
        v110[0] = *((std::_Ref_count_base **)v18 + 2);
        v91.m128i_i8[12] = 0;
        v86.m128i_i64[0] = LODWORD(v110[0]);
        v86.m128i_i64[1] = __PAIR64__(v91.m128i_u32[3], HIDWORD(v110[0]));
        std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
          (__int64)v121,
          (__int64)v105,
          (unsigned __int8 *)&v86);
        if ( !v117[4] || v86.m128i_i32[0] != *(_DWORD *)v117 )
        {
          *(__m128i *)v110 = v86;
          asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(v118, &v87, v110);
          if ( *v119 )
          {
            if ( (_BYTE)v90 && !BYTE4(v89) )
              std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::emplace<unsigned int &,float &>(
                (__int64)v120,
                (__int64)v104,
                &v87,
                &v89);
          }
        }
        v18 = *(std::_Ref_count_base **)v18;
      }
      while ( v18 != (std::_Ref_count_base *)v17 );
      v14 = v106[0];
    }
    v19 = *(__int64 ****)(v14 + 72);
    for ( i = *v19; i != (__int64 **)v19; i = (__int64 **)*i )
    {
      v110[0] = (std::_Ref_count_base *)i[2];
      v91.m128i_i8[12] = 1;
      v86.m128i_i64[0] = LODWORD(v110[0]);
      v86.m128i_i64[1] = __PAIR64__(v91.m128i_u32[3], HIDWORD(v110[0]));
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
        (__int64)v121,
        (__int64)v104,
        (unsigned __int8 *)&v86);
      v21 = v86;
      if ( !v117[4] || _mm_cvtsi128_si32(v86) != *(_DWORD *)v117 )
      {
        *(__m128i *)v110 = v86;
        asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(v118, &v87, v110);
        if ( *v119 )
        {
          if ( (_BYTE)v90 && !BYTE4(v89) )
            std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::emplace<unsigned int &,float &>(
              (__int64)v120,
              (__int64)v105,
              &v87,
              &v89);
        }
      }
      if ( Src[1] == v108 )
      {
        std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::_Emplace_reallocate<asg::SemanticIndex::DiskAnn::Neighbor>(
          Src,
          Src[1],
          &v86);
      }
      else
      {
        *(__m128i *)Src[1] = v21;
        Src[1] = (char *)Src[1] + 16;
      }
    }
  }
  if ( !*(_QWORD *)&v122[0] )
  {
    std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
      (__int64)v121,
      (__int64)v104,
      (unsigned __int8 *)&v99);
    *(_OWORD *)v110 = 0;
    asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(v11, v110, v9, (unsigned int)v99);
    v22 = v110[0];
    if ( *((_BYTE *)v110[0] + 64) == 1 )
    {
      v87 = 386;
      v88 = 13;
      v89 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
      v90 = "class std::vector<struct asg::SemanticIndex::DiskAnn::Neighbor,class std::allocator<struct asg::SemanticInde"
            "x::DiskAnn::Neighbor> > __cdecl asg::SemanticIndex::DiskAnn::Index::FindNearestNodes(class asg::SemanticInde"
            "x::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData co"
            "nst >,unsigned __int64,struct asg::SemanticIndex::DiskAnn::GraphContinuationData *,bool,class std::optional<"
            "unsigned int>) const";
      asg::details::AsgAssertFail(&v87);
    }
    v23 = *((_QWORD *)v110[0] + 4);
    if ( v23 )
      _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
    v91 = *(__m128i *)((char *)v22 + 24);
    v24 = (std::_Ref_count_base *)v91.m128i_i64[1];
    v25 = asg::SemanticIndex::DiskAnn::Index::CalculateDistance(
            v11,
            v9,
            *a5,
            (const struct asg::SemanticRegistry::IVectorData *)v91.m128i_i64[0]);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    v86.m128i_i64[0] = *((unsigned int *)v22 + 4);
    v86.m128i_i64[1] = LODWORD(v25);
    asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(v111, &v87, &v86);
    ++v109;
    if ( v110[1] )
      std::_Ref_count_base::_Decref(v110[1]);
  }
  v126 = 0;
  v26 = operator new(0x40u);
  *v26 = ___7___Func_impl_no_alloc_V_lambda_2___1__FindNearestNodes_Index_DiskAnn_SemanticIndex_asg__AEBA_AV__vector_UNeighbor_DiskAnn_SemanticIndex_asg__V__allocator_UNeighbor_DiskAnn_SemanticIndex_asg___std___std__AEAVOperationState_456_IV__shared_ptr___CBUIVectorData_SemanticRegistry_asg___8__KPEAUGraphContinuationData_456__NV__optional_I_8__Z_XV__shared_ptr_UGraphNode_DiskAnn_SemanticIndex_asg___8_H_std__6B_;
  v26[1] = v11;
  v26[2] = v9;
  v26[3] = v121;
  v26[4] = a5;
  v26[5] = &v117;
  v26[6] = &v109;
  v26[7] = v125;
  v126 = v26;
  v27 = *(_QWORD *)&v111[8];
  v28 = *(_QWORD *)v111;
  if ( *(_QWORD *)v111 >= (unsigned __int64)((__int64)(*(_QWORD *)&v111[16] - *(_QWORD *)&v111[8]) >> 4) )
  {
LABEL_66:
    if ( v106[0] )
    {
      *(_OWORD *)Block = 0;
      memset(v124, 0, sizeof(v124));
      std::unordered_set<unsigned int>::unordered_set<unsigned int>(Block);
      v50 = (unsigned __int8 *)Src[0];
      for ( j = (unsigned __int8 *)Src[1]; v50 != j; v50 += 16 )
        std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
          (__int64)Block,
          (__int64)v104,
          v50);
      v103 = (asg::SemanticIndex::DiskAnn::Index *)&v92;
      v92 = (int)v113[0];
      v93 = 0;
      v94 = 0;
      v52 = operator new(0x18u);
      *v52 = v52;
      v52[1] = v52;
      v93 = v52;
      v95 = 0;
      v96 = 0;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
        &v95,
        16,
        v52);
      v53 = v93;
      v93 = v113[1];
      v113[1] = v53;
      v54 = v94;
      v94 = v114;
      *(_QWORD *)&v114 = v54;
      v55 = v95;
      *(_QWORD *)&v95 = *((_QWORD *)&v114 + 1);
      *((_QWORD *)&v114 + 1) = v55;
      v56 = *((_QWORD *)&v95 + 1);
      *((_QWORD *)&v95 + 1) = v115;
      *(_QWORD *)&v115 = v56;
      v57 = v96;
      v96 = *((_QWORD *)&v115 + 1);
      *((_QWORD *)&v115 + 1) = v57;
      v58 = v116;
      *(_QWORD *)&v116 = 7;
      v97 = v58;
      v59 = *((_QWORD *)&v116 + 1);
      *((_QWORD *)&v116 + 1) = 8;
      v98 = v59;
      v103 = (asg::SemanticIndex::DiskAnn::Index *)&v92;
      v60 = v106[0];
      if ( *(_BYTE *)(v106[0] + 192LL) )
      {
        v87 = 53;
        v88 = 13;
        v89 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\include\\SemanticIndex\\DiskAnn\\QueryContinuationData.h";
        v90 = "void __cdecl asg::SemanticIndex::DiskAnn::GraphContinuationData::UpdateWithNewSearchResults(const class st"
              "d::unordered_set<unsigned int,struct std::hash<unsigned int>,struct std::equal_to<unsigned int>,class std:"
              ":allocator<unsigned int> > &,class std::unordered_set<struct asg::SemanticIndex::DiskAnn::QueryDistance,st"
              "ruct std::hash<struct asg::SemanticIndex::DiskAnn::QueryDistance>,struct std::equal_to<struct asg::Semanti"
              "cIndex::DiskAnn::QueryDistance>,class std::allocator<struct asg::SemanticIndex::DiskAnn::QueryDistance> >)";
        asg::details::AsgAssertFail(&v87);
      }
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>>(
        v106[0] + 128LL,
        *(_QWORD **)Block[1],
        (_QWORD *)Block[1]);
      if ( (int *)v60 != &v92 )
      {
        std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::clear(v60);
        *(_DWORD *)v60 = v92;
        v61 = *(void **)(v60 + 8);
        *(_QWORD *)(v60 + 8) = v93;
        v93 = v61;
        v62 = *(_QWORD *)(v60 + 16);
        *(_QWORD *)(v60 + 16) = v94;
        v94 = v62;
        v63 = *(_QWORD *)(v60 + 24);
        *(_QWORD *)(v60 + 24) = v95;
        *(_QWORD *)&v95 = v63;
        v64 = *(_QWORD *)(v60 + 32);
        *(_QWORD *)(v60 + 32) = *((_QWORD *)&v95 + 1);
        *((_QWORD *)&v95 + 1) = v64;
        v65 = *(_QWORD *)(v60 + 40);
        *(_QWORD *)(v60 + 40) = v96;
        v96 = v65;
        v66 = *(_QWORD *)(v60 + 48);
        *(_QWORD *)(v60 + 48) = v97;
        v97 = v66;
        v67 = *(_QWORD *)(v60 + 56);
        *(_QWORD *)(v60 + 56) = v98;
        v98 = v67;
      }
      std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::clear(v60 + 64);
      std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::_Insert_range_unchecked<asg::SemanticIndex::DiskAnn::QueryDistance const *,asg::SemanticIndex::DiskAnn::QueryDistance const *>(
        v60 + 64,
        0,
        0);
      std::_Hash<std::_Uset_traits<char16_t,std::_Uhash_compare<char16_t,std::hash<char16_t>,std::equal_to<char16_t>>,std::allocator<char16_t>,0>>::~_Hash<std::_Uset_traits<char16_t,std::_Uhash_compare<char16_t,std::hash<char16_t>,std::equal_to<char16_t>>,std::allocator<char16_t>,0>>(&v92);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)v124 + 8);
      v68 = (_QWORD **)Block[1];
      **((_QWORD **)Block[1] + 1) = 0;
      v69 = *v68;
      if ( v69 )
      {
        do
        {
          v70 = (_QWORD *)*v69;
          operator delete(v69);
          v69 = v70;
        }
        while ( v70 );
      }
      operator delete(Block[1]);
    }
    v71 = (volatile signed __int64 *)*((_QWORD *)v9 + 4);
    if ( v71 )
    {
      _InterlockedAdd64(v71, v109);
      _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)v9 + 4) + 72LL), v12);
    }
    v72 = v108;
    v108 = 0;
    v73 = Src[1];
    Src[1] = 0;
    v74 = Src[0];
    Src[0] = 0;
    *v10 = v74;
    v10[1] = v73;
    v10[2] = v72;
    if ( v126 )
    {
      LOBYTE(v72) = v126 != v125;
      (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v126 + 32LL))(v126, v72);
      v126 = 0;
    }
    std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v114 + 8);
    v75 = (_QWORD **)v113[1];
    **((_QWORD **)v113[1] + 1) = 0;
    v76 = *v75;
    if ( v76 )
    {
      do
      {
        v77 = (_QWORD *)*v76;
        operator delete(v76);
        v76 = v77;
      }
      while ( v77 );
    }
    operator delete(v113[1]);
    std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)v122 + 8);
    v78 = (_QWORD **)v121[1];
    **((_QWORD **)v121[1] + 1) = 0;
    v79 = *v78;
    if ( v79 )
    {
      do
      {
        v80 = (_QWORD *)*v79;
        operator delete(v79);
        v79 = v80;
      }
      while ( v80 );
    }
    operator delete(v121[1]);
    std::vector<std::u16string_view>::_Tidy(&v111[8]);
    v81 = Src[0];
    if ( Src[0] )
    {
      if ( (((char *)v108 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
      {
        _mm_lfence();
        v81 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v81 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v81);
      *(_OWORD *)Src = 0;
      v108 = 0;
    }
    asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v127);
    v82 = (volatile signed __int32 *)v102[1];
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
        if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
      }
    }
  }
  else
  {
    while ( 1 )
    {
      if ( (unsigned __int64)(((char *)Src[1] - (char *)Src[0]) >> 4) >= 0x2710 )
      {
LABEL_65:
        v9 = v101;
        v10 = v100;
        goto LABEL_66;
      }
      *(_BYTE *)(v27 + 16 * v28 + 12) = 1;
      v29 = *(_QWORD *)v111;
      v30 = (__int64)(*(_QWORD *)&v111[16] - *(_QWORD *)&v111[8]) >> 4;
      if ( *(_QWORD *)v111 < v30 )
      {
        v31 = *(_QWORD *)v111 + 1LL;
        v32 = *(_QWORD *)v111;
        do
        {
          v33 = v31;
          if ( !*(_BYTE *)(*(_QWORD *)&v111[8] + 16 * v32 + 12) )
            break;
          *(_QWORD *)v111 = v31++;
          v32 = v33;
        }
        while ( v33 < v30 );
      }
      v34 = 2 * v29;
      v35 = *(__m128 *)(*(_QWORD *)&v111[8] + 8 * v34);
      if ( a8 )
      {
        if ( *((float *)v11 + 17) > _mm_shuffle_ps(v35, v35, 170).m128_f32[0] )
          break;
      }
      LODWORD(v110[0]) = ++v12;
      v36 = Src[1];
      if ( Src[1] == v108 )
      {
        v37 = ((char *)Src[1] - (char *)Src[0]) >> 4;
        if ( v37 == 0xFFFFFFFFFFFFFFFLL )
          std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
            v108,
            v30,
            0xFFFFFFFFFFFFFFFLL);
        v38 = v37 + 1;
        v39 = ((char *)v108 - (char *)Src[0]) >> 4;
        v40 = v39 >> 1;
        if ( v39 <= 0xFFFFFFFFFFFFFFFLL - (v39 >> 1) )
        {
          v41 = v37 + 1;
          if ( v40 + v39 >= v38 )
            v41 = v40 + v39;
          if ( v41 > 0xFFFFFFFFFFFFFFFLL )
            __scrt_throw_std_bad_array_new_length();
        }
        else
        {
          v41 = 0xFFFFFFFFFFFFFFFLL;
        }
        _mm_lfence();
        v42 = 2 * v41;
        v43 = std::_Allocate<16,std::_Default_allocate_traits>(v42 * 8);
        v44 = 2 * v37;
        *(__m128 *)&v43[v44] = v35;
        v45 = Src[0];
        v46 = v43;
        if ( v36 == Src[1] )
        {
          v47 = (char *)((char *)Src[1] - (char *)Src[0]);
        }
        else
        {
          memmove(v43, Src[0], (size_t)v36 - (unsigned __int64)Src[0]);
          v46 = &v43[v44 + 2];
          _mm_lfence();
          v47 = (char *)((char *)Src[1] - (char *)v36);
          v45 = v36;
        }
        memmove(v46, v45, (size_t)v47);
        v48 = Src[0];
        if ( Src[0] )
        {
          if ( (((char *)v108 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
          {
            _mm_lfence();
            v48 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v48 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          operator delete(v48);
        }
        Src[0] = v43;
        Src[1] = &v43[2 * v38];
        v108 = &v43[v42];
        v11 = v103;
        v12 = (unsigned int)v110[0];
      }
      else
      {
        *(__m128 *)Src[1] = v35;
        Src[1] = (char *)Src[1] + 16;
      }
      v91 = 0;
      asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(
        v11,
        &v91,
        v101,
        (unsigned int)_mm_cvtsi128_si32((__m128i)v35));
      v86 = v91;
      v91 = 0;
      v99 = &v86;
      LODWORD(v110[0]) = 1;
      if ( !v126 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(_BYTE *, __m128i *, std::_Ref_count_base **))(*(_QWORD *)v126 + 16LL))(v126, &v86, v110);
      v49 = (volatile signed __int32 *)v86.m128i_i64[1];
      if ( v86.m128i_i64[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v86.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      v27 = *(_QWORD *)&v111[8];
      v28 = *(_QWORD *)v111;
      if ( *(_QWORD *)v111 >= (unsigned __int64)((__int64)(*(_QWORD *)&v111[16] - *(_QWORD *)&v111[8]) >> 4) )
        goto LABEL_65;
    }
    v91 = *(__m128i *)(*(_QWORD *)&v111[8] + 8 * v34);
    v10 = v100;
    *v100 = 0;
    v10[1] = 0;
    v10[2] = 0;
    _mm_lfence();
    v84 = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
    *v10 = v84;
    v10[1] = v84;
    v10[2] = v84 + 2;
    memmove(v84, &v91, 0x10u);
    v10[1] = v84 + 2;
    if ( v126 )
    {
      LOBYTE(v85) = v126 != v125;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v126 + 32LL))(v126, v85);
      v126 = 0;
    }
    std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v114 + 8);
    std::list<enum asg::SemanticRegistry::ModelClass>::~list<enum asg::SemanticRegistry::ModelClass>(&v113[1]);
    std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)v122 + 8);
    std::list<unsigned int>::~list<unsigned int>(&v121[1]);
    std::vector<std::u16string_view>::_Tidy(&v111[8]);
    std::vector<std::u16string_view>::_Tidy(Src);
    asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v127);
    std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(v102);
  }
  return v10;
}

```

## disassembly

```asm
0x1801b0040  push    rbp
0x1801b0042  push    rbx
0x1801b0043  push    rsi
0x1801b0044  push    rdi
0x1801b0045  push    r12
0x1801b0047  push    r13
0x1801b0049  push    r14
0x1801b004b  push    r15
0x1801b004d  lea     rbp, [rsp-208h]
0x1801b0055  sub     rsp, 308h
0x1801b005c  movaps  [rsp+340h+var_50], xmm6
0x1801b0064  mov     rax, cs:__security_cookie
0x1801b006b  xor     rax, rsp
0x1801b006e  mov     [rbp+240h+var_60], rax
0x1801b0075  mov     r13, r8
0x1801b0078  mov     [rbp+240h+var_280], r8
0x1801b007c  mov     rsi, rdx
0x1801b007f  mov     [rbp+240h+var_288], rdx
0x1801b0083  mov     r14, rcx
0x1801b0086  mov     [rbp+240h+var_270], rcx
0x1801b008a  mov     [rbp+240h+var_278], rdx
0x1801b008e  mov     dword ptr [rbp+240h+var_290], r9d
0x1801b0092  mov     r12, [rbp+240h+arg_20]
0x1801b0099  mov     [rbp+240h+var_278], r12
0x1801b009d  mov     [rbp+240h+var_238], r12
0x1801b00a1  mov     rax, [rbp+240h+arg_30]
0x1801b00a8  mov     [rbp+240h+var_240], rax
0x1801b00ac  xor     r15d, r15d
0x1801b00af  mov     r8d, 6
0x1801b00b5  mov     rdx, [r13+20h]
0x1801b00b9  lea     rcx, [rbp+240h+var_C0]
0x1801b00c0  call    asg__SemanticIndex__DiskAnn__Checkpoint
0x1801b00c5  nop
0x1801b00c6  xorps   xmm0, xmm0
0x1801b00c9  xorps   xmm1, xmm1
0x1801b00cc  movdqu  xmmword ptr [rbp+240h+Src], xmm1
0x1801b00d1  mov     [rbp+240h+var_220], r15
0x1801b00d5  movups  [rbp+240h+var_200], xmm0
0x1801b00d9  movups  [rbp+240h+var_1F0], xmm0
0x1801b00dd  mov     qword ptr [rbp+240h+var_200], r15
0x1801b00e1  movdqu  [rbp+240h+var_200+8], xmm1
0x1801b00e6  mov     qword ptr [rbp+240h+var_1F0+8], r15
0x1801b00ea  movups  xmmword ptr [rbp+240h+var_180], xmm0
0x1801b00f1  movups  [rbp+240h+var_170], xmm0
0x1801b00f8  movups  [rbp+240h+var_160], xmm0
0x1801b00ff  movups  [rbp+240h+var_150], xmm0
0x1801b0106  lea     rcx, [rbp+240h+var_180]
0x1801b010d  call    ??0?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@QEAA@XZ; std::unordered_set<uint>::unordered_set<uint>(void)
0x1801b0112  nop
0x1801b0113  mov     rdi, [rbp+240h+arg_28]
0x1801b011a  lea     rbx, [rdi+rdi*2]
0x1801b011e  mov     rdx, [r14+10h]
0x1801b0122  add     rdx, rbx
0x1801b0125  lea     rcx, [rbp+240h+var_180]
0x1801b012c  call    ?reserve@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAAX_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::reserve(unsigned __int64)
0x1801b0131  mov     rdx, [r14+10h]
0x1801b0135  add     rdx, rbx
0x1801b0138  lea     rcx, [rbp+240h+Src]
0x1801b013c  call    ?reserve@?$vector@UNeighbor@DiskAnn@SemanticIndex@asg@@V?$allocator@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@@std@@QEAAX_K@Z; std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::reserve(unsigned __int64)
0x1801b0141  mov     rax, qword ptr [rbp+240h+var_1F0+8]
0x1801b0145  sub     rax, qword ptr [rbp+240h+var_200+8]
0x1801b0149  sar     rax, 4
0x1801b014d  cmp     rdi, rax
0x1801b0150  jbe     short loc_1801B0161
0x1801b0152  lfence
0x1801b0155  mov     rdx, rdi
0x1801b0158  lea     rcx, [rbp+240h+var_200+8]
0x1801b015c  call    ?reserve@?$vector@UNeighbor@DiskAnn@SemanticIndex@asg@@V?$allocator@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@@std@@QEAAX_K@Z; std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::reserve(unsigned __int64)
0x1801b0161  mov     [rbp+240h+var_218], r15d
0x1801b0165  xorps   xmm0, xmm0
0x1801b0168  movups  xmmword ptr [rbp+240h+var_1E0], xmm0
0x1801b016c  movups  [rbp+240h+var_1D0], xmm0
0x1801b0170  movups  [rbp+240h+var_1C0], xmm0
0x1801b0177  movups  [rbp+240h+var_1B0], xmm0
0x1801b017e  mov     dword ptr [rbp+240h+var_1E0], 0
0x1801b0185  xor     ebx, ebx
0x1801b0187  mov     [rbp+240h+var_1E0+8], rbx
0x1801b018b  mov     qword ptr [rbp+240h+var_1D0], rbx
0x1801b018f  mov     ecx, 18h; Size
0x1801b0194  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801b0199  mov     [rax], rax
0x1801b019c  mov     [rax+8], rax
0x1801b01a0  mov     [rbp+240h+var_1E0+8], rax
0x1801b01a4  mov     qword ptr [rbp+240h+var_1D0+8], rbx
0x1801b01a8  xorps   xmm0, xmm0
0x1801b01ab  movdqa  [rbp+240h+var_1C0], xmm0
0x1801b01b3  mov     qword ptr [rbp+240h+var_1B0], 7
0x1801b01be  mov     qword ptr [rbp+240h+var_1B0+8], 8
0x1801b01c9  mov     dword ptr [rbp+240h+var_1E0], 3F800000h
0x1801b01d0  mov     r8, rax
0x1801b01d3  mov     edx, 10h
0x1801b01d8  lea     rcx, [rbp+240h+var_1D0+8]
0x1801b01dc  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbValue@Sqlite@asg@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbValue@Sqlite@asg@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>)
0x1801b01e1  nop
0x1801b01e2  lea     rax, [rbp+240h+arg_40]
0x1801b01e9  mov     [rbp+240h+var_1A0], rax
0x1801b01f0  lea     rax, [rbp+240h+var_200]
0x1801b01f4  mov     [rbp+240h+var_198], rax
0x1801b01fb  lea     rax, [rbp+240h+var_240]
0x1801b01ff  mov     [rbp+240h+var_190], rax
0x1801b0206  lea     rax, [rbp+240h+var_1E0]
0x1801b020a  mov     [rbp+240h+var_188], rax
0x1801b0211  mov     rax, [rbp+240h+var_240]
0x1801b0215  test    rax, rax
0x1801b0218  jz      loc_1801B041C
0x1801b021e  mov     rdi, [rax+88h]
0x1801b0225  mov     rbx, [rdi]
0x1801b0228  cmp     rbx, rdi
0x1801b022b  jz      short loc_1801B0257
0x1801b022d  nop     dword ptr [rax]
0x1801b0230  mov     eax, [rbx+10h]
0x1801b0233  mov     dword ptr [rbp+240h+var_210], eax
0x1801b0236  lea     r8, [rbp+240h+var_210]
0x1801b023a  lea     rdx, [rsp+340h+var_2E0]
0x1801b023f  lea     rcx, [rbp+240h+var_180]
0x1801b0246  call    ??$emplace@I@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@$$QEAI@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint>(uint &&)
0x1801b024b  mov     rbx, [rbx]
0x1801b024e  cmp     rbx, rdi
0x1801b0251  jnz     short loc_1801B0230
0x1801b0253  mov     rax, [rbp+240h+var_240]
0x1801b0257  mov     rdi, [rax+8]
0x1801b025b  mov     rbx, [rdi]
0x1801b025e  cmp     rbx, rdi
0x1801b0261  jz      loc_1801B032E
0x1801b0267  nop     word ptr [rax+rax+00000000h]
0x1801b0270  mov     rax, [rbx+10h]
0x1801b0274  mov     [rbp+240h+var_210], rax
0x1801b0278  mov     byte ptr [rsp+340h+var_2E0+0Ch], 0
0x1801b027d  mov     dword ptr [rsp+340h+var_310], eax
0x1801b0281  mov     dword ptr [rsp+340h+var_310+4], 0
0x1801b0289  movss   xmm1, dword ptr [rbp+240h+var_210+4]
0x1801b028e  movss   dword ptr [rsp+340h+var_310+8], xmm1
0x1801b0294  movss   xmm0, dword ptr [rsp+340h+var_2E0+0Ch]
0x1801b029a  movss   dword ptr [rsp+340h+var_310+0Ch], xmm0
0x1801b02a0  lea     r8, [rsp+340h+var_310]
0x1801b02a5  lea     rdx, [rbp+240h+var_250]
0x1801b02a9  lea     rcx, [rbp+240h+var_180]
0x1801b02b0  call    ??$emplace@AEBI@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint const &>(uint const &)
0x1801b02b5  mov     rax, [rbp+240h+var_1A0]
0x1801b02bc  cmp     byte ptr [rax+4], 0
0x1801b02c0  jz      short loc_1801B02CA
0x1801b02c2  mov     eax, [rax]
0x1801b02c4  cmp     dword ptr [rsp+340h+var_310], eax
0x1801b02c8  jz      short loc_1801B031E
0x1801b02ca  movaps  xmm0, [rsp+340h+var_310]
0x1801b02cf  movdqa  xmmword ptr [rbp+240h+var_210], xmm0
0x1801b02d4  lea     r8, [rbp+240h+var_210]
0x1801b02d8  lea     rdx, [rsp+340h+var_300]
0x1801b02dd  mov     rcx, [rbp+240h+var_198]
0x1801b02e4  call    ?Insert@NeighborPriorityQueue@DiskAnn@SemanticIndex@asg@@QEAA?AV?$optional@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@UNeighbor@234@@Z; asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(asg::SemanticIndex::DiskAnn::Neighbor)
0x1801b02e9  mov     rax, [rbp+240h+var_190]
0x1801b02f0  cmp     qword ptr [rax], 0
0x1801b02f4  jz      short loc_1801B031E
0x1801b02f6  cmp     byte ptr [rsp+340h+var_2F0], 0
0x1801b02fb  jz      short loc_1801B031E
0x1801b02fd  cmp     byte ptr [rsp+340h+var_2F8+4], 0
0x1801b0302  jnz     short loc_1801B031E
0x1801b0304  lea     r9, [rsp+340h+var_2F8]
0x1801b0309  lea     r8, [rsp+340h+var_300]
0x1801b030e  lea     rdx, [rbp+240h+var_260]
0x1801b0312  mov     rcx, [rbp+240h+var_188]
0x1801b0319  call    ??$emplace@AEAIAEAM@?$_Hash@V?$_Uset_traits@UQueryDistance@DiskAnn@SemanticIndex@asg@@V?$_Uhash_compare@UQueryDistance@DiskAnn@SemanticIndex@asg@@U?$hash@UQueryDistance@DiskAnn@SemanticIndex@asg@@@std@@U?$equal_to@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@@std@@V?$allocator@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UQueryDistance@DiskAnn@SemanticIndex@asg@@@std@@@std@@@std@@_N@1@AEAIAEAM@Z; std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::emplace<uint &,float &>(uint &,float &)
0x1801b031e  mov     rbx, [rbx]
0x1801b0321  cmp     rbx, rdi
0x1801b0324  jnz     loc_1801B0270
0x1801b032a  mov     rax, [rbp+240h+var_240]
0x1801b032e  mov     rdi, [rax+48h]
0x1801b0332  mov     rbx, [rdi]
0x1801b0335  cmp     rbx, rdi
0x1801b0338  jz      loc_1801B041C
0x1801b033e  xchg    ax, ax
0x1801b0340  mov     rax, [rbx+10h]
0x1801b0344  mov     [rbp+240h+var_210], rax
0x1801b0348  mov     byte ptr [rsp+340h+var_2E0+0Ch], 1
0x1801b034d  mov     dword ptr [rsp+340h+var_310], eax
0x1801b0351  mov     dword ptr [rsp+340h+var_310+4], 0
0x1801b0359  movss   xmm1, dword ptr [rbp+240h+var_210+4]
0x1801b035e  movss   dword ptr [rsp+340h+var_310+8], xmm1
0x1801b0364  movss   xmm0, dword ptr [rsp+340h+var_2E0+0Ch]
0x1801b036a  movss   dword ptr [rsp+340h+var_310+0Ch], xmm0
0x1801b0370  lea     r8, [rsp+340h+var_310]
0x1801b0375  lea     rdx, [rbp+240h+var_260]
0x1801b0379  lea     rcx, [rbp+240h+var_180]
0x1801b0380  call    ??$emplace@AEBI@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint const &>(uint const &)
0x1801b0385  movaps  xmm6, [rsp+340h+var_310]
0x1801b038a  mov     rcx, [rbp+240h+var_1A0]
0x1801b0391  cmp     byte ptr [rcx+4], 0
0x1801b0395  jz      short loc_1801B039F
0x1801b0397  movd    eax, xmm6
0x1801b039b  cmp     eax, [rcx]
0x1801b039d  jz      short loc_1801B03EE
0x1801b039f  movdqa  xmmword ptr [rbp+240h+var_210], xmm6
0x1801b03a4  lea     r8, [rbp+240h+var_210]
0x1801b03a8  lea     rdx, [rsp+340h+var_300]
0x1801b03ad  mov     rcx, [rbp+240h+var_198]
0x1801b03b4  call    ?Insert@NeighborPriorityQueue@DiskAnn@SemanticIndex@asg@@QEAA?AV?$optional@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@UNeighbor@234@@Z; asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(asg::SemanticIndex::DiskAnn::Neighbor)
0x1801b03b9  mov     rax, [rbp+240h+var_190]
0x1801b03c0  cmp     qword ptr [rax], 0
0x1801b03c4  jz      short loc_1801B03EE
0x1801b03c6  cmp     byte ptr [rsp+340h+var_2F0], 0
0x1801b03cb  jz      short loc_1801B03EE
0x1801b03cd  cmp     byte ptr [rsp+340h+var_2F8+4], 0
0x1801b03d2  jnz     short loc_1801B03EE
0x1801b03d4  lea     r9, [rsp+340h+var_2F8]
0x1801b03d9  lea     r8, [rsp+340h+var_300]
0x1801b03de  lea     rdx, [rbp+240h+var_250]
0x1801b03e2  mov     rcx, [rbp+240h+var_188]
0x1801b03e9  call    ??$emplace@AEAIAEAM@?$_Hash@V?$_Uset_traits@UQueryDistance@DiskAnn@SemanticIndex@asg@@V?$_Uhash_compare@UQueryDistance@DiskAnn@SemanticIndex@asg@@U?$hash@UQueryDistance@DiskAnn@SemanticIndex@asg@@@std@@U?$equal_to@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@@std@@V?$allocator@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UQueryDistance@DiskAnn@SemanticIndex@asg@@@std@@@std@@@std@@_N@1@AEAIAEAM@Z; std::_Hash<std::_Uset_traits<asg::SemanticIndex::DiskAnn::QueryDistance,std::_Uhash_compare<asg::SemanticIndex::DiskAnn::QueryDistance,std::hash<asg::SemanticIndex::DiskAnn::QueryDistance>,std::equal_to<asg::SemanticIndex::DiskAnn::QueryDistance>>,std::allocator<asg::SemanticIndex::DiskAnn::QueryDistance>,0>>::emplace<uint &,float &>(uint &,float &)
0x1801b03ee  mov     rdx, [rbp+240h+Src+8]
0x1801b03f2  cmp     rdx, [rbp+240h+var_220]
0x1801b03f6  jz      short loc_1801B0402
0x1801b03f8  movups  xmmword ptr [rdx], xmm6
0x1801b03fb  add     [rbp+240h+Src+8], 10h
0x1801b0400  jmp     short loc_1801B0410
0x1801b0402  lea     r8, [rsp+340h+var_310]
0x1801b0407  lea     rcx, [rbp+240h+Src]
0x1801b040b  call    ??$_Emplace_reallocate@UNeighbor@DiskAnn@SemanticIndex@asg@@@?$vector@UNeighbor@DiskAnn@SemanticIndex@asg@@V?$allocator@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@@std@@AEAAPEAUNeighbor@DiskAnn@SemanticIndex@asg@@QEAU2345@$$QEAU2345@@Z; std::vector<asg::SemanticIndex::DiskAnn::Neighbor>::_Emplace_reallocate<asg::SemanticIndex::DiskAnn::Neighbor>(asg::SemanticIndex::DiskAnn::Neighbor * const,asg::SemanticIndex::DiskAnn::Neighbor &&)
0x1801b0410  mov     rbx, [rbx]
0x1801b0413  cmp     rbx, rdi
0x1801b0416  jnz     loc_1801B0340
0x1801b041c  cmp     qword ptr [rbp+240h+var_170], 0
0x1801b0424  jnz     loc_1801B04E6
0x1801b042a  lea     r8, [rbp+240h+var_290]
0x1801b042e  lea     rdx, [rbp+240h+var_260]
0x1801b0432  lea     rcx, [rbp+240h+var_180]
0x1801b0439  call    ??$emplace@AEBI@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::emplace<uint const &>(uint const &)
0x1801b043e  xorps   xmm0, xmm0
0x1801b0441  movups  xmmword ptr [rbp+240h+var_210], xmm0
0x1801b0445  mov     r9d, dword ptr [rbp+240h+var_290]
0x1801b0449  mov     r8, r13
0x1801b044c  lea     rdx, [rbp+240h+var_210]
0x1801b0450  mov     rcx, r14
0x1801b0453  call    ?GetGraphNodeAndUpdateCache@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@I@Z; asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(asg::SemanticIndex::DiskAnn::OperationState &,uint)
0x1801b0458  nop
0x1801b0459  mov     rbx, [rbp+240h+var_210]
0x1801b045d  cmp     byte ptr [rbx+40h], 1
0x1801b0461  jz      loc_1801B0D36
0x1801b0467  mov     rax, [rbx+20h]
0x1801b046b  test    rax, rax
0x1801b046e  jz      short loc_1801B0474
0x1801b0470  lock inc dword ptr [rax+8]
0x1801b0474  mov     r9, [rbx+18h]; struct asg::SemanticRegistry::IVectorData *
0x1801b0478  mov     qword ptr [rsp+340h+var_2E0], r9
0x1801b047d  mov     rdi, [rbx+20h]
0x1801b0481  mov     [rsp+68h], rdi
0x1801b0486  mov     r8, [r12]; struct asg::SemanticRegistry::IVectorData *
0x1801b048a  mov     rdx, r13; struct asg::SemanticIndex::DiskAnn::OperationState *
0x1801b048d  mov     rcx, r14; this
0x1801b0490  call    ?CalculateDistance@Index@DiskAnn@SemanticIndex@asg@@AEBAMAEBVOperationState@234@AEBUIVectorData@SemanticRegistry@4@1@Z; asg::SemanticIndex::DiskAnn::Index::CalculateDistance(asg::SemanticIndex::DiskAnn::OperationState const &,asg::SemanticRegistry::IVectorData const &,asg::SemanticRegistry::IVectorData const &)
0x1801b0495  movaps  xmm6, xmm0
0x1801b0498  test    rdi, rdi
0x1801b049b  jz      short loc_1801B04A5
0x1801b049d  mov     rcx, rdi; this
0x1801b04a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801b04a5  mov     eax, [rbx+10h]
0x1801b04a8  mov     dword ptr [rsp+340h+var_310], eax
0x1801b04ac  mov     dword ptr [rsp+340h+var_310+4], 0
0x1801b04b4  movss   dword ptr [rsp+340h+var_310+8], xmm6
0x1801b04ba  mov     dword ptr [rsp+340h+var_310+0Ch], 0
0x1801b04c2  lea     r8, [rsp+340h+var_310]
0x1801b04c7  lea     rdx, [rsp+340h+var_300]
0x1801b04cc  lea     rcx, [rbp+240h+var_200]
0x1801b04d0  call    ?Insert@NeighborPriorityQueue@DiskAnn@SemanticIndex@asg@@QEAA?AV?$optional@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@UNeighbor@234@@Z; asg::SemanticIndex::DiskAnn::NeighborPriorityQueue::Insert(asg::SemanticIndex::DiskAnn::Neighbor)
0x1801b04d5  inc     [rbp+240h+var_218]
0x1801b04d8  mov     rcx, [rbp+240h+var_210+8]; this
0x1801b04dc  test    rcx, rcx
0x1801b04df  jz      short loc_1801B04E6
0x1801b04e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801b04e6  xor     edi, edi
0x1801b04e8  mov     [rbp+240h+var_C8], rdi
0x1801b04ef  mov     ecx, 40h ; '@'; Size
0x1801b04f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801b04f9  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_2_@?1??FindNearestNodes@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$vector@UNeighbor@DiskAnn@SemanticIndex@asg@@V?$allocator@UNeighbor@DiskAnn@SemanticIndex@asg@@@std@@@std@@AEAVOperationState@456@IV?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@8@_KPEAUGraphContinuationData@456@_NV?$optional@I@8@@Z@XV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@8@H@std@@6B@; const std::_Func_impl_no_alloc<`asg::SemanticIndex::DiskAnn::Index::FindNearestNodes(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,unsigned __int64,asg::SemanticIndex::DiskAnn::GraphContinuationData *,bool,std::optional<uint>)'::`2'::_lambda_2_,void,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,int>::`vftable'
0x1801b0500  mov     [rax], rcx
0x1801b0503  mov     [rax+8], r14
0x1801b0507  mov     [rax+10h], r13
0x1801b050b  lea     rcx, [rbp+240h+var_180]
0x1801b0512  mov     [rax+18h], rcx
0x1801b0516  mov     [rax+20h], r12
0x1801b051a  lea     rcx, [rbp+240h+var_1A0]
0x1801b0521  mov     [rax+28h], rcx
0x1801b0525  lea     rcx, [rbp+240h+var_218]
0x1801b0529  mov     [rax+30h], rcx
0x1801b052d  lea     rcx, [rbp+240h+var_100]
0x1801b0534  mov     [rax+38h], rcx
0x1801b0538  mov     [rbp+240h+var_C8], rax
0x1801b053f  mov     rax, qword ptr [rbp+240h+var_1F0]
0x1801b0543  mov     rdx, qword ptr [rbp+240h+var_200+8]
0x1801b0547  sub     rax, rdx
0x1801b054a  sar     rax, 4
0x1801b054e  mov     r12d, 0FFFFFFFFh
0x1801b0554  mov     rcx, qword ptr [rbp+240h+var_200]
0x1801b0558  cmp     rcx, rax
0x1801b055b  jnb     loc_1801B07F0
0x1801b0561  movzx   r13d, [rbp+240h+arg_38]
0x1801b0569  mov     r8, 0FFFFFFFFFFFFFFFh
0x1801b0573  mov     rax, [rbp+240h+Src+8]
0x1801b0577  sub     rax, [rbp+240h+Src]
0x1801b057b  sar     rax, 4
0x1801b057f  cmp     rax, 2710h
  ... truncated ...
```
