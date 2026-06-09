# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::DoesSecondaryTileExist(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>)

- ea: `0x18017e464`
- end: `0x18017e7d3`
- name: `?DoesSecondaryTileExist@SecondaryTileInitializationHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAA_NV?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@Z`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015b3e0`

## callees

- `0x18000ce94`
- `0x18001ac50`
- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x1800e8600`
- `0x180121244`
- `0x18017cee8`
- `0x18017cf20`
- `0x18017e464`
- `0x18017e7dc`
- `0x18017ea00`
- `0x18017ea58`
- `0x1801e8a74`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e574`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e6cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e574`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e6cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017e777`

## string_xrefs

- `0x18017e4d9`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18017e551`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18017e598`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18017e5d5`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18017e71b`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
char __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::DoesSecondaryTileExist(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  int v4; // eax
  __int64 TileIdentifier; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int i; // eax
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  HSTRING v19; // rcx
  std::_Ref_count_base *v20; // rcx
  HSTRING v22; // rcx
  std::_Ref_count_base *v23; // rcx
  HSTRING string; // [rsp+20h] [rbp-49h] BYREF
  HSTRING v25; // [rsp+28h] [rbp-41h] BYREF
  HSTRING v26; // [rsp+30h] [rbp-39h] BYREF
  HSTRING v27; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v31; // [rsp+58h] [rbp-11h] BYREF
  HSTRING v32; // [rsp+60h] [rbp-9h] BYREF
  int v33; // [rsp+68h] [rbp-1h]
  _QWORD v34[2]; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+17h] BYREF
  __int64 v36; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v34[1] = a2;
  v30 = 0;
  v3 = **(_QWORD **)(a1 + 16);
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.StartScreen.SecondaryTile",
    0x25u,
    0x24u);
  v4 = Windows::Foundation::GetActivationFactoryAsUser<Windows::UI::StartScreen::ISecondaryTileFactory>(v36, v3, &v30);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileiniti"
                    "alizationhandler.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(
    &v30,
    &v31);
  TileIdentifier = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                     *a2,
                     &string);
  wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
    TileIdentifier,
    &v29);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&string);
  v26 = 0;
  v6 = v29;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL);
  WindowsDeleteString(0);
  v26 = 0;
  v8 = v7(v6, &v26);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileiniti"
                    "alizationhandler.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
  v25 = 0;
  v9 = v29;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 56LL);
  WindowsDeleteString(0);
  v25 = 0;
  v11 = v10(v9, &v25);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileiniti"
                    "alizationhandler.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
  v28 = 0;
  v12 = *v31;
  v28 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v12 + 48))(v31, v26, &v28);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileiniti"
                    "alizationhandler.cpp",
      (const char *)(unsigned int)v13,
      (int)string);
  wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *>>>(
    &v27,
    v28);
  string = v27;
  v32 = v27;
  v33 = 0;
  v34[0] = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,wil::err_exception_policy>::end(
    &string,
    &hstringHeader);
  for ( i = v33; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v33 )
  {
    v15 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *>,wil::err_exception_policy>::vector_iterator::operator*(&v32);
    string = 0;
    v16 = *(_QWORD *)v15;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v15 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v18 = v17(v16, &string);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileini"
                      "tializationhandler.cpp",
        (const char *)(unsigned int)v18,
        (int)string);
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(&string, &v25) )
    {
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
      v19 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
      }
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v28);
      WindowsDeleteString(v25);
      v25 = 0;
      WindowsDeleteString(v26);
      v26 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v31);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v30);
      v20 = (std::_Ref_count_base *)a2[1];
      if ( v20 )
        std::_Ref_count_base::_Decref(v20);
      return 1;
    }
    WindowsDeleteString(string);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
  v22 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v22 + 16LL))(v22);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v28);
  WindowsDeleteString(v25);
  v25 = 0;
  WindowsDeleteString(v26);
  v26 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v31);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v30);
  v23 = (std::_Ref_count_base *)a2[1];
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  return 0;
}

```

## disassembly

```asm
0x18017e464  mov     [rsp-8+arg_10], rbx
0x18017e469  mov     [rsp-8+arg_18], rsi
0x18017e46e  push    rbp
0x18017e46f  push    rdi
0x18017e470  push    r14
0x18017e472  lea     rbp, [rsp-47h]
0x18017e477  sub     rsp, 0B0h
0x18017e47e  mov     rax, cs:__security_cookie
0x18017e485  xor     rax, rsp
0x18017e488  mov     [rbp+57h+var_20], rax
0x18017e48c  mov     rsi, rdx
0x18017e48f  mov     [rbp+57h+var_48], rdx
0x18017e493  xor     r14d, r14d
0x18017e496  mov     [rbp+57h+var_70], r14
0x18017e49a  mov     rax, [rcx+10h]
0x18017e49e  mov     rbx, [rax]
0x18017e4a1  mov     [rbp+57h+var_28], r14
0x18017e4a5  lea     r9d, [r14+24h]; unsigned int
0x18017e4a9  lea     r8d, [r14+25h]; unsigned int
0x18017e4ad  lea     rdx, ?RuntimeClass_Windows_UI_StartScreen_SecondaryTile@@3QBGB; "Windows.UI.StartScreen.SecondaryTile"
0x18017e4b4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18017e4b8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18017e4bd  nop
0x18017e4be  lea     r8, [rbp+57h+var_70]
0x18017e4c2  mov     rdx, rbx
0x18017e4c5  mov     rcx, [rbp+57h+var_28]
0x18017e4c9  call    ??$GetActivationFactoryAsUser@UISecondaryTileFactory@StartScreen@UI@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUISecondaryTileFactory@StartScreen@UI@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::UI::StartScreen::ISecondaryTileFactory>(HSTRING__ *,Windows::System::IUser *,Windows::UI::StartScreen::ISecondaryTileFactory * *)
0x18017e4ce  mov     rcx, [rbp+5Fh]; this
0x18017e4d2  test    eax, eax
0x18017e4d4  jns     short loc_18017E4EB
0x18017e4d6  mov     r9d, eax; char *
0x18017e4d9  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18017e4e0  mov     edx, 0CCh; void *
0x18017e4e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e4eb  lea     rdx, [rbp+57h+var_68]
0x18017e4ef  lea     rcx, [rbp+57h+var_70]
0x18017e4f3  call    ??$query@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@@?$com_ptr_t@UISecondaryTileStatics@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(void)
0x18017e4f8  nop
0x18017e4f9  lea     rdx, [rbp+57h+string]
0x18017e4fd  mov     rcx, [rsi]
0x18017e500  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18017e505  nop
0x18017e506  lea     rdx, [rbp+57h+var_78]
0x18017e50a  mov     rcx, rax
0x18017e50d  call    ??$query@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(void)
0x18017e512  nop
0x18017e513  lea     rcx, [rbp+57h+string]; void *
0x18017e517  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e51c  mov     [rbp+57h+var_90], r14
0x18017e520  mov     rdi, [rbp+57h+var_78]
0x18017e524  mov     rax, [rdi]
0x18017e527  mov     rbx, [rax+30h]
0x18017e52b  xor     ecx, ecx; string
0x18017e52d  call    cs:__imp_WindowsDeleteString
0x18017e533  mov     [rbp+57h+var_90], r14
0x18017e537  lea     rdx, [rbp+57h+var_90]
0x18017e53b  mov     rcx, rdi
0x18017e53e  mov     rax, rbx
0x18017e541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e546  mov     rcx, [rbp+5Fh]; this
0x18017e54a  test    eax, eax
0x18017e54c  jns     short loc_18017E563
0x18017e54e  mov     r9d, eax; char *
0x18017e551  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18017e558  mov     edx, 0D1h; void *
0x18017e55d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e563  mov     [rbp+57h+var_98], r14
0x18017e567  mov     rdi, [rbp+57h+var_78]
0x18017e56b  mov     rax, [rdi]
0x18017e56e  mov     rbx, [rax+38h]
0x18017e572  xor     ecx, ecx; string
0x18017e574  call    cs:__imp_WindowsDeleteString
0x18017e57a  mov     [rbp+57h+var_98], r14
0x18017e57e  lea     rdx, [rbp+57h+var_98]
0x18017e582  mov     rcx, rdi
0x18017e585  mov     rax, rbx
0x18017e588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e58d  mov     rcx, [rbp+5Fh]; this
0x18017e591  test    eax, eax
0x18017e593  jns     short loc_18017E5AA
0x18017e595  mov     r9d, eax; char *
0x18017e598  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18017e59f  mov     edx, 0D3h; void *
0x18017e5a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e5aa  mov     [rbp+57h+var_80], r14
0x18017e5ae  mov     rcx, [rbp+57h+var_68]
0x18017e5b2  mov     rax, [rcx]
0x18017e5b5  mov     [rbp+57h+var_80], r14
0x18017e5b9  lea     r8, [rbp+57h+var_80]
0x18017e5bd  mov     rdx, [rbp+57h+var_90]
0x18017e5c1  mov     rax, [rax+30h]
0x18017e5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e5ca  mov     rcx, [rbp+5Fh]; this
0x18017e5ce  test    eax, eax
0x18017e5d0  jns     short loc_18017E5E7
0x18017e5d2  mov     r9d, eax; char *
0x18017e5d5  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18017e5dc  mov     edx, 0D6h; void *
0x18017e5e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e5e7  mov     rdx, [rbp+57h+var_80]
0x18017e5eb  lea     rcx, [rbp+57h+var_88]
0x18017e5ef  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *> *,tagCOWAIT_FLAGS)
0x18017e5f4  nop
0x18017e5f5  mov     rax, [rbp+57h+var_88]
0x18017e5f9  mov     [rbp+57h+string], rax
0x18017e5fd  mov     [rbp+57h+var_60], rax
0x18017e601  mov     [rbp+57h+var_58], r14d
0x18017e605  mov     [rbp+57h+var_50], r14
0x18017e609  lea     rdx, [rbp+57h+hstringHeader]
0x18017e60d  lea     rcx, [rbp+57h+string]
0x18017e611  call    ?end@?$vector_range@U?$IVectorView@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,wil::err_exception_policy>::end(void)
0x18017e616  nop
0x18017e617  mov     eax, [rbp+57h+var_58]
0x18017e61a  cmp     eax, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18017e61d  jz      loc_18017E72D
0x18017e623  lea     rcx, [rbp+57h+var_60]
0x18017e627  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UISecondaryTile@StartScreen@UI@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18017e62c  mov     [rbp+57h+string], r14
0x18017e630  mov     rdi, [rax]
0x18017e633  mov     rax, [rdi]
0x18017e636  mov     rbx, [rax+38h]
0x18017e63a  xor     ecx, ecx; string
0x18017e63c  call    cs:__imp_WindowsDeleteString
0x18017e642  mov     [rbp+57h+string], r14
0x18017e646  lea     rdx, [rbp+57h+string]
0x18017e64a  mov     rcx, rdi
0x18017e64d  mov     rax, rbx
0x18017e650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e655  mov     rcx, [rbp+5Fh]; this
0x18017e659  test    eax, eax
0x18017e65b  js      loc_18017E718
0x18017e661  lea     rdx, [rbp+57h+var_98]
0x18017e665  lea     rcx, [rbp+57h+string]
0x18017e669  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBVHString@012@0@Z; Microsoft::WRL::Wrappers::operator==(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &)
0x18017e66e  nop
0x18017e66f  mov     rcx, [rbp+57h+string]; string
0x18017e673  test    al, al
0x18017e675  jnz     short loc_18017E687
0x18017e677  call    cs:__imp_WindowsDeleteString
0x18017e67d  mov     eax, [rbp+57h+var_58]
0x18017e680  inc     eax
0x18017e682  mov     [rbp+57h+var_58], eax
0x18017e685  jmp     short loc_18017E61A
0x18017e687  call    cs:__imp_WindowsDeleteString
0x18017e68d  mov     [rbp+57h+string], r14
0x18017e691  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x18017e695  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e69a  nop
0x18017e69b  lea     rcx, [rbp+57h+var_50]
0x18017e69f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e6a4  nop
0x18017e6a5  mov     rcx, [rbp+57h+var_88]
0x18017e6a9  test    rcx, rcx
0x18017e6ac  jz      short loc_18017E6BF
0x18017e6ae  mov     [rbp+57h+var_88], r14
0x18017e6b2  mov     rax, [rcx]
0x18017e6b5  mov     rax, [rax+10h]
0x18017e6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e6be  nop
0x18017e6bf  lea     rcx, [rbp+57h+var_80]; void *
0x18017e6c3  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e6c8  nop
0x18017e6c9  mov     rcx, [rbp+57h+var_98]; string
0x18017e6cd  call    cs:__imp_WindowsDeleteString
0x18017e6d3  mov     [rbp+57h+var_98], r14
0x18017e6d7  mov     rcx, [rbp+57h+var_90]; string
0x18017e6db  call    cs:__imp_WindowsDeleteString
0x18017e6e1  mov     [rbp+57h+var_90], r14
0x18017e6e5  lea     rcx, [rbp+57h+var_78]; void *
0x18017e6e9  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e6ee  nop
0x18017e6ef  lea     rcx, [rbp+57h+var_68]; void *
0x18017e6f3  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e6f8  nop
0x18017e6f9  lea     rcx, [rbp+57h+var_70]; void *
0x18017e6fd  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e702  nop
0x18017e703  mov     rcx, [rsi+8]; this
0x18017e707  test    rcx, rcx
0x18017e70a  jz      short loc_18017E711
0x18017e70c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18017e711  mov     al, 1
0x18017e713  jmp     loc_18017E7AF
0x18017e718  mov     r9d, eax; char *
0x18017e71b  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18017e722  mov     edx, 0DCh; void *
0x18017e727  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e72d  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x18017e731  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e736  nop
0x18017e737  lea     rcx, [rbp+57h+var_50]
0x18017e73b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017e740  nop
0x18017e741  mov     rcx, [rbp+57h+var_88]
0x18017e745  test    rcx, rcx
0x18017e748  jz      short loc_18017E75B
0x18017e74a  mov     [rbp+57h+var_88], r14
0x18017e74e  mov     rax, [rcx]
0x18017e751  mov     rax, [rax+10h]
0x18017e755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e75a  nop
0x18017e75b  lea     rcx, [rbp+57h+var_80]; void *
0x18017e75f  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e764  nop
0x18017e765  mov     rcx, [rbp+57h+var_98]; string
0x18017e769  call    cs:__imp_WindowsDeleteString
0x18017e76f  mov     [rbp+57h+var_98], r14
0x18017e773  mov     rcx, [rbp+57h+var_90]; string
0x18017e777  call    cs:__imp_WindowsDeleteString
0x18017e77d  mov     [rbp+57h+var_90], r14
0x18017e781  lea     rcx, [rbp+57h+var_78]; void *
0x18017e785  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e78a  nop
0x18017e78b  lea     rcx, [rbp+57h+var_68]; void *
0x18017e78f  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e794  nop
0x18017e795  lea     rcx, [rbp+57h+var_70]; void *
0x18017e799  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017e79e  nop
0x18017e79f  mov     rcx, [rsi+8]; this
0x18017e7a3  test    rcx, rcx
0x18017e7a6  jz      short loc_18017E7AD
0x18017e7a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18017e7ad  xor     al, al
0x18017e7af  mov     rcx, [rbp+57h+var_20]
0x18017e7b3  xor     rcx, rsp; StackCookie
0x18017e7b6  call    __security_check_cookie
0x18017e7bb  lea     r11, [rsp+0C0h+var_10]
0x18017e7c3  mov     rbx, [r11+30h]
0x18017e7c7  mov     rsi, [r11+38h]
0x18017e7cb  mov     rsp, r11
0x18017e7ce  pop     r14
0x18017e7d0  pop     rdi
0x18017e7d1  pop     rbp
0x18017e7d2  retn
```
