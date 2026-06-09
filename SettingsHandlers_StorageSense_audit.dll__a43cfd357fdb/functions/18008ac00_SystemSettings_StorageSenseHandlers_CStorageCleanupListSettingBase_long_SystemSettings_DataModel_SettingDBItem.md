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
  int v29; // eax
  int v30; // r8d
  int refreshed; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int16 **v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r9
  _QWORD *v41; // rdi
  HWND ForegroundWindow; // rbx
  const struct _GUID *v43; // rdx
  const struct _GUID *v44; // r8
  int InstanceAsAdmin; // eax
  wil::details::in1diag3 *v46; // rcx
  __int64 v47; // r14
  __int64 (__fastcall *v48)(__int64, char *); // rbx
  HWND v49; // rax
  const struct _GUID *v50; // rdx
  const struct _GUID *v51; // r8
  int v52; // eax
  wil::details::in1diag3 *v53; // rcx
  __int64 v54; // r14
  __int64 (__fastcall *v55)(__int64, char *); // rbx
  __int64 v56; // rax
  int v57; // eax
  int v58; // r12d
  __int64 v59; // rax
  _QWORD *v60; // r13
  __int64 v61; // rax
  __int128 v62; // xmm6
  __int128 v63; // xmm7
  __int128 v64; // xmm8
  __int128 v65; // xmm9
  __int128 v66; // xmm10
  __int128 v67; // xmm11
  __int128 v68; // xmm12
  __int128 v69; // xmm13
  __int16 v70; // bx
  __int64 v71; // r8
  int v72; // eax
  int v73; // r9d
  int v74; // eax
  unsigned int v75; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v77; // rdx
  int v78; // ebx
  unsigned __int64 v79; // rax
  __int64 v80; // rbx
  int v81; // eax
  __int64 v82; // r8
  int v83; // edx
  int Size; // eax
  __int64 v85; // r9
  unsigned int v86; // r13d
  __int64 v87; // rbx
  int v88; // eax
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v89; // rbx
  std::_Ref_count_base **v90; // rax
  __int64 v91; // rdx
  unsigned int v92; // r13d
  char **v93; // rbx
  __int64 v94; // r15
  const struct _tlgProvider_t *v95; // rax
  __int64 v96; // rdx
  const struct _tlgProvider_t *v97; // r8
  int v98; // r9d
  char **v99; // rbx
  const struct _tlgProvider_t *v100; // rax
  __int64 v101; // rdx
  const struct _tlgProvider_t *v102; // r8
  int v103; // r9d
  unsigned __int16 **v104; // r8
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v105; // rbx
  std::_Ref_count_base **v106; // rax
  int v108; // [rsp+28h] [rbp-120h]
  int v109; // [rsp+28h] [rbp-120h]
  int v110; // [rsp+28h] [rbp-120h]
  int v111; // [rsp+28h] [rbp-120h]
  char v112; // [rsp+C8h] [rbp-80h]
  char v113; // [rsp+C9h] [rbp-7Fh] BYREF
  _BYTE v114[6]; // [rsp+CAh] [rbp-7Eh] BYREF
  SystemSettings::DataModel::CSettingBase *v115; // [rsp+D0h] [rbp-78h] BYREF
  unsigned int v116; // [rsp+D8h] [rbp-70h] BYREF
  int v117; // [rsp+DCh] [rbp-6Ch] BYREF
  unsigned int v118; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int16 v119[4]; // [rsp+E8h] [rbp-60h] BYREF
  unsigned int v120; // [rsp+F0h] [rbp-58h] BYREF
  unsigned int v121; // [rsp+F4h] [rbp-54h] BYREF
  unsigned int v122; // [rsp+F8h] [rbp-50h]
  unsigned int v123; // [rsp+FCh] [rbp-4Ch]
  unsigned int v124; // [rsp+100h] [rbp-48h]
  unsigned int v125; // [rsp+104h] [rbp-44h]
  unsigned __int64 v126; // [rsp+108h] [rbp-40h] BYREF
  unsigned __int64 v127; // [rsp+110h] [rbp-38h] BYREF
  __int64 v128; // [rsp+118h] [rbp-30h] BYREF
  __int64 v129; // [rsp+120h] [rbp-28h]
  std::_Ref_count_base *v130[2]; // [rsp+128h] [rbp-20h] BYREF
  char *v131; // [rsp+138h] [rbp-10h] BYREF
  std::_Ref_count_base *v132; // [rsp+140h] [rbp-8h]
  std::_Ref_count_base *v133[2]; // [rsp+148h] [rbp+0h] BYREF
  __int64 v134; // [rsp+158h] [rbp+10h] BYREF
  _QWORD v135[2]; // [rsp+160h] [rbp+18h] BYREF
  __int64 v136; // [rsp+170h] [rbp+28h] BYREF
  __int64 v137; // [rsp+178h] [rbp+30h] BYREF
  __int64 v138; // [rsp+180h] [rbp+38h] BYREF
  char *v139; // [rsp+188h] [rbp+40h] BYREF
  __int64 v140; // [rsp+190h] [rbp+48h] BYREF
  std::_Ref_count_base *v141[2]; // [rsp+198h] [rbp+50h] BYREF
  __int64 v142; // [rsp+1A8h] [rbp+60h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B8h] [rbp+70h] BYREF
  char *v144; // [rsp+1C0h] [rbp+78h] BYREF
  int v145; // [rsp+1C8h] [rbp+80h]
  GUID pguid; // [rsp+1D0h] [rbp+88h] BYREF
  _BYTE v147[336]; // [rsp+1E8h] [rbp+A0h] BYREF
  WCHAR szVolumePathName[2]; // [rsp+338h] [rbp+1F0h] BYREF
  unsigned __int16 v149[558]; // [rsp+33Ch] [rbp+1F4h] BYREF
  WCHAR Buffer[8]; // [rsp+798h] [rbp+650h] BYREF
  __int128 v151; // [rsp+7A8h] [rbp+660h]
  __int128 v152; // [rsp+7B8h] [rbp+670h]
  __int128 v153; // [rsp+7C8h] [rbp+680h]
  __int128 v154; // [rsp+7D8h] [rbp+690h]
  __int128 v155; // [rsp+7E8h] [rbp+6A0h]
  __int128 v156; // [rsp+7F8h] [rbp+6B0h]
  __int128 v157; // [rsp+808h] [rbp+6C0h]
  __int16 v158; // [rsp+818h] [rbp+6D0h]
  wil::details::in1diag3 *retaddr; // [rsp+A90h] [rbp+948h]

  v2 = 0;
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    Instance = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v4 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationStarted,>(&v131);
    *(_OWORD *)v133 = 0;
    v133[0] = *v4;
    v133[1] = v4[1];
    *v4 = 0;
    v4[1] = 0;
    v128 = (__int64)v133;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      Instance,
      &v128);
    if ( v133[1] )
      std::_Ref_count_base::_Decref(v133[1]);
    if ( v132 )
      std::_Ref_count_base::_Decref(v132);
  }
  std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>(v135);
  v134 = 0;
  v126 = 0;
  v5 = 0.0;
  v128 = 0;
  v6 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 74));
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
      (const char *)(unsigned int)v6,
      v108);
    goto LABEL_124;
  }
  v129 = 0;
  v120 = 0;
  v121 = 0;
  v123 = 0;
  v124 = 0;
  v122 = 0;
  v125 = 0;
  v8 = 0;
  v112 = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
  memset_0((char *)this + 392, -1, 0x60u);
  pguid = 0;
  CoCreateGuid(&pguid);
  v9 = (char *)this + 616;
  RtlInitializeCorrelationVector((char *)this + 616, 2, &pguid);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Start<CORRELATION_VECTOR &>(v147);
  v10 = (unsigned int **)((char *)this + 264);
  v11 = (unsigned int *)*((_QWORD *)this + 33);
  if ( v11 && (*v11 || v11[1]) )
  {
    memset_0(v149, 0, 0x454u);
    wcscpy(szVolumePathName, L"ј");
    StorageDeviceInfo = GetStorageDeviceInfo(*v11, v11[1], szVolumePathName);
    if ( StorageDeviceInfo >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)this + 244, 4u, v149);
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
        v118 = 0;
        v16 = *v10;
        if ( *v10 )
        {
          v2 = *v16;
          v116 = v16[1];
          v9 = (char *)this + 616;
        }
        else
        {
          v116 = 0;
        }
        SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::GetCleanupHandlers(v135);
        v126 = v135[1];
        SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v17);
        v18 = (__int64 *)v135[0];
        v19 = *(__int64 **)v135[0];
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
          v115 = 0;
          v127 = 0;
          *(_QWORD *)v119 = 0;
          v20 = *(_OWORD *)v9;
          v21 = *((_OWORD *)v9 + 1);
          v22 = *((_OWORD *)v9 + 2);
          v23 = *((_OWORD *)v9 + 3);
          v24 = *((_OWORD *)v9 + 4);
          v25 = *((_OWORD *)v9 + 5);
          v26 = *((_OWORD *)v9 + 6);
          v27 = *((_OWORD *)v9 + 7);
          v28 = *((_WORD *)v9 + 64);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
          v29 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                  &v131,
                  (char *)this + 264,
                  *((unsigned int *)this + 96));
          *(_OWORD *)Buffer = v20;
          v151 = v21;
          v152 = v22;
          v153 = v23;
          v154 = v24;
          v155 = v25;
          v156 = v26;
          v157 = v27;
          v158 = v28;
          *(_OWORD *)v141 = *((_OWORD *)v19 + 1);
          v142 = v19[4];
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                        (unsigned int)v141,
                        v29,
                        v30,
                        (unsigned int)&v115,
                        (__int64)Buffer);
          v32 = retaddr;
          if ( refreshed < 0 )
            break;
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v115, 0, 0, 0, 0);
          v32 = retaddr;
          if ( refreshed < 0 )
          {
            v33 = 608;
            goto LABEL_27;
          }
          refreshed = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, _QWORD))(*(_QWORD *)v115 + 216LL))(
                        v115,
                        0);
          v32 = retaddr;
          if ( refreshed < 0 )
          {
            v33 = 609;
            goto LABEL_27;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            v119,
            0);
          StorageDeviceInfo = SystemSettings::DataModel::GetResourceStringById(
                                (SystemSettings::DataModel *)v19[2],
                                v119,
                                v36);
          if ( StorageDeviceInfo < 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
              v119,
              v37,
              v38);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v127);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
            goto LABEL_103;
          }
          ++v118;
          SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
            this,
            *(_QWORD *)v119,
            *((unsigned int *)this + 131),
            100 * v118 / (unsigned int)v126);
          LOBYTE(v39) = 1;
          SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
            (char *)&unk_18018A990 + 272 * *((int *)this + 96),
            v39,
            0);
          Sleep(0xC8u);
          v129 += *((_QWORD *)v115 + 34);
          if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::ShowSubCategory(
                                  v2,
                                  v116,
                                  *((unsigned int *)v19 + 8)) )
          {
            LOBYTE(v40) = 1;
            Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 74),
              0,
              v115,
              v40);
            SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
          }
LABEL_35:
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
            v119,
            v34,
            v35);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
          v19 = (__int64 *)*v19;
          v18 = (__int64 *)v135[0];
          v9 = (char *)this + 616;
        }
        v33 = 607;
LABEL_27:
        wil::details::in1diag3::_Log_Hr(
          v32,
          (void *)v33,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
          (const char *)(unsigned int)refreshed,
          v109);
        goto LABEL_35;
      }
      v41 = (_QWORD *)((char *)this + 600);
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
        InstanceAsAdmin = CoCreateInstanceAsAdmin(ForegroundWindow, v43, v44, (void **)this + 76);
        v46 = retaddr;
        if ( InstanceAsAdmin >= 0 )
        {
          v47 = *((_QWORD *)this + 76);
          if ( !v47 )
          {
LABEL_48:
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
LABEL_49:
            if ( !*v41 )
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
          v48 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v47 + 24LL);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
          InstanceAsAdmin = v48(v47, (char *)this + 600);
          v46 = retaddr;
          if ( InstanceAsAdmin >= 0 )
            goto LABEL_49;
        }
        wil::details::in1diag3::_Log_Hr(
          v46,
          (void *)0x28C,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
          (const char *)(unsigned int)InstanceAsAdmin,
          v108);
        goto LABEL_48;
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 608);
      v49 = GetForegroundWindow();
      v52 = CoCreateInstanceAsAdmin(v49, v50, v51, (void **)this + 76);
      v53 = retaddr;
      if ( v52 >= 0 )
      {
        v54 = *((_QWORD *)this + 76);
        if ( !v54 )
        {
LABEL_56:
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
LABEL_57:
          if ( !*v41 )
          {
LABEL_58:
            v56 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CleanmgrHelper,>(&v115);
            Microsoft::WRL::ComPtr<ICleanmgrHelper>::operator=<SystemSettings::StorageSenseHandlers::CleanmgrHelper>(
              (char *)this + 600,
              v56);
            if ( v115 )
            {
              v115 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICleanmgrHelper>::Release();
            }
          }
LABEL_60:
          StorageDeviceInfo = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v41 + 24LL))(
                                *v41,
                                (char *)this + 488);
          if ( StorageDeviceInfo >= 0 )
          {
            v57 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v41 + 104LL))(
                    *v41,
                    12,
                    (char *)this + 392);
            v58 = v57;
            if ( v57 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2DD,
                (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                (const char *)(unsigned int)v57,
                v108);
            v8 = v58 >= 0;
            StorageDeviceInfo = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(*(_QWORD *)*v41 + 32LL))(
                                  *v41,
                                  &v126);
            if ( StorageDeviceInfo >= 0 )
            {
              v59 = *((_QWORD *)this + 35);
              if ( v59 != *((_QWORD *)this + 36) )
                *((_QWORD *)this + 36) = v59;
              v60 = (_QWORD *)((char *)this + 304);
              v61 = *((_QWORD *)this + 38);
              if ( v61 != *((_QWORD *)this + 39) )
                *((_QWORD *)this + 39) = v61;
              v116 = 0;
              if ( v126 )
              {
                while ( !*((_BYTE *)this + 520) )
                {
                  v115 = 0;
                  v62 = *(_OWORD *)((char *)this + 616);
                  v63 = *(_OWORD *)((char *)this + 632);
                  v64 = *(_OWORD *)((char *)this + 648);
                  v65 = *(_OWORD *)((char *)this + 664);
                  v66 = *(_OWORD *)((char *)this + 680);
                  v67 = *(_OWORD *)((char *)this + 696);
                  v68 = *(_OWORD *)((char *)this + 712);
                  v69 = *(_OWORD *)((char *)this + 728);
                  v70 = *((_WORD *)this + 372);
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
                  v72 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                          &v131,
                          (char *)this + 264,
                          v71);
                  *(_OWORD *)Buffer = v62;
                  v151 = v63;
                  v152 = v64;
                  v153 = v65;
                  v154 = v66;
                  v155 = v67;
                  v156 = v68;
                  v157 = v69;
                  v158 = v70;
                  v74 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                          *v41,
                          v116,
                          v72,
                          v73,
                          (__int64)&v115,
                          (__int64)Buffer);
                  if ( v74 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x2F8,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v74,
                      v110);
                    ++v125;
                    goto LABEL_95;
                  }
                  v75 = *((_DWORD *)this + 131);
                  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v115 + 30), 0);
                  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
                    this,
                    StringRawBuffer,
                    v75,
                    100 * v116 / (unsigned int)v126);
                  LOBYTE(v77) = 1;
                  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                    (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                    v77,
                    0);
                  v78 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(
                          v115,
                          0,
                          (__int64)this + 280,
                          (ULONGLONG)v60,
                          &v134);
                  if ( !v134 )
                  {
                    v5 = v5 + *(double *)(208LL * v120 + *v60 + 184);
                    v128 = *(_QWORD *)&v5;
                  }
                  ++v120;
                  if ( v78 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x309,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v78,
                      v111);
                    StorageDeviceInfo = v78;
                    ++v124;
                    goto LABEL_95;
                  }
                  v79 = *((_QWORD *)v115 + 34);
                  v127 = v79;
                  ++v121;
                  if ( v79 )
                  {
                    v129 += v79;
                    ++v123;
                    v117 = 0;
                    v80 = v116;
                    v81 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)*v41 + 72LL))(*v41, v116, &v117);
                    if ( v81 >= 0 )
                    {
                      v83 = v117;
                      if ( v117 )
                        ++v122;
                    }
                    else
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x316,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)v81,
                        v111);
                      v83 = v117;
                    }
                    LOBYTE(v82) = v83 != 0;
                    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsItemChecked(
                      (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                      v80,
                      v82);
                    v118 = 0;
                    Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
                             *((_QWORD *)this + 74),
                             &v118);
                    if ( Size < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x31E,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)Size,
                        v111);
                      goto LABEL_90;
                    }
                    v86 = 0;
                    if ( !v118 )
                    {
LABEL_88:
                      LOBYTE(v85) = 1;
                      Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                        *((_QWORD *)this + 74),
                        0,
                        v115,
                        v85);
                      goto LABEL_89;
                    }
                    while ( 1 )
                    {
                      *(_QWORD *)v119 = 0;
                      v87 = *((_QWORD *)this + 74);
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v119);
                      v88 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                              v87,
                              v86,
                              v119);
                      if ( v88 >= 0 )
                      {
                        if ( *(_QWORD *)(*(_QWORD *)v119 + 272LL) < v127 )
                        {
                          Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                            *((_QWORD *)this + 74),
                            v86,
                            v115,
                            0);
                          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v119);
LABEL_89:
                          SystemSettings::DataModel::CSettingBase::OnValueChanged(
                            this,
                            (const unsigned __int16 *)&stru_18010EDA8);
                          v60 = (_QWORD *)((char *)this + 304);
LABEL_90:
                          SystemSettings::DataModel::CSettingBase::OnValueChanged(
                            this,
                            (const unsigned __int16 *)&stru_180107F20);
                          if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                                                  *((unsigned int *)this + 94),
                                                  *((unsigned int *)this + 95)) )
                          {
                            v89 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
                            *(_QWORD *)v119 = v115;
                            v90 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListItemLoaded,SystemSettings::StorageSenseHandlers::CStorageCleanupItem *,int &>(
                                                             v141,
                                                             v119,
                                                             &v117);
                            *(_OWORD *)v130 = 0;
                            v130[0] = *v90;
                            v130[1] = v90[1];
                            *v90 = 0;
                            v90[1] = 0;
                            *(_QWORD *)v119 = v130;
                            SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
                              v89,
                              v119);
                            if ( v130[1] )
                              std::_Ref_count_base::_Decref(v130[1]);
                            if ( v141[1] )
                              std::_Ref_count_base::_Decref(v141[1]);
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
                          (const char *)(unsigned int)v88,
                          v111);
                      }
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v119);
                      if ( ++v86 >= v118 )
                        goto LABEL_88;
                    }
                  }
LABEL_95:
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
                  if ( ++v116 >= v126 )
                    goto LABEL_99;
                }
                *((_BYTE *)this + 520) = 0;
                *((_WORD *)this + 253) = 256;
                *((_DWORD *)this + 132) = 1;
                v112 = 1;
              }
LABEL_99:
              SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
                this,
                0,
                *((unsigned int *)this + 131),
                100);
              if ( !*((_BYTE *)this + 507) )
              {
                LOBYTE(v91) = 1;
                SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                  (char *)&unk_18018A990 + 272 * *((int *)this + 96),
                  v91,
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
        v55 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v54 + 24LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 600);
        v52 = v55(v54, (char *)this + 600);
        v53 = retaddr;
        if ( v52 >= 0 )
          goto LABEL_57;
      }
      wil::details::in1diag3::_Log_Hr(
        v53,
        (void *)0x2BC,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
        (const char *)(unsigned int)v52,
        v108);
      goto LABEL_56;
    }
    LastError = GetLastError();
    StorageDeviceInfo = LastError;
    if ( LastError > 0 )
      StorageDeviceInfo = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_104:
  *(_OWORD *)Buffer = *(_OWORD *)v9;
  v151 = *((_OWORD *)v9 + 1);
  v152 = *((_OWORD *)v9 + 2);
  v153 = *((_OWORD *)v9 + 3);
  v154 = *((_OWORD *)v9 + 4);
  v155 = *((_OWORD *)v9 + 5);
  v156 = *((_OWORD *)v9 + 6);
  v157 = *((_OWORD *)v9 + 7);
  v158 = *((_WORD *)v9 + 64);
  v92 = v120;
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Stop(
    v12,
    (char *)this + 488,
    v129,
    (unsigned int)StorageDeviceInfo,
    v126,
    v125,
    v120,
    v121,
    v124,
    v123,
    v122,
    v8,
    (char *)this + 392);
  v93 = (char **)((char *)this + 280);
  v94 = v128;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3) )
  {
    LOWORD(v117) = 14247 * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3);
    v95 = SettingsHandlersStorageSenseLogging::Provider();
    v97 = v95;
    if ( *(_DWORD *)v95 && (unsigned __int8)tlgKeywordOn(v95, 0x400000000000LL) )
    {
      v144 = *v93;
      v145 = 184 * (unsigned __int16)v117;
      v141[0] = (std::_Ref_count_base *)&v117;
      LODWORD(v141[1]) = 2;
      v128 = (__int64)this + 617;
      v139 = (char *)*((_QWORD *)this + 62);
      v131 = (char *)this + 392;
      LOWORD(v132) = 12;
      v113 = v112;
      v114[0] = v8;
      v140 = v94;
      v121 = v122;
      v118 = v123;
      v120 = v124;
      LODWORD(v127) = v92;
      *(_DWORD *)v119 = v125;
      v136 = v126;
      LOWORD(v116) = v117;
      v137 = v134;
      LODWORD(v115) = StorageDeviceInfo;
      v138 = v129;
      v130[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 488);
      v133[0] = (std::_Ref_count_base *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v97,
        (unsigned int)&unk_180153733,
        (_DWORD)v97,
        v98,
        (__int64)v133,
        (__int64)v130,
        (__int64)&v138,
        (__int64)&v115,
        (__int64)&v137,
        (__int64)&v116,
        (__int64)&v136,
        (__int64)v119,
        (__int64)&v127,
        (__int64)&v120,
        (__int64)&v118,
        (__int64)&v121,
        (__int64)&v140,
        (__int64)v114,
        (__int64)&v113,
        (__int64)&v131,
        (__int64)&v139,
        (__int64)&v128,
        (__int64)v141,
        (__int64)&v144);
    }
    if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 36) )
      *((_QWORD *)this + 36) = *v93;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart>::shrink_to_fit((char *)this + 280, v96, v97);
  }
  v99 = (char **)((char *)this + 304);
  if ( 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4) )
  {
    LOWORD(v117) = 20165 * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4);
    v100 = SettingsHandlersStorageSenseLogging::Provider();
    v102 = v100;
    if ( *(_DWORD *)v100 && (unsigned __int8)tlgKeywordOn(v100, 0x400000000000LL) )
    {
      v131 = *v99;
      LODWORD(v132) = 208 * (unsigned __int16)v117;
      v141[0] = (std::_Ref_count_base *)&v117;
      LODWORD(v141[1]) = 2;
      v133[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 617);
      v130[0] = *((std::_Ref_count_base **)this + 62);
      v144 = (char *)this + 392;
      LOWORD(v145) = 12;
      v114[0] = v112;
      v113 = v8;
      v138 = v94;
      LODWORD(v115) = v122;
      *(_DWORD *)v119 = v123;
      LODWORD(v127) = v124;
      v121 = v92;
      v118 = v125;
      v137 = v126;
      LOWORD(v116) = v117;
      v136 = v134;
      v120 = StorageDeviceInfo;
      v140 = v129;
      v139 = (char *)this + 488;
      v128 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v102,
        (unsigned int)&unk_180153556,
        (_DWORD)v102,
        v103,
        (__int64)&v128,
        (__int64)&v139,
        (__int64)&v140,
        (__int64)&v120,
        (__int64)&v136,
        (__int64)&v116,
        (__int64)&v137,
        (__int64)&v118,
        (__int64)&v121,
        (__int64)&v127,
        (__int64)v119,
        (__int64)&v115,
        (__int64)&v138,
        (__int64)&v113,
        (__int64)v114,
        (__int64)&v144,
        (__int64)v130,
        (__int64)v133,
        (__int64)v141,
        (__int64)&v131);
    }
    if ( *((_QWORD *)this + 38) != *((_QWORD *)this + 39) )
      *((_QWORD *)this + 39) = *v99;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop>::shrink_to_fit((char *)this + 304, v101, v102);
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
    v104);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111DC8);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    v105 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v106 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationFinished,>(&v131);
    *(_OWORD *)v130 = 0;
    v130[0] = *v106;
    v130[1] = v106[1];
    *v106 = 0;
    v106[1] = 0;
    v133[0] = (std::_Ref_count_base *)v130;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      v105,
      v133);
    if ( v130[1] )
      std::_Ref_count_base::_Decref(v130[1]);
    if ( v132 )
      std::_Ref_count_base::_Decref(v132);
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::~StorageSenseScan((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan *)v147);
LABEL_124:
  std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>::_Free_non_head<std::allocator<std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>>>(
    v7,
    v135[0]);
  return std::_Deallocate<16>(v135[0], 40);
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
