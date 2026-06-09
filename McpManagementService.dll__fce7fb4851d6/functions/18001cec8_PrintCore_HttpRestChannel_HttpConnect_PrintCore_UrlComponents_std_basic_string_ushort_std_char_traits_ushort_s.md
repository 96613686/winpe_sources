# PrintCore::HttpRestChannel::_HttpConnect(PrintCore::UrlComponents,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,PrintCore::HttpContext &)

- ea: `0x18001cec8`
- end: `0x18001d22e`
- name: `?_HttpConnect@HttpRestChannel@PrintCore@@AEAAXUUrlComponents@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUHttpContext@2@@Z`
- size: `870`
- prototype: `void __fastcall(__int64, PrintCore::UrlComponents *, __int64, HINTERNET **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d7dc`

## callees

- `0x180003a60`
- `0x18000e164`
- `0x18000e208`
- `0x18000e248`
- `0x180011c58`
- `0x180011e58`
- `0x180012040`
- `0x180012aa8`
- `0x180012c30`
- `0x18001b9ec`
- `0x18001c378`
- `0x18001c770`
- `0x18001c9a8`
- `0x18001cec8`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x18001cff7`
- `WINHTTP!WinHttpOpenRequest` at `0x18001cff7`
- `WINHTTP!WinHttpSetOption` at `0x18001d09d`
- `WINHTTP!WinHttpSetOption` at `0x18001d0ee`
- `WINHTTP!WinHttpSetOption` at `0x18001d09d`
- `WINHTTP!WinHttpSetOption` at `0x18001d0ee`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001d04d`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001d04d`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001d19e`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001d19e`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001d136`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001d136`
- `WINHTTP!WinHttpConnect` at `0x18001cf22`
- `WINHTTP!WinHttpConnect` at `0x18001cf22`

## string_xrefs

- `0x18001d0fd`: `Error while setting the request security flags`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintCore::HttpRestChannel::_HttpConnect(
        __int64 a1,
        PrintCore::UrlComponents *a2,
        __int64 a3,
        HINTERNET **a4)
{
  const WCHAR *v8; // rax
  HINTERNET **v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rax
  char v12; // r14
  const WCHAR *v13; // rax
  DWORD dwFlags; // edx
  LPCWSTR v15; // r10
  __int64 v16; // rax
  HINTERNET **v17; // rsi
  BOOL v18; // eax
  BOOL v19; // eax
  BOOL v20; // eax
  void (__stdcall *v21)(HINTERNET, DWORD_PTR, DWORD, LPVOID, DWORD); // rdx
  WINHTTP_STATUS_CALLBACK v22; // rax
  __int64 v23; // rax
  const WCHAR *v24; // rax
  bool v25; // al
  __int64 v26; // rax
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  LPCWSTR *ppwszAcceptTypesb; // [rsp+28h] [rbp-D8h]
  LPCWSTR *ppwszAcceptTypesa; // [rsp+28h] [rbp-D8h]
  HINTERNET v30; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  HINTERNET v32; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v33; // [rsp+58h] [rbp-A8h]
  _BYTE v34[88]; // [rsp+60h] [rbp-A0h] BYREF
  PrintCore::UrlComponents *v35; // [rsp+B8h] [rbp-48h]
  _BYTE v36[8]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v37; // [rsp+C8h] [rbp-38h]
  _BYTE v38[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v35 = a2;
  LODWORD(v30) = 0;
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32);
  v30 = WinHttpConnect(**v9, v8, *(_WORD *)(v10 + 128), 0);
  v11 = std::make_shared<PrintCore::HInternetRAII,void *>(&v32, &v30);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
    a4 + 2,
    v11);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *((_QWORD *)a2 + 10)) < *((_QWORD *)a2 + 14) )
    std::_Xlen_string();
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 64);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 96);
  std::wstring::wstring(v38);
  v12 = 2;
  LODWORD(v30) = 2;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  v32 = WinHttpOpenRequest(*a4[2], v15, v13, 0, 0, 0, dwFlags);
  v16 = std::make_shared<PrintCore::HInternetRAII,void *>(v36, &v32);
  v17 = a4 + 4;
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
    a4 + 4,
    v16);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  v18 = WinHttpSetTimeouts(**v17, 0, *(_DWORD *)(a1 + 176), *(_DWORD *)(a1 + 180), *(_DWORD *)(a1 + 184));
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x152,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
    (const char *)!v18,
    (bool)"Error while setting WinHttp timeouts",
    (const char *)ppwszAcceptTypes);
  Buffer = 8;
  v19 = WinHttpSetOption(**v17, 0x3Fu, &Buffer, 4u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x158,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
    (const char *)!v19,
    (bool)"Error disabling keep alive",
    (const char *)ppwszAcceptTypesb);
  if ( *(_BYTE *)(a1 + 168) && *(_DWORD *)(a1 + 172) )
  {
    v20 = WinHttpSetOption(**v17, 0x1Fu, (LPVOID)(a1 + 172), 4u);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
      (const char *)!v20,
      (bool)"Error while setting the request security flags",
      (const char *)ppwszAcceptTypesa);
  }
  v21 = *(void (__stdcall **)(HINTERNET, DWORD_PTR, DWORD, LPVOID, DWORD))(a1 + 192);
  if ( v21 != (void (__stdcall *)(HINTERNET, DWORD_PTR, DWORD, LPVOID, DWORD))-1LL )
  {
    v22 = WinHttpSetStatusCallback(**v17, v21, 0x10000u, 0);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
      (const char *)((WINHTTP_STATUS_CALLBACK)((char *)v22 + 1) == 0),
      (bool)"Error while setting the secure failure callback",
      (const char *)ppwszAcceptTypesa);
  }
  v25 = 0;
  if ( *(_QWORD *)(a1 + 56) )
  {
    v23 = PrintCore::HttpRestChannel::_ConstructContentTypeHeader(a1, v36);
    v12 = 3;
    LODWORD(v30) = 3;
    v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    if ( !WinHttpAddRequestHeaders(**v17, v24, 0xFFFFFFFF, 0x20000000u) )
      v25 = 1;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x16B,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
    (const char *)v25,
    (bool)"Error adding Content-Type header",
    (const char *)ppwszAcceptTypesa);
  if ( (v12 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v36);
  v26 = PrintCore::HttpContext::HttpContext((PrintCore::HttpContext *)v34, (const struct PrintCore::HttpContext *)a4);
  PrintCore::HttpRestChannel::_AddAdditionalHeaders(a1, v26);
  std::wstring::_Tidy_deallocate(v38);
  PrintCore::UrlComponents::~UrlComponents(a2);
}

```

## disassembly

```asm
0x18001cec8  push    rbp
0x18001ceca  push    rbx
0x18001cecb  push    rsi
0x18001cecc  push    rdi
0x18001cecd  push    r12
0x18001cecf  push    r14
0x18001ced1  push    r15
0x18001ced3  lea     rbp, [rsp-10h]
0x18001ced8  sub     rsp, 110h
0x18001cedf  mov     rax, cs:__security_cookie
0x18001cee6  xor     rax, rsp
0x18001cee9  mov     [rbp+40h+var_40], rax
0x18001ceed  mov     r15, r9
0x18001cef0  mov     r12, r8
0x18001cef3  mov     rdi, rdx
0x18001cef6  mov     rbx, rcx
0x18001cef9  mov     [rbp+40h+var_88], rdx
0x18001cefd  mov     dword ptr [rsp+140h+var_100], 0
0x18001cf05  lea     rcx, [rdx+20h]
0x18001cf09  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cf0e  mov     rcx, [r9]
0x18001cf11  xor     r9d, r9d; dwReserved
0x18001cf14  movzx   r8d, word ptr [rdx+80h]; nServerPort
0x18001cf1c  mov     rdx, rax; pswzServerName
0x18001cf1f  mov     rcx, [rcx]; hSession
0x18001cf22  call    cs:__imp_WinHttpConnect
0x18001cf28  mov     [rsp+140h+var_100], rax
0x18001cf2d  lea     rdx, [rsp+140h+var_100]
0x18001cf32  lea     rcx, [rsp+140h+var_F0]
0x18001cf37  call    ??$make_shared@VHInternetRAII@PrintCore@@PEAX@std@@YA?AV?$shared_ptr@VHInternetRAII@PrintCore@@@0@$$QEAPEAX@Z; std::make_shared<PrintCore::HInternetRAII,void *>(void * &&)
0x18001cf3c  mov     rdx, rax
0x18001cf3f  lea     rcx, [r15+10h]
0x18001cf43  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18001cf48  mov     rcx, [rsp+140h+var_E8]; this
0x18001cf4d  test    rcx, rcx
0x18001cf50  jz      short loc_18001CF57
0x18001cf52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cf57  lea     rcx, [rdi+40h]
0x18001cf5b  mov     r8, [rcx+10h]
0x18001cf5f  mov     r10, [rdi+70h]
0x18001cf63  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001cf6d  sub     rax, r8
0x18001cf70  cmp     rax, r10
0x18001cf73  jb      loc_18001D228
0x18001cf79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cf7e  mov     r9, rax
0x18001cf81  lea     rcx, [rdi+60h]
0x18001cf85  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cf8a  mov     qword ptr [rsp+140h+dwFlags], r10
0x18001cf8f  mov     [rsp+140h+ppwszAcceptTypes], rax
0x18001cf94  mov     [rsp+140h+pwszReferrer], r8
0x18001cf99  lea     rcx, [rbp+40h+var_60]
0x18001cf9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cfa2  mov     r14d, 2
0x18001cfa8  mov     dword ptr [rsp+140h+var_100], r14d
0x18001cfad  mov     rcx, r12
0x18001cfb0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cfb5  mov     r10, rax
0x18001cfb8  mov     cl, [rbx+0A8h]
0x18001cfbe  neg     cl
0x18001cfc0  sbb     edx, edx
0x18001cfc2  and     edx, 800000h
0x18001cfc8  lea     rcx, [rbp+40h+var_60]
0x18001cfcc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cfd1  mov     r8, rax; pwszObjectName
0x18001cfd4  mov     rcx, [r15+10h]
0x18001cfd8  mov     [rsp+140h+dwFlags], edx; dwFlags
0x18001cfdc  mov     [rsp+140h+ppwszAcceptTypes], 0; char *
0x18001cfe5  mov     [rsp+140h+pwszReferrer], 0; pwszReferrer
0x18001cfee  xor     r9d, r9d; pwszVersion
0x18001cff1  mov     rdx, r10; pwszVerb
0x18001cff4  mov     rcx, [rcx]; hConnect
0x18001cff7  call    cs:__imp_WinHttpOpenRequest
0x18001cffd  mov     [rsp+140h+var_F0], rax
0x18001d002  lea     rdx, [rsp+140h+var_F0]
0x18001d007  lea     rcx, [rbp+40h+var_80]
0x18001d00b  call    ??$make_shared@VHInternetRAII@PrintCore@@PEAX@std@@YA?AV?$shared_ptr@VHInternetRAII@PrintCore@@@0@$$QEAPEAX@Z; std::make_shared<PrintCore::HInternetRAII,void *>(void * &&)
0x18001d010  lea     rsi, [r15+20h]
0x18001d014  mov     rdx, rax
0x18001d017  mov     rcx, rsi
0x18001d01a  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18001d01f  mov     rcx, [rbp+40h+var_78]; this
0x18001d023  test    rcx, rcx
0x18001d026  jz      short loc_18001D02D
0x18001d028  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001d02d  mov     rcx, [rsi]
0x18001d030  mov     eax, [rbx+0B8h]
0x18001d036  mov     dword ptr [rsp+140h+pwszReferrer], eax; nReceiveTimeout
0x18001d03a  mov     r9d, [rbx+0B4h]; nSendTimeout
0x18001d041  mov     r8d, [rbx+0B0h]; nConnectTimeout
0x18001d048  xor     edx, edx; nResolveTimeout
0x18001d04a  mov     rcx, [rcx]; hInternet
0x18001d04d  call    cs:__imp_WinHttpSetTimeouts
0x18001d053  test    eax, eax
0x18001d055  setz    al
0x18001d058  mov     rcx, [rbp+48h]; this
0x18001d05c  lea     rdx, aErrorWhileSett; "Error while setting WinHttp timeouts"
0x18001d063  mov     [rsp+140h+pwszReferrer], rdx; bool
0x18001d068  movzx   r9d, al; char *
0x18001d06c  lea     r12, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\H"...
0x18001d073  mov     r8, r12; unsigned int
0x18001d076  mov     edx, 152h; void *
0x18001d07b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001d080  mov     [rsp+140h+Buffer], 8
0x18001d088  mov     rcx, [rsi]
0x18001d08b  mov     r9d, 4; dwBufferLength
0x18001d091  lea     r8, [rsp+140h+Buffer]; lpBuffer
0x18001d096  lea     edx, [r9+3Bh]; dwOption
0x18001d09a  mov     rcx, [rcx]; hInternet
0x18001d09d  call    cs:__imp_WinHttpSetOption
0x18001d0a3  test    eax, eax
0x18001d0a5  setz    al
0x18001d0a8  mov     rcx, [rbp+48h]; this
0x18001d0ac  lea     rdx, aErrorDisabling; "Error disabling keep alive"
0x18001d0b3  mov     [rsp+140h+pwszReferrer], rdx; bool
0x18001d0b8  movzx   r9d, al; char *
0x18001d0bc  mov     r8, r12; unsigned int
0x18001d0bf  mov     edx, 158h; void *
0x18001d0c4  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001d0c9  cmp     byte ptr [rbx+0A8h], 0
0x18001d0d0  jz      short loc_18001D11A
0x18001d0d2  lea     r8, [rbx+0ACh]; lpBuffer
0x18001d0d9  cmp     dword ptr [r8], 0
0x18001d0dd  jz      short loc_18001D11A
0x18001d0df  mov     rcx, [rsi]
0x18001d0e2  mov     edx, 1Fh; dwOption
0x18001d0e7  lea     r9d, [rdx-1Bh]; dwBufferLength
0x18001d0eb  mov     rcx, [rcx]; hInternet
0x18001d0ee  call    cs:__imp_WinHttpSetOption
0x18001d0f4  test    eax, eax
0x18001d0f6  setz    al
0x18001d0f9  mov     rcx, [rbp+48h]; this
0x18001d0fd  lea     rdx, aErrorWhileSett_0; "Error while setting the request securit"...
0x18001d104  mov     [rsp+140h+pwszReferrer], rdx; bool
0x18001d109  movzx   r9d, al; char *
0x18001d10d  mov     r8, r12; unsigned int
0x18001d110  mov     edx, 161h; void *
0x18001d115  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001d11a  mov     rdx, [rbx+0C0h]; lpfnInternetCallback
0x18001d121  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001d125  jz      short loc_18001D164
0x18001d127  mov     rcx, [rsi]
0x18001d12a  xor     r9d, r9d; dwReserved
0x18001d12d  mov     r8d, 10000h; dwNotificationFlags
0x18001d133  mov     rcx, [rcx]; hInternet
0x18001d136  call    cs:__imp_WinHttpSetStatusCallback
0x18001d13c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d140  setz    al
0x18001d143  mov     rcx, [rbp+48h]; this
0x18001d147  lea     rdx, aErrorWhileSett_1; "Error while setting the secure failure "...
0x18001d14e  mov     [rsp+140h+pwszReferrer], rdx; bool
0x18001d153  movzx   r9d, al; char *
0x18001d157  mov     r8, r12; unsigned int
0x18001d15a  mov     edx, 167h; void *
0x18001d15f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001d164  cmp     qword ptr [rbx+38h], 0
0x18001d169  jz      short loc_18001D1AC
0x18001d16b  lea     rdx, [rbp+40h+var_80]
0x18001d16f  mov     rcx, rbx
0x18001d172  call    ?_ConstructContentTypeHeader@HttpRestChannel@PrintCore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; PrintCore::HttpRestChannel::_ConstructContentTypeHeader(void)
0x18001d177  nop
0x18001d178  mov     r14d, 3
0x18001d17e  mov     dword ptr [rsp+140h+var_100], r14d
0x18001d183  mov     rcx, rax
0x18001d186  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d18b  mov     rcx, [rsi]
0x18001d18e  mov     r9d, 20000000h; dwModifiers
0x18001d194  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x18001d198  mov     rdx, rax; lpszHeaders
0x18001d19b  mov     rcx, [rcx]; hRequest
0x18001d19e  call    cs:__imp_WinHttpAddRequestHeaders
0x18001d1a4  test    eax, eax
0x18001d1a6  jnz     short loc_18001D1AC
0x18001d1a8  mov     al, 1
0x18001d1aa  jmp     short loc_18001D1AE
0x18001d1ac  xor     eax, eax
0x18001d1ae  mov     rcx, [rbp+48h]; this
0x18001d1b2  lea     rdx, aErrorAddingCon; "Error adding Content-Type header"
0x18001d1b9  mov     [rsp+140h+pwszReferrer], rdx; bool
0x18001d1be  movzx   r9d, al; char *
0x18001d1c2  mov     r8, r12; unsigned int
0x18001d1c5  mov     edx, 16Bh; void *
0x18001d1ca  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001d1cf  nop
0x18001d1d0  test    r14b, 1
0x18001d1d4  jz      short loc_18001D1DF
0x18001d1d6  lea     rcx, [rbp+40h+var_80]
0x18001d1da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d1df  mov     rdx, r15; struct PrintCore::HttpContext *
0x18001d1e2  lea     rcx, [rsp+140h+var_E0]; this
0x18001d1e7  call    ??0HttpContext@PrintCore@@QEAA@AEBU01@@Z; PrintCore::HttpContext::HttpContext(PrintCore::HttpContext const &)
0x18001d1ec  mov     rdx, rax
0x18001d1ef  mov     rcx, rbx
0x18001d1f2  call    ?_AddAdditionalHeaders@HttpRestChannel@PrintCore@@AEAAXUHttpContext@2@@Z; PrintCore::HttpRestChannel::_AddAdditionalHeaders(PrintCore::HttpContext)
0x18001d1f7  nop
0x18001d1f8  lea     rcx, [rbp+40h+var_60]
0x18001d1fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d201  nop
0x18001d202  mov     rcx, rdi; this
0x18001d205  call    ??1UrlComponents@PrintCore@@QEAA@XZ; PrintCore::UrlComponents::~UrlComponents(void)
0x18001d20a  mov     rcx, [rbp+40h+var_40]
0x18001d20e  xor     rcx, rsp; StackCookie
0x18001d211  call    __security_check_cookie
0x18001d216  add     rsp, 110h
0x18001d21d  pop     r15
0x18001d21f  pop     r14
0x18001d221  pop     r12
0x18001d223  pop     rdi
0x18001d224  pop     rsi
0x18001d225  pop     rbx
0x18001d226  pop     rbp
0x18001d227  retn
0x18001d228  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
