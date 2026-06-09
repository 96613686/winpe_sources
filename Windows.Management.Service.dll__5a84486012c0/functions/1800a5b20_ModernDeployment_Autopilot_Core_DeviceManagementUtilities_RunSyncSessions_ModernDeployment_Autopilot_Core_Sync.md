# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::RunSyncSessions(ModernDeployment::Autopilot::Core::SyncSessionExitCondition)

- ea: `0x1800a5b20`
- end: `0x1800a63b7`
- name: `?RunSyncSessions@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJW4SyncSessionExitCondition@234@@Z`
- size: `2199`
- prototype: `int __high(enum ModernDeployment::Autopilot::Core::SyncSessionExitCondition)`
- caller_count: `0`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x18006b708`
- `0x18006c694`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x180080708`
- `0x18008084c`
- `0x18008122c`
- `0x1800841e8`
- `0x180089ff4`
- `0x18008c244`
- `0x18008c588`
- `0x1800a1d9c`
- `0x1800a2174`
- `0x1800a31d4`
- `0x1800a31f8`
- `0x1800a3264`
- `0x1800a4044`
- `0x1800a44c4`
- `0x1800a4644`
- `0x1800a49ec`
- `0x1800a4ae0`
- `0x1800a4b7c`
- `0x1800a4c48`
- `0x1800a5b20`
- `0x1800a7358`
- `0x1800a74e4`
- `0x1800a7fac`
- `0x1800a8084`
- `0x1800a8180`
- `0x1800a823c`
- `0x1800a8320`
- `0x1800cab84`
- `0x1800dfdf0`
- `0x1800fb3c0`
- `0x1800fb480`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a611a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a611a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a5bc2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a5bc2`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a5ee8`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a5ee8`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a5f74`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a5f74`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x1800a601a`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x1800a601a`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1800a6045`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1800a6045`

## string_xrefs

- `0x1800a5b84`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5bd8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5c31`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5d68`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5dbe`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a5e13`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6155`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a61ac`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a61e7`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a62b6`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a631d`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6363`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceManagementUtilities::RunSyncSessions(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v3; // esi
  int IsSyncSchedulingDisabledByPolicy; // eax
  unsigned int v5; // ebx
  int ActiveUserSid; // eax
  __int64 v8; // rcx
  int EnrollmentId; // eax
  int EnrollmentIds; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int MaxPollingDuration; // eax
  int SyncInterval; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // r13
  unsigned int v17; // r14d
  unsigned int v18; // r15d
  __int64 v19; // rcx
  unsigned int v20; // r12d
  int HavePolicyProvidersCompletedInstallation; // eax
  __int64 v22; // rcx
  int IsSyncDone; // eax
  int v24; // eax
  int DevicePreparationHint; // eax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rbx
  bool v29; // r14
  __int64 v30; // rax
  int InitiationInfo; // r12d
  int v32; // r13d
  __int64 v33; // rbx
  __int64 v34; // rax
  int v35; // edx
  int v36; // ecx
  __int64 v37; // rcx
  int v38; // eax
  int v39; // ecx
  __int64 v40; // rax
  int v41; // eax
  int v42; // ebx
  int v43; // eax
  int v44; // edx
  int v45; // ecx
  __int64 v46; // rbx
  _QWORD *v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // edi
  unsigned int v50; // edi
  const unsigned __int16 *v51; // rcx
  int v52; // eax
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v57; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v58; // [rsp+58h] [rbp-A8h]
  unsigned int v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v60[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v61; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v62; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v63[2]; // [rsp+80h] [rbp-80h] BYREF
  char v64; // [rsp+90h] [rbp-70h]
  unsigned __int64 v65; // [rsp+98h] [rbp-68h]
  __int64 v66; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v67[5]; // [rsp+B0h] [rbp-50h] BYREF
  int v68; // [rsp+C4h] [rbp-3Ch]
  char v69[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v70[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v71[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v72[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v73; // [rsp+140h] [rbp+40h]
  _QWORD v74[42]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v3 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl'::`2'::impl)
    && a2 == 4 )
  {
    return 0;
  }
  v59[0] = 0;
  IsSyncSchedulingDisabledByPolicy = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy((int *)v59);
  v5 = IsSyncSchedulingDisabledByPolicy;
  if ( IsSyncSchedulingDisabledByPolicy >= 0 )
  {
    if ( v59[0] )
      return 0;
    v61 = 0;
    if ( a2 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v61,
        0);
      ActiveUserSid = DmGetActiveUserSid(&v61);
      v5 = ActiveUserSid;
      if ( ActiveUserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          v53);
LABEL_97:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
        return v5;
      }
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, SyncSessionUserId, v61);
    }
    v56 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v56,
      0);
    EnrollmentId = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(&v56);
    v5 = EnrollmentId;
    if ( EnrollmentId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
        (const char *)(unsigned int)EnrollmentId,
        v53);
LABEL_96:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
      goto LABEL_97;
    }
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v57);
    EnrollmentIds = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(&v57);
    v5 = EnrollmentIds;
    if ( EnrollmentIds < 0 )
    {
      v11 = (unsigned int)EnrollmentIds;
      v12 = 124;
LABEL_94:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
        (const char *)v11,
        v53);
LABEL_95:
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        &v57,
        &v57);
      goto LABEL_96;
    }
    v62 = 0;
    MaxPollingDuration = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetMaxPollingDuration(&v62);
    v5 = MaxPollingDuration;
    if ( MaxPollingDuration < 0 )
    {
      v11 = (unsigned int)MaxPollingDuration;
      v12 = 127;
      goto LABEL_94;
    }
    v60[0] = 0;
    SyncInterval = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetSyncInterval(v60);
    v5 = SyncInterval;
    if ( SyncInterval < 0 )
    {
      v11 = (unsigned int)SyncInterval;
      v12 = 130;
      goto LABEL_94;
    }
    v59[0] = 0;
    if ( (int)ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetAutopilotDwordPolicy(
                L"EnrollmentStatusPageSyncBackoffCountThreshold",
                v59) < 0
      || (v15 = v59[0]) == 0 )
    {
      v15 = 5;
    }
    v16 = v15 * v58;
    v65 = v16;
    if ( v16 > 0xFFFFFFFF )
    {
      v5 = -2147024362;
      v11 = 2147942934LL;
      v12 = 134;
      goto LABEL_94;
    }
    v55 = 0;
    v17 = 0;
    v18 = 0;
    wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v74);
    v74[0] = &ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::`vftable';
    ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::StartActivity(
      (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
      a2);
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v19, BeginningSyncSessions, a2);
    v20 = v60[0];
    *(_QWORD *)v59 = v60[0];
    while ( 1 )
    {
      if ( a2 )
      {
        switch ( a2 )
        {
          case 1u:
            IsSyncDone = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(v56, 0, &v55);
            v5 = IsSyncDone;
            if ( IsSyncDone < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9F,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                (const char *)(unsigned int)IsSyncDone,
                v53);
              ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
                (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
                v18,
                v3,
                v55);
              goto LABEL_92;
            }
            break;
          case 2u:
            v24 = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(v56, v61, &v55);
            v5 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA3,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                (const char *)(unsigned int)v24,
                v53);
              ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
                (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
                v18,
                v3,
                v55);
              goto LABEL_92;
            }
            break;
          case 3u:
            v26 = 1;
            if ( Windows::Management::Setup::ProvisioningHelpers::IsInOOBE() )
            {
              DevicePreparationHint = Windows::Management::Setup::ProvisioningHelpers::TryGetDevicePreparationHint();
              if ( DevicePreparationHint > 0 && (unsigned int)DevicePreparationHint <= 4 )
                v26 = 0;
            }
            v55 = v26;
            break;
          default:
            v5 = -2147418113;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAB,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
              (const char *)0x8000FFFFLL,
              v53);
            ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
              (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
              v18,
              v3,
              v55);
LABEL_92:
            ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::~RunSyncSessionsForEsp((ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74);
            goto LABEL_95;
        }
      }
      else
      {
        HavePolicyProvidersCompletedInstallation = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(
                                                     v3,
                                                     &v55);
        v5 = HavePolicyProvidersCompletedInstallation;
        if ( HavePolicyProvidersCompletedInstallation < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9B,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
            (const char *)(unsigned int)HavePolicyProvidersCompletedInstallation,
            v53);
          ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
            (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
            v18,
            v3,
            v55);
          goto LABEL_92;
        }
      }
      if ( v55 )
        break;
      if ( v17 < 5 )
      {
        v27 = *v57;
        v66 = *v57;
        while ( 1 )
        {
          if ( *(_BYTE *)(v27 + 25) )
          {
            v17 = v20;
            break;
          }
          v28 = v27 + 32;
          std::wstring::wstring(v71, v27 + 32);
          std::wstring::wstring(v72, v28 + 32);
          if ( v73 )
          {
            v29 = 0;
            memset_0(v67, 0, 0x40u);
            v67[0] = 64;
            v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
            InitiationInfo = OmaDmGetInitiationInfo(v30, v67);
            if ( InitiationInfo >= 0 )
            {
              v32 = v68;
              v29 = (unsigned int)(v68 - 5) <= 1;
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
              {
                v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
                v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
                McTemplateU0qqzzq_EventWriteTransfer(v36, v35, v29, v32, v34, v33, a2);
              }
              if ( v29 )
              {
                v37 = *(_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(
                                   &v57,
                                   v69,
                                   v71)
                    + 64LL;
                *(_QWORD *)(v37 + 16) = 0;
                *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37) = 0;
              }
              LODWORD(v16) = v65;
            }
            OmaDmFreeInitiationInfo(v67);
            if ( !v29 )
            {
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
              {
                v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
                McTemplateU0dzqq_EventWriteTransfer(v39, (unsigned int)SyncSessionSkipped, InitiationInfo, v38, a2, 0);
              }
              goto LABEL_68;
            }
            v20 = v59[0];
          }
          *(_QWORD *)v60 = 0;
          v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
          v63[1] = 0;
          v64 = 1;
          v63[0] = v60;
          v53 = 0;
          if ( a2 == 2 )
            v41 = OmaDmInitiateSessionAsUser(v61, v40, 1, 2);
          else
            v41 = OmaDmInitiateSessionAsDevice(v40, 1, 2);
          v42 = v41;
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v63);
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
          {
            v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
            McTemplateU0dzqz_EventWriteTransfer(v45, v44, v42, v43, a2, *(__int64 *)v60);
          }
          if ( (int)(v42 + 0x80000000) < 0 || v42 == -2102656508 )
          {
            v46 = *(_QWORD *)v60;
            v47 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(&v57, v70, v71);
            std::wstring::assign(*v47 + 64LL, v46);
            if ( !(++v18 % (unsigned int)v16) )
            {
              *(_QWORD *)v59 = 2LL * v20;
              if ( *(_QWORD *)v59 > 0xFFFFFFFF )
              {
                v5 = -2147024362;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x10D,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                  (const char *)0x80070216LL,
                  v53);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v60);
                std::wstring::_Tidy_deallocate(v72);
                std::wstring::_Tidy_deallocate(v71);
                ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
                  (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
                  v18,
                  v3,
                  v55);
                goto LABEL_92;
              }
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v60);
LABEL_68:
          std::wstring::_Tidy_deallocate(v72);
          std::wstring::_Tidy_deallocate(v71);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v66);
          v27 = v66;
          v20 = v59[0];
        }
      }
      Sleep(0x1388u);
      v48 = v3 + 5;
      if ( v3 + 5 < v3 )
      {
        v5 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
          (const char *)0x80070216LL,
          v53);
        ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
          (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
          v18,
          0xFFFFFFFF,
          v55);
        goto LABEL_92;
      }
      v3 += 5;
      if ( v17 < 5 )
      {
        v5 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
          (const char *)0x80070216LL,
          v53);
        ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
          (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
          v18,
          v3,
          v55);
        goto LABEL_92;
      }
      if ( v48 > v62 )
        goto LABEL_79;
      v17 -= 5;
    }
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v22, ExitingSyncSessions, a2);
LABEL_79:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
      goto LABEL_90;
    if ( a2 )
    {
      v49 = a2 - 1;
      if ( v49 )
      {
        v50 = v49 - 1;
        if ( v50 )
        {
          if ( v50 == 1 )
          {
            v51 = L"WindowsAutopilot.Telemetry.EarlyBoot.ESP.Sync.DppProvisioning";
            goto LABEL_88;
          }
LABEL_90:
          ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(
            (ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74,
            v18,
            v3,
            v55);
          ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::~RunSyncSessionsForEsp((ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp *)v74);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            &v57,
            &v57);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
          return 0;
        }
        v51 = L"WindowsAutopilot.Telemetry.EarlyBoot.ESP.Sync.AccountSetup";
      }
      else
      {
        v51 = L"WindowsAutopilot.Telemetry.EarlyBoot.ESP.Sync.DeviceSetup";
      }
    }
    else
    {
      v51 = L"WindowsAutopilot.Telemetry.EarlyBoot.ESP.Sync.PolicyProviders";
    }
LABEL_88:
    v52 = ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(
            v51,
            v55 != 0,
            v55 == 0 ? 0x800705B4 : 0,
            1000LL * v3,
            0);
    if ( v52 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
        (const char *)(unsigned int)v52,
        v54);
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
    (const char *)(unsigned int)IsSyncSchedulingDisabledByPolicy,
    v53);
  return v5;
}

```

## disassembly

```asm
0x1800a5b20  push    rbp
0x1800a5b22  push    rbx
0x1800a5b23  push    rsi
0x1800a5b24  push    rdi
0x1800a5b25  push    r12
0x1800a5b27  push    r13
0x1800a5b29  push    r14
0x1800a5b2b  push    r15
0x1800a5b2d  lea     rbp, [rsp-1B8h]
0x1800a5b35  sub     rsp, 2B8h
0x1800a5b3c  mov     rax, cs:__security_cookie
0x1800a5b43  xor     rax, rsp
0x1800a5b46  mov     [rbp+1F0h+var_50], rax
0x1800a5b4d  mov     edi, edx
0x1800a5b4f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl(void)'::`2'::impl
0x1800a5b56  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(void)
0x1800a5b5b  xor     esi, esi
0x1800a5b5d  test    al, al
0x1800a5b5f  jz      short loc_1800A5B66
0x1800a5b61  cmp     edi, 4
0x1800a5b64  jz      short loc_1800A5BA0
0x1800a5b66  mov     [rsp+2F0h+var_290], esi
0x1800a5b6a  lea     rcx, [rsp+2F0h+var_290]; int *
0x1800a5b6f  call    ?IsSyncSchedulingDisabledByPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy(int &)
0x1800a5b74  mov     ebx, eax
0x1800a5b76  test    eax, eax
0x1800a5b78  jns     short loc_1800A5B9A
0x1800a5b7a  mov     rcx, [rbp+1F8h]; this
0x1800a5b81  mov     r9d, eax; char *
0x1800a5b84  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5b8b  mov     edx, 66h ; 'f'; void *
0x1800a5b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5b95  jmp     loc_1800A6392
0x1800a5b9a  cmp     [rsp+2F0h+var_290], esi
0x1800a5b9e  jz      short loc_1800A5BA7
0x1800a5ba0  xor     eax, eax
0x1800a5ba2  jmp     loc_1800A6394
0x1800a5ba7  mov     [rsp+2F0h+var_280], rsi
0x1800a5bac  cmp     edi, 2
0x1800a5baf  jnz     short loc_1800A5C06
0x1800a5bb1  xor     edx, edx
0x1800a5bb3  lea     rcx, [rsp+2F0h+var_280]
0x1800a5bb8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a5bbd  lea     rcx, [rsp+2F0h+var_280]
0x1800a5bc2  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a5bc8  mov     ebx, eax
0x1800a5bca  test    eax, eax
0x1800a5bcc  jns     short loc_1800A5BEC
0x1800a5bce  mov     rcx, [rbp+1F8h]; this
0x1800a5bd5  mov     r9d, eax; char *
0x1800a5bd8  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5bdf  lea     edx, [rdi+6Fh]; void *
0x1800a5be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5be7  jmp     loc_1800A6388
0x1800a5bec  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a5bf3  jz      short loc_1800A5C06
0x1800a5bf5  mov     r8, [rsp+2F0h+var_280]
0x1800a5bfa  lea     rdx, SyncSessionUserId
0x1800a5c01  call    McTemplateU0z_EventWriteTransfer
0x1800a5c06  mov     [rsp+2F0h+var_2A8], rsi
0x1800a5c0b  xor     edx, edx
0x1800a5c0d  lea     rcx, [rsp+2F0h+var_2A8]
0x1800a5c12  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a5c17  lea     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 **
0x1800a5c1c  call    ?GetEnrollmentId@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJPEAPEAG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(ushort * *)
0x1800a5c21  mov     ebx, eax
0x1800a5c23  test    eax, eax
0x1800a5c25  jns     short loc_1800A5C47
0x1800a5c27  mov     rcx, [rbp+1F8h]; this
0x1800a5c2e  mov     r9d, eax; char *
0x1800a5c31  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5c38  mov     edx, 78h ; 'x'; void *
0x1800a5c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5c42  jmp     loc_1800A637E
0x1800a5c47  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a5c4c  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800a5c51  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a5c56  call    ?GetEnrollmentIds@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(std::map<std::wstring,std::wstring> &)
0x1800a5c5b  mov     ebx, eax
0x1800a5c5d  test    eax, eax
0x1800a5c5f  jns     short loc_1800A5C6E
0x1800a5c61  mov     r9d, eax
0x1800a5c64  mov     edx, 7Ch ; '|'
0x1800a5c69  jmp     loc_1800A635C
0x1800a5c6e  mov     [rsp+2F0h+var_278], esi
0x1800a5c72  lea     rcx, [rsp+2F0h+var_278]; unsigned int *
0x1800a5c77  call    ?GetMaxPollingDuration@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetMaxPollingDuration(ulong &)
0x1800a5c7c  mov     ebx, eax
0x1800a5c7e  test    eax, eax
0x1800a5c80  jns     short loc_1800A5C8F
0x1800a5c82  mov     r9d, eax
0x1800a5c85  mov     edx, 7Fh
0x1800a5c8a  jmp     loc_1800A635C
0x1800a5c8f  mov     [rsp+2F0h+var_288], esi
0x1800a5c93  lea     rcx, [rsp+2F0h+var_288]; unsigned int *
0x1800a5c98  call    ?GetSyncInterval@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetSyncInterval(ulong &)
0x1800a5c9d  mov     ebx, eax
0x1800a5c9f  test    eax, eax
0x1800a5ca1  jns     short loc_1800A5CB0
0x1800a5ca3  mov     r9d, eax
0x1800a5ca6  mov     edx, 82h
0x1800a5cab  jmp     loc_1800A635C
0x1800a5cb0  mov     [rsp+2F0h+var_290], esi
0x1800a5cb4  lea     rdx, [rsp+2F0h+var_290]; unsigned int *
0x1800a5cb9  lea     rcx, aEnrollmentstat_1; "EnrollmentStatusPageSyncBackoffCountThr"...
0x1800a5cc0  call    ?GetAutopilotDwordPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBGAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetAutopilotDwordPolicy(ushort const * const,ulong &)
0x1800a5cc5  test    eax, eax
0x1800a5cc7  js      short loc_1800A5CD1
0x1800a5cc9  mov     eax, [rsp+2F0h+var_290]
0x1800a5ccd  test    eax, eax
0x1800a5ccf  jnz     short loc_1800A5CD6
0x1800a5cd1  mov     eax, 5
0x1800a5cd6  mov     r13d, [rsp+2F0h+var_298]
0x1800a5cdb  imul    r13, rax
0x1800a5cdf  mov     [rbp+1F0h+var_258], r13
0x1800a5ce3  mov     eax, 0FFFFFFFFh
0x1800a5ce8  cmp     r13, rax
0x1800a5ceb  ja      loc_1800A634F
0x1800a5cf1  mov     [rsp+2F0h+var_2B0], esi
0x1800a5cf5  xor     r14d, r14d
0x1800a5cf8  xor     r15d, r15d
0x1800a5cfb  lea     rdx, aRunsyncsession; "RunSyncSessionsForEsp"
0x1800a5d02  lea     rcx, [rbp+1F0h+var_1A0]; struct wil::details::IFailureCallback *
0x1800a5d06  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a5d0b  lea     rax, ??_7RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::`vftable'
0x1800a5d12  mov     [rbp+1F0h+var_1A0], rax
0x1800a5d16  mov     edx, edi; unsigned int
0x1800a5d18  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a5d1c  call    ?StartActivity@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXK@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::StartActivity(ulong)
0x1800a5d21  nop
0x1800a5d22  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a5d29  jz      short loc_1800A5D3A
0x1800a5d2b  mov     r8d, edi
0x1800a5d2e  lea     rdx, BeginningSyncSessions
0x1800a5d35  call    McTemplateU0q_EventWriteTransfer
0x1800a5d3a  mov     r12d, [rsp+2F0h+var_288]
0x1800a5d3f  mov     qword ptr [rsp+2F0h+var_290], r12
0x1800a5d44  test    edi, edi
0x1800a5d46  jnz     short loc_1800A5D94
0x1800a5d48  lea     rdx, [rsp+2F0h+var_2B0]; int *
0x1800a5d4d  mov     ecx, esi; unsigned int
0x1800a5d4f  call    ?HavePolicyProvidersCompletedInstallation@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@SAJKAEAH@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(ulong,int &)
0x1800a5d54  mov     ebx, eax
0x1800a5d56  test    eax, eax
0x1800a5d58  jns     loc_1800A5E6C
0x1800a5d5e  mov     rcx, [rbp+1F8h]; this
0x1800a5d65  mov     r9d, eax; char *
0x1800a5d68  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5d6f  mov     edx, 9Bh; void *
0x1800a5d74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5d79  nop
0x1800a5d7a  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a5d7f  mov     r8d, esi; unsigned int
0x1800a5d82  mov     edx, r15d; unsigned int
0x1800a5d85  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a5d89  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a5d8e  nop
0x1800a5d8f  jmp     loc_1800A6344
0x1800a5d94  cmp     edi, 1
0x1800a5d97  jnz     short loc_1800A5DEA
0x1800a5d99  lea     r8, [rsp+2F0h+var_2B0]; int *
0x1800a5d9e  xor     edx, edx; unsigned __int16 *
0x1800a5da0  mov     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 *
0x1800a5da5  call    ?IsSyncDone@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0AEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(ushort const * const,ushort const * const,int &)
0x1800a5daa  mov     ebx, eax
0x1800a5dac  test    eax, eax
0x1800a5dae  jns     loc_1800A5E6C
0x1800a5db4  mov     rcx, [rbp+1F8h]; this
0x1800a5dbb  mov     r9d, eax; char *
0x1800a5dbe  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5dc5  mov     edx, 9Fh; void *
0x1800a5dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5dcf  nop
0x1800a5dd0  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a5dd5  mov     r8d, esi; unsigned int
0x1800a5dd8  mov     edx, r15d; unsigned int
0x1800a5ddb  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a5ddf  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a5de4  nop
0x1800a5de5  jmp     loc_1800A6344
0x1800a5dea  cmp     edi, 2
0x1800a5ded  jnz     short loc_1800A5E3F
0x1800a5def  lea     r8, [rsp+2F0h+var_2B0]; int *
0x1800a5df4  mov     rdx, [rsp+2F0h+var_280]; unsigned __int16 *
0x1800a5df9  mov     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 *
0x1800a5dfe  call    ?IsSyncDone@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0AEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(ushort const * const,ushort const * const,int &)
0x1800a5e03  mov     ebx, eax
0x1800a5e05  test    eax, eax
0x1800a5e07  jns     short loc_1800A5E6C
0x1800a5e09  mov     rcx, [rbp+1F8h]; this
0x1800a5e10  mov     r9d, eax; char *
0x1800a5e13  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5e1a  mov     edx, 0A3h; void *
0x1800a5e1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5e24  nop
0x1800a5e25  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a5e2a  mov     r8d, esi; unsigned int
0x1800a5e2d  mov     edx, r15d; unsigned int
0x1800a5e30  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a5e34  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a5e39  nop
0x1800a5e3a  jmp     loc_1800A6344
0x1800a5e3f  cmp     edi, 3
0x1800a5e42  jnz     loc_1800A630E
0x1800a5e48  call    ?IsInOOBE@ProvisioningHelpers@Setup@Management@Windows@@SA_NXZ; Windows::Management::Setup::ProvisioningHelpers::IsInOOBE(void)
0x1800a5e4d  test    al, al
0x1800a5e4f  jz      short loc_1800A5E63
0x1800a5e51  call    ?TryGetDevicePreparationHint@ProvisioningHelpers@Setup@Management@Windows@@SA?AW4AUTOPILOT_DEVICE_PREP_HINT@@XZ; Windows::Management::Setup::ProvisioningHelpers::TryGetDevicePreparationHint(void)
0x1800a5e56  test    eax, eax
0x1800a5e58  jle     short loc_1800A5E63
0x1800a5e5a  cmp     eax, 4
0x1800a5e5d  ja      short loc_1800A5E63
0x1800a5e5f  xor     eax, eax
0x1800a5e61  jmp     short loc_1800A5E68
0x1800a5e63  mov     eax, 1
0x1800a5e68  mov     [rsp+2F0h+var_2B0], eax
0x1800a5e6c  cmp     [rsp+2F0h+var_2B0], 0
0x1800a5e71  jnz     loc_1800A6216
0x1800a5e77  cmp     r14d, 5
0x1800a5e7b  jnb     loc_1800A6115
0x1800a5e81  mov     rax, [rsp+2F0h+var_2A0]
0x1800a5e86  mov     rax, [rax]
0x1800a5e89  mov     [rbp+1F0h+var_250], rax
0x1800a5e8d  cmp     byte ptr [rax+19h], 0
0x1800a5e91  jnz     loc_1800A6112
0x1800a5e97  lea     rbx, [rax+20h]
0x1800a5e9b  mov     rdx, rbx
0x1800a5e9e  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a5ea2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a5ea7  lea     rdx, [rbx+20h]
0x1800a5eab  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a5eaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a5eb4  cmp     [rbp+1F0h+var_1B0], 0
0x1800a5eb9  jz      loc_1800A5FBD
0x1800a5ebf  xor     r14b, r14b
0x1800a5ec2  mov     ebx, 40h ; '@'
0x1800a5ec7  mov     r8d, ebx; Size
0x1800a5eca  xor     edx, edx; Val
0x1800a5ecc  lea     rcx, [rbp+1F0h+var_240]; void *
0x1800a5ed0  call    memset_0
0x1800a5ed5  mov     [rbp+1F0h+var_240], ebx
0x1800a5ed8  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a5edc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5ee1  mov     rcx, rax
0x1800a5ee4  lea     rdx, [rbp+1F0h+var_240]
0x1800a5ee8  call    cs:__imp_OmaDmGetInitiationInfo
0x1800a5eee  mov     r12d, eax
0x1800a5ef1  test    eax, eax
0x1800a5ef3  js      short loc_1800A5F70
0x1800a5ef5  mov     r13d, [rbp+1F0h+var_22C]
0x1800a5ef9  lea     ecx, [r13-5]
0x1800a5efd  cmp     ecx, 1
0x1800a5f00  setbe   r14b
0x1800a5f04  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a5f0b  jz      short loc_1800A5F3C
0x1800a5f0d  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a5f11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5f16  mov     rbx, rax
0x1800a5f19  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a5f1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5f22  movzx   r8d, r14b
0x1800a5f26  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x1800a5f2a  mov     [rsp+2F0h+var_2C8], rbx
0x1800a5f2f  mov     [rsp+2F0h+var_2D0], rax
0x1800a5f34  mov     r9d, r13d
0x1800a5f37  call    McTemplateU0qqzzq_EventWriteTransfer
0x1800a5f3c  test    r14b, r14b
0x1800a5f3f  jz      short loc_1800A5F6C
0x1800a5f41  lea     r8, [rbp+1F0h+var_1E0]
0x1800a5f45  lea     rdx, [rbp+1F0h+var_200]
0x1800a5f49  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a5f4e  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800a5f53  mov     rcx, [rax]
0x1800a5f56  add     rcx, 40h ; '@'
0x1800a5f5a  mov     qword ptr [rcx+10h], 0
0x1800a5f62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5f67  xor     ecx, ecx
0x1800a5f69  mov     [rax], cx
0x1800a5f6c  mov     r13, [rbp+1F0h+var_258]
0x1800a5f70  lea     rcx, [rbp+1F0h+var_240]
0x1800a5f74  call    cs:__imp_OmaDmFreeInitiationInfo
0x1800a5f7a  test    r14b, r14b
0x1800a5f7d  jnz     short loc_1800A5FB8
0x1800a5f7f  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a5f86  jz      loc_1800A60E9
0x1800a5f8c  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a5f90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5f95  mov     r9, rax
0x1800a5f98  mov     dword ptr [rsp+2F0h+var_2C8], 0
0x1800a5fa0  mov     dword ptr [rsp+2F0h+var_2D0], edi
0x1800a5fa4  mov     r8d, r12d
0x1800a5fa7  lea     rdx, SyncSessionSkipped
0x1800a5fae  call    McTemplateU0dzqq_EventWriteTransfer
0x1800a5fb3  jmp     loc_1800A60E9
0x1800a5fb8  mov     r12, qword ptr [rsp+2F0h+var_290]
0x1800a5fbd  mov     qword ptr [rsp+2F0h+var_288], 0
0x1800a5fc6  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a5fca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5fcf  lea     rcx, [rsp+2F0h+var_288]
0x1800a5fd4  mov     [rbp+1F0h+var_268], 0
  ... truncated ...
```
