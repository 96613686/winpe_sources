# TbLogProvider::GetTokenForVailContainer::TraceParams(Windows::Security::Authentication::Web::Core::WebTokenRequsetResultOperationParams const &)

- ea: `0x1800b2b34`
- end: `0x1800b2edf`
- name: `?TraceParams@GetTokenForVailContainer@TbLogProvider@@QEAAXAEBUWebTokenRequsetResultOperationParams@Core@Web@Authentication@Security@Windows@@@Z`
- size: `939`
- prototype: `void __fastcall(TbLogProvider::GetTokenForVailContainer *__hidden this, const struct Windows::Security::Authentication::Web::Core::WebTokenRequsetResultOperationParams *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a399c`

## callees

- `0x1800016e0`
- `0x18000fcf8`
- `0x18002d940`
- `0x180043370`
- `0x1800455a4`
- `0x18005e830`
- `0x180063fc4`
- `0x18008e690`
- `0x1800b2b34`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2da6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2ea6`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall TbLogProvider::GetTokenForVailContainer::TraceParams(
        TbLogProvider::GetTokenForVailContainer *this,
        __int64 **a2)
{
  __int64 v4; // rax
  int (*v5)(void); // rax
  bool v6; // r14
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  int v9; // edi
  int v10; // r9d
  char v11; // [rsp+70h] [rbp-B8h] BYREF
  bool v12[3]; // [rsp+71h] [rbp-B7h] BYREF
  int v13; // [rsp+74h] [rbp-B4h] BYREF
  __int64 v14; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+80h] [rbp-A8h] BYREF
  HSTRING v16; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+90h] [rbp-98h] BYREF
  HSTRING string; // [rsp+98h] [rbp-90h] BYREF
  HSTRING v19; // [rsp+A0h] [rbp-88h] BYREF
  HSTRING v20; // [rsp+A8h] [rbp-80h] BYREF
  HSTRING v21; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-70h] BYREF
  PCWSTR StringRawBuffer; // [rsp+C0h] [rbp-68h] BYREF
  PCWSTR v24; // [rsp+C8h] [rbp-60h] BYREF
  PCWSTR v25; // [rsp+D0h] [rbp-58h] BYREF
  PCWSTR v26; // [rsp+D8h] [rbp-50h] BYREF
  PCWSTR v27; // [rsp+E0h] [rbp-48h] BYREF
  _BYTE v28[32]; // [rsp+E8h] [rbp-40h] BYREF

  v15 = 0;
  v21 = 0;
  v20 = 0;
  v4 = **a2;
  v15 = 0;
  v5 = *(int (**)(void))(v4 + 48);
  try
  {
    if ( v5() >= 0 )
    {
      (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 48LL))(v15, &v21);
      v14 = 0;
      if ( (int)wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(
                  &v15,
                  (__int64)&v14) >= 0 )
        (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 56LL))(v14, &v20);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v14);
    }
    v16 = 0;
    (*(void (__fastcall **)(__int64 *, HSTRING *))(**a2 + 56))(*a2, &v16);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v28,
      L"enumerate.accounts.local");
    v6 = (unsigned int)Windows::Internal::StringReference::CompareOrdinal(
                         (Windows::Internal::StringReference *)v28,
                         (const struct Windows::Internal::String *)&v16) == 0;
    v19 = 0;
    (*(void (__fastcall **)(__int64 *, HSTRING *))(**a2 + 64))(*a2, &v19);
    string = 0;
    v17 = 0;
    if ( (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))**a2)(
           *a2,
           &GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a,
           &v17) >= 0 )
      (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 48LL))(v17, &string);
    v13 = 0;
    if ( (*(int (__fastcall **)(__int64 *, int *))(**a2 + 72))(*a2, &v13) < 0 )
      v13 = 0;
    v7 = TbLogProvider::Provider();
    v9 = (int)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8) )
    {
      v22 = *((unsigned int *)a2 + 5);
      v11 = *((_BYTE *)a2 + 16);
      LODWORD(v14) = v13;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v24 = WindowsGetStringRawBuffer(v19, 0);
      v12[0] = v6;
      v25 = WindowsGetStringRawBuffer(v16, 0);
      v26 = WindowsGetStringRawBuffer(v20, 0);
      v27 = WindowsGetStringRawBuffer(v21, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v9,
        (unsigned int)word_180147672,
        *((_QWORD *)this + 34) + 8,
        v10,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)v12,
        (__int64)&v24,
        (__int64)&StringRawBuffer,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v22);
    }
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v17);
    if ( string )
      WindowsDeleteString(string);
    if ( v19 )
      WindowsDeleteString(v19);
    if ( v16 )
      WindowsDeleteString(v16);
    if ( v20 )
      WindowsDeleteString(v20);
    if ( v21 )
      WindowsDeleteString(v21);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v15);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800b2b34  mov     r11, rsp
0x1800b2b37  mov     [r11+18h], rbx
0x1800b2b3b  push    rsi
0x1800b2b3c  push    rdi
0x1800b2b3d  push    r14
0x1800b2b3f  sub     rsp, 110h
0x1800b2b46  mov     rax, cs:__security_cookie
0x1800b2b4d  xor     rax, rsp
0x1800b2b50  mov     [rsp+128h+var_20], rax
0x1800b2b58  mov     rbx, rdx
0x1800b2b5b  mov     rsi, rcx
0x1800b2b5e  mov     qword ptr [r11-0A8h], 0
0x1800b2b69  mov     qword ptr [r11-78h], 0
0x1800b2b71  mov     qword ptr [r11-80h], 0
0x1800b2b79  mov     rcx, [rdx]
0x1800b2b7c  mov     rax, [rcx]
0x1800b2b7f  mov     qword ptr [r11-0A8h], 0
0x1800b2b8a  lea     rdx, [r11-0A8h]
0x1800b2b91  mov     rax, [rax+30h]
0x1800b2b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b9a  test    eax, eax
0x1800b2b9c  js      short loc_1800B2BFE
0x1800b2b9e  mov     rcx, [rsp+128h+var_A8]
0x1800b2ba6  mov     rax, [rcx]
0x1800b2ba9  lea     rdx, [rsp+128h+var_78]
0x1800b2bb1  mov     rax, [rax+30h]
0x1800b2bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2bba  nop
0x1800b2bbb  mov     [rsp+128h+var_B0], 0
0x1800b2bc4  lea     rdx, [rsp+128h+var_B0]
0x1800b2bc9  lea     rcx, [rsp+128h+var_A8]
0x1800b2bd1  call    ??$com_query_to_nothrow@UIWebAccountProvider2@Credentials@Security@Windows@@AEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@0@PEAPEAUIWebAccountProvider2@Credentials@Security@Windows@@@Z; wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &,Windows::Security::Credentials::IWebAccountProvider2 * *)
0x1800b2bd6  test    eax, eax
0x1800b2bd8  js      short loc_1800B2BF4
0x1800b2bda  mov     rcx, [rsp+128h+var_B0]
0x1800b2bdf  mov     rax, [rcx]
0x1800b2be2  lea     rdx, [rsp+128h+var_80]
0x1800b2bea  mov     rax, [rax+38h]
0x1800b2bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2bf3  nop
0x1800b2bf4  lea     rcx, [rsp+128h+var_B0]
0x1800b2bf9  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800b2bfe  mov     [rsp+128h+var_A0], 0
0x1800b2c0a  mov     rcx, [rbx]
0x1800b2c0d  mov     rax, [rcx]
0x1800b2c10  lea     rdx, [rsp+128h+var_A0]
0x1800b2c18  mov     rax, [rax+38h]
0x1800b2c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2c21  mov     rdx, cs:off_18012B2F0; unsigned __int16 *
0x1800b2c28  lea     rcx, [rsp+128h+var_40]; this
0x1800b2c30  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800b2c35  lea     rdx, [rsp+128h+var_A0]; struct Windows::Internal::String *
0x1800b2c3d  lea     rcx, [rsp+128h+var_40]; this
0x1800b2c45  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x1800b2c4a  test    eax, eax
0x1800b2c4c  setz    r14b
0x1800b2c50  mov     [rsp+128h+var_88], 0
0x1800b2c5c  mov     rcx, [rbx]
0x1800b2c5f  mov     rax, [rcx]
0x1800b2c62  lea     rdx, [rsp+128h+var_88]
0x1800b2c6a  mov     rax, [rax+40h]
0x1800b2c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2c73  mov     [rsp+128h+string], 0
0x1800b2c7f  mov     [rsp+128h+var_98], 0
0x1800b2c8b  mov     rcx, [rbx]
0x1800b2c8e  mov     rax, [rcx]
0x1800b2c91  lea     r8, [rsp+128h+var_98]
0x1800b2c99  lea     rdx, _GUID_5a755b51_3bb1_41a5_a63d_90bc32c7db9a
0x1800b2ca0  mov     rax, [rax]
0x1800b2ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ca8  test    eax, eax
0x1800b2caa  js      short loc_1800B2CC8
0x1800b2cac  mov     rcx, [rsp+128h+var_98]
0x1800b2cb4  mov     rax, [rcx]
0x1800b2cb7  lea     rdx, [rsp+128h+string]
0x1800b2cbf  mov     rax, [rax+30h]
0x1800b2cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2cc8  mov     [rsp+128h+var_B4], 0
0x1800b2cd0  mov     rcx, [rbx]
0x1800b2cd3  mov     rax, [rcx]
0x1800b2cd6  lea     rdx, [rsp+128h+var_B4]
0x1800b2cdb  mov     rax, [rax+48h]
0x1800b2cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ce4  test    eax, eax
0x1800b2ce6  jns     short loc_1800B2CF0
0x1800b2ce8  mov     [rsp+128h+var_B4], 0
0x1800b2cf0  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800b2cf5  mov     rdi, rax
0x1800b2cf8  mov     ecx, [rax]
0x1800b2cfa  cmp     ecx, 5
0x1800b2cfd  jbe     loc_1800B2E3B
0x1800b2d03  mov     rdx, 400000000000h
0x1800b2d0d  mov     rcx, rax
0x1800b2d10  call    _tlgKeywordOn
0x1800b2d15  test    al, al
0x1800b2d17  jz      loc_1800B2E3B
0x1800b2d1d  mov     ecx, [rbx+14h]
0x1800b2d20  mov     [rsp+128h+var_70], rcx
0x1800b2d28  mov     al, [rbx+10h]
0x1800b2d2b  mov     [rsp+128h+var_B8], al
0x1800b2d2f  mov     eax, [rsp+128h+var_B4]
0x1800b2d33  mov     dword ptr [rsp+128h+var_B0], eax
0x1800b2d37  xor     edx, edx; length
0x1800b2d39  mov     rcx, [rsp+128h+string]; string
0x1800b2d41  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2d47  mov     [rsp+128h+var_68], rax
0x1800b2d4f  xor     edx, edx; length
0x1800b2d51  mov     rcx, [rsp+128h+var_88]; string
0x1800b2d59  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2d5f  mov     [rsp+128h+var_60], rax
0x1800b2d67  mov     [rsp+128h+var_B7], r14b
0x1800b2d6c  xor     edx, edx; length
0x1800b2d6e  mov     rcx, [rsp+128h+var_A0]; string
0x1800b2d76  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2d7c  mov     [rsp+128h+var_58], rax
0x1800b2d84  xor     edx, edx; length
0x1800b2d86  mov     rcx, [rsp+128h+var_80]; string
0x1800b2d8e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2d94  mov     [rsp+128h+var_50], rax
0x1800b2d9c  xor     edx, edx; length
0x1800b2d9e  mov     rcx, [rsp+128h+var_78]; string
0x1800b2da6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2dac  mov     [rsp+128h+var_48], rax
0x1800b2db4  mov     r8, [rsi+110h]
0x1800b2dbb  add     r8, 8
0x1800b2dbf  lea     rax, [rsp+128h+var_70]
0x1800b2dc7  mov     [rsp+128h+var_C8], rax
0x1800b2dcc  lea     rax, [rsp+128h+var_B8]
0x1800b2dd1  mov     [rsp+128h+var_D0], rax
0x1800b2dd6  lea     rax, [rsp+128h+var_B0]
0x1800b2ddb  mov     [rsp+128h+var_D8], rax
0x1800b2de0  lea     rax, [rsp+128h+var_68]
0x1800b2de8  mov     [rsp+128h+var_E0], rax
0x1800b2ded  lea     rax, [rsp+128h+var_60]
0x1800b2df5  mov     [rsp+128h+var_E8], rax
0x1800b2dfa  lea     rax, [rsp+128h+var_B7]
0x1800b2dff  mov     [rsp+128h+var_F0], rax
0x1800b2e04  lea     rax, [rsp+128h+var_58]
0x1800b2e0c  mov     [rsp+128h+var_F8], rax
0x1800b2e11  lea     rax, [rsp+128h+var_50]
0x1800b2e19  mov     [rsp+128h+var_100], rax
0x1800b2e1e  lea     rax, [rsp+128h+var_48]
0x1800b2e26  mov     [rsp+128h+var_108], rax
0x1800b2e2b  lea     rdx, word_180147672
0x1800b2e32  mov     rcx, rdi
0x1800b2e35  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$00@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$00@@33AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1800b2e3a  nop
0x1800b2e3b  lea     rcx, [rsp+128h+var_98]
0x1800b2e43  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800b2e48  nop
0x1800b2e49  mov     rcx, [rsp+128h+string]; string
0x1800b2e51  test    rcx, rcx
0x1800b2e54  jz      short loc_1800B2E5D
0x1800b2e56  call    cs:__imp_WindowsDeleteString
0x1800b2e5c  nop
0x1800b2e5d  mov     rcx, [rsp+128h+var_88]; string
0x1800b2e65  test    rcx, rcx
0x1800b2e68  jz      short loc_1800B2E71
0x1800b2e6a  call    cs:__imp_WindowsDeleteString
0x1800b2e70  nop
0x1800b2e71  mov     rcx, [rsp+128h+var_A0]; string
0x1800b2e79  test    rcx, rcx
0x1800b2e7c  jz      short loc_1800B2E85
0x1800b2e7e  call    cs:__imp_WindowsDeleteString
0x1800b2e84  nop
0x1800b2e85  mov     rcx, [rsp+128h+var_80]; string
0x1800b2e8d  test    rcx, rcx
0x1800b2e90  jz      short loc_1800B2E99
0x1800b2e92  call    cs:__imp_WindowsDeleteString
0x1800b2e98  nop
0x1800b2e99  mov     rcx, [rsp+128h+var_78]; string
0x1800b2ea1  test    rcx, rcx
0x1800b2ea4  jz      short loc_1800B2EAD
0x1800b2ea6  call    cs:__imp_WindowsDeleteString
0x1800b2eac  nop
0x1800b2ead  lea     rcx, [rsp+128h+var_A8]
0x1800b2eb5  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800b2eba  nop
0x1800b2ebb  mov     rcx, [rsp+128h+var_20]
0x1800b2ec3  xor     rcx, rsp; StackCookie
0x1800b2ec6  call    __security_check_cookie
0x1800b2ecb  mov     rbx, [rsp+128h+arg_10]
0x1800b2ed3  add     rsp, 110h
0x1800b2eda  pop     r14
0x1800b2edc  pop     rdi
0x1800b2edd  pop     rsi
0x1800b2ede  retn
```
