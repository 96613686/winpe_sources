# OSIntegration::Tools::MoCOMHelper::WriteContractCustomProperties(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionRegistration> &)

- ea: `0x18003a9f8`
- end: `0x18003aec2`
- name: `?WriteContractCustomProperties@MoCOMHelper@Tools@OSIntegration@@AEBAJAEAV?$ComPtr@UExtensionRegistration@DEH@OSIntegration@@@WRL@Microsoft@@@Z`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b8fb8`

## callees

- `0x18000b3bc`
- `0x18003a300`
- `0x18003a320`
- `0x18003a9f8`
- `0x18003aec8`
- `0x18003b58c`
- `0x180098bf4`
- `0x1800a2854`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ab77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003acc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ad16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ab77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003acc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ad16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aa71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aa81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003abd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003abe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003acdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aa71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aa81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003abd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003abe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003acdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad2e`

## string_xrefs

- `0x18003aba0`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003ac90`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003add4`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003ae14`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003ae9f`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::WriteContractCustomProperties(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rsi
  HSTRING v6; // rcx
  unsigned int *v8; // rsi
  __int64 v9; // rcx
  int v10; // eax
  HRESULT v11; // ebx
  const WCHAR *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // rcx
  int v16; // eax
  const WCHAR *v17; // rcx
  unsigned __int64 v18; // rdx
  HSTRING v19; // rcx
  HSTRING v20; // rcx
  char *v21; // rax
  HSTRING v22; // rdx
  HSTRING v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  HSTRING v26; // rcx
  const WCHAR *v27; // rcx
  unsigned __int64 v28; // rdx
  HSTRING v29; // rcx
  char *v30; // rax
  HSTRING v31; // rdx
  HSTRING v32; // rcx
  __int64 v33; // rcx
  HSTRING v34; // rcx
  HSTRING v35; // rcx
  HSTRING v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-20h] BYREF
  char v38; // [rsp+28h] [rbp-18h] BYREF
  char v39; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HSTRING v41; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v42; // [rsp+88h] [rbp+48h] BYREF
  HSTRING string; // [rsp+90h] [rbp+50h] BYREF
  HSTRING v44; // [rsp+98h] [rbp+58h] BYREF

  v42 = 0;
  string = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 128LL))(*a2, &v41);
  for ( i = 0; ; ++i )
  {
    if ( i >= a1[51] )
    {
      for ( j = 0; ; ++j )
      {
        if ( j >= a1[63] )
        {
          v6 = v41;
          if ( v41 )
          {
            v41 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
          }
          if ( string )
            WindowsDeleteString(string);
          if ( v42 )
            WindowsDeleteString(v42);
          return 0;
        }
        v14 = *(_QWORD *)(a1[61] + 8 * j);
        v44 = v41;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v44);
        v16 = OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::DefaultPropertyComparisonRule<Common::StringBuffer>>::Evaluate(
                v15,
                v14,
                &v44);
        v11 = v16;
        if ( v16 != -2147023728 && v16 != -2147483637 )
          break;
        v17 = *(const WCHAR **)(v14 + 32);
        if ( !v17 )
        {
          v11 = -2147467261;
LABEL_44:
          v25 = 2795;
          goto LABEL_47;
        }
        v44 = 0;
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        if ( v18 <= 0xFFFFFFFF )
        {
          v11 = WindowsCreateString(v17, v18, &v44);
          if ( v11 >= 0 )
          {
            v26 = v42;
            v42 = v44;
            WindowsDeleteString(v26);
          }
        }
        else
        {
          v11 = -2147024362;
        }
        if ( v11 < 0 )
          goto LABEL_44;
        v27 = *(const WCHAR **)(v14 + 8);
        if ( !v27 )
        {
          v11 = -2147467261;
LABEL_46:
          v25 = 2796;
          goto LABEL_47;
        }
        v44 = 0;
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] );
        if ( v28 > 0xFFFFFFFF )
        {
          v11 = -2147024362;
        }
        else
        {
          v11 = WindowsCreateString(v27, v28, &v44);
          if ( v11 >= 0 )
          {
            v29 = string;
            string = v44;
            WindowsDeleteString(v29);
          }
        }
        if ( v11 < 0 )
          goto LABEL_46;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, HSTRING *))(*(_QWORD *)*a2 + 144LL))(
                *a2,
                &v42,
                &string) )
        {
          v11 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAEF,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
            (const char *)0x8007000ELL,
            v37);
          v34 = v41;
          if ( v41 )
          {
            v41 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v34 + 16LL))(v34);
          }
          goto LABEL_30;
        }
        v30 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 128LL))(*a2, &v37);
        v31 = 0;
        if ( &v39 != v30 )
        {
          v31 = *(HSTRING *)v30;
          *(_QWORD *)v30 = 0;
        }
        v32 = v41;
        v41 = v31;
        if ( v32 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 16LL))(v32);
        v33 = v37;
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
      }
      if ( v16 >= 0 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xAF8,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
                (const char *)0xB7,
                v37);
        goto LABEL_48;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAFA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v16,
        v37);
      v36 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
      }
      goto LABEL_30;
    }
    v8 = *(unsigned int **)(a1[49] + 8 * i);
    v44 = v41;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v44);
    v10 = OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
            v9,
            v8,
            &v44);
    v11 = v10;
    if ( v10 == -2147023728 || v10 == -2147483637 )
      break;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xADF,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v10,
        v37);
      v35 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v35 + 16LL))(v35);
      }
      goto LABEL_30;
    }
LABEL_42:
    ;
  }
  v12 = (const WCHAR *)*((_QWORD *)v8 + 2);
  if ( !v12 )
  {
    v11 = -2147467261;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v11,
      v37);
    v20 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
    }
LABEL_30:
    if ( string )
      WindowsDeleteString(string);
    if ( v42 )
      WindowsDeleteString(v42);
    return (unsigned int)v11;
  }
  v44 = 0;
  v13 = -1;
  do
    ++v13;
  while ( v12[v13] );
  if ( v13 <= 0xFFFFFFFF )
  {
    v11 = WindowsCreateString(v12, v13, &v44);
    if ( v11 >= 0 )
    {
      v19 = v42;
      v42 = v44;
      WindowsDeleteString(v19);
    }
  }
  else
  {
    v11 = -2147024362;
  }
  if ( v11 < 0 )
    goto LABEL_28;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, _QWORD))(*(_QWORD *)*a2 + 136LL))(*a2, &v42, *v8) )
  {
    v21 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 128LL))(*a2, &v37);
    v22 = 0;
    if ( &v38 != v21 )
    {
      v22 = *(HSTRING *)v21;
      *(_QWORD *)v21 = 0;
    }
    v23 = v41;
    v41 = v22;
    if ( v23 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_42;
  }
  v11 = -2147024882;
  v25 = 2775;
LABEL_47:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v11,
    v37);
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v42);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003a9f8  push    rbp
0x18003a9fa  push    rbx
0x18003a9fb  push    rsi
0x18003a9fc  push    rdi
0x18003a9fd  push    r12
0x18003a9ff  push    r14
0x18003aa01  push    r15
0x18003aa03  mov     rbp, rsp
0x18003aa06  sub     rsp, 40h
0x18003aa0a  mov     r15, rdx
0x18003aa0d  mov     r14, rcx
0x18003aa10  xor     r12d, r12d
0x18003aa13  mov     [rbp+arg_8], r12
0x18003aa17  mov     [rbp+string], r12
0x18003aa1b  mov     rcx, [rdx]
0x18003aa1e  mov     rax, [rcx]
0x18003aa21  lea     rdx, [rbp+arg_0]
0x18003aa25  mov     rax, [rax+80h]
0x18003aa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa31  nop
0x18003aa32  mov     edi, r12d
0x18003aa35  cmp     rdi, [r14+198h]
0x18003aa3c  jb      short loc_18003AA98
0x18003aa3e  mov     rsi, r12
0x18003aa41  cmp     rsi, [r14+1F8h]
0x18003aa48  jb      loc_18003AB00
0x18003aa4e  mov     rcx, [rbp+arg_0]
0x18003aa52  test    rcx, rcx
0x18003aa55  jz      short loc_18003AA68
0x18003aa57  mov     [rbp+arg_0], r12
0x18003aa5b  mov     rax, [rcx]
0x18003aa5e  mov     rax, [rax+10h]
0x18003aa62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa67  nop
0x18003aa68  mov     rcx, [rbp+string]; string
0x18003aa6c  test    rcx, rcx
0x18003aa6f  jz      short loc_18003AA78
0x18003aa71  call    cs:__imp_WindowsDeleteString
0x18003aa77  nop
0x18003aa78  mov     rcx, [rbp+arg_8]; string
0x18003aa7c  test    rcx, rcx
0x18003aa7f  jz      short loc_18003AA87
0x18003aa81  call    cs:__imp_WindowsDeleteString
0x18003aa87  xor     eax, eax
0x18003aa89  add     rsp, 40h
0x18003aa8d  pop     r15
0x18003aa8f  pop     r14
0x18003aa91  pop     r12
0x18003aa93  pop     rdi
0x18003aa94  pop     rsi
0x18003aa95  pop     rbx
0x18003aa96  pop     rbp
0x18003aa97  retn
0x18003aa98  mov     rax, [r14+188h]
0x18003aa9f  mov     rsi, [rax+rdi*8]
0x18003aaa3  mov     rax, [rbp+arg_0]
0x18003aaa7  mov     [rbp+arg_18], rax
0x18003aaab  lea     rcx, [rbp+arg_18]
0x18003aaaf  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003aab4  lea     r8, [rbp+arg_18]
0x18003aab8  mov     rdx, rsi
0x18003aabb  call    ?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x18003aac0  mov     ebx, eax
0x18003aac2  cmp     eax, 80070490h
0x18003aac7  jnz     loc_18003AE72
0x18003aacd  mov     rcx, [rsi+10h]; sourceString
0x18003aad1  test    rcx, rcx
0x18003aad4  jz      loc_18003AB6C
0x18003aada  mov     [rbp+arg_18], r12
0x18003aade  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003aae2  inc     rdx; length
0x18003aae5  cmp     [rcx+rdx*2], r12w
0x18003aaea  jnz     short loc_18003AAE2
0x18003aaec  mov     eax, 0FFFFFFFFh
0x18003aaf1  cmp     rdx, rax
0x18003aaf4  jbe     short loc_18003AB73
0x18003aaf6  mov     ebx, 80070216h
0x18003aafb  jmp     loc_18003AB95
0x18003ab00  mov     rax, [r14+1E8h]
0x18003ab07  mov     rdi, [rax+rsi*8]
0x18003ab0b  mov     rax, [rbp+arg_0]
0x18003ab0f  mov     [rbp+arg_18], rax
0x18003ab13  lea     rcx, [rbp+arg_18]
0x18003ab17  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003ab1c  lea     r8, [rbp+arg_18]
0x18003ab20  mov     rdx, rdi
0x18003ab23  call    ?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@V?$DefaultPropertyComparisonRule@VStringBuffer@Common@@@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::DefaultPropertyComparisonRule<Common::StringBuffer>>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x18003ab28  mov     ebx, eax
0x18003ab2a  cmp     eax, 80070490h
0x18003ab2f  jnz     loc_18003AE8F
0x18003ab35  mov     rcx, [rdi+20h]; sourceString
0x18003ab39  test    rcx, rcx
0x18003ab3c  jz      loc_18003AC77
0x18003ab42  mov     [rbp+arg_18], r12
0x18003ab46  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003ab4a  inc     rdx; length
0x18003ab4d  cmp     [rcx+rdx*2], r12w
0x18003ab52  jnz     short loc_18003AB4A
0x18003ab54  mov     eax, 0FFFFFFFFh
0x18003ab59  cmp     rdx, rax
0x18003ab5c  jbe     loc_18003ACC3
0x18003ab62  mov     ebx, 80070216h
0x18003ab67  jmp     loc_18003ACEA
0x18003ab6c  mov     ebx, 80004003h
0x18003ab71  jmp     short loc_18003AB99
0x18003ab73  lea     r8, [rbp+arg_18]; string
0x18003ab77  call    cs:__imp_WindowsCreateString
0x18003ab7d  mov     ebx, eax
0x18003ab7f  test    eax, eax
0x18003ab81  js      short loc_18003AB95
0x18003ab83  mov     rcx, [rbp+arg_8]; string
0x18003ab87  mov     rax, [rbp+arg_18]
0x18003ab8b  mov     [rbp+arg_8], rax
0x18003ab8f  call    cs:__imp_WindowsDeleteString
0x18003ab95  test    ebx, ebx
0x18003ab97  jns     short loc_18003ABF2
0x18003ab99  mov     rcx, [rbp+38h]; this
0x18003ab9d  mov     r9d, ebx; char *
0x18003aba0  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003aba7  mov     edx, 0AD6h; void *
0x18003abac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abb1  nop
0x18003abb2  mov     rcx, [rbp+arg_0]
0x18003abb6  test    rcx, rcx
0x18003abb9  jz      short loc_18003ABCC
0x18003abbb  mov     [rbp+arg_0], r12
0x18003abbf  mov     rax, [rcx]
0x18003abc2  mov     rax, [rax+10h]
0x18003abc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abcb  nop
0x18003abcc  mov     rcx, [rbp+string]; string
0x18003abd0  test    rcx, rcx
0x18003abd3  jz      short loc_18003ABDC
0x18003abd5  call    cs:__imp_WindowsDeleteString
0x18003abdb  nop
0x18003abdc  mov     rcx, [rbp+arg_8]; string
0x18003abe0  test    rcx, rcx
0x18003abe3  jz      short loc_18003ABEB
0x18003abe5  call    cs:__imp_WindowsDeleteString
0x18003abeb  mov     eax, ebx
0x18003abed  jmp     loc_18003AA89
0x18003abf2  mov     rcx, [r15]
0x18003abf5  mov     rax, [rcx]
0x18003abf8  mov     r8d, [rsi]
0x18003abfb  lea     rdx, [rbp+arg_8]
0x18003abff  mov     rax, [rax+88h]
0x18003ac06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac0b  test    al, al
0x18003ac0d  jz      loc_18003AE80
0x18003ac13  mov     rcx, [r15]
0x18003ac16  mov     rax, [rcx]
0x18003ac19  lea     rdx, [rbp+var_20]
0x18003ac1d  mov     rax, [rax+80h]
0x18003ac24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac29  mov     rdx, r12
0x18003ac2c  lea     rcx, [rbp+var_18]
0x18003ac30  cmp     rcx, rax
0x18003ac33  jz      short loc_18003AC3B
0x18003ac35  mov     rdx, [rax]
0x18003ac38  mov     [rax], r12
0x18003ac3b  mov     rcx, [rbp+arg_0]
0x18003ac3f  mov     [rbp+arg_0], rdx
0x18003ac43  test    rcx, rcx
0x18003ac46  jz      short loc_18003AC55
0x18003ac48  mov     rax, [rcx]
0x18003ac4b  mov     rax, [rax+10h]
0x18003ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac54  nop
0x18003ac55  mov     rcx, [rbp+var_20]
0x18003ac59  test    rcx, rcx
0x18003ac5c  jz      short loc_18003AC6F
0x18003ac5e  mov     [rbp+var_20], r12
0x18003ac62  mov     rax, [rcx]
0x18003ac65  mov     rax, [rax+10h]
0x18003ac69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac6e  nop
0x18003ac6f  inc     rdi
0x18003ac72  jmp     loc_18003AA35
0x18003ac77  mov     ebx, 80004003h
0x18003ac7c  mov     edx, 0AEBh
0x18003ac81  jmp     short loc_18003AC8D
0x18003ac83  mov     ebx, 80004003h
0x18003ac88  mov     edx, 0AECh; void *
0x18003ac8d  mov     r9d, ebx; char *
0x18003ac90  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003ac97  mov     rcx, [rbp+38h]; this
0x18003ac9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aca0  nop
0x18003aca1  lea     rcx, [rbp+arg_0]
0x18003aca5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003acaa  nop
0x18003acab  lea     rcx, [rbp+string]
0x18003acaf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18003acb4  nop
0x18003acb5  lea     rcx, [rbp+arg_8]
0x18003acb9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18003acbe  jmp     loc_18003ABEB
0x18003acc3  lea     r8, [rbp+arg_18]; string
0x18003acc7  call    cs:__imp_WindowsCreateString
0x18003accd  mov     ebx, eax
0x18003accf  test    eax, eax
0x18003acd1  js      short loc_18003ACE5
0x18003acd3  mov     rcx, [rbp+arg_8]; string
0x18003acd7  mov     rax, [rbp+arg_18]
0x18003acdb  mov     [rbp+arg_8], rax
0x18003acdf  call    cs:__imp_WindowsDeleteString
0x18003ace5  mov     eax, 0FFFFFFFFh
0x18003acea  test    ebx, ebx
0x18003acec  js      short loc_18003AC7C
0x18003acee  mov     rcx, [rdi+8]; sourceString
0x18003acf2  test    rcx, rcx
0x18003acf5  jz      short loc_18003AC83
0x18003acf7  mov     [rbp+arg_18], r12
0x18003acfb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003acff  inc     rdx; length
0x18003ad02  cmp     [rcx+rdx*2], r12w
0x18003ad07  jnz     short loc_18003ACFF
0x18003ad09  cmp     rdx, rax
0x18003ad0c  ja      loc_18003ADBE
0x18003ad12  lea     r8, [rbp+arg_18]; string
0x18003ad16  call    cs:__imp_WindowsCreateString
0x18003ad1c  mov     ebx, eax
0x18003ad1e  test    eax, eax
0x18003ad20  js      short loc_18003AD34
0x18003ad22  mov     rcx, [rbp+string]; string
0x18003ad26  mov     rax, [rbp+arg_18]
0x18003ad2a  mov     [rbp+string], rax
0x18003ad2e  call    cs:__imp_WindowsDeleteString
0x18003ad34  test    ebx, ebx
0x18003ad36  js      loc_18003AC88
0x18003ad3c  mov     rcx, [r15]
0x18003ad3f  mov     rax, [rcx]
0x18003ad42  lea     r8, [rbp+string]
0x18003ad46  lea     rdx, [rbp+arg_8]
0x18003ad4a  mov     rax, [rax+90h]
0x18003ad51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad56  test    al, al
0x18003ad58  jz      short loc_18003ADC8
0x18003ad5a  mov     rcx, [r15]
0x18003ad5d  mov     rax, [rcx]
0x18003ad60  lea     rdx, [rbp+var_20]
0x18003ad64  mov     rax, [rax+80h]
0x18003ad6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad70  mov     rdx, r12
0x18003ad73  lea     rcx, [rbp+var_10]
0x18003ad77  cmp     rcx, rax
0x18003ad7a  jz      short loc_18003AD82
0x18003ad7c  mov     rdx, [rax]
0x18003ad7f  mov     [rax], r12
0x18003ad82  mov     rcx, [rbp+arg_0]
0x18003ad86  mov     [rbp+arg_0], rdx
0x18003ad8a  test    rcx, rcx
0x18003ad8d  jz      short loc_18003AD9C
0x18003ad8f  mov     rax, [rcx]
0x18003ad92  mov     rax, [rax+10h]
0x18003ad96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad9b  nop
0x18003ad9c  mov     rcx, [rbp+var_20]
0x18003ada0  test    rcx, rcx
0x18003ada3  jz      short loc_18003ADB6
0x18003ada5  mov     [rbp+var_20], r12
0x18003ada9  mov     rax, [rcx]
0x18003adac  mov     rax, [rax+10h]
0x18003adb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adb5  nop
0x18003adb6  inc     rsi
0x18003adb9  jmp     loc_18003AA41
0x18003adbe  mov     ebx, 80070216h
0x18003adc3  jmp     loc_18003AD34
0x18003adc8  mov     rcx, [rbp+38h]; this
0x18003adcc  mov     ebx, 8007000Eh
0x18003add1  mov     r9d, ebx; char *
0x18003add4  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003addb  mov     edx, 0AEFh; void *
0x18003ade0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ade5  nop
0x18003ade6  mov     rcx, [rbp+arg_0]
0x18003adea  test    rcx, rcx
0x18003aded  jz      short loc_18003AE00
0x18003adef  mov     [rbp+arg_0], r12
0x18003adf3  mov     rax, [rcx]
0x18003adf6  mov     rax, [rax+10h]
0x18003adfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adff  nop
0x18003ae00  jmp     loc_18003ABCC
0x18003ae05  test    ebx, ebx
0x18003ae07  jns     loc_18003AC6F
0x18003ae0d  mov     rcx, [rbp+38h]; this
0x18003ae11  mov     r9d, ebx; char *
0x18003ae14  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003ae1b  mov     edx, 0ADFh; void *
0x18003ae20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae25  nop
0x18003ae26  mov     rcx, [rbp+arg_0]
0x18003ae2a  test    rcx, rcx
0x18003ae2d  jz      short loc_18003AE40
0x18003ae2f  mov     [rbp+arg_0], r12
0x18003ae33  mov     rax, [rcx]
0x18003ae36  mov     rax, [rax+10h]
0x18003ae3a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
