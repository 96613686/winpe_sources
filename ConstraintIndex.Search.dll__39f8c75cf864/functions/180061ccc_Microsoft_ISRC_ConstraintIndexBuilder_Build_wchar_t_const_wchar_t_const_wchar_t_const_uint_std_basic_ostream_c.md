# Microsoft::ISRC::ConstraintIndexBuilder::Build(wchar_t const *,wchar_t const *,wchar_t const *,uint,std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x180061ccc`
- end: `0x1800623b3`
- name: `?Build@ConstraintIndexBuilder@ISRC@Microsoft@@SAXPEB_W00IAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `1767`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180005e50`
- `0x180006334`
- `0x180006e80`
- `0x180009b5c`
- `0x180009e14`
- `0x18000b190`
- `0x18000b264`
- `0x18000c840`
- `0x18000cdb0`
- `0x18000f1e8`
- `0x18001ae50`
- `0x18001c3b8`
- `0x18001cb54`
- `0x18002b3a4`
- `0x180052518`
- `0x180053274`
- `0x1800536cc`
- `0x180059098`
- `0x180059b58`
- `0x18005b1c4`
- `0x18005b288`
- `0x18005c6a8`
- `0x18005d45c`
- `0x18005d5c4`
- `0x18005d5ec`
- `0x18005ec34`
- `0x18005fea0`
- `0x180061ccc`
- `0x180064b88`
- `0x180066014`
- `0x18006afb8`
- `0x18006b278`
- `0x18006c3c4`
- `0x18006c5e8`
- `0x18006c7dc`
- `0x18006cec0`
- `0x18006db2c`
- `0x1800705d8`
- `0x1800713f8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180061dcb`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180061dcb`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180061dda`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180061dda`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180061f11`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180061f11`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180061efe`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180061efe`

## string_xrefs

- `0x180061dfa`: `Reading data...`
- `0x180061d71`: `Reading schema...`
- `0x18006224d`: `   Reading values...`
- `0x1800622ab`: `   Reading forward index...`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Microsoft::ISRC::ConstraintIndexBuilder::Build(wchar_t *a1, wchar_t *a2, __int64 a3, int a4)
{
  unsigned __int64 v8; // rdx
  bool v9; // r8
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int128 v28; // rdi
  __int64 v29; // rax
  const char *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  const char *v33; // rax
  int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int128 v39; // rdi
  __int64 v40; // rax
  const char *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  const char *v44; // rax
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **i; // rbx
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment *v46; // rdi
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // r9
  Microsoft::ISRC::ConstraintIndexBuilder *v50; // rcx
  Microsoft::ISRC::ConstraintIndexBuilder *v51; // rcx
  const char *v52; // [rsp+20h] [rbp-E0h]
  const char *v53; // [rsp+28h] [rbp-D8h]
  const unsigned int *v54; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v55; // [rsp+38h] [rbp-C8h]
  char v56; // [rsp+48h] [rbp-B8h]
  __int128 v57; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v58; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v59[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v61[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v62[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v63[272]; // [rsp+E0h] [rbp-20h] BYREF
  int v64; // [rsp+1F0h] [rbp+F0h] BYREF
  char v65[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v66[16]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v67; // [rsp+210h] [rbp+110h]
  _OWORD v68[3]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v69; // [rsp+250h] [rbp+150h]
  _BYTE v70[40]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v71[32]; // [rsp+280h] [rbp+180h] BYREF
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **v72; // [rsp+2A0h] [rbp+1A0h]
  struct Microsoft::ISRC::ConstraintIndexBuilder::Segment **v73; // [rsp+2A8h] [rbp+1A8h]
  float v74[44]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v75[72]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v76[272]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v77[272]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR pszPath[264]; // [rsp+5D0h] [rbp+4D0h] BYREF

  memset_0(v71, 0, 0x128u);
  Microsoft::ISRC::ConstraintIndexBuilder::ConstraintIndexBuilder((Microsoft::ISRC::ConstraintIndexBuilder *)v71);
  *(__int64 *)((char *)&std::cout + *(int *)(std::cout + 4) + 32) = 3;
  std::chrono::steady_clock::now(v65);
  *(_QWORD *)&v58 = &std::cout;
  *((_QWORD *)&v58 + 1) = v65;
  std::function_void___cdecl_char_const____::operator___lambda_95c28cb69a85e8d8c9862769ba9d5242__0_(v75, &v58);
  LODWORD(v74[43]) = a4;
  std::_Func_class<void,char const *>::operator()(v75, "Reading schema...");
  memset_0(v77, 0, sizeof(v77));
  std::ifstream::ifstream(v77, a1, 1);
  StringCchCopyW(pszPath, v8, a1);
  PathCchRemoveFileSpec(pszPath, 0x104u);
  PathCchAddBackslash(pszPath, 0x104u);
  Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema((Microsoft::ISRC::ConstraintIndexBuilder *)v71);
  std::_Func_class<void,char const *>::operator()(v75, "Reading data...");
  v57 = 0;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  Microsoft::ISRC::MemoryMappedFileReader::MemoryMappedFileReader(
    (Microsoft::ISRC::MemoryMappedFileReader *)v68,
    a2,
    v9);
  v64 = 0;
  while ( Microsoft::ISRC::MemoryMappedFileReader::ReadLine(
            (Microsoft::ISRC::MemoryMappedFileReader *)v68,
            (struct Microsoft::ISRC::RangeString *)&v57) )
  {
    v64 = v11 + 1;
    v12 = v57;
    if ( *((_QWORD *)&v57 + 1) != (_QWORD)v57 && *(_BYTE *)v57 != 35 )
    {
      LOBYTE(v10) = 9;
      v13 = std::_Find_vectorized<char const,char>(v57, *((_QWORD *)&v57 + 1), v10);
      v14 = v13;
      if ( v13 == v15 )
      {
        std::string::string(v66, v12);
        v36 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                v63,
                "Invalid data - line %u: Line must be tab delimited record with segment, score, and ID preceeding attributes ( %s%s )",
                v34,
                v35,
                v52);
        v54 = (const unsigned int *)&v64;
        *(_QWORD *)&v55 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *((_QWORD *)&v55 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
        v37 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v36,
                &v54);
        v38 = std::string::substr(v66, v62, 0, 64);
        *(_QWORD *)&v57 = std::_String_val<std::_Simple_types<char>>::_Myptr(v38);
        v54 = (const unsigned int *)&v57;
        *(_QWORD *)&v39 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *(_QWORD *)&v55 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
        *((_QWORD *)&v39 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
        *((_QWORD *)&v55 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
        v40 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v37,
                &v54);
        v41 = "...";
        if ( v67 <= 0x40 )
          v41 = (const char *)&word_1801017B2;
        v59[0] = v41;
        v54 = (const unsigned int *)v59;
        v55 = v39;
        v42 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                v40,
                &v54);
        v43 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v42, v61);
        v44 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v43);
        Microsoft::ISRC::InvalidDataException::InvalidDataException(
          (Microsoft::ISRC::InvalidDataException *)pExceptionObject,
          v44);
        throw (Microsoft::ISRC::InvalidDataException *)pExceptionObject;
      }
      std::string::string(v70, v12, v13);
      v58 = 0;
      v16 = std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>>,0>>::_Try_emplace<std::string const &,>(
              v74,
              (__int64)v59,
              (__int64)v70);
      v17 = *(_QWORD *)v16;
      v18 = *(_QWORD *)(*(_QWORD *)v16 + 48LL);
      *(_QWORD *)&v58 = v18;
      v19 = *(_QWORD *)(v17 + 56);
      *((_QWORD *)&v58 + 1) = v19;
      if ( v19 )
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
      if ( v18 )
      {
        if ( (unsigned int)_o_strtoul(v14 + 1, 0, 0) - 1 > 0xF9FF )
        {
          std::string::string(v66, v12);
          v24 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(
                  v63,
                  "Invalid data - line %u: Score in second column must be an integer greater than 0 and no more than %u ( %s%s )",
                  v22,
                  v23,
                  v52,
                  v53);
          v54 = (const unsigned int *)&v64;
          *(_QWORD *)&v55 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v55 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
          v25 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v24,
                  &v54);
          v54 = &Microsoft::ISRC::ConstraintIndexBuilderConstants::s_MaxScore;
          *(_QWORD *)&v55 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v55 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,unsigned int const>;
          v26 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v25,
                  &v54);
          v27 = std::string::substr(v66, v61, 0, 64);
          v59[0] = std::_String_val<std::_Simple_types<char>>::_Myptr(v27);
          v54 = (const unsigned int *)v59;
          *(_QWORD *)&v28 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *(_QWORD *)&v55 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
          *((_QWORD *)&v28 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          *((_QWORD *)&v55 + 1) = boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>;
          v29 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v26,
                  &v54);
          v30 = "...";
          if ( v67 <= 0x40 )
            v30 = (const char *)&word_1801017B2;
          *(_QWORD *)&v57 = v30;
          v54 = (const unsigned int *)&v57;
          v55 = v28;
          v31 = boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(
                  v29,
                  &v54);
          v32 = boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(v31, v62);
          v33 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v32);
          Microsoft::ISRC::InvalidDataException::InvalidDataException(
            (Microsoft::ISRC::InvalidDataException *)pExceptionObject,
            v33);
          throw (Microsoft::ISRC::InvalidDataException *)pExceptionObject;
        }
        LODWORD(v54) = atol((const char *)(v14 + 1));
        v55 = v57;
        v20 = *(_QWORD *)(v18 + 128);
        v21 = v18 + 120;
        if ( v20 == *(_QWORD *)(v18 + 136) )
          std::vector<std::pair<unsigned int,Microsoft::ISRC::RangeString>>::_Emplace_reallocate<std::pair<unsigned int,Microsoft::ISRC::RangeString>>(
            v21,
            v20,
            &v54);
        else
          std::vector<std::pair<Microsoft::ISRC::NumericPoint2D,unsigned int>>::_Emplace_back_with_unused_capacity<std::pair<Microsoft::ISRC::NumericPoint2D,unsigned int>>(
            v21,
            &v54);
      }
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v58 + 8));
      std::string::_Tidy_deallocate(v70);
    }
  }
  for ( i = v72; i != v73; i += 2 )
  {
    v46 = *i;
    v47 = std::operator+<char>(v66, "Segment: ", *i);
    v48 = std::_String_val<std::_Simple_types<char>>::_Myptr(v47);
    std::_Func_class<void,char const *>::operator()(v75, v48);
    std::string::_Tidy_deallocate(v66);
    LOBYTE(v49) = v56;
    std::_Sort_unchecked_std::pair_unsigned_int_Microsoft::ISRC::RangeString_____lambda_bd763e29cea7a6255e36bc3a62563b8a___(
      *((_QWORD *)v46 + 15),
      *((_QWORD *)v46 + 16),
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v46 + 16) - *((_QWORD *)v46 + 15)) >> 3),
      v49);
    std::_Func_class<void,char const *>::operator()(v75, "   Reading values...");
    Microsoft::ISRC::ConstraintIndexBuilder::ReadValues(v50, v46);
    std::_Func_class<void,char const *>::operator()(v75, "   Building inverted index...");
    *(_QWORD *)&v58 = v71;
    *((_QWORD *)&v58 + 1) = &std::cout;
    std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_boost::shared_ptr_Microsoft::ISRC::AttributeBuilder_________lambda_252d3536eb11a5b64a6d3407a326372e___(
      &v57,
      *((_QWORD *)v46 + 4),
      *((_QWORD *)v46 + 5),
      &v58);
    Microsoft::ISRC::ConstraintIndexBuilder::Segment::RemoveEmptyAttributes(v46);
    std::_Func_class<void,char const *>::operator()(v75, "   Reading forward index...");
    Microsoft::ISRC::ConstraintIndexBuilder::ReadForwardIndex(v51, v46);
    std::_Func_class<void,char const *>::operator()(v75, "   Materializing intersections...");
    Microsoft::ISRC::ConstraintIndexBuilder::BuildIntersections((Microsoft::ISRC::ConstraintIndexBuilder *)v71, v46);
  }
  std::_Func_class<void,char const *>::operator()(v75, "Writing index...");
  memset_0(v76, 0, 0x108u);
  std::ofstream::ofstream(v76, a3, 32);
  Microsoft::ISRC::ConstraintIndexBuilder::WriteIndex(v71, v76);
  std::_Func_class<void,char const *>::operator()(v75, "Done.");
  Microsoft::ISRC::ConstraintIndexBuilder::DumpStats(v71);
  std::ofstream::`vbase destructor'(v76);
  Microsoft::ISRC::MemoryMap::~MemoryMap((Microsoft::ISRC::MemoryMap *)v68);
  std::ifstream::`vbase destructor'(v77);
  Microsoft::ISRC::ConstraintIndexBuilder::~ConstraintIndexBuilder((Microsoft::ISRC::ConstraintIndexBuilder *)v71);
}

```

## disassembly

```asm
0x180061ccc  push    rbp
0x180061cce  push    rbx
0x180061ccf  push    rsi
0x180061cd0  push    rdi
0x180061cd1  push    r14
0x180061cd3  push    r15
0x180061cd5  lea     rbp, [rsp-6F8h]
0x180061cdd  sub     rsp, 7F8h
0x180061ce4  mov     rax, cs:__security_cookie
0x180061ceb  xor     rax, rsp
0x180061cee  mov     [rbp+720h+var_40], rax
0x180061cf5  mov     ebx, r9d
0x180061cf8  mov     r14, r8
0x180061cfb  mov     rsi, rdx
0x180061cfe  mov     rdi, rcx
0x180061d01  xor     edx, edx; Val
0x180061d03  mov     r8d, 128h; Size
0x180061d09  lea     rcx, [rbp+720h+var_5A0]; void *
0x180061d10  call    memset_0
0x180061d15  lea     rcx, [rbp+720h+var_5A0]; this
0x180061d1c  call    ??0ConstraintIndexBuilder@ISRC@Microsoft@@AEAA@XZ; Microsoft::ISRC::ConstraintIndexBuilder::ConstraintIndexBuilder(void)
0x180061d21  nop
0x180061d22  mov     rax, cs:?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x180061d29  movsxd  rcx, dword ptr [rax+4]
0x180061d2d  lea     r15, ?cout@std@@3V?$basic_ostream@DU?$char_traits@D@std@@@1@A; std::ostream std::cout
0x180061d34  mov     qword ptr [rcx+r15+20h], 3
0x180061d3d  lea     rcx, [rbp+720h+var_628]
0x180061d44  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180061d49  mov     qword ptr [rsp+820h+var_7C0], r15
0x180061d4e  lea     rax, [rbp+720h+var_628]
0x180061d55  mov     qword ptr [rsp+820h+var_7C0+8], rax
0x180061d5a  lea     rdx, [rsp+820h+var_7C0]
0x180061d5f  lea     rcx, [rbp+720h+var_4B8]
0x180061d66  call    std__function_void___cdecl_char_const______operator___lambda_95c28cb69a85e8d8c9862769ba9d5242__0_
0x180061d6b  mov     [rbp+720h+var_4BC], ebx
0x180061d71  lea     rdx, aReadingSchema; "Reading schema..."
0x180061d78  lea     rcx, [rbp+720h+var_4B8]
0x180061d7f  call    ??R?$_Func_class@XPEBD@std@@QEBAXPEBD@Z; std::_Func_class<void,char const *>::operator()(char const *)
0x180061d84  xor     edx, edx; Val
0x180061d86  mov     r8d, 110h; Size
0x180061d8c  lea     rcx, [rbp+720h+var_360]; void *
0x180061d93  call    memset_0
0x180061d98  mov     r8d, 1
0x180061d9e  mov     rdx, rdi
0x180061da1  lea     rcx, [rbp+720h+var_360]
0x180061da8  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x180061dad  nop
0x180061dae  mov     r8, rdi; wchar_t *
0x180061db1  lea     rcx, [rbp+720h+pszPath]; wchar_t *
0x180061db8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180061dbd  mov     ebx, 104h
0x180061dc2  mov     edx, ebx; cchPath
0x180061dc4  lea     rcx, [rbp+720h+pszPath]; pszPath
0x180061dcb  call    cs:__imp_PathCchRemoveFileSpec
0x180061dd1  mov     edx, ebx; cchPath
0x180061dd3  lea     rcx, [rbp+720h+pszPath]; pszPath
0x180061dda  call    cs:__imp_PathCchAddBackslash
0x180061de0  lea     r8, [rbp+720h+pszPath]
0x180061de7  lea     rdx, [rbp+720h+var_360]
0x180061dee  lea     rcx, [rbp+720h+var_5A0]; this
0x180061df5  call    ?ReadSchema@ConstraintIndexBuilder@ISRC@Microsoft@@AEAAXAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@PEB_W@Z; Microsoft::ISRC::ConstraintIndexBuilder::ReadSchema(std::istream &,wchar_t const *)
0x180061dfa  lea     rdx, aReadingData; "Reading data..."
0x180061e01  lea     rcx, [rbp+720h+var_4B8]
0x180061e08  call    ??R?$_Func_class@XPEBD@std@@QEBAXPEBD@Z; std::_Func_class<void,char const *>::operator()(char const *)
0x180061e0d  xorps   xmm0, xmm0
0x180061e10  movdqu  [rsp+820h+var_7D0], xmm0
0x180061e16  xorps   xmm1, xmm1
0x180061e19  xor     eax, eax
0x180061e1b  movups  [rbp+720h+var_600], xmm1
0x180061e22  movups  [rbp+720h+var_5F0], xmm1
0x180061e29  movups  [rbp+720h+var_5E0], xmm1
0x180061e30  mov     [rbp+720h+var_5D0], rax
0x180061e37  mov     rdx, rsi; wchar_t *
0x180061e3a  lea     rcx, [rbp+720h+var_600]; this
0x180061e41  call    ??0MemoryMappedFileReader@ISRC@Microsoft@@QEAA@PEB_W_N@Z; Microsoft::ISRC::MemoryMappedFileReader::MemoryMappedFileReader(wchar_t const *,bool)
0x180061e46  nop
0x180061e47  xor     r9d, r9d
0x180061e4a  mov     [rbp+720h+var_630], r9d
0x180061e51  lea     rdx, [rsp+820h+var_7D0]; struct Microsoft::ISRC::RangeString *
0x180061e56  lea     rcx, [rbp+720h+var_600]; this
0x180061e5d  call    ?ReadLine@MemoryMappedFileReader@ISRC@Microsoft@@QEAA_NAEAURangeString@23@@Z; Microsoft::ISRC::MemoryMappedFileReader::ReadLine(Microsoft::ISRC::RangeString &)
0x180061e62  test    al, al
0x180061e64  jz      loc_1800621CE
0x180061e6a  inc     r9d
0x180061e6d  mov     [rbp+720h+var_630], r9d
0x180061e74  mov     rdx, qword ptr [rsp+820h+var_7D0+8]
0x180061e79  mov     rbx, qword ptr [rsp+820h+var_7D0]
0x180061e7e  cmp     rdx, rbx
0x180061e81  jz      short loc_180061E51
0x180061e83  cmp     byte ptr [rbx], 23h ; '#'
0x180061e86  jz      short loc_180061E51
0x180061e88  mov     r8b, 9
0x180061e8b  mov     rcx, rbx
0x180061e8e  call    ??$_Find_vectorized@$$CBDD@std@@YAPEBDQEBD0D@Z; std::_Find_vectorized<char const,char>(char const * const,char const * const,char)
0x180061e93  mov     rdi, rax
0x180061e96  cmp     rax, rdx
0x180061e99  mov     rdx, rbx
0x180061e9c  jz      loc_1800620B4
0x180061ea2  mov     r8, rax
0x180061ea5  lea     rcx, [rbp+720h+var_5C8]
0x180061eac  call    ??$?0PEBD$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD0AEBV?$allocator@D@1@@Z; std::string::string(char const *,char const *,std::allocator<char> const &)
0x180061eb1  nop
0x180061eb2  xorps   xmm0, xmm0
0x180061eb5  movups  [rsp+820h+var_7C0], xmm0
0x180061eba  lea     r8, [rbp+720h+var_5C8]
0x180061ec1  lea     rdx, [rsp+820h+var_7B0]
0x180061ec6  lea     rcx, [rbp+720h+var_568]
0x180061ecd  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@USegment@ConstraintIndexBuilder@ISRC@Microsoft@@@boost@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Hash<std::_Umap_traits<std::string,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,boost::shared_ptr<Microsoft::ISRC::ConstraintIndexBuilder::Segment>>>,0>>::_Try_emplace<std::string const &,>(std::string const &)
0x180061ed2  mov     rcx, [rax]
0x180061ed5  mov     rsi, [rcx+30h]
0x180061ed9  mov     qword ptr [rsp+820h+var_7C0], rsi
0x180061ede  mov     rax, [rcx+38h]
0x180061ee2  mov     qword ptr [rsp+820h+var_7C0+8], rax
0x180061ee7  test    rax, rax
0x180061eea  jz      short loc_180061EF0
0x180061eec  lock inc dword ptr [rax+8]
0x180061ef0  test    rsi, rsi
0x180061ef3  jz      short loc_180061F51
0x180061ef5  xor     r8d, r8d
0x180061ef8  xor     edx, edx
0x180061efa  lea     rcx, [rdi+1]
0x180061efe  call    cs:__imp__o_strtoul
0x180061f04  dec     eax
0x180061f06  cmp     eax, 0F9FFh
0x180061f0b  ja      short loc_180061F74
0x180061f0d  lea     rcx, [rdi+1]; String
0x180061f11  call    cs:__imp_atol
0x180061f17  mov     dword ptr [rsp+820h+var_7F0], eax
0x180061f1b  movups  xmm0, [rsp+820h+var_7D0]
0x180061f20  movdqu  [rsp+820h+var_7E8], xmm0
0x180061f26  mov     rdx, [rsi+80h]
0x180061f2d  lea     rcx, [rsi+78h]
0x180061f31  cmp     rdx, [rsi+88h]
0x180061f38  jz      short loc_180061F46
0x180061f3a  lea     rdx, [rsp+820h+var_7F0]
0x180061f3f  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@@?$vector@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@V?$allocator@U?$pair@UNumericPoint2D@ISRC@Microsoft@@I@std@@@2@@std@@AEAAAEAU?$pair@UNumericPoint2D@ISRC@Microsoft@@I@1@$$QEAU21@@Z; std::vector<std::pair<Microsoft::ISRC::NumericPoint2D,uint>>::_Emplace_back_with_unused_capacity<std::pair<Microsoft::ISRC::NumericPoint2D,uint>>(std::pair<Microsoft::ISRC::NumericPoint2D,uint> &&)
0x180061f44  jmp     short loc_180061F51
0x180061f46  lea     r8, [rsp+820h+var_7F0]
0x180061f4b  call    ??$_Emplace_reallocate@U?$pair@IURangeString@ISRC@Microsoft@@@std@@@?$vector@U?$pair@IURangeString@ISRC@Microsoft@@@std@@V?$allocator@U?$pair@IURangeString@ISRC@Microsoft@@@std@@@2@@std@@AEAAPEAU?$pair@IURangeString@ISRC@Microsoft@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<uint,Microsoft::ISRC::RangeString>>::_Emplace_reallocate<std::pair<uint,Microsoft::ISRC::RangeString>>(std::pair<uint,Microsoft::ISRC::RangeString> * const,std::pair<uint,Microsoft::ISRC::RangeString> &&)
0x180061f50  nop
0x180061f51  lea     rcx, [rsp+820h+var_7C0+8]; this
0x180061f56  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180061f5b  nop
0x180061f5c  lea     rcx, [rbp+720h+var_5C8]
0x180061f63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180061f68  mov     r9d, [rbp+720h+var_630]
0x180061f6f  jmp     loc_180061E51
0x180061f74  mov     rdx, rbx
0x180061f77  lea     rcx, [rbp+720h+var_620]
0x180061f7e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180061f83  nop
0x180061f84  lea     rdx, aInvalidDataLin; "Invalid data - line %u: Score in second"...
0x180061f8b  lea     rcx, [rbp+720h+var_740]
0x180061f8f  call    ??0?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEAA@PEBD@Z; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(char const *)
0x180061f94  nop
0x180061f95  lea     rcx, [rbp+720h+var_630]
0x180061f9c  mov     [rsp+820h+var_7F0], rcx
0x180061fa1  lea     rbx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180061fa8  mov     qword ptr [rsp+820h+var_7E8], rbx
0x180061fad  lea     rdi, ??$call_put_last@DU?$char_traits@D@std@@$$CBI@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,uint const>(std::ostream &,void const *)
0x180061fb4  mov     qword ptr [rsp+820h+var_7E8+8], rdi
0x180061fb9  lea     rdx, [rsp+820h+var_7F0]
0x180061fbe  mov     rcx, rax
0x180061fc1  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180061fc6  lea     rcx, ?s_MaxScore@ConstraintIndexBuilderConstants@ISRC@Microsoft@@2IB; uint const Microsoft::ISRC::ConstraintIndexBuilderConstants::s_MaxScore
0x180061fcd  mov     [rsp+820h+var_7F0], rcx
0x180061fd2  mov     qword ptr [rsp+820h+var_7E8], rbx
0x180061fd7  mov     qword ptr [rsp+820h+var_7E8+8], rdi
0x180061fdc  lea     rdx, [rsp+820h+var_7F0]
0x180061fe1  mov     rcx, rax
0x180061fe4  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180061fe9  mov     rbx, rax
0x180061fec  mov     r9d, 40h ; '@'
0x180061ff2  xor     r8d, r8d
0x180061ff5  lea     rdx, [rbp+720h+var_788]
0x180061ff9  lea     rcx, [rbp+720h+var_620]
0x180062000  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x180062005  nop
0x180062006  mov     rcx, rax
0x180062009  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18006200e  mov     [rsp+820h+var_7B0], rax
0x180062013  lea     rax, [rsp+820h+var_7B0]
0x180062018  mov     [rsp+820h+var_7F0], rax
0x18006201d  lea     rdi, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180062024  mov     qword ptr [rsp+820h+var_7E8], rdi
0x180062029  lea     rsi, ??$call_put_last@DU?$char_traits@D@std@@QEBD@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>(std::ostream &,void const *)
0x180062030  mov     qword ptr [rsp+820h+var_7E8+8], rsi
0x180062035  lea     rdx, [rsp+820h+var_7F0]
0x18006203a  mov     rcx, rbx
0x18006203d  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180062042  lea     rcx, asc_180103728; "..."
0x180062049  lea     rdx, word_1801017B2
0x180062050  cmp     [rbp+720h+var_610], 40h ; '@'
0x180062058  cmovbe  rcx, rdx
0x18006205c  mov     qword ptr [rsp+820h+var_7D0], rcx
0x180062061  lea     rcx, [rsp+820h+var_7D0]
0x180062066  mov     [rsp+820h+var_7F0], rcx
0x18006206b  mov     qword ptr [rsp+820h+var_7E8], rdi
0x180062070  mov     qword ptr [rsp+820h+var_7E8+8], rsi
0x180062075  lea     rdx, [rsp+820h+var_7F0]
0x18006207a  mov     rcx, rax
0x18006207d  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180062082  lea     rdx, [rbp+720h+var_768]
0x180062086  mov     rcx, rax
0x180062089  call    ?str@?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x18006208e  nop
0x18006208f  mov     rcx, rax
0x180062092  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180062097  mov     rdx, rax; char *
0x18006209a  lea     rcx, [rbp+720h+pExceptionObject]; this
0x18006209e  call    ??0InvalidDataException@ISRC@Microsoft@@QEAA@PEBD@Z; Microsoft::ISRC::InvalidDataException::InvalidDataException(char const *)
0x1800620a3  lea     rdx, _TI3?AVInvalidDataException@ISRC@Microsoft@@; pThrowInfo
0x1800620aa  lea     rcx, [rbp+720h+pExceptionObject]; pExceptionObject
0x1800620ae  call    _CxxThrowException_0
0x1800620b4  lea     rcx, [rbp+720h+var_620]
0x1800620bb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800620c0  nop
0x1800620c1  lea     rdx, aInvalidDataLin_0; "Invalid data - line %u: Line must be ta"...
0x1800620c8  lea     rcx, [rbp+720h+var_740]
0x1800620cc  call    ??0?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEAA@PEBD@Z; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::basic_format<char,std::char_traits<char>,std::allocator<char>>(char const *)
0x1800620d1  nop
0x1800620d2  lea     rcx, [rbp+720h+var_630]
0x1800620d9  mov     [rsp+820h+var_7F0], rcx
0x1800620de  lea     rbx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800620e5  mov     qword ptr [rsp+820h+var_7E8], rbx
0x1800620ea  lea     rdi, ??$call_put_last@DU?$char_traits@D@std@@$$CBI@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,uint const>(std::ostream &,void const *)
0x1800620f1  mov     qword ptr [rsp+820h+var_7E8+8], rdi
0x1800620f6  lea     rdx, [rsp+820h+var_7F0]
0x1800620fb  mov     rcx, rax
0x1800620fe  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x180062103  mov     rbx, rax
0x180062106  mov     r9d, 40h ; '@'
0x18006210c  xor     r8d, r8d
0x18006210f  lea     rdx, [rbp+720h+var_768]
0x180062113  lea     rcx, [rbp+720h+var_620]
0x18006211a  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x18006211f  nop
0x180062120  mov     rcx, rax
0x180062123  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180062128  mov     qword ptr [rsp+820h+var_7D0], rax
0x18006212d  lea     rax, [rsp+820h+var_7D0]
0x180062132  mov     [rsp+820h+var_7F0], rax
0x180062137  lea     rdi, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18006213e  mov     qword ptr [rsp+820h+var_7E8], rdi
0x180062143  lea     rsi, ??$call_put_last@DU?$char_traits@D@std@@QEBD@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<char,std::char_traits<char>,char const * const>(std::ostream &,void const *)
0x18006214a  mov     qword ptr [rsp+820h+var_7E8+8], rsi
0x18006214f  lea     rdx, [rsp+820h+var_7F0]
0x180062154  mov     rcx, rbx
0x180062157  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x18006215c  lea     rcx, asc_180103728; "..."
0x180062163  lea     rdx, word_1801017B2
0x18006216a  cmp     [rbp+720h+var_610], 40h ; '@'
0x180062172  cmovbe  rcx, rdx
0x180062176  mov     [rsp+820h+var_7B0], rcx
0x18006217b  lea     rcx, [rsp+820h+var_7B0]
0x180062180  mov     [rsp+820h+var_7F0], rcx
0x180062185  mov     qword ptr [rsp+820h+var_7E8], rdi
0x18006218a  mov     qword ptr [rsp+820h+var_7E8+8], rsi
0x18006218f  lea     rdx, [rsp+820h+var_7F0]
0x180062194  mov     rcx, rax
0x180062197  call    ??$feed_impl@DU?$char_traits@D@std@@V?$allocator@D@2@AEBU?$put_holder@DU?$char_traits@D@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEAV32@AEBU?$put_holder@DU?$char_traits@D@std@@@012@@Z; boost::io::detail::feed_impl<char,std::char_traits<char>,std::allocator<char>,boost::io::detail::put_holder<char,std::char_traits<char>> const &>(boost::basic_format<char,std::char_traits<char>,std::allocator<char>> &,boost::io::detail::put_holder<char,std::char_traits<char>> const &)
0x18006219c  lea     rdx, [rbp+720h+var_788]
0x1800621a0  mov     rcx, rax
0x1800621a3  call    ?str@?$basic_format@DU?$char_traits@D@std@@V?$allocator@D@2@@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; boost::basic_format<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x1800621a8  nop
0x1800621a9  mov     rcx, rax
0x1800621ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800621b1  mov     rdx, rax; char *
0x1800621b4  lea     rcx, [rbp+720h+pExceptionObject]; this
0x1800621b8  call    ??0InvalidDataException@ISRC@Microsoft@@QEAA@PEBD@Z; Microsoft::ISRC::InvalidDataException::InvalidDataException(char const *)
0x1800621bd  lea     rdx, _TI3?AVInvalidDataException@ISRC@Microsoft@@; pThrowInfo
0x1800621c4  lea     rcx, [rbp+720h+pExceptionObject]; pExceptionObject
0x1800621c8  call    _CxxThrowException_0
0x1800621ce  mov     rbx, [rbp+720h+var_580]
0x1800621d5  cmp     rbx, [rbp+720h+var_578]
0x1800621dc  jz      loc_1800622F1
0x1800621e2  mov     rdi, [rbx]
0x1800621e5  mov     r8, rdi
0x1800621e8  lea     rdx, aSegment; "Segment: "
0x1800621ef  lea     rcx, [rbp+720h+var_620]
0x1800621f6  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x1800621fb  nop
0x1800621fc  mov     rcx, rax
0x1800621ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180062204  mov     rdx, rax
0x180062207  lea     rcx, [rbp+720h+var_4B8]
0x18006220e  call    ??R?$_Func_class@XPEBD@std@@QEBAXPEBD@Z; std::_Func_class<void,char const *>::operator()(char const *)
0x180062213  nop
0x180062214  lea     rcx, [rbp+720h+var_620]
0x18006221b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180062220  mov     rdx, [rdi+80h]
0x180062227  mov     rcx, [rdi+78h]
0x18006222b  mov     r8, rdx
0x18006222e  sub     r8, rcx
0x180062231  sar     r8, 3
0x180062235  mov     rax, 0AAAAAAAAAAAAAAABh
0x18006223f  imul    r8, rax
0x180062243  mov     r9b, [rsp+820h+var_7D8]
0x180062248  call    std___Sort_unchecked_std__pair_unsigned_int_Microsoft__ISRC__RangeString_____lambda_bd763e29cea7a6255e36bc3a62563b8a___
0x18006224d  lea     rdx, aReadingValues; "   Reading values..."
  ... truncated ...
```
