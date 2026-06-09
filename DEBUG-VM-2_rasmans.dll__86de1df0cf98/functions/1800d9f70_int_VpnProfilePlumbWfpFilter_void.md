# int_VpnProfilePlumbWfpFilter(void)

- ea: `0x1800d9f70`
- end: `0x1800da786`
- name: `?int_VpnProfilePlumbWfpFilter@@YAKXZ`
- size: `2070`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bfad0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800d9f70`
- `0x1800da78c`
- `0x1800e1e64`
- `0x1800e2294`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da25a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da702`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800da06c`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800da06c`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800da611`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800da673`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800da611`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800da673`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800da53c`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800da5b2`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800da53c`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800da5b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800da250`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800da250`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800da0d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800da0d0`

## string_xrefs

- `0x1800da079`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800da124`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800da146`: `DuplicateToken`
- `0x1800da2b8`: `ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 int_VpnProfilePlumbWfpFilter(void)
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  DWORD LastError; // eax
  DWORD v3; // r15d
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  DWORD v7; // eax
  DWORD v8; // r15d
  DWORD v9; // eax
  __int64 v10; // r8
  DWORD v11; // eax
  DWORD v12; // eax
  __int64 v13; // r8
  DWORD v14; // eax
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+70h] [rbp-90h] BYREF
  FWPM_CALLOUT0 v23; // [rsp+D0h] [rbp-30h] BYREF
  FWPM_FILTER0 filter; // [rsp+130h] [rbp+30h] BYREF
  FWPM_FILTER0 v25; // [rsp+200h] [rbp+100h] BYREF
  GUID v26; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v27; // [rsp+2E0h] [rbp+1E0h]
  int v28; // [rsp+2E8h] [rbp+1E8h]
  int v29; // [rsp+2F0h] [rbp+1F0h]
  GUID v30; // [rsp+2F8h] [rbp+1F8h]
  int v31; // [rsp+308h] [rbp+208h]
  int v32; // [rsp+310h] [rbp+210h]
  int v33; // [rsp+318h] [rbp+218h]
  GUID v34; // [rsp+320h] [rbp+220h]
  int v35; // [rsp+330h] [rbp+230h]
  int v36; // [rsp+338h] [rbp+238h]
  NET_LUID *p_InterfaceLuid; // [rsp+340h] [rbp+240h]
  GUID v38; // [rsp+348h] [rbp+248h]
  int v39; // [rsp+358h] [rbp+258h]
  int v40; // [rsp+360h] [rbp+260h]
  __int128 *v41; // [rsp+368h] [rbp+268h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 572, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  filter.filterKey.Data1 = 0;
  memset_0(&filter.filterKey.Data2, 0, 0xC4u);
  v25.filterKey.Data1 = 0;
  memset_0(&v25.filterKey.Data2, 0, 0xC4u);
  v26.Data1 = 0;
  memset_0(&v26.Data2, 0, 0x9Cu);
  StringSid = 0;
  InterfaceLuid.Value = 0;
  StringSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  callout.calloutKey.Data1 = 0;
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  v23.calloutKey.Data1 = 0;
  memset_0(&v23.calloutKey.Data2, 0, 0x54u);
  v21 = 0;
  v0 = ConvertInterfaceIndexToLuid(InterfaceIndex, &InterfaceLuid);
  if ( v0 < 0 )
  {
    v1 = 87;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control[1].Flink,
        573,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (unsigned int)v0,
        87);
    }
    goto LABEL_69;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 574, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v3,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          5497,
          "int_VpnProfilePlumbWfpFilter");
      v1 = 0;
      v4 = "DuplicateToken";
      v5 = v3;
      goto LABEL_68;
    }
  }
  v6 = VpnStringBuild(&StringSecurityDescriptor, L"O:LSD:(A;;CC;;;", StringSid);
  v1 = v6;
  if ( v6 >= 0 )
  {
    v1 = 0;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 575, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v6);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      v1,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      5508,
      "int_VpnProfilePlumbWfpFilter");
  if ( (v1 & 0x1FFF0000) == 0x70000 )
    v1 = (unsigned __int16)v1;
  if ( !v1 )
  {
LABEL_31:
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            StringSecurityDescriptor,
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 577, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v7);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v8,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            5514,
            "int_VpnProfilePlumbWfpFilter");
        v5 = v8;
        v4 = "ConvertStringSecurityDescriptorToSecurityDescriptor";
        goto LABEL_68;
      }
    }
    v26 = FWPM_CONDITION_IP_PROTOCOL;
    v30 = FWPM_CONDITION_IP_PROTOCOL;
    p_InterfaceLuid = &InterfaceLuid;
    LODWORD(v21) = SecurityDescriptorSize;
    *((_QWORD *)&v21 + 1) = SecurityDescriptor;
    v41 = &v21;
    *(_DWORD *)&filter.filterKey.Data4[4] = -1917430209;
    filter.displayData.name = L"VPN IPv4 TCP Flow counting filter";
    filter.displayData.description = L"This filter keep track of VPN IPv4 TCP Flow, to determine when the connection is no longer in use";
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)&v26;
    v34 = FWPM_CONDITION_IP_LOCAL_INTERFACE;
    *(_DWORD *)&v25.filterKey.Data4[4] = 668242566;
    v25.displayData.name = L"VPN IPv6 TCP Flow counting filter";
    v38 = FWPM_CONDITION_ALE_USER_ID;
    *(_QWORD *)&filter.filterKey.Data2 = 0xE12DB8AD4AD526F3uLL;
    v25.displayData.description = L"This filter keep track of VPN IPv6 TCP Flow, to determine when the connection is no longer in use";
    *(_QWORD *)&v25.filterKey.Data2 = 0x21B475A5440E8E64LL;
    filter.action.type = 24580;
    v25.action.type = 24580;
    v25.filterCondition = (FWPM_FILTER_CONDITION0 *)&v26;
    v27 = 0;
    v28 = 1;
    v29 = 6;
    v31 = 0;
    v32 = 1;
    v33 = 17;
    v35 = 0;
    v36 = 4;
    v39 = 0;
    v40 = 14;
    filter.filterKey.Data1 = 2078314097;
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
    filter.weight.type = FWP_EMPTY;
    filter.subLayerKey = FWPM_SUBLAYER_INSPECTION;
    filter.numFilterConditions = 4;
    filter.action.filterType = stru_18010A590;
    v25.filterKey.Data1 = -1669476602;
    v25.flags = 0;
    v25.layerKey = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
    v25.weight.type = FWP_EMPTY;
    v25.subLayerKey = FWPM_SUBLAYER_INSPECTION;
    v25.numFilterConditions = 4;
    v25.action.filterType = stru_18010A580;
    callout.calloutKey = stru_18010A590;
    v23.calloutKey = stru_18010A580;
    callout.displayData.name = L"callout for vpn ale IPv4 flows";
    callout.applicableLayer = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
    v23.displayData.name = L"callout for vpn ale IPv6 flows";
    v23.applicableLayer = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
    v9 = FwpmCalloutAdd0(g_FwpEngineHandle, &callout, 0, 0);
    v1 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 578, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_46;
      v10 = 5583;
LABEL_45:
      TraceVpnWppErrorW32Impl(
        v1,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v10,
        "int_VpnProfilePlumbWfpFilter");
LABEL_46:
      v4 = "FwpmCalloutAdd0";
LABEL_67:
      v5 = v1;
LABEL_68:
      VpnReportError("int_VpnProfilePlumbWfpFilter", v4, v5);
      goto LABEL_69;
    }
    v11 = FwpmCalloutAdd0(g_FwpEngineHandle, &v23, 0, 0);
    v1 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 579, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v11);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_46;
      v10 = 5587;
      goto LABEL_45;
    }
    v12 = FwpmFilterAdd0(g_FwpEngineHandle, &filter, 0, 0);
    v1 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 580, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_66;
      v13 = 5591;
    }
    else
    {
      v14 = FwpmFilterAdd0(g_FwpEngineHandle, &v25, 0, 0);
      v1 = v14;
      if ( !v14 )
        goto LABEL_69;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 581, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v14);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_66;
      v13 = 5595;
    }
    TraceVpnWppErrorW32Impl(
      v1,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v13,
      "int_VpnProfilePlumbWfpFilter");
LABEL_66:
    v4 = "FwpmFilterAdd0";
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 576, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      v1,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      5509,
      "int_VpnProfilePlumbWfpFilter");
LABEL_69:
  MprCommonFree((LPVOID)StringSecurityDescriptor);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v1 )
  {
    int_VpnProfileUnPlumbWfpFilter();
    if ( (v1 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 582, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v1);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          v1,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          5617,
          "int_VpnProfilePlumbWfpFilter");
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800d9f70  push    rbp
0x1800d9f72  push    rbx
0x1800d9f73  push    rdi
0x1800d9f74  push    r12
0x1800d9f76  push    r13
0x1800d9f78  push    r14
0x1800d9f7a  push    r15
0x1800d9f7c  lea     rbp, [rsp-280h]
0x1800d9f84  sub     rsp, 380h
0x1800d9f8b  mov     rax, cs:__security_cookie
0x1800d9f92  xor     rax, rsp
0x1800d9f95  mov     [rbp+2B0h+var_40], rax
0x1800d9f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9fa3  lea     r13, WPP_GLOBAL_Control
0x1800d9faa  cmp     rcx, r13
0x1800d9fad  jz      short loc_1800D9FCA
0x1800d9faf  test    byte ptr [rcx+1Ch], 8
0x1800d9fb3  jz      short loc_1800D9FCA
0x1800d9fb5  mov     rcx, [rcx+10h]
0x1800d9fb9  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9fc0  mov     edx, 23Ch
0x1800d9fc5  call    WPP_SF_
0x1800d9fca  mov     ebx, 0C4h
0x1800d9fcf  lea     rcx, [rbp+2B0h+filter.filterKey.Data2]; void *
0x1800d9fd3  xor     r12d, r12d
0x1800d9fd6  mov     r8d, ebx; Size
0x1800d9fd9  xor     edx, edx; Val
0x1800d9fdb  mov     [rbp+2B0h+filter.filterKey.Data1], r12d
0x1800d9fdf  call    memset_0
0x1800d9fe4  mov     r8d, ebx; Size
0x1800d9fe7  mov     [rbp+2B0h+var_1B0.filterKey.Data1], r12d
0x1800d9fee  xor     edx, edx; Val
0x1800d9ff0  lea     rcx, [rbp+2B0h+var_1B0.filterKey.Data2]; void *
0x1800d9ff7  call    memset_0
0x1800d9ffc  xor     edx, edx; Val
0x1800d9ffe  mov     [rbp+2B0h+var_E0], r12d
0x1800da005  lea     r8d, [rbx-28h]; Size
0x1800da009  lea     rcx, [rbp+2B0h+var_DC]; void *
0x1800da010  call    memset_0
0x1800da015  lea     ebx, [r12+54h]
0x1800da01a  mov     [rsp+3B0h+StringSid], r12
0x1800da01f  mov     r8d, ebx; Size
0x1800da022  mov     qword ptr [rsp+3B0h+InterfaceLuid], r12
0x1800da027  xor     edx, edx; Val
0x1800da029  mov     [rsp+3B0h+StringSecurityDescriptor], r12
0x1800da02e  lea     rcx, [rsp+3B0h+callout.calloutKey.Data2]; void *
0x1800da033  mov     [rsp+3B0h+SecurityDescriptor], r12
0x1800da038  mov     [rsp+3B0h+SecurityDescriptorSize], r12d
0x1800da03d  mov     [rsp+3B0h+callout.calloutKey.Data1], r12d
0x1800da042  call    memset_0
0x1800da047  mov     r8d, ebx; Size
0x1800da04a  mov     [rbp+2B0h+var_2E0.calloutKey.Data1], r12d
0x1800da04e  xor     edx, edx; Val
0x1800da050  lea     rcx, [rbp+2B0h+var_2E0.calloutKey.Data2]; void *
0x1800da054  call    memset_0
0x1800da059  mov     ecx, cs:InterfaceIndex; InterfaceIndex
0x1800da05f  lea     rdx, [rsp+3B0h+InterfaceLuid]; InterfaceLuid
0x1800da064  xorps   xmm0, xmm0
0x1800da067  movups  [rsp+3B0h+var_358], xmm0
0x1800da06c  call    cs:__imp_ConvertInterfaceIndexToLuid
0x1800da072  lea     rdi, aIntVpnprofilep_0; "int_VpnProfilePlumbWfpFilter"
0x1800da079  lea     r14, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800da080  test    eax, eax
0x1800da082  jns     short loc_1800DA0C4
0x1800da084  lea     ebx, [r12+57h]
0x1800da089  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da090  cmp     rcx, r13
0x1800da093  jz      loc_1800DA6DE
0x1800da099  test    byte ptr [rcx+1Ch], 1
0x1800da09d  jz      loc_1800DA6DE
0x1800da0a3  mov     rcx, [rcx+10h]
0x1800da0a7  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800da0ae  mov     edx, 23Dh
0x1800da0b3  mov     dword ptr [rsp+3B0h+var_390], ebx
0x1800da0b7  mov     r9d, eax
0x1800da0ba  call    WPP_SF_Dd
0x1800da0bf  jmp     loc_1800DA6DE
0x1800da0c4  mov     rcx, cs:Sid; Sid
0x1800da0cb  lea     rdx, [rsp+3B0h+StringSid]; StringSid
0x1800da0d0  call    cs:__imp_ConvertSidToStringSidW
0x1800da0d6  test    eax, eax
0x1800da0d8  jnz     short loc_1800DA155
0x1800da0da  call    cs:__imp_GetLastError
0x1800da0e0  mov     r15d, eax
0x1800da0e3  test    eax, eax
0x1800da0e5  jz      short loc_1800DA155
0x1800da0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da0ee  cmp     rcx, r13
0x1800da0f1  jz      short loc_1800DA111
0x1800da0f3  test    byte ptr [rcx+1Ch], 1
0x1800da0f7  jz      short loc_1800DA111
0x1800da0f9  mov     rcx, [rcx+10h]
0x1800da0fd  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800da104  mov     edx, 23Eh
0x1800da109  mov     r9d, eax
0x1800da10c  call    WPP_SF_d
0x1800da111  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800da118  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800da11d  lea     rdi, aIntVpnprofilep_0; "int_VpnProfilePlumbWfpFilter"
0x1800da124  lea     r14, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800da12b  test    al, al
0x1800da12d  jz      short loc_1800DA143
0x1800da12f  mov     r9, rdi
0x1800da132  mov     r8d, 1579h
0x1800da138  mov     rdx, r14
0x1800da13b  mov     ecx, r15d
0x1800da13e  call    TraceVpnWppErrorW32Impl
0x1800da143  mov     ebx, r12d
0x1800da146  lea     rdx, aDuplicatetoken; "DuplicateToken"
0x1800da14d  mov     r8d, r15d
0x1800da150  jmp     loc_1800DA6D6
0x1800da155  mov     r8, [rsp+3B0h+StringSid]
0x1800da15a  lea     r9, aACcS11521; ")(A;;CC;;;S-1-15-2-1)"
0x1800da161  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800da168  mov     [rsp+3B0h+var_390], r12
0x1800da16d  lea     rcx, [rsp+3B0h+StringSecurityDescriptor]
0x1800da172  call    VpnStringBuild
0x1800da177  mov     ebx, eax
0x1800da179  test    eax, eax
0x1800da17b  jns     loc_1800DA239
0x1800da181  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da188  cmp     rcx, r13
0x1800da18b  jz      short loc_1800DA1AB
0x1800da18d  test    byte ptr [rcx+1Ch], 1
0x1800da191  jz      short loc_1800DA1AB
0x1800da193  mov     rcx, [rcx+10h]
0x1800da197  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800da19e  mov     edx, 23Fh
0x1800da1a3  mov     r9d, eax
0x1800da1a6  call    WPP_SF_d
0x1800da1ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800da1b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800da1b7  test    al, al
0x1800da1b9  jz      short loc_1800DA1CE
0x1800da1bb  mov     r9, rdi
0x1800da1be  mov     r8d, 1584h
0x1800da1c4  mov     rdx, r14
0x1800da1c7  mov     ecx, ebx
0x1800da1c9  call    TraceVpnWppErrorHRImpl
0x1800da1ce  mov     eax, ebx
0x1800da1d0  and     eax, 1FFF0000h
0x1800da1d5  cmp     eax, 70000h
0x1800da1da  jnz     short loc_1800DA1DF
0x1800da1dc  movzx   ebx, bx
0x1800da1df  test    ebx, ebx
0x1800da1e1  jz      short loc_1800DA23C
0x1800da1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da1ea  cmp     rcx, r13
0x1800da1ed  jz      short loc_1800DA20D
0x1800da1ef  test    byte ptr [rcx+1Ch], 1
0x1800da1f3  jz      short loc_1800DA20D
0x1800da1f5  mov     rcx, [rcx+10h]
0x1800da1f9  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800da200  mov     edx, 240h
0x1800da205  mov     r9d, ebx
0x1800da208  call    WPP_SF_d
0x1800da20d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800da214  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800da219  test    al, al
0x1800da21b  jz      loc_1800DA6DE
0x1800da221  mov     r9, rdi
0x1800da224  mov     r8d, 1585h
0x1800da22a  mov     rdx, r14
0x1800da22d  mov     ecx, ebx
0x1800da22f  call    TraceVpnWppErrorW32Impl
0x1800da234  jmp     loc_1800DA6DE
0x1800da239  mov     ebx, r12d
0x1800da23c  mov     rcx, [rsp+3B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800da241  lea     r9, [rsp+3B0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800da246  lea     r8, [rsp+3B0h+SecurityDescriptor]; SecurityDescriptor
0x1800da24b  mov     edx, 1; StringSDRevision
0x1800da250  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800da256  test    eax, eax
0x1800da258  jnz     short loc_1800DA2C4
0x1800da25a  call    cs:__imp_GetLastError
0x1800da260  mov     r15d, eax
0x1800da263  test    eax, eax
0x1800da265  jz      short loc_1800DA2C4
0x1800da267  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da26e  cmp     rcx, r13
0x1800da271  jz      short loc_1800DA291
0x1800da273  test    byte ptr [rcx+1Ch], 1
0x1800da277  jz      short loc_1800DA291
0x1800da279  mov     rcx, [rcx+10h]
0x1800da27d  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800da284  mov     edx, 241h
0x1800da289  mov     r9d, eax
0x1800da28c  call    WPP_SF_d
0x1800da291  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800da298  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800da29d  test    al, al
0x1800da29f  jz      short loc_1800DA2B5
0x1800da2a1  mov     r9, rdi
0x1800da2a4  mov     r8d, 158Ah
0x1800da2aa  mov     rdx, r14
0x1800da2ad  mov     ecx, r15d
0x1800da2b0  call    TraceVpnWppErrorW32Impl
0x1800da2b5  mov     r8d, r15d
0x1800da2b8  lea     rdx, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x1800da2bf  jmp     loc_1800DA6D6
0x1800da2c4  mov     eax, dword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data4+4
0x1800da2ca  mov     r9d, 4
0x1800da2d0  movsd   xmm0, qword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data2
0x1800da2d8  mov     ecx, cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x1800da2de  movups  xmm1, xmmword ptr cs:FWPM_SUBLAYER_INSPECTION.Data1
0x1800da2e5  mov     r8d, cs:stru_18010A590.Data1
0x1800da2ec  movups  xmm4, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4.Data1
0x1800da2f3  mov     edx, dword ptr cs:stru_18010A590.Data4+4
0x1800da2f9  movups  xmm2, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6.Data1
0x1800da300  mov     [rbp+2B0h+var_D4], eax
0x1800da306  movsd   xmm3, qword ptr cs:stru_18010A590.Data2
0x1800da30e  mov     [rbp+2B0h+var_AC], eax
0x1800da314  lea     rax, [rsp+3B0h+InterfaceLuid]
0x1800da319  mov     [rbp+2B0h+var_70], rax
0x1800da320  mov     eax, [rsp+3B0h+SecurityDescriptorSize]
0x1800da324  mov     dword ptr [rsp+3B0h+var_358], eax
0x1800da328  mov     rax, [rsp+3B0h+SecurityDescriptor]
0x1800da32d  mov     qword ptr [rsp+3B0h+var_358+8], rax
0x1800da332  lea     rax, [rsp+3B0h+var_358]
0x1800da337  mov     [rbp+2B0h+var_48], rax
0x1800da33e  mov     eax, dword ptr cs:key.Data4+4
0x1800da344  mov     dword ptr [rbp+2B0h+filter.filterKey.Data4+4], eax
0x1800da347  lea     rax, aVpnIpv4TcpFlow; "VPN IPv4 TCP Flow counting filter"
0x1800da34e  mov     [rbp+2B0h+filter.displayData.name], rax
0x1800da352  lea     rax, aThisFilterKeep_0; "This filter keep track of VPN IPv4 TCP "...
0x1800da359  mov     [rbp+2B0h+filter.displayData.description], rax
0x1800da35d  lea     rax, [rbp+2B0h+var_E0]
0x1800da364  movsd   [rbp+2B0h+var_DC], xmm0
0x1800da36c  movsd   [rbp+2B0h+var_B4], xmm0
0x1800da374  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_INTERFACE.Data1
0x1800da37b  mov     [rbp+2B0h+filter.filterCondition], rax
0x1800da382  mov     eax, dword ptr cs:stru_1800FC7B0.Data4+4
0x1800da388  movdqu  [rbp+2B0h+var_90], xmm0
0x1800da390  mov     dword ptr [rbp+2B0h+var_1B0.filterKey.Data4+4], eax
0x1800da396  lea     rax, aVpnIpv6TcpFlow; "VPN IPv6 TCP Flow counting filter"
0x1800da39d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_ALE_USER_ID.Data1
0x1800da3a4  mov     [rbp+2B0h+var_1B0.displayData.name], rax
0x1800da3ab  lea     rax, aThisFilterKeep; "This filter keep track of VPN IPv6 TCP "...
0x1800da3b2  mov     [rbp+2B0h+var_E0], ecx
0x1800da3b8  movdqu  [rbp+2B0h+var_68], xmm0
0x1800da3c0  mov     [rbp+2B0h+var_B8], ecx
0x1800da3c6  mov     ecx, 6004h
0x1800da3cb  movsd   xmm0, qword ptr cs:key.Data2
0x1800da3d3  movsd   qword ptr [rbp+2B0h+filter.filterKey.Data2], xmm0
0x1800da3d8  movsd   xmm0, qword ptr cs:stru_1800FC7B0.Data2
0x1800da3e0  mov     [rbp+2B0h+var_1B0.displayData.description], rax
0x1800da3e7  lea     rax, [rbp+2B0h+var_E0]
0x1800da3ee  movsd   qword ptr [rbp+2B0h+var_1B0.filterKey.Data2], xmm0
0x1800da3f6  movsd   xmm0, qword ptr cs:stru_18010A580.Data2
0x1800da3fe  mov     [rbp+2B0h+filter.action.type], ecx
0x1800da404  mov     [rbp+2B0h+var_1B0.action.type], ecx
0x1800da40a  mov     ecx, cs:stru_18010A580.Data1
0x1800da410  mov     [rbp+2B0h+var_1B0.filterCondition], rax
0x1800da417  mov     eax, dword ptr cs:stru_18010A580.Data4+4
0x1800da41d  mov     [rbp+2B0h+var_D0], r12d
0x1800da424  mov     [rbp+2B0h+var_C8], 1
0x1800da42e  mov     [rbp+2B0h+var_C0], 6
0x1800da438  mov     [rbp+2B0h+var_A8], r12d
0x1800da43f  mov     [rbp+2B0h+var_A0], 1
0x1800da449  mov     [rbp+2B0h+var_98], 11h
0x1800da453  mov     [rbp+2B0h+var_80], r12d
0x1800da45a  mov     [rbp+2B0h+var_78], r9d
0x1800da461  mov     [rbp+2B0h+var_58], r12d
0x1800da468  mov     [rbp+2B0h+var_50], 0Eh
0x1800da472  mov     [rbp+2B0h+filter.filterKey.Data1], 7BE08E71h
0x1800da479  mov     [rbp+2B0h+filter.flags], r12d
0x1800da47d  movdqu  xmmword ptr [rbp+2B0h+filter.layerKey.Data1], xmm4
0x1800da482  mov     [rbp+2B0h+filter.weight.type], r12d
0x1800da489  movdqu  xmmword ptr [rbp+2B0h+filter.subLayerKey.Data1], xmm1
0x1800da491  mov     [rbp+2B0h+filter.numFilterConditions], r9d
0x1800da498  mov     dword ptr [rbp+2B0h+filter.action.4], r8d
0x1800da49f  movsd   qword ptr [rbp+2B0h+filter.action.4+4], xmm3
0x1800da4a7  mov     dword ptr [rbp+2B0h+filter.action.4+0Ch], edx
0x1800da4ad  mov     [rbp+2B0h+var_1B0.filterKey.Data1], 9C7DCF06h
0x1800da4b7  mov     [rbp+2B0h+var_1B0.flags], r12d
0x1800da4be  movdqu  xmmword ptr [rbp+2B0h+var_1B0.layerKey.Data1], xmm2
0x1800da4c6  mov     [rbp+2B0h+var_1B0.weight.type], r12d
0x1800da4cd  movdqu  xmmword ptr [rbp+2B0h+var_1B0.subLayerKey.Data1], xmm1
0x1800da4d5  mov     [rbp+2B0h+var_1B0.numFilterConditions], r9d
0x1800da4dc  mov     dword ptr [rbp+2B0h+var_1B0.action.4], ecx
0x1800da4e2  movsd   qword ptr [rbp+2B0h+var_1B0.action.4+4], xmm0
0x1800da4ea  mov     dword ptr [rsp+3B0h+callout.calloutKey.Data4+4], edx
0x1800da4ee  xor     r9d, r9d; id
0x1800da4f1  lea     rdx, aCalloutForVpnA; "callout for vpn ale IPv4 flows"
0x1800da4f8  mov     dword ptr [rbp+2B0h+var_1B0.action.4+0Ch], eax
0x1800da4fe  mov     dword ptr [rbp+2B0h+var_2E0.calloutKey.Data4+4], eax
0x1800da501  lea     rax, aCalloutForVpnA_0; "callout for vpn ale IPv6 flows"
0x1800da508  mov     [rbp+2B0h+callout.displayData.name], rdx
0x1800da50c  lea     rdx, [rsp+3B0h+callout]; callout
0x1800da511  mov     [rsp+3B0h+callout.calloutKey.Data1], r8d
0x1800da516  xor     r8d, r8d; sd
0x1800da519  mov     [rbp+2B0h+var_2E0.calloutKey.Data1], ecx
0x1800da51c  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; engineHandle
0x1800da523  movsd   qword ptr [rsp+3B0h+callout.calloutKey.Data2], xmm3
0x1800da529  movdqu  xmmword ptr [rbp+2B0h+callout.applicableLayer.Data1], xmm4
0x1800da52e  mov     [rbp+2B0h+var_2E0.displayData.name], rax
0x1800da532  movsd   qword ptr [rbp+2B0h+var_2E0.calloutKey.Data2], xmm0
0x1800da537  movdqu  xmmword ptr [rbp+2B0h+var_2E0.applicableLayer.Data1], xmm2
0x1800da53c  call    cs:__imp_FwpmCalloutAdd0
0x1800da542  mov     ebx, eax
  ... truncated ...
```
