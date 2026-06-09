# WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::RuntimeClassInitialize(WindowsInternal::Shell::UnifiedTile::TileFeatures,WindowsInternal::Shell::UnifiedTile::TileSources,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifierStatics *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *,WindowsInternal::Shell::UnifiedTile::UnifiedTileManagerCreationStatus *,bool)

- ea: `0x180038760`
- end: `0x180039165`
- name: `?RuntimeClassInitialize@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@QEAAJW4TileFeatures@234@W4TileSources@234@PEAUIUnifiedTileIdentifierStatics@234@PEAUIUnifiedTileManagerOptions@234@PEAVUnifiedTileManagerCreationStatus@234@_N@Z`
- size: `2565`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d030c`

## callees

- `0x18000b5f0`
- `0x18000cb0c`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001aca4`
- `0x18001dfb8`
- `0x180038760`
- `0x18003916c`
- `0x1800391c4`
- `0x18003921c`
- `0x180039308`
- `0x180039420`
- `0x1800394d8`
- `0x18003950c`
- `0x180039568`
- `0x180039610`
- `0x18004ef8c`
- `0x18005020c`
- `0x180092800`
- `0x1800a3bbc`
- `0x1800a3bf4`
- `0x1800a59ec`
- `0x1800b1110`
- `0x1800b1b64`
- `0x1800d0810`
- `0x180126334`
- `0x180136f8c`
- `0x180147be8`
- `0x18015adbc`
- `0x180161204`
- `0x180201e50`
- `0x1802eb958`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800387fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800387fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038821`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003905d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003905d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800390a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039132`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800390f0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800390f0`

## string_xrefs

- `0x180038bbe`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180038c4a`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180038c6e`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180038cf1`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180038f5c`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180039046`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x180039092`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18003911b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *a5,
        struct WindowsInternal::Shell::UnifiedTile::UnifiedTileManagerCreationStatus *a6,
        char a7)
{
  bool v11; // r13
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char *DataManager; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *, __int64); // rbx
  UserHelpers **v20; // rdi
  int v21; // eax
  struct Windows::System::IUser *v22; // rdx
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int CustomTransformers; // eax
  int CanonicalTransformers; // eax
  __int64 (__fastcall *v28)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *, HSTRING *); // rbx
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  __int64 v32; // rdx
  unsigned int v33; // ebx
  char v34; // al
  __int64 v35; // rdx
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  const char *v39; // r9
  __int64 result; // rax
  __int64 v41; // rcx
  struct Windows::System::IUser **v42; // rdx
  void *v43; // rdx
  int CurrentUser; // ebx
  char v45; // cl
  __int64 v46; // rcx
  __int64 v47; // rcx
  unsigned __int64 v48; // rcx
  _QWORD **v49; // rdi
  _QWORD *i; // rbx
  __int64 *v51; // r8
  __int64 v52; // rcx
  char *CacheManager; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rax
  bool IsSystemAccount; // al
  int v59; // [rsp+20h] [rbp-228h]
  _BYTE v60[8]; // [rsp+40h] [rbp-208h] BYREF
  int v61[2]; // [rsp+48h] [rbp-200h] BYREF
  __int64 v62; // [rsp+50h] [rbp-1F8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1F0h] BYREF
  int v64[4]; // [rsp+60h] [rbp-1E8h] BYREF
  __int64 v65; // [rsp+70h] [rbp-1D8h]
  std::_Ref_count_base **v66; // [rsp+78h] [rbp-1D0h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::UnifiedTileManagerCreationStatus *v67; // [rsp+80h] [rbp-1C8h]
  int v68[4]; // [rsp+88h] [rbp-1C0h] BYREF
  __int64 v69; // [rsp+98h] [rbp-1B0h]
  char v70; // [rsp+A0h] [rbp-1A8h] BYREF
  char v71; // [rsp+A8h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v72[2]; // [rsp+B0h] [rbp-198h] BYREF
  void **v73; // [rsp+C0h] [rbp-188h] BYREF
  _BYTE v74[272]; // [rsp+C8h] [rbp-180h] BYREF
  _BYTE v75[8]; // [rsp+1D8h] [rbp-70h] BYREF
  _BYTE v76[48]; // [rsp+1E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v67 = a6;
  wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v73);
  v73 = &UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable';
  v11 = 1;
  try
  {
    UnifiedTileTelemetry::UnifiedTileManagerInitialization::StartActivity(
      (UnifiedTileTelemetry::UnifiedTileManagerInitialization *)&v73,
      a7 != 1);
    AcquireSRWLockExclusive(&WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::s_lock);
    v66 = (std::_Ref_count_base **)&WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::s_lock;
    *(_QWORD *)v61 = a1;
    std::_Tree<std::_Tset_traits<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *,std::less<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,std::allocator<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,0>>::_Emplace<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>(
      v12,
      v72,
      v61);
    ReleaseSRWLockExclusive(&WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::s_lock);
    if ( *(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions **)(a1 + 144) != a5 )
    {
      if ( a5 )
        (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *))(*(_QWORD *)a5 + 8LL))(a5);
      v13 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(a1 + 144) = a5;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    *(_DWORD *)(a1 + 572) = a3;
    *(_DWORD *)(a1 + 568) = a2;
    if ( *(_QWORD *)(a1 + 528) != a4 )
    {
      if ( a4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
      v14 = *(_QWORD *)(a1 + 528);
      *(_QWORD *)(a1 + 528) = a4;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    DataManager = (char *)DataStoreCache::Create_DataManager(v61);
    v16 = 0;
    if ( &v70 != DataManager )
    {
      v16 = *(_QWORD *)DataManager;
      *(_QWORD *)DataManager = 0;
    }
    v17 = *(_QWORD *)(a1 + 128);
    *(_QWORD *)(a1 + 128) = v16;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v18 = *(_QWORD *)v61;
    if ( *(_QWORD *)v61 )
    {
      *(_QWORD *)v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *, __int64))(*(_QWORD *)a5 + 88LL);
    v20 = (UserHelpers **)(a1 + 544);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 544);
    v21 = v19(a5, a1 + 544);
    v23 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
        (const char *)(unsigned int)v21,
        v59);
      v73 = &UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable';
      wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v73);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v76);
      wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v75);
      wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(v74);
      return v23;
    }
    if ( *v20 )
    {
      if ( !UserHelpers::IsThreadEffectiveUser(*v20, v22) )
      {
        *(_QWORD *)v61 = *v20;
        v57 = std::make_shared<UserHelpers::Impersonator,Windows::System::IUser * &>(v72, v61);
        std::shared_ptr<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>::operator=(
          a1 + 552,
          v57);
        if ( v72[1] )
          std::_Ref_count_base::_Decref(v72[1]);
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 544);
      CurrentUser = UserHelpers::GetCurrentUser((UserHelpers *)(a1 + 544), v42);
      if ( CurrentUser >= 0
        || (IsSystemAccount = UserHelpers::IsSystemAccount((UserHelpers *)0xFFFFFFFFFFFFFFFALL, v43),
            v45 = 1,
            IsSystemAccount) )
      {
        v45 = 0;
      }
      if ( v45 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x116,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
          (const char *)(unsigned int)CurrentUser,
          v59);
    }
    v62 = 0;
    *(_QWORD *)v61 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v24 = Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>(
            &v62,
            v61);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
        (const char *)(unsigned int)v24,
        v59);
      v47 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
    }
    else
    {
      *(_DWORD *)(a1 + 576) = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, int *, __int64))(**(_QWORD **)(a1 + 128)
                                                                                           + 40LL))(
                                           *(_QWORD *)(a1 + 128),
                                           v61,
                                           v62);
      CustomTransformers = WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::ReadCustomTransformers(
                             (WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *)a1,
                             a5);
      v25 = CustomTransformers;
      if ( CustomTransformers < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
          (const char *)(unsigned int)CustomTransformers,
          v59);
        v46 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
      }
      else
      {
        CanonicalTransformers = WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::CreateCanonicalTransformers(
                                  (struct IUnknown *)a1,
                                  a5);
        v25 = CanonicalTransformers;
        if ( CanonicalTransformers >= 0 )
        {
          string = 0;
          v28 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *, HSTRING *))(*(_QWORD *)a5 + 120LL);
          WindowsDeleteString(0);
          string = 0;
          v29 = v28(a5, &string);
          v30 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13A,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
              (const char *)(unsigned int)v29,
              v59);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
            UnifiedTileTelemetry::UnifiedTileManagerInitialization::~UnifiedTileManagerInitialization((UnifiedTileTelemetry::UnifiedTileManagerInitialization *)&v73);
            return v30;
          }
          else
          {
            v60[0] = 0;
            v31 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *, _BYTE *))(*(_QWORD *)a5 + 136LL))(
                    a5,
                    v60);
            v33 = v31;
            if ( v31 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x13C,
                (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
                (const char *)(unsigned int)v31,
                v59);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
              UnifiedTileTelemetry::UnifiedTileManagerInitialization::~UnifiedTileManagerInitialization((UnifiedTileTelemetry::UnifiedTileManagerInitialization *)&v73);
              return v33;
            }
            else
            {
              if ( !v60[0] || (v34 = 1, a7) )
                v34 = 0;
              if ( !string || v34 )
              {
                v11 = 0;
              }
              else
              {
                *(_OWORD *)v72 = TileData;
                *(_OWORD *)v68 = 0;
                v69 = 0;
                *(_QWORD *)v61 = &v73;
                v66 = v72;
                std::vector<_GUID>::_Construct_n<_GUID * const &,_GUID * const &>(v68, 1, &v66, v61);
                std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(v64);
                v48 = *(_QWORD *)(a1 + 192);
                v66 = (std::_Ref_count_base **)v48;
                if ( v48 > (v65 - *(_QWORD *)v64) >> 3 )
                {
                  if ( v48 > 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector too long");
                  std::vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>::_Reallocate<0>(v64, &v66);
                }
                v49 = *(_QWORD ***)(a1 + 184);
                for ( i = *v49; i != v49; i = (_QWORD *)*i )
                {
                  v51 = i + 4;
                  if ( *(_QWORD *)&v64[2] == v65 )
                  {
                    std::vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer> const &>(
                      v64,
                      *(_QWORD *)&v64[2],
                      v51);
                  }
                  else
                  {
                    v52 = *v51;
                    **(_QWORD **)&v64[2] = *v51;
                    if ( v52 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
                    *(_QWORD *)&v64[2] += 8LL;
                  }
                }
                LOBYTE(v59) = v60[0] != 0;
                CacheManager = (char *)DataStoreCache::Create_CacheManager(
                                         (int)v61,
                                         *(_QWORD *)(a1 + 128),
                                         (int)v64,
                                         (int)v68,
                                         v59,
                                         string,
                                         a1 + 552);
                v54 = 0;
                if ( &v71 != CacheManager )
                {
                  v54 = *(_QWORD *)CacheManager;
                  *(_QWORD *)CacheManager = 0;
                }
                v32 = *(_QWORD *)(a1 + 520);
                *(_QWORD *)(a1 + 520) = v54;
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                v55 = *(_QWORD *)v61;
                if ( *(_QWORD *)v61 )
                {
                  *(_QWORD *)v61 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                }
                if ( *(_QWORD *)v64 )
                {
                  std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>>(
                    *(_QWORD *)v64,
                    *(_QWORD *)&v64[2]);
                  std::_Deallocate<16>(*(_QWORD *)v64, (v65 - *(_QWORD *)v64) & 0xFFFFFFFFFFFFFFF8uLL);
                  *(_OWORD *)v64 = 0;
                  v65 = 0;
                }
                if ( *(_QWORD *)v68 )
                  std::_Deallocate<16>(*(_QWORD *)v68, (v69 - *(_QWORD *)v68) & 0xFFFFFFFFFFFFFFF0uLL);
              }
              _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                a1 + 152,
                v32,
                0);
              _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                a1 + 160,
                v35,
                0);
              v36 = WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::ExecuteDataStoreReconciliationStages(
                      (WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *)a1,
                      (struct UnifiedTileTelemetry::UnifiedTileManagerInitialization *)&v73,
                      v11,
                      v67);
              v37 = v36;
              if ( v36 == -2147286527 )
              {
                WindowsDeleteString(string);
                string = 0;
                v38 = v62;
                if ( v62 )
                {
                  v62 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                }
                v73 = &UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable';
                wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v73);
                wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v76);
                wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v75);
                wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(v74);
                return 2147680769LL;
              }
              else if ( v36 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x157,
                  (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
                  (const char *)(unsigned int)v36,
                  v59);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
                UnifiedTileTelemetry::UnifiedTileManagerInitialization::~UnifiedTileManagerInitialization((UnifiedTileTelemetry::UnifiedTileManagerInitialization *)&v73);
                return v37;
              }
              else
              {
                WindowsDeleteString(string);
                string = 0;
                v41 = v62;
                if ( v62 )
                {
                  v62 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                }
                v73 = &UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable';
                wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v73);
                wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v76);
                wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v75);
                wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(v74);
                return 0;
              }
            }
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
          (const char *)(unsigned int)CanonicalTransformers,
          v59);
        v56 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        }
      }
    }
    v73 = &UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable';
    wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v73);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v76);
    wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v75);
    wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(v74);
    result = v25;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15B,
                           (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
                           v39);
  }
  return result;
}

```

## disassembly

```asm
0x180038760  mov     [rsp+arg_8], rbx
0x180038765  mov     [rsp+arg_10], rsi
0x18003876a  push    rdi
0x18003876b  push    r12
0x18003876d  push    r13
0x18003876f  push    r14
0x180038771  push    r15
0x180038773  sub     rsp, 220h
0x18003877a  mov     rax, cs:__security_cookie
0x180038781  xor     rax, rsp
0x180038784  mov     [rsp+248h+var_38], rax
0x18003878c  mov     rbx, r9
0x18003878f  mov     edi, r8d
0x180038792  mov     r12d, edx
0x180038795  mov     r14, rcx
0x180038798  mov     r15, [rsp+248h+arg_20]
0x1800387a0  mov     rax, [rsp+248h+arg_28]
0x1800387a8  mov     [rsp+248h+var_1C8], rax
0x1800387b0  lea     rdx, aUnifiedtileman_4; "UnifiedTileManagerInitialization"
0x1800387b7  lea     rcx, [rsp+248h+var_188]; struct wil::details::IFailureCallback *
0x1800387bf  call    ??0?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800387c4  lea     rax, ??_7UnifiedTileManagerInitialization@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable'
0x1800387cb  mov     [rsp+248h+var_188], rax
0x1800387d3  mov     dl, [rsp+248h+arg_30]
0x1800387da  mov     r13d, 1
0x1800387e0  xor     dl, r13b; bool
0x1800387e3  lea     rcx, [rsp+248h+var_188]; this
0x1800387eb  call    ?StartActivity@UnifiedTileManagerInitialization@UnifiedTileTelemetry@@QEAAX_N@Z; UnifiedTileTelemetry::UnifiedTileManagerInitialization::StartActivity(bool)
0x1800387f0  nop
0x1800387f1  lea     rsi, ?s_lock@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::s_lock
0x1800387f8  mov     rcx, rsi; SRWLock
0x1800387fb  call    cs:__imp_AcquireSRWLockExclusive
0x180038801  mov     [rsp+248h+var_1D0], rsi
0x180038806  mov     qword ptr [rsp+248h+var_200], r14
0x18003880b  lea     r8, [rsp+248h+var_200]
0x180038810  lea     rdx, [rsp+248h+var_198]
0x180038818  call    ??$_Emplace@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@?$_Tree@V?$_Tset_traits@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@U?$less@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@std@@V?$allocator@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@PEAX@std@@_N@1@$$QEAPEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Z; std::_Tree<std::_Tset_traits<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *,std::less<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,std::allocator<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>,0>>::_Emplace<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>(WindowsInternal::Shell::UnifiedTile::UnifiedTileManager * &&)
0x18003881d  nop
0x18003881e  mov     rcx, rsi; SRWLock
0x180038821  call    cs:__imp_ReleaseSRWLockExclusive
0x180038827  cmp     [r14+90h], r15
0x18003882e  jz      loc_180039018
0x180038834  xor     esi, esi
0x180038836  test    r15, r15
0x180038839  jz      short loc_18003884B
0x18003883b  mov     rax, [r15]
0x18003883e  mov     rcx, r15
0x180038841  mov     rax, [rax+8]
0x180038845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003884a  nop
0x18003884b  mov     rcx, [r14+90h]
0x180038852  mov     [r14+90h], r15
0x180038859  test    rcx, rcx
0x18003885c  jz      short loc_18003886B
0x18003885e  mov     rax, [rcx]
0x180038861  mov     rax, [rax+10h]
0x180038865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003886a  nop
0x18003886b  mov     [r14+23Ch], edi
0x180038872  mov     [r14+238h], r12d
0x180038879  cmp     [r14+210h], rbx
0x180038880  jz      short loc_1800388B7
0x180038882  test    rbx, rbx
0x180038885  jz      short loc_180038897
0x180038887  mov     rax, [rbx]
0x18003888a  mov     rcx, rbx
0x18003888d  mov     rax, [rax+8]
0x180038891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038896  nop
0x180038897  mov     rcx, [r14+210h]
0x18003889e  mov     [r14+210h], rbx
0x1800388a5  test    rcx, rcx
0x1800388a8  jz      short loc_1800388B7
0x1800388aa  mov     rax, [rcx]
0x1800388ad  mov     rax, [rax+10h]
0x1800388b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388b6  nop
0x1800388b7  lea     rcx, [rsp+248h+var_200]
0x1800388bc  call    ?Create_DataManager@DataStoreCache@@YA?AV?$ComPtr@UIDataManager@DataStoreCache@@@WRL@Microsoft@@XZ; DataStoreCache::Create_DataManager(void)
0x1800388c1  mov     rcx, rsi
0x1800388c4  lea     rdx, [rsp+248h+var_1A8]
0x1800388cc  cmp     rdx, rax
0x1800388cf  jz      short loc_1800388D7
0x1800388d1  mov     rcx, [rax]
0x1800388d4  mov     [rax], rsi
0x1800388d7  mov     rdx, [r14+80h]
0x1800388de  mov     [r14+80h], rcx
0x1800388e5  test    rdx, rdx
0x1800388e8  jz      short loc_1800388FA
0x1800388ea  mov     rax, [rdx]
0x1800388ed  mov     rcx, rdx
0x1800388f0  mov     rax, [rax+10h]
0x1800388f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388f9  nop
0x1800388fa  mov     rcx, qword ptr [rsp+248h+var_200]
0x1800388ff  test    rcx, rcx
0x180038902  jz      short loc_180038916
0x180038904  mov     qword ptr [rsp+248h+var_200], rsi
0x180038909  mov     rax, [rcx]
0x18003890c  mov     rax, [rax+10h]
0x180038910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038915  nop
0x180038916  mov     rax, [r15]
0x180038919  mov     rbx, [rax+58h]
0x18003891d  lea     rdi, [r14+220h]
0x180038924  mov     rcx, rdi
0x180038927  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003892c  mov     rdx, rdi
0x18003892f  mov     rcx, r15
0x180038932  mov     rax, rbx
0x180038935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003893a  mov     ebx, eax
0x18003893c  test    eax, eax
0x18003893e  js      loc_180038BB3
0x180038944  cmp     [rdi], rsi
0x180038947  jz      loc_180038C1A
0x18003894d  mov     rcx, [rdi]; this
0x180038950  call    ?IsThreadEffectiveUser@UserHelpers@@YA_NPEAUIUser@System@Windows@@@Z; UserHelpers::IsThreadEffectiveUser(Windows::System::IUser *)
0x180038955  test    al, al
0x180038957  jz      loc_180038FD4
0x18003895d  mov     [rsp+248h+var_1F8], rsi
0x180038962  mov     qword ptr [rsp+248h+var_200], r14
0x180038967  lea     rcx, [rsp+248h+var_1F8]
0x18003896c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038971  lea     rdx, [rsp+248h+var_200]
0x180038976  lea     rcx, [rsp+248h+var_1F8]
0x18003897b  call    ??$MakeAndInitialize@VDataItemEventHandlerWrapper@DataStoreCache@@UIDataItemEventHandler@@PEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAPEAUIDataItemEventHandler@@$$QEAPEAVUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>(IDataItemEventHandler * *,WindowsInternal::Shell::UnifiedTile::UnifiedTileManager * &&)
0x180038980  mov     ebx, eax
0x180038982  test    eax, eax
0x180038984  js      loc_180038CE6
0x18003898a  mov     rcx, [r14+80h]
0x180038991  mov     rax, [rcx]
0x180038994  mov     r8, [rsp+248h+var_1F8]
0x180038999  lea     rdx, [rsp+248h+var_200]
0x18003899e  mov     rax, [rax+28h]
0x1800389a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389a7  mov     eax, [rax]
0x1800389a9  mov     [r14+240h], eax
0x1800389b0  mov     rdx, r15; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *
0x1800389b3  mov     rcx, r14; this
0x1800389b6  call    ?ReadCustomTransformers@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@AEAAJPEAUIUnifiedTileManagerOptions@234@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::ReadCustomTransformers(WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *)
0x1800389bb  mov     ebx, eax
0x1800389bd  test    eax, eax
0x1800389bf  js      loc_180038C63
0x1800389c5  mov     rdx, r15; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *
0x1800389c8  mov     rcx, r14; this
0x1800389cb  call    ?CreateCanonicalTransformers@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@AEAAJPEAUIUnifiedTileManagerOptions@234@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::CreateCanonicalTransformers(WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerOptions *)
0x1800389d0  mov     ebx, eax
0x1800389d2  test    eax, eax
0x1800389d4  js      loc_180038F51
0x1800389da  mov     [rsp+248h+string], rsi
0x1800389df  mov     rax, [r15]
0x1800389e2  mov     rbx, [rax+78h]
0x1800389e6  xor     ecx, ecx; string
0x1800389e8  call    cs:__imp_WindowsDeleteString
0x1800389ee  mov     [rsp+248h+string], rsi
0x1800389f3  lea     rdx, [rsp+248h+string]
0x1800389f8  mov     rcx, r15
0x1800389fb  mov     rax, rbx
0x1800389fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a03  mov     ebx, eax
0x180038a05  test    eax, eax
0x180038a07  js      loc_18003903B
0x180038a0d  mov     [rsp+248h+var_208], sil
0x180038a12  mov     rax, [r15]
0x180038a15  lea     rdx, [rsp+248h+var_208]
0x180038a1a  mov     rcx, r15
0x180038a1d  mov     rax, [rax+88h]
0x180038a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a29  mov     ebx, eax
0x180038a2b  test    eax, eax
0x180038a2d  js      loc_180039087
0x180038a33  cmp     [rsp+248h+var_208], sil
0x180038a38  jnz     loc_1800390D3
0x180038a3e  mov     al, sil
0x180038a41  cmp     [rsp+248h+string], rsi
0x180038a46  jnz     loc_180038D69
0x180038a4c  mov     r13b, sil
0x180038a4f  lea     rcx, [r14+98h]
0x180038a56  xor     r8d, r8d
0x180038a59  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180038a5e  lea     rcx, [r14+0A0h]
0x180038a65  xor     r8d, r8d
0x180038a68  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180038a6d  mov     r9, [rsp+248h+var_1C8]; struct WindowsInternal::Shell::UnifiedTile::UnifiedTileManagerCreationStatus *
0x180038a75  mov     r8b, r13b; bool
0x180038a78  lea     rdx, [rsp+248h+var_188]; struct UnifiedTileTelemetry::UnifiedTileManagerInitialization *
0x180038a80  mov     rcx, r14; this
0x180038a83  call    ?ExecuteDataStoreReconciliationStages@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@AEAAJAEAVUnifiedTileManagerInitialization@UnifiedTileTelemetry@@_NPEAVUnifiedTileManagerCreationStatus@234@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::ExecuteDataStoreReconciliationStages(UnifiedTileTelemetry::UnifiedTileManagerInitialization &,bool,WindowsInternal::Shell::UnifiedTile::UnifiedTileManagerCreationStatus *)
0x180038a88  mov     ebx, eax
0x180038a8a  mov     edi, 80030201h
0x180038a8f  cmp     eax, edi
0x180038a91  jnz     loc_180038B35
0x180038a97  mov     rcx, [rsp+248h+string]; string
0x180038a9c  call    cs:__imp_WindowsDeleteString
0x180038aa2  mov     [rsp+248h+string], rsi
0x180038aa7  mov     rcx, [rsp+248h+var_1F8]
0x180038aac  test    rcx, rcx
0x180038aaf  jz      short loc_180038AC3
0x180038ab1  mov     [rsp+248h+var_1F8], rsi
0x180038ab6  mov     rax, [rcx]
0x180038ab9  mov     rax, [rax+10h]
0x180038abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ac2  nop
0x180038ac3  lea     rax, ??_7UnifiedTileManagerInitialization@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable'
0x180038aca  mov     [rsp+248h+var_188], rax
0x180038ad2  lea     rcx, [rsp+248h+var_188]
0x180038ada  call    ?Destroy@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180038adf  lea     rcx, [rsp+248h+var_68]; this
0x180038ae7  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180038aec  lea     rcx, [rsp+248h+var_70]
0x180038af4  call    ?reset@?$shared_object@V?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180038af9  lea     rcx, [rsp+248h+var_180]
0x180038b01  call    ??1?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180038b06  mov     eax, edi
0x180038b08  mov     rcx, [rsp+248h+var_38]
0x180038b10  xor     rcx, rsp; StackCookie
0x180038b13  call    __security_check_cookie
0x180038b18  lea     r11, [rsp+248h+var_28]
0x180038b20  mov     rbx, [r11+38h]
0x180038b24  mov     rsi, [r11+40h]
0x180038b28  mov     rsp, r11
0x180038b2b  pop     r15
0x180038b2d  pop     r14
0x180038b2f  pop     r13
0x180038b31  pop     r12
0x180038b33  pop     rdi
0x180038b34  retn
0x180038b35  test    ebx, ebx
0x180038b37  js      loc_180039110
0x180038b3d  mov     rcx, [rsp+248h+string]; string
0x180038b42  call    cs:__imp_WindowsDeleteString
0x180038b48  mov     [rsp+248h+string], rsi
0x180038b4d  mov     rcx, [rsp+248h+var_1F8]
0x180038b52  test    rcx, rcx
0x180038b55  jz      short loc_180038B69
0x180038b57  mov     [rsp+248h+var_1F8], rsi
0x180038b5c  mov     rax, [rcx]
0x180038b5f  mov     rax, [rax+10h]
0x180038b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b68  nop
0x180038b69  lea     rax, ??_7UnifiedTileManagerInitialization@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable'
0x180038b70  mov     [rsp+248h+var_188], rax
0x180038b78  lea     rcx, [rsp+248h+var_188]
0x180038b80  call    ?Destroy@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180038b85  lea     rcx, [rsp+248h+var_68]; this
0x180038b8d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180038b92  lea     rcx, [rsp+248h+var_70]
0x180038b9a  call    ?reset@?$shared_object@V?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180038b9f  lea     rcx, [rsp+248h+var_180]
0x180038ba7  call    ??1?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180038bac  xor     eax, eax
0x180038bae  jmp     loc_180038B08
0x180038bb3  mov     rcx, [rsp+248h]; this
0x180038bbb  mov     r9d, ebx; char *
0x180038bbe  lea     r8, aShellcommonShe_56; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180038bc5  mov     edx, 10Eh; void *
0x180038bca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038bcf  nop
0x180038bd0  lea     rax, ??_7UnifiedTileManagerInitialization@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::UnifiedTileManagerInitialization::`vftable'
0x180038bd7  mov     [rsp+248h+var_188], rax
0x180038bdf  lea     rcx, [rsp+248h+var_188]
0x180038be7  call    ?Destroy@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180038bec  lea     rcx, [rsp+248h+var_68]; this
0x180038bf4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180038bf9  lea     rcx, [rsp+248h+var_70]
0x180038c01  call    ?reset@?$shared_object@V?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180038c06  lea     rcx, [rsp+248h+var_180]
0x180038c0e  call    ??1?$ActivityData@VUnifiedTileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<UnifiedTileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180038c13  mov     eax, ebx
0x180038c15  jmp     loc_180038B08
0x180038c1a  mov     rcx, rdi
0x180038c1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038c22  mov     rcx, rdi; this
0x180038c25  call    ?GetCurrentUser@UserHelpers@@YAJPEAPEAUIUser@System@Windows@@@Z; UserHelpers::GetCurrentUser(Windows::System::IUser * *)
0x180038c2a  mov     ebx, eax
0x180038c2c  test    eax, eax
0x180038c2e  js      loc_18003901F
0x180038c34  mov     cl, sil
0x180038c37  mov     rax, [rsp+248h]
0x180038c3f  test    cl, cl
0x180038c41  jz      loc_18003895D
0x180038c47  mov     r9d, ebx; char *
0x180038c4a  lea     r8, aShellcommonShe_56; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180038c51  mov     edx, 116h; void *
0x180038c56  mov     rcx, rax; this
0x180038c59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038c5e  jmp     loc_18003895D
0x180038c63  mov     rcx, [rsp+248h]; this
0x180038c6b  mov     r9d, ebx; char *
0x180038c6e  lea     r8, aShellcommonShe_56; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180038c75  mov     edx, 131h; void *
0x180038c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c7f  nop
0x180038c80  mov     rcx, [rsp+248h+var_1F8]
0x180038c85  test    rcx, rcx
0x180038c88  jz      short loc_180038C9C
0x180038c8a  mov     [rsp+248h+var_1F8], rsi
0x180038c8f  mov     rax, [rcx]
0x180038c92  mov     rax, [rax+10h]
  ... truncated ...
```
