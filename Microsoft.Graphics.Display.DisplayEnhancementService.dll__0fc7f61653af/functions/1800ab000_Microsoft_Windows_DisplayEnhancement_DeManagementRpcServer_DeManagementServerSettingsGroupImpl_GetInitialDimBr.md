# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialDimBrightnessMultiplierGuidValue(void)

- ea: `0x1800ab000`
- end: `0x1800ab311`
- name: `?GetInitialDimBrightnessMultiplierGuidValue@DeManagementServerSettingsGroupImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@AEAAMXZ`
- size: `785`
- prototype: `float __fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bd480`

## callees

- `0x180005860`
- `0x180009b3c`
- `0x18000f778`
- `0x18000fa0c`
- `0x18000fa98`
- `0x18000fcf4`
- `0x18000fdd8`
- `0x18001c65c`
- `0x18001eb18`
- `0x18001f958`
- `0x18002a278`
- `0x18002a65c`
- `0x18006ce0c`
- `0x1800754ac`
- `0x18009f8ec`
- `0x1800ab000`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800ab139`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800ab139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab294`
- `POWRPROF!PowerReadDCValue` at `0x1800ab1b5`
- `POWRPROF!PowerReadDCValue` at `0x1800ab1b5`
- `POWRPROF!PowerReadACValue` at `0x1800ab211`
- `POWRPROF!PowerReadACValue` at `0x1800ab211`

## string_xrefs

- `0x1800ab14e`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`
- `0x1800ab1ca`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`
- `0x1800ab226`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
float __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialDimBrightnessMultiplierGuidValue(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *this)
{
  __int64 v2; // rax
  __int64 (__fastcall *v3)(__int64, GUID **, GUID **, _QWORD); // r10
  __int64 v4; // r11
  __int64 *v5; // rdx
  DWORD ActiveScheme; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  const char *v9; // r9
  float v10; // xmm2_4
  GUID *v11; // rcx
  float v12; // xmm6_4
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int Type; // [rsp+20h] [rbp-108h]
  unsigned int Typea; // [rsp+20h] [rbp-108h]
  DWORD BufferSize; // [rsp+40h] [rbp-E8h] BYREF
  int v19; // [rsp+44h] [rbp-E4h] BYREF
  GUID *SchemeGuid; // [rsp+48h] [rbp-E0h] BYREF
  BYTE v21[4]; // [rsp+50h] [rbp-D8h] BYREF
  UCHAR Buffer[4]; // [rsp+54h] [rbp-D4h] BYREF
  wil *v23; // [rsp+58h] [rbp-D0h] BYREF
  GUID *ActivePolicyGuid[2]; // [rsp+60h] [rbp-C8h] BYREF
  char v25; // [rsp+70h] [rbp-B8h]
  std::_Ref_count_base *v26[2]; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+90h] [rbp-98h] BYREF
  std::_Ref_count_base *v28; // [rsp+98h] [rbp-90h]
  _BYTE v29[32]; // [rsp+A0h] [rbp-88h] BYREF
  unsigned int v30[16]; // [rsp+C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter,>(&v27);
  *(_OWORD *)v26 = 0;
  v23 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v23,
    0);
  v19 = 1061997773;
  v2 = _lambda_e33cf7eca0821ae7a67a0f116eee0b6a_::_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_(v29, this, &v19, &v23);
  std::function_void___cdecl_void___unsigned_long__::function_void___cdecl_void___unsigned_long____lambda_00040f37b15831b64603e20200855dba__0_(
    v30,
    v2);
  try
  {
    *(GUID *)ActivePolicyGuid = GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS;
    v5 = (__int64 *)v3(v4, &SchemeGuid, ActivePolicyGuid, 0);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>::operator=<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration,std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>,0>(
      v26,
      v5);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>(&SchemeGuid);
    std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(v30);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3B3,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagements"
                    "erversettingsgroup.cpp",
      v15);
  }
  if ( !wil::handle_wait(v23, (void *)0x7D0, v14, (int)v15) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    SchemeGuid = 0;
    ActivePolicyGuid[0] = (GUID *)&SchemeGuid;
    ActivePolicyGuid[1] = 0;
    v25 = 1;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid[1]);
    try
    {
      if ( ActiveScheme )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x3BD,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)ActiveScheme,
          (unsigned int)v30);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(ActivePolicyGuid);
      *(_DWORD *)Buffer = 0;
      *(_DWORD *)v21 = 0;
      BufferSize = 4;
      v7 = PowerReadDCValue(
             0,
             SchemeGuid,
             &GUID_VIDEO_SUBGROUP,
             &GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS,
             0,
             Buffer,
             &BufferSize);
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x3C8,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)v7,
          Type);
      BufferSize = 4;
      v8 = PowerReadACValue(
             0,
             SchemeGuid,
             &GUID_VIDEO_SUBGROUP,
             &GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS,
             0,
             v21,
             &BufferSize);
      if ( v8 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x3D0,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)v8,
          Typea);
      v10 = fmaxf(fmaxf((float)*(int *)v21 / 100.0, (float)*(int *)Buffer / 100.0), 0.001);
      if ( v10 >= 1.0 )
        v10 = FLOAT_1_0;
      v19 = LODWORD(v10);
      v11 = SchemeGuid;
      SchemeGuid = 0;
      if ( v11 )
        LocalFree(v11);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x3D4,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagemen"
                      "tserversettingsgroup.cpp",
        v9);
    }
  }
  std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(v26);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(&v27);
  v12 = *(float *)&v19;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  return v12;
}

```

## disassembly

```asm
0x1800ab000  mov     rax, rsp
0x1800ab003  push    rdi
0x1800ab004  sub     rsp, 120h
0x1800ab00b  movaps  xmmword ptr [rax-18h], xmm6
0x1800ab00f  mov     rax, cs:__security_cookie
0x1800ab016  xor     rax, rsp
0x1800ab019  mov     [rsp+128h+var_28], rax
0x1800ab021  mov     rdi, rcx
0x1800ab024  lea     rcx, [rsp+128h+var_98]
0x1800ab02c  call    ??$make_shared@VPowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VPowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter,>(void)
0x1800ab031  nop
0x1800ab032  xorps   xmm0, xmm0
0x1800ab035  movdqu  xmmword ptr [rsp+128h+var_A8], xmm0
0x1800ab03e  mov     [rsp+128h+var_D0], 0
0x1800ab047  xor     edx, edx
0x1800ab049  lea     rcx, [rsp+128h+var_D0]
0x1800ab04e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800ab053  mov     [rsp+128h+var_E4], 3F4CCCCDh
0x1800ab05b  mov     r11, [rsp+128h+var_98]
0x1800ab063  mov     rax, [r11]
0x1800ab066  mov     r10, [rax+8]
0x1800ab06a  lea     r9, [rsp+128h+var_D0]
0x1800ab06f  lea     r8, [rsp+128h+var_E4]
0x1800ab074  mov     rdx, rdi
0x1800ab077  lea     rcx, [rsp+128h+var_88]
0x1800ab07f  call    ??0_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_@@QEAA@PEAV?$DeviceWatcherAdapterImpl@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; _lambda_e33cf7eca0821ae7a67a0f116eee0b6a_::_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_(Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl> *,std::wstring const &,bool &)
0x1800ab084  mov     rdx, rax
0x1800ab087  lea     rcx, [rsp+128h+var_68]
0x1800ab08f  call    std__function_void___cdecl_void___unsigned_long____function_void___cdecl_void___unsigned_long____lambda_00040f37b15831b64603e20200855dba__0_
0x1800ab094  nop
0x1800ab095  movups  xmm2, xmmword ptr cs:GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS.Data1
0x1800ab09c  movdqu  xmmword ptr [rsp+128h+ActivePolicyGuid], xmm2
0x1800ab0a2  lea     rax, [rsp+128h+var_68]
0x1800ab0aa  mov     [rsp+128h+Type], rax; unsigned int
0x1800ab0af  xor     r9d, r9d
0x1800ab0b2  lea     r8, [rsp+128h+ActivePolicyGuid]
0x1800ab0b7  lea     rdx, [rsp+128h+SchemeGuid]
0x1800ab0bc  mov     rcx, r11
0x1800ab0bf  mov     rax, r10
0x1800ab0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0c7  nop
0x1800ab0c8  mov     rdx, rax
0x1800ab0cb  lea     rcx, [rsp+128h+var_A8]
0x1800ab0d3  call    ??$?4VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@$0A@@?$shared_ptr@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>::operator=<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration,std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>,0>(std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration> &&)
0x1800ab0d8  nop
0x1800ab0d9  lea     rcx, [rsp+128h+SchemeGuid]
0x1800ab0de  call    ??1?$unique_ptr@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>(void)
0x1800ab0e3  nop
0x1800ab0e4  lea     rcx, [rsp+128h+var_68]
0x1800ab0ec  call    ??1?$function@$$A6A?AVDeManagementULongSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@XZ@std@@QEAA@XZ; std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(void)
0x1800ab0f1  nop
0x1800ab0f2  jmp     short $+2
0x1800ab0f4  mov     edx, 7D0h; void *
0x1800ab0f9  mov     rcx, [rsp+128h+var_D0]; this
0x1800ab0fe  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800ab103  test    al, al
0x1800ab105  jnz     loc_1800AB29D
0x1800ab10b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ab110  nop
0x1800ab111  mov     [rsp+128h+SchemeGuid], 0
0x1800ab11a  lea     rax, [rsp+128h+SchemeGuid]
0x1800ab11f  mov     [rsp+128h+ActivePolicyGuid], rax
0x1800ab124  mov     [rsp+128h+ActivePolicyGuid+8], 0
0x1800ab12d  mov     [rsp+128h+var_B8], 1
0x1800ab132  lea     rdx, [rsp+128h+ActivePolicyGuid+8]; ActivePolicyGuid
0x1800ab137  xor     ecx, ecx; UserRootPowerKey
0x1800ab139  call    cs:__imp_PowerGetActiveScheme
0x1800ab13f  mov     rcx, [rsp+128h]; this
0x1800ab147  test    eax, eax
0x1800ab149  jz      short loc_1800AB160
0x1800ab14b  mov     r9d, eax; char *
0x1800ab14e  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800ab155  mov     edx, 3BDh; void *
0x1800ab15a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab160  lea     rcx, [rsp+128h+ActivePolicyGuid]
0x1800ab165  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800ab16a  mov     dword ptr [rsp+128h+var_D4], 0
0x1800ab172  mov     dword ptr [rsp+128h+var_D8], 0
0x1800ab17a  mov     edi, 4
0x1800ab17f  mov     [rsp+128h+var_E8], edi
0x1800ab183  lea     rax, [rsp+128h+var_E8]
0x1800ab188  mov     [rsp+128h+BufferSize], rax; BufferSize
0x1800ab18d  lea     rax, [rsp+128h+var_D4]
0x1800ab192  mov     [rsp+128h+Buffer], rax; Buffer
0x1800ab197  mov     [rsp+128h+Type], 0; unsigned int
0x1800ab1a0  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS; PowerSettingGuid
0x1800ab1a7  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800ab1ae  mov     rdx, [rsp+128h+SchemeGuid]; SchemeGuid
0x1800ab1b3  xor     ecx, ecx; RootPowerKey
0x1800ab1b5  call    cs:__imp_PowerReadDCValue
0x1800ab1bb  mov     rcx, [rsp+128h]; this
0x1800ab1c3  test    eax, eax
0x1800ab1c5  jz      short loc_1800AB1DB
0x1800ab1c7  mov     r9d, eax; char *
0x1800ab1ca  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800ab1d1  mov     edx, 3C8h; void *
0x1800ab1d6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab1db  mov     [rsp+128h+var_E8], edi
0x1800ab1df  lea     rax, [rsp+128h+var_E8]
0x1800ab1e4  mov     [rsp+128h+BufferSize], rax; BufferSize
0x1800ab1e9  lea     rax, [rsp+128h+var_D8]
0x1800ab1ee  mov     [rsp+128h+Buffer], rax; Buffer
0x1800ab1f3  mov     [rsp+128h+Type], 0; unsigned int
0x1800ab1fc  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_DIM_BRIGHTNESS; PowerSettingGuid
0x1800ab203  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800ab20a  mov     rdx, [rsp+128h+SchemeGuid]; SchemeGuid
0x1800ab20f  xor     ecx, ecx; RootPowerKey
0x1800ab211  call    cs:__imp_PowerReadACValue
0x1800ab217  mov     rcx, [rsp+128h]; this
0x1800ab21f  test    eax, eax
0x1800ab221  jz      short loc_1800AB237
0x1800ab223  mov     r9d, eax; char *
0x1800ab226  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800ab22d  mov     edx, 3D0h; void *
0x1800ab232  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab237  mov     eax, dword ptr [rsp+128h+var_D8]
0x1800ab23b  xorps   xmm2, xmm2
0x1800ab23e  cvtsi2ss xmm2, rax
0x1800ab243  divss   xmm2, cs:__real@42c80000
0x1800ab24b  mov     eax, dword ptr [rsp+128h+var_D4]
0x1800ab24f  xorps   xmm0, xmm0
0x1800ab252  cvtsi2ss xmm0, rax
0x1800ab257  divss   xmm0, cs:__real@42c80000
0x1800ab25f  maxss   xmm2, xmm0
0x1800ab263  maxss   xmm2, cs:__real@3a83126f
0x1800ab26b  movss   xmm0, cs:__real@3f800000
0x1800ab273  comiss  xmm0, xmm2
0x1800ab276  ja      short loc_1800AB27B
0x1800ab278  movaps  xmm2, xmm0
0x1800ab27b  movss   [rsp+128h+var_E4], xmm2
0x1800ab281  mov     rcx, [rsp+128h+SchemeGuid]; hMem
0x1800ab286  mov     [rsp+128h+SchemeGuid], 0
0x1800ab28f  test    rcx, rcx
0x1800ab292  jz      short loc_1800AB29B
0x1800ab294  call    cs:__imp_LocalFree
0x1800ab29a  nop
0x1800ab29b  jmp     short $+2
0x1800ab29d  lea     rcx, [rsp+128h+var_A8]
0x1800ab2a5  call    ?reset@?$shared_ptr@V?$TokenWithStatus@UColorUpdate@ColorManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(void)
0x1800ab2aa  lea     rcx, [rsp+128h+var_98]
0x1800ab2b2  call    ?reset@?$shared_ptr@V?$TokenWithStatus@UColorUpdate@ColorManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(void)
0x1800ab2b7  movss   xmm6, [rsp+128h+var_E4]
0x1800ab2bd  lea     rcx, [rsp+128h+var_D0]
0x1800ab2c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ab2c7  nop
0x1800ab2c8  mov     rcx, [rsp+128h+var_A8+8]; this
0x1800ab2d0  test    rcx, rcx
0x1800ab2d3  jz      short loc_1800AB2DB
0x1800ab2d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ab2da  nop
0x1800ab2db  mov     rcx, [rsp+128h+var_90]; this
0x1800ab2e3  test    rcx, rcx
0x1800ab2e6  jz      short loc_1800AB2ED
0x1800ab2e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ab2ed  movaps  xmm0, xmm6
0x1800ab2f0  mov     rcx, [rsp+128h+var_28]
0x1800ab2f8  xor     rcx, rsp; StackCookie
0x1800ab2fb  call    __security_check_cookie
0x1800ab300  movaps  xmm6, [rsp+128h+var_18]
0x1800ab308  add     rsp, 120h
0x1800ab30f  pop     rdi
0x1800ab310  retn
```
