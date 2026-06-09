# SystemSettings::StorageSenseHandlers::CAppOperationSetting::_MoveAppModern(HWND__ *)

- ea: `0x180048354`
- end: `0x180048ccd`
- name: `?_MoveAppModern@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEAUHWND__@@@Z`
- size: `2425`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180043ac0`

## callees

- `0x180001878`
- `0x180001e3c`
- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000e6cc`
- `0x180011280`
- `0x180012a70`
- `0x18001f468`
- `0x18001fe08`
- `0x180035f2c`
- `0x180035fec`
- `0x180036904`
- `0x180036a44`
- `0x180036e00`
- `0x18003c2c0`
- `0x180040200`
- `0x180040c70`
- `0x180044070`
- `0x180044e28`
- `0x180046b50`
- `0x180047628`
- `0x1800479f0`
- `0x180048354`
- `0x1800494c0`
- `0x1800ba7ec`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800486f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004873b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800486f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004873b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004884f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800488fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004884f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800488fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048b73`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004846f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004846f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180048ab8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180048ab8`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::_MoveAppModern(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this,
        HWND a2)
{
  __int64 v4; // r15
  char v5; // si
  const struct _tlgProvider_t *v6; // rax
  SystemSettings::StorageSenseHandlers::CRemovableMediaManager *v7; // rcx
  __int64 v8; // rdx
  int AppRepository; // ebx
  __int64 v10; // r12
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rax
  _OWORD *v13; // rax
  _OWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rax
  _OWORD *v17; // rcx
  __int64 v18; // rdx
  const struct _tlgProvider_t *v19; // rax
  _OWORD *v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // rdx
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 **v29; // rax
  const unsigned __int16 *v30; // rdx
  __int64 *v31; // rax
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, _QWORD, _QWORD, __int64, __int64 *); // rdi
  __int64 v34; // rbx
  __int64 v35; // rax
  const struct _tlgProvider_t *v36; // rax
  __int64 *v37; // rax
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, _QWORD, _QWORD, __int64, __int64 *); // rdi
  __int64 v40; // rbx
  __int64 v41; // rax
  int v42; // ecx
  int v43; // r9d
  __int64 v44; // rcx
  const struct _tlgProvider_t *v45; // rax
  int v46; // edi
  int v47; // r8d
  int v48; // r9d
  const struct _tlgProvider_t *v49; // rax
  _OWORD *v50; // rax
  _OWORD *v51; // rcx
  __int64 v52; // rdx
  PCWSTR v53; // rax
  _OWORD *v54; // rcx
  _OWORD *v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v59; // [rsp+20h] [rbp-E0h]
  unsigned __int64 StringRawBuffer; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v65; // [rsp+78h] [rbp-88h] BYREF
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  unsigned int InstallDrive; // [rsp+88h] [rbp-78h]
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR v71; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v72[1120]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v73[1120]; // [rsp+510h] [rbp+410h] BYREF
  HSTRING v74; // [rsp+970h] [rbp+870h] BYREF
  int v75; // [rsp+978h] [rbp+878h]
  __int128 v76; // [rsp+97Ch] [rbp+87Ch]
  int v77; // [rsp+98Ch] [rbp+88Ch]
  wil::details::in1diag3 *retaddr; // [rsp+9D8h] [rbp+8D8h]

  v62 = 0;
  v69 = 0;
  v68 = 0;
  v64 = 0;
  v63 = 0;
  v4 = 0;
  v70 = 0;
  v66 = *((_QWORD *)this + 31);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v66);
  string = 0;
  v5 = 0;
  InstallDrive = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDrive(
                   *((SystemSettings::StorageSenseHandlers::CPackageSizeSetting **)this + 31),
                   0);
  v6 = SettingsHandlersStorageSenseLogging::Provider();
  if ( *(_DWORD *)v6 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v6,
      byte_180150403,
      0,
      0);
  memset_0(v72, 0, sizeof(v72));
  AppRepository = SystemSettings::StorageSenseHandlers::CRemovableMediaManager::StorageDeviceFromSaveLocation(
                    v7,
                    (const unsigned __int16 *)(*((_QWORD *)this + 35) + 240LL),
                    0,
                    (struct STORAGE_DEVICE_INFO_WITH_TYPE *)v72);
  v10 = 8;
  if ( AppRepository < 0 )
  {
    v11 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v11 > 2u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v11,
        byte_180150339,
        0,
        0);
    goto LABEL_53;
  }
  LOBYTE(v8) = 1;
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*((_QWORD *)this + 31), v8, 0);
  AppRepository = RoInitialize(1);
  if ( AppRepository < 0 )
  {
    v12 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v12 > 2u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v12,
        byte_1801503A3,
        0,
        0);
    goto LABEL_53;
  }
  v5 = 1;
  v13 = v73;
  v14 = v72;
  v15 = 8;
  do
  {
    *v13 = *v14;
    v13[1] = v14[1];
    v13[2] = v14[2];
    v13[3] = v14[3];
    v13[4] = v14[4];
    v13[5] = v14[5];
    v13[6] = v14[6];
    v13[7] = v14[7];
    v13 += 8;
    v14 += 8;
    --v15;
  }
  while ( v15 );
  *v13 = *v14;
  v13[1] = v14[1];
  v13[2] = v14[2];
  v13[3] = v14[3];
  v13[4] = v14[4];
  v13[5] = v14[5];
  if ( (int)SystemSettings::StorageSenseHandlers::CAppOperationSetting::_FindPackageVolume(v14, v73, &v64) < 0 )
  {
    v16 = v73;
    v17 = v72;
    v18 = 8;
    do
    {
      *v16 = *v17;
      v16[1] = v17[1];
      v16[2] = v17[2];
      v16[3] = v17[3];
      v16[4] = v17[4];
      v16[5] = v17[5];
      v16[6] = v17[6];
      v16[7] = v17[7];
      v16 += 8;
      v17 += 8;
      --v18;
    }
    while ( v18 );
    *v16 = *v17;
    v16[1] = v17[1];
    v16[2] = v17[2];
    v16[3] = v17[3];
    v16[4] = v17[4];
    v16[5] = v17[5];
    AppRepository = SystemSettings::StorageSenseHandlers::CAppOperationSetting::_CreateAppRepository(v17, v73, a2);
    if ( AppRepository < 0 )
    {
      v19 = SettingsHandlersStorageSenseLogging::Provider();
      if ( *(_DWORD *)v19 > 2u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v19,
          byte_180150289,
          0,
          0);
      goto LABEL_53;
    }
    v20 = v73;
    v21 = v72;
    v22 = 8;
    do
    {
      *v20 = *v21;
      v20[1] = v21[1];
      v20[2] = v21[2];
      v20[3] = v21[3];
      v20[4] = v21[4];
      v20[5] = v21[5];
      v20[6] = v21[6];
      v20[7] = v21[7];
      v20 += 8;
      v21 += 8;
      --v22;
    }
    while ( v22 );
    *v20 = *v21;
    v20[1] = v21[1];
    v20[2] = v21[2];
    v20[3] = v21[3];
    v20[4] = v21[4];
    v20[5] = v21[5];
    AppRepository = SystemSettings::StorageSenseHandlers::CAppOperationSetting::_FindPackageVolume(v21, v73, &v64);
    if ( AppRepository < 0 )
    {
      v23 = SettingsHandlersStorageSenseLogging::Provider();
      if ( *(_DWORD *)v23 > 2u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v23,
          word_1801502DA,
          0,
          0);
      goto LABEL_53;
    }
  }
  v24 = *((_QWORD *)this + 31);
  v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 48LL);
  WindowsDeleteString(string);
  string = 0;
  v26 = v25(v24, &string);
  AppRepository = v26;
  if ( v26 >= 0 )
  {
    v65 = &v66;
    v29 = (__int64 **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationProgressHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::IDeploymentResult____Windows::Management::Deployment::DeploymentProgress_::___Windows::Foundation::IAsyncOperationWithProgress_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress____Windows::Management::Deployment::DeploymentProgress__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationProgressHandler_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress___lambda_94e70399866f18d209f69adbd9f672ae___1_Windows::Foundation::IAsyncOperationWithProgress_Windows::Management::Deployment::DeploymentResult___Windows::Management::Deployment::DeploymentProgress____Windows::Management::Deployment::DeploymentProgress___lambda_94e70399866f18d209f69adbd9f672ae___(
                        &StringRawBuffer,
                        &v65);
    v65 = *v29;
    *v29 = 0;
    if ( StringRawBuffer )
    {
      StringRawBuffer = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
      &v70,
      &v65);
    if ( v65 )
      (*(void (__fastcall **)(__int64 *))(*v65 + 16))(v65);
    v4 = v70;
    if ( !v70 )
    {
      AppRepository = -2147024882;
      goto LABEL_53;
    }
    if ( *((_BYTE *)this + 273) )
    {
      v37 = (__int64 *)Windows::Internal::StringReference::StringReference(&v74, (const unsigned __int16 (*)[62])v30);
      AppRepository = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
                        *v37,
                        &v69);
      if ( AppRepository < 0 )
      {
        v49 = SettingsHandlersStorageSenseLogging::Provider();
        if ( *(_DWORD *)v49 > 2u )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v49,
            &byte_1801501C7,
            0,
            0);
        goto LABEL_53;
      }
      v38 = v69;
      v39 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v69 + 480LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
      v40 = v64;
      StringRawBuffer = (unsigned __int64)WindowsGetStringRawBuffer(string, 0);
      v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v74, &StringRawBuffer);
      AppRepository = v39(v38, *(_QWORD *)(v41 + 24), 0, v40, &v63);
    }
    else
    {
      v31 = (__int64 *)Windows::Internal::StringReference::StringReference(
                         &v74,
                         L"Windows.Management.Deployment.PackageManager");
      AppRepository = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(
                        *v31,
                        &v68);
      if ( AppRepository < 0 )
      {
        v36 = SettingsHandlersStorageSenseLogging::Provider();
        if ( *(_DWORD *)v36 > 2u )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v36,
            &dword_18015022C,
            0,
            0);
        goto LABEL_53;
      }
      v32 = v68;
      v33 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v68 + 104LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
      v34 = v64;
      StringRawBuffer = (unsigned __int64)WindowsGetStringRawBuffer(string, 0);
      v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v74, &StringRawBuffer);
      AppRepository = v33(v32, *(_QWORD *)(v35 + 24), 0, v34, &v63);
    }
    if ( AppRepository < 0 )
    {
      v62 = 1;
    }
    else
    {
      StringRawBuffer = 0;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 48LL))(v63, v4);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&StringRawBuffer);
      AppRepository = Windows::Management::Deployment::WaitForDeploymentOperation(
                        v42,
                        v63,
                        0,
                        v43,
                        (__int64)&StringRawBuffer);
      if ( StringRawBuffer )
        (*(void (__fastcall **)(unsigned __int64, int *))(*(_QWORD *)StringRawBuffer + 64LL))(StringRawBuffer, &v62);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&StringRawBuffer);
      if ( AppRepository >= 0 )
      {
        SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDrive(
          *((SystemSettings::StorageSenseHandlers::CPackageSizeSetting **)this + 31),
          1);
        v76 = 0;
        v77 = 0;
        v75 = 5;
        v74 = (HSTRING)*((_QWORD *)this + 31);
        StringRawBuffer = (unsigned __int64)&v74;
        SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::Notify(
          v44,
          &StringRawBuffer);
        goto LABEL_49;
      }
    }
    v45 = SettingsHandlersStorageSenseLogging::Provider();
    v46 = (int)v45;
    if ( *(_DWORD *)v45 > 2u )
    {
      LODWORD(v65) = v62;
      LODWORD(StringRawBuffer) = AppRepository;
      v71 = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v46,
        (unsigned int)byte_180150171,
        v47,
        v48,
        (__int64)&v71,
        (__int64)&StringRawBuffer,
        (__int64)&v65);
    }
LABEL_49:
    v5 = 1;
    if ( AppRepository >= 0 )
    {
LABEL_54:
      SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(*((_QWORD *)this + 31), 0, 0);
      if ( v5 )
        RoUninitialize();
      StringRawBuffer = 0;
      SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSize(
        *((SystemSettings::StorageSenseHandlers::CPackageSizeSetting **)this + 31),
        0,
        &StringRawBuffer);
      v50 = v73;
      v51 = v72;
      v52 = 8;
      do
      {
        *v50 = *v51;
        v50[1] = v51[1];
        v50[2] = v51[2];
        v50[3] = v51[3];
        v50[4] = v51[4];
        v50[5] = v51[5];
        v50[6] = v51[6];
        v50[7] = v51[7];
        v50 += 8;
        v51 += 8;
        --v52;
      }
      while ( v52 );
      *v50 = *v51;
      v50[1] = v51[1];
      v50[2] = v51[2];
      v50[3] = v51[3];
      v50[4] = v51[4];
      v50[5] = v51[5];
      v53 = WindowsGetStringRawBuffer(string, 0);
      v54 = v72;
      v55 = v73;
      do
      {
        *v54 = *v55;
        v54[1] = v55[1];
        v54[2] = v55[2];
        v54[3] = v55[3];
        v54[4] = v55[4];
        v54[5] = v55[5];
        v54[6] = v55[6];
        v54[7] = v55[7];
        v54 += 8;
        v55 += 8;
        --v10;
      }
      while ( v10 );
      *v54 = *v55;
      v54[1] = v55[1];
      v54[2] = v55[2];
      v54[3] = v55[3];
      v54[4] = v55[4];
      v54[5] = v55[5];
      SystemSettings::StorageSenseHandlers::CAppOperationSetting::_TraceLoggingAppOperation(
        InstallDrive,
        v53,
        StringRawBuffer);
      WindowsDeleteString(string);
      string = 0;
      v56 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
      v57 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      goto LABEL_66;
    }
LABEL_53:
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, HWND))(**((_QWORD **)this + 31) + 232LL))(
      *((_QWORD *)this + 31),
      (unsigned int)AppRepository,
      0,
      a2);
    goto LABEL_54;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x620,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)(unsigned int)v26,
    v59);
  WindowsDeleteString(string);
  string = 0;
  v27 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
  v28 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
LABEL_66:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v69);
  return (unsigned int)AppRepository;
}

```

## disassembly

```asm
0x180048354  mov     [rsp-8+arg_10], rbx
0x180048359  push    rbp
0x18004835a  push    rsi
0x18004835b  push    rdi
0x18004835c  push    r12
0x18004835e  push    r13
0x180048360  push    r14
0x180048362  push    r15
0x180048364  lea     rbp, [rsp-8A0h]
0x18004836c  sub     rsp, 9A0h
0x180048373  mov     rax, cs:__security_cookie
0x18004837a  xor     rax, rsp
0x18004837d  mov     [rbp+8D0h+var_40], rax
0x180048384  mov     r13, rdx
0x180048387  mov     r14, rcx
0x18004838a  xor     edi, edi
0x18004838c  mov     [rsp+9D0h+var_970], edi
0x180048390  mov     [rbp+8D0h+var_938], rdi
0x180048394  mov     [rbp+8D0h+var_940], rdi
0x180048398  mov     [rsp+9D0h+var_960], rdi
0x18004839d  mov     [rsp+9D0h+var_968], rdi
0x1800483a2  mov     r15d, edi
0x1800483a5  mov     [rbp+8D0h+var_930], rdi
0x1800483a9  mov     rax, [rcx+0F8h]
0x1800483b0  mov     [rbp+8D0h+var_950], rax
0x1800483b4  lea     rcx, [rbp+8D0h+var_950]
0x1800483b8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800483bd  nop
0x1800483be  mov     [rsp+9D0h+string], rdi
0x1800483c3  mov     sil, dil
0x1800483c6  xor     edx, edx; bool
0x1800483c8  mov     rcx, [r14+0F8h]; this
0x1800483cf  call    ?GetInstallDrive@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAH_N@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDrive(bool)
0x1800483d4  mov     [rbp+8D0h+var_948], eax
0x1800483d7  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800483dc  mov     ecx, [rax]
0x1800483de  cmp     ecx, 4
0x1800483e1  jbe     short loc_1800483F8
0x1800483e3  xor     r9d, r9d
0x1800483e6  xor     r8d, r8d
0x1800483e9  lea     rdx, byte_180150403
0x1800483f0  mov     rcx, rax
0x1800483f3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800483f8  xor     edx, edx; Val
0x1800483fa  mov     r8d, 460h; Size
0x180048400  lea     rcx, [rbp+8D0h+var_920]; void *
0x180048404  call    memset_0
0x180048409  mov     rdx, [r14+118h]
0x180048410  add     rdx, 0F0h; unsigned __int16 *
0x180048417  lea     r9, [rbp+8D0h+var_920]; struct STORAGE_DEVICE_INFO_WITH_TYPE *
0x18004841b  xor     r8d, r8d; unsigned int *
0x18004841e  call    ?StorageDeviceFromSaveLocation@CRemovableMediaManager@StorageSenseHandlers@SystemSettings@@QEAAJPEBGPEAIPEAUSTORAGE_DEVICE_INFO_WITH_TYPE@@@Z; SystemSettings::StorageSenseHandlers::CRemovableMediaManager::StorageDeviceFromSaveLocation(ushort const *,uint *,STORAGE_DEVICE_INFO_WITH_TYPE *)
0x180048423  mov     ebx, eax
0x180048425  mov     r12d, 8
0x18004842b  test    eax, eax
0x18004842d  jns     short loc_180048459
0x18004842f  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x180048434  mov     ecx, [rax]
0x180048436  cmp     ecx, 2
0x180048439  jbe     loc_180048A84
0x18004843f  xor     r9d, r9d
0x180048442  xor     r8d, r8d
0x180048445  lea     rdx, byte_180150339
0x18004844c  mov     rcx, rax
0x18004844f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180048454  jmp     loc_180048A84
0x180048459  xor     r8d, r8d
0x18004845c  mov     dl, 1
0x18004845e  mov     rcx, [r14+0F8h]
0x180048465  call    ?SetIsAppBusy@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAX_NW4AppOperationType@23@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::SetIsAppBusy(bool,SystemSettings::StorageSenseHandlers::AppOperationType)
0x18004846a  mov     ecx, 1
0x18004846f  call    cs:__imp_RoInitialize
0x180048475  mov     ebx, eax
0x180048477  test    eax, eax
0x180048479  jns     short loc_1800484A5
0x18004847b  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x180048480  mov     ecx, [rax]
0x180048482  cmp     ecx, 2
0x180048485  jbe     loc_180048A84
0x18004848b  xor     r9d, r9d
0x18004848e  xor     r8d, r8d
0x180048491  lea     rdx, byte_1801503A3
0x180048498  mov     rcx, rax
0x18004849b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800484a0  jmp     loc_180048A84
0x1800484a5  mov     sil, 1
0x1800484a8  lea     rax, [rbp+8D0h+var_4C0]
0x1800484af  lea     rcx, [rbp+8D0h+var_920]
0x1800484b3  mov     rdx, r12
0x1800484b6  mov     ebx, 80h
0x1800484bb  movups  xmm0, xmmword ptr [rcx]
0x1800484be  movups  xmmword ptr [rax], xmm0
0x1800484c1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800484c5  movups  xmmword ptr [rax+10h], xmm1
0x1800484c9  movups  xmm0, xmmword ptr [rcx+20h]
0x1800484cd  movups  xmmword ptr [rax+20h], xmm0
0x1800484d1  movups  xmm1, xmmword ptr [rcx+30h]
0x1800484d5  movups  xmmword ptr [rax+30h], xmm1
0x1800484d9  movups  xmm0, xmmword ptr [rcx+40h]
0x1800484dd  movups  xmmword ptr [rax+40h], xmm0
0x1800484e1  movups  xmm1, xmmword ptr [rcx+50h]
0x1800484e5  movups  xmmword ptr [rax+50h], xmm1
0x1800484e9  movups  xmm0, xmmword ptr [rcx+60h]
0x1800484ed  movups  xmmword ptr [rax+60h], xmm0
0x1800484f1  movups  xmm1, xmmword ptr [rcx+70h]
0x1800484f5  movups  xmmword ptr [rax+70h], xmm1
0x1800484f9  add     rax, rbx
0x1800484fc  add     rcx, rbx
0x1800484ff  sub     rdx, 1
0x180048503  jnz     short loc_1800484BB
0x180048505  movups  xmm0, xmmword ptr [rcx]
0x180048508  movups  xmmword ptr [rax], xmm0
0x18004850b  movups  xmm1, xmmword ptr [rcx+10h]
0x18004850f  movups  xmmword ptr [rax+10h], xmm1
0x180048513  movups  xmm0, xmmword ptr [rcx+20h]
0x180048517  movups  xmmword ptr [rax+20h], xmm0
0x18004851b  movups  xmm1, xmmword ptr [rcx+30h]
0x18004851f  movups  xmmword ptr [rax+30h], xmm1
0x180048523  movups  xmm0, xmmword ptr [rcx+40h]
0x180048527  movups  xmmword ptr [rax+40h], xmm0
0x18004852b  movups  xmm1, xmmword ptr [rcx+50h]
0x18004852f  movups  xmmword ptr [rax+50h], xmm1
0x180048533  lea     r8, [rsp+9D0h+var_960]
0x180048538  lea     rdx, [rbp+8D0h+var_4C0]
0x18004853f  call    ?_FindPackageVolume@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJUSTORAGE_DEVICE_INFO_WITH_TYPE@@PEAPEAUIPackageVolume@Deployment@Management@Windows@@@Z; SystemSettings::StorageSenseHandlers::CAppOperationSetting::_FindPackageVolume(STORAGE_DEVICE_INFO_WITH_TYPE,Windows::Management::Deployment::IPackageVolume * *)
0x180048544  test    eax, eax
0x180048546  jns     loc_1800486E0
0x18004854c  lea     rax, [rbp+8D0h+var_4C0]
0x180048553  lea     rcx, [rbp+8D0h+var_920]
0x180048557  mov     rdx, r12
0x18004855a  movups  xmm0, xmmword ptr [rcx]
0x18004855d  movups  xmmword ptr [rax], xmm0
0x180048560  movups  xmm1, xmmword ptr [rcx+10h]
0x180048564  movups  xmmword ptr [rax+10h], xmm1
0x180048568  movups  xmm0, xmmword ptr [rcx+20h]
0x18004856c  movups  xmmword ptr [rax+20h], xmm0
0x180048570  movups  xmm1, xmmword ptr [rcx+30h]
0x180048574  movups  xmmword ptr [rax+30h], xmm1
0x180048578  movups  xmm0, xmmword ptr [rcx+40h]
0x18004857c  movups  xmmword ptr [rax+40h], xmm0
0x180048580  movups  xmm1, xmmword ptr [rcx+50h]
0x180048584  movups  xmmword ptr [rax+50h], xmm1
0x180048588  movups  xmm0, xmmword ptr [rcx+60h]
0x18004858c  movups  xmmword ptr [rax+60h], xmm0
0x180048590  movups  xmm1, xmmword ptr [rcx+70h]
0x180048594  movups  xmmword ptr [rax+70h], xmm1
0x180048598  add     rax, rbx
0x18004859b  add     rcx, rbx
0x18004859e  sub     rdx, 1
0x1800485a2  jnz     short loc_18004855A
0x1800485a4  movups  xmm0, xmmword ptr [rcx]
0x1800485a7  movups  xmmword ptr [rax], xmm0
0x1800485aa  movups  xmm1, xmmword ptr [rcx+10h]
0x1800485ae  movups  xmmword ptr [rax+10h], xmm1
0x1800485b2  movups  xmm0, xmmword ptr [rcx+20h]
0x1800485b6  movups  xmmword ptr [rax+20h], xmm0
0x1800485ba  movups  xmm1, xmmword ptr [rcx+30h]
0x1800485be  movups  xmmword ptr [rax+30h], xmm1
0x1800485c2  movups  xmm0, xmmword ptr [rcx+40h]
0x1800485c6  movups  xmmword ptr [rax+40h], xmm0
0x1800485ca  movups  xmm1, xmmword ptr [rcx+50h]
0x1800485ce  movups  xmmword ptr [rax+50h], xmm1
0x1800485d2  mov     r8, r13
0x1800485d5  lea     rdx, [rbp+8D0h+var_4C0]
0x1800485dc  call    ?_CreateAppRepository@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJUSTORAGE_DEVICE_INFO_WITH_TYPE@@PEAUHWND__@@@Z; SystemSettings::StorageSenseHandlers::CAppOperationSetting::_CreateAppRepository(STORAGE_DEVICE_INFO_WITH_TYPE,HWND__ *)
0x1800485e1  mov     ebx, eax
0x1800485e3  test    eax, eax
0x1800485e5  jns     short loc_180048611
0x1800485e7  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800485ec  mov     ecx, [rax]
0x1800485ee  cmp     ecx, 2
0x1800485f1  jbe     loc_180048A84
0x1800485f7  xor     r9d, r9d
0x1800485fa  xor     r8d, r8d
0x1800485fd  lea     rdx, byte_180150289
0x180048604  mov     rcx, rax
0x180048607  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004860c  jmp     loc_180048A84
0x180048611  lea     rax, [rbp+8D0h+var_4C0]
0x180048618  lea     rcx, [rbp+8D0h+var_920]
0x18004861c  mov     rdx, r12
0x18004861f  movups  xmm0, xmmword ptr [rcx]
0x180048622  movups  xmmword ptr [rax], xmm0
0x180048625  movups  xmm1, xmmword ptr [rcx+10h]
0x180048629  movups  xmmword ptr [rax+10h], xmm1
0x18004862d  movups  xmm0, xmmword ptr [rcx+20h]
0x180048631  movups  xmmword ptr [rax+20h], xmm0
0x180048635  movups  xmm1, xmmword ptr [rcx+30h]
0x180048639  movups  xmmword ptr [rax+30h], xmm1
0x18004863d  movups  xmm0, xmmword ptr [rcx+40h]
0x180048641  movups  xmmword ptr [rax+40h], xmm0
0x180048645  movups  xmm1, xmmword ptr [rcx+50h]
0x180048649  movups  xmmword ptr [rax+50h], xmm1
0x18004864d  movups  xmm0, xmmword ptr [rcx+60h]
0x180048651  movups  xmmword ptr [rax+60h], xmm0
0x180048655  movups  xmm1, xmmword ptr [rcx+70h]
0x180048659  movups  xmmword ptr [rax+70h], xmm1
0x18004865d  lea     rax, [rax+80h]
0x180048664  lea     rcx, [rcx+80h]
0x18004866b  sub     rdx, 1
0x18004866f  jnz     short loc_18004861F
0x180048671  movups  xmm0, xmmword ptr [rcx]
0x180048674  movups  xmmword ptr [rax], xmm0
0x180048677  movups  xmm1, xmmword ptr [rcx+10h]
0x18004867b  movups  xmmword ptr [rax+10h], xmm1
0x18004867f  movups  xmm0, xmmword ptr [rcx+20h]
0x180048683  movups  xmmword ptr [rax+20h], xmm0
0x180048687  movups  xmm1, xmmword ptr [rcx+30h]
0x18004868b  movups  xmmword ptr [rax+30h], xmm1
0x18004868f  movups  xmm0, xmmword ptr [rcx+40h]
0x180048693  movups  xmmword ptr [rax+40h], xmm0
0x180048697  movups  xmm1, xmmword ptr [rcx+50h]
0x18004869b  movups  xmmword ptr [rax+50h], xmm1
0x18004869f  lea     r8, [rsp+9D0h+var_960]
0x1800486a4  lea     rdx, [rbp+8D0h+var_4C0]
0x1800486ab  call    ?_FindPackageVolume@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@AEAAJUSTORAGE_DEVICE_INFO_WITH_TYPE@@PEAPEAUIPackageVolume@Deployment@Management@Windows@@@Z; SystemSettings::StorageSenseHandlers::CAppOperationSetting::_FindPackageVolume(STORAGE_DEVICE_INFO_WITH_TYPE,Windows::Management::Deployment::IPackageVolume * *)
0x1800486b0  mov     ebx, eax
0x1800486b2  test    eax, eax
0x1800486b4  jns     short loc_1800486E0
0x1800486b6  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800486bb  mov     ecx, [rax]
0x1800486bd  cmp     ecx, 2
0x1800486c0  jbe     loc_180048A84
0x1800486c6  xor     r9d, r9d
0x1800486c9  xor     r8d, r8d
0x1800486cc  lea     rdx, word_1801502DA
0x1800486d3  mov     rcx, rax
0x1800486d6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800486db  jmp     loc_180048A84
0x1800486e0  mov     rdi, [r14+0F8h]
0x1800486e7  mov     rax, [rdi]
0x1800486ea  mov     rbx, [rax+30h]
0x1800486ee  mov     rcx, [rsp+9D0h+string]; string
0x1800486f3  call    cs:__imp_WindowsDeleteString
0x1800486f9  mov     [rsp+9D0h+string], 0
0x180048702  lea     rdx, [rsp+9D0h+string]
0x180048707  mov     rcx, rdi
0x18004870a  mov     rax, rbx
0x18004870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048712  mov     ebx, eax
0x180048714  xor     edi, edi
0x180048716  test    eax, eax
0x180048718  jns     short loc_18004878C
0x18004871a  mov     rcx, [rbp+8D8h]; this
0x180048721  mov     r9d, eax; char *
0x180048724  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004872b  mov     edx, 620h; void *
0x180048730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048735  nop
0x180048736  mov     rcx, [rsp+9D0h+string]; string
0x18004873b  call    cs:__imp_WindowsDeleteString
0x180048741  mov     [rsp+9D0h+string], rdi
0x180048746  mov     rcx, [rbp+8D0h+var_950]
0x18004874a  test    rcx, rcx
0x18004874d  jz      short loc_180048760
0x18004874f  mov     [rbp+8D0h+var_950], rdi
0x180048753  mov     rax, [rcx]
0x180048756  mov     rax, [rax+10h]
0x18004875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004875f  nop
0x180048760  lea     rcx, [rsp+9D0h+var_968]
0x180048765  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004876a  nop
0x18004876b  mov     rcx, [rsp+9D0h+var_960]
0x180048770  test    rcx, rcx
0x180048773  jz      short loc_180048787
0x180048775  mov     [rsp+9D0h+var_960], rdi
0x18004877a  mov     rax, [rcx]
0x18004877d  mov     rax, [rax+10h]
0x180048781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048786  nop
0x180048787  jmp     loc_180048C8E
0x18004878c  lea     rax, [rbp+8D0h+var_950]
0x180048790  mov     [rsp+9D0h+var_958], rax
0x180048795  lea     rdx, [rsp+9D0h+var_958]
0x18004879a  lea     rcx, [rsp+9D0h+var_980]
0x18004879f  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationProgressHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__IDeploymentResult____Windows__Management__Deployment__DeploymentProgress______Windows__Foundation__IAsyncOperationWithProgress_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress____Windows__Management__Deployment__DeploymentProgress____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationProgressHandler_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress___lambda_94e70399866f18d209f69adbd9f672ae___1_Windows__Foundation__IAsyncOperationWithProgress_Windows__Management__Deployment__DeploymentResult___Windows__Management__Deployment__DeploymentProgress____Windows__Management__Deployment__DeploymentProgress___lambda_94e70399866f18d209f69adbd9f672ae___
0x1800487a4  mov     rcx, [rax]
0x1800487a7  mov     [rsp+9D0h+var_958], rcx
0x1800487ac  mov     [rax], rdi
0x1800487af  mov     rcx, [rsp+9D0h+var_980]
0x1800487b4  test    rcx, rcx
0x1800487b7  jz      short loc_1800487C3
0x1800487b9  mov     [rsp+9D0h+var_980], rdi
0x1800487be  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800487c3  lea     rdx, [rsp+9D0h+var_958]
0x1800487c8  lea     rcx, [rbp+8D0h+var_930]
0x1800487cc  call    ??4?$ComPtr@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> &&)
0x1800487d1  nop
0x1800487d2  mov     rcx, [rsp+9D0h+var_958]
0x1800487d7  test    rcx, rcx
0x1800487da  jz      short loc_1800487E9
0x1800487dc  mov     rax, [rcx]
0x1800487df  mov     rax, [rax+10h]
0x1800487e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487e8  nop
0x1800487e9  mov     r15, [rbp+8D0h+var_930]
0x1800487ed  test    r15, r15
0x1800487f0  jnz     short loc_1800487FC
0x1800487f2  mov     ebx, 8007000Eh
  ... truncated ...
```
