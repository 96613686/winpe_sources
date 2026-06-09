# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::UnresolvedLinkPathTileInitializationHandler::InitializeTile(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>)

- ea: `0x18016d160`
- end: `0x18016d3e4`
- name: `?InitializeTile@UnresolvedLinkPathTileInitializationHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@UEAAXV?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@Z`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001ac50`
- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x18016d160`
- `0x18016d3ec`
- `0x18016df10`
- `0x18017cee8`
- `0x18017cf7c`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016d378`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016d1c2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016d2b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016d1c2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18016d2b6`

## string_xrefs

- `0x18016d1d3`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\unresolvedlinkpathtileinitializationhandler.cpp`
- `0x18016d23c`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\unresolvedlinkpathtileinitializationhandler.cpp`
- `0x18016d2c7`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\unresolvedlinkpathtileinitializationhandler.cpp`
- `0x18016d312`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\unresolvedlinkpathtileinitializationhandler.cpp`
- `0x18016d3d2`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\unresolvedlinkpathtileinitializationhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::UnresolvedLinkPathTileInitializationHandler::InitializeTile(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // eax
  __int64 TileIdentifier; // rax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, HSTRING, HSTRING *); // rbx
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  std::_Ref_count_base *v13; // rcx
  HSTRING string; // [rsp+20h] [rbp-29h] BYREF
  HSTRING v15; // [rsp+28h] [rbp-21h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *v16; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v17; // [rsp+38h] [rbp-11h] BYREF
  __int64 v18; // [rsp+40h] [rbp-9h] BYREF
  __int64 v19; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  __int64 v22; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v20[1] = a2;
  v19 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.CuratedCollectionInitializationStatics",
    0x60u,
    0x5Fu);
  ActivationFactory = RoGetActivationFactory(v22, &GUID_b8876332_e375_4688_8e01_3c35c99b93e1, &v19);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\unresolvedlinkpath"
                    "tileinitializationhandler.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
  TileIdentifier = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                     *a2,
                     &v17);
  wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
    TileIdentifier,
    v20);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v17);
  v15 = 0;
  v5 = v20[0];
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20[0] + 48LL);
  WindowsDeleteString(0);
  v15 = 0;
  v7 = v6(v5, &v15);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\unresolvedlinkpath"
                    "tileinitializationhandler.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
  string = 0;
  v8 = v19;
  v9 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v19 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v9(v8, v15, &string) < 0 )
  {
    if ( !*(_BYTE *)(*a2 + 297LL) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\unresolvedlinkpa"
                      "thtileinitializationhandler.cpp",
        (const char *)0x8000FFFFLL,
        (int)string);
  }
  else
  {
    v18 = 0;
    v22 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsInternal.Shell.UnifiedTile.UnifiedTileIdentifier",
      0x38u,
      0x37u);
    v10 = RoGetActivationFactory(v22, &GUID_87a52467_266a_4b20_a2c8_e316bfbaf64a, &v18);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\unresolvedlinkpa"
                      "thtileinitializationhandler.cpp",
        (const char *)(unsigned int)v10,
        (int)string);
    wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifierStatics,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifierFactory>(
      &v18,
      &v17);
    v16 = 0;
    v11 = *v17;
    v16 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **))(v11 + 48))(
            v17,
            string,
            &v16);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\unresolvedlinkpa"
                      "thtileinitializationhandler.cpp",
        (const char *)(unsigned int)v12,
        (int)string);
    WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::UpdateTileIdentifier(
      (WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile *)*a2,
      v16);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v16);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v17);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v18);
  }
  *(_BYTE *)(*a2 + 296LL) = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v15);
  v15 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v20);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v19);
  v13 = (std::_Ref_count_base *)a2[1];
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
}

```

## disassembly

```asm
0x18016d160  mov     [rsp-8+arg_0], rbx
0x18016d165  mov     [rsp-8+arg_10], rsi
0x18016d16a  push    rbp
0x18016d16b  push    rdi
0x18016d16c  push    r14
0x18016d16e  lea     rbp, [rsp-47h]
0x18016d173  sub     rsp, 90h
0x18016d17a  mov     rax, cs:__security_cookie
0x18016d181  xor     rax, rsp
0x18016d184  mov     [rbp+57h+var_20], rax
0x18016d188  mov     rsi, rdx
0x18016d18b  mov     [rbp+57h+var_48], rdx
0x18016d18f  xor     r14d, r14d
0x18016d192  mov     [rbp+57h+var_58], r14
0x18016d196  mov     [rbp+57h+var_28], r14
0x18016d19a  lea     r9d, [r14+5Fh]; unsigned int
0x18016d19e  lea     r8d, [r14+60h]; unsigned int
0x18016d1a2  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_CuratedCollectionInitializationStatics@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Curat"...
0x18016d1a9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18016d1ad  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18016d1b2  nop
0x18016d1b3  lea     r8, [rbp+57h+var_58]
0x18016d1b7  lea     rdx, _GUID_b8876332_e375_4688_8e01_3c35c99b93e1
0x18016d1be  mov     rcx, [rbp+57h+var_28]
0x18016d1c2  call    cs:__imp_RoGetActivationFactory
0x18016d1c8  mov     rcx, [rbp+5Fh]; this
0x18016d1cc  test    eax, eax
0x18016d1ce  jns     short loc_18016D1E4
0x18016d1d0  mov     r9d, eax; char *
0x18016d1d3  lea     r8, aShellcommonShe_95; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016d1da  lea     edx, [r14+1Fh]; void *
0x18016d1de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016d1e4  lea     rdx, [rbp+57h+var_68]
0x18016d1e8  mov     rcx, [rsi]
0x18016d1eb  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18016d1f0  nop
0x18016d1f1  lea     rdx, [rbp+57h+var_50]
0x18016d1f5  mov     rcx, rax
0x18016d1f8  call    ??$query@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(void)
0x18016d1fd  nop
0x18016d1fe  lea     rcx, [rbp+57h+var_68]; void *
0x18016d202  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d207  mov     [rbp+57h+var_78], r14
0x18016d20b  mov     rdi, [rbp+57h+var_50]
0x18016d20f  mov     rax, [rdi]
0x18016d212  mov     rbx, [rax+30h]
0x18016d216  xor     ecx, ecx; string
0x18016d218  call    cs:__imp_WindowsDeleteString
0x18016d21e  mov     [rbp+57h+var_78], r14
0x18016d222  lea     rdx, [rbp+57h+var_78]
0x18016d226  mov     rcx, rdi
0x18016d229  mov     rax, rbx
0x18016d22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d231  mov     rcx, [rbp+5Fh]; this
0x18016d235  test    eax, eax
0x18016d237  jns     short loc_18016D24E
0x18016d239  mov     r9d, eax; char *
0x18016d23c  lea     r8, aShellcommonShe_95; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016d243  mov     edx, 23h ; '#'; void *
0x18016d248  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016d24e  mov     [rbp+57h+string], r14
0x18016d252  mov     rdi, [rbp+57h+var_58]
0x18016d256  mov     rax, [rdi]
0x18016d259  mov     rbx, [rax+68h]
0x18016d25d  xor     ecx, ecx; string
0x18016d25f  call    cs:__imp_WindowsDeleteString
0x18016d265  mov     [rbp+57h+string], r14
0x18016d269  lea     r8, [rbp+57h+string]
0x18016d26d  mov     rdx, [rbp+57h+var_78]
0x18016d271  mov     rcx, rdi
0x18016d274  mov     rax, rbx
0x18016d277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d27c  test    eax, eax
0x18016d27e  js      loc_18016D350
0x18016d284  mov     [rbp+57h+var_60], r14
0x18016d288  mov     [rbp+57h+var_28], r14
0x18016d28c  mov     r9d, 37h ; '7'; unsigned int
0x18016d292  lea     r8d, [r9+1]; unsigned int
0x18016d296  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileIdentifier@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x18016d29d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18016d2a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18016d2a6  nop
0x18016d2a7  lea     r8, [rbp+57h+var_60]
0x18016d2ab  lea     rdx, _GUID_87a52467_266a_4b20_a2c8_e316bfbaf64a
0x18016d2b2  mov     rcx, [rbp+57h+var_28]
0x18016d2b6  call    cs:__imp_RoGetActivationFactory
0x18016d2bc  mov     rcx, [rbp+5Fh]; this
0x18016d2c0  test    eax, eax
0x18016d2c2  jns     short loc_18016D2D9
0x18016d2c4  mov     r9d, eax; char *
0x18016d2c7  lea     r8, aShellcommonShe_95; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016d2ce  mov     edx, 28h ; '('; void *
0x18016d2d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016d2d9  lea     rdx, [rbp+57h+var_68]
0x18016d2dd  lea     rcx, [rbp+57h+var_60]
0x18016d2e1  call    ??$query@UIWin32UnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@@?$com_ptr_t@UIUnifiedTileIdentifierStatics@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWin32UnifiedTileIdentifierFactory@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifierStatics,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifierFactory>(void)
0x18016d2e6  nop
0x18016d2e7  mov     [rbp+57h+var_70], r14
0x18016d2eb  mov     rcx, [rbp+57h+var_68]
0x18016d2ef  mov     rax, [rcx]
0x18016d2f2  mov     [rbp+57h+var_70], r14
0x18016d2f6  lea     r8, [rbp+57h+var_70]
0x18016d2fa  mov     rdx, [rbp+57h+string]
0x18016d2fe  mov     rax, [rax+30h]
0x18016d302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d307  mov     rcx, [rbp+5Fh]; this
0x18016d30b  test    eax, eax
0x18016d30d  jns     short loc_18016D324
0x18016d30f  mov     r9d, eax; char *
0x18016d312  lea     r8, aShellcommonShe_95; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016d319  mov     edx, 2Bh ; '+'; void *
0x18016d31e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016d324  mov     rdx, [rbp+57h+var_70]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *
0x18016d328  mov     rcx, [rsi]; this
0x18016d32b  call    ?UpdateTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAAXPEAUIUnifiedTileIdentifier@456@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::UpdateTileIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x18016d330  nop
0x18016d331  lea     rcx, [rbp+57h+var_70]; void *
0x18016d335  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d33a  nop
0x18016d33b  lea     rcx, [rbp+57h+var_68]; void *
0x18016d33f  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d344  nop
0x18016d345  lea     rcx, [rbp+57h+var_60]; void *
0x18016d349  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d34e  jmp     short loc_18016D35C
0x18016d350  mov     rax, [rsi]
0x18016d353  cmp     [rax+129h], r14b
0x18016d35a  jz      short loc_18016D3C8
0x18016d35c  mov     rax, [rsi]
0x18016d35f  mov     [rax+128h], r14b
0x18016d366  mov     rcx, [rbp+57h+string]; string
0x18016d36a  call    cs:__imp_WindowsDeleteString
0x18016d370  mov     [rbp+57h+string], r14
0x18016d374  mov     rcx, [rbp+57h+var_78]; string
0x18016d378  call    cs:__imp_WindowsDeleteString
0x18016d37e  mov     [rbp+57h+var_78], r14
0x18016d382  lea     rcx, [rbp+57h+var_50]; void *
0x18016d386  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d38b  nop
0x18016d38c  lea     rcx, [rbp+57h+var_58]; void *
0x18016d390  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016d395  nop
0x18016d396  mov     rcx, [rsi+8]; this
0x18016d39a  test    rcx, rcx
0x18016d39d  jz      short loc_18016D3A4
0x18016d39f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18016d3a4  mov     rcx, [rbp+57h+var_20]
0x18016d3a8  xor     rcx, rsp; StackCookie
0x18016d3ab  call    __security_check_cookie
0x18016d3b0  lea     r11, [rsp+0A0h+var_10]
0x18016d3b8  mov     rbx, [r11+20h]
0x18016d3bc  mov     rsi, [r11+30h]
0x18016d3c0  mov     rsp, r11
0x18016d3c3  pop     r14
0x18016d3c5  pop     rdi
0x18016d3c6  pop     rbp
0x18016d3c7  retn
0x18016d3c8  mov     rcx, [rbp+5Fh]; this
0x18016d3cc  mov     r9d, 8000FFFFh; char *
0x18016d3d2  lea     r8, aShellcommonShe_95; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016d3d9  mov     edx, 36h ; '6'; void *
0x18016d3de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
