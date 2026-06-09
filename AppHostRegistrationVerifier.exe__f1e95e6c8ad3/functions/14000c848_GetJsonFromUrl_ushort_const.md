# GetJsonFromUrl(ushort const *)

- ea: `0x14000c848`
- end: `0x14000cc3a`
- name: `?GetJsonFromUrl@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `1010`
- prototype: `const WCHAR *__fastcall(const WCHAR *, const WCHAR *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000be20`
- `0x140011851`

## callees

- `0x140002210`
- `0x14000834c`
- `0x1400083ac`
- `0x140008814`
- `0x140008f1c`
- `0x1400090ac`
- `0x14000a04c`
- `0x14000ac20`
- `0x14000c848`
- `0x14000d49c`
- `0x14000fbb0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000cbd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000c8be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000c8be`

## string_xrefs

- `0x14000cb2e`: `Windows.Data.Json.JsonArray`
- `0x14000c892`: `Windows.Foundation.Uri`

## pseudocode

```c
const WCHAR *__fastcall GetJsonFromUrl(const WCHAR *a1, const WCHAR *a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD); // rbx
  int v11; // eax
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v13; // edx
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  const char *v17; // r9
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v23; // eax
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v25; // edx
  __int64 v26; // r8
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, const WCHAR *); // rbx
  int v31; // eax
  HSTRING string; // [rsp+20h] [rbp-49h] BYREF
  int v34; // [rsp+28h] [rbp-41h] BYREF
  __int64 v35; // [rsp+30h] [rbp-39h] BYREF
  int (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-31h] BYREF
  __int64 v37; // [rsp+40h] [rbp-29h] BYREF
  int (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-21h] BYREF
  __int64 v39; // [rsp+50h] [rbp-19h] BYREF
  __int64 v40; // [rsp+58h] [rbp-11h] BYREF
  int v41; // [rsp+60h] [rbp-9h]
  __int64 v42; // [rsp+68h] [rbp-1h] BYREF
  __int64 v43; // [rsp+70h] [rbp+7h] BYREF
  const WCHAR *v44[2]; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v46; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v44[1] = a1;
  v44[0] = a2;
  v41 = 0;
  v40 = 0;
  v46 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v3 = v46;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v40);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v40);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1DC,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
  v39 = 0;
  v5 = v40;
  v6 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v40 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v44);
  v8 = v6(v5, v7[1].Reserved.Reserved1, &v39);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1DE,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
  wil::ActivateInstance<Windows::Web::Http::IHttpClient>((__int64)&v43);
  v38 = 0;
  v9 = v43;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v43 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v38);
  v11 = v10(v9, v39, &v38);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
  v35 = 0;
  v12 = v38;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v35);
  v15 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(
          v12,
          v13,
          v14);
  if ( v15 >= 0 )
    v15 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v12)[10])(v12, &v35);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v15,
      (int)string);
  v34 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 128LL))(v35, &v34);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v16,
      (int)string);
  if ( v34 == 200 )
    v17 = 0;
  else
    v17 = (const char *)(v34 | 0x80190000);
  if ( (int)v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1EC,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      v17,
      (int)string);
  string = 0;
  v37 = 0;
  v18 = v35;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v37);
  v20 = v19(v18, &v37);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F1,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
  v36 = 0;
  v21 = v37;
  v22 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v37 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v36);
  v23 = v22(v21, &v36);
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v23,
      (int)string);
  WindowsDeleteString(string);
  string = 0;
  v24 = v36;
  v27 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(
          v36,
          v25,
          v26);
  if ( v27 >= 0 )
    v27 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v24)[10])(v24, &string);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v27,
      (int)string);
  v42 = 0;
  v46 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v28 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(
          v46,
          (__int64)&v42);
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F8,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v28,
      (int)string);
  *(_QWORD *)a1 = 0;
  v41 = 1;
  v29 = v42;
  v30 = *(__int64 (__fastcall **)(__int64, HSTRING, const WCHAR *))(*(_QWORD *)v42 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1);
  v31 = v30(v29, string, a1);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v31,
      (int)string);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v37);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v38);
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(&v43);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v40);
  return a1;
}

```

## disassembly

```asm
0x14000c848  mov     [rsp-8+arg_10], rbx
0x14000c84d  mov     [rsp-8+arg_18], rsi
0x14000c852  push    rbp
0x14000c853  push    rdi
0x14000c854  push    r14
0x14000c856  lea     rbp, [rsp-47h]
0x14000c85b  sub     rsp, 0B0h
0x14000c862  mov     rax, cs:__security_cookie
0x14000c869  xor     rax, rsp
0x14000c86c  mov     [rbp+57h+var_18], rax
0x14000c870  mov     rsi, rcx
0x14000c873  mov     [rbp+57h+var_40], rcx
0x14000c877  mov     [rbp+57h+var_48], rdx
0x14000c87b  xor     r14d, r14d
0x14000c87e  mov     [rbp+57h+var_60], r14d
0x14000c882  mov     [rbp+57h+var_68], r14
0x14000c886  mov     [rbp+57h+var_20], r14
0x14000c88a  lea     r9d, [r14+16h]; unsigned int
0x14000c88e  lea     r8d, [r14+17h]; unsigned int
0x14000c892  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x14000c899  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14000c89d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000c8a2  nop
0x14000c8a3  mov     rbx, [rbp+57h+var_20]
0x14000c8a7  lea     rcx, [rbp+57h+var_68]
0x14000c8ab  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c8b0  lea     r8, [rbp+57h+var_68]
0x14000c8b4  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x14000c8bb  mov     rcx, rbx
0x14000c8be  call    cs:__imp_RoGetActivationFactory
0x14000c8c4  mov     rcx, [rbp+5Fh]; this
0x14000c8c8  test    eax, eax
0x14000c8ca  jns     short loc_14000C8E1
0x14000c8cc  mov     r9d, eax; char *
0x14000c8cf  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c8d6  mov     edx, 1DCh; void *
0x14000c8db  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c8e1  mov     [rbp+57h+var_70], r14
0x14000c8e5  mov     rdi, [rbp+57h+var_68]
0x14000c8e9  mov     rax, [rdi]
0x14000c8ec  mov     rbx, [rax+30h]
0x14000c8f0  lea     rcx, [rbp+57h+var_70]
0x14000c8f4  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c8f9  lea     rdx, [rbp+57h+var_48]
0x14000c8fd  lea     rcx, [rbp+57h+hstringHeader]
0x14000c901  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000c906  nop
0x14000c907  lea     r8, [rbp+57h+var_70]
0x14000c90b  mov     rdx, [rax+18h]
0x14000c90f  mov     rcx, rdi
0x14000c912  mov     rax, rbx
0x14000c915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c91a  mov     rcx, [rbp+5Fh]; this
0x14000c91e  test    eax, eax
0x14000c920  jns     short loc_14000C937
0x14000c922  mov     r9d, eax; char *
0x14000c925  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c92c  mov     edx, 1DEh; void *
0x14000c931  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c937  lea     rcx, [rbp+57h+var_50]
0x14000c93b  call    ??$ActivateInstance@UIHttpClient@Http@Web@Windows@@@wil@@YA?AV?$com_ptr_t@UIHttpClient@Http@Web@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Web::Http::IHttpClient>(ushort const *)
0x14000c940  nop
0x14000c941  mov     [rbp+57h+var_78], r14
0x14000c945  mov     rdi, [rbp+57h+var_50]
0x14000c949  mov     rax, [rdi]
0x14000c94c  mov     rbx, [rax+38h]
0x14000c950  lea     rcx, [rbp+57h+var_78]
0x14000c954  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c959  lea     r8, [rbp+57h+var_78]
0x14000c95d  mov     rdx, [rbp+57h+var_70]
0x14000c961  mov     rcx, rdi
0x14000c964  mov     rax, rbx
0x14000c967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c96c  mov     rcx, [rbp+5Fh]; this
0x14000c970  test    eax, eax
0x14000c972  jns     short loc_14000C989
0x14000c974  mov     r9d, eax; char *
0x14000c977  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c97e  mov     edx, 1E3h; void *
0x14000c983  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c989  mov     [rbp+57h+var_90], r14
0x14000c98d  mov     rbx, [rbp+57h+var_78]
0x14000c991  lea     rcx, [rbp+57h+var_90]
0x14000c995  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c99a  mov     rcx, rbx
0x14000c99d  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)
0x14000c9a2  test    eax, eax
0x14000c9a4  js      short loc_14000C9B9
0x14000c9a6  mov     rax, [rbx]
0x14000c9a9  lea     rdx, [rbp+57h+var_90]
0x14000c9ad  mov     rcx, rbx
0x14000c9b0  mov     rax, [rax+50h]
0x14000c9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9b9  mov     rcx, [rbp+5Fh]; this
0x14000c9bd  test    eax, eax
0x14000c9bf  jns     short loc_14000C9D6
0x14000c9c1  mov     r9d, eax; char *
0x14000c9c4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c9cb  mov     edx, 1E7h; void *
0x14000c9d0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c9d6  mov     [rbp+57h+var_98], r14d
0x14000c9da  mov     rcx, [rbp+57h+var_90]
0x14000c9de  mov     rax, [rcx]
0x14000c9e1  lea     rdx, [rbp+57h+var_98]
0x14000c9e5  mov     rax, [rax+80h]
0x14000c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9f1  mov     rcx, [rbp+5Fh]; this
0x14000c9f5  test    eax, eax
0x14000c9f7  jns     short loc_14000CA0E
0x14000c9f9  mov     r9d, eax; char *
0x14000c9fc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ca03  mov     edx, 1EBh; void *
0x14000ca08  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ca0e  mov     r9d, [rbp+57h+var_98]
0x14000ca12  cmp     r9d, 0C8h
0x14000ca19  jnz     short loc_14000CA20
0x14000ca1b  mov     r9d, r14d
0x14000ca1e  jmp     short loc_14000CA27
0x14000ca20  or      r9d, 80190000h; char *
0x14000ca27  mov     rcx, [rbp+5Fh]; this
0x14000ca2b  test    r9d, r9d
0x14000ca2e  jns     short loc_14000CA42
0x14000ca30  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ca37  mov     edx, 1ECh; void *
0x14000ca3c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ca42  mov     [rbp+57h+string], r14
0x14000ca46  mov     [rbp+57h+var_80], r14
0x14000ca4a  mov     rdi, [rbp+57h+var_90]
0x14000ca4e  mov     rax, [rdi]
0x14000ca51  mov     rbx, [rax+30h]
0x14000ca55  lea     rcx, [rbp+57h+var_80]
0x14000ca59  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ca5e  lea     rdx, [rbp+57h+var_80]
0x14000ca62  mov     rcx, rdi
0x14000ca65  mov     rax, rbx
0x14000ca68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca6d  mov     rcx, [rbp+5Fh]; this
0x14000ca71  test    eax, eax
0x14000ca73  jns     short loc_14000CA8A
0x14000ca75  mov     r9d, eax; char *
0x14000ca78  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000ca7f  mov     edx, 1F1h; void *
0x14000ca84  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000ca8a  mov     [rbp+57h+var_88], r14
0x14000ca8e  mov     rdi, [rbp+57h+var_80]
0x14000ca92  mov     rax, [rdi]
0x14000ca95  mov     rbx, [rax+50h]
0x14000ca99  lea     rcx, [rbp+57h+var_88]
0x14000ca9d  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000caa2  lea     rdx, [rbp+57h+var_88]
0x14000caa6  mov     rcx, rdi
0x14000caa9  mov     rax, rbx
0x14000caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cab1  mov     rcx, [rbp+5Fh]; this
0x14000cab5  test    eax, eax
0x14000cab7  jns     short loc_14000CACE
0x14000cab9  mov     r9d, eax; char *
0x14000cabc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cac3  mov     edx, 1F4h; void *
0x14000cac8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cace  mov     rcx, [rbp+57h+string]; string
0x14000cad2  call    cs:__imp_WindowsDeleteString
0x14000cad8  mov     [rbp+57h+string], r14
0x14000cadc  mov     rbx, [rbp+57h+var_88]
0x14000cae0  mov     rcx, rbx
0x14000cae3  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x14000cae8  test    eax, eax
0x14000caea  js      short loc_14000CAFF
0x14000caec  mov     rax, [rbx]
0x14000caef  lea     rdx, [rbp+57h+string]
0x14000caf3  mov     rcx, rbx
0x14000caf6  mov     rax, [rax+50h]
0x14000cafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caff  mov     rcx, [rbp+5Fh]; this
0x14000cb03  test    eax, eax
0x14000cb05  jns     short loc_14000CB1C
0x14000cb07  mov     r9d, eax; char *
0x14000cb0a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cb11  mov     edx, 1F5h; void *
0x14000cb16  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cb1c  mov     [rbp+57h+var_58], r14
0x14000cb20  mov     [rbp+57h+var_20], r14
0x14000cb24  mov     r9d, 1Bh; unsigned int
0x14000cb2a  lea     r8d, [r9+1]; unsigned int
0x14000cb2e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x14000cb35  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14000cb39  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000cb3e  nop
0x14000cb3f  lea     rdx, [rbp+57h+var_58]
0x14000cb43  mov     rcx, [rbp+57h+var_20]
0x14000cb47  call    ??$GetActivationFactory@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>)
0x14000cb4c  mov     rcx, [rbp+5Fh]; this
0x14000cb50  test    eax, eax
0x14000cb52  jns     short loc_14000CB69
0x14000cb54  mov     r9d, eax; char *
0x14000cb57  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cb5e  mov     edx, 1F8h; void *
0x14000cb63  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cb69  mov     [rsi], r14
0x14000cb6c  mov     [rbp+57h+var_60], 1
0x14000cb73  mov     rdi, [rbp+57h+var_58]
0x14000cb77  mov     rax, [rdi]
0x14000cb7a  mov     rbx, [rax+30h]
0x14000cb7e  mov     rcx, rsi
0x14000cb81  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cb86  mov     r8, rsi
0x14000cb89  mov     rdx, [rbp+57h+string]
0x14000cb8d  mov     rcx, rdi
0x14000cb90  mov     rax, rbx
0x14000cb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb98  mov     rcx, [rbp+5Fh]; this
0x14000cb9c  test    eax, eax
0x14000cb9e  jns     short loc_14000CBB5
0x14000cba0  mov     r9d, eax; char *
0x14000cba3  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000cbaa  mov     edx, 1FAh; void *
0x14000cbaf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000cbb5  lea     rcx, [rbp+57h+var_58]
0x14000cbb9  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cbbe  nop
0x14000cbbf  lea     rcx, [rbp+57h+var_88]
0x14000cbc3  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cbc8  nop
0x14000cbc9  lea     rcx, [rbp+57h+var_80]
0x14000cbcd  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cbd2  nop
0x14000cbd3  mov     rcx, [rbp+57h+string]; string
0x14000cbd7  call    cs:__imp_WindowsDeleteString
0x14000cbdd  mov     [rbp+57h+string], r14
0x14000cbe1  lea     rcx, [rbp+57h+var_90]
0x14000cbe5  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cbea  nop
0x14000cbeb  lea     rcx, [rbp+57h+var_78]
0x14000cbef  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cbf4  nop
0x14000cbf5  lea     rcx, [rbp+57h+var_50]
0x14000cbf9  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x14000cbfe  nop
0x14000cbff  lea     rcx, [rbp+57h+var_70]
0x14000cc03  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cc08  nop
0x14000cc09  lea     rcx, [rbp+57h+var_68]
0x14000cc0d  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000cc12  mov     rax, rsi
0x14000cc15  mov     rcx, [rbp+57h+var_18]
0x14000cc19  xor     rcx, rsp; StackCookie
0x14000cc1c  call    __security_check_cookie
0x14000cc21  lea     r11, [rsp+0C0h+var_10]
0x14000cc29  mov     rbx, [r11+30h]
0x14000cc2d  mov     rsi, [r11+38h]
0x14000cc31  mov     rsp, r11
0x14000cc34  pop     r14
0x14000cc36  pop     rdi
0x14000cc37  pop     rbp
0x14000cc38  retn
```
