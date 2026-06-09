# DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformer(DataStoreCache::IDataManager *,Windows::System::IUser *,DataStoreCache::PlaceholderTileTransformer::PlaceholderTileTransformerOptions,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformerTestHook>,DataStoreCache::IMRTTransformer *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileBatchCookie> *)

- ea: `0x1800b3bec`
- end: `0x1800b4668`
- name: `??0PlaceholderTileTransformer@Internal@0DataStoreCache@@QEAA@PEAUIDataManager@2@PEAUIUser@System@Windows@@W4PlaceholderTileTransformerOptions@02@V?$shared_ptr@UPlaceholderTileTransformerTestHook@Internal@PlaceholderTileTransformer@DataStoreCache@@@std@@PEAUIMRTTransformer@2@PEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@PEAV?$shared_ptr@VIPlaceholderTileBatchCookie@PlaceholderTileTransformer@DataStoreCache@@@9@@Z`
- size: `2684`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18010d270`

## callees

- `0x18000befc`
- `0x18000cb0c`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001dac0`
- `0x180021b78`
- `0x18002cf08`
- `0x18003b1c0`
- `0x18005020c`
- `0x18005821c`
- `0x18006ca70`
- `0x18006d0d0`
- `0x1800963a0`
- `0x1800b2e60`
- `0x1800b2e94`
- `0x1800b2f1c`
- `0x1800b2fec`
- `0x1800b308c`
- `0x1800b321c`
- `0x1800b36fc`
- `0x1800b38bc`
- `0x1800b3bec`
- `0x1800b5aa0`
- `0x1800df0a8`
- `0x1800e01d8`
- `0x1800ecc9c`
- `0x18011f520`
- `0x180147be8`
- `0x1801506f0`
- `0x180161204`
- `0x18017d9d0`
- `0x180197f6c`
- `0x180201e50`
- `0x18020295c`
- `0x18020be30`
- `0x1803664a4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b3dd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b3dd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b4471`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b4471`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b44f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b44f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3e19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b430a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3e19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b430a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b4322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3e50`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4381`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4381`

## string_xrefs

- `0x1800b3f90`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1800b44fb`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1800b4510`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1800b4540`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformer(
        __int64 a1,
        std::_Ref_count_base *a2,
        __int64 a3,
        __int64 a4,
        std::_Ref_count_base ***a5,
        RTL_SRWLOCK *a6,
        std::_Ref_count_base *a7,
        std::_Ref_count_base **a8)
{
  int v10; // r15d
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  std::_Ref_count_base **v14; // r13
  _QWORD *v15; // r12
  struct Windows::System::IUser **v16; // rdx
  HSTRING v17; // rcx
  std::_Ref_count_base *v18; // rdi
  __int64 (__fastcall *v19)(std::_Ref_count_base *, HSTRING *); // rbx
  int v20; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // r9d
  std::_Ref_count_base *v25; // rbx
  std::_Ref_count_base *v26; // rcx
  std::_Ref_count_base *v27; // rcx
  std::_Ref_count_base ***v28; // rsi
  __int64 v29; // r8
  __int64 v30; // rdx
  std::_Ref_count_base *v31; // rbx
  std::_Ref_count_base **v32; // rdi
  std::_Ref_count_base **v33; // rcx
  std::_Ref_count_base *v34; // rax
  std::_Ref_count_base *v35; // r12
  int v36; // r15d
  std::_Ref_count_base *v37; // rdi
  std::_Ref_count_base *v38; // rsi
  std::_Ref_count_base *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rax
  std::_Ref_count_base ***v42; // rdi
  std::_Ref_count_base *v43; // rbx
  std::_Ref_count_base *v44; // rax
  std::_Ref_count_base *v45; // rcx
  std::_Ref_count_base *v46; // rax
  _QWORD *v47; // rdx
  std::_Ref_count_base *v48; // rbx
  std::_Ref_count_base *v49; // rax
  std::_Ref_count_base *v50; // rcx
  std::_Ref_count_base *v51; // rax
  _BYTE *v52; // rdx
  HRESULT v53; // eax
  __int64 v54; // rcx
  HRESULT v55; // eax
  int ActivationFactory; // eax
  std::_Ref_count_base **v57; // rdx
  std::_Ref_count_base *v58; // rbx
  std::_Ref_count_base *v59; // rcx
  std::_Ref_count_base *v60; // rcx
  std::_Ref_count_base *v62; // rax
  std::_Ref_count_base *v63; // rcx
  std::_Ref_count_base *v64; // rax
  int CurrentUser; // eax
  std::_Ref_count_base **v66; // rcx
  int v67; // r15d
  __int64 v68; // rax
  std::_Ref_count_base *v69; // rcx
  _QWORD *v70; // rax
  int v71; // [rsp+20h] [rbp-E0h]
  std::_Ref_count_base *v72[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v73; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v74[2]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v75[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v76; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v78[2]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base ***v79; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v80; // [rsp+98h] [rbp-68h]
  std::_Ref_count_base *v81[2]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v82; // [rsp+B0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v83; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base **v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+C8h] [rbp-38h]
  __int64 v86; // [rsp+D0h] [rbp-30h]
  __int128 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v88; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v89; // [rsp+F0h] [rbp-10h]
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v91; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v92[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v93; // [rsp+158h] [rbp+58h]
  _BYTE v94[56]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE *v95; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v85 = a1;
  v78[0] = a2;
  v79 = a5;
  v86 = (__int64)a5;
  v83 = a6;
  v75[0] = a7;
  v84 = a8;
  v10 = 0;
  LODWORD(v73) = 0;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>();
  *(_QWORD *)a1 = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable';
  *(_QWORD *)(a1 + 8) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>>'};
  *(_QWORD *)(a1 + 40) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>>'};
  *(_QWORD *)(a1 + 48) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `WindowsInternal::Shell::UnifiedTile::ITileActivator'};
  *(_QWORD *)(a1 + 56) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'};
  *(_QWORD *)(a1 + 64) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource'};
  *(_QWORD *)(a1 + 72) = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'};
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  wil::GetActivationFactory<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifierStatics>(a1 + 168);
  v72[0] = (std::_Ref_count_base *)a1;
  v11 = (__int64 *)wil::MakeAndInitializeOrThrow<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileCollectionDataUpdater,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer *,DataStoreCache::IDataManager * &,DataStoreCache::IMRTTransformer * &,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &>(
                     (unsigned int)&v73,
                     (unsigned int)v72,
                     (unsigned int)v78,
                     (unsigned int)&v83,
                     (unsigned int)v75);
  v12 = *v11;
  *v11 = 0;
  *(_QWORD *)(a1 + 176) = v12;
  v13 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = (std::_Ref_count_base **)(a1 + 184);
  *(_QWORD *)(a1 + 184) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
    a1 + 192,
    a5);
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  v15 = (_QWORD *)(a1 + 224);
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  AcquireSRWLockExclusive(&DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock);
  v83 = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock;
  if ( !*v14 )
  {
    *v14 = 0;
    CurrentUser = UserHelpers::GetCurrentUser((UserHelpers *)(a1 + 184), v16);
    if ( CurrentUser < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)CurrentUser,
        v71);
  }
  v87 = 0;
  v88 = 0;
  v89 = 0;
  std::wstring::_Construct_empty(&v87);
  v17 = 0;
  string = 0;
  v18 = *v14;
  if ( *v14 )
  {
    v19 = *(__int64 (__fastcall **)(std::_Ref_count_base *, HSTRING *))(*(_QWORD *)v18 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v20 = v19(v18, &string);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v20,
        v71);
    v17 = string;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
  v22 = -1;
  do
    ++v22;
  while ( StringRawBuffer[v22] );
  std::wstring::_Assign<unsigned short>(&v87, StringRawBuffer);
  std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::find(
    v23,
    v72,
    &v87);
  v25 = v72[0];
  if ( v72[0] != (std::_Ref_count_base *)qword_1804DCCA8 )
  {
    *(_OWORD *)v72 = 0;
    v26 = (std::_Ref_count_base *)*((_QWORD *)v25 + 7);
    if ( v26 && std::_Ref_count_base::_Incref_nz(v26) )
    {
      v72[0] = *((std::_Ref_count_base **)v25 + 6);
      v72[1] = *((std::_Ref_count_base **)v25 + 7);
    }
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 208,
      v72);
    if ( v72[1] )
      std::_Ref_count_base::_Decref(v72[1]);
    *(_OWORD *)v72 = 0;
    v27 = (std::_Ref_count_base *)*((_QWORD *)v25 + 9);
    if ( v27 && std::_Ref_count_base::_Incref_nz(v27) )
    {
      v72[0] = *((std::_Ref_count_base **)v25 + 8);
      v72[1] = *((std::_Ref_count_base **)v25 + 9);
    }
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 224,
      v72);
    if ( v72[1] )
      std::_Ref_count_base::_Decref(v72[1]);
  }
  if ( !*(_QWORD *)(a1 + 208) )
  {
    v33 = *v79;
    if ( *v79 )
    {
      v34 = v33[1];
      if ( v34 )
        _InterlockedIncrement((volatile signed __int32 *)v34 + 2);
      v74[0] = *v33;
      v35 = v33[1];
      v74[1] = v35;
      v75[0] = (std::_Ref_count_base *)v74;
      v36 = 1;
    }
    else
    {
      *(_OWORD *)v81 = 0;
      v75[0] = (std::_Ref_count_base *)v81;
      v36 = 2;
      v35 = v74[1];
    }
    LODWORD(v73) = v36;
    v37 = *v14;
    v38 = (std::_Ref_count_base *)operator new(0xF8u);
    v72[0] = v38;
    *(_OWORD *)v38 = 0;
    *((_DWORD *)v38 + 2) = 1;
    *((_DWORD *)v38 + 3) = 1;
    *(_QWORD *)v38 = &std::_Ref_count_obj2<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::`vftable';
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
    DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>(
      (_DWORD)v38 + 16,
      (_DWORD)v37,
      0,
      (unsigned int)&hstringHeader,
      (__int64)v75[0]);
    *(_OWORD *)v74 = 0;
    v10 = v36 | 0x20;
    std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::_Set_ptr_rep_and_enable_shared<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>(
      v74,
      (char *)v38 + 16,
      v38);
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 208,
      v74);
    v39 = v74[1];
    if ( v74[1] )
      std::_Ref_count_base::_Decref(v74[1]);
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      v39 = v81[1];
      if ( v81[1] )
        std::_Ref_count_base::_Decref(v81[1]);
    }
    if ( (v10 & 1) != 0 )
    {
      v10 &= ~1u;
      if ( v35 )
        std::_Ref_count_base::_Decref(v35);
    }
    v40 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::_Try_emplace<std::wstring const &,>(
                      v39,
                      &hstringHeader,
                      &v87);
    std::weak_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::operator=<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,0>(
      *v40 + 48LL,
      a1 + 208);
    v15 = (_QWORD *)(a1 + 224);
  }
  v28 = v79;
  if ( !*v15 )
  {
    if ( *v79 )
    {
      v66 = (std::_Ref_count_base **)std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
                                       v74,
                                       *v79 + 2);
      v67 = v10 | 4;
    }
    else
    {
      *(_OWORD *)v81 = 0;
      v66 = v81;
      v67 = v10 | 8;
    }
    LODWORD(v73) = v67;
    LODWORD(v79) = 0;
    v72[0] = *v14;
    v68 = std::make_shared<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>,Windows::System::IUser *,enum DataStoreCache::CloudUtil::Internal::CloudItemManagerOptions,std::nullptr_t,std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManagerTestHook<Windows::Data::PlaceholderTileCollectionLocal>>>(
            (unsigned int)&hstringHeader,
            (unsigned int)v72,
            (unsigned int)&v79,
            v24,
            (__int64)v66);
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      v15,
      v68);
    v69 = *(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8];
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
    if ( (v67 & 8) != 0 )
    {
      LOBYTE(v67) = v67 & 0xF7;
      v69 = v81[1];
      if ( v81[1] )
        std::_Ref_count_base::_Decref(v81[1]);
    }
    if ( (v67 & 4) != 0 )
    {
      v69 = v74[1];
      if ( v74[1] )
        std::_Ref_count_base::_Decref(v74[1]);
    }
    v70 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::_Try_emplace<std::wstring const &,>(
                      v69,
                      &hstringHeader,
                      &v87);
    std::weak_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::operator=<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,0>(
      *v70 + 64LL,
      v15);
  }
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
    a1 + 160,
    v78[0]);
  LOBYTE(v29) = 3;
  LOBYTE(v30) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::GetImpl'::`2'::impl,
    v30,
    v29);
  v31 = (std::_Ref_count_base *)operator new(0x70u);
  v72[0] = v31;
  memset_0(v31, 0, 0x70u);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::PlaceholderTileMigrationManager(v31);
  *(_QWORD *)v31 = &winrt::impl::heap_implements<DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager>::`vftable';
  v82 = v31;
  v32 = (std::_Ref_count_base **)(a1 + 288);
  if ( (std::_Ref_count_base **)(a1 + 288) == &v82 )
  {
    if ( v31 )
      winrt::com_ptr<winrt::WindowsInternal::Shell::UnifiedTile::Shim::implementation::UnifiedTile>::unconditional_release_ref(&v82);
  }
  else
  {
    if ( *v32 )
      winrt::com_ptr<winrt::WindowsInternal::Shell::UnifiedTile::Shim::implementation::UnifiedTile>::unconditional_release_ref(a1 + 288);
    *v32 = v31;
  }
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::BeginBatchUpdate(a1 + 72, v75);
  v76 = 0;
  v72[0] = (std::_Ref_count_base *)&v76;
  v41 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v72);
  Microsoft::WRL::AsWeak<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileCollectionDataUpdater>(
    *(_QWORD *)(a1 + 176),
    v41);
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetRoamedData(a1, &v79);
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetLocalData(a1, v81);
  v42 = v79;
  v43 = v76;
  if ( v76 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v76 + 8LL))(v76);
  v92[0] = &std::_Func_impl_no_alloc<_lambda_a5e86e17d5fff25afa4e610f10d0a9dc_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>> const &>::`vftable';
  v92[1] = v43;
  v72[0] = 0;
  v93 = v92;
  DataStoreCache::CloudUtil::Internal::ObservableCloudItem<DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::AddObserver(
    v42[8],
    v78,
    v92);
  v44 = v78[0];
  v45 = v78[1];
  *(_OWORD *)v78 = 0;
  *(_QWORD *)(a1 + 240) = v44;
  v46 = *(std::_Ref_count_base **)(a1 + 248);
  *(_QWORD *)(a1 + 248) = v45;
  if ( v46 )
  {
    std::_Ref_count_base::_Decref(v46);
    if ( v78[1] )
      std::_Ref_count_base::_Decref(v78[1]);
  }
  if ( v93 )
  {
    v47 = v92;
    LOBYTE(v47) = v93 != v92;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v93 + 32LL))(v93, v47);
    v93 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v72);
  v48 = v81[0];
  v78[0] = v76;
  if ( v76 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v76 + 8LL))(v76);
  v95 = 0;
  v95 = (_BYTE *)std::_Func_impl_no_alloc<_lambda_870dd18122e8a1af77c82753ebc9f10e_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> const &>::_Func_impl_no_alloc<_lambda_870dd18122e8a1af77c82753ebc9f10e_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> const &>(
                   v94,
                   v78);
  DataStoreCache::CloudUtil::Internal::ObservableCloudItem<DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::AddObserver(
    *((_QWORD *)v48 + 8),
    v72,
    v94);
  v49 = v72[0];
  v50 = v72[1];
  *(_OWORD *)v72 = 0;
  *(_QWORD *)(a1 + 256) = v49;
  v51 = *(std::_Ref_count_base **)(a1 + 264);
  *(_QWORD *)(a1 + 264) = v50;
  if ( v51 )
  {
    std::_Ref_count_base::_Decref(v51);
    if ( v72[1] )
      std::_Ref_count_base::_Decref(v72[1]);
  }
  if ( v95 )
  {
    v52 = v94;
    LOBYTE(v52) = v95 != v94;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v95 + 32LL))(v95, v52);
    v95 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v78);
  WindowsDeleteString(*(HSTRING *)(a1 + 280));
  *(_QWORD *)(a1 + 280) = 0;
  v53 = WindowsCreateString(L"PlaceholderTileVerbProvider", 0x1Bu, (HSTRING *)(a1 + 280));
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)v53,
      v71);
  v54 = *(_QWORD *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  v91 = 0;
  v55 = WindowsCreateStringReference(
          L"WindowsInternal.Shell.UnifiedTile.Private.VerbStringHelper",
          0x3Au,
          &hstringHeader,
          &v91);
  if ( v55 < 0 )
  {
    RaiseException(v55, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v91, &GUID_773a5acc_918a_4eed_ba13_62bd17ee0dcf, a1 + 272);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v71);
  v57 = v84;
  if ( v84 )
  {
    v62 = v75[0];
    v63 = v75[1];
    *(_OWORD *)v75 = 0;
    *v84 = v62;
    v64 = v57[1];
    v57[1] = v63;
    if ( v64 )
      std::_Ref_count_base::_Decref(v64);
    v58 = v75[1];
  }
  else
  {
    *(_OWORD *)v74 = 0;
    v58 = v75[1];
    if ( v75[1] )
      _InterlockedIncrement((volatile signed __int32 *)v75[1] + 2);
    *(_OWORD *)v74 = *(_OWORD *)v75;
    DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::EndBatchUpdate(
      a1 + 72,
      &hstringHeader,
      v74);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  }
  if ( v81[1] )
    std::_Ref_count_base::_Decref(v81[1]);
  if ( v80 )
    std::_Ref_count_base::_Decref(v80);
  v59 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v59 + 16LL))(v59);
  }
  if ( v58 )
    std::_Ref_count_base::_Decref(v58);
  WindowsDeleteString(string);
  string = 0;
  if ( v89 > 7 )
    std::_Deallocate<16>(v87, 2 * v89 + 2);
  v88 = 0;
  v89 = 7;
  LOWORD(v87) = 0;
  ReleaseSRWLockExclusive(&DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock);
  v60 = (std::_Ref_count_base *)v28[1];
  if ( v60 )
    std::_Ref_count_base::_Decref(v60);
  return a1;
}

```

## disassembly

```asm
0x1800b3bec  mov     [rsp-8+arg_10], rbx
0x1800b3bf1  push    rbp
0x1800b3bf2  push    rsi
0x1800b3bf3  push    rdi
0x1800b3bf4  push    r12
0x1800b3bf6  push    r13
0x1800b3bf8  push    r14
0x1800b3bfa  push    r15
0x1800b3bfc  lea     rbp, [rsp-0B0h]
0x1800b3c04  sub     rsp, 1B0h
0x1800b3c0b  mov     rax, cs:__security_cookie
0x1800b3c12  xor     rax, rsp
0x1800b3c15  mov     [rbp+0E0h+var_40], rax
0x1800b3c1c  mov     rbx, r8
0x1800b3c1f  mov     r14, rcx
0x1800b3c22  mov     [rbp+0E0h+var_118], rcx
0x1800b3c26  mov     [rbp+0E0h+var_160], rdx
0x1800b3c2a  mov     rdi, [rbp+0E0h+arg_20]
0x1800b3c31  mov     [rbp+0E0h+var_150], rdi
0x1800b3c35  mov     [rbp+0E0h+var_110], rdi
0x1800b3c39  mov     rax, [rbp+0E0h+arg_28]
0x1800b3c40  mov     [rbp+0E0h+var_128], rax
0x1800b3c44  mov     rax, [rbp+0E0h+arg_30]
0x1800b3c4b  mov     [rsp+1E0h+var_180], rax
0x1800b3c50  mov     rax, [rbp+0E0h+arg_38]
0x1800b3c57  mov     [rbp+0E0h+var_120], rax
0x1800b3c5b  xor     esi, esi
0x1800b3c5d  mov     r15d, esi
0x1800b3c60  mov     dword ptr [rsp+1E0h+var_1A0], esi
0x1800b3c64  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UITileActivator@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileVerbProvider@Private@678@UITileMigrationEventSource@678@U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>(void)
0x1800b3c69  nop
0x1800b3c6a  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6B@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'
0x1800b3c71  mov     [r14], rax
0x1800b3c74  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UITileActivator@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileVerbProvider@Private@89WindowsInternal@@UITileMigrationEventSource@89WindowsInternal@@U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@Details@23@@Details@WRL@Microsoft@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>>'}
0x1800b3c7b  mov     [r14+8], rax
0x1800b3c7f  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UITileActivator@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileVerbProvider@Private@678@UITileMigrationEventSource@678@U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UITileActivator@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileVerbProvider@Private@89WindowsInternal@@UITileMigrationEventSource@89WindowsInternal@@U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@234@@Details@WRL@Microsoft@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,WindowsInternal::Shell::UnifiedTile::ITileActivator,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>>'}
0x1800b3c86  mov     [r14+28h], rax
0x1800b3c8a  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6BITileActivator@UnifiedTile@Shell@WindowsInternal@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `WindowsInternal::Shell::UnifiedTile::ITileActivator'}
0x1800b3c91  mov     [r14+30h], rax
0x1800b3c95  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@UITileMigrationEventSource@678@U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@Details@WRL@Microsoft@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTileVerbProvider,WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'}
0x1800b3c9c  mov     [r14+38h], rax
0x1800b3ca0  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6BITileMigrationEventSource@UnifiedTile@Shell@WindowsInternal@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `WindowsInternal::Shell::UnifiedTile::ITileMigrationEventSource'}
0x1800b3ca7  mov     [r14+40h], rax
0x1800b3cab  lea     rax, ??_7PlaceholderTileTransformer@Internal@0DataStoreCache@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@UIPlaceholderTileTransformer@34@UIDataStoreTransformer@4@VNil@Details@WRL@Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@V789Microsoft@@@23@@Details@WRL@Microsoft@@@; const DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal,DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer,DataStoreCache::IDataStoreTransformer,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'}
0x1800b3cb2  mov     [r14+48h], rax
0x1800b3cb6  xor     eax, eax
0x1800b3cb8  mov     [r14+60h], rax
0x1800b3cbc  mov     [r14+68h], rsi
0x1800b3cc0  mov     [r14+70h], rsi
0x1800b3cc4  mov     [r14+78h], rax
0x1800b3cc8  mov     [r14+80h], rsi
0x1800b3ccf  mov     [r14+88h], rsi
0x1800b3cd6  mov     [r14+90h], rsi
0x1800b3cdd  mov     [r14+98h], rsi
0x1800b3ce4  mov     [r14+0A0h], rsi
0x1800b3ceb  lea     rcx, [r14+0A8h]
0x1800b3cf2  call    ??$GetActivationFactory@UIUnifiedTileIdentifierStatics@UnifiedTile@Shell@WindowsInternal@@@wil@@YA?AV?$com_ptr_t@UIUnifiedTileIdentifierStatics@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifierStatics>(ushort const *)
0x1800b3cf7  nop
0x1800b3cf8  mov     [rsp+1E0h+var_1B0], r14
0x1800b3cfd  lea     rax, [rsp+1E0h+var_180]
0x1800b3d02  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x1800b3d07  lea     r9, [rbp+0E0h+var_128]
0x1800b3d0b  lea     r8, [rbp+0E0h+var_160]
0x1800b3d0f  lea     rdx, [rsp+1E0h+var_1B0]
0x1800b3d14  lea     rcx, [rsp+1E0h+var_1A0]
0x1800b3d19  call    ??$MakeAndInitializeOrThrow@VPlaceholderTileCollectionDataUpdater@Internal@PlaceholderTileTransformer@DataStoreCache@@PEAV3234@AEAPEAUIDataManager@4@AEAPEAUIMRTTransformer@4@AEAPEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@wil@@YA?AV?$ComPtr@VPlaceholderTileCollectionDataUpdater@Internal@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@$$QEAPEAVPlaceholderTileTransformer@Internal@4DataStoreCache@@AEAPEAUIDataManager@6@AEAPEAUIMRTTransformer@6@AEAPEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Z; wil::MakeAndInitializeOrThrow<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileCollectionDataUpdater,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer *,DataStoreCache::IDataManager * &,DataStoreCache::IMRTTransformer * &,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &>(DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer * &&,DataStoreCache::IDataManager * &,DataStoreCache::IMRTTransformer * &,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &)
0x1800b3d1e  mov     rcx, [rax]
0x1800b3d21  mov     [rax], rsi
0x1800b3d24  mov     [r14+0B0h], rcx
0x1800b3d2b  mov     rcx, [rsp+1E0h+var_1A0]
0x1800b3d30  test    rcx, rcx
0x1800b3d33  jz      short loc_1800B3D47
0x1800b3d35  mov     [rsp+1E0h+var_1A0], rsi
0x1800b3d3a  mov     rax, [rcx]
0x1800b3d3d  mov     rax, [rax+10h]
0x1800b3d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d46  nop
0x1800b3d47  lea     r13, [r14+0B8h]
0x1800b3d4e  mov     [r13+0], rbx
0x1800b3d52  test    rbx, rbx
0x1800b3d55  jz      short loc_1800B3D67
0x1800b3d57  mov     rax, [rbx]
0x1800b3d5a  mov     rcx, rbx
0x1800b3d5d  mov     rax, [rax+8]
0x1800b3d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d66  nop
0x1800b3d67  lea     rcx, [r14+0C0h]
0x1800b3d6e  mov     rdx, rdi
0x1800b3d71  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x1800b3d76  nop
0x1800b3d77  lea     rsi, [r14+0D0h]
0x1800b3d7e  xor     ebx, ebx
0x1800b3d80  mov     [rsi], rbx
0x1800b3d83  mov     [rsi+8], rbx
0x1800b3d87  lea     r12, [r14+0E0h]
0x1800b3d8e  mov     [r12], rbx
0x1800b3d92  mov     [r12+8], rbx
0x1800b3d97  mov     [r14+0F0h], rbx
0x1800b3d9e  mov     [r14+0F8h], rbx
0x1800b3da5  mov     [r14+100h], rbx
0x1800b3dac  mov     [r14+108h], rbx
0x1800b3db3  mov     [r14+110h], rbx
0x1800b3dba  mov     [r14+118h], rbx
0x1800b3dc1  mov     [r14+120h], rbx
0x1800b3dc8  lea     rdi, ?s_singletonLock@PlaceholderTileTransformer@Internal@1DataStoreCache@@0Vsrwlock@wil@@A; wil::srwlock DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock
0x1800b3dcf  mov     rcx, rdi; SRWLock
0x1800b3dd2  call    cs:__imp_AcquireSRWLockExclusive
0x1800b3dd8  mov     [rbp+0E0h+var_128], rdi
0x1800b3ddc  cmp     [r13+0], rbx
0x1800b3de0  jz      loc_1800B4522
0x1800b3de6  xorps   xmm0, xmm0
0x1800b3de9  movups  [rbp+0E0h+var_108], xmm0
0x1800b3ded  mov     [rbp+0E0h+var_F8], rbx
0x1800b3df1  mov     [rbp+0E0h+var_F0], rbx
0x1800b3df5  lea     rcx, [rbp+0E0h+var_108]
0x1800b3df9  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800b3dfe  nop
0x1800b3dff  mov     rcx, rbx
0x1800b3e02  mov     [rsp+1E0h+string], rbx
0x1800b3e07  mov     rdi, [r13+0]
0x1800b3e0b  test    rdi, rdi
0x1800b3e0e  jz      short loc_1800B3E4E
0x1800b3e10  mov     rax, [rdi]
0x1800b3e13  mov     rbx, [rax+30h]
0x1800b3e17  xor     ecx, ecx; string
0x1800b3e19  call    cs:__imp_WindowsDeleteString
0x1800b3e1f  mov     [rsp+1E0h+string], 0
0x1800b3e28  lea     rdx, [rsp+1E0h+string]
0x1800b3e2d  mov     rcx, rdi
0x1800b3e30  mov     rax, rbx
0x1800b3e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e38  mov     rcx, [rbp+0E8h]; this
0x1800b3e3f  xor     ebx, ebx
0x1800b3e41  test    eax, eax
0x1800b3e43  js      loc_1800B3F8D
0x1800b3e49  mov     rcx, [rsp+1E0h+string]; string
0x1800b3e4e  xor     edx, edx; length
0x1800b3e50  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b3e56  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b3e5a  inc     r8
0x1800b3e5d  cmp     [rax+r8*2], bx
0x1800b3e62  jnz     short loc_1800B3E5A
0x1800b3e64  mov     rdx, rax
0x1800b3e67  lea     rcx, [rbp+0E0h+var_108]
0x1800b3e6b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b3e70  lea     r8, [rbp+0E0h+var_108]
0x1800b3e74  lea     rdx, [rsp+1E0h+var_1B0]
0x1800b3e79  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::find(std::wstring const &)
0x1800b3e7e  mov     rbx, [rsp+1E0h+var_1B0]
0x1800b3e83  xor     edi, edi
0x1800b3e85  cmp     rbx, cs:qword_1804DCCA8
0x1800b3e8c  jz      short loc_1800B3EF2
0x1800b3e8e  xorps   xmm0, xmm0
0x1800b3e91  movdqu  xmmword ptr [rsp+1E0h+var_1B0], xmm0
0x1800b3e97  mov     rcx, [rbx+38h]; this
0x1800b3e9b  test    rcx, rcx
0x1800b3e9e  jnz     loc_1800B4101
0x1800b3ea4  lea     rdx, [rsp+1E0h+var_1B0]
0x1800b3ea9  mov     rcx, rsi
0x1800b3eac  call    ??4?$shared_ptr@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> &&)
0x1800b3eb1  mov     rcx, [rsp+1E0h+var_1B0+8]; this
0x1800b3eb6  test    rcx, rcx
0x1800b3eb9  jz      short loc_1800B3EC0
0x1800b3ebb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b3ec0  xorps   xmm0, xmm0
0x1800b3ec3  movdqu  xmmword ptr [rsp+1E0h+var_1B0], xmm0
0x1800b3ec9  mov     rcx, [rbx+48h]; this
0x1800b3ecd  test    rcx, rcx
0x1800b3ed0  jnz     loc_1800B40DD
0x1800b3ed6  lea     rdx, [rsp+1E0h+var_1B0]
0x1800b3edb  mov     rcx, r12
0x1800b3ede  call    ??4?$shared_ptr@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> &&)
0x1800b3ee3  mov     rcx, [rsp+1E0h+var_1B0+8]; this
0x1800b3ee8  test    rcx, rcx
0x1800b3eeb  jz      short loc_1800B3EF2
0x1800b3eed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b3ef2  cmp     [rsi], rdi
0x1800b3ef5  jz      loc_1800B3FA2
0x1800b3efb  mov     rsi, [rbp+0E0h+var_150]
0x1800b3eff  cmp     [r12], rdi
0x1800b3f03  jz      loc_1800B4556
0x1800b3f09  xor     r13d, r13d
0x1800b3f0c  lea     rcx, [r14+0A0h]
0x1800b3f13  mov     rdx, [rbp+0E0h+var_160]
0x1800b3f17  call    ??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x1800b3f1c  mov     r8b, 3
0x1800b3f1f  mov     dl, 1
0x1800b3f21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RestoreSparkPlaceholders@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RestoreSparkPlaceholders@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RestoreSparkPlaceholders> `wil::Feature<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::GetImpl(void)'::`2'::impl
0x1800b3f28  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RestoreSparkPlaceholders@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800b3f2d  mov     edi, 70h ; 'p'
0x1800b3f32  mov     ecx, edi; Size
0x1800b3f34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3f39  mov     rbx, rax
0x1800b3f3c  mov     [rsp+1E0h+var_1B0], rax
0x1800b3f41  mov     r8d, edi; Size
0x1800b3f44  xor     edx, edx; Val
0x1800b3f46  mov     rcx, rax; void *
0x1800b3f49  call    memset_0
0x1800b3f4e  mov     rcx, rbx; this
0x1800b3f51  call    ??0PlaceholderTileMigrationManager@PlaceholderTileTransformer@DataStoreCache@@QEAA@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::PlaceholderTileMigrationManager(void)
0x1800b3f56  lea     rax, ??_7?$heap_implements@UPlaceholderTileMigrationManager@PlaceholderTileTransformer@DataStoreCache@@@impl@winrt@@6B@; const winrt::impl::heap_implements<DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager>::`vftable'
0x1800b3f5d  mov     [rbx], rax
0x1800b3f60  mov     [rbp+0E0h+var_130], rbx
0x1800b3f64  lea     rax, [rbp+0E0h+var_130]
0x1800b3f68  lea     rdi, [r14+120h]
0x1800b3f6f  cmp     rdi, rax
0x1800b3f72  jz      loc_1800B4125
0x1800b3f78  cmp     [rdi], r13
0x1800b3f7b  jz      short loc_1800B3F85
0x1800b3f7d  mov     rcx, rdi
0x1800b3f80  call    ?unconditional_release_ref@?$com_ptr@UUnifiedTile@implementation@Shim@1Shell@WindowsInternal@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsInternal::Shell::UnifiedTile::Shim::implementation::UnifiedTile>::unconditional_release_ref(void)
0x1800b3f85  mov     [rdi], rbx
0x1800b3f88  jmp     loc_1800B4133
0x1800b3f8d  mov     r9d, eax; char *
0x1800b3f90  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1800b3f97  mov     edx, 95h; void *
0x1800b3f9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3fa2  mov     rcx, [rbp+0E0h+var_150]
0x1800b3fa6  mov     rcx, [rcx]
0x1800b3fa9  test    rcx, rcx
0x1800b3fac  jz      loc_1800B40BC
0x1800b3fb2  mov     rax, [rcx+8]
0x1800b3fb6  test    rax, rax
0x1800b3fb9  jz      short loc_1800B3FBF
0x1800b3fbb  lock inc dword ptr [rax+8]
0x1800b3fbf  mov     rax, [rcx]
0x1800b3fc2  mov     [rsp+1E0h+var_190], rax
0x1800b3fc7  mov     r12, [rcx+8]
0x1800b3fcb  mov     [rsp+1E0h+var_190+8], r12
0x1800b3fd0  lea     rax, [rsp+1E0h+var_190]
0x1800b3fd5  mov     [rsp+1E0h+var_180], rax
0x1800b3fda  mov     r15d, 1
0x1800b3fe0  mov     dword ptr [rsp+1E0h+var_1A0], r15d
0x1800b3fe5  mov     rdi, [r13+0]
0x1800b3fe9  mov     ecx, 0F8h; Size
0x1800b3fee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3ff3  mov     rsi, rax
0x1800b3ff6  mov     [rsp+1E0h+var_1B0], rax
0x1800b3ffb  xorps   xmm0, xmm0
0x1800b3ffe  movups  xmmword ptr [rax], xmm0
0x1800b4001  mov     dword ptr [rax+8], 1
0x1800b4008  mov     dword ptr [rax+0Ch], 1
0x1800b400f  lea     rax, ??_7?$_Ref_count_obj2@V?$CloudItemManager@V?$GenericCloudItem@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@6B@; const std::_Ref_count_obj2<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::`vftable'
0x1800b4016  mov     [rsi], rax
0x1800b4019  movdqu  xmmword ptr [rbp+0E0h+hstringHeader.Reserved], xmm0
0x1800b401e  mov     rax, [rsp+1E0h+var_180]
0x1800b4023  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x1800b4028  lea     r9, [rbp+0E0h+hstringHeader]
0x1800b402c  xor     r8d, r8d
0x1800b402f  mov     rdx, rdi
0x1800b4032  lea     rcx, [rsi+10h]
0x1800b4036  call    ??0?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@QEAA@PEAUIUser@System@Windows@@W4CloudItemManagerOptions@123@AEBV?$shared_ptr@V?$CloudItemManagerCallback@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@CloudUtil@DataStoreCache@@@std@@AEBV?$shared_ptr@U?$CloudItemManagerTestHook@UPlaceholderTileCollection@Data@Windows@@@Internal@CloudUtil@DataStoreCache@@@9@@Z; DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>(Windows::System::IUser *,DataStoreCache::CloudUtil::Internal::CloudItemManagerOptions,std::shared_ptr<DataStoreCache::CloudUtil::CloudItemManagerCallback<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>> const &,std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManagerTestHook<Windows::Data::PlaceholderTileCollection>> const &)
0x1800b403b  nop
0x1800b403c  xorps   xmm0, xmm0
0x1800b403f  movdqu  xmmword ptr [rsp+1E0h+var_190], xmm0
0x1800b4045  or      r15d, 20h
0x1800b4049  mov     r8, rsi
0x1800b404c  lea     rdx, [rsi+10h]
0x1800b4050  lea     rcx, [rsp+1E0h+var_190]
0x1800b4055  call    ??$_Set_ptr_rep_and_enable_shared@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@?$shared_ptr@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@AEAAXQEAV?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::_Set_ptr_rep_and_enable_shared<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>(DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>> * const,std::_Ref_count_base * const)
0x1800b405a  lea     rdx, [rsp+1E0h+var_190]
0x1800b405f  lea     rbx, [r14+0D0h]
0x1800b4066  mov     rcx, rbx
0x1800b4069  call    ??4?$shared_ptr@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> &&)
0x1800b406e  mov     rcx, [rsp+1E0h+var_190+8]; this
0x1800b4073  xor     edi, edi
0x1800b4075  test    rcx, rcx
0x1800b4078  jz      short loc_1800B4080
0x1800b407a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b407f  nop
0x1800b4080  test    r15b, 2
0x1800b4084  jnz     loc_1800B45F3
0x1800b408a  test    r15b, 1
0x1800b408e  jnz     loc_1800B460E
0x1800b4094  lea     r8, [rbp+0E0h+var_108]
0x1800b4098  lea     rdx, [rbp+0E0h+hstringHeader]
0x1800b409c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPlaceholderTileTransformerSingleton@PlaceholderTileTransformer@Internal@4DataStoreCache@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800b40a1  mov     rcx, [rax]
0x1800b40a4  add     rcx, 30h ; '0'
0x1800b40a8  mov     rdx, rbx
0x1800b40ab  call    ??$?4V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@$0A@@?$weak_ptr@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@QEAAAEAV01@AEBV?$shared_ptr@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@1@@Z; std::weak_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::operator=<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,0>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>> const &)
0x1800b40b0  lea     r12, [r14+0E0h]
0x1800b40b7  jmp     loc_1800B3EFB
0x1800b40bc  xorps   xmm0, xmm0
0x1800b40bf  movdqu  xmmword ptr [rbp+0E0h+var_140], xmm0
0x1800b40c4  lea     rax, [rbp+0E0h+var_140]
0x1800b40c8  mov     [rsp+1E0h+var_180], rax
0x1800b40cd  mov     r15d, 2
0x1800b40d3  mov     r12, [rsp+1E0h+var_190+8]
0x1800b40d8  jmp     loc_1800B3FE0
0x1800b40dd  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x1800b40e2  test    al, al
0x1800b40e4  jz      loc_1800B3ED6
0x1800b40ea  mov     rax, [rbx+40h]
0x1800b40ee  mov     [rsp+1E0h+var_1B0], rax
0x1800b40f3  mov     rax, [rbx+48h]
0x1800b40f7  mov     [rsp+1E0h+var_1B0+8], rax
0x1800b40fc  jmp     loc_1800B3ED6
0x1800b4101  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x1800b4106  test    al, al
  ... truncated ...
```
