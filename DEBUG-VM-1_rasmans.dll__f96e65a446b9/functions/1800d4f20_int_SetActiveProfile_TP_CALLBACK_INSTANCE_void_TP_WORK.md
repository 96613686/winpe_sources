# int_SetActiveProfile(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800d4f20`
- end: `0x1800d5e73`
- name: `?int_SetActiveProfile@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `3923`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180065328`
- `0x1800a4874`
- `0x1800a49ec`
- `0x1800a56d8`
- `0x1800a68d8`
- `0x1800a6cbc`
- `0x1800b81fc`
- `0x1800bf670`
- `0x1800c0e48`
- `0x1800c0ef0`
- `0x1800d4f20`
- `0x1800d61bc`
- `0x1800daba4`
- `0x1800db0ac`
- `0x1800dbbb0`
- `0x1800dc76c`
- `0x1800dc964`
- `0x1800dde2c`
- `0x1800e014c`
- `0x1800e0b3c`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e1e64`
- `0x1800e218c`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800d56be`
- `ntdll!RtlFreeSid` at `0x1800d56be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d58c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d58c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5e1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5e1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5d31`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5d31`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d58b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d58b7`

## string_xrefs

- `0x1800d5219`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5279`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5332`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d561a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d57b1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5869`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5918`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d596f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d59db`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5b49`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5bee`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5cb1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5d88`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d589c`: `VpnStringCopy for pProfileName`
- `0x1800d57e4`: `VpnStringCopy for pProfilePhonebookPath `

## pseudocode

```c
void __fastcall int_SetActiveProfile(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  DWORD v3; // r13d
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v5; // rsi
  struct _LIST_ENTRY *v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  struct _LIST_ENTRY *v10; // rbp
  struct _LIST_ENTRY *Blink; // r14
  const WCHAR *v12; // r12
  int v13; // ebx
  unsigned int Blink_high; // r15d
  struct _LIST_ENTRY *v15; // rcx
  const char *v16; // r8
  const char *v17; // rax
  LPCWSTR *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // r8
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // ebx
  int v28; // edi
  unsigned int v29; // ebx
  struct _LIST_ENTRY *v30; // rcx
  LPCWSTR v31; // rax
  int v32; // edx
  int v33; // r8d
  LPCWSTR v34; // rax
  int v35; // edx
  int v36; // r8d
  unsigned int v37; // ebx
  __int64 v38; // r8
  struct _LIST_ENTRY *v39; // rcx
  __int64 v40; // rdx
  LPCWSTR v41; // rax
  int v42; // edx
  int v43; // r8d
  LPCWSTR v44; // rax
  int v45; // edx
  int v46; // r8d
  WCHAR *v47; // rcx
  _DWORD **v48; // rdi
  int v49; // eax
  int v50; // ebx
  int v51; // eax
  const char *v53; // rdx
  __int64 *v54; // rdi
  int v55; // eax
  int v56; // eax
  DWORD LastError; // eax
  DWORD v59; // ebx
  __int64 v60; // r8
  DWORD v61; // eax
  struct _LIST_ENTRY *v62; // rcx
  DWORD v63; // eax
  int v64; // r8d
  unsigned int LockdownNciNrptRule; // eax
  DWORD ActiveTokenAndSessionId; // eax
  unsigned int v67; // eax
  __int64 v68; // r8
  __int64 v69; // r9
  unsigned int v70; // ebx
  struct _LIST_ENTRY *v71; // rcx
  __int64 v72; // rdx
  DWORD v73; // eax
  bool v74; // di
  struct _TP_WORK *v75; // rcx
  struct _LIST_ENTRY *v76; // [rsp+40h] [rbp-58h]
  PSID Sid; // [rsp+48h] [rbp-50h] BYREF
  DWORD v78; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 618, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  v3 = 0;
  Sid = 0;
  v78 = 0;
  VpnCriticalSectionEnter(&g_CsSetActiveProfileOperation);
  Flink = g_RasSetActiveList.Flink;
  if ( g_RasSetActiveList.Flink == &g_RasSetActiveList )
  {
    v5 = 0;
    v76 = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 619, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
  }
  else
  {
    if ( g_RasSetActiveList.Flink->Blink != &g_RasSetActiveList
      || (v6 = g_RasSetActiveList.Flink->Flink, g_RasSetActiveList.Flink->Flink->Blink != g_RasSetActiveList.Flink) )
    {
      __fastfail(3u);
    }
    v5 = g_RasSetActiveList.Flink - 2;
    g_RasSetActiveList.Flink = g_RasSetActiveList.Flink->Flink;
    v76 = Flink - 2;
    v6->Blink = &g_RasSetActiveList;
  }
  VpnCriticalSectionLeave(&g_CsSetActiveProfileOperation);
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( v5 )
  {
    v10 = v5->Flink;
    Blink = v5->Blink;
    v12 = (const WCHAR *)v5[1].Flink;
    v13 = (int)v5[1].Blink;
    Blink_high = HIDWORD(v5[1].Blink);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      v16 = L"<NULL>";
      v17 = L"<NULL>";
      if ( v12 )
        v16 = (const char *)v5[1].Flink;
      if ( Blink )
        v17 = (const char *)v5->Blink;
      WPP_SF_SSScc((TRACEHANDLE)WPP_GLOBAL_Control[1].Flink, (__int64)v17, (__int64)v16, v13 != 0, Blink_high != 0);
      v15 = WPP_GLOBAL_Control;
    }
    v18 = &g_ActiveUserProfile;
    if ( !Blink_high )
      v18 = &g_ActiveDeviceProfile;
    if ( !v13 )
    {
LABEL_56:
      if ( !v10 || !Blink || !v12 )
      {
        if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v15[1].Blink) & 1) != 0 )
          WPP_SF_(v15[1].Flink, 655, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        goto LABEL_262;
      }
      v28 = 1;
      if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v15[1].Blink) & 4) != 0 )
        WPP_SF_(v15[1].Flink, 626, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v29 = VpnProfileSetRasManServiceState(1, v7, v8, v9);
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 627, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v29);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v29,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6212,
            "int_SetActiveProfile");
      }
      if ( Blink_high )
      {
        if ( g_IsActiveUserProfile )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 628, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            v30 = WPP_GLOBAL_Control;
          }
          v31 = g_ActiveUserProfile;
          do
          {
            v32 = *(LPCWSTR)((char *)v31 + (char *)v10 - (char *)g_ActiveUserProfile);
            v33 = *v31 - v32;
            if ( v33 )
              break;
            ++v31;
          }
          while ( v32 );
          if ( v33 )
            goto LABEL_83;
          v34 = qword_18010DFD8;
          do
          {
            v35 = *(LPCWSTR)((char *)v34 + (char *)Blink - (char *)qword_18010DFD8);
            v36 = *v34 - v35;
            if ( v36 )
              break;
            ++v34;
          }
          while ( v35 );
          if ( v36 )
          {
LABEL_83:
            if ( v30 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v30[1].Blink) & 4) != 0 )
              WPP_SF_(v30[1].Flink, 629, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            VpnProfileDeActivateAutoTrigger(1, Blink_high, 7);
            VpnProfileActiveFree(&g_ActiveUserProfile);
            v30 = WPP_GLOBAL_Control;
            g_IsActiveUserProfile = 0;
          }
          else
          {
            v28 = 0;
          }
          if ( g_pNrptRuleListPersistentPrefixForUserTunnel )
          {
            v37 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel, 1);
            if ( !v37 )
              goto LABEL_121;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 630, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v37);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_121;
            v38 = 6238;
LABEL_120:
            TraceVpnWppErrorW32Impl(
              v37,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              v38,
              "int_SetActiveProfile");
LABEL_121:
            v30 = WPP_GLOBAL_Control;
            goto LABEL_122;
          }
          goto LABEL_122;
        }
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v40 = 631;
LABEL_137:
          WPP_SF_(v39[1].Flink, v40, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        }
      }
      else
      {
        if ( g_IsActiveDeviceProfile )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 632, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            v30 = WPP_GLOBAL_Control;
          }
          v41 = g_ActiveDeviceProfile;
          do
          {
            v42 = *(LPCWSTR)((char *)v41 + (char *)v10 - (char *)g_ActiveDeviceProfile);
            v43 = *v41 - v42;
            if ( v43 )
              break;
            ++v41;
          }
          while ( v42 );
          if ( v43 )
            goto LABEL_110;
          v44 = qword_18010E238;
          do
          {
            v45 = *(LPCWSTR)((char *)v44 + (char *)Blink - (char *)qword_18010E238);
            v46 = *v44 - v45;
            if ( v46 )
              break;
            ++v44;
          }
          while ( v45 );
          if ( v46 )
          {
LABEL_110:
            if ( v30 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v30[1].Blink) & 4) != 0 )
              WPP_SF_(v30[1].Flink, 633, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            VpnProfileDeActivateAutoTrigger(1, 0, 7);
            VpnProfileActiveFree(&g_ActiveDeviceProfile);
            v30 = WPP_GLOBAL_Control;
            g_IsActiveDeviceProfile = 0;
          }
          else
          {
            v28 = 0;
          }
          if ( g_pNrptRuleListPersistentPrefixForDeviceTunnel )
          {
            v37 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel, 1);
            if ( !v37 )
              goto LABEL_121;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 634, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v37);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_121;
            v38 = 6271;
            goto LABEL_120;
          }
LABEL_122:
          if ( !v28 )
          {
            if ( v30 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v30[1].Blink) & 4) != 0 )
            {
              WPP_SF_(v30[1].Flink, 644, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
              v30 = WPP_GLOBAL_Control;
            }
            if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
            {
              McTemplateU0z_EventWriteTransfer(v30, VpnAutoTriggerProfileModified, v18[1]);
              v30 = WPP_GLOBAL_Control;
            }
            if ( v30 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v30[1].Blink) & 4) != 0 )
              WPP_SF_SS(
                v30[1].Flink,
                645,
                (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)*v18,
                (__int64)v18[1]);
            v47 = (WCHAR *)v18[73];
            if ( v47 )
            {
              RtlFreeSid(v47);
              v18[73] = 0;
            }
            v48 = (_DWORD **)(v18 + 74);
            VpnProfileActiveSettingsFree((LPVOID)v18[74]);
            v18[74] = 0;
            *((_DWORD *)v18 + 6) = 0;
            goto LABEL_201;
          }
LABEL_141:
          if ( v30 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v30[1].Blink) & 4) != 0 )
            WPP_SF_(v30[1].Flink, 636, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          v49 = VpnStringCopy(v10);
          v50 = v49;
          if ( v49 < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                637,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)v49);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorHRImpl(
                (unsigned int)v50,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6285,
                "int_SetActiveProfile");
            v51 = (v50 >> 16) & 0x1FFF;
            if ( v51 == 7 ? (unsigned __int16)v50 : v50 )
            {
              if ( v51 == 7 )
                v50 = (unsigned __int16)v50;
              v53 = "VpnStringCopy for pProfilePhonebookPath ";
LABEL_157:
              VpnReportError("int_SetActiveProfile", v53, (unsigned int)v50);
LABEL_262:
              v5 = v76;
              goto LABEL_263;
            }
          }
          v54 = (__int64 *)(v18 + 1);
          v55 = VpnStringCopy(Blink);
          v50 = v55;
          if ( v55 < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                638,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)v55);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorHRImpl(
                (unsigned int)v50,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6289,
                "int_SetActiveProfile");
            v56 = (v50 >> 16) & 0x1FFF;
            if ( v56 == 7 ? (unsigned __int16)v50 : v50 )
            {
              if ( v56 == 7 )
                v50 = (unsigned __int16)v50;
              v53 = "VpnStringCopy for pProfileName";
              goto LABEL_157;
            }
          }
          if ( ConvertStringSidToSidW(v12, &Sid) )
          {
            v61 = VpnSidCopy(Sid);
            v59 = v61;
            if ( v61 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 641, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v61);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  v59,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6301,
                  "int_SetActiveProfile");
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 642, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v59);
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                goto LABEL_262;
              v60 = 6302;
LABEL_183:
              TraceVpnWppErrorW32Impl(
                v59,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                v60,
                "int_SetActiveProfile");
              goto LABEL_262;
            }
          }
          else
          {
            LastError = GetLastError();
            v59 = LastError;
            if ( LastError )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 639, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  v59,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6295,
                  "int_SetActiveProfile");
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 640, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v59);
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                goto LABEL_262;
              v60 = 6296;
              goto LABEL_183;
            }
          }
          v62 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_SS(
              WPP_GLOBAL_Control[1].Flink,
              643,
              (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              (unsigned int)*v18,
              *v54);
          }
          if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(v62, VpnAutoTriggerProfileAdded, *v54);
          v48 = (_DWORD **)(v18 + 74);
LABEL_201:
          v63 = VpnProfileActiveSettingsGet(*v18, v18[1]);
          v59 = v63;
          if ( v63 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 646, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v63);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_262;
            v60 = 6335;
            goto LABEL_183;
          }
          if ( (*v48)[33] )
          {
            LockdownNciNrptRule = int_VpnCreateLockdownNciNrptRule((unsigned __int16 *)v18[1]);
            v59 = LockdownNciNrptRule;
            if ( LockdownNciNrptRule )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  647,
                  &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                  LockdownNciNrptRule);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  v59,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6344,
                  "int_SetActiveProfile");
              v59 = 0;
            }
          }
          if ( Blink_high )
          {
            ActiveTokenAndSessionId = GetActiveTokenAndSessionId((void *)v18[2], &v78, 0);
            v3 = v78;
            v59 = ActiveTokenAndSessionId;
          }
          if ( v59 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 653, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v59);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v59,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6419,
                "int_SetActiveProfile");
LABEL_254:
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 654, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v59);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_262;
            v60 = 6424;
            goto LABEL_183;
          }
          v67 = RasAddNrptRulesEx(*((_QWORD *)*v48 + 1), **v48, v64, 0, 1, 0);
          v70 = v67;
          if ( v67 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 648, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v67);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v70,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6365,
                "int_SetActiveProfile");
          }
          *((_DWORD *)v18 + 6) = v3;
          if ( Blink_high )
          {
            g_IsActiveUserProfile = 1;
            v71 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              v72 = 649;
LABEL_231:
              WPP_SF_(v71[1].Flink, v72, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            }
          }
          else
          {
            g_IsActiveDeviceProfile = 1;
            v71 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              v72 = 650;
              goto LABEL_231;
            }
          }
          v73 = VpnProfileActivateAutoTrigger((__int64)v18, Blink_high, v68, v69);
          v59 = v73;
          if ( v73 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 651, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v73);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v59,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6386,
                "int_SetActiveProfile");
            v59 = 0;
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 652, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          }
          VpnCriticalSectionEnter(&g_CsLogicalConnection);
          v74 = g_fIsDeviceTunnelAllowed;
          VpnCriticalSectionLeave(&g_CsLogicalConnection);
          if ( Blink_high || v74 )
          {
            AddVPNTriggerEvent(7, Blink_high);
            v75 = g_pReConnectUserTunnelWorkItem;
            if ( !Blink_high )
              v75 = g_pReConnectDeviceTunnelWorkItem;
            SubmitThreadpoolWork(v75);
          }
          if ( !v59 )
            goto LABEL_262;
          goto LABEL_254;
        }
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v40 = 635;
          goto LABEL_137;
        }
      }
      if ( (unsigned int)IsDefaultTracingEnabled() )
        EnableAutoWPPTracingForSubComponent(0);
      v30 = WPP_GLOBAL_Control;
      goto LABEL_141;
    }
    if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v15[1].Blink) & 4) != 0 )
      WPP_SF_(v15[1].Flink, 622, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(v15, VpnAutoTriggerProfileDeleted, v18[1]);
    VpnProfileDeActivateAutoTrigger(1, Blink_high, 7);
    VpnProfileActiveFree(v18);
    if ( Blink_high )
      g_IsActiveUserProfile = 0;
    else
      g_IsActiveDeviceProfile = 0;
    DisableAutoWPPTracingForSubComponent(0);
    if ( Blink_high )
    {
      if ( !g_pNrptRuleListPersistentPrefixForUserTunnel )
        goto LABEL_49;
      v22 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel, 1);
      v23 = v22;
      if ( !v22 )
        goto LABEL_49;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 623, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v22);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_49;
      v24 = 6188;
    }
    else
    {
      if ( !g_pNrptRuleListPersistentPrefixForDeviceTunnel )
        goto LABEL_49;
      v25 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel, 1);
      v23 = v25;
      if ( !v25 )
        goto LABEL_49;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 624, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v25);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_49;
      v24 = 6196;
    }
    TraceVpnWppErrorW32Impl(
      v23,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v24,
      "int_SetActiveProfile");
LABEL_49:
    v26 = VpnProfileSetRasManServiceState(0, v19, v20, v21);
    v27 = v26;
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 625, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v26);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v27,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6204,
          "int_SetActiveProfile");
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 620, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
LABEL_263:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  FreeSetProfileContext((struct _SET_ACTIVE_PROFILE_WORK_CONTEXT *)v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 656, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
}

```

## disassembly

```asm
0x1800d4f20  push    rbx
0x1800d4f22  push    rbp
0x1800d4f23  push    rsi
0x1800d4f24  push    rdi
0x1800d4f25  push    r12
0x1800d4f27  push    r13
0x1800d4f29  push    r14
0x1800d4f2b  push    r15
0x1800d4f2d  sub     rsp, 58h
0x1800d4f31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4f38  lea     rbp, WPP_GLOBAL_Control
0x1800d4f3f  cmp     rcx, rbp
0x1800d4f42  jz      short loc_1800D4F5F
0x1800d4f44  test    byte ptr [rcx+1Ch], 8
0x1800d4f48  jz      short loc_1800D4F5F
0x1800d4f4a  mov     rcx, [rcx+10h]
0x1800d4f4e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4f55  mov     edx, 26Ah
0x1800d4f5a  call    WPP_SF_
0x1800d4f5f  xor     r13d, r13d
0x1800d4f62  mov     [rsp+98h+Sid], 0
0x1800d4f6b  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d4f72  mov     [rsp+98h+arg_18], r13d
0x1800d4f7a  call    VpnCriticalSectionEnter
0x1800d4f7f  mov     rax, cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d4f86  lea     rcx, ?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d4f8d  cmp     rax, rcx
0x1800d4f90  jnz     short loc_1800D4FC2
0x1800d4f92  xor     esi, esi
0x1800d4f94  mov     [rsp+98h+var_58], rsi
0x1800d4f99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4fa0  cmp     rcx, rbp
0x1800d4fa3  jz      short loc_1800D4FED
0x1800d4fa5  test    byte ptr [rcx+1Ch], 1
0x1800d4fa9  jz      short loc_1800D4FED
0x1800d4fab  mov     rcx, [rcx+10h]
0x1800d4faf  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4fb6  mov     edx, 26Bh
0x1800d4fbb  call    WPP_SF_
0x1800d4fc0  jmp     short loc_1800D4FED
0x1800d4fc2  cmp     [rax+8], rcx
0x1800d4fc6  jnz     loc_1800D5E6C
0x1800d4fcc  mov     rdx, [rax]
0x1800d4fcf  cmp     [rdx+8], rax
0x1800d4fd3  jnz     loc_1800D5E6C
0x1800d4fd9  lea     rsi, [rax-20h]
0x1800d4fdd  mov     cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A, rdx; _LIST_ENTRY g_RasSetActiveList
0x1800d4fe4  mov     [rsp+98h+var_58], rsi
0x1800d4fe9  mov     [rdx+8], rcx
0x1800d4fed  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d4ff4  call    VpnCriticalSectionLeave
0x1800d4ff9  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800d5000  call    VpnCriticalSectionEnter
0x1800d5005  test    rsi, rsi
0x1800d5008  jnz     short loc_1800D503E
0x1800d500a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5011  cmp     rcx, rbp
0x1800d5014  jz      loc_1800D5E07
0x1800d501a  test    byte ptr [rcx+1Ch], 1
0x1800d501e  jz      loc_1800D5E07
0x1800d5024  mov     rcx, [rcx+10h]
0x1800d5028  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d502f  mov     edx, 26Ch
0x1800d5034  call    WPP_SF_
0x1800d5039  jmp     loc_1800D5E07
0x1800d503e  mov     rbp, [rsi]
0x1800d5041  mov     r14, [rsi+8]
0x1800d5045  mov     r12, [rsi+10h]
0x1800d5049  mov     ebx, [rsi+18h]
0x1800d504c  mov     r15d, [rsi+1Ch]
0x1800d5050  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5057  lea     rdi, WPP_GLOBAL_Control
0x1800d505e  cmp     rcx, rdi
0x1800d5061  jz      short loc_1800D50C1
0x1800d5063  test    byte ptr [rcx+1Ch], 4
0x1800d5067  jz      short loc_1800D50C1
0x1800d5069  mov     rcx, [rcx+10h]; LoggerHandle
0x1800d506d  lea     r9, aNull_5; "<NULL>"
0x1800d5074  test    r15d, r15d
0x1800d5077  mov     r8, r9
0x1800d507a  mov     rax, r9
0x1800d507d  mov     edx, 26Dh
0x1800d5082  setnz   r11b
0x1800d5086  test    ebx, ebx
0x1800d5088  mov     [rsp+98h+var_60], r11b; char
0x1800d508d  setnz   r10b
0x1800d5091  test    r12, r12
0x1800d5094  mov     [rsp+98h+var_68], r10b; char
0x1800d5099  cmovnz  r8, r12
0x1800d509d  test    r14, r14
0x1800d50a0  mov     [rsp+98h+var_70], r8; __int64
0x1800d50a5  cmovnz  rax, r14
0x1800d50a9  test    rbp, rbp
0x1800d50ac  mov     [rsp+98h+var_78], rax; __int64
0x1800d50b1  cmovnz  r9, rbp
0x1800d50b5  call    WPP_SF_SSScc
0x1800d50ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d50c1  test    r15d, r15d
0x1800d50c4  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d50cb  lea     rsi, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d50d2  cmovz   rsi, rax
0x1800d50d6  test    ebx, ebx
0x1800d50d8  jz      loc_1800D528E
0x1800d50de  cmp     rcx, rdi
0x1800d50e1  jz      short loc_1800D50FE
0x1800d50e3  test    byte ptr [rcx+1Ch], 4
0x1800d50e7  jz      short loc_1800D50FE
0x1800d50e9  mov     rcx, [rcx+10h]
0x1800d50ed  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d50f4  mov     edx, 26Eh
0x1800d50f9  call    WPP_SF_
0x1800d50fe  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800d5105  jz      short loc_1800D5117
0x1800d5107  mov     r8, [rsi+8]
0x1800d510b  lea     rdx, VpnAutoTriggerProfileDeleted
0x1800d5112  call    McTemplateU0z_EventWriteTransfer
0x1800d5117  mov     r8d, 7
0x1800d511d  mov     edx, r15d
0x1800d5120  lea     ebx, [r8-6]
0x1800d5124  mov     ecx, ebx
0x1800d5126  call    VpnProfileDeActivateAutoTrigger
0x1800d512b  mov     rcx, rsi
0x1800d512e  call    VpnProfileActiveFree
0x1800d5133  test    r15d, r15d
0x1800d5136  jz      short loc_1800D5141
0x1800d5138  mov     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d513f  jmp     short loc_1800D5148
0x1800d5141  mov     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800d5148  xor     ecx, ecx
0x1800d514a  call    DisableAutoWPPTracingForSubComponent
0x1800d514f  test    r15d, r15d
0x1800d5152  jz      short loc_1800D51B7
0x1800d5154  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForUserTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForUserTunnel
0x1800d515b  test    rcx, rcx
0x1800d515e  jz      loc_1800D5225
0x1800d5164  mov     edx, ebx
0x1800d5166  call    RasRemoveNrptRules
0x1800d516b  mov     ebx, eax
0x1800d516d  test    eax, eax
0x1800d516f  jz      loc_1800D5225
0x1800d5175  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d517c  cmp     rcx, rdi
0x1800d517f  jz      short loc_1800D519F
0x1800d5181  test    byte ptr [rcx+1Ch], 1
0x1800d5185  jz      short loc_1800D519F
0x1800d5187  mov     rcx, [rcx+10h]
0x1800d518b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d5192  mov     edx, 26Fh
0x1800d5197  mov     r9d, eax
0x1800d519a  call    WPP_SF_d
0x1800d519f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d51a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d51ab  test    al, al
0x1800d51ad  jz      short loc_1800D5225
0x1800d51af  mov     r8d, 182Ch
0x1800d51b5  jmp     short loc_1800D5210
0x1800d51b7  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForDeviceTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForDeviceTunnel
0x1800d51be  test    rcx, rcx
0x1800d51c1  jz      short loc_1800D5225
0x1800d51c3  mov     edx, ebx
0x1800d51c5  call    RasRemoveNrptRules
0x1800d51ca  mov     ebx, eax
0x1800d51cc  test    eax, eax
0x1800d51ce  jz      short loc_1800D5225
0x1800d51d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d51d7  cmp     rcx, rdi
0x1800d51da  jz      short loc_1800D51FA
0x1800d51dc  test    byte ptr [rcx+1Ch], 1
0x1800d51e0  jz      short loc_1800D51FA
0x1800d51e2  mov     rcx, [rcx+10h]
0x1800d51e6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d51ed  mov     edx, 270h
0x1800d51f2  mov     r9d, eax
0x1800d51f5  call    WPP_SF_d
0x1800d51fa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d5201  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5206  test    al, al
0x1800d5208  jz      short loc_1800D5225
0x1800d520a  mov     r8d, 1834h
0x1800d5210  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d5217  mov     ecx, ebx
0x1800d5219  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5220  call    TraceVpnWppErrorW32Impl
0x1800d5225  xor     ecx, ecx
0x1800d5227  call    VpnProfileSetRasManServiceState
0x1800d522c  mov     ebx, eax
0x1800d522e  test    eax, eax
0x1800d5230  jz      short loc_1800D5287
0x1800d5232  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5239  cmp     rcx, rdi
0x1800d523c  jz      short loc_1800D525C
0x1800d523e  test    byte ptr [rcx+1Ch], 1
0x1800d5242  jz      short loc_1800D525C
0x1800d5244  mov     rcx, [rcx+10h]
0x1800d5248  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d524f  mov     edx, 271h
0x1800d5254  mov     r9d, eax
0x1800d5257  call    WPP_SF_d
0x1800d525c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d5263  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5268  test    al, al
0x1800d526a  jz      short loc_1800D5287
0x1800d526c  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d5273  mov     r8d, 183Ch
0x1800d5279  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5280  mov     ecx, ebx
0x1800d5282  call    TraceVpnWppErrorW32Impl
0x1800d5287  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d528e  test    rbp, rbp
0x1800d5291  jz      loc_1800D5DDB
0x1800d5297  test    r14, r14
0x1800d529a  jz      loc_1800D5DDB
0x1800d52a0  test    r12, r12
0x1800d52a3  jz      loc_1800D5DDB
0x1800d52a9  mov     ebx, 1
0x1800d52ae  mov     edi, ebx
0x1800d52b0  lea     rax, WPP_GLOBAL_Control
0x1800d52b7  cmp     rcx, rax
0x1800d52ba  jz      short loc_1800D52D7
0x1800d52bc  test    byte ptr [rcx+1Ch], 4
0x1800d52c0  jz      short loc_1800D52D7
0x1800d52c2  mov     rcx, [rcx+10h]
0x1800d52c6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d52cd  mov     edx, 272h
0x1800d52d2  call    WPP_SF_
0x1800d52d7  mov     ecx, ebx
0x1800d52d9  call    VpnProfileSetRasManServiceState
0x1800d52de  mov     ebx, eax
0x1800d52e0  test    eax, eax
0x1800d52e2  jz      short loc_1800D5340
0x1800d52e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d52eb  lea     rax, WPP_GLOBAL_Control
0x1800d52f2  cmp     rcx, rax
0x1800d52f5  jz      short loc_1800D5315
0x1800d52f7  test    [rcx+1Ch], dil
0x1800d52fb  jz      short loc_1800D5315
0x1800d52fd  mov     rcx, [rcx+10h]
0x1800d5301  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d5308  mov     edx, 273h
0x1800d530d  mov     r9d, ebx
0x1800d5310  call    WPP_SF_d
0x1800d5315  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d531c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5321  test    al, al
0x1800d5323  jz      short loc_1800D5340
0x1800d5325  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d532c  mov     r8d, 1844h
0x1800d5332  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5339  mov     ecx, ebx
0x1800d533b  call    TraceVpnWppErrorW32Impl
0x1800d5340  test    r15d, r15d
0x1800d5343  jz      loc_1800D54CB
0x1800d5349  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d5350  jz      loc_1800D54A0
0x1800d5356  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d535d  lea     rbx, WPP_GLOBAL_Control
0x1800d5364  cmp     rcx, rbx
0x1800d5367  jz      short loc_1800D538B
0x1800d5369  test    byte ptr [rcx+1Ch], 4
0x1800d536d  jz      short loc_1800D538B
0x1800d536f  mov     rcx, [rcx+10h]
0x1800d5373  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d537a  mov     edx, 274h
0x1800d537f  call    WPP_SF_
0x1800d5384  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d538b  mov     rax, cs:?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d5392  mov     r9, rbp
0x1800d5395  sub     r9, rax
0x1800d5398  movzx   r8d, word ptr [rax]
0x1800d539c  movzx   edx, word ptr [rax+r9]
0x1800d53a1  sub     r8d, edx
0x1800d53a4  jnz     short loc_1800D53AE
0x1800d53a6  add     rax, 2
0x1800d53aa  test    edx, edx
0x1800d53ac  jnz     short loc_1800D5398
0x1800d53ae  test    r8d, r8d
0x1800d53b1  jnz     short loc_1800D53DF
0x1800d53b3  mov     rax, cs:qword_18010DFD8
0x1800d53ba  mov     r9, r14
0x1800d53bd  sub     r9, rax
0x1800d53c0  movzx   r8d, word ptr [rax]
0x1800d53c4  movzx   edx, word ptr [rax+r9]
0x1800d53c9  sub     r8d, edx
0x1800d53cc  jnz     short loc_1800D53D6
0x1800d53ce  add     rax, 2
0x1800d53d2  test    edx, edx
0x1800d53d4  jnz     short loc_1800D53C0
0x1800d53d6  test    r8d, r8d
0x1800d53d9  jnz     short loc_1800D53DF
0x1800d53db  xor     edi, edi
0x1800d53dd  jmp     short loc_1800D5429
0x1800d53df  cmp     rcx, rbx
0x1800d53e2  jz      short loc_1800D53FF
0x1800d53e4  test    byte ptr [rcx+1Ch], 4
0x1800d53e8  jz      short loc_1800D53FF
0x1800d53ea  mov     rcx, [rcx+10h]
0x1800d53ee  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d53f5  mov     edx, 275h
0x1800d53fa  call    WPP_SF_
0x1800d53ff  mov     r8d, 7
  ... truncated ...
```
