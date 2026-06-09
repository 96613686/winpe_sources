# asg::SemanticIndex::DiskAnn::Index::AddReverseLink(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::vector<uint,std::allocator<uint>> const &)

- ea: `0x1801add80`
- end: `0x1801aed8e`
- name: `?AddReverseLink@Index@DiskAnn@SemanticIndex@asg@@AEAAXAEAVOperationState@234@IAEBV?$vector@IV?$allocator@I@std@@@std@@@Z`
- size: `4110`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b2e50`

## callees

- `0x1800040f0`
- `0x180006220`
- `0x180006600`
- `0x180006b60`
- `0x180006e30`
- `0x180007360`
- `0x1800076f0`
- `0x180007b20`
- `0x180007ba0`
- `0x1800178d0`
- `0x180018410`
- `0x18002b6f0`
- `0x18002c570`
- `0x180030ee0`
- `0x18003f290`
- `0x1800416e0`
- `0x180041740`
- `0x180042c90`
- `0x180043b70`
- `0x180078ed0`
- `0x18007f3c0`
- `0x18007f440`
- `0x1801a9de0`
- `0x1801aa050`
- `0x1801aa360`
- `0x1801aa690`
- `0x1801ab500`
- `0x1801ad6d0`
- `0x1801ad780`
- `0x1801ad820`
- `0x1801add80`
- `0x1801afc60`
- `0x1801b0db0`
- `0x1801b13c0`
- `0x1801b4d80`
- `0x1801b4e70`
- `0x1801b4fa0`
- `0x1801ccfb0`
- `0x1801cefb0`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`
- `0x180211440`
- `0x1802421a0`

## string_xrefs

- `0x1801aeccb`: `void __cdecl asg::SemanticIndex::DiskAnn::Index::AddReverseLink(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,const class std::vector<unsigned int,class std::allocator<unsigned int> > &)`
- `0x1801aed05`: `void __cdecl asg::SemanticIndex::DiskAnn::Index::AddReverseLink(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,const class std::vector<unsigned int,class std::allocator<unsigned int> > &)`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall asg::SemanticIndex::DiskAnn::Index::AddReverseLink(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int **a4)
{
  unsigned int v5; // esi
  __int64 v7; // r15
  unsigned __int64 v8; // r12
  __int64 v9; // rax
  unsigned int *v10; // r13
  unsigned int *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rbx
  _QWORD *v14; // r15
  __int128 v15; // kr00_16
  _DWORD *v16; // rax
  void *v17; // rbx
  signed __int64 v18; // rdi
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rsi
  _QWORD *v23; // r14
  _DWORD *v24; // rcx
  _DWORD *v25; // rdi
  const void *v26; // rdx
  void *v27; // rcx
  char *v28; // r8
  const char *v29; // rdx
  const char *v30; // rcx
  void **v31; // rax
  char v32; // r8
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // r12
  __int64 v36; // r13
  unsigned int *v37; // rdi
  unsigned int *v38; // r15
  unsigned int v39; // r12d
  __int64 v40; // rdx
  void *v41; // rdi
  signed __int64 v42; // rbx
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rsi
  _QWORD *v46; // r14
  const void *v47; // rdx
  char *v48; // rcx
  char *v49; // r8
  volatile signed __int32 *v50; // rbx
  __int64 ClearedNodeIdsForConsolidation; // rbx
  unsigned int *v52; // rsi
  unsigned int *i; // r14
  _DWORD *v54; // rdi
  _DWORD *j; // rbx
  volatile signed __int32 *v56; // rbx
  char *v57; // rax
  _QWORD **v58; // rcx
  _QWORD *v59; // rcx
  _QWORD *v60; // rbx
  unsigned int *v61; // rsi
  unsigned int *k; // r14
  std::_Ref_count_base *v63; // rdi
  _QWORD *v64; // rax
  unsigned __int64 v65; // rcx
  float v66; // xmm0_4
  float v67; // xmm7_4
  float v68; // xmm0_4
  unsigned __int64 v69; // rax
  unsigned __int64 v70; // rbx
  float v71; // xmm0_4
  float v72; // xmm0_4
  unsigned __int64 v73; // rax
  unsigned __int64 v74; // rdx
  char v75; // cl
  __int64 v76; // rax
  const char *v77; // rdx
  const char *v78; // rcx
  void **v79; // rax
  char v80; // r8
  __int64 v81; // rax
  volatile signed __int32 *v82; // rbx
  _QWORD **v83; // rcx
  _QWORD *v84; // rcx
  _QWORD *v85; // rbx
  _QWORD **v86; // rcx
  _QWORD *v87; // rcx
  _QWORD *v88; // rbx
  volatile signed __int32 *v89; // rbx
  void *v90; // rcx
  __int64 v91; // rdi
  __int64 v92; // rbx
  void *v93; // rcx
  void *v94; // rcx
  void *v95; // rcx
  int v96; // [rsp+30h] [rbp-D8h]
  int v97; // [rsp+38h] [rbp-D0h]
  __int64 pExceptionObject; // [rsp+48h] [rbp-C0h] BYREF
  const char *v99; // [rsp+50h] [rbp-B8h]
  const char *v100; // [rsp+58h] [rbp-B0h]
  __int64 v101; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v102; // [rsp+70h] [rbp-98h] BYREF
  void **v103; // [rsp+80h] [rbp-88h] BYREF
  __int128 v104; // [rsp+88h] [rbp-80h] BYREF
  int v105[2]; // [rsp+98h] [rbp-70h]
  void **v106; // [rsp+A0h] [rbp-68h] BYREF
  const char *v107; // [rsp+A8h] [rbp-60h]
  const char *v108; // [rsp+B0h] [rbp-58h]
  int v109[2]; // [rsp+B8h] [rbp-50h]
  __int128 v110; // [rsp+C0h] [rbp-48h] BYREF
  std::_Ref_count_base *v111[2]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int8 v112[16]; // [rsp+E0h] [rbp-28h] BYREF
  unsigned int v113; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v114; // [rsp+F8h] [rbp-10h] BYREF
  void **v115; // [rsp+108h] [rbp+0h] BYREF
  const char *v116; // [rsp+110h] [rbp+8h]
  unsigned __int64 v117; // [rsp+118h] [rbp+10h]
  __int128 v118; // [rsp+120h] [rbp+18h] BYREF
  __int64 v119; // [rsp+130h] [rbp+28h]
  __int128 v120; // [rsp+138h] [rbp+30h]
  _BYTE v121[64]; // [rsp+148h] [rbp+40h] BYREF
  char v122[64]; // [rsp+188h] [rbp+80h] BYREF
  void *v123[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  const char *v124; // [rsp+1D8h] [rbp+D0h]
  void *Src[2]; // [rsp+1E0h] [rbp+D8h] BYREF
  void *v126; // [rsp+1F0h] [rbp+E8h]
  __int128 v127; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v128; // [rsp+208h] [rbp+100h]
  __int128 v129; // [rsp+210h] [rbp+108h] BYREF
  __int64 v130; // [rsp+220h] [rbp+118h]
  void *Block[2]; // [rsp+228h] [rbp+120h] BYREF
  __int128 v132; // [rsp+238h] [rbp+130h] BYREF
  __int128 v133; // [rsp+248h] [rbp+140h]
  __int128 v134; // [rsp+258h] [rbp+150h]
  void *v135[2]; // [rsp+268h] [rbp+160h] BYREF
  _OWORD v136[3]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v137[64]; // [rsp+2A8h] [rbp+1A0h] BYREF
  _BYTE v138[64]; // [rsp+2E8h] [rbp+1E0h] BYREF
  _BYTE v139[96]; // [rsp+328h] [rbp+220h] BYREF

  v5 = a3;
  *(_DWORD *)v112 = a3;
  *(_QWORD *)v105 = a2;
  v7 = a1;
  *(_QWORD *)v109 = a1;
  v113 = a3;
  v97 = 0;
  asg::SemanticIndex::DiskAnn::Checkpoint(v139, *(_QWORD *)(a2 + 32), 4);
  if ( *a4 == a4[1] )
  {
    pExceptionObject = 0x9000002B1LL;
    v99 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v100 = "void __cdecl asg::SemanticIndex::DiskAnn::Index::AddReverseLink(class asg::SemanticIndex::DiskAnn::OperationS"
           "tate &,unsigned int,const class std::vector<unsigned int,class std::allocator<unsigned int> > &)";
    asg::details::AsgAssertFail(&pExceptionObject);
  }
  v8 = *(_QWORD *)(v7 + 16) + *(_QWORD *)(v7 + 24);
  *(_QWORD *)&v114 = v8;
  v9 = std::vector<unsigned int>::vector<unsigned int>(&pExceptionObject, a4);
  asg::SemanticIndex::DiskAnn::Index::PopulateNodeCache<std::vector<unsigned int>>(v7, a2, v9);
  v129 = 0;
  v130 = 0;
  std::vector<std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>::reserve(&v129, a4[1] - *a4);
  *(_OWORD *)Src = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v10 = *a4;
  v11 = a4[1];
  *(_QWORD *)&v110 = v11;
  if ( v10 != v11 )
  {
    while ( 1 )
    {
      v12 = *v10;
      LODWORD(v103) = v12;
      v102 = 0;
      asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(v7, &v102, *(_QWORD *)v105, v12);
      v13 = v102;
      if ( *(_BYTE *)(v102 + 64) == 1 )
      {
        pExceptionObject = 0xD000002CCLL;
        v99 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
        v100 = "void __cdecl asg::SemanticIndex::DiskAnn::Index::AddReverseLink(class asg::SemanticIndex::DiskAnn::Operat"
               "ionState &,unsigned int,const class std::vector<unsigned int,class std::allocator<unsigned int> > &)";
        asg::details::AsgAssertFail(&pExceptionObject);
      }
      v14 = (_QWORD *)(v102 + 40);
      v15 = *(_OWORD *)(v102 + 40);
      v16 = (_DWORD *)v15;
      if ( (_QWORD)v15 == *((_QWORD *)&v15 + 1) )
        goto LABEL_9;
      while ( *v16 != v5 )
      {
        if ( ++v16 == *((_DWORD **)&v15 + 1) )
          goto LABEL_9;
      }
      if ( v16 == *((_DWORD **)&v15 + 1) )
      {
LABEL_9:
        if ( ((__int64)(*((_QWORD *)&v15 + 1) - v15) >> 2) + 1 <= v8 )
        {
          *(_OWORD *)v123 = 0;
          v124 = 0;
          asg::SemanticIndex::DiskAnn::Index::AddReverseLink_::_2_::_lambda_1_::operator()(&v101, v123, v102 + 40, v5);
          *(_OWORD *)v111 = 0;
          v29 = v124;
          v124 = 0;
          v30 = (const char *)v123[1];
          v123[1] = 0;
          v31 = (void **)v123[0];
          v123[0] = 0;
          v106 = v31;
          v107 = v30;
          v108 = v29;
          v103 = (void **)&v106;
          v32 = *(_BYTE *)(v13 + 64);
          v108 = 0;
          v107 = 0;
          v106 = 0;
          pExceptionObject = (__int64)v31;
          v99 = v30;
          v100 = v29;
          v104 = 0;
          v33 = *(_QWORD *)(v13 + 32);
          if ( v33 )
            _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
          v104 = *(_OWORD *)(v13 + 24);
          asg::SemanticIndex::DiskAnn::GraphNode::Make(
            (unsigned int)v111,
            *(_DWORD *)(v13 + 16),
            (unsigned int)&v104,
            (unsigned int)&pExceptionObject,
            v32);
          v97 |= 4u;
          std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(&v106);
          std::vector<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor const>>::_Emplace_one_at_back<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor>>(
            &v129,
            v111);
          if ( v111[1] )
            std::_Ref_count_base::_Decref(v111[1]);
          std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(v123);
        }
        else
        {
          v17 = Src[1];
          if ( Src[1] == v126 )
          {
            v18 = ((char *)Src[1] - (char *)Src[0]) >> 2;
            if ( v18 == 0x3FFFFFFFFFFFFFFFLL )
              std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
                v126,
                v15,
                0x3FFFFFFFFFFFFFFFLL);
            v19 = v18 + 1;
            v20 = (signed __int64)((__int64)v126 - (unsigned __int64)Src[0]) >> 2;
            v21 = v20 >> 1;
            if ( v20 <= 0x3FFFFFFFFFFFFFFFLL - (v20 >> 1) )
            {
              v22 = v18 + 1;
              if ( v21 + v20 >= v19 )
                v22 = v21 + v20;
              if ( v22 > 0x3FFFFFFFFFFFFFFFLL )
                __scrt_throw_std_bad_array_new_length();
            }
            else
            {
              v22 = 0x3FFFFFFFFFFFFFFFLL;
            }
            _mm_lfence();
            v23 = std::_Allocate<16,std::_Default_allocate_traits>(4 * v22);
            v24 = (_DWORD *)v23 + v18;
            v25 = v24 + 1;
            v115 = Src;
            v117 = v22;
            *((_QWORD *)&v118 + 1) = v24 + 1;
            *v24 = (_DWORD)v103;
            *(_QWORD *)&v118 = v24;
            v26 = Src[0];
            v27 = v23;
            if ( v17 == Src[1] )
            {
              v28 = (char *)((char *)Src[1] - (char *)Src[0]);
            }
            else
            {
              memmove(v23, Src[0], (size_t)v17 - (unsigned __int64)Src[0]);
              *(_QWORD *)&v118 = v23;
              v28 = (char *)((char *)Src[1] - (char *)v17);
              v26 = v17;
              v27 = v25;
            }
            memmove(v27, v26, (size_t)v28);
            v116 = 0;
            std::vector<unsigned int>::_Change_array(Src, v23, v19, v22);
            std::vector<unsigned int>::_Reallocation_guard::~_Reallocation_guard(&v115);
            v5 = *(_DWORD *)v112;
            v11 = (unsigned int *)v110;
            v8 = v114;
          }
          else
          {
            *(_DWORD *)Src[1] = v12;
            Src[1] = (char *)Src[1] + 4;
          }
          std::vector<unsigned int>::_Insert_counted_range<unsigned int const *>(
            &v127,
            *((_QWORD *)&v127 + 1),
            *v14,
            (__int64)(v14[1] - *v14) >> 2);
        }
      }
      if ( *((_QWORD *)&v102 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v102 + 1));
      if ( ++v10 == v11 )
        break;
      v7 = *(_QWORD *)v109;
    }
  }
  if ( Src[0] != Src[1] )
  {
    v34 = std::vector<unsigned int>::vector<unsigned int>(&pExceptionObject, &v127);
    v35 = *(_QWORD *)v105;
    v36 = *(_QWORD *)v109;
    asg::SemanticIndex::DiskAnn::Index::PopulateNodeCache<std::vector<unsigned int>>(
      *(_QWORD *)v109,
      *(_QWORD *)v105,
      v34);
    *(_OWORD *)v123 = 0;
    v124 = 0;
    std::vector<unsigned int>::reserve(v123, (__int64)(*((_QWORD *)&v127 + 1) - v127) >> 2);
    v37 = (unsigned int *)*((_QWORD *)&v127 + 1);
    *(_QWORD *)v112 = *((_QWORD *)&v127 + 1);
    v38 = (unsigned int *)v127;
    if ( (_QWORD)v127 != *((_QWORD *)&v127 + 1) )
    {
      do
      {
        v39 = *v38;
        v102 = 0;
        asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(v36, &v102, *(_QWORD *)v105, v39);
        if ( *(_BYTE *)(v102 + 64) == 1 )
        {
          v41 = v123[1];
          if ( v123[1] == v124 )
          {
            v42 = ((char *)v123[1] - (char *)v123[0]) >> 2;
            if ( v42 == 0x3FFFFFFFFFFFFFFFLL )
              std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
                v124,
                v40,
                0x3FFFFFFFFFFFFFFFLL);
            v43 = ((char *)v124 - (char *)v123[0]) >> 2;
            v44 = v43 >> 1;
            if ( v43 <= 0x3FFFFFFFFFFFFFFFLL - (v43 >> 1) )
            {
              v45 = v42 + 1;
              if ( v44 + v43 >= v42 + 1 )
                v45 = v44 + v43;
              if ( v45 > 0x3FFFFFFFFFFFFFFFLL )
                __scrt_throw_std_bad_array_new_length();
            }
            else
            {
              v45 = 0x3FFFFFFFFFFFFFFFLL;
            }
            _mm_lfence();
            v46 = std::_Allocate<16,std::_Default_allocate_traits>(4 * v45);
            *((_DWORD *)v46 + v42) = v39;
            v47 = v123[0];
            v48 = (char *)v46;
            if ( v41 == v123[1] )
            {
              v49 = (char *)((char *)v123[1] - (char *)v123[0]);
            }
            else
            {
              memmove(v46, v123[0], (size_t)v41 - (unsigned __int64)v123[0]);
              v49 = (char *)((char *)v123[1] - (char *)v41);
              v48 = (char *)v46 + 4 * v42 + 4;
              v47 = v41;
            }
            memmove(v48, v47, (size_t)v49);
            std::vector<unsigned int>::_Change_array(v123, v46, v42 + 1, v45);
            v36 = *(_QWORD *)v109;
          }
          else
          {
            *(_DWORD *)v123[1] = v39;
            v123[1] = (char *)v123[1] + 4;
          }
          v37 = *(unsigned int **)v112;
        }
        v50 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
        if ( *((_QWORD *)&v102 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
            if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
          }
        }
        ++v38;
      }
      while ( v38 != v37 );
      v35 = *(_QWORD *)v105;
    }
    std::unordered_set<unsigned int>::unordered_set<unsigned int>(v137);
    std::unordered_set<unsigned int>::unordered_set<unsigned int>(v138);
    if ( v123[0] != v123[1] )
    {
      *(_OWORD *)Block = 0;
      v132 = 0;
      v133 = 0;
      v134 = 0;
      std::unordered_set<unsigned int>::unordered_set<unsigned int>(Block);
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::reserve(
        Block,
        v114 * (((char *)v123[1] - (char *)v123[0]) >> 2));
      ClearedNodeIdsForConsolidation = asg::SemanticIndex::DiskAnn::GraphStore::BatchGetClearedNodeIdsForConsolidation(
                                         *(_QWORD *)(v36 + 104),
                                         v121,
                                         *(_QWORD *)(v35 + 72));
      std::unordered_set<unsigned int>::operator=(v137, ClearedNodeIdsForConsolidation);
      std::unordered_set<unsigned int>::operator=(v138, ClearedNodeIdsForConsolidation + 64);
      asg::SemanticIndex::DiskAnn::ClearedNodeIds::~ClearedNodeIds((asg::SemanticIndex::DiskAnn::ClearedNodeIds *)v121);
      v52 = (unsigned int *)v123[0];
      for ( i = (unsigned int *)v123[1]; v52 != i; ++v52 )
      {
        v102 = 0;
        asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(v36, &v102, v35, *v52);
        v54 = *(_DWORD **)(v102 + 48);
        for ( j = *(_DWORD **)(v102 + 40); j != v54; ++j )
        {
          *(_DWORD *)v112 = *j;
          LODWORD(v103) = *(_DWORD *)v112;
          if ( !(unsigned __int8)std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::contains(
                                   v137,
                                   &v103)
            && !(unsigned __int8)std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::contains(
                                   v138,
                                   &v103) )
          {
            std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
              (__int64)Block,
              (__int64)v111,
              v112);
          }
        }
        v56 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
        if ( *((_QWORD *)&v102 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
            if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
          }
        }
      }
      *(_QWORD *)&v104 = &v115;
      LODWORD(v115) = Block[0];
      v116 = 0;
      v117 = 0;
      v57 = (char *)operator new(0x18u);
      *(_QWORD *)v57 = v57;
      *((_QWORD *)v57 + 1) = v57;
      v116 = v57;
      v118 = 0;
      v119 = 0;
      v120 = v134;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(
        &v118,
        (__int64)(v133 - *((_QWORD *)&v132 + 1)) >> 3,
        v57);
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>>(
        (__int64)&v115,
        *(_QWORD **)Block[1],
        (_QWORD *)Block[1]);
      asg::SemanticIndex::DiskAnn::Index::PopulateNodeCache<std::unordered_set<unsigned int>>(v36, v35, &v115);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v132 + 8);
      v58 = (_QWORD **)Block[1];
      **((_QWORD **)Block[1] + 1) = 0;
      v59 = *v58;
      if ( v59 )
      {
        do
        {
          v60 = (_QWORD *)*v59;
          operator delete(v59);
          v59 = v60;
        }
        while ( v60 );
      }
      operator delete(Block[1]);
    }
    v61 = (unsigned int *)Src[0];
    for ( k = (unsigned int *)Src[1]; v61 != k; ++v61 )
    {
      *(_OWORD *)v111 = 0;
      asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(v36, v111, v35, *v61);
      *(_OWORD *)v135 = 0;
      memset(v136, 0, sizeof(v136));
      *(_QWORD *)&v104 = v121;
      std::unordered_set<unsigned int>::unordered_set<unsigned int>(v121, v137);
      std::unordered_set<unsigned int>::unordered_set<unsigned int>(v122, v138);
      v63 = v111[0];
      asg::SemanticIndex::DiskAnn::Index::FindNewCandidateOutboundIds(
        v36,
        (int)v135,
        v35,
        (int)v111[0],
        (asg::SemanticIndex::DiskAnn::ClearedNodeIds *)v121);
      v133 = 0;
      v134 = 0;
      Block[0] = 0;
      Block[1] = 0;
      v132 = 0u;
      v64 = operator new(0x18u);
      *v64 = v64;
      v64[1] = v64;
      Block[1] = v64;
      *((_QWORD *)&v132 + 1) = 0;
      v133 = 0;
      *(_QWORD *)&v134 = 7;
      *((_QWORD *)&v134 + 1) = 8;
      LODWORD(Block[0]) = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(
        (char *)&v132 + 8,
        16,
        v64);
      v65 = *(_QWORD *)&v136[0] + 1LL;
      if ( *(_QWORD *)&v136[0] + 1LL < 0 )
        v66 = (float)(int)(v65 & 1 | (v65 >> 1)) + (float)(int)(v65 & 1 | (v65 >> 1));
      else
        v66 = (float)(int)v65;
      v67 = *(float *)Block;
      v68 = ceilf(v66 / *(float *)Block);
      v69 = 0;
      if ( v68 >= 9.223372e18 )
      {
        v68 = v68 - 9.223372e18;
        if ( v68 < 9.223372e18 )
          v69 = 0x8000000000000000uLL;
      }
      v70 = v69 + (unsigned int)(int)v68;
      if ( (__int64)v132 < 0 )
        v71 = (float)(v132 & 1 | ((unsigned __int64)v132 >> 1)) + (float)(v132 & 1 | ((unsigned __int64)v132 >> 1));
      else
        v71 = (float)(int)v132;
      v72 = ceilf(v71 / v67);
      v73 = 0;
      if ( v72 >= 9.223372e18 )
      {
        v72 = v72 - 9.223372e18;
        if ( v72 < 9.223372e18 )
          v73 = 0x8000000000000000uLL;
      }
      v74 = v73 + (unsigned int)(int)v72;
      if ( v74 < v70 )
        v74 = v70;
      if ( v74 > *((_QWORD *)&v134 + 1) )
      {
        _mm_lfence();
        std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Forced_rehash(
          Block,
          v74);
      }
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>>(
        (__int64)Block,
        *(_QWORD **)v135[1],
        (_QWORD *)v135[1]);
      std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::emplace<unsigned int const &>(
        (__int64)Block,
        (__int64)v112,
        (unsigned __int8 *)&v113);
      v75 = *(_BYTE *)(v36 + 65);
      if ( *((_BYTE *)v63 + 64) == 1 )
      {
        std::logic_error::logic_error(
          (std::logic_error *)&pExceptionObject,
          "Cannot get the embedding of a 'Cleared' node.");
        throw (std::logic_error *)&pExceptionObject;
      }
      v114 = 0;
      v76 = *((_QWORD *)v63 + 4);
      if ( v76 )
        _InterlockedIncrement((volatile signed __int32 *)(v76 + 8));
      v114 = *(_OWORD *)((char *)v63 + 24);
      LOBYTE(v96) = v75;
      asg::SemanticIndex::DiskAnn::Index::RebalanceNodeCore<std::unordered_set<unsigned int>>(
        v36,
        &v115,
        v35,
        &v114,
        Block,
        v96);
      v102 = 0;
      v77 = (const char *)v117;
      v117 = 0;
      v78 = v116;
      v116 = 0;
      v79 = v115;
      v115 = 0;
      v106 = v79;
      v107 = v78;
      v108 = v77;
      *(_QWORD *)&v104 = &v106;
      v80 = *((_BYTE *)v63 + 64);
      v108 = 0;
      v107 = 0;
      v106 = 0;
      pExceptionObject = (__int64)v79;
      v99 = v78;
      v100 = v77;
      v110 = 0;
      v81 = *((_QWORD *)v63 + 4);
      if ( v81 )
        _InterlockedIncrement((volatile signed __int32 *)(v81 + 8));
      v110 = *(_OWORD *)((char *)v63 + 24);
      asg::SemanticIndex::DiskAnn::GraphNode::Make(
        (unsigned int)&v102,
        *((_DWORD *)v63 + 4),
        (unsigned int)&v110,
        (unsigned int)&pExceptionObject,
        v80);
      v97 |= 3u;
      std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(&v106);
      std::vector<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor const>>::_Emplace_one_at_back<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor>>(
        &v129,
        &v102);
      v82 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
      if ( *((_QWORD *)&v102 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
          if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
        }
      }
      std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(&v115);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v132 + 8);
      v83 = (_QWORD **)Block[1];
      **((_QWORD **)Block[1] + 1) = 0;
      v84 = *v83;
      if ( v84 )
      {
        do
        {
          v85 = (_QWORD *)*v84;
          operator delete(v84);
          v84 = v85;
        }
        while ( v85 );
      }
      operator delete(Block[1]);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)v136 + 8);
      v86 = (_QWORD **)v135[1];
      **((_QWORD **)v135[1] + 1) = 0;
      v87 = *v86;
      if ( v87 )
      {
        do
        {
          v88 = (_QWORD *)*v87;
          operator delete(v87);
          v87 = v88;
        }
        while ( v88 );
      }
      operator delete(v135[1]);
      v89 = (volatile signed __int32 *)v111[1];
      if ( v111[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v111[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
          if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
        }
      }
    }
    asg::SemanticIndex::DiskAnn::ClearedNodeIds::~ClearedNodeIds((asg::SemanticIndex::DiskAnn::ClearedNodeIds *)v137);
    v90 = v123[0];
    if ( v123[0] )
    {
      if ( (((char *)v124 - (char *)v123[0]) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
      {
        _mm_lfence();
        v90 = (void *)*((_QWORD *)v123[0] - 1);
        if ( (unsigned __int64)((char *)v123[0] - (char *)v90 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v90);
    }
  }
  v91 = *(_QWORD *)v105;
  v92 = *(_QWORD *)v109;
  asg::SemanticIndex::DiskAnn::Index::BatchUpdateOutbounds<std::vector<std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>(
    *(__int64 *)v109,
    *(__int64 **)v105,
    (__int128 **)&v129);
  asg::SemanticIndex::DiskAnn::GraphStore::IncrementPrunedNodeCount(
    *(asg::SemanticIndex::DiskAnn::GraphStore **)(v92 + 104),
    *(struct asg::Sqlite::DbTransaction **)(v91 + 72),
    ((char *)Src[1] - (char *)Src[0]) >> 2);
  v93 = (void *)v127;
  if ( (_QWORD)v127 )
  {
    if ( ((v128 - (_QWORD)v127) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
    {
      _mm_lfence();
      v93 = *(void **)(v127 - 8);
      if ( (unsigned __int64)(v127 - (_QWORD)v93 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v93);
    v127 = 0;
    v128 = 0;
  }
  v94 = Src[0];
  if ( Src[0] )
  {
    if ( (((unsigned __int64)v126 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
    {
      _mm_lfence();
      v94 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v94 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v94);
    *(_OWORD *)Src = 0;
    v126 = 0;
  }
  if ( (_QWORD)v129 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<asg::SemanticRegistry::SourceVersion const>>>(
      v129,
      *((__int64 *)&v129 + 1));
    v95 = (void *)v129;
    if ( ((v130 - (_QWORD)v129) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      _mm_lfence();
      v95 = *(void **)(v129 - 8);
      if ( (unsigned __int64)(v129 - (_QWORD)v95 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v95);
    v129 = 0;
    v130 = 0;
  }
  asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v139);
}

```

## disassembly

```asm
0x1801add80  mov     rax, rsp
0x1801add83  push    rbp
0x1801add84  push    rbx
0x1801add85  push    rsi
0x1801add86  push    rdi
0x1801add87  push    r12
0x1801add89  push    r13
0x1801add8b  push    r14
0x1801add8d  push    r15
0x1801add8f  lea     rbp, [rax-2F8h]
0x1801add96  sub     rsp, 3B8h
0x1801add9d  movaps  xmmword ptr [rax-58h], xmm6
0x1801adda1  movaps  xmmword ptr [rax-68h], xmm7
0x1801adda5  mov     rax, cs:__security_cookie
0x1801addac  xor     rax, rsp
0x1801addaf  mov     [rbp+2F0h+var_70], rax
0x1801addb6  mov     rbx, r9
0x1801addb9  mov     esi, r8d
0x1801addbc  mov     dword ptr [rbp+2F0h+var_318], r8d
0x1801addc0  mov     rdi, rdx
0x1801addc3  mov     qword ptr [rbp+2F0h+var_360], rdx
0x1801addc7  mov     r15, rcx
0x1801addca  mov     qword ptr [rbp+2F0h+var_340], rcx
0x1801addce  mov     [rbp+2F0h+var_308], r8d
0x1801addd2  mov     dword ptr [rsp+30h], 0
0x1801addda  mov     r8d, 4
0x1801adde0  mov     rdx, [rdx+20h]
0x1801adde4  lea     rcx, [rbp+2F0h+var_D0]
0x1801addeb  call    asg__SemanticIndex__DiskAnn__Checkpoint
0x1801addf0  nop
0x1801addf1  mov     rax, [rbx+8]
0x1801addf5  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1801addfa  cmp     [rbx], rax
0x1801addfd  jz      loc_1801AECAF
0x1801ade03  mov     r12, [r15+18h]
0x1801ade07  add     r12, [r15+10h]
0x1801ade0b  mov     qword ptr [rbp+2F0h+var_300], r12
0x1801ade0f  mov     rdx, rbx
0x1801ade12  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@AEBV01@@Z; std::vector<uint>::vector<uint>(std::vector<uint> const &)
0x1801ade17  mov     r8, rax
0x1801ade1a  mov     rdx, rdi
0x1801ade1d  mov     rcx, r15
0x1801ade20  call    ??$PopulateNodeCache@V?$vector@IV?$allocator@I@std@@@std@@@Index@DiskAnn@SemanticIndex@asg@@AEBAXAEAVOperationState@123@V?$vector@IV?$allocator@I@std@@@std@@@Z; asg::SemanticIndex::DiskAnn::Index::PopulateNodeCache<std::vector<uint>>(asg::SemanticIndex::DiskAnn::OperationState &,std::vector<uint>)
0x1801ade25  xorps   xmm1, xmm1
0x1801ade28  movdqu  [rbp+2F0h+var_1E8], xmm1
0x1801ade30  xor     edi, edi
0x1801ade32  mov     [rbp+2F0h+var_1D8], rdi
0x1801ade39  mov     rdx, [rbx+8]
0x1801ade3d  sub     rdx, [rbx]
0x1801ade40  sar     rdx, 2
0x1801ade44  lea     rcx, [rbp+2F0h+var_1E8]
0x1801ade4b  call    ?reserve@?$vector@V?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@V?$allocator@V?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>::reserve(unsigned __int64)
0x1801ade50  xorps   xmm1, xmm1
0x1801ade53  movdqu  xmmword ptr [rbp+2F0h+Src], xmm1
0x1801ade5b  mov     [rbp+2F0h+var_208], rdi
0x1801ade62  movdqu  [rbp+2F0h+var_200], xmm1
0x1801ade6a  mov     [rbp+2F0h+var_1F0], rdi
0x1801ade71  mov     r13, [rbx]
0x1801ade74  mov     r14, [rbx+8]
0x1801ade78  mov     qword ptr [rbp+2F0h+var_338], r14
0x1801ade7c  cmp     r13, r14
0x1801ade7f  jz      loc_1801AE17F
0x1801ade85  nop     word ptr [rax+rax+00000000h]
0x1801ade90  mov     edi, [r13+0]
0x1801ade94  mov     dword ptr [rsp+3F0h+var_378], edi
0x1801ade98  xorps   xmm0, xmm0
0x1801ade9b  movups  [rsp+3F0h+var_390+8], xmm0
0x1801adea0  mov     r9d, edi
0x1801adea3  mov     r8, qword ptr [rbp+2F0h+var_360]
0x1801adea7  lea     rdx, [rsp+3F0h+var_390+8]
0x1801adeac  mov     rcx, r15
0x1801adeaf  call    ?GetGraphNodeAndUpdateCache@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@I@Z; asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(asg::SemanticIndex::DiskAnn::OperationState &,uint)
0x1801adeb4  nop
0x1801adeb5  mov     rbx, qword ptr [rsp+3F0h+var_390+8]
0x1801adeba  cmp     byte ptr [rbx+40h], 1
0x1801adebe  jz      loc_1801AECE9
0x1801adec4  lea     r15, [rbx+28h]
0x1801adec8  mov     rcx, [r15+8]
0x1801adecc  mov     rdx, [r15]
0x1801adecf  mov     rax, rdx
0x1801aded2  cmp     rdx, rcx
0x1801aded5  jz      short loc_1801ADEEF
0x1801aded7  cmp     [rax], esi
0x1801aded9  jz      short loc_1801ADEE6
0x1801adedb  add     rax, 4
0x1801adedf  cmp     rax, rcx
0x1801adee2  jnz     short loc_1801ADED7
0x1801adee4  jmp     short loc_1801ADEEF
0x1801adee6  cmp     rax, rcx
0x1801adee9  jnz     loc_1801AE049
0x1801adeef  sub     rcx, rdx
0x1801adef2  sar     rcx, 2
0x1801adef6  inc     rcx
0x1801adef9  cmp     rcx, r12
0x1801adefc  jbe     loc_1801AE070
0x1801adf02  mov     rbx, [rbp+2F0h+Src+8]
0x1801adf09  mov     rcx, [rbp+2F0h+var_208]
0x1801adf10  cmp     rbx, rcx
0x1801adf13  jz      short loc_1801ADF24
0x1801adf15  mov     [rbx], edi
0x1801adf17  add     [rbp+2F0h+Src+8], 4
0x1801adf1f  jmp     loc_1801AE028
0x1801adf24  mov     rdi, rbx
0x1801adf27  mov     rax, [rbp+2F0h+Src]
0x1801adf2e  sub     rdi, rax
0x1801adf31  sar     rdi, 2
0x1801adf35  mov     r8, 3FFFFFFFFFFFFFFFh
0x1801adf3f  cmp     rdi, r8
0x1801adf42  jz      loc_1801AECE3
0x1801adf48  lea     r12, [rdi+1]
0x1801adf4c  sub     rcx, rax
0x1801adf4f  sar     rcx, 2
0x1801adf53  mov     rdx, rcx
0x1801adf56  shr     rdx, 1
0x1801adf59  mov     rax, r8
0x1801adf5c  sub     rax, rdx
0x1801adf5f  cmp     rcx, rax
0x1801adf62  jbe     short loc_1801ADF69
0x1801adf64  mov     rsi, r8
0x1801adf67  jmp     short loc_1801ADF80
0x1801adf69  lea     rax, [rdx+rcx]
0x1801adf6d  mov     rsi, r12
0x1801adf70  cmp     rax, r12
0x1801adf73  cmovnb  rsi, rax
0x1801adf77  cmp     rsi, r8
0x1801adf7a  ja      loc_1801AECDD
0x1801adf80  lfence
0x1801adf83  lea     rcx, ds:0[rsi*4]
0x1801adf8b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801adf90  mov     r14, rax
0x1801adf93  lea     rcx, [rax+rdi*4]
0x1801adf97  lea     rdi, [rcx+4]
0x1801adf9b  lea     rax, [rbp+2F0h+Src]
0x1801adfa2  mov     [rbp+2F0h+var_2F0], rax
0x1801adfa6  mov     [rbp+2F0h+var_2E0], rsi
0x1801adfaa  mov     qword ptr [rbp+2F0h+var_2D8+8], rdi
0x1801adfae  mov     eax, dword ptr [rsp+3F0h+var_378]
0x1801adfb2  mov     [rcx], eax
0x1801adfb4  mov     qword ptr [rbp+2F0h+var_2D8], rcx
0x1801adfb8  mov     r8, [rbp+2F0h+Src+8]
0x1801adfbf  mov     rdx, [rbp+2F0h+Src]; Src
0x1801adfc6  mov     rcx, r14; void *
0x1801adfc9  cmp     rbx, r8
0x1801adfcc  jnz     short loc_1801ADFD3
0x1801adfce  sub     r8, rdx
0x1801adfd1  jmp     short loc_1801ADFF2
0x1801adfd3  mov     r8, rbx
0x1801adfd6  sub     r8, rdx; Size
0x1801adfd9  call    memmove
0x1801adfde  mov     qword ptr [rbp+2F0h+var_2D8], r14
0x1801adfe2  mov     r8, [rbp+2F0h+Src+8]
0x1801adfe9  sub     r8, rbx; Size
0x1801adfec  mov     rdx, rbx; Src
0x1801adfef  mov     rcx, rdi; void *
0x1801adff2  call    memmove
0x1801adff7  mov     [rbp+2F0h+var_2E8], 0
0x1801adfff  mov     r9, rsi
0x1801ae002  mov     r8, r12
0x1801ae005  mov     rdx, r14
0x1801ae008  lea     rcx, [rbp+2F0h+Src]
0x1801ae00f  call    ?_Change_array@?$vector@IV?$allocator@I@std@@@std@@AEAAXQEAI_K1@Z; std::vector<uint>::_Change_array(uint * const,unsigned __int64,unsigned __int64)
0x1801ae014  lea     rcx, [rbp+2F0h+var_2F0]
0x1801ae018  call    ??1_Reallocation_guard@?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::_Reallocation_guard::~_Reallocation_guard(void)
0x1801ae01d  mov     esi, dword ptr [rbp+2F0h+var_318]
0x1801ae020  mov     r14, qword ptr [rbp+2F0h+var_338]
0x1801ae024  mov     r12, qword ptr [rbp+2F0h+var_300]
0x1801ae028  mov     r8, [r15]
0x1801ae02b  mov     r9, [r15+8]
0x1801ae02f  sub     r9, r8
0x1801ae032  sar     r9, 2
0x1801ae036  mov     rdx, qword ptr [rbp+2F0h+var_200+8]
0x1801ae03d  lea     rcx, [rbp+2F0h+var_200]
0x1801ae044  call    ??$_Insert_counted_range@PEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@1@PEBI_K@Z; std::vector<uint>::_Insert_counted_range<uint const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uint>>>,uint const *,unsigned __int64)
0x1801ae049  xor     edi, edi
0x1801ae04b  mov     rcx, [rsp+3F0h+var_380]; this
0x1801ae050  test    rcx, rcx
0x1801ae053  jz      short loc_1801AE05A
0x1801ae055  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801ae05a  add     r13, 4
0x1801ae05e  cmp     r13, r14
0x1801ae061  jz      loc_1801AE17F
0x1801ae067  mov     r15, qword ptr [rbp+2F0h+var_340]
0x1801ae06b  jmp     loc_1801ADE90
0x1801ae070  xorps   xmm0, xmm0
0x1801ae073  xor     eax, eax
0x1801ae075  movups  xmmword ptr [rbp+2F0h+var_230], xmm0
0x1801ae07c  mov     [rbp+2F0h+var_220], rax
0x1801ae083  mov     r9d, esi
0x1801ae086  mov     r8, r15
0x1801ae089  lea     rdx, [rbp+2F0h+var_230]
0x1801ae090  lea     rcx, [rsp+3F0h+var_390]
0x1801ae095  call    _asg__SemanticIndex__DiskAnn__Index__AddReverseLink____2____lambda_1___operator__
0x1801ae09a  nop
0x1801ae09b  xorps   xmm0, xmm0
0x1801ae09e  movups  xmmword ptr [rbp+2F0h+var_328], xmm0
0x1801ae0a2  mov     rdx, [rbp+2F0h+var_220]
0x1801ae0a9  xor     edi, edi
0x1801ae0ab  mov     [rbp+2F0h+var_220], rdi
0x1801ae0b2  mov     rcx, [rbp+2F0h+var_230+8]
0x1801ae0b9  mov     [rbp+2F0h+var_230+8], rdi
0x1801ae0c0  mov     rax, [rbp+2F0h+var_230]
0x1801ae0c7  mov     [rbp+2F0h+var_230], rdi
0x1801ae0ce  mov     [rbp+2F0h+var_358], rax
0x1801ae0d2  mov     [rbp+2F0h+var_350], rcx
0x1801ae0d6  mov     [rbp+2F0h+var_348], rdx
0x1801ae0da  lea     r8, [rbp+2F0h+var_358]
0x1801ae0de  mov     [rsp+3F0h+var_378], r8
0x1801ae0e3  movzx   r8d, byte ptr [rbx+40h]
0x1801ae0e8  mov     [rbp+2F0h+var_348], rdi
0x1801ae0ec  mov     [rbp+2F0h+var_350], rdi
0x1801ae0f0  mov     [rbp+2F0h+var_358], rdi
0x1801ae0f4  mov     [rsp+3F0h+pExceptionObject], rax
0x1801ae0f9  mov     [rsp+3F0h+var_3A8], rcx
0x1801ae0fe  mov     [rsp+3F0h+var_3A0], rdx
0x1801ae103  movdqu  [rbp+2F0h+var_370], xmm0
0x1801ae108  mov     rax, [rbx+20h]
0x1801ae10c  test    rax, rax
0x1801ae10f  jz      short loc_1801AE115
0x1801ae111  lock inc dword ptr [rax+8]
0x1801ae115  mov     rax, [rbx+18h]
0x1801ae119  mov     qword ptr [rbp+2F0h+var_370], rax
0x1801ae11d  mov     rax, [rbx+20h]
0x1801ae121  mov     qword ptr [rbp+2F0h+var_370+8], rax
0x1801ae125  mov     byte ptr [rsp+3F0h+Reserved], r8b
0x1801ae12a  lea     r9, [rsp+3F0h+pExceptionObject]
0x1801ae12f  lea     r8, [rbp+2F0h+var_370]
0x1801ae133  mov     edx, [rbx+10h]
0x1801ae136  lea     rcx, [rbp+2F0h+var_328]
0x1801ae13a  call    ?Make@GraphNode@DiskAnn@SemanticIndex@asg@@SA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@IV?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@6@V?$vector@IV?$allocator@I@std@@@6@W4NodeState@234@@Z; asg::SemanticIndex::DiskAnn::GraphNode::Make(uint,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,std::vector<uint>,asg::SemanticIndex::DiskAnn::NodeState)
0x1801ae13f  or      dword ptr [rsp+30h], 4
0x1801ae144  lea     rcx, [rbp+2F0h+var_358]
0x1801ae148  call    ?_Tidy@?$vector@W4ModelClass@SemanticRegistry@asg@@V?$allocator@W4ModelClass@SemanticRegistry@asg@@@std@@@std@@AEAAXXZ; std::vector<asg::SemanticRegistry::ModelClass>::_Tidy(void)
0x1801ae14d  nop
0x1801ae14e  lea     rdx, [rbp+2F0h+var_328]
0x1801ae152  lea     rcx, [rbp+2F0h+var_1E8]
0x1801ae159  call    ??$_Emplace_one_at_back@V?$shared_ptr@UModelDescriptor@SemanticRegistry@asg@@@std@@@?$vector@V?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@std@@V?$allocator@V?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@1@$$QEAV?$shared_ptr@UModelDescriptor@SemanticRegistry@asg@@@1@@Z; std::vector<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor const>>::_Emplace_one_at_back<std::shared_ptr<asg::SemanticRegistry::ModelDescriptor>>(std::shared_ptr<asg::SemanticRegistry::ModelDescriptor> &&)
0x1801ae15e  nop
0x1801ae15f  mov     rcx, [rbp+2F0h+var_328+8]; this
0x1801ae163  test    rcx, rcx
0x1801ae166  jz      short loc_1801AE16E
0x1801ae168  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801ae16d  nop
0x1801ae16e  lea     rcx, [rbp+2F0h+var_230]
0x1801ae175  call    ?_Tidy@?$vector@W4ModelClass@SemanticRegistry@asg@@V?$allocator@W4ModelClass@SemanticRegistry@asg@@@std@@@std@@AEAAXXZ; std::vector<asg::SemanticRegistry::ModelClass>::_Tidy(void)
0x1801ae17a  jmp     loc_1801AE04B
0x1801ae17f  mov     rax, [rbp+2F0h+Src+8]
0x1801ae186  cmp     [rbp+2F0h+Src], rax
0x1801ae18d  jz      loc_1801AEAEE
0x1801ae193  lea     rdx, [rbp+2F0h+var_200]
0x1801ae19a  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1801ae19f  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@AEBV01@@Z; std::vector<uint>::vector<uint>(std::vector<uint> const &)
0x1801ae1a4  mov     r8, rax
0x1801ae1a7  mov     r12, qword ptr [rbp+2F0h+var_360]
0x1801ae1ab  mov     rdx, r12
0x1801ae1ae  mov     r13, qword ptr [rbp+2F0h+var_340]
0x1801ae1b2  mov     rcx, r13
0x1801ae1b5  call    ??$PopulateNodeCache@V?$vector@IV?$allocator@I@std@@@std@@@Index@DiskAnn@SemanticIndex@asg@@AEBAXAEAVOperationState@123@V?$vector@IV?$allocator@I@std@@@std@@@Z; asg::SemanticIndex::DiskAnn::Index::PopulateNodeCache<std::vector<uint>>(asg::SemanticIndex::DiskAnn::OperationState &,std::vector<uint>)
0x1801ae1ba  xorps   xmm1, xmm1
0x1801ae1bd  movdqu  xmmword ptr [rbp+2F0h+var_230], xmm1
0x1801ae1c5  mov     [rbp+2F0h+var_220], rdi
0x1801ae1cc  mov     rdx, qword ptr [rbp+2F0h+var_200+8]
0x1801ae1d3  sub     rdx, qword ptr [rbp+2F0h+var_200]
0x1801ae1da  sar     rdx, 2
0x1801ae1de  lea     rcx, [rbp+2F0h+var_230]
0x1801ae1e5  call    ?reserve@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::reserve(unsigned __int64)
0x1801ae1ea  mov     r15, qword ptr [rbp+2F0h+var_200]
0x1801ae1f1  mov     rdi, qword ptr [rbp+2F0h+var_200+8]
0x1801ae1f8  mov     qword ptr [rbp+2F0h+var_318], rdi
0x1801ae1fc  cmp     r15, rdi
0x1801ae1ff  jz      loc_1801AE37C
0x1801ae205  nop     word ptr [rax+rax+00000000h]
0x1801ae210  mov     r12d, [r15]
0x1801ae213  xorps   xmm0, xmm0
0x1801ae216  movups  [rsp+3F0h+var_390+8], xmm0
0x1801ae21b  mov     r9d, r12d
0x1801ae21e  mov     r8, qword ptr [rbp+2F0h+var_360]
0x1801ae222  lea     rdx, [rsp+3F0h+var_390+8]
0x1801ae227  mov     rcx, r13
0x1801ae22a  call    ?GetGraphNodeAndUpdateCache@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@I@Z; asg::SemanticIndex::DiskAnn::Index::GetGraphNodeAndUpdateCache(asg::SemanticIndex::DiskAnn::OperationState &,uint)
0x1801ae22f  nop
0x1801ae230  mov     rax, qword ptr [rsp+3F0h+var_390+8]
0x1801ae235  cmp     byte ptr [rax+40h], 1
0x1801ae239  jnz     loc_1801AE332
0x1801ae23f  mov     rdi, [rbp+2F0h+var_230+8]
0x1801ae246  mov     rcx, [rbp+2F0h+var_220]
0x1801ae24d  cmp     rdi, rcx
0x1801ae250  jz      short loc_1801AE262
0x1801ae252  mov     [rdi], r12d
0x1801ae255  add     [rbp+2F0h+var_230+8], 4
0x1801ae25d  jmp     loc_1801AE32E
0x1801ae262  mov     rbx, rdi
0x1801ae265  mov     rax, [rbp+2F0h+var_230]
0x1801ae26c  sub     rbx, rax
0x1801ae26f  sar     rbx, 2
0x1801ae273  mov     r8, 3FFFFFFFFFFFFFFFh
0x1801ae27d  cmp     rbx, r8
0x1801ae280  jz      loc_1801AED22
0x1801ae286  lea     r13, [rbx+1]
0x1801ae28a  sub     rcx, rax
0x1801ae28d  sar     rcx, 2
  ... truncated ...
```
