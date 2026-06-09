# SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18005bb6c`
- end: `0x18005c007`
- name: `?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z`
- size: `1179`
- prototype: `__int64 __fastcall(SessionDataUtil *__hidden this, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c2f0`

## callees

- `0x180003180`
- `0x1800117ac`
- `0x1800259b8`
- `0x180027948`
- `0x18005bb6c`
- `0x18005c010`
- `0x18005efd4`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bc02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bc02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bd05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bd05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005beb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bf2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005beb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005bf2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005bef7`

## string_xrefs

- `0x18005bbde`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall SessionDataUtil::ExtractExtendedSessionData(
        const WCHAR *this,
        const wchar_t *a2,
        wchar_t *a3,
        wchar_t **a4)
{
  double v4; // xmm3_8
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  int NumberPropertyWithDefault; // ebx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, JsonUtil **); // rdi
  __int64 v14; // rax
  const wchar_t *v15; // r8
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  JsonUtil *v18; // rbx
  __int64 (__fastcall *v19)(JsonUtil *, HSTRING, __int64 **); // rdi
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // eax
  __int64 v24; // rdx
  unsigned int i; // edi
  __int64 v26; // rax
  int v27; // eax
  __int64 (__fastcall ***v28)(__int64, GUID *, __int64 *); // rcx
  __int64 v29; // rdx
  __int64 (__fastcall **v30)(__int64, GUID *, __int64 *); // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rdi
  int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v38; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-49h] BYREF
  HSTRING string; // [rsp+40h] [rbp-31h] BYREF
  const WCHAR *v42; // [rsp+48h] [rbp-29h] BYREF
  __int64 (__fastcall ***v43)(__int64, GUID *, __int64 *); // [rsp+50h] [rbp-21h] BYREF
  JsonUtil *v44; // [rsp+58h] [rbp-19h] BYREF
  JsonUtil *v45; // [rsp+60h] [rbp-11h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-9h] BYREF
  __int64 v47; // [rsp+70h] [rbp-1h] BYREF
  __int64 *v48; // [rsp+78h] [rbp+7h] BYREF
  __int64 v49; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v42 = a2;
  if ( !this || !*this )
  {
    v38 = 51;
    goto LABEL_64;
  }
  if ( !a2 || !*a2 )
  {
    v38 = 52;
LABEL_64:
    NumberPropertyWithDefault = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80070057LL,
      (int)hstringHeader.Reserved.Reserved1);
    return (unsigned int)NumberPropertyWithDefault;
  }
  v49 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v7 < 0 )
    goto LABEL_67;
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v49);
  NumberPropertyWithDefault = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v45 = 0;
    v12 = v49;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, JsonUtil **))(*(_QWORD *)v49 + 48LL);
    v45 = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v42);
    NumberPropertyWithDefault = v13(v12, *(_QWORD *)(v14 + 24), &v45);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 59;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_57:
      if ( v45 )
        (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v45 + 16LL))(v45);
      goto LABEL_59;
    }
    v42 = 0;
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v45,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"Version",
                                  v15,
                                  v4,
                                  (double *)hstringHeader.Reserved.Reserved1);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 62;
      goto LABEL_14;
    }
    v42 = 0;
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v45,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"SchemaVersion",
                                  v17,
                                  v4,
                                  (double *)hstringHeader.Reserved.Reserved1);
    if ( NumberPropertyWithDefault < 0 )
    {
      v16 = 65;
      goto LABEL_14;
    }
    v42 = this;
    v48 = 0;
    v18 = v45;
    v19 = *(__int64 (__fastcall **)(JsonUtil *, HSTRING, __int64 **))(*(_QWORD *)v45 + 72LL);
    v48 = 0;
    string = 0;
    v20 = WindowsCreateStringReference(L"Sessions", 8u, &hstringHeader, &string);
    if ( v20 >= 0 )
    {
      v23 = v19(v18, string, &v48);
      NumberPropertyWithDefault = v23;
      v43 = 0;
      if ( v23 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          v44 = 0;
          v26 = *v48;
          v44 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, JsonUtil **))(v26 + 48))(v48, i, &v44);
          NumberPropertyWithDefault = v27;
          if ( v27 == -2147483637 )
          {
LABEL_38:
            if ( v44 )
              (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
            goto LABEL_40;
          }
          if ( v27 < 0 )
            break;
          v28 = v43;
          v43 = 0;
          if ( v28 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v28)[2])(v28);
          v27 = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v44, (__int64)&v43);
          NumberPropertyWithDefault = v27;
          if ( v27 < 0 )
          {
            v29 = 132;
            goto LABEL_35;
          }
          if ( v43 )
            goto LABEL_38;
          if ( v44 )
            (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v29 = 131;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v27,
          (int)hstringHeader.Reserved.Reserved1);
        if ( v44 )
          (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v44 + 16LL))(v44);
        goto LABEL_53;
      }
      if ( v23 != -2089484279 )
      {
        v24 = 116;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)NumberPropertyWithDefault,
          (int)hstringHeader.Reserved.Reserved1);
LABEL_53:
        if ( v43 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v43)[2])(v43);
        if ( v48 )
          (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
        goto LABEL_57;
      }
      v43 = 0;
      NumberPropertyWithDefault = lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(&v42, v45, (__int64)&v43);
      if ( NumberPropertyWithDefault < 0 )
      {
        v24 = 117;
        goto LABEL_21;
      }
LABEL_40:
      if ( !v43 )
      {
        NumberPropertyWithDefault = 0;
        goto LABEL_53;
      }
      v47 = 0;
      v30 = *v43;
      v47 = 0;
      v31 = (*v30)((__int64)v43, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v47);
      NumberPropertyWithDefault = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)v31,
          (int)hstringHeader.Reserved.Reserved1);
        goto LABEL_51;
      }
      v46 = 0;
      v32 = v47;
      v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 56LL);
      WindowsDeleteString(0);
      v46 = 0;
      v34 = v33(v32, &v46);
      NumberPropertyWithDefault = v34;
      if ( v34 >= 0 )
      {
        v42 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
          &v42,
          StringRawBuffer,
          -1);
        if ( v42 )
        {
          *(_QWORD *)a3 = v42;
          NumberPropertyWithDefault = 0;
          goto LABEL_50;
        }
        NumberPropertyWithDefault = -2147024882;
        v35 = 2147942414LL;
        v36 = 151;
      }
      else
      {
        v35 = (unsigned int)v34;
        v36 = 148;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)v35,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_50:
      WindowsDeleteString(v46);
      v46 = 0;
LABEL_51:
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      goto LABEL_53;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
LABEL_67:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x18005C006LL);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_59:
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)NumberPropertyWithDefault;
}

```

## disassembly

```asm
0x18005bb6c  mov     rax, rsp
0x18005bb6f  mov     [rax+8], rbx
0x18005bb73  push    rbp
0x18005bb74  push    rsi
0x18005bb75  push    rdi
0x18005bb76  push    r14
0x18005bb78  push    r15
0x18005bb7a  lea     rbp, [rax-5Fh]
0x18005bb7e  sub     rsp, 0A0h
0x18005bb85  movaps  xmmword ptr [rax-38h], xmm6
0x18005bb89  mov     rax, cs:__security_cookie
0x18005bb90  xor     rax, rsp
0x18005bb93  mov     [rbp+57h+var_40], rax
0x18005bb97  mov     r14, r8
0x18005bb9a  mov     rsi, rcx
0x18005bb9d  mov     [rbp+57h+var_80], rdx
0x18005bba1  xor     r15d, r15d
0x18005bba4  test    rcx, rcx
0x18005bba7  jz      loc_18005BFB0
0x18005bbad  cmp     [rcx], r15w
0x18005bbb1  jz      loc_18005BFB0
0x18005bbb7  test    rdx, rdx
0x18005bbba  jz      loc_18005BFA9
0x18005bbc0  cmp     [rdx], r15w
0x18005bbc4  jz      loc_18005BFA9
0x18005bbca  mov     [rbp+57h+var_48], r15
0x18005bbce  mov     [rbp+57h+string], r15
0x18005bbd2  lea     r9, [rbp+57h+string]; string
0x18005bbd6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005bbda  lea     edx, [r15+1Ch]; length
0x18005bbde  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18005bbe5  call    cs:__imp_WindowsCreateStringReference
0x18005bbeb  test    eax, eax
0x18005bbed  js      loc_18005BFFF
0x18005bbf3  lea     r8, [rbp+57h+var_48]
0x18005bbf7  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18005bbfe  mov     rcx, [rbp+57h+string]
0x18005bc02  call    cs:__imp_RoGetActivationFactory
0x18005bc08  mov     ebx, eax
0x18005bc0a  test    eax, eax
0x18005bc0c  jns     short loc_18005BC2A
0x18005bc0e  mov     rcx, [rbp+5Fh]; this
0x18005bc12  mov     r9d, eax; char *
0x18005bc15  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005bc1c  lea     edx, [r15+38h]; void *
0x18005bc20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bc25  jmp     loc_18005BF91
0x18005bc2a  mov     [rbp+57h+var_68], r15
0x18005bc2e  mov     rbx, [rbp+57h+var_48]
0x18005bc32  mov     rax, [rbx]
0x18005bc35  mov     rdi, [rax+30h]
0x18005bc39  mov     [rbp+57h+var_68], r15
0x18005bc3d  lea     rdx, [rbp+57h+var_80]
0x18005bc41  lea     rcx, [rbp+57h+hstringHeader]
0x18005bc45  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18005bc4a  nop
0x18005bc4b  lea     r8, [rbp+57h+var_68]
0x18005bc4f  mov     rdx, [rax+18h]
0x18005bc53  mov     rcx, rbx
0x18005bc56  mov     rax, rdi
0x18005bc59  call    _guard_dispatch_icall
0x18005bc5e  mov     ebx, eax
0x18005bc60  test    eax, eax
0x18005bc62  jns     short loc_18005BC6B
0x18005bc64  mov     edx, 3Bh ; ';'
0x18005bc69  jmp     short loc_18005BCBE
0x18005bc6b  xorps   xmm6, xmm6
0x18005bc6e  movsd   [rbp+57h+var_80], xmm6
0x18005bc73  lea     r9, [rbp+57h+var_80]
0x18005bc77  xorps   xmm2, xmm2
0x18005bc7a  lea     rdx, aVersion; "Version"
0x18005bc81  mov     rcx, [rbp+57h+var_68]; this
0x18005bc85  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18005bc8a  mov     ebx, eax
0x18005bc8c  test    eax, eax
0x18005bc8e  jns     short loc_18005BC97
0x18005bc90  mov     edx, 3Eh ; '>'
0x18005bc95  jmp     short loc_18005BCBE
0x18005bc97  movsd   [rbp+57h+var_80], xmm6
0x18005bc9c  lea     r9, [rbp+57h+var_80]
0x18005bca0  xorps   xmm2, xmm2
0x18005bca3  lea     rdx, aSchemaversion; "SchemaVersion"
0x18005bcaa  mov     rcx, [rbp+57h+var_68]; this
0x18005bcae  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18005bcb3  mov     ebx, eax
0x18005bcb5  test    eax, eax
0x18005bcb7  jns     short loc_18005BCD6
0x18005bcb9  mov     edx, 41h ; 'A'; void *
0x18005bcbe  mov     rcx, [rbp+5Fh]; this
0x18005bcc2  mov     r9d, ebx; char *
0x18005bcc5  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005bccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bcd1  jmp     loc_18005BF7B
0x18005bcd6  mov     [rbp+57h+var_80], rsi
0x18005bcda  mov     [rbp+57h+var_50], r15
0x18005bcde  mov     rbx, [rbp+57h+var_68]
0x18005bce2  mov     rax, [rbx]
0x18005bce5  mov     rdi, [rax+48h]
0x18005bce9  mov     [rbp+57h+var_50], r15
0x18005bced  mov     [rbp+57h+string], r15
0x18005bcf1  lea     r9, [rbp+57h+string]; string
0x18005bcf5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005bcf9  mov     edx, 8; length
0x18005bcfe  lea     rcx, aSessions; "Sessions"
0x18005bd05  call    cs:__imp_WindowsCreateStringReference
0x18005bd0b  test    eax, eax
0x18005bd0d  js      loc_18005BFF7
0x18005bd13  lea     r8, [rbp+57h+var_50]
0x18005bd17  mov     rdx, [rbp+57h+string]
0x18005bd1b  mov     rcx, rbx
0x18005bd1e  mov     rax, rdi
0x18005bd21  call    _guard_dispatch_icall
0x18005bd26  mov     ebx, eax
0x18005bd28  mov     [rbp+57h+var_78], r15
0x18005bd2c  test    eax, eax
0x18005bd2e  jns     short loc_18005BD7A
0x18005bd30  cmp     eax, 83750009h
0x18005bd35  jz      short loc_18005BD3E
0x18005bd37  mov     edx, 74h ; 't'
0x18005bd3c  jmp     short loc_18005BD62
0x18005bd3e  mov     [rbp+57h+var_78], r15
0x18005bd42  lea     r8, [rbp+57h+var_78]
0x18005bd46  mov     rdx, [rbp+57h+var_68]
0x18005bd4a  lea     rcx, [rbp+57h+var_80]
0x18005bd4e  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x18005bd53  mov     ebx, eax
0x18005bd55  test    eax, eax
0x18005bd57  jns     loc_18005BE50
0x18005bd5d  mov     edx, 75h ; 'u'; void *
0x18005bd62  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005bd69  mov     rcx, [rbp+5Fh]; this
0x18005bd6d  mov     r9d, ebx; char *
0x18005bd70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bd75  jmp     loc_18005BF4F
0x18005bd7a  mov     edi, r15d
0x18005bd7d  mov     [rbp+57h+var_70], r15
0x18005bd81  mov     rcx, [rbp+57h+var_50]
0x18005bd85  mov     rax, [rcx]
0x18005bd88  mov     [rbp+57h+var_70], r15
0x18005bd8c  lea     r8, [rbp+57h+var_70]
0x18005bd90  mov     edx, edi
0x18005bd92  mov     rax, [rax+30h]
0x18005bd96  call    _guard_dispatch_icall
0x18005bd9b  mov     ebx, eax
0x18005bd9d  cmp     eax, 8000000Bh
0x18005bda2  jz      loc_18005BE3A
0x18005bda8  test    eax, eax
0x18005bdaa  js      short loc_18005BE06
0x18005bdac  mov     rcx, [rbp+57h+var_78]
0x18005bdb0  mov     [rbp+57h+var_78], r15
0x18005bdb4  test    rcx, rcx
0x18005bdb7  jz      short loc_18005BDC6
0x18005bdb9  mov     rax, [rcx]
0x18005bdbc  mov     rax, [rax+10h]
0x18005bdc0  call    _guard_dispatch_icall
0x18005bdc5  nop
0x18005bdc6  lea     r8, [rbp+57h+var_78]
0x18005bdca  mov     rdx, [rbp+57h+var_70]
0x18005bdce  lea     rcx, [rbp+57h+var_80]
0x18005bdd2  call    _lambda_a4c2085267137ef4ce0642cdecb305f9___operator__
0x18005bdd7  mov     ebx, eax
0x18005bdd9  test    eax, eax
0x18005bddb  js      short loc_18005BDFF
0x18005bddd  cmp     [rbp+57h+var_78], r15
0x18005bde1  jnz     short loc_18005BDFD
0x18005bde3  mov     rcx, [rbp+57h+var_70]
0x18005bde7  test    rcx, rcx
0x18005bdea  jz      short loc_18005BDF9
0x18005bdec  mov     rax, [rcx]
0x18005bdef  mov     rax, [rax+10h]
0x18005bdf3  call    _guard_dispatch_icall
0x18005bdf8  nop
0x18005bdf9  inc     edi
0x18005bdfb  jmp     short loc_18005BD7D
0x18005bdfd  jmp     short loc_18005BE3A
0x18005bdff  mov     edx, 84h
0x18005be04  jmp     short loc_18005BE0B
0x18005be06  mov     edx, 83h; void *
0x18005be0b  mov     r9d, eax; char *
0x18005be0e  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005be15  mov     rcx, [rbp+5Fh]; this
0x18005be19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005be1e  nop
0x18005be1f  mov     rcx, [rbp+57h+var_70]
0x18005be23  test    rcx, rcx
0x18005be26  jz      short loc_18005BE35
0x18005be28  mov     rax, [rcx]
0x18005be2b  mov     rax, [rax+10h]
0x18005be2f  call    _guard_dispatch_icall
0x18005be34  nop
0x18005be35  jmp     loc_18005BF4F
0x18005be3a  mov     rcx, [rbp+57h+var_70]
0x18005be3e  test    rcx, rcx
0x18005be41  jz      short loc_18005BE50
0x18005be43  mov     rax, [rcx]
0x18005be46  mov     rax, [rax+10h]
0x18005be4a  call    _guard_dispatch_icall
0x18005be4f  nop
0x18005be50  cmp     [rbp+57h+var_78], r15
0x18005be54  jnz     short loc_18005BE5E
0x18005be56  mov     ebx, r15d
0x18005be59  jmp     loc_18005BF4F
0x18005be5e  mov     [rbp+57h+var_58], r15
0x18005be62  mov     rcx, [rbp+57h+var_78]
0x18005be66  mov     rax, [rcx]
0x18005be69  mov     [rbp+57h+var_58], r15
0x18005be6d  lea     r8, [rbp+57h+var_58]
0x18005be71  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18005be78  mov     rax, [rax]
0x18005be7b  call    _guard_dispatch_icall
0x18005be80  mov     ebx, eax
0x18005be82  test    eax, eax
0x18005be84  jns     short loc_18005BEA3
0x18005be86  mov     rcx, [rbp+5Fh]; this
0x18005be8a  mov     r9d, eax; char *
0x18005be8d  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005be94  mov     edx, 91h; void *
0x18005be99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005be9e  jmp     loc_18005BF39
0x18005bea3  mov     [rbp+57h+var_60], r15
0x18005bea7  mov     rbx, [rbp+57h+var_58]
0x18005beab  mov     rax, [rbx]
0x18005beae  mov     rdi, [rax+38h]
0x18005beb2  xor     ecx, ecx; string
0x18005beb4  call    cs:__imp_WindowsDeleteString
0x18005beba  mov     [rbp+57h+var_60], r15
0x18005bebe  lea     rdx, [rbp+57h+var_60]
0x18005bec2  mov     rcx, rbx
0x18005bec5  mov     rax, rdi
0x18005bec8  call    _guard_dispatch_icall
0x18005becd  mov     ebx, eax
0x18005becf  test    eax, eax
0x18005bed1  jns     short loc_18005BEED
0x18005bed3  mov     r9d, eax; char *
0x18005bed6  mov     edx, 94h; void *
0x18005bedb  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005bee2  mov     rcx, [rbp+5Fh]; this
0x18005bee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005beeb  jmp     short loc_18005BF2B
0x18005beed  mov     [rbp+57h+var_80], r15
0x18005bef1  xor     edx, edx; length
0x18005bef3  mov     rcx, [rbp+57h+var_60]; string
0x18005bef7  call    cs:__imp_WindowsGetStringRawBuffer
0x18005befd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005bf01  mov     rdx, rax
0x18005bf04  lea     rcx, [rbp+57h+var_80]
0x18005bf08  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18005bf0d  mov     rax, [rbp+57h+var_80]
0x18005bf11  test    rax, rax
0x18005bf14  jnz     short loc_18005BF25
0x18005bf16  mov     ebx, 8007000Eh
0x18005bf1b  mov     r9d, ebx
0x18005bf1e  mov     edx, 97h
0x18005bf23  jmp     short loc_18005BEDB
0x18005bf25  mov     [r14], rax
0x18005bf28  mov     ebx, r15d
0x18005bf2b  mov     rcx, [rbp+57h+var_60]; string
0x18005bf2f  call    cs:__imp_WindowsDeleteString
0x18005bf35  mov     [rbp+57h+var_60], r15
0x18005bf39  mov     rcx, [rbp+57h+var_58]
0x18005bf3d  test    rcx, rcx
0x18005bf40  jz      short loc_18005BF4F
0x18005bf42  mov     rax, [rcx]
0x18005bf45  mov     rax, [rax+10h]
0x18005bf49  call    _guard_dispatch_icall
0x18005bf4e  nop
0x18005bf4f  mov     rcx, [rbp+57h+var_78]
0x18005bf53  test    rcx, rcx
0x18005bf56  jz      short loc_18005BF65
0x18005bf58  mov     rax, [rcx]
0x18005bf5b  mov     rax, [rax+10h]
0x18005bf5f  call    _guard_dispatch_icall
0x18005bf64  nop
0x18005bf65  mov     rcx, [rbp+57h+var_50]
0x18005bf69  test    rcx, rcx
0x18005bf6c  jz      short loc_18005BF7B
0x18005bf6e  mov     rax, [rcx]
0x18005bf71  mov     rax, [rax+10h]
0x18005bf75  call    _guard_dispatch_icall
0x18005bf7a  nop
0x18005bf7b  mov     rcx, [rbp+57h+var_68]
0x18005bf7f  test    rcx, rcx
0x18005bf82  jz      short loc_18005BF91
0x18005bf84  mov     rax, [rcx]
0x18005bf87  mov     rax, [rax+10h]
0x18005bf8b  call    _guard_dispatch_icall
0x18005bf90  nop
0x18005bf91  mov     rcx, [rbp+57h+var_48]
0x18005bf95  test    rcx, rcx
0x18005bf98  jz      short loc_18005BFA7
0x18005bf9a  mov     rdx, [rcx]
0x18005bf9d  mov     rax, [rdx+10h]
0x18005bfa1  call    _guard_dispatch_icall
0x18005bfa6  nop
0x18005bfa7  jmp     short loc_18005BFCD
0x18005bfa9  mov     edx, 34h ; '4'
0x18005bfae  jmp     short loc_18005BFB5
0x18005bfb0  mov     edx, 33h ; '3'; void *
0x18005bfb5  mov     ebx, 80070057h
0x18005bfba  mov     r9d, ebx; char *
  ... truncated ...
```
