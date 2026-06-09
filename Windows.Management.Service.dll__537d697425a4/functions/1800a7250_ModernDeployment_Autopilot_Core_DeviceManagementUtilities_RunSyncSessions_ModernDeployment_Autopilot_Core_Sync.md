# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::RunSyncSessions(ModernDeployment::Autopilot::Core::SyncSessionExitCondition)

- ea: `0x1800a7250`
- end: `0x1800a7b0c`
- name: `?RunSyncSessions@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJW4SyncSessionExitCondition@234@@Z`
- size: `2236`
- prototype: `int __high(enum ModernDeployment::Autopilot::Core::SyncSessionExitCondition)`
- caller_count: `0`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb94`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x180081150`
- `0x180081294`
- `0x180081cac`
- `0x180084d5c`
- `0x18008aea8`
- `0x18008d290`
- `0x18008d620`
- `0x1800a33b0`
- `0x1800a3794`
- `0x1800a4824`
- `0x1800a4848`
- `0x1800a48b4`
- `0x1800a56cc`
- `0x1800a5b60`
- `0x1800a5ce4`
- `0x1800a609c`
- `0x1800a6190`
- `0x1800a622c`
- `0x1800a6300`
- `0x1800a7250`
- `0x1800a8b38`
- `0x1800a8cd4`
- `0x1800a97b4`
- `0x1800a988c`
- `0x1800a9998`
- `0x1800a9a58`
- `0x1800a9b3c`
- `0x1800cce4c`
- `0x1800e2668`
- `0x1800fe4a0`
- `0x1800fe56c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7868`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7868`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a72f2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a72f2`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a761e`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a761e`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a76b0`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a76b0`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x1800a775c`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x1800a775c`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1800a778d`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x1800a778d`

## string_xrefs

- `0x1800a72b4`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a730e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7367`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a749e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a74f4`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7549`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a78a9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7900`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a793b`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7a0a`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7a71`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7ab7`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

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
0x1800a7250  push    rbp
0x1800a7252  push    rbx
0x1800a7253  push    rsi
0x1800a7254  push    rdi
0x1800a7255  push    r12
0x1800a7257  push    r13
0x1800a7259  push    r14
0x1800a725b  push    r15
0x1800a725d  lea     rbp, [rsp-1B8h]
0x1800a7265  sub     rsp, 2B8h
0x1800a726c  mov     rax, cs:__security_cookie
0x1800a7273  xor     rax, rsp
0x1800a7276  mov     [rbp+1F0h+var_50], rax
0x1800a727d  mov     edi, edx
0x1800a727f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl(void)'::`2'::impl
0x1800a7286  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(void)
0x1800a728b  xor     esi, esi
0x1800a728d  test    al, al
0x1800a728f  jz      short loc_1800A7296
0x1800a7291  cmp     edi, 4
0x1800a7294  jz      short loc_1800A72D0
0x1800a7296  mov     [rsp+2F0h+var_290], esi
0x1800a729a  lea     rcx, [rsp+2F0h+var_290]; int *
0x1800a729f  call    ?IsSyncSchedulingDisabledByPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy(int &)
0x1800a72a4  mov     ebx, eax
0x1800a72a6  test    eax, eax
0x1800a72a8  jns     short loc_1800A72CA
0x1800a72aa  mov     rcx, [rbp+1F8h]; this
0x1800a72b1  mov     r9d, eax; char *
0x1800a72b4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a72bb  mov     edx, 66h ; 'f'; void *
0x1800a72c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a72c5  jmp     loc_1800A7AE6
0x1800a72ca  cmp     [rsp+2F0h+var_290], esi
0x1800a72ce  jz      short loc_1800A72D7
0x1800a72d0  xor     eax, eax
0x1800a72d2  jmp     loc_1800A7AE8
0x1800a72d7  mov     [rsp+2F0h+var_280], rsi
0x1800a72dc  cmp     edi, 2
0x1800a72df  jnz     short loc_1800A733C
0x1800a72e1  xor     edx, edx
0x1800a72e3  lea     rcx, [rsp+2F0h+var_280]
0x1800a72e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a72ed  lea     rcx, [rsp+2F0h+var_280]
0x1800a72f2  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a72f9  nop     dword ptr [rax+rax+00h]
0x1800a72fe  mov     ebx, eax
0x1800a7300  test    eax, eax
0x1800a7302  jns     short loc_1800A7322
0x1800a7304  mov     rcx, [rbp+1F8h]; this
0x1800a730b  mov     r9d, eax; char *
0x1800a730e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7315  lea     edx, [rdi+6Fh]; void *
0x1800a7318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a731d  jmp     loc_1800A7ADC
0x1800a7322  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a7329  jz      short loc_1800A733C
0x1800a732b  mov     r8, [rsp+2F0h+var_280]
0x1800a7330  lea     rdx, SyncSessionUserId
0x1800a7337  call    McTemplateU0z_EventWriteTransfer
0x1800a733c  mov     [rsp+2F0h+var_2A8], rsi
0x1800a7341  xor     edx, edx
0x1800a7343  lea     rcx, [rsp+2F0h+var_2A8]
0x1800a7348  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a734d  lea     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 **
0x1800a7352  call    ?GetEnrollmentId@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJPEAPEAG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(ushort * *)
0x1800a7357  mov     ebx, eax
0x1800a7359  test    eax, eax
0x1800a735b  jns     short loc_1800A737D
0x1800a735d  mov     rcx, [rbp+1F8h]; this
0x1800a7364  mov     r9d, eax; char *
0x1800a7367  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a736e  mov     edx, 78h ; 'x'; void *
0x1800a7373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7378  jmp     loc_1800A7AD2
0x1800a737d  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a7382  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800a7387  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a738c  call    ?GetEnrollmentIds@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(std::map<std::wstring,std::wstring> &)
0x1800a7391  mov     ebx, eax
0x1800a7393  test    eax, eax
0x1800a7395  jns     short loc_1800A73A4
0x1800a7397  mov     r9d, eax
0x1800a739a  mov     edx, 7Ch ; '|'
0x1800a739f  jmp     loc_1800A7AB0
0x1800a73a4  mov     [rsp+2F0h+var_278], esi
0x1800a73a8  lea     rcx, [rsp+2F0h+var_278]; unsigned int *
0x1800a73ad  call    ?GetMaxPollingDuration@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetMaxPollingDuration(ulong &)
0x1800a73b2  mov     ebx, eax
0x1800a73b4  test    eax, eax
0x1800a73b6  jns     short loc_1800A73C5
0x1800a73b8  mov     r9d, eax
0x1800a73bb  mov     edx, 7Fh
0x1800a73c0  jmp     loc_1800A7AB0
0x1800a73c5  mov     [rsp+2F0h+var_288], esi
0x1800a73c9  lea     rcx, [rsp+2F0h+var_288]; unsigned int *
0x1800a73ce  call    ?GetSyncInterval@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetSyncInterval(ulong &)
0x1800a73d3  mov     ebx, eax
0x1800a73d5  test    eax, eax
0x1800a73d7  jns     short loc_1800A73E6
0x1800a73d9  mov     r9d, eax
0x1800a73dc  mov     edx, 82h
0x1800a73e1  jmp     loc_1800A7AB0
0x1800a73e6  mov     [rsp+2F0h+var_290], esi
0x1800a73ea  lea     rdx, [rsp+2F0h+var_290]; unsigned int *
0x1800a73ef  lea     rcx, aEnrollmentstat_1; "EnrollmentStatusPageSyncBackoffCountThr"...
0x1800a73f6  call    ?GetAutopilotDwordPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBGAEAK@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetAutopilotDwordPolicy(ushort const * const,ulong &)
0x1800a73fb  test    eax, eax
0x1800a73fd  js      short loc_1800A7407
0x1800a73ff  mov     eax, [rsp+2F0h+var_290]
0x1800a7403  test    eax, eax
0x1800a7405  jnz     short loc_1800A740C
0x1800a7407  mov     eax, 5
0x1800a740c  mov     r13d, [rsp+2F0h+var_298]
0x1800a7411  imul    r13, rax
0x1800a7415  mov     [rbp+1F0h+var_258], r13
0x1800a7419  mov     eax, 0FFFFFFFFh
0x1800a741e  cmp     r13, rax
0x1800a7421  ja      loc_1800A7AA3
0x1800a7427  mov     [rsp+2F0h+var_2B0], esi
0x1800a742b  xor     r14d, r14d
0x1800a742e  xor     r15d, r15d
0x1800a7431  lea     rdx, aRunsyncsession; "RunSyncSessionsForEsp"
0x1800a7438  lea     rcx, [rbp+1F0h+var_1A0]; struct wil::details::IFailureCallback *
0x1800a743c  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a7441  lea     rax, ??_7RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::`vftable'
0x1800a7448  mov     [rbp+1F0h+var_1A0], rax
0x1800a744c  mov     edx, edi; unsigned int
0x1800a744e  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a7452  call    ?StartActivity@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXK@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::StartActivity(ulong)
0x1800a7457  nop
0x1800a7458  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a745f  jz      short loc_1800A7470
0x1800a7461  mov     r8d, edi
0x1800a7464  lea     rdx, BeginningSyncSessions
0x1800a746b  call    McTemplateU0q_EventWriteTransfer
0x1800a7470  mov     r12d, [rsp+2F0h+var_288]
0x1800a7475  mov     qword ptr [rsp+2F0h+var_290], r12
0x1800a747a  test    edi, edi
0x1800a747c  jnz     short loc_1800A74CA
0x1800a747e  lea     rdx, [rsp+2F0h+var_2B0]; int *
0x1800a7483  mov     ecx, esi; unsigned int
0x1800a7485  call    ?HavePolicyProvidersCompletedInstallation@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@SAJKAEAH@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(ulong,int &)
0x1800a748a  mov     ebx, eax
0x1800a748c  test    eax, eax
0x1800a748e  jns     loc_1800A75A2
0x1800a7494  mov     rcx, [rbp+1F8h]; this
0x1800a749b  mov     r9d, eax; char *
0x1800a749e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a74a5  mov     edx, 9Bh; void *
0x1800a74aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a74af  nop
0x1800a74b0  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a74b5  mov     r8d, esi; unsigned int
0x1800a74b8  mov     edx, r15d; unsigned int
0x1800a74bb  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a74bf  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a74c4  nop
0x1800a74c5  jmp     loc_1800A7A98
0x1800a74ca  cmp     edi, 1
0x1800a74cd  jnz     short loc_1800A7520
0x1800a74cf  lea     r8, [rsp+2F0h+var_2B0]; int *
0x1800a74d4  xor     edx, edx; unsigned __int16 *
0x1800a74d6  mov     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 *
0x1800a74db  call    ?IsSyncDone@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0AEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(ushort const * const,ushort const * const,int &)
0x1800a74e0  mov     ebx, eax
0x1800a74e2  test    eax, eax
0x1800a74e4  jns     loc_1800A75A2
0x1800a74ea  mov     rcx, [rbp+1F8h]; this
0x1800a74f1  mov     r9d, eax; char *
0x1800a74f4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a74fb  mov     edx, 9Fh; void *
0x1800a7500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7505  nop
0x1800a7506  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a750b  mov     r8d, esi; unsigned int
0x1800a750e  mov     edx, r15d; unsigned int
0x1800a7511  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a7515  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a751a  nop
0x1800a751b  jmp     loc_1800A7A98
0x1800a7520  cmp     edi, 2
0x1800a7523  jnz     short loc_1800A7575
0x1800a7525  lea     r8, [rsp+2F0h+var_2B0]; int *
0x1800a752a  mov     rdx, [rsp+2F0h+var_280]; unsigned __int16 *
0x1800a752f  mov     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 *
0x1800a7534  call    ?IsSyncDone@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0AEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncDone(ushort const * const,ushort const * const,int &)
0x1800a7539  mov     ebx, eax
0x1800a753b  test    eax, eax
0x1800a753d  jns     short loc_1800A75A2
0x1800a753f  mov     rcx, [rbp+1F8h]; this
0x1800a7546  mov     r9d, eax; char *
0x1800a7549  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7550  mov     edx, 0A3h; void *
0x1800a7555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a755a  nop
0x1800a755b  mov     r9d, [rsp+2F0h+var_2B0]; int
0x1800a7560  mov     r8d, esi; unsigned int
0x1800a7563  mov     edx, r15d; unsigned int
0x1800a7566  lea     rcx, [rbp+1F0h+var_1A0]; this
0x1800a756a  call    ?Stop@RunSyncSessionsForEsp@ZeroTouchProvCxhTelemetry@@QEAAXKKH@Z; ZeroTouchProvCxhTelemetry::RunSyncSessionsForEsp::Stop(ulong,ulong,int)
0x1800a756f  nop
0x1800a7570  jmp     loc_1800A7A98
0x1800a7575  cmp     edi, 3
0x1800a7578  jnz     loc_1800A7A62
0x1800a757e  call    ?IsInOOBE@ProvisioningHelpers@Setup@Management@Windows@@SA_NXZ; Windows::Management::Setup::ProvisioningHelpers::IsInOOBE(void)
0x1800a7583  test    al, al
0x1800a7585  jz      short loc_1800A7599
0x1800a7587  call    ?TryGetDevicePreparationHint@ProvisioningHelpers@Setup@Management@Windows@@SA?AW4AUTOPILOT_DEVICE_PREP_HINT@@XZ; Windows::Management::Setup::ProvisioningHelpers::TryGetDevicePreparationHint(void)
0x1800a758c  test    eax, eax
0x1800a758e  jle     short loc_1800A7599
0x1800a7590  cmp     eax, 4
0x1800a7593  ja      short loc_1800A7599
0x1800a7595  xor     eax, eax
0x1800a7597  jmp     short loc_1800A759E
0x1800a7599  mov     eax, 1
0x1800a759e  mov     [rsp+2F0h+var_2B0], eax
0x1800a75a2  cmp     [rsp+2F0h+var_2B0], 0
0x1800a75a7  jnz     loc_1800A796A
0x1800a75ad  cmp     r14d, 5
0x1800a75b1  jnb     loc_1800A7863
0x1800a75b7  mov     rax, [rsp+2F0h+var_2A0]
0x1800a75bc  mov     rax, [rax]
0x1800a75bf  mov     [rbp+1F0h+var_250], rax
0x1800a75c3  cmp     byte ptr [rax+19h], 0
0x1800a75c7  jnz     loc_1800A7860
0x1800a75cd  lea     rbx, [rax+20h]
0x1800a75d1  mov     rdx, rbx
0x1800a75d4  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a75d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a75dd  lea     rdx, [rbx+20h]
0x1800a75e1  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a75e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a75ea  cmp     [rbp+1F0h+var_1B0], 0
0x1800a75ef  jz      loc_1800A76FF
0x1800a75f5  xor     r14b, r14b
0x1800a75f8  mov     ebx, 40h ; '@'
0x1800a75fd  mov     r8d, ebx; Size
0x1800a7600  xor     edx, edx; Val
0x1800a7602  lea     rcx, [rbp+1F0h+var_240]; void *
0x1800a7606  call    memset_0
0x1800a760b  mov     [rbp+1F0h+var_240], ebx
0x1800a760e  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a7612  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7617  mov     rcx, rax
0x1800a761a  lea     rdx, [rbp+1F0h+var_240]
0x1800a761e  call    cs:__imp_OmaDmGetInitiationInfo
0x1800a7625  nop     dword ptr [rax+rax+00h]
0x1800a762a  mov     r12d, eax
0x1800a762d  test    eax, eax
0x1800a762f  js      short loc_1800A76AC
0x1800a7631  mov     r13d, [rbp+1F0h+var_22C]
0x1800a7635  lea     ecx, [r13-5]
0x1800a7639  cmp     ecx, 1
0x1800a763c  setbe   r14b
0x1800a7640  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a7647  jz      short loc_1800A7678
0x1800a7649  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a764d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7652  mov     rbx, rax
0x1800a7655  lea     rcx, [rbp+1F0h+var_1C0]
0x1800a7659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a765e  movzx   r8d, r14b
0x1800a7662  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x1800a7666  mov     [rsp+2F0h+var_2C8], rbx
0x1800a766b  mov     [rsp+2F0h+var_2D0], rax
0x1800a7670  mov     r9d, r13d
0x1800a7673  call    McTemplateU0qqzzq_EventWriteTransfer
0x1800a7678  test    r14b, r14b
0x1800a767b  jz      short loc_1800A76A8
0x1800a767d  lea     r8, [rbp+1F0h+var_1E0]
0x1800a7681  lea     rdx, [rbp+1F0h+var_200]
0x1800a7685  lea     rcx, [rsp+2F0h+var_2A0]
0x1800a768a  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800a768f  mov     rcx, [rax]
0x1800a7692  add     rcx, 40h ; '@'
0x1800a7696  mov     qword ptr [rcx+10h], 0
0x1800a769e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a76a3  xor     ecx, ecx
0x1800a76a5  mov     [rax], cx
0x1800a76a8  mov     r13, [rbp+1F0h+var_258]
0x1800a76ac  lea     rcx, [rbp+1F0h+var_240]
0x1800a76b0  call    cs:__imp_OmaDmFreeInitiationInfo
0x1800a76b7  nop     dword ptr [rax+rax+00h]
0x1800a76bc  test    r14b, r14b
0x1800a76bf  jnz     short loc_1800A76FA
0x1800a76c1  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800a76c8  jz      loc_1800A7837
0x1800a76ce  lea     rcx, [rbp+1F0h+var_1E0]
0x1800a76d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a76d7  mov     r9, rax
0x1800a76da  mov     dword ptr [rsp+2F0h+var_2C8], 0
0x1800a76e2  mov     dword ptr [rsp+2F0h+var_2D0], edi
0x1800a76e6  mov     r8d, r12d
0x1800a76e9  lea     rdx, SyncSessionSkipped
0x1800a76f0  call    McTemplateU0dzqq_EventWriteTransfer
0x1800a76f5  jmp     loc_1800A7837
0x1800a76fa  mov     r12, qword ptr [rsp+2F0h+var_290]
0x1800a76ff  mov     qword ptr [rsp+2F0h+var_288], 0
0x1800a7708  lea     rcx, [rbp+1F0h+var_1E0]
  ... truncated ...
```
