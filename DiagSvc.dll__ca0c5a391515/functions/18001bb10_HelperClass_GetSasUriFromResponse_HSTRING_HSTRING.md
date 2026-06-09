# HelperClass::GetSasUriFromResponse(HSTRING__ *,HSTRING__ * *)

- ea: `0x18001bb10`
- end: `0x18001bc73`
- name: `?GetSasUriFromResponse@HelperClass@@SAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `355`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015978`

## callees

- `0x180003fc0`
- `0x18000517c`
- `0x18000ade0`
- `0x180014044`
- `0x18001bb10`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bc2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bc2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bba0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bba0`

## string_xrefs

- `0x18001bb75`: `Windows.Data.Json.JsonObject`
- `0x18001bb58`: `packageSasUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HelperClass::GetSasUriFromResponse(HSTRING a1, HSTRING *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v10; // rax
  HSTRING v11; // rax
  HSTRING v12; // rcx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  const wchar_t *v17; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]

  v16 = 0;
  v15 = 0;
  string = 0;
  *a2 = 0;
  v17 = L"packageSasUri";
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = v19;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v16);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v16);
  if ( ActivationFactory < 0 )
    goto LABEL_5;
  v6 = v16;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v16 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
  ActivationFactory = v7(v6, a1, &v15);
  if ( ActivationFactory < 0
    || (v8 = v15,
        v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL),
        WindowsDeleteString(string),
        string = 0,
        v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v17),
        ActivationFactory = v9(v8, *(_QWORD *)(v10 + 24), &string),
        ActivationFactory < 0) )
  {
LABEL_5:
    v12 = string;
  }
  else
  {
    v11 = string;
    v12 = 0;
    string = 0;
    *a2 = v11;
  }
  WindowsDeleteString(v12);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v16);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001bb10  mov     [rsp-18h+arg_10], rbx
0x18001bb15  mov     [rsp-18h+arg_18], rsi
0x18001bb1a  push    rbp
0x18001bb1b  push    rdi
0x18001bb1c  push    r14
0x18001bb1e  mov     rbp, rsp
0x18001bb21  sub     rsp, 70h
0x18001bb25  mov     rax, cs:__security_cookie
0x18001bb2c  xor     rax, rsp
0x18001bb2f  mov     [rbp+var_10], rax
0x18001bb33  mov     rsi, rdx
0x18001bb36  mov     r14, rcx
0x18001bb39  mov     [rbp+var_40], 0
0x18001bb41  mov     [rbp+var_48], 0
0x18001bb49  mov     [rbp+string], 0
0x18001bb51  mov     qword ptr [rdx], 0
0x18001bb58  lea     rax, aPackagesasuri; "packageSasUri"
0x18001bb5f  mov     [rbp+var_38], rax
0x18001bb63  mov     [rbp+var_18], 0
0x18001bb6b  mov     r9d, 1Ch; unsigned int
0x18001bb71  lea     r8d, [r9+1]; unsigned int
0x18001bb75  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001bb7c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001bb80  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001bb85  mov     rbx, [rbp+var_18]
0x18001bb89  lea     rcx, [rbp+var_40]
0x18001bb8d  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bb92  lea     r8, [rbp+var_40]
0x18001bb96  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001bb9d  mov     rcx, rbx
0x18001bba0  call    cs:__imp_RoGetActivationFactory
0x18001bba6  mov     ebx, eax
0x18001bba8  test    eax, eax
0x18001bbaa  js      short loc_18001BC2B
0x18001bbac  mov     rdi, [rbp+var_40]
0x18001bbb0  mov     rax, [rdi]
0x18001bbb3  mov     rbx, [rax+30h]
0x18001bbb7  lea     rcx, [rbp+var_48]
0x18001bbbb  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bbc0  lea     r8, [rbp+var_48]
0x18001bbc4  mov     rdx, r14
0x18001bbc7  mov     rcx, rdi
0x18001bbca  mov     rax, rbx
0x18001bbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd2  mov     ebx, eax
0x18001bbd4  test    eax, eax
0x18001bbd6  js      short loc_18001BC2B
0x18001bbd8  mov     rdi, [rbp+var_48]
0x18001bbdc  mov     rax, [rdi]
0x18001bbdf  mov     rbx, [rax+50h]
0x18001bbe3  mov     rcx, [rbp+string]; string
0x18001bbe7  call    cs:__imp_WindowsDeleteString
0x18001bbed  mov     [rbp+string], 0
0x18001bbf5  lea     rdx, [rbp+var_38]
0x18001bbf9  lea     rcx, [rbp+hstringHeader]
0x18001bbfd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001bc02  nop
0x18001bc03  lea     r8, [rbp+string]
0x18001bc07  mov     rdx, [rax+18h]
0x18001bc0b  mov     rcx, rdi
0x18001bc0e  mov     rax, rbx
0x18001bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc16  mov     ebx, eax
0x18001bc18  test    eax, eax
0x18001bc1a  js      short loc_18001BC2B
0x18001bc1c  mov     rax, [rbp+string]
0x18001bc20  xor     ecx, ecx
0x18001bc22  mov     [rbp+string], rcx
0x18001bc26  mov     [rsi], rax
0x18001bc29  jmp     short loc_18001BC2F
0x18001bc2b  mov     rcx, [rbp+string]; string
0x18001bc2f  call    cs:__imp_WindowsDeleteString
0x18001bc35  mov     [rbp+string], 0
0x18001bc3d  lea     rcx, [rbp+var_48]
0x18001bc41  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bc46  nop
0x18001bc47  lea     rcx, [rbp+var_40]
0x18001bc4b  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bc50  mov     eax, ebx
0x18001bc52  mov     rcx, [rbp+var_10]
0x18001bc56  xor     rcx, rsp; StackCookie
0x18001bc59  call    __security_check_cookie
0x18001bc5e  lea     r11, [rsp+70h+var_s0]
0x18001bc63  mov     rbx, [r11+30h]
0x18001bc67  mov     rsi, [r11+38h]
0x18001bc6b  mov     rsp, r11
0x18001bc6e  pop     r14
0x18001bc70  pop     rdi
0x18001bc71  pop     rbp
0x18001bc72  retn
```
