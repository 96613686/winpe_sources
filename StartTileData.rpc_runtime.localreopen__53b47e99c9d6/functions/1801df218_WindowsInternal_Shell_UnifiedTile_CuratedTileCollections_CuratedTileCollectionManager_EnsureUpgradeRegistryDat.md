# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::EnsureUpgradeRegistryDataParsed(bool *)

- ea: `0x1801df218`
- end: `0x1801df5d4`
- name: `?EnsureUpgradeRegistryDataParsed@CuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAXPEA_N@Z`
- size: `956`
- prototype: `void __fastcall(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004aef0`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18003d040`
- `0x18004ce04`
- `0x18004ffc0`
- `0x18006f2b0`
- `0x180083e60`
- `0x180095c24`
- `0x1801238dc`
- `0x180154ea0`
- `0x18017d9d0`
- `0x1801df218`
- `0x1801df5dc`
- `0x1801df69c`
- `0x1801df700`
- `0x1801e0718`
- `0x1801e0fb8`
- `0x1801e1390`
- `0x180201e50`
- `0x180228ae8`
- `0x18024072c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df33a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df34a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df58f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df33a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df34a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df58f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801df59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801df3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801df423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801df3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801df423`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801df500`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801df500`

## string_xrefs

- `0x1801df28b`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1801df2c6`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1801df384`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1801df531`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1801df562`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::EnsureUpgradeRegistryDataParsed(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *this,
        bool *a2)
{
  __int64 v4; // rbx
  int v5; // eax
  int v6; // eax
  bool v7; // al
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, int *, int *, HSTRING *); // rbx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // r8
  PCWSTR v16; // rax
  __int64 v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rbx
  int v22; // edi
  int v23; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  _BYTE v26[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v33[7]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+C0h] [rbp-40h] BYREF
  int v37; // [rsp+C4h] [rbp-3Ch]
  _BYTE v38[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v39[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v40; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v32 = 0;
  v4 = *((_QWORD *)this + 9);
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.CuratedCollectionInitializationStatics",
    0x60u,
    0x5Fu);
  v5 = Windows::Foundation::GetActivationFactoryAsUser<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics>(
         v35,
         v4,
         &v32);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x318,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
      (const char *)(unsigned int)v5,
      v24);
  v26[0] = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v32 + 136LL))(v32, v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
      (const char *)(unsigned int)v6,
      v24);
  v7 = v26[0] != 0;
  *a2 = v26[0] != 0;
  if ( v7 )
  {
    if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
        CuratedTileCollectionManager_DetectOSUpgrade_UpgradeDetected);
    v29 = 0;
    v27 = 0;
    string = 0;
    v30 = 0;
    v8 = v32;
    v9 = *(__int64 (__fastcall **)(__int64, int *, int *, HSTRING *))(*(_QWORD *)v32 + 144LL);
    WindowsDeleteString(0);
    v30 = 0;
    WindowsDeleteString(string);
    string = 0;
    v10 = v9(v8, &v29, &v27, &string);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v10,
        (int)&v30);
    CDSHelpers::LoadCDSData<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(v33, *((_QWORD *)this + 9));
    v11 = *(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionTypesMap;
    v28 = *(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionTypesMap;
    while ( !*(_BYTE *)(v11 + 25) )
    {
      v12 = v11 + 32;
      v13 = std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry>>,0>>::_Find<std::wstring>(
              v33,
              v11 + 32);
      if ( v13 == v33[0] )
      {
        Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry::CuratedTileCollectionUpgradeEntry((Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry *)&v36);
        v36 = v29;
        v37 = v27;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v15 = -1;
        do
          ++v15;
        while ( StringRawBuffer[v15] );
        std::wstring::_Assign<unsigned short>(v38, StringRawBuffer);
        v16 = WindowsGetStringRawBuffer(v30, 0);
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
        std::wstring::_Assign<unsigned short>(v39, v16);
        v18 = *(_QWORD *)std::map<std::wstring,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry>::_Try_emplace<std::wstring const &,>(
                           v33,
                           &hstringHeader,
                           v12);
        *(_DWORD *)(v18 + 64) = v36;
        *(_DWORD *)(v18 + 68) = v37;
        std::wstring::operator=(v18 + 72, v38);
        std::wstring::operator=(v18 + 104, v39);
        ImageResourceInfo::~ImageResourceInfo((ImageResourceInfo *)&v36);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>>>,std::_Iterator_base0>::operator++(&v28);
      v11 = v28;
    }
    wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(
      &v28,
      *((_QWORD *)this + 9));
    wil::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(
      &v36,
      v33);
    v19 = v28;
    v28 = 0;
    v40 = v19;
    v20 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_____lambda_94bbb6a50da7c9561cd1b9f59a4a8c66___(
                       &hstringHeader,
                       &v36);
    v21 = *v20;
    *v20 = 0;
    if ( hstringHeader.Reserved.Reserved1 )
    {
      hstringHeader.Reserved.Reserved1 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ISelectionDataParser>::Release();
    }
    v22 = SHTaskPoolQueueTask(0, 64, 0, 0, v21, 0);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_::__lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_(&v36);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v22,
        v25);
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 128LL))(v32);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x350,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v23,
        v25);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v28);
    wil::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>::~cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(v33);
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(string);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v32);
}

```

## disassembly

```asm
0x1801df218  mov     [rsp-8+arg_10], rbx
0x1801df21d  mov     [rsp-8+arg_18], rsi
0x1801df222  push    rbp
0x1801df223  push    rdi
0x1801df224  push    r14
0x1801df226  lea     rbp, [rsp-20h]
0x1801df22b  sub     rsp, 120h
0x1801df232  mov     rax, cs:__security_cookie
0x1801df239  xor     rax, rsp
0x1801df23c  mov     [rbp+30h+var_20], rax
0x1801df240  mov     rdi, rdx
0x1801df243  mov     rsi, rcx
0x1801df246  xor     r14d, r14d
0x1801df249  mov     [rsp+130h+var_D8], r14
0x1801df24e  mov     rbx, [rcx+48h]
0x1801df252  mov     [rbp+30h+var_80], r14
0x1801df256  lea     r9d, [r14+5Fh]; unsigned int
0x1801df25a  lea     r8d, [r14+60h]; unsigned int
0x1801df25e  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_CuratedCollectionInitializationStatics@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Curat"...
0x1801df265  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x1801df269  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801df26e  nop
0x1801df26f  lea     r8, [rsp+130h+var_D8]
0x1801df274  mov     rdx, rbx
0x1801df277  mov     rcx, [rbp+30h+var_80]
0x1801df27b  call    ??$GetActivationFactoryAsUser@UICuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUICuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Z; Windows::Foundation::GetActivationFactoryAsUser<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics>(HSTRING__ *,Windows::System::IUser *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics * *)
0x1801df280  mov     rcx, [rbp+38h]; this
0x1801df284  test    eax, eax
0x1801df286  jns     short loc_1801DF29D
0x1801df288  mov     r9d, eax; char *
0x1801df28b  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801df292  mov     edx, 318h; void *
0x1801df297  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801df29d  mov     [rsp+130h+var_100], r14b
0x1801df2a2  mov     rcx, [rsp+130h+var_D8]
0x1801df2a7  mov     rax, [rcx]
0x1801df2aa  lea     rdx, [rsp+130h+var_100]
0x1801df2af  mov     rax, [rax+88h]
0x1801df2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df2bb  mov     rcx, [rbp+38h]; this
0x1801df2bf  test    eax, eax
0x1801df2c1  jns     short loc_1801DF2D8
0x1801df2c3  mov     r9d, eax; char *
0x1801df2c6  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801df2cd  mov     edx, 31Bh; void *
0x1801df2d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801df2d8  cmp     [rsp+130h+var_100], r14b
0x1801df2dd  setnz   al
0x1801df2e0  mov     [rdi], al
0x1801df2e2  test    al, al
0x1801df2e4  jz      loc_1801DF5A6
0x1801df2ea  mov     r9d, 1
0x1801df2f0  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, r9b
0x1801df2f7  jz      short loc_1801DF315
0x1801df2f9  lea     rax, [rbp+30h+hstringHeader]
0x1801df2fd  mov     qword ptr [rsp+130h+var_110], rax
0x1801df302  lea     rdx, CuratedTileCollectionManager_DetectOSUpgrade_UpgradeDetected
0x1801df309  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x1801df310  call    McGenEventWrite_EventWriteTransfer
0x1801df315  mov     [rsp+130h+var_F0], r14d
0x1801df31a  mov     [rsp+130h+var_FC], r14d
0x1801df31f  mov     [rsp+130h+string], r14
0x1801df324  mov     [rsp+130h+var_E8], r14
0x1801df329  mov     rdi, [rsp+130h+var_D8]
0x1801df32e  mov     rax, [rdi]
0x1801df331  mov     rbx, [rax+90h]
0x1801df338  xor     ecx, ecx; string
0x1801df33a  call    cs:__imp_WindowsDeleteString
0x1801df340  mov     [rsp+130h+var_E8], r14
0x1801df345  mov     rcx, [rsp+130h+string]; string
0x1801df34a  call    cs:__imp_WindowsDeleteString
0x1801df350  mov     [rsp+130h+string], r14
0x1801df355  lea     rax, [rsp+130h+var_E8]
0x1801df35a  mov     qword ptr [rsp+130h+var_110], rax; int
0x1801df35f  lea     r9, [rsp+130h+string]
0x1801df364  lea     r8, [rsp+130h+var_FC]
0x1801df369  lea     rdx, [rsp+130h+var_F0]
0x1801df36e  mov     rcx, rdi
0x1801df371  mov     rax, rbx
0x1801df374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df379  mov     rcx, [rbp+38h]; this
0x1801df37d  test    eax, eax
0x1801df37f  jns     short loc_1801DF396
0x1801df381  mov     r9d, eax; char *
0x1801df384  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801df38b  mov     edx, 329h; void *
0x1801df390  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801df396  mov     rdx, [rsi+48h]
0x1801df39a  lea     rcx, [rsp+130h+var_D0]
0x1801df39f  call    ??$LoadCDSData@UCuratedTileCollectionsManagerData@UnifiedTile@Data@Windows@@@CDSHelpers@@YA?AV?$cloud_store_data@UCuratedTileCollectionsManagerData@UnifiedTile@Data@Windows@@@wil@@PEAUIUser@System@Windows@@@Z; CDSHelpers::LoadCDSData<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(Windows::System::IUser *)
0x1801df3a4  nop
0x1801df3a5  mov     rax, qword ptr cs:?CollectionTypesMap@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@2@@std@@B; std::map<std::wstring,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes> const WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionTypesMap
0x1801df3ac  mov     rax, [rax]
0x1801df3af  mov     [rsp+130h+var_F8], rax
0x1801df3b4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801df3b8  cmp     [rax+19h], r14b
0x1801df3bc  jnz     loc_1801DF49A
0x1801df3c2  lea     rbx, [rax+20h]
0x1801df3c6  mov     rdx, rbx
0x1801df3c9  lea     rcx, [rsp+130h+var_D0]
0x1801df3ce  call    ??$_Find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry>>,0>>::_Find<std::wstring>(std::wstring const &)
0x1801df3d3  cmp     rax, [rsp+130h+var_D0]
0x1801df3d8  jnz     loc_1801DF486
0x1801df3de  lea     rcx, [rbp+30h+var_70]; this
0x1801df3e2  call    ??0CuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@QEAA@XZ; Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry::CuratedTileCollectionUpgradeEntry(void)
0x1801df3e7  nop
0x1801df3e8  mov     eax, [rsp+130h+var_F0]
0x1801df3ec  mov     [rbp+30h+var_70], eax
0x1801df3ef  mov     eax, [rsp+130h+var_FC]
0x1801df3f3  mov     [rbp+30h+var_6C], eax
0x1801df3f6  xor     edx, edx; length
0x1801df3f8  mov     rcx, [rsp+130h+string]; string
0x1801df3fd  call    cs:__imp_WindowsGetStringRawBuffer
0x1801df403  mov     r8, rdi
0x1801df406  inc     r8
0x1801df409  cmp     [rax+r8*2], r14w
0x1801df40e  jnz     short loc_1801DF406
0x1801df410  mov     rdx, rax
0x1801df413  lea     rcx, [rbp+30h+var_68]
0x1801df417  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801df41c  xor     edx, edx; length
0x1801df41e  mov     rcx, [rsp+130h+var_E8]; string
0x1801df423  call    cs:__imp_WindowsGetStringRawBuffer
0x1801df429  mov     r8, rdi
0x1801df42c  inc     r8
0x1801df42f  cmp     [rax+r8*2], r14w
0x1801df434  jnz     short loc_1801DF42C
0x1801df436  mov     rdx, rax
0x1801df439  lea     rcx, [rbp+30h+var_48]
0x1801df43d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801df442  mov     r8, rbx
0x1801df445  lea     rdx, [rbp+30h+hstringHeader]
0x1801df449  lea     rcx, [rsp+130h+var_D0]
0x1801df44e  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCuratedTileCollectionUpgradeEntry@UnifiedTile@Data@Windows@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::UnifiedTile::CuratedTileCollectionUpgradeEntry>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1801df453  mov     rbx, [rax]
0x1801df456  mov     eax, [rbp+30h+var_70]
0x1801df459  mov     [rbx+40h], eax
0x1801df45c  mov     eax, [rbp+30h+var_6C]
0x1801df45f  mov     [rbx+44h], eax
0x1801df462  lea     rcx, [rbx+48h]
0x1801df466  lea     rdx, [rbp+30h+var_68]
0x1801df46a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801df46f  lea     rcx, [rbx+68h]
0x1801df473  lea     rdx, [rbp+30h+var_48]
0x1801df477  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801df47c  nop
0x1801df47d  lea     rcx, [rbp+30h+var_70]; this
0x1801df481  call    ??1ImageResourceInfo@@QEAA@XZ; ImageResourceInfo::~ImageResourceInfo(void)
0x1801df486  lea     rcx, [rsp+130h+var_F8]
0x1801df48b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>>>,std::_Iterator_base0>::operator++(void)
0x1801df490  mov     rax, [rsp+130h+var_F8]
0x1801df495  jmp     loc_1801DF3B8
0x1801df49a  mov     rdx, [rsi+48h]
0x1801df49e  lea     rcx, [rsp+130h+var_F8]
0x1801df4a3  call    ??0?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIBuffer@Streams@Storage@Windows@@@Z; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(Windows::Storage::Streams::IBuffer *)
0x1801df4a8  nop
0x1801df4a9  lea     rdx, [rsp+130h+var_D0]
0x1801df4ae  lea     rcx, [rbp+30h+var_70]
0x1801df4b2  call    ??0?$cloud_store_data@UCuratedTileCollectionsManagerData@UnifiedTile@Data@Windows@@@wil@@QEAA@AEBV01@@Z; wil::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(wil::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData> const &)
0x1801df4b7  mov     rax, [rsp+130h+var_F8]
0x1801df4bc  mov     [rsp+130h+var_F8], r14
0x1801df4c1  mov     [rbp+30h+var_38], rax
0x1801df4c5  lea     rdx, [rbp+30h+var_70]
0x1801df4c9  lea     rcx, [rbp+30h+hstringHeader]
0x1801df4cd  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_____lambda_94bbb6a50da7c9561cd1b9f59a4a8c66___
0x1801df4d2  mov     rbx, [rax]
0x1801df4d5  mov     [rax], r14
0x1801df4d8  mov     rcx, qword ptr [rbp+30h+hstringHeader.Reserved]
0x1801df4dc  test    rcx, rcx
0x1801df4df  jz      short loc_1801DF4EA
0x1801df4e1  mov     qword ptr [rbp+30h+hstringHeader.Reserved], r14
0x1801df4e5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ISelectionDataParser>::Release(void)
0x1801df4ea  mov     [rsp+130h+var_108], r14
0x1801df4ef  mov     qword ptr [rsp+130h+var_110], rbx; int
0x1801df4f4  xor     r9d, r9d
0x1801df4f7  xor     r8d, r8d
0x1801df4fa  lea     edx, [r9+40h]
0x1801df4fe  xor     ecx, ecx
0x1801df500  call    cs:__imp_SHTaskPoolQueueTask
0x1801df506  mov     edi, eax
0x1801df508  test    rbx, rbx
0x1801df50b  jz      short loc_1801DF51D
0x1801df50d  mov     rdx, [rbx]
0x1801df510  mov     rcx, rbx
0x1801df513  mov     rax, [rdx+10h]
0x1801df517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df51c  nop
0x1801df51d  lea     rcx, [rbp+30h+var_70]
0x1801df521  call    _lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_____lambda_94bbb6a50da7c9561cd1b9f59a4a8c66_
0x1801df526  mov     rcx, [rbp+38h]; this
0x1801df52a  test    edi, edi
0x1801df52c  jns     short loc_1801DF543
0x1801df52e  mov     r9d, edi; char *
0x1801df531  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801df538  mov     edx, 34Ch; void *
0x1801df53d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801df543  mov     rcx, [rsp+130h+var_D8]
0x1801df548  mov     rax, [rcx]
0x1801df54b  mov     rax, [rax+80h]
0x1801df552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df557  mov     rcx, [rbp+38h]; this
0x1801df55b  test    eax, eax
0x1801df55d  jns     short loc_1801DF574
0x1801df55f  mov     r9d, eax; char *
0x1801df562  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801df569  mov     edx, 350h; void *
0x1801df56e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801df574  lea     rcx, [rsp+130h+var_F8]; void *
0x1801df579  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801df57e  nop
0x1801df57f  lea     rcx, [rsp+130h+var_D0]
0x1801df584  call    ??1?$cloud_store_data@UCuratedTileCollectionsManagerData@UnifiedTile@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>::~cloud_store_data<Windows::Data::UnifiedTile::CuratedTileCollectionsManagerData>(void)
0x1801df589  nop
0x1801df58a  mov     rcx, [rsp+130h+var_E8]; string
0x1801df58f  call    cs:__imp_WindowsDeleteString
0x1801df595  mov     [rsp+130h+var_E8], r14
0x1801df59a  mov     rcx, [rsp+130h+string]; string
0x1801df59f  call    cs:__imp_WindowsDeleteString
0x1801df5a5  nop
0x1801df5a6  lea     rcx, [rsp+130h+var_D8]; void *
0x1801df5ab  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801df5b0  mov     rcx, [rbp+30h+var_20]
0x1801df5b4  xor     rcx, rsp; StackCookie
0x1801df5b7  call    __security_check_cookie
0x1801df5bc  lea     r11, [rsp+130h+var_10]
0x1801df5c4  mov     rbx, [r11+30h]
0x1801df5c8  mov     rsi, [r11+38h]
0x1801df5cc  mov     rsp, r11
0x1801df5cf  pop     r14
0x1801df5d1  pop     rdi
0x1801df5d2  pop     rbp
0x1801df5d3  retn
```
