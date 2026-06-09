# Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded(Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId const &,bool,Windows::Internal::Storage::Cloud::Core::CorrelationVector const &)

- ea: `0x180033620`
- end: `0x180033fe1`
- name: `?TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@6@AEBVCloudStoreCollectionId@23456@_NAEBVCorrelationVector@23456@@Z`
- size: `2497`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `61`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001159c`
- `0x180037500`
- `0x180099540`
- `0x1800d7958`
- `0x1800d825c`
- `0x1800ec270`
- `0x18018c5c0`
- `0x18018d7d0`
- `0x18018fd10`

## callees

- `0x180011e18`
- `0x180016290`
- `0x180016a78`
- `0x180016cf4`
- `0x180019080`
- `0x180019720`
- `0x18001c2dc`
- `0x18001c6c4`
- `0x1800219e0`
- `0x1800233f0`
- `0x1800238d0`
- `0x180023fd4`
- `0x1800250e0`
- `0x180025508`
- `0x18002e010`
- `0x180033620`
- `0x18003409c`
- `0x1800347b0`
- `0x1800348dc`
- `0x180034ac4`
- `0x180034e20`
- `0x18003533c`
- `0x1800366d8`
- `0x18003727c`
- `0x180037500`
- `0x18003f364`
- `0x180047904`
- `0x180051090`
- `0x18005274c`
- `0x180054540`
- `0x180054714`
- `0x18005edd0`
- `0x18005f060`
- `0x18009a718`
- `0x18009aafc`
- `0x18009f828`
- `0x1800a62f0`
- `0x1800c2398`
- `0x1800c27dc`
- `0x1800d40f0`
- `0x1800d6e40`
- `0x1800e54a4`
- `0x1800e5508`
- `0x1800e915c`
- `0x1800e93e0`
- `0x180118504`
- `0x18011a088`
- `0x1801201a0`
- `0x180120668`
- `0x18012353c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a17`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003387e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003387e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180033fcf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180033fcf`

## string_xrefs

- `0x180033a02`: `LastProfileWriteSuccessTime`
- `0x180033bab`: `LastProfileWriteSuccessTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded(
        Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl *a1,
        __int64 a2,
        _QWORD *a3,
        unsigned __int8 a4,
        __int64 a5)
{
  int v5; // r12d
  char v9; // bl
  char v10; // r15
  _QWORD *v11; // r13
  char IsPerDeviceOnly; // al
  unsigned __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  void **v16; // rsi
  __int64 v17; // rax
  __int64 v19; // r14
  void *v20; // rax
  __int64 v21; // rax
  CloudStoreUtilities::StorageTestHook *v22; // rcx
  bool IsEnabled; // al
  const char *v24; // rdx
  const struct Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId *v25; // rax
  LSTATUS ValueW; // eax
  unsigned __int64 v27; // r9
  const struct Windows::Data::Platform::BackupRestore::DeviceProfile *v28; // rax
  unsigned __int64 NextVersion; // rbx
  __int64 *v30; // rax
  __int64 v31; // r8
  _QWORD *v32; // rdx
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rcx
  char v39; // al
  _QWORD *v40; // rbx
  unsigned __int64 CurrentTimeAsInt64; // rsi
  __int64 v42; // rax
  __int64 v43; // rax
  char v44; // al
  __int64 v45; // rax
  __int64 v46; // rax
  HKEY v47; // rcx
  unsigned int v48; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  char v53; // [rsp+40h] [rbp-C0h]
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 pvData; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v56[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v57; // [rsp+70h] [rbp-90h]
  __int64 v58[10]; // [rsp+80h] [rbp-80h] BYREF
  void *v59[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v60; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v61; // [rsp+E8h] [rbp-18h]
  _BYTE v62[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v63; // [rsp+F8h] [rbp-8h]
  _QWORD *v64; // [rsp+100h] [rbp+0h]
  char v65[64]; // [rsp+110h] [rbp+10h] BYREF
  char Source[132]; // [rsp+150h] [rbp+50h] BYREF
  int v67; // [rsp+1D4h] [rbp+D4h]
  __m128i v68[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v69[12]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v70[8]; // [rsp+280h] [rbp+180h] BYREF
  int v71[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v72[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v73[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int64 v74; // [rsp+320h] [rbp+220h]
  int v75[4]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v76[16]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v77[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v78[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v79[40]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int64 v80; // [rsp+3E8h] [rbp+2E8h]
  _BYTE v81[32]; // [rsp+400h] [rbp+300h] BYREF
  int v82[4]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v83[136]; // [rsp+430h] [rbp+330h] BYREF
  int v84; // [rsp+4B8h] [rbp+3B8h]
  Windows::Internal::Storage::Cloud *retaddr; // [rsp+518h] [rbp+418h]

  v5 = a4;
  v56[0] = a2;
  v9 = 0;
  v57 = 0;
  if ( __TSS0__1__TryUpdatePartitionMetadataIfNeeded_CloudStoreCoreImpl_Core_Cloud_Storage_Internal_Windows__AEAA_AUPartition_Partitioning_Platform_Data_7_AEBVCloudStoreCollectionId_34567__NAEBVCorrelationVector_34567__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 268LL) )
  {
    Init_thread_header(&__TSS0__1__TryUpdatePartitionMetadataIfNeeded_CloudStoreCoreImpl_Core_Cloud_Storage_Internal_Windows__AEAA_AUPartition_Partitioning_Platform_Data_7_AEBVCloudStoreCollectionId_34567__NAEBVCorrelationVector_34567__Z_4HA);
    if ( __TSS0__1__TryUpdatePartitionMetadataIfNeeded_CloudStoreCoreImpl_Core_Cloud_Storage_Internal_Windows__AEAA_AUPartition_Partitioning_Platform_Data_7_AEBVCloudStoreCollectionId_34567__NAEBVCorrelationVector_34567__Z_4HA == -1 )
    {
      Windows::Data::Platform::Partitioning::Partition::Partition((Windows::Data::Platform::Partitioning::Partition *)&`Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded'::`2'::s_emptyPartition);
      atexit(`Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded'::`2'::`dynamic atexit destructor for 's_emptyPartition'');
      Init_thread_footer(&__TSS0__1__TryUpdatePartitionMetadataIfNeeded_CloudStoreCoreImpl_Core_Cloud_Storage_Internal_Windows__AEAA_AUPartition_Partitioning_Platform_Data_7_AEBVCloudStoreCollectionId_34567__NAEBVCorrelationVector_34567__Z_4HA);
    }
  }
  if ( (*((_BYTE *)a1 + 40) & 2) != 0 )
  {
    Windows::Data::Platform::Partitioning::Partition::Partition(
      (Windows::Data::Platform::Partitioning::Partition *)a2,
      (const struct Windows::Data::Platform::Partitioning::Partition *)&`Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded'::`2'::s_emptyPartition);
    return a2;
  }
  Windows::Internal::Storage::Cloud::Core::CorrelationVector::Extend(a5, Source);
  v10 = 0;
  if ( !a3[2] )
    goto LABEL_10;
  v11 = a3 + 4;
  IsPerDeviceOnly = Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::IsPerDeviceOnly(a1, a3 + 4);
  v53 = IsPerDeviceOnly;
  if ( (_BYTE)v5 && IsPerDeviceOnly )
  {
    v21 = Utf8StringToWideString(v59);
    v9 = 2;
    v57 = 2;
    if ( *(_QWORD *)(v21 + 24) > 7u )
      v21 = *(_QWORD *)v21;
    if ( CompareStringOrdinal(L"windows.data.platform.backuprestore.deviceprofile", -1, (LPCWCH)v21, -1, 1) != 2
      && UseCloudStoreOnActivityFeed::IsBackupRestoreEnabled() )
    {
      v10 = 1;
    }
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    v13 = v61;
    if ( v61 > 7 )
      std::_Deallocate<16>(v59[0], (const struct std::nothrow_t *)(2 * v61 + 2));
  }
  if ( v10 )
  {
    LOBYTE(v14) = 3;
    LOBYTE(v13) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::GetImpl'::`2'::impl,
      v13,
      v14);
    IsEnabled = CloudStoreUtilities::StorageTestHook::IsEnabled(v22);
    v24 = "TestDeviceProfiles";
    if ( !IsEnabled )
      v24 = "DeviceProfiles";
    std::string::string(v65, v24);
    std::string::string(v62, byte_1802299F5);
    v25 = (const struct Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId *)Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId::CloudStoreCollectionId((Windows::Internal::Storage::Cloud::Core *)v82);
    Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::CloudStoreItemId(v68, v25, &qword_18029AD00, a3);
    Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId::~CloudStoreCollectionId((Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId *)v82);
    std::string::_Tidy_deallocate(v62);
    std::string::_Tidy_deallocate(v65);
    ++v67;
    Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::Load(
      (__int64)a1,
      (__int64)v71,
      (__int64)v68,
      0,
      (__int64)Source);
    tombstoned<deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>>::tombstoned<deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>>(
      v59,
      v73);
    v61 = v74;
    if ( !v74 || v60 )
    {
      v48 = v74 != 0 ? 0xFFFFFFF7 : 0;
      if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
      {
        v30 = (__int64 *)Windows::Internal::Storage::Cloud::Core::CorrelationVector::ToString(Source, v65);
        v31 = (__int64)v30;
        v9 |= 4u;
        if ( (unsigned __int64)v30[3] > 0xF )
          v31 = *v30;
        v32 = a3 + 12;
        if ( a3[15] > 0xFu )
          v32 = (_QWORD *)*v32;
        v33 = v70;
        if ( v70[3] > 0xFu )
          v33 = (_QWORD *)v70[0];
        v34 = v69;
        if ( v69[3] > 0xFu )
          v34 = (_QWORD *)v69[0];
        McTemplateU0dtssss_EventWriteTransfer(
          (_DWORD)v33,
          (_DWORD)v32,
          v48 - 2147217391,
          v5,
          (__int64)v34,
          (__int64)v33,
          (__int64)v32,
          v31);
      }
      if ( (v9 & 4) != 0 )
        std::string::_Tidy_deallocate(v65);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13EC,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
        (const char *)(v48 - 2147217391),
        bIgnoreCase);
    }
    pvData = 0;
    pcbData[0] = 8;
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SystemMetaData",
               L"LastProfileWriteSuccessTime",
               0x40u,
               0,
               &pvData,
               pcbData);
    v27 = (unsigned int)ValueW;
    if ( ValueW > 0 )
      v27 = (unsigned __int16)ValueW | 0x80070000;
    if ( (v27 & 0x80000000) != 0LL )
    {
      pvData = 0;
      if ( (unsigned int)(v27 + 2147024894) <= 1 || (v44 = 1, (_DWORD)v27 == -2147023728) )
        v44 = 0;
      if ( v44 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x13FF,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
          (const char *)v27,
          bIgnoreCasea);
    }
    v28 = (const struct Windows::Data::Platform::BackupRestore::DeviceProfile *)deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>::deserialized(v59);
    Windows::Data::Platform::BackupRestore::DeviceProfile::DeviceProfile(
      (Windows::Data::Platform::BackupRestore::DeviceProfile *)v75,
      v28);
    NextVersion = Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::GetNextVersion(a1, 0);
    if ( (__int64)(10000000 * (pvData + 86400)) / 8388609 + 10000000 * (pvData + 86400) < NextVersion )
    {
      v80 = NextVersion;
      Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::BuildOsVersionString(pcbData);
      std::wstring::assign(v81, *(_QWORD *)pcbData);
      deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>::deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>(
        v62,
        v75);
      v45 = deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>::serialized(v62);
      v46 = tombstoned<schematized_data>::tombstoned<schematized_data>(v65, v45, 0);
      versioned<tombstoned<schematized_data>>::versioned<tombstoned<schematized_data>>(v58, v46);
      schematized_data::~schematized_data((schematized_data *)v65);
      ++v67;
      Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::Save(
        (int)a1,
        (int)v82,
        (int)v68,
        (int)v71,
        (__int64)v58,
        0,
        Source);
      if ( v84 == 1 )
      {
        pvData = NextVersion;
        v35 = SHRegSetQWORD(
                v47,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SystemMetaData",
                L"LastProfileWriteSuccessTime",
                NextVersion);
        if ( v35 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x142F,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
            (const char *)(unsigned int)v35,
            bIgnoreCasec);
      }
      Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v83);
      schematized_data::~schematized_data((schematized_data *)v58);
      if ( v63 )
        std::_Ref_count_base::_Decref(v63);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pcbData);
    }
    std::wstring::~wstring(v81);
    std::wstring::~wstring(v79);
    std::wstring::~wstring(v78);
    std::wstring::~wstring(v77);
    std::wstring::~wstring(v75);
    std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(v59);
    Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v72);
    Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId((Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *)v68);
    goto LABEL_10;
  }
  if ( v53 )
  {
LABEL_10:
    *(_DWORD *)a2 = `Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded'::`2'::s_emptyPartition;
    *(_DWORD *)(a2 + 4) = dword_1802A1F74;
    *(_QWORD *)(a2 + 8) = qword_1802A1F78;
    *(_QWORD *)(a2 + 16) = qword_1802A1F80;
    *(_QWORD *)(a2 + 24) = qword_1802A1F88;
    *(_OWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 56) = 0;
    v15 = qword_1802A1FA0;
    v16 = &qword_1802A1F90;
    if ( (unsigned __int64)qword_1802A1FA8 > 7 )
      v16 = (void **)qword_1802A1F90;
    if ( (unsigned __int64)qword_1802A1FA0 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( (unsigned __int64)qword_1802A1FA0 > 7 )
    {
      v19 = std::wstring::_Calculate_growth(qword_1802A1FA0);
      if ( (unsigned __int64)(v19 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v20 = std::_Allocate<16,std::_Default_allocate_traits>(2 * (v19 + 1));
      *(_QWORD *)(a2 + 32) = v20;
      *(_QWORD *)(a2 + 48) = v15;
      *(_QWORD *)(a2 + 56) = v19;
      memcpy_0(v20, v16, 2 * v15 + 2);
    }
    else
    {
      *(_QWORD *)(a2 + 48) = qword_1802A1FA0;
      *(_QWORD *)(a2 + 56) = 7;
      *(_OWORD *)(a2 + 32) = *(_OWORD *)v16;
    }
    *(_DWORD *)(a2 + 64) = dword_1802A1FB0;
    if ( qword_1802A1FB8 )
      v17 = bond::nullable<Windows::Data::Platform::Partitioning::DeviceExperiencePartition,void>::new_value<Windows::Data::Platform::Partitioning::DeviceExperiencePartition const &>();
    else
      v17 = 0;
    *(_QWORD *)(a2 + 72) = v17;
    return a2;
  }
  GetItemIdOfType_Windows::Data::Platform::Partitioning::PartitionIndex_((Windows::Internal::Storage::Cloud::Core *)v68);
  ++v67;
  Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::Load(
    (__int64)a1,
    (__int64)v71,
    (__int64)v68,
    1u,
    (__int64)Source);
  versioned<tombstoned<deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>>>::versioned<tombstoned<deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>>>(
    v59,
    v73);
  if ( !v61 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x145B,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
      (const char *)0x80041011LL,
      bIgnoreCaseb);
  if ( v60 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x145C,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
      (const char *)0x80041008LL,
      bIgnoreCaseb);
  v36 = deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>::deserialized(v59);
  std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::Platform::Partitioning::Partition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::Platform::Partitioning::Partition>>,0>>::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::Platform::Partitioning::Partition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::Platform::Partitioning::Partition>>,0>>(
    v56,
    v36);
  v37 = Utf8StringToWideString(v65);
  std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::Platform::Partitioning::Partition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::Platform::Partitioning::Partition>>,0>>::_Find_lower_bound<std::wstring>(
    v56,
    v62,
    v37);
  v39 = std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>,std::shared_ptr<versioned<tombstoned<schematized_data>>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreItemId>,std::shared_ptr<versioned<tombstoned<schematized_data>>>>>>,0>>::_Lower_bound_duplicate<std::wstring>(
          v38,
          v64,
          v37);
  v40 = (_QWORD *)v56[0];
  if ( v39 )
    v40 = v64;
  std::wstring::~wstring(v65);
  if ( v40 == (_QWORD *)v56[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1460,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorecore.cpp",
      (const char *)0x8000000BLL,
      bIgnoreCaseb);
  CurrentTimeAsInt64 = Windows::Internal::Storage::Cloud::GetCurrentTimeAsInt64(retaddr);
  if ( v40[11] + 864000000000LL < CurrentTimeAsInt64
    || (_BYTE)v5 && !(unsigned __int8)Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::IsLocalOnly(a1, v11) )
  {
    v40[11] = CurrentTimeAsInt64;
    if ( (_BYTE)v5 )
      v40[10] = CurrentTimeAsInt64;
    Windows::Data::Platform::Partitioning::Partition::Partition(
      (Windows::Data::Platform::Partitioning::Partition *)v82,
      (const struct Windows::Data::Platform::Partitioning::Partition *)(v40 + 8));
    deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>::deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>(
      v62,
      v56);
    v42 = deserializable_data<Windows::Data::Platform::Partitioning::PartitionIndex>::serialized(v62);
    v43 = tombstoned<schematized_data>::tombstoned<schematized_data>(v65, v42, 0);
    versioned<tombstoned<schematized_data>>::versioned<tombstoned<schematized_data>>(v58, v43);
    schematized_data::~schematized_data((schematized_data *)v65);
    ++v67;
    Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::Save(
      (int)a1,
      (int)v75,
      (int)v68,
      (int)v71,
      (__int64)v58,
      0,
      Source);
    Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v76);
    Windows::Data::Platform::Partitioning::Partition::Partition(a2, v82);
    schematized_data::~schematized_data((schematized_data *)v58);
    if ( v63 )
      std::_Ref_count_base::_Decref(v63);
    Windows::Data::Platform::Partitioning::Partition::~Partition((Windows::Data::Platform::Partitioning::Partition *)v82);
  }
  else
  {
    Windows::Data::Platform::Partitioning::Partition::Partition(
      (Windows::Data::Platform::Partitioning::Partition *)a2,
      (const struct Windows::Data::Platform::Partitioning::Partition *)(v40 + 8));
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Windows::Data::Platform::Partitioning::Partition>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::Platform::Partitioning::Partition>,void *>>>(
    v56,
    v56);
  std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(v59);
  Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v72);
  Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId((Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *)v68);
  return a2;
}

```

## disassembly

```asm
0x180033620  push    rbp
0x180033622  push    rbx
0x180033623  push    rsi
0x180033624  push    rdi
0x180033625  push    r12
0x180033627  push    r13
0x180033629  push    r14
0x18003362b  push    r15
0x18003362d  lea     rbp, [rsp-3D8h]
0x180033635  sub     rsp, 4D8h
0x18003363c  mov     rax, cs:__security_cookie
0x180033643  xor     rax, rsp
0x180033646  mov     [rbp+410h+var_50], rax
0x18003364d  movzx   r12d, r9b
0x180033651  mov     rsi, r8
0x180033654  mov     rdi, rdx
0x180033657  mov     r14, rcx
0x18003365a  mov     [rsp+510h+var_4B0], rdx
0x18003365f  mov     r15, [rbp+410h+arg_20]
0x180033666  xor     ebx, ebx
0x180033668  mov     [rsp+510h+var_4A0], ebx
0x18003366c  mov     ecx, cs:_tls_index
0x180033672  mov     rax, gs:58h
0x18003367b  mov     edx, 10Ch
0x180033680  mov     rax, [rax+rcx*8]
0x180033684  mov     eax, [rdx+rax]
0x180033687  cmp     cs:?$TSS0@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4HA, eax
0x18003368d  jg      loc_1800338A1
0x180033693  test    byte ptr [r14+28h], 2
0x180033698  jnz     loc_1800337DA
0x18003369e  lea     rdx, [rbp+410h+Source]
0x1800336a2  mov     rcx, r15
0x1800336a5  call    ?Extend@CorrelationVector@Core@Cloud@Storage@Internal@Windows@@QEBA?AV123456@XZ; Windows::Internal::Storage::Cloud::Core::CorrelationVector::Extend(void)
0x1800336aa  xor     r15d, r15d
0x1800336ad  cmp     [rsi+10h], r15
0x1800336b1  jz      short loc_180033709
0x1800336b3  lea     r13, [rsi+20h]
0x1800336b7  mov     rdx, r13
0x1800336ba  mov     rcx, r14
0x1800336bd  call    ?IsPerDeviceOnly@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::IsPerDeviceOnly(std::string const &)
0x1800336c2  mov     [rsp+510h+var_4D0], al
0x1800336c6  test    r12b, r12b
0x1800336c9  jnz     loc_18003383E
0x1800336cf  test    bl, 2
0x1800336d2  jz      short loc_1800336F2
0x1800336d4  and     ebx, 0FFFFFFFDh
0x1800336d7  mov     rdx, [rbp+410h+var_428]
0x1800336db  cmp     rdx, 7
0x1800336df  jbe     short loc_1800336F2
0x1800336e1  lea     rdx, ds:2[rdx*2]
0x1800336e9  mov     rcx, [rbp+410h+var_440]
0x1800336ed  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800336f2  test    r15b, r15b
0x1800336f5  jnz     loc_1800338E3
0x1800336fb  xor     r15d, r15d
0x1800336fe  cmp     [rsp+510h+var_4D0], r15b
0x180033703  jz      loc_180033C02
0x180033709  mov     eax, cs:?s_emptyPartition@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4U89Platform@Data@7@A; Windows::Data::Platform::Partitioning::Partition `Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::TryUpdatePartitionMetadataIfNeeded(Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId const &,bool,Windows::Internal::Storage::Cloud::Core::CorrelationVector const &)'::`2'::s_emptyPartition
0x18003370f  mov     [rdi], eax
0x180033711  mov     eax, cs:dword_1802A1F74
0x180033717  mov     [rdi+4], eax
0x18003371a  mov     rax, cs:qword_1802A1F78
0x180033721  mov     [rdi+8], rax
0x180033725  mov     rax, cs:qword_1802A1F80
0x18003372c  mov     [rdi+10h], rax
0x180033730  mov     rax, cs:qword_1802A1F88
0x180033737  mov     [rdi+18h], rax
0x18003373b  xorps   xmm0, xmm0
0x18003373e  movups  xmmword ptr [rdi+20h], xmm0
0x180033742  mov     [rdi+30h], r15
0x180033746  mov     [rdi+38h], r15
0x18003374a  mov     rbx, cs:qword_1802A1FA0
0x180033751  lea     rsi, qword_1802A1F90
0x180033758  mov     eax, 7
0x18003375d  cmp     cs:qword_1802A1FA8, rax
0x180033764  cmova   rsi, cs:qword_1802A1F90
0x18003376c  mov     r8, 7FFFFFFFFFFFFFFEh
0x180033776  cmp     rbx, r8
0x180033779  ja      loc_180033FC8
0x18003377f  cmp     rbx, rax
0x180033782  ja      short loc_1800337EB
0x180033784  mov     [rdi+30h], rbx
0x180033788  mov     [rdi+38h], rax
0x18003378c  movups  xmm0, xmmword ptr [rsi]
0x18003378f  movdqu  xmmword ptr [rdi+20h], xmm0
0x180033794  mov     eax, cs:dword_1802A1FB0
0x18003379a  mov     [rdi+40h], eax
0x18003379d  mov     rdx, cs:qword_1802A1FB8
0x1800337a4  test    rdx, rdx
0x1800337a7  jnz     loc_180033FD6
0x1800337ad  mov     rax, r15
0x1800337b0  mov     [rdi+48h], rax
0x1800337b4  mov     rax, rdi
0x1800337b7  mov     rcx, [rbp+410h+var_50]
0x1800337be  xor     rcx, rsp; StackCookie
0x1800337c1  call    __security_check_cookie
0x1800337c6  add     rsp, 4D8h
0x1800337cd  pop     r15
0x1800337cf  pop     r14
0x1800337d1  pop     r13
0x1800337d3  pop     r12
0x1800337d5  pop     rdi
0x1800337d6  pop     rsi
0x1800337d7  pop     rbx
0x1800337d8  pop     rbp
0x1800337d9  retn
0x1800337da  lea     rdx, ?s_emptyPartition@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4U89Platform@Data@7@A; struct Windows::Data::Platform::Partitioning::Partition *
0x1800337e1  mov     rcx, rdi; this
0x1800337e4  call    ??0Partition@Partitioning@Platform@Data@Windows@@QEAA@AEBU01234@@Z; Windows::Data::Platform::Partitioning::Partition::Partition(Windows::Data::Platform::Partitioning::Partition const &)
0x1800337e9  jmp     short loc_1800337B4
0x1800337eb  mov     rdx, rax
0x1800337ee  mov     rcx, rbx
0x1800337f1  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800337f6  mov     r14, rax
0x1800337f9  lea     rcx, [rax+1]
0x1800337fd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180033807  cmp     rcx, rax
0x18003380a  jbe     short loc_180033812
0x18003380c  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180033812  add     rcx, rcx
0x180033815  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003381a  mov     [rdi+20h], rax
0x18003381e  mov     [rdi+30h], rbx
0x180033822  mov     [rdi+38h], r14
0x180033826  lea     r8, ds:2[rbx*2]; Size
0x18003382e  mov     rdx, rsi; Src
0x180033831  mov     rcx, rax; void *
0x180033834  call    memcpy_0
0x180033839  jmp     loc_180033794
0x18003383e  test    al, al
0x180033840  jz      loc_1800336CF
0x180033846  mov     rdx, r13
0x180033849  lea     rcx, [rbp+410h+var_440]
0x18003384d  call    ?Utf8StringToWideString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8StringToWideString(std::string const &)
0x180033852  nop
0x180033853  mov     ebx, 2
0x180033858  mov     [rsp+510h+var_4A0], ebx
0x18003385c  cmp     qword ptr [rax+18h], 7
0x180033861  jbe     short loc_180033866
0x180033863  mov     rax, [rax]
0x180033866  mov     [rsp+510h+bIgnoreCase], 1; bIgnoreCase
0x18003386e  or      edx, 0FFFFFFFFh; cchCount1
0x180033871  mov     r9d, edx; cchCount2
0x180033874  mov     r8, rax; lpString2
0x180033877  lea     rcx, aWindowsDataPla_22; "windows.data.platform.backuprestore.dev"...
0x18003387e  call    cs:__imp_CompareStringOrdinal
0x180033884  cmp     eax, ebx
0x180033886  jz      loc_1800336CF
0x18003388c  call    ?IsBackupRestoreEnabled@UseCloudStoreOnActivityFeed@@SA_NXZ; UseCloudStoreOnActivityFeed::IsBackupRestoreEnabled(void)
0x180033891  test    al, al
0x180033893  jz      loc_1800336CF
0x180033899  mov     r15b, 1
0x18003389c  jmp     loc_1800336CF
0x1800338a1  lea     rcx, ?$TSS0@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4HA
0x1800338a8  call    _Init_thread_header
0x1800338ad  cmp     cs:?$TSS0@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4HA, 0FFFFFFFFh
0x1800338b4  jnz     loc_180033693
0x1800338ba  lea     rcx, ?s_emptyPartition@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4U89Platform@Data@7@A; this
0x1800338c1  call    ??0Partition@Partitioning@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::Partitioning::Partition::Partition(void)
0x1800338c6  lea     rcx, ??__Fs_emptyPartition@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@6@AEBVCloudStoreCollectionId@23456@_NAEBVCorrelationVector@23456@@Z@YAXXZ; void (__cdecl *)()
0x1800338cd  call    atexit
0x1800338d2  lea     rcx, ?$TSS0@?1??TryUpdatePartitionMetadataIfNeeded@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@AEAA?AUPartition@Partitioning@Platform@Data@7@AEBVCloudStoreCollectionId@34567@_NAEBVCorrelationVector@34567@@Z@4HA
0x1800338d9  call    _Init_thread_footer
0x1800338de  jmp     loc_180033693
0x1800338e3  mov     r8b, 3
0x1800338e6  mov     dl, 1
0x1800338e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore> `wil::Feature<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::GetImpl(void)'::`2'::impl
0x1800338ef  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800338f4  call    ?IsEnabled@StorageTestHook@CloudStoreUtilities@@YA_NXZ; CloudStoreUtilities::StorageTestHook::IsEnabled(void)
0x1800338f9  lea     rcx, aDeviceprofiles_0; "DeviceProfiles"
0x180033900  lea     rdx, aTestdeviceprof; "TestDeviceProfiles"
0x180033907  xor     r15d, r15d
0x18003390a  test    al, al
0x18003390c  cmovz   rdx, rcx
0x180033910  lea     rcx, [rbp+410h+var_400]
0x180033914  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180033919  nop
0x18003391a  lea     rdx, byte_1802299F5
0x180033921  lea     rcx, [rbp+410h+var_420]
0x180033925  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003392a  nop
0x18003392b  lea     r9, [rbp+410h+var_400]
0x18003392f  lea     r8, qword_18029AD00
0x180033936  lea     rdx, [rbp+410h+var_420]
0x18003393a  lea     rcx, [rbp+410h+var_F0]; this
0x180033941  call    ??0CloudStoreCollectionId@Core@Cloud@Storage@Internal@Windows@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId::CloudStoreCollectionId(std::string const &,std::string const &,std::string const &)
0x180033946  nop
0x180033947  mov     r9, rsi
0x18003394a  lea     r8, qword_18029AD00
0x180033951  mov     rdx, rax
0x180033954  lea     rcx, [rbp+410h+var_330]; this
0x18003395b  call    ??0CloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@QEAA@AEBVCloudStoreCollectionId@12345@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::CloudStoreItemId(Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId const &,std::string const &,std::string const &)
0x180033960  nop
0x180033961  lea     rcx, [rbp+410h+var_F0]; this
0x180033968  call    ??1CloudStoreCollectionId@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CloudStoreCollectionId::~CloudStoreCollectionId(void)
0x18003396d  nop
0x18003396e  lea     rcx, [rbp+410h+var_420]; void *
0x180033972  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033977  nop
0x180033978  lea     rcx, [rbp+410h+var_400]; void *
0x18003397c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033981  inc     [rbp+410h+var_33C]
0x180033987  lea     rax, [rbp+410h+Source]
0x18003398b  mov     qword ptr [rsp+510h+bIgnoreCase], rax; int
0x180033990  xor     r9d, r9d
0x180033993  lea     r8, [rbp+410h+var_330]
0x18003399a  lea     rdx, [rbp+410h+var_250]
0x1800339a1  mov     rcx, r14
0x1800339a4  call    ?Load@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@UEAA?AUEntry@CloudStoreCore@23456@AEBVCloudStoreItemId@23456@W4CloudStoreCoreLoadOptions@23456@AEBVCorrelationVector@23456@@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::Load(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,Windows::Internal::Storage::Cloud::Core::CloudStoreCoreLoadOptions,Windows::Internal::Storage::Cloud::Core::CorrelationVector const &)
0x1800339a9  nop
0x1800339aa  lea     rdx, [rbp+410h+var_230]
0x1800339b1  lea     rcx, [rbp+410h+var_440]
0x1800339b5  call    ??$?0Vschematized_data@@@?$tombstoned@V?$deserializable_data@UDeviceProfile@BackupRestore@Platform@Data@Windows@@@@@@QEAA@AEBV?$tombstoned@Vschematized_data@@@@@Z; tombstoned<deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>>::tombstoned<deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>>(tombstoned<schematized_data> const &)
0x1800339ba  mov     rax, [rbp+410h+var_1F0]
0x1800339c1  mov     [rbp+410h+var_428], rax
0x1800339c5  test    rax, rax
0x1800339c8  jz      loc_180033F27
0x1800339ce  cmp     [rbp+410h+var_430], r15b
0x1800339d2  jnz     loc_180033F27
0x1800339d8  mov     [rsp+510h+var_4C0], r15
0x1800339dd  mov     [rsp+510h+var_4C8], 8
0x1800339e5  lea     rax, [rsp+510h+var_4C8]
0x1800339ea  mov     [rsp+510h+pcbData], rax; pcbData
0x1800339ef  lea     rax, [rsp+510h+var_4C0]
0x1800339f4  mov     [rsp+510h+pvData], rax; pvData
0x1800339f9  mov     qword ptr [rsp+510h+bIgnoreCase], r15; int
0x1800339fe  lea     r9d, [r15+40h]; dwFlags
0x180033a02  lea     r8, aLastprofilewri; "LastProfileWriteSuccessTime"
0x180033a09  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180033a10  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180033a17  call    cs:__imp_RegGetValueW
0x180033a1d  mov     r9d, eax
0x180033a20  test    eax, eax
0x180033a22  jle     short loc_180033A2F
0x180033a24  movzx   r9d, ax
0x180033a28  or      r9d, 80070000h; char *
0x180033a2f  test    r9d, r9d
0x180033a32  js      loc_180033E35
0x180033a38  lea     rcx, [rbp+410h+var_440]
0x180033a3c  call    ?deserialized@?$deserializable_data@UDeviceProfile@BackupRestore@Platform@Data@Windows@@@@QEBAAEBUDeviceProfile@BackupRestore@Platform@Data@Windows@@XZ; deserializable_data<Windows::Data::Platform::BackupRestore::DeviceProfile>::deserialized(void)
0x180033a41  mov     rdx, rax; struct Windows::Data::Platform::BackupRestore::DeviceProfile *
0x180033a44  lea     rcx, [rbp+410h+var_1B0]; this
0x180033a4b  call    ??0DeviceProfile@BackupRestore@Platform@Data@Windows@@QEAA@AEBU01234@@Z; Windows::Data::Platform::BackupRestore::DeviceProfile::DeviceProfile(Windows::Data::Platform::BackupRestore::DeviceProfile const &)
0x180033a50  nop
0x180033a51  xor     edx, edx; __int64 *
0x180033a53  mov     rcx, r14; this
0x180033a56  call    ?GetNextVersion@CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@UEAA_KPEB_J@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::GetNextVersion(__int64 const *)
0x180033a5b  mov     rbx, rax
0x180033a5e  mov     rcx, [rsp+510h+var_4C0]
0x180033a63  add     rcx, 15180h
0x180033a6a  imul    r8, rcx, 989680h
0x180033a71  mov     rax, 0D6BF94D5E57A42BDh
0x180033a7b  imul    r8
0x180033a7e  add     rdx, r8
0x180033a81  sar     rdx, 17h
0x180033a85  mov     rcx, rdx
0x180033a88  shr     rcx, 3Fh
0x180033a8c  add     rdx, rcx
0x180033a8f  cmp     rdx, rbx
0x180033a92  jb      loc_180033E5D
0x180033a98  lea     rcx, [rbp+410h+var_110]
0x180033a9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033aa4  lea     rcx, [rbp+410h+var_150]
0x180033aab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033ab0  lea     rcx, [rbp+410h+var_170]
0x180033ab7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033abc  lea     rcx, [rbp+410h+var_190]
0x180033ac3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033ac8  lea     rcx, [rbp+410h+var_1B0]
0x180033acf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033ad4  nop
0x180033ad5  lea     rcx, [rbp+410h+var_440]
0x180033ad9  call    ??1?$shared_ptr@VDownloaderCore@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(void)
0x180033ade  nop
0x180033adf  lea     rcx, [rbp+410h+var_240]; this
0x180033ae6  call    ??1Entry@CurrentCache@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry(void)
0x180033aeb  nop
0x180033aec  lea     rcx, [rbp+410h+var_330]; this
0x180033af3  call    ??1CloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId(void)
0x180033af8  jmp     loc_180033709
0x180033afd  lea     rdx, [rbp+410h+var_400]; void *
0x180033b01  lea     rcx, [rbp+410h+Source]; Source
0x180033b05  call    ?ToString@CorrelationVector@Core@Cloud@Storage@Internal@Windows@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Windows::Internal::Storage::Cloud::Core::CorrelationVector::ToString(void)
0x180033b0a  mov     r8, rax
0x180033b0d  or      ebx, 4
0x180033b10  cmp     qword ptr [rax+18h], 0Fh
0x180033b15  jbe     short loc_180033B1A
0x180033b17  mov     r8, [rax]
0x180033b1a  lea     rdx, [rsi+60h]
0x180033b1e  cmp     qword ptr [rdx+18h], 0Fh
0x180033b23  jbe     short loc_180033B28
0x180033b25  mov     rdx, [rdx]
0x180033b28  lea     rcx, [rbp+410h+var_290]
0x180033b2f  cmp     [rbp+410h+var_278], 0Fh
0x180033b37  cmova   rcx, [rbp+410h+var_290]
0x180033b3f  lea     rax, [rbp+410h+var_2F0]
0x180033b46  cmp     [rbp+410h+var_2D8], 0Fh
0x180033b4e  cmova   rax, [rbp+410h+var_2F0]
0x180033b56  mov     r9d, r12d
0x180033b59  mov     [rsp+510h+var_4D8], r8
  ... truncated ...
```
