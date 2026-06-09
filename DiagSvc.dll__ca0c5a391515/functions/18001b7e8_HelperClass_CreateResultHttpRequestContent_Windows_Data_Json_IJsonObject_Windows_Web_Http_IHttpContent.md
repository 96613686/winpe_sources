# HelperClass::CreateResultHttpRequestContent(Windows::Data::Json::IJsonObject *,Windows::Web::Http::IHttpContent * *)

- ea: `0x18001b7e8`
- end: `0x18001bb0a`
- name: `?CreateResultHttpRequestContent@HelperClass@@SAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAUIHttpContent@Http@Web@5@@Z`
- size: `802`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, struct Windows::Web::Http::IHttpContent **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b80`

## callees

- `0x180003fc0`
- `0x18000517c`
- `0x18000847c`
- `0x18000ade0`
- `0x18001b178`
- `0x18001b7e8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bae6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b970`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ba23`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b970`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ba23`

## string_xrefs

- `0x18001b82c`: `Windows.Data.Json.JsonObject`
- `0x18001ba51`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HelperClass::CreateResultHttpRequestContent(
        struct Windows::Data::Json::IJsonObject *a1,
        struct Windows::Web::Http::IHttpContent **a2)
{
  int ActivationFactory; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64); // rdi
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, struct Windows::Web::Http::IHttpContent **); // rbx
  struct Windows::Web::Http::IHttpContent *v13; // rdi
  __int64 (__fastcall *v14)(struct Windows::Web::Http::IHttpContent *, __int64 **); // rbx
  __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, GUID *, __int64 *); // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  struct Windows::Web::Http::IHttpContent *v20; // rax
  __int64 v22; // [rsp+20h] [rbp-39h] BYREF
  __int64 v23; // [rsp+28h] [rbp-31h] BYREF
  __int64 *v24; // [rsp+30h] [rbp-29h] BYREF
  struct Windows::Web::Http::IHttpContent *v25; // [rsp+38h] [rbp-21h] BYREF
  __int64 v26; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-1h] BYREF
  GUID *v30; // [rsp+70h] [rbp+17h]

  string = 0;
  v28 = 0;
  v25 = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                        (__int64)v30,
                        &v28);
  if ( ActivationFactory >= 0 )
  {
    v24 = (__int64 *)a1;
    if ( a1 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 8LL))(a1);
    v22 = 0;
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
                          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v24,
                          (__int64)&v22);
    if ( ActivationFactory >= 0 )
    {
      v5 = v28;
      v6 = (*v28)[7];
      v7 = v22;
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"result", 7u, 6u);
      ActivationFactory = v6(v5, v30, v7);
      if ( ActivationFactory >= 0 )
      {
        v23 = 0;
        ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
                              &v28,
                              (__int64)&v23);
        if ( ActivationFactory >= 0 )
        {
          v8 = v23;
          v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 56LL);
          WindowsDeleteString(string);
          string = 0;
          ActivationFactory = v9(v8, &string);
        }
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v23);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v24);
    if ( ActivationFactory >= 0 )
    {
      v23 = 0;
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Web.Http.HttpStringContent",
        0x23u,
        0x22u);
      v10 = (__int64)v30;
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v23);
      ActivationFactory = RoGetActivationFactory(v10, &GUID_46649d5b_2e93_48eb_8e61_19677878e57f, &v23);
      if ( ActivationFactory >= 0 )
      {
        v11 = v23;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Web::Http::IHttpContent **))(*(_QWORD *)v23 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v25);
        ActivationFactory = v12(v11, string, &v25);
        if ( ActivationFactory >= 0 )
        {
          v22 = 0;
          v26 = 0;
          v24 = 0;
          v13 = v25;
          v14 = *(__int64 (__fastcall **)(struct Windows::Web::Http::IHttpContent *, __int64 **))(*(_QWORD *)v25 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v24);
          ActivationFactory = v14(v13, &v24);
          if ( ActivationFactory >= 0 )
          {
            v30 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Web.Http.Headers.HttpMediaTypeHeaderValue",
              0x32u,
              0x31u);
            v15 = (__int64)v30;
            Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v22);
            ActivationFactory = RoGetActivationFactory(v15, &GUID_bed747a8_cd17_42dd_9367_ab9c5b56dd7d, &v22);
            if ( ActivationFactory >= 0 )
            {
              v16 = v22;
              v17 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v26);
              v30 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"application/json",
                0x11u,
                0x10u);
              ActivationFactory = v17(v16, v30, &v26);
              if ( ActivationFactory >= 0 )
              {
                v18 = *v24;
                v19 = v26;
                v26 = 0;
                ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, __int64))(v18 + 152))(v24, v19);
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v26);
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v22);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v23);
      if ( ActivationFactory >= 0 )
      {
        v20 = v25;
        v25 = 0;
        *a2 = v20;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v28);
  WindowsDeleteString(string);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001b7e8  push    rbp
0x18001b7ea  push    rbx
0x18001b7eb  push    rsi
0x18001b7ec  push    rdi
0x18001b7ed  push    r14
0x18001b7ef  push    r15
0x18001b7f1  lea     rbp, [rsp-2Fh]
0x18001b7f6  sub     rsp, 88h
0x18001b7fd  mov     rax, cs:__security_cookie
0x18001b804  xor     rax, rsp
0x18001b807  mov     [rbp+57h+var_38], rax
0x18001b80b  mov     r14, rdx
0x18001b80e  mov     rdi, rcx
0x18001b811  xor     r15d, r15d
0x18001b814  mov     [rbp+57h+string], r15
0x18001b818  mov     [rbp+57h+var_60], r15
0x18001b81c  mov     [rbp+57h+var_78], r15
0x18001b820  mov     [rbp+57h+var_40], r15
0x18001b824  lea     r9d, [r15+1Ch]; unsigned int
0x18001b828  lea     r8d, [r15+1Dh]; unsigned int
0x18001b82c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001b833  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001b837  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001b83c  lea     rdx, [rbp+57h+var_60]
0x18001b840  mov     rcx, [rbp+57h+var_40]
0x18001b844  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18001b849  mov     ebx, eax
0x18001b84b  test    eax, eax
0x18001b84d  js      loc_18001BACE
0x18001b853  mov     [rbp+57h+var_80], rdi
0x18001b857  test    rdi, rdi
0x18001b85a  jz      short loc_18001B86C
0x18001b85c  mov     rax, [rdi]
0x18001b85f  mov     rcx, rdi
0x18001b862  mov     rax, [rax+8]
0x18001b866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b86b  nop
0x18001b86c  mov     [rbp+57h+var_90], r15
0x18001b870  lea     rdx, [rbp+57h+var_90]
0x18001b874  lea     rcx, [rbp+57h+var_80]
0x18001b878  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18001b87d  mov     ebx, eax
0x18001b87f  test    eax, eax
0x18001b881  js      loc_18001B918
0x18001b887  mov     rsi, [rbp+57h+var_60]
0x18001b88b  mov     rax, [rsi]
0x18001b88e  mov     rdi, [rax+38h]
0x18001b892  mov     rbx, [rbp+57h+var_90]
0x18001b896  mov     [rbp+57h+var_40], r15
0x18001b89a  mov     r9d, 6; unsigned int
0x18001b8a0  lea     r8d, [r9+1]; unsigned int
0x18001b8a4  lea     rdx, aResult; "result"
0x18001b8ab  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001b8af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001b8b4  nop
0x18001b8b5  mov     r8, rbx
0x18001b8b8  mov     rdx, [rbp+57h+var_40]
0x18001b8bc  mov     rcx, rsi
0x18001b8bf  mov     rax, rdi
0x18001b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c7  mov     ebx, eax
0x18001b8c9  test    eax, eax
0x18001b8cb  js      short loc_18001B918
0x18001b8cd  mov     [rbp+57h+var_88], r15
0x18001b8d1  lea     rdx, [rbp+57h+var_88]
0x18001b8d5  lea     rcx, [rbp+57h+var_60]
0x18001b8d9  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18001b8de  mov     ebx, eax
0x18001b8e0  test    eax, eax
0x18001b8e2  js      short loc_18001B90E
0x18001b8e4  mov     rdi, [rbp+57h+var_88]
0x18001b8e8  mov     rax, [rdi]
0x18001b8eb  mov     rbx, [rax+38h]
0x18001b8ef  mov     rcx, [rbp+57h+string]; string
0x18001b8f3  call    cs:__imp_WindowsDeleteString
0x18001b8f9  mov     [rbp+57h+string], r15
0x18001b8fd  lea     rdx, [rbp+57h+string]
0x18001b901  mov     rcx, rdi
0x18001b904  mov     rax, rbx
0x18001b907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b90c  mov     ebx, eax
0x18001b90e  lea     rcx, [rbp+57h+var_88]
0x18001b912  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b917  nop
0x18001b918  lea     rcx, [rbp+57h+var_90]
0x18001b91c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b921  nop
0x18001b922  lea     rcx, [rbp+57h+var_80]
0x18001b926  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b92b  test    ebx, ebx
0x18001b92d  js      loc_18001BACE
0x18001b933  mov     [rbp+57h+var_88], r15
0x18001b937  mov     [rbp+57h+var_40], r15
0x18001b93b  mov     r9d, 22h ; '"'; unsigned int
0x18001b941  lea     r8d, [r9+1]; unsigned int
0x18001b945  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpStringContent@@3QBGB; "Windows.Web.Http.HttpStringContent"
0x18001b94c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001b950  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001b955  mov     rbx, [rbp+57h+var_40]
0x18001b959  lea     rcx, [rbp+57h+var_88]
0x18001b95d  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b962  lea     r8, [rbp+57h+var_88]
0x18001b966  lea     rdx, _GUID_46649d5b_2e93_48eb_8e61_19677878e57f
0x18001b96d  mov     rcx, rbx
0x18001b970  call    cs:__imp_RoGetActivationFactory
0x18001b976  mov     ebx, eax
0x18001b978  test    eax, eax
0x18001b97a  js      loc_18001BAB6
0x18001b980  mov     rdi, [rbp+57h+var_88]
0x18001b984  mov     rax, [rdi]
0x18001b987  mov     rbx, [rax+30h]
0x18001b98b  lea     rcx, [rbp+57h+var_78]
0x18001b98f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b994  lea     r8, [rbp+57h+var_78]
0x18001b998  mov     rdx, [rbp+57h+string]
0x18001b99c  mov     rcx, rdi
0x18001b99f  mov     rax, rbx
0x18001b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9a7  mov     ebx, eax
0x18001b9a9  test    eax, eax
0x18001b9ab  js      loc_18001BAB6
0x18001b9b1  mov     [rbp+57h+var_90], r15
0x18001b9b5  mov     [rbp+57h+var_70], r15
0x18001b9b9  mov     [rbp+57h+var_80], r15
0x18001b9bd  mov     rdi, [rbp+57h+var_78]
0x18001b9c1  mov     rax, [rdi]
0x18001b9c4  mov     rbx, [rax+30h]
0x18001b9c8  lea     rcx, [rbp+57h+var_80]
0x18001b9cc  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b9d1  lea     rdx, [rbp+57h+var_80]
0x18001b9d5  mov     rcx, rdi
0x18001b9d8  mov     rax, rbx
0x18001b9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9e0  mov     ebx, eax
0x18001b9e2  test    eax, eax
0x18001b9e4  js      loc_18001BA98
0x18001b9ea  mov     [rbp+57h+var_40], r15
0x18001b9ee  mov     r9d, 31h ; '1'; unsigned int
0x18001b9f4  lea     r8d, [r9+1]; unsigned int
0x18001b9f8  lea     rdx, ?RuntimeClass_Windows_Web_Http_Headers_HttpMediaTypeHeaderValue@@3QBGB; "Windows.Web.Http.Headers.HttpMediaTypeH"...
0x18001b9ff  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001ba03  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ba08  mov     rbx, [rbp+57h+var_40]
0x18001ba0c  lea     rcx, [rbp+57h+var_90]
0x18001ba10  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ba15  lea     r8, [rbp+57h+var_90]
0x18001ba19  lea     rdx, _GUID_bed747a8_cd17_42dd_9367_ab9c5b56dd7d
0x18001ba20  mov     rcx, rbx
0x18001ba23  call    cs:__imp_RoGetActivationFactory
0x18001ba29  mov     ebx, eax
0x18001ba2b  test    eax, eax
0x18001ba2d  js      short loc_18001BA98
0x18001ba2f  mov     rdi, [rbp+57h+var_90]
0x18001ba33  mov     rax, [rdi]
0x18001ba36  mov     rbx, [rax+30h]
0x18001ba3a  lea     rcx, [rbp+57h+var_70]
0x18001ba3e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001ba43  mov     [rbp+57h+var_40], r15
0x18001ba47  mov     r9d, 10h; unsigned int
0x18001ba4d  lea     r8d, [r9+1]; unsigned int
0x18001ba51  lea     rdx, aApplicationJso; "application/json"
0x18001ba58  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001ba5c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ba61  nop
0x18001ba62  lea     r8, [rbp+57h+var_70]
0x18001ba66  mov     rdx, [rbp+57h+var_40]
0x18001ba6a  mov     rcx, rdi
0x18001ba6d  mov     rax, rbx
0x18001ba70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba75  mov     ebx, eax
0x18001ba77  test    eax, eax
0x18001ba79  js      short loc_18001BA98
0x18001ba7b  mov     rcx, [rbp+57h+var_80]
0x18001ba7f  mov     rax, [rcx]
0x18001ba82  mov     rdx, [rbp+57h+var_70]
0x18001ba86  mov     [rbp+57h+var_70], r15
0x18001ba8a  mov     rax, [rax+98h]
0x18001ba91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba96  mov     ebx, eax
0x18001ba98  lea     rcx, [rbp+57h+var_80]
0x18001ba9c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001baa1  nop
0x18001baa2  lea     rcx, [rbp+57h+var_70]
0x18001baa6  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001baab  nop
0x18001baac  lea     rcx, [rbp+57h+var_90]
0x18001bab0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bab5  nop
0x18001bab6  lea     rcx, [rbp+57h+var_88]
0x18001baba  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001babf  test    ebx, ebx
0x18001bac1  js      short loc_18001BACE
0x18001bac3  mov     rax, [rbp+57h+var_78]
0x18001bac7  mov     [rbp+57h+var_78], r15
0x18001bacb  mov     [r14], rax
0x18001bace  lea     rcx, [rbp+57h+var_78]
0x18001bad2  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bad7  nop
0x18001bad8  lea     rcx, [rbp+57h+var_60]
0x18001badc  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bae1  nop
0x18001bae2  mov     rcx, [rbp+57h+string]; string
0x18001bae6  call    cs:__imp_WindowsDeleteString
0x18001baec  mov     eax, ebx
0x18001baee  mov     rcx, [rbp+57h+var_38]
0x18001baf2  xor     rcx, rsp; StackCookie
0x18001baf5  call    __security_check_cookie
0x18001bafa  add     rsp, 88h
0x18001bb01  pop     r15
0x18001bb03  pop     r14
0x18001bb05  pop     rdi
0x18001bb06  pop     rsi
0x18001bb07  pop     rbx
0x18001bb08  pop     rbp
0x18001bb09  retn
```
