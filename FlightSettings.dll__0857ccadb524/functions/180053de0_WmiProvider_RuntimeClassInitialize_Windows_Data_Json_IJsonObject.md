# WmiProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x180053de0`
- end: `0x1800541f3`
- name: `?RuntimeClassInitialize@WmiProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1043`
- prototype: `__int64 __fastcall(WmiProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800477b0`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180047c28`
- `0x1800539bc`
- `0x180053de0`
- `0x1800541fc`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053e67`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053f5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005408c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005410b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005418a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053e67`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053f5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005408c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005410b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005418a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800540a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005411f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005419e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800540a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005411f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005419e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005404f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005404f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053f91`

## string_xrefs

- `0x180053ee4`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053fd3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180054029`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WmiProvider::RuntimeClassInitialize(WmiProvider *this, struct Windows::Data::Json::IJsonObject *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 bstr_nothrow; // rax
  int (__fastcall *v14)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  unsigned __int64 v15; // rcx
  PCWSTR v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r12
  unsigned __int64 v21; // rcx
  int (__fastcall *v22)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  unsigned __int64 v23; // rcx
  bool v24; // sf
  int v25; // eax
  int (__fastcall *v26)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  int v27; // eax
  HSTRING v28; // [rsp+20h] [rbp-50h] BYREF
  UINT32 length; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *(double *)&v28 = 0.0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  *(double *)&v28 = 0.0;
  length = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( WmiProvider::s_pszJsonTagQuery[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(WmiProvider::s_pszJsonTagQuery, length, &hstringHeader, &string);
  v7 = v4(a2, string, &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 50;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
      (const char *)v9,
      (int)v28);
LABEL_10:
    WindowsDeleteString(v28);
    return v8;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v28, 0);
  bstr_nothrow = wil::make_bstr_nothrow(&length, StringRawBuffer);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 16,
    bstr_nothrow);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&length);
  if ( !*((_QWORD *)this + 2) )
  {
    v8 = -2147024882;
    v9 = 2147942414LL;
    v10 = 53;
    goto LABEL_9;
  }
  WindowsDeleteString(v28);
  *(double *)&v28 = 0.0;
  v14 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  *(double *)&v28 = 0.0;
  length = 0;
  v15 = -1;
  do
    ++v15;
  while ( WmiProvider::s_pszJsonTagNamespace[v15] );
  if ( (int)ULongLongToUInt(v15, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(WmiProvider::s_pszJsonTagNamespace, length, &hstringHeader, &string);
  if ( v14(a2, string, &v28) < 0 )
    v16 = L"ROOT\\CIMV2";
  else
    v16 = WindowsGetStringRawBuffer(v28, 0);
  v17 = wil::make_bstr_nothrow(&length, v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 24,
    v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&length);
  if ( !*((_QWORD *)this + 3) )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
      (const char *)0x8007000ELL,
      (int)v28);
    goto LABEL_10;
  }
  WindowsDeleteString(v28);
  v18 = wil::make_bstr_nothrow(&v28, L"WQL");
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 32,
    v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  if ( !*((_QWORD *)this + 4) )
  {
    v8 = -2147024882;
    v19 = 65;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
      (const char *)v8,
      (int)v28);
    return v8;
  }
  v20 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  length = 0;
  v21 = -1;
  do
    ++v21;
  while ( WmiProvider::s_pszJsonTagPropName[v21] );
  if ( (int)ULongLongToUInt(v21, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(WmiProvider::s_pszJsonTagPropName, length, &hstringHeader, &string);
  v8 = v20(a2, string, (char *)this + 40);
  if ( (v8 & 0x80000000) != 0 )
  {
    v19 = 68;
    goto LABEL_23;
  }
  *(double *)&v28 = 0.0;
  v22 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 88LL);
  length = 0;
  v23 = -1;
  do
    ++v23;
  while ( WmiProvider::s_pszJsonTagTimeout[v23] );
  if ( (int)ULongLongToUInt(v23, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(WmiProvider::s_pszJsonTagTimeout, length, &hstringHeader, &string);
  v24 = v22(a2, string, &v28) < 0;
  v25 = (int)*(double *)&v28;
  if ( v24 )
    v25 = 2000;
  *((_DWORD *)this + 12) = v25;
  *(double *)&v28 = 0.0;
  v26 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 88LL);
  length = 0;
  do
    ++v5;
  while ( WmiProvider::s_pszJsonTagVariantFlags[v5] );
  if ( (int)ULongLongToUInt(v5, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(WmiProvider::s_pszJsonTagVariantFlags, length, &hstringHeader, &string);
  v24 = v26(a2, string, &v28) < 0;
  v27 = (int)*(double *)&v28;
  if ( v24 )
    LOWORD(v27) = 0;
  *((_WORD *)this + 26) = v27;
  return 0;
}

```

## disassembly

```asm
0x180053de0  mov     [rsp-38h+arg_10], rbx
0x180053de5  push    rbp
0x180053de6  push    rsi
0x180053de7  push    rdi
0x180053de8  push    r12
0x180053dea  push    r13
0x180053dec  push    r14
0x180053dee  push    r15
0x180053df0  mov     rbp, rsp
0x180053df3  sub     rsp, 70h
0x180053df7  movaps  [rsp+70h+var_10], xmm6
0x180053dfc  mov     rax, cs:__security_cookie
0x180053e03  xor     rax, rsp
0x180053e06  mov     [rbp+var_20], rax
0x180053e0a  mov     rsi, rdx
0x180053e0d  mov     r14, rcx
0x180053e10  xor     r13d, r13d
0x180053e13  mov     [rbp+var_50], r13
0x180053e17  mov     rax, [rdx]
0x180053e1a  mov     r15, [rax+50h]
0x180053e1e  xor     ecx, ecx; string
0x180053e20  call    cs:__imp_WindowsDeleteString
0x180053e26  mov     [rbp+var_50], r13
0x180053e2a  mov     rbx, cs:?s_pszJsonTagQuery@WmiProvider@@0QEBGEB; ushort const * const WmiProvider::s_pszJsonTagQuery
0x180053e31  mov     [rbp+length], r13d
0x180053e35  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053e39  mov     rcx, rdi
0x180053e3c  inc     rcx; unsigned __int64
0x180053e3f  cmp     [rbx+rcx*2], r13w
0x180053e44  jnz     short loc_180053E3C
0x180053e46  lea     rdx, [rbp+length]; unsigned int *
0x180053e4a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180053e4f  mov     r12d, 1
0x180053e55  test    eax, eax
0x180053e57  jns     short loc_180053E6D
0x180053e59  xor     r9d, r9d; lpArguments
0x180053e5c  xor     r8d, r8d; nNumberOfArguments
0x180053e5f  mov     edx, r12d; dwExceptionFlags
0x180053e62  mov     ecx, 0C000000Dh; dwExceptionCode
0x180053e67  call    cs:__imp_RaiseException
0x180053e6d  lea     r9, [rbp+string]; string
0x180053e71  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053e75  mov     edx, [rbp+length]; length
0x180053e78  mov     rcx, rbx; sourceString
0x180053e7b  call    cs:__imp_WindowsCreateStringReference
0x180053e81  lea     r8, [rbp+var_50]
0x180053e85  mov     rdx, [rbp+string]
0x180053e89  mov     rcx, rsi
0x180053e8c  mov     rax, r15
0x180053e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e94  mov     ebx, eax
0x180053e96  test    eax, eax
0x180053e98  jns     short loc_180053EA4
0x180053e9a  mov     r9d, eax
0x180053e9d  mov     edx, 32h ; '2'
0x180053ea2  jmp     short loc_180053EE4
0x180053ea4  xor     edx, edx; length
0x180053ea6  mov     rcx, [rbp+var_50]; string
0x180053eaa  call    cs:__imp_WindowsGetStringRawBuffer
0x180053eb0  mov     rdx, rax
0x180053eb3  lea     rcx, [rbp+length]
0x180053eb7  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180053ebc  mov     rdx, rax
0x180053ebf  lea     rcx, [r14+10h]
0x180053ec3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180053ec8  lea     rcx, [rbp+length]
0x180053ecc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180053ed1  cmp     [r14+10h], r13
0x180053ed5  jnz     short loc_180053F06
0x180053ed7  mov     ebx, 8007000Eh
0x180053edc  mov     r9d, ebx; char *
0x180053edf  mov     edx, 35h ; '5'; void *
0x180053ee4  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053eeb  mov     rcx, [rbp+38h]; this
0x180053eef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053ef4  nop
0x180053ef5  mov     rcx, [rbp+var_50]; string
0x180053ef9  call    cs:__imp_WindowsDeleteString
0x180053eff  mov     eax, ebx
0x180053f01  jmp     loc_1800541CA
0x180053f06  mov     rcx, [rbp+var_50]; string
0x180053f0a  call    cs:__imp_WindowsDeleteString
0x180053f10  mov     [rbp+var_50], r13
0x180053f14  mov     rax, [rsi]
0x180053f17  mov     r15, [rax+50h]
0x180053f1b  xor     ecx, ecx; string
0x180053f1d  call    cs:__imp_WindowsDeleteString
0x180053f23  mov     [rbp+var_50], r13
0x180053f27  mov     rbx, cs:?s_pszJsonTagNamespace@WmiProvider@@0QEBGEB; ushort const * const WmiProvider::s_pszJsonTagNamespace
0x180053f2e  mov     [rbp+length], r13d
0x180053f32  mov     rcx, rdi
0x180053f35  inc     rcx; unsigned __int64
0x180053f38  cmp     [rbx+rcx*2], r13w
0x180053f3d  jnz     short loc_180053F35
0x180053f3f  lea     rdx, [rbp+length]; unsigned int *
0x180053f43  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180053f48  test    eax, eax
0x180053f4a  jns     short loc_180053F60
0x180053f4c  xor     r9d, r9d; lpArguments
0x180053f4f  xor     r8d, r8d; nNumberOfArguments
0x180053f52  mov     edx, r12d; dwExceptionFlags
0x180053f55  mov     ecx, 0C000000Dh; dwExceptionCode
0x180053f5a  call    cs:__imp_RaiseException
0x180053f60  lea     r9, [rbp+string]; string
0x180053f64  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053f68  mov     edx, [rbp+length]; length
0x180053f6b  mov     rcx, rbx; sourceString
0x180053f6e  call    cs:__imp_WindowsCreateStringReference
0x180053f74  lea     r8, [rbp+var_50]
0x180053f78  mov     rdx, [rbp+string]
0x180053f7c  mov     rcx, rsi
0x180053f7f  mov     rax, r15
0x180053f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f87  test    eax, eax
0x180053f89  js      short loc_180053F99
0x180053f8b  xor     edx, edx; length
0x180053f8d  mov     rcx, [rbp+var_50]; string
0x180053f91  call    cs:__imp_WindowsGetStringRawBuffer
0x180053f97  jmp     short loc_180053FA0
0x180053f99  lea     rax, aRootCimv2; "ROOT\\CIMV2"
0x180053fa0  mov     rdx, rax
0x180053fa3  lea     rcx, [rbp+length]
0x180053fa7  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180053fac  mov     rdx, rax
0x180053faf  lea     rcx, [r14+18h]
0x180053fb3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180053fb8  lea     rcx, [rbp+length]
0x180053fbc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180053fc1  cmp     [r14+18h], r13
0x180053fc5  jnz     short loc_180053FEA
0x180053fc7  mov     rcx, [rbp+38h]; this
0x180053fcb  mov     ebx, 8007000Eh
0x180053fd0  mov     r9d, ebx; char *
0x180053fd3  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053fda  mov     edx, 3Dh ; '='; void *
0x180053fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053fe4  nop
0x180053fe5  jmp     loc_180053EF5
0x180053fea  mov     rcx, [rbp+var_50]; string
0x180053fee  call    cs:__imp_WindowsDeleteString
0x180053ff4  lea     rdx, aWql; "WQL"
0x180053ffb  lea     rcx, [rbp+var_50]
0x180053fff  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180054004  mov     rdx, rax
0x180054007  lea     rcx, [r14+20h]
0x18005400b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180054010  lea     rcx, [rbp+var_50]
0x180054014  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180054019  cmp     [r14+20h], r13
0x18005401d  jnz     short loc_180054041
0x18005401f  mov     ebx, 8007000Eh
0x180054024  mov     edx, 41h ; 'A'; void *
0x180054029  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180054030  mov     r9d, ebx; char *
0x180054033  mov     rcx, [rbp+38h]; this
0x180054037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005403c  jmp     loc_180053EFF
0x180054041  mov     rax, [rsi]
0x180054044  mov     r12, [rax+50h]
0x180054048  lea     rbx, [r14+28h]
0x18005404c  mov     rcx, [rbx]; string
0x18005404f  call    cs:__imp_WindowsDeleteString
0x180054055  mov     [rbx], r13
0x180054058  mov     r15, cs:?s_pszJsonTagPropName@WmiProvider@@0QEBGEB; ushort const * const WmiProvider::s_pszJsonTagPropName
0x18005405f  mov     [rbp+length], r13d
0x180054063  mov     rcx, rdi
0x180054066  inc     rcx; unsigned __int64
0x180054069  cmp     [r15+rcx*2], r13w
0x18005406e  jnz     short loc_180054066
0x180054070  lea     rdx, [rbp+length]; unsigned int *
0x180054074  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180054079  test    eax, eax
0x18005407b  jns     short loc_180054092
0x18005407d  xor     r9d, r9d; lpArguments
0x180054080  xor     r8d, r8d; nNumberOfArguments
0x180054083  lea     edx, [r9+1]; dwExceptionFlags
0x180054087  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005408c  call    cs:__imp_RaiseException
0x180054092  lea     r9, [rbp+string]; string
0x180054096  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005409a  mov     edx, [rbp+length]; length
0x18005409d  mov     rcx, r15; sourceString
0x1800540a0  call    cs:__imp_WindowsCreateStringReference
0x1800540a6  mov     r8, rbx
0x1800540a9  mov     rdx, [rbp+string]
0x1800540ad  mov     rcx, rsi
0x1800540b0  mov     rax, r12
0x1800540b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540b8  mov     ebx, eax
0x1800540ba  test    eax, eax
0x1800540bc  jns     short loc_1800540C8
0x1800540be  mov     edx, 44h ; 'D'
0x1800540c3  jmp     loc_180054029
0x1800540c8  xorps   xmm6, xmm6
0x1800540cb  movsd   [rbp+var_50], xmm6
0x1800540d0  mov     rax, [rsi]
0x1800540d3  mov     r15, [rax+58h]
0x1800540d7  mov     rbx, cs:?s_pszJsonTagTimeout@WmiProvider@@0QEBGEB; ushort const * const WmiProvider::s_pszJsonTagTimeout
0x1800540de  mov     [rbp+length], r13d
0x1800540e2  mov     rcx, rdi
0x1800540e5  inc     rcx; unsigned __int64
0x1800540e8  cmp     [rbx+rcx*2], r13w
0x1800540ed  jnz     short loc_1800540E5
0x1800540ef  lea     rdx, [rbp+length]; unsigned int *
0x1800540f3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800540f8  test    eax, eax
0x1800540fa  jns     short loc_180054111
0x1800540fc  xor     r9d, r9d; lpArguments
0x1800540ff  xor     r8d, r8d; nNumberOfArguments
0x180054102  lea     edx, [r9+1]; dwExceptionFlags
0x180054106  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005410b  call    cs:__imp_RaiseException
0x180054111  lea     r9, [rbp+string]; string
0x180054115  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180054119  mov     edx, [rbp+length]; length
0x18005411c  mov     rcx, rbx; sourceString
0x18005411f  call    cs:__imp_WindowsCreateStringReference
0x180054125  lea     r8, [rbp+var_50]
0x180054129  mov     rdx, [rbp+string]
0x18005412d  mov     rcx, rsi
0x180054130  mov     rax, r15
0x180054133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054138  test    eax, eax
0x18005413a  cvttsd2si eax, [rbp+var_50]
0x18005413f  jns     short loc_180054146
0x180054141  mov     eax, 7D0h
0x180054146  mov     [r14+30h], eax
0x18005414a  movsd   [rbp+var_50], xmm6
0x18005414f  mov     rax, [rsi]
0x180054152  mov     r15, [rax+58h]
0x180054156  mov     rbx, cs:?s_pszJsonTagVariantFlags@WmiProvider@@0QEBGEB; ushort const * const WmiProvider::s_pszJsonTagVariantFlags
0x18005415d  mov     [rbp+length], r13d
0x180054161  inc     rdi
0x180054164  cmp     [rbx+rdi*2], r13w
0x180054169  jnz     short loc_180054161
0x18005416b  lea     rdx, [rbp+length]; unsigned int *
0x18005416f  mov     rcx, rdi; unsigned __int64
0x180054172  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180054177  test    eax, eax
0x180054179  jns     short loc_180054190
0x18005417b  xor     r9d, r9d; lpArguments
0x18005417e  xor     r8d, r8d; nNumberOfArguments
0x180054181  lea     edx, [r9+1]; dwExceptionFlags
0x180054185  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005418a  call    cs:__imp_RaiseException
0x180054190  lea     r9, [rbp+string]; string
0x180054194  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180054198  mov     edx, [rbp+length]; length
0x18005419b  mov     rcx, rbx; sourceString
0x18005419e  call    cs:__imp_WindowsCreateStringReference
0x1800541a4  lea     r8, [rbp+var_50]
0x1800541a8  mov     rdx, [rbp+string]
0x1800541ac  mov     rcx, rsi
0x1800541af  mov     rax, r15
0x1800541b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541b7  test    eax, eax
0x1800541b9  cvttsd2si eax, [rbp+var_50]
0x1800541be  jns     short loc_1800541C3
0x1800541c0  mov     eax, r13d
0x1800541c3  mov     [r14+34h], ax
0x1800541c8  xor     eax, eax
0x1800541ca  mov     rcx, [rbp+var_20]
0x1800541ce  xor     rcx, rsp; StackCookie
0x1800541d1  call    __security_check_cookie
0x1800541d6  mov     rbx, [rsp+70h+arg_10]
0x1800541de  movaps  xmm6, [rsp+70h+var_10]
0x1800541e3  add     rsp, 70h
0x1800541e7  pop     r15
0x1800541e9  pop     r14
0x1800541eb  pop     r13
0x1800541ed  pop     r12
0x1800541ef  pop     rdi
0x1800541f0  pop     rsi
0x1800541f1  pop     rbp
0x1800541f2  retn
```
