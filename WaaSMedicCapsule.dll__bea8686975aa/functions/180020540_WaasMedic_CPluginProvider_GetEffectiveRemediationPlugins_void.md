# WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(void)

- ea: `0x180020540`
- end: `0x18002086a`
- name: `?GetEffectiveRemediationPlugins@CPluginProvider@WaasMedic@@SA?AV?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@XZ`
- size: `810`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f140`
- `0x180020870`

## callees

- `0x180003bb0`
- `0x180003bd4`
- `0x180005ef1`
- `0x18001d780`
- `0x18001eed0`
- `0x180020540`
- `0x180020c08`
- `0x180020ca8`
- `0x180020d48`
- `0x180020ea8`

## string_xrefs

- `0x180020685`: `AutoInPlaceUpgradeInboxPlugin`
- `0x180020719`: `CanvasPlugin`
- `0x180020768`: `DiskCleanupPlugin`
- `0x1800207b7`: `InPlaceUpgradeMcpPlugin`
- `0x180020806`: `RebootNeededPlugin`
- `0x180020575`: `ServiceHealthPlugin`
- `0x18002058d`: `ScheduledTasksPlugin`
- `0x1800205a5`: `NoUsoScanPlugin`
- `0x1800205bd`: `BinaryHealthPlugin`
- `0x1800205d5`: `ServicingCleanupPlugin`
- `0x1800205eb`: `DynamicProtectionPlugin`
- `0x180020601`: `TimeSyncPlugin`
- `0x180020617`: `StackDataResetPlugin`
- `0x18002062d`: `AutomaticCorruptionRepairPlugin`
- `0x180020643`: `ManualCorruptionRepairPlugin`
- `0x180020659`: `InPlaceUpgradePlugin`
- `0x18002066f`: `EdgeUpdateRepairPlugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(_QWORD *a1)
{
  char *v2; // rbx
  _OWORD *v3; // rdx
  _OWORD *v4; // rdx
  _OWORD *v5; // rdx
  _OWORD *v6; // rdx
  __int128 v8; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+30h] [rbp-D0h]
  _QWORD *v10; // [rsp+38h] [rbp-C8h]
  _QWORD Src[26]; // [rsp+40h] [rbp-C0h] BYREF

  v10 = a1;
  v9 = 0;
  Src[0] = L"ServiceHealthPlugin";
  Src[1] = WaasMedic::CServiceHealthPlugin::CreateInstance;
  Src[2] = L"ScheduledTasksPlugin";
  Src[3] = WaasMedic::CScheduledTasksPlugin::CreateInstance;
  Src[4] = L"NoUsoScanPlugin";
  Src[5] = WaasMedic::CNoUsoScanPlugin::CreateInstance;
  Src[6] = L"BinaryHealthPlugin";
  Src[7] = WaasMedic::CBinaryHealthPlugin::CreateInstance;
  Src[8] = L"ServicingCleanupPlugin";
  Src[9] = WaasMedic::CServicingCleanupPlugin::CreateInstance;
  Src[10] = L"DynamicProtectionPlugin";
  Src[11] = WaasMedic::CDynamicProtectionPlugin::CreateInstance;
  Src[12] = L"TimeSyncPlugin";
  Src[13] = WaasMedic::CTimeSyncPlugin::CreateInstance;
  Src[14] = L"StackDataResetPlugin";
  Src[15] = WaasMedic::CStackDataResetPlugin::CreateInstance;
  Src[16] = L"AutomaticCorruptionRepairPlugin";
  Src[17] = WaasMedic::AutomaticCorruptionRepairPlugin::CreateInstance;
  Src[18] = L"ManualCorruptionRepairPlugin";
  Src[19] = WaasMedic::ManualCorruptionRepairPlugin::CreateInstance;
  Src[20] = L"InPlaceUpgradePlugin";
  Src[21] = WaasMedic::CInPlaceUpgrade::CreateInstance;
  Src[22] = L"EdgeUpdateRepairPlugin";
  Src[23] = WaasMedic::EdgeUpdateRepairPlugin::CreateInstance;
  Src[24] = L"AutoInPlaceUpgradeInboxPlugin";
  Src[25] = WaasMedic::CAutoInPlaceUpgradeInbox::CreateInstance;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v2 = (char *)operator new(0xD0u);
  *a1 = v2;
  a1[1] = v2;
  a1[2] = v2 + 208;
  memmove_0(v2, Src, 0xD0u);
  a1[1] = v2 + 208;
  *(_QWORD *)&v8 = 0;
  std::_Tidy_guard<std::vector<WaasMedic::tagPluginRegistrationInfo>>::~_Tidy_guard<std::vector<WaasMedic::tagPluginRegistrationInfo>>(&v8);
  v9 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPlugin_52564597>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CanvasPlugin_52564597>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v8 = L"CanvasPlugin";
    *((_QWORD *)&v8 + 1) = WaasMedic::CanvasPlugin::CreateInstance;
    v3 = (_OWORD *)a1[1];
    if ( v3 == (_OWORD *)a1[2] )
    {
      std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(
        a1,
        v3,
        &v8);
    }
    else
    {
      *v3 = v8;
      a1[1] += 16LL;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DiskCleanupMCPPlugin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DiskCleanupMCPPlugin>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v8 = L"DiskCleanupPlugin";
    *((_QWORD *)&v8 + 1) = WaasMedic::CDiskCleanupPlugin::CreateInstance;
    v4 = (_OWORD *)a1[1];
    if ( v4 == (_OWORD *)a1[2] )
    {
      std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(
        a1,
        v4,
        &v8);
    }
    else
    {
      *v4 = v8;
      a1[1] += 16LL;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPUMCPPlugin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPUMCPPlugin>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v8 = L"InPlaceUpgradeMcpPlugin";
    *((_QWORD *)&v8 + 1) = WaasMedic::InPlaceUpgradeMcpPlugin::CreateInstance;
    v5 = (_OWORD *)a1[1];
    if ( v5 == (_OWORD *)a1[2] )
    {
      std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(
        a1,
        v5,
        &v8);
    }
    else
    {
      *v5 = v8;
      a1[1] += 16LL;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RebootNeededPlugin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RebootNeededPlugin>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v8 = L"RebootNeededPlugin";
    *((_QWORD *)&v8 + 1) = WaasMedic::CRebootNeededPlugin::CreateInstance;
    v6 = (_OWORD *)a1[1];
    if ( v6 == (_OWORD *)a1[2] )
    {
      std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(
        a1,
        v6,
        &v8);
    }
    else
    {
      *v6 = v8;
      a1[1] += 16LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180020540  mov     [rsp-8+arg_8], rbx
0x180020545  mov     [rsp-8+arg_10], rdi
0x18002054a  push    rbp
0x18002054b  lea     rbp, [rsp-20h]
0x180020550  sub     rsp, 120h
0x180020557  mov     rax, cs:__security_cookie
0x18002055e  xor     rax, rsp
0x180020561  mov     [rbp+20h+var_10], rax
0x180020565  mov     rdi, rcx
0x180020568  mov     [rsp+120h+var_E8], rcx
0x18002056d  mov     [rsp+120h+var_F0], 0
0x180020575  lea     rax, aServicehealthp_1; "ServiceHealthPlugin"
0x18002057c  mov     [rsp+120h+Src], rax
0x180020581  lea     rax, ?CreateInstance@CServiceHealthPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CServiceHealthPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020588  mov     [rsp+120h+var_D8], rax
0x18002058d  lea     rax, aScheduledtasks; "ScheduledTasksPlugin"
0x180020594  mov     [rsp+120h+var_D0], rax
0x180020599  lea     rax, ?CreateInstance@CScheduledTasksPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CScheduledTasksPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800205a0  mov     [rsp+120h+var_C8], rax
0x1800205a5  lea     rax, aNousoscanplugi; "NoUsoScanPlugin"
0x1800205ac  mov     [rsp+120h+var_C0], rax
0x1800205b1  lea     rax, ?CreateInstance@CNoUsoScanPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CNoUsoScanPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800205b8  mov     [rsp+120h+var_B8], rax
0x1800205bd  lea     rax, aBinaryhealthpl_0; "BinaryHealthPlugin"
0x1800205c4  mov     [rsp+120h+var_B0], rax
0x1800205c9  lea     rax, ?CreateInstance@CBinaryHealthPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CBinaryHealthPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800205d0  mov     [rsp+120h+var_A8], rax
0x1800205d5  lea     rax, aServicingclean; "ServicingCleanupPlugin"
0x1800205dc  mov     [rbp+20h+var_A0], rax
0x1800205e0  lea     rax, ?CreateInstance@CServicingCleanupPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CServicingCleanupPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800205e7  mov     [rbp+20h+var_98], rax
0x1800205eb  lea     rax, aDynamicprotect; "DynamicProtectionPlugin"
0x1800205f2  mov     [rbp+20h+var_90], rax
0x1800205f6  lea     rax, ?CreateInstance@CDynamicProtectionPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CDynamicProtectionPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800205fd  mov     [rbp+20h+var_88], rax
0x180020601  lea     rax, aTimesyncplugin; "TimeSyncPlugin"
0x180020608  mov     [rbp+20h+var_80], rax
0x18002060c  lea     rax, ?CreateInstance@CTimeSyncPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CTimeSyncPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020613  mov     [rbp+20h+var_78], rax
0x180020617  lea     rax, aStackdatareset; "StackDataResetPlugin"
0x18002061e  mov     [rbp+20h+var_70], rax
0x180020622  lea     rax, ?CreateInstance@CStackDataResetPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CStackDataResetPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020629  mov     [rbp+20h+var_68], rax
0x18002062d  lea     rax, aAutomaticcorru; "AutomaticCorruptionRepairPlugin"
0x180020634  mov     [rbp+20h+var_60], rax
0x180020638  lea     rax, ?CreateInstance@AutomaticCorruptionRepairPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::AutomaticCorruptionRepairPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x18002063f  mov     [rbp+20h+var_58], rax
0x180020643  lea     rax, aManualcorrupti; "ManualCorruptionRepairPlugin"
0x18002064a  mov     [rbp+20h+var_50], rax
0x18002064e  lea     rax, ?CreateInstance@ManualCorruptionRepairPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::ManualCorruptionRepairPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020655  mov     [rbp+20h+var_48], rax
0x180020659  lea     rax, aInplaceupgrade_4; "InPlaceUpgradePlugin"
0x180020660  mov     [rbp+20h+var_40], rax
0x180020664  lea     rax, ?CreateInstance@CInPlaceUpgrade@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CInPlaceUpgrade::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x18002066b  mov     [rbp+20h+var_38], rax
0x18002066f  lea     rax, aEdgeupdaterepa_2; "EdgeUpdateRepairPlugin"
0x180020676  mov     [rbp+20h+var_30], rax
0x18002067a  lea     rax, ?CreateInstance@EdgeUpdateRepairPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::EdgeUpdateRepairPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020681  mov     [rbp+20h+var_28], rax
0x180020685  lea     rax, aAutoinplaceupg; "AutoInPlaceUpgradeInboxPlugin"
0x18002068c  mov     [rbp+20h+var_20], rax
0x180020690  lea     rax, ?CreateInstance@CAutoInPlaceUpgradeInbox@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CAutoInPlaceUpgradeInbox::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020697  mov     [rbp+20h+var_18], rax
0x18002069b  mov     qword ptr [rcx], 0
0x1800206a2  mov     qword ptr [rcx+8], 0
0x1800206aa  mov     qword ptr [rcx+10h], 0
0x1800206b2  mov     ecx, 0D0h; Size
0x1800206b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800206bc  mov     rbx, rax
0x1800206bf  mov     [rdi], rax
0x1800206c2  mov     [rdi+8], rax
0x1800206c6  add     rax, 0D0h
0x1800206cc  mov     [rdi+10h], rax
0x1800206d0  mov     r8d, 0D0h; Size
0x1800206d6  lea     rdx, [rsp+120h+Src]; Src
0x1800206db  mov     rcx, rbx; void *
0x1800206de  call    memmove_0
0x1800206e3  lea     rax, [rbx+0D0h]
0x1800206ea  mov     [rdi+8], rax
0x1800206ee  mov     qword ptr [rsp+120h+var_100], 0
0x1800206f7  lea     rcx, [rsp+120h+var_100]
0x1800206fc  call    ??1?$_Tidy_guard@V?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<WaasMedic::tagPluginRegistrationInfo>>::~_Tidy_guard<std::vector<WaasMedic::tagPluginRegistrationInfo>>(void)
0x180020701  mov     [rsp+120h+var_F0], 1
0x180020709  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CanvasPlugin_52564597@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPlugin_52564597@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPlugin_52564597> `wil::Feature<__WilFeatureTraits_Feature_CanvasPlugin_52564597>::GetImpl(void)'::`2'::impl
0x180020710  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPlugin_52564597@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPlugin_52564597>::__private_IsEnabled(void)
0x180020715  test    al, al
0x180020717  jz      short loc_180020758
0x180020719  lea     rax, aCanvasplugin; "CanvasPlugin"
0x180020720  mov     qword ptr [rsp+120h+var_100], rax
0x180020725  lea     rax, ?CreateInstance@CanvasPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CanvasPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x18002072c  mov     qword ptr [rsp+120h+var_100+8], rax
0x180020731  mov     rdx, [rdi+8]
0x180020735  cmp     rdx, [rdi+10h]
0x180020739  jz      short loc_18002074B
0x18002073b  movups  xmm0, [rsp+120h+var_100]
0x180020740  movdqu  xmmword ptr [rdx], xmm0
0x180020744  add     qword ptr [rdi+8], 10h
0x180020749  jmp     short loc_180020758
0x18002074b  lea     r8, [rsp+120h+var_100]
0x180020750  mov     rcx, rdi
0x180020753  call    ??$_Emplace_reallocate@UtagPluginRegistrationInfo@WaasMedic@@@?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@AEAAPEAUtagPluginRegistrationInfo@WaasMedic@@QEAU23@$$QEAU23@@Z; std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(WaasMedic::tagPluginRegistrationInfo * const,WaasMedic::tagPluginRegistrationInfo &&)
0x180020758  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DiskCleanupMCPPlugin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DiskCleanupMCPPlugin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DiskCleanupMCPPlugin> `wil::Feature<__WilFeatureTraits_Feature_DiskCleanupMCPPlugin>::GetImpl(void)'::`2'::impl
0x18002075f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DiskCleanupMCPPlugin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DiskCleanupMCPPlugin>::__private_IsEnabled(void)
0x180020764  test    al, al
0x180020766  jz      short loc_1800207A7
0x180020768  lea     rax, aDiskcleanupplu; "DiskCleanupPlugin"
0x18002076f  mov     qword ptr [rsp+120h+var_100], rax
0x180020774  lea     rax, ?CreateInstance@CDiskCleanupPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CDiskCleanupPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x18002077b  mov     qword ptr [rsp+120h+var_100+8], rax
0x180020780  mov     rdx, [rdi+8]
0x180020784  cmp     rdx, [rdi+10h]
0x180020788  jz      short loc_18002079A
0x18002078a  movups  xmm0, [rsp+120h+var_100]
0x18002078f  movdqu  xmmword ptr [rdx], xmm0
0x180020793  add     qword ptr [rdi+8], 10h
0x180020798  jmp     short loc_1800207A7
0x18002079a  lea     r8, [rsp+120h+var_100]
0x18002079f  mov     rcx, rdi
0x1800207a2  call    ??$_Emplace_reallocate@UtagPluginRegistrationInfo@WaasMedic@@@?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@AEAAPEAUtagPluginRegistrationInfo@WaasMedic@@QEAU23@$$QEAU23@@Z; std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(WaasMedic::tagPluginRegistrationInfo * const,WaasMedic::tagPluginRegistrationInfo &&)
0x1800207a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPUMCPPlugin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPUMCPPlugin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPUMCPPlugin> `wil::Feature<__WilFeatureTraits_Feature_IPUMCPPlugin>::GetImpl(void)'::`2'::impl
0x1800207ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPUMCPPlugin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPUMCPPlugin>::__private_IsEnabled(void)
0x1800207b3  test    al, al
0x1800207b5  jz      short loc_1800207F6
0x1800207b7  lea     rax, aInplaceupgrade; "InPlaceUpgradeMcpPlugin"
0x1800207be  mov     qword ptr [rsp+120h+var_100], rax
0x1800207c3  lea     rax, ?CreateInstance@InPlaceUpgradeMcpPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::InPlaceUpgradeMcpPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x1800207ca  mov     qword ptr [rsp+120h+var_100+8], rax
0x1800207cf  mov     rdx, [rdi+8]
0x1800207d3  cmp     rdx, [rdi+10h]
0x1800207d7  jz      short loc_1800207E9
0x1800207d9  movups  xmm0, [rsp+120h+var_100]
0x1800207de  movdqu  xmmword ptr [rdx], xmm0
0x1800207e2  add     qword ptr [rdi+8], 10h
0x1800207e7  jmp     short loc_1800207F6
0x1800207e9  lea     r8, [rsp+120h+var_100]
0x1800207ee  mov     rcx, rdi
0x1800207f1  call    ??$_Emplace_reallocate@UtagPluginRegistrationInfo@WaasMedic@@@?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@AEAAPEAUtagPluginRegistrationInfo@WaasMedic@@QEAU23@$$QEAU23@@Z; std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(WaasMedic::tagPluginRegistrationInfo * const,WaasMedic::tagPluginRegistrationInfo &&)
0x1800207f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RebootNeededPlugin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RebootNeededPlugin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RebootNeededPlugin> `wil::Feature<__WilFeatureTraits_Feature_RebootNeededPlugin>::GetImpl(void)'::`2'::impl
0x1800207fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RebootNeededPlugin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RebootNeededPlugin>::__private_IsEnabled(void)
0x180020802  test    al, al
0x180020804  jz      short loc_180020845
0x180020806  lea     rax, aRebootneededpl; "RebootNeededPlugin"
0x18002080d  mov     qword ptr [rsp+120h+var_100], rax
0x180020812  lea     rax, ?CreateInstance@CRebootNeededPlugin@WaasMedic@@SAJPEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z; WaasMedic::CRebootNeededPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *)
0x180020819  mov     qword ptr [rsp+120h+var_100+8], rax
0x18002081e  mov     rdx, [rdi+8]
0x180020822  cmp     rdx, [rdi+10h]
0x180020826  jz      short loc_180020838
0x180020828  movups  xmm0, [rsp+120h+var_100]
0x18002082d  movdqu  xmmword ptr [rdx], xmm0
0x180020831  add     qword ptr [rdi+8], 10h
0x180020836  jmp     short loc_180020845
0x180020838  lea     r8, [rsp+120h+var_100]
0x18002083d  mov     rcx, rdi
0x180020840  call    ??$_Emplace_reallocate@UtagPluginRegistrationInfo@WaasMedic@@@?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@AEAAPEAUtagPluginRegistrationInfo@WaasMedic@@QEAU23@$$QEAU23@@Z; std::vector<WaasMedic::tagPluginRegistrationInfo>::_Emplace_reallocate<WaasMedic::tagPluginRegistrationInfo>(WaasMedic::tagPluginRegistrationInfo * const,WaasMedic::tagPluginRegistrationInfo &&)
0x180020845  mov     rax, rdi
0x180020848  mov     rcx, [rbp+20h+var_10]
0x18002084c  xor     rcx, rsp; StackCookie
0x18002084f  call    __security_check_cookie
0x180020854  lea     r11, [rsp+120h+var_s0]
0x18002085c  mov     rbx, [r11+18h]
0x180020860  mov     rdi, [r11+20h]
0x180020864  mov     rsp, r11
0x180020867  pop     rbp
0x180020868  retn
```
