# asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript(asg::SemanticIndex::CheckpointOnCloseOption,std::basic_string_view<char8_t,std::char_traits<char8_t>>,std::span<uchar const,-1>,std::basic_string_view<char8_t,std::char_traits<char8_t>>,asg::Guid,unsigned __int64,asg::SemanticRegistry::SemanticContentType,asg::SemanticIndex::IndexQuantizationPreference,unsigned __int64,std::function<std::optional<asg::SemanticRegistry::VectorSpaceInfo> (asg::Guid const &)> const &,std::basic_string_view<char8_t,std::char_traits<char8_t>>,std::function<void (asg::SemanticIndex::ApplicationDb &,asg::Sqlite::DbConnection &,bool)>)

- ea: `0x1801a21c0`
- end: `0x1801a3630`
- name: `?InitializeDatabaseFromScript@ApplicationDb@SemanticIndex@asg@@CA?AV?$tuple@W4VectorCompatibilityStatus@SemanticIndex@asg@@V?$shared_ptr@VApplicationDb@SemanticIndex@asg@@@std@@UEmbeddingInfo@SemanticRegistry@3@@std@@W4CheckpointOnCloseOption@23@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@V?$span@$$CBE$0?0@5@1UGuid@3@_KW4SemanticContentType@SemanticRegistry@3@W4IndexQuantizationPreference@23@4AEBV?$function@$$A6A?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@AEBUGuid@asg@@@Z@5@1V?$function@$$A6AXAEAVApplicationDb@SemanticIndex@asg@@AEAUDbConnection@Sqlite@3@_N@Z@5@@Z`
- size: `5232`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801a1520`

## callees

- `0x180006410`
- `0x180007830`
- `0x180007de0`
- `0x1800085c0`
- `0x18000cc40`
- `0x18001da60`
- `0x18002b900`
- `0x180078ed0`
- `0x18007b3e0`
- `0x18007d250`
- `0x18007d640`
- `0x1800864e0`
- `0x1801793f0`
- `0x1801795e0`
- `0x1801798a0`
- `0x180179e70`
- `0x18017af80`
- `0x18017b0c0`
- `0x18017fa90`
- `0x180180080`
- `0x180192380`
- `0x18019ab40`
- `0x18019ac70`
- `0x18019b190`
- `0x18019c000`
- `0x18019ca00`
- `0x18019ddb0`
- `0x18019f0a0`
- `0x1801a1e70`
- `0x1801a21c0`
- `0x1801a3d90`
- `0x1801a5a70`
- `0x1801a5d80`
- `0x1801d1320`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f7680`
- `0x1801f97e0`
- `0x180206ec0`
- `0x18022a750`
- `0x18022a790`
- `0x180242860`
- `0x180242ca0`

## string_xrefs

- `0x1801a3509`: `Failed to acquire the database creation and upgrade lock due to an error during the sync object wait operation`
- `0x1801a3512`: `Failed to acquire the database creation and upgrade lock due to an error during sync object creation`
- `0x1801a2832`: `Cannot create quantized database: quantization parameters unknown`
- `0x1801a28b7`: `class std::tuple<enum asg::SemanticIndex::VectorCompatibilityStatus,class std::shared_ptr<class asg::SemanticIndex::ApplicationDb>,struct asg::SemanticRegistry::EmbeddingInfo> __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript(enum asg::SemanticIndex::CheckpointOnCloseOption,class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,struct asg::Guid,u`
- `0x1801a2ba9`: `class std::tuple<enum asg::SemanticIndex::VectorCompatibilityStatus,class std::shared_ptr<class asg::SemanticIndex::ApplicationDb>,struct asg::SemanticRegistry::EmbeddingInfo> __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript(enum asg::SemanticIndex::CheckpointOnCloseOption,class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,struct asg::Guid,u`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript(
        __int64 a1,
        unsigned int a2,
        __int128 *a3,
        __int128 *a4,
        __int64 a5,
        __int128 *a6,
        __int64 a7,
        unsigned int a8,
        int a9,
        volatile signed __int32 *a10,
        __int64 a11,
        __int128 *a12,
        __int64 a13)
{
  int v13; // r12d
  __int128 *v15; // r14
  __int64 v16; // r13
  __int128 *v17; // r15
  __int64 v18; // rcx
  int v19; // esi
  char *v20; // rbx
  __int128 *v21; // rax
  bool *v22; // rax
  __int128 *v23; // rax
  void *v24; // rcx
  void *v25; // rcx
  asg::Sqlite::DbConnection *v26; // rbx
  __int64 v27; // r8
  char v28; // bl
  __m128i v29; // xmm0
  __int128 v30; // xmm0
  __m128i *p_Buf1; // rdx
  int v32; // ebx
  double *v33; // rdx
  int v34; // ebx
  __int64 v35; // rdx
  unsigned int v36; // eax
  __m128i *v37; // rax
  __m128i *v38; // rax
  __int64 v39; // xmm0_8
  int v40; // eax
  __int128 *v41; // xmm0_8
  int v42; // eax
  volatile signed __int32 *v43; // rbx
  volatile signed __int32 *v44; // rbx
  void *v45; // rbx
  void *v46; // rax
  int v47; // ebx
  __int64 v48; // rdx
  __int64 v49; // r12
  __int64 v50; // rcx
  __int64 v51; // rcx
  volatile signed __int32 *v52; // rsi
  volatile signed __int32 *v53; // rax
  volatile signed __int32 *v54; // rbx
  __int64 v55; // rax
  volatile signed __int32 *v56; // rax
  volatile signed __int32 *v57; // rdx
  volatile signed __int32 *v58; // rcx
  __m128i *v59; // rax
  __m128i v60; // xmm6
  unsigned __int64 v61; // r15
  unsigned int v62; // eax
  __m128i *v63; // rax
  __int64 v64; // rdx
  volatile signed __int32 *v65; // rsi
  __int64 v66; // rcx
  __int64 v68; // r8
  __int64 v69; // rdx
  const char *v70; // rdx
  __int64 v71; // rax
  _BYTE v72[32]; // [rsp+0h] [rbp-868h] BYREF
  bool v73; // [rsp+40h] [rbp-828h]
  bool v74[3]; // [rsp+41h] [rbp-827h] BYREF
  int v75; // [rsp+44h] [rbp-824h]
  int v76; // [rsp+48h] [rbp-820h] BYREF
  int VectorCompatibility; // [rsp+50h] [rbp-818h]
  unsigned int CurrentTableGroup; // [rsp+58h] [rbp-810h]
  __int128 v79; // [rsp+60h] [rbp-808h] BYREF
  const char *v80; // [rsp+70h] [rbp-7F8h]
  int v81; // [rsp+80h] [rbp-7E8h]
  int v82; // [rsp+84h] [rbp-7E4h]
  volatile signed __int32 *v83; // [rsp+88h] [rbp-7E0h]
  __int128 v84; // [rsp+90h] [rbp-7D8h]
  __int128 Buf2; // [rsp+A0h] [rbp-7C8h] BYREF
  const char *v86; // [rsp+B0h] [rbp-7B8h]
  __int128 *v87; // [rsp+D0h] [rbp-798h]
  __int64 v88; // [rsp+D8h] [rbp-790h]
  __int128 *v89; // [rsp+E0h] [rbp-788h]
  __int64 v90; // [rsp+E8h] [rbp-780h]
  asg::Sqlite::DbTransaction *v91[2]; // [rsp+F0h] [rbp-778h] BYREF
  _QWORD *v92; // [rsp+100h] [rbp-768h]
  __int64 v93; // [rsp+108h] [rbp-760h]
  __int128 *v94; // [rsp+110h] [rbp-758h]
  _QWORD v95[7]; // [rsp+120h] [rbp-748h] BYREF
  char *v96; // [rsp+158h] [rbp-710h]
  asg::Sqlite::DbTransaction **v97; // [rsp+160h] [rbp-708h]
  const asg::Sqlite::DbException *v98; // [rsp+180h] [rbp-6E8h] BYREF
  double v99[7]; // [rsp+188h] [rbp-6E0h] BYREF
  double *v100; // [rsp+1C0h] [rbp-6A8h]
  char v101; // [rsp+1C8h] [rbp-6A0h]
  _BYTE pExceptionObject[24]; // [rsp+1D0h] [rbp-698h] BYREF
  _BYTE v103[64]; // [rsp+1E8h] [rbp-680h] BYREF
  _BYTE v104[64]; // [rsp+228h] [rbp-640h] BYREF
  __int128 *v105; // [rsp+268h] [rbp-600h]
  __int64 v106; // [rsp+270h] [rbp-5F8h]
  char v107; // [rsp+278h] [rbp-5F0h] BYREF
  bool v108[4]; // [rsp+27Ch] [rbp-5ECh] BYREF
  __int128 v109; // [rsp+280h] [rbp-5E8h] BYREF
  __int64 v110; // [rsp+290h] [rbp-5D8h] BYREF
  __int128 v111; // [rsp+2A0h] [rbp-5C8h] BYREF
  __int64 v112; // [rsp+2B0h] [rbp-5B8h] BYREF
  int v113; // [rsp+2B8h] [rbp-5B0h]
  asg::Sqlite::DbTransaction *v114[2]; // [rsp+2C0h] [rbp-5A8h] BYREF
  __int128 *v115; // [rsp+2D0h] [rbp-598h] BYREF
  int v116; // [rsp+2D8h] [rbp-590h]
  __m128i v117; // [rsp+2E0h] [rbp-588h] BYREF
  __m128i v118; // [rsp+2F0h] [rbp-578h]
  __m128i v119; // [rsp+300h] [rbp-568h] BYREF
  char v120; // [rsp+320h] [rbp-548h]
  __m128i Buf1; // [rsp+330h] [rbp-538h] BYREF
  __m128i v122; // [rsp+340h] [rbp-528h]
  __m128i v123; // [rsp+350h] [rbp-518h] BYREF
  __int64 v124; // [rsp+368h] [rbp-500h]
  char v125; // [rsp+370h] [rbp-4F8h]
  __int128 v126; // [rsp+380h] [rbp-4E8h] BYREF
  __int128 v127; // [rsp+390h] [rbp-4D8h] BYREF
  __int64 v128; // [rsp+3A0h] [rbp-4C8h]
  unsigned __int64 v129; // [rsp+3A8h] [rbp-4C0h]
  __int64 v130; // [rsp+3C8h] [rbp-4A0h]
  __int64 v131; // [rsp+3D0h] [rbp-498h] BYREF
  void *Block; // [rsp+3D8h] [rbp-490h]
  __int128 v133; // [rsp+3E0h] [rbp-488h] BYREF
  __int128 v134; // [rsp+3F0h] [rbp-478h]
  __int128 v135; // [rsp+400h] [rbp-468h]
  _QWORD v136[9]; // [rsp+410h] [rbp-458h] BYREF
  char v137; // [rsp+458h] [rbp-410h]
  const char *v138; // [rsp+460h] [rbp-408h]
  __int128 v139; // [rsp+468h] [rbp-400h]
  __int64 v140; // [rsp+47Ch] [rbp-3ECh]
  int v141; // [rsp+484h] [rbp-3E4h]
  char v142; // [rsp+4A8h] [rbp-3C0h]
  const char *v143; // [rsp+4B0h] [rbp-3B8h]
  __int64 v144; // [rsp+4B8h] [rbp-3B0h]
  char v145; // [rsp+4C8h] [rbp-3A0h]
  char v146; // [rsp+4F8h] [rbp-370h]
  const char *v147; // [rsp+500h] [rbp-368h]
  __int128 v148; // [rsp+508h] [rbp-360h]
  char v149; // [rsp+548h] [rbp-320h]
  const char *v150; // [rsp+550h] [rbp-318h]
  int v151; // [rsp+558h] [rbp-310h]
  char v152; // [rsp+598h] [rbp-2D0h]
  const char *v153; // [rsp+5A0h] [rbp-2C8h]
  unsigned int v154; // [rsp+5A8h] [rbp-2C0h]
  char v155; // [rsp+5E8h] [rbp-280h]
  const char *v156; // [rsp+5F0h] [rbp-278h]
  char v157[72]; // [rsp+5F8h] [rbp-270h] BYREF
  const char *v158; // [rsp+640h] [rbp-228h]
  char v159[72]; // [rsp+648h] [rbp-220h] BYREF
  _DWORD v160[46]; // [rsp+690h] [rbp-1D8h] BYREF
  char v161; // [rsp+748h] [rbp-120h]
  _DWORD v162[29]; // [rsp+750h] [rbp-118h] BYREF
  int v163; // [rsp+7C4h] [rbp-A4h]
  char v164; // [rsp+808h] [rbp-60h]

  v87 = a4;
  v15 = a3;
  v89 = a3;
  v16 = a1;
  v93 = a1;
  CurrentTableGroup = a2;
  v115 = a3;
  v94 = a4;
  *(_QWORD *)&v84 = a5;
  v105 = a6;
  v83 = a10;
  v90 = a11;
  v17 = a12;
  *(_QWORD *)&v111 = a12;
  v88 = a13;
  v106 = a13;
  v82 = 0;
  VectorCompatibility = 3;
  v81 = 3;
  v73 = 0;
  v74[0] = 0;
  BYTE4(v110) = 0;
  LOBYTE(v13) = 0;
  v75 = v13;
  LOBYTE(v113) = 0;
  v92 = (_QWORD *)(a11 + 56);
  v18 = *(_QWORD *)(a11 + 56);
  if ( !v18 )
    std::_Xbad_function_call();
  (*(void (__fastcall **)(__int64, _DWORD *, __int128 *))(*(_QWORD *)v18 + 16LL))(v18, v162, a6);
  if ( !v164 )
  {
    v68 = asg::GuidToString(&Buf1, a6);
    v69 = std::operator+<char>(&v117, "Unable to get info for vector space id: ", v68);
    asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v69);
    throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
  }
  v117 = 0;
  v118 = 0u;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v117);
  asg::SemanticIndex::GlobalMutex::Create(&v131, &v117, 0xFFFFFFFF);
  if ( !Block )
  {
    v70 = "Failed to acquire the database creation and upgrade lock";
    switch ( (_DWORD)v131 )
    {
      case 1:
        v70 = "Failed to acquire the database creation and upgrade lock due to timeout";
        break;
      case 2:
        v70 = "Failed to acquire the database creation and upgrade lock due to an error during sync object creation";
        break;
      case 3:
        v70 = "Failed to acquire the database creation and upgrade lock due to an error during the sync object wait operation";
        break;
    }
    asg::SemanticIndex::SemanticIndexException::SemanticIndexException(v103, v70, 23);
    throw (asg::SemanticIndex::SemanticIndexException *)v103;
  }
  v76 = 2;
  v109 = *a12;
  v127 = *v15;
  asg::Sqlite::DbConnection::TryFileExists(v108, &v127, (__int64)&v109);
  if ( v108[1] )
  {
    if ( v108[0] )
    {
      v19 = 6;
      goto LABEL_26;
    }
    v73 = 1;
    v19 = 10;
LABEL_9:
    std::basic_string<char8_t>::basic_string<char8_t>(&Buf1, v15, v74);
    v20 = aShm_0;
    do
    {
      std::operator+<char8_t>(&v127, &Buf1, v20);
      v21 = &v127;
      if ( v129 > 0xF )
        v21 = (__int128 *)v127;
      *(_QWORD *)&v109 = v21;
      *((_QWORD *)&v109 + 1) = v128;
      Buf2 = *v17;
      v79 = v109;
      v22 = asg::Sqlite::DbConnection::TryFileExists(v74, &v79, (__int64)&Buf2);
      if ( v22[1] && *v22 )
      {
        v23 = &v127;
        if ( v129 > 0xF )
          v23 = (__int128 *)v127;
        *(_QWORD *)&v111 = v23;
        *((_QWORD *)&v111 + 1) = v128;
        Buf2 = *v17;
        v79 = v111;
        asg::Sqlite::DbConnection::TryRemoveFile((bool *)&v76, &v79, (__int64)&Buf2);
      }
      if ( v129 > 0xF )
      {
        v24 = (void *)v127;
        if ( v129 + 1 >= 0x1000 )
        {
          v24 = *(void **)(v127 - 8);
          if ( (unsigned __int64)(v127 - (_QWORD)v24 - 8) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        operator delete(v24);
      }
      v20 += 32;
    }
    while ( v20 != aShm_1 );
    if ( v122.m128i_i64[1] > 0xFuLL )
    {
      v25 = (void *)Buf1.m128i_i64[0];
      if ( (unsigned __int64)(v122.m128i_i64[1] + 1) >= 0x1000 )
      {
        v25 = *(void **)(Buf1.m128i_i64[0] - 8);
        if ( (unsigned __int64)(Buf1.m128i_i64[0] - (_QWORD)v25 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v25);
    }
    goto LABEL_26;
  }
  try
  {
    v109 = 0;
    v127 = *a12;
    v79 = *a4;
    Buf2 = *v15;
    asg::Sqlite::DbConnection::Create(
      (unsigned int)&v109,
      (unsigned int)&Buf2,
      (unsigned int)&v79,
      (unsigned int)&v127,
      0,
      1);
    v19 = 6;
    v76 = 6;
    std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(&v109);
  }
  catch ( const asg::Sqlite::DbException *v98 )
  {
    if ( *((_DWORD *)v98 + 11) == 14 )
    {
      v74[0] = 1;
      v76 |= 8u;
    }
    else
    {
      v76 |= 4u;
    }
    v73 = v74[0];
    v19 = v76;
    v16 = v93;
    v15 = v115;
    v17 = (__int128 *)v111;
    VectorCompatibility = v81;
    v89 = v115;
    v75 = (unsigned __int8)v113;
    v87 = v94;
    v88 = v106;
    if ( !v74[0] )
      goto LABEL_26;
    goto LABEL_9;
  }
LABEL_26:
  v126 = 0;
  Buf2 = *v17;
  v79 = *v87;
  v127 = *v15;
  asg::Sqlite::DbConnection::Create(
    (unsigned int)&v126,
    (unsigned int)&v127,
    (unsigned int)&v79,
    (unsigned int)&Buf2,
    v19,
    200);
  v26 = (asg::Sqlite::DbConnection *)v126;
  asg::Sqlite::DbConnection::CreateScalarFunction(
    (asg::Sqlite::DbConnection *)v126,
    (__int64)asg::SemanticIndex::sqlite3CosineDistance,
    0,
    0);
  asg::Sqlite::DbConnection::CreateScalarFunction(v26, (__int64)asg::SemanticIndex::sqliteQuantizeEmbedding, 0, 0);
  asg::Sqlite::DbConnection::CreateScalarFunction(v26, (__int64)asg::SemanticIndex::sqliteDequantizeEmbedding, 0, 0);
  *(_OWORD *)v114 = 0;
  LOBYTE(v27) = 1;
  asg::Sqlite::DbConnection::BeginTransaction(v126, v114, v27);
  if ( v73 )
  {
    v112 = *(_QWORD *)&v162[27];
    v28 = v163;
    v75 = v163;
    v113 = v163;
    if ( !(_BYTE)v163 || a9 == 2 )
    {
      if ( a9 == 1 )
      {
        v118.m128i_i8[8] = 0;
        Buf1 = v117;
        v29.m128i_i64[1] = v118.m128i_i64[1];
        v29.m128i_i64[0] = v118.m128i_i64[0];
        v118 = v29;
        v122 = v29;
        asg::details::_asg_Log<std::integral_constant<bool,0>>(
          &v117,
          &Buf1,
          3,
          L"Cannot create quantized database: quantization parameters unknown");
        if ( v119.m128i_i8[0] )
          std::basic_string<char16_t>::_Tidy_deallocate(&v117);
      }
      LODWORD(v111) = 1;
    }
    else
    {
      LODWORD(v111) = 0;
    }
    BYTE4(v111) = 1;
    v110 = v111;
    *(_QWORD *)&Buf2 = 0x16000003F6LL;
    *((_QWORD *)&Buf2 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
    v86 = "class std::tuple<enum asg::SemanticIndex::VectorCompatibilityStatus,class std::shared_ptr<class asg::SemanticI"
          "ndex::ApplicationDb>,struct asg::SemanticRegistry::EmbeddingInfo> __cdecl asg::SemanticIndex::ApplicationDb::I"
          "nitializeDatabaseFromScript(enum asg::SemanticIndex::CheckpointOnCloseOption,class std::basic_string_view<char"
          "8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,class std::basic_string_view<c"
          "har8_t,struct std::char_traits<char8_t> >,struct asg::Guid,unsigned __int64,enum asg::SemanticRegistry::Semant"
          "icContentType,enum asg::SemanticIndex::IndexQuantizationPreference,unsigned __int64,const class std::function<"
          "class std::optional<class asg::SemanticRegistry::VectorSpaceInfo> __cdecl(struct asg::Guid const &)> &,class s"
          "td::basic_string_view<char8_t,struct std::char_traits<char8_t> >,class std::function<void __cdecl(class asg::S"
          "emanticIndex::ApplicationDb &,struct asg::Sqlite::DbConnection &,bool)>)";
    v136[0] = ":schema_version";
    v136[1] = asg::SemanticIndex::DbSchema::LatestSchemaVersion;
    v137 = 1;
    v30 = *(_OWORD *)asg::NewGuid(&Buf2);
    v138 = ":db_id";
    v139 = v30;
    v142 = 3;
    v143 = ":dimension";
    v144 = a7;
    v146 = 1;
    v147 = ":vector_space_id";
    v148 = *v105;
    v149 = 3;
    if ( !BYTE4(v110) )
      std::_Throw_bad_optional_access();
    v150 = ":element_type";
    v151 = v110;
    v152 = 0;
    v153 = ":content_type";
    v154 = a8;
    v155 = 0;
    if ( v28 )
    {
      *(double *)v117.m128i_i64 = *(float *)&v112;
      v120 = 2;
      p_Buf1 = &v117;
      v32 = 33;
    }
    else
    {
      Buf1.m128i_i64[0] = 0;
      v125 = 7;
      p_Buf1 = &Buf1;
      v32 = 34;
    }
    v156 = ":quantization_scale";
    asg::Sqlite::DbValue::DbValue(v157, p_Buf1);
    if ( (_BYTE)v75 )
    {
      v99[0] = *((float *)&v112 + 1);
      v101 = 2;
      v33 = v99;
      v34 = v32 | 4;
    }
    else
    {
      v95[0] = 0;
      LOBYTE(v97) = 7;
      v33 = (double *)v95;
      v34 = v32 | 8;
    }
    v82 = v34;
    v158 = ":quantization_zero_point";
    asg::Sqlite::DbValue::DbValue(v159, v33);
    *(_QWORD *)&v109 = v136;
    *((_QWORD *)&v109 + 1) = 8;
    `eh vector destructor iterator'(
      v136,
      0x50u,
      8u,
      std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
    if ( (v34 & 8) != 0 )
    {
      LOBYTE(v34) = v34 & 0xF7;
      std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(v95);
    }
    if ( (v34 & 4) != 0 )
    {
      LOBYTE(v34) = v34 & 0xFB;
      switch ( v101 )
      {
        case 0:
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 7:
          break;
        case 6:
          if ( v100 )
          {
            LOBYTE(v35) = v100 != v99;
            (*(void (__fastcall **)(double *, __int64))(*(_QWORD *)v100 + 32LL))(v100, v35);
            v100 = 0;
          }
          break;
      }
    }
    if ( (v34 & 2) != 0 )
    {
      LOBYTE(v34) = v34 & 0xFD;
      std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&Buf1);
    }
    if ( (v34 & 1) != 0 )
      std::_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>::~_Variant_destroy_layer_<int,__int64,double,asg::Guid,std::u8string_view,asg::Sqlite::DbBlobView,asg::Sqlite::DbInListView,std::nullptr_t>(&v117);
    Buf2 = v109;
    v79 = *(_OWORD *)v84;
    asg::Sqlite::DbTransaction::ExecuteNonQuery(v114[0]);
  }
  try
  {
    v109 = 0u;
    *(_QWORD *)&v84 = "SELECT schema_version FROM si_db_info";
    *((_QWORD *)&v84 + 1) = 37;
    Buf2 = 0u;
    v79 = v84;
    v36 = asg::Sqlite::DbTransaction::ExecuteSingleValueQuery<int>(v114[0], &v79, &Buf2, 0);
  }
  catch ( ... )
  {
    Buf2 = *(_OWORD *)std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(&v127);
    v79 = *(_OWORD *)std::u8string_view::basic_string_view<char8_t,std::char_traits<char8_t>>(
                       &v109,
                       "Failed to read schema version from database");
    v71 = asg::Sqlite::DbException::DbException(
            (unsigned int)v72 + 288,
            (unsigned int)v72 + 96,
            0,
            0,
            (__int64)&Buf2,
            0);
    std::throw_with_nested<asg::Sqlite::DbException>(v71);
  }
  if ( v36 != asg::SemanticIndex::DbSchema::LatestSchemaVersion )
    asg::SemanticIndex::ApplicationDb::UpgradeToLatestSchema((asg::SemanticIndex::DbSchema *)v36, v114[0]);
  v107 = 0;
  if ( !v73 )
  {
    v37 = (__m128i *)asg::SemanticIndex::ApplicationDb::ReadEmbeddingInfo(&Buf2, v114[0], 0);
    Buf1 = *v37;
    v122 = v37[1];
    v123 = v37[2];
    v38 = (__m128i *)asg::SemanticIndex::ApplicationDb::ReadEmbeddingInfo(&Buf2, v114[0], 1);
    v117 = *v38;
    v118 = v38[1];
    v119 = v38[2];
    if ( !*v92 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(_QWORD, _QWORD *, __m128i *))(*(_QWORD *)*v92 + 16LL))(*v92, v136, &Buf1);
    if ( !*v92 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(_QWORD, _DWORD *, __m128i *))(*(_QWORD *)*v92 + 16LL))(*v92, v160, &v117);
    if ( v145 )
    {
      v39 = v140;
      v40 = v141;
    }
    else
    {
      BYTE8(v84) = 0;
      v39 = v84;
      v40 = DWORD2(v84);
    }
    *(_QWORD *)&v111 = v39;
    DWORD2(v111) = v40;
    if ( v161 )
    {
      v41 = *(__int128 **)&v160[27];
      v42 = v160[29];
    }
    else
    {
      BYTE8(v84) = 0;
      v41 = (__int128 *)v84;
      v42 = DWORD2(v84);
    }
    v115 = v41;
    v116 = v42;
    v95[0] = &Buf1;
    v95[1] = &v123;
    v95[2] = &v111;
    v95[3] = &v117;
    v95[4] = &v119;
    v95[5] = &v115;
    v95[6] = &v110;
    v96 = &v107;
    v97 = v114;
    if ( a9 == 1 )
    {
      asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript_::_57_::_lambda_1_::operator()(v95, 0);
    }
    else if ( a9 == 2 )
    {
      asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript_::_57_::_lambda_1_::operator()(v95, 1);
    }
    else
    {
      *(_QWORD *)&Buf2 = 0x1500000497LL;
      *((_QWORD *)&Buf2 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
      v86 = "class std::tuple<enum asg::SemanticIndex::VectorCompatibilityStatus,class std::shared_ptr<class asg::Semanti"
            "cIndex::ApplicationDb>,struct asg::SemanticRegistry::EmbeddingInfo> __cdecl asg::SemanticIndex::ApplicationD"
            "b::InitializeDatabaseFromScript(enum asg::SemanticIndex::CheckpointOnCloseOption,class std::basic_string_vie"
            "w<char8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,class std::basic_strin"
            "g_view<char8_t,struct std::char_traits<char8_t> >,struct asg::Guid,unsigned __int64,enum asg::SemanticRegist"
            "ry::SemanticContentType,enum asg::SemanticIndex::IndexQuantizationPreference,unsigned __int64,const class st"
            "d::function<class std::optional<class asg::SemanticRegistry::VectorSpaceInfo> __cdecl(struct asg::Guid const"
            " &)> &,class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,class std::function<void __cd"
            "ecl(class asg::SemanticIndex::ApplicationDb &,struct asg::Sqlite::DbConnection &,bool)>)";
      if ( a9 )
      {
        v79 = Buf2;
        v80 = v86;
        asg::details::AsgAssertFail(&v79);
      }
      BYTE4(v110) = 0;
    }
    if ( v161 )
      (**(void (__fastcall ***)(_DWORD *, _QWORD))v160)(v160, 0);
    if ( v145 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v136[0])(v136, 0);
  }
  asg::Sqlite::DbTransaction::Commit(v114[0]);
  if ( v107 )
  {
    *(_QWORD *)&v109 = "VACUUM";
    *((_QWORD *)&v109 + 1) = 6;
    Buf2 = v109;
    asg::Sqlite::DbConnection::Exec((asg::Sqlite::DbConnection *)v126);
  }
  v43 = (volatile signed __int32 *)v114[1];
  if ( v114[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v114[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
      if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
    }
  }
  v44 = (volatile signed __int32 *)*((_QWORD *)&v126 + 1);
  if ( *((_QWORD *)&v126 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v126 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
      if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
    }
  }
  v45 = Block;
  if ( Block )
  {
    asg::SemanticIndex::GlobalMutex::~GlobalMutex((asg::SemanticIndex::GlobalMutex *)Block);
    operator delete(v45);
  }
  v109 = 0;
  v46 = operator new(0x120u);
  v47 = (int)v46;
  *(_QWORD *)&v84 = v46;
  if ( v46 )
  {
    memset(v46, 0, 0x120u);
    v124 = 0;
    v49 = v88;
    v50 = *(_QWORD *)(v88 + 56);
    if ( v50 )
    {
      if ( v50 != v88 )
      {
        v124 = *(_QWORD *)(v88 + 56);
        goto LABEL_91;
      }
      v124 = (*(__int64 (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v50 + 8LL))(v50, &Buf1);
      v51 = *(_QWORD *)(v49 + 56);
      if ( v51 )
      {
        LOBYTE(v48) = v51 != v49;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 32LL))(v51, v48);
LABEL_91:
        *(_QWORD *)(v49 + 56) = 0;
      }
    }
    Buf2 = *v17;
    v79 = *v87;
    v127 = *v89;
    LOBYTE(v48) = 1;
    v52 = (volatile signed __int32 *)asg::SemanticIndex::ApplicationDb::ApplicationDb(
                                       v47,
                                       v48,
                                       CurrentTableGroup,
                                       (unsigned int)&v127,
                                       (__int64)&v79,
                                       (__int64)&Buf2,
                                       (__int64)v83,
                                       (__int64)&Buf1);
    goto LABEL_94;
  }
  v52 = 0;
  v49 = v88;
LABEL_94:
  v83 = v52;
  v53 = (volatile signed __int32 *)operator new(0x18u);
  v54 = v53;
  v83 = v53;
  if ( v53 )
  {
    *(_OWORD *)v53 = 0;
    *((_DWORD *)v53 + 2) = 1;
    *((_DWORD *)v53 + 3) = 1;
    *(_QWORD *)v53 = &std::_Ref_count<asg::SemanticIndex::ApplicationDb>::`vftable';
    *((_QWORD *)v53 + 2) = v52;
  }
  else
  {
    v54 = 0;
  }
  *(_QWORD *)&v109 = v52;
  *((_QWORD *)&v109 + 1) = v54;
  if ( v52 )
  {
    v55 = *((_QWORD *)v52 + 1);
    if ( !v55 || !*(_DWORD *)(v55 + 8) )
    {
      if ( v54 )
      {
        _InterlockedIncrement(v54 + 2);
        v56 = v52;
        v57 = v54;
        _InterlockedIncrement(v54 + 3);
      }
      else
      {
        v56 = 0;
        v57 = 0;
      }
      *(_QWORD *)v52 = v56;
      v58 = (volatile signed __int32 *)*((_QWORD *)v52 + 1);
      *((_QWORD *)v52 + 1) = v57;
      if ( v58 && _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      if ( v54 )
      {
        if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
    }
  }
  *(_OWORD *)v91 = 0;
  v130 = 0;
  v96 = 0;
  asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(v52, v91, v95, &v127);
  CurrentTableGroup = asg::SemanticIndex::ApplicationDb::GetCurrentTableGroup(v91[0]);
  v59 = (__m128i *)asg::SemanticIndex::ApplicationDb::ReadEmbeddingInfo(&v117, v91[0], CurrentTableGroup);
  Buf1 = *v59;
  v60 = v59[1];
  v122 = v60;
  v123 = v59[2];
  v133 = *v105;
  *(_QWORD *)&v134 = a7;
  v61 = _mm_srli_si128(v60, 8).m128i_u64[0];
  v62 = v61;
  if ( BYTE4(v110) )
    v62 = v110;
  *((_QWORD *)&v134 + 1) = __PAIR64__(a8, v62);
  v63 = (__m128i *)&v112;
  if ( !(_BYTE)v75 )
    v63 = &v123;
  *(_QWORD *)&v135 = v63->m128i_i64[0];
  DWORD2(v135) = v63->m128i_i32[2];
  Buf2 = `asg::EmptyGuid'::`2'::empty;
  if ( !memcmp(&Buf1, &Buf2, 0x10u) && !v60.m128i_i64[0] && v61 == -1 )
  {
    if ( !BYTE4(v110) )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        v104,
        "elementType must be provided for a new database",
        14);
      throw (asg::SemanticIndex::SemanticIndexException *)v104;
    }
    asg::SemanticIndex::ApplicationDb::UpdateEmbeddingInfo(v91[0], CurrentTableGroup, &v133);
  }
  else
  {
    if ( !v73 )
      VectorCompatibility = asg::SemanticIndex::ApplicationDb::GetVectorCompatibility(&v133, &Buf1, v90);
    *((_BYTE *)v91[0] + 500) = 1;
  }
  asg::Sqlite::DbTransaction::Commit(v91[0]);
  *(_OWORD *)v16 = v133;
  *(_OWORD *)(v16 + 16) = v134;
  *(_OWORD *)(v16 + 32) = v135;
  *(_QWORD *)(v16 + 48) = 0;
  *(_QWORD *)(v16 + 56) = 0;
  if ( v54 )
    _InterlockedIncrement(v54 + 2);
  *(_QWORD *)(v16 + 48) = v52;
  *(_QWORD *)(v16 + 56) = v54;
  *(_DWORD *)(v16 + 64) = VectorCompatibility;
  v65 = (volatile signed __int32 *)v91[1];
  if ( v91[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v91[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
      if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
    }
  }
  if ( v54 )
  {
    if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
      if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
    }
  }
  if ( v164 )
    (**(void (__fastcall ***)(_DWORD *, _QWORD))v162)(v162, 0);
  v66 = *(_QWORD *)(v49 + 56);
  if ( v66 )
  {
    LOBYTE(v64) = v66 != v49;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 32LL))(v66, v64);
    *(_QWORD *)(v49 + 56) = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x1801a21c0  push    rbx
0x1801a21c2  push    rsi
0x1801a21c3  push    rdi
0x1801a21c4  push    r12
0x1801a21c6  push    r13
0x1801a21c8  push    r14
0x1801a21ca  push    r15
0x1801a21cc  sub     rsp, 830h
0x1801a21d3  movaps  [rsp+868h+var_48], xmm6
0x1801a21db  mov     rax, cs:__security_cookie
0x1801a21e2  xor     rax, rsp
0x1801a21e5  mov     [rsp+868h+var_58], rax
0x1801a21ed  mov     rsi, r9
0x1801a21f0  mov     [rsp+868h+var_798], r9
0x1801a21f8  mov     r14, r8
0x1801a21fb  mov     [rsp+868h+var_788], r8
0x1801a2203  mov     r13, rcx
0x1801a2206  mov     [rsp+868h+var_760], rcx
0x1801a220e  mov     [rsp+868h+var_810], edx
0x1801a2212  mov     [rsp+868h+var_598], r8
0x1801a221a  mov     [rsp+868h+var_758], r9
0x1801a2222  mov     rax, [rsp+868h+arg_20]
0x1801a222a  mov     qword ptr [rsp+868h+var_7D8], rax
0x1801a2232  mov     rbx, [rsp+868h+arg_28]
0x1801a223a  mov     [rsp+868h+var_600], rbx
0x1801a2242  mov     rax, [rsp+868h+arg_48]
0x1801a224a  mov     [rsp+868h+var_7E0], rax
0x1801a2252  mov     rcx, [rsp+868h+arg_50]
0x1801a225a  mov     [rsp+868h+var_780], rcx
0x1801a2262  mov     r15, [rsp+868h+arg_58]
0x1801a226a  mov     qword ptr [rsp+868h+var_5C8], r15
0x1801a2272  mov     rax, [rsp+868h+arg_60]
0x1801a227a  mov     [rsp+868h+var_790], rax
0x1801a2282  mov     [rsp+868h+var_5F8], rax
0x1801a228a  xor     edi, edi
0x1801a228c  mov     [rsp+868h+var_7E4], edi
0x1801a2293  mov     eax, 3
0x1801a2298  mov     [rsp+868h+var_818], eax
0x1801a229c  mov     [rsp+868h+var_7E8], eax
0x1801a22a3  xor     al, al
0x1801a22a5  mov     [rsp+868h+var_828], al
0x1801a22a9  mov     [rsp+868h+var_827], al
0x1801a22ad  mov     [rsp+868h+var_5D4], al
0x1801a22b4  xor     r12b, r12b
0x1801a22b7  mov     [rsp+868h+var_824], r12d
0x1801a22bc  mov     byte ptr [rsp+868h+var_5B0], r12b
0x1801a22c4  lea     rax, [rcx+38h]
0x1801a22c8  mov     [rsp+868h+var_768], rax
0x1801a22d0  mov     rcx, [rax]
0x1801a22d3  test    rcx, rcx
0x1801a22d6  jz      loc_1801A3498
0x1801a22dc  mov     rax, [rcx]
0x1801a22df  mov     r8, rbx
0x1801a22e2  lea     rdx, [rsp+868h+var_118]
0x1801a22ea  call    qword ptr [rax+10h]
0x1801a22ed  nop
0x1801a22ee  cmp     [rsp+868h+var_60], 0
0x1801a22f6  jz      loc_1801A349E
0x1801a22fc  xorps   xmm0, xmm0
0x1801a22ff  movups  [rsp+868h+var_588], xmm0
0x1801a2307  mov     qword ptr [rsp+868h+var_578], rdi
0x1801a230f  mov     qword ptr [rsp+868h+var_578+8], rdi
0x1801a2317  mov     r8d, 1Ah
0x1801a231d  lea     rdx, aDatabaseCreati; "Database_CreationOrUpgrade"
0x1801a2324  lea     rcx, [rsp+868h+var_588]
0x1801a232c  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a2331  mov     r8d, 0FFFFFFFFh
0x1801a2337  lea     rdx, [rsp+868h+var_588]
0x1801a233f  lea     rcx, [rsp+868h+var_498]
0x1801a2347  call    ?Create@GlobalMutex@SemanticIndex@asg@@SA?AV?$tuple@V?$unique_ptr@VGlobalMutex@SemanticIndex@asg@@U?$default_delete@VGlobalMutex@SemanticIndex@asg@@@std@@@std@@W4CreateErrorCode@GlobalMutex@SemanticIndex@asg@@@std@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@5@I@Z; asg::SemanticIndex::GlobalMutex::Create(std::basic_string<char16_t>,uint)
0x1801a234c  nop
0x1801a234d  cmp     [rsp+868h+Block], 0
0x1801a2356  jz      loc_1801A34EC
0x1801a235c  mov     [rsp+868h+var_820], 2
0x1801a2364  movups  xmm0, xmmword ptr [r15]
0x1801a2368  movaps  [rsp+868h+var_5E8], xmm0
0x1801a2370  movups  xmm1, xmmword ptr [r14]
0x1801a2374  movaps  [rsp+868h+var_4D8], xmm1
0x1801a237c  lea     r8, [rsp+868h+var_5E8]
0x1801a2384  lea     rdx, [rsp+868h+var_4D8]
0x1801a238c  lea     rcx, [rsp+868h+var_5EC]
0x1801a2394  call    ?TryFileExists@DbConnection@Sqlite@asg@@SA?AV?$optional@_N@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@0@Z; asg::Sqlite::DbConnection::TryFileExists(std::u8string_view,std::u8string_view)
0x1801a2399  cmp     [rsp+868h+var_5EB], 0
0x1801a23a1  jz      short loc_1801A23C6
0x1801a23a3  cmp     [rsp+868h+var_5EC], 0
0x1801a23ab  jz      short loc_1801A23B7
0x1801a23ad  mov     esi, 6
0x1801a23b2  jmp     loc_1801A264F
0x1801a23b7  mov     [rsp+868h+var_828], 1
0x1801a23bc  mov     esi, 0Ah
0x1801a23c1  jmp     loc_1801A24AD
0x1801a23c6  xorps   xmm0, xmm0
0x1801a23c9  movups  [rsp+868h+var_5E8], xmm0
0x1801a23d1  movups  xmm1, xmmword ptr [r15]
0x1801a23d5  movaps  [rsp+868h+var_4D8], xmm1
0x1801a23dd  movups  xmm0, xmmword ptr [rsi]
0x1801a23e0  movaps  [rsp+868h+var_808], xmm0
0x1801a23e5  movups  xmm1, xmmword ptr [r14]
0x1801a23e9  movaps  [rsp+868h+Buf2], xmm1
0x1801a23f1  mov     [rsp+868h+var_840], 1
0x1801a23fa  mov     dword ptr [rsp+868h+Reserved], edi
0x1801a23fe  lea     r9, [rsp+868h+var_4D8]
0x1801a2406  lea     r8, [rsp+868h+var_808]
0x1801a240b  lea     rdx, [rsp+868h+Buf2]
0x1801a2413  lea     rcx, [rsp+868h+var_5E8]
0x1801a241b  call    ?Create@DbConnection@Sqlite@asg@@SA?AV?$shared_ptr@UDbConnection@Sqlite@asg@@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@V?$span@$$CBE$0?0@5@0W4CreateDisposition@23@_K@Z; asg::Sqlite::DbConnection::Create(std::u8string_view,std::span<uchar const,-1>,std::u8string_view,asg::Sqlite::CreateDisposition,unsigned __int64)
0x1801a2420  mov     esi, 6
0x1801a2425  mov     [rsp+868h+var_820], esi
0x1801a2429  lea     rcx, [rsp+868h+var_5E8]
0x1801a2431  call    ??1?$shared_ptr@V?$vector@UGuid@asg@@V?$allocator@UGuid@asg@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(void)
0x1801a2436  nop
0x1801a2437  jmp     loc_1801A264F
0x1801a243c  movzx   r12d, [rsp+868h+var_827]
0x1801a2442  mov     [rsp+868h+var_828], r12b
0x1801a2447  xor     edi, edi
0x1801a2449  mov     eax, [rsp+868h+var_7E8]
0x1801a2450  mov     esi, [rsp+868h+var_820]
0x1801a2454  mov     r13, [rsp+868h+var_760]
0x1801a245c  mov     r14, [rsp+868h+var_598]
0x1801a2464  mov     r15, qword ptr [rsp+868h+var_5C8]
0x1801a246c  mov     [rsp+868h+var_818], eax
0x1801a2470  mov     [rsp+868h+var_788], r14
0x1801a2478  movzx   eax, byte ptr [rsp+868h+var_5B0]
0x1801a2480  mov     [rsp+868h+var_824], eax
0x1801a2484  mov     rax, [rsp+868h+var_758]
0x1801a248c  mov     [rsp+868h+var_798], rax
0x1801a2494  mov     rax, [rsp+868h+var_5F8]
0x1801a249c  mov     [rsp+868h+var_790], rax
0x1801a24a4  test    r12b, r12b
0x1801a24a7  jz      loc_1801A264F
0x1801a24ad  lea     r8, [rsp+868h+var_827]
0x1801a24b2  mov     rdx, r14
0x1801a24b5  lea     rcx, [rsp+868h+Buf1]
0x1801a24bd  call    ??$?0V?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@$0A@@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAA@AEBV?$basic_string_view@_QU?$char_traits@_Q@std@@@1@AEBV?$allocator@_Q@1@@Z; std::basic_string<char8_t>::basic_string<char8_t>(std::u8string_view const &,std::allocator<char8_t> const &)
0x1801a24c2  nop
0x1801a24c3  lea     rbx, aShm_0; "-shm"
0x1801a24ca  lea     r12, aShm_1; "-shm"
0x1801a24d1  mov     r8, rbx; void *
0x1801a24d4  lea     rdx, [rsp+868h+Buf1]; Src
0x1801a24dc  lea     rcx, [rsp+868h+var_4D8]; void *
0x1801a24e4  call    ??$?H_QU?$char_traits@_Q@std@@V?$allocator@_Q@1@@std@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@0@AEBV10@0@Z; std::operator+<char8_t>(std::basic_string<char8_t> const &,std::basic_string<char8_t> const &)
0x1801a24e9  nop
0x1801a24ea  lea     rax, [rsp+868h+var_4D8]
0x1801a24f2  cmp     [rsp+868h+var_4C0], 0Fh
0x1801a24fb  cmova   rax, qword ptr [rsp+868h+var_4D8]
0x1801a2504  mov     qword ptr [rsp+868h+var_5E8], rax
0x1801a250c  mov     rax, [rsp+868h+var_4C8]
0x1801a2514  mov     qword ptr [rsp+868h+var_5E8+8], rax
0x1801a251c  movups  xmm0, xmmword ptr [r15]
0x1801a2520  movaps  [rsp+868h+Buf2], xmm0
0x1801a2528  movaps  xmm1, [rsp+868h+var_5E8]
0x1801a2530  movdqa  [rsp+868h+var_808], xmm1
0x1801a2536  lea     r8, [rsp+868h+Buf2]
0x1801a253e  lea     rdx, [rsp+868h+var_808]
0x1801a2543  lea     rcx, [rsp+868h+var_827]
0x1801a2548  call    ?TryFileExists@DbConnection@Sqlite@asg@@SA?AV?$optional@_N@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@0@Z; asg::Sqlite::DbConnection::TryFileExists(std::u8string_view,std::u8string_view)
0x1801a254d  cmp     byte ptr [rax+1], 0
0x1801a2551  jz      short loc_1801A25BC
0x1801a2553  cmp     byte ptr [rax], 0
0x1801a2556  jz      short loc_1801A25BC
0x1801a2558  lea     rax, [rsp+868h+var_4D8]
0x1801a2560  cmp     [rsp+868h+var_4C0], 0Fh
0x1801a2569  cmova   rax, qword ptr [rsp+868h+var_4D8]
0x1801a2572  mov     qword ptr [rsp+868h+var_5C8], rax
0x1801a257a  mov     rax, [rsp+868h+var_4C8]
0x1801a2582  mov     qword ptr [rsp+868h+var_5C8+8], rax
0x1801a258a  movups  xmm0, xmmword ptr [r15]
0x1801a258e  movaps  [rsp+868h+Buf2], xmm0
0x1801a2596  movaps  xmm1, [rsp+868h+var_5C8]
0x1801a259e  movdqa  [rsp+868h+var_808], xmm1
0x1801a25a4  lea     r8, [rsp+868h+Buf2]
0x1801a25ac  lea     rdx, [rsp+868h+var_808]
0x1801a25b1  lea     rcx, [rsp+868h+var_820]
0x1801a25b6  call    ?TryRemoveFile@DbConnection@Sqlite@asg@@SA?AV?$optional@_N@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@0@Z; asg::Sqlite::DbConnection::TryRemoveFile(std::u8string_view,std::u8string_view)
0x1801a25bb  nop
0x1801a25bc  mov     rdx, [rsp+868h+var_4C0]
0x1801a25c4  cmp     rdx, 0Fh
0x1801a25c8  jbe     short loc_1801A25FF
0x1801a25ca  inc     rdx
0x1801a25cd  mov     rcx, qword ptr [rsp+868h+var_4D8]
0x1801a25d5  mov     rax, rcx
0x1801a25d8  cmp     rdx, 1000h
0x1801a25df  jb      short loc_1801A25FA
0x1801a25e1  add     rdx, 27h ; '''
0x1801a25e5  mov     rcx, [rcx-8]; Block
0x1801a25e9  sub     rax, rcx
0x1801a25ec  sub     rax, 8
0x1801a25f0  cmp     rax, 1Fh
0x1801a25f4  ja      loc_1801A355F
0x1801a25fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a25ff  add     rbx, 20h ; ' '
0x1801a2603  cmp     rbx, r12
0x1801a2606  jnz     loc_1801A24D1
0x1801a260c  mov     rdx, [rsp+868h+var_520]
0x1801a2614  cmp     rdx, 0Fh
0x1801a2618  jbe     short loc_1801A264F
0x1801a261a  inc     rdx
0x1801a261d  mov     rcx, qword ptr [rsp+868h+Buf1]
0x1801a2625  mov     rax, rcx
0x1801a2628  cmp     rdx, 1000h
0x1801a262f  jb      short loc_1801A264A
0x1801a2631  add     rdx, 27h ; '''
0x1801a2635  mov     rcx, [rcx-8]; Block
0x1801a2639  sub     rax, rcx
0x1801a263c  sub     rax, 8
0x1801a2640  cmp     rax, 1Fh
0x1801a2644  ja      loc_1801A354A
0x1801a264a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a264f  xorps   xmm0, xmm0
0x1801a2652  movups  [rsp+868h+var_4E8], xmm0
0x1801a265a  movups  xmm1, xmmword ptr [r15]
0x1801a265e  movaps  [rsp+868h+Buf2], xmm1
0x1801a2666  mov     rax, [rsp+868h+var_798]
0x1801a266e  movups  xmm0, xmmword ptr [rax]
0x1801a2671  movaps  [rsp+868h+var_808], xmm0
0x1801a2676  movups  xmm1, xmmword ptr [r14]
0x1801a267a  movaps  [rsp+868h+var_4D8], xmm1
0x1801a2682  mov     [rsp+868h+var_840], 0C8h
0x1801a268b  mov     dword ptr [rsp+868h+Reserved], esi
0x1801a268f  lea     r9, [rsp+868h+Buf2]
0x1801a2697  lea     r8, [rsp+868h+var_808]
0x1801a269c  lea     rdx, [rsp+868h+var_4D8]
0x1801a26a4  lea     rcx, [rsp+868h+var_4E8]
0x1801a26ac  call    ?Create@DbConnection@Sqlite@asg@@SA?AV?$shared_ptr@UDbConnection@Sqlite@asg@@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@V?$span@$$CBE$0?0@5@0W4CreateDisposition@23@_K@Z; asg::Sqlite::DbConnection::Create(std::u8string_view,std::span<uchar const,-1>,std::u8string_view,asg::Sqlite::CreateDisposition,unsigned __int64)
0x1801a26b1  nop
0x1801a26b2  mov     rbx, qword ptr [rsp+868h+var_4E8]
0x1801a26ba  mov     [rsp+868h+var_838], rdi
0x1801a26bf  mov     [rsp+868h+var_840], rdi
0x1801a26c4  lea     rax, asg__SemanticIndex__sqlite3CosineDistance
0x1801a26cb  mov     [rsp+868h+Reserved], rax
0x1801a26d0  mov     r9d, 200800h
0x1801a26d6  mov     r14d, 0FFFFFFFFh
0x1801a26dc  mov     r8d, r14d
0x1801a26df  lea     rdx, aCosinedistance; "CosineDistance"
0x1801a26e6  mov     rcx, rbx
0x1801a26e9  call    ?CreateScalarFunction@DbConnection@Sqlite@asg@@QEAAXPEB_QHHP6AXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@ZPEAXP6AX4@Z@Z; asg::Sqlite::DbConnection::CreateScalarFunction(char8_t const *,int,int,void (*)(sqlite3_context *,int,sqlite3_value * *),void *,void (*)(void *))
0x1801a26ee  mov     [rsp+868h+var_838], rdi
0x1801a26f3  mov     [rsp+868h+var_840], rdi
0x1801a26f8  lea     rax, asg__SemanticIndex__sqliteQuantizeEmbedding
0x1801a26ff  mov     [rsp+868h+Reserved], rax
0x1801a2704  mov     r9d, 200800h
0x1801a270a  mov     r8d, 3
0x1801a2710  lea     rdx, aQuantizeembedd_0; "QuantizeEmbedding"
0x1801a2717  mov     rcx, rbx
0x1801a271a  call    ?CreateScalarFunction@DbConnection@Sqlite@asg@@QEAAXPEB_QHHP6AXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@ZPEAXP6AX4@Z@Z; asg::Sqlite::DbConnection::CreateScalarFunction(char8_t const *,int,int,void (*)(sqlite3_context *,int,sqlite3_value * *),void *,void (*)(void *))
0x1801a271f  mov     [rsp+868h+var_838], rdi
0x1801a2724  mov     [rsp+868h+var_840], rdi
0x1801a2729  lea     rax, asg__SemanticIndex__sqliteDequantizeEmbedding
0x1801a2730  mov     [rsp+868h+Reserved], rax
0x1801a2735  mov     r9d, 200800h
0x1801a273b  mov     r8d, 3
0x1801a2741  lea     rdx, aDequantizeembe; "DequantizeEmbedding"
0x1801a2748  mov     rcx, rbx
0x1801a274b  call    ?CreateScalarFunction@DbConnection@Sqlite@asg@@QEAAXPEB_QHHP6AXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@ZPEAXP6AX4@Z@Z; asg::Sqlite::DbConnection::CreateScalarFunction(char8_t const *,int,int,void (*)(sqlite3_context *,int,sqlite3_value * *),void *,void (*)(void *))
0x1801a2750  xorps   xmm0, xmm0
0x1801a2753  movups  xmmword ptr [rsp+868h+var_5A8], xmm0
0x1801a275b  mov     r8b, 1
0x1801a275e  lea     rdx, [rsp+868h+var_5A8]
0x1801a2766  mov     rcx, qword ptr [rsp+868h+var_4E8]
0x1801a276e  call    ?BeginTransaction@DbConnection@Sqlite@asg@@QEAA?AV?$shared_ptr@VDbTransaction@Sqlite@asg@@@std@@_N@Z; asg::Sqlite::DbConnection::BeginTransaction(bool)
0x1801a2773  nop
0x1801a2774  mov     esi, [rsp+868h+arg_40]
0x1801a277b  cmp     [rsp+868h+var_828], 0
0x1801a2780  jz      loc_1801A2BA9
0x1801a2786  movsd   xmm0, [rsp+868h+var_AC]
0x1801a278f  movsd   [rsp+868h+var_5B8], xmm0
0x1801a2798  mov     ebx, [rsp+868h+var_A4]
0x1801a279f  mov     [rsp+868h+var_824], ebx
0x1801a27a3  mov     [rsp+868h+var_5B0], ebx
0x1801a27aa  test    bl, bl
0x1801a27ac  jz      short loc_1801A27BF
0x1801a27ae  cmp     esi, 2
0x1801a27b1  jz      short loc_1801A27BF
0x1801a27b3  mov     dword ptr [rsp+868h+var_5C8], edi
0x1801a27ba  jmp     loc_1801A2876
0x1801a27bf  cmp     esi, 1
0x1801a27c2  jnz     loc_1801A286B
0x1801a27c8  movups  xmm0, [rsp+868h+var_588]
0x1801a27d0  movsd   xmm1, qword ptr [rsp+868h+var_578]
0x1801a27d9  mov     byte ptr [rsp+868h+var_578+8], 0
0x1801a27e1  mov     eax, dword ptr [rsp+868h+var_578+9]
0x1801a27e8  mov     dword ptr [rsp+868h+var_578+9], eax
0x1801a27ef  movzx   eax, word ptr [rsp+868h+var_578+0Dh]
0x1801a27f7  mov     word ptr [rsp+868h+var_578+0Dh], ax
0x1801a27ff  movzx   eax, byte ptr [rsp+868h+var_578+0Fh]
0x1801a2807  mov     byte ptr [rsp+868h+var_578+0Fh], al
0x1801a280e  movaps  [rsp+868h+Buf1], xmm0
0x1801a2816  movaps  xmm0, [rsp+868h+var_578]
0x1801a281e  movsd   xmm0, xmm1
0x1801a2822  movaps  [rsp+868h+var_578], xmm0
0x1801a282a  movaps  xmmword ptr [rsp+340h], xmm0
0x1801a2832  lea     r9, aCannotCreateQu; "Cannot create quantized database: quant"...
0x1801a2839  mov     r8d, 3
0x1801a283f  lea     rdx, [rsp+868h+Buf1]
0x1801a2847  lea     rcx, [rsp+868h+var_588]
0x1801a284f  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x1801a2854  cmp     byte ptr [rsp+868h+var_568], 0
0x1801a285c  jz      short loc_1801A286B
0x1801a285e  lea     rcx, [rsp+868h+var_588]
0x1801a2866  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
  ... truncated ...
```
