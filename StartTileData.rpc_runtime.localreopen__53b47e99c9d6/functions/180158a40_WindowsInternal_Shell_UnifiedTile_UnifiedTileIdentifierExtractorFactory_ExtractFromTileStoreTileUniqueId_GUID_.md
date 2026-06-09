# WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromTileStoreTileUniqueId(_GUID,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)

- ea: `0x180158a40`
- end: `0x180158cfa`
- name: `?ExtractFromTileStoreTileUniqueId@UnifiedTileIdentifierExtractorFactory@UnifiedTile@Shell@WindowsInternal@@UEAAJU_GUID@@PEAPEAUIUnifiedTileIdentifier@234@@Z`
- size: `698`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory *__hidden this, struct _GUID *__struct_ptr, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800301cc`
- `0x18004ffc0`
- `0x180158a40`
- `0x1801593b0`
- `0x180201e50`
- `0x1802e3b80`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158ca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158ca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180158cb9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180158ab6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180158ab6`

## string_xrefs

- `0x180158ac9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180158b22`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180158b72`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180158bbc`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180158c19`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180158c53`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromTileStoreTileUniqueId(
        WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory *this,
        struct _GUID *a2,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **a3)
{
  struct _GUID *v4; // r14
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING_HEADER *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  const char *v19; // r9
  __int64 v20; // rdx
  HSTRING v22; // [rsp+20h] [rbp-60h] BYREF
  __int64 v23; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v27; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v4 = a2;
  *a3 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_TileStoreWrites>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_TileStoreWrites>::GetImpl'::`2'::impl,
    a2);
  v26 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.TileView",
    0x2Au,
    0x29u);
  ActivationFactory = RoGetActivationFactory(v29, &GUID_61424521_07b6_40d2_9323_b78cdae5eb61, &v26);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v22);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    return v6;
  }
  v23 = 0;
  v7 = v26;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v26 + 152LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *v4;
  v9 = v8(v7, &hstringHeader, &v23);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)v9,
      (int)v22);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    goto LABEL_19;
  }
  v22 = 0;
  v10 = v23;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 184LL);
  WindowsDeleteString(0);
  v22 = 0;
  v12 = v11(v10, &v22);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)v12,
      (int)v22);
LABEL_17:
    WindowsDeleteString(v22);
    v22 = 0;
    goto LABEL_18;
  }
  v25 = 0;
  v13 = v23;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v15 = v14(v13, &v25);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)v15,
      (int)v22);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    goto LABEL_17;
  }
  string = 0;
  v16 = v25;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 232LL);
  WindowsDeleteString(0);
  string = 0;
  v18 = v17(v16, &string);
  v6 = v18;
  if ( v18 < 0 )
  {
    v20 = 48;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)v18,
      (int)v22);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_16;
  }
  if ( !string )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x33,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      v19);
  v27 = v22;
  hstringHeader.Reserved.Reserved1 = string;
  v18 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(
          a3,
          &hstringHeader,
          &v27);
  v6 = v18;
  if ( v18 < 0 )
  {
    v20 = 54;
    goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  WindowsDeleteString(v22);
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  return 0;
}

```

## disassembly

```asm
0x180158a40  mov     [rsp-28h+arg_0], rbx
0x180158a45  push    rbp
0x180158a46  push    rsi
0x180158a47  push    rdi
0x180158a48  push    r14
0x180158a4a  push    r15
0x180158a4c  mov     rbp, rsp
0x180158a4f  sub     rsp, 80h
0x180158a56  mov     rax, cs:__security_cookie
0x180158a5d  xor     rax, rsp
0x180158a60  mov     [rbp+var_10], rax
0x180158a64  mov     rsi, r8
0x180158a67  mov     r14, rdx
0x180158a6a  xor     r15d, r15d
0x180158a6d  mov     [r8], r15
0x180158a70  mov     dl, 1
0x180158a72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TileStoreWrites@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TileStoreWrites@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TileStoreWrites> `wil::Feature<__WilFeatureTraits_Feature_TileStoreWrites>::GetImpl(void)'::`2'::impl
0x180158a79  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_TileStoreWrites@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TileStoreWrites>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180158a7e  mov     [rbp+var_40], r15
0x180158a82  lea     rcx, [rbp+var_40]
0x180158a86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158a8b  mov     [rbp+var_18], r15
0x180158a8f  lea     r9d, [r15+29h]; unsigned int
0x180158a93  lea     r8d, [r15+2Ah]; unsigned int
0x180158a97  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_TileView@@3QBGB; "Windows.Internal.StateRepository.TileVi"...
0x180158a9e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180158aa2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180158aa7  lea     r8, [rbp+var_40]
0x180158aab  lea     rdx, _GUID_61424521_07b6_40d2_9323_b78cdae5eb61
0x180158ab2  mov     rcx, [rbp+var_18]
0x180158ab6  call    cs:__imp_RoGetActivationFactory
0x180158abc  mov     ebx, eax
0x180158abe  test    eax, eax
0x180158ac0  jns     short loc_180158ADE
0x180158ac2  mov     rcx, [rbp+28h]; this
0x180158ac6  mov     r9d, eax; char *
0x180158ac9  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158ad0  lea     edx, [r15+23h]; void *
0x180158ad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158ad9  jmp     loc_180158C91
0x180158ade  mov     [rbp+var_58], r15
0x180158ae2  mov     rdi, [rbp+var_40]
0x180158ae6  mov     rax, [rdi]
0x180158ae9  mov     rbx, [rax+98h]
0x180158af0  lea     rcx, [rbp+var_58]
0x180158af4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158af9  movups  xmm0, xmmword ptr [r14]
0x180158afd  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180158b02  lea     r8, [rbp+var_58]
0x180158b06  lea     rdx, [rbp+hstringHeader]
0x180158b0a  mov     rcx, rdi
0x180158b0d  mov     rax, rbx
0x180158b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158b15  mov     ebx, eax
0x180158b17  test    eax, eax
0x180158b19  jns     short loc_180158B38
0x180158b1b  mov     rcx, [rbp+28h]; this
0x180158b1f  mov     r9d, eax; char *
0x180158b22  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158b29  mov     edx, 26h ; '&'; void *
0x180158b2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158b33  jmp     loc_180158C88
0x180158b38  mov     [rbp+var_60], r15
0x180158b3c  mov     rdi, [rbp+var_58]
0x180158b40  mov     rax, [rdi]
0x180158b43  mov     rbx, [rax+0B8h]
0x180158b4a  xor     ecx, ecx; string
0x180158b4c  call    cs:__imp_WindowsDeleteString
0x180158b52  mov     [rbp+var_60], r15
0x180158b56  lea     rdx, [rbp+var_60]
0x180158b5a  mov     rcx, rdi
0x180158b5d  mov     rax, rbx
0x180158b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158b65  mov     ebx, eax
0x180158b67  test    eax, eax
0x180158b69  jns     short loc_180158B88
0x180158b6b  mov     rcx, [rbp+28h]; this
0x180158b6f  mov     r9d, eax; char *
0x180158b72  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158b79  mov     edx, 29h ; ')'; void *
0x180158b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158b83  jmp     loc_180158C7A
0x180158b88  mov     [rbp+var_48], r15
0x180158b8c  mov     rdi, [rbp+var_58]
0x180158b90  mov     rax, [rdi]
0x180158b93  mov     rbx, [rax+48h]
0x180158b97  lea     rcx, [rbp+var_48]
0x180158b9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158ba0  lea     rdx, [rbp+var_48]
0x180158ba4  mov     rcx, rdi
0x180158ba7  mov     rax, rbx
0x180158baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158baf  mov     ebx, eax
0x180158bb1  test    eax, eax
0x180158bb3  jns     short loc_180158BD2
0x180158bb5  mov     rcx, [rbp+28h]; this
0x180158bb9  mov     r9d, eax; char *
0x180158bbc  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158bc3  mov     edx, 2Ch ; ','; void *
0x180158bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158bcd  jmp     loc_180158C71
0x180158bd2  mov     [rbp+string], r15
0x180158bd6  mov     rdi, [rbp+var_48]
0x180158bda  mov     rax, [rdi]
0x180158bdd  mov     rbx, [rax+0E8h]
0x180158be4  xor     ecx, ecx; string
0x180158be6  call    cs:__imp_WindowsDeleteString
0x180158bec  mov     [rbp+string], r15
0x180158bf0  lea     rdx, [rbp+string]
0x180158bf4  mov     rcx, rdi
0x180158bf7  mov     rax, rbx
0x180158bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158bff  mov     ebx, eax
0x180158c01  test    eax, eax
0x180158c03  jns     short loc_180158C0C
0x180158c05  mov     edx, 30h ; '0'
0x180158c0a  jmp     short loc_180158C50
0x180158c0c  mov     rax, [rbp+string]
0x180158c10  test    rax, rax
0x180158c13  jnz     short loc_180158C29
0x180158c15  mov     rcx, [rbp+28h]; this
0x180158c19  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158c20  lea     edx, [rax+33h]; void *
0x180158c23  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180158c29  mov     rdx, [rbp+var_60]
0x180158c2d  mov     [rbp+var_38], rdx
0x180158c31  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180158c35  lea     r8, [rbp+var_38]
0x180158c39  lea     rdx, [rbp+hstringHeader]
0x180158c3d  mov     rcx, rsi
0x180158c40  call    ??$MakeAndInitialize@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@AEAPEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,HSTRING__ * &)
0x180158c45  mov     ebx, eax
0x180158c47  test    eax, eax
0x180158c49  jns     short loc_180158C9E
0x180158c4b  mov     edx, 36h ; '6'; void *
0x180158c50  mov     r9d, eax; char *
0x180158c53  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180158c5a  mov     rcx, [rbp+28h]; this
0x180158c5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158c63  mov     rcx, [rbp+string]; string
0x180158c67  call    cs:__imp_WindowsDeleteString
0x180158c6d  mov     [rbp+string], r15
0x180158c71  lea     rcx, [rbp+var_48]
0x180158c75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158c7a  mov     rcx, [rbp+var_60]; string
0x180158c7e  call    cs:__imp_WindowsDeleteString
0x180158c84  mov     [rbp+var_60], r15
0x180158c88  lea     rcx, [rbp+var_58]
0x180158c8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158c91  lea     rcx, [rbp+var_40]
0x180158c95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158c9a  mov     eax, ebx
0x180158c9c  jmp     short loc_180158CD7
0x180158c9e  mov     rcx, [rbp+string]; string
0x180158ca2  call    cs:__imp_WindowsDeleteString
0x180158ca8  mov     [rbp+string], r15
0x180158cac  lea     rcx, [rbp+var_48]
0x180158cb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158cb5  mov     rcx, [rbp+var_60]; string
0x180158cb9  call    cs:__imp_WindowsDeleteString
0x180158cbf  mov     [rbp+var_60], r15
0x180158cc3  lea     rcx, [rbp+var_58]
0x180158cc7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158ccc  lea     rcx, [rbp+var_40]
0x180158cd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180158cd5  xor     eax, eax
0x180158cd7  mov     rcx, [rbp+var_10]
0x180158cdb  xor     rcx, rsp; StackCookie
0x180158cde  call    __security_check_cookie
0x180158ce3  mov     rbx, [rsp+80h+arg_0]
0x180158ceb  add     rsp, 80h
0x180158cf2  pop     r15
0x180158cf4  pop     r14
0x180158cf6  pop     rdi
0x180158cf7  pop     rsi
0x180158cf8  pop     rbp
0x180158cf9  retn
```
