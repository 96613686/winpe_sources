# Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::InitializeAdapter(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009d6c0`
- end: `0x18009db43`
- name: `?InitializeAdapter@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1155`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005860`
- `0x180006440`
- `0x180009f68`
- `0x18000c234`
- `0x18000f778`
- `0x18000fa0c`
- `0x180013138`
- `0x18001ff40`
- `0x180029350`
- `0x180029404`
- `0x180037470`
- `0x18005b70c`
- `0x180063c54`
- `0x180063dd4`
- `0x180066310`
- `0x180066344`
- `0x1800847b4`
- `0x18009a150`
- `0x18009af08`
- `0x18009c934`
- `0x18009d6c0`
- `0x18009df78`
- `0x18009ea08`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18009d828`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18009d9e2`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18009d828`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18009d9e2`

## string_xrefs

- `0x18009dab3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009dac8`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009dadd`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009daf2`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009db07`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009db1c`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009db31`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::InitializeAdapter(
        Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *this,
        __int64 a2)
{
  int v4; // eax
  UINT32 *v5; // rsi
  int v6; // eax
  int v7; // eax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int DeviceInfo; // eax
  int v11; // eax
  int v12; // eax
  __int64 *v13; // rax
  char *v14; // rbx
  unsigned int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rcx
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v26; // [rsp+68h] [rbp-98h]
  __int128 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h]
  _BYTE v29[8]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v30; // [rsp+90h] [rbp-70h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[924]; // [rsp+B4h] [rbp-4Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  std::wstring::operator=((char *)this + 8);
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(v29);
  v24 = 0;
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(&v19, a2);
  v4 = Microsoft::WRL::ComPtr<Windows::Devices::Display::IDisplayMonitor>::As<Windows::Devices::Display::Internal::IDisplayMonitorInternal>(
         &v19,
         (__int64)&v24);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v4,
      v17);
  v23 = 0;
  v5 = (UINT32 *)((char *)this + 96);
  v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), char *))(*v19)[12])(
         v19,
         (char *)this + 96);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v6,
      v17);
  v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v19)[11])(v19, &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v7,
      v17);
  *((_QWORD *)this + 11) = v23;
  v8 = (_DWORD *)((char *)this + 100);
  v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), char *))(*v19)[8])(
         v19,
         (char *)this + 100);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v9,
      v17);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl'::`2'::impl) )
    *((_DWORD *)this + 34) = *v8;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl'::`2'::impl) )
  {
    memset_0(v32, 0, sizeof(v32));
    requestPacket.type = -7;
    requestPacket.size = 944;
    requestPacket.adapterId = (LUID)*((_QWORD *)this + 11);
    requestPacket.id = *v5;
    DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
    if ( DeviceInfo )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
        (const char *)DeviceInfo,
        v17);
    std::wstring::assign((char *)this + 56, v32);
  }
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RefreshBrightnessCapabilities(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl'::`2'::impl) )
  {
    Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(this);
    goto LABEL_34;
  }
  v20 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 80LL))(v24, &v20);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v11,
      v17);
  v12 = *v8;
  *((_DWORD *)this + 34) = *v8;
  if ( v12 == 1 )
  {
    if ( v20 == 1 )
    {
      *((_DWORD *)this + 34) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids);
      }
      goto LABEL_26;
    }
LABEL_21:
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 8LL))(*((_QWORD *)this + 15)) == 2
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl) )
    {
      LOBYTE(v18) = 0;
      v21 = 0;
      v27 = 0;
      v28 = 0;
      v22 = 0;
      v13 = (__int64 *)std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper,enum Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>,int,bool>(
                         (unsigned int)&v25,
                         (unsigned int)&v22,
                         (unsigned int)&v27,
                         (unsigned int)&v21,
                         (__int64)&v18);
      std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
        (_QWORD *)this + 15,
        v13);
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(&v27);
    }
    goto LABEL_26;
  }
  if ( v12 )
    goto LABEL_21;
LABEL_26:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl) )
  {
    v14 = (char *)this + 56;
  }
  else
  {
    memset_0(v32, 0, sizeof(v32));
    requestPacket.type = -7;
    requestPacket.size = 944;
    requestPacket.adapterId = (LUID)*((_QWORD *)this + 11);
    requestPacket.id = *v5;
    v15 = DisplayConfigGetDeviceInfo(&requestPacket);
    if ( v15 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
        (const char *)v15,
        v17);
    v14 = (char *)this + 56;
    std::wstring::assign((char *)this + 56, v32);
  }
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v25, v14);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::LogDisplayCapabilityEvent(
    v25,
    *((unsigned int *)this + 34),
    (char *)this + 120);
  if ( (*(unsigned __int8 (__fastcall **)(Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *))(*(_QWORD *)this + 40LL))(this) )
    Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(this);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
LABEL_34:
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v16)[2])(v16);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
}

```

## disassembly

```asm
0x18009d6c0  mov     [rsp-8+arg_10], rbx
0x18009d6c5  push    rbp
0x18009d6c6  push    rsi
0x18009d6c7  push    rdi
0x18009d6c8  lea     rbp, [rsp-360h]
0x18009d6d0  sub     rsp, 460h
0x18009d6d7  mov     rax, cs:__security_cookie
0x18009d6de  xor     rax, rsp
0x18009d6e1  mov     [rbp+370h+var_20], rax
0x18009d6e8  mov     rbx, rdx
0x18009d6eb  mov     rdi, rcx
0x18009d6ee  add     rcx, 8
0x18009d6f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009d6f7  lea     rcx, [rbp+370h+var_3E8]
0x18009d6fb  call    ?GetOrMakeShared@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VOEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(void)
0x18009d700  nop
0x18009d701  mov     [rsp+470h+var_418], 0
0x18009d70a  mov     rdx, rbx
0x18009d70d  lea     rcx, [rsp+470h+var_438]
0x18009d712  call    ?GetDisplayMonitorFromDeviceId@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$ComPtr@UIDisplayMonitor@Display@Devices@Windows@@@WRL@5@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(std::wstring const &)
0x18009d717  nop
0x18009d718  lea     rdx, [rsp+470h+var_418]
0x18009d71d  lea     rcx, [rsp+470h+var_438]
0x18009d722  call    ??$As@UIDisplayMonitorInternal@Internal@Display@Devices@Windows@@@?$ComPtr@UIDisplayMonitor@Display@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDisplayMonitorInternal@Internal@Display@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Display::IDisplayMonitor>::As<Windows::Devices::Display::Internal::IDisplayMonitorInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Display::Internal::IDisplayMonitorInternal>>)
0x18009d727  mov     rcx, [rbp+378h]; this
0x18009d72e  test    eax, eax
0x18009d730  js      loc_18009DAC5
0x18009d736  mov     [rsp+470h+var_420], 0
0x18009d73f  mov     rcx, [rsp+470h+var_438]
0x18009d744  lea     rsi, [rdi+60h]
0x18009d748  mov     rax, [rcx]
0x18009d74b  mov     rdx, rsi
0x18009d74e  mov     rax, [rax+60h]
0x18009d752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d757  mov     rcx, [rbp+378h]; this
0x18009d75e  test    eax, eax
0x18009d760  js      loc_18009DADA
0x18009d766  mov     rcx, [rsp+470h+var_438]
0x18009d76b  mov     rax, [rcx]
0x18009d76e  lea     rdx, [rsp+470h+var_420]
0x18009d773  mov     rax, [rax+58h]
0x18009d777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d77c  mov     rcx, [rbp+378h]; this
0x18009d783  test    eax, eax
0x18009d785  js      loc_18009DAEF
0x18009d78b  mov     eax, dword ptr [rsp+470h+var_420]
0x18009d78f  mov     [rdi+58h], eax
0x18009d792  mov     eax, dword ptr [rsp+470h+var_420+4]
0x18009d796  mov     [rdi+5Ch], eax
0x18009d799  mov     rcx, [rsp+470h+var_438]
0x18009d79e  lea     rbx, [rdi+64h]
0x18009d7a2  mov     rax, [rcx]
0x18009d7a5  mov     rdx, rbx
0x18009d7a8  mov     rax, [rax+40h]
0x18009d7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7b1  mov     rcx, [rbp+378h]; this
0x18009d7b8  test    eax, eax
0x18009d7ba  js      loc_18009DB04
0x18009d7c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SenBf2601@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SenBf2601@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601> `wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl(void)'::`2'::impl
0x18009d7c7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SenBf2601@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(void)
0x18009d7cc  test    al, al
0x18009d7ce  jz      short loc_18009D7D8
0x18009d7d0  mov     eax, [rbx]
0x18009d7d2  mov     [rdi+88h], eax
0x18009d7d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009d7df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009d7e4  test    al, al
0x18009d7e6  jnz     short loc_18009D7F8
0x18009d7e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange> `wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl(void)'::`2'::impl
0x18009d7ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(void)
0x18009d7f4  test    al, al
0x18009d7f6  jz      short loc_18009D84A
0x18009d7f8  xor     edx, edx; Val
0x18009d7fa  mov     r8d, 39Ch; Size
0x18009d800  lea     rcx, [rbp+370h+var_3BC]; void *
0x18009d804  call    memset_0
0x18009d809  mov     [rbp+370h+requestPacket.type], 0FFFFFFF9h
0x18009d810  mov     [rbp+370h+requestPacket.size], 3B0h
0x18009d817  mov     rax, [rdi+58h]
0x18009d81b  mov     qword ptr [rbp+370h+requestPacket.adapterId.LowPart], rax
0x18009d81f  mov     eax, [rsi]
0x18009d821  mov     [rbp+370h+requestPacket.id], eax
0x18009d824  lea     rcx, [rbp+370h+requestPacket]; requestPacket
0x18009d828  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18009d82e  mov     rcx, [rbp+378h]; this
0x18009d835  test    eax, eax
0x18009d837  jnz     loc_18009DB19
0x18009d83d  lea     rcx, [rdi+38h]
0x18009d841  lea     rdx, [rbp+370h+var_3BC]
0x18009d845  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18009d84a  mov     rcx, rdi; this
0x18009d84d  call    ?RefreshBrightnessCapabilities@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RefreshBrightnessCapabilities(void)
0x18009d852  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange> `wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl(void)'::`2'::impl
0x18009d859  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(void)
0x18009d85e  test    al, al
0x18009d860  jz      short loc_18009D86F
0x18009d862  mov     rcx, rdi; this
0x18009d865  call    ?RegisterForBrightnessCapabilityChanges@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(void)
0x18009d86a  jmp     loc_18009DA55
0x18009d86f  mov     [rsp+470h+var_430], 0
0x18009d877  mov     rcx, [rsp+470h+var_418]
0x18009d87c  mov     rax, [rcx]
0x18009d87f  lea     rdx, [rsp+470h+var_430]
0x18009d884  mov     rax, [rax+50h]
0x18009d888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d88d  mov     rcx, [rbp+378h]; this
0x18009d894  test    eax, eax
0x18009d896  js      loc_18009DB2E
0x18009d89c  mov     eax, [rbx]
0x18009d89e  mov     [rdi+88h], eax
0x18009d8a4  cmp     eax, 1
0x18009d8a7  jnz     short loc_18009D901
0x18009d8a9  cmp     [rsp+470h+var_430], eax
0x18009d8ad  jnz     short loc_18009D909
0x18009d8af  mov     dword ptr [rdi+88h], 0
0x18009d8b9  lea     rax, WPP_GLOBAL_Control
0x18009d8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d8c7  cmp     rcx, rax
0x18009d8ca  jz      loc_18009D99C
0x18009d8d0  test    dword ptr [rcx+1Ch], 100h
0x18009d8d7  jz      loc_18009D99C
0x18009d8dd  cmp     byte ptr [rcx+19h], 2
0x18009d8e1  jb      loc_18009D99C
0x18009d8e7  mov     edx, 0Ch
0x18009d8ec  lea     r8, WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids
0x18009d8f3  mov     rcx, [rcx+10h]
0x18009d8f7  call    WPP_SF_s
0x18009d8fc  jmp     loc_18009D99C
0x18009d901  test    eax, eax
0x18009d903  jz      loc_18009D99C
0x18009d909  mov     rcx, [rdi+78h]
0x18009d90d  mov     rax, [rcx]
0x18009d910  mov     rax, [rax+8]
0x18009d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d919  cmp     eax, 2
0x18009d91c  jnz     short loc_18009D99C
0x18009d91e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009d925  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009d92a  test    al, al
0x18009d92c  jnz     short loc_18009D99C
0x18009d92e  mov     byte ptr [rsp+470h+var_440], al
0x18009d932  mov     [rsp+470h+var_42C], 0
0x18009d93a  xorps   xmm0, xmm0
0x18009d93d  movdqu  [rsp+470h+var_400], xmm0
0x18009d943  mov     [rbp+370h+var_3F0], 0
0x18009d94b  mov     [rsp+470h+var_428], 0
0x18009d953  lea     rax, [rsp+470h+var_440]
0x18009d958  mov     qword ptr [rsp+470h+var_450], rax; unsigned int
0x18009d95d  lea     r9, [rsp+470h+var_42C]
0x18009d962  lea     r8, [rsp+470h+var_400]
0x18009d967  lea     rdx, [rsp+470h+var_428]
0x18009d96c  lea     rcx, [rsp+470h+var_410]
0x18009d971  call    ??$make_shared@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@W4BrightnessSupportType@2345@V?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@H_N@std@@YA?AV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@0@$$QEAW4BrightnessSupportType@Foundation@DisplayEnhancement@Windows@Microsoft@@$$QEAV?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@0@$$QEAH$$QEA_N@Z; std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper,Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>,int,bool>(Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType &&,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &&,int &&,bool &&)
0x18009d976  mov     rdx, rax
0x18009d979  lea     rcx, [rdi+78h]
0x18009d97d  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18009d982  mov     rcx, [rsp+470h+var_408]; this
0x18009d987  test    rcx, rcx
0x18009d98a  jz      short loc_18009D992
0x18009d98c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009d991  nop
0x18009d992  lea     rcx, [rsp+470h+var_400]
0x18009d997  call    ?_Tidy@?$vector@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(void)
0x18009d99c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009d9a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009d9a8  test    al, al
0x18009d9aa  jz      short loc_18009D9B2
0x18009d9ac  lea     rbx, [rdi+38h]
0x18009d9b0  jmp     short loc_18009DA07
0x18009d9b2  xor     edx, edx; Val
0x18009d9b4  mov     r8d, 39Ch; Size
0x18009d9ba  lea     rcx, [rbp+370h+var_3BC]; void *
0x18009d9be  call    memset_0
0x18009d9c3  mov     [rbp+370h+requestPacket.type], 0FFFFFFF9h
0x18009d9ca  mov     [rbp+370h+requestPacket.size], 3B0h
0x18009d9d1  mov     rax, [rdi+58h]
0x18009d9d5  mov     qword ptr [rbp+370h+requestPacket.adapterId.LowPart], rax
0x18009d9d9  mov     eax, [rsi]
0x18009d9db  mov     [rbp+370h+requestPacket.id], eax
0x18009d9de  lea     rcx, [rbp+370h+requestPacket]; requestPacket
0x18009d9e2  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18009d9e8  mov     rcx, [rbp+378h]; this
0x18009d9ef  test    eax, eax
0x18009d9f1  jnz     loc_18009DAB0
0x18009d9f7  lea     rbx, [rdi+38h]
0x18009d9fb  lea     rdx, [rbp+370h+var_3BC]
0x18009d9ff  mov     rcx, rbx
0x18009da02  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18009da07  mov     rdx, rbx
0x18009da0a  lea     rcx, [rsp+470h+var_410]
0x18009da0f  call    ?GetOrMakeShared@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(std::wstring const &)
0x18009da14  nop
0x18009da15  lea     r8, [rdi+78h]
0x18009da19  mov     edx, [rdi+88h]
0x18009da1f  mov     rcx, [rsp+470h+var_410]
0x18009da24  call    ?LogDisplayCapabilityEvent@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@QEAAXW4DisplayMonitorConnectionKind@Display@Devices@4@AEBV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::LogDisplayCapabilityEvent(Windows::Devices::Display::DisplayMonitorConnectionKind,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper> const &)
0x18009da29  mov     rax, [rdi]
0x18009da2c  mov     rcx, rdi
0x18009da2f  mov     rax, [rax+28h]
0x18009da33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da38  test    al, al
0x18009da3a  jz      short loc_18009DA45
0x18009da3c  mov     rcx, rdi; this
0x18009da3f  call    ?RegisterForBrightnessCapabilityChanges@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RegisterForBrightnessCapabilityChanges(void)
0x18009da44  nop
0x18009da45  mov     rcx, [rsp+470h+var_408]; this
0x18009da4a  test    rcx, rcx
0x18009da4d  jz      short loc_18009DA55
0x18009da4f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009da54  nop
0x18009da55  mov     rcx, [rsp+470h+var_438]
0x18009da5a  test    rcx, rcx
0x18009da5d  jz      short loc_18009DA75
0x18009da5f  mov     [rsp+470h+var_438], 0
0x18009da68  mov     rax, [rcx]
0x18009da6b  mov     rax, [rax+10h]
0x18009da6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da74  nop
0x18009da75  lea     rcx, [rsp+470h+var_418]
0x18009da7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009da7f  nop
0x18009da80  mov     rcx, [rbp+370h+var_3E0]; this
0x18009da84  test    rcx, rcx
0x18009da87  jz      short loc_18009DA8E
0x18009da89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009da8e  mov     rcx, [rbp+370h+var_20]
0x18009da95  xor     rcx, rsp; StackCookie
0x18009da98  call    __security_check_cookie
0x18009da9d  mov     rbx, [rsp+470h+arg_10]
0x18009daa5  add     rsp, 460h
0x18009daac  pop     rdi
0x18009daad  pop     rsi
0x18009daae  pop     rbp
0x18009daaf  retn
0x18009dab0  mov     r9d, eax; char *
0x18009dab3  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009daba  mov     edx, 0BDh; void *
0x18009dabf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009dac5  mov     r9d, eax; char *
0x18009dac8  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009dacf  mov     edx, 75h ; 'u'; void *
0x18009dad4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009dada  mov     r9d, eax; char *
0x18009dadd  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009dae4  mov     edx, 79h ; 'y'; void *
0x18009dae9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009daef  mov     r9d, eax; char *
0x18009daf2  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009daf9  mov     edx, 7Ah ; 'z'; void *
0x18009dafe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009db04  mov     r9d, eax; char *
0x18009db07  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009db0e  mov     edx, 7Dh ; '}'; void *
0x18009db13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009db19  mov     r9d, eax; char *
0x18009db1c  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009db23  mov     edx, 8Ch; void *
0x18009db28  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009db2e  mov     r9d, eax; char *
0x18009db31  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009db38  mov     edx, 99h; void *
0x18009db3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
