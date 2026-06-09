# asg::SemanticIndex::SemanticIndexStore::AddOrReplace(asg::Guid,std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>)

- ea: `0x18018e2c0`
- end: `0x18018f430`
- name: `?AddOrReplace@SemanticIndexStore@SemanticIndex@asg@@QEAAXUGuid@3@V?$span@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@@Z`
- size: `4464`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `56`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002cdb0`
- `0x18002d560`

## callees

- `0x180004140`
- `0x180004920`
- `0x180006220`
- `0x180006410`
- `0x180007a00`
- `0x180007a80`
- `0x180007a90`
- `0x180007b20`
- `0x180007ba0`
- `0x180007e70`
- `0x1800085c0`
- `0x180008970`
- `0x18000acb0`
- `0x180017620`
- `0x180017f70`
- `0x18002b900`
- `0x180038620`
- `0x18003db20`
- `0x1800450e0`
- `0x1800476a0`
- `0x180078ed0`
- `0x18007c250`
- `0x18007c5a0`
- `0x18017e240`
- `0x18017ee70`
- `0x18017fa90`
- `0x180180080`
- `0x1801831c0`
- `0x180184bc0`
- `0x180185d00`
- `0x180187fb0`
- `0x180189630`
- `0x180189970`
- `0x18018a250`
- `0x18018a730`
- `0x18018b070`
- `0x18018cc60`
- `0x18018e2c0`
- `0x18018ffd0`
- `0x180190d40`
- `0x180192380`
- `0x180192ff0`
- `0x180194d50`
- `0x180197d50`
- `0x180198080`
- `0x180199e30`
- `0x18019a370`
- `0x18019a460`
- `0x1801c3f10`
- `0x1801d1370`

## string_xrefs

- `0x18018f2d0`: `update.Embedding is null`
- `0x18018f278`: `Updates are from both the current and previous vector spaces`
- `0x18018ea83`: `void __cdecl asg::SemanticIndex::SemanticIndexStore::AddOrReplace(struct asg::Guid,class std::span<struct asg::SemanticIndex::ItemRegionEmbeddingUpdate const ,-1>)`
- `0x18018eda7`: `INSERT INTO %ls (embedding_id, item_id, region_id, ordinal, metadata_json, embedding_altstore) VALUES (:emb, :id, :region, :order, :metadata, :embedding)`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
void __fastcall asg::SemanticIndex::SemanticIndexStore::AddOrReplace(_QWORD *a1, __int128 *a2, wchar_t **a3)
{
  _QWORD *v4; // rsi
  _QWORD *v5; // rax
  wchar_t *v6; // rbx
  __int64 *v7; // rax
  asg::SemanticIndex::ItemRegionEmbeddingUpdate *v8; // rdi
  asg::SemanticIndex::ItemRegionEmbeddingUpdate *v9; // rbx
  _QWORD *v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  asg::Sqlite::DbTransaction **v14; // rax
  wchar_t *v15; // r13
  char v16; // r14
  char v17; // bl
  wchar_t *v18; // rdi
  __int64 v19; // r12
  asg::Sqlite::DbTransaction *v20; // rdx
  asg::Sqlite::DbTransaction *v21; // rax
  __int64 v22; // r9
  unsigned __int64 i; // rcx
  _QWORD *v24; // rax
  __int64 *v25; // rbx
  __int64 v26; // rax
  asg::SemanticPipelines *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rax
  char v30; // bl
  __int64 v31; // rax
  bool v32; // bl
  __int128 *v33; // rdi
  int CurrentTableGroup; // eax
  asg::Sqlite::DbTransaction *v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  int v38; // r12d
  wchar_t *v39; // rdi
  __int64 v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // r14
  int v43; // eax
  asg::SemanticRegistry::IVectorData *v44; // rbx
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // rdi
  __int64 v48; // rax
  _QWORD *v49; // rdi
  unsigned __int64 v50; // rsi
  int v51; // eax
  asg::SemanticRegistry::IVectorData *v52; // rbx
  int v53; // eax
  __int64 v54; // rdi
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rbx
  __int64 v57; // rcx
  asg::Sqlite::DbTransaction *v58; // r15
  wchar_t *v59; // r14
  size_t v60; // rdi
  __int64 v61; // rcx
  unsigned __int64 j; // rdx
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // rsi
  __int64 v66; // rcx
  __int64 v67; // rax
  __int128 *v68; // r8
  _QWORD *v69; // rax
  _QWORD *v70; // rax
  _QWORD *v71; // rdx
  void *v72; // rcx
  void *v73; // rcx
  unsigned __int64 v74; // rdx
  void *v75; // rcx
  void *v76; // rcx
  volatile signed __int32 *v77; // rbx
  volatile signed __int32 *v78; // rbx
  asg::SemanticIndex::ItemRegionEmbeddingUpdate *v79; // r8
  char v80; // [rsp+30h] [rbp-5A8h]
  int v81; // [rsp+34h] [rbp-5A4h]
  __int128 v82; // [rsp+40h] [rbp-598h] BYREF
  const char *v83; // [rsp+50h] [rbp-588h]
  __int128 v84; // [rsp+60h] [rbp-578h] BYREF
  const char *v85; // [rsp+70h] [rbp-568h]
  _QWORD *v86; // [rsp+80h] [rbp-558h]
  __int128 v87; // [rsp+90h] [rbp-548h] BYREF
  wchar_t *S1; // [rsp+A0h] [rbp-538h]
  __int128 v89; // [rsp+B0h] [rbp-528h] BYREF
  __int128 *v90; // [rsp+C0h] [rbp-518h]
  __int64 v91; // [rsp+C8h] [rbp-510h] BYREF
  __int128 v92; // [rsp+D0h] [rbp-508h] BYREF
  _QWORD v93[2]; // [rsp+E0h] [rbp-4F8h] BYREF
  __int64 v94; // [rsp+F0h] [rbp-4E8h]
  unsigned __int64 v95; // [rsp+F8h] [rbp-4E0h]
  __int128 v96; // [rsp+100h] [rbp-4D8h] BYREF
  void *Block[3]; // [rsp+110h] [rbp-4C8h] BYREF
  unsigned __int64 v98; // [rsp+128h] [rbp-4B0h]
  _QWORD *v99; // [rsp+130h] [rbp-4A8h] BYREF
  unsigned __int64 v100; // [rsp+138h] [rbp-4A0h]
  char v101; // [rsp+170h] [rbp-468h]
  __int128 v102; // [rsp+178h] [rbp-460h]
  _BYTE v103[32]; // [rsp+190h] [rbp-448h] BYREF
  const char *v104; // [rsp+1B0h] [rbp-428h] BYREF
  __int128 v105; // [rsp+1B8h] [rbp-420h]
  char v106; // [rsp+1F8h] [rbp-3E0h]
  const char *v107; // [rsp+200h] [rbp-3D8h]
  __int128 v108; // [rsp+208h] [rbp-3D0h]
  char v109; // [rsp+248h] [rbp-390h]
  _QWORD v110[9]; // [rsp+250h] [rbp-388h] BYREF
  char v111; // [rsp+298h] [rbp-340h]
  const char *v112; // [rsp+2A0h] [rbp-338h]
  int v113; // [rsp+2A8h] [rbp-330h]
  char v114; // [rsp+2E8h] [rbp-2F0h]
  const char *v115; // [rsp+2F0h] [rbp-2E8h]
  char v116[72]; // [rsp+2F8h] [rbp-2E0h] BYREF
  const char *v117; // [rsp+340h] [rbp-298h]
  char v118[72]; // [rsp+348h] [rbp-290h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+390h] [rbp-248h] BYREF
  _BYTE v120[64]; // [rsp+3D0h] [rbp-208h] BYREF
  asg::Sqlite::DbTransaction *v121[2]; // [rsp+410h] [rbp-1C8h] BYREF
  asg::SemanticIndex::ItemRegionEmbeddingUpdate *v122[2]; // [rsp+420h] [rbp-1B8h] BYREF
  __int64 v123; // [rsp+430h] [rbp-1A8h]
  __int128 v124; // [rsp+438h] [rbp-1A0h] BYREF
  unsigned __int64 v125; // [rsp+448h] [rbp-190h]
  unsigned __int64 v126; // [rsp+450h] [rbp-188h]
  __int128 v127; // [rsp+458h] [rbp-180h]
  __int64 v128; // [rsp+468h] [rbp-170h]
  __int64 v129; // [rsp+470h] [rbp-168h] BYREF
  __int64 *v130; // [rsp+478h] [rbp-160h] BYREF
  _QWORD v131[5]; // [rsp+488h] [rbp-150h] BYREF
  _QWORD v132[4]; // [rsp+4B0h] [rbp-128h] BYREF
  char v133; // [rsp+4D0h] [rbp-108h]
  _QWORD v134[7]; // [rsp+4F0h] [rbp-E8h] BYREF
  _QWORD *v135; // [rsp+528h] [rbp-B0h]
  char v136; // [rsp+530h] [rbp-A8h]
  _QWORD v137[7]; // [rsp+540h] [rbp-98h] BYREF
  _QWORD *v138; // [rsp+578h] [rbp-60h]
  char v139; // [rsp+580h] [rbp-58h]
  __int128 v140; // [rsp+590h] [rbp-48h]

  v90 = a2;
  v4 = a1;
  v86 = a1;
  v81 = 0;
  std::u8string_view::__autoclassinit2(v122, 24);
  *(_OWORD *)v122 = 0;
  v123 = 0;
  v5 = (_QWORD *)std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::end(a3, &v89);
  v6 = *a3;
  if ( (unsigned __int8)std::any_of_std::_Span_iterator_asg::SemanticIndex::ItemRegionEmbeddingUpdate_const____asg::SemanticIndex::SemanticIndexStore::AddOrReplace_::_3_::_lambda_1___(
                          *a3,
                          *v5,
                          v4) )
  {
    v7 = (__int64 *)std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::end(a3, &v89);
    std::vector<asg::SemanticIndex::ItemRegionEmbeddingUpdate>::insert<std::_Span_iterator<asg::SemanticIndex::ItemRegionEmbeddingUpdate const>,0>(
      (unsigned int)v122,
      (unsigned int)&v91,
      v122[1],
      (_DWORD)v6,
      *v7);
    v8 = v122[1];
    v9 = v122[0];
    if ( v122[0] != v122[1] )
    {
      v10 = (_QWORD *)((char *)v122[0] + 56);
      do
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
        asg::SemanticRegistry::ValidateEmbeddingElementType(v11);
        v12 = asg::SemanticIndex::SemanticIndexStore::ConvertIfNecessary(v4, &v84, v10);
        std::shared_ptr<asg::SemanticIndex::DiskAnn::QueryContinuationData const>::operator=(v10, v12);
        std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(&v84);
        v10 += 9;
      }
      while ( v10 - 7 != (_QWORD *)v8 );
      v9 = v122[0];
    }
    v13 = std::vector<asg::SemanticIndex::ItemRegionEmbeddingUpdate>::size(v122);
    v14 = (asg::Sqlite::DbTransaction **)std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>(
                                           &v82,
                                           (__int64)v9,
                                           v13);
    v121[0] = *v14;
    v121[1] = v14[1];
    *(_OWORD *)a3 = *(_OWORD *)v121;
  }
  std::u8string_view::__autoclassinit2(&v129, 64);
  std::unordered_map<std::u16string_view,std::basic_string<char8_t>>::unordered_map<std::u16string_view,std::basic_string<char8_t>>(&v129);
  v15 = a3[1];
  std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::reserve(
    &v129,
    v15);
  v16 = 0;
  v17 = 0;
  v80 = 0;
  S1 = *a3;
  v18 = S1;
  v19 = std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::_Unchecked_end(a3);
  if ( v18 != (wchar_t *)v19 )
  {
    do
    {
      v20 = (asg::Sqlite::DbTransaction *)v18;
      if ( *((_QWORD *)v18 + 3) > 7u )
        v20 = *(asg::Sqlite::DbTransaction **)v18;
      v21 = (asg::Sqlite::DbTransaction *)*((_QWORD *)v18 + 2);
      v121[0] = v20;
      v121[1] = v21;
      v22 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 2 * (__int64)v21; ++i )
        v22 = 0x100000001B3LL * (*((unsigned __int8 *)v20 + i) ^ (unsigned __int64)v22);
      v24 = std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::_Find_last<std::u16string_view>(
              &v129,
              &v82,
              (__int64)v121,
              v22);
      v25 = v130;
      if ( v24[1] )
        v25 = (__int64 *)v24[1];
      if ( v25 == v130 )
      {
        v84 = *(_OWORD *)asg::SemanticPipelines::RegionId::operator std::u16string_view(v18, &v92);
        v26 = asg::utf16To8(Block, &v84);
        std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::emplace_hint<asg::SemanticPipelines::RegionId const &,std::basic_string<char8_t>>(
          &v129,
          &v89,
          v25,
          v18,
          v26);
        std::basic_string<char8_t>::_Tidy_deallocate(Block);
      }
      v27 = (asg::SemanticPipelines *)*((_QWORD *)v18 + 7);
      if ( !v27 )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)v103, "update.Embedding is null");
        throw (std::invalid_argument *)v103;
      }
      asg::SemanticIndex::ValidateEmbedding(v27);
      v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v18 + 7) + 32LL))(*((_QWORD *)v18 + 7));
      v29 = asg::SemanticIndex::DbDiskAnnEmbeddingStore::VectorSpace(v86[22], &v104);
      v30 = asg::SemanticIndex::MatchesIdOrAlias(v29, v28);
      std::_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>::~_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>(&v104);
      if ( v30 )
      {
        v17 = 1;
        v80 = 1;
      }
      else
      {
        v32 = 0;
        if ( *((_BYTE *)v86 + 56) )
        {
          v31 = asg::SemanticIndex::DbDiskAnnEmbeddingStore::VectorSpace(v86[24], &v104);
          v81 |= 1u;
          if ( (unsigned __int8)asg::SemanticIndex::MatchesIdOrAlias(v31, v28) )
            v32 = 1;
        }
        if ( (v81 & 1) != 0 )
        {
          v81 &= ~1u;
          std::_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>::~_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>(&v104);
        }
        if ( !v32 )
        {
          asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
            v120,
            "Embedding is from an unexpected vector space",
            6);
          throw (asg::SemanticIndex::SemanticIndexException *)v120;
        }
        v16 = 1;
        v17 = v80;
      }
      v18 += 36;
    }
    while ( v18 != (wchar_t *)v19 );
    if ( v17 && v16 )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        pExceptionObject,
        "Updates are from both the current and previous vector spaces",
        6);
      throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
    }
    v4 = v86;
  }
  *(_OWORD *)v121 = 0;
  asg::SemanticIndex::SemanticIndexStore::BeginWriteTransaction(v4, v121);
  v33 = v90;
  v84 = *v90;
  asg::SemanticIndex::SemanticIndexStore::Remove<std::ranges::single_view<asg::Guid>>(v4, v121[0], &v84);
  if ( v17 )
    CurrentTableGroup = asg::SemanticIndex::ApplicationDb::GetCurrentTableGroup(v121[0]);
  else
    CurrentTableGroup = asg::SemanticIndex::ApplicationDb::GetPreviousTableGroup(v121[0]);
  v35 = v121[0];
  v104 = ":itemId";
  v105 = *v33;
  v106 = 3;
  v107 = ":tableId";
  LODWORD(v108) = CurrentTableGroup;
  v109 = 0;
  *(_QWORD *)&v89 = &v104;
  *((_QWORD *)&v89 + 1) = v110;
  v84 = v89;
  v84 = *(_OWORD *)asg::Sqlite::DbParameters::DbParameters(&v82, &v84);
  v92 = *(_OWORD *)std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(
                     &v96,
                     "INSERT INTO si_items (id, table_id) VALUES (:itemId, :tableId)");
  asg::Sqlite::DbTransaction::ExecuteNonQuery(v35);
  `eh vector destructor iterator'(
    &v104,
    0x50u,
    2u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  v140 = *(_OWORD *)a3;
  v102 = 0;
  v36 = v4 + 22;
  if ( !v80 )
    v36 = v4 + 24;
  v37 = v36[1];
  if ( v37 )
    _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
  *(_QWORD *)&v102 = *v36;
  *(_QWORD *)&v89 = v36[1];
  *((_QWORD *)&v102 + 1) = v89;
  v127 = 0;
  v128 = 0;
  asg::SemanticIndex::DbDiskAnnEmbeddingStore::AddBatch_std::ranges::transform_view_std::span_asg::SemanticIndex::ItemRegionEmbeddingUpdate_const___1___asg::SemanticIndex::SemanticIndexStore::AddOrReplace_::_32_::_lambda_2_____((asg::SemanticIndex::DbDiskAnnEmbeddingStore *)v102);
  v38 = 0;
  v39 = *a3;
  v40 = (__int64)&(*a3)[36 * (_QWORD)v15];
  v91 = v40;
  while ( v39 != (wchar_t *)v40 )
  {
    v137[0] = 0;
    v139 = 7;
    asg::SemanticIndex::TryGetEmbeddingMetadataJson(v132, v39 + 16);
    if ( v133 )
    {
      v41 = v132;
      if ( v132[3] > 0xFu )
        v41 = (_QWORD *)v132[0];
      v99 = v41;
      v100 = v132[2];
      v101 = 4;
      *(_QWORD *)&v87 = v137;
      std::_Variant_raw_visit1<2>::_Visit<std::_Variant_assign_visitor<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>,std::_Variant_storage_<0,int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>>(
        5,
        &v87,
        &v99);
      std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&v99);
    }
    v134[0] = 0;
    v136 = 7;
    v42 = 8LL * v38;
    if ( *(_BYTE *)(v42 + v127 + 4) )
    {
      v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v39 + 7) + 16LL))(*((_QWORD *)v39 + 7));
      v44 = (asg::SemanticRegistry::IVectorData *)*((_QWORD *)v39 + 7);
      v45 = *(_QWORD *)v44;
      if ( v43 )
      {
        v51 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(v45 + 16))(v44);
        *(_QWORD *)&v82 = 0x1900000463LL;
        *((_QWORD *)&v82 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\SemanticIndexStore.cpp";
        v83 = "void __cdecl asg::SemanticIndex::SemanticIndexStore::AddOrReplace(struct asg::Guid,class std::span<struct "
              "asg::SemanticIndex::ItemRegionEmbeddingUpdate const ,-1>)";
        if ( v51 != 1 )
        {
          v84 = v82;
          v85 = v83;
          asg::details::AsgAssertFail(&v84);
        }
        v52 = (asg::SemanticRegistry::IVectorData *)*((_QWORD *)v39 + 7);
        v53 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v52 + 16LL))(v52);
        if ( v53 != 1 )
        {
          (*(void (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v52 + 16LL))(v52);
          LOBYTE(v53) = 0;
        }
        *(_QWORD *)&v82 = 0xD00000060LL;
        *((_QWORD *)&v82 + 1) = "C:\\__w\\1\\s\\src\\SemanticPipelines\\internal\\libSemanticPipelines\\include\\Semantic"
                                "Pipelines\\ModelEmbedding.h";
        v83 = "class std::span<float const ,-1> __cdecl asg::SemanticPipelines::IModelEmbedding::AsSpan<float>(void) const";
        if ( !(_BYTE)v53 )
        {
          v84 = v82;
          v85 = v83;
          asg::details::AsgAssertFail(&v84);
        }
        asg::SemanticRegistry::IVectorData::Dimension(v52);
        v54 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v52 + 24LL))(v52);
        v55 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v52 + 8LL))(v52);
        if ( v55 < 4 )
          v54 = 0;
        v99 = (_QWORD *)v54;
        v100 = v55 & 0xFFFFFFFFFFFFFFFCuLL;
        v101 = 5;
        *(_QWORD *)&v87 = v134;
        std::_Variant_raw_visit1<2>::_Visit<std::_Variant_assign_visitor<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>,std::_Variant_storage_<0,int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>>(
          6,
          &v87,
          &v99);
        std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&v99);
      }
      else
      {
        (*(void (__fastcall **)(asg::SemanticRegistry::IVectorData *))(v45 + 16))(v44);
        v46 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v44 + 16LL))(v44);
        *(_QWORD *)&v82 = 0xD00000060LL;
        *((_QWORD *)&v82 + 1) = "C:\\__w\\1\\s\\src\\SemanticPipelines\\internal\\libSemanticPipelines\\include\\Semantic"
                                "Pipelines\\ModelEmbedding.h";
        v83 = "class std::span<unsigned char const ,-1> __cdecl asg::SemanticPipelines::IModelEmbedding::AsSpan<unsigned "
              "char>(void) const";
        if ( v46 )
        {
          v84 = v82;
          v85 = v83;
          asg::details::AsgAssertFail(&v84);
        }
        asg::SemanticRegistry::IVectorData::Dimension(v44);
        v47 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v44 + 24LL))(v44);
        v48 = (*(__int64 (__fastcall **)(asg::SemanticRegistry::IVectorData *))(*(_QWORD *)v44 + 8LL))(v44);
        v99 = (_QWORD *)v47;
        v100 = v48;
        v101 = 5;
        *(_QWORD *)&v87 = v134;
        std::_Variant_raw_visit1<2>::_Visit<std::_Variant_assign_visitor<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>,std::_Variant_storage_<0,int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>>(
          6,
          &v87,
          &v99);
        std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&v99);
      }
    }
    v49 = v4 + 33;
    if ( !v80 )
      v49 = v4 + 53;
    v124 = 0;
    v125 = 0;
    v126 = 0;
    v50 = v49[2];
    if ( v49[3] > 7u )
      v49 = (_QWORD *)*v49;
    if ( v50 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v50 > 7 )
    {
      v56 = v50 | 7;
      if ( (v50 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v56 < 0xA )
          v56 = 10;
        v57 = v56 + 1;
        if ( v56 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
      }
      else
      {
        v56 = 0x7FFFFFFFFFFFFFFELL;
        v57 = 0x7FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      *(_QWORD *)&v124 = std::_Allocate<16,std::_Default_allocate_traits>(2 * v57);
      v125 = v50;
      v126 = v56;
      memmove((void *)v124, v49, 2 * v50 + 2);
    }
    else
    {
      v125 = v50;
      v126 = 7;
      v124 = *(_OWORD *)v49;
    }
    v58 = v121[0];
    v104 = ":emb";
    *(_QWORD *)&v105 = *(unsigned int *)(v42 + v127);
    v106 = 1;
    v107 = ":id";
    v108 = *v90;
    v109 = 3;
    v59 = S1;
    if ( *((_QWORD *)S1 + 3) > 7u )
      v59 = *(wchar_t **)S1;
    v60 = *((_QWORD *)S1 + 2);
    v61 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2 * v60; ++j )
      v61 = 0x100000001B3LL * (*((unsigned __int8 *)v59 + j) ^ (unsigned __int64)v61);
    v63 = v131[3] & v61;
    v64 = *(_QWORD *)(v131[0] + 16 * v63 + 8);
    if ( (__int64 *)v64 == v130 )
LABEL_139:
      std::_Xout_of_range("invalid unordered_map<K, T> key");
    v65 = *(_QWORD *)(v131[0] + 16 * v63);
    while ( v60 != *(_QWORD *)(v64 + 24) || v60 && wmemcmp(v59, *(const wchar_t **)(v64 + 16), v60) )
    {
      if ( v64 == v65 )
        goto LABEL_139;
      v64 = *(_QWORD *)(v64 + 8);
    }
    v110[0] = ":region";
    v66 = v64 + 32;
    if ( *(_QWORD *)(v64 + 56) > 0xFu )
      v66 = *(_QWORD *)(v64 + 32);
    v67 = *(_QWORD *)(v64 + 48);
    v110[1] = v66;
    v110[2] = v67;
    v111 = 4;
    v112 = ":order";
    v113 = v38;
    v114 = 0;
    v115 = ":metadata";
    asg::Sqlite::DbValue::DbValue((asg::Sqlite::DbValue *)v116, (const struct asg::Sqlite::DbValue *)v137);
    v117 = ":embedding";
    asg::Sqlite::DbValue::DbValue((asg::Sqlite::DbValue *)v118, (const struct asg::Sqlite::DbValue *)v134);
    v68 = &v124;
    if ( v126 > 7 )
      v68 = (__int128 *)v124;
    asg::details::_asg_u16format(
      v93,
      L"INSERT INTO %ls (embedding_id, item_id, region_id, ordinal, metadata_json, embedding_altstore) VALUES (:emb, :id, "
       ":region, :order, :metadata, :embedding)",
      v68);
    v81 |= 2u;
    v69 = v93;
    if ( v95 > 7 )
      v69 = (_QWORD *)v93[0];
    *(_QWORD *)&v96 = v69;
    *((_QWORD *)&v96 + 1) = v94;
    *(_QWORD *)&v92 = &v104;
    *((_QWORD *)&v92 + 1) = 6;
    v87 = v96;
    v70 = (_QWORD *)asg::utf16To8(Block, &v87);
    v71 = v70;
    if ( v70[3] > 0xFu )
      v71 = (_QWORD *)*v70;
    *(_QWORD *)&v84 = v71;
    *((_QWORD *)&v84 + 1) = v70[2];
    v87 = v92;
    v82 = v84;
    asg::Sqlite::DbTransaction::ExecuteNonQuery(v58);
    if ( v98 > 0xF )
    {
      v72 = Block[0];
      if ( v98 + 1 >= 0x1000 )
      {
        v72 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v72 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v72);
    }
    Block[2] = 0;
    v98 = 15;
    LOBYTE(Block[0]) = 0;
    if ( v95 > 7 )
    {
      v73 = (void *)v93[0];
      if ( 2 * v95 + 2 >= 0x1000 )
      {
        v73 = *(void **)(v93[0] - 8LL);
        if ( (unsigned __int64)(v93[0] - (_QWORD)v73 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v73);
    }
    v94 = 0;
    v95 = 7;
    LOWORD(v93[0]) = 0;
    `eh vector destructor iterator'(
      &v104,
      0x50u,
      6u,
      std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
    ++v38;
    v74 = v126;
    if ( v126 > 7 )
    {
      v75 = (void *)v124;
      if ( 2 * v126 + 2 >= 0x1000 )
      {
        v75 = *(void **)(v124 - 8);
        if ( (unsigned __int64)(v124 - (_QWORD)v75 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v75);
    }
    v125 = 0;
    v126 = 7;
    LOWORD(v124) = 0;
    switch ( v136 )
    {
      case 0:
      case 1:
      case 2:
      case 3:
      case 4:
      case 5:
      case 7:
        goto LABEL_103;
      case 6:
        if ( v135 )
        {
          LOBYTE(v74) = v135 != v134;
          (*(void (__fastcall **)(_QWORD *, unsigned __int64))(*v135 + 32LL))(v135, v74);
          v135 = 0;
        }
LABEL_103:
        if ( v133 )
          std::string::~string(v132);
        switch ( v139 )
        {
          case 0:
          case 1:
          case 2:
          case 3:
          case 4:
          case 5:
          case 7:
            goto LABEL_108;
          case 6:
            if ( v138 )
            {
              LOBYTE(v74) = v138 != v137;
              (*(void (__fastcall **)(_QWORD *, unsigned __int64))(*v138 + 32LL))(v138, v74);
            }
            break;
        }
        break;
      case 8:
        break;
    }
LABEL_108:
    v39 = S1 + 36;
    S1 += 36;
    v4 = v86;
    v40 = v91;
  }
  asg::Sqlite::DbTransaction::Commit(v121[0]);
  v76 = (void *)v127;
  if ( (_QWORD)v127 )
  {
    if ( ((v128 - (_QWORD)v127) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      v76 = *(void **)(v127 - 8);
      if ( (unsigned __int64)(v127 - (_QWORD)v76 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v76);
    v127 = 0;
    v128 = 0;
  }
  v77 = (volatile signed __int32 *)v89;
  if ( (_QWORD)v89 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v89 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
      if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
    }
  }
  v78 = (volatile signed __int32 *)v121[1];
  if ( v121[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v121[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
      if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
    }
  }
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(v131);
  std::list<std::pair<std::u16string_view const,std::basic_string<char8_t>>>::~list<std::pair<std::u16string_view const,std::basic_string<char8_t>>>(&v130);
  if ( v122[0] )
  {
    std::_Destroy_range<std::allocator<asg::SemanticIndex::ItemRegionEmbeddingUpdate>>(v122[0], v122[1]);
    v79 = v122[0];
    if ( (unsigned __int64)(72 * ((signed __int64)(v123 - (unsigned __int64)v122[0]) / 72)) >= 0x1000 )
    {
      v79 = (asg::SemanticIndex::ItemRegionEmbeddingUpdate *)*((_QWORD *)v122[0] - 1);
      if ( (unsigned __int64)(v122[0] - v79 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v79);
  }
}

```

## disassembly

```asm
0x18018e2c0  mov     [rsp+arg_8], rbx
0x18018e2c5  mov     [rsp+arg_18], rsi
0x18018e2ca  push    rdi
0x18018e2cb  push    r12
0x18018e2cd  push    r13
0x18018e2cf  push    r14
0x18018e2d1  push    r15
0x18018e2d3  sub     rsp, 5B0h
0x18018e2da  mov     rax, cs:__security_cookie
0x18018e2e1  xor     rax, rsp
0x18018e2e4  mov     [rsp+5D8h+var_30], rax
0x18018e2ec  mov     r15, r8
0x18018e2ef  mov     [rsp+5D8h+var_518], rdx
0x18018e2f7  mov     rsi, rcx
0x18018e2fa  mov     [rsp+5D8h+var_558], rcx
0x18018e302  xor     ebx, ebx
0x18018e304  mov     [rsp+5D8h+var_5A4], ebx
0x18018e308  mov     edx, 18h
0x18018e30d  lea     rcx, [rsp+5D8h+var_1B8]
0x18018e315  call    ?__autoclassinit2@?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@QEAAX_K@Z; std::u8string_view::__autoclassinit2(unsigned __int64)
0x18018e31a  xorps   xmm0, xmm0
0x18018e31d  movdqu  xmmword ptr [rsp+5D8h+var_1B8], xmm0
0x18018e326  mov     [rsp+5D8h+var_1A8], rbx
0x18018e32e  lea     rdx, [rsp+5D8h+var_528]
0x18018e336  mov     rcx, r15
0x18018e339  call    ?end@?$span@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@QEBA?AU?$_Span_iterator@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@2@XZ; std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::end(void)
0x18018e33e  mov     rbx, [r15]
0x18018e341  mov     r8, rsi
0x18018e344  mov     rdx, [rax]
0x18018e347  mov     rcx, rbx
0x18018e34a  call    std__any_of_std___Span_iterator_asg__SemanticIndex__ItemRegionEmbeddingUpdate_const____asg__SemanticIndex__SemanticIndexStore__AddOrReplace____3____lambda_1___
0x18018e34f  test    al, al
0x18018e351  jz      loc_18018E43A
0x18018e357  lea     rdx, [rsp+5D8h+var_528]
0x18018e35f  mov     rcx, r15
0x18018e362  call    ?end@?$span@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@QEBA?AU?$_Span_iterator@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@2@XZ; std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::end(void)
0x18018e367  mov     rax, [rax]
0x18018e36a  mov     [rsp+5D8h+Reserved], rax
0x18018e36f  mov     r9, rbx
0x18018e372  mov     r8, [rsp+5D8h+var_1B8+8]
0x18018e37a  lea     rdx, [rsp+5D8h+var_510]
0x18018e382  lea     rcx, [rsp+5D8h+var_1B8]
0x18018e38a  call    ??$insert@U?$_Span_iterator@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@std@@$0A@@?$vector@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@V?$allocator@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@@std@@@std@@@1@U?$_Span_iterator@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@1@1@Z; std::vector<asg::SemanticIndex::ItemRegionEmbeddingUpdate>::insert<std::_Span_iterator<asg::SemanticIndex::ItemRegionEmbeddingUpdate const>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<asg::SemanticIndex::ItemRegionEmbeddingUpdate>>>,std::_Span_iterator<asg::SemanticIndex::ItemRegionEmbeddingUpdate const>,std::_Span_iterator<asg::SemanticIndex::ItemRegionEmbeddingUpdate const>)
0x18018e38f  mov     rdi, [rsp+5D8h+var_1B8+8]
0x18018e397  mov     rbx, [rsp+5D8h+var_1B8]
0x18018e39f  cmp     rbx, rdi
0x18018e3a2  jz      short loc_18018E3FA
0x18018e3a4  add     rbx, 38h ; '8'
0x18018e3a8  nop     dword ptr [rax+rax+00000000h]
0x18018e3b0  mov     rcx, [rbx]
0x18018e3b3  mov     rax, [rcx]
0x18018e3b6  call    qword ptr [rax+10h]
0x18018e3b9  mov     ecx, eax
0x18018e3bb  call    ?ValidateEmbeddingElementType@SemanticRegistry@asg@@YAXW4EmbeddingElementType@12@@Z; asg::SemanticRegistry::ValidateEmbeddingElementType(asg::SemanticRegistry::EmbeddingElementType)
0x18018e3c0  mov     r8, rbx
0x18018e3c3  lea     rdx, [rsp+5D8h+var_578]
0x18018e3c8  mov     rcx, rsi
0x18018e3cb  call    ?ConvertIfNecessary@SemanticIndexStore@SemanticIndex@asg@@AEBA?AV?$shared_ptr@UIModelEmbedding@SemanticPipelines@asg@@@std@@AEBV45@@Z; asg::SemanticIndex::SemanticIndexStore::ConvertIfNecessary(std::shared_ptr<asg::SemanticPipelines::IModelEmbedding> const &)
0x18018e3d0  mov     rdx, rax
0x18018e3d3  mov     rcx, rbx
0x18018e3d6  call    ??4?$shared_ptr@$$CBUQueryContinuationData@DiskAnn@SemanticIndex@asg@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<asg::SemanticIndex::DiskAnn::QueryContinuationData const>::operator=(std::shared_ptr<asg::SemanticIndex::DiskAnn::QueryContinuationData const> &&)
0x18018e3db  lea     rcx, [rsp+5D8h+var_578]
0x18018e3e0  call    ??1?$shared_ptr@V?$vector@UGuid@asg@@V?$allocator@UGuid@asg@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(void)
0x18018e3e5  add     rbx, 48h ; 'H'
0x18018e3e9  lea     rax, [rbx-38h]
0x18018e3ed  cmp     rax, rdi
0x18018e3f0  jnz     short loc_18018E3B0
0x18018e3f2  mov     rbx, [rsp+5D8h+var_1B8]
0x18018e3fa  lea     rcx, [rsp+5D8h+var_1B8]
0x18018e402  call    ?size@?$vector@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@V?$allocator@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@@std@@@std@@QEBA_KXZ; std::vector<asg::SemanticIndex::ItemRegionEmbeddingUpdate>::size(void)
0x18018e407  mov     r8, rax
0x18018e40a  mov     rdx, rbx
0x18018e40d  lea     rcx, [rsp+5D8h+var_598]
0x18018e412  call    ??$?0PEAUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@?$span@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@QEAA@PEAUItemRegionEmbeddingUpdate@SemanticIndex@asg@@_K@Z; std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>(asg::SemanticIndex::ItemRegionEmbeddingUpdate *,unsigned __int64)
0x18018e417  mov     rcx, [rax]
0x18018e41a  mov     [rsp+5D8h+var_1C8], rcx
0x18018e422  mov     rax, [rax+8]
0x18018e426  mov     [rsp+5D8h+var_1C8+8], rax
0x18018e42e  movups  xmm0, xmmword ptr [rsp+5D8h+var_1C8]
0x18018e436  movups  xmmword ptr [r15], xmm0
0x18018e43a  mov     edx, 40h ; '@'
0x18018e43f  lea     rcx, [rsp+5D8h+var_168]
0x18018e447  call    ?__autoclassinit2@?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@QEAAX_K@Z; std::u8string_view::__autoclassinit2(unsigned __int64)
0x18018e44c  lea     rcx, [rsp+5D8h+var_168]
0x18018e454  call    ??0?$unordered_map@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@U?$hash@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@U?$equal_to@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::u16string_view,std::basic_string<char8_t>>::unordered_map<std::u16string_view,std::basic_string<char8_t>>(void)
0x18018e459  nop
0x18018e45a  mov     r13, [r15+8]
0x18018e45e  mov     rdx, r13
0x18018e461  lea     rcx, [rsp+5D8h+var_168]
0x18018e469  call    ?reserve@?$_Hash@V?$_Umap_traits@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@V?$_Uhash_compare@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@U?$hash@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@U?$equal_to@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@2@$0A@@std@@@std@@QEAAX_K@Z; std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::reserve(unsigned __int64)
0x18018e46e  xor     r14b, r14b
0x18018e471  xor     bl, bl
0x18018e473  mov     [rsp+5D8h+var_5A8], bl
0x18018e477  mov     rdi, [r15]
0x18018e47a  mov     [rsp+5D8h+S1], rdi
0x18018e482  mov     rcx, r15
0x18018e485  call    ?_Unchecked_end@?$span@$$CBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@QEBAPEBUItemRegionEmbeddingUpdate@SemanticIndex@asg@@XZ; std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate const,-1>::_Unchecked_end(void)
0x18018e48a  mov     r12, rax
0x18018e48d  cmp     rdi, rax
0x18018e490  jz      loc_18018E685
0x18018e496  mov     rcx, 0CBF29CE484222325h
0x18018e4a0  mov     r10, 100000001B3h
0x18018e4aa  nop     word ptr [rax+rax+00h]
0x18018e4b0  mov     rdx, rdi
0x18018e4b3  cmp     qword ptr [rdi+18h], 7
0x18018e4b8  jbe     short loc_18018E4BD
0x18018e4ba  mov     rdx, [rdi]
0x18018e4bd  mov     rax, [rdi+10h]
0x18018e4c1  mov     [rsp+5D8h+var_1C8], rdx
0x18018e4c9  mov     [rsp+5D8h+var_1C8+8], rax
0x18018e4d1  mov     r9, rcx
0x18018e4d4  lea     r8, [rax+rax]
0x18018e4d8  xor     ecx, ecx
0x18018e4da  test    r8, r8
0x18018e4dd  jz      short loc_18018E4F3
0x18018e4df  nop
0x18018e4e0  movzx   eax, byte ptr [rdx+rcx]
0x18018e4e4  xor     r9, rax
0x18018e4e7  imul    r9, r10
0x18018e4eb  inc     rcx
0x18018e4ee  cmp     rcx, r8
0x18018e4f1  jb      short loc_18018E4E0
0x18018e4f3  lea     r8, [rsp+5D8h+var_1C8]
0x18018e4fb  lea     rdx, [rsp+5D8h+var_598]
0x18018e500  lea     rcx, [rsp+5D8h+var_168]
0x18018e508  call    ??$_Find_last@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@V?$_Uhash_compare@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@U?$hash@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@U?$equal_to@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@PEAX@std@@@1@AEBV?$basic_string_view@_SU?$char_traits@_S@std@@@1@_K@Z; std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::_Find_last<std::u16string_view>(std::u16string_view const &,unsigned __int64)
0x18018e50d  mov     rcx, [rax+8]
0x18018e511  mov     rbx, [rsp+5D8h+var_160]
0x18018e519  test    rcx, rcx
0x18018e51c  cmovnz  rbx, rcx
0x18018e520  cmp     rbx, [rsp+5D8h+var_160]
0x18018e528  jnz     short loc_18018E583
0x18018e52a  lea     rdx, [rsp+5D8h+var_508]
0x18018e532  mov     rcx, rdi
0x18018e535  call    ??BRegionId@SemanticPipelines@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::SemanticPipelines::RegionId::operator std::u16string_view(void)
0x18018e53a  movups  xmm0, xmmword ptr [rax]
0x18018e53d  movaps  [rsp+5D8h+var_578], xmm0
0x18018e542  lea     rdx, [rsp+5D8h+var_578]
0x18018e547  lea     rcx, [rsp+5D8h+Block]
0x18018e54f  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x18018e554  nop
0x18018e555  mov     [rsp+5D8h+Reserved], rax
0x18018e55a  mov     r9, rdi
0x18018e55d  mov     r8, rbx
0x18018e560  lea     rdx, [rsp+5D8h+var_528]
0x18018e568  lea     rcx, [rsp+5D8h+var_168]
0x18018e570  call    ??$emplace_hint@AEBURegionId@SemanticPipelines@asg@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@V?$_Uhash_compare@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@U?$hash@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@U?$equal_to@V?$basic_string_view@_SU?$char_traits@_S@std@@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@2@@std@@@std@@@std@@@1@AEBURegionId@SemanticPipelines@asg@@$$QEAV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@1@@Z; std::_Hash<std::_Umap_traits<std::u16string_view,std::basic_string<char8_t>,std::_Uhash_compare<std::u16string_view,std::hash<std::u16string_view>,std::equal_to<std::u16string_view>>,std::allocator<std::pair<std::u16string_view const,std::basic_string<char8_t>>>,0>>::emplace_hint<asg::SemanticPipelines::RegionId const &,std::basic_string<char8_t>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u16string_view const,std::basic_string<char8_t>>>>>,asg::SemanticPipelines::RegionId const &,std::basic_string<char8_t> &&)
0x18018e575  nop
0x18018e576  lea     rcx, [rsp+5D8h+Block]; void *
0x18018e57e  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
0x18018e583  mov     rcx, [rdi+38h]; this
0x18018e587  test    rcx, rcx
0x18018e58a  jz      loc_18018F2D0
0x18018e590  call    asg__SemanticIndex__ValidateEmbedding
0x18018e595  mov     rcx, [rdi+38h]
0x18018e599  mov     rax, [rcx]
0x18018e59c  call    qword ptr [rax+20h]
0x18018e59f  mov     rsi, rax
0x18018e5a2  lea     rdx, [rsp+5D8h+var_428]
0x18018e5aa  mov     rax, [rsp+5D8h+var_558]
0x18018e5b2  mov     rcx, [rax+0B0h]
0x18018e5b9  call    ?VectorSpace@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@QEBA?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@XZ; asg::SemanticIndex::DbDiskAnnEmbeddingStore::VectorSpace(void)
0x18018e5be  mov     rdx, rsi
0x18018e5c1  mov     rcx, rax
0x18018e5c4  call    asg__SemanticIndex__MatchesIdOrAlias
0x18018e5c9  movzx   ebx, al
0x18018e5cc  lea     rcx, [rsp+5D8h+var_428]
0x18018e5d4  call    ??1?$_Optional_construct_base@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@QEAA@XZ; std::_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>::~_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>(void)
0x18018e5d9  test    bl, bl
0x18018e5db  jz      short loc_18018E5E5
0x18018e5dd  mov     bl, 1
0x18018e5df  mov     [rsp+5D8h+var_5A8], bl
0x18018e5e3  jmp     short loc_18018E64F
0x18018e5e5  mov     rax, [rsp+5D8h+var_558]
0x18018e5ed  cmp     byte ptr [rax+38h], 0
0x18018e5f1  jz      short loc_18018E61F
0x18018e5f3  lea     rdx, [rsp+5D8h+var_428]
0x18018e5fb  mov     rcx, [rax+0C0h]
0x18018e602  call    ?VectorSpace@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@QEBA?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@XZ; asg::SemanticIndex::DbDiskAnnEmbeddingStore::VectorSpace(void)
0x18018e607  or      [rsp+5D8h+var_5A4], 1
0x18018e60c  mov     rdx, rsi
0x18018e60f  mov     rcx, rax
0x18018e612  call    asg__SemanticIndex__MatchesIdOrAlias
0x18018e617  test    al, al
0x18018e619  jz      short loc_18018E61F
0x18018e61b  mov     bl, 1
0x18018e61d  jmp     short loc_18018E621
0x18018e61f  xor     bl, bl
0x18018e621  mov     esi, [rsp+5D8h+var_5A4]
0x18018e625  test    sil, 1
0x18018e629  jz      short loc_18018E63F
0x18018e62b  and     esi, 0FFFFFFFEh
0x18018e62e  mov     [rsp+5D8h+var_5A4], esi
0x18018e632  lea     rcx, [rsp+5D8h+var_428]
0x18018e63a  call    ??1?$_Optional_construct_base@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@QEAA@XZ; std::_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>::~_Optional_construct_base<asg::SemanticRegistry::VectorSpaceInfo>(void)
0x18018e63f  test    bl, bl
0x18018e641  jz      loc_18018F2A1
0x18018e647  mov     r14b, 1
0x18018e64a  movzx   ebx, [rsp+5D8h+var_5A8]
0x18018e64f  add     rdi, 48h ; 'H'
0x18018e653  cmp     rdi, r12
0x18018e656  mov     rcx, 0CBF29CE484222325h
0x18018e660  mov     r10, 100000001B3h
0x18018e66a  jnz     loc_18018E4B0
0x18018e670  test    bl, bl
0x18018e672  jz      short loc_18018E67D
0x18018e674  test    r14b, r14b
0x18018e677  jnz     loc_18018F272
0x18018e67d  mov     rsi, [rsp+5D8h+var_558]
0x18018e685  xorps   xmm0, xmm0
0x18018e688  movups  xmmword ptr [rsp+5D8h+var_1C8], xmm0
0x18018e690  lea     rdx, [rsp+5D8h+var_1C8]
0x18018e698  mov     rcx, rsi
0x18018e69b  call    ?BeginWriteTransaction@SemanticIndexStore@SemanticIndex@asg@@QEAA?AV?$shared_ptr@VApplicationDbWriteTransaction@SemanticIndex@asg@@@std@@XZ; asg::SemanticIndex::SemanticIndexStore::BeginWriteTransaction(void)
0x18018e6a0  nop
0x18018e6a1  mov     rdi, [rsp+5D8h+var_518]
0x18018e6a9  movups  xmm0, xmmword ptr [rdi]
0x18018e6ac  movups  [rsp+5D8h+var_578], xmm0
0x18018e6b1  lea     r8, [rsp+5D8h+var_578]
0x18018e6b6  mov     rdx, [rsp+5D8h+var_1C8]
0x18018e6be  mov     rcx, rsi
0x18018e6c1  call    ??$Remove@V?$single_view@UGuid@asg@@@ranges@std@@@SemanticIndexStore@SemanticIndex@asg@@AEAA_JAEAVDbTransaction@Sqlite@2@AEBV?$single_view@UGuid@asg@@@ranges@std@@@Z; asg::SemanticIndex::SemanticIndexStore::Remove<std::ranges::single_view<asg::Guid>>(asg::Sqlite::DbTransaction &,std::ranges::single_view<asg::Guid> const &)
0x18018e6c6  mov     rcx, [rsp+5D8h+var_1C8]
0x18018e6ce  test    bl, bl
0x18018e6d0  jz      short loc_18018E6D9
0x18018e6d2  call    ?GetCurrentTableGroup@ApplicationDb@SemanticIndex@asg@@SA?AW4TableGroupId@23@AEAVDbTransaction@Sqlite@3@@Z; asg::SemanticIndex::ApplicationDb::GetCurrentTableGroup(asg::Sqlite::DbTransaction &)
0x18018e6d7  jmp     short loc_18018E6DE
0x18018e6d9  call    ?GetPreviousTableGroup@ApplicationDb@SemanticIndex@asg@@SA?AW4TableGroupId@23@AEAVDbTransaction@Sqlite@3@@Z; asg::SemanticIndex::ApplicationDb::GetPreviousTableGroup(asg::Sqlite::DbTransaction &)
0x18018e6de  mov     rbx, [rsp+5D8h+var_1C8]
0x18018e6e6  lea     rcx, aItemid; ":itemId"
0x18018e6ed  mov     [rsp+5D8h+var_428], rcx
0x18018e6f5  movups  xmm0, xmmword ptr [rdi]
0x18018e6f8  movups  [rsp+5D8h+var_420], xmm0
0x18018e700  mov     [rsp+5D8h+var_3E0], 3
0x18018e708  lea     rcx, aTableid; ":tableId"
0x18018e70f  mov     [rsp+5D8h+var_3D8], rcx
0x18018e717  mov     dword ptr [rsp+5D8h+var_3D0], eax
0x18018e71e  mov     [rsp+5D8h+var_390], 0
0x18018e726  lea     rax, [rsp+5D8h+var_428]
0x18018e72e  mov     qword ptr [rsp+5D8h+var_528], rax
0x18018e736  lea     rax, [rsp+5D8h+var_388]
0x18018e73e  mov     qword ptr [rsp+5D8h+var_528+8], rax
0x18018e746  movaps  xmm0, [rsp+5D8h+var_528]
0x18018e74e  movdqa  [rsp+5D8h+var_578], xmm0
0x18018e754  lea     rdx, [rsp+5D8h+var_578]
0x18018e759  lea     rcx, [rsp+5D8h+var_598]
0x18018e75e  call    ??0DbParameters@Sqlite@asg@@QEAA@V?$initializer_list@U?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@@std@@@Z; asg::Sqlite::DbParameters::DbParameters(std::initializer_list<std::pair<char8_t const *,asg::Sqlite::DbValue>>)
0x18018e763  movups  xmm0, xmmword ptr [rax]
0x18018e766  movaps  [rsp+5D8h+var_578], xmm0
0x18018e76b  lea     rdx, aInsertIntoSiIt; "INSERT INTO si_items (id, table_id) VAL"...
0x18018e772  lea     rcx, [rsp+5D8h+var_4D8]
0x18018e77a  call    ??0?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@QEAA@QEB_Q@Z; std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(char8_t const * const)
0x18018e77f  movups  xmm0, xmmword ptr [rax]
0x18018e782  movaps  [rsp+5D8h+var_508], xmm0
0x18018e78a  lea     r8, [rsp+5D8h+var_578]
0x18018e78f  lea     rdx, [rsp+5D8h+var_508]
0x18018e797  mov     rcx, rbx; this
0x18018e79a  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x18018e79f  nop
0x18018e7a0  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x18018e7a7  mov     edx, 50h ; 'P'; unsigned __int64
0x18018e7ac  mov     r8d, 2; unsigned __int64
0x18018e7b2  lea     rcx, [rsp+5D8h+var_428]; void *
0x18018e7ba  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18018e7bf  movups  xmm0, xmmword ptr [r15]
0x18018e7c3  movups  [rsp+5D8h+var_48], xmm0
0x18018e7cb  xorps   xmm1, xmm1
0x18018e7ce  movups  [rsp+5D8h+var_460], xmm1
0x18018e7d6  cmp     [rsp+5D8h+var_5A8], 0
0x18018e7db  lea     rax, [rsi+0B0h]
0x18018e7e2  jnz     short loc_18018E7EB
0x18018e7e4  lea     rax, [rsi+0C0h]
0x18018e7eb  mov     rcx, [rax+8]
0x18018e7ef  test    rcx, rcx
0x18018e7f2  jz      short loc_18018E7F8
0x18018e7f4  lock inc dword ptr [rcx+8]
0x18018e7f8  mov     rcx, [rax]; this
0x18018e7fb  mov     qword ptr [rsp+5D8h+var_460], rcx
0x18018e803  mov     rdx, [rax+8]
0x18018e807  mov     qword ptr [rsp+5D8h+var_528], rdx
0x18018e80f  mov     qword ptr [rsp+5D8h+var_460+8], rdx
0x18018e817  xorps   xmm0, xmm0
0x18018e81a  xor     eax, eax
0x18018e81c  movups  [rsp+5D8h+var_180], xmm0
0x18018e824  mov     [rsp+5D8h+var_170], rax
0x18018e82c  mov     r9, [rsp+5D8h+var_1C8]
0x18018e834  lea     r8, [rsp+5D8h+var_48]
0x18018e83c  lea     rdx, [rsp+5D8h+var_180]
0x18018e844  call    asg__SemanticIndex__DbDiskAnnEmbeddingStore__AddBatch_std__ranges__transform_view_std__span_asg__SemanticIndex__ItemRegionEmbeddingUpdate_const___1___asg__SemanticIndex__SemanticIndexStore__AddOrReplace____32____lambda_2_____
0x18018e849  nop
0x18018e84a  xor     ebx, ebx
0x18018e84c  mov     r12d, ebx
0x18018e84f  lea     rax, ds:0[r13*8]
0x18018e857  add     rax, r13
0x18018e85a  mov     rdi, [r15]
0x18018e85d  lea     rax, [rdi+rax*8]
0x18018e861  mov     [rsp+5D8h+var_510], rax
0x18018e869  mov     r13, 100000001B3h
0x18018e873  lea     r15, aClassStdSpanUn; "class std::span<unsigned char const ,-1"...
0x18018e87a  cmp     rdi, rax
  ... truncated ...
```
