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
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  std::_Ref_count_base **v16; // r13
  __int64 *v17; // r12
  struct Windows::System::IUser **v18; // rdx
  HSTRING v19; // rcx
  std::_Ref_count_base *v20; // rdi
  __int64 (__fastcall *v21)(std::_Ref_count_base *, HSTRING *); // rbx
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  std::_Ref_count_base *v28; // rbx
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v30; // rcx
  std::_Ref_count_base ***v31; // rsi
  __int64 v32; // r8
  __int64 v33; // rdx
  std::_Ref_count_base *v34; // rbx
  std::_Ref_count_base **v35; // rdi
  std::_Ref_count_base **v36; // rcx
  std::_Ref_count_base *v37; // rax
  std::_Ref_count_base *v38; // r12
  int v39; // r15d
  std::_Ref_count_base *v40; // rdi
  std::_Ref_count_base *v41; // rsi
  std::_Ref_count_base *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  std::_Ref_count_base ***v45; // rdi
  std::_Ref_count_base *v46; // rbx
  std::_Ref_count_base *v47; // rax
  std::_Ref_count_base *v48; // rcx
  std::_Ref_count_base *v49; // rax
  _QWORD *v50; // rdx
  std::_Ref_count_base *v51; // rbx
  std::_Ref_count_base *v52; // rax
  std::_Ref_count_base *v53; // rcx
  std::_Ref_count_base *v54; // rax
  _QWORD *v55; // rdx
  HRESULT v56; // eax
  __int64 v57; // rcx
  HRESULT v58; // eax
  int ActivationFactory; // eax
  std::_Ref_count_base **v60; // rdx
  std::_Ref_count_base *v61; // rbx
  std::_Ref_count_base *v62; // rcx
  std::_Ref_count_base *v63; // rcx
  std::_Ref_count_base *v65; // rax
  std::_Ref_count_base *v66; // rcx
  std::_Ref_count_base *v67; // rax
  int CurrentUser; // eax
  std::_Ref_count_base **v69; // rcx
  int v70; // r15d
  __int64 v71; // rax
  std::_Ref_count_base *v72; // rcx
  __int64 v73; // rax
  int v74; // [rsp+20h] [rbp-E0h]
  std::_Ref_count_base *v75[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v76; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v77[2]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v78[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v79; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v81[2]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base ***v82; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v83; // [rsp+98h] [rbp-68h]
  std::_Ref_count_base *v84[2]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v85; // [rsp+B0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v86; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base **v87; // [rsp+C0h] [rbp-40h]
  __int64 v88; // [rsp+C8h] [rbp-38h]
  __int64 v89; // [rsp+D0h] [rbp-30h]
  __int128 v90; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v91; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v92; // [rsp+F0h] [rbp-10h]
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v94; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v95[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v96; // [rsp+158h] [rbp+58h]
  _QWORD v97[7]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD *v98; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v88 = a1;
  v81[0] = a2;
  v82 = a5;
  v89 = (__int64)a5;
  v86 = a6;
  v78[0] = a7;
  v87 = a8;
  v10 = 0;
  LODWORD(v76) = 0;
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
  v75[0] = (std::_Ref_count_base *)a1;
  v11 = (__int64 *)wil::MakeAndInitializeOrThrow<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileCollectionDataUpdater,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer *,DataStoreCache::IDataManager * &,DataStoreCache::IMRTTransformer * &,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &>(
                     (unsigned int)&v76,
                     (unsigned int)v75,
                     (unsigned int)v81,
                     (unsigned int)&v86,
                     (unsigned int)v78);
  v14 = *v11;
  *v11 = 0;
  *(_QWORD *)(a1 + 176) = v14;
  v15 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = (std::_Ref_count_base **)(a1 + 184);
  *(_QWORD *)(a1 + 184) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
    a1 + 192,
    a5,
    v12,
    v13);
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  v17 = (__int64 *)(a1 + 224);
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
  v86 = &DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock;
  if ( !*v16 )
  {
    *v16 = 0;
    CurrentUser = UserHelpers::GetCurrentUser((UserHelpers *)(a1 + 184), v18);
    if ( CurrentUser < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)CurrentUser,
        v74);
  }
  v90 = 0;
  v91 = 0;
  v92 = 0;
  std::wstring::_Construct_empty(&v90);
  v19 = 0;
  string = 0;
  v20 = *v16;
  if ( *v16 )
  {
    v21 = *(__int64 (__fastcall **)(std::_Ref_count_base *, HSTRING *))(*(_QWORD *)v20 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v22 = v21(v20, &string);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v22,
        v74);
    v19 = string;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v19, 0);
  v24 = -1;
  do
    ++v24;
  while ( StringRawBuffer[v24] );
  std::wstring::_Assign<unsigned short>(&v90, StringRawBuffer);
  std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::find(
    v25,
    v75,
    &v90);
  v28 = v75[0];
  if ( v75[0] != (std::_Ref_count_base *)qword_1804DCCA8 )
  {
    *(_OWORD *)v75 = 0;
    v29 = (std::_Ref_count_base *)*((_QWORD *)v28 + 7);
    if ( v29 && std::_Ref_count_base::_Incref_nz(v29) )
    {
      v75[0] = *((std::_Ref_count_base **)v28 + 6);
      v75[1] = *((std::_Ref_count_base **)v28 + 7);
    }
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 208,
      v75);
    if ( v75[1] )
      std::_Ref_count_base::_Decref(v75[1]);
    *(_OWORD *)v75 = 0;
    v30 = (std::_Ref_count_base *)*((_QWORD *)v28 + 9);
    if ( v30 && std::_Ref_count_base::_Incref_nz(v30) )
    {
      v75[0] = *((std::_Ref_count_base **)v28 + 8);
      v75[1] = *((std::_Ref_count_base **)v28 + 9);
    }
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 224,
      v75);
    if ( v75[1] )
      std::_Ref_count_base::_Decref(v75[1]);
  }
  if ( !*(_QWORD *)(a1 + 208) )
  {
    v36 = *v82;
    if ( *v82 )
    {
      v37 = v36[1];
      if ( v37 )
        _InterlockedIncrement((volatile signed __int32 *)v37 + 2);
      v77[0] = *v36;
      v38 = v36[1];
      v77[1] = v38;
      v78[0] = (std::_Ref_count_base *)v77;
      v39 = 1;
    }
    else
    {
      *(_OWORD *)v84 = 0;
      v78[0] = (std::_Ref_count_base *)v84;
      v39 = 2;
      v38 = v77[1];
    }
    LODWORD(v76) = v39;
    v40 = *v16;
    v41 = (std::_Ref_count_base *)operator new(0xF8u);
    v75[0] = v41;
    *(_OWORD *)v41 = 0;
    *((_DWORD *)v41 + 2) = 1;
    *((_DWORD *)v41 + 3) = 1;
    *(_QWORD *)v41 = &std::_Ref_count_obj2<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::`vftable';
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
    DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>(
      (_DWORD)v41 + 16,
      (_DWORD)v40,
      0,
      (unsigned int)&hstringHeader,
      (__int64)v78[0]);
    *(_OWORD *)v77 = 0;
    v10 = v39 | 0x20;
    std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::_Set_ptr_rep_and_enable_shared<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>(
      v77,
      (char *)v41 + 16,
      v41);
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      a1 + 208,
      v77);
    v42 = v77[1];
    if ( v77[1] )
      std::_Ref_count_base::_Decref(v77[1]);
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      v42 = v84[1];
      if ( v84[1] )
        std::_Ref_count_base::_Decref(v84[1]);
    }
    if ( (v10 & 1) != 0 )
    {
      v10 &= ~1u;
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
    }
    v43 = std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::_Try_emplace<std::wstring const &,>(
            v42,
            &hstringHeader,
            &v90);
    std::weak_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::operator=<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,0>(
      (_QWORD *)(*(_QWORD *)v43 + 48LL),
      (__int64 *)(a1 + 208));
    v17 = (__int64 *)(a1 + 224);
  }
  v31 = v82;
  if ( !*v17 )
  {
    if ( *v82 )
    {
      v69 = (std::_Ref_count_base **)std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
                                       v77,
                                       *v82 + 2,
                                       v26,
                                       v27);
      v70 = v10 | 4;
    }
    else
    {
      *(_OWORD *)v84 = 0;
      v69 = v84;
      v70 = v10 | 8;
    }
    LODWORD(v76) = v70;
    LODWORD(v82) = 0;
    v75[0] = *v16;
    v71 = std::make_shared<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>,Windows::System::IUser *,enum DataStoreCache::CloudUtil::Internal::CloudItemManagerOptions,std::nullptr_t,std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManagerTestHook<Windows::Data::PlaceholderTileCollectionLocal>>>(
            (unsigned int)&hstringHeader,
            (unsigned int)v75,
            (unsigned int)&v82,
            v27,
            (__int64)v69);
    std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
      v17,
      v71);
    v72 = *(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8];
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
    if ( (v70 & 8) != 0 )
    {
      LOBYTE(v70) = v70 & 0xF7;
      v72 = v84[1];
      if ( v84[1] )
        std::_Ref_count_base::_Decref(v84[1]);
    }
    if ( (v70 & 4) != 0 )
    {
      v72 = v77[1];
      if ( v77[1] )
        std::_Ref_count_base::_Decref(v77[1]);
    }
    v73 = std::_Hash<std::_Umap_traits<std::wstring,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::PlaceholderTileTransformerSingleton>>,0>>::_Try_emplace<std::wstring const &,>(
            v72,
            &hstringHeader,
            &v90);
    std::weak_ptr<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::operator=<DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,0>(
      (_QWORD *)(*(_QWORD *)v73 + 64LL),
      v17);
  }
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
    a1 + 160,
    v81[0]);
  LOBYTE(v32) = 3;
  LOBYTE(v33) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RestoreSparkPlaceholders>::GetImpl'::`2'::impl,
    v33,
    v32);
  v34 = (std::_Ref_count_base *)operator new(0x70u);
  v75[0] = v34;
  memset_0(v34, 0, 0x70u);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager::PlaceholderTileMigrationManager(v34);
  *(_QWORD *)v34 = &winrt::impl::heap_implements<DataStoreCache::PlaceholderTileTransformer::PlaceholderTileMigrationManager>::`vftable';
  v85 = v34;
  v35 = (std::_Ref_count_base **)(a1 + 288);
  if ( (std::_Ref_count_base **)(a1 + 288) == &v85 )
  {
    if ( v34 )
      winrt::com_ptr<winrt::WindowsInternal::Shell::UnifiedTile::Shim::implementation::UnifiedTile>::unconditional_release_ref(&v85);
  }
  else
  {
    if ( *v35 )
      winrt::com_ptr<winrt::WindowsInternal::Shell::UnifiedTile::Shim::implementation::UnifiedTile>::unconditional_release_ref(a1 + 288);
    *v35 = v34;
  }
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::BeginBatchUpdate(a1 + 72, v78);
  v79 = 0;
  v75[0] = (std::_Ref_count_base *)&v79;
  v44 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v75);
  Microsoft::WRL::AsWeak<DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileCollectionDataUpdater>(
    *(_QWORD *)(a1 + 176),
    v44);
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetRoamedData(a1, &v82);
  DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetLocalData(a1, v84);
  v45 = v82;
  v46 = v79;
  if ( v79 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v79 + 8LL))(v79);
  v95[0] = &std::_Func_impl_no_alloc<_lambda_a5e86e17d5fff25afa4e610f10d0a9dc_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>> const &>::`vftable';
  v95[1] = v46;
  v75[0] = 0;
  v96 = v95;
  DataStoreCache::CloudUtil::Internal::ObservableCloudItem<DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::AddObserver(
    v45[8],
    v81,
    v95);
  v47 = v81[0];
  v48 = v81[1];
  *(_OWORD *)v81 = 0;
  *(_QWORD *)(a1 + 240) = v47;
  v49 = *(std::_Ref_count_base **)(a1 + 248);
  *(_QWORD *)(a1 + 248) = v48;
  if ( v49 )
  {
    std::_Ref_count_base::_Decref(v49);
    if ( v81[1] )
      std::_Ref_count_base::_Decref(v81[1]);
  }
  if ( v96 )
  {
    v50 = v95;
    LOBYTE(v50) = v96 != v95;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v96 + 32LL))(v96, v50);
    v96 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
  v51 = v84[0];
  v81[0] = v79;
  if ( v79 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v79 + 8LL))(v79);
  v98 = 0;
  v98 = std::_Func_impl_no_alloc<_lambda_870dd18122e8a1af77c82753ebc9f10e_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> const &>::_Func_impl_no_alloc<_lambda_870dd18122e8a1af77c82753ebc9f10e_,void,DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>> const &>(
          v97,
          v81);
  DataStoreCache::CloudUtil::Internal::ObservableCloudItem<DataStoreCache::CloudUtil::CloudItemChangeInfo<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::CuratedTileCollection::TileCollectionContainer,0>>>::AddObserver(
    *((_QWORD *)v51 + 8),
    v75,
    v97);
  v52 = v75[0];
  v53 = v75[1];
  *(_OWORD *)v75 = 0;
  *(_QWORD *)(a1 + 256) = v52;
  v54 = *(std::_Ref_count_base **)(a1 + 264);
  *(_QWORD *)(a1 + 264) = v53;
  if ( v54 )
  {
    std::_Ref_count_base::_Decref(v54);
    if ( v75[1] )
      std::_Ref_count_base::_Decref(v75[1]);
  }
  if ( v98 )
  {
    v55 = v97;
    LOBYTE(v55) = v98 != v97;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v98 + 32LL))(v98, v55);
    v98 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v81);
  WindowsDeleteString(*(HSTRING *)(a1 + 280));
  *(_QWORD *)(a1 + 280) = 0;
  v56 = WindowsCreateString(L"PlaceholderTileVerbProvider", 0x1Bu, (HSTRING *)(a1 + 280));
  if ( v56 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)v56,
      v74);
  v57 = *(_QWORD *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  v94 = 0;
  v58 = WindowsCreateStringReference(
          L"WindowsInternal.Shell.UnifiedTile.Private.VerbStringHelper",
          0x3Au,
          &hstringHeader,
          &v94);
  if ( v58 < 0 )
  {
    RaiseException(v58, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v94, &GUID_773a5acc_918a_4eed_ba13_62bd17ee0dcf, a1 + 272);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v74);
  v60 = v87;
  if ( v87 )
  {
    v65 = v78[0];
    v66 = v78[1];
    *(_OWORD *)v78 = 0;
    *v87 = v65;
    v67 = v60[1];
    v60[1] = v66;
    if ( v67 )
      std::_Ref_count_base::_Decref(v67);
    v61 = v78[1];
  }
  else
  {
    *(_OWORD *)v77 = 0;
    v61 = v78[1];
    if ( v78[1] )
      _InterlockedIncrement((volatile signed __int32 *)v78[1] + 2);
    *(_OWORD *)v77 = *(_OWORD *)v78;
    DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::EndBatchUpdate(
      a1 + 72,
      &hstringHeader,
      v77);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  }
  if ( v84[1] )
    std::_Ref_count_base::_Decref(v84[1]);
  if ( v83 )
    std::_Ref_count_base::_Decref(v83);
  v62 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v62 + 16LL))(v62);
  }
  if ( v61 )
    std::_Ref_count_base::_Decref(v61);
  WindowsDeleteString(string);
  string = 0;
  if ( v92 > 7 )
    std::_Deallocate<16>(v90, 2 * v92 + 2);
  v91 = 0;
  v92 = 7;
  LOWORD(v90) = 0;
  ReleaseSRWLockExclusive(&DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::s_singletonLock);
  v63 = (std::_Ref_count_base *)v31[1];
  if ( v63 )
    std::_Ref_count_base::_Decref(v63);
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
