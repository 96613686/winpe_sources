# SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::DoGetValueAsyncWork(void)

- ea: `0x1800898d0`
- end: `0x18008abee`
- name: `?DoGetValueAsyncWork@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAXXZ`
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
- `0x1800898d0`
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

- `ntdll!RtlInitializeCorrelationVector` at `0x180089a78`
- `ntdll!RtlInitializeCorrelationVector` at `0x180089a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b12`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180089a5c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180089a5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a210`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180089de8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008a579`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180089de8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008a579`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180089b08`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180089b08`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008aac6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008aac6`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180089b44`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180089b44`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180089acf`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180089acf`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180089ef3`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180089fbc`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180089ef3`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180089fbc`

## string_xrefs

- `0x1800899ee`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`
- `0x180089c19`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`
- `0x180089eb6`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\tempcleanup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::DoGetValueAsyncWork(
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
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
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
  __int64 *v56; // rax
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
  int v107; // [rsp+28h] [rbp-120h]
  int v108; // [rsp+28h] [rbp-120h]
  int v109; // [rsp+28h] [rbp-120h]
  int v110; // [rsp+28h] [rbp-120h]
  char v111; // [rsp+C8h] [rbp-80h]
  char v112; // [rsp+C9h] [rbp-7Fh] BYREF
  _BYTE v113[6]; // [rsp+CAh] [rbp-7Eh] BYREF
  SystemSettings::DataModel::CSettingBase *v114; // [rsp+D0h] [rbp-78h] BYREF
  unsigned int v115; // [rsp+D8h] [rbp-70h] BYREF
  int v116; // [rsp+DCh] [rbp-6Ch] BYREF
  unsigned int v117; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int16 v118[4]; // [rsp+E8h] [rbp-60h] BYREF
  unsigned int v119; // [rsp+F0h] [rbp-58h] BYREF
  unsigned int v120; // [rsp+F4h] [rbp-54h] BYREF
  unsigned int v121; // [rsp+F8h] [rbp-50h]
  unsigned int v122; // [rsp+FCh] [rbp-4Ch]
  unsigned int v123; // [rsp+100h] [rbp-48h]
  unsigned int v124; // [rsp+104h] [rbp-44h]
  void *v125; // [rsp+108h] [rbp-40h] BYREF
  unsigned __int64 v126; // [rsp+110h] [rbp-38h] BYREF
  __int64 v127; // [rsp+118h] [rbp-30h] BYREF
  __int64 v128; // [rsp+120h] [rbp-28h]
  std::_Ref_count_base *v129[2]; // [rsp+128h] [rbp-20h] BYREF
  char *v130; // [rsp+138h] [rbp-10h] BYREF
  std::_Ref_count_base *v131; // [rsp+140h] [rbp-8h]
  std::_Ref_count_base *v132[2]; // [rsp+148h] [rbp+0h] BYREF
  __int64 v133; // [rsp+158h] [rbp+10h] BYREF
  void *v134[2]; // [rsp+160h] [rbp+18h] BYREF
  __int64 v135; // [rsp+170h] [rbp+28h] BYREF
  __int64 v136; // [rsp+178h] [rbp+30h] BYREF
  __int64 v137; // [rsp+180h] [rbp+38h] BYREF
  char *v138; // [rsp+188h] [rbp+40h] BYREF
  __int64 v139; // [rsp+190h] [rbp+48h] BYREF
  std::_Ref_count_base *v140[2]; // [rsp+198h] [rbp+50h] BYREF
  __int64 v141; // [rsp+1A8h] [rbp+60h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B8h] [rbp+70h] BYREF
  char *v143; // [rsp+1C0h] [rbp+78h] BYREF
  int v144; // [rsp+1C8h] [rbp+80h]
  GUID pguid; // [rsp+1D0h] [rbp+88h] BYREF
  _BYTE v146[336]; // [rsp+1E8h] [rbp+A0h] BYREF
  WCHAR szVolumePathName[2]; // [rsp+338h] [rbp+1F0h] BYREF
  unsigned __int16 v148[558]; // [rsp+33Ch] [rbp+1F4h] BYREF
  WCHAR Buffer[8]; // [rsp+798h] [rbp+650h] BYREF
  __int128 v150; // [rsp+7A8h] [rbp+660h]
  __int128 v151; // [rsp+7B8h] [rbp+670h]
  __int128 v152; // [rsp+7C8h] [rbp+680h]
  __int128 v153; // [rsp+7D8h] [rbp+690h]
  __int128 v154; // [rsp+7E8h] [rbp+6A0h]
  __int128 v155; // [rsp+7F8h] [rbp+6B0h]
  __int128 v156; // [rsp+808h] [rbp+6C0h]
  __int16 v157; // [rsp+818h] [rbp+6D0h]
  wil::details::in1diag3 *retaddr; // [rsp+A90h] [rbp+948h]

  v2 = 0;
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    Instance = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v4 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationStarted,>(&v130);
    *(_OWORD *)v132 = 0;
    v132[0] = *v4;
    v132[1] = v4[1];
    *v4 = 0;
    v4[1] = 0;
    v127 = (__int64)v132;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      Instance,
      &v127);
    if ( v132[1] )
      std::_Ref_count_base::_Decref(v132[1]);
    if ( v131 )
      std::_Ref_count_base::_Decref(v131);
  }
  std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>(v134);
  v133 = 0;
  v125 = 0;
  v5 = 0.0;
  v127 = 0;
  v6 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 74));
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
      (const char *)(unsigned int)v6,
      v107);
    goto LABEL_124;
  }
  v128 = 0;
  v119 = 0;
  v120 = 0;
  v122 = 0;
  v123 = 0;
  v121 = 0;
  v124 = 0;
  v8 = 0;
  v111 = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
  memset_0((char *)this + 392, -1, 0x60u);
  pguid = 0;
  CoCreateGuid(&pguid);
  v9 = (char *)this + 616;
  RtlInitializeCorrelationVector((char *)this + 616, 2, &pguid);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Start<CORRELATION_VECTOR &>(v146);
  v10 = (unsigned int **)((char *)this + 264);
  v11 = (unsigned int *)*((_QWORD *)this + 33);
  if ( v11 && (*v11 || v11[1]) )
  {
    memset_0(v148, 0, 0x454u);
    wcscpy(szVolumePathName, L"ј");
    StorageDeviceInfo = GetStorageDeviceInfo(*v11, v11[1], szVolumePathName);
    if ( StorageDeviceInfo >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)this + 244, 4u, v148);
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
        &qword_18018A990[34 * *((int *)this + 96)],
        v15,
        0);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111EA8);
      *(_WORD *)((char *)this + 505) = 0;
      *((_BYTE *)this + 507) = 0;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
      if ( !IsDesktopSKU() )
      {
        v117 = 0;
        v16 = *v10;
        if ( *v10 )
        {
          v2 = *v16;
          v115 = v16[1];
          v9 = (char *)this + 616;
        }
        else
        {
          v115 = 0;
        }
        SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::GetCleanupHandlers(v134);
        v125 = v134[1];
        SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v17);
        v18 = v134[0];
        v19 = *(_QWORD **)v134[0];
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
          v114 = 0;
          v126 = 0;
          *(_QWORD *)v118 = 0;
          v20 = *(_OWORD *)v9;
          v21 = *((_OWORD *)v9 + 1);
          v22 = *((_OWORD *)v9 + 2);
          v23 = *((_OWORD *)v9 + 3);
          v24 = *((_OWORD *)v9 + 4);
          v25 = *((_OWORD *)v9 + 5);
          v26 = *((_OWORD *)v9 + 6);
          v27 = *((_OWORD *)v9 + 7);
          v28 = *((_WORD *)v9 + 64);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v114);
          v29 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                  &v130,
                  (char *)this + 264,
                  *((unsigned int *)this + 96));
          *(_OWORD *)Buffer = v20;
          v150 = v21;
          v151 = v22;
          v152 = v23;
          v153 = v24;
          v154 = v25;
          v155 = v26;
          v156 = v27;
          v157 = v28;
          *(_OWORD *)v140 = *((_OWORD *)v19 + 1);
          v141 = v19[4];
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                        (unsigned int)v140,
                        v29,
                        v30,
                        (unsigned int)&v114,
                        (__int64)Buffer);
          v32 = retaddr;
          if ( refreshed < 0 )
            break;
          refreshed = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v114, 0, 0, 0, 0);
          v32 = retaddr;
          if ( refreshed < 0 )
          {
            v33 = 608;
            goto LABEL_27;
          }
          refreshed = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, _QWORD))(*(_QWORD *)v114 + 216LL))(
                        v114,
                        0);
          v32 = retaddr;
          if ( refreshed < 0 )
          {
            v33 = 609;
            goto LABEL_27;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            v118,
            0);
          StorageDeviceInfo = SystemSettings::DataModel::GetResourceStringById(
                                (SystemSettings::DataModel *)v19[2],
                                v118,
                                v36);
          if ( StorageDeviceInfo < 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
              v118,
              v37,
              v38);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v126);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v114);
            goto LABEL_103;
          }
          ++v117;
          SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
            this,
            *(_QWORD *)v118,
            *((unsigned int *)this + 131),
            100 * v117 / (unsigned int)v125);
          LOBYTE(v39) = 1;
          SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
            &qword_18018A990[34 * *((int *)this + 96)],
            v39,
            0);
          Sleep(0xC8u);
          v128 += *((_QWORD *)v114 + 34);
          if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::ShowSubCategory(
                                  v2,
                                  v115,
                                  *((unsigned int *)v19 + 8)) )
          {
            LOBYTE(v40) = 1;
            Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 74),
              0,
              v114,
              v40);
            SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
          }
LABEL_35:
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
            v118,
            v34,
            v35);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v126);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v114);
          v19 = (_QWORD *)*v19;
          v18 = v134[0];
          v9 = (char *)this + 616;
        }
        v33 = 607;
LABEL_27:
        wil::details::in1diag3::_Log_Hr(
          v32,
          (void *)v33,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
          (const char *)(unsigned int)refreshed,
          v108);
        goto LABEL_35;
      }
      v41 = (_QWORD *)((char *)this + 600);
      if ( *((_QWORD *)this + 75) )
        goto LABEL_60;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MoveAdminCleanupToTempFilesMainPage>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MoveAdminCleanupToTempFilesMainPage>::GetImpl'::`2'::impl) )
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
          v107);
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
            v56 = (__int64 *)Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CleanmgrHelper,>(&v114);
            Microsoft::WRL::ComPtr<ICleanmgrHelper>::operator=<SystemSettings::StorageSenseHandlers::CleanmgrHelper>(
              (__int64 *)this + 75,
              v56);
            if ( v114 )
            {
              v114 = 0;
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
                v107);
            v8 = v58 >= 0;
            StorageDeviceInfo = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v41 + 32LL))(*v41, &v125);
            if ( StorageDeviceInfo >= 0 )
            {
              v59 = *((_QWORD *)this + 35);
              if ( v59 != *((_QWORD *)this + 36) )
                *((_QWORD *)this + 36) = v59;
              v60 = (_QWORD *)((char *)this + 304);
              v61 = *((_QWORD *)this + 38);
              if ( v61 != *((_QWORD *)this + 39) )
                *((_QWORD *)this + 39) = v61;
              v115 = 0;
              if ( v125 )
              {
                while ( !*((_BYTE *)this + 520) )
                {
                  v114 = 0;
                  v62 = *(_OWORD *)((char *)this + 616);
                  v63 = *(_OWORD *)((char *)this + 632);
                  v64 = *(_OWORD *)((char *)this + 648);
                  v65 = *(_OWORD *)((char *)this + 664);
                  v66 = *(_OWORD *)((char *)this + 680);
                  v67 = *(_OWORD *)((char *)this + 696);
                  v68 = *(_OWORD *)((char *)this + 712);
                  v69 = *(_OWORD *)((char *)this + 728);
                  v70 = *((_WORD *)this + 372);
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v114);
                  v72 = std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
                          &v130,
                          (char *)this + 264,
                          v71);
                  *(_OWORD *)Buffer = v62;
                  v150 = v63;
                  v151 = v64;
                  v152 = v65;
                  v153 = v66;
                  v154 = v67;
                  v155 = v68;
                  v156 = v69;
                  v157 = v70;
                  v74 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(
                          *v41,
                          v115,
                          v72,
                          v73,
                          (__int64)&v114,
                          (__int64)Buffer);
                  if ( v74 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x2F8,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v74,
                      v109);
                    ++v124;
                    goto LABEL_95;
                  }
                  v75 = *((_DWORD *)this + 131);
                  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v114 + 30), 0);
                  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
                    this,
                    StringRawBuffer,
                    v75,
                    100 * v115 / (unsigned int)v125);
                  LOBYTE(v77) = 1;
                  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                    &qword_18018A990[34 * *((int *)this + 96)],
                    v77,
                    0);
                  v78 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(
                          v114,
                          0,
                          (_QWORD *)this + 35,
                          (ULONGLONG)v60,
                          &v133);
                  if ( !v133 )
                  {
                    v5 = v5 + *(double *)(208LL * v119 + *v60 + 184);
                    v127 = *(_QWORD *)&v5;
                  }
                  ++v119;
                  if ( v78 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x309,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                      (const char *)(unsigned int)v78,
                      v110);
                    StorageDeviceInfo = v78;
                    ++v123;
                    goto LABEL_95;
                  }
                  v79 = *((_QWORD *)v114 + 34);
                  v126 = v79;
                  ++v120;
                  if ( v79 )
                  {
                    v128 += v79;
                    ++v122;
                    v116 = 0;
                    v80 = v115;
                    v81 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)*v41 + 72LL))(*v41, v115, &v116);
                    if ( v81 >= 0 )
                    {
                      v83 = v116;
                      if ( v116 )
                        ++v121;
                    }
                    else
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x316,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)v81,
                        v110);
                      v83 = v116;
                    }
                    LOBYTE(v82) = v83 != 0;
                    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsItemChecked(
                      &qword_18018A990[34 * *((int *)this + 96)],
                      v80,
                      v82);
                    v117 = 0;
                    Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
                             *((_QWORD *)this + 74),
                             &v117);
                    if ( Size < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x31E,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\tempcleanup.cpp",
                        (const char *)(unsigned int)Size,
                        v110);
                      goto LABEL_90;
                    }
                    v86 = 0;
                    if ( !v117 )
                    {
LABEL_88:
                      LOBYTE(v85) = 1;
                      Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                        *((_QWORD *)this + 74),
                        0,
                        v114,
                        v85);
                      goto LABEL_89;
                    }
                    while ( 1 )
                    {
                      *(_QWORD *)v118 = 0;
                      v87 = *((_QWORD *)this + 74);
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v118);
                      v88 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                              v87,
                              v86,
                              v118);
                      if ( v88 >= 0 )
                      {
                        if ( *(_QWORD *)(*(_QWORD *)v118 + 272LL) < v126 )
                        {
                          Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                            *((_QWORD *)this + 74),
                            v86,
                            v114,
                            0);
                          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v118);
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
                            *(_QWORD *)v118 = v114;
                            v90 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListItemLoaded,SystemSettings::StorageSenseHandlers::CStorageCleanupItem *,int &>(
                                                             v140,
                                                             v118,
                                                             &v116);
                            *(_OWORD *)v129 = 0;
                            v129[0] = *v90;
                            v129[1] = v90[1];
                            *v90 = 0;
                            v90[1] = 0;
                            *(_QWORD *)v118 = v129;
                            SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
                              v89,
                              v118);
                            if ( v129[1] )
                              std::_Ref_count_base::_Decref(v129[1]);
                            if ( v140[1] )
                              std::_Ref_count_base::_Decref(v140[1]);
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
                          v110);
                      }
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v118);
                      if ( ++v86 >= v117 )
                        goto LABEL_88;
                    }
                  }
LABEL_95:
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v114);
                  if ( ++v115 >= (unsigned __int64)v125 )
                    goto LABEL_99;
                }
                *((_BYTE *)this + 520) = 0;
                *((_WORD *)this + 253) = 256;
                *((_DWORD *)this + 132) = 1;
                v111 = 1;
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
                  &qword_18018A990[34 * *((int *)this + 96)],
                  v91,
                  0);
                Sleep(0xC8u);
              }
              *((_BYTE *)this + 505) = 1;
              *((_DWORD *)this + 131) = 0;
              SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
                &qword_18018A990[34 * *((int *)this + 96)],
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
        v107);
      goto LABEL_56;
    }
    LastError = GetLastError();
    StorageDeviceInfo = LastError;
    if ( LastError > 0 )
      StorageDeviceInfo = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_104:
  *(_OWORD *)Buffer = *(_OWORD *)v9;
  v150 = *((_OWORD *)v9 + 1);
  v151 = *((_OWORD *)v9 + 2);
  v152 = *((_OWORD *)v9 + 3);
  v153 = *((_OWORD *)v9 + 4);
  v154 = *((_OWORD *)v9 + 5);
  v155 = *((_OWORD *)v9 + 6);
  v156 = *((_OWORD *)v9 + 7);
  v157 = *((_WORD *)v9 + 64);
  v92 = v119;
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Stop(
    v12,
    (char *)this + 488,
    v128,
    (unsigned int)StorageDeviceInfo,
    v125,
    v124,
    v119,
    v120,
    v123,
    v122,
    v121,
    v8,
    (char *)this + 392);
  v93 = (char **)((char *)this + 280);
  v94 = v127;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3) )
  {
    LOWORD(v116) = 14247 * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3);
    v95 = SettingsHandlersStorageSenseLogging::Provider();
    v97 = v95;
    if ( *(_DWORD *)v95 && (unsigned __int8)tlgKeywordOn(v95, 0x400000000000LL) )
    {
      v143 = *v93;
      v144 = 184 * (unsigned __int16)v116;
      v140[0] = (std::_Ref_count_base *)&v116;
      LODWORD(v140[1]) = 2;
      v127 = (__int64)this + 617;
      v138 = (char *)*((_QWORD *)this + 62);
      v130 = (char *)this + 392;
      LOWORD(v131) = 12;
      v112 = v111;
      v113[0] = v8;
      v139 = v94;
      v120 = v121;
      v117 = v122;
      v119 = v123;
      LODWORD(v126) = v92;
      *(_DWORD *)v118 = v124;
      v135 = (__int64)v125;
      LOWORD(v115) = v116;
      v136 = v133;
      LODWORD(v114) = StorageDeviceInfo;
      v137 = v128;
      v129[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 488);
      v132[0] = (std::_Ref_count_base *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v97,
        (unsigned int)&unk_180154140,
        (_DWORD)v97,
        v98,
        (__int64)v132,
        (__int64)v129,
        (__int64)&v137,
        (__int64)&v114,
        (__int64)&v136,
        (__int64)&v115,
        (__int64)&v135,
        (__int64)v118,
        (__int64)&v126,
        (__int64)&v119,
        (__int64)&v117,
        (__int64)&v120,
        (__int64)&v139,
        (__int64)v113,
        (__int64)&v112,
        (__int64)&v130,
        (__int64)&v138,
        (__int64)&v127,
        (__int64)v140,
        (__int64)&v143);
    }
    if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 36) )
      *((_QWORD *)this + 36) = *v93;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart>::shrink_to_fit((char *)this + 280, v96, v97);
  }
  v99 = (char **)((char *)this + 304);
  if ( 0x4EC4EC4EC4EC4EC5LL * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4) )
  {
    LOWORD(v116) = 20165 * ((__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4);
    v100 = SettingsHandlersStorageSenseLogging::Provider();
    v102 = v100;
    if ( *(_DWORD *)v100 && (unsigned __int8)tlgKeywordOn(v100, 0x400000000000LL) )
    {
      v130 = *v99;
      LODWORD(v131) = 208 * (unsigned __int16)v116;
      v140[0] = (std::_Ref_count_base *)&v116;
      LODWORD(v140[1]) = 2;
      v132[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 617);
      v129[0] = *((std::_Ref_count_base **)this + 62);
      v143 = (char *)this + 392;
      LOWORD(v144) = 12;
      v113[0] = v111;
      v112 = v8;
      v137 = v94;
      LODWORD(v114) = v121;
      *(_DWORD *)v118 = v122;
      LODWORD(v126) = v123;
      v120 = v92;
      v117 = v124;
      v136 = (__int64)v125;
      LOWORD(v115) = v116;
      v135 = v133;
      v119 = StorageDeviceInfo;
      v139 = v128;
      v138 = (char *)this + 488;
      v127 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v102,
        (unsigned int)byte_180153F63,
        (_DWORD)v102,
        v103,
        (__int64)&v127,
        (__int64)&v138,
        (__int64)&v139,
        (__int64)&v119,
        (__int64)&v135,
        (__int64)&v115,
        (__int64)&v136,
        (__int64)&v117,
        (__int64)&v120,
        (__int64)&v126,
        (__int64)v118,
        (__int64)&v114,
        (__int64)&v137,
        (__int64)&v112,
        (__int64)v113,
        (__int64)&v143,
        (__int64)v129,
        (__int64)v132,
        (__int64)v140,
        (__int64)&v130);
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
    v106 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationFinished,>(&v130);
    *(_OWORD *)v129 = 0;
    v129[0] = *v106;
    v129[1] = v106[1];
    *v106 = 0;
    v106[1] = 0;
    v132[0] = (std::_Ref_count_base *)v129;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      v105,
      v132);
    if ( v129[1] )
      std::_Ref_count_base::_Decref(v129[1]);
    if ( v131 )
      std::_Ref_count_base::_Decref(v131);
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::~StorageSenseScan((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan *)v146);
LABEL_124:
  std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>::_Free_non_head<std::allocator<std::_List_node<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,void *>>>(
    v7,
    v134[0]);
  std::_Deallocate<16>(v134[0], 0x28u);
}

```

## disassembly

```asm
0x1800898d0  mov     rax, rsp
0x1800898d3  push    rbp
0x1800898d4  push    rbx
0x1800898d5  push    rsi
0x1800898d6  push    rdi
0x1800898d7  push    r12
0x1800898d9  push    r13
0x1800898db  push    r14
0x1800898dd  push    r15
0x1800898df  lea     rbp, [rax-948h]
0x1800898e6  sub     rsp, 0A48h
0x1800898ed  movaps  xmmword ptr [rax-58h], xmm6
0x1800898f1  movaps  xmmword ptr [rax-68h], xmm7
0x1800898f5  movaps  xmmword ptr [rax-78h], xmm8
0x1800898fa  movaps  xmmword ptr [rax-88h], xmm9
0x180089902  movaps  xmmword ptr [rax-98h], xmm10
0x18008990a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180089912  movaps  xmmword ptr [rax-0B8h], xmm12
0x18008991a  movaps  xmmword ptr [rax-0C8h], xmm13
0x180089922  movaps  xmmword ptr [rax-0D8h], xmm14
0x18008992a  mov     rax, cs:__security_cookie
0x180089931  xor     rax, rsp
0x180089934  mov     [rbp+940h+var_E0], rax
0x18008993b  mov     rsi, rcx
0x18008993e  mov     edx, [rcx+17Ch]
0x180089944  mov     ecx, [rcx+178h]
0x18008994a  call    ?IsSystemVolume@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NW4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(_STORAGE_DEVICE_TYPE,ulong)
0x18008994f  xor     r13d, r13d
0x180089952  test    al, al
0x180089954  jz      short loc_1800899B8
0x180089956  call    ?GetInstance@CStorageCleanupListHandlerSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance(void)
0x18008995b  mov     rbx, rax
0x18008995e  lea     rcx, [rbp+940h+var_950]
0x180089962  call    ??$make_shared@UCleanupListInitializationStarted@StorageSenseHandlers@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@UCleanupListInitializationStarted@StorageSenseHandlers@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListInitializationStarted,>(void)
0x180089967  nop
0x180089968  xorps   xmm0, xmm0
0x18008996b  movdqu  xmmword ptr [rbp+940h+var_940], xmm0
0x180089970  mov     rcx, [rax]
0x180089973  mov     [rbp+940h+var_940], rcx
0x180089977  mov     rcx, [rax+8]
0x18008997b  mov     [rbp+940h+var_940+8], rcx
0x18008997f  mov     [rax], r13
0x180089982  mov     [rax+8], r13
0x180089986  lea     rax, [rbp+940h+var_940]
0x18008998a  mov     [rbp+940h+var_970], rax
0x18008998e  lea     rdx, [rbp+940h+var_970]
0x180089992  mov     rcx, rbx
0x180089995  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x18008999a  nop
0x18008999b  mov     rcx, [rbp+940h+var_940+8]; this
0x18008999f  test    rcx, rcx
0x1800899a2  jz      short loc_1800899AA
0x1800899a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800899a9  nop
0x1800899aa  mov     rcx, [rbp+940h+var_948]; this
0x1800899ae  test    rcx, rcx
0x1800899b1  jz      short loc_1800899B8
0x1800899b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800899b8  lea     rcx, [rbp+940h+var_928]
0x1800899bc  call    ??0?$list@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@V?$allocator@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@@std@@@std@@QEAA@XZ; std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER>(void)
0x1800899c1  nop
0x1800899c2  mov     [rbp+940h+var_930], r13
0x1800899c6  mov     [rbp+940h+var_980], r13
0x1800899ca  xorps   xmm14, xmm14
0x1800899ce  movsd   [rbp+940h+var_970], xmm14
0x1800899d4  mov     rcx, [rsi+250h]
0x1800899db  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x1800899e0  mov     rcx, [rbp+948h]; this
0x1800899e7  test    eax, eax
0x1800899e9  jns     short loc_180089A04
0x1800899eb  mov     r9d, eax; char *
0x1800899ee  lea     r8, aOnecoreuapShel_25; "onecoreuap\\shell\\coresettinghandlers"...
0x1800899f5  mov     edx, 1FCh; void *
0x1800899fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800899ff  jmp     loc_18008AB7D
0x180089a04  mov     [rbp+940h+var_968], r13
0x180089a08  mov     [rbp+940h+var_998], r13d
0x180089a0c  mov     [rbp+940h+var_994], r13d
0x180089a10  mov     [rbp+940h+var_98C], r13d
0x180089a14  mov     [rbp+940h+var_988], r13d
0x180089a18  mov     [rbp+940h+var_990], r13d
0x180089a1c  mov     [rbp+940h+var_984], r13d
0x180089a20  mov     r12b, r13b
0x180089a23  mov     [rbp+940h+var_9C0], r13b
0x180089a27  lea     rdx, stru_18010EDA8; unsigned __int16 *
0x180089a2e  mov     rcx, rsi; this
0x180089a31  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180089a36  lea     rcx, [rsi+188h]; void *
0x180089a3d  mov     r8d, 60h ; '`'; Size
0x180089a43  or      edx, 0FFFFFFFFh; Val
0x180089a46  call    memset_0
0x180089a4b  xorps   xmm0, xmm0
0x180089a4e  movups  xmmword ptr [rbp+940h+pguid.Data1], xmm0
0x180089a55  lea     rcx, [rbp+940h+pguid]; pguid
0x180089a5c  call    cs:__imp_CoCreateGuid
0x180089a62  lea     rdi, [rsi+268h]
0x180089a69  lea     r8, [rbp+940h+pguid]
0x180089a70  mov     edx, 2
0x180089a75  mov     rcx, rdi
0x180089a78  call    cs:__imp_RtlInitializeCorrelationVector
0x180089a7e  lea     rcx, [rbp+940h+var_8A0]
0x180089a85  call    ??$Start@AEAUCORRELATION_VECTOR@@@StorageSenseScan@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@SA?AV01234@AEAUCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseScan::Start<CORRELATION_VECTOR &>(CORRELATION_VECTOR &)
0x180089a8a  nop
0x180089a8b  lea     r15, [rsi+108h]
0x180089a92  mov     rbx, [r15]
0x180089a95  test    rbx, rbx
0x180089a98  jz      short loc_180089AFA
0x180089a9a  cmp     [rbx], r13d
0x180089a9d  jnz     short loc_180089AA5
0x180089a9f  cmp     [rbx+4], r13d
0x180089aa3  jz      short loc_180089AFA
0x180089aa5  xor     edx, edx; Val
0x180089aa7  mov     r8d, 454h; Size
0x180089aad  lea     rcx, [rbp+940h+var_74C]; void *
0x180089ab4  call    memset_0
0x180089ab9  mov     dword ptr [rbp+940h+szVolumePathName], 458h
0x180089ac3  lea     r8, [rbp+940h+szVolumePathName]
0x180089aca  mov     edx, [rbx+4]
0x180089acd  mov     ecx, [rbx]
0x180089acf  call    cs:__imp_GetStorageDeviceInfo
0x180089ad5  mov     r14d, eax
0x180089ad8  test    eax, eax
0x180089ada  js      loc_18008A5DC
0x180089ae0  lea     rcx, [rsi+1E8h]; unsigned __int16 *
0x180089ae7  lea     r8, [rbp+940h+var_74C]; unsigned __int16 *
0x180089aee  mov     edx, 4; unsigned __int64
0x180089af3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180089af8  jmp     short loc_180089B5F
0x180089afa  mov     ebx, 104h
0x180089aff  mov     edx, ebx; uSize
0x180089b01  lea     rcx, [rbp+940h+Buffer]; lpBuffer
0x180089b08  call    cs:__imp_GetWindowsDirectoryW
0x180089b0e  test    eax, eax
0x180089b10  jnz     short loc_180089B33
0x180089b12  call    cs:__imp_GetLastError
0x180089b18  mov     r14d, eax
0x180089b1b  test    eax, eax
0x180089b1d  jle     loc_18008A5DC
0x180089b23  movzx   r14d, ax
0x180089b27  or      r14d, 80070000h
0x180089b2e  jmp     loc_18008A5DC
0x180089b33  mov     r8d, ebx; cchBufferLength
0x180089b36  lea     rdx, [rbp+940h+szVolumePathName]; lpszVolumePathName
0x180089b3d  lea     rcx, [rbp+940h+Buffer]; lpszFileName
0x180089b44  call    cs:__imp_GetVolumePathNameW
0x180089b4a  test    eax, eax
0x180089b4c  jz      short loc_180089B12
0x180089b4e  mov     r14d, r13d
0x180089b51  movzx   eax, [rbp+940h+szVolumePathName]
0x180089b58  mov     [rsi+1E8h], ax
0x180089b5f  mov     ebx, 1
0x180089b64  mov     [rsi+20Ch], rbx
0x180089b6b  xor     r9d, r9d
0x180089b6e  mov     r8d, ebx
0x180089b71  xor     edx, edx
0x180089b73  mov     rcx, rsi
0x180089b76  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x180089b7b  movsxd  rax, dword ptr [rsi+180h]
0x180089b82  imul    rcx, rax, 110h
0x180089b89  lea     rax, qword_18018A990
0x180089b90  add     rcx, rax
0x180089b93  xor     r8d, r8d
0x180089b96  mov     dl, bl
0x180089b98  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x180089b9d  lea     rdx, stru_180111EA8; unsigned __int16 *
0x180089ba4  mov     rcx, rsi; this
0x180089ba7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180089bac  mov     [rsi+1F9h], r13w
0x180089bb4  mov     [rsi+1FBh], r13b
0x180089bbb  lea     rdx, stru_180112038; unsigned __int16 *
0x180089bc2  mov     rcx, rsi; this
0x180089bc5  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180089bca  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x180089bcf  test    al, al
0x180089bd1  jnz     loc_180089EAF
0x180089bd7  mov     [rbp+940h+var_9A8], r13d
0x180089bdb  mov     rax, [r15]
0x180089bde  test    rax, rax
0x180089be1  jz      short loc_180089BF5
0x180089be3  mov     r13d, [rax]
0x180089be6  mov     edi, [rax+4]
0x180089be9  mov     [rbp+940h+var_9B0], edi
0x180089bec  lea     rdi, [rsi+268h]
0x180089bf3  jmp     short loc_180089BFC
0x180089bf5  mov     [rbp+940h+var_9B0], 0
0x180089bfc  lea     rcx, [rbp+940h+var_928]
0x180089c00  call    ?GetCleanupHandlers@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@YAXPEAV?$list@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@V?$allocator@USTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@@std@@@std@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::GetCleanupHandlers(std::list<SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER> *)
0x180089c05  mov     rax, [rbp+940h+var_920]
0x180089c09  mov     [rbp+940h+var_980], rax
0x180089c0d  call    ?RefreshQueries@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(void)
0x180089c12  mov     rax, [rbp+940h+var_928]
0x180089c16  mov     rbx, [rax]
0x180089c19  lea     r15, aOnecoreuapShel_25; "onecoreuap\\shell\\coresettinghandlers"...
0x180089c20  cmp     rbx, rax
0x180089c23  jz      loc_180089EA2
0x180089c29  mov     al, [rsi+208h]
0x180089c2f  nop
0x180089c30  xor     ecx, ecx
0x180089c32  test    al, al
0x180089c34  jnz     loc_180089E87
0x180089c3a  mov     [rbp+940h+var_9B8], rcx
0x180089c3e  mov     [rbp+940h+var_978], rcx
0x180089c42  mov     qword ptr [rbp+940h+var_9A0], rcx
0x180089c46  movups  xmm6, xmmword ptr [rdi]
0x180089c49  movups  xmm7, xmmword ptr [rdi+10h]
0x180089c4d  movups  xmm8, xmmword ptr [rdi+20h]
0x180089c52  movups  xmm9, xmmword ptr [rdi+30h]
0x180089c57  movups  xmm10, xmmword ptr [rdi+40h]
0x180089c5c  movups  xmm11, xmmword ptr [rdi+50h]
0x180089c61  movups  xmm12, xmmword ptr [rdi+60h]
0x180089c66  movups  xmm13, xmmword ptr [rdi+70h]
0x180089c6b  movzx   edi, word ptr [rdi+80h]
0x180089c72  lea     rcx, [rbp+940h+var_9B8]
0x180089c76  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180089c7b  mov     r8d, [rsi+180h]
0x180089c82  lea     rdx, [rsi+108h]
0x180089c89  lea     rcx, [rbp+940h+var_950]
0x180089c8d  call    ??$?0UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@$0A@@?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@QEAA@AEBV?$shared_ptr@UCleanupListOperationProgress@StorageSenseHandlers@SystemSettings@@@1@@Z; std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress> const &)
0x180089c92  movups  xmmword ptr [rbp+940h+Buffer], xmm6
0x180089c99  movups  [rbp+940h+var_2E0], xmm7
0x180089ca0  movups  [rbp+940h+var_2D0], xmm8
0x180089ca8  movups  [rbp+940h+var_2C0], xmm9
0x180089cb0  movups  [rbp+940h+var_2B0], xmm10
0x180089cb8  movups  [rbp+940h+var_2A0], xmm11
0x180089cc0  movups  [rbp+940h+var_290], xmm12
0x180089cc8  movups  [rbp+940h+var_280], xmm13
0x180089cd0  mov     [rbp+940h+var_270], di
0x180089cd7  movups  xmm0, xmmword ptr [rbx+10h]
0x180089cdb  movaps  xmmword ptr [rbp+940h+var_8F0], xmm0
0x180089cdf  movsd   xmm1, qword ptr [rbx+20h]
0x180089ce4  movsd   [rbp+940h+var_8E0], xmm1
0x180089ce9  lea     rcx, [rbp+940h+Buffer]
0x180089cf0  mov     [rsp+0A80h+var_A60], rcx; int
0x180089cf5  lea     r9, [rbp+940h+var_9B8]
0x180089cf9  mov     rdx, rax
0x180089cfc  lea     rcx, [rbp+940h+var_8F0]
0x180089d00  call    ?CreateInstance@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@SAJUSTORAGE_CLEANUP_PROVIDER@StorageSenseCategoriesEx@23@V?$shared_ptr@UStorageSenseAdvPageInfo@StorageSenseHandlers@SystemSettings@@@std@@W4CleanupSingletonKind@23@PEAPEAV123@UCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::CreateInstance(SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::STORAGE_CLEANUP_PROVIDER,std::shared_ptr<SystemSettings::StorageSenseHandlers::StorageSenseAdvPageInfo>,SystemSettings::StorageSenseHandlers::CleanupSingletonKind,SystemSettings::StorageSenseHandlers::CStorageCleanupItem * *,CORRELATION_VECTOR)
0x180089d05  mov     rcx, [rbp+948h]; this
0x180089d0c  test    eax, eax
0x180089d0e  jns     short loc_180089D25
0x180089d10  mov     edx, 25Fh; void *
0x180089d15  mov     r9d, eax; char *
0x180089d18  mov     r8, r15; unsigned int
0x180089d1b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180089d20  jmp     loc_180089E35
0x180089d25  mov     [rsp+0A80h+var_A60], 0; __int64
0x180089d2e  xor     r9d, r9d
0x180089d31  xor     r8d, r8d
0x180089d34  xor     edx, edx
0x180089d36  mov     rcx, [rbp+940h+var_9B8]; this
0x180089d3a  call    ?RefreshSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4CleanupItemSizeRefreshOperationKind@23@PEAV?$vector@UPluginScanStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginScanStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(SystemSettings::StorageSenseHandlers::CleanupItemSizeRefreshOperationKind,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart> *,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop> *,unsigned __int64 *)
0x180089d3f  mov     rcx, [rbp+948h]
0x180089d46  test    eax, eax
0x180089d48  jns     short loc_180089D51
0x180089d4a  mov     edx, 260h
0x180089d4f  jmp     short loc_180089D15
0x180089d51  mov     rcx, [rbp+940h+var_9B8]
0x180089d55  mov     rax, [rcx]
0x180089d58  xor     edx, edx
0x180089d5a  mov     rax, [rax+0D8h]
0x180089d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d66  mov     rcx, [rbp+948h]
0x180089d6d  test    eax, eax
0x180089d6f  jns     short loc_180089D78
0x180089d71  mov     edx, 261h
0x180089d76  jmp     short loc_180089D15
0x180089d78  xor     edx, edx
0x180089d7a  lea     rcx, [rbp+940h+var_9A0]
0x180089d7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180089d83  lea     rdx, [rbp+940h+var_9A0]; unsigned __int16 *
0x180089d87  mov     rcx, [rbx+10h]; this
0x180089d8b  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180089d90  mov     r14d, eax
0x180089d93  test    eax, eax
0x180089d95  js      loc_180089E65
0x180089d9b  mov     edi, [rbp+940h+var_9A8]
0x180089d9e  inc     edi
0x180089da0  mov     [rbp+940h+var_9A8], edi
0x180089da3  imul    eax, edi, 64h ; 'd'
0x180089da6  xor     edx, edx
0x180089da8  div     dword ptr [rbp+940h+var_980]
0x180089dab  mov     r9d, eax
0x180089dae  mov     r8d, [rsi+20Ch]
0x180089db5  mov     rdx, qword ptr [rbp+940h+var_9A0]
0x180089db9  mov     rcx, rsi
0x180089dbc  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x180089dc1  movsxd  rax, dword ptr [rsi+180h]
0x180089dc8  imul    rcx, rax, 110h
0x180089dcf  lea     rax, qword_18018A990
0x180089dd6  add     rcx, rax
0x180089dd9  xor     r8d, r8d
0x180089ddc  mov     dl, 1
0x180089dde  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x180089de3  mov     ecx, 0C8h; dwMilliseconds
0x180089de8  call    cs:__imp_Sleep
0x180089dee  mov     rax, [rbp+940h+var_9B8]
0x180089df2  mov     r9, [rax+110h]
0x180089df9  add     [rbp+940h+var_968], r9
0x180089dfd  mov     r8d, [rbx+20h]
0x180089e01  mov     edx, [rbp+940h+var_9B0]
  ... truncated ...
```
