# MapsStoreManager::Initialize(ushort const *,ushort const *,ushort const *,void (*)(float,void *),void (*)(long,void *),void (*)(long,unsigned __int64,void *),void (*)(long,IMapRegionNode *,void *),void *)

- ea: `0x18001944c`
- end: `0x180019e18`
- name: `?Initialize@MapsStoreManager@@QEAAJPEBG00P6AXMPEAX@ZP6AXJ1@ZP6AXJ_K1@ZP6AXJPEAVIMapRegionNode@@1@Z1@Z`
- size: `2508`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void (*)(float, void *), void (*)(int, void *), void (*)(int, unsigned __int64, void *), void (*)(int, struct IMapRegionNode *, void *), void *)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011a10`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x180011d90`
- `0x180011ea0`
- `0x1800126c4`
- `0x180012720`
- `0x1800141a4`
- `0x1800141d8`
- `0x18001420c`
- `0x180014968`
- `0x180014a24`
- `0x180014a7c`
- `0x180014ae0`
- `0x180016178`
- `0x1800161b0`
- `0x180016548`
- `0x180016770`
- `0x180016d58`
- `0x180016e10`
- `0x180017334`
- `0x1800179ac`
- `0x18001944c`
- `0x180019f3c`
- `0x180019f68`
- `0x18001b9e0`
- `0x18001d108`
- `0x18001d45c`
- `0x180038744`
- `0x18003be64`
- `0x18003d830`
- `0x18003dbbc`
- `0x18004653c`
- `0x18004670c`
- `0x18004d954`
- `0x1800763e8`
- `0x180098010`

## import_xrefs

- `MapConfiguration!ConfigurationManager_Create` at `0x180019674`
- `MapConfiguration!ConfigurationManager_Create` at `0x180019674`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001953b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001953b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001957e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001957e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d6f`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001986e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800199e2`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001986e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800199e2`
- `ZTrace_Maps!ZTraceHelper` at `0x1800194b4`
- `ZTrace_Maps!ZTraceHelper` at `0x1800194b4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019694`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019742`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019694`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019742`

## string_xrefs

- `0x180019496`: `Initialize called when store is already Initialized`
- `0x180019594`: `\mapscache`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void (*a5)(float, void *),
        void (*a6)(int, void *),
        void (*a7)(int, unsigned __int64, void *),
        void (*a8)(int, struct IMapRegionNode *, void *),
        void *a9)
{
  unsigned int v12; // r13d
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _RTL_CRITICAL_SECTION *v18; // rbx
  unsigned __int64 v19; // rdx
  std::_Ref_count_base *OwningThread; // rcx
  int v21; // eax
  wil *v22; // rcx
  MapControl::ConfigurationManager *v23; // rbx
  int SystemLocaleInfo; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 Configuration; // rax
  _DWORD *v28; // rbx
  std::_Ref_count_base *LockSemaphore; // rcx
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rax
  ULONG_PTR *v33; // rax
  ULONG_PTR v34; // rdx
  struct _RTL_CRITICAL_SECTION_DEBUG *v35; // rdx
  __int64 v36; // r9
  __int64 GenerationsManager; // rax
  __int64 *v38; // rax
  __int64 v39; // rdx
  void *v40; // rdx
  char *v41; // r15
  std::_Ref_count_base *v42; // rcx
  __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  _DWORD *v46; // r14
  std::_Ref_count_base *SpinCount; // rcx
  int v48; // eax
  _QWORD v49[2]; // [rsp+40h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v50[2]; // [rsp+50h] [rbp-1D8h] BYREF
  int v51; // [rsp+60h] [rbp-1C8h] BYREF
  MapsStorePal::MapsStoreLocalSettingsInitializer *v52[2]; // [rsp+68h] [rbp-1C0h] BYREF
  int v53; // [rsp+78h] [rbp-1B0h] BYREF
  _RTL_CRITICAL_SECTION *v54; // [rsp+80h] [rbp-1A8h]
  MapControl::LocaleMapConfiguration *v55; // [rsp+88h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v56; // [rsp+90h] [rbp-198h]
  unsigned __int64 v57; // [rsp+98h] [rbp-190h] BYREF
  const unsigned __int16 *v58; // [rsp+A0h] [rbp-188h]
  const void *v59; // [rsp+A8h] [rbp-180h]
  _BYTE v60[16]; // [rsp+B0h] [rbp-178h] BYREF
  _BYTE v61[32]; // [rsp+C0h] [rbp-168h] BYREF
  _BYTE v62[32]; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v63[32]; // [rsp+100h] [rbp-128h] BYREF
  _BYTE v64[32]; // [rsp+120h] [rbp-108h] BYREF
  _BYTE v65[32]; // [rsp+140h] [rbp-E8h] BYREF
  _BYTE v66[32]; // [rsp+160h] [rbp-C8h] BYREF
  _BYTE v67[32]; // [rsp+180h] [rbp-A8h] BYREF
  _BYTE v68[32]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v69[32]; // [rsp+1C0h] [rbp-68h] BYREF

  v58 = a4;
  v59 = lpCriticalSection;
  v12 = 0;
  if ( MapControl::RegionSet::getIsLoaded(lpCriticalSection) )
  {
    ZTraceHelper(
      2,
      "MapsStoreManager::Initialize",
      88,
      lpCriticalSection,
      "Initialize called when store is already Initialized");
    return 0;
  }
  else
  {
    std::wstring::wstring(v67);
    std::wstring::wstring(v66);
    std::wstring::wstring(v65);
    std::wstring::wstring(v64);
    std::wstring::wstring(v63);
    std::wstring::wstring(v62);
    std::wstring::wstring(v61);
    try
    {
      if ( !BYTE1(lpCriticalSection[1].DebugInfo) )
      {
        v54 = &Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex;
        EnterCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex);
        v14 = Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount;
        if ( !Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount )
        {
          v52[0] = (MapsStorePal::MapsStoreLocalSettingsInitializer *)operator new(1u);
          _InterlockedExchange64(
            &Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstance,
            MapsStorePal::MapsStoreLocalSettingsInitializer::MapsStoreLocalSettingsInitializer(v52[0]));
          v14 = Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount;
        }
        Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount = v14 + 1;
        LeaveCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex);
        Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::initialize();
        BYTE1(lpCriticalSection[1].DebugInfo) = 1;
      }
      v15 = std::wstring::wstring(v68, L"\\mapscache");
      v16 = std::operator+<unsigned short>(v69, a2, v15);
      std::wstring::operator=(&lpCriticalSection[1].LockCount, v16);
      std::wstring::_Tidy_deallocate(v69);
      std::wstring::_Tidy_deallocate(v68);
      std::wstring::assign(&lpCriticalSection[2], a3);
      v17 = std::make_unique<Pal::NetworkManagerImplementation,,0>(v49);
      std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(
        &lpCriticalSection[2].SpinCount,
        v17);
      std::unique_ptr<Pal::NetworkRequestImplWindowsService>::~unique_ptr<Pal::NetworkRequestImplWindowsService>(v49);
      v18 = (_RTL_CRITICAL_SECTION *)operator new(0xB0u);
      v54 = v18;
      v18->LockCount = 1;
      v18->RecursionCount = 1;
      v18->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&std::_Ref_count_obj2<Utility::SharedMemoryCache>::`vftable';
      std::_Construct_in_place<Utility::SharedMemoryCache,>(&v18->OwningThread);
      *(_QWORD *)&lpCriticalSection[3].LockCount = &v18->OwningThread;
      OwningThread = (std::_Ref_count_base *)lpCriticalSection[3].OwningThread;
      lpCriticalSection[3].OwningThread = v18;
      if ( OwningThread )
        std::_Ref_count_base::_Decref(OwningThread);
      Utility::SharedMemoryCache::setMaximumSize(*(LPCRITICAL_SECTION *)&lpCriticalSection[3].LockCount, v19);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&lpCriticalSection[3]);
      v21 = ConfigurationManager_Create(&lpCriticalSection[3]);
      if ( v21 >= 0 )
      {
        v23 = *(MapControl::ConfigurationManager **)&lpCriticalSection[3].DebugInfo->EntryCount;
        v54 = (_RTL_CRITICAL_SECTION *)v23;
        SystemLocaleInfo = MapPlatformConfig::GetSystemLocaleInfo(v62, v61);
        if ( SystemLocaleInfo >= 0 )
        {
          v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
          std::wstring::wstring(v69, v25);
          v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62);
          std::wstring::wstring(v68, v26);
          Configuration = MapControl::ConfigurationManager::getConfiguration(v23);
          std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
            &v55,
            Configuration);
          Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v60);
          std::wstring::_Tidy_deallocate(v68);
          std::wstring::_Tidy_deallocate(v69);
          if ( v55 )
          {
            v57 = 0;
            v53 = 256000;
            MapControl::LocaleMapConfiguration::getPersistentCacheSizeInBytes(v55, &v57);
            v52[0] = (MapsStorePal::MapsStoreLocalSettingsInitializer *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&lpCriticalSection[2]);
            LODWORD(v49[0]) = 4;
            v28 = operator new(0x1E0u);
            v50[0] = (std::_Ref_count_base *)v28;
            v28[2] = 1;
            v28[3] = 1;
            *(_QWORD *)v28 = &std::_Ref_count_obj2<pplx::details::_Task_impl<unsigned char>>::`vftable';
            std::_Construct_in_place<MapControl::PersistentMapsCache,enum Pal::FileLocation,unsigned short const *,std::shared_ptr<Utility::SharedMemoryCache> &,unsigned int &,unsigned __int64 &>(
              (_DWORD)v28 + 16,
              (unsigned int)v49,
              (unsigned int)v52,
              (_DWORD)lpCriticalSection + 128,
              (__int64)&v53,
              (__int64)&v57);
            lpCriticalSection[8].OwningThread = v28 + 4;
            LockSemaphore = (std::_Ref_count_base *)lpCriticalSection[8].LockSemaphore;
            lpCriticalSection[8].LockSemaphore = v28;
            if ( LockSemaphore )
              std::_Ref_count_base::_Decref(LockSemaphore);
            (*(void (__fastcall **)(HANDLE, int *, _QWORD))(*(_QWORD *)lpCriticalSection[8].OwningThread + 88LL))(
              lpCriticalSection[8].OwningThread,
              &v51,
              0);
            v30 = -2080309245;
            if ( v51 == 41943040 )
              v30 = -2080309235;
            if ( v51 == 1 )
            {
              v31 = Core::requirePresent<Pal::Stream>(v49, &v55);
              v32 = MapControl::MapDataTypesRegistryFactory::createForBingMapsStore(v52, v31);
              v33 = (ULONG_PTR *)std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
                                   v50,
                                   v32);
              v34 = *v33;
              *v33 = lpCriticalSection[8].SpinCount;
              lpCriticalSection[8].SpinCount = v34;
              v35 = (struct _RTL_CRITICAL_SECTION_DEBUG *)v33[1];
              v33[1] = (ULONG_PTR)lpCriticalSection[9].DebugInfo;
              lpCriticalSection[9].DebugInfo = v35;
              if ( v50[1] )
                std::_Ref_count_base::_Decref(v50[1]);
              Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v52);
              Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v49);
              v36 = Core::requirePresent<Pal::Stream>(v49, &lpCriticalSection[8].SpinCount);
              GenerationsManager = MapControl::Factories::createGenerationsManager(
                                     v52,
                                     lpCriticalSection[2].SpinCount,
                                     &lpCriticalSection[3].LockCount,
                                     v36);
              v38 = (__int64 *)std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
                                 v50,
                                 GenerationsManager);
              v39 = *v38;
              *v38 = *(_QWORD *)&lpCriticalSection[9].LockCount;
              *(_QWORD *)&lpCriticalSection[9].LockCount = v39;
              v40 = (void *)v38[1];
              v38[1] = (__int64)lpCriticalSection[9].OwningThread;
              lpCriticalSection[9].OwningThread = v40;
              if ( v50[1] )
                std::_Ref_count_base::_Decref(v50[1]);
              Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v52);
              Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v49);
              v52[0] = (MapsStorePal::MapsStoreLocalSettingsInitializer *)lpCriticalSection[2].SpinCount;
              v41 = (char *)operator new(0xC8u);
              v50[0] = (std::_Ref_count_base *)v41;
              *((_DWORD *)v41 + 2) = 1;
              *((_DWORD *)v41 + 3) = 1;
              *(_QWORD *)v41 = &std::_Ref_count_obj2<pplx::details::_Task_impl<unsigned char>>::`vftable';
              std::_Construct_in_place<MapControl::PersistedDataLoader,std::shared_ptr<MapControl::DataTypesRegistry> &,std::shared_ptr<MapControl::GenerationsManager> &,Pal::NetworkManager &,std::shared_ptr<Utility::SharedMemoryCache> &,std::shared_ptr<MapControl::PersistentCache> &,unsigned int const &>(
                (_DWORD)v41 + 16,
                (_DWORD)lpCriticalSection + 352,
                (_DWORD)lpCriticalSection + 368,
                v52[0],
                (__int64)&lpCriticalSection[3].LockCount,
                (__int64)&lpCriticalSection[8].OwningThread,
                (__int64)&dword_1800A4694);
              lpCriticalSection[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)(v41 + 16);
              v42 = *(std::_Ref_count_base **)&lpCriticalSection[8].LockCount;
              *(_QWORD *)&lpCriticalSection[8].LockCount = v41;
              if ( v42 )
                std::_Ref_count_base::_Decref(v42);
              v43 = *(__int64 **)&lpCriticalSection[9].LockCount;
              v44 = *v43;
              *(_OWORD *)v50 = 0;
              v45 = *(_QWORD *)&lpCriticalSection[8].LockCount;
              if ( v45 )
                _InterlockedAdd((volatile signed __int32 *)(v45 + 8), 1u);
              v50[0] = (std::_Ref_count_base *)lpCriticalSection[8].DebugInfo;
              v50[1] = *(std::_Ref_count_base **)&lpCriticalSection[8].LockCount;
              (*(void (__fastcall **)(__int64 *, std::_Ref_count_base **))(v44 + 16))(v43, v50);
              if ( v50[1] )
                std::_Ref_count_base::_Decref(v50[1]);
              v50[0] = (std::_Ref_count_base *)operator new(0x50u);
              v49[0] = MapControl::RegionManager::RegionManager(
                         v50[0],
                         (int)lpCriticalSection + 352,
                         (int)lpCriticalSection + 368,
                         (int)lpCriticalSection + 320,
                         (__int64)&v54[8],
                         4);
              std::unique_ptr<MapControl::RegionManager>::operator=<std::default_delete<MapControl::RegionManager>,0>(
                &lpCriticalSection[3].LockSemaphore,
                v49);
              std::unique_ptr<MapControl::RegionManager>::~unique_ptr<MapControl::RegionManager>(v49);
              MapControl::LocaleMapConfiguration::getValueString(v55, 298, &lpCriticalSection[14].SpinCount);
              v46 = operator new(0x60u);
              v46[2] = 1;
              v46[3] = 1;
              *(_QWORD *)v46 = &std::_Ref_count_obj2<MapsStoreManager::CopyrightData>::`vftable';
              std::_Construct_in_place<MapsStoreManager::CopyrightData,>((Pal::Mutex *)(v46 + 4));
              lpCriticalSection[15].LockSemaphore = v46 + 4;
              SpinCount = (std::_Ref_count_base *)lpCriticalSection[15].SpinCount;
              lpCriticalSection[15].SpinCount = (ULONG_PTR)v46;
              if ( SpinCount )
                std::_Ref_count_base::_Decref(SpinCount);
              *((_DWORD *)lpCriticalSection[15].LockSemaphore + 18) = 0;
              *((_DWORD *)lpCriticalSection[15].LockSemaphore + 19) = 0;
              if ( *(_QWORD *)&lpCriticalSection[5].LockCount )
                __int2c();
              std::wstring::assign(&lpCriticalSection[13].OwningThread, v58);
              lpCriticalSection[11].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a5;
              *(_QWORD *)&lpCriticalSection[11].LockCount = a6;
              lpCriticalSection[11].OwningThread = a7;
              lpCriticalSection[11].LockSemaphore = a8;
              lpCriticalSection[11].SpinCount = (ULONG_PTR)a9;
              EnterCriticalSection(lpCriticalSection);
              LOBYTE(lpCriticalSection[1].DebugInfo) = 1;
              LeaveCriticalSection(lpCriticalSection);
              if ( v56 )
                std::_Ref_count_base::_Decref(v56);
            }
            else
            {
              v12 = ZTraceReportOrigination(v30, "MapsStoreManager::Initialize", 141, lpCriticalSection);
              if ( v56 )
                std::_Ref_count_base::_Decref(v56);
            }
          }
          else
          {
            v12 = ZTraceReportOrigination(-2147467259, "MapsStoreManager::Initialize", 128, lpCriticalSection);
            if ( v56 )
              std::_Ref_count_base::_Decref(v56);
          }
          std::wstring::_Tidy_deallocate(v61);
          std::wstring::_Tidy_deallocate(v62);
          std::wstring::_Tidy_deallocate(v63);
          std::wstring::_Tidy_deallocate(v64);
          std::wstring::_Tidy_deallocate(v65);
          std::wstring::_Tidy_deallocate(v66);
          std::wstring::_Tidy_deallocate(v67);
        }
        else
        {
          v12 = ZTraceReportPropagation(SystemLocaleInfo, "MapsStoreManager::Initialize", 125, lpCriticalSection);
          std::wstring::_Tidy_deallocate(v61);
          std::wstring::_Tidy_deallocate(v62);
          std::wstring::_Tidy_deallocate(v63);
          std::wstring::_Tidy_deallocate(v64);
          std::wstring::_Tidy_deallocate(v65);
          std::wstring::_Tidy_deallocate(v66);
          std::wstring::_Tidy_deallocate(v67);
        }
      }
      else
      {
        v12 = ZTraceReportPropagation(v21, "MapsStoreManager::Initialize", 121, lpCriticalSection);
        std::wstring::_Tidy_deallocate(v61);
        std::wstring::_Tidy_deallocate(v62);
        std::wstring::_Tidy_deallocate(v63);
        std::wstring::_Tidy_deallocate(v64);
        std::wstring::_Tidy_deallocate(v65);
        std::wstring::_Tidy_deallocate(v66);
        std::wstring::_Tidy_deallocate(v67);
      }
    }
    catch ( ... )
    {
      v48 = wil::ResultFromCaughtException(v22);
      return (unsigned int)ZTraceReportOrigination(v48, "MapsStoreManager::Initialize", 193, v59);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x18001944c  push    rbx
0x18001944e  push    rsi
0x18001944f  push    rdi
0x180019450  push    r12
0x180019452  push    r13
0x180019454  push    r14
0x180019456  push    r15
0x180019458  sub     rsp, 1F0h
0x18001945f  mov     rax, cs:__security_cookie
0x180019466  xor     rax, rsp
0x180019469  mov     [rsp+228h+var_48], rax
0x180019471  mov     [rsp+228h+var_188], r9
0x180019479  mov     r14, r8
0x18001947c  mov     rbx, rdx
0x18001947f  mov     rdi, rcx
0x180019482  mov     [rsp+228h+var_180], rcx
0x18001948a  xor     r13d, r13d
0x18001948d  call    ?getIsLoaded@RegionSet@MapControl@@QEAA_NXZ; MapControl::RegionSet::getIsLoaded(void)
0x180019492  test    al, al
0x180019494  jz      short loc_1800194C1
0x180019496  lea     rax, aInitializeCall; "Initialize called when store is already"...
0x18001949d  mov     [rsp+228h+var_208], rax
0x1800194a2  mov     r9, rdi
0x1800194a5  lea     r8d, [r13+58h]
0x1800194a9  lea     rdx, aMapsstoremanag_15; "MapsStoreManager::Initialize"
0x1800194b0  lea     ecx, [r13+2]
0x1800194b4  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x1800194ba  xor     eax, eax
0x1800194bc  jmp     loc_180019DF5
0x1800194c1  lea     rcx, [rsp+228h+var_A8]
0x1800194c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800194ce  nop
0x1800194cf  lea     rcx, [rsp+228h+var_C8]
0x1800194d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800194dc  nop
0x1800194dd  lea     rcx, [rsp+228h+var_E8]
0x1800194e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800194ea  nop
0x1800194eb  lea     rcx, [rsp+228h+var_108]
0x1800194f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800194f8  nop
0x1800194f9  lea     rcx, [rsp+228h+var_128]
0x180019501  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019506  nop
0x180019507  lea     rcx, [rsp+228h+var_148]
0x18001950f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019514  nop
0x180019515  lea     rcx, [rsp+228h+var_168]
0x18001951d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019522  nop
0x180019523  cmp     byte ptr [rdi+29h], 0
0x180019527  jnz     short loc_18001958F
0x180019529  lea     r15, ?sInstanceMutex@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex
0x180019530  mov     [rsp+228h+var_1A8], r15
0x180019538  mov     rcx, r15; lpCriticalSection
0x18001953b  call    cs:__imp_EnterCriticalSection
0x180019541  nop
0x180019542  mov     eax, cs:?sInstanceCount@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0HA; int Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount
0x180019548  mov     esi, 1
0x18001954d  test    eax, eax
0x18001954f  jnz     short loc_180019573
0x180019551  mov     ecx, esi; Size
0x180019553  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019558  mov     [rsp+228h+var_1C0], rax
0x18001955d  mov     rcx, rax; this
0x180019560  call    ??0MapsStoreLocalSettingsInitializer@MapsStorePal@@QEAA@XZ; MapsStorePal::MapsStoreLocalSettingsInitializer::MapsStoreLocalSettingsInitializer(void)
0x180019565  nop
0x180019566  xchg    rax, cs:?sInstance@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0U?$atomic@PEAVMapsStoreLocalSettingsInitializer@MapsStorePal@@@std@@A; std::atomic<MapsStorePal::MapsStoreLocalSettingsInitializer *> Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstance
0x18001956d  mov     eax, cs:?sInstanceCount@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0HA; int Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount
0x180019573  add     eax, esi
0x180019575  mov     cs:?sInstanceCount@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0HA, eax; int Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount
0x18001957b  mov     rcx, r15; lpCriticalSection
0x18001957e  call    cs:__imp_LeaveCriticalSection
0x180019584  call    ?initialize@?$PrivateSingleton@VMapsStorePerformanceTracerInitializer@MapsStorePal@@$$V@Pal@@SAXXZ; Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::initialize(void)
0x180019589  mov     [rdi+29h], sil
0x18001958d  jmp     short loc_180019594
0x18001958f  mov     esi, 1
0x180019594  lea     rdx, aMapscache; "\\mapscache"
0x18001959b  lea     rcx, [rsp+228h+var_88]
0x1800195a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800195a8  nop
0x1800195a9  mov     r8, rax
0x1800195ac  mov     rdx, rbx
0x1800195af  lea     rcx, [rsp+228h+var_68]
0x1800195b7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800195bc  lea     rcx, [rdi+30h]
0x1800195c0  mov     rdx, rax
0x1800195c3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800195c8  lea     rcx, [rsp+228h+var_68]
0x1800195d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800195d5  nop
0x1800195d6  lea     rcx, [rsp+228h+var_88]
0x1800195de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800195e3  mov     rdx, r14
0x1800195e6  lea     rcx, [rdi+50h]
0x1800195ea  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800195ef  lea     rcx, [rsp+228h+var_1E8]
0x1800195f4  call    ??$make_unique@VNetworkManagerImplementation@Pal@@$$V$0A@@std@@YA?AV?$unique_ptr@VNetworkManagerImplementation@Pal@@U?$default_delete@VNetworkManagerImplementation@Pal@@@std@@@0@XZ; std::make_unique<Pal::NetworkManagerImplementation,,0>(void)
0x1800195f9  lea     rcx, [rdi+70h]
0x1800195fd  mov     rdx, rax
0x180019600  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180019605  lea     rcx, [rsp+228h+var_1E8]
0x18001960a  call    ??1?$unique_ptr@VNetworkRequestImplWindowsService@Pal@@U?$default_delete@VNetworkRequestImplWindowsService@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImplWindowsService>::~unique_ptr<Pal::NetworkRequestImplWindowsService>(void)
0x18001960f  mov     ecx, 0B0h; Size
0x180019614  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019619  mov     rbx, rax
0x18001961c  mov     [rsp+228h+var_1A8], rax
0x180019624  mov     [rax+8], esi
0x180019627  mov     [rax+0Ch], esi
0x18001962a  lea     rax, ??_7?$_Ref_count_obj2@VSharedMemoryCache@Utility@@@std@@6B@; const std::_Ref_count_obj2<Utility::SharedMemoryCache>::`vftable'
0x180019631  mov     [rbx], rax
0x180019634  lea     r15, [rbx+10h]
0x180019638  mov     rcx, r15
0x18001963b  call    ??$_Construct_in_place@VSharedMemoryCache@Utility@@$$V@std@@YAXAEAVSharedMemoryCache@Utility@@@Z; std::_Construct_in_place<Utility::SharedMemoryCache,>(Utility::SharedMemoryCache &)
0x180019640  nop
0x180019641  lea     r14, [rdi+80h]
0x180019648  mov     [r14], r15
0x18001964b  mov     rcx, [r14+8]; this
0x18001964f  mov     [r14+8], rbx
0x180019653  test    rcx, rcx
0x180019656  jz      short loc_18001965D
0x180019658  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001965d  mov     rcx, [r14]; lpCriticalSection
0x180019660  call    ?setMaximumSize@SharedMemoryCache@Utility@@QEAAX_K@Z; Utility::SharedMemoryCache::setMaximumSize(unsigned __int64)
0x180019665  lea     rbx, [rdi+78h]
0x180019669  mov     rcx, rbx
0x18001966c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019671  mov     rcx, rbx
0x180019674  call    cs:__imp_ConfigurationManager_Create
0x18001967a  test    eax, eax
0x18001967c  jns     loc_180019704
0x180019682  mov     r9, rdi
0x180019685  mov     r8d, 79h ; 'y'
0x18001968b  lea     rdx, aMapsstoremanag_15; "MapsStoreManager::Initialize"
0x180019692  mov     ecx, eax
0x180019694  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001969a  mov     r13d, eax
0x18001969d  lea     rcx, [rsp+228h+var_168]
0x1800196a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196aa  nop
0x1800196ab  lea     rcx, [rsp+228h+var_148]
0x1800196b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196b8  nop
0x1800196b9  lea     rcx, [rsp+228h+var_128]
0x1800196c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196c6  nop
0x1800196c7  lea     rcx, [rsp+228h+var_108]
0x1800196cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196d4  nop
0x1800196d5  lea     rcx, [rsp+228h+var_E8]
0x1800196dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196e2  nop
0x1800196e3  lea     rcx, [rsp+228h+var_C8]
0x1800196eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196f0  nop
0x1800196f1  lea     rcx, [rsp+228h+var_A8]
0x1800196f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196fe  nop
0x1800196ff  jmp     loc_180019DF2
0x180019704  mov     rax, [rbx]
0x180019707  mov     rbx, [rax+20h]
0x18001970b  mov     [rsp+228h+var_1A8], rbx
0x180019713  lea     rdx, [rsp+228h+var_168]
0x18001971b  lea     rcx, [rsp+228h+var_148]
0x180019723  call    ?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapPlatformConfig::GetSystemLocaleInfo(std::wstring *,std::wstring *)
0x180019728  test    eax, eax
0x18001972a  jns     loc_1800197B2
0x180019730  mov     r9, rdi
0x180019733  mov     r8d, 7Dh ; '}'
0x180019739  lea     rdx, aMapsstoremanag_15; "MapsStoreManager::Initialize"
0x180019740  mov     ecx, eax
0x180019742  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180019748  mov     r13d, eax
0x18001974b  lea     rcx, [rsp+228h+var_168]
0x180019753  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019758  nop
0x180019759  lea     rcx, [rsp+228h+var_148]
0x180019761  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019766  nop
0x180019767  lea     rcx, [rsp+228h+var_128]
0x18001976f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019774  nop
0x180019775  lea     rcx, [rsp+228h+var_108]
0x18001977d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019782  nop
0x180019783  lea     rcx, [rsp+228h+var_E8]
0x18001978b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019790  nop
0x180019791  lea     rcx, [rsp+228h+var_C8]
0x180019799  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001979e  nop
0x18001979f  lea     rcx, [rsp+228h+var_A8]
0x1800197a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800197ac  nop
0x1800197ad  jmp     loc_180019DF2
0x1800197b2  lea     rcx, [rsp+228h+var_168]
0x1800197ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800197bf  mov     rdx, rax
0x1800197c2  lea     rcx, [rsp+228h+var_68]
0x1800197ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800197cf  nop
0x1800197d0  lea     rcx, [rsp+228h+var_148]
0x1800197d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800197dd  mov     rdx, rax
0x1800197e0  lea     rcx, [rsp+228h+var_88]
0x1800197e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800197ed  nop
0x1800197ee  lea     r9, [rsp+228h+var_68]
0x1800197f6  lea     r8, [rsp+228h+var_88]
0x1800197fe  lea     rdx, [rsp+228h+var_178]
0x180019806  mov     rcx, rbx; this
0x180019809  call    ?getConfiguration@ConfigurationManager@MapControl@@QEAA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapControl::ConfigurationManager::getConfiguration(std::wstring const &,std::wstring const &)
0x18001980e  mov     rdx, rax
0x180019811  lea     rcx, [rsp+228h+var_1A0]
0x180019819  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x18001981e  nop
0x18001981f  lea     rcx, [rsp+228h+var_178]
0x180019827  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18001982c  nop
0x18001982d  lea     rcx, [rsp+228h+var_88]
0x180019835  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001983a  nop
0x18001983b  lea     rcx, [rsp+228h+var_68]
0x180019843  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019848  mov     rax, [rsp+228h+var_1A0]
0x180019850  test    rax, rax
0x180019853  jnz     loc_1800198F1
0x180019859  mov     r9, rdi
0x18001985c  mov     r8d, 80h
0x180019862  lea     rdx, aMapsstoremanag_15; "MapsStoreManager::Initialize"
0x180019869  mov     ecx, 80004005h
0x18001986e  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180019874  mov     r13d, eax
0x180019877  mov     rcx, [rsp+228h+var_198]; this
0x18001987f  test    rcx, rcx
0x180019882  jz      short loc_18001988A
0x180019884  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019889  nop
0x18001988a  lea     rcx, [rsp+228h+var_168]
0x180019892  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019897  nop
0x180019898  lea     rcx, [rsp+228h+var_148]
0x1800198a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198a5  nop
0x1800198a6  lea     rcx, [rsp+228h+var_128]
0x1800198ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198b3  nop
0x1800198b4  lea     rcx, [rsp+228h+var_108]
0x1800198bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198c1  nop
0x1800198c2  lea     rcx, [rsp+228h+var_E8]
0x1800198ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198cf  nop
0x1800198d0  lea     rcx, [rsp+228h+var_C8]
0x1800198d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198dd  nop
0x1800198de  lea     rcx, [rsp+228h+var_A8]
0x1800198e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198eb  nop
0x1800198ec  jmp     loc_180019DF2
0x1800198f1  mov     [rsp+228h+var_190], 0
0x1800198fd  mov     [rsp+228h+var_1B0], 3E800h
0x180019905  lea     rdx, [rsp+228h+var_190]; unsigned __int64 *
0x18001990d  mov     rcx, rax; this
0x180019910  call    ?getPersistentCacheSizeInBytes@LocaleMapConfiguration@MapControl@@QEBAXPEA_K@Z; MapControl::LocaleMapConfiguration::getPersistentCacheSizeInBytes(unsigned __int64 *)
0x180019915  lea     rcx, [rdi+50h]
0x180019919  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001991e  mov     [rsp+228h+var_1C0], rax
0x180019923  mov     dword ptr [rsp+228h+var_1E8], 4
0x18001992b  mov     ecx, 1E0h; Size
0x180019930  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019935  mov     rbx, rax
0x180019938  mov     [rsp+228h+var_1D8], rax
0x18001993d  mov     [rax+8], esi
0x180019940  mov     [rax+0Ch], esi
0x180019943  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@pplx@@@std@@6B@; const std::_Ref_count_obj2<pplx::details::_Task_impl<uchar>>::`vftable'
0x18001994a  mov     [rbx], rax
0x18001994d  lea     r15, [rbx+10h]
0x180019951  lea     rax, [rsp+228h+var_190]
0x180019959  mov     [rsp+228h+var_200], rax
0x18001995e  lea     rax, [rsp+228h+var_1B0]
0x180019963  mov     [rsp+228h+var_208], rax
0x180019968  mov     r9, r14
0x18001996b  lea     r8, [rsp+228h+var_1C0]
0x180019970  lea     rdx, [rsp+228h+var_1E8]
0x180019975  mov     rcx, r15
0x180019978  call    ??$_Construct_in_place@VPersistentMapsCache@MapControl@@W4FileLocation@Pal@@PEBGAEAV?$shared_ptr@VSharedMemoryCache@Utility@@@std@@AEAIAEA_K@std@@YAXAEAVPersistentMapsCache@MapControl@@$$QEAW4FileLocation@Pal@@$$QEAPEBGAEAV?$shared_ptr@VSharedMemoryCache@Utility@@@0@AEAIAEA_K@Z; std::_Construct_in_place<MapControl::PersistentMapsCache,Pal::FileLocation,ushort const *,std::shared_ptr<Utility::SharedMemoryCache> &,uint &,unsigned __int64 &>(MapControl::PersistentMapsCache &,Pal::FileLocation &&,ushort const * &&,std::shared_ptr<Utility::SharedMemoryCache> &,uint &,unsigned __int64 &)
0x18001997d  nop
0x18001997e  lea     r12, [rdi+150h]
0x180019985  mov     [r12], r15
0x180019989  mov     rcx, [r12+8]; this
0x18001998e  mov     [r12+8], rbx
0x180019993  test    rcx, rcx
0x180019996  jz      short loc_18001999D
0x180019998  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001999d  mov     rcx, [r12]
0x1800199a1  mov     rax, [rcx]
0x1800199a4  xor     r8d, r8d
0x1800199a7  lea     rdx, [rsp+228h+var_1C8]
0x1800199ac  mov     rax, [rax+58h]
  ... truncated ...
```
