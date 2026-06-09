# HelperClass::SetNamedString(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)

- ea: `0x18001c144`
- end: `0x18001c25e`
- name: `?SetNamedString@HelperClass@@SAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b80`

## callees

- `0x180003fc0`
- `0x18000517c`
- `0x18000ade0`
- `0x180014044`
- `0x18001c144`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c1b9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c1b9`

## string_xrefs

- `0x18001c18e`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HelperClass::SetNamedString(
        struct Windows::Data::Json::IJsonObject *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64); // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v13; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  const unsigned __int16 *v15; // [rsp+30h] [rbp-40h] BYREF
  const unsigned __int16 *v16; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h]

  v16 = a2;
  v15 = a3;
  v14 = 0;
  v13 = 0;
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v4 = v18;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v14);
  if ( ActivationFactory >= 0 )
  {
    v6 = v14;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v15);
    ActivationFactory = v7(v6, *(_QWORD *)(v8 + 24), &v13);
    if ( ActivationFactory >= 0 )
    {
      v9 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64))(*(_QWORD *)a1 + 56LL);
      v10 = v13;
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v16);
      ActivationFactory = v9(a1, *(_QWORD *)(v11 + 24), v10);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001c144  mov     [rsp-18h+arg_18], rbx
0x18001c149  push    rbp
0x18001c14a  push    rsi
0x18001c14b  push    rdi
0x18001c14c  mov     rbp, rsp
0x18001c14f  sub     rsp, 70h
0x18001c153  mov     rax, cs:__security_cookie
0x18001c15a  xor     rax, rsp
0x18001c15d  mov     [rbp+var_10], rax
0x18001c161  mov     rsi, rcx
0x18001c164  mov     [rbp+var_38], rdx
0x18001c168  mov     [rbp+var_40], r8
0x18001c16c  mov     [rbp+var_48], 0
0x18001c174  mov     [rbp+var_50], 0
0x18001c17c  mov     [rbp+var_18], 0
0x18001c184  mov     r9d, 1Bh; unsigned int
0x18001c18a  lea     r8d, [r9+1]; unsigned int
0x18001c18e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001c195  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001c199  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c19e  mov     rbx, [rbp+var_18]
0x18001c1a2  lea     rcx, [rbp+var_48]
0x18001c1a6  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001c1ab  lea     r8, [rbp+var_48]
0x18001c1af  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001c1b6  mov     rcx, rbx
0x18001c1b9  call    cs:__imp_RoGetActivationFactory
0x18001c1bf  mov     ebx, eax
0x18001c1c1  test    eax, eax
0x18001c1c3  js      short loc_18001C22D
0x18001c1c5  mov     rdi, [rbp+var_48]
0x18001c1c9  mov     rax, [rdi]
0x18001c1cc  mov     rbx, [rax+50h]
0x18001c1d0  lea     rcx, [rbp+var_50]
0x18001c1d4  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001c1d9  lea     rdx, [rbp+var_40]
0x18001c1dd  lea     rcx, [rbp+hstringHeader]
0x18001c1e1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c1e6  nop
0x18001c1e7  lea     r8, [rbp+var_50]
0x18001c1eb  mov     rdx, [rax+18h]
0x18001c1ef  mov     rcx, rdi
0x18001c1f2  mov     rax, rbx
0x18001c1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1fa  mov     ebx, eax
0x18001c1fc  test    eax, eax
0x18001c1fe  js      short loc_18001C22D
0x18001c200  mov     rax, [rsi]
0x18001c203  mov     rdi, [rax+38h]
0x18001c207  mov     rbx, [rbp+var_50]
0x18001c20b  lea     rdx, [rbp+var_38]
0x18001c20f  lea     rcx, [rbp+hstringHeader]
0x18001c213  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c218  nop
0x18001c219  mov     r8, rbx
0x18001c21c  mov     rdx, [rax+18h]
0x18001c220  mov     rcx, rsi
0x18001c223  mov     rax, rdi
0x18001c226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c22b  mov     ebx, eax
0x18001c22d  lea     rcx, [rbp+var_50]
0x18001c231  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001c236  nop
0x18001c237  lea     rcx, [rbp+var_48]
0x18001c23b  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001c240  mov     eax, ebx
0x18001c242  mov     rcx, [rbp+var_10]
0x18001c246  xor     rcx, rsp; StackCookie
0x18001c249  call    __security_check_cookie
0x18001c24e  mov     rbx, [rsp+70h+arg_18]
0x18001c256  add     rsp, 70h
0x18001c25a  pop     rdi
0x18001c25b  pop     rsi
0x18001c25c  pop     rbp
0x18001c25d  retn
```
