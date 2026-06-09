# SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::DoGetValueAsyncWork(void)

- ea: `0x18008ac00`
- end: `0x18008bf1e`
- name: `?DoGetValueAsyncWork@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAXXZ`
- size: `4894`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this)`
- caller_count: `0`
- callee_count: `51`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000171c`
- `0x180004820`
- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000f038`
- `0x180014940`
- `0x180019d30`
- `0x18001a530`
- `0x18001f230`
- `0x18001fc0c`
- `0x18001fe08`
- `0x1800248c0`
- `0x1800292a8`
- `0x18002ee18`
- `0x180034cd8`
- `0x180035c0c`
- `0x180043f48`
- `0x18004ef90`
- `0x18005c450`
- `0x18005fa88`
- `0x180077780`
- `0x18008503c`
- `0x180085868`
- `0x180085abc`
- `0x1800864e8`
- `0x180086a60`
- `0x180086ab8`
- `0x180086b10`
- `0x180087564`
- `0x180088080`
- `0x180088e40`
- `0x180088f38`
- `0x180089170`
- `0x18008ac00`
- `0x18008c730`
- `0x180090a3c`
- `0x1800916fc`
- `0x180091780`
- `0x1800920d0`
- `0x180092f10`
- `0x180092f7c`
- `0x1800931ec`
- `0x180093454`
- `0x1800934a0`
- `0x1800b36f4`
- `0x1800b38a8`
- `0x1800b450c`
- `0x1800b5cc0`
- `0x1800c1928`

## import_xrefs

- `ntdll!RtlInitializeCorrelationVector` at `0x18008ada8`
- `ntdll!RtlInitializeCorrelationVector` at `0x18008ada8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ae42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ae42`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008ad8c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008ad8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008b540`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008b118`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008b8a9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008b118`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008b8a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008ae38`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008ae38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008bdf6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008bdf6`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18008ae74`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18008ae74`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008adff`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008adff`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18008b223`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18008b2ec`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18008b223`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18008b2ec`

## string_xrefs

- `0x18008ad1e`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`
- `0x18008af49`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`
- `0x18008b1e6`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::DoGetValueAsyncWork(
        SystemSettings::DataModel::CSettingBase *this)
{
  unsigned int v2; // r13d
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *Instance; // rbx
  std::_Ref_count_base **v4; // rax
  double v5; // xmm14_8
  int v6; // eax
  __int64 v7; // rcx
  bool v8; // r12
  char *v9; // rdi
  unsigned int **v10; // r15
  unsigned int *v11; // rbx
  __int64 v12; // rcx
  signed int StorageDeviceInfo; // r14d
  signed int LastError; // eax
  __int64 v15; // rdx
  unsigned int *v16; // rax
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v17; // rcx
  __int64 *v18; // rax
  __int64 *v19; // rbx
  __int128 v20; // xmm6
  __int128 v21; // xmm7
  __int128 v22; // xmm8
  __int128 v23; // xmm9
  __int128 v24; // xmm10
  __int128 v25; // xmm11
  __int128 v26; // xmm12
  __int128 v27; // xmm13
  __int16 v28; // di
  __int64 v29; // r9
  int v30; // eax
  int v31; // r8d
  int refreshed; // eax
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rdx
  unsigned __int16 **v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r9
  _QWORD *v38; // rdi
  HWND ForegroundWindow; // rbx
  const struct _GUID *v40; // rdx
  const struct _GUID *v41; // r8
  int InstanceAsAdmin; // eax
  wil::details::in1diag3 *v43; // rcx
  __int64 v44; // r14
  __int64 (__fastcall *v45)(__int64, char *); // rbx
  HWND v46; // rax
  const struct _GUID *v47; // rdx
  const struct _GUID *v48; // r8
  int v49; // eax
  wil::details::in1diag3 *v50; // rcx
  __int64 v51; // r14
  __int64 (__fastcall *v52)(__int64, char *); // rbx
  __int64 v53; // rax
  int v54; // eax
  int v55; // r12d
  __int64 v56; // rax
  _QWORD *v57; // r13
  __int64 v58; // rax
  __int128 v59; // xmm6
  __int128 v60; // xmm7
  __int128 v61; // xmm8
  __int128 v62; // xmm9
  __int128 v63; // xmm10
  __int128 v64; // xmm11
  __int128 v65; // xmm12
  __int128 v66; // xmm13
  __int16 v67; // bx
  __int64 v68; // r8
  int v69; // eax
  int v70; // r9d
  int v71; // eax
  unsigned int v72; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v74; // rdx
  int v75; // ebx
  unsigned __int64 v76; // rax
  __int64 v77; // rbx
  int v78; // eax
  __int64 v79; // r8
  int v80; // edx
  int Size; // eax
  __int64 v82; // r9
  unsigned int v83; // r13d
  __int64 v84; // rbx
  int v85; // eax
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v86; // rbx
  std::_Ref_count_base **v87; // rax
  __int64 v88; // rdx
  unsigned int v89; // r13d
  char **v90; // rbx
  __int64 v91; // r15
  const struct _tlgProvider_t *v92; // rax
  __int64 v93; // rdx
  const struct _tlgProvider_t *v94; // r8
  int v95; // r9d
  char **v96; // rbx
  const struct _tlgProvider_t *v97; // rax
  __int64 v98; // rdx
  const struct _tlgProvider_t *v99; // r8
  int v100; // r9d
  unsigned __int16 **v101; // r8
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v102; // rbx
  std::_Ref_count_base **v103; // rax
  int v105; // [rsp+28h] [rbp-120h]
  int v106; // [rsp+28h] [rbp-120h]
  int v107; // [rsp+28h] [rbp-120h]
  int v108; // [rsp+28h] [rbp-120h]
  char v109; // [rsp+C8h] [rbp-80h]
  char v110; // [rsp+C9h] [rbp-7Fh] BYREF
  _BYTE v111[6]; // [rsp+CAh] [rbp-7Eh] BYREF
  SystemSettings::DataModel::CSettingBase *v112; // [rsp+D0h] [rbp-78h] BYREF
  unsigned int v113; // [rsp+D8h] [rbp-70h] BYREF
  int v114; // [rsp+DCh] [rbp-6Ch] BYREF
  unsigned int v115; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int16 v116[4]; // [rsp+E8h] [rbp-60h] BYREF
  unsigned int v117; // [rsp+F0h] [rbp-58h] BYREF
  unsigned int v118; // [rsp+F4h] [rbp-54h] BYREF
  unsigned int v119; // [rsp+F8h] [rbp-50h]
  unsigned int v120; // [rsp+FCh] [rbp-4Ch]
  unsigned int v121; // [rsp+100h] [rbp-48h]
  unsigned int v122; // [rsp+104h] [rbp-44h]
  unsigned __int64 v123; // [rsp+108h] [rbp-40h] BYREF
  unsigned __int64 v124; // [rsp+110h] [rbp-38h] BYREF
  __int64 v125; // [rsp+118h] [rbp-30h] BYREF
  __int64 v126; // [rsp+120h] [rbp-28h]
  std::_Ref_count_base *v127[2]; // [rsp+128h] [rbp-20h] BYREF
  char *v128; // [rsp+138h] [rbp-10h] BYREF
  std::_Ref_count_base *v129; // [rsp+140h] [rbp-8h]
  std::_Ref_count_base *v130[2]; // [rsp+148h] [rbp+0h] BYREF
  __int64 v131; // [rsp+158h] [rbp+10h] BYREF
  _QWORD v132[2]; // [rsp+160h] [rbp+18h] BYREF
  __int64 v133; // [rsp+170h] [rbp+28h] BYREF
  __int64 v134; // [rsp+178h] [rbp+30h] BYREF
  __int64 v135; // [rsp+180h] [rbp+38h] BYREF
  char *v136; // [rsp+188h] [rbp+40h] BYREF
  __int64 v137; // [rsp+190h] [rbp+48h] BYREF
  std::_Ref_count_base *v138[2]; // [rsp+198h] [rbp+50h] BYREF
  __int64 v139; // [rsp+1A8h] [rbp+60h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B8h] [rbp+70h] BYREF
  char *v141; // [rsp+1C0h] [rbp+78h] BYREF
  int v142; // [rsp+1C8h] [rbp+80h]
  GUID pguid; // [rsp+1D0h] [rbp+88h] BYREF
  _BYTE v144[336]; // [rsp+1E8h] [rbp+A0h] BYREF
  WCHAR szVolumePathName[2]; // [rsp+338h] [rbp+1F0h] BYREF
  unsigned __int16 v146[558]; // [rsp+33Ch] [rbp+1F4h] BYREF
  WCHAR Buffer[8]; // [rsp+798h] [rbp+650h] BYREF
  __int128 v148; // [rsp+7A8h] [rbp+660h]
  __int128 v149; // [rsp+7B8h] [rbp+670h]
  __int128 v150; // [rsp+7C8h] [rbp+680h]
  __int128 v151; // [rsp+7D8h] [rbp+690h]
  __int128 v152; // [rsp+7E8h] [rbp+6A0h]
  __int128 v153; // [rsp+7F8h] [rbp+6B0h]
  __int128 v154; // [rsp+808h] [rbp+6C0h]
  __int16 v155; // [rsp+818h] [rbp+6D0h]
  wil::details::in1diag3 *retaddr; // [rsp+A90h] [rbp+948h]

  v2 = 0;
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    Instance = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v4 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationStarted,>(&v128);
    *(_OWORD *)v130 = 0;
    v130[0] = *v4;
    v130[1] = v4[1];
    *v4 = 0;
    v4[1] = 0;
    v125 = (__int64)v130;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      Instance,
      &v125);
    if ( v130[1] )
      std::_Ref_count_base::_Decref(v130[1]);
    if ( v129 )
      std::_Ref_count_base::_Decref(v129);
  }
  std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>(v132);
  v131 = 0;
  v123 = 0;
  v5 = 0.0;
  v125 = 0;
  v6 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 74));
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
      (const char *)(unsigned int)v6,
      v105);
    goto LABEL_124;
  }
  v126 = 0;
  v117 = 0;
  v118 = 0;
  v120 = 0;
  v121 = 0;
  v119 = 0;
  v122 = 0;
  v8 = 0;
  v109 = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
  memset_0((char *)this + 392, -1, 0x60u);
  pguid = 0;
  CoCreateGuid(&pguid);
  v9 = (char *)this + 616;
  RtlInitializeCorrelationVector((char *)this + 616, 2, &pguid);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Start<CORRELATION_VECTOR &>(v144);
  v10 = (unsigned int **)((char *)this + 264);
  v11 = (unsigned int *)*((_QWORD *)this + 33);
  if ( v11 && (*v11 || v11[1]) )
  {
    memset_0(v146, 0, 0x454u);
    wcscpy(szVolumePathName, L"ј");
    StorageDeviceInfo = GetStorageDeviceInfo(*v11, v11[1], szVolumePathName);
    if ( StorageDeviceInfo >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)this + 244, 4u, v146);
      goto LABEL_18;
    }
  }
  else
  {
    if ( GetWindowsDirectoryW(Buffer, 0x104u) && GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
    {
      StorageDeviceInfo = 0;
      *((_WORD *)this + 244) = szVolumePathName[0];
LABEL_18:
      *(_QWORD *)((char *)this + 524) = 1;
      SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
        this,
        0,
        1,
        0);
      LOBYTE(v15) = 1;
      SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
        (char *)&unk_18018A990 + 272 * *((int *)this + 96),
        v15,
        0);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111EA8);
      *(_WORD *)((char *)this + 505) = 0;
      *((_BYTE *)this + 507) = 0;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
      if ( !IsDesktopSKU() )
      {
        v115 = 0;
        v16 = *v10;
        if ( *v10 )
        {
          v2 = *v16;
          v113 = v16[1];
          v9 = (char *)this + 616;
        }
        else
        {
          v113 = 0;
        }
        SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::GetCleanupHandlers(v132);
        v123 = v132[1];
        SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v17);
        v18 = (__int64 *)v132[0];
        v19 = *(__int64 **)v132[0];
        while ( 1 )
        {
          if ( v19 == v18 )
          {
LABEL_38:
            SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::_Sort(this);
            goto LABEL_99;
          }
          if ( *((_BYTE *)this + 520) )
          {
            *((_BYTE *)this + 520) = 0;
            *((_WORD *)this + 253) = 256;
            *((_DWORD *)this + 132) = 1;
            goto LABEL_38;
          }
          v112 = 0;
          v124 = 0;
          *(_QWORD *)v116 = 0;
          v20 = *(_OWORD *)v9;
          v21 = *((_OWORD *)v9 + 1);
          v22 = *((_OWORD *)v9 + 2);
          v23 = *((_OWORD *)v9 + 3);
          v24 = *((_OWORD *)v9 + 4);
          v25 = *((_OWORD *)v9 + 5);
          v26 = *((_OWORD *)v9 + 6);
          v27 = *((_OWORD *)v9 + 7);
          v28 = *((_WORD *)v9 + 64);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v112);
          v30 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                  &v128,
                  (char *)this + 264,
                  *((unsigned int *)this + 96),
                  v29);
          *(_OWORD *)Buffer = v20;
          v148 = v21;
          v149 = v22;
          v150 = v23;
          v151 = v24;
          v152 = v25;
          v153 = v26;
          v154 = v27;
          v155 = v28;
          *(_OWORD *)v138 = *((_OWORD *)v19 + 1);
          v139 = v19[4];
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                        (unsigned int)v138,
                        v30,
                        v31,
                        (unsigned int)&v112,
                        (__int64)Buffer);
          v33 = retaddr;
          if ( refreshed < 0 )
            break;
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v112, 0, 0, 0, 0);
          v33 = retaddr;
          if ( refreshed < 0 )
          {
            v34 = 608;
            goto LABEL_27;
          }
          refreshed = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, _QWORD))(*(_QWORD *)v112 + 216LL))(
                        v112,
                        0);
          v33 = retaddr;
          if ( refreshed < 0 )
          {
            v34 = 609;
            goto LABEL_27;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            v116,
            0);
          StorageDeviceInfo = SystemSettings::DataModel::GetResourceStringById(
                                (SystemSettings::DataModel *)v19[2],
                                v116,
                                v35);
          if ( StorageDeviceInfo < 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v116);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v124);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v112);
            goto LABEL_103;
          }
          ++v115;
          SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
            this,
            *(_QWORD *)v116,
            *((unsigned int *)this + 131),
            100 * v115 / (unsigned int)v123);
          LOBYTE(v36) = 1;
          SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
            (char *)&unk_18018A990 + 272 * *((int *)this + 96),
            v36,
            0);
          Sleep(0xC8u);
          v126 += *((_QWORD *)v112 + 34);
          if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::ShowSubCategory(
                                  v2,
                                  v113,
                                  *((unsigned int *)v19 + 8)) )
          {
            LOBYTE(v37) = 1;
            Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 74),
              0,
              v112,
              v37);
            SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
          }
LABEL_35:
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v116);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v124);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v112);
          v19 = (__int64 *)*v19;
          v18 = (__int64 *)v132[0];
          v9 = (char *)this + 616;
        }
        v34 = 607;
LABEL_27:
        wil::details::in1diag3::_Log_Hr(
          v33,
          (void *)v34,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
          (const char *)(unsigned int)refreshed,
          v106);
        goto LABEL_35;
      }
      v38 = (_QWORD *)((char *)this + 600);
      if ( *((_QWORD *)this + 75) )
        goto LABEL_60;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MoveAdminCleanupToTempFilesMainPage>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MoveAdminCleanupToTempFilesMainPage>::GetImpl'::`2'::impl) )
      {
        if ( !*((_BYTE *)this + 508) )
          goto LABEL_49;
        ForegroundWindow = (HWND)*((_QWORD *)this + 64);
        if ( !ForegroundWindow )
          ForegroundWindow = GetForegroundWindow();
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 608);
        InstanceAsAdmin = CoCreateInstanceAsAdmin(ForegroundWindow, v40, v41, (void **)this + 76);
        v43 = retaddr;
        if ( InstanceAsAdmin >= 0 )
        {
          v44 = *((_QWORD *)this + 76);
          if ( !v44 )
          {
LABEL_48:
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
LABEL_49:
            if ( !*v38 )
            {
              if ( *((_BYTE *)this + 508) )
              {
                *((_BYTE *)this + 508) = 0;
                *((_QWORD *)this + 64) = 0;
                SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112530);
                SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112548);
              }
              goto LABEL_58;
            }
            goto LABEL_60;
          }
          v45 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v44 + 24LL);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
          InstanceAsAdmin = v45(v44, (char *)this + 600);
          v43 = retaddr;
          if ( InstanceAsAdmin >= 0 )
            goto LABEL_49;
        }
        wil::details::in1diag3::_Log_Hr(
          v43,
          (void *)0x28C,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
          (const char *)(unsigned int)InstanceAsAdmin,
          v105);
        goto LABEL_48;
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 608);
      v46 = GetForegroundWindow();
      v49 = CoCreateInstanceAsAdmin(v46, v47, v48, (void **)this + 76);
      v50 = retaddr;
      if ( v49 >= 0 )
      {
        v51 = *((_QWORD *)this + 76);
        if ( !v51 )
        {
LABEL_56:
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
LABEL_57:
          if ( !*v38 )
          {
LABEL_58:
            v53 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CleanmgrHelper,>(&v112);
            Microsoft::WRL::ComPtr<ICleanmgrHelper>::operator=<SystemSettings::StorageSenseHandlers::CleanmgrHelper>(
              (char *)this + 600,
              v53);
            if ( v112 )
            {
              v112 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICleanmgrHelper>::Release();
            }
          }
LABEL_60:
          StorageDeviceInfo = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v38 + 24LL))(
                                *v38,
                                (char *)this + 488);
          if ( StorageDeviceInfo >= 0 )
          {
            v54 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v38 + 104LL))(
                    *v38,
                    12,
                    (char *)this + 392);
            v55 = v54;
            if ( v54 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2DD,
                (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                (const char *)(unsigned int)v54,
                v105);
            v8 = v55 >= 0;
            StorageDeviceInfo = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(*(_QWORD *)*v38 + 32LL))(
                                  *v38,
                                  &v123);
            if ( StorageDeviceInfo >= 0 )
            {
              v56 = *((_QWORD *)this + 35);
              if ( v56 != *((_QWORD *)this + 36) )
                *((_QWORD *)this + 36) = v56;
              v57 = (_QWORD *)((char *)this + 304);
              v58 = *((_QWORD *)this + 38);
              if ( v58 != *((_QWORD *)this + 39) )
                *((_QWORD *)this + 39) = v58;
              v113 = 0;
              if ( v123 )
              {
                while ( !*((_BYTE *)this + 520) )
                {
                  v112 = 0;
                  v59 = *(_OWORD *)((char *)this + 616);
                  v60 = *(_OWORD *)((char *)this + 632);
                  v61 = *(_OWORD *)((char *)this + 648);
                  v62 = *(_OWORD *)((char *)this + 664);
                  v63 = *(_OWORD *)((char *)this + 680);
                  v64 = *(_OWORD *)((char *)this + 696);
                  v65 = *(_OWORD *)((char *)this + 712);
                  v66 = *(_OWORD *)((char *)this + 728);
                  v67 = *((_WORD *)this + 372);
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v112);
                  v69 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                          &v128,
                          (char *)this + 264,
                          v68,
                          *((unsigned int *)this + 96));
                  *(_OWORD *)Buffer = v59;
                  v148 = v60;
                  v149 = v61;
                  v150 = v62;
                  v151 = v63;
                  v152 = v64;
                  v153 = v65;
                  v154 = v66;
                  v155 = v67;
                  v71 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                          *v38,
                          v113,
                          v69,
                          v70,
                          (__int64)&v112,
                          (__int64)Buffer);
                  if ( v71 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x2F8,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v71,
                      v107);
                    ++v122;
                    goto LABEL_95;
                  }
                  v72 = *((_DWORD *)this + 131);
                  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v112 + 30), 0);
                  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
                    this,
                    StringRawBuffer,
                    v72,
                    100 * v113 / (unsigned int)v123);
                  LOBYTE(v74) = 1;
                  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                    (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                    v74,
                    0);
                  v75 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(
                          v112,
                          0,
                          (__int64)this + 280,
                          (ULONGLONG)v57,
                          &v131);
                  if ( !v131 )
                  {
                    v5 = v5 + *(double *)(208LL * v117 + *v57 + 184);
                    v125 = *(_QWORD *)&v5;
                  }
                  ++v117;
                  if ( v75 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x309,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v75,
                      v108);
                    StorageDeviceInfo = v75;
                    ++v121;
                    goto LABEL_95;
                  }
                  v76 = *((_QWORD *)v112 + 34);
                  v124 = v76;
                  ++v118;
                  if ( v76 )
                  {
                    v126 += v76;
                    ++v120;
                    v114 = 0;
                    v77 = v113;
                    v78 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)*v38 + 72LL))(*v38, v113, &v114);
                    if ( v78 >= 0 )
                    {
                      v80 = v114;
                      if ( v114 )
                        ++v119;
                    }
                    else
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x316,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)v78,
                        v108);
                      v80 = v114;
                    }
                    LOBYTE(v79) = v80 != 0;
                    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsItemChecked(
                      (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                      v77,
                      v79);
                    v115 = 0;
                    Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
                             *((_QWORD *)this + 74),
                             &v115);
                    if ( Size < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x31E,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)Size,
                        v108);
                      goto LABEL_90;
                    }
                    v83 = 0;
                    if ( !v115 )
                    {
LABEL_88:
                      LOBYTE(v82) = 1;
                      Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                        *((_QWORD *)this + 74),
                        0,
                        v112,
                        v82);
                      goto LABEL_89;
                    }
                    while ( 1 )
                    {
                      *(_QWORD *)v116 = 0;
                      v84 = *((_QWORD *)this + 74);
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v116);
                      v85 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                              v84,
                              v83,
                              v116);
                      if ( v85 >= 0 )
                      {
                        if ( *(_QWORD *)(*(_QWORD *)v116 + 272LL) < v124 )
                        {
                          Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                            *((_QWORD *)this + 74),
                            v83,
                            v112,
                            0);
                          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v116);
LABEL_89:
                          SystemSettings::DataModel::CSettingBase::OnValueChanged(
                            this,
                            (const unsigned __int16 *)&stru_18010EDA8);
                          v57 = (_QWORD *)((char *)this + 304);
LABEL_90:
                          SystemSettings::DataModel::CSettingBase::OnValueChanged(
                            this,
                            (const unsigned __int16 *)&stru_180107F20);
                          if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                                                  *((unsigned int *)this + 94),
                                                  *((unsigned int *)this + 95)) )
                          {
                            v86 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
                            *(_QWORD *)v116 = v112;
                            v87 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListItemLoaded,SystemSettings::StorageSenseHandlers::CStorageCleanupItem *,int &>(
                                                             v138,
                                                             v116,
                                                             &v114);
                            *(_OWORD *)v127 = 0;
                            v127[0] = *v87;
                            v127[1] = v87[1];
                            *v87 = 0;
                            v87[1] = 0;
                            *(_QWORD *)v116 = v127;
                            SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
                              v86,
                              v116);
                            if ( v127[1] )
                              std::_Ref_count_base::_Decref(v127[1]);
                            if ( v138[1] )
                              std::_Ref_count_base::_Decref(v138[1]);
                          }
                          break;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x324,
                          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                          (const char *)(unsigned int)v85,
                          v108);
                      }
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v116);
                      if ( ++v83 >= v115 )
                        goto LABEL_88;
                    }
                  }
LABEL_95:
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v112);
                  if ( ++v113 >= v123 )
                    goto LABEL_99;
                }
                *((_BYTE *)this + 520) = 0;
                *((_WORD *)this + 253) = 256;
                *((_DWORD *)this + 132) = 1;
                v109 = 1;
              }
LABEL_99:
              SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
                this,
                0,
                *((unsigned int *)this + 131),
                100);
              if ( !*((_BYTE *)this + 507) )
              {
                LOBYTE(v88) = 1;
                SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                  (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                  v88,
                  0);
                Sleep(0xC8u);
              }
              *((_BYTE *)this + 505) = 1;
              *((_DWORD *)this + 131) = 0;
              SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                0,
                0);
              SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
              if ( v8 )
                SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1801122D0);
            }
          }
LABEL_103:
          v9 = (char *)this + 616;
          goto LABEL_104;
        }
        v52 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 24LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
        v49 = v52(v51, (char *)this + 600);
        v50 = retaddr;
        if ( v49 >= 0 )
          goto LABEL_57;
      }
      wil::details::in1diag3::_Log_Hr(
        v50,
        (void *)0x2BC,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
        (const char *)(unsigned int)v49,
        v105);
      goto LABEL_56;
    }
    LastError = GetLastError();
    StorageDeviceInfo = LastError;
    if ( LastError > 0 )
      StorageDeviceInfo = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_104:
  *(_OWORD *)Buffer = *(_OWORD *)v9;
  v148 = *((_OWORD *)v9 + 1);
  v149 = *((_OWORD *)v9 + 2);
  v150 = *((_OWORD *)v9 + 3);
  v151 = *((_OWORD *)v9 + 4);
  v152 = *((_OWORD *)v9 + 5);
  v153 = *((_OWORD *)v9 + 6);
  v154 = *((_OWORD *)v9 + 7);
  v155 = *((_WORD *)v9 + 64);
  v89 = v117;
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Stop(
    v12,
    (char *)this + 488,
    v126,
    (unsigned int)StorageDeviceInfo,
    v123,
    v122,
    v117,
    v118,
    v121,
    v120,
    v119,
    v8,
    (char *)this + 392);
  v90 = (char **)((char *)this + 280);
  v91 = v125;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3) )
  {
    LOWORD(v114) = 14247 * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3);
    v92 = SettingsHandlersStorageSenseLogging::Provider();
    v94 = v92;
    if ( *(_DWORD *)v92 && (unsigned __int8)tlgKeywordOn(v92, 0x400000000000LL) )
    {
      v141 = *v90;
      v142 = 184 * (unsigned __int16)v114;
      v138[0] = (std::_Ref_count_base *)&v114;
      LODWORD(v138[1]) = 2;
      v125 = (__int64)this + 617;
      v136 = (char *)*((_QWORD *)this + 62);
      v128 = (char *)this + 392;
      LOWORD(v129) = 12;
      v110 = v109;
      v111[0] = v8;
      v137 = v91;
      v118 = v119;
      v115 = v120;
      v117 = v121;
      LODWORD(v124) = v89;
      *(_DWORD *)v116 = v122;
      v133 = v123;
      LOWORD(v113) = v114;
      v134 = v131;
      LODWORD(v112) = StorageDeviceInfo;
      v135 = v126;
      v127[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 488);
      v130[0] = (std::_Ref_count_base *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v94,
        (unsigned int)&unk_180153733,
        (_DWORD)v94,
        v95,
        (__int64)v130,
        (__int64)v127,
        (__int64)&v135,
        (__int64)&v112,
        (__int64)&v134,
        (__int64)&v113,
        (__int64)&v133,
        (__int64)v116,
        (__int64)&v124,
        (__int64)&v117,
        (__int64)&v115,
        (__int64)&v118,
        (__int64)&v137,
        (__int64)v111,
        (__int64)&v110,
        (__int64)&v128,
        (__int64)&v136,
        (__int64)&v125,
        (__int64)v138,
        (__int64)&v141);
    }
    if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 36) )
      *((_QWORD *)this + 36) = *v90;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart>::shrink_to_fit((char *)this + 280, v93, v94);
  }
  v96 = (char **)((char *)this + 304);
  if ( 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4) )
  {
    LOWORD(v114) = 20165 * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4);
    v97 = SettingsHandlersStorageSenseLogging::Provider();
    v99 = v97;
    if ( *(_DWORD *)v97 && (unsigned __int8)tlgKeywordOn(v97, 0x400000000000LL) )
    {
      v128 = *v96;
      LODWORD(v129) = 208 * (unsigned __int16)v114;
      v138[0] = (std::_Ref_count_base *)&v114;
      LODWORD(v138[1]) = 2;
      v130[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 617);
      v127[0] = *((std::_Ref_count_base **)this + 62);
      v141 = (char *)this + 392;
      LOWORD(v142) = 12;
      v111[0] = v109;
      v110 = v8;
      v135 = v91;
      LODWORD(v112) = v119;
      *(_DWORD *)v116 = v120;
      LODWORD(v124) = v121;
      v118 = v89;
      v115 = v122;
      v134 = v123;
      LOWORD(v113) = v114;
      v133 = v131;
      v117 = StorageDeviceInfo;
      v137 = v126;
      v136 = (char *)this + 488;
      v125 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v99,
        (unsigned int)&unk_180153556,
        (_DWORD)v99,
        v100,
        (__int64)&v125,
        (__int64)&v136,
        (__int64)&v137,
        (__int64)&v117,
        (__int64)&v133,
        (__int64)&v113,
        (__int64)&v134,
        (__int64)&v115,
        (__int64)&v118,
        (__int64)&v124,
        (__int64)v116,
        (__int64)&v112,
        (__int64)&v135,
        (__int64)&v110,
        (__int64)v111,
        (__int64)&v141,
        (__int64)v127,
        (__int64)v130,
        (__int64)v138,
        (__int64)&v128);
    }
    if ( *((_QWORD *)this + 38) != *((_QWORD *)this + 39) )
      *((_QWORD *)this + 39) = *v96;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop>::shrink_to_fit((char *)this + 304, v98, v99);
  }
  *((_BYTE *)this + 504) = 1;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111E88);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111EF0);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)this + 880,
    0);
  SystemSettings::StorageSenseHandlers::StringHelpers::GetDateTimeString(
    (SystemSettings::StorageSenseHandlers::StringHelpers *)&SystemTimeAsFileTime,
    (struct _FILETIME *)this + 110,
    v101);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111DC8);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    v102 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v103 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationFinished,>(&v128);
    *(_OWORD *)v127 = 0;
    v127[0] = *v103;
    v127[1] = v103[1];
    *v103 = 0;
    v103[1] = 0;
    v130[0] = (std::_Ref_count_base *)v127;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      v102,
      v130);
    if ( v127[1] )
      std::_Ref_count_base::_Decref(v127[1]);
    if ( v129 )
      std::_Ref_count_base::_Decref(v129);
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::~StorageSenseScan((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan *)v144);
LABEL_124:
  std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>::_Free_non_head<std::allocator<std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>>>(
    v7,
    v132[0]);
  return std::_Deallocate<16>(v132[0], 40);
}

```

## disassembly

```asm
0x18008ac00  mov     rax, rsp
0x18008ac03  push    rbp
0x18008ac04  push    rbx
0x18008ac05  push    rsi
0x18008ac06  push    rdi
0x18008ac07  push    r12
0x18008ac09  push    r13
0x18008ac0b  push    r14
0x18008ac0d  push    r15
0x18008ac0f  lea     rbp, [rax-948h]
0x18008ac16  sub     rsp, 0A48h
0x18008ac1d  movaps  xmmword ptr [rax-58h], xmm6
0x18008ac21  movaps  xmmword ptr [rax-68h], xmm7
0x18008ac25  movaps  xmmword ptr [rax-78h], xmm8
0x18008ac2a  movaps  xmmword ptr [rax-88h], xmm9
0x18008ac32  movaps  xmmword ptr [rax-98h], xmm10
0x18008ac3a  movaps  xmmword ptr [rax-0A8h], xmm11
0x18008ac42  movaps  xmmword ptr [rax-0B8h], xmm12
0x18008ac4a  movaps  xmmword ptr [rax-0C8h], xmm13
0x18008ac52  movaps  xmmword ptr [rax-0D8h], xmm14
0x18008ac5a  mov     rax, cs:__security_cookie
0x18008ac61  xor     rax, rsp
0x18008ac64  mov     [rbp+940h+var_E0], rax
0x18008ac6b  mov     rsi, rcx
0x18008ac6e  mov     edx, [rcx+17Ch]
0x18008ac74  mov     ecx, [rcx+178h]
0x18008ac7a  call    ?IsSystemVolume@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NW4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(_STORAGE_DEVICE_TYPE,ulong)
0x18008ac7f  xor     r13d, r13d
0x18008ac82  test    al, al
0x18008ac84  jz      short loc_18008ACE8
0x18008ac86  call    ?GetInstance@CStorageCleanupListHandlerSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance(void)
0x18008ac8b  mov     rbx, rax
0x18008ac8e  lea     rcx, [rbp+940h+var_950]
0x18008ac92  call    ??$make_shared@UCleanupListInitializationStarted@StorageSenseHandlers@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@UCleanupListInitializationStarted@StorageSenseHandlers@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationStarted,>(void)
0x18008ac97  nop
0x18008ac98  xorps   xmm0, xmm0
0x18008ac9b  movdqu  xmmword ptr [rbp+940h+var_940], xmm0
0x18008aca0  mov     rcx, [rax]
0x18008aca3  mov     [rbp+940h+var_940], rcx
0x18008aca7  mov     rcx, [rax+8]
0x18008acab  mov     [rbp+940h+var_940+8], rcx
0x18008acaf  mov     [rax], r13
0x18008acb2  mov     [rax+8], r13
0x18008acb6  lea     rax, [rbp+940h+var_940]
0x18008acba  mov     [rbp+940h+var_970], rax
0x18008acbe  lea     rdx, [rbp+940h+var_970]
0x18008acc2  mov     rcx, rbx
0x18008acc5  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x18008acca  nop
0x18008accb  mov     rcx, [rbp+940h+var_940+8]; this
0x18008accf  test    rcx, rcx
0x18008acd2  jz      short loc_18008ACDA
0x18008acd4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008acd9  nop
0x18008acda  mov     rcx, [rbp+940h+var_948]; this
0x18008acde  test    rcx, rcx
0x18008ace1  jz      short loc_18008ACE8
0x18008ace3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008ace8  lea     rcx, [rbp+940h+var_928]
0x18008acec  call    ??0?$list@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@V?$allocator@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@@std@@@std@@QEAA@XZ; std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>(void)
0x18008acf1  nop
0x18008acf2  mov     [rbp+940h+var_930], r13
0x18008acf6  mov     [rbp+940h+var_980], r13
0x18008acfa  xorps   xmm14, xmm14
0x18008acfe  movsd   [rbp+940h+var_970], xmm14
0x18008ad04  mov     rcx, [rsi+250h]
0x18008ad0b  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x18008ad10  mov     rcx, [rbp+948h]; this
0x18008ad17  test    eax, eax
0x18008ad19  jns     short loc_18008AD34
0x18008ad1b  mov     r9d, eax; char *
0x18008ad1e  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\coresettinghandlers"...
0x18008ad25  mov     edx, 1FCh; void *
0x18008ad2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ad2f  jmp     loc_18008BEAD
0x18008ad34  mov     [rbp+940h+var_968], r13
0x18008ad38  mov     [rbp+940h+var_998], r13d
0x18008ad3c  mov     [rbp+940h+var_994], r13d
0x18008ad40  mov     [rbp+940h+var_98C], r13d
0x18008ad44  mov     [rbp+940h+var_988], r13d
0x18008ad48  mov     [rbp+940h+var_990], r13d
0x18008ad4c  mov     [rbp+940h+var_984], r13d
0x18008ad50  mov     r12b, r13b
0x18008ad53  mov     [rbp+940h+var_9C0], r13b
0x18008ad57  lea     rdx, stru_18010EDA8; unsigned __int16 *
0x18008ad5e  mov     rcx, rsi; this
0x18008ad61  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008ad66  lea     rcx, [rsi+188h]; void *
0x18008ad6d  mov     r8d, 60h ; '`'; Size
0x18008ad73  or      edx, 0FFFFFFFFh; Val
0x18008ad76  call    memset_0
0x18008ad7b  xorps   xmm0, xmm0
0x18008ad7e  movups  xmmword ptr [rbp+940h+pguid.Data1], xmm0
0x18008ad85  lea     rcx, [rbp+940h+pguid]; pguid
0x18008ad8c  call    cs:__imp_CoCreateGuid
0x18008ad92  lea     rdi, [rsi+268h]
0x18008ad99  lea     r8, [rbp+940h+pguid]
0x18008ada0  mov     edx, 2
0x18008ada5  mov     rcx, rdi
0x18008ada8  call    cs:__imp_RtlInitializeCorrelationVector
0x18008adae  lea     rcx, [rbp+940h+var_8A0]
0x18008adb5  call    ??$Start@AEAUCORRELATION_VECTOR@@@StorageSenseScan@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@SA?AV01234@AEAUCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Start<CORRELATION_VECTOR &>(CORRELATION_VECTOR &)
0x18008adba  nop
0x18008adbb  lea     r15, [rsi+108h]
0x18008adc2  mov     rbx, [r15]
0x18008adc5  test    rbx, rbx
0x18008adc8  jz      short loc_18008AE2A
0x18008adca  cmp     [rbx], r13d
0x18008adcd  jnz     short loc_18008ADD5
0x18008adcf  cmp     [rbx+4], r13d
0x18008add3  jz      short loc_18008AE2A
0x18008add5  xor     edx, edx; Val
0x18008add7  mov     r8d, 454h; Size
0x18008addd  lea     rcx, [rbp+940h+var_74C]; void *
0x18008ade4  call    memset_0
0x18008ade9  mov     dword ptr [rbp+940h+szVolumePathName], 458h
0x18008adf3  lea     r8, [rbp+940h+szVolumePathName]
0x18008adfa  mov     edx, [rbx+4]
0x18008adfd  mov     ecx, [rbx]
0x18008adff  call    cs:__imp_GetStorageDeviceInfo
0x18008ae05  mov     r14d, eax
0x18008ae08  test    eax, eax
0x18008ae0a  js      loc_18008B90C
0x18008ae10  lea     rcx, [rsi+1E8h]; unsigned __int16 *
0x18008ae17  lea     r8, [rbp+940h+var_74C]; unsigned __int16 *
0x18008ae1e  mov     edx, 4; unsigned __int64
0x18008ae23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008ae28  jmp     short loc_18008AE8F
0x18008ae2a  mov     ebx, 104h
0x18008ae2f  mov     edx, ebx; uSize
0x18008ae31  lea     rcx, [rbp+940h+Buffer]; lpBuffer
0x18008ae38  call    cs:__imp_GetWindowsDirectoryW
0x18008ae3e  test    eax, eax
0x18008ae40  jnz     short loc_18008AE63
0x18008ae42  call    cs:__imp_GetLastError
0x18008ae48  mov     r14d, eax
0x18008ae4b  test    eax, eax
0x18008ae4d  jle     loc_18008B90C
0x18008ae53  movzx   r14d, ax
0x18008ae57  or      r14d, 80070000h
0x18008ae5e  jmp     loc_18008B90C
0x18008ae63  mov     r8d, ebx; cchBufferLength
0x18008ae66  lea     rdx, [rbp+940h+szVolumePathName]; lpszVolumePathName
0x18008ae6d  lea     rcx, [rbp+940h+Buffer]; lpszFileName
0x18008ae74  call    cs:__imp_GetVolumePathNameW
0x18008ae7a  test    eax, eax
0x18008ae7c  jz      short loc_18008AE42
0x18008ae7e  mov     r14d, r13d
0x18008ae81  movzx   eax, [rbp+940h+szVolumePathName]
0x18008ae88  mov     [rsi+1E8h], ax
0x18008ae8f  mov     ebx, 1
0x18008ae94  mov     [rsi+20Ch], rbx
0x18008ae9b  xor     r9d, r9d
0x18008ae9e  mov     r8d, ebx
0x18008aea1  xor     edx, edx
0x18008aea3  mov     rcx, rsi
0x18008aea6  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008aeab  movsxd  rax, dword ptr [rsi+180h]
0x18008aeb2  imul    rcx, rax, 110h
0x18008aeb9  lea     rax, unk_18018A990
0x18008aec0  add     rcx, rax
0x18008aec3  xor     r8d, r8d
0x18008aec6  mov     dl, bl
0x18008aec8  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008aecd  lea     rdx, stru_180111EA8; unsigned __int16 *
0x18008aed4  mov     rcx, rsi; this
0x18008aed7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008aedc  mov     [rsi+1F9h], r13w
0x18008aee4  mov     [rsi+1FBh], r13b
0x18008aeeb  lea     rdx, stru_180112038; unsigned __int16 *
0x18008aef2  mov     rcx, rsi; this
0x18008aef5  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008aefa  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x18008aeff  test    al, al
0x18008af01  jnz     loc_18008B1DF
0x18008af07  mov     [rbp+940h+var_9A8], r13d
0x18008af0b  mov     rax, [r15]
0x18008af0e  test    rax, rax
0x18008af11  jz      short loc_18008AF25
0x18008af13  mov     r13d, [rax]
0x18008af16  mov     edi, [rax+4]
0x18008af19  mov     [rbp+940h+var_9B0], edi
0x18008af1c  lea     rdi, [rsi+268h]
0x18008af23  jmp     short loc_18008AF2C
0x18008af25  mov     [rbp+940h+var_9B0], 0
0x18008af2c  lea     rcx, [rbp+940h+var_928]
0x18008af30  call    ?GetCleanupHandlers@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@YAXPEAV?$list@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@V?$allocator@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@@std@@@std@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::GetCleanupHandlers(std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER> *)
0x18008af35  mov     rax, [rbp+940h+var_920]
0x18008af39  mov     [rbp+940h+var_980], rax
0x18008af3d  call    ?RefreshQueries@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(void)
0x18008af42  mov     rax, [rbp+940h+var_928]
0x18008af46  mov     rbx, [rax]
0x18008af49  lea     r15, aOnecoreuapShel_25; "onecoreuap\\shell\\coresettinghandlers"...
0x18008af50  cmp     rbx, rax
0x18008af53  jz      loc_18008B1D2
0x18008af59  mov     al, [rsi+208h]
0x18008af5f  nop
0x18008af60  xor     ecx, ecx
0x18008af62  test    al, al
0x18008af64  jnz     loc_18008B1B7
0x18008af6a  mov     [rbp+940h+var_9B8], rcx
0x18008af6e  mov     [rbp+940h+var_978], rcx
0x18008af72  mov     qword ptr [rbp+940h+var_9A0], rcx
0x18008af76  movups  xmm6, xmmword ptr [rdi]
0x18008af79  movups  xmm7, xmmword ptr [rdi+10h]
0x18008af7d  movups  xmm8, xmmword ptr [rdi+20h]
0x18008af82  movups  xmm9, xmmword ptr [rdi+30h]
0x18008af87  movups  xmm10, xmmword ptr [rdi+40h]
0x18008af8c  movups  xmm11, xmmword ptr [rdi+50h]
0x18008af91  movups  xmm12, xmmword ptr [rdi+60h]
0x18008af96  movups  xmm13, xmmword ptr [rdi+70h]
0x18008af9b  movzx   edi, word ptr [rdi+80h]
0x18008afa2  lea     rcx, [rbp+940h+var_9B8]
0x18008afa6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008afab  mov     r8d, [rsi+180h]
0x18008afb2  lea     rdx, [rsi+108h]
0x18008afb9  lea     rcx, [rbp+940h+var_950]
0x18008afbd  call    ??$?0UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@$0A@@?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@QEAA@AEBV?$shared_ptr@UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@@1@@Z; std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress> const &)
0x18008afc2  movups  xmmword ptr [rbp+940h+Buffer], xmm6
0x18008afc9  movups  [rbp+940h+var_2E0], xmm7
0x18008afd0  movups  [rbp+940h+var_2D0], xmm8
0x18008afd8  movups  [rbp+940h+var_2C0], xmm9
0x18008afe0  movups  [rbp+940h+var_2B0], xmm10
0x18008afe8  movups  [rbp+940h+var_2A0], xmm11
0x18008aff0  movups  [rbp+940h+var_290], xmm12
0x18008aff8  movups  [rbp+940h+var_280], xmm13
0x18008b000  mov     [rbp+940h+var_270], di
0x18008b007  movups  xmm0, xmmword ptr [rbx+10h]
0x18008b00b  movaps  xmmword ptr [rbp+940h+var_8F0], xmm0
0x18008b00f  movsd   xmm1, qword ptr [rbx+20h]
0x18008b014  movsd   [rbp+940h+var_8E0], xmm1
0x18008b019  lea     rcx, [rbp+940h+Buffer]
0x18008b020  mov     [rsp+0A80h+var_A60], rcx; int
0x18008b025  lea     r9, [rbp+940h+var_9B8]
0x18008b029  mov     rdx, rax
0x18008b02c  lea     rcx, [rbp+940h+var_8F0]
0x18008b030  call    ?CreateInstance@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@SAJUSTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@23@V?$shared_ptr@UStorageSenseAdvPageInfo@StorageSenseHandlers@SystemSettings@@@std@@W4CleanupSingletonKind@23@PEAPEAV123@UCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,std::shared_ptr<SystemSettings::StorageSenseHandlers::StorageSenseAdvPageInfo>,SystemSettings::StorageSenseHandlers::CleanupSingletonKind,SystemSettings::StorageSenseHandlers::CStorageCleanupItem * *,CORRELATION_VECTOR)
0x18008b035  mov     rcx, [rbp+948h]; this
0x18008b03c  test    eax, eax
0x18008b03e  jns     short loc_18008B055
0x18008b040  mov     edx, 25Fh; void *
0x18008b045  mov     r9d, eax; char *
0x18008b048  mov     r8, r15; unsigned int
0x18008b04b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008b050  jmp     loc_18008B165
0x18008b055  mov     [rsp+0A80h+var_A60], 0; __int64
0x18008b05e  xor     r9d, r9d
0x18008b061  xor     r8d, r8d
0x18008b064  xor     edx, edx
0x18008b066  mov     rcx, [rbp+940h+var_9B8]; this
0x18008b06a  call    ?RefreshSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4CleanupItemSizeRefreshOperationKind@23@PEAV?$vector@UPluginScanStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginScanStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(SystemSettings::StorageSenseHandlers::CleanupItemSizeRefreshOperationKind,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart> *,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop> *,unsigned __int64 *)
0x18008b06f  mov     rcx, [rbp+948h]
0x18008b076  test    eax, eax
0x18008b078  jns     short loc_18008B081
0x18008b07a  mov     edx, 260h
0x18008b07f  jmp     short loc_18008B045
0x18008b081  mov     rcx, [rbp+940h+var_9B8]
0x18008b085  mov     rax, [rcx]
0x18008b088  xor     edx, edx
0x18008b08a  mov     rax, [rax+0D8h]
0x18008b091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b096  mov     rcx, [rbp+948h]
0x18008b09d  test    eax, eax
0x18008b09f  jns     short loc_18008B0A8
0x18008b0a1  mov     edx, 261h
0x18008b0a6  jmp     short loc_18008B045
0x18008b0a8  xor     edx, edx
0x18008b0aa  lea     rcx, [rbp+940h+var_9A0]
0x18008b0ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008b0b3  lea     rdx, [rbp+940h+var_9A0]; unsigned __int16 *
0x18008b0b7  mov     rcx, [rbx+10h]; this
0x18008b0bb  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x18008b0c0  mov     r14d, eax
0x18008b0c3  test    eax, eax
0x18008b0c5  js      loc_18008B195
0x18008b0cb  mov     edi, [rbp+940h+var_9A8]
0x18008b0ce  inc     edi
0x18008b0d0  mov     [rbp+940h+var_9A8], edi
0x18008b0d3  imul    eax, edi, 64h ; 'd'
0x18008b0d6  xor     edx, edx
0x18008b0d8  div     dword ptr [rbp+940h+var_980]
0x18008b0db  mov     r9d, eax
0x18008b0de  mov     r8d, [rsi+20Ch]
0x18008b0e5  mov     rdx, qword ptr [rbp+940h+var_9A0]
0x18008b0e9  mov     rcx, rsi
0x18008b0ec  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008b0f1  movsxd  rax, dword ptr [rsi+180h]
0x18008b0f8  imul    rcx, rax, 110h
0x18008b0ff  lea     rax, unk_18018A990
0x18008b106  add     rcx, rax
0x18008b109  xor     r8d, r8d
0x18008b10c  mov     dl, 1
0x18008b10e  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008b113  mov     ecx, 0C8h; dwMilliseconds
0x18008b118  call    cs:__imp_Sleep
0x18008b11e  mov     rax, [rbp+940h+var_9B8]
0x18008b122  mov     r9, [rax+110h]
0x18008b129  add     [rbp+940h+var_968], r9
0x18008b12d  mov     r8d, [rbx+20h]
0x18008b131  mov     edx, [rbp+940h+var_9B0]
  ... truncated ...
```
