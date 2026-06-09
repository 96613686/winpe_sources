# GidsApplication::CreateApplication(void)

- ea: `0x180046b28`
- end: `0x1800477fa`
- name: `?CreateApplication@GidsApplication@@QEAAXXZ`
- size: `3282`
- prototype: `void __fastcall(GidsApplication *__hidden this)`
- caller_count: `1`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x18001f6dc`

## callees

- `0x180008000`
- `0x180008148`
- `0x1800089c0`
- `0x1800089e8`
- `0x18000a5fc`
- `0x18000aa10`
- `0x18000bb10`
- `0x18000c520`
- `0x18000efc0`
- `0x1800102fc`
- `0x1800103c0`
- `0x180010754`
- `0x180010898`
- `0x180010b30`
- `0x180010e9c`
- `0x180010ed0`
- `0x180010f78`
- `0x180011314`
- `0x18001162c`
- `0x1800170f8`
- `0x180018178`
- `0x180018600`
- `0x1800186e8`
- `0x180018948`
- `0x18001c054`
- `0x18001cc58`
- `0x18001e7e8`
- `0x18002915c`
- `0x1800291c0`
- `0x180029694`
- `0x180029718`
- `0x180029754`
- `0x1800297e8`
- `0x180029860`
- `0x180029ee4`
- `0x18002f8d4`
- `0x18002fd14`
- `0x1800334ec`
- `0x18003ae40`
- `0x18003df0c`
- `0x180046b28`
- `0x18005199c`
- `0x180058700`
- `0x18005e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall GidsApplication::CreateApplication(GidsApplication *this)
{
  __m128i si128; // xmm6
  _QWORD *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 Df; // rax
  FileSystem::DedicatedFile **v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 ElementaryFileRule; // rax
  FileSystem::DedicatedFile *v11; // rbx
  __int64 Ef; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  FileSystem::DedicatedFile *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  FileSystem::DedicatedFile *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  FileSystem::DedicatedFile *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  FileSystem::DedicatedFile *v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  FileSystem::DedicatedFile *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __m128i v46; // xmm2
  __m128i v47; // xmm1
  __m128i v48; // xmm0
  __int64 v49; // rcx
  Crt::type *v50; // rbx
  __int64 v51; // r8
  __int64 v52; // rdi
  const struct Crt::type *v53; // rdx
  FileSystem::DedicatedFile *v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  _BYTE v58[4]; // [rsp+28h] [rbp-E0h] BYREF
  int v59; // [rsp+2Ch] [rbp-DCh] BYREF
  __m128i v60; // [rsp+38h] [rbp-D0h] BYREF
  std::tr1::_Ref_count_base **v61; // [rsp+48h] [rbp-C0h]
  _QWORD v62[3]; // [rsp+70h] [rbp-98h] BYREF
  std::tr1::_Ref_count_base **v63; // [rsp+88h] [rbp-80h]
  std::tr1::_Ref_count_base *v64[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v65; // [rsp+C8h] [rbp-40h]
  int v66; // [rsp+CCh] [rbp-3Ch]
  int v67; // [rsp+D0h] [rbp-38h]
  _BYTE v68[56]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v69[104]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v70[32]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v71[8]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v72[40]; // [rsp+1A0h] [rbp+98h] BYREF
  int v73; // [rsp+1C8h] [rbp+C0h] BYREF
  __int16 v74; // [rsp+1CCh] [rbp+C4h]
  _BYTE v75[32]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v76[56]; // [rsp+200h] [rbp+F8h] BYREF
  _BYTE v77[32]; // [rsp+238h] [rbp+130h] BYREF
  __m128i v78; // [rsp+258h] [rbp+150h]
  int v79; // [rsp+268h] [rbp+160h]
  char v80; // [rsp+26Ch] [rbp+164h]
  __m128i v81; // [rsp+2B8h] [rbp+1B0h]
  int v82; // [rsp+2C8h] [rbp+1C0h]
  char v83; // [rsp+2CCh] [rbp+1C4h]
  __m128i v84; // [rsp+2D8h] [rbp+1D0h]
  int v85; // [rsp+2E8h] [rbp+1E0h]
  char v86; // [rsp+2ECh] [rbp+1E4h]
  __m128i v87; // [rsp+2F8h] [rbp+1F0h]
  int v88; // [rsp+308h] [rbp+200h]
  char v89; // [rsp+30Ch] [rbp+204h]
  _DWORD v90[3]; // [rsp+318h] [rbp+210h] BYREF
  int v91; // [rsp+324h] [rbp+21Ch]
  __int16 v92; // [rsp+328h] [rbp+220h] BYREF
  __int16 *v93; // [rsp+330h] [rbp+228h]
  _BYTE v94[8]; // [rsp+338h] [rbp+230h] BYREF
  _BYTE *v95; // [rsp+340h] [rbp+238h]
  int v96; // [rsp+348h] [rbp+240h]
  _BYTE v97[8]; // [rsp+350h] [rbp+248h] BYREF
  _BYTE *v98; // [rsp+358h] [rbp+250h]
  _BYTE v99[72]; // [rsp+368h] [rbp+260h] BYREF
  int v100; // [rsp+3B0h] [rbp+2A8h]
  _DWORD v101[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _BYTE v102[32]; // [rsp+3C0h] [rbp+2B8h] BYREF
  _BYTE v103[88]; // [rsp+3E0h] [rbp+2D8h] BYREF

  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(v68);
  (*(void (__fastcall **)(GidsApplication *, _BYTE *))(*(_QWORD *)this + 8LL))(this, v71);
  v65 = 2;
  v66 = 1;
  v67 = 2;
  v58[0] = 0;
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v70);
  SecurityRule::type::type((SecurityRule::type *)v77);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v78 = si128;
  v79 = 1;
  v80 = 1;
  v84 = si128;
  v85 = 1;
  v86 = 1;
  v87 = si128;
  v88 = 1;
  v89 = 1;
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v70, v77);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  DataObjectImplicit<ScardGidsModule,4>::type::type(v101);
  v101[0] = 1;
  v101[1] = 3;
  v3 = (_QWORD *)rangelib::make_raw_range<std::vector<unsigned char> const &>(&v62[1], v72);
  v60 = 0;
  v61 = 0;
  std::vector<unsigned char>::_Construct<char *>(&v60, *v3, v3[1]);
  std::vector<unsigned char>::_Assign_rv(v102, &v60);
  std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(&v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>(
    &v60,
    v70);
  SecurityAttribute::type::operator=(v103, &v60);
  v4 = *((_QWORD *)this + 30);
  v5 = DataObjectImplicit<ScardGidsModule,4>::type::type(v77, v101);
  Df = FileSystem::CreateDf(v4, v69, v5);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v7 = (FileSystem::DedicatedFile **)((char *)this + 272);
  v61 = (std::tr1::_Ref_count_base **)((char *)this + 272);
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    Df);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v8 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v8);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  DataObjectImplicit<ScardGidsModule,5>::type::type(&v73);
  *(_OWORD *)v64 = 0;
  v9 = DataObjectImplicit<ScardGidsModule,5>::type::type(v69);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v9);
  v73 = 2;
  v74 = -24576;
  *(__m128i *)&v62[1] = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v63) = 1;
  v60 = si128;
  LODWORD(v61) = 1;
  ElementaryFileRule = SecurityRule::make_ElementaryFileRule(v77, &v60, &v62[1]);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, ElementaryFileRule);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v11 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  Ef = FileSystem::DedicatedFile::CreateEf(v11);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    Ef);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v13 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v13);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v14 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v14);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v15 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v15);
  v73 = 2;
  v74 = -24560;
  v60 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v61) = 1;
  *(__m128i *)&v62[1] = si128;
  LODWORD(v63) = 1;
  v16 = SecurityRule::make_ElementaryFileRule(v77, &v62[1], &v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v16);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v17 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v18 = FileSystem::DedicatedFile::CreateEf(v17);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    v18);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v19 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v19);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v20 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v20);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v21 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v21);
  v73 = 2;
  v74 = -24559;
  v60 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v61) = 4;
  *(__m128i *)&v62[1] = si128;
  LODWORD(v63) = 1;
  v22 = SecurityRule::make_ElementaryFileRule(v77, &v62[1], &v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v22);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v23 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v24 = FileSystem::DedicatedFile::CreateEf(v23);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    v24);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v25 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v25);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v26 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v26);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v27 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v27);
  v73 = 2;
  v74 = -24558;
  v60 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v61) = 1;
  *(__m128i *)&v62[1] = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v63) = 1;
  v28 = SecurityRule::make_ElementaryFileRule(v77, &v62[1], &v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v28);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v29 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v30 = FileSystem::DedicatedFile::CreateEf(v29);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    v30);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v31 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v31);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v32 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v32);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v33 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v33);
  v73 = 2;
  v74 = -24557;
  v60 = si128;
  LODWORD(v61) = 1;
  *(__m128i *)&v62[1] = si128;
  LODWORD(v63) = 1;
  v34 = SecurityRule::make_ElementaryFileRule(v77, &v62[1], &v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v34);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v35 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v36 = FileSystem::DedicatedFile::CreateEf(v35);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    v36);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v37 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v37);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v38 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v38);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v39 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v39);
  v73 = 2;
  v74 = -24556;
  v60 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(v61) = 1;
  *(__m128i *)&v62[1] = v60;
  LODWORD(v63) = 1;
  v40 = SecurityRule::make_ElementaryFileRule(v77, &v62[1], &v60);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v40);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v41 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v42 = FileSystem::DedicatedFile::CreateEf(v41);
  v60.m128i_i64[0] = (__int64)v68;
  v60.m128i_i64[1] = (__int64)v58;
  v61 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v60,
    v42);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v43 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v43);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v44 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v44);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v60);
  v45 = DataObjectImplicit<ScardGidsModule,5>::type::type(v77);
  DataObjectImplicit<ScardGidsModule,5>::type::operator=(&v73, v45);
  v73 = 4;
  v74 = -20352;
  v46 = _mm_load_si128((const __m128i *)&_xmm);
  v47 = _mm_load_si128((const __m128i *)&_xmm);
  v48 = _mm_load_si128((const __m128i *)&_xmm);
  SecurityRule::type::type((SecurityRule::type *)v77);
  v81 = v48;
  v82 = 1;
  v83 = 1;
  v84 = v47;
  v85 = 1;
  v86 = 1;
  v87 = v46;
  v88 = 4;
  v89 = 1;
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(v75, v77);
  SecurityRule::type::~type((SecurityRule::type *)v77);
  v91 = 4;
  HIBYTE(v92) = 0;
  v93 = &v92;
  v94[1] = 0;
  v95 = v94;
  v96 = 0;
  v97[2] = 0;
  v98 = v97;
  LOBYTE(v49) = 2;
  v90[0] = CryptoAlgorithm::make(v49);
  v91 = 0;
  v92 = 384;
  v96 = 3;
  Asn1Vector<Asn1Tag>::type::type(&v60);
  v100 = 3;
  GidsCrtDo<DataObjectImplicit<ScardGidsModule,15>,15,1>::type::type(v99, v90);
  v100 = 0;
  v50 = (Crt::type *)v60.m128i_i64[1];
  if ( (unsigned __int64)v99 >= v60.m128i_i64[1] || (v51 = v60.m128i_i64[0], v60.m128i_i64[0] > (unsigned __int64)v99) )
  {
    if ( (std::tr1::_Ref_count_base **)v60.m128i_i64[1] == v61 )
    {
      std::vector<Crt::type,wil::secure_allocator<Crt::type>>::_Reserve(&v60);
      v50 = (Crt::type *)v60.m128i_i64[1];
    }
    v53 = (const struct Crt::type *)v99;
  }
  else
  {
    v52 = (__int64)&v99[-v60.m128i_i64[0]] / 80;
    if ( (std::tr1::_Ref_count_base **)v60.m128i_i64[1] == v61 )
    {
      std::vector<Crt::type,wil::secure_allocator<Crt::type>>::_Reserve(&v60);
      v50 = (Crt::type *)v60.m128i_i64[1];
      v51 = v60.m128i_i64[0];
    }
    v53 = (const struct Crt::type *)(v51 + 80 * v52);
  }
  Crt::type::type(v50, v53);
  v60.m128i_i64[1] = (__int64)v50 + 80;
  oneoflib::one_of<typveclib::typevec<GidsCrtDo<DataObjectImplicit<ScardGidsModule,15>,15,1>::type,GidsCrtDo<DataObjectImplicit<ScardGidsModule,17>,17,3>::type,GidsCrtDo<DataObjectImplicit<ScardGidsModule,16>,16,2>::type,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil>,typbldlib::metavalue<0>,typbldlib::metavalue<3>,typbldlib::metavalue<1>>::~one_of<typveclib::typevec<GidsCrtDo<DataObjectImplicit<ScardGidsModule,15>,15,1>::type,GidsCrtDo<DataObjectImplicit<ScardGidsModule,17>,17,3>::type,GidsCrtDo<DataObjectImplicit<ScardGidsModule,16>,16,2>::type,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil>,typbldlib::metavalue<0>,typbldlib::metavalue<3>,typbldlib::metavalue<1>>(v99);
  optnllib::optional<Asn1Vector<Crt>::type>::clear(v76);
  std::vector<Crt::type,wil::secure_allocator<Crt::type>>::vector<Crt::type,wil::secure_allocator<Crt::type>>(v76, &v60);
  v76[32] = 1;
  v54 = *v7;
  DataObjectImplicit<ScardGidsModule,5>::type::type(v77, &v73);
  v55 = FileSystem::DedicatedFile::CreateEf(v54);
  v62[1] = v68;
  v62[2] = v58;
  v63 = v64;
  std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v62[1],
    v55);
  std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v69);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v68);
  if ( !v58[0] )
  {
    v59 = 80;
    v56 = errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(&v62[1], &v59);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v56);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62[1]);
  }
  v57 = FileSystem::ElementaryFile::SetLifeCycleStatus(v64[0]);
  errorlib::scoped_error<apdustatus_error::tag>::throwfailed(v57);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v62[1]);
  std::vector<Crt::type,wil::secure_allocator<Crt::type>>::_Tidy(&v60);
  GidsCrtDo<DataObjectImplicit<ScardGidsModule,15>,15,1>::type::~type(v90);
  if ( v64[1] )
    std::tr1::_Ref_count_base::_Decref(v64[1]);
  DataObjectImplicit<ScardGidsModule,5>::type::~type(&v73);
  DataObjectImplicit<ScardGidsModule,4>::type::~type(v101);
  std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::_Tidy(v70);
  std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(v72);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(v68);
}

```

## disassembly

```asm
0x180046b28  mov     rax, rsp
0x180046b2b  push    rbp
0x180046b2c  push    rbx
0x180046b2d  push    rsi
0x180046b2e  push    rdi
0x180046b2f  push    r12
0x180046b31  push    r13
0x180046b33  push    r14
0x180046b35  push    r15
0x180046b37  lea     rbp, [rax-398h]
0x180046b3e  sub     rsp, 458h
0x180046b45  movaps  xmmword ptr [rax-58h], xmm6
0x180046b49  mov     rax, cs:__security_cookie
0x180046b50  xor     rax, rsp
0x180046b53  mov     [rbp+390h+var_60], rax
0x180046b5a  mov     rdi, rcx
0x180046b5d  xor     r12d, r12d
0x180046b60  lea     rcx, [rbp+390h+var_3C0]
0x180046b64  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180046b69  nop
0x180046b6a  mov     rax, [rdi]
0x180046b6d  lea     rdx, [rbp+390h+var_300]
0x180046b74  mov     rcx, rdi
0x180046b77  mov     rax, [rax+8]
0x180046b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b80  nop
0x180046b81  lea     eax, [r12+2]
0x180046b86  mov     [rbp+390h+var_3D0], eax
0x180046b89  lea     r15d, [r12+1]
0x180046b8e  mov     [rbp+390h+var_3CC], r15d
0x180046b92  mov     [rbp+390h+var_3C8], eax
0x180046b95  mov     [rsp+20h], r12b
0x180046b9a  lea     rcx, [rbp+390h+var_320]
0x180046b9e  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x180046ba3  nop
0x180046ba4  lea     rcx, [rbp+390h+var_260]; this
0x180046bab  call    ??0type@SecurityRule@@QEAA@XZ; SecurityRule::type::type(void)
0x180046bb0  movdqa  xmm6, cs:__xmm@00000001000000010000000200000001
0x180046bb8  movdqa  [rbp+390h+var_240], xmm6
0x180046bc0  mov     [rbp+390h+var_230], r15d
0x180046bc7  mov     [rbp+390h+var_22C], r15b
0x180046bce  movdqa  [rbp+390h+var_1C0], xmm6
0x180046bd6  mov     [rbp+390h+var_1B0], r15d
0x180046bdd  mov     [rbp+390h+var_1AC], r15b
0x180046be4  movdqa  [rbp+390h+var_1A0], xmm6
0x180046bec  mov     [rbp+390h+var_190], r15d
0x180046bf3  mov     [rbp+390h+var_18C], r15b
0x180046bfa  lea     rdx, [rbp+390h+var_260]
0x180046c01  lea     rcx, [rbp+390h+var_320]
0x180046c05  call    ?push_back@?$vector@Utype@SecurityRule@@U?$secure_allocator@Utype@SecurityRule@@@wil@@@std@@QEAAX$$QEAUtype@SecurityRule@@@Z; std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(SecurityRule::type &&)
0x180046c0a  nop
0x180046c0b  lea     rcx, [rbp+390h+var_260]; this
0x180046c12  call    ??1type@SecurityRule@@QEAA@XZ; SecurityRule::type::~type(void)
0x180046c17  lea     rcx, [rbp+390h+var_E0]
0x180046c1e  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$03@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,4>::type::type(void)
0x180046c23  nop
0x180046c24  mov     [rbp+390h+var_E0], r15d
0x180046c2b  lea     r13d, [r12+3]
0x180046c30  mov     [rbp+390h+var_DC], r13d
0x180046c37  lea     rdx, [rbp+390h+var_2F8]
0x180046c3e  lea     rcx, [rsp+490h+var_428+8]
0x180046c43  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x180046c48  xorps   xmm0, xmm0
0x180046c4b  movdqu  [rsp+490h+var_468+8], xmm0
0x180046c51  mov     [rsp+490h+var_450], r12
0x180046c56  mov     r8, [rax+8]
0x180046c5a  mov     rdx, [rax]
0x180046c5d  lea     rcx, [rsp+490h+var_468+8]
0x180046c62  call    ??$_Construct@PEAD@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAD0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<char *>(char *,char *,std::input_iterator_tag)
0x180046c67  nop
0x180046c68  lea     rdx, [rsp+490h+var_468+8]
0x180046c6d  lea     rcx, [rbp+390h+var_D8]
0x180046c74  call    ?_Assign_rv@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAV12@@Z; std::vector<uchar>::_Assign_rv(std::vector<uchar> &&)
0x180046c79  nop
0x180046c7a  lea     rcx, [rsp+490h+var_468+8]
0x180046c7f  call    ??1?$vector@U_CRYPTOAPI_BLOB@@V?$allocator@U_CRYPTOAPI_BLOB@@@std@@@std@@QEAA@XZ; std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(void)
0x180046c84  lea     rdx, [rbp+390h+var_320]
0x180046c88  lea     rcx, [rsp+490h+var_468+8]
0x180046c8d  call    ??0?$vector@Utype@SecurityRule@@U?$secure_allocator@Utype@SecurityRule@@@wil@@@std@@QEAA@AEBV01@@Z; std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>(std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>> const &)
0x180046c92  lea     rdx, [rsp+490h+var_468+8]
0x180046c97  lea     rcx, [rbp+390h+var_B8]
0x180046c9e  call    ??4type@SecurityAttribute@@QEAAAEAU01@U01@@Z; SecurityAttribute::type::operator=(SecurityAttribute::type)
0x180046ca3  mov     rbx, [rdi+0F0h]
0x180046caa  lea     rdx, [rbp+390h+var_E0]
0x180046cb1  lea     rcx, [rbp+390h+var_260]
0x180046cb8  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$03@@QEAA@AEBU01@@Z; DataObjectImplicit<ScardGidsModule,4>::type::type(DataObjectImplicit<ScardGidsModule,4>::type const &)
0x180046cbd  mov     r8, rax
0x180046cc0  lea     rdx, [rbp+390h+var_388]
0x180046cc4  mov     rcx, rbx
0x180046cc7  call    ?CreateDf@FileSystem@@QEAA?AV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@Utype@?$DataObjectImplicit@UScardGidsModule@@$03@@@Z; FileSystem::CreateDf(DataObjectImplicit<ScardGidsModule,4>::type)
0x180046ccc  lea     rcx, [rbp+390h+var_3C0]
0x180046cd0  mov     qword ptr [rsp+490h+var_468+8], rcx
0x180046cd5  lea     rcx, [rsp+20h]
0x180046cda  mov     [rsp+490h+var_458], rcx
0x180046cdf  lea     rsi, [rdi+110h]
0x180046ce6  mov     [rsp+490h+var_450], rsi
0x180046ceb  mov     rdx, rax
0x180046cee  lea     rcx, [rsp+490h+var_468+8]
0x180046cf3  call    ??$?4V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@34@U534@U534@U534@U534@U534@U534@@?$tuple@AEAV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEA_NAEAV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@12@@Z; std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180046cf8  lea     rcx, [rbp+390h+var_388]
0x180046cfc  call    ??1?$_Cons_node@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@U?$_Cons_node@_NU?$_Cons_node@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@std@@U?$_Cons_node@U_Nil@tr1@std@@U123@@23@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x180046d01  lea     rcx, [rbp+390h+var_3C0]
0x180046d05  call    ?throwfailed@?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<apdustatus_error::tag>::throwfailed(void)
0x180046d0a  lea     r14d, [r12+50h]
0x180046d0f  cmp     [rsp+20h], r12b
0x180046d14  jnz     short loc_180046D3E
0x180046d16  mov     [rsp+490h+var_46C], r14d
0x180046d1b  lea     rdx, [rsp+490h+var_46C]
0x180046d20  lea     rcx, [rsp+490h+var_428+8]
0x180046d25  call    ??$make_initiated@J@?$scoped_error@Utag@winerror_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(long &&)
0x180046d2a  nop
0x180046d2b  mov     rcx, rax
0x180046d2e  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180046d33  nop
0x180046d34  lea     rcx, [rsp+490h+var_428+8]
0x180046d39  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180046d3e  lea     rcx, [rbp+390h+var_2D0]
0x180046d45  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,5>::type::type(void)
0x180046d4a  nop
0x180046d4b  xorps   xmm0, xmm0
0x180046d4e  movdqu  xmmword ptr [rbp+390h+var_3E0], xmm0
0x180046d53  lea     rcx, [rbp+390h+var_388]
0x180046d57  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,5>::type::type(void)
0x180046d5c  mov     rdx, rax
0x180046d5f  lea     rcx, [rbp+390h+var_2D0]
0x180046d66  call    ??4type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAAAEAU01@U01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::operator=(DataObjectImplicit<ScardGidsModule,5>::type)
0x180046d6b  mov     edi, 2
0x180046d70  mov     [rbp+390h+var_2D0], edi
0x180046d76  mov     eax, 0A000h
0x180046d7b  mov     [rbp+390h+var_2CC], ax
0x180046d82  movdqa  xmm0, cs:__xmm@00000002000000020000000200000001
0x180046d8a  movdqa  xmmword ptr [rsp+490h+var_428+8], xmm0
0x180046d90  mov     dword ptr [rbp+390h+var_410], r15d
0x180046d94  movdqa  [rsp+490h+var_468+8], xmm6
0x180046d9a  mov     dword ptr [rsp+490h+var_450], r15d
0x180046d9f  lea     r8, [rsp+490h+var_428+8]
0x180046da4  lea     rdx, [rsp+490h+var_468+8]
0x180046da9  lea     rcx, [rbp+390h+var_260]
0x180046db0  call    ?make_ElementaryFileRule@SecurityRule@@SA?AUtype@1@U2SecurityCondition@@0@Z; SecurityRule::make_ElementaryFileRule(SecurityCondition::type,SecurityCondition::type)
0x180046db5  nop
0x180046db6  mov     rdx, rax
0x180046db9  lea     rcx, [rbp+390h+var_2B8]
0x180046dc0  call    ?push_back@?$vector@Utype@SecurityRule@@U?$secure_allocator@Utype@SecurityRule@@@wil@@@std@@QEAAX$$QEAUtype@SecurityRule@@@Z; std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(SecurityRule::type &&)
0x180046dc5  nop
0x180046dc6  lea     rcx, [rbp+390h+var_260]; this
0x180046dcd  call    ??1type@SecurityRule@@QEAA@XZ; SecurityRule::type::~type(void)
0x180046dd2  mov     rbx, [rsi]
0x180046dd5  lea     rdx, [rbp+390h+var_2D0]
0x180046ddc  lea     rcx, [rbp+390h+var_260]
0x180046de3  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@AEBU01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::type(DataObjectImplicit<ScardGidsModule,5>::type const &)
0x180046de8  mov     r9, rax
0x180046deb  lea     r8, [rbp+390h+var_3D0]
0x180046def  lea     rdx, [rbp+390h+var_388]
0x180046df3  mov     rcx, rbx; this
0x180046df6  call    ?CreateEf@DedicatedFile@FileSystem@@QEAA?AV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@AEBUtype@AuthenticatedRoleStatus@@U6?$DataObjectImplicit@UScardGidsModule@@$04@@@Z; FileSystem::DedicatedFile::CreateEf(AuthenticatedRoleStatus::type const &,DataObjectImplicit<ScardGidsModule,5>::type)
0x180046dfb  lea     rcx, [rbp+390h+var_3C0]
0x180046dff  mov     qword ptr [rsp+490h+var_468+8], rcx
0x180046e04  lea     rcx, [rsp+20h]
0x180046e09  mov     [rsp+490h+var_458], rcx
0x180046e0e  lea     rcx, [rbp+390h+var_3E0]
0x180046e12  mov     [rsp+490h+var_450], rcx
0x180046e17  mov     rdx, rax
0x180046e1a  lea     rcx, [rsp+490h+var_468+8]
0x180046e1f  call    ??$?4V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@34@U534@U534@U534@U534@U534@U534@@?$tuple@AEAV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEA_NAEAV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@12@@Z; std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180046e24  lea     rcx, [rbp+390h+var_388]
0x180046e28  call    ??1?$_Cons_node@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@U?$_Cons_node@_NU?$_Cons_node@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@std@@U?$_Cons_node@U_Nil@tr1@std@@U123@@23@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x180046e2d  lea     rcx, [rbp+390h+var_3C0]
0x180046e31  call    ?throwfailed@?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<apdustatus_error::tag>::throwfailed(void)
0x180046e36  cmp     [rsp+20h], r12b
0x180046e3b  jnz     short loc_180046E65
0x180046e3d  mov     [rsp+490h+var_46C], r14d
0x180046e42  lea     rdx, [rsp+490h+var_46C]
0x180046e47  lea     rcx, [rsp+490h+var_428+8]
0x180046e4c  call    ??$make_initiated@J@?$scoped_error@Utag@winerror_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(long &&)
0x180046e51  nop
0x180046e52  mov     rcx, rax
0x180046e55  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180046e5a  nop
0x180046e5b  lea     rcx, [rsp+490h+var_428+8]
0x180046e60  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180046e65  mov     r8d, r13d
0x180046e68  lea     rdx, [rsp+490h+var_468+8]
0x180046e6d  mov     rcx, [rbp+390h+var_3E0]; this
0x180046e71  call    ?SetLifeCycleStatus@ElementaryFile@FileSystem@@QEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@W4type@LifeCycleStatus@@@Z; FileSystem::ElementaryFile::SetLifeCycleStatus(LifeCycleStatus::type)
0x180046e76  nop
0x180046e77  mov     rcx, rax
0x180046e7a  call    ?throwfailed@?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<apdustatus_error::tag>::throwfailed(void)
0x180046e7f  nop
0x180046e80  lea     rcx, [rsp+490h+var_468+8]
0x180046e85  call    ??1?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(void)
0x180046e8a  lea     rcx, [rbp+390h+var_260]
0x180046e91  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,5>::type::type(void)
0x180046e96  mov     rdx, rax
0x180046e99  lea     rcx, [rbp+390h+var_2D0]
0x180046ea0  call    ??4type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAAAEAU01@U01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::operator=(DataObjectImplicit<ScardGidsModule,5>::type)
0x180046ea5  mov     [rbp+390h+var_2D0], edi
0x180046eab  mov     eax, 0A010h
0x180046eb0  mov     [rbp+390h+var_2CC], ax
0x180046eb7  movdqa  xmm0, cs:__xmm@00000002000000020000000200000001
0x180046ebf  movdqa  [rsp+490h+var_468+8], xmm0
0x180046ec5  mov     dword ptr [rsp+490h+var_450], r15d
0x180046eca  movdqa  xmmword ptr [rsp+490h+var_428+8], xmm6
0x180046ed0  mov     dword ptr [rbp+390h+var_410], r15d
0x180046ed4  lea     r8, [rsp+490h+var_468+8]
0x180046ed9  lea     rdx, [rsp+490h+var_428+8]
0x180046ede  lea     rcx, [rbp+390h+var_260]
0x180046ee5  call    ?make_ElementaryFileRule@SecurityRule@@SA?AUtype@1@U2SecurityCondition@@0@Z; SecurityRule::make_ElementaryFileRule(SecurityCondition::type,SecurityCondition::type)
0x180046eea  nop
0x180046eeb  mov     rdx, rax
0x180046eee  lea     rcx, [rbp+390h+var_2B8]
0x180046ef5  call    ?push_back@?$vector@Utype@SecurityRule@@U?$secure_allocator@Utype@SecurityRule@@@wil@@@std@@QEAAX$$QEAUtype@SecurityRule@@@Z; std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(SecurityRule::type &&)
0x180046efa  nop
0x180046efb  lea     rcx, [rbp+390h+var_260]; this
0x180046f02  call    ??1type@SecurityRule@@QEAA@XZ; SecurityRule::type::~type(void)
0x180046f07  mov     rbx, [rsi]
0x180046f0a  lea     rdx, [rbp+390h+var_2D0]
0x180046f11  lea     rcx, [rbp+390h+var_260]
0x180046f18  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@AEBU01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::type(DataObjectImplicit<ScardGidsModule,5>::type const &)
0x180046f1d  mov     r9, rax
0x180046f20  lea     r8, [rbp+390h+var_3D0]
0x180046f24  lea     rdx, [rbp+390h+var_388]
0x180046f28  mov     rcx, rbx; this
0x180046f2b  call    ?CreateEf@DedicatedFile@FileSystem@@QEAA?AV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@AEBUtype@AuthenticatedRoleStatus@@U6?$DataObjectImplicit@UScardGidsModule@@$04@@@Z; FileSystem::DedicatedFile::CreateEf(AuthenticatedRoleStatus::type const &,DataObjectImplicit<ScardGidsModule,5>::type)
0x180046f30  lea     rcx, [rbp+390h+var_3C0]
0x180046f34  mov     qword ptr [rsp+490h+var_468+8], rcx
0x180046f39  lea     rcx, [rsp+20h]
0x180046f3e  mov     [rsp+490h+var_458], rcx
0x180046f43  lea     rcx, [rbp+390h+var_3E0]
0x180046f47  mov     [rsp+490h+var_450], rcx
0x180046f4c  mov     rdx, rax
0x180046f4f  lea     rcx, [rsp+490h+var_468+8]
0x180046f54  call    ??$?4V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@34@U534@U534@U534@U534@U534@U534@@?$tuple@AEAV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEA_NAEAV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@12@@Z; std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180046f59  lea     rcx, [rbp+390h+var_388]
0x180046f5d  call    ??1?$_Cons_node@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@U?$_Cons_node@_NU?$_Cons_node@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@std@@U?$_Cons_node@U_Nil@tr1@std@@U123@@23@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<apdustatus_error::tag>,std::tr1::_Cons_node<bool,std::tr1::_Cons_node<std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x180046f62  lea     rcx, [rbp+390h+var_3C0]
0x180046f66  call    ?throwfailed@?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<apdustatus_error::tag>::throwfailed(void)
0x180046f6b  cmp     [rsp+20h], r12b
0x180046f70  jnz     short loc_180046F9A
0x180046f72  mov     [rsp+490h+var_46C], r14d
0x180046f77  lea     rdx, [rsp+490h+var_46C]
0x180046f7c  lea     rcx, [rsp+490h+var_428+8]
0x180046f81  call    ??$make_initiated@J@?$scoped_error@Utag@winerror_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::make_initiated<long>(long &&)
0x180046f86  nop
0x180046f87  mov     rcx, rax
0x180046f8a  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180046f8f  nop
0x180046f90  lea     rcx, [rsp+490h+var_428+8]
0x180046f95  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180046f9a  mov     r8d, r13d
0x180046f9d  lea     rdx, [rsp+490h+var_468+8]
0x180046fa2  mov     rcx, [rbp+390h+var_3E0]; this
0x180046fa6  call    ?SetLifeCycleStatus@ElementaryFile@FileSystem@@QEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@W4type@LifeCycleStatus@@@Z; FileSystem::ElementaryFile::SetLifeCycleStatus(LifeCycleStatus::type)
0x180046fab  nop
0x180046fac  mov     rcx, rax
0x180046faf  call    ?throwfailed@?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<apdustatus_error::tag>::throwfailed(void)
0x180046fb4  nop
0x180046fb5  lea     rcx, [rsp+490h+var_468+8]
0x180046fba  call    ??1?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(void)
0x180046fbf  lea     rcx, [rbp+390h+var_260]
0x180046fc6  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,5>::type::type(void)
0x180046fcb  mov     rdx, rax
0x180046fce  lea     rcx, [rbp+390h+var_2D0]
0x180046fd5  call    ??4type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAAAEAU01@U01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::operator=(DataObjectImplicit<ScardGidsModule,5>::type)
0x180046fda  mov     [rbp+390h+var_2D0], edi
0x180046fe0  mov     eax, 0A011h
0x180046fe5  mov     [rbp+390h+var_2CC], ax
0x180046fec  movdqa  xmm0, cs:__xmm@00000001000000010000000100000002
0x180046ff4  movdqa  [rsp+490h+var_468+8], xmm0
0x180046ffa  mov     dword ptr [rsp+490h+var_450], 4
0x180047002  movdqa  xmmword ptr [rsp+490h+var_428+8], xmm6
0x180047008  mov     dword ptr [rbp+390h+var_410], r15d
0x18004700c  lea     r8, [rsp+490h+var_468+8]
0x180047011  lea     rdx, [rsp+490h+var_428+8]
0x180047016  lea     rcx, [rbp+390h+var_260]
0x18004701d  call    ?make_ElementaryFileRule@SecurityRule@@SA?AUtype@1@U2SecurityCondition@@0@Z; SecurityRule::make_ElementaryFileRule(SecurityCondition::type,SecurityCondition::type)
0x180047022  nop
0x180047023  mov     rdx, rax
0x180047026  lea     rcx, [rbp+390h+var_2B8]
0x18004702d  call    ?push_back@?$vector@Utype@SecurityRule@@U?$secure_allocator@Utype@SecurityRule@@@wil@@@std@@QEAAX$$QEAUtype@SecurityRule@@@Z; std::vector<SecurityRule::type,wil::secure_allocator<SecurityRule::type>>::push_back(SecurityRule::type &&)
0x180047032  nop
0x180047033  lea     rcx, [rbp+390h+var_260]; this
0x18004703a  call    ??1type@SecurityRule@@QEAA@XZ; SecurityRule::type::~type(void)
0x18004703f  mov     rbx, [rsi]
0x180047042  lea     rdx, [rbp+390h+var_2D0]
0x180047049  lea     rcx, [rbp+390h+var_260]
0x180047050  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$04@@QEAA@AEBU01@@Z; DataObjectImplicit<ScardGidsModule,5>::type::type(DataObjectImplicit<ScardGidsModule,5>::type const &)
0x180047055  mov     r9, rax
0x180047058  lea     r8, [rbp+390h+var_3D0]
0x18004705c  lea     rdx, [rbp+390h+var_388]
0x180047060  mov     rcx, rbx; this
0x180047063  call    ?CreateEf@DedicatedFile@FileSystem@@QEAA?AV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@AEBUtype@AuthenticatedRoleStatus@@U6?$DataObjectImplicit@UScardGidsModule@@$04@@@Z; FileSystem::DedicatedFile::CreateEf(AuthenticatedRoleStatus::type const &,DataObjectImplicit<ScardGidsModule,5>::type)
0x180047068  lea     rcx, [rbp+390h+var_3C0]
0x18004706c  mov     qword ptr [rsp+490h+var_468+8], rcx
0x180047071  lea     rcx, [rsp+20h]
0x180047076  mov     [rsp+490h+var_458], rcx
0x18004707b  lea     rcx, [rbp+390h+var_3E0]
0x18004707f  mov     [rsp+490h+var_450], rcx
0x180047084  mov     rdx, rax
0x180047087  lea     rcx, [rsp+490h+var_468+8]
0x18004708c  call    ??$?4V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@34@U534@U534@U534@U534@U534@U534@@?$tuple@AEAV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEA_NAEAV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@apdustatus_error@@@errorlib@@_NV?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U_Nil@45@U645@U645@U645@U645@U645@U645@@12@@Z; std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag> &,bool &,std::tr1::shared_ptr<FileSystem::ElementaryFile> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<apdustatus_error::tag>,bool,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
  ... truncated ...
```
