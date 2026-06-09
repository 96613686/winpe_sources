# Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim::AddSettingsGroup(bool,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>)

- ea: `0x18007c86c`
- end: `0x18007d565`
- name: `?AddSettingsGroup@DePowerGuidsShim@DisplayEnhancementPowerGuids@DisplayEnhancement@Windows@Microsoft@@QEAAX_NV?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@Z`
- size: `3321`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002056c`
- `0x180027bd8`

## callees

- `0x180005860`
- `0x180009a84`
- `0x180009aa4`
- `0x18000f778`
- `0x18000fa0c`
- `0x18000fb14`
- `0x1800121d0`
- `0x180013578`
- `0x1800194e4`
- `0x18001c894`
- `0x18001f19c`
- `0x180024ed0`
- `0x180029350`
- `0x180037cc8`
- `0x180037dd0`
- `0x180037fbc`
- `0x18005b70c`
- `0x18006ce0c`
- `0x1800753fc`
- `0x18007c86c`
- `0x18007d56c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c97a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c97a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9eb`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18007caf8`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18007caf8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007cd38`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007cdbb`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007ce4a`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007cd38`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007cdbb`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18007ce4a`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007cd65`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007cde2`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007ce6d`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007cd65`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007cde2`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18007ce6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cea4`
- `POWRPROF!PowerApplySettingChanges` at `0x18007cd81`
- `POWRPROF!PowerApplySettingChanges` at `0x18007ce01`
- `POWRPROF!PowerApplySettingChanges` at `0x18007ce85`
- `POWRPROF!PowerApplySettingChanges` at `0x18007cd81`
- `POWRPROF!PowerApplySettingChanges` at `0x18007ce01`
- `POWRPROF!PowerApplySettingChanges` at `0x18007ce85`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18007c90a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18007c90a`

## string_xrefs

- `0x18007c9fb`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`
- `0x18007d496`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d4ab`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d4c0`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d4d5`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d4ea`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d4ff`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d514`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d529`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d53e`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`
- `0x18007d553`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim::AddSettingsGroup(
        __int64 a1,
        char a2,
        __int64 **a3)
{
  char v5; // si
  DWORD v6; // ebx
  char IsEnabled; // al
  int v8; // r8d
  int v9; // edx
  _QWORD *v10; // rcx
  char v11; // r14
  bool v12; // r15
  char LastError; // al
  DWORD v14; // eax
  _QWORD *v15; // r14
  char v16; // bl
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  Microsoft::Windows::DisplayEnhancement::Foundation *v21; // rcx
  DWORD ActiveScheme; // eax
  __int64 v23; // rax
  int v24; // ebx
  DWORD v25; // r15d
  __int64 v26; // rax
  int v27; // ebx
  DWORD v28; // r13d
  __int64 v29; // rax
  int v30; // ebx
  DWORD v31; // ebx
  DWORD v32; // eax
  DWORD v33; // eax
  unsigned int v34; // eax
  DWORD v35; // eax
  DWORD v36; // eax
  unsigned int v37; // eax
  DWORD v38; // eax
  DWORD v39; // eax
  unsigned int v40; // eax
  GUID *v41; // rcx
  int v42; // edx
  int v43; // r8d
  int v44; // edx
  int v45; // r8d
  __int64 v46; // rax
  int v47; // r9d
  __int64 *v48; // rcx
  __int64 v49; // rax
  int *v50; // rdx
  int v51; // edx
  int v52; // r8d
  __int64 v53; // rax
  int v54; // r9d
  char *v55; // rax
  __int64 *v56; // rcx
  __int64 v57; // rax
  unsigned int *v58; // rax
  PVOID *v59; // rdx
  _UNKNOWN **v60; // r8
  __int64 *v61; // rcx
  __int64 v62; // rax
  unsigned int *v63; // rax
  PVOID *v64; // rdx
  const GUID *v65; // r8
  __int64 *v66; // rcx
  __int64 v67; // rax
  std::_Ref_count_base *v68; // rcx
  DWORD AcValueIndex; // [rsp+20h] [rbp-99h]
  DWORD AcValueIndexa; // [rsp+20h] [rbp-99h]
  DWORD AcValueIndexb; // [rsp+20h] [rbp-99h]
  DWORD AcValueIndexc; // [rsp+20h] [rbp-99h]
  int v73; // [rsp+40h] [rbp-79h]
  GUID *SchemeGuid; // [rsp+60h] [rbp-59h] BYREF
  int v75; // [rsp+68h] [rbp-51h]
  int v76; // [rsp+6Ch] [rbp-4Dh]
  int v77; // [rsp+70h] [rbp-49h]
  DWORD DcValueIndex; // [rsp+74h] [rbp-45h]
  char v79[8]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v80[16]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v81[16]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v82[16]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 **v83; // [rsp+B0h] [rbp-9h]
  HANDLE Handles; // [rsp+B8h] [rbp-1h] BYREF
  GUID *ActivePolicyGuid; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v86; // [rsp+C8h] [rbp+Fh]
  __int64 v87; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v83 = a3;
  v77 = 0;
  v5 = 1;
  if ( a2 && !*(_BYTE *)(a1 + 304) )
  {
    *(_BYTE *)(a1 + 304) = 1;
    Handles = *(HANDLE *)(a1 + 312);
    ActivePolicyGuid = *(GUID **)(a1 + 320);
    v86 = *(_QWORD *)(a1 + 328);
    v87 = *(_QWORD *)(a1 + 336);
    v6 = WaitForMultipleObjects(4u, &Handles, 1, 0x1388u);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl'::`2'::impl);
    v9 = -1;
    if ( IsEnabled && (v6 == -1 || v6 == 258) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        v11 = 0;
      }
      v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( v6 == -1 )
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
        }
        else
        {
          LastError = 0;
        }
        LOBYTE(v8) = v12;
        LOBYTE(v9) = v11;
        WPP_RECORDER_AND_TRACE_SF_sDDq(
          v10[2],
          v9,
          v8,
          v10[5],
          2,
          19,
          22,
          &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
          v73,
          v6,
          LastError,
          a1);
      }
    }
    if ( v6 != 3 )
    {
      if ( v6 == -1 )
        v14 = GetLastError();
      else
        v14 = 0;
      MicrosoftTelemetryAssertTriggeredArgs("Microsoft.Graphics.Display.DisplayEnhancementService.dll", v6, v14);
    }
  }
  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v79,
    (struct wil::srwlock *)(a1 + 8));
  v15 = (_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 16) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v79);
    goto LABEL_156;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
    || (v16 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v16 = 0;
  }
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(**a3 + 24))(*a3, &Handles);
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17, v18, v19);
    WPP_RECORDER_AND_TRACE_SF_sSq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      4,
      19,
      23,
      &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
      v73,
      v20,
      a1);
    std::wstring::_Tidy_deallocate(&Handles);
  }
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>::operator=(
    a1 + 16,
    a3);
  if ( Microsoft::Windows::DisplayEnhancement::Foundation::IsDesktopOS(v21) )
  {
    SchemeGuid = 0;
    Handles = &SchemeGuid;
    ActivePolicyGuid = 0;
    LOBYTE(v86) = 1;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
    if ( ActiveScheme )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
        (const char *)ActiveScheme,
        AcValueIndex);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&Handles);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 520LL))(*v15, v80);
    v23 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 520LL))(*v15, v81);
    v24 = 2;
    v77 = 2;
    v25 = 100;
    if ( *(_DWORD *)(v23 + 8) <= 0x64u )
    {
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 520LL))(*v15, v82);
      v77 = 6;
      v24 = 22;
      DcValueIndex = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, HANDLE *))(*(_QWORD *)*v15 + 520LL))(*v15, &Handles)
                               + 8);
    }
    else
    {
      DcValueIndex = 100;
    }
    if ( (v24 & 0x10) != 0 )
      v24 &= ~0x10u;
    if ( (v24 & 8) != 0 )
      v24 &= ~8u;
    if ( (v24 & 4) != 0 )
      v24 &= ~4u;
    if ( (v24 & 2) != 0 )
      v24 &= ~2u;
    if ( (v24 & 1) != 0 )
      v24 &= ~1u;
    (*(void (__fastcall **)(_QWORD, HANDLE *))(*(_QWORD *)*v15 + 472LL))(*v15, &Handles);
    v26 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 472LL))(*v15, v82);
    v27 = v24 | 0x20;
    v77 = v27;
    if ( (unsigned int)(int)(float)(*(float *)(v26 + 8) * 100.0) <= 0x64 )
    {
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 472LL))(*v15, v81);
      v77 = v27 | 0x40;
      v27 |= 0xC0u;
      v28 = (int)(float)(*(float *)((*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 472LL))(*v15, v80) + 8)
                       * 100.0);
    }
    else
    {
      v28 = 100;
    }
    if ( (v27 & 0x80u) != 0 )
      v27 &= ~0x80u;
    if ( (v27 & 0x40) != 0 )
      v27 &= ~0x40u;
    if ( (v27 & 0x20) != 0 )
      v27 &= ~0x20u;
    (*(void (__fastcall **)(_QWORD, HANDLE *))(*(_QWORD *)*v15 + 400LL))(*v15, &Handles);
    v29 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 400LL))(*v15, v82);
    v30 = v27 | 0x100;
    v77 = v30;
    if ( (unsigned int)(int)(float)(*(float *)(v29 + 8) * 100.0) <= 0x64 )
    {
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 400LL))(*v15, v81);
      v77 = v30 | 0x200;
      v25 = (int)(float)(*(float *)((*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 400LL))(*v15, v80) + 8)
                       * 100.0);
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 40LL))(*v15) )
    {
      v31 = DcValueIndex;
      v32 = PowerWriteACValueIndex(
              0,
              SchemeGuid,
              &GUID_VIDEO_SUBGROUP,
              &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
              DcValueIndex);
      if ( v32 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1E8,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v32,
          AcValueIndexa);
      v33 = PowerWriteDCValueIndex(0, SchemeGuid, &GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS, v31);
      if ( v33 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1EA,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v33,
          AcValueIndex);
      v34 = PowerApplySettingChanges(&GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS);
      if ( v34 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1EB,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v34,
          AcValueIndex);
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 56LL))(*v15) )
    {
      v35 = PowerWriteACValueIndex(
              0,
              SchemeGuid,
              &GUID_VIDEO_SUBGROUP,
              &GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS,
              v28);
      if ( v35 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F0,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v35,
          AcValueIndexb);
      v36 = PowerWriteDCValueIndex(
              0,
              SchemeGuid,
              &GUID_VIDEO_SUBGROUP,
              &GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS,
              v28);
      if ( v36 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F1,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v36,
          AcValueIndex);
      v37 = PowerApplySettingChanges(&GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS);
      if ( v37 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F2,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v37,
          AcValueIndex);
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 48LL))(*v15) )
    {
      v38 = PowerWriteACValueIndex(0, SchemeGuid, &GUID_ENERGY_SAVER_SUBGROUP, &GUID_ENERGY_SAVER_BRIGHTNESS, v25);
      if ( v38 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v38,
          AcValueIndexc);
      v39 = PowerWriteDCValueIndex(0, SchemeGuid, &GUID_ENERGY_SAVER_SUBGROUP, &GUID_ENERGY_SAVER_BRIGHTNESS, v25);
      if ( v39 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v39,
          AcValueIndex);
      v40 = PowerApplySettingChanges(&GUID_ENERGY_SAVER_SUBGROUP, &GUID_ENERGY_SAVER_BRIGHTNESS);
      if ( v40 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
          (const char *)v40,
          AcValueIndex);
    }
    v41 = SchemeGuid;
    SchemeGuid = 0;
    if ( v41 )
      LocalFree(v41);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v79);
  Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim::CheckAndRegisterForCurrentMonitorBrightnessDisplay(
    a1,
    a3);
  Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard *)v79,
    (struct wil::srwlock *)(a1 + 176));
  if ( *(_QWORD *)(a1 + 224) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl'::`2'::impl) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || (LOBYTE(v44) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v44) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v45) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v45) = 0;
      }
      if ( (_BYTE)v44 || (_BYTE)v45 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v44,
          v45,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          19,
          25,
          &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
          v73,
          **(_DWORD **)(a1 + 224),
          a1);
      goto LABEL_92;
    }
    v46 = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(**a3 + 520))(*a3, &Handles);
    v47 = **(_DWORD **)(a1 + 224);
    if ( *(_DWORD *)(v46 + 8) != v47 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || (LOBYTE(v42) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v42) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v43) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v43) = 0;
      }
      if ( (_BYTE)v42 || (_BYTE)v43 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          v43,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          19,
          24,
          &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
          v73,
          v47,
          a1);
LABEL_92:
      v48 = *a3;
      v49 = **a3;
      SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
      v50 = *(int **)(a1 + 224);
LABEL_107:
      v75 = *v50;
      v76 = 4;
      SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
      (*(void (__fastcall **)(__int64 *, GUID **))(v49 + 528))(v48, &SchemeGuid);
    }
  }
  else if ( *(_QWORD *)(a1 + 184) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl'::`2'::impl) )
    {
      v53 = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(**a3 + 520))(*a3, &Handles);
      v54 = **(_DWORD **)(a1 + 184);
      if ( *(_DWORD *)(v53 + 8) == v54 )
        goto LABEL_118;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || (LOBYTE(v42) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v42) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v43) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v43) = 0;
      }
      if ( (_BYTE)v42 || (_BYTE)v43 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          v43,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          19,
          26,
          &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
          v73,
          v54,
          a1);
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || (LOBYTE(v51) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v51) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v52) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v52) = 0;
      }
      if ( (_BYTE)v51 || (_BYTE)v52 )
        WPP_RECORDER_AND_TRACE_SF_sdq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v51,
          v52,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          19,
          27,
          &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
          v73,
          **(_DWORD **)(a1 + 184),
          a1);
    }
    v48 = *a3;
    v49 = **a3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
    v50 = *(int **)(a1 + 184);
    goto LABEL_107;
  }
LABEL_118:
  v55 = *(char **)(a1 + 192);
  if ( v55 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || (LOBYTE(v42) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    {
      LOBYTE(v42) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v43) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
    {
      LOBYTE(v43) = 0;
    }
    if ( (_BYTE)v42 || (_BYTE)v43 )
      WPP_RECORDER_AND_TRACE_SF_sdq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v42,
        v43,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        5,
        19,
        28,
        &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
        v73,
        *v55,
        a1);
    v56 = *a3;
    v57 = **a3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
    LOBYTE(v75) = **(_BYTE **)(a1 + 192);
    v76 = 4;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    (*(void (__fastcall **)(__int64 *, GUID **))(v57 + 360))(v56, &SchemeGuid);
  }
  v58 = *(unsigned int **)(a1 + 200);
  if ( v58 )
  {
    v59 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || (LOBYTE(v59) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    {
      LOBYTE(v59) = 0;
    }
    v60 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v60) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
    {
      LOBYTE(v60) = 0;
    }
    if ( (_BYTE)v59 || (_BYTE)v60 )
      WPP_RECORDER_AND_TRACE_SF_sgq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (int)v59,
        (int)v60,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        AcValueIndex,
        19,
        29,
        &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
        v73,
        *(_OWORD *)&_mm_cvtps_pd((__m128)*v58),
        a1);
    v61 = *a3;
    v62 = **a3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
    v75 = **(_DWORD **)(a1 + 200);
    v76 = 3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    (*(void (__fastcall **)(__int64 *, GUID **))(v62 + 480))(v61, &SchemeGuid);
  }
  v63 = *(unsigned int **)(a1 + 208);
  if ( v63 )
  {
    v64 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || (LOBYTE(v64) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    {
      LOBYTE(v64) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
      v5 = 0;
    if ( (_BYTE)v64 || v5 )
    {
      v65 = &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids;
      LOBYTE(v65) = v5;
      WPP_RECORDER_AND_TRACE_SF_sgq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (int)v64,
        (int)v65,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        AcValueIndex,
        19,
        30,
        &WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids,
        v73,
        *(_OWORD *)&_mm_cvtps_pd((__m128)*v63),
        a1);
    }
    v66 = *a3;
    v67 = **a3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
    v75 = **(_DWORD **)(a1 + 208);
    v76 = 3;
    SchemeGuid = (GUID *)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    (*(void (__fastcall **)(__int64 *, GUID **))(v67 + 408))(v66, &SchemeGuid);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v79);
LABEL_156:
  v68 = (std::_Ref_count_base *)a3[1];
  if ( v68 )
    std::_Ref_count_base::_Decref(v68);
}

```

## disassembly

```asm
0x18007c86c  mov     [rsp-8+arg_8], rbx
0x18007c871  push    rbp
0x18007c872  push    rsi
0x18007c873  push    rdi
0x18007c874  push    r12
0x18007c876  push    r13
0x18007c878  push    r14
0x18007c87a  push    r15
0x18007c87c  lea     rbp, [rsp-27h]
0x18007c881  sub     rsp, 0E0h
0x18007c888  mov     rax, cs:__security_cookie
0x18007c88f  xor     rax, rsp
0x18007c892  mov     [rbp+57h+var_38], rax
0x18007c896  mov     r12, r8
0x18007c899  mov     rdi, rcx
0x18007c89c  mov     [rbp+57h+var_60], r8
0x18007c8a0  xor     r13d, r13d
0x18007c8a3  mov     [rbp+57h+var_A0], r13d
0x18007c8a7  lea     esi, [r13+1]
0x18007c8ab  lea     r15, WPP_GLOBAL_Control
0x18007c8b2  test    dl, dl
0x18007c8b4  jz      loc_18007CA07
0x18007c8ba  cmp     [rcx+130h], r13b
0x18007c8c1  jnz     loc_18007CA07
0x18007c8c7  mov     [rcx+130h], sil
0x18007c8ce  mov     rax, [rcx+138h]
0x18007c8d5  mov     [rbp+57h+Handles], rax
0x18007c8d9  mov     rax, [rcx+140h]
0x18007c8e0  mov     [rbp+57h+ActivePolicyGuid], rax
0x18007c8e4  mov     rax, [rcx+148h]
0x18007c8eb  mov     [rbp+57h+var_48], rax
0x18007c8ef  mov     rax, [rcx+150h]
0x18007c8f6  mov     [rbp+57h+var_40], rax
0x18007c8fa  mov     r9d, 1388h; dwMilliseconds
0x18007c900  mov     r8d, esi; bWaitAll
0x18007c903  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18007c907  lea     ecx, [rsi+3]; nCount
0x18007c90a  call    cs:__imp_WaitForMultipleObjects
0x18007c910  mov     ebx, eax
0x18007c912  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange> `wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl(void)'::`2'::impl
0x18007c919  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(void)
0x18007c91e  or      edx, 0FFFFFFFFh
0x18007c921  test    al, al
0x18007c923  jz      loc_18007C9E2
0x18007c929  cmp     ebx, edx
0x18007c92b  jz      short loc_18007C939
0x18007c92d  cmp     ebx, 102h
0x18007c933  jnz     loc_18007C9E2
0x18007c939  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c940  cmp     rcx, r15
0x18007c943  jz      short loc_18007C957
0x18007c945  test    dword ptr [rcx+1Ch], 40000h
0x18007c94c  jz      short loc_18007C957
0x18007c94e  cmp     byte ptr [rcx+19h], 2
0x18007c952  mov     r14b, sil
0x18007c955  jnb     short loc_18007C95A
0x18007c957  mov     r14b, r13b
0x18007c95a  lea     rax, WPP_RECORDER_INITIALIZED
0x18007c961  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18007c968  setnz   r15b
0x18007c96c  test    r14b, r14b
0x18007c96f  jnz     short loc_18007C976
0x18007c971  test    r15b, r15b
0x18007c974  jz      short loc_18007C9DB
0x18007c976  cmp     ebx, edx
0x18007c978  jnz     short loc_18007C995
0x18007c97a  call    cs:__imp_GetLastError
0x18007c980  test    eax, eax
0x18007c982  jle     short loc_18007C98C
0x18007c984  movzx   eax, ax
0x18007c987  or      eax, 80070000h
0x18007c98c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c993  jmp     short loc_18007C998
0x18007c995  mov     eax, r13d
0x18007c998  mov     qword ptr [rsp+110h+var_B8], rdi; char
0x18007c99d  mov     dword ptr [rsp+110h+var_C0], eax; char
0x18007c9a1  mov     dword ptr [rsp+110h+var_C8], ebx; char
0x18007c9a5  lea     rax, WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids
0x18007c9ac  mov     [rsp+110h+MessageGuid], rax; MessageGuid
0x18007c9b1  mov     [rsp+110h+var_E0], 16h; __int16
0x18007c9b8  mov     [rsp+110h+var_E8], 13h; int
0x18007c9c0  mov     byte ptr [rsp+110h+AcValueIndex], 2; char
0x18007c9c5  mov     r9, [rcx+28h]; int
0x18007c9c9  mov     r8b, r15b; int
0x18007c9cc  mov     dl, r14b; int
0x18007c9cf  mov     rcx, [rcx+10h]; int
0x18007c9d3  call    WPP_RECORDER_AND_TRACE_SF_sDDq
0x18007c9d8  or      edx, 0FFFFFFFFh
0x18007c9db  lea     r15, WPP_GLOBAL_Control
0x18007c9e2  cmp     ebx, 3
0x18007c9e5  jz      short loc_18007CA07
0x18007c9e7  cmp     ebx, edx
0x18007c9e9  jnz     short loc_18007C9F3
0x18007c9eb  call    cs:__imp_GetLastError
0x18007c9f1  jmp     short loc_18007C9F6
0x18007c9f3  mov     eax, r13d
0x18007c9f6  mov     r8d, eax
0x18007c9f9  mov     edx, ebx
0x18007c9fb  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x18007ca02  call    MicrosoftTelemetryAssertTriggeredArgs
0x18007ca07  lea     rdx, [rdi+8]; struct wil::srwlock *
0x18007ca0b  lea     rcx, [rbp+57h+var_98]; this
0x18007ca0f  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18007ca14  nop
0x18007ca15  lea     r14, [rdi+10h]
0x18007ca19  cmp     [r14], r13
0x18007ca1c  jnz     loc_18007D453
0x18007ca22  mov     rax, cs:WPP_GLOBAL_Control
0x18007ca29  cmp     rax, r15
0x18007ca2c  jz      short loc_18007CA40
0x18007ca2e  test    dword ptr [rax+1Ch], 40000h
0x18007ca35  jz      short loc_18007CA40
0x18007ca37  cmp     byte ptr [rax+19h], 4
0x18007ca3b  mov     bl, sil
0x18007ca3e  jnb     short loc_18007CA43
0x18007ca40  mov     bl, r13b
0x18007ca43  lea     rax, WPP_RECORDER_INITIALIZED
0x18007ca4a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18007ca51  setnz   r15b
0x18007ca55  test    bl, bl
0x18007ca57  jnz     short loc_18007CA5E
0x18007ca59  test    r15b, r15b
0x18007ca5c  jz      short loc_18007CAC6
0x18007ca5e  mov     rcx, [r12]
0x18007ca62  mov     rax, [rcx]
0x18007ca65  lea     rdx, [rbp+57h+Handles]
0x18007ca69  mov     rax, [rax+18h]
0x18007ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca72  mov     rcx, rax
0x18007ca75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ca7a  mov     qword ptr [rsp+110h+var_C0], rdi; char
0x18007ca7f  mov     qword ptr [rsp+110h+var_C8], rax; __int64
0x18007ca84  lea     rax, WPP_bc81babb0b413ffa4fc194d6c423ba98_Traceguids
0x18007ca8b  mov     [rsp+110h+MessageGuid], rax; MessageGuid
0x18007ca90  mov     [rsp+110h+var_E0], 17h; __int16
0x18007ca97  mov     [rsp+110h+var_E8], 13h; int
0x18007ca9f  mov     byte ptr [rsp+110h+AcValueIndex], 4; unsigned int
0x18007caa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007caab  mov     r9, [rcx+28h]
0x18007caaf  mov     r8b, r15b
0x18007cab2  mov     dl, bl
0x18007cab4  mov     rcx, [rcx+10h]; LoggerHandle
0x18007cab8  call    WPP_RECORDER_AND_TRACE_SF_sSq
0x18007cabd  lea     rcx, [rbp+57h+Handles]
0x18007cac1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007cac6  mov     rdx, r12
0x18007cac9  mov     rcx, r14
0x18007cacc  call    ??4?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>::operator=(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup> const &)
0x18007cad1  call    ?IsDesktopOS@Foundation@DisplayEnhancement@Windows@Microsoft@@YA_NXZ; Microsoft::Windows::DisplayEnhancement::Foundation::IsDesktopOS(void)
0x18007cad6  test    al, al
0x18007cad8  jz      loc_18007CEAB
0x18007cade  mov     [rbp+57h+SchemeGuid], r13
0x18007cae2  lea     rax, [rbp+57h+SchemeGuid]
0x18007cae6  mov     [rbp+57h+Handles], rax
0x18007caea  mov     [rbp+57h+ActivePolicyGuid], r13
0x18007caee  mov     byte ptr [rbp+57h+var_48], sil
0x18007caf2  lea     rdx, [rbp+57h+ActivePolicyGuid]; ActivePolicyGuid
0x18007caf6  xor     ecx, ecx; UserRootPowerKey
0x18007caf8  call    cs:__imp_PowerGetActiveScheme
0x18007cafe  mov     rcx, [rbp+5Fh]; this
0x18007cb02  test    eax, eax
0x18007cb04  jnz     loc_18007D4BD
0x18007cb0a  lea     rcx, [rbp+57h+Handles]
0x18007cb0e  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18007cb13  mov     rcx, [r14]
0x18007cb16  mov     rax, [rcx]
0x18007cb19  lea     rdx, [rbp+57h+var_90]
0x18007cb1d  mov     rax, [rax+208h]
0x18007cb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb29  nop
0x18007cb2a  mov     rcx, [r14]
0x18007cb2d  mov     rax, [rcx]
0x18007cb30  lea     rdx, [rbp+57h+var_80]
0x18007cb34  mov     rax, [rax+208h]
0x18007cb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb40  nop
0x18007cb41  mov     ebx, 2
0x18007cb46  mov     [rbp+57h+var_A0], ebx
0x18007cb49  lea     r15d, [rbx+62h]
0x18007cb4d  cmp     [rax+8], r15d
0x18007cb51  jbe     short loc_18007CB59
0x18007cb53  mov     [rbp+57h+DcValueIndex], r15d
0x18007cb57  jmp     short loc_18007CB98
0x18007cb59  mov     rcx, [r14]
0x18007cb5c  mov     rax, [rcx]
0x18007cb5f  lea     rdx, [rbp+57h+var_70]
0x18007cb63  mov     rax, [rax+208h]
0x18007cb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb6f  nop
0x18007cb70  mov     [rbp+57h+var_A0], 6
0x18007cb77  mov     rcx, [r14]
0x18007cb7a  mov     rax, [rcx]
0x18007cb7d  lea     rdx, [rbp+57h+Handles]
0x18007cb81  mov     rax, [rax+208h]
0x18007cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb8d  mov     ebx, 16h
0x18007cb92  mov     eax, [rax+8]
0x18007cb95  mov     [rbp+57h+DcValueIndex], eax
0x18007cb98  test    bl, 10h
0x18007cb9b  jz      short loc_18007CBA0
0x18007cb9d  and     ebx, 0FFFFFFEFh
0x18007cba0  test    bl, 8
0x18007cba3  jz      short loc_18007CBA8
0x18007cba5  and     ebx, 0FFFFFFF7h
0x18007cba8  test    bl, 4
0x18007cbab  jz      short loc_18007CBB0
0x18007cbad  and     ebx, 0FFFFFFFBh
0x18007cbb0  test    bl, 2
0x18007cbb3  jz      short loc_18007CBB8
0x18007cbb5  and     ebx, 0FFFFFFFDh
0x18007cbb8  test    sil, bl
0x18007cbbb  jz      short loc_18007CBC0
0x18007cbbd  and     ebx, 0FFFFFFFEh
0x18007cbc0  mov     rcx, [r14]
0x18007cbc3  mov     rax, [rcx]
0x18007cbc6  lea     rdx, [rbp+57h+Handles]
0x18007cbca  mov     rax, [rax+1D8h]
0x18007cbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cbd6  nop
0x18007cbd7  mov     rcx, [r14]
0x18007cbda  mov     rax, [rcx]
0x18007cbdd  lea     rdx, [rbp+57h+var_70]
0x18007cbe1  mov     rax, [rax+1D8h]
0x18007cbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cbed  nop
0x18007cbee  or      ebx, 20h
0x18007cbf1  mov     [rbp+57h+var_A0], ebx
0x18007cbf4  movss   xmm0, dword ptr [rax+8]
0x18007cbf9  mulss   xmm0, cs:__real@42c80000
0x18007cc01  cvttss2si rax, xmm0
0x18007cc06  cmp     eax, r15d
0x18007cc09  jbe     short loc_18007CC10
0x18007cc0b  mov     r13d, r15d
0x18007cc0e  jmp     short loc_18007CC59
0x18007cc10  mov     rcx, [r14]
0x18007cc13  mov     rax, [rcx]
0x18007cc16  lea     rdx, [rbp+57h+var_80]
0x18007cc1a  mov     rax, [rax+1D8h]
0x18007cc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc26  nop
0x18007cc27  or      ebx, 40h
0x18007cc2a  mov     [rbp+57h+var_A0], ebx
0x18007cc2d  mov     rcx, [r14]
0x18007cc30  mov     rax, [rcx]
0x18007cc33  lea     rdx, [rbp+57h+var_90]
0x18007cc37  mov     rax, [rax+1D8h]
0x18007cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc43  bts     ebx, 7
0x18007cc47  movss   xmm0, dword ptr [rax+8]
0x18007cc4c  mulss   xmm0, cs:__real@42c80000
0x18007cc54  cvttss2si r13, xmm0
0x18007cc59  test    bl, bl
0x18007cc5b  jns     short loc_18007CC61
0x18007cc5d  btr     ebx, 7
0x18007cc61  test    bl, 40h
0x18007cc64  jz      short loc_18007CC69
0x18007cc66  and     ebx, 0FFFFFFBFh
0x18007cc69  test    bl, 20h
0x18007cc6c  jz      short loc_18007CC71
0x18007cc6e  and     ebx, 0FFFFFFDFh
0x18007cc71  mov     rcx, [r14]
0x18007cc74  mov     rax, [rcx]
0x18007cc77  lea     rdx, [rbp+57h+Handles]
0x18007cc7b  mov     rax, [rax+190h]
0x18007cc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc87  nop
0x18007cc88  mov     rcx, [r14]
0x18007cc8b  mov     rax, [rcx]
0x18007cc8e  lea     rdx, [rbp+57h+var_70]
0x18007cc92  mov     rax, [rax+190h]
0x18007cc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc9e  nop
0x18007cc9f  bts     ebx, 8
0x18007cca3  mov     [rbp+57h+var_A0], ebx
0x18007cca6  movss   xmm0, dword ptr [rax+8]
0x18007ccab  mulss   xmm0, cs:__real@42c80000
0x18007ccb3  cvttss2si rax, xmm0
0x18007ccb8  cmp     eax, r15d
0x18007ccbb  ja      short loc_18007CD03
0x18007ccbd  mov     rcx, [r14]
0x18007ccc0  mov     rax, [rcx]
0x18007ccc3  lea     rdx, [rbp+57h+var_80]
0x18007ccc7  mov     rax, [rax+190h]
0x18007ccce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ccd3  nop
0x18007ccd4  bts     ebx, 9
0x18007ccd8  mov     [rbp+57h+var_A0], ebx
0x18007ccdb  mov     rcx, [r14]
0x18007ccde  mov     rax, [rcx]
0x18007cce1  lea     rdx, [rbp+57h+var_90]
0x18007cce5  mov     rax, [rax+190h]
0x18007ccec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ccf1  movss   xmm0, dword ptr [rax+8]
0x18007ccf6  mulss   xmm0, cs:__real@42c80000
0x18007ccfe  cvttss2si r15, xmm0
0x18007cd03  mov     rcx, [r14]
0x18007cd06  mov     rax, [rcx]
0x18007cd09  mov     rax, [rax+28h]
0x18007cd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd12  lea     rbx, GUID_VIDEO_SUBGROUP
  ... truncated ...
```
