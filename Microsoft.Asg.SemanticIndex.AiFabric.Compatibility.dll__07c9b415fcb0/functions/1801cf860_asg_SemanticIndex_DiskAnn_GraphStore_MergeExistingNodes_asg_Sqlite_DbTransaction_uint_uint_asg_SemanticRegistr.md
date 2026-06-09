# asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(asg::Sqlite::DbTransaction &,uint,uint,asg::SemanticRegistry::IVectorData const *)

- ea: `0x1801cf860`
- end: `0x1801d0040`
- name: `?MergeExistingNodes@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@IIPEBUIVectorData@SemanticRegistry@4@@Z`
- size: `2016`
- prototype: `void __usercall(asg::SemanticIndex::DiskAnn::GraphStore *__hidden this@<rcx>, struct asg::Sqlite::DbTransaction *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const struct asg::SemanticRegistry::IVectorData *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b2e50`

## callees

- `0x1800040f0`
- `0x1800048e0`
- `0x180006220`
- `0x180006b60`
- `0x180007ce0`
- `0x180007de0`
- `0x18000ae40`
- `0x18000d290`
- `0x180017620`
- `0x180017950`
- `0x180017b80`
- `0x180017f70`
- `0x180018130`
- `0x18001db90`
- `0x18002b900`
- `0x18002c570`
- `0x180038d00`
- `0x1800437b0`
- `0x1800476a0`
- `0x180078ed0`
- `0x18007c250`
- `0x18007c5a0`
- `0x180181140`
- `0x1801831c0`
- `0x1801c9850`
- `0x1801ca420`
- `0x1801caa80`
- `0x1801cee00`
- `0x1801cf860`
- `0x1801d0940`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f7680`
- `0x1801f97e0`
- `0x180206ec0`

## string_xrefs

- `0x1801cf901`: `DELETE FROM %ls WHERE id = :id RETURNING reference_count`
- `0x1801cfacd`: `void __cdecl asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(class asg::Sqlite::DbTransaction &,unsigned int,unsigned int,const struct asg::SemanticRegistry::IVectorData *)`
- `0x1801cfe33`: `UPDATE %ls SET embedding_id = :target_id, embedding_altstore = CASE WHEN embedding_altstore IS NULL THEN :embedding ELSE embedding_altstore END WHERE embedding_id = :source_id`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(
        asg::SemanticIndex::DiskAnn::GraphStore *this,
        struct asg::Sqlite::DbTransaction *a2,
        unsigned int a3,
        unsigned int a4,
        const struct asg::SemanticRegistry::IVectorData *a5)
{
  unsigned int v5; // r14d
  __int64 v6; // rbx
  __int64 v9; // r8
  __int64 v10; // rdi
  __int128 *v11; // rax
  unsigned __int64 *v12; // rax
  unsigned __int64 v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  unsigned __int64 v16; // r9
  _QWORD *v17; // rax
  unsigned __int64 v18; // rsi
  unsigned __int64 SafeVariableLimit; // rax
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rdi
  _QWORD *v22; // rbx
  unsigned __int64 v23; // rax
  _QWORD **v24; // rcx
  _QWORD *v25; // rcx
  _QWORD *v26; // rbx
  __int64 v27; // rbx
  const void *v28; // rax
  __m128i *p_pExceptionObject; // rdx
  char v30; // bl
  int v31; // r8d
  __int64 v32; // rcx
  __int64 v33; // xmm1_8
  __int128 v34; // xmm6
  __int64 v35; // rax
  _QWORD **v36; // rcx
  _QWORD *v37; // rcx
  _QWORD *v38; // rbx
  __int128 v39; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v40; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v41[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  const char *v43; // [rsp+70h] [rbp-90h]
  unsigned __int64 v44; // [rsp+78h] [rbp-88h]
  unsigned int v45; // [rsp+80h] [rbp-80h]
  __int128 v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h] BYREF
  int v50; // [rsp+C0h] [rbp-40h] BYREF
  void *Block; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v52; // [rsp+D0h] [rbp-30h]
  __int128 v53; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-18h]
  __int128 v55; // [rsp+F0h] [rbp-10h]
  void *v56[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v57; // [rsp+110h] [rbp+10h] BYREF
  __int128 v58; // [rsp+120h] [rbp+20h]
  __int128 v59; // [rsp+130h] [rbp+30h]
  __m128i pExceptionObject; // [rsp+140h] [rbp+40h] BYREF
  char v61; // [rsp+180h] [rbp+80h]
  char v62; // [rsp+188h] [rbp+88h]
  _QWORD v63[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v64; // [rsp+1E0h] [rbp+E0h]
  _QWORD v65[9]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v66; // [rsp+238h] [rbp+138h]
  const char *v67; // [rsp+240h] [rbp+140h]
  __int64 v68; // [rsp+248h] [rbp+148h]
  char v69; // [rsp+288h] [rbp+188h]
  char v70[80]; // [rsp+290h] [rbp+190h] BYREF
  _OWORD v71[3]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v72; // [rsp+318h] [rbp+218h]
  char v73; // [rsp+320h] [rbp+220h]

  v5 = a4;
  v45 = a4;
  v6 = a3;
  LODWORD(v40) = 0;
  asg::SemanticIndex::DiskAnn::GraphStore::TryGetStartNodeId(this, &v40, a2);
  if ( !BYTE4(v40) )
  {
    std::string::string(&v42, "Start node not found in the graph", v9);
    asg::SemanticIndex::DiskAnn::DiskAnnException::DiskAnnException(&v46, &v42, 2);
    throw (asg::SemanticIndex::DiskAnn::DiskAnnException *)&v46;
  }
  if ( (_DWORD)v6 == (_DWORD)v40 )
  {
    std::logic_error::logic_error((std::logic_error *)&v42, "Cannot merge the start node");
    throw (std::logic_error *)&v42;
  }
  pExceptionObject.m128i_i64[0] = (__int64)":id";
  v10 = (unsigned int)v6;
  *(_QWORD *)&v49 = v6;
  pExceptionObject.m128i_i64[1] = v6;
  v62 = 1;
  asg::details::_asg_u16format(&v42, L"DELETE FROM %ls WHERE id = :id RETURNING reference_count");
  v11 = &v42;
  if ( v44 > 7 )
    v11 = (__int128 *)v42;
  v41[0] = (unsigned __int64)v11;
  v41[1] = (unsigned __int64)v43;
  *(_QWORD *)&v40 = &pExceptionObject;
  *((_QWORD *)&v40 + 1) = 1;
  v39 = *(_OWORD *)v41;
  v12 = (unsigned __int64 *)asg::utf16To8(&v46, &v39);
  v13 = (unsigned __int64)v12;
  if ( v12[3] > 0xF )
    v13 = *v12;
  v41[0] = v13;
  v41[1] = v12[2];
  v39 = v40;
  v40 = *(_OWORD *)v41;
  asg::Sqlite::DbTransaction::ExecuteOptionalSingleValueQuery<__int64>(
    (_DWORD)a2,
    (unsigned int)v41,
    (unsigned int)&v40,
    (unsigned int)&v39,
    0);
  if ( v48 > 0xF )
  {
    v14 = (void *)v46;
    if ( v48 + 1 >= 0x1000 )
    {
      v14 = *(void **)(v46 - 8);
      if ( (unsigned __int64)(v46 - (_QWORD)v14 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v14);
  }
  v47 = 0;
  v48 = 15;
  LOBYTE(v46) = 0;
  if ( v44 > 7 )
  {
    v15 = (void *)v42;
    if ( 2 * v44 + 2 >= 0x1000 )
    {
      v15 = *(void **)(v42 - 8);
      if ( (unsigned __int64)(v42 - (_QWORD)v15 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v15);
  }
  v43 = 0;
  v44 = 7;
  LOWORD(v42) = 0;
  `eh vector destructor iterator'(
    &pExceptionObject,
    0x50u,
    1u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  v16 = 1;
  if ( LOBYTE(v41[1]) )
    v16 = v41[0];
  asg::SemanticIndex::DiskAnn::GraphStore::IncrementDuplicateReferenceCount(this, a2, v5, v16);
  *(_OWORD *)v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  LODWORD(v40) = v6;
  asg::SemanticIndex::DiskAnn::GraphStore::BatchClearNodes<std::ranges::single_view<unsigned int>>(this, v56, a2, &v40);
  *(_QWORD *)&v42 = 0x900000243LL;
  *((_QWORD *)&v42 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\GraphStore.cpp";
  v43 = "void __cdecl asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(class asg::Sqlite::DbTransaction &,unsi"
        "gned int,unsigned int,const struct asg::SemanticRegistry::IVectorData *)";
  if ( (_QWORD)v57 != 1 )
  {
    v46 = v42;
    v47 = v43;
    asg::details::AsgAssertFail(&v46);
  }
  v41[0] = (unsigned __int64)&v50;
  v50 = (int)v56[0];
  Block = 0;
  v52 = 0;
  _mm_lfence();
  v17 = operator new(0x18u);
  *v17 = v17;
  v17[1] = v17;
  Block = v17;
  v53 = 0;
  v54 = 0;
  v55 = v59;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(
    &v53,
    (__int64)(v58 - *((_QWORD *)&v57 + 1)) >> 3,
    v17);
  std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>,std::_Iterator_base0>>(
    (__int64)&v50,
    *(_QWORD **)v56[1],
    (_QWORD *)v56[1]);
  v41[0] = (unsigned __int64)&v50;
  *(_QWORD *)&v39 = this;
  *((_QWORD *)&v39 + 1) = a2;
  v18 = v52;
  if ( v52 )
  {
    SafeVariableLimit = asg::Sqlite::DbTransaction::GetSafeVariableLimit(a2, 0x64u);
    v20 = SafeVariableLimit >> 1;
    if ( !(SafeVariableLimit >> 1) )
    {
      v39 = *(_OWORD *)std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(&v40);
      v49 = *(_OWORD *)std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(
                         &v46,
                         "Variable limit too low for batching");
      asg::Sqlite::DbException::DbException((unsigned int)&pExceptionObject, (unsigned int)&v49, 1, 1, (__int64)&v39, 0);
      throw (asg::Sqlite::DbException *)&pExceptionObject;
    }
    v21 = v18;
    if ( v20 < v18 )
      v21 = SafeVariableLimit >> 1;
    v22 = *(_QWORD **)Block;
    while ( v21 )
    {
      v43 = 0;
      *(_QWORD *)&v42 = v22;
      *((_QWORD *)&v42 + 1) = v21;
      v46 = v42;
      v47 = 0;
      `asg::SemanticIndex::DiskAnn::GraphStore::BatchInsertNodesForPurging<std::unordered_set<unsigned int>>'::`2'::_lambda_1_::operator()<std::ranges::subrange<std::counted_iterator<std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned int>>>>,std::default_sentinel_t,1>,unsigned __int64>(
        &v39,
        &v46,
        v21);
      v23 = v21;
      do
      {
        v22 = (_QWORD *)*v22;
        --v23;
      }
      while ( v23 );
      v18 -= v21;
      v21 = v18;
      if ( v20 < v18 )
        v21 = v20;
    }
    v5 = v45;
    v10 = v49;
  }
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v53);
  v24 = (_QWORD **)Block;
  **((_QWORD **)Block + 1) = 0;
  v25 = *v24;
  if ( v25 )
  {
    do
    {
      v26 = (_QWORD *)*v25;
      operator delete(v25);
      v25 = v26;
    }
    while ( v26 );
  }
  operator delete(Block);
  if ( a5 )
  {
    v27 = (*(__int64 (__fastcall **)(const struct asg::SemanticRegistry::IVectorData *))(*(_QWORD *)a5 + 8LL))(a5);
    v28 = asg::SemanticRegistry::IVectorData::Data(a5);
    pExceptionObject = *(__m128i *)std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>(
                                     &v46,
                                     (__int64)v28,
                                     v27);
    v61 = 5;
    p_pExceptionObject = &pExceptionObject;
    v30 = 5;
    v31 = _mm_cvtsi128_si32(pExceptionObject);
    v32 = pExceptionObject.m128i_i64[0];
    v33 = pExceptionObject.m128i_i64[0];
  }
  else
  {
    v63[0] = 0;
    v64 = 7;
    p_pExceptionObject = (__m128i *)v63;
    v30 = 6;
    v31 = 0;
    v33 = 0;
    v32 = 0;
  }
  v73 = -1;
  switch ( p_pExceptionObject[4].m128i_i8[0] )
  {
    case 0:
      LODWORD(v71[0]) = v31;
      v73 = 0;
      break;
    case 1:
      v73 = 1;
      goto LABEL_43;
    case 2:
      *(_QWORD *)&v71[0] = v33;
      v73 = 2;
      break;
    case 3:
      v71[0] = *p_pExceptionObject;
      v73 = 3;
      break;
    case 4:
      v71[0] = *p_pExceptionObject;
      v73 = 4;
      break;
    case 5:
      v71[0] = *p_pExceptionObject;
      v73 = 5;
      break;
    case 6:
      v72 = 0;
      std::_Func_class<void,>::_Reset_move(v71, p_pExceptionObject);
      v73 = 6;
      break;
    case 7:
      v73 = 7;
LABEL_43:
      *(_QWORD *)&v71[0] = v32;
      break;
  }
  if ( (v30 & 2) != 0 )
  {
    v30 &= ~2u;
    std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(v63);
  }
  if ( (v30 & 1) != 0 )
    std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&pExceptionObject);
  v65[0] = ":source_id";
  v65[1] = v10;
  v66 = 1;
  v67 = ":target_id";
  v68 = v5;
  v69 = 1;
  std::pair<char8_t const *,asg::Sqlite::DbValue>::pair<char8_t const *,asg::Sqlite::DbValue>(v70, ":embedding", v71);
  *(_QWORD *)&v39 = v65;
  *((_QWORD *)&v39 + 1) = v71;
  v34 = *(_OWORD *)asg::Sqlite::DbParameters::DbParameters(&v40, &v39);
  *(_QWORD *)&v49 = std::basic_string<char16_t>::c_str((char *)this + 40);
  v35 = asg::u16format<char16_t const *>(
          &v50,
          L"UPDATE %ls SET embedding_id = :target_id, embedding_altstore = CASE WHEN embedding_altstore IS NULL THEN :embe"
           "dding ELSE embedding_altstore END WHERE embedding_id = :source_id",
          &v49);
  v39 = v34;
  *(_OWORD *)v41 = *(_OWORD *)asg::SemanticPipelines::RegionId::operator std::u16string_view(v35, &v42);
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a2);
  std::basic_string<char16_t>::_Tidy_deallocate(&v50);
  `eh vector destructor iterator'(
    v65,
    0x50u,
    3u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(v71);
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v57 + 8);
  v36 = (_QWORD **)v56[1];
  **((_QWORD **)v56[1] + 1) = 0;
  v37 = *v36;
  if ( v37 )
  {
    do
    {
      v38 = (_QWORD *)*v37;
      operator delete(v37);
      v37 = v38;
    }
    while ( v38 );
  }
  operator delete(v56[1]);
}

```

## disassembly

```asm
0x1801cf860  mov     [rsp-8+arg_10], rbx
0x1801cf865  push    rbp
0x1801cf866  push    rsi
0x1801cf867  push    rdi
0x1801cf868  push    r12
0x1801cf86a  push    r13
0x1801cf86c  push    r14
0x1801cf86e  push    r15
0x1801cf870  lea     rbp, [rsp-250h]
0x1801cf878  sub     rsp, 350h
0x1801cf87f  movaps  [rsp+380h+var_40], xmm6
0x1801cf887  mov     rax, cs:__security_cookie
0x1801cf88e  xor     rax, rsp
0x1801cf891  mov     [rbp+280h+var_50], rax
0x1801cf898  mov     r14d, r9d
0x1801cf89b  mov     [rbp+280h+var_300], r9d
0x1801cf89f  mov     ebx, r8d
0x1801cf8a2  mov     r15, rdx
0x1801cf8a5  mov     r13, rcx
0x1801cf8a8  mov     r12, [rbp+280h+arg_20]
0x1801cf8af  xor     esi, esi
0x1801cf8b1  mov     dword ptr [rsp+380h+var_340], esi
0x1801cf8b5  mov     r8, rdx
0x1801cf8b8  lea     rdx, [rsp+380h+var_340]
0x1801cf8bd  call    ?TryGetStartNodeId@GraphStore@DiskAnn@SemanticIndex@asg@@QEBA?AV?$optional@I@std@@AEAVDbTransaction@Sqlite@4@@Z; asg::SemanticIndex::DiskAnn::GraphStore::TryGetStartNodeId(asg::Sqlite::DbTransaction &)
0x1801cf8c2  cmp     byte ptr [rsp+380h+var_340+4], sil
0x1801cf8c7  jz      loc_1801CFF98
0x1801cf8cd  cmp     ebx, dword ptr [rsp+380h+var_340]
0x1801cf8d1  jz      loc_1801CFFCF
0x1801cf8d7  lea     rax, aId_1; ":id"
0x1801cf8de  mov     qword ptr [rbp+280h+pExceptionObject], rax
0x1801cf8e2  mov     edi, ebx
0x1801cf8e4  mov     qword ptr [rbp+280h+var_2D0], rbx
0x1801cf8e8  mov     qword ptr [rbp+280h+pExceptionObject+8], rbx
0x1801cf8ec  mov     [rbp+280h+var_1F8], 1
0x1801cf8f3  lea     r8, [r13+48h]
0x1801cf8f7  cmp     qword ptr [r8+18h], 7
0x1801cf8fc  jbe     short loc_1801CF901
0x1801cf8fe  mov     r8, [r8]
0x1801cf901  lea     rdx, aDeleteFromLsWh_5; "DELETE FROM %ls WHERE id = :id RETURNIN"...
0x1801cf908  lea     rcx, [rsp+380h+var_320]
0x1801cf90d  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801cf912  nop
0x1801cf913  lea     rax, [rsp+380h+var_320]
0x1801cf918  cmp     [rsp+380h+var_308], 7
0x1801cf91e  cmova   rax, qword ptr [rsp+380h+var_320]
0x1801cf924  mov     [rsp+380h+var_330], rax
0x1801cf929  mov     rax, [rsp+380h+var_310]
0x1801cf92e  mov     [rsp+380h+var_330+8], rax
0x1801cf933  lea     rax, [rbp+280h+pExceptionObject]
0x1801cf937  mov     qword ptr [rsp+380h+var_340], rax
0x1801cf93c  mov     qword ptr [rsp+380h+var_340+8], 1
0x1801cf945  movaps  xmm0, xmmword ptr [rsp+380h+var_330]
0x1801cf94a  movdqa  [rsp+380h+var_350], xmm0
0x1801cf950  lea     rdx, [rsp+380h+var_350]
0x1801cf955  lea     rcx, [rbp+280h+var_2F0]
0x1801cf959  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801cf95e  nop
0x1801cf95f  mov     rcx, rax
0x1801cf962  cmp     qword ptr [rax+18h], 0Fh
0x1801cf967  jbe     short loc_1801CF96C
0x1801cf969  mov     rcx, [rax]
0x1801cf96c  mov     [rsp+380h+var_330], rcx
0x1801cf971  mov     rax, [rax+10h]
0x1801cf975  mov     [rsp+380h+var_330+8], rax
0x1801cf97a  movups  xmm0, [rsp+380h+var_340]
0x1801cf97f  movaps  [rsp+380h+var_350], xmm0
0x1801cf984  movaps  xmm1, xmmword ptr [rsp+380h+var_330]
0x1801cf989  movdqa  [rsp+380h+var_340], xmm1
0x1801cf98f  mov     dword ptr [rsp+380h+Reserved], esi
0x1801cf993  lea     r9, [rsp+380h+var_350]
0x1801cf998  lea     r8, [rsp+380h+var_340]
0x1801cf99d  lea     rdx, [rsp+380h+var_330]
0x1801cf9a2  mov     rcx, r15
0x1801cf9a5  call    ??$ExecuteOptionalSingleValueQuery@_J@DbTransaction@Sqlite@asg@@QEAA?AV?$optional@_J@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@4@UDbParameters@12@W4DbStatementOptions@12@@Z; asg::Sqlite::DbTransaction::ExecuteOptionalSingleValueQuery<__int64>(std::u8string_view,asg::Sqlite::DbParameters,asg::Sqlite::DbStatementOptions)
0x1801cf9aa  nop
0x1801cf9ab  mov     rdx, [rbp+280h+var_2D8]
0x1801cf9af  cmp     rdx, 0Fh
0x1801cf9b3  jbe     short loc_1801CF9E6
0x1801cf9b5  inc     rdx
0x1801cf9b8  mov     rcx, qword ptr [rbp+280h+var_2F0]
0x1801cf9bc  mov     rax, rcx
0x1801cf9bf  cmp     rdx, 1000h
0x1801cf9c6  jb      short loc_1801CF9E1
0x1801cf9c8  add     rdx, 27h ; '''
0x1801cf9cc  mov     rcx, [rcx-8]; Block
0x1801cf9d0  sub     rax, rcx
0x1801cf9d3  sub     rax, 8
0x1801cf9d7  cmp     rax, 1Fh
0x1801cf9db  ja      loc_1801CFFF2
0x1801cf9e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cf9e6  mov     [rbp+280h+var_2E0], rsi
0x1801cf9ea  mov     [rbp+280h+var_2D8], 0Fh
0x1801cf9f2  mov     byte ptr [rbp+280h+var_2F0], 0
0x1801cf9f6  mov     rdx, [rsp+380h+var_308]
0x1801cf9fb  cmp     rdx, 7
0x1801cf9ff  jbe     short loc_1801CFA38
0x1801cfa01  lea     rdx, ds:2[rdx*2]
0x1801cfa09  mov     rcx, qword ptr [rsp+380h+var_320]
0x1801cfa0e  mov     rax, rcx
0x1801cfa11  cmp     rdx, 1000h
0x1801cfa18  jb      short loc_1801CFA33
0x1801cfa1a  add     rdx, 27h ; '''
0x1801cfa1e  mov     rcx, [rcx-8]; Block
0x1801cfa22  sub     rax, rcx
0x1801cfa25  sub     rax, 8
0x1801cfa29  cmp     rax, 1Fh
0x1801cfa2d  ja      loc_1801D0007
0x1801cfa33  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cfa38  mov     [rsp+380h+var_310], rsi
0x1801cfa3d  mov     [rsp+380h+var_308], 7
0x1801cfa46  mov     word ptr [rsp+380h+var_320], si
0x1801cfa4b  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x1801cfa52  mov     edx, 50h ; 'P'; unsigned __int64
0x1801cfa57  mov     r8d, 1; unsigned __int64
0x1801cfa5d  lea     rcx, [rbp+280h+pExceptionObject]; void *
0x1801cfa61  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801cfa66  mov     r9d, 1
0x1801cfa6c  cmp     byte ptr [rsp+380h+var_330+8], 0
0x1801cfa71  cmovnz  r9, [rsp+380h+var_330]; unsigned __int64
0x1801cfa77  mov     r8d, r14d; unsigned int
0x1801cfa7a  mov     rdx, r15; struct asg::Sqlite::DbTransaction *
0x1801cfa7d  mov     rcx, r13; this
0x1801cfa80  call    ?IncrementDuplicateReferenceCount@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@I_K@Z; asg::SemanticIndex::DiskAnn::GraphStore::IncrementDuplicateReferenceCount(asg::Sqlite::DbTransaction &,uint,unsigned __int64)
0x1801cfa85  xorps   xmm0, xmm0
0x1801cfa88  movups  xmmword ptr [rbp+280h+var_280], xmm0
0x1801cfa8c  movups  [rbp+280h+var_270], xmm0
0x1801cfa90  movups  [rbp+280h+var_260], xmm0
0x1801cfa94  movups  [rbp+280h+var_250], xmm0
0x1801cfa98  mov     dword ptr [rsp+380h+var_340], ebx
0x1801cfa9c  lea     r9, [rsp+380h+var_340]
0x1801cfaa1  mov     r8, r15
0x1801cfaa4  lea     rdx, [rbp+280h+var_280]
0x1801cfaa8  mov     rcx, r13
0x1801cfaab  call    ??$BatchClearNodes@V?$single_view@I@ranges@std@@@GraphStore@DiskAnn@SemanticIndex@asg@@QEBA?AV?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@AEAVDbTransaction@Sqlite@3@AEBV?$single_view@I@ranges@5@@Z; asg::SemanticIndex::DiskAnn::GraphStore::BatchClearNodes<std::ranges::single_view<uint>>(asg::Sqlite::DbTransaction &,std::ranges::single_view<uint> const &)
0x1801cfab0  nop
0x1801cfab1  mov     dword ptr [rsp+380h+var_320], 243h
0x1801cfab9  mov     dword ptr [rsp+380h+var_320+4], 9
0x1801cfac1  lea     rax, aCW1SSrcSemanti_6; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801cfac8  mov     qword ptr [rsp+380h+var_320+8], rax
0x1801cfacd  lea     rdx, aVoidCdeclAsgSe; "void __cdecl asg::SemanticIndex::DiskAn"...
0x1801cfad4  mov     [rsp+380h+var_310], rdx
0x1801cfad9  cmp     qword ptr [rbp+280h+var_270], 1
0x1801cfade  jnz     loc_1801CFF7A
0x1801cfae4  lea     rax, [rbp+280h+var_2C0]
0x1801cfae8  mov     [rsp+380h+var_330], rax
0x1801cfaed  mov     eax, dword ptr [rbp+280h+var_280]
0x1801cfaf0  mov     [rbp+280h+var_2C0], eax
0x1801cfaf3  mov     [rbp+280h+Block], rsi
0x1801cfaf7  mov     [rbp+280h+var_2B0], rsi
0x1801cfafb  lfence
0x1801cfafe  mov     ecx, 18h; Size
0x1801cfb03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801cfb08  mov     [rax], rax
0x1801cfb0b  mov     [rax+8], rax
0x1801cfb0f  mov     [rbp+280h+Block], rax
0x1801cfb13  xorps   xmm0, xmm0
0x1801cfb16  movdqu  [rbp+280h+var_2A8], xmm0
0x1801cfb1b  mov     [rbp+280h+var_298], rsi
0x1801cfb1f  mov     rcx, qword ptr [rbp+280h+var_250]
0x1801cfb23  mov     qword ptr [rbp+280h+var_290], rcx
0x1801cfb27  mov     rcx, qword ptr [rbp+280h+var_250+8]
0x1801cfb2b  mov     qword ptr [rbp+280h+var_290+8], rcx
0x1801cfb2f  mov     rdx, qword ptr [rbp+280h+var_260]
0x1801cfb33  sub     rdx, qword ptr [rbp+280h+var_270+8]
0x1801cfb37  sar     rdx, 3
0x1801cfb3b  mov     r8, rax
0x1801cfb3e  lea     rcx, [rbp+280h+var_2A8]
0x1801cfb42  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UTextRegionStream@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UTextRegionStream@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextRegionStream>>>>)
0x1801cfb47  mov     rdx, [rbp+280h+var_280+8]
0x1801cfb4b  mov     r8, rdx
0x1801cfb4e  mov     rdx, [rdx]
0x1801cfb51  lea     rcx, [rbp+280h+var_2C0]
0x1801cfb55  call    ??$_Insert_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<uint>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<uint>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<uint>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<uint>>,std::_Iterator_base0>)
0x1801cfb5a  nop
0x1801cfb5b  lea     rax, [rbp+280h+var_2C0]
0x1801cfb5f  mov     [rsp+380h+var_330], rax
0x1801cfb64  mov     qword ptr [rsp+380h+var_350], r13
0x1801cfb69  mov     qword ptr [rsp+380h+var_350+8], r15
0x1801cfb6e  mov     rsi, [rbp+280h+var_2B0]
0x1801cfb72  test    rsi, rsi
0x1801cfb75  jz      loc_1801CFC13
0x1801cfb7b  mov     edx, 64h ; 'd'; unsigned __int64
0x1801cfb80  mov     rcx, r15; this
0x1801cfb83  call    ?GetSafeVariableLimit@DbTransaction@Sqlite@asg@@QEBA_K_K@Z; asg::Sqlite::DbTransaction::GetSafeVariableLimit(unsigned __int64)
0x1801cfb88  mov     r14, rax
0x1801cfb8b  shr     r14, 1
0x1801cfb8e  jz      loc_1801CFF18
0x1801cfb94  mov     rdi, rsi
0x1801cfb97  cmp     r14, rsi
0x1801cfb9a  cmovb   rdi, r14
0x1801cfb9e  mov     rbx, [rbp+280h+Block]
0x1801cfba2  mov     rbx, [rbx]
0x1801cfba5  test    rdi, rdi
0x1801cfba8  jz      short loc_1801CFC0B
0x1801cfbaa  nop     word ptr [rax+rax+00h]
0x1801cfbb0  mov     [rsp+380h+var_310], 0
0x1801cfbb9  mov     qword ptr [rsp+380h+var_320], rbx
0x1801cfbbe  mov     qword ptr [rsp+380h+var_320+8], rdi
0x1801cfbc3  movups  xmm0, [rsp+380h+var_320]
0x1801cfbc8  movaps  [rbp+280h+var_2F0], xmm0
0x1801cfbcc  movsd   xmm1, [rsp+380h+var_310]
0x1801cfbd2  movsd   [rbp+280h+var_2E0], xmm1
0x1801cfbd7  mov     r8, rdi
0x1801cfbda  lea     rdx, [rbp+280h+var_2F0]
0x1801cfbde  lea     rcx, [rsp+380h+var_350]
0x1801cfbe3  call    ??$?RV?$subrange@V?$counted_iterator@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@@std@@Udefault_sentinel_t@2@$00@ranges@std@@_K@_lambda_1_@?1???$BatchInsertNodesForPurging@V?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@V?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@@Z@QEBA?A_PV?$subrange@V?$counted_iterator@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@I@std@@@std@@@std@@@std@@Udefault_sentinel_t@2@$00@ranges@8@_K@Z
0x1801cfbe8  mov     rax, rdi
0x1801cfbeb  nop     dword ptr [rax+rax+00h]
0x1801cfbf0  mov     rbx, [rbx]
0x1801cfbf3  sub     rax, 1
0x1801cfbf7  jnz     short loc_1801CFBF0
0x1801cfbf9  sub     rsi, rdi
0x1801cfbfc  mov     rdi, rsi
0x1801cfbff  cmp     r14, rsi
0x1801cfc02  cmovb   rdi, r14
0x1801cfc06  test    rdi, rdi
0x1801cfc09  jnz     short loc_1801CFBB0
0x1801cfc0b  mov     r14d, [rbp+280h+var_300]
0x1801cfc0f  mov     rdi, qword ptr [rbp+280h+var_2D0]
0x1801cfc13  lea     rcx, [rbp+280h+var_2A8]
0x1801cfc17  call    ?_Tidy@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<uint,uint>>::_Tidy(void)
0x1801cfc1c  mov     rcx, [rbp+280h+Block]
0x1801cfc20  mov     rax, [rcx+8]
0x1801cfc24  xor     esi, esi
0x1801cfc26  mov     [rax], rsi
0x1801cfc29  mov     rcx, [rcx]; Block
0x1801cfc2c  test    rcx, rcx
0x1801cfc2f  jz      short loc_1801CFC46
0x1801cfc31  mov     rbx, [rcx]
0x1801cfc34  mov     edx, 18h
0x1801cfc39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cfc3e  mov     rcx, rbx
0x1801cfc41  test    rbx, rbx
0x1801cfc44  jnz     short loc_1801CFC31
0x1801cfc46  mov     edx, 18h
0x1801cfc4b  mov     rcx, [rbp+280h+Block]; Block
0x1801cfc4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cfc54  test    r12, r12
0x1801cfc57  jz      short loc_1801CFCA5
0x1801cfc59  mov     rax, [r12]
0x1801cfc5d  mov     rcx, r12
0x1801cfc60  call    qword ptr [rax+8]
0x1801cfc63  mov     rbx, rax
0x1801cfc66  mov     rcx, r12; this
0x1801cfc69  call    ?Data@IVectorData@SemanticRegistry@asg@@QEBAPEBXXZ; asg::SemanticRegistry::IVectorData::Data(void)
0x1801cfc6e  mov     r8, rbx
0x1801cfc71  mov     rdx, rax
0x1801cfc74  lea     rcx, [rbp+280h+var_2F0]
0x1801cfc78  call    ??$?0PEAUItemRegionEmbeddingUpdate@SemanticIndex@asg@@@?$span@UItemRegionEmbeddingUpdate@SemanticIndex@asg@@$0?0@std@@QEAA@PEAUItemRegionEmbeddingUpdate@SemanticIndex@asg@@_K@Z; std::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>::span<asg::SemanticIndex::ItemRegionEmbeddingUpdate,-1>(asg::SemanticIndex::ItemRegionEmbeddingUpdate *,unsigned __int64)
0x1801cfc7d  movups  xmm0, xmmword ptr [rax]
0x1801cfc80  movups  [rbp+280h+pExceptionObject], xmm0
0x1801cfc84  mov     [rbp+280h+var_200], 5
0x1801cfc8b  lea     rdx, [rbp+280h+pExceptionObject]
0x1801cfc8f  mov     ebx, 5
0x1801cfc94  movd    r8d, xmm0
0x1801cfc99  movq    rcx, xmm0
0x1801cfc9e  movq    xmm1, rcx
0x1801cfca3  jmp     short loc_1801CFCC8
0x1801cfca5  mov     [rbp+280h+var_1E0], rsi
0x1801cfcac  mov     [rbp+280h+var_1A0], 7
0x1801cfcb3  lea     rdx, [rbp+280h+var_1E0]
0x1801cfcba  mov     ebx, 6
0x1801cfcbf  mov     r8d, esi
0x1801cfcc2  xorps   xmm1, xmm1
0x1801cfcc5  mov     rcx, rsi
0x1801cfcc8  mov     [rbp+280h+var_60], 0FFh
0x1801cfccf  movsx   rax, byte ptr [rdx+40h]
0x1801cfcd4  lea     r9, cs:180000000h
0x1801cfcdb  mov     eax, ds:(jpt_1801CFCE6 - 180000000h)[r9+rax*4]; switch 8 cases
0x1801cfce3  add     rax, r9
0x1801cfce6  jmp     rax; switch jump
0x1801cfce8  mov     dword ptr [rbp+280h+var_A0], r8d; jumptable 00000001801CFCE6 case 0
0x1801cfcef  mov     [rbp+280h+var_60], sil
0x1801cfcf6  jmp     short loc_1801CFD75
0x1801cfcf8  mov     [rbp+280h+var_60], 1; jumptable 00000001801CFCE6 case 1
0x1801cfcff  jmp     short loc_1801CFD6E
0x1801cfd01  movsd   qword ptr [rbp+280h+var_A0], xmm1; jumptable 00000001801CFCE6 case 2
0x1801cfd09  mov     [rbp+280h+var_60], 2
0x1801cfd10  jmp     short loc_1801CFD75
0x1801cfd12  movups  xmm0, xmmword ptr [rdx]; jumptable 00000001801CFCE6 case 3
0x1801cfd15  movaps  [rbp+280h+var_A0], xmm0
0x1801cfd1c  mov     [rbp+280h+var_60], 3
0x1801cfd23  jmp     short loc_1801CFD75
0x1801cfd25  movups  xmm0, xmmword ptr [rdx]; jumptable 00000001801CFCE6 case 4
0x1801cfd28  movaps  [rbp+280h+var_A0], xmm0
0x1801cfd2f  mov     [rbp+280h+var_60], 4
0x1801cfd36  jmp     short loc_1801CFD75
0x1801cfd38  movups  xmm0, xmmword ptr [rdx]; jumptable 00000001801CFCE6 case 5
0x1801cfd3b  movaps  [rbp+280h+var_A0], xmm0
0x1801cfd42  mov     [rbp+280h+var_60], 5
0x1801cfd49  jmp     short loc_1801CFD75
0x1801cfd4b  mov     [rbp+280h+var_68], rsi; jumptable 00000001801CFCE6 case 6
0x1801cfd52  lea     rcx, [rbp+280h+var_A0]
0x1801cfd59  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x1801cfd5e  mov     [rbp+280h+var_60], 6
0x1801cfd65  jmp     short loc_1801CFD75
0x1801cfd67  mov     [rbp+280h+var_60], 7; jumptable 00000001801CFCE6 case 7
0x1801cfd6e  mov     qword ptr [rbp+280h+var_A0], rcx
0x1801cfd75  test    bl, 2
  ... truncated ...
```
