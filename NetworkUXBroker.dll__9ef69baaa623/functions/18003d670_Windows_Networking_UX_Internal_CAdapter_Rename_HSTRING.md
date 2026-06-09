# Windows::Networking::UX::Internal::CAdapter::Rename(HSTRING__ *)

- ea: `0x18003d670`
- end: `0x18003d953`
- name: `?Rename@CAdapter@Internal@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `739`
- prototype: `int(Windows::Networking::UX::Internal::CAdapter *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000955c`
- `0x18000a6e4`
- `0x18000e768`
- `0x180021ed0`
- `0x180035dc0`
- `0x180037c4c`
- `0x18003d670`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003d819`
- `OLEAUT32!__imp_VariantInit` at `0x18003d819`
- `OLEAUT32!__imp_VariantClear` at `0x18003d880`
- `OLEAUT32!__imp_VariantClear` at `0x18003d905`
- `OLEAUT32!__imp_VariantClear` at `0x18003d880`
- `OLEAUT32!__imp_VariantClear` at `0x18003d905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6da`

## string_xrefs

- `0x18003d6c5`: `Rename`
- `0x18003d781`: `Rename`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapter::Rename(
        Windows::Networking::UX::Internal::CAdapter *this,
        HSTRING a2)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, _QWORD, _QWORD); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, const wchar_t *, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  LONGLONG v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v23; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v24; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ce47fe168b1334e278c37086d4204e68_Traceguids);
  wil::make_bstr(&v20, L"MSFT_NetAdapter");
  wil::make_bstr(&v19, L"Rename");
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::make_bstr(&v18, StringRawBuffer);
  v5 = *((_QWORD *)this + 11);
  v25 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v5 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v7 = v6(v5, v20, 0, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
      (const char *)(unsigned int)v7,
      (int)&v25);
    goto LABEL_21;
  }
  v9 = v25;
  v24 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64 *))(*(_QWORD *)v25 + 152LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v11 = v10(v9, L"Rename", 0, &v24);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
      (const char *)(unsigned int)v11,
      0);
LABEL_8:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    goto LABEL_21;
  }
  v12 = v24;
  v23 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 120LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  v14 = v13(v12, 0, &v23);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
      (const char *)(unsigned int)v14,
      0);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    goto LABEL_8;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = v18;
  v18 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v23 + 40LL))(
          v23,
          L"NewName",
          0,
          &pvarg);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 109;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
      (const char *)(unsigned int)v15,
      0);
    VariantClear(&pvarg);
    goto LABEL_11;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 11) + 192LL))(
          *((_QWORD *)this + 11),
          *((_QWORD *)this + 13),
          v19,
          0);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 112;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ce47fe168b1334e278c37086d4204e68_Traceguids, 0);
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v8 = 0;
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  return v8;
}

```

## disassembly

```asm
0x18003d670  push    rbp
0x18003d672  push    rbx
0x18003d673  push    rsi
0x18003d674  push    rdi
0x18003d675  push    r15
0x18003d677  mov     rbp, rsp
0x18003d67a  sub     rsp, 80h
0x18003d681  mov     rbx, rdx
0x18003d684  mov     rsi, rcx
0x18003d687  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d68e  lea     r15, WPP_GLOBAL_Control
0x18003d695  cmp     rcx, r15
0x18003d698  jz      short loc_18003D6B5
0x18003d69a  test    byte ptr [rcx+1Ch], 40h
0x18003d69e  jz      short loc_18003D6B5
0x18003d6a0  mov     rcx, [rcx+10h]
0x18003d6a4  lea     r8, WPP_ce47fe168b1334e278c37086d4204e68_Traceguids
0x18003d6ab  mov     edx, 12h
0x18003d6b0  call    WPP_SF_
0x18003d6b5  lea     rdx, aMsftNetadapter; "MSFT_NetAdapter"
0x18003d6bc  lea     rcx, [rbp+var_20]
0x18003d6c0  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18003d6c5  lea     rdx, aRename; "Rename"
0x18003d6cc  lea     rcx, [rbp+var_28]
0x18003d6d0  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18003d6d5  xor     edx, edx; length
0x18003d6d7  mov     rcx, rbx; string
0x18003d6da  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d6e0  mov     rdx, rax
0x18003d6e3  lea     rcx, [rbp+var_30]
0x18003d6e7  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18003d6ec  mov     rdi, [rsi+58h]
0x18003d6f0  lea     rcx, [rbp+arg_18]
0x18003d6f4  mov     [rbp+arg_18], 0
0x18003d6fc  mov     rax, [rdi]
0x18003d6ff  mov     rbx, [rax+30h]
0x18003d703  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d708  mov     rdx, [rbp+var_20]
0x18003d70c  lea     rax, [rbp+arg_18]
0x18003d710  mov     [rsp+80h+var_58], 0
0x18003d719  xor     r9d, r9d
0x18003d71c  mov     qword ptr [rsp+80h+var_60], rax; int
0x18003d721  xor     r8d, r8d
0x18003d724  mov     rax, rbx
0x18003d727  mov     rcx, rdi
0x18003d72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d72f  mov     ebx, eax
0x18003d731  test    eax, eax
0x18003d733  jns     short loc_18003D752
0x18003d735  mov     rcx, [rbp+28h]; this
0x18003d739  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003d740  mov     r9d, eax; char *
0x18003d743  mov     edx, 62h ; 'b'; void *
0x18003d748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d74d  jmp     loc_18003D91F
0x18003d752  mov     rdi, [rbp+arg_18]
0x18003d756  lea     rcx, [rbp+arg_10]
0x18003d75a  mov     [rbp+arg_10], 0
0x18003d762  mov     rax, [rdi]
0x18003d765  mov     rbx, [rax+98h]
0x18003d76c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d771  lea     r9, [rbp+arg_10]
0x18003d775  mov     qword ptr [rsp+80h+var_60], 0; int
0x18003d77e  xor     r8d, r8d
0x18003d781  lea     rdx, aRename; "Rename"
0x18003d788  mov     rcx, rdi
0x18003d78b  mov     rax, rbx
0x18003d78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d793  mov     ebx, eax
0x18003d795  test    eax, eax
0x18003d797  jns     short loc_18003D7BF
0x18003d799  mov     rcx, [rbp+28h]; this
0x18003d79d  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003d7a4  mov     r9d, eax; char *
0x18003d7a7  mov     edx, 65h ; 'e'; void *
0x18003d7ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d7b1  lea     rcx, [rbp+arg_10]
0x18003d7b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d7ba  jmp     loc_18003D91F
0x18003d7bf  mov     rdi, [rbp+arg_10]
0x18003d7c3  lea     rcx, [rbp+arg_0]
0x18003d7c7  mov     [rbp+arg_0], 0
0x18003d7cf  mov     rax, [rdi]
0x18003d7d2  mov     rbx, [rax+78h]
0x18003d7d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d7db  lea     r8, [rbp+arg_0]
0x18003d7df  xor     edx, edx
0x18003d7e1  mov     rcx, rdi
0x18003d7e4  mov     rax, rbx
0x18003d7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7ec  mov     ebx, eax
0x18003d7ee  test    eax, eax
0x18003d7f0  jns     short loc_18003D815
0x18003d7f2  mov     rcx, [rbp+28h]; this
0x18003d7f6  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003d7fd  mov     r9d, eax; char *
0x18003d800  mov     edx, 68h ; 'h'; void *
0x18003d805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d80a  lea     rcx, [rbp+arg_0]
0x18003d80e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d813  jmp     short loc_18003D7B1
0x18003d815  lea     rcx, [rbp+pvarg]; pvarg
0x18003d819  call    cs:__imp_VariantInit
0x18003d81f  mov     rcx, [rbp+arg_0]
0x18003d823  lea     r9, [rbp+pvarg]
0x18003d827  mov     eax, 8
0x18003d82c  mov     [rsp+80h+var_60], 0; int
0x18003d834  mov     word ptr [rbp+pvarg], ax
0x18003d838  lea     rdx, aNewname; "NewName"
0x18003d83f  mov     rax, [rbp+var_30]
0x18003d843  xor     r8d, r8d
0x18003d846  mov     qword ptr [rbp+pvarg+8], rax
0x18003d84a  mov     [rbp+var_30], 0
0x18003d852  mov     rax, [rcx]
0x18003d855  mov     rax, [rax+28h]
0x18003d859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d85e  mov     ebx, eax
0x18003d860  test    eax, eax
0x18003d862  jns     short loc_18003D888
0x18003d864  mov     edx, 6Dh ; 'm'; void *
0x18003d869  mov     rcx, [rbp+28h]; this
0x18003d86d  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003d874  mov     r9d, eax; char *
0x18003d877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d87c  lea     rcx, [rbp+pvarg]; pvarg
0x18003d880  call    cs:__imp_VariantClear
0x18003d886  jmp     short loc_18003D80A
0x18003d888  mov     rdx, [rbp+arg_0]
0x18003d88c  xor     r9d, r9d
0x18003d88f  mov     rcx, [rsi+58h]
0x18003d893  mov     r8, [rbp+var_28]
0x18003d897  mov     [rsp+80h+var_48], 0
0x18003d8a0  mov     [rsp+80h+var_50], 0
0x18003d8a9  mov     rax, [rcx]
0x18003d8ac  mov     [rsp+80h+var_58], rdx
0x18003d8b1  mov     rdx, [rsi+68h]
0x18003d8b5  mov     qword ptr [rsp+80h+var_60], 0
0x18003d8be  mov     rax, [rax+0C0h]
0x18003d8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8ca  mov     ebx, eax
0x18003d8cc  test    eax, eax
0x18003d8ce  jns     short loc_18003D8D7
0x18003d8d0  mov     edx, 70h ; 'p'
0x18003d8d5  jmp     short loc_18003D869
0x18003d8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8de  cmp     rcx, r15
0x18003d8e1  jz      short loc_18003D901
0x18003d8e3  test    byte ptr [rcx+1Ch], 40h
0x18003d8e7  jz      short loc_18003D901
0x18003d8e9  mov     rcx, [rcx+10h]
0x18003d8ed  lea     r8, WPP_ce47fe168b1334e278c37086d4204e68_Traceguids
0x18003d8f4  mov     edx, 13h
0x18003d8f9  xor     r9d, r9d
0x18003d8fc  call    WPP_SF_d
0x18003d901  lea     rcx, [rbp+pvarg]; pvarg
0x18003d905  call    cs:__imp_VariantClear
0x18003d90b  lea     rcx, [rbp+arg_0]
0x18003d90f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d914  lea     rcx, [rbp+arg_10]
0x18003d918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d91d  xor     ebx, ebx
0x18003d91f  lea     rcx, [rbp+arg_18]
0x18003d923  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d928  lea     rcx, [rbp+var_30]
0x18003d92c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d931  lea     rcx, [rbp+var_28]
0x18003d935  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d93a  lea     rcx, [rbp+var_20]
0x18003d93e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d943  mov     eax, ebx
0x18003d945  add     rsp, 80h
0x18003d94c  pop     r15
0x18003d94e  pop     rdi
0x18003d94f  pop     rsi
0x18003d950  pop     rbx
0x18003d951  pop     rbp
0x18003d952  retn
```
