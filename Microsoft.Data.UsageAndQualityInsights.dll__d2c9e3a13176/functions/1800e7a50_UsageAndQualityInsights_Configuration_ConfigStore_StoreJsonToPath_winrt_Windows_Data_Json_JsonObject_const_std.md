# UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(winrt::Windows::Data::Json::JsonObject const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800e7a50`
- end: `0x1800e7d99`
- name: `?StoreJsonToPath@ConfigStore@Configuration@UsageAndQualityInsights@@CAXAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `841`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x1800e75bc`

## callees

- `0x1800033d0`
- `0x1800040a0`
- `0x180004140`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180020650`
- `0x18004c51c`
- `0x1800e4b98`
- `0x1800e5ee8`
- `0x1800e7a50`
- `0x1800e8504`
- `0x1800e8620`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800e7bca`
- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800e7cb9`
- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800e7bca`
- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800e7cb9`
- `msvcp_win!??0?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x1800e7b5a`
- `msvcp_win!??0?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x1800e7b5a`
- `msvcp_win!??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x1800e7b07`
- `msvcp_win!??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x1800e7b07`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800e7d65`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800e7d65`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x1800e7cd0`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x1800e7cd0`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800e7d5b`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800e7d5b`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e7b79`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e7b79`
- `msvcp_win!??0?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z` at `0x1800e7b26`
- `msvcp_win!??0?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z` at `0x1800e7b26`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e7d92`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e7d92`

## string_xrefs

- `0x1800e7aa6`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`
- `0x1800e7c17`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`
- `0x1800e7c5e`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`
- `0x1800e7cf3`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`
- `0x1800e7a90`: `File path cannot be empty`
- `0x1800e7c01`: `Failed to open file for writing`
- `0x1800e7c48`: `JSON serialization resulted in empty string`
- `0x1800e7cdd`: `Failed to write JSON data to file`

## pseudocode

```c
void __fastcall UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // r8
  __int128 *v5; // rbx
  unsigned int *v6; // rbx
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  int v11; // [rsp+20h] [rbp-E0h]
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  int *v16; // [rsp+40h] [rbp-C0h] BYREF
  void **v17; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[96]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-50h]
  char v20; // [rsp+BAh] [rbp-46h]
  __int64 v21; // [rsp+BCh] [rbp-44h]
  char v22; // [rsp+C4h] [rbp-3Ch]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  _BYTE v24[112]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v25; // [rsp+158h] [rbp+58h] BYREF
  __int64 v26; // [rsp+168h] [rbp+68h]
  unsigned __int64 v27; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v2 = a2;
  LODWORD(lpMem[0]) = 0;
  LOBYTE(v11) = a2[2] == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
    (const char *)0x80070057LL,
    v11,
    (bool)"File path cannot be empty",
    (const char *)lpMem[0]);
  v4 = v2[2];
  if ( v2[3] > 7u )
    v2 = (_QWORD *)*v2;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v25, v2, v4);
  v5 = &v25;
  if ( v27 > 7 )
    v5 = (__int128 *)v25;
  v16 = &std::wofstream::`vbtable';
  std::wios::wios(v24);
  LODWORD(lpMem[0]) = 7;
  std::wostream::wostream(&v16, &v17, 0, 0);
  *(int **)((char *)&v16 + v16[1]) = (int *)&std::wofstream::`vftable';
  *(_DWORD *)((char *)&lpMem[1] + v16[1] + 4) = v16[1] - 168;
  std::wstreambuf::wstreambuf(&v17);
  v17 = &std::wfilebuf::`vftable';
  v22 = 0;
  v20 = 0;
  std::wstreambuf::_Init(&v17);
  v23 = 0;
  v21 = `std::wfilebuf::_Init'::`2'::_Stinit;
  v19 = 0;
  if ( !std::wfilebuf::open(&v17, v5, 2) )
    std::wios::setstate((char *)&v16 + v16[1], 2);
  *(int **)((char *)&v16 + v16[1]) = (int *)&std::wofstream::`vftable';
  *(_DWORD *)((char *)&lpMem[1] + v16[1] + 4) = v16[1] - 168;
  LOBYTE(v12) = v23 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x95,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
    (const char *)0x80070005LL,
    v12,
    (bool)"Failed to open file for writing",
    (const char *)lpMem[0]);
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(a1, lpMem);
  v6 = (unsigned int *)lpMem[0];
  LOBYTE(v13) = lpMem[0] == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x98,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
    (const char *)0x80070057LL,
    v13,
    (bool)"JSON serialization resulted in empty string",
    (const char *)lpMem[0]);
  if ( v6 )
  {
    v7 = v6[1];
    v8 = (const wchar_t *)*((_QWORD *)v6 + 2);
  }
  else
  {
    v7 = 0;
    v8 = &S1;
  }
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&v16, v8, v7);
  if ( !std::wfilebuf::close(&v17) )
    std::wios::setstate((char *)&v16 + v16[1], 2);
  LOBYTE(v14) = std::ios_base::fail((std::ios_base *)((char *)&v16 + v16[1]));
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
    (const char *)0x80004005LL,
    v14,
    (bool)"Failed to write JSON data to file",
    (const char *)lpMem[0]);
  if ( v6 )
  {
    v9 = _InterlockedDecrement((volatile signed __int32 *)v6 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v6);
    }
  }
  *(int **)((char *)&v16 + v16[1]) = (int *)&std::wofstream::`vftable';
  *(_DWORD *)((char *)&lpMem[1] + v16[1] + 4) = v16[1] - 168;
  std::wfilebuf::~wfilebuf<wchar_t,std::char_traits<wchar_t>>(&v17);
  std::wostream::~wostream<wchar_t,std::char_traits<wchar_t>>(v18);
  std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v24);
  std::wstring::~wstring(&v25);
}

```

## disassembly

```asm
0x1800e7a50  push    rbp
0x1800e7a52  push    rbx
0x1800e7a53  push    rdi
0x1800e7a54  push    r13
0x1800e7a56  lea     rbp, [rsp-88h]
0x1800e7a5e  sub     rsp, 188h
0x1800e7a65  mov     rax, cs:__security_cookie
0x1800e7a6c  xor     rax, rsp
0x1800e7a6f  mov     [rbp+0A0h+var_28], rax
0x1800e7a73  mov     rbx, rdx
0x1800e7a76  mov     rdi, rcx
0x1800e7a79  mov     dword ptr [rsp+1A0h+lpMem], 0; char *
0x1800e7a81  cmp     qword ptr [rdx+10h], 0
0x1800e7a86  setz    al
0x1800e7a89  mov     rcx, [rbp+0A8h]; this
0x1800e7a90  lea     rdx, aFilePathCannot; "File path cannot be empty"
0x1800e7a97  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x1800e7a9c  mov     byte ptr [rsp+1A0h+var_180], al; int
0x1800e7aa0  mov     r9d, 80070057h; char *
0x1800e7aa6  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e7aad  mov     edx, 90h; void *
0x1800e7ab2  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800e7ab7  mov     r8, [rbx+10h]
0x1800e7abb  cmp     qword ptr [rbx+18h], 7
0x1800e7ac0  jbe     short loc_1800E7AC5
0x1800e7ac2  mov     rbx, [rbx]
0x1800e7ac5  xorps   xmm0, xmm0
0x1800e7ac8  movups  [rbp+0A0h+var_48], xmm0
0x1800e7acc  mov     [rbp+0A0h+var_38], 0
0x1800e7ad4  mov     [rbp+0A0h+var_30], 0
0x1800e7adc  mov     rdx, rbx
0x1800e7adf  lea     rcx, [rbp+0A0h+var_48]
0x1800e7ae3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800e7ae8  nop
0x1800e7ae9  lea     rbx, [rbp+0A0h+var_48]
0x1800e7aed  cmp     [rbp+0A0h+var_30], 7
0x1800e7af2  cmova   rbx, qword ptr [rbp+0A0h+var_48]
0x1800e7af7  lea     rax, ??_8?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@7B@; const std::wofstream::`vbtable'
0x1800e7afe  mov     [rsp+1A0h+var_160], rax
0x1800e7b03  lea     rcx, [rbp+0A0h+var_B8]
0x1800e7b07  call    cs:__imp_??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ; std::wios::wios(void)
0x1800e7b0d  nop
0x1800e7b0e  mov     dword ptr [rsp+1A0h+lpMem], 7; char *
0x1800e7b16  xor     r9d, r9d
0x1800e7b19  xor     r8d, r8d
0x1800e7b1c  lea     rdx, [rsp+1A0h+var_158]
0x1800e7b21  lea     rcx, [rsp+1A0h+var_160]
0x1800e7b26  call    cs:__imp_??0?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z; std::wostream::wostream(std::wstreambuf *,bool)
0x1800e7b2c  nop
0x1800e7b2d  mov     rax, [rsp+1A0h+var_160]
0x1800e7b32  movsxd  rcx, dword ptr [rax+4]
0x1800e7b36  lea     r13, ??_7?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wofstream::`vftable'
0x1800e7b3d  mov     [rsp+rcx+1A0h+var_160], r13
0x1800e7b42  mov     rax, [rsp+1A0h+var_160]
0x1800e7b47  movsxd  rcx, dword ptr [rax+4]
0x1800e7b4b  lea     edx, [rcx-0A8h]
0x1800e7b51  mov     [rsp+rcx+1A0h+var_164], edx
0x1800e7b55  lea     rcx, [rsp+1A0h+var_158]
0x1800e7b5a  call    cs:__imp_??0?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAA@XZ; std::wstreambuf::wstreambuf(void)
0x1800e7b60  lea     rax, ??_7?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@6B@; const std::wfilebuf::`vftable'
0x1800e7b67  mov     [rsp+1A0h+var_158], rax
0x1800e7b6c  mov     [rbp+0A0h+var_DC], 0
0x1800e7b70  mov     [rbp+0A0h+var_E6], 0
0x1800e7b74  lea     rcx, [rsp+1A0h+var_158]
0x1800e7b79  call    cs:__imp_?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ; std::wstreambuf::_Init(void)
0x1800e7b7f  mov     [rbp+0A0h+var_D8], 0
0x1800e7b87  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::wfilebuf::_Init(_iobuf *,std::wfilebuf::_Initfl)'::`2'::_Stinit
0x1800e7b8e  mov     [rbp+0A0h+var_E4], rax
0x1800e7b92  mov     [rbp+0A0h+var_F0], 0
0x1800e7b9a  mov     r8d, 2
0x1800e7ba0  mov     rdx, rbx
0x1800e7ba3  lea     rcx, [rsp+1A0h+var_158]
0x1800e7ba8  call    ?open@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@PEB_WHH@Z; std::wfilebuf::open(wchar_t const *,int,int)
0x1800e7bad  test    rax, rax
0x1800e7bb0  jnz     short loc_1800E7BD1
0x1800e7bb2  mov     rax, [rsp+1A0h+var_160]
0x1800e7bb7  movsxd  rcx, dword ptr [rax+4]
0x1800e7bbb  lea     rax, [rsp+1A0h+var_160]
0x1800e7bc0  add     rcx, rax
0x1800e7bc3  xor     r8d, r8d
0x1800e7bc6  lea     edx, [r8+2]
0x1800e7bca  call    cs:__imp_?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x1800e7bd0  nop
0x1800e7bd1  mov     rax, [rsp+1A0h+var_160]
0x1800e7bd6  movsxd  rcx, dword ptr [rax+4]
0x1800e7bda  mov     [rsp+rcx+1A0h+var_160], r13
0x1800e7bdf  mov     rax, [rsp+1A0h+var_160]
0x1800e7be4  movsxd  rcx, dword ptr [rax+4]
0x1800e7be8  lea     edx, [rcx-0A8h]
0x1800e7bee  mov     [rsp+rcx+1A0h+var_164], edx
0x1800e7bf2  cmp     [rbp+0A0h+var_D8], 0
0x1800e7bf7  setz    al
0x1800e7bfa  mov     rcx, [rbp+0A8h]; this
0x1800e7c01  lea     rdx, aFailedToOpenFi; "Failed to open file for writing"
0x1800e7c08  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x1800e7c0d  mov     byte ptr [rsp+1A0h+var_180], al; int
0x1800e7c11  mov     r9d, 80070005h; char *
0x1800e7c17  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e7c1e  mov     edx, 95h; void *
0x1800e7c23  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800e7c28  lea     rdx, [rsp+1A0h+lpMem]
0x1800e7c2d  mov     rcx, rdi
0x1800e7c30  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x1800e7c35  nop
0x1800e7c36  mov     rbx, [rsp+1A0h+lpMem]
0x1800e7c3b  test    rbx, rbx
0x1800e7c3e  setz    al
0x1800e7c41  mov     rcx, [rbp+0A8h]; this
0x1800e7c48  lea     rdx, aJsonSerializat; "JSON serialization resulted in empty st"...
0x1800e7c4f  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x1800e7c54  mov     byte ptr [rsp+1A0h+var_180], al; int
0x1800e7c58  mov     r9d, 80070057h; char *
0x1800e7c5e  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e7c65  mov     edx, 98h; void *
0x1800e7c6a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800e7c6f  test    rbx, rbx
0x1800e7c72  jz      short loc_1800E7C7E
0x1800e7c74  mov     r8d, [rbx+4]
0x1800e7c78  mov     rdx, [rbx+10h]
0x1800e7c7c  jmp     short loc_1800E7C88
0x1800e7c7e  xor     r8d, r8d
0x1800e7c81  lea     rdx, S1
0x1800e7c88  lea     rcx, [rsp+1A0h+var_160]
0x1800e7c8d  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1800e7c92  lea     rcx, [rsp+1A0h+var_158]
0x1800e7c97  call    ?close@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@XZ; std::wfilebuf::close(void)
0x1800e7c9c  test    rax, rax
0x1800e7c9f  jnz     short loc_1800E7CBF
0x1800e7ca1  mov     rax, [rsp+1A0h+var_160]
0x1800e7ca6  movsxd  rcx, dword ptr [rax+4]
0x1800e7caa  lea     rax, [rsp+1A0h+var_160]
0x1800e7caf  add     rcx, rax
0x1800e7cb2  xor     r8d, r8d
0x1800e7cb5  lea     edx, [r8+2]
0x1800e7cb9  call    cs:__imp_?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x1800e7cbf  mov     rax, [rsp+1A0h+var_160]
0x1800e7cc4  movsxd  rcx, dword ptr [rax+4]
0x1800e7cc8  lea     rax, [rsp+1A0h+var_160]
0x1800e7ccd  add     rcx, rax
0x1800e7cd0  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x1800e7cd6  mov     rcx, [rbp+0A8h]; this
0x1800e7cdd  lea     rdx, aFailedToWriteJ; "Failed to write JSON data to file"
0x1800e7ce4  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x1800e7ce9  mov     byte ptr [rsp+1A0h+var_180], al; int
0x1800e7ced  mov     r9d, 80004005h; char *
0x1800e7cf3  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e7cfa  mov     edx, 9Dh; void *
0x1800e7cff  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800e7d04  nop
0x1800e7d05  test    rbx, rbx
0x1800e7d08  jz      short loc_1800E7D2B
0x1800e7d0a  or      eax, 0FFFFFFFFh
0x1800e7d0d  lock xadd [rbx+18h], eax
0x1800e7d12  sub     eax, 1
0x1800e7d15  jnz     short loc_1800E7D8E
0x1800e7d17  nop
0x1800e7d18  call    WINRT_IMPL_GetProcessHeap
0x1800e7d1d  mov     rcx, rax; hHeap
0x1800e7d20  mov     r8, rbx; lpMem
0x1800e7d23  xor     edx, edx; dwFlags
0x1800e7d25  call    WINRT_IMPL_HeapFree
0x1800e7d2a  nop
0x1800e7d2b  mov     rax, [rsp+1A0h+var_160]
0x1800e7d30  movsxd  rcx, dword ptr [rax+4]
0x1800e7d34  mov     [rsp+rcx+1A0h+var_160], r13
0x1800e7d39  mov     rax, [rsp+1A0h+var_160]
0x1800e7d3e  movsxd  rcx, dword ptr [rax+4]
0x1800e7d42  lea     edx, [rcx-0A8h]
0x1800e7d48  mov     [rsp+rcx+1A0h+var_164], edx
0x1800e7d4c  lea     rcx, [rsp+1A0h+var_158]
0x1800e7d51  call    ??1?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wfilebuf::~wfilebuf<wchar_t,std::char_traits<wchar_t>>(void)
0x1800e7d56  lea     rcx, [rsp+1A0h+var_150]
0x1800e7d5b  call    cs:__imp_??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wostream::~wostream<wchar_t,std::char_traits<wchar_t>>(void)
0x1800e7d61  lea     rcx, [rbp+0A0h+var_B8]
0x1800e7d65  call    cs:__imp_??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(void)
0x1800e7d6b  nop
0x1800e7d6c  lea     rcx, [rbp+0A0h+var_48]; void *
0x1800e7d70  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e7d75  mov     rcx, [rbp+0A0h+var_28]
0x1800e7d79  xor     rcx, rsp; StackCookie
0x1800e7d7c  call    __security_check_cookie
0x1800e7d81  add     rsp, 188h
0x1800e7d88  pop     r13
0x1800e7d8a  pop     rdi
0x1800e7d8b  pop     rbx
0x1800e7d8c  pop     rbp
0x1800e7d8d  retn
0x1800e7d8e  test    eax, eax
0x1800e7d90  jns     short loc_1800E7D2B
0x1800e7d92  call    cs:__imp_abort
```
