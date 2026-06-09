# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialBrightnessSliderGuidValue(void)

- ea: `0x1800aad08`
- end: `0x1800aaff9`
- name: `?GetInitialBrightnessSliderGuidValue@DeManagementServerSettingsGroupImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@AEAAIXZ`
- size: `753`
- prototype: `unsigned int __fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bd360`

## callees

- `0x180005860`
- `0x180007c58`
- `0x180009b3c`
- `0x18000f778`
- `0x18000fa0c`
- `0x18000fa98`
- `0x18000fdd8`
- `0x18001c65c`
- `0x18001eb18`
- `0x18001f958`
- `0x18002a278`
- `0x18002a65c`
- `0x18006ce0c`
- `0x1800754ac`
- `0x18009f920`
- `0x1800aad08`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800aae3f`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800aae3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaf7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaf7f`
- `POWRPROF!PowerReadDCValue` at `0x1800aaeaf`
- `POWRPROF!PowerReadDCValue` at `0x1800aaeaf`
- `POWRPROF!PowerReadACValue` at `0x1800aaf07`
- `POWRPROF!PowerReadACValue` at `0x1800aaf07`

## string_xrefs

- `0x1800aae54`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`
- `0x1800aaec4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`
- `0x1800aaf1c`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialBrightnessSliderGuidValue(
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
  int v10; // ecx
  int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  GUID *v14; // rcx
  unsigned int v15; // edi
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int Type; // [rsp+20h] [rbp-108h]
  unsigned int Typea; // [rsp+20h] [rbp-108h]
  int v21; // [rsp+40h] [rbp-E8h] BYREF
  BYTE v22[4]; // [rsp+44h] [rbp-E4h] BYREF
  DWORD BufferSize; // [rsp+48h] [rbp-E0h] BYREF
  GUID *SchemeGuid; // [rsp+50h] [rbp-D8h] BYREF
  UCHAR Buffer[8]; // [rsp+58h] [rbp-D0h] BYREF
  wil *v26[2]; // [rsp+60h] [rbp-C8h] BYREF
  GUID *ActivePolicyGuid[2]; // [rsp+70h] [rbp-B8h] BYREF
  char v28; // [rsp+80h] [rbp-A8h]
  std::_Ref_count_base *v29[2]; // [rsp+90h] [rbp-98h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-88h] BYREF
  std::_Ref_count_base *v31; // [rsp+A8h] [rbp-80h]
  _BYTE v32[32]; // [rsp+B0h] [rbp-78h] BYREF
  unsigned int v33[16]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter,>(&v30);
  *(_OWORD *)v29 = 0;
  *(_DWORD *)v22 = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v26,
    v22);
  v21 = 100;
  v2 = _lambda_e33cf7eca0821ae7a67a0f116eee0b6a_::_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_(v32, &v21, this, v26);
  std::function_void___cdecl_void___unsigned_long__::function_void___cdecl_void___unsigned_long____lambda_17f3ceb6d72abcf5c4c21a4d590fa019__0_(
    v33,
    v2);
  try
  {
    *(GUID *)ActivePolicyGuid = GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS;
    v5 = (__int64 *)v3(v4, &SchemeGuid, ActivePolicyGuid, 0);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>::operator=<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration,std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>,0>(
      v29,
      v5);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>(&SchemeGuid);
    std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(v33);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x374,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagements"
                    "erversettingsgroup.cpp",
      v18);
  }
  if ( !wil::handle_wait(v26[0], (void *)0x7D0, v17, (int)v18) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    SchemeGuid = 0;
    ActivePolicyGuid[0] = (GUID *)&SchemeGuid;
    ActivePolicyGuid[1] = 0;
    v28 = 1;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid[1]);
    try
    {
      if ( ActiveScheme )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x37E,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)ActiveScheme,
          (unsigned int)v33);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(ActivePolicyGuid);
      *(_DWORD *)Buffer = 0;
      *(_DWORD *)v22 = 0;
      BufferSize = 4;
      v7 = PowerReadDCValue(
             0,
             SchemeGuid,
             &GUID_VIDEO_SUBGROUP,
             &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
             0,
             Buffer,
             &BufferSize);
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x389,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)v7,
          Type);
      BufferSize = 4;
      v8 = PowerReadACValue(
             0,
             SchemeGuid,
             &GUID_VIDEO_SUBGROUP,
             &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
             0,
             v22,
             &BufferSize);
      if ( v8 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x391,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagem"
                        "entserversettingsgroup.cpp",
          (const char *)v8,
          Typea);
      v10 = *(_DWORD *)Buffer;
      v11 = *(_DWORD *)Buffer;
      if ( *(_DWORD *)v22 > *(_DWORD *)Buffer )
        v11 = *(_DWORD *)v22;
      if ( !v11 )
        goto LABEL_17;
      v12 = *(_DWORD *)Buffer;
      if ( *(_DWORD *)v22 > *(_DWORD *)Buffer )
        v12 = *(_DWORD *)v22;
      if ( v12 >= 0x64 )
      {
        v21 = 100;
      }
      else
      {
LABEL_17:
        v13 = *(_DWORD *)Buffer;
        if ( *(_DWORD *)v22 > *(_DWORD *)Buffer )
          v13 = *(_DWORD *)v22;
        if ( v13 )
        {
          if ( *(_DWORD *)v22 > *(_DWORD *)Buffer )
            v10 = *(_DWORD *)v22;
          v21 = v10;
        }
        else
        {
          v21 = 0;
        }
      }
      v14 = SchemeGuid;
      SchemeGuid = 0;
      if ( v14 )
        LocalFree(v14);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x395,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagemen"
                      "tserversettingsgroup.cpp",
        v9);
    }
  }
  std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(v29);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(&v30);
  v15 = v21;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v26);
  if ( v29[1] )
    std::_Ref_count_base::_Decref(v29[1]);
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  return v15;
}

```

## disassembly

```asm
0x1800aad08  mov     [rsp+arg_0], rbx
0x1800aad0d  push    rdi
0x1800aad0e  sub     rsp, 120h
0x1800aad15  mov     rax, cs:__security_cookie
0x1800aad1c  xor     rax, rsp
0x1800aad1f  mov     [rsp+128h+var_18], rax
0x1800aad27  mov     rbx, rcx
0x1800aad2a  lea     rcx, [rsp+128h+var_88]
0x1800aad32  call    ??$make_shared@VPowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VPowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter,>(void)
0x1800aad37  nop
0x1800aad38  xorps   xmm0, xmm0
0x1800aad3b  movdqu  xmmword ptr [rsp+128h+var_98], xmm0
0x1800aad44  mov     dword ptr [rsp+128h+var_E4], 1
0x1800aad4c  lea     rdx, [rsp+128h+var_E4]
0x1800aad51  lea     rcx, [rsp+128h+var_C8]
0x1800aad56  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800aad5b  nop
0x1800aad5c  mov     [rsp+128h+var_E8], 64h ; 'd'
0x1800aad64  mov     r11, [rsp+128h+var_88]
0x1800aad6c  mov     rax, [r11]
0x1800aad6f  mov     r10, [rax+8]
0x1800aad73  lea     r9, [rsp+128h+var_C8]
0x1800aad78  mov     r8, rbx
0x1800aad7b  lea     rdx, [rsp+128h+var_E8]
0x1800aad80  lea     rcx, [rsp+128h+var_78]
0x1800aad88  call    ??0_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_@@QEAA@PEAV?$DeviceWatcherAdapterImpl@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; _lambda_e33cf7eca0821ae7a67a0f116eee0b6a_::_lambda_e33cf7eca0821ae7a67a0f116eee0b6a_(Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl> *,std::wstring const &,bool &)
0x1800aad8d  mov     rdx, rax
0x1800aad90  lea     rcx, [rsp+128h+var_58]
0x1800aad98  call    std__function_void___cdecl_void___unsigned_long____function_void___cdecl_void___unsigned_long____lambda_17f3ceb6d72abcf5c4c21a4d590fa019__0_
0x1800aad9d  nop
0x1800aad9e  movups  xmm2, xmmword ptr cs:GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS.Data1
0x1800aada5  movdqu  xmmword ptr [rsp+128h+ActivePolicyGuid], xmm2
0x1800aadab  lea     rax, [rsp+128h+var_58]
0x1800aadb3  mov     [rsp+128h+Type], rax; unsigned int
0x1800aadb8  xor     r9d, r9d
0x1800aadbb  lea     r8, [rsp+128h+ActivePolicyGuid]
0x1800aadc0  lea     rdx, [rsp+128h+SchemeGuid]
0x1800aadc5  mov     rcx, r11
0x1800aadc8  mov     rax, r10
0x1800aadcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aadd0  nop
0x1800aadd1  mov     rdx, rax
0x1800aadd4  lea     rcx, [rsp+128h+var_98]
0x1800aaddc  call    ??$?4VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@$0A@@?$shared_ptr@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@VPowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>::operator=<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration,std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration>,0>(std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration> &&)
0x1800aade1  nop
0x1800aade2  lea     rcx, [rsp+128h+SchemeGuid]
0x1800aade7  call    ??1?$unique_ptr@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$DeviceWatcherAdapter@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapter<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>>(void)
0x1800aadec  nop
0x1800aaded  lea     rcx, [rsp+128h+var_58]
0x1800aadf5  call    ??1?$function@$$A6A?AVDeManagementULongSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@XZ@std@@QEAA@XZ; std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(void)
0x1800aadfa  nop
0x1800aadfb  jmp     short $+2
0x1800aadfd  mov     edx, 7D0h; void *
0x1800aae02  mov     rcx, [rsp+128h+var_C8]; this
0x1800aae07  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800aae0c  xor     ebx, ebx
0x1800aae0e  test    al, al
0x1800aae10  jnz     loc_1800AAF88
0x1800aae16  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800aae1b  nop
0x1800aae1c  mov     [rsp+128h+SchemeGuid], rbx
0x1800aae21  lea     rax, [rsp+128h+SchemeGuid]
0x1800aae26  mov     [rsp+128h+ActivePolicyGuid], rax
0x1800aae2b  mov     [rsp+128h+ActivePolicyGuid+8], rbx
0x1800aae30  mov     [rsp+128h+var_A8], 1
0x1800aae38  lea     rdx, [rsp+128h+ActivePolicyGuid+8]; ActivePolicyGuid
0x1800aae3d  xor     ecx, ecx; UserRootPowerKey
0x1800aae3f  call    cs:__imp_PowerGetActiveScheme
0x1800aae45  mov     rcx, [rsp+128h]; this
0x1800aae4d  test    eax, eax
0x1800aae4f  jz      short loc_1800AAE66
0x1800aae51  mov     r9d, eax; char *
0x1800aae54  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800aae5b  mov     edx, 37Eh; void *
0x1800aae60  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800aae66  lea     rcx, [rsp+128h+ActivePolicyGuid]
0x1800aae6b  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800aae70  mov     dword ptr [rsp+128h+var_D0], ebx
0x1800aae74  mov     dword ptr [rsp+128h+var_E4], ebx
0x1800aae78  mov     edi, 4
0x1800aae7d  mov     [rsp+128h+var_E0], edi
0x1800aae81  lea     rax, [rsp+128h+var_E0]
0x1800aae86  mov     [rsp+128h+BufferSize], rax; BufferSize
0x1800aae8b  lea     rax, [rsp+128h+var_D0]
0x1800aae90  mov     [rsp+128h+Buffer], rax; Buffer
0x1800aae95  mov     [rsp+128h+Type], rbx; unsigned int
0x1800aae9a  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS; PowerSettingGuid
0x1800aaea1  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800aaea8  mov     rdx, [rsp+128h+SchemeGuid]; SchemeGuid
0x1800aaead  xor     ecx, ecx; RootPowerKey
0x1800aaeaf  call    cs:__imp_PowerReadDCValue
0x1800aaeb5  mov     rcx, [rsp+128h]; this
0x1800aaebd  test    eax, eax
0x1800aaebf  jz      short loc_1800AAED5
0x1800aaec1  mov     r9d, eax; char *
0x1800aaec4  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800aaecb  mov     edx, 389h; void *
0x1800aaed0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800aaed5  mov     [rsp+128h+var_E0], edi
0x1800aaed9  lea     rax, [rsp+128h+var_E0]
0x1800aaede  mov     [rsp+128h+BufferSize], rax; BufferSize
0x1800aaee3  lea     rax, [rsp+128h+var_E4]
0x1800aaee8  mov     [rsp+128h+Buffer], rax; Buffer
0x1800aaeed  mov     [rsp+128h+Type], rbx; unsigned int
0x1800aaef2  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS; PowerSettingGuid
0x1800aaef9  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800aaf00  mov     rdx, [rsp+128h+SchemeGuid]; SchemeGuid
0x1800aaf05  xor     ecx, ecx; RootPowerKey
0x1800aaf07  call    cs:__imp_PowerReadACValue
0x1800aaf0d  mov     rcx, [rsp+128h]; this
0x1800aaf15  test    eax, eax
0x1800aaf17  jz      short loc_1800AAF2D
0x1800aaf19  mov     r9d, eax; char *
0x1800aaf1c  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800aaf23  mov     edx, 391h; void *
0x1800aaf28  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800aaf2d  mov     ecx, dword ptr [rsp+128h+var_D0]
0x1800aaf31  mov     eax, ecx
0x1800aaf33  mov     edx, dword ptr [rsp+128h+var_E4]
0x1800aaf37  cmp     edx, ecx
0x1800aaf39  cmova   eax, edx
0x1800aaf3c  test    eax, eax
0x1800aaf3e  jz      short loc_1800AAF56
0x1800aaf40  mov     eax, ecx
0x1800aaf42  cmp     edx, ecx
0x1800aaf44  cmova   eax, edx
0x1800aaf47  cmp     eax, 64h ; 'd'
0x1800aaf4a  jb      short loc_1800AAF56
0x1800aaf4c  mov     [rsp+128h+var_E8], 64h ; 'd'
0x1800aaf54  jmp     short loc_1800AAF70
0x1800aaf56  mov     eax, ecx
0x1800aaf58  cmp     edx, ecx
0x1800aaf5a  cmova   eax, edx
0x1800aaf5d  test    eax, eax
0x1800aaf5f  jz      short loc_1800AAF6C
0x1800aaf61  cmp     edx, ecx
0x1800aaf63  cmova   ecx, edx
0x1800aaf66  mov     [rsp+128h+var_E8], ecx
0x1800aaf6a  jmp     short loc_1800AAF70
0x1800aaf6c  mov     [rsp+128h+var_E8], ebx
0x1800aaf70  mov     rcx, [rsp+128h+SchemeGuid]; hMem
0x1800aaf75  mov     [rsp+128h+SchemeGuid], rbx
0x1800aaf7a  test    rcx, rcx
0x1800aaf7d  jz      short loc_1800AAF86
0x1800aaf7f  call    cs:__imp_LocalFree
0x1800aaf85  nop
0x1800aaf86  jmp     short $+2
0x1800aaf88  lea     rcx, [rsp+128h+var_98]
0x1800aaf90  call    ?reset@?$shared_ptr@V?$TokenWithStatus@UColorUpdate@ColorManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(void)
0x1800aaf95  lea     rcx, [rsp+128h+var_88]
0x1800aaf9d  call    ?reset@?$shared_ptr@V?$TokenWithStatus@UColorUpdate@ColorManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatus<Microsoft::Windows::DisplayEnhancement::ColorManagers::ColorUpdate>>::reset(void)
0x1800aafa2  mov     edi, [rsp+128h+var_E8]
0x1800aafa6  lea     rcx, [rsp+128h+var_C8]
0x1800aafab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aafb0  nop
0x1800aafb1  mov     rcx, [rsp+128h+var_98+8]; this
0x1800aafb9  test    rcx, rcx
0x1800aafbc  jz      short loc_1800AAFC4
0x1800aafbe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aafc3  nop
0x1800aafc4  mov     rcx, [rsp+128h+var_80]; this
0x1800aafcc  test    rcx, rcx
0x1800aafcf  jz      short loc_1800AAFD6
0x1800aafd1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aafd6  mov     eax, edi
0x1800aafd8  mov     rcx, [rsp+128h+var_18]
0x1800aafe0  xor     rcx, rsp; StackCookie
0x1800aafe3  call    __security_check_cookie
0x1800aafe8  mov     rbx, [rsp+128h+arg_0]
0x1800aaff0  add     rsp, 120h
0x1800aaff7  pop     rdi
0x1800aaff8  retn
```
