# Uev::UevIPC::SerializeMapToJson(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &)

- ea: `0x140015a68`
- end: `0x140015d50`
- name: `?SerializeMapToJson@UevIPC@Uev@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callers

- `0x140015874`

## callees

- `0x140003e50`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000e0c0`
- `0x1400114c0`
- `0x140011524`
- `0x1400115ac`
- `0x1400116c8`
- `0x140011ab4`
- `0x140011bb4`
- `0x140011cf8`
- `0x1400120dc`
- `0x140012cc4`
- `0x1400130d0`
- `0x140013460`
- `0x14001358c`
- `0x140015a68`
- `0x140017a50`
- `0x140018d78`
- `0x140019098`

## import_xrefs

- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x140015c05`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x140015c05`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x140015c5f`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x140015c5f`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x140015c6c`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x140015c6c`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140015bf0`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140015bf0`

## string_xrefs

- `0x140015ca6`: `write_json_internal`
- `0x140015cff`: `write_json_internal`
- `0x140015cb3`: `admin\oss\boost\vcpkg\objfre\amd64\vcpkg_installed\target-windows\include\boost\property_tree\json_parser\detail\write.hpp`
- `0x140015d0c`: `admin\oss\boost\vcpkg\objfre\amd64\vcpkg_installed\target-windows\include\boost\property_tree\json_parser\detail\write.hpp`
- `0x140015d20`: `ptree contains data that cannot be represented in JSON format`
- `0x140015cc7`: `write error`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Uev::UevIPC::SerializeMapToJson(__int64 a1, __int64 a2, _QWORD **a3)
{
  _QWORD *v5; // rbx
  __int128 *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 **v9; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int128 v17; // [rsp+30h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+40h] [rbp-C0h]
  __int16 v19; // [rsp+50h] [rbp-B0h]
  __int128 *v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[96]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v24[6]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v25[48]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v26; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v27[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v28[120]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v29[104]; // [rsp+1D8h] [rbp+D8h] BYREF

  v21 = a2;
  boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(v25);
  v5 = (_QWORD *)**a3;
  while ( v5 != *a3 )
  {
    std::wstring::wstring((__int64)&v17, (__int64)(v5 + 4));
    v19 = 46;
    v6 = &v17;
    if ( si128.m128i_i64[1] > 7uLL )
      v6 = (__int128 *)v17;
    v20 = v6;
    boost::property_tree::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>>::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>>(
      (__int64)v24,
      (__int64)&v17);
    v7 = boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::walk_path(v25, v24);
    std::wstring::_Tidy_deallocate(v24);
    if ( !v7 )
    {
      v8 = boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(v24);
      v7 = boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::put_child(
             v25,
             &v17,
             v8);
      boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::~basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(v24);
    }
    boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::put_value<std::wstring,boost::property_tree::id_translator<std::wstring>>(
      v7,
      v5 + 8);
    std::wstring::_Tidy_deallocate(&v17);
    v9 = (__int64 **)v5[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = v5[1]; !*(_BYTE *)(i + 25) && v5 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v5 = (_QWORD *)i;
      v5 = (_QWORD *)i;
    }
    else
    {
      v5 = (_QWORD *)v5[2];
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  std::wostringstream::wostringstream(&v26);
  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v17) = 0;
  if ( !boost::property_tree::json_parser::verify_json<boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>>(
          (__int64)v25,
          0) )
  {
    v15 = boost::source_location::source_location(
            (boost::source_location *)v22,
            "admin\\oss\\boost\\vcpkg\\objfre\\amd64\\vcpkg_installed\\target-windows\\include\\boost\\property_tree\\jso"
            "n_parser\\detail\\write.hpp",
            0x9Fu,
            "write_json_internal",
            0xDu);
    std::string::string(v24, "ptree contains data that cannot be represented in JSON format");
    v16 = boost::property_tree::json_parser::json_parser_error::json_parser_error((__int64)v23, v24, (__int64)&v17);
    boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(v16, v15);
  }
  boost::property_tree::json_parser::write_json_helper<boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>>(
    (__int64)&v26,
    (__int64)v25,
    0);
  std::wostream::operator<<(&v26, std::endl<wchar_t,std::char_traits<wchar_t>>);
  if ( !std::ios_base::good((std::ios_base *)&v27[*(int *)(v26 + 4) - 8]) )
  {
    v13 = boost::source_location::source_location(
            (boost::source_location *)v22,
            "admin\\oss\\boost\\vcpkg\\objfre\\amd64\\vcpkg_installed\\target-windows\\include\\boost\\property_tree\\jso"
            "n_parser\\detail\\write.hpp",
            0xA3u,
            "write_json_internal",
            0xDu);
    std::string::string(v24, "write error");
    v14 = boost::property_tree::json_parser::json_parser_error::json_parser_error((__int64)v23, v24, (__int64)&v17);
    boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(v14, v13);
  }
  std::string::_Tidy_deallocate(&v17);
  std::wstringbuf::str(v27, a2);
  *(_QWORD *)&v27[*(int *)(v26 + 4) - 8] = &std::wostringstream::`vftable';
  *(_DWORD *)&v25[*(int *)(v26 + 4) + 44] = *(_DWORD *)(v26 + 4) - 136;
  std::wstringbuf::~wstringbuf(v27);
  std::wostream::~wostream<wchar_t,std::char_traits<wchar_t>>(v28);
  std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v29);
  boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::~basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(v25);
  return a2;
}

```

## disassembly

```asm
0x140015a68  push    rbp
0x140015a6a  push    rbx
0x140015a6b  push    rsi
0x140015a6c  push    rdi
0x140015a6d  push    r14
0x140015a6f  push    r15
0x140015a71  lea     rbp, [rsp-158h]
0x140015a79  sub     rsp, 258h
0x140015a80  mov     rax, cs:__security_cookie
0x140015a87  xor     rax, rsp
0x140015a8a  mov     [rbp+180h+var_40], rax
0x140015a91  mov     r14, r8
0x140015a94  mov     rsi, rdx
0x140015a97  mov     [rsp+280h+var_218], rdx
0x140015a9c  lea     rcx, [rbp+180h+var_160]
0x140015aa0  call    ??0?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(void)
0x140015aa5  nop
0x140015aa6  mov     rbx, [r14]
0x140015aa9  mov     rbx, [rbx]
0x140015aac  cmp     rbx, [r14]
0x140015aaf  jz      loc_140015B9D
0x140015ab5  lea     rdx, [rbx+20h]
0x140015ab9  lea     rcx, [rsp+280h+var_250]
0x140015abe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140015ac3  mov     eax, 2Eh ; '.'
0x140015ac8  mov     [rsp+280h+var_230], ax
0x140015acd  lea     rax, [rsp+280h+var_250]
0x140015ad2  cmp     [rsp+280h+var_238], 7
0x140015ad8  cmova   rax, qword ptr [rsp+280h+var_250]
0x140015ade  mov     [rsp+280h+var_228], rax
0x140015ae3  lea     rdx, [rsp+280h+var_250]
0x140015ae8  lea     rcx, [rbp+180h+var_190]
0x140015aec  call    ??0?$string_path@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$id_translator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@property_tree@boost@@@property_tree@boost@@QEAA@AEBV012@@Z; boost::property_tree::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>>::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>>(boost::property_tree::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>> const &)
0x140015af1  nop
0x140015af2  lea     rdx, [rbp+180h+var_190]
0x140015af6  lea     rcx, [rbp+180h+var_160]
0x140015afa  call    ?walk_path@?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@AEBAPEAV123@AEAV?$string_path@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$id_translator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@property_tree@boost@@@23@@Z; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::walk_path(boost::property_tree::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>> &)
0x140015aff  mov     rdi, rax
0x140015b02  lea     rcx, [rbp+180h+var_190]
0x140015b06  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015b0b  test    rdi, rdi
0x140015b0e  jnz     short loc_140015B37
0x140015b10  lea     rcx, [rbp+180h+var_190]
0x140015b14  call    ??0?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(void)
0x140015b19  nop
0x140015b1a  mov     r8, rax
0x140015b1d  lea     rdx, [rsp+280h+var_250]
0x140015b22  lea     rcx, [rbp+180h+var_160]
0x140015b26  call    ?put_child@?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAAAEAV123@AEBV?$string_path@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$id_translator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@property_tree@boost@@@23@AEBV123@@Z; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::put_child(boost::property_tree::string_path<std::wstring,boost::property_tree::id_translator<std::wstring>> const &,boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>> const &)
0x140015b2b  mov     rdi, rax
0x140015b2e  lea     rcx, [rbp+180h+var_190]
0x140015b32  call    ??1?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::~basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(void)
0x140015b37  lea     rdx, [rbx+40h]
0x140015b3b  mov     rcx, rdi
0x140015b3e  call    ??$put_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$id_translator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@property_tree@boost@@@?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$id_translator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@12@@Z; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::put_value<std::wstring,boost::property_tree::id_translator<std::wstring>>(std::wstring const &,boost::property_tree::id_translator<std::wstring>)
0x140015b43  nop
0x140015b44  lea     rcx, [rsp+280h+var_250]
0x140015b49  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015b4e  mov     rcx, [rbx+10h]
0x140015b52  cmp     byte ptr [rcx+19h], 0
0x140015b56  jz      short loc_140015B79
0x140015b58  mov     rax, [rbx+8]
0x140015b5c  jmp     short loc_140015B6B
0x140015b5e  cmp     rbx, [rax+10h]
0x140015b62  jnz     short loc_140015B71
0x140015b64  mov     rbx, rax
0x140015b67  mov     rax, [rax+8]
0x140015b6b  cmp     byte ptr [rax+19h], 0
0x140015b6f  jz      short loc_140015B5E
0x140015b71  mov     rbx, rax
0x140015b74  jmp     loc_140015AAC
0x140015b79  mov     rbx, rcx
0x140015b7c  mov     rcx, [rcx]
0x140015b7f  cmp     byte ptr [rcx+19h], 0
0x140015b83  jnz     loc_140015AAC
0x140015b89  mov     rbx, rcx
0x140015b8c  mov     rax, [rcx]
0x140015b8f  mov     rcx, rax
0x140015b92  cmp     byte ptr [rax+19h], 0
0x140015b96  jz      short loc_140015B89
0x140015b98  jmp     loc_140015AAC
0x140015b9d  lea     rcx, [rbp+180h+var_130]
0x140015ba1  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x140015ba6  nop
0x140015ba7  xorps   xmm0, xmm0
0x140015baa  movups  [rsp+280h+var_250], xmm0
0x140015baf  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x140015bb7  movdqu  xmmword ptr [rsp+40h], xmm1
0x140015bbd  mov     byte ptr [rsp+280h+var_250], 0
0x140015bc2  xor     edx, edx
0x140015bc4  lea     rcx, [rbp+180h+var_160]
0x140015bc8  call    ??$verify_json@V?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YA_NAEBV?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@12@H@Z; boost::property_tree::json_parser::verify_json<boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>>(boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>> const &,int)
0x140015bcd  test    al, al
0x140015bcf  jz      loc_140015CF7
0x140015bd5  xor     r8d, r8d
0x140015bd8  lea     rdx, [rbp+180h+var_160]
0x140015bdc  lea     rcx, [rbp+180h+var_130]
0x140015be0  call    ??$write_json_helper@V?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@@json_parser@property_tree@boost@@YAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@12@H_N@Z; boost::property_tree::json_parser::write_json_helper<boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>>(std::wostream &,boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>> const &,int,bool)
0x140015be5  lea     rdx, ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x140015bec  lea     rcx, [rbp+180h+var_130]
0x140015bf0  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::wostream::operator<<(std::wostream & (*)(std::wostream &))
0x140015bf6  mov     rax, [rbp+180h+var_130]
0x140015bfa  movsxd  rcx, dword ptr [rax+4]
0x140015bfe  lea     rax, [rbp+180h+var_130]
0x140015c02  add     rcx, rax
0x140015c05  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x140015c0b  test    al, al
0x140015c0d  jz      loc_140015C9E
0x140015c13  lea     rcx, [rsp+280h+var_250]
0x140015c18  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140015c1d  mov     rdx, rsi
0x140015c20  lea     rcx, [rbp+180h+var_128]
0x140015c24  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x140015c29  nop
0x140015c2a  mov     rax, [rbp+180h+var_130]
0x140015c2e  movsxd  rcx, dword ptr [rax+4]
0x140015c32  lea     rax, ??_7?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wostringstream::`vftable'
0x140015c39  mov     [rbp+rcx+180h+var_130], rax
0x140015c3e  mov     rcx, [rbp+180h+var_130]
0x140015c42  movsxd  rdx, dword ptr [rcx+4]
0x140015c46  lea     r8d, [rdx-88h]
0x140015c4d  mov     [rbp+rdx+180h+var_134], r8d
0x140015c52  lea     rcx, [rbp+180h+var_128]
0x140015c56  call    ??1?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ; std::wstringbuf::~wstringbuf(void)
0x140015c5b  lea     rcx, [rbp+180h+var_120]
0x140015c5f  call    cs:__imp_??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wostream::~wostream<wchar_t,std::char_traits<wchar_t>>(void)
0x140015c65  lea     rcx, [rbp+180h+var_A8]
0x140015c6c  call    cs:__imp_??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(void)
0x140015c72  nop
0x140015c73  lea     rcx, [rbp+180h+var_160]
0x140015c77  call    ??1?$basic_ptree@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>::~basic_ptree<std::wstring,std::wstring,std::less<std::wstring>>(void)
0x140015c7c  mov     rax, rsi
0x140015c7f  mov     rcx, [rbp+180h+var_40]
0x140015c86  xor     rcx, rsp; StackCookie
0x140015c89  call    __security_check_cookie
0x140015c8e  add     rsp, 258h
0x140015c95  pop     r15
0x140015c97  pop     r14
0x140015c99  pop     rdi
0x140015c9a  pop     rsi
0x140015c9b  pop     rbx
0x140015c9c  pop     rbp
0x140015c9d  retn
0x140015c9e  mov     [rsp+280h+var_260], 0Dh; unsigned int
0x140015ca6  lea     r9, aWriteJsonInter; "write_json_internal"
0x140015cad  mov     r8d, 0A3h; unsigned int
0x140015cb3  lea     rdx, aAdminOssBoostV_0; "admin\\oss\\boost\\vcpkg\\objfre\\amd64"...
0x140015cba  lea     rcx, [rsp+280h+var_210]; this
0x140015cbf  call    ??0source_location@boost@@QEAA@PEBDI0I@Z; boost::source_location::source_location(char const *,uint,char const *,uint)
0x140015cc4  mov     rbx, rax
0x140015cc7  lea     rdx, aWriteError; "write error"
0x140015cce  lea     rcx, [rbp+180h+var_190]
0x140015cd2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140015cd7  nop
0x140015cd8  lea     r8, [rsp+280h+var_250]
0x140015cdd  lea     rdx, [rbp+180h+var_190]
0x140015ce1  lea     rcx, [rbp+180h+var_1F0]
0x140015ce5  call    ??0json_parser_error@json_parser@property_tree@boost@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0K@Z; boost::property_tree::json_parser::json_parser_error::json_parser_error(std::string const &,std::string const &,ulong)
0x140015cea  nop
0x140015ceb  mov     rdx, rbx
0x140015cee  mov     rcx, rax
0x140015cf1  call    ??$throw_exception@Vjson_parser_error@json_parser@property_tree@boost@@@boost@@YAXAEBVjson_parser_error@json_parser@property_tree@0@AEBUsource_location@0@@Z; boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(boost::property_tree::json_parser::json_parser_error const &,boost::source_location const &)
0x140015cf7  mov     [rsp+280h+var_260], 0Dh; unsigned int
0x140015cff  lea     r9, aWriteJsonInter; "write_json_internal"
0x140015d06  mov     r8d, 9Fh; unsigned int
0x140015d0c  lea     rdx, aAdminOssBoostV_0; "admin\\oss\\boost\\vcpkg\\objfre\\amd64"...
0x140015d13  lea     rcx, [rsp+280h+var_210]; this
0x140015d18  call    ??0source_location@boost@@QEAA@PEBDI0I@Z; boost::source_location::source_location(char const *,uint,char const *,uint)
0x140015d1d  mov     rbx, rax
0x140015d20  lea     rdx, aPtreeContainsD; "ptree contains data that cannot be repr"...
0x140015d27  lea     rcx, [rbp+180h+var_190]
0x140015d2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140015d30  nop
0x140015d31  lea     r8, [rsp+280h+var_250]
0x140015d36  lea     rdx, [rbp+180h+var_190]
0x140015d3a  lea     rcx, [rbp+180h+var_1F0]
0x140015d3e  call    ??0json_parser_error@json_parser@property_tree@boost@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0K@Z; boost::property_tree::json_parser::json_parser_error::json_parser_error(std::string const &,std::string const &,ulong)
0x140015d43  nop
0x140015d44  mov     rdx, rbx
0x140015d47  mov     rcx, rax
0x140015d4a  call    ??$throw_exception@Vjson_parser_error@json_parser@property_tree@boost@@@boost@@YAXAEBVjson_parser_error@json_parser@property_tree@0@AEBUsource_location@0@@Z; boost::throw_exception<boost::property_tree::json_parser::json_parser_error>(boost::property_tree::json_parser::json_parser_error const &,boost::source_location const &)
```
