# GetDynamicAppUriHandlerGroupPackageFullNameAndHostId(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroup> const &,HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x14000c3ec`
- end: `0x14000c785`
- name: `?GetDynamicAppUriHandlerGroupPackageFullNameAndHostId@@YAXAEBV?$ComPtr@UIDynamicAppUriHandlerGroup@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAUHSTRING__@@PEAPEAU4@2@Z`
- size: `921`
- prototype: `HRESULT __fastcall(__int64 *, HSTRING, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x1400084f4`
- `0x14000a04c`
- `0x14000c3ec`
- `0x14000cc94`
- `0x14000d49c`
- `0x14000fbb0`
- `0x14000fdc0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x14000c589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x14000c589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c66d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c66d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c54e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c5a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c5b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c62b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c54e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c5a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c5b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c62b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c6e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c724`

## string_xrefs

- `0x14000c773`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
HRESULT __fastcall GetDynamicAppUriHandlerGroupPackageFullNameAndHostId(
        __int64 *a1,
        HSTRING a2,
        HSTRING *a3,
        HSTRING *a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // eax
  int i; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  HRESULT v27; // eax
  HRESULT v28; // eax
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-31h] BYREF
  __int64 v32; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v33; // [rsp+38h] [rbp-21h] BYREF
  __int64 v34; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v35; // [rsp+48h] [rbp-11h] BYREF
  __int64 v36; // [rsp+50h] [rbp-9h] BYREF
  __int64 v37; // [rsp+58h] [rbp-1h]
  unsigned int v38; // [rsp+60h] [rbp+7h]
  __int64 v39; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v40; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v41[8]; // [rsp+78h] [rbp+1Fh] BYREF
  int v42; // [rsp+80h] [rbp+27h]
  _BYTE v43[8]; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 result; // [rsp+C0h] [rbp+67h] BYREF

  v35 = 0;
  v7 = *a1;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 144LL);
  WindowsDeleteString(0);
  v35 = 0;
  v9 = v8(v7, &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x76,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
  wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>((const WCHAR *)&v40);
  v34 = 0;
  v10 = v40;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v40 + 112LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v34);
  v12 = v11(v10, v35, &v34);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7B,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
  result = v34;
  v37 = v34;
  v38 = 0;
  v39 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::end(
    &result,
    (__int64)v41);
  for ( i = v38; i != v42; i = ++v38 )
  {
    v14 = v37;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
    v16 = v15(v14, v38, &v39);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v16,
        (int)string);
    v32 = 0;
    v17 = v39;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v32);
    v19 = v18(v17, &v32);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7F,
        (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
        (const char *)(unsigned int)v19,
        (int)string);
    string = 0;
    v31 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    GetPackageFamilyAndFullNameForExtension(&v32, &string, &v31);
    LODWORD(result) = -1;
    v20 = WindowsCompareStringOrdinal(a2, string, (INT32 *)&result);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x86,
        (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
        (const char *)(unsigned int)v20,
        (int)string);
    if ( !(_DWORD)result )
    {
      v36 = 0;
      v21 = v32;
      v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 104LL);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v36);
      v23 = v22(v21, &v36);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x8B,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v23,
          (int)string);
      v33 = 0;
      v24 = v36;
      v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 224LL);
      WindowsDeleteString(0);
      v33 = 0;
      v26 = v25(v24, &v33);
      if ( v26 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x8E,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v26,
          (int)string);
      if ( v33 )
      {
        v27 = WindowsDuplicateString(v33, a4);
        if ( v27 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x91,
            (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
            (const char *)(unsigned int)v27,
            (int)string);
      }
      v28 = WindowsDuplicateString(v31, a3);
      if ( v28 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x94,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v28,
          (int)string);
      WindowsDeleteString(v33);
      v33 = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v36);
      WindowsDeleteString(v31);
      v31 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v32);
      break;
    }
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v32);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v43);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v34);
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(&v40);
  return WindowsDeleteString(v35);
}

```

## disassembly

```asm
0x14000c3ec  mov     [rsp-8+arg_8], rbx
0x14000c3f1  mov     [rsp-8+arg_10], rsi
0x14000c3f6  push    rbp
0x14000c3f7  push    rdi
0x14000c3f8  push    r12
0x14000c3fa  push    r14
0x14000c3fc  push    r15
0x14000c3fe  lea     rbp, [rsp-37h]
0x14000c403  sub     rsp, 90h
0x14000c40a  mov     r14, r9
0x14000c40d  mov     rsi, r8
0x14000c410  mov     r15, rdx
0x14000c413  xor     r12d, r12d
0x14000c416  mov     [rbp+57h+var_68], r12
0x14000c41a  mov     rdi, [rcx]
0x14000c41d  mov     rax, [rdi]
0x14000c420  mov     rbx, [rax+90h]
0x14000c427  xor     ecx, ecx; string
0x14000c429  call    cs:__imp_WindowsDeleteString
0x14000c42f  mov     [rbp+57h+var_68], r12
0x14000c433  lea     rdx, [rbp+57h+var_68]
0x14000c437  mov     rcx, rdi
0x14000c43a  mov     rax, rbx
0x14000c43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c442  mov     rcx, [rbp+5Fh]; this
0x14000c446  test    eax, eax
0x14000c448  jns     short loc_14000C45F
0x14000c44a  mov     r9d, eax; char *
0x14000c44d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c454  lea     edx, [r12+76h]; void *
0x14000c459  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c45f  lea     rcx, [rbp+57h+var_40]
0x14000c463  call    ??$GetActivationFactory@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(ushort const *)
0x14000c468  nop
0x14000c469  mov     [rbp+57h+var_70], r12
0x14000c46d  mov     rdi, [rbp+57h+var_40]
0x14000c471  mov     rax, [rdi]
0x14000c474  mov     rbx, [rax+70h]
0x14000c478  lea     rcx, [rbp+57h+var_70]
0x14000c47c  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c481  lea     r8, [rbp+57h+var_70]
0x14000c485  mov     rdx, [rbp+57h+var_68]
0x14000c489  mov     rcx, rdi
0x14000c48c  mov     rax, rbx
0x14000c48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c494  mov     rcx, [rbp+5Fh]; this
0x14000c498  test    eax, eax
0x14000c49a  jns     short loc_14000C4B1
0x14000c49c  mov     r9d, eax; char *
0x14000c49f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c4a6  mov     edx, 7Bh ; '{'; void *
0x14000c4ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c4b1  mov     rax, [rbp+57h+var_70]
0x14000c4b5  mov     [rbp+57h+result], rax
0x14000c4b9  mov     [rbp+57h+var_58], rax
0x14000c4bd  mov     [rbp+57h+var_50], r12d
0x14000c4c1  mov     [rbp+57h+var_48], r12
0x14000c4c5  lea     rdx, [rbp+57h+var_38]
0x14000c4c9  lea     rcx, [rbp+57h+result]
0x14000c4cd  call    ?end@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::end(void)
0x14000c4d2  nop
0x14000c4d3  mov     eax, [rbp+57h+var_50]
0x14000c4d6  cmp     eax, [rbp+57h+var_30]
0x14000c4d9  jz      loc_14000C6F8
0x14000c4df  mov     rdi, [rbp+57h+var_58]
0x14000c4e3  mov     rax, [rdi]
0x14000c4e6  mov     rbx, [rax+30h]
0x14000c4ea  lea     rcx, [rbp+57h+var_48]
0x14000c4ee  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c4f3  lea     r8, [rbp+57h+var_48]
0x14000c4f7  mov     edx, [rbp+57h+var_50]
0x14000c4fa  mov     rcx, rdi
0x14000c4fd  mov     rax, rbx
0x14000c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c505  mov     rcx, [rbp+5Fh]; this
0x14000c509  test    eax, eax
0x14000c50b  js      loc_14000C770
0x14000c511  mov     [rbp+57h+var_80], r12
0x14000c515  mov     rdi, [rbp+57h+var_48]
0x14000c519  mov     rax, [rdi]
0x14000c51c  mov     rbx, [rax+50h]
0x14000c520  lea     rcx, [rbp+57h+var_80]
0x14000c524  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c529  lea     rdx, [rbp+57h+var_80]
0x14000c52d  mov     rcx, rdi
0x14000c530  mov     rax, rbx
0x14000c533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c538  mov     rcx, [rbp+5Fh]; this
0x14000c53c  test    eax, eax
0x14000c53e  js      loc_14000C75B
0x14000c544  mov     [rbp+57h+string], r12
0x14000c548  mov     [rbp+57h+var_88], r12
0x14000c54c  xor     ecx, ecx; string
0x14000c54e  call    cs:__imp_WindowsDeleteString
0x14000c554  mov     [rbp+57h+var_88], r12
0x14000c558  mov     rcx, [rbp+57h+string]; string
0x14000c55c  call    cs:__imp_WindowsDeleteString
0x14000c562  mov     [rbp+57h+string], r12
0x14000c566  lea     r8, [rbp+57h+var_88]
0x14000c56a  lea     rdx, [rbp+57h+string]
0x14000c56e  lea     rcx, [rbp+57h+var_80]
0x14000c572  call    ?GetPackageFamilyAndFullNameForExtension@@YAXAEBV?$ComPtr@UIApplicationExtension@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAPEAUHSTRING__@@1@Z; GetPackageFamilyAndFullNameForExtension(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtension> const &,HSTRING__ * *,HSTRING__ * *)
0x14000c577  mov     dword ptr [rbp+57h+result], 0FFFFFFFFh
0x14000c57e  lea     r8, [rbp+57h+result]; result
0x14000c582  mov     rdx, [rbp+57h+string]; string2
0x14000c586  mov     rcx, r15; string1
0x14000c589  call    cs:__imp_WindowsCompareStringOrdinal
0x14000c58f  mov     rcx, [rbp+5Fh]; this
0x14000c593  test    eax, eax
0x14000c595  js      loc_14000C746
0x14000c59b  cmp     dword ptr [rbp+57h+result], r12d
0x14000c59f  jz      short loc_14000C5D3
0x14000c5a1  mov     rcx, [rbp+57h+var_88]; string
0x14000c5a5  call    cs:__imp_WindowsDeleteString
0x14000c5ab  mov     [rbp+57h+var_88], r12
0x14000c5af  mov     rcx, [rbp+57h+string]; string
0x14000c5b3  call    cs:__imp_WindowsDeleteString
0x14000c5b9  mov     [rbp+57h+string], r12
0x14000c5bd  lea     rcx, [rbp+57h+var_80]
0x14000c5c1  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c5c6  mov     eax, [rbp+57h+var_50]
0x14000c5c9  inc     eax
0x14000c5cb  mov     [rbp+57h+var_50], eax
0x14000c5ce  jmp     loc_14000C4D6
0x14000c5d3  mov     [rbp+57h+var_60], r12
0x14000c5d7  mov     rdi, [rbp+57h+var_80]
0x14000c5db  mov     rax, [rdi]
0x14000c5de  mov     rbx, [rax+68h]
0x14000c5e2  lea     rcx, [rbp+57h+var_60]
0x14000c5e6  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c5eb  lea     rdx, [rbp+57h+var_60]
0x14000c5ef  mov     rcx, rdi
0x14000c5f2  mov     rax, rbx
0x14000c5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5fa  mov     rcx, [rbp+5Fh]; this
0x14000c5fe  test    eax, eax
0x14000c600  jns     short loc_14000C617
0x14000c602  mov     r9d, eax; char *
0x14000c605  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c60c  mov     edx, 8Bh; void *
0x14000c611  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c617  mov     [rbp+57h+var_78], r12
0x14000c61b  mov     rdi, [rbp+57h+var_60]
0x14000c61f  mov     rax, [rdi]
0x14000c622  mov     rbx, [rax+0E0h]
0x14000c629  xor     ecx, ecx; string
0x14000c62b  call    cs:__imp_WindowsDeleteString
0x14000c631  mov     [rbp+57h+var_78], r12
0x14000c635  lea     rdx, [rbp+57h+var_78]
0x14000c639  mov     rcx, rdi
0x14000c63c  mov     rax, rbx
0x14000c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c644  mov     rcx, [rbp+5Fh]; this
0x14000c648  test    eax, eax
0x14000c64a  jns     short loc_14000C661
0x14000c64c  mov     r9d, eax; char *
0x14000c64f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c656  mov     edx, 8Eh; void *
0x14000c65b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c661  mov     rcx, [rbp+57h+var_78]; string
0x14000c665  test    rcx, rcx
0x14000c668  jz      short loc_14000C690
0x14000c66a  mov     rdx, r14; newString
0x14000c66d  call    cs:__imp_WindowsDuplicateString
0x14000c673  mov     rcx, [rbp+5Fh]; this
0x14000c677  test    eax, eax
0x14000c679  jns     short loc_14000C690
0x14000c67b  mov     r9d, eax; char *
0x14000c67e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c685  mov     edx, 91h; void *
0x14000c68a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c690  mov     rdx, rsi; newString
0x14000c693  mov     rcx, [rbp+57h+var_88]; string
0x14000c697  call    cs:__imp_WindowsDuplicateString
0x14000c69d  mov     rcx, [rbp+5Fh]; this
0x14000c6a1  test    eax, eax
0x14000c6a3  jns     short loc_14000C6BA
0x14000c6a5  mov     r9d, eax; char *
0x14000c6a8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c6af  mov     edx, 94h; void *
0x14000c6b4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c6ba  mov     rcx, [rbp+57h+var_78]; string
0x14000c6be  call    cs:__imp_WindowsDeleteString
0x14000c6c4  mov     [rbp+57h+var_78], r12
0x14000c6c8  lea     rcx, [rbp+57h+var_60]
0x14000c6cc  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c6d1  nop
0x14000c6d2  mov     rcx, [rbp+57h+var_88]; string
0x14000c6d6  call    cs:__imp_WindowsDeleteString
0x14000c6dc  mov     [rbp+57h+var_88], r12
0x14000c6e0  mov     rcx, [rbp+57h+string]; string
0x14000c6e4  call    cs:__imp_WindowsDeleteString
0x14000c6ea  mov     [rbp+57h+string], r12
0x14000c6ee  lea     rcx, [rbp+57h+var_80]
0x14000c6f2  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c6f7  nop
0x14000c6f8  lea     rcx, [rbp+57h+var_28]
0x14000c6fc  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c701  nop
0x14000c702  lea     rcx, [rbp+57h+var_48]
0x14000c706  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c70b  nop
0x14000c70c  lea     rcx, [rbp+57h+var_70]
0x14000c710  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c715  nop
0x14000c716  lea     rcx, [rbp+57h+var_40]
0x14000c71a  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x14000c71f  nop
0x14000c720  mov     rcx, [rbp+57h+var_68]; string
0x14000c724  call    cs:__imp_WindowsDeleteString
0x14000c72a  lea     r11, [rsp+0B0h+var_20]
0x14000c732  mov     rbx, [r11+38h]
0x14000c736  mov     rsi, [r11+40h]
0x14000c73a  mov     rsp, r11
0x14000c73d  pop     r15
0x14000c73f  pop     r14
0x14000c741  pop     r12
0x14000c743  pop     rdi
0x14000c744  pop     rbp
0x14000c745  retn
0x14000c746  mov     r9d, eax; char *
0x14000c749  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c750  mov     edx, 86h; void *
0x14000c755  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c75b  mov     r9d, eax; char *
0x14000c75e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c765  mov     edx, 7Fh; void *
0x14000c76a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c770  mov     r9d, eax; char *
0x14000c773  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000c77a  mov     edx, 1CBEh; void *
0x14000c77f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
