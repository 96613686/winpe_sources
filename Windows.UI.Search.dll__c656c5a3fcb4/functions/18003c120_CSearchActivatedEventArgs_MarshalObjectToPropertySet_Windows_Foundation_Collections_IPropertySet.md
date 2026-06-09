# CSearchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18003c120`
- end: `0x18003c52e`
- name: `?MarshalObjectToPropertySet@CSearchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1038`
- prototype: `__int64 __fastcall(CSearchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180009d6c`
- `0x18000f2a8`
- `0x18001e9a0`
- `0x18003c120`
- `0x1800412dc`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c26a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c26a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4df`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CSearchActivatedEventArgs::MarshalObjectToPropertySet(
        CSearchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(char *, __int64 *); // rbx
  int v10; // eax
  __int64 (__fastcall *v11)(char *, HSTRING *); // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(char *, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v25; // rbx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v32; // rbx
  int v34; // [rsp+20h] [rbp-39h]
  _BYTE v35[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v37; // [rsp+40h] [rbp-19h] BYREF
  __int64 v38; // [rsp+48h] [rbp-11h] BYREF
  __int64 v39; // [rsp+50h] [rbp-9h] BYREF
  __int64 v40; // [rsp+58h] [rbp-1h] BYREF
  __int64 v41; // [rsp+60h] [rbp+7h] BYREF
  __int64 v42; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v44; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
         (CSearchActivatedEventArgs *)((char *)this - 240),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v41 = 0;
    v42 = 0;
    v6 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v41);
    v7 = v6(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v41);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 106;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v7,
        v34);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v41);
      return v5;
    }
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v44,
           (__int64)&v42);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 107;
      goto LABEL_7;
    }
    v38 = 0;
    v9 = *(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this - 2) + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
    v10 = v9((char *)this - 16, &v38);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v10,
        v34);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
      goto LABEL_33;
    }
    string = 0;
    v11 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 1) + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11((char *)this - 8, &string);
    v5 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v12,
        v34);
LABEL_13:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_10;
    }
    v37 = 0;
    v13 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 1) + 56LL);
    WindowsDeleteString(0);
    v37 = 0;
    v14 = v13((char *)this - 8, &v37);
    v5 = v14;
    if ( v14 < 0 )
    {
      v15 = 116;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v14,
        v34);
LABEL_17:
      WindowsDeleteString(v37);
      v37 = 0;
      goto LABEL_13;
    }
    v35[0] = 0;
    v16 = v38;
    if ( v38 )
    {
      v17 = v41;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v41 + 80LL);
      v44 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"LinguisticDetails", 0x12u, 0x11u);
      v14 = v18(v17, v44, v16, v35);
      v5 = v14;
      if ( v14 < 0 )
      {
        v15 = 122;
        goto LABEL_16;
      }
    }
    v39 = 0;
    v19 = v42;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v42 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
    v21 = v20(v19, string, &v39);
    v5 = v21;
    if ( v21 >= 0 )
    {
      v23 = v41;
      v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v41 + 80LL);
      v25 = v39;
      v44 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Query", 6u, 5u);
      v21 = v24(v23, v44, v25, v35);
      v5 = v21;
      if ( v21 >= 0 )
      {
        v40 = 0;
        v26 = v42;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v42 + 144LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v40);
        v28 = v27(v26, v37, &v40);
        v5 = v28;
        if ( v28 >= 0 )
        {
          v30 = v41;
          v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v41 + 80LL);
          v32 = v40;
          v44 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Language", 9u, 8u);
          v28 = v31(v30, v44, v32, v35);
          v5 = v28;
          if ( v28 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
            WindowsDeleteString(v37);
            v37 = 0;
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
            v5 = 0;
            goto LABEL_33;
          }
          v29 = 131;
        }
        else
        {
          v29 = 130;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
          (const char *)(unsigned int)v28,
          v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v40);
        goto LABEL_24;
      }
      v22 = 127;
    }
    else
    {
      v22 = 126;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
      (const char *)(unsigned int)v21,
      v34);
LABEL_24:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65,
    (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
    (const char *)(unsigned int)v4,
    v34);
  return v5;
}

```

## disassembly

```asm
0x18003c120  mov     [rsp-8+arg_10], rbx
0x18003c125  mov     [rsp-8+arg_18], rsi
0x18003c12a  push    rbp
0x18003c12b  push    rdi
0x18003c12c  push    r14
0x18003c12e  lea     rbp, [rsp-47h]
0x18003c133  sub     rsp, 0A0h
0x18003c13a  mov     rax, cs:__security_cookie
0x18003c141  xor     rax, rsp
0x18003c144  mov     [rbp+57h+var_20], rax
0x18003c148  mov     rdi, rdx
0x18003c14b  mov     rsi, rcx
0x18003c14e  add     rcx, 0FFFFFFFFFFFFFF10h; this
0x18003c155  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18003c15a  mov     ebx, eax
0x18003c15c  xor     r14d, r14d
0x18003c15f  test    eax, eax
0x18003c161  jns     short loc_18003C17F
0x18003c163  mov     rcx, [rbp+5Fh]; this
0x18003c167  mov     r9d, eax; char *
0x18003c16a  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c171  lea     edx, [r14+65h]; void *
0x18003c175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c17a  jmp     loc_18003C508
0x18003c17f  mov     [rbp+57h+var_50], r14
0x18003c183  mov     [rbp+57h+var_48], r14
0x18003c187  mov     rax, [rdi]
0x18003c18a  mov     rbx, [rax]
0x18003c18d  lea     rcx, [rbp+57h+var_50]
0x18003c191  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c196  lea     r8, [rbp+57h+var_50]
0x18003c19a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18003c1a1  mov     rcx, rdi
0x18003c1a4  mov     rax, rbx
0x18003c1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1ac  mov     ebx, eax
0x18003c1ae  test    eax, eax
0x18003c1b0  jns     short loc_18003C1B9
0x18003c1b2  mov     edx, 6Ah ; 'j'
0x18003c1b7  jmp     short loc_18003C1EF
0x18003c1b9  mov     [rbp+57h+var_28], r14
0x18003c1bd  mov     r9d, 20h ; ' '; unsigned int
0x18003c1c3  lea     r8d, [r9+1]; unsigned int
0x18003c1c7  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18003c1ce  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003c1d2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c1d7  lea     rdx, [rbp+57h+var_48]
0x18003c1db  mov     rcx, [rbp+57h+var_28]
0x18003c1df  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18003c1e4  mov     ebx, eax
0x18003c1e6  test    eax, eax
0x18003c1e8  jns     short loc_18003C207
0x18003c1ea  mov     edx, 6Bh ; 'k'; void *
0x18003c1ef  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c1f6  mov     r9d, eax; char *
0x18003c1f9  mov     rcx, [rbp+5Fh]; this
0x18003c1fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c202  jmp     loc_18003C4F5
0x18003c207  mov     [rbp+57h+var_68], r14
0x18003c20b  mov     rax, [rsi-10h]
0x18003c20f  mov     rbx, [rax+30h]
0x18003c213  lea     rcx, [rbp+57h+var_68]
0x18003c217  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c21c  lea     rdx, [rbp+57h+var_68]
0x18003c220  lea     rcx, [rsi-10h]
0x18003c224  mov     rax, rbx
0x18003c227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c22c  mov     ebx, eax
0x18003c22e  test    eax, eax
0x18003c230  jns     short loc_18003C259
0x18003c232  mov     rcx, [rbp+5Fh]; this
0x18003c236  mov     r9d, eax; char *
0x18003c239  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c240  mov     edx, 6Eh ; 'n'; void *
0x18003c245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c24a  nop
0x18003c24b  lea     rcx, [rbp+57h+var_68]
0x18003c24f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c254  jmp     loc_18003C4F5
0x18003c259  mov     [rbp+57h+string], r14
0x18003c25d  lea     rdi, [rsi-8]
0x18003c261  mov     rax, [rdi]
0x18003c264  mov     rbx, [rax+30h]
0x18003c268  xor     ecx, ecx; string
0x18003c26a  call    cs:__imp_WindowsDeleteString
0x18003c270  mov     [rbp+57h+string], r14
0x18003c274  lea     rdx, [rbp+57h+string]
0x18003c278  mov     rcx, rdi
0x18003c27b  mov     rax, rbx
0x18003c27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c283  mov     ebx, eax
0x18003c285  test    eax, eax
0x18003c287  jns     short loc_18003C2B2
0x18003c289  mov     rcx, [rbp+5Fh]; this
0x18003c28d  mov     r9d, eax; char *
0x18003c290  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c297  mov     edx, 71h ; 'q'; void *
0x18003c29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2a1  nop
0x18003c2a2  mov     rcx, [rbp+57h+string]; string
0x18003c2a6  call    cs:__imp_WindowsDeleteString
0x18003c2ac  mov     [rbp+57h+string], r14
0x18003c2b0  jmp     short loc_18003C24B
0x18003c2b2  mov     [rbp+57h+var_70], r14
0x18003c2b6  mov     rax, [rdi]
0x18003c2b9  mov     rbx, [rax+38h]
0x18003c2bd  xor     ecx, ecx; string
0x18003c2bf  call    cs:__imp_WindowsDeleteString
0x18003c2c5  mov     [rbp+57h+var_70], r14
0x18003c2c9  lea     rdx, [rbp+57h+var_70]
0x18003c2cd  mov     rcx, rdi
0x18003c2d0  mov     rax, rbx
0x18003c2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2d8  mov     ebx, eax
0x18003c2da  test    eax, eax
0x18003c2dc  jns     short loc_18003C307
0x18003c2de  mov     edx, 74h ; 't'; void *
0x18003c2e3  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c2ea  mov     r9d, eax; char *
0x18003c2ed  mov     rcx, [rbp+5Fh]; this
0x18003c2f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2f6  nop
0x18003c2f7  mov     rcx, [rbp+57h+var_70]; string
0x18003c2fb  call    cs:__imp_WindowsDeleteString
0x18003c301  mov     [rbp+57h+var_70], r14
0x18003c305  jmp     short loc_18003C2A2
0x18003c307  mov     [rbp+57h+var_80], r14b
0x18003c30b  mov     rbx, [rbp+57h+var_68]
0x18003c30f  test    rbx, rbx
0x18003c312  jz      short loc_18003C361
0x18003c314  mov     rsi, [rbp+57h+var_50]
0x18003c318  mov     rax, [rsi]
0x18003c31b  mov     rdi, [rax+50h]
0x18003c31f  mov     [rbp+57h+var_28], r14
0x18003c323  mov     r9d, 11h; unsigned int
0x18003c329  lea     r8d, [r9+1]; unsigned int
0x18003c32d  lea     rdx, aLinguisticdeta; "LinguisticDetails"
0x18003c334  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003c338  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c33d  nop
0x18003c33e  lea     r9, [rbp+57h+var_80]
0x18003c342  mov     r8, rbx
0x18003c345  mov     rdx, [rbp+57h+var_28]
0x18003c349  mov     rcx, rsi
0x18003c34c  mov     rax, rdi
0x18003c34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c354  mov     ebx, eax
0x18003c356  test    eax, eax
0x18003c358  jns     short loc_18003C361
0x18003c35a  mov     edx, 7Ah ; 'z'
0x18003c35f  jmp     short loc_18003C2E3
0x18003c361  mov     [rbp+57h+var_60], r14
0x18003c365  mov     rdi, [rbp+57h+var_48]
0x18003c369  mov     rax, [rdi]
0x18003c36c  mov     rbx, [rax+90h]
0x18003c373  lea     rcx, [rbp+57h+var_60]
0x18003c377  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c37c  lea     r8, [rbp+57h+var_60]
0x18003c380  mov     rdx, [rbp+57h+string]
0x18003c384  mov     rcx, rdi
0x18003c387  mov     rax, rbx
0x18003c38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c38f  mov     ebx, eax
0x18003c391  test    eax, eax
0x18003c393  jns     short loc_18003C3BC
0x18003c395  mov     edx, 7Eh ; '~'; void *
0x18003c39a  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c3a1  mov     r9d, eax; char *
0x18003c3a4  mov     rcx, [rbp+5Fh]; this
0x18003c3a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3ad  nop
0x18003c3ae  lea     rcx, [rbp+57h+var_60]
0x18003c3b2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c3b7  jmp     loc_18003C2F7
0x18003c3bc  mov     rsi, [rbp+57h+var_50]
0x18003c3c0  mov     rax, [rsi]
0x18003c3c3  mov     rdi, [rax+50h]
0x18003c3c7  mov     rbx, [rbp+57h+var_60]
0x18003c3cb  mov     [rbp+57h+var_28], r14
0x18003c3cf  mov     r9d, 5; unsigned int
0x18003c3d5  lea     r8d, [r9+1]; unsigned int
0x18003c3d9  lea     rdx, aQuery; "Query"
0x18003c3e0  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003c3e4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c3e9  nop
0x18003c3ea  lea     r9, [rbp+57h+var_80]
0x18003c3ee  mov     r8, rbx
0x18003c3f1  mov     rdx, [rbp+57h+var_28]
0x18003c3f5  mov     rcx, rsi
0x18003c3f8  mov     rax, rdi
0x18003c3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c400  mov     ebx, eax
0x18003c402  test    eax, eax
0x18003c404  jns     short loc_18003C40D
0x18003c406  mov     edx, 7Fh
0x18003c40b  jmp     short loc_18003C39A
0x18003c40d  mov     [rbp+57h+var_58], r14
0x18003c411  mov     rdi, [rbp+57h+var_48]
0x18003c415  mov     rax, [rdi]
0x18003c418  mov     rbx, [rax+90h]
0x18003c41f  lea     rcx, [rbp+57h+var_58]
0x18003c423  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c428  lea     r8, [rbp+57h+var_58]
0x18003c42c  mov     rdx, [rbp+57h+var_70]
0x18003c430  mov     rcx, rdi
0x18003c433  mov     rax, rbx
0x18003c436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c43b  mov     ebx, eax
0x18003c43d  test    eax, eax
0x18003c43f  jns     short loc_18003C468
0x18003c441  mov     edx, 82h; void *
0x18003c446  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003c44d  mov     r9d, eax; char *
0x18003c450  mov     rcx, [rbp+5Fh]; this
0x18003c454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c459  nop
0x18003c45a  lea     rcx, [rbp+57h+var_58]
0x18003c45e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c463  jmp     loc_18003C3AE
0x18003c468  mov     rsi, [rbp+57h+var_50]
0x18003c46c  mov     rax, [rsi]
0x18003c46f  mov     rdi, [rax+50h]
0x18003c473  mov     rbx, [rbp+57h+var_58]
0x18003c477  mov     [rbp+57h+var_28], r14
0x18003c47b  mov     r9d, 8; unsigned int
0x18003c481  lea     r8d, [r9+1]; unsigned int
0x18003c485  lea     rdx, aLanguage; "Language"
0x18003c48c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003c490  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c495  nop
0x18003c496  lea     r9, [rbp+57h+var_80]
0x18003c49a  mov     r8, rbx
0x18003c49d  mov     rdx, [rbp+57h+var_28]
0x18003c4a1  mov     rcx, rsi
0x18003c4a4  mov     rax, rdi
0x18003c4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ac  mov     ebx, eax
0x18003c4ae  test    eax, eax
0x18003c4b0  jns     short loc_18003C4B9
0x18003c4b2  mov     edx, 83h
0x18003c4b7  jmp     short loc_18003C446
0x18003c4b9  lea     rcx, [rbp+57h+var_58]
0x18003c4bd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c4c2  nop
0x18003c4c3  lea     rcx, [rbp+57h+var_60]
0x18003c4c7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c4cc  nop
0x18003c4cd  mov     rcx, [rbp+57h+var_70]; string
0x18003c4d1  call    cs:__imp_WindowsDeleteString
0x18003c4d7  mov     [rbp+57h+var_70], r14
0x18003c4db  mov     rcx, [rbp+57h+string]; string
0x18003c4df  call    cs:__imp_WindowsDeleteString
0x18003c4e5  mov     [rbp+57h+string], r14
0x18003c4e9  lea     rcx, [rbp+57h+var_68]
0x18003c4ed  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c4f2  mov     ebx, r14d
0x18003c4f5  lea     rcx, [rbp+57h+var_48]
0x18003c4f9  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c4fe  nop
0x18003c4ff  lea     rcx, [rbp+57h+var_50]
0x18003c503  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003c508  mov     eax, ebx
0x18003c50a  mov     rcx, [rbp+57h+var_20]
0x18003c50e  xor     rcx, rsp; StackCookie
0x18003c511  call    __security_check_cookie
0x18003c516  lea     r11, [rsp+0B0h+var_10]
0x18003c51e  mov     rbx, [r11+30h]
0x18003c522  mov     rsi, [r11+38h]
0x18003c526  mov     rsp, r11
0x18003c529  pop     r14
0x18003c52b  pop     rdi
0x18003c52c  pop     rbp
0x18003c52d  retn
```
