# Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::DeRequestCoordinatorImpl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::Windows::DisplayEnhancement::Foundation::MonitorAdapterTargetId,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::WnfAdapter> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Transition::DeTransition> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Transition::DeTransition> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup> const &)

- ea: `0x1800c154c`
- end: `0x1800c1844`
- name: `??0DeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMonitorAdapterTargetId@Foundation@234@AEBV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@6@AEBV?$shared_ptr@VPowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@6@AEBV?$shared_ptr@VWnfAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@6@AEBV?$shared_ptr@VDeTransition@Transition@DisplayEnhancement@Windows@Microsoft@@@6@5AEBV?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@6@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bf740`

## callees

- `0x180008ae8`
- `0x180011704`
- `0x180011f7c`
- `0x180011fe8`
- `0x180013138`
- `0x18001c3ac`
- `0x18001edfc`
- `0x180031254`
- `0x18009830c`
- `0x1800c154c`
- `0x1800c2ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c1683`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c1683`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x1800c161e`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x1800c161e`

## string_xrefs

- `0x1800c181d`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\derequestcoordinator.cpp`
- `0x1800c1832`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\derequestcoordinator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::DeRequestCoordinatorImpl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct SmFx::StateMachineEngine::StateMachineEngineImpl **v12; // rsi
  __int64 v13; // rax
  _QWORD *v14; // rax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v16; // eax
  int v18; // [rsp+20h] [rbp-58h]
  _QWORD v19[6]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v20; // [rsp+60h] [rbp-18h]
  int v21; // [rsp+62h] [rbp-16h]
  __int16 v22; // [rsp+66h] [rbp-12h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v12 = (struct SmFx::StateMachineEngine::StateMachineEngineImpl **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)a1 = &Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::`vftable';
  std::wstring::wstring(a1 + 32, a2);
  *(_QWORD *)(a1 + 64) = *(_QWORD *)a3;
  *(_DWORD *)(a1 + 72) = *(_DWORD *)(a3 + 8);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 80,
    a5);
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  v13 = a6[1];
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  *(_QWORD *)(a1 + 96) = *a6;
  *(_QWORD *)(a1 + 104) = a6[1];
  *(_QWORD *)(a1 + 112) = 0;
  std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>(a1 + 120);
  std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>(a1 + 136);
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
  *v14 = v14;
  v14[1] = v14;
  *(_QWORD *)(a1 + 160) = v14;
  *(_DWORD *)(a1 + 176) = RtlAllocateWnfSerializationGroup();
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 272), 0, 0);
  *(_BYTE *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 316) = 0;
  Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(a1 + 328);
  Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(a1 + 432);
  *(_QWORD *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 552) = 0;
  *(_DWORD *)(a1 + 544) = 0;
  *(_BYTE *)(a1 + 548) = 1;
  *(_WORD *)(a1 + 549) = 0;
  *(_BYTE *)(a1 + 551) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  *(_DWORD *)(a1 + 560) = 0;
  *(_BYTE *)(a1 + 564) = 1;
  *(_WORD *)(a1 + 565) = 0;
  *(_BYTE *)(a1 + 567) = 0;
  Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateUnsupportedCausation(a1 + 576);
  *(_BYTE *)(a1 + 600) = 1;
  *(_QWORD *)(a1 + 608) = 0;
  *(_QWORD *)(a1 + 616) = 0;
  *(_DWORD *)(a1 + 624) = 0;
  *(_BYTE *)(a1 + 628) = 0;
  *(_QWORD *)(a1 + 632) = 0;
  *(_QWORD *)(a1 + 640) = 0;
  *(_DWORD *)(a1 + 648) = 0;
  *(_BYTE *)(a1 + 652) = 0;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 656,
    a4);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 672,
    a7);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 688,
    a8);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    a1 + 704,
    a9);
  *(_QWORD *)(a1 + 720) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 720, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\derequestcoordinator.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
  v21 = 0;
  v22 = 0;
  v19[0] = &Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::c_specification;
  v19[1] = v12;
  v20 = 257;
  v19[2] = Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogMachineExceptionThunk;
  v19[3] = Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogEventEnqueueThunk;
  v19[4] = Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogTransitionThunk;
  v19[5] = Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtMachineDestroyedThunk;
  v16 = SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(
          (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v19,
          v12);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\derequestcoordinator.cpp",
      (const char *)(unsigned int)v16,
      v18);
  return a1;
}

```

## disassembly

```asm
0x1800c154c  mov     [rsp-30h+arg_0], rcx
0x1800c1551  push    rbp
0x1800c1552  push    rbx
0x1800c1553  push    rsi
0x1800c1554  push    rdi
0x1800c1555  push    r14
0x1800c1557  push    r15
0x1800c1559  mov     rbp, rsp
0x1800c155c  sub     rsp, 78h
0x1800c1560  mov     r14, r9
0x1800c1563  mov     rbx, r8
0x1800c1566  mov     rdi, rcx
0x1800c1569  lea     rsi, [rcx+8]
0x1800c156d  xor     r15d, r15d
0x1800c1570  mov     [rsi], r15
0x1800c1573  mov     [rcx+10h], r15
0x1800c1577  mov     [rcx+18h], r15
0x1800c157b  lea     rax, ??_7DeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::`vftable'
0x1800c1582  mov     [rcx], rax
0x1800c1585  add     rcx, 20h ; ' '
0x1800c1589  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c158e  nop
0x1800c158f  movsd   xmm0, qword ptr [rbx]
0x1800c1593  movsd   qword ptr [rdi+40h], xmm0
0x1800c1598  mov     eax, [rbx+8]
0x1800c159b  mov     [rdi+48h], eax
0x1800c159e  lea     rcx, [rdi+50h]
0x1800c15a2  mov     rdx, [rbp+arg_20]
0x1800c15a6  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c15ab  nop
0x1800c15ac  mov     [rdi+60h], r15
0x1800c15b0  mov     [rdi+68h], r15
0x1800c15b4  mov     rcx, [rbp+arg_28]
0x1800c15b8  mov     rax, [rcx+8]
0x1800c15bc  test    rax, rax
0x1800c15bf  jz      short loc_1800C15C5
0x1800c15c1  lock inc dword ptr [rax+8]
0x1800c15c5  mov     rax, [rcx]
0x1800c15c8  mov     [rdi+60h], rax
0x1800c15cc  mov     rax, [rcx+8]
0x1800c15d0  mov     [rdi+68h], rax
0x1800c15d4  xor     eax, eax
0x1800c15d6  mov     [rdi+70h], rax
0x1800c15da  lea     rcx, [rdi+78h]
0x1800c15de  call    ??0?$list@V?$shared_ptr@V?$TokenWithStatusServer@UBrightnessUpdate@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@V?$allocator@V?$shared_ptr@V?$TokenWithStatusServer@UBrightnessUpdate@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>(void)
0x1800c15e3  nop
0x1800c15e4  lea     rcx, [rdi+88h]
0x1800c15eb  call    ??0?$list@V?$shared_ptr@V?$TokenWithStatusServer@UBrightnessUpdate@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@V?$allocator@V?$shared_ptr@V?$TokenWithStatusServer@UBrightnessUpdate@BrightnessManagers@DisplayEnhancement@Windows@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::TokenWithStatusServer<Microsoft::Windows::DisplayEnhancement::BrightnessManagers::BrightnessUpdate>>>(void)
0x1800c15f0  nop
0x1800c15f1  xor     eax, eax
0x1800c15f3  mov     [rdi+98h], rax
0x1800c15fa  mov     [rdi+0A0h], r15
0x1800c1601  mov     [rdi+0A8h], r15
0x1800c1608  lea     ecx, [rax+20h]
0x1800c160b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800c1610  mov     [rax], rax
0x1800c1613  mov     [rax+8], rax
0x1800c1617  mov     [rdi+0A0h], rax
0x1800c161e  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x1800c1624  mov     [rdi+0B0h], eax
0x1800c162a  mov     [rdi+0B8h], r15
0x1800c1631  mov     [rdi+0C0h], r15
0x1800c1638  mov     [rdi+0C8h], r15
0x1800c163f  mov     [rdi+0D0h], r15
0x1800c1646  mov     [rdi+0D8h], r15
0x1800c164d  mov     [rdi+0E0h], r15
0x1800c1654  mov     [rdi+0E8h], r15
0x1800c165b  mov     [rdi+0F0h], r15
0x1800c1662  mov     [rdi+0F8h], r15
0x1800c1669  mov     [rdi+100h], r15
0x1800c1670  mov     [rdi+108h], r15
0x1800c1677  lea     rcx, [rdi+110h]; lpCriticalSection
0x1800c167e  xor     r8d, r8d; Flags
0x1800c1681  xor     edx, edx; dwSpinCount
0x1800c1683  call    cs:__imp_InitializeCriticalSectionEx
0x1800c1689  nop
0x1800c168a  mov     [rdi+138h], r15b
0x1800c1691  mov     [rdi+13Ch], r15
0x1800c1698  lea     rcx, [rdi+148h]
0x1800c169f  call    ?CreateEmptyColorConfig@ColorConfiguration@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(void)
0x1800c16a4  nop
0x1800c16a5  lea     rcx, [rdi+1B0h]
0x1800c16ac  call    ?CreateEmptyColorConfig@ColorConfiguration@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::ColorConfiguration::CreateEmptyColorConfig(void)
0x1800c16b1  nop
0x1800c16b2  mov     [rdi+218h], r15
0x1800c16b9  xor     eax, eax
0x1800c16bb  mov     [rdi+228h], rax
0x1800c16c2  mov     [rdi+220h], eax
0x1800c16c8  mov     byte ptr [rdi+224h], 1
0x1800c16cf  mov     [rdi+225h], ax
0x1800c16d6  mov     [rdi+227h], al
0x1800c16dc  mov     [rdi+238h], rax
0x1800c16e3  mov     [rdi+230h], eax
0x1800c16e9  mov     byte ptr [rdi+234h], 1
0x1800c16f0  mov     [rdi+235h], ax
0x1800c16f7  mov     [rdi+237h], al
0x1800c16fd  lea     rcx, [rdi+240h]
0x1800c1704  call    ?CreateUnsupportedCausation@BrightnessCausation@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AU12345@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCausation::CreateUnsupportedCausation(void)
0x1800c1709  nop
0x1800c170a  mov     byte ptr [rdi+258h], 1
0x1800c1711  mov     [rdi+260h], r15
0x1800c1718  mov     [rdi+268h], r15
0x1800c171f  mov     [rdi+270h], r15d
0x1800c1726  mov     [rdi+274h], r15b
0x1800c172d  mov     [rdi+278h], r15
0x1800c1734  mov     [rdi+280h], r15
0x1800c173b  mov     [rdi+288h], r15d
0x1800c1742  mov     [rdi+28Ch], r15b
0x1800c1749  lea     rcx, [rdi+290h]
0x1800c1750  mov     rdx, r14
0x1800c1753  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c1758  nop
0x1800c1759  lea     rcx, [rdi+2A0h]
0x1800c1760  mov     rdx, [rbp+arg_30]
0x1800c1764  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c1769  nop
0x1800c176a  lea     rcx, [rdi+2B0h]
0x1800c1771  mov     rdx, [rbp+arg_38]
0x1800c1775  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c177a  nop
0x1800c177b  lea     rcx, [rdi+2C0h]
0x1800c1782  mov     rdx, [rbp+arg_40]
0x1800c1786  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800c178b  nop
0x1800c178c  lea     rcx, [rdi+2D0h]
0x1800c1793  mov     [rcx], r15
0x1800c1796  mov     edx, 1
0x1800c179b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800c17a0  mov     rcx, [rbp+30h]; this
0x1800c17a4  test    eax, eax
0x1800c17a6  js      loc_1800C182F
0x1800c17ac  mov     [rbp+var_16], r15d
0x1800c17b0  mov     [rbp+var_12], r15w
0x1800c17b5  lea     rax, ?c_specification@?$DeRequestCoordinatorStateMachine@VDeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Coordinator@DisplayEnhancement@Windows@Microsoft@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::c_specification
0x1800c17bc  mov     [rbp+var_48], rax
0x1800c17c0  mov     [rbp+var_40], rsi
0x1800c17c4  mov     [rbp+var_18], 101h
0x1800c17ca  lea     rax, ?EvtLogMachineExceptionThunk@?$DeRequestCoordinatorStateMachine@VDeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Coordinator@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4MachineException@SmFx@@GG@Z; Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogMachineExceptionThunk(void *,SmFx::MachineException,ushort,ushort)
0x1800c17d1  mov     [rbp+var_38], rax
0x1800c17d5  lea     rax, ?EvtLogEventEnqueueThunk@?$DeRequestCoordinatorStateMachine@VDeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Coordinator@DisplayEnhancement@Windows@Microsoft@@CAXPEAXG@Z; Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogEventEnqueueThunk(void *,ushort)
0x1800c17dc  mov     [rbp+var_30], rax
0x1800c17e0  lea     rax, ?EvtLogTransitionThunk@?$DeRequestCoordinatorStateMachine@VDeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Coordinator@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4TransitionType@SmFx@@GGG@Z; Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtLogTransitionThunk(void *,SmFx::TransitionType,ushort,ushort,ushort)
0x1800c17e7  mov     [rbp+var_28], rax
0x1800c17eb  lea     rax, ?EvtMachineDestroyedThunk@?$DeRequestCoordinatorStateMachine@VDeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@Coordinator@DisplayEnhancement@Windows@Microsoft@@CAXPEAX@Z; Microsoft::Windows::DisplayEnhancement::Coordinator::GeneratedStateMachines::DeRequestCoordinatorStateMachine<Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl>::EvtMachineDestroyedThunk(void *)
0x1800c17f2  mov     [rbp+var_20], rax
0x1800c17f6  mov     rdx, rsi; struct SmFx::StateMachineEngine::StateMachineEngineImpl **
0x1800c17f9  lea     rcx, [rbp+var_48]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x1800c17fd  call    ?MakeAndInitialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@SAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@PEAPEAV123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &,SmFx::StateMachineEngine::StateMachineEngineImpl * *)
0x1800c1802  mov     rcx, [rbp+30h]; this
0x1800c1806  test    eax, eax
0x1800c1808  js      short loc_1800C181A
0x1800c180a  mov     rax, rdi
0x1800c180d  add     rsp, 78h
0x1800c1811  pop     r15
0x1800c1813  pop     r14
0x1800c1815  pop     rdi
0x1800c1816  pop     rsi
0x1800c1817  pop     rbx
0x1800c1818  pop     rbp
0x1800c1819  retn
0x1800c181a  mov     r9d, eax; char *
0x1800c181d  lea     r8, aOnecoreuapDriv_5; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c1824  mov     edx, 89h; void *
0x1800c1829  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800c182f  mov     r9d, eax; char *
0x1800c1832  lea     r8, aOnecoreuapDriv_5; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c1839  mov     edx, 87h; void *
0x1800c183e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
