# Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema(std::basic_istream<char,std::char_traits<char>> &,wchar_t const *,std::basic_istream<char,std::char_traits<char>> &)

- ea: `0x18006b2d8`
- end: `0x18006c3bd`
- name: `?ReadSchema@ConstraintIndexBuilder@ISRC@Microsoft@@AEAAXAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@PEB_W0@Z`
- size: `4325`
- prototype: `__int64 __fastcall(Microsoft::ISRC::ConstraintIndexBuilder *this)`
- caller_count: `2`
- callee_count: `69`
- tags: `broker_com_uri`

## callers

- `0x180061438`
- `0x18006c3c4`

## callees

- `0x1800049e0`
- `0x180004a04`
- `0x180005e44`
- `0x180005e50`
- `0x1800062a0`
- `0x1800097dc`
- `0x180009dcc`
- `0x180009e14`
- `0x180009f40`
- `0x180009f64`
- `0x180009fa0`
- `0x18000a8d8`
- `0x18000b190`
- `0x18000b7bc`
- `0x18000c840`
- `0x18000c860`
- `0x18000cdb0`
- `0x18000cdf0`
- `0x18000f16c`
- `0x18000f1e8`
- `0x18000fb8c`
- `0x18001123c`
- `0x18001196c`
- `0x180011ea4`
- `0x180011f08`
- `0x180013c14`
- `0x18001c8f4`
- `0x18002d060`
- `0x1800316c0`
- `0x180032b08`
- `0x180051f7c`
- `0x180051fd4`
- `0x18005202c`
- `0x180052084`
- `0x1800520dc`
- `0x180052248`
- `0x180052360`
- `0x1800523b8`
- `0x180052410`
- `0x180052d94`
- `0x180053538`
- `0x180053f4c`
- `0x180059b58`
- `0x180059ccc`
- `0x180059f4c`
- `0x18005b1c4`
- `0x18005c38c`
- `0x18005c6a8`
- `0x18005d218`
- `0x18005d254`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b495`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b8a6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b946`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006ba20`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bac0`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bba1`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bc41`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bd38`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006be99`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bebe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bee6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bf41`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bfda`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b495`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b8a6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006b946`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006ba20`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bac0`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bba1`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bc41`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bd38`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006be99`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bebe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bee6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bf41`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18006bfda`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006b46e`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006be79`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006b46e`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006be79`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema(
        Microsoft::ISRC::ConstraintIndexBuilder *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rdx
  _BYTE *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  char v12; // r13
  unsigned __int64 v13; // rbx
  __int64 i; // rcx
  char *v15; // rax
  char *v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rax
  const wchar_t *v19; // rax
  __int64 v20; // rax
  unsigned __int64 j; // r9
  char v22; // r15
  __int64 v23; // rax
  const char *v24; // r8
  const char *v25; // r9
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  const char *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // rax
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *v33; // rbx
  __int64 *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  _BYTE *v38; // rax
  __int64 v39; // rdx
  const char *v40; // r8
  const char *v41; // r9
  void *v42; // rbx
  struct Microsoft::ISRC::StringAttributeBuilder *v43; // rbx
  __int64 *v44; // rax
  __int64 v45; // rdx
  boost::detail::shared_count *v46; // rcx
  _BYTE *v47; // rbx
  __int64 *v48; // rax
  __int64 v49; // rdx
  void *v50; // rbx
  struct Microsoft::ISRC::Number2AttributeBuilder *v51; // rbx
  __int64 *v52; // rax
  __int64 v53; // rdx
  _BYTE *v54; // rbx
  __int64 *v55; // rax
  __int64 v56; // rdx
  void *v57; // rbx
  struct Microsoft::ISRC::UnconstrainingAttributeBuilder *v58; // rbx
  __int64 *v59; // rax
  __int64 v60; // rdx
  _BYTE *v61; // rbx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  const char *v64; // r8
  _BYTE *v65; // rbx
  _QWORD *v66; // rax
  __int64 v67; // rdx
  _DWORD *v68; // rbx
  __int64 v69; // r8
  unsigned __int64 k; // rdi
  char *v71; // rax
  char *v72; // rsi
  __int64 v73; // r8
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  const char *v84; // rax
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rax
  const char *v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rax
  const char *v91; // rax
  __int64 m; // rbx
  _QWORD *v93; // rsi
  __int64 v94; // rdi
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rax
  unsigned int v98; // r15d
  __int64 v99; // rdx
  _QWORD *v100; // rdi
  _QWORD *v101; // rax
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v104)(); // [rsp+40h] [rbp-C0h]
  const char *v105; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v106; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v107; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v108; // [rsp+68h] [rbp-98h] BYREF
  __int64 v109; // [rsp+70h] [rbp-90h] BYREF
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *v110; // [rsp+78h] [rbp-88h] BYREF
  __int64 v111; // [rsp+80h] [rbp-80h] BYREF
  struct Microsoft::ISRC::Number2AttributeBuilder *v112; // [rsp+88h] [rbp-78h] BYREF
  __int64 v113; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v114; // [rsp+98h] [rbp-68h] BYREF
  __int64 v115; // [rsp+A0h] [rbp-60h] BYREF
  struct Microsoft::ISRC::StringAttributeBuilder *v116; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v117; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v118; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v119[3]; // [rsp+C0h] [rbp-40h] BYREF
  struct Microsoft::ISRC::UnconstrainingAttributeBuilder *v120; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v121; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v122[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v123[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v124[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v125[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v126[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v127[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE *v128; // [rsp+130h] [rbp+30h]
  _BYTE *v129; // [rsp+138h] [rbp+38h]
  void *v130; // [rsp+140h] [rbp+40h]
  _BYTE *v131; // [rsp+148h] [rbp+48h]
  void *v132; // [rsp+150h] [rbp+50h]
  _BYTE *v133; // [rsp+158h] [rbp+58h]
  void *v134; // [rsp+160h] [rbp+60h]
  Microsoft::ISRC::ConstraintIndexBuilder::Segment *v135; // [rsp+168h] [rbp+68h]
  _BYTE v136[272]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v137; // [rsp+280h] [rbp+180h] BYREF
  __int64 v138; // [rsp+290h] [rbp+190h]
  _BYTE v139[32]; // [rsp+298h] [rbp+198h] BYREF
  __int128 v140; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v141[16]; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned __int64 v142; // [rsp+2D8h] [rbp+1D8h]
  __int128 v143; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v144; // [rsp+2F8h] [rbp+1F8h]
  __int128 v145; // [rsp+308h] [rbp+208h] BYREF
  __int64 v146; // [rsp+318h] [rbp+218h]
  _QWORD v147[12]; // [rsp+320h] [rbp+220h] BYREF

  v106 = a4;
  std::string::string(v141);
  v137 = 0;
  v138 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v137);
  v145 = 0;
  v146 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v145);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v7 + 4LL) + v7 + 16) & 6) != 0 )
  {
    Microsoft::ISRC::InvalidUsageException::InvalidUsageException(
      (Microsoft::ISRC::InvalidUsageException *)&pExceptionObject,
      "Schema file not found.");
    throw (Microsoft::ISRC::InvalidUsageException *)&pExceptionObject;
  }
  do
  {
    do
      std::getline<char,std::char_traits<char>,std::allocator<char>>(a2, v141);
    while ( !v142 );
    v8 = (_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v141);
  }
  while ( *v8 == 35 );
  LOBYTE(v9) = 9;
  Microsoft::ISRC::StringSplit(v8, v9, &v137);
  v10 = -1;
  do
    ++v10;
  while ( *(_BYTE *)(*(_QWORD *)v137 + v10) );
  std::string::_Assign<char>(this);
  v11 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v11 )
    std::default_delete<Microsoft::ISRC::CompletionTrie<Microsoft::ISRC::Void>>::operator()();
  std::string::string(v139, &word_1801017B2);
  *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::string,unsigned int,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned int>>,0>>::_Try_emplace<std::string,>(
                           (_QWORD *)this + 20,
                           (__int64)&pExceptionObject,
                           (__int64)v139)
            + 48LL) = 0;
  std::string::_Tidy_deallocate(v139);
  v12 = 1;
  v13 = 1;
  for ( i = v137; v13 < (__int64)(*((_QWORD *)&v137 + 1) - v137) >> 3; i = v137 )
  {
    v15 = strchr(*(const char **)(i + 8 * v13), 61);
    v16 = v15;
    if ( v15 )
    {
      *v15 = 0;
      if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * v13)) )
      {
        std::wstring::wstring(v139, a3);
        v17 = ConvertMultiByteToWideChar(&pExceptionObject, v16 + 1);
        v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
        std::wstring::_Append<wchar_t>(v139, v18);
        std::wstring::_Tidy_deallocate(&pExceptionObject);
        v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v139);
        Microsoft::ISRC::ConstraintIndexBuilder::ReadConversions(this, v19);
        std::wstring::_Tidy_deallocate(v139);
      }
    }
    ++v13;
  }
  if ( !*((_QWORD *)this + 15) )
  {
    std::string::string(v139, 4);
    memset_0(v147, 0, sizeof(v147));
    Microsoft::ISRC::CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>::CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>(v147);
    v20 = std::string::string(&pExceptionObject, v139);
    Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::Add(v147, v20, 0);
    Microsoft::ISRC::CompletionTrieBuilder<unsigned int>::Finalize(v147);
    v107 = Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::ToTrie(v147);
    std::unique_ptr<Microsoft::ISRC::CompletionTrie<unsigned int>>::operator=<std::default_delete<Microsoft::ISRC::CompletionTrie<unsigned int>>,0>(
      (__int64 *)this + 15,
      &v107);
    std::unique_ptr<Microsoft::ISRC::CompletionTrie<std::pair<unsigned int,unsigned int>>>::~unique_ptr<Microsoft::ISRC::CompletionTrie<std::pair<unsigned int,unsigned int>>>(&v107);
    Microsoft::ISRC::CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>::~CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>(v147);
    std::string::_Tidy_deallocate(v139);
  }
  v143 = 0;
  v144 = 0;
  std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(&v143);
  std::vector<bool>::resize(&v143, *((_QWORD *)this + 22));
  for ( j = 0; j < *((_QWORD *)&v144 + 1); ++j )
    *(_DWORD *)(v143 + 4 * (j >> 5)) &= ~(1 << (j & 0x1F));
LABEL_18:
  v22 = 1;
  while ( 1 )
  {
    v23 = std::getline<char,std::char_traits<char>,std::allocator<char>>(a2, v141);
    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v23 + 4LL) + v23 + 16) & 6) != 0 )
      break;
    if ( v12 )
    {
      if ( v142 )
      {
        if ( *(_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v141) != 35 )
        {
          v26 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                  v136,
                  "Expected blank line after domain and before first segment ( %s%s )",
                  v24,
                  v25);
          v27 = std::string::substr(v141, &v118, 0, 64);
          v106 = std::_String_val<std::_Simple_types<char>>::_Myptr(v27);
          *(_QWORD *)&pExceptionObject = &v106;
          *((_QWORD *)&pExceptionObject + 1) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          v104 = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v28 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v26,
                  &pExceptionObject);
          v29 = "...";
          if ( v142 <= 0x40 )
            v29 = (const char *)&word_1801017B2;
          v105 = v29;
          *(_QWORD *)&pExceptionObject = &v105;
          *((_QWORD *)&pExceptionObject + 1) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          v104 = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v30 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v28,
                  &pExceptionObject);
          v31 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v30, &v120);
          v32 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v31);
          Microsoft::ISRC::InvalidDataException::InvalidDataException(
            (Microsoft::ISRC::InvalidDataException *)v139,
            v32);
          throw (Microsoft::ISRC::InvalidDataException *)v139;
        }
      }
      else
      {
        v12 = 0;
      }
    }
    else if ( v22 )
    {
      if ( v142 && *(_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v141) != 35 )
      {
        v135 = (Microsoft::ISRC::ConstraintIndexBuilder::Segment *)operator new(0xE8u);
        v33 = (struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *)Microsoft::ISRC::ConstraintIndexBuilder::Segment::Segment(v135);
        v110 = v33;
        v111 = 0;
        v34 = (__int64 *)boost::detail::shared_count::shared_count((boost::detail::shared_count *)&v107, v33);
        v35 = v111;
        v111 = *v34;
        *v34 = v35;
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v107);
        boost::detail::sp_enable_shared_from_this(&v110, v33, v33);
        v37 = *((_QWORD *)this + 5);
        if ( v37 == *((_QWORD *)this + 6) )
        {
          std::vector<boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>::_Emplace_reallocate<boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>(
            (char *)this + 32,
            v37,
            &v110);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>>>::construct<boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>,boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>>(
            v36,
            v37,
            &v110);
          *((_QWORD *)this + 5) += 16LL;
        }
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v111);
        std::string::operator=(*(_QWORD *)(*((_QWORD *)this + 5) - 16LL), v141);
        v22 = 0;
      }
    }
    else
    {
      if ( !v142 )
        goto LABEL_18;
      v38 = (_BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(v141);
      if ( *v38 != 35 )
      {
        LOBYTE(v39) = 9;
        Microsoft::ISRC::StringSplit(v38, v39, &v137);
        if ( (unsigned __int64)((__int64)(*((_QWORD *)&v137 + 1) - v137) >> 3) < 2 )
        {
          v85 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                  v136,
                  "Invalid attribute.  Expected: <attrName>   <attrType>   [NoIndex]   [NoShow]   [Conversions=<convFileP"
                  "attern>]   [Synonyms=<synFile>] ( Found: %s%s )",
                  v40,
                  v41);
          v86 = std::string::substr(v141, &v118, 0, 64);
          v106 = std::_String_val<std::_Simple_types<char>>::_Myptr(v86);
          *(_QWORD *)&pExceptionObject = &v106;
          *((_QWORD *)&pExceptionObject + 1) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          v104 = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v87 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v85,
                  &pExceptionObject);
          v88 = "...";
          if ( v142 <= 0x40 )
            v88 = (const char *)&word_1801017B2;
          v105 = v88;
          *(_QWORD *)&pExceptionObject = &v105;
          *((_QWORD *)&pExceptionObject + 1) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          v104 = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v89 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v87,
                  &pExceptionObject);
          v90 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v89, &v120);
          v91 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v90);
          Microsoft::ISRC::InvalidDataException::InvalidDataException(
            (Microsoft::ISRC::InvalidDataException *)v139,
            v91);
          throw (Microsoft::ISRC::InvalidDataException *)v139;
        }
        v140 = 0;
        if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
        {
          if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
          {
            if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
            {
              if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
              {
                if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
                {
                  if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
                  {
                    if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8)) )
                    {
                      v81 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                              v136,
                              "Unexpected attribute type.  Expected: String, Number, Number2, DateTime, Unconstraining ( Found: %s )",
                              v64);
                      *(_QWORD *)&pExceptionObject = v137 + 8;
                      *((_QWORD *)&pExceptionObject + 1) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
                      v104 = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
                      v82 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                              v81,
                              &pExceptionObject);
                      v83 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v82, &v118);
                      v84 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v83);
                      Microsoft::ISRC::InvalidDataException::InvalidDataException(
                        (Microsoft::ISRC::InvalidDataException *)v139,
                        v84);
                      throw (Microsoft::ISRC::InvalidDataException *)v139;
                    }
                    v65 = operator new(0x200u);
                    v128 = v65;
                    memset_0(v65, 0, 0x200u);
                    Microsoft::ISRC::AttributeBuilder::AttributeBuilder((Microsoft::ISRC::AttributeBuilder *)v65);
                    *(_QWORD *)v65 = &Microsoft::ISRC::RangeAttributeBuilder<Microsoft::ISRC::DateTime,6,Microsoft::ISRC::DateTimeRange>::`vftable';
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 360);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 384);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 408);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 432);
                    v65[456] = 1;
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 464);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v65 + 488);
                    pExceptionObject = (unsigned __int64)v65;
                    v66 = (_QWORD *)boost::detail::shared_count::shared_count(&v105, v65);
                    v67 = *((_QWORD *)&pExceptionObject + 1);
                    *((_QWORD *)&pExceptionObject + 1) = *v66;
                    *v66 = v67;
                    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v105);
                    boost::detail::sp_enable_shared_from_this(&pExceptionObject, v65, v65);
                    boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &pExceptionObject);
                    v46 = (boost::detail::shared_count *)((char *)&pExceptionObject + 8);
                  }
                  else
                  {
                    v61 = operator new(0x200u);
                    v129 = v61;
                    memset_0(v61, 0, 0x200u);
                    Microsoft::ISRC::AttributeBuilder::AttributeBuilder((Microsoft::ISRC::AttributeBuilder *)v61);
                    *(_QWORD *)v61 = &Microsoft::ISRC::RangeAttributeBuilder<double,5,Microsoft::ISRC::NumericRange>::`vftable';
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 360);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 384);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 408);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 432);
                    v61[456] = 1;
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 464);
                    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v61 + 488);
                    v118 = v61;
                    v119[0] = 0;
                    v62 = (_QWORD *)boost::detail::shared_count::shared_count(v127, v61);
                    v63 = v119[0];
                    v119[0] = *v62;
                    *v62 = v63;
                    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v127);
                    boost::detail::sp_enable_shared_from_this(&v118, v61, v61);
                    boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v118);
                    v46 = (boost::detail::shared_count *)v119;
                  }
                }
                else
                {
                  v57 = operator new(0x260u);
                  v130 = v57;
                  memset_0(v57, 0, 0x260u);
                  v58 = (struct Microsoft::ISRC::UnconstrainingAttributeBuilder *)Microsoft::ISRC::UnconstrainingAttributeBuilder::UnconstrainingAttributeBuilder((Microsoft::ISRC::UnconstrainingAttributeBuilder *)v57);
                  v120 = v58;
                  v121 = 0;
                  v59 = (__int64 *)boost::detail::shared_count::shared_count((boost::detail::shared_count *)v126, v58);
                  v60 = v121;
                  v121 = *v59;
                  *v59 = v60;
                  boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v126);
                  boost::detail::sp_enable_shared_from_this(&v120, v58, v58);
                  boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v120);
                  v46 = (boost::detail::shared_count *)&v121;
                }
              }
              else
              {
                v54 = operator new(0x1D0u);
                v131 = v54;
                memset_0(v54, 0, 0x1D0u);
                Microsoft::ISRC::AttributeBuilder::AttributeBuilder((Microsoft::ISRC::AttributeBuilder *)v54);
                *(_QWORD *)v54 = &Microsoft::ISRC::OrderedAttributeBuilder<Microsoft::ISRC::DateTime,3>::`vftable';
                std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v54 + 360);
                std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v54 + 384);
                v54[408] = 3;
                std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v54 + 416);
                std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v54 + 440);
                v108 = v54;
                v109 = 0;
                v55 = (__int64 *)boost::detail::shared_count::shared_count(v125, v54);
                v56 = v109;
                v109 = *v55;
                *v55 = v56;
                boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v125);
                boost::detail::sp_enable_shared_from_this(&v108, v54, v54);
                boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v108);
                v46 = (boost::detail::shared_count *)&v109;
              }
            }
            else
            {
              v50 = operator new(0x210u);
              v132 = v50;
              memset_0(v50, 0, 0x210u);
              v51 = (struct Microsoft::ISRC::Number2AttributeBuilder *)Microsoft::ISRC::Number2AttributeBuilder::Number2AttributeBuilder((Microsoft::ISRC::Number2AttributeBuilder *)v50);
              v112 = v51;
              v113 = 0;
              v52 = (__int64 *)boost::detail::shared_count::shared_count((boost::detail::shared_count *)v124, v51);
              v53 = v113;
              v113 = *v52;
              *v52 = v53;
              boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v124);
              boost::detail::sp_enable_shared_from_this(&v112, v51, v51);
              boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v112);
              v46 = (boost::detail::shared_count *)&v113;
            }
          }
          else
          {
            v47 = operator new(0x1D0u);
            v133 = v47;
            memset_0(v47, 0, 0x1D0u);
            Microsoft::ISRC::AttributeBuilder::AttributeBuilder((Microsoft::ISRC::AttributeBuilder *)v47);
            *(_QWORD *)v47 = &Microsoft::ISRC::OrderedAttributeBuilder<double,1>::`vftable';
            std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v47 + 360);
            std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v47 + 384);
            v47[408] = 3;
            std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v47 + 416);
            std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v47 + 440);
            v114 = v47;
            v115 = 0;
            v48 = (__int64 *)boost::detail::shared_count::shared_count(v123, v47);
            v49 = v115;
            v115 = *v48;
            *v48 = v49;
            boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v123);
            boost::detail::sp_enable_shared_from_this(&v114, v47, v47);
            boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v114);
            v46 = (boost::detail::shared_count *)&v115;
          }
        }
        else
        {
          v42 = operator new(0x380u);
          v134 = v42;
          memset_0(v42, 0, 0x380u);
          v43 = (struct Microsoft::ISRC::StringAttributeBuilder *)Microsoft::ISRC::StringAttributeBuilder::StringAttributeBuilder((Microsoft::ISRC::StringAttributeBuilder *)v42);
          v116 = v43;
          v117 = 0;
          v44 = (__int64 *)boost::detail::shared_count::shared_count((boost::detail::shared_count *)v122, v43);
          v45 = v117;
          v117 = *v44;
          *v44 = v45;
          boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v122);
          boost::detail::sp_enable_shared_from_this(&v116, v43, v43);
          boost::shared_ptr<Microsoft::ISRC::CSGSuggestionIterator>::operator=(&v140, &v116);
          v46 = (boost::detail::shared_count *)&v117;
        }
        boost::detail::shared_count::~shared_count(v46);
        v68 = (_DWORD *)v140;
        v69 = -1;
        do
          ++v69;
        while ( *(_BYTE *)(*(_QWORD *)v137 + v69) );
        std::string::_Assign<char>(v140 + 16);
        for ( k = 2; k < (__int64)(*((_QWORD *)&v137 + 1) - v137) >> 3; ++k )
        {
          v71 = strchr(*(const char **)(v137 + 8 * k), 61);
          v72 = v71;
          if ( v71 )
          {
            *v71 = 0;
            if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * k)) )
            {
              if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * k)) )
              {
                if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * k)) )
                {
                  if ( (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v68 + 16LL))(v68) != 4 )
                  {
                    Microsoft::ISRC::InvalidUsageException::InvalidUsageException(
                      (Microsoft::ISRC::InvalidUsageException *)v139,
                      "UnconstrainingValues can only be specified on unconstraining attributes.");
                    throw (Microsoft::ISRC::InvalidUsageException *)v139;
                  }
                  v76 = -1;
                  do
                    ++v76;
                  while ( v72[v76 + 1] );
                  std::string::_Assign<char>(v68 + 144);
                }
              }
              else
              {
                if ( (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v68 + 16LL))(v68) )
                {
                  if ( (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v68 + 16LL))(v68) != 4 )
                  {
                    Microsoft::ISRC::InvalidUsageException::InvalidUsageException(
                      (Microsoft::ISRC::InvalidUsageException *)v139,
                      "Conversions can only be specified on string and unconstraining attributes.");
                    throw (Microsoft::ISRC::InvalidUsageException *)v139;
                  }
                  v74 = std::vector<char *>::vector<char *>(v139, &v145);
                  v75 = (__int64)(v68 + 132);
                }
                else
                {
                  v74 = std::vector<char *>::vector<char *>(v139, &v145);
                  v75 = (__int64)(v68 + 180);
                }
                Microsoft::ISRC::ConstraintIndexBuilder::PopulateConversions(
                  (_DWORD)this,
                  (unsigned int)&v143,
                  (_DWORD)v72 + 1,
                  v74,
                  v75);
              }
            }
            else
            {
              v73 = -1;
              do
                ++v73;
              while ( v72[v73 + 1] );
              std::string::_Assign<char>(v68 + 12);
              std::ostream::operator<<(v68 + 24, *(_QWORD *)(*(int *)(*(_QWORD *)v106 + 4LL) + v106 + 72));
            }
          }
          else if ( (unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * k)) )
          {
            if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v137 + 8 * k)) )
              v68[82] |= 2u;
          }
          else
          {
            v68[82] |= 1u;
          }
        }
        v77 = *((_QWORD *)this + 5);
        v78 = *(_QWORD *)(v77 - 16) + 32LL;
        v79 = *(_QWORD *)(*(_QWORD *)(v77 - 16) + 40LL);
        if ( v79 == *(_QWORD *)(*(_QWORD *)(v77 - 16) + 48LL) )
        {
          std::vector<boost::shared_ptr<Microsoft::ISRC::AttributeBuilder>>::_Emplace_reallocate<boost::shared_ptr<Microsoft::ISRC::AttributeBuilder> const &>(
            v78,
            v79,
            &v140);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<boost::shared_ptr<Microsoft::ISRC::CSGSuggestion>>>::construct<boost::shared_ptr<Microsoft::ISRC::CSGSuggestion>,boost::shared_ptr<Microsoft::ISRC::CSGSuggestion> const &>(
            v78,
            v79,
            &v140);
          *(_QWORD *)(v80 + 8) += 16LL;
        }
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v140 + 8));
      }
    }
  }
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    Microsoft::ISRC::InvalidUsageException::InvalidUsageException(
      (Microsoft::ISRC::InvalidUsageException *)v139,
      "Schema file not valid; Found 0 segments.");
    throw (Microsoft::ISRC::InvalidUsageException *)v139;
  }
  Microsoft::ISRC::ConstraintIndexBuilder::BuildFilterConversionTrie(this, &v143);
  for ( m = *((_QWORD *)this + 4); m != *((_QWORD *)this + 5); m += 16 )
  {
    pExceptionObject = 0;
    v93 = *(_QWORD **)m;
    *(_QWORD *)&pExceptionObject = *(_QWORD *)m;
    v94 = *(_QWORD *)(m + 8);
    *((_QWORD *)&pExceptionObject + 1) = v94;
    if ( v94 )
      _InterlockedIncrement((volatile signed __int32 *)(v94 + 8));
    v95 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>>,0>>::_Try_emplace<std::string const &,>(
                       (float *)this + 14,
                       (__int64)&v120,
                       (__int64)v93);
    if ( v94 )
      _InterlockedIncrement((volatile signed __int32 *)(v94 + 8));
    v118 = *(_BYTE **)(v95 + 48);
    *(_QWORD *)(v95 + 48) = v93;
    v96 = *(_QWORD *)(v95 + 56);
    *(_QWORD *)(v95 + 56) = v94;
    v119[0] = v96;
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v119);
    v97 = v93[5];
    if ( v93[4] == v97 )
    {
      Microsoft::ISRC::InvalidUsageException::InvalidUsageException(
        (Microsoft::ISRC::InvalidUsageException *)v139,
        "Schema file not valid; Found 0 attributes for a segment.");
      throw (Microsoft::ISRC::InvalidUsageException *)v139;
    }
    v98 = 0;
    if ( (v97 - v93[4]) >> 4 )
    {
      do
      {
        v99 = 16LL * v98;
        *(_DWORD *)(*(_QWORD *)(v99 + v93[4]) + 332LL) = v98;
        v100 = (_QWORD *)(v99 + v93[4]);
        v101 = (_QWORD *)std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::AttributeBuilder>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::AttributeBuilder>>>,0>>::_Try_emplace<std::string const &,>(
                           v93 + 7,
                           (__int64)&v108,
                           *v100 + 16LL);
        boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::StringToAttribute>>::operator=(*v101 + 48LL, v100);
        ++v98;
      }
      while ( v98 < (unsigned __int64)((__int64)(v93[5] - v93[4]) >> 4) );
    }
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&pExceptionObject + 8));
  }
  std::vector<std::pair<unsigned short,unsigned short>>::~vector<std::pair<unsigned short,unsigned short>>(&v143);
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v145);
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v137);
  return std::string::_Tidy_deallocate(v141);
}

```

## disassembly

```asm
0x18006b2d8  push    rbp
0x18006b2da  push    rbx
0x18006b2db  push    rsi
0x18006b2dc  push    rdi
0x18006b2dd  push    r12
0x18006b2df  push    r13
0x18006b2e1  push    r14
0x18006b2e3  push    r15
0x18006b2e5  lea     rbp, [rsp-298h]
0x18006b2ed  sub     rsp, 398h
0x18006b2f4  mov     rax, cs:__security_cookie
0x18006b2fb  xor     rax, rsp
0x18006b2fe  mov     [rbp+2D0h+var_50], rax
0x18006b305  mov     [rsp+3D0h+var_378], r9
0x18006b30a  mov     r15, r8
0x18006b30d  mov     r12, rdx
0x18006b310  mov     r14, rcx
0x18006b313  lea     rcx, [rbp+2D0h+var_108]
0x18006b31a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18006b31f  nop
0x18006b320  xorps   xmm1, xmm1
0x18006b323  xor     eax, eax
0x18006b325  movups  [rbp+2D0h+var_150], xmm1
0x18006b32c  mov     [rbp+2D0h+var_140], rax
0x18006b333  lea     rcx, [rbp+2D0h+var_150]
0x18006b33a  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18006b33f  nop
0x18006b340  xorps   xmm0, xmm0
0x18006b343  xor     eax, eax
0x18006b345  movups  [rbp+2D0h+var_C8], xmm0
0x18006b34c  mov     [rbp+2D0h+var_B8], rax
0x18006b353  lea     rcx, [rbp+2D0h+var_C8]
0x18006b35a  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18006b35f  nop
0x18006b360  mov     rax, [rdx]
0x18006b363  movsxd  rcx, dword ptr [rax+4]
0x18006b367  test    byte ptr [rcx+rdx+10h], 6
0x18006b36c  jz      short loc_18006B391
0x18006b36e  lea     rdx, aSchemaFileNotF; "Schema file not found."
0x18006b375  lea     rcx, [rsp+3D0h+pExceptionObject]; this
0x18006b37a  call    ??0InvalidUsageException@ISRC@Microsoft@@QEAA@PEBD@Z; Microsoft::ISRC::InvalidUsageException::InvalidUsageException(char const *)
0x18006b37f  lea     rdx, _TI3?AVInvalidUsageException@ISRC@Microsoft@@; pThrowInfo
0x18006b386  lea     rcx, [rsp+3D0h+pExceptionObject]; pExceptionObject
0x18006b38b  call    _CxxThrowException_0
0x18006b391  xor     esi, esi
0x18006b393  lea     rdx, [rbp+2D0h+var_108]
0x18006b39a  mov     rcx, r12
0x18006b39d  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &,std::string &)
0x18006b3a2  cmp     [rbp+2D0h+var_F8], rsi
0x18006b3a9  jbe     short loc_18006B393
0x18006b3ab  lea     rcx, [rbp+2D0h+var_108]
0x18006b3b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006b3b7  cmp     byte ptr [rax], 23h ; '#'
0x18006b3ba  jz      short loc_18006B393
0x18006b3bc  lea     r8, [rbp+2D0h+var_150]
0x18006b3c3  mov     dl, 9
0x18006b3c5  mov     rcx, rax
0x18006b3c8  call    ?StringSplit@ISRC@Microsoft@@YAXPEADDAEAV?$vector@PEADV?$allocator@PEAD@std@@@std@@@Z; Microsoft::ISRC::StringSplit(char *,char,std::vector<char *> &)
0x18006b3cd  mov     rax, qword ptr [rbp+2D0h+var_150]
0x18006b3d4  mov     rdx, [rax]
0x18006b3d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006b3db  inc     r8
0x18006b3de  cmp     [rdx+r8], sil
0x18006b3e2  jnz     short loc_18006B3DB
0x18006b3e4  mov     rcx, r14
0x18006b3e7  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18006b3ec  lea     rdi, [r14+78h]
0x18006b3f0  mov     rdx, [rdi]
0x18006b3f3  mov     [rdi], rsi
0x18006b3f6  test    rdx, rdx
0x18006b3f9  jz      short loc_18006B400
0x18006b3fb  call    ??R?$default_delete@V?$CompletionTrie@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@@std@@QEBAXPEAV?$CompletionTrie@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@@Z; std::default_delete<Microsoft::ISRC::CompletionTrie<Microsoft::ISRC::Void>>::operator()(Microsoft::ISRC::CompletionTrie<Microsoft::ISRC::Void> *)
0x18006b400  lea     rdx, word_1801017B2
0x18006b407  lea     rcx, [rbp+2D0h+var_138]
0x18006b40e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006b413  nop
0x18006b414  lea     r8, [rbp+2D0h+var_138]
0x18006b41b  lea     rdx, [rsp+3D0h+pExceptionObject]
0x18006b420  lea     rcx, [r14+0A0h]
0x18006b427  call    ??$_Try_emplace@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>>::_Try_emplace<std::string,>(std::string &&)
0x18006b42c  mov     rcx, [rax]
0x18006b42f  mov     [rcx+30h], esi
0x18006b432  lea     rcx, [rbp+2D0h+var_138]
0x18006b439  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006b43e  mov     r13d, 1
0x18006b444  mov     ebx, r13d
0x18006b447  mov     rax, qword ptr [rbp+2D0h+var_150+8]
0x18006b44e  mov     rcx, qword ptr [rbp+2D0h+var_150]
0x18006b455  sub     rax, rcx
0x18006b458  sar     rax, 3
0x18006b45c  cmp     rax, r13
0x18006b45f  jbe     loc_18006B52A
0x18006b465  mov     edx, 3Dh ; '='; Val
0x18006b46a  mov     rcx, [rcx+rbx*8]; Str
0x18006b46e  call    cs:__imp_strchr
0x18006b474  mov     rsi, rax
0x18006b477  test    rax, rax
0x18006b47a  jz      loc_18006B507
0x18006b480  mov     byte ptr [rax], 0
0x18006b483  lea     rdx, aConversions; "Conversions"
0x18006b48a  mov     rcx, qword ptr [rbp+2D0h+var_150]
0x18006b491  mov     rcx, [rcx+rbx*8]
0x18006b495  call    cs:__imp__o__stricmp
0x18006b49b  test    eax, eax
0x18006b49d  jnz     short loc_18006B507
0x18006b49f  mov     rdx, r15
0x18006b4a2  lea     rcx, [rbp+2D0h+var_138]
0x18006b4a9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006b4ae  nop
0x18006b4af  lea     rdx, [rsi+1]
0x18006b4b3  lea     rcx, [rsp+3D0h+pExceptionObject]
0x18006b4b8  call    ?ConvertMultiByteToWideChar@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD@Z; ConvertMultiByteToWideChar(char const *)
0x18006b4bd  mov     r8, [rax+10h]
0x18006b4c1  mov     rcx, rax
0x18006b4c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b4c9  mov     rdx, rax
0x18006b4cc  lea     rcx, [rbp+2D0h+var_138]
0x18006b4d3  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006b4d8  nop
0x18006b4d9  lea     rcx, [rsp+3D0h+pExceptionObject]
0x18006b4de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b4e3  lea     rcx, [rbp+2D0h+var_138]
0x18006b4ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b4ef  mov     rdx, rax; wchar_t *
0x18006b4f2  mov     rcx, r14; this
0x18006b4f5  call    ?ReadConversions@ConstraintIndexBuilder@ISRC@Microsoft@@AEAAXPEB_W@Z; Microsoft::ISRC::ConstraintIndexBuilder::ReadConversions(wchar_t const *)
0x18006b4fa  nop
0x18006b4fb  lea     rcx, [rbp+2D0h+var_138]
0x18006b502  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b507  add     rbx, r13
0x18006b50a  mov     rax, qword ptr [rbp+2D0h+var_150+8]
0x18006b511  mov     rcx, qword ptr [rbp+2D0h+var_150]
0x18006b518  sub     rax, rcx
0x18006b51b  sar     rax, 3
0x18006b51f  cmp     rbx, rax
0x18006b522  jb      loc_18006B465
0x18006b528  xor     esi, esi
0x18006b52a  cmp     [rdi], rsi
0x18006b52d  jnz     loc_18006B5D7
0x18006b533  xor     r8d, r8d
0x18006b536  lea     edx, [r8+4]
0x18006b53a  lea     rcx, [rbp+2D0h+var_138]
0x18006b541  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x18006b546  nop
0x18006b547  xor     edx, edx; Val
0x18006b549  lea     r8d, [rdx+60h]; Size
0x18006b54d  lea     rcx, [rbp+2D0h+var_B0]; void *
0x18006b554  call    memset_0
0x18006b559  lea     rcx, [rbp+2D0h+var_B0]
0x18006b560  call    ??0?$CompletionTrieBuilder@U?$pair@II@std@@@ISRC@Microsoft@@QEAA@XZ; Microsoft::ISRC::CompletionTrieBuilder<std::pair<uint,uint>>::CompletionTrieBuilder<std::pair<uint,uint>>(void)
0x18006b565  nop
0x18006b566  lea     rdx, [rbp+2D0h+var_138]
0x18006b56d  lea     rcx, [rsp+3D0h+pExceptionObject]
0x18006b572  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18006b577  xor     r8d, r8d
0x18006b57a  mov     rdx, rax
0x18006b57d  lea     rcx, [rbp+2D0h+var_B0]
0x18006b584  call    ?Add@?$CompletionTrieBuilder@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IUVoid@23@@Z; Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::Add(std::string,uint,Microsoft::ISRC::Void)
0x18006b589  lea     rcx, [rbp+2D0h+var_B0]
0x18006b590  call    ?Finalize@?$CompletionTrieBuilder@I@ISRC@Microsoft@@QEAAXXZ; Microsoft::ISRC::CompletionTrieBuilder<uint>::Finalize(void)
0x18006b595  lea     rcx, [rbp+2D0h+var_B0]
0x18006b59c  call    ?ToTrie@?$CompletionTrieBuilder@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@QEBAPEAV?$CompletionTrie@UVoid@ISRC@Microsoft@@@23@XZ; Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::ToTrie(void)
0x18006b5a1  mov     [rsp+3D0h+var_370], rax
0x18006b5a6  lea     rdx, [rsp+3D0h+var_370]
0x18006b5ab  mov     rcx, rdi
0x18006b5ae  call    ??$?4U?$default_delete@V?$CompletionTrie@I@ISRC@Microsoft@@@std@@$0A@@?$unique_ptr@V?$CompletionTrie@I@ISRC@Microsoft@@U?$default_delete@V?$CompletionTrie@I@ISRC@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::ISRC::CompletionTrie<uint>>::operator=<std::default_delete<Microsoft::ISRC::CompletionTrie<uint>>,0>(std::unique_ptr<Microsoft::ISRC::CompletionTrie<uint>> &&)
0x18006b5b3  lea     rcx, [rsp+3D0h+var_370]
0x18006b5b8  call    ??1?$unique_ptr@V?$CompletionTrie@U?$pair@II@std@@@ISRC@Microsoft@@U?$default_delete@V?$CompletionTrie@U?$pair@II@std@@@ISRC@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::ISRC::CompletionTrie<std::pair<uint,uint>>>::~unique_ptr<Microsoft::ISRC::CompletionTrie<std::pair<uint,uint>>>(void)
0x18006b5bd  nop
0x18006b5be  lea     rcx, [rbp+2D0h+var_B0]
0x18006b5c5  call    ??1?$CompletionTrieBuilder@U?$pair@II@std@@@ISRC@Microsoft@@QEAA@XZ; Microsoft::ISRC::CompletionTrieBuilder<std::pair<uint,uint>>::~CompletionTrieBuilder<std::pair<uint,uint>>(void)
0x18006b5ca  nop
0x18006b5cb  lea     rcx, [rbp+2D0h+var_138]
0x18006b5d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006b5d7  xorps   xmm0, xmm0
0x18006b5da  movups  [rbp+2D0h+var_E8], xmm0
0x18006b5e1  movups  [rbp+2D0h+var_D8], xmm0
0x18006b5e8  lea     rcx, [rbp+2D0h+var_E8]
0x18006b5ef  call    ??0?$_Vb_val@V?$allocator@_N@std@@@std@@QEAA@AEBV?$allocator@_N@1@@Z; std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(std::allocator<bool> const &)
0x18006b5f4  nop
0x18006b5f5  mov     rdx, [r14+0B0h]
0x18006b5fc  lea     rcx, [rbp+2D0h+var_E8]
0x18006b603  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x18006b608  mov     r9, rsi
0x18006b60b  cmp     qword ptr [rbp+2D0h+var_D8+8], rsi
0x18006b612  jbe     short loc_18006B63F
0x18006b614  mov     r8, qword ptr [rbp+2D0h+var_E8]
0x18006b61b  mov     rdx, r9
0x18006b61e  shr     rdx, 5
0x18006b622  mov     ecx, r9d
0x18006b625  and     ecx, 1Fh
0x18006b628  mov     eax, [r8+rdx*4]
0x18006b62c  btr     eax, ecx
0x18006b62f  mov     [r8+rdx*4], eax
0x18006b633  add     r9, r13
0x18006b636  cmp     r9, qword ptr [rbp+2D0h+var_D8+8]
0x18006b63d  jb      short loc_18006B614
0x18006b63f  mov     edi, 1D0h
0x18006b644  mov     r15b, 1
0x18006b647  lea     rdx, [rbp+2D0h+var_108]
0x18006b64e  mov     rcx, r12
0x18006b651  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &,std::string &)
0x18006b656  mov     rcx, [rax]
0x18006b659  movsxd  rdx, dword ptr [rcx+4]
0x18006b65d  test    byte ptr [rdx+rax+10h], 6
0x18006b662  jnz     loc_18006C20E
0x18006b668  test    r13b, r13b
0x18006b66b  jz      loc_18006B771
0x18006b671  cmp     [rbp+2D0h+var_F8], rsi
0x18006b678  jnz     short loc_18006B67F
0x18006b67a  mov     r13b, sil
0x18006b67d  jmp     short loc_18006B647
0x18006b67f  lea     rcx, [rbp+2D0h+var_108]
0x18006b686  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006b68b  cmp     byte ptr [rax], 23h ; '#'
0x18006b68e  jz      short loc_18006B647
0x18006b690  lea     rdx, aExpectedBlankL; "Expected blank line after domain and be"...
0x18006b697  lea     rcx, [rbp+2D0h+var_260]
0x18006b69b  call    ??0?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEAA@PEBD@Z; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(char const *)
0x18006b6a0  mov     rbx, rax
0x18006b6a3  mov     r9d, 40h ; '@'
0x18006b6a9  xor     r8d, r8d
0x18006b6ac  lea     rdx, [rbp+2D0h+var_318]
0x18006b6b0  lea     rcx, [rbp+2D0h+var_108]
0x18006b6b7  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x18006b6bc  nop
0x18006b6bd  mov     rcx, rax
0x18006b6c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006b6c5  mov     [rsp+3D0h+var_378], rax
0x18006b6ca  lea     rax, [rsp+3D0h+var_378]
0x18006b6cf  mov     qword ptr [rsp+3D0h+pExceptionObject], rax
0x18006b6d4  lea     rdi, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18006b6db  mov     qword ptr [rsp+3D0h+pExceptionObject+8], rdi
0x18006b6e0  lea     rsi, ??$call_put_last@DU?$char_traits@D@std@@QEBD@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>(std::ostream &,void const *)
0x18006b6e7  mov     [rsp+3D0h+var_390], rsi
0x18006b6ec  lea     rdx, [rsp+3D0h+pExceptionObject]
0x18006b6f1  mov     rcx, rbx
0x18006b6f4  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x18006b6f9  lea     rcx, asc_180103728; "..."
0x18006b700  cmp     [rbp+2D0h+var_F8], 40h ; '@'
0x18006b708  lea     rdx, word_1801017B2
0x18006b70f  cmovbe  rcx, rdx
0x18006b713  mov     [rsp+3D0h+var_380], rcx
0x18006b718  lea     rcx, [rsp+3D0h+var_380]
0x18006b71d  mov     qword ptr [rsp+3D0h+pExceptionObject], rcx
0x18006b722  mov     qword ptr [rsp+3D0h+pExceptionObject+8], rdi
0x18006b727  mov     [rsp+3D0h+var_390], rsi
0x18006b72c  lea     rdx, [rsp+3D0h+pExceptionObject]
0x18006b731  mov     rcx, rax
0x18006b734  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x18006b739  lea     rdx, [rbp+2D0h+var_2F8]
0x18006b73d  mov     rcx, rax
0x18006b740  call    ?str@?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x18006b745  nop
0x18006b746  mov     rcx, rax
0x18006b749  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006b74e  mov     rdx, rax; char *
0x18006b751  lea     rcx, [rbp+2D0h+var_138]; this
0x18006b758  call    ??0InvalidDataException@ISRC@Microsoft@@QEAA@PEBD@Z; Microsoft::ISRC::InvalidDataException::InvalidDataException(char const *)
0x18006b75d  lea     rdx, _TI3?AVInvalidDataException@ISRC@Microsoft@@; pThrowInfo
0x18006b764  lea     rcx, [rbp+2D0h+var_138]; pExceptionObject
0x18006b76b  call    _CxxThrowException_0
0x18006b771  test    r15b, r15b
0x18006b774  jz      loc_18006B83E
0x18006b77a  cmp     [rbp+2D0h+var_F8], rsi
0x18006b781  jz      loc_18006B647
0x18006b787  lea     rcx, [rbp+2D0h+var_108]
0x18006b78e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006b793  cmp     byte ptr [rax], 23h ; '#'
0x18006b796  jz      loc_18006B647
0x18006b79c  mov     ecx, 0E8h; Size
0x18006b7a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b7a6  mov     [rbp+2D0h+var_268], rax
0x18006b7aa  mov     rcx, rax; this
0x18006b7ad  call    ??0Segment@ConstraintIndexBuilder@ISRC@Microsoft@@QEAA@XZ; Microsoft::ISRC::ConstraintIndexBuilder::Segment::Segment(void)
0x18006b7b2  mov     rbx, rax
0x18006b7b5  mov     [rsp+3D0h+var_358], rax
0x18006b7ba  mov     [rbp+2D0h+var_350], rsi
0x18006b7be  mov     rdx, rax; struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *
0x18006b7c1  lea     rcx, [rsp+3D0h+var_370]; this
0x18006b7c6  call    ??$?0USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@shared_count@detail@boost@@QEAA@PEAUSegment@ConstraintIndexBuilder@ISRC@Microsoft@@@Z; boost::detail::shared_count::shared_count(Microsoft::ISRC::ConstraintIndexBuilder::Segment *)
0x18006b7cb  mov     rdx, [rbp+2D0h+var_350]
0x18006b7cf  mov     rcx, [rax]
0x18006b7d2  mov     [rbp+2D0h+var_350], rcx
0x18006b7d6  mov     [rax], rdx
0x18006b7d9  lea     rcx, [rsp+3D0h+var_370]; this
0x18006b7de  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x18006b7e3  mov     r8, rbx
0x18006b7e6  mov     rdx, rbx
0x18006b7e9  lea     rcx, [rsp+3D0h+var_358]
0x18006b7ee  call    ?sp_enable_shared_from_this@detail@boost@@YAXZZ; boost::detail::sp_enable_shared_from_this(...)
0x18006b7f3  nop
0x18006b7f4  mov     rdx, [r14+28h]
0x18006b7f8  lea     r8, [rsp+3D0h+var_358]
0x18006b7fd  cmp     rdx, [r14+30h]
0x18006b801  jz      short loc_18006B80F
0x18006b803  call    ??$construct@V?$shared_ptr@U?$IIterator@VCSGResultWrapper@ISRC@Microsoft@@@ISRC@Microsoft@@@boost@@V12@@?$_Default_allocator_traits@V?$allocator@V?$shared_ptr@U?$IIterator@VCSGResultWrapper@ISRC@Microsoft@@@ISRC@Microsoft@@@boost@@@std@@@std@@SAXAEAV?$allocator@V?$shared_ptr@U?$IIterator@VCSGResultWrapper@ISRC@Microsoft@@@ISRC@Microsoft@@@boost@@@1@QEAV?$shared_ptr@U?$IIterator@VCSGResultWrapper@ISRC@Microsoft@@@ISRC@Microsoft@@@boost@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>>>::construct<boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>,boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>>(std::allocator<boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>>> &,boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>> * const,boost::shared_ptr<Microsoft::ISRC::IIterator<Microsoft::ISRC::CSGResultWrapper>> &&)
0x18006b808  add     qword ptr [r14+28h], 10h
0x18006b80d  jmp     short loc_18006B819
0x18006b80f  lea     rcx, [r14+20h]
  ... truncated ...
```
