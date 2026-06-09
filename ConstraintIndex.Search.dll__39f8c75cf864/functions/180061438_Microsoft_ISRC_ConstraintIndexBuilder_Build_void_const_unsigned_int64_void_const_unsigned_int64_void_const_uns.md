# Microsoft::ISRC::ConstraintIndexBuilder::Build(void const *,unsigned __int64,void const *,unsigned __int64,void const *,unsigned __int64,wchar_t const *,void * *,unsigned __int64 *,uint,std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x180061438`
- end: `0x180061cc5`
- name: `?Build@ConstraintIndexBuilder@ISRC@Microsoft@@SAXPEBX_K0101PEB_WPEAPEAXPEA_KIAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `2189`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x1800718b0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180005e50`
- `0x180006334`
- `0x180006e80`
- `0x180009e14`
- `0x180009e50`
- `0x180009fe4`
- `0x18000b190`
- `0x18000b2d4`
- `0x18000c840`
- `0x18000cb00`
- `0x18000cdb0`
- `0x18000f1e8`
- `0x180013750`
- `0x180014b44`
- `0x18001c3b8`
- `0x18002b3a4`
- `0x180052474`
- `0x180053274`
- `0x1800536cc`
- `0x180059098`
- `0x180059b58`
- `0x18005b1c4`
- `0x18005b36c`
- `0x18005c6a8`
- `0x18005d45c`
- `0x18005d5c4`
- `0x18005ec34`
- `0x18005fea0`
- `0x180061438`
- `0x180064b88`
- `0x180066014`
- `0x18006afb8`
- `0x18006b278`
- `0x18006b2d8`
- `0x18006c5e8`
- `0x18006c7dc`
- `0x18006db2c`
- `0x1800705d8`
- `0x1800713f8`
- `0x1800efc6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061bbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061bbf`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180061750`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180061750`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18006173d`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18006173d`

## string_xrefs

- `0x180061636`: `Reading data...`
- `0x180061524`: `Reading schema...`
- `0x180061a94`: `   Reading values...`
- `0x180061aff`: `   Reading forward index...`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Microsoft::ISRC::ConstraintIndexBuilder::Build(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        void **a8,
        SIZE_T *a9,
        float a10)
{
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // r9d
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  __int128 v36; // rdi
  __int64 v37; // rax
  const char *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  const char *v41; // rax
  int v42; // r8d
  const char *v43; // r9
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rax
  __int128 v47; // rdi
  __int64 v48; // rax
  const char *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  const char *v52; // rax
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **i; // rbx
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *v54; // rdi
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // r9
  Microsoft::ISRC::ConstraintIndexBuilder *v58; // rcx
  Microsoft::ISRC::ConstraintIndexBuilder *v59; // rcx
  SIZE_T *v60; // rbx
  HLOCAL v61; // rax
  void **v62; // rdi
  const void *v63; // rax
  const char *v64; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v65; // [rsp+28h] [rbp-D8h]
  char v66; // [rsp+38h] [rbp-C8h]
  void **v67; // [rsp+40h] [rbp-C0h] BYREF
  SIZE_T *v68; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v70[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h]
  __int64 v72; // [rsp+90h] [rbp-70h]
  __int64 v73; // [rsp+98h] [rbp-68h]
  _BYTE v74[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v75[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v76[272]; // [rsp+E0h] [rbp-20h] BYREF
  int v77; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v78[16]; // [rsp+1F8h] [rbp+F8h] BYREF
  SIZE_T v79; // [rsp+208h] [rbp+108h]
  __int128 v80; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int64 v81; // [rsp+230h] [rbp+130h]
  char v82[8]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v83; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int64 v84; // [rsp+258h] [rbp+158h]
  _BYTE v85[32]; // [rsp+270h] [rbp+170h] BYREF
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **v86; // [rsp+290h] [rbp+190h]
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **v87; // [rsp+298h] [rbp+198h]
  float v88[44]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v89[72]; // [rsp+358h] [rbp+258h] BYREF
  _BYTE v90[24]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v91[112]; // [rsp+3B8h] [rbp+2B8h] BYREF
  unsigned int v92; // [rsp+428h] [rbp+328h]
  _BYTE v93[24]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v94[112]; // [rsp+4B8h] [rbp+3B8h] BYREF
  unsigned int v95; // [rsp+528h] [rbp+428h]
  _BYTE v96[16]; // [rsp+5A0h] [rbp+4A0h] BYREF
  char v97[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v98[232]; // [rsp+5B8h] [rbp+4B8h] BYREF

  v67 = a8;
  v68 = a9;
  memset_0(v85, 0, 0x128u);
  Microsoft::ISRC::ConstraintIndexBuilder::ConstraintIndexBuilder((Microsoft::ISRC::ConstraintIndexBuilder *)v85);
  *(__int64 *)((char *)&std::cout + *(int *)(std::cout + 4) + 32) = 3;
  std::chrono::steady_clock::now(v82);
  *(_QWORD *)&v80 = &std::cout;
  *((_QWORD *)&v80 + 1) = v82;
  std::function_void___cdecl_char_const____::operator___lambda_05a53b556bfa95c89927fb00353746b7__0_(v89, &v80);
  v88[43] = a10;
  std::_Func_class<void,char const *>::operator()(v89, "Reading schema...");
  memset_0(v93, 0, 0xF8u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v93);
  v14 = std::string::string(v78, a1, a2);
  std::stringbuf::_Tidy(v94);
  v15 = std::_String_val<std::_Simple_types<char>>::_Myptr(v14);
  std::stringbuf::_Init(v94, v15, *(_QWORD *)(v14 + 16), v95);
  std::string::_Tidy_deallocate(v78);
  memset_0(v90, 0, 0xF8u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v90);
  v16 = std::string::string(v78, a5, a6);
  std::stringbuf::_Tidy(v91);
  v17 = std::_String_val<std::_Simple_types<char>>::_Myptr(v16);
  std::stringbuf::_Init(v91, v17, *(_QWORD *)(v16 + 16), v92);
  std::string::_Tidy_deallocate(v78);
  Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema((Microsoft::ISRC::ConstraintIndexBuilder *)v85);
  std::_Func_class<void,char const *>::operator()(v89, "Reading data...");
  v83 = 0;
  memset(v70, 0, sizeof(v70));
  v71 = 0;
  v72 = a3;
  v73 = a3 + a4;
  v77 = 0;
  while ( Microsoft::ISRC::MemoryMappedFileReader::ReadLine(
            (Microsoft::ISRC::MemoryMappedFileReader *)v70,
            (struct Microsoft::ISRC::RangeString *)&v83) )
  {
    v77 = v19 + 1;
    v20 = v83;
    if ( *((_QWORD *)&v83 + 1) != (_QWORD)v83 && *(_BYTE *)v83 != 35 )
    {
      LOBYTE(v18) = 9;
      v21 = std::_Find_vectorized<char const,char>(v83, *((_QWORD *)&v83 + 1), v18);
      v22 = v21;
      if ( v21 == v23 )
      {
        std::string::string(&v80, v20);
        v44 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                v76,
                "Invalid data - line %u: Line must be tab delimited record with segment, score, and ID preceeding attributes ( %s%s )",
                v42,
                v43,
                v64);
        v64 = (const char *)&v77;
        *(_QWORD *)&v65 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *((_QWORD *)&v65 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
        v45 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v44,
                &v64);
        v46 = std::string::substr(&v80, v75, 0, 64);
        v68 = (SIZE_T *)std::_String_val<std::_Simple_types<char>>::_Myptr(v46);
        v64 = (const char *)&v68;
        *(_QWORD *)&v47 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *(_QWORD *)&v65 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *((_QWORD *)&v47 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
        *((_QWORD *)&v65 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
        v48 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v45,
                &v64);
        v49 = "...";
        if ( v81 <= 0x40 )
          v49 = (const char *)&word_1801017B2;
        v67 = (void **)v49;
        v64 = (const char *)&v67;
        v65 = v47;
        v50 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v48,
                &v64);
        v51 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v50, v74);
        v52 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v51);
        Microsoft::ISRC::InvalidDataException::InvalidDataException(
          (Microsoft::ISRC::InvalidDataException *)pExceptionObject,
          v52);
        throw (Microsoft::ISRC::InvalidDataException *)pExceptionObject;
      }
      std::string::string(v78, v20, v21);
      v80 = 0;
      v24 = std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>>,0>>::_Try_emplace<std::string const &,>(
              v88,
              (__int64)pExceptionObject,
              (__int64)v78);
      v25 = *(_QWORD *)v24;
      v26 = *(_QWORD *)(*(_QWORD *)v24 + 48LL);
      *(_QWORD *)&v80 = v26;
      v27 = *(_QWORD *)(v25 + 56);
      *((_QWORD *)&v80 + 1) = v27;
      if ( v27 )
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
      if ( v26 )
      {
        if ( (unsigned int)_o_strtoul(v22 + 1, 0, 0) - 1 > 0xF9FF )
        {
          std::string::string(&v83, v20);
          v32 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                  v76,
                  "Invalid data - line %u: Score in second column must be an integer greater than 0 and no more than %u ( %s%s )",
                  v30,
                  v31,
                  v64,
                  (const char *)v65);
          v64 = (const char *)&v77;
          *(_QWORD *)&v65 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v65 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
          v33 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v32,
                  &v64);
          v64 = (const char *)&Microsoft::ISRC::ConstraintIndexBuilderConstants::s_MaxScore;
          *(_QWORD *)&v65 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v65 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
          v34 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v33,
                  &v64);
          v35 = std::string::substr(&v83, v74, 0, 64);
          v67 = (void **)std::_String_val<std::_Simple_types<char>>::_Myptr(v35);
          v64 = (const char *)&v67;
          *(_QWORD *)&v36 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *(_QWORD *)&v65 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v36 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          *((_QWORD *)&v65 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v37 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v34,
                  &v64);
          v38 = "...";
          if ( v84 <= 0x40 )
            v38 = (const char *)&word_1801017B2;
          v68 = (SIZE_T *)v38;
          v64 = (const char *)&v68;
          v65 = v36;
          v39 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v37,
                  &v64);
          v40 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v39, v75);
          v41 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v40);
          Microsoft::ISRC::InvalidDataException::InvalidDataException(
            (Microsoft::ISRC::InvalidDataException *)pExceptionObject,
            v41);
          throw (Microsoft::ISRC::InvalidDataException *)pExceptionObject;
        }
        LODWORD(v64) = atol((const char *)(v22 + 1));
        v65 = v83;
        v28 = *(_QWORD *)(v26 + 128);
        v29 = v26 + 120;
        if ( v28 == *(_QWORD *)(v26 + 136) )
          std::vector<std::pair<unsigned int,Microsoft::ISRC::RangeString>>::_Emplace_reallocate<std::pair<unsigned int,Microsoft::ISRC::RangeString>>(
            v29,
            v28,
            &v64);
        else
          std::vector<std::pair<Microsoft::ISRC::NumericPoint2D,unsigned int>>::_Emplace_back_with_unused_capacity<std::pair<Microsoft::ISRC::NumericPoint2D,unsigned int>>(
            v29,
            &v64);
      }
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v80 + 8));
      std::string::_Tidy_deallocate(v78);
    }
  }
  for ( i = v86; i != v87; i += 2 )
  {
    v54 = *i;
    v55 = std::operator+<char>(v78, "Segment: ", *i);
    v56 = std::_String_val<std::_Simple_types<char>>::_Myptr(v55);
    std::_Func_class<void,char const *>::operator()(v89, v56);
    std::string::_Tidy_deallocate(v78);
    LOBYTE(v57) = v66;
    std::_Sort_unchecked_std::pair_unsigned_int_Microsoft::ISRC::RangeString_____lambda_bd763e29cea7a6255e36bc3a62563b8a___(
      *((_QWORD *)v54 + 15),
      *((_QWORD *)v54 + 16),
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v54 + 16) - *((_QWORD *)v54 + 15)) >> 3),
      v57);
    std::_Func_class<void,char const *>::operator()(v89, "   Reading values...");
    Microsoft::ISRC::ConstraintIndexBuilder::ReadValues(v58, v54);
    std::_Func_class<void,char const *>::operator()(v89, "   Building inverted index...");
    *(_QWORD *)&v80 = v85;
    *((_QWORD *)&v80 + 1) = &std::cout;
    std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_boost::shared_ptr_Microsoft::ISRC::AttributeBuilder_________lambda_ffccdf0cc2192abc562c3c504fcceac1___(
      pExceptionObject,
      *((_QWORD *)v54 + 4),
      *((_QWORD *)v54 + 5),
      &v80,
      (_DWORD)v64,
      v65,
      *((_QWORD *)&v65 + 1));
    Microsoft::ISRC::ConstraintIndexBuilder::Segment::RemoveEmptyAttributes(v54);
    std::_Func_class<void,char const *>::operator()(v89, "   Reading forward index...");
    Microsoft::ISRC::ConstraintIndexBuilder::ReadForwardIndex(v59, v54);
    std::_Func_class<void,char const *>::operator()(v89, "   Materializing intersections...");
    Microsoft::ISRC::ConstraintIndexBuilder::BuildIntersections((Microsoft::ISRC::ConstraintIndexBuilder *)v85, v54);
  }
  std::_Func_class<void,char const *>::operator()(v89, "Writing index...");
  memset_0(v96, 0, 0xF8u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v96);
  Microsoft::ISRC::ConstraintIndexBuilder::WriteIndex(v85, v97);
  std::stringbuf::str(v98, v78);
  v60 = v68;
  *v68 = v79;
  std::string::_Tidy_deallocate(v78);
  v61 = LocalAlloc(0, *v60);
  v62 = v67;
  *v67 = v61;
  if ( !v61 )
  {
    *((_QWORD *)&v65 + 1) = 0;
    *(_QWORD *)&v65 = "bad allocation";
    v64 = (const char *)&std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&v64;
  }
  std::stringbuf::str(v98, v78);
  v63 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(v78);
  memcpy_0(*v62, v63, *v60);
  std::string::_Tidy_deallocate(v78);
  std::_Func_class<void,char const *>::operator()(v89, "Done.");
  Microsoft::ISRC::ConstraintIndexBuilder::DumpStats(v85);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v96);
  Microsoft::ISRC::MemoryMap::~MemoryMap((Microsoft::ISRC::MemoryMap *)v70);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v90);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v93);
  Microsoft::ISRC::ConstraintIndexBuilder::~ConstraintIndexBuilder((Microsoft::ISRC::ConstraintIndexBuilder *)v85);
}

```

## disassembly

```asm
0x180061438  mov     [rsp-8+arg_10], rbx
0x18006143d  push    rbp
0x18006143e  push    rsi
0x18006143f  push    rdi
0x180061440  push    r12
0x180061442  push    r13
0x180061444  push    r14
0x180061446  push    r15
0x180061448  lea     rbp, [rsp-5B0h]
0x180061450  sub     rsp, 6B0h
0x180061457  mov     rax, cs:__security_cookie
0x18006145e  xor     rax, rsp
0x180061461  mov     [rbp+5E0h+var_40], rax
0x180061468  mov     r13, r9
0x18006146b  mov     r12, r8
0x18006146e  mov     rdi, rdx
0x180061471  mov     rbx, rcx
0x180061474  mov     r14, [rbp+5E0h+arg_20]
0x18006147b  mov     rsi, [rbp+5E0h+arg_28]
0x180061482  mov     r15, [rbp+5E0h+arg_30]
0x180061489  mov     rax, [rbp+5E0h+arg_38]
0x180061490  mov     [rsp+6E0h+var_6A0], rax
0x180061495  mov     rax, [rbp+5E0h+arg_40]
0x18006149c  mov     [rsp+6E0h+var_698], rax
0x1800614a1  xor     edx, edx; Val
0x1800614a3  mov     r8d, 128h; Size
0x1800614a9  lea     rcx, [rbp+5E0h+var_470]; void *
0x1800614b0  call    memset_0
0x1800614b5  lea     rcx, [rbp+5E0h+var_470]; this
0x1800614bc  call    ??0ConstraintIndexBuilder@ISRC@Microsoft@@AEAA@XZ; Microsoft::ISRC::ConstraintIndexBuilder::ConstraintIndexBuilder(void)
0x1800614c1  nop
0x1800614c2  mov     rax, cs:?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x1800614c9  movsxd  rcx, dword ptr [rax+4]
0x1800614cd  lea     rax, ?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x1800614d4  mov     qword ptr [rcx+rax+20h], 3
0x1800614dd  lea     rcx, [rbp+5E0h+var_4A0]
0x1800614e4  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800614e9  lea     rax, ?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x1800614f0  mov     qword ptr [rbp+5E0h+var_4C0], rax
0x1800614f7  lea     rax, [rbp+5E0h+var_4A0]
0x1800614fe  mov     qword ptr [rbp+5E0h+var_4C0+8], rax
0x180061505  lea     rdx, [rbp+5E0h+var_4C0]
0x18006150c  lea     rcx, [rbp+5E0h+var_388]
0x180061513  call    std__function_void___cdecl_char_const______operator___lambda_05a53b556bfa95c89927fb00353746b7__0_
0x180061518  mov     eax, [rbp+5E0h+arg_48]
0x18006151e  mov     [rbp+5E0h+var_38C], eax
0x180061524  lea     rdx, aReadingSchema; "Reading schema..."
0x18006152b  lea     rcx, [rbp+5E0h+var_388]
0x180061532  call    ??R?$_Func_class@XPEBD@std@@QEBAXPEBD@Z; std::_Func_class<void,char const *>::operator()(char const *)
0x180061537  xor     edx, edx; Val
0x180061539  mov     r8d, 0F8h; Size
0x18006153f  lea     rcx, [rbp+5E0h+var_240]; void *
0x180061546  call    memset_0
0x18006154b  lea     rcx, [rbp+5E0h+var_240]
0x180061552  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180061557  nop
0x180061558  mov     r8, rdi
0x18006155b  mov     rdx, rbx
0x18006155e  lea     rcx, [rbp+5E0h+var_4E8]
0x180061565  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD_K@Z; std::string::string(char const * const,unsigned __int64)
0x18006156a  mov     rbx, rax
0x18006156d  lea     rcx, [rbp+5E0h+var_228]
0x180061574  call    ?_Tidy@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXXZ; std::stringbuf::_Tidy(void)
0x180061579  mov     rcx, rbx
0x18006157c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180061581  mov     rdx, rax
0x180061584  mov     r9d, [rbp+5E0h+var_1B8]
0x18006158b  mov     r8, [rbx+10h]
0x18006158f  lea     rcx, [rbp+5E0h+var_228]
0x180061596  call    ?_Init@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXPEBD_KH@Z; std::stringbuf::_Init(char const *,unsigned __int64,int)
0x18006159b  nop
0x18006159c  lea     rcx, [rbp+5E0h+var_4E8]
0x1800615a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800615a8  xor     edx, edx; Val
0x1800615aa  mov     r8d, 0F8h; Size
0x1800615b0  lea     rcx, [rbp+5E0h+var_340]; void *
0x1800615b7  call    memset_0
0x1800615bc  lea     rcx, [rbp+5E0h+var_340]
0x1800615c3  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800615c8  nop
0x1800615c9  mov     r8, rsi
0x1800615cc  mov     rdx, r14
0x1800615cf  lea     rcx, [rbp+5E0h+var_4E8]
0x1800615d6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD_K@Z; std::string::string(char const * const,unsigned __int64)
0x1800615db  mov     rbx, rax
0x1800615de  lea     rcx, [rbp+5E0h+var_328]
0x1800615e5  call    ?_Tidy@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXXZ; std::stringbuf::_Tidy(void)
0x1800615ea  mov     rcx, rbx
0x1800615ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800615f2  mov     rdx, rax
0x1800615f5  mov     r9d, [rbp+5E0h+var_2B8]
0x1800615fc  mov     r8, [rbx+10h]
0x180061600  lea     rcx, [rbp+5E0h+var_328]
0x180061607  call    ?_Init@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXPEBD_KH@Z; std::stringbuf::_Init(char const *,unsigned __int64,int)
0x18006160c  nop
0x18006160d  lea     rcx, [rbp+5E0h+var_4E8]
0x180061614  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180061619  lea     r9, [rbp+5E0h+var_340]
0x180061620  mov     r8, r15
0x180061623  lea     rdx, [rbp+5E0h+var_240]
0x18006162a  lea     rcx, [rbp+5E0h+var_470]; this
0x180061631  call    ?ReadSchema@ConstraintIndexBuilder@ISRC@Microsoft@@AEAAXAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@PEB_W0@Z; Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema(std::istream &,wchar_t const *,std::istream &)
0x180061636  lea     rdx, aReadingData; "Reading data..."
0x18006163d  lea     rcx, [rbp+5E0h+var_388]
0x180061644  call    ??R?$_Func_class@XPEBD@std@@QEBAXPEBD@Z; std::_Func_class<void,char const *>::operator()(char const *)
0x180061649  xorps   xmm0, xmm0
0x18006164c  movdqu  [rbp+5E0h+var_498], xmm0
0x180061654  xorps   xmm1, xmm1
0x180061657  xor     eax, eax
0x180061659  movups  [rsp+6E0h+var_668], xmm1
0x18006165e  movups  [rbp+5E0h+var_658], xmm1
0x180061662  movdqu  [rsp+6E0h+var_678], xmm0
0x180061668  mov     qword ptr [rsp+6E0h+var_668], rax
0x18006166d  mov     dword ptr [rbp+5E0h+var_658], eax
0x180061670  mov     qword ptr [rbp+5E0h+var_658+8], r12
0x180061674  lea     rax, [r12+r13]
0x180061678  mov     [rbp+5E0h+var_648], rax
0x18006167c  xor     r9d, r9d
0x18006167f  mov     [rbp+5E0h+var_4F0], r9d
0x180061686  lea     rdx, [rbp+5E0h+var_498]; struct Microsoft::ISRC::RangeString *
0x18006168d  lea     rcx, [rsp+6E0h+var_678]; this
0x180061692  call    ?ReadLine@MemoryMappedFileReader@ISRC@Microsoft@@QEAA_NAEAURangeString@23@@Z; Microsoft::ISRC::MemoryMappedFileReader::ReadLine(Microsoft::ISRC::RangeString &)
0x180061697  test    al, al
0x180061699  jz      loc_180061A15
0x18006169f  inc     r9d
0x1800616a2  mov     [rbp+5E0h+var_4F0], r9d
0x1800616a9  mov     rdx, qword ptr [rbp+5E0h+var_498+8]
0x1800616b0  mov     rbx, qword ptr [rbp+5E0h+var_498]
0x1800616b7  cmp     rdx, rbx
0x1800616ba  jz      short loc_180061686
0x1800616bc  cmp     byte ptr [rbx], 23h ; '#'
0x1800616bf  jz      short loc_180061686
0x1800616c1  mov     r8b, 9
0x1800616c4  mov     rcx, rbx
0x1800616c7  call    ??$_Find_vectorized@$$CBDD@std@@YAPEBDQEBD0D@Z; std::_Find_vectorized<char const,char>(char const * const,char const * const,char)
0x1800616cc  mov     rdi, rax
0x1800616cf  cmp     rax, rdx
0x1800616d2  mov     rdx, rbx
0x1800616d5  jz      loc_1800618F9
0x1800616db  mov     r8, rax
0x1800616de  lea     rcx, [rbp+5E0h+var_4E8]
0x1800616e5  call    ??$?0PEBD$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD0AEBV?$allocator@D@1@@Z; std::string::string(char const *,char const *,std::allocator<char> const &)
0x1800616ea  nop
0x1800616eb  xorps   xmm0, xmm0
0x1800616ee  movups  [rbp+5E0h+var_4C0], xmm0
0x1800616f5  lea     r8, [rbp+5E0h+var_4E8]
0x1800616fc  lea     rdx, [rsp+6E0h+pExceptionObject]
0x180061701  lea     rcx, [rbp+5E0h+var_438]
0x180061708  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>>,0>>::_Try_emplace<std::string const &,>(std::string const &)
0x18006170d  mov     rcx, [rax]
0x180061710  mov     rsi, [rcx+30h]
0x180061714  mov     qword ptr [rbp+5E0h+var_4C0], rsi
0x18006171b  mov     rax, [rcx+38h]
0x18006171f  mov     qword ptr [rbp+5E0h+var_4C0+8], rax
0x180061726  test    rax, rax
0x180061729  jz      short loc_18006172F
0x18006172b  lock inc dword ptr [rax+8]
0x18006172f  test    rsi, rsi
0x180061732  jz      short loc_180061792
0x180061734  xor     r8d, r8d
0x180061737  xor     edx, edx
0x180061739  lea     rcx, [rdi+1]
0x18006173d  call    cs:__imp__o_strtoul
0x180061743  dec     eax
0x180061745  cmp     eax, 0F9FFh
0x18006174a  ja      short loc_1800617B7
0x18006174c  lea     rcx, [rdi+1]; String
0x180061750  call    cs:__imp_atol
0x180061756  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x18006175a  movups  xmm0, [rbp+5E0h+var_498]
0x180061761  movdqu  [rsp+6E0h+var_6B8], xmm0
0x180061767  mov     rdx, [rsi+80h]
0x18006176e  lea     rcx, [rsi+78h]
0x180061772  cmp     rdx, [rsi+88h]
0x180061779  jz      short loc_180061787
0x18006177b  lea     rdx, [rsp+6E0h+var_6C0]
0x180061780  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@@?$vector@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@V?$allocator@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@@2@@std@@AEAAAEAU?$pair@UNumericPoint2D@ISRC@Microsoft@@I@1@$$QEAU21@@Z; std::vector<std::pair<Microsoft::ISRC::NumericPoint2D,uint>>::_Emplace_back_with_unused_capacity<std::pair<Microsoft::ISRC::NumericPoint2D,uint>>(std::pair<Microsoft::ISRC::NumericPoint2D,uint> &&)
0x180061785  jmp     short loc_180061792
0x180061787  lea     r8, [rsp+6E0h+var_6C0]
0x18006178c  call    ??$_Emplace_reallocate@U?$pair@IURangeString@ISRC@Microsoft@@@std@@@?$vector@U?$pair@IURangeString@ISRC@Microsoft@@@std@@V?$allocator@U?$pair@IURangeString@ISRC@Microsoft@@@std@@@2@@std@@AEAAPEAU?$pair@IURangeString@ISRC@Microsoft@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<uint,Microsoft::ISRC::RangeString>>::_Emplace_reallocate<std::pair<uint,Microsoft::ISRC::RangeString>>(std::pair<uint,Microsoft::ISRC::RangeString> * const,std::pair<uint,Microsoft::ISRC::RangeString> &&)
0x180061791  nop
0x180061792  lea     rcx, [rbp+5E0h+var_4C0+8]; this
0x180061799  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x18006179e  nop
0x18006179f  lea     rcx, [rbp+5E0h+var_4E8]
0x1800617a6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800617ab  mov     r9d, [rbp+5E0h+var_4F0]
0x1800617b2  jmp     loc_180061686
0x1800617b7  mov     rdx, rbx
0x1800617ba  lea     rcx, [rbp+5E0h+var_498]
0x1800617c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800617c6  nop
0x1800617c7  lea     rdx, aInvalidDataLin; "Invalid data - line %u: Score in second"...
0x1800617ce  lea     rcx, [rbp+5E0h+var_600]
0x1800617d2  call    ??0?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEAA@PEBD@Z; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(char const *)
0x1800617d7  nop
0x1800617d8  lea     rcx, [rbp+5E0h+var_4F0]
0x1800617df  mov     [rsp+6E0h+var_6C0], rcx
0x1800617e4  lea     rbx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800617eb  mov     qword ptr [rsp+6E0h+var_6B8], rbx
0x1800617f0  lea     rdi, ??$call_put_last@DU?$char_traits@D@std@@$$CBI@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,uint const>(std::ostream &,void const *)
0x1800617f7  mov     qword ptr [rsp+6E0h+var_6B8+8], rdi
0x1800617fc  lea     rdx, [rsp+6E0h+var_6C0]
0x180061801  mov     rcx, rax
0x180061804  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180061809  lea     rcx, ?s_MaxScore@ConstraintIndexBuilderConstants@ISRC@Microsoft@@2IB; uint const Microsoft::ISRC::ConstraintIndexBuilderConstants::s_MaxScore
0x180061810  mov     [rsp+6E0h+var_6C0], rcx
0x180061815  mov     qword ptr [rsp+6E0h+var_6B8], rbx
0x18006181a  mov     qword ptr [rsp+6E0h+var_6B8+8], rdi
0x18006181f  lea     rdx, [rsp+6E0h+var_6C0]
0x180061824  mov     rcx, rax
0x180061827  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x18006182c  mov     rbx, rax
0x18006182f  mov     r9d, 40h ; '@'
0x180061835  xor     r8d, r8d
0x180061838  lea     rdx, [rbp+5E0h+var_640]
0x18006183c  lea     rcx, [rbp+5E0h+var_498]
0x180061843  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x180061848  nop
0x180061849  mov     rcx, rax
0x18006184c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180061851  mov     [rsp+6E0h+var_6A0], rax
0x180061856  lea     rax, [rsp+6E0h+var_6A0]
0x18006185b  mov     [rsp+6E0h+var_6C0], rax
0x180061860  lea     rdi, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180061867  mov     qword ptr [rsp+6E0h+var_6B8], rdi
0x18006186c  lea     rsi, ??$call_put_last@DU?$char_traits@D@std@@QEBD@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>(std::ostream &,void const *)
0x180061873  mov     qword ptr [rsp+6E0h+var_6B8+8], rsi
0x180061878  lea     rdx, [rsp+6E0h+var_6C0]
0x18006187d  mov     rcx, rbx
0x180061880  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180061885  lea     rcx, asc_180103728; "..."
0x18006188c  lea     rdx, word_1801017B2
0x180061893  cmp     [rbp+5E0h+var_488], 40h ; '@'
0x18006189b  cmovbe  rcx, rdx
0x18006189f  mov     [rsp+6E0h+var_698], rcx
0x1800618a4  lea     rcx, [rsp+6E0h+var_698]
0x1800618a9  mov     [rsp+6E0h+var_6C0], rcx
0x1800618ae  mov     qword ptr [rsp+6E0h+var_6B8], rdi
0x1800618b3  mov     qword ptr [rsp+6E0h+var_6B8+8], rsi
0x1800618b8  lea     rdx, [rsp+6E0h+var_6C0]
0x1800618bd  mov     rcx, rax
0x1800618c0  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x1800618c5  lea     rdx, [rbp+5E0h+var_620]
0x1800618c9  mov     rcx, rax
0x1800618cc  call    ?str@?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x1800618d1  nop
0x1800618d2  mov     rcx, rax
0x1800618d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800618da  mov     rdx, rax; char *
0x1800618dd  lea     rcx, [rsp+6E0h+pExceptionObject]; this
0x1800618e2  call    ??0InvalidDataException@ISRC@Microsoft@@QEAA@PEBD@Z; Microsoft::ISRC::InvalidDataException::InvalidDataException(char const *)
0x1800618e7  lea     rdx, _TI3?AVInvalidDataException@ISRC@Microsoft@@; pThrowInfo
0x1800618ee  lea     rcx, [rsp+6E0h+pExceptionObject]; pExceptionObject
0x1800618f3  call    _CxxThrowException_0
0x1800618f9  lea     rcx, [rbp+5E0h+var_4C0]
0x180061900  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180061905  nop
0x180061906  lea     rdx, aInvalidDataLin_0; "Invalid data - line %u: Line must be ta"...
0x18006190d  lea     rcx, [rbp+5E0h+var_600]
0x180061911  call    ??0?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEAA@PEBD@Z; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(char const *)
0x180061916  nop
0x180061917  lea     rcx, [rbp+5E0h+var_4F0]
0x18006191e  mov     [rsp+6E0h+var_6C0], rcx
0x180061923  lea     rbx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18006192a  mov     qword ptr [rsp+6E0h+var_6B8], rbx
0x18006192f  lea     rdi, ??$call_put_last@DU?$char_traits@D@std@@$$CBI@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,uint const>(std::ostream &,void const *)
0x180061936  mov     qword ptr [rsp+6E0h+var_6B8+8], rdi
0x18006193b  lea     rdx, [rsp+6E0h+var_6C0]
0x180061940  mov     rcx, rax
0x180061943  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180061948  mov     rbx, rax
0x18006194b  mov     r9d, 40h ; '@'
0x180061951  xor     r8d, r8d
0x180061954  lea     rdx, [rbp+5E0h+var_620]
0x180061958  lea     rcx, [rbp+5E0h+var_4C0]
0x18006195f  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x180061964  nop
0x180061965  mov     rcx, rax
0x180061968  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006196d  mov     [rsp+6E0h+var_698], rax
0x180061972  lea     rax, [rsp+6E0h+var_698]
0x180061977  mov     [rsp+6E0h+var_6C0], rax
0x18006197c  lea     rdi, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180061983  mov     qword ptr [rsp+6E0h+var_6B8], rdi
0x180061988  lea     rsi, ??$call_put_last@DU?$char_traits@D@std@@QEBD@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>(std::ostream &,void const *)
0x18006198f  mov     qword ptr [rsp+6E0h+var_6B8+8], rsi
0x180061994  lea     rdx, [rsp+6E0h+var_6C0]
0x180061999  mov     rcx, rbx
0x18006199c  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x1800619a1  lea     rcx, asc_180103728; "..."
0x1800619a8  lea     rdx, word_1801017B2
0x1800619af  cmp     [rbp+5E0h+var_4B0], 40h ; '@'
0x1800619b7  cmovbe  rcx, rdx
0x1800619bb  mov     [rsp+6E0h+var_6A0], rcx
0x1800619c0  lea     rcx, [rsp+6E0h+var_6A0]
0x1800619c5  mov     [rsp+6E0h+var_6C0], rcx
0x1800619ca  mov     qword ptr [rsp+6E0h+var_6B8], rdi
0x1800619cf  mov     qword ptr [rsp+6E0h+var_6B8+8], rsi
0x1800619d4  lea     rdx, [rsp+6E0h+var_6C0]
  ... truncated ...
```
