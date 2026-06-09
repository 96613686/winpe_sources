# CSearchActivatedEventArgs::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18003ca00`
- end: `0x18003ce0e`
- name: `?RuntimeClassInitialize@CSearchActivatedEventArgs@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1038`
- prototype: `__int64 __fastcall(CSearchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d3e8`

## callees

- `0x180007b3c`
- `0x180009d6c`
- `0x18000f2a8`
- `0x18003a1e0`
- `0x18003ca00`
- `0x18003ce14`
- `0x180042160`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cbd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ccd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cbd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cc31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ccd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cd5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cd6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cd5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cd6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CSearchActivatedEventArgs::RuntimeClassInitialize(
        CSearchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **); // rdi
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, _QWORD); // rbx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *v27; // rdi
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v29; // rax
  HSTRING string; // [rsp+20h] [rbp-29h] BYREF
  HSTRING v32; // [rsp+28h] [rbp-21h] BYREF
  struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *v33; // [rsp+30h] [rbp-19h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **); // [rsp+38h] [rbp-11h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-9h] BYREF
  __int64 v36; // [rsp+48h] [rbp-1h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp+7h] BYREF
  __int64 v38; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v39; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v41; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithViewIdBase::RuntimeClassInitialize(this, a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v38 = 0;
    v6 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
    v7 = v6(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v38);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v7,
        (int)string);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v38);
      return v5;
    }
    v34 = 0;
    v33 = 0;
    v8 = v38;
    v9 = *(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v34);
    v41 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"LinguisticDetails", 0x12u, 0x11u);
    if ( v9(v8, v41, &v34) >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
      v11 = **v34;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v33);
      v12 = v11(v10, &GUID_82fb460e_0940_4b6d_b8d0_642b30989e15, &v33);
      v5 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
          (const char *)(unsigned int)v12,
          (int)string);
LABEL_8:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v34);
        goto LABEL_27;
      }
    }
    string = 0;
    v35 = 0;
    v13 = v38;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v35);
    v41 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Query", 6u, 5u);
    v15 = v14(v13, v41, &v35);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
        (const char *)(unsigned int)v15,
        (int)string);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v35);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_8;
    }
    v36 = 0;
    v16 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v35, (__int64)&v36);
    v5 = v16;
    if ( v16 >= 0 )
    {
      v18 = v36;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 152LL);
      WindowsDeleteString(string);
      string = 0;
      v16 = v19(v18, &string);
      v5 = v16;
      if ( v16 >= 0 )
      {
        v32 = 0;
        v37 = 0;
        v20 = v38;
        v21 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
        v41 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Language", 9u, 8u);
        v22 = v21(v20, v41, &v37);
        v5 = v22;
        if ( v22 >= 0 )
        {
          v39 = 0;
          v23 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v37, (__int64)&v39);
          v5 = v23;
          if ( v23 >= 0 )
          {
            v25 = v39;
            v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 152LL);
            WindowsDeleteString(v32);
            v32 = 0;
            v23 = v26(v25, &v32);
            v5 = v23;
            if ( v23 >= 0 )
            {
              v27 = v33;
              StringRawBuffer = WindowsGetStringRawBuffer(v32, 0);
              v29 = WindowsGetStringRawBuffer(string, 0);
              CSearchActivatedEventArgs::RuntimeClassInitialize(this, v29, StringRawBuffer, v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
              WindowsDeleteString(v32);
              v32 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v35);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v33);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v34);
              v5 = 0;
              goto LABEL_27;
            }
            v24 = 92;
          }
          else
          {
            v24 = 91;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
            (const char *)(unsigned int)v23,
            (int)string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
            (const char *)(unsigned int)v22,
            (int)string);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v37);
        WindowsDeleteString(v32);
        v32 = 0;
        goto LABEL_15;
      }
      v17 = 85;
    }
    else
    {
      v17 = 84;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
      (const char *)(unsigned int)v16,
      (int)string);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v36);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x44,
    (unsigned int)"shell\\searchui\\abi\\base\\appactivation.cpp",
    (const char *)(unsigned int)v4,
    (int)string);
  return v5;
}

```

## disassembly

```asm
0x18003ca00  mov     [rsp-8+arg_10], rbx
0x18003ca05  mov     [rsp-8+arg_18], rsi
0x18003ca0a  push    rbp
0x18003ca0b  push    rdi
0x18003ca0c  push    r14
0x18003ca0e  lea     rbp, [rsp-47h]
0x18003ca13  sub     rsp, 90h
0x18003ca1a  mov     rax, cs:__security_cookie
0x18003ca21  xor     rax, rsp
0x18003ca24  mov     [rbp+57h+var_18], rax
0x18003ca28  mov     rdi, rdx
0x18003ca2b  mov     rsi, rcx
0x18003ca2e  call    ?RuntimeClassInitialize@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)
0x18003ca33  mov     ebx, eax
0x18003ca35  xor     r14d, r14d
0x18003ca38  test    eax, eax
0x18003ca3a  jns     short loc_18003CA58
0x18003ca3c  mov     rcx, [rbp+5Fh]; this
0x18003ca40  mov     r9d, eax; char *
0x18003ca43  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003ca4a  lea     edx, [r14+44h]; void *
0x18003ca4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca53  jmp     loc_18003CDE8
0x18003ca58  mov     [rbp+57h+var_48], r14
0x18003ca5c  mov     rax, [rdi]
0x18003ca5f  mov     rbx, [rax]
0x18003ca62  lea     rcx, [rbp+57h+var_48]
0x18003ca66  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003ca6b  lea     r8, [rbp+57h+var_48]
0x18003ca6f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18003ca76  mov     rcx, rdi
0x18003ca79  mov     rax, rbx
0x18003ca7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca81  mov     ebx, eax
0x18003ca83  test    eax, eax
0x18003ca85  jns     short loc_18003CAA4
0x18003ca87  mov     rcx, [rbp+5Fh]; this
0x18003ca8b  mov     r9d, eax; char *
0x18003ca8e  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003ca95  mov     edx, 47h ; 'G'; void *
0x18003ca9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca9f  jmp     loc_18003CDDF
0x18003caa4  mov     [rbp+57h+var_68], r14
0x18003caa8  mov     [rbp+57h+var_70], r14
0x18003caac  mov     rdi, [rbp+57h+var_48]
0x18003cab0  mov     rax, [rdi]
0x18003cab3  mov     rbx, [rax+30h]
0x18003cab7  lea     rcx, [rbp+57h+var_68]
0x18003cabb  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cac0  mov     [rbp+57h+var_20], r14
0x18003cac4  mov     r9d, 11h; unsigned int
0x18003caca  lea     r8d, [r9+1]; unsigned int
0x18003cace  lea     rdx, aLinguisticdeta; "LinguisticDetails"
0x18003cad5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003cad9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003cade  nop
0x18003cadf  lea     r8, [rbp+57h+var_68]
0x18003cae3  mov     rdx, [rbp+57h+var_20]
0x18003cae7  mov     rcx, rdi
0x18003caea  mov     rax, rbx
0x18003caed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003caf2  nop
0x18003caf3  shr     eax, 1Fh
0x18003caf6  xor     al, 1
0x18003caf8  jz      short loc_18003CB5A
0x18003cafa  mov     rbx, [rbp+57h+var_68]
0x18003cafe  mov     rax, [rbx]
0x18003cb01  mov     rdi, [rax]
0x18003cb04  lea     rcx, [rbp+57h+var_70]
0x18003cb08  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cb0d  lea     r8, [rbp+57h+var_70]
0x18003cb11  lea     rdx, _GUID_82fb460e_0940_4b6d_b8d0_642b30989e15
0x18003cb18  mov     rcx, rbx
0x18003cb1b  mov     rax, rdi
0x18003cb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb23  mov     ebx, eax
0x18003cb25  test    eax, eax
0x18003cb27  jns     short loc_18003CB5A
0x18003cb29  mov     rcx, [rbp+5Fh]; this
0x18003cb2d  mov     r9d, eax; char *
0x18003cb30  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003cb37  mov     edx, 4Dh ; 'M'; void *
0x18003cb3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb41  nop
0x18003cb42  lea     rcx, [rbp+57h+var_70]
0x18003cb46  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cb4b  nop
0x18003cb4c  lea     rcx, [rbp+57h+var_68]
0x18003cb50  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cb55  jmp     loc_18003CDDF
0x18003cb5a  mov     [rbp+57h+string], r14
0x18003cb5e  mov     [rbp+57h+var_60], r14
0x18003cb62  mov     rdi, [rbp+57h+var_48]
0x18003cb66  mov     rax, [rdi]
0x18003cb69  mov     rbx, [rax+30h]
0x18003cb6d  lea     rcx, [rbp+57h+var_60]
0x18003cb71  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cb76  mov     [rbp+57h+var_20], r14
0x18003cb7a  mov     r9d, 5; unsigned int
0x18003cb80  lea     r8d, [r9+1]; unsigned int
0x18003cb84  lea     rdx, aQuery; "Query"
0x18003cb8b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003cb8f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003cb94  nop
0x18003cb95  lea     r8, [rbp+57h+var_60]
0x18003cb99  mov     rdx, [rbp+57h+var_20]
0x18003cb9d  mov     rcx, rdi
0x18003cba0  mov     rax, rbx
0x18003cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cba8  mov     ebx, eax
0x18003cbaa  test    eax, eax
0x18003cbac  jns     short loc_18003CBE4
0x18003cbae  mov     rcx, [rbp+5Fh]; this
0x18003cbb2  mov     r9d, eax; char *
0x18003cbb5  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003cbbc  mov     edx, 52h ; 'R'; void *
0x18003cbc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cbc6  nop
0x18003cbc7  lea     rcx, [rbp+57h+var_60]
0x18003cbcb  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cbd0  nop
0x18003cbd1  mov     rcx, [rbp+57h+string]; string
0x18003cbd5  call    cs:__imp_WindowsDeleteString
0x18003cbdb  mov     [rbp+57h+string], r14
0x18003cbdf  jmp     loc_18003CB42
0x18003cbe4  mov     [rbp+57h+var_58], r14
0x18003cbe8  lea     rdx, [rbp+57h+var_58]
0x18003cbec  lea     rcx, [rbp+57h+var_60]
0x18003cbf0  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18003cbf5  mov     ebx, eax
0x18003cbf7  test    eax, eax
0x18003cbf9  jns     short loc_18003CC1F
0x18003cbfb  mov     edx, 54h ; 'T'; void *
0x18003cc00  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003cc07  mov     r9d, eax; char *
0x18003cc0a  mov     rcx, [rbp+5Fh]; this
0x18003cc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cc13  nop
0x18003cc14  lea     rcx, [rbp+57h+var_58]
0x18003cc18  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cc1d  jmp     short loc_18003CBC7
0x18003cc1f  mov     rdi, [rbp+57h+var_58]
0x18003cc23  mov     rax, [rdi]
0x18003cc26  mov     rbx, [rax+98h]
0x18003cc2d  mov     rcx, [rbp+57h+string]; string
0x18003cc31  call    cs:__imp_WindowsDeleteString
0x18003cc37  mov     [rbp+57h+string], r14
0x18003cc3b  lea     rdx, [rbp+57h+string]
0x18003cc3f  mov     rcx, rdi
0x18003cc42  mov     rax, rbx
0x18003cc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc4a  mov     ebx, eax
0x18003cc4c  test    eax, eax
0x18003cc4e  jns     short loc_18003CC57
0x18003cc50  mov     edx, 55h ; 'U'
0x18003cc55  jmp     short loc_18003CC00
0x18003cc57  mov     [rbp+57h+var_78], r14
0x18003cc5b  mov     [rbp+57h+var_50], r14
0x18003cc5f  mov     rdi, [rbp+57h+var_48]
0x18003cc63  mov     rax, [rdi]
0x18003cc66  mov     rbx, [rax+30h]
0x18003cc6a  lea     rcx, [rbp+57h+var_50]
0x18003cc6e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cc73  mov     [rbp+57h+var_20], r14
0x18003cc77  mov     r9d, 8; unsigned int
0x18003cc7d  lea     r8d, [r9+1]; unsigned int
0x18003cc81  lea     rdx, aLanguage; "Language"
0x18003cc88  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003cc8c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003cc91  nop
0x18003cc92  lea     r8, [rbp+57h+var_50]
0x18003cc96  mov     rdx, [rbp+57h+var_20]
0x18003cc9a  mov     rcx, rdi
0x18003cc9d  mov     rax, rbx
0x18003cca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cca5  mov     ebx, eax
0x18003cca7  test    eax, eax
0x18003cca9  jns     short loc_18003CCE1
0x18003ccab  mov     rcx, [rbp+5Fh]; this
0x18003ccaf  mov     r9d, eax; char *
0x18003ccb2  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003ccb9  mov     edx, 59h ; 'Y'; void *
0x18003ccbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ccc3  nop
0x18003ccc4  lea     rcx, [rbp+57h+var_50]
0x18003ccc8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cccd  nop
0x18003ccce  mov     rcx, [rbp+57h+var_78]; string
0x18003ccd2  call    cs:__imp_WindowsDeleteString
0x18003ccd8  mov     [rbp+57h+var_78], r14
0x18003ccdc  jmp     loc_18003CC14
0x18003cce1  mov     [rbp+57h+var_40], r14
0x18003cce5  lea     rdx, [rbp+57h+var_40]
0x18003cce9  lea     rcx, [rbp+57h+var_50]
0x18003cced  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18003ccf2  mov     ebx, eax
0x18003ccf4  test    eax, eax
0x18003ccf6  jns     short loc_18003CD1C
0x18003ccf8  mov     edx, 5Bh ; '['; void *
0x18003ccfd  lea     r8, aShellSearchuiA; "shell\\searchui\\abi\\base\\appactivati"...
0x18003cd04  mov     r9d, eax; char *
0x18003cd07  mov     rcx, [rbp+5Fh]; this
0x18003cd0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cd10  nop
0x18003cd11  lea     rcx, [rbp+57h+var_40]
0x18003cd15  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cd1a  jmp     short loc_18003CCC4
0x18003cd1c  mov     rdi, [rbp+57h+var_40]
0x18003cd20  mov     rax, [rdi]
0x18003cd23  mov     rbx, [rax+98h]
0x18003cd2a  mov     rcx, [rbp+57h+var_78]; string
0x18003cd2e  call    cs:__imp_WindowsDeleteString
0x18003cd34  mov     [rbp+57h+var_78], r14
0x18003cd38  lea     rdx, [rbp+57h+var_78]
0x18003cd3c  mov     rcx, rdi
0x18003cd3f  mov     rax, rbx
0x18003cd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd47  mov     ebx, eax
0x18003cd49  test    eax, eax
0x18003cd4b  jns     short loc_18003CD54
0x18003cd4d  mov     edx, 5Ch ; '\'
0x18003cd52  jmp     short loc_18003CCFD
0x18003cd54  mov     rdi, [rbp+57h+var_70]
0x18003cd58  xor     edx, edx; length
0x18003cd5a  mov     rcx, [rbp+57h+var_78]; string
0x18003cd5e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cd64  mov     rbx, rax
0x18003cd67  xor     edx, edx; length
0x18003cd69  mov     rcx, [rbp+57h+string]; string
0x18003cd6d  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cd73  mov     r9, rdi; struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *
0x18003cd76  mov     r8, rbx; unsigned __int16 *
0x18003cd79  mov     rdx, rax; unsigned __int16 *
0x18003cd7c  mov     rcx, rsi; this
0x18003cd7f  call    ?RuntimeClassInitialize@CSearchActivatedEventArgs@@QEAAJPEBG0PEAUISearchPaneQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z; CSearchActivatedEventArgs::RuntimeClassInitialize(ushort const *,ushort const *,Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *)
0x18003cd84  nop
0x18003cd85  lea     rcx, [rbp+57h+var_40]
0x18003cd89  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cd8e  nop
0x18003cd8f  lea     rcx, [rbp+57h+var_50]
0x18003cd93  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cd98  nop
0x18003cd99  mov     rcx, [rbp+57h+var_78]; string
0x18003cd9d  call    cs:__imp_WindowsDeleteString
0x18003cda3  mov     [rbp+57h+var_78], r14
0x18003cda7  lea     rcx, [rbp+57h+var_58]
0x18003cdab  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cdb0  nop
0x18003cdb1  lea     rcx, [rbp+57h+var_60]
0x18003cdb5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cdba  nop
0x18003cdbb  mov     rcx, [rbp+57h+string]; string
0x18003cdbf  call    cs:__imp_WindowsDeleteString
0x18003cdc5  mov     [rbp+57h+string], r14
0x18003cdc9  lea     rcx, [rbp+57h+var_70]
0x18003cdcd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cdd2  nop
0x18003cdd3  lea     rcx, [rbp+57h+var_68]
0x18003cdd7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cddc  mov     ebx, r14d
0x18003cddf  lea     rcx, [rbp+57h+var_48]
0x18003cde3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003cde8  mov     eax, ebx
0x18003cdea  mov     rcx, [rbp+57h+var_18]
0x18003cdee  xor     rcx, rsp; StackCookie
0x18003cdf1  call    __security_check_cookie
0x18003cdf6  lea     r11, [rsp+0A0h+var_10]
0x18003cdfe  mov     rbx, [r11+30h]
0x18003ce02  mov     rsi, [r11+38h]
0x18003ce06  mov     rsp, r11
0x18003ce09  pop     r14
0x18003ce0b  pop     rdi
0x18003ce0c  pop     rbp
0x18003ce0d  retn
```
