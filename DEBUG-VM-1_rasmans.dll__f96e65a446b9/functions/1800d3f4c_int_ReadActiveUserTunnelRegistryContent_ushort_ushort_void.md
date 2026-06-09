# int_ReadActiveUserTunnelRegistryContent(ushort * *,ushort * *,void * *)

- ea: `0x1800d3f4c`
- end: `0x1800d49b9`
- name: `?int_ReadActiveUserTunnelRegistryContent@@YAKPEAPEAG0PEAPEAX@Z`
- size: `2669`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c945c`
- `0x1800de2d8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800c0bf0`
- `0x1800d3f4c`
- `0x1800dab4c`
- `0x1800e0a54`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e218c`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7260`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d3fd1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d409d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d3fd1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d409d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d466d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d466d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4808`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d41ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d4324`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d4445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d452c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d41ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d4324`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d4445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d452c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d4007`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d4007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d48c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d48c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4752`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d48f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4752`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d48f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d4663`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d4663`

## string_xrefs

- `0x1800d3fe6`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800d3fd7`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800d404f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d411a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d41d0`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d4216`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d41ac`: `AutoTriggerProfilePhoneBookPath`
- `0x1800d46d0`: `ConvertStringSidToSid`
- `0x1800d4742`: `VpnSidCopy`
- `0x1800d4070`: `RegOpenKeyEx`
- `0x1800d42f1`: `FixAutoTriggerProfilePath`
- `0x1800d4048`: `int_ReadActiveUserTunnelRegistryContent`
- `0x1800d4113`: `int_ReadActiveUserTunnelRegistryContent`
- `0x1800d41c9`: `int_ReadActiveUserTunnelRegistryContent`
- `0x1800d420f`: `int_ReadActiveUserTunnelRegistryContent`
- `0x1800d43da`: `VpnStringCopy for profile name`
- `0x1800d4437`: `UserSID`
- `0x1800d4525`: `UserSID`
- `0x1800d429a`: `VpnStringCopy for profile path`

## pseudocode

```c
__int64 __fastcall int_ReadActiveUserTunnelRegistryContent(LPVOID *a1, unsigned __int16 **a2, void **a3)
{
  struct _LIST_ENTRY *v4; // rcx
  BYTE *v5; // r12
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rbx
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // r8
  const char *v13; // rdx
  BYTE *v14; // rax
  __int64 v15; // r8
  int v16; // ebx
  int v17; // eax
  unsigned int fixed; // eax
  int v20; // ebx
  int v21; // eax
  unsigned __int16 *v23; // rbx
  LSTATUS v24; // eax
  unsigned int v25; // eax
  DWORD v26; // eax
  unsigned int v27; // eax
  void *v28; // rbx
  DWORD v29; // ebx
  DWORD LastError; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  PSID v33; // rcx
  __int64 v34; // r8
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v37; // [rsp+38h] [rbp-41h] BYREF
  DWORD Type; // [rsp+40h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-31h] BYREF
  PSID Sid; // [rsp+50h] [rbp-29h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-21h]
  LPVOID v42; // [rsp+60h] [rbp-19h]
  unsigned __int16 **v43; // [rsp+68h] [rbp-11h]
  void **v44; // [rsp+70h] [rbp-9h]
  _BYTE v45[16]; // [rsp+78h] [rbp-1h] BYREF
  LPVOID *v46; // [rsp+88h] [rbp+Fh]
  __int64 v47; // [rsp+90h] [rbp+17h]

  v44 = a3;
  v43 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 124, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  v5 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  Sid = 0;
  lpMem = 0;
  v42 = 0;
  v37 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v4);
  v7 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v8 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !IsStateSeparationEnabled )
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20017u, &hKey);
  v11 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 125, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v11,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1382,
        "int_ReadActiveUserTunnelRegistryContent");
    v12 = v11;
    v13 = "RegOpenKeyEx";
    goto LABEL_134;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v10) )
      v7 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 126, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v7);
  }
  cbData = 522;
  v14 = (BYTE *)((__int64 (*)(void))VpnAlloc)();
  v5 = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1393,
        "int_ReadActiveUserTunnelRegistryContent");
    v11 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 128, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_135;
    v15 = 1395;
    goto LABEL_29;
  }
  cbData = 520;
  v11 = RegQueryValueExW(hKey, L"AutoTriggerProfilePhoneBookPath", 0, &Type, v14, &cbData);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v29 = Type;
      LastError = GetLastError();
      WPP_SF_DDD(WPP_GLOBAL_Control[1].Flink, v31, v32, LastError, v29, v11);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v11,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1402,
        "int_ReadActiveUserTunnelRegistryContent");
    goto LABEL_126;
  }
  if ( Type - 1 > 1 )
  {
LABEL_126:
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 130, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        1168,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1404,
        "int_ReadActiveUserTunnelRegistryContent");
    v11 = 1168;
    goto LABEL_132;
  }
  *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v16 = VpnStringCopy(v5);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 131, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v16);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        (unsigned int)v16,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1411,
        "int_ReadActiveUserTunnelRegistryContent");
    v17 = (v16 >> 16) & 0x1FFF;
    if ( v17 == 7 ? (unsigned __int16)v16 : v16 )
    {
      if ( v17 == 7 )
        v16 = (unsigned __int16)v16;
      v13 = "VpnStringCopy for profile path";
      v12 = (unsigned int)v16;
      goto LABEL_134;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 132, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, lpMem);
  fixed = FixAutoTriggerProfilePath(hKey);
  v11 = fixed;
  if ( fixed )
  {
    v12 = fixed;
    v13 = "FixAutoTriggerProfilePath";
    goto LABEL_134;
  }
  cbData = 520;
  v11 = RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, v5, &cbData);
  if ( v11 || Type - 1 > 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 133, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        1168,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1426,
        "int_ReadActiveUserTunnelRegistryContent");
    v11 = 1168;
    v13 = "RegQueryValueEx for REG_VAL_PROFILE_NAME";
    v12 = 1168;
    goto LABEL_134;
  }
  *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v20 = VpnStringCopy(v5);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 134, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v20);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        (unsigned int)v20,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1434,
        "int_ReadActiveUserTunnelRegistryContent");
    v21 = (v20 >> 16) & 0x1FFF;
    if ( v21 == 7 ? (unsigned __int16)v20 : v20 )
    {
      if ( v21 == 7 )
        v20 = (unsigned __int16)v20;
      v13 = "VpnStringCopy for profile name";
      v12 = (unsigned int)v20;
      goto LABEL_134;
    }
  }
  v23 = (unsigned __int16 *)v42;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 135, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v42);
  cbData = 520;
  v24 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v5, &cbData);
  if ( v24 != 234 )
  {
    if ( !v24 && Type - 1 <= 1 )
      goto LABEL_94;
    v11 = 1168;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        1168,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1463,
        "int_ReadActiveUserTunnelRegistryContent");
LABEL_132:
    v12 = 1168;
LABEL_133:
    v13 = "RegQueryValueEx";
    goto LABEL_134;
  }
  MprCommonFree(v5);
  v5 = (BYTE *)VpnAlloc(cbData + 1);
  if ( v5 )
  {
    v25 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v5, &cbData);
    v11 = v25;
    if ( v25 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 138, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v25);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v11,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          1457,
          "int_ReadActiveUserTunnelRegistryContent");
      v12 = v11;
      goto LABEL_133;
    }
LABEL_94:
    if ( cbData > 1 )
    {
      *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1)] = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 140, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v5);
      }
      if ( ConvertStringSidToSidW((LPCWSTR)v5, &Sid) )
      {
        v27 = VpnSidCopy(Sid);
        v11 = v27;
        if ( v27 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 142, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v27);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              v11,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1489,
              "int_ReadActiveUserTunnelRegistryContent");
          v12 = v11;
          v13 = "VpnSidCopy";
          goto LABEL_134;
        }
      }
      else
      {
        v26 = GetLastError();
        v11 = v26;
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 141, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v26);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              v11,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1483,
              "int_ReadActiveUserTunnelRegistryContent");
          v12 = v11;
          v13 = "ConvertStringSidToSid";
          goto LABEL_134;
        }
      }
      LocalFree(Sid);
      *a1 = lpMem;
      Sid = 0;
      *v43 = v23;
      v28 = v37;
      *v44 = v37;
      goto LABEL_136;
    }
    v13 = "RegQueryValueEx";
    v11 = 1168;
    v12 = 1168;
LABEL_134:
    VpnReportError("int_ReadActiveUserTunnelRegistryContent", v13, v12);
    goto LABEL_135;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 136, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      1452,
      "int_ReadActiveUserTunnelRegistryContent");
  v11 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 137, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    goto LABEL_135;
  v15 = 1454;
LABEL_29:
  TraceVpnWppErrorW32Impl(
    14,
    L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
    v15,
    "int_ReadActiveUserTunnelRegistryContent");
LABEL_135:
  v28 = v37;
LABEL_136:
  if ( hKey )
    RegCloseKey(hKey);
  MprCommonFree(v5);
  if ( v11 )
  {
    MprCommonFree(lpMem);
    MprCommonFree(v42);
    MprCommonFree(v28);
    v33 = Sid;
    if ( Sid )
    {
      LocalFree(Sid);
      Sid = 0;
    }
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    LODWORD(v37) = v11;
    v46 = &v37;
    v47 = 4;
    McGenEventWrite_EventWriteTransfer(v33, VpnAutoTriggerReadConfigRegistryContent, v34, 2, v45);
  }
  g_fConfigUserRegContentFailed = v11 != 0;
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 143, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v11);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v11,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1534,
        "int_ReadActiveUserTunnelRegistryContent");
  }
  return v11;
}

```

## disassembly

```asm
0x1800d3f4c  mov     [rsp-8+arg_18], rbx
0x1800d3f51  push    rbp
0x1800d3f52  push    rsi
0x1800d3f53  push    rdi
0x1800d3f54  push    r12
0x1800d3f56  push    r13
0x1800d3f58  push    r14
0x1800d3f5a  push    r15
0x1800d3f5c  lea     rbp, [rsp-27h]
0x1800d3f61  sub     rsp, 0A0h
0x1800d3f68  mov     rax, cs:__security_cookie
0x1800d3f6f  xor     rax, rsp
0x1800d3f72  mov     [rbp+57h+var_38], rax
0x1800d3f76  mov     [rbp+57h+var_60], r8
0x1800d3f7a  mov     r13, rcx
0x1800d3f7d  mov     [rbp+57h+var_68], rdx
0x1800d3f81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3f88  lea     rsi, WPP_GLOBAL_Control
0x1800d3f8f  lea     r15, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d3f96  cmp     rcx, rsi
0x1800d3f99  jz      short loc_1800D3FB2
0x1800d3f9b  test    byte ptr [rcx+1Ch], 8
0x1800d3f9f  jz      short loc_1800D3FB2
0x1800d3fa1  mov     rcx, [rcx+10h]
0x1800d3fa5  mov     edx, 7Ch ; '|'
0x1800d3faa  mov     r8, r15
0x1800d3fad  call    WPP_SF_
0x1800d3fb2  xor     r12d, r12d
0x1800d3fb5  mov     [rbp+57h+hKey], r12
0x1800d3fb9  mov     [rbp+57h+cbData], r12d
0x1800d3fbd  mov     [rbp+57h+Type], r12d
0x1800d3fc1  mov     [rbp+57h+Sid], r12
0x1800d3fc5  mov     [rbp+57h+lpMem], r12
0x1800d3fc9  mov     [rbp+57h+var_70], r12
0x1800d3fcd  mov     [rbp+57h+var_98], r12
0x1800d3fd1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d3fd7  lea     rbx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800d3fde  mov     r9d, 20017h; samDesired
0x1800d3fe4  test    al, al
0x1800d3fe6  lea     r14, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800d3fed  lea     rax, [rbp+57h+hKey]
0x1800d3ff1  mov     rdx, rbx
0x1800d3ff4  cmovz   rdx, r14; lpSubKey
0x1800d3ff8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800d3ffd  xor     r8d, r8d; ulOptions
0x1800d4000  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d4007  call    cs:__imp_RegOpenKeyExW
0x1800d400d  mov     edi, eax
0x1800d400f  test    eax, eax
0x1800d4011  jz      short loc_1800D408B
0x1800d4013  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d401a  cmp     rcx, rsi
0x1800d401d  jz      short loc_1800D4039
0x1800d401f  test    byte ptr [rcx+1Ch], 1
0x1800d4023  jz      short loc_1800D4039
0x1800d4025  mov     rcx, [rcx+10h]
0x1800d4029  lea     edx, [r12+7Dh]
0x1800d402e  mov     r9d, eax
0x1800d4031  mov     r8, r15
0x1800d4034  call    WPP_SF_d
0x1800d4039  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d4040  mov     rcx, r14
0x1800d4043  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d4048  lea     rsi, aIntReadactiveu; "int_ReadActiveUserTunnelRegistryContent"
0x1800d404f  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d4056  test    al, al
0x1800d4058  jz      short loc_1800D406D
0x1800d405a  mov     r9, rsi
0x1800d405d  mov     r8d, 566h
0x1800d4063  mov     rdx, r15
0x1800d4066  mov     ecx, edi
0x1800d4068  call    TraceVpnWppErrorW32Impl
0x1800d406d  mov     r8d, edi
0x1800d4070  lea     rdx, aRegopenkeyex; "RegOpenKeyEx"
0x1800d4077  mov     rcx, rsi
0x1800d407a  call    VpnReportError
0x1800d407f  lea     r13, WPP_GLOBAL_Control
0x1800d4086  jmp     loc_1800D48B3
0x1800d408b  mov     rax, cs:WPP_GLOBAL_Control
0x1800d4092  cmp     rax, rsi
0x1800d4095  jz      short loc_1800D40C4
0x1800d4097  test    byte ptr [rax+1Ch], 4
0x1800d409b  jz      short loc_1800D40C4
0x1800d409d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d40a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d40aa  mov     edx, 7Eh ; '~'
0x1800d40af  test    al, al
0x1800d40b1  mov     r8, r15
0x1800d40b4  cmovz   rbx, r14
0x1800d40b8  mov     rcx, [rcx+10h]
0x1800d40bc  mov     r9, rbx
0x1800d40bf  call    WPP_SF_S
0x1800d40c4  mov     ecx, 20Ah
0x1800d40c9  mov     [rbp+57h+cbData], ecx
0x1800d40cc  call    VpnAlloc
0x1800d40d1  mov     r12, rax
0x1800d40d4  test    rax, rax
0x1800d40d7  jnz     loc_1800D4193
0x1800d40dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d40e4  lea     ebx, [rax+0Eh]
0x1800d40e7  cmp     rcx, rsi
0x1800d40ea  jz      short loc_1800D4104
0x1800d40ec  test    byte ptr [rcx+1Ch], 1
0x1800d40f0  jz      short loc_1800D4104
0x1800d40f2  mov     rcx, [rcx+10h]
0x1800d40f6  lea     edx, [rax+7Fh]
0x1800d40f9  mov     r9d, ebx
0x1800d40fc  mov     r8, r15
0x1800d40ff  call    WPP_SF_d
0x1800d4104  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d410b  mov     rcx, r14
0x1800d410e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d4113  lea     rsi, aIntReadactiveu; "int_ReadActiveUserTunnelRegistryContent"
0x1800d411a  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d4121  test    al, al
0x1800d4123  jz      short loc_1800D4138
0x1800d4125  mov     r9, rsi
0x1800d4128  mov     r8d, 571h
0x1800d412e  mov     rdx, r15
0x1800d4131  mov     ecx, ebx
0x1800d4133  call    TraceVpnWppErrorW32Impl
0x1800d4138  mov     edi, ebx
0x1800d413a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4141  lea     r13, WPP_GLOBAL_Control
0x1800d4148  cmp     rcx, r13
0x1800d414b  jz      short loc_1800D416B
0x1800d414d  test    byte ptr [rcx+1Ch], 1
0x1800d4151  jz      short loc_1800D416B
0x1800d4153  mov     rcx, [rcx+10h]
0x1800d4157  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d415e  mov     edx, 80h
0x1800d4163  mov     r9d, ebx
0x1800d4166  call    WPP_SF_d
0x1800d416b  mov     rcx, r14
0x1800d416e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d4173  test    al, al
0x1800d4175  jz      loc_1800D48B3
0x1800d417b  mov     r8d, 573h
0x1800d4181  mov     r9, rsi
0x1800d4184  mov     rdx, r15
0x1800d4187  mov     ecx, ebx
0x1800d4189  call    TraceVpnWppErrorW32Impl
0x1800d418e  jmp     loc_1800D48B3
0x1800d4193  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d4197  lea     rax, [rbp+57h+cbData]
0x1800d419b  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d41a0  lea     r9, [rbp+57h+Type]; lpType
0x1800d41a4  xor     r8d, r8d; lpReserved
0x1800d41a7  mov     [rsp+0D0h+phkResult], r12; lpData
0x1800d41ac  lea     rdx, aAutotriggerpro_0; "AutoTriggerProfilePhoneBookPath"
0x1800d41b3  mov     [rbp+57h+cbData], 208h
0x1800d41ba  call    cs:__imp_RegQueryValueExW
0x1800d41c0  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d41c7  mov     edi, eax
0x1800d41c9  lea     rsi, aIntReadactiveu; "int_ReadActiveUserTunnelRegistryContent"
0x1800d41d0  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d41d7  test    eax, eax
0x1800d41d9  jnz     loc_1800D47EC
0x1800d41df  mov     eax, [rbp+57h+Type]
0x1800d41e2  dec     eax
0x1800d41e4  cmp     eax, 1
0x1800d41e7  ja      loc_1800D484A
0x1800d41ed  mov     ecx, [rbp+57h+cbData]
0x1800d41f0  lea     rdx, [rbp+57h+lpMem]
0x1800d41f4  shr     rcx, 1
0x1800d41f7  xor     eax, eax
0x1800d41f9  mov     [r12+rcx*2], ax
0x1800d41fe  mov     rcx, r12; Src
0x1800d4201  call    VpnStringCopy
0x1800d4206  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d420d  mov     ebx, eax
0x1800d420f  lea     rsi, aIntReadactiveu; "int_ReadActiveUserTunnelRegistryContent"
0x1800d4216  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d421d  test    eax, eax
0x1800d421f  jns     loc_1800D42A9
0x1800d4225  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d422c  lea     rax, WPP_GLOBAL_Control
0x1800d4233  cmp     rcx, rax
0x1800d4236  jz      short loc_1800D4256
0x1800d4238  test    byte ptr [rcx+1Ch], 1
0x1800d423c  jz      short loc_1800D4256
0x1800d423e  mov     rcx, [rcx+10h]
0x1800d4242  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4249  mov     edx, 83h
0x1800d424e  mov     r9d, ebx
0x1800d4251  call    WPP_SF_d
0x1800d4256  mov     rcx, r14
0x1800d4259  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d425e  test    al, al
0x1800d4260  jz      short loc_1800D4275
0x1800d4262  mov     r9, rsi
0x1800d4265  mov     r8d, 583h
0x1800d426b  mov     rdx, r15
0x1800d426e  mov     ecx, ebx
0x1800d4270  call    TraceVpnWppErrorHRImpl
0x1800d4275  mov     eax, ebx
0x1800d4277  sar     eax, 10h
0x1800d427a  and     eax, 1FFFh
0x1800d427f  cmp     eax, 7
0x1800d4282  jnz     short loc_1800D428B
0x1800d4284  movzx   ecx, bx
0x1800d4287  mov     edx, ecx
0x1800d4289  jmp     short loc_1800D4290
0x1800d428b  mov     ecx, ebx
0x1800d428d  movzx   edx, bx
0x1800d4290  test    ecx, ecx
0x1800d4292  jz      short loc_1800D42A9
0x1800d4294  cmp     eax, 7
0x1800d4297  cmovz   ebx, edx
0x1800d429a  lea     rdx, aVpnstringcopyF_2; "VpnStringCopy for profile path"
0x1800d42a1  mov     r8d, ebx
0x1800d42a4  jmp     loc_1800D4077
0x1800d42a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d42b0  lea     rax, WPP_GLOBAL_Control
0x1800d42b7  cmp     rcx, rax
0x1800d42ba  jz      short loc_1800D42DB
0x1800d42bc  test    byte ptr [rcx+1Ch], 4
0x1800d42c0  jz      short loc_1800D42DB
0x1800d42c2  mov     r9, [rbp+57h+lpMem]
0x1800d42c6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d42cd  mov     rcx, [rcx+10h]
0x1800d42d1  mov     edx, 84h
0x1800d42d6  call    WPP_SF_S
0x1800d42db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d42df  lea     rdx, [rbp+57h+lpMem]
0x1800d42e3  call    FixAutoTriggerProfilePath
0x1800d42e8  mov     edi, eax
0x1800d42ea  test    eax, eax
0x1800d42ec  jz      short loc_1800D42FD
0x1800d42ee  mov     r8d, eax
0x1800d42f1  lea     rdx, aFixautotrigger; "FixAutoTriggerProfilePath"
0x1800d42f8  jmp     loc_1800D4077
0x1800d42fd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d4301  lea     rax, [rbp+57h+cbData]
0x1800d4305  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800d430a  lea     r9, [rbp+57h+Type]; lpType
0x1800d430e  xor     r8d, r8d; lpReserved
0x1800d4311  mov     [rsp+0D0h+phkResult], r12; lpData
0x1800d4316  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800d431d  mov     [rbp+57h+cbData], 208h
0x1800d4324  call    cs:__imp_RegQueryValueExW
0x1800d432a  mov     edi, eax
0x1800d432c  test    eax, eax
0x1800d432e  jnz     loc_1800D4786
0x1800d4334  mov     eax, [rbp+57h+Type]
0x1800d4337  dec     eax
0x1800d4339  cmp     eax, 1
0x1800d433c  ja      loc_1800D4786
0x1800d4342  mov     ecx, [rbp+57h+cbData]
0x1800d4345  lea     rdx, [rbp+57h+var_70]
0x1800d4349  shr     rcx, 1
0x1800d434c  xor     eax, eax
0x1800d434e  mov     [r12+rcx*2], ax
0x1800d4353  mov     rcx, r12; Src
0x1800d4356  call    VpnStringCopy
0x1800d435b  mov     ebx, eax
0x1800d435d  test    eax, eax
0x1800d435f  jns     loc_1800D43E9
0x1800d4365  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d436c  lea     rax, WPP_GLOBAL_Control
0x1800d4373  cmp     rcx, rax
0x1800d4376  jz      short loc_1800D4396
0x1800d4378  test    byte ptr [rcx+1Ch], 1
0x1800d437c  jz      short loc_1800D4396
0x1800d437e  mov     rcx, [rcx+10h]
0x1800d4382  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4389  mov     edx, 86h
0x1800d438e  mov     r9d, ebx
0x1800d4391  call    WPP_SF_d
0x1800d4396  mov     rcx, r14
0x1800d4399  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d439e  test    al, al
0x1800d43a0  jz      short loc_1800D43B5
0x1800d43a2  mov     r9, rsi
0x1800d43a5  mov     r8d, 59Ah
0x1800d43ab  mov     rdx, r15
0x1800d43ae  mov     ecx, ebx
0x1800d43b0  call    TraceVpnWppErrorHRImpl
0x1800d43b5  mov     eax, ebx
0x1800d43b7  sar     eax, 10h
0x1800d43ba  and     eax, 1FFFh
0x1800d43bf  cmp     eax, 7
0x1800d43c2  jnz     short loc_1800D43CB
0x1800d43c4  movzx   ecx, bx
0x1800d43c7  mov     edx, ecx
0x1800d43c9  jmp     short loc_1800D43D0
0x1800d43cb  mov     ecx, ebx
0x1800d43cd  movzx   edx, bx
0x1800d43d0  test    ecx, ecx
0x1800d43d2  jz      short loc_1800D43E9
0x1800d43d4  cmp     eax, 7
0x1800d43d7  cmovz   ebx, edx
0x1800d43da  lea     rdx, aVpnstringcopyF_0; "VpnStringCopy for profile name"
0x1800d43e1  mov     r8d, ebx
0x1800d43e4  jmp     loc_1800D4077
0x1800d43e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d43f0  lea     rdi, WPP_GLOBAL_Control
0x1800d43f7  mov     rbx, [rbp+57h+var_70]
0x1800d43fb  cmp     rcx, rdi
0x1800d43fe  jz      short loc_1800D441E
  ... truncated ...
```
