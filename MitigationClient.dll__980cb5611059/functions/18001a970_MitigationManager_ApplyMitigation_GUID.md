# MitigationManager::ApplyMitigation(_GUID)

- ea: `0x18001a970`
- end: `0x18001b2cd`
- name: `?ApplyMitigation@MitigationManager@@UEAAJU_GUID@@@Z`
- size: `2397`
- prototype: `__int64 __fastcall(MitigationManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b2e0`

## callees

- `0x18000a6e0`
- `0x18000ea68`
- `0x18000eb00`
- `0x18001055c`
- `0x18001208c`
- `0x180016bec`
- `0x180016e28`
- `0x180017c84`
- `0x180017d74`
- `0x180019764`
- `0x180019fd0`
- `0x18001a85c`
- `0x18001a970`
- `0x18001b9e0`
- `0x18001d75c`
- `0x18001d984`
- `0x1800211e0`
- `0x180021858`
- `0x18002407c`
- `0x18002eb74`
- `0x180040c34`
- `0x180040e58`
- `0x1800429f8`
- `0x180042c8c`
- `0x180042da4`
- `0x180042f54`
- `0x180044240`
- `0x180051828`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001a9e8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001a9e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b0e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b0e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001acf4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001acf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall MitigationManager::ApplyMitigation(MitigationStateCollection **this, struct _GUID *a2)
{
  unsigned int v4; // edx
  int v5; // eax
  unsigned int v6; // ebx
  MitigationContext *MitigationContext; // rax
  int ClientState; // eax
  unsigned int v10; // ebx
  int Mitigation; // eax
  unsigned int v12; // edx
  unsigned int v13; // edi
  int v14; // esi
  wil::details *v15; // rbx
  int EventName; // eax
  unsigned int v17; // edi
  int v18; // eax
  unsigned int v19; // ebx
  int MitigationDeviceState; // eax
  unsigned int v21; // edi
  unsigned int Data1; // edi
  int AvailableMitigationFromOneSettings; // eax
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // edi
  void *v27; // rdx
  int v28; // edi
  int updated; // eax
  unsigned int v30; // edi
  int v31; // edi
  unsigned int v32; // esi
  PCWSTR StringRawBuffer; // rax
  unsigned int v34; // edx
  unsigned int v35; // edx
  int v36; // [rsp+20h] [rbp-268h]
  int v37; // [rsp+20h] [rbp-268h]
  bool v38; // [rsp+40h] [rbp-248h] BYREF
  bool v39[7]; // [rsp+41h] [rbp-247h] BYREF
  unsigned __int64 v40; // [rsp+48h] [rbp-240h] BYREF
  GUID v41; // [rsp+50h] [rbp-238h] BYREF
  struct _GUID v42; // [rsp+60h] [rbp-228h] BYREF
  IID rclsid; // [rsp+70h] [rbp-218h] BYREF
  ULONG SecurityDescriptorSize[4]; // [rsp+80h] [rbp-208h] BYREF
  IID v45; // [rsp+90h] [rbp-1F8h] BYREF
  unsigned __int16 *v46[2]; // [rsp+A0h] [rbp-1E8h] BYREF
  _OWORD v47[2]; // [rsp+B0h] [rbp-1D8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+D0h] [rbp-1B8h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-1A8h]
  _QWORD v50[42]; // [rsp+F0h] [rbp-198h] BYREF
  char v51; // [rsp+240h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v50,
    "ApplyMitigationsActivity");
  v50[0] = &MitigationTelemetryClass::ApplyMitigationsActivity::`vftable';
  v51 = 0;
  MitigationTelemetryClass::ApplyMitigationsActivity::StartActivity(
    (MitigationTelemetryClass::ApplyMitigationsActivity *)v50,
    v4);
  v40 = (unsigned __int64)&MitigationManager::m_lock & -(__int64)TryEnterCriticalSection(&MitigationManager::m_lock);
  if ( !v40 )
  {
    v5 = MitigationManager::AcquireLock(0, &v40);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
        (const char *)(unsigned int)v5,
        v36);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
      MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
      return v6;
    }
  }
  rclsid = *a2;
  MitigationContext = MitigationExecutionContext::GetMitigationContext(&rclsid);
  rclsid = (IID)xmmword_180062A30;
  MitigationContext::SetCallerId(MitigationContext, &rclsid);
  *(_QWORD *)&v45.Data1 = a2;
  v45.Data4[0] = 1;
  v42.Data1 = 0;
  ClientState = MitigationStateCollection::GetClientState(
                  this[6],
                  (enum ClientState *)&v42,
                  (enum ClientStateAuthority *)&rclsid);
  v10 = ClientState;
  if ( ClientState < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)ClientState,
      v36);
  *(_OWORD *)v46 = 0;
  memset(v47, 0, 28);
  Mitigation = MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::GetMitigation(this[5], a2, v46);
  v13 = Mitigation;
  if ( Mitigation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)Mitigation,
      v36);
    v45 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v45, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v13;
  }
  v14 = DWORD2(v47[1]);
  if ( !v42.Data1 && DWORD2(v47[1]) != 3 )
  {
    MitigationTelemetryClass::ApplyMitigationsActivity::Stop(
      (MitigationTelemetryClass::ApplyMitigationsActivity *)v50,
      v12);
    v45 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v45, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v10;
  }
  v15 = 0;
  *(_QWORD *)&rclsid.Data1 = 0;
  v46[0] = 0;
  v46[1] = 0;
  *(_QWORD *)&v47[0] = 0;
  *(_OWORD *)SecurityDescriptor = 0;
  LODWORD(SecurityDescriptor[0]) = 24;
  v49 = 0;
  SecurityDescriptorSize[0] = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
  v46[1] = (unsigned __int16 *)-1LL;
  *(_QWORD *)&v47[0] = -1;
  v42 = *a2;
  EventName = StringUtils::GetEventName(&v42, v46);
  v17 = EventName;
  if ( EventName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)EventName,
      v36);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v45 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v45, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v17;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAD:(A;;GA;;;BA)(A;;GRGX;;;IU)",
         1u,
         &SecurityDescriptor[1],
         SecurityDescriptorSize) )
  {
    v18 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &rclsid,
            1,
            v46[0],
            SecurityDescriptor);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
        (const char *)(unsigned int)v18,
        v36);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
      v45 = *a2;
      MitigationExecutionContext::DispatchFailedEvent(&v45, 12, 2147549183LL);
      MitigationExecutionContext::ClearAllContexts();
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
      MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
      return v19;
    }
    v15 = *(wil::details **)&rclsid.Data1;
  }
  v42.Data1 = 0;
  v39[0] = 0;
  v38 = 0;
  MitigationDeviceState = MitigationStateCollection::GetMitigationDeviceState(
                            this[6],
                            (enum MitigationPreference *)&v42,
                            v39,
                            &v38);
  v21 = MitigationDeviceState;
  if ( MitigationDeviceState < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)MitigationDeviceState,
      v36);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v45 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v45, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v21;
  }
  Data1 = v42.Data1;
  MitigationTelemetryClass::DeviceState<bool &,int,bool &>(v39, &v42, &v38);
  if ( !v39[0] || Data1 != 2 )
  {
    MitigationExecutionContext::DispatchEvent(5, 2147942487LL);
    MitigationTelemetryClass::ApplyMitigationsActivity::Stop(
      (MitigationTelemetryClass::ApplyMitigationsActivity *)v50,
      v35);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v41 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return 0;
  }
  *(_QWORD *)&v42.Data1 = 0;
  v41 = *a2;
  AvailableMitigationFromOneSettings = MitigationManager::GetAvailableMitigationFromOneSettings((__int64)this);
  v24 = AvailableMitigationFromOneSettings;
  if ( AvailableMitigationFromOneSettings != -2135164402 )
  {
    if ( AvailableMitigationFromOneSettings >= 0 )
    {
      *(&MitigationExecutionContext::s_commonContext + 1) = 1;
      v41 = *a2;
      updated = AvailableMitigations::UpdateStatus(this[5], &v41, 1);
      v30 = updated;
      if ( updated < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
          (const char *)(unsigned int)updated,
          v36);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
        v41 = *a2;
        MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
        MitigationExecutionContext::ClearAllContexts();
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
        MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
        return v30;
      }
      v31 = *(_DWORD *)(*(_QWORD *)&v42.Data1 + 56LL);
      v32 = *(_DWORD *)(*(_QWORD *)&v42.Data1 + 60LL);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)&v42.Data1 + 24LL), 0);
      v38 = 0;
      v41 = *a2;
      v28 = MitigationManager::ExecuteMitigation(
              (MitigationManager *)this,
              &v41,
              (__int64)StringRawBuffer,
              v32,
              4,
              &v38,
              v31);
      goto LABEL_31;
    }
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)AvailableMitigationFromOneSettings,
      v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v41 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v24;
  }
  if ( v14 != 3 )
    goto LABEL_27;
  v41 = *a2;
  v25 = AvailableMitigations::UpdateStatus(this[5], &v41, 1);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)v25,
      v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v41 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return v26;
  }
  v38 = 0;
  v41 = *a2;
  v28 = MitigationManager::ExecuteMitigation((MitigationManager *)this, &v41, 0, 3u, 4, &v38, 0);
LABEL_31:
  wil::details::SetEvent(v15, v27);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationmanager\\mitigationmanager.cpp",
      (const char *)(unsigned int)v28,
      v37);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v41 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return (unsigned int)v28;
  }
  else
  {
    MitigationTelemetryClass::ApplyMitigationsActivity::Stop(
      (MitigationTelemetryClass::ApplyMitigationsActivity *)v50,
      v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&rclsid);
    v41 = *a2;
    MitigationExecutionContext::DispatchFailedEvent(&v41, 12, 2147549183LL);
    MitigationExecutionContext::ClearAllContexts();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v40);
    MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity((MitigationTelemetryClass::ApplyMitigationsActivity *)v50);
    return 0;
  }
}

```

## disassembly

```asm
0x18001a970  mov     [rsp+arg_10], rbx
0x18001a975  mov     [rsp+arg_18], rsi
0x18001a97a  push    rdi
0x18001a97b  push    r12
0x18001a97d  push    r13
0x18001a97f  push    r14
0x18001a981  push    r15
0x18001a983  sub     rsp, 260h
0x18001a98a  mov     rax, cs:__security_cookie
0x18001a991  xor     rax, rsp
0x18001a994  mov     [rsp+288h+var_38], rax
0x18001a99c  mov     r14, rdx
0x18001a99f  mov     r13, rcx
0x18001a9a2  lea     rdx, aApplymitigatio; "ApplyMitigationsActivity"
0x18001a9a9  lea     rcx, [rsp+288h+var_198]
0x18001a9b1  call    ??0?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001a9b6  lea     rax, ??_7ApplyMitigationsActivity@MitigationTelemetryClass@@6B@; const MitigationTelemetryClass::ApplyMitigationsActivity::`vftable'
0x18001a9bd  mov     [rsp+288h+var_198], rax
0x18001a9c5  xor     r12d, r12d
0x18001a9c8  mov     [rsp+288h+var_48], r12b
0x18001a9d0  lea     rcx, [rsp+288h+var_198]; this
0x18001a9d8  call    ?StartActivity@ApplyMitigationsActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::ApplyMitigationsActivity::StartActivity(ulong)
0x18001a9dd  nop
0x18001a9de  lea     rbx, ?m_lock@MitigationManager@@0Vcritical_section@wil@@A; wil::critical_section MitigationManager::m_lock
0x18001a9e5  mov     rcx, rbx; lpCriticalSection
0x18001a9e8  call    cs:__imp_TryEnterCriticalSection
0x18001a9ee  neg     eax
0x18001a9f0  sbb     rcx, rcx
0x18001a9f3  and     rcx, rbx
0x18001a9f6  mov     [rsp+288h+var_240], rcx
0x18001a9fb  jnz     short loc_18001AA49
0x18001a9fd  lea     rdx, [rsp+288h+var_240]
0x18001aa02  call    ?AcquireLock@MitigationManager@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MitigationManager::AcquireLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &)
0x18001aa07  mov     ebx, eax
0x18001aa09  test    eax, eax
0x18001aa0b  jns     short loc_18001AA49
0x18001aa0d  mov     rcx, [rsp+288h]; this
0x18001aa15  mov     r9d, eax; char *
0x18001aa18  lea     r8, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001aa1f  mov     edx, 0D7h; void *
0x18001aa24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa29  nop
0x18001aa2a  lea     rcx, [rsp+288h+var_240]
0x18001aa2f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001aa34  nop
0x18001aa35  lea     rcx, [rsp+288h+var_198]; this
0x18001aa3d  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001aa42  mov     eax, ebx
0x18001aa44  jmp     loc_18001B29F
0x18001aa49  movups  xmm0, xmmword ptr [r14]
0x18001aa4d  movdqu  xmmword ptr [rsp+288h+rclsid.Data1], xmm0
0x18001aa53  lea     rcx, [rsp+288h+rclsid]; rclsid
0x18001aa58  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@U_GUID@@@Z; MitigationExecutionContext::GetMitigationContext(_GUID)
0x18001aa5d  movups  xmm0, cs:xmmword_180062A30
0x18001aa64  movdqu  xmmword ptr [rsp+288h+rclsid.Data1], xmm0
0x18001aa6a  lea     rdx, [rsp+288h+rclsid]; struct _GUID
0x18001aa6f  mov     rcx, rax; this
0x18001aa72  call    ?SetCallerId@MitigationContext@@QEAAXU_GUID@@@Z; MitigationContext::SetCallerId(_GUID)
0x18001aa77  mov     qword ptr [rsp+288h+var_1F8], r14
0x18001aa7f  mov     byte ptr [rsp+288h+var_1F8+8], 1
0x18001aa87  mov     [rsp+288h+var_228.Data1], r12d
0x18001aa8c  lea     r8, [rsp+288h+rclsid]; enum ClientStateAuthority *
0x18001aa91  lea     rdx, [rsp+288h+var_228]; enum ClientState *
0x18001aa96  mov     rcx, [r13+30h]; this
0x18001aa9a  call    ?GetClientState@MitigationStateCollection@@QEAAJAEAW4ClientState@@AEAW4ClientStateAuthority@@@Z; MitigationStateCollection::GetClientState(ClientState &,ClientStateAuthority &)
0x18001aa9f  mov     ebx, eax
0x18001aaa1  mov     rcx, [rsp+288h]; this
0x18001aaa9  lea     r15, aOnecoreBaseDia_24; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001aab0  test    eax, eax
0x18001aab2  jns     short loc_18001AAC4
0x18001aab4  mov     r9d, eax; char *
0x18001aab7  mov     r8, r15; unsigned int
0x18001aaba  mov     edx, 0E8h; void *
0x18001aabf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001aac4  xorps   xmm0, xmm0
0x18001aac7  movups  xmmword ptr [rsp+288h+var_1E8], xmm0
0x18001aacf  movups  [rsp+288h+var_1D8], xmm0
0x18001aad7  movups  [rsp+288h+var_1D8+0Ch], xmm0
0x18001aadf  lea     r8, [rsp+288h+var_1E8]
0x18001aae7  mov     rdx, r14
0x18001aaea  mov     rcx, [r13+28h]
0x18001aaee  call    ?GetMitigation@?$MitigationLog@U_AVAILABLE_MITIGATION_RECORD@@UMitigationResultInternal@@@@QEAAJAEBU_GUID@@AEAU_AVAILABLE_MITIGATION_RECORD@@@Z; MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::GetMitigation(_GUID const &,_AVAILABLE_MITIGATION_RECORD &)
0x18001aaf3  mov     edi, eax
0x18001aaf5  test    eax, eax
0x18001aaf7  jns     short loc_18001AB5C
0x18001aaf9  mov     rcx, [rsp+288h]; this
0x18001ab01  mov     r9d, eax; char *
0x18001ab04  mov     r8, r15; unsigned int
0x18001ab07  mov     edx, 0ECh; void *
0x18001ab0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ab11  nop
0x18001ab12  movups  xmm0, xmmword ptr [r14]
0x18001ab16  movdqu  [rsp+288h+var_1F8], xmm0
0x18001ab1f  mov     edx, 0Ch
0x18001ab24  mov     r8d, 8000FFFFh
0x18001ab2a  lea     rcx, [rsp+288h+var_1F8]
0x18001ab32  call    ?DispatchFailedEvent@MitigationExecutionContext@@SAXU_GUID@@W4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchFailedEvent(_GUID,FailureBucketId,long)
0x18001ab37  call    ?ClearAllContexts@MitigationExecutionContext@@SAXXZ; MitigationExecutionContext::ClearAllContexts(void)
0x18001ab3c  nop
0x18001ab3d  lea     rcx, [rsp+288h+var_240]
0x18001ab42  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ab47  nop
0x18001ab48  lea     rcx, [rsp+288h+var_198]; this
0x18001ab50  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001ab55  mov     eax, edi
0x18001ab57  jmp     loc_18001B29F
0x18001ab5c  mov     esi, [rsp+288h+var_1C0]
0x18001ab63  cmp     [rsp+288h+var_228.Data1], r12d
0x18001ab68  jnz     short loc_18001ABC7
0x18001ab6a  cmp     esi, 3
0x18001ab6d  jz      short loc_18001ABC7
0x18001ab6f  lea     rcx, [rsp+288h+var_198]; this
0x18001ab77  call    ?Stop@ApplyMitigationsActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::ApplyMitigationsActivity::Stop(ulong)
0x18001ab7c  nop
0x18001ab7d  movups  xmm0, xmmword ptr [r14]
0x18001ab81  movdqu  [rsp+288h+var_1F8], xmm0
0x18001ab8a  mov     edx, 0Ch
0x18001ab8f  mov     r8d, 8000FFFFh
0x18001ab95  lea     rcx, [rsp+288h+var_1F8]
0x18001ab9d  call    ?DispatchFailedEvent@MitigationExecutionContext@@SAXU_GUID@@W4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchFailedEvent(_GUID,FailureBucketId,long)
0x18001aba2  call    ?ClearAllContexts@MitigationExecutionContext@@SAXXZ; MitigationExecutionContext::ClearAllContexts(void)
0x18001aba7  nop
0x18001aba8  lea     rcx, [rsp+288h+var_240]
0x18001abad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001abb2  nop
0x18001abb3  lea     rcx, [rsp+288h+var_198]; this
0x18001abbb  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001abc0  mov     eax, ebx
0x18001abc2  jmp     loc_18001B29F
0x18001abc7  mov     rbx, r12
0x18001abca  mov     qword ptr [rsp+288h+rclsid.Data1], rbx
0x18001abcf  mov     [rsp+288h+var_1E8], r12
0x18001abd7  mov     [rsp+288h+var_1E8+8], r12
0x18001abdf  mov     qword ptr [rsp+288h+var_1D8], r12
0x18001abe7  xorps   xmm0, xmm0
0x18001abea  xor     eax, eax
0x18001abec  movups  xmmword ptr [rsp+288h+SecurityDescriptor], xmm0
0x18001abf4  mov     [rsp+288h+var_1A8], rax
0x18001abfc  mov     dword ptr [rsp+288h+SecurityDescriptor], 18h
0x18001ac07  mov     dword ptr [rsp+288h+var_1A8], r12d
0x18001ac0f  mov     [rsp+288h+SecurityDescriptorSize], r12d
0x18001ac17  lea     rcx, [rsp+288h+var_1E8]
0x18001ac1f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ac24  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ac28  mov     [rsp+288h+var_1E8+8], rax
0x18001ac30  mov     qword ptr [rsp+288h+var_1D8], rax
0x18001ac38  movups  xmm0, xmmword ptr [r14]
0x18001ac3c  movdqu  xmmword ptr [rsp+288h+var_228.Data1], xmm0
0x18001ac42  lea     rdx, [rsp+288h+var_1E8]; unsigned __int16 **
0x18001ac4a  lea     rcx, [rsp+288h+var_228]; struct _GUID
0x18001ac4f  call    ?GetEventName@StringUtils@@SAJU_GUID@@PEAPEAG@Z; StringUtils::GetEventName(_GUID,ushort * *)
0x18001ac54  mov     edi, eax
0x18001ac56  test    eax, eax
0x18001ac58  jns     short loc_18001ACD6
0x18001ac5a  mov     rcx, [rsp+288h]; this
0x18001ac62  mov     r9d, eax; char *
0x18001ac65  mov     r8, r15; unsigned int
0x18001ac68  mov     edx, 107h; void *
0x18001ac6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac72  nop
0x18001ac73  lea     rcx, [rsp+288h+var_1E8]
0x18001ac7b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ac80  nop
0x18001ac81  lea     rcx, [rsp+288h+rclsid]
0x18001ac86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ac8b  nop
0x18001ac8c  movups  xmm0, xmmword ptr [r14]
0x18001ac90  movdqu  [rsp+288h+var_1F8], xmm0
0x18001ac99  mov     edx, 0Ch
0x18001ac9e  mov     r8d, 8000FFFFh
0x18001aca4  lea     rcx, [rsp+288h+var_1F8]
0x18001acac  call    ?DispatchFailedEvent@MitigationExecutionContext@@SAXU_GUID@@W4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchFailedEvent(_GUID,FailureBucketId,long)
0x18001acb1  call    ?ClearAllContexts@MitigationExecutionContext@@SAXXZ; MitigationExecutionContext::ClearAllContexts(void)
0x18001acb6  nop
0x18001acb7  lea     rcx, [rsp+288h+var_240]
0x18001acbc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001acc1  nop
0x18001acc2  lea     rcx, [rsp+288h+var_198]; this
0x18001acca  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001accf  mov     eax, edi
0x18001acd1  jmp     loc_18001B29F
0x18001acd6  lea     r9, [rsp+288h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001acde  lea     r8, [rsp+288h+SecurityDescriptor+8]; SecurityDescriptor
0x18001ace6  mov     edi, 1
0x18001aceb  mov     edx, edi; StringSDRevision
0x18001aced  lea     rcx, StringSecurityDescriptor; "O:BAD:(A;;GA;;;BA)(A;;GRGX;;;IU)"
0x18001acf4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001acfa  test    eax, eax
0x18001acfc  jz      loc_18001ADA3
0x18001ad02  lea     r9, [rsp+288h+SecurityDescriptor]
0x18001ad0a  mov     r8, [rsp+288h+var_1E8]
0x18001ad12  mov     edx, edi
0x18001ad14  lea     rcx, [rsp+288h+rclsid]
0x18001ad19  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001ad1e  mov     ebx, eax
0x18001ad20  test    eax, eax
0x18001ad22  jns     short loc_18001AD9E
0x18001ad24  mov     rcx, [rsp+288h]; this
0x18001ad2c  mov     r9d, eax; char *
0x18001ad2f  mov     r8, r15; unsigned int
0x18001ad32  mov     edx, 10Bh; void *
0x18001ad37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad3c  nop
0x18001ad3d  lea     rcx, [rsp+288h+var_1E8]
0x18001ad45  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ad4a  nop
0x18001ad4b  lea     rcx, [rsp+288h+rclsid]
0x18001ad50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad55  nop
0x18001ad56  movups  xmm0, xmmword ptr [r14]
0x18001ad5a  movdqu  [rsp+288h+var_1F8], xmm0
0x18001ad63  lea     edx, [rdi+0Bh]
0x18001ad66  mov     r8d, 8000FFFFh
0x18001ad6c  lea     rcx, [rsp+288h+var_1F8]
0x18001ad74  call    ?DispatchFailedEvent@MitigationExecutionContext@@SAXU_GUID@@W4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchFailedEvent(_GUID,FailureBucketId,long)
0x18001ad79  call    ?ClearAllContexts@MitigationExecutionContext@@SAXXZ; MitigationExecutionContext::ClearAllContexts(void)
0x18001ad7e  nop
0x18001ad7f  lea     rcx, [rsp+288h+var_240]
0x18001ad84  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ad89  nop
0x18001ad8a  lea     rcx, [rsp+288h+var_198]; this
0x18001ad92  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001ad97  mov     eax, ebx
0x18001ad99  jmp     loc_18001B29F
0x18001ad9e  mov     rbx, qword ptr [rsp+288h+rclsid.Data1]
0x18001ada3  mov     [rsp+288h+var_228.Data1], r12d
0x18001ada8  mov     [rsp+288h+var_247], r12b
0x18001adad  mov     [rsp+288h+var_248], r12b
0x18001adb2  lea     r9, [rsp+288h+var_248]; bool *
0x18001adb7  lea     r8, [rsp+288h+var_247]; bool *
0x18001adbc  lea     rdx, [rsp+288h+var_228]; enum MitigationPreference *
0x18001adc1  mov     rcx, [r13+30h]; this
0x18001adc5  call    ?GetMitigationDeviceState@MitigationStateCollection@@QEAAJPEAW4MitigationPreference@@PEA_N1@Z; MitigationStateCollection::GetMitigationDeviceState(MitigationPreference *,bool *,bool *)
0x18001adca  mov     edi, eax
0x18001adcc  test    eax, eax
0x18001adce  jns     short loc_18001AE4C
0x18001add0  mov     rcx, [rsp+288h]; this
0x18001add8  mov     r9d, eax; char *
0x18001addb  mov     r8, r15; unsigned int
0x18001adde  mov     edx, 112h; void *
0x18001ade3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ade8  nop
0x18001ade9  lea     rcx, [rsp+288h+var_1E8]
0x18001adf1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001adf6  nop
0x18001adf7  lea     rcx, [rsp+288h+rclsid]
0x18001adfc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ae01  nop
0x18001ae02  movups  xmm0, xmmword ptr [r14]
0x18001ae06  movdqu  [rsp+288h+var_1F8], xmm0
0x18001ae0f  mov     edx, 0Ch
0x18001ae14  mov     r8d, 8000FFFFh
0x18001ae1a  lea     rcx, [rsp+288h+var_1F8]
0x18001ae22  call    ?DispatchFailedEvent@MitigationExecutionContext@@SAXU_GUID@@W4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchFailedEvent(_GUID,FailureBucketId,long)
0x18001ae27  call    ?ClearAllContexts@MitigationExecutionContext@@SAXXZ; MitigationExecutionContext::ClearAllContexts(void)
0x18001ae2c  nop
0x18001ae2d  lea     rcx, [rsp+288h+var_240]
0x18001ae32  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ae37  nop
0x18001ae38  lea     rcx, [rsp+288h+var_198]; this
0x18001ae40  call    ??1ApplyMitigationsActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::ApplyMitigationsActivity::~ApplyMitigationsActivity(void)
0x18001ae45  mov     eax, edi
0x18001ae47  jmp     loc_18001B29F
0x18001ae4c  mov     edi, [rsp+288h+var_228.Data1]
0x18001ae50  mov     [rsp+288h+var_228.Data1], edi
0x18001ae54  lea     r8, [rsp+288h+var_248]
0x18001ae59  lea     rdx, [rsp+288h+var_228]
0x18001ae5e  lea     rcx, [rsp+288h+var_247]
0x18001ae63  call    ??$DeviceState@AEA_NHAEA_N@MitigationTelemetryClass@@SAXAEA_N$$QEAH0@Z; MitigationTelemetryClass::DeviceState<bool &,int,bool &>(bool &,int &&,bool &)
0x18001ae68  cmp     [rsp+288h+var_247], r12b
0x18001ae6d  jz      loc_18001B221
0x18001ae73  cmp     edi, 2
0x18001ae76  jnz     loc_18001B221
0x18001ae7c  mov     qword ptr [rsp+288h+var_228.Data1], r12
0x18001ae81  movups  xmm0, xmmword ptr [r14]
0x18001ae85  movdqu  [rsp+288h+var_238], xmm0
0x18001ae8b  lea     r8, [rsp+288h+var_228]
0x18001ae90  lea     rdx, [rsp+288h+var_238]
0x18001ae95  mov     rcx, r13
0x18001ae98  call    ?GetAvailableMitigationFromOneSettings@MitigationManager@@AEAAJU_GUID@@AEAV?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@@Z; MitigationManager::GetAvailableMitigationFromOneSettings(_GUID,Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata> &)
0x18001ae9d  mov     edi, eax
0x18001ae9f  cmp     eax, 80BBFA0Eh
0x18001aea4  jnz     loc_18001AF97
0x18001aeaa  cmp     esi, 3
0x18001aead  jnz     loc_18001AF9F
0x18001aeb3  movups  xmm0, xmmword ptr [r14]
0x18001aeb7  movdqu  [rsp+288h+var_238], xmm0
0x18001aebd  lea     r8d, [rsi-2]
0x18001aec1  lea     rdx, [rsp+288h+var_238]
0x18001aec6  mov     rcx, [r13+28h]
0x18001aeca  call    ?UpdateStatus@AvailableMitigations@@QEAAJU_GUID@@W4MitigationStatus@@@Z; AvailableMitigations::UpdateStatus(_GUID,MitigationStatus)
0x18001aecf  mov     edi, eax
0x18001aed1  test    eax, eax
0x18001aed3  jns     short loc_18001AF54
0x18001aed5  mov     rcx, [rsp+288h]; this
0x18001aedd  mov     r9d, eax; char *
0x18001aee0  mov     r8, r15; unsigned int
0x18001aee3  mov     edx, 124h; void *
0x18001aee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aeed  nop
  ... truncated ...
```
