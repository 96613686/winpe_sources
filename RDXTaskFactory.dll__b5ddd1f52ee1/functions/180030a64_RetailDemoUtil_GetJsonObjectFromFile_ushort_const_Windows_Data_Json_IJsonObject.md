# RetailDemoUtil::GetJsonObjectFromFile(ushort const *,Windows::Data::Json::IJsonObject * *)

- ea: `0x180030a64`
- end: `0x180030db7`
- name: `?GetJsonObjectFromFile@RetailDemoUtil@@YAXPEBGPEAPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `851`
- prototype: `void __fastcall(RetailDemoUtil *__hidden this, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800412d0`
- `0x180045468`

## callees

- `0x180003390`
- `0x18000e330`
- `0x18001094c`
- `0x18001bf68`
- `0x180026824`
- `0x18002f628`
- `0x18002f6a4`
- `0x180030a64`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030b69`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030bae`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030b69`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030bae`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180030ab6`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180030ab6`
- `SHCORE!IStream_Size` at `0x180030ad4`
- `SHCORE!IStream_Size` at `0x180030ad4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030c1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c9a`

## string_xrefs

- `0x180030bfa`: `Windows.Data.Json.JsonObject`
- `0x180030cd5`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030cea`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030cff`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d17`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d2c`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d44`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d5c`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d78`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030d90`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030da5`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RetailDemoUtil::GetJsonObjectFromFile(
        const WCHAR *this,
        const unsigned __int16 *a2,
        struct Windows::Data::Json::IJsonObject **a3)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // r8
  const char *v9; // r9
  int v10; // ebx
  int v11; // r9d
  const WCHAR *v12; // r15
  unsigned int v13; // esi
  int ActivationFactory; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, const unsigned __int16 *); // rbx
  unsigned int v17; // eax
  int v18; // eax
  LPWSTR v19; // rcx
  CHAR *v20; // rcx
  int pstmTemplate; // [rsp+20h] [rbp-39h]
  int pstmTemplatea; // [rsp+20h] [rbp-39h]
  int pstmTemplateb; // [rsp+20h] [rbp-39h]
  int cbMultiByte; // [rsp+30h] [rbp-29h] BYREF
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp-21h] BYREF
  ULARGE_INTEGER pui; // [rsp+40h] [rbp-19h] BYREF
  LPWSTR lpWideCharStr; // [rsp+48h] [rbp-11h] BYREF
  IStream *pstm; // [rsp+50h] [rbp-9h] BYREF
  __int64 v29; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v31; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(_QWORD *)a2 = 0;
  pstm = 0;
  v4 = SHCreateStreamOnFileEx(this, 0, 0x80u, 0, 0, &pstm);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v4,
      pstmTemplate);
  pui.QuadPart = 0;
  v5 = IStream_Size(pstm, &pui);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v5,
      pstmTemplate);
  wil::make_unique_cotaskmem<unsigned char [0]>(&lpMultiByteStr, pui.LowPart + 2LL);
  if ( !lpMultiByteStr )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x8007000ELL,
      pstmTemplate);
  cbMultiByte = 0;
  v6 = (*(__int64 (__fastcall **)(IStream *, LPCCH, _QWORD, int *))(*(_QWORD *)pstm + 24LL))(
         pstm,
         lpMultiByteStr,
         pui.LowPart,
         &cbMultiByte);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v6,
      pstmTemplate);
  lpMultiByteStr[pui.LowPart] = 0;
  if ( pui.LowPart != cbMultiByte )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x319,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x8000FFFFLL,
      pstmTemplate);
  v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  v10 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x8000FFFFLL,
      pstmTemplatea);
  wil::make_unique_cotaskmem<unsigned short [0]>(&lpWideCharStr, v7 + 1LL, v8, v9);
  if ( !lpWideCharStr )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x8007000ELL,
      pstmTemplatea);
  v11 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, v10);
  lpWideCharStr[v11] = 0;
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)0x8000FFFFLL,
      pstmTemplateb);
  v12 = lpWideCharStr + 1;
  if ( *lpWideCharStr != 0xFEFF )
    v12 = lpWideCharStr;
  v13 = v11 - 1;
  if ( *lpWideCharStr != 0xFEFF )
    v13 = v11;
  v29 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v31, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v29);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)ActivationFactory,
      pstmTemplateb);
  v15 = v29;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v29 + 48LL);
  v31 = 0;
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v13);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v12, v17, v13);
  v18 = v16(v15, v31, a2);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v18,
      pstmTemplateb);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v29);
  v19 = lpWideCharStr;
  lpWideCharStr = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  v20 = (CHAR *)lpMultiByteStr;
  lpMultiByteStr = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&pstm);
}

```

## disassembly

```asm
0x180030a64  mov     [rsp-8+arg_10], rbx
0x180030a69  mov     [rsp-8+arg_18], rsi
0x180030a6e  push    rbp
0x180030a6f  push    rdi
0x180030a70  push    r12
0x180030a72  push    r14
0x180030a74  push    r15
0x180030a76  lea     rbp, [rsp-37h]
0x180030a7b  sub     rsp, 90h
0x180030a82  mov     rax, cs:__security_cookie
0x180030a89  xor     rax, rsp
0x180030a8c  mov     [rbp+57h+var_30], rax
0x180030a90  mov     r14, rdx
0x180030a93  xor     r12d, r12d
0x180030a96  mov     [rdx], r12
0x180030a99  mov     [rbp+57h+pstm], r12
0x180030a9d  lea     rax, [rbp+57h+pstm]
0x180030aa1  mov     [rsp+0B0h+ppstm], rax; ppstm
0x180030aa6  mov     [rsp+0B0h+pstmTemplate], r12; int
0x180030aab  xor     r9d, r9d; fCreate
0x180030aae  xor     edx, edx; grfMode
0x180030ab0  mov     r8d, 80h; dwAttributes
0x180030ab6  call    cs:__imp_SHCreateStreamOnFileEx
0x180030abc  mov     rcx, [rbp+5Fh]; this
0x180030ac0  test    eax, eax
0x180030ac2  js      loc_180030CE7
0x180030ac8  mov     qword ptr [rbp+57h+pui], r12
0x180030acc  lea     rdx, [rbp+57h+pui]; pui
0x180030ad0  mov     rcx, [rbp+57h+pstm]; pstm
0x180030ad4  call    cs:__imp_IStream_Size
0x180030ada  mov     rcx, [rbp+5Fh]; this
0x180030ade  test    eax, eax
0x180030ae0  js      loc_180030CFC
0x180030ae6  mov     edx, dword ptr [rbp+57h+pui]
0x180030ae9  add     rdx, 2
0x180030aed  lea     rcx, [rbp+57h+lpMultiByteStr]
0x180030af1  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180030af6  nop
0x180030af7  mov     rcx, [rbp+5Fh]; this
0x180030afb  mov     rdx, [rbp+57h+lpMultiByteStr]
0x180030aff  test    rdx, rdx
0x180030b02  jz      loc_180030D11
0x180030b08  mov     [rbp+57h+cbMultiByte], r12d
0x180030b0c  mov     rcx, [rbp+57h+pstm]
0x180030b10  mov     rax, [rcx]
0x180030b13  lea     r9, [rbp+57h+cbMultiByte]
0x180030b17  mov     r8d, dword ptr [rbp+57h+pui]
0x180030b1b  mov     rax, [rax+18h]
0x180030b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b24  mov     rcx, [rbp+5Fh]; this
0x180030b28  test    eax, eax
0x180030b2a  js      loc_180030D29
0x180030b30  mov     ecx, dword ptr [rbp+57h+pui]
0x180030b33  mov     rax, [rbp+57h+lpMultiByteStr]
0x180030b37  mov     [rcx+rax], r12b
0x180030b3b  mov     r9d, [rbp+57h+cbMultiByte]; cbMultiByte
0x180030b3f  cmp     dword ptr [rbp+57h+pui], r9d
0x180030b43  setz    al
0x180030b46  mov     rcx, [rbp+5Fh]; this
0x180030b4a  test    al, al
0x180030b4c  jz      loc_180030D3E
0x180030b52  mov     dword ptr [rsp+0B0h+ppstm], r12d; cchWideChar
0x180030b57  mov     [rsp+0B0h+pstmTemplate], r12; int
0x180030b5c  mov     r8, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x180030b60  xor     edx, edx; dwFlags
0x180030b62  mov     edi, 0FDE9h
0x180030b67  mov     ecx, edi; CodePage
0x180030b69  call    cs:__imp_MultiByteToWideChar
0x180030b6f  movsxd  rbx, eax
0x180030b72  mov     rcx, [rbp+5Fh]; this
0x180030b76  test    eax, eax
0x180030b78  jz      loc_180030D56
0x180030b7e  lea     rdx, [rbx+1]
0x180030b82  lea     rcx, [rbp+57h+lpWideCharStr]
0x180030b86  call    ??$make_unique_cotaskmem@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<ushort [0]>(unsigned __int64)
0x180030b8b  nop
0x180030b8c  mov     rax, [rbp+57h+lpWideCharStr]
0x180030b90  test    rax, rax
0x180030b93  jz      loc_180030D6E
0x180030b99  mov     dword ptr [rsp+0B0h+ppstm], ebx; cchWideChar
0x180030b9d  mov     [rsp+0B0h+pstmTemplate], rax; int
0x180030ba2  mov     r9d, [rbp+57h+cbMultiByte]; cbMultiByte
0x180030ba6  mov     r8, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x180030baa  xor     edx, edx; dwFlags
0x180030bac  mov     ecx, edi; CodePage
0x180030bae  call    cs:__imp_MultiByteToWideChar
0x180030bb4  movsxd  r9, eax
0x180030bb7  mov     rcx, [rbp+57h+lpWideCharStr]
0x180030bbb  mov     [rcx+r9*2], r12w
0x180030bc0  mov     rcx, [rbp+5Fh]; this
0x180030bc4  test    eax, eax
0x180030bc6  jz      loc_180030D8A
0x180030bcc  mov     rax, [rbp+57h+lpWideCharStr]
0x180030bd0  mov     ecx, 0FEFFh
0x180030bd5  lea     r15, [rax+2]
0x180030bd9  cmp     [rax], cx
0x180030bdc  cmovnz  r15, rax
0x180030be0  lea     esi, [r9-1]
0x180030be4  cmovnz  esi, r9d
0x180030be8  mov     [rbp+57h+var_58], r12
0x180030bec  mov     [rbp+57h+var_38], r12
0x180030bf0  lea     r9d, [r12+1Ch]; unsigned int
0x180030bf5  lea     r8d, [r12+1Dh]; unsigned int
0x180030bfa  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180030c01  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180030c05  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030c0a  nop
0x180030c0b  lea     r8, [rbp+57h+var_58]
0x180030c0f  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180030c16  mov     rcx, [rbp+57h+var_38]
0x180030c1a  call    cs:__imp_RoGetActivationFactory
0x180030c20  mov     rcx, [rbp+5Fh]; this
0x180030c24  test    eax, eax
0x180030c26  js      loc_180030DA2
0x180030c2c  mov     rdi, [rbp+57h+var_58]
0x180030c30  mov     rax, [rdi]
0x180030c33  mov     rbx, [rax+30h]
0x180030c37  mov     [rbp+57h+var_38], r12
0x180030c3b  mov     ecx, esi; unsigned int
0x180030c3d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180030c42  mov     r9d, esi; unsigned int
0x180030c45  mov     r8d, eax; unsigned int
0x180030c48  mov     rdx, r15; sourceString
0x180030c4b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180030c4f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030c54  nop
0x180030c55  mov     r8, r14
0x180030c58  mov     rdx, [rbp+57h+var_38]
0x180030c5c  mov     rcx, rdi
0x180030c5f  mov     rax, rbx
0x180030c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c67  mov     rcx, [rbp+5Fh]; this
0x180030c6b  test    eax, eax
0x180030c6d  js      short loc_180030CD2
0x180030c6f  lea     rcx, [rbp+57h+var_58]
0x180030c73  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030c78  nop
0x180030c79  mov     rcx, [rbp+57h+lpWideCharStr]; pv
0x180030c7d  mov     [rbp+57h+lpWideCharStr], r12
0x180030c81  test    rcx, rcx
0x180030c84  jz      short loc_180030C8D
0x180030c86  call    cs:__imp_CoTaskMemFree
0x180030c8c  nop
0x180030c8d  mov     rcx, [rbp+57h+lpMultiByteStr]; pv
0x180030c91  mov     [rbp+57h+lpMultiByteStr], r12
0x180030c95  test    rcx, rcx
0x180030c98  jz      short loc_180030CA1
0x180030c9a  call    cs:__imp_CoTaskMemFree
0x180030ca0  nop
0x180030ca1  lea     rcx, [rbp+57h+pstm]
0x180030ca5  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030caa  mov     rcx, [rbp+57h+var_30]
0x180030cae  xor     rcx, rsp; StackCookie
0x180030cb1  call    __security_check_cookie
0x180030cb6  lea     r11, [rsp+0B0h+var_20]
0x180030cbe  mov     rbx, [r11+40h]
0x180030cc2  mov     rsi, [r11+48h]
0x180030cc6  mov     rsp, r11
0x180030cc9  pop     r15
0x180030ccb  pop     r14
0x180030ccd  pop     r12
0x180030ccf  pop     rdi
0x180030cd0  pop     rbp
0x180030cd1  retn
0x180030cd2  mov     r9d, eax; char *
0x180030cd5  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030cdc  mov     edx, 32Fh; void *
0x180030ce1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030ce7  mov     r9d, eax; char *
0x180030cea  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030cf1  mov     edx, 311h; void *
0x180030cf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030cfc  mov     r9d, eax; char *
0x180030cff  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d06  mov     edx, 313h; void *
0x180030d0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d11  mov     r9d, 8007000Eh; char *
0x180030d17  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d1e  mov     edx, 315h; void *
0x180030d23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d29  mov     r9d, eax; char *
0x180030d2c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d33  mov     edx, 317h; void *
0x180030d38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d3e  mov     r9d, 8000FFFFh; char *
0x180030d44  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d4b  mov     edx, 319h; void *
0x180030d50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d56  mov     r9d, 8000FFFFh; char *
0x180030d5c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d63  mov     edx, 31Dh; void *
0x180030d68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d6e  mov     rcx, [rbp+5Fh]; this
0x180030d72  mov     r9d, 8007000Eh; char *
0x180030d78  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d7f  mov     edx, 31Fh; void *
0x180030d84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030d8a  mov     r9d, 8000FFFFh; char *
0x180030d90  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030d97  mov     edx, 323h; void *
0x180030d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030da2  mov     r9d, eax; char *
0x180030da5  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030dac  mov     edx, 32Eh; void *
0x180030db1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
