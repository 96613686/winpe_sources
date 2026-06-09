# DoProcessRasTriggerConnectionCallback(HRASCONN__ *,ulong,ulong)

- ea: `0x1800bfad0`
- end: `0x1800c03f4`
- name: `?DoProcessRasTriggerConnectionCallback@@YAKPEAUHRASCONN__@@KK@Z`
- size: `2340`
- prototype: `unsigned int __fastcall(HRASCONN, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d2ef0`
- `0x1800d3260`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x180005f1c`
- `0x18000bf70`
- `0x180032508`
- `0x1800593d0`
- `0x1800b81fc`
- `0x1800bf530`
- `0x1800bfad0`
- `0x1800c394c`
- `0x1800c8340`
- `0x1800c8898`
- `0x1800c9388`
- `0x1800c9ad8`
- `0x1800c9c10`
- `0x1800cac58`
- `0x1800cbb64`
- `0x1800d86c4`
- `0x1800d9f70`
- `0x1800daba4`
- `0x1800e0fec`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c02f1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c02f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c01a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c01a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c01b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c01b4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bfe76`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bffbc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bffd3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bfe76`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bffbc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800bffd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bfeb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800bfeb3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bff6d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bff6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c02dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c02dc`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800bfcd1`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800bfcd1`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800c0308`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800c0308`

## string_xrefs

- `0x1800bfd24`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c018c`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c0210`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c0269`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c035b`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c03d3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`

## pseudocode

```c
__int64 __fastcall DoProcessRasTriggerConnectionCallback(HRASCONN a1, int a2, __int64 a3)
{
  int v3; // ebp
  int v4; // r14d
  unsigned int v6; // ebx
  bool v7; // si
  bool v8; // r15
  LPCWSTR *v9; // rdi
  struct _LIST_ENTRY *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r9
  struct _TP_WORK *v13; // rcx
  bool v14; // di
  __int64 v15; // r9
  struct _LIST_ENTRY *v16; // rcx
  bool v17; // dl
  struct _LIST_ENTRY *v18; // rcx
  unsigned int InterfaceInfo; // eax
  __int64 v20; // r8
  unsigned int v21; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  HANDLE v25; // rcx
  DWORD v26; // eax
  bool v28[4]; // [rsp+20h] [rbp-58h]

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control[1].Flink, 260, a3, a1, a2, a3);
  v6 = 0;
  v7 = v4 == 0;
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( a1 == (HRASCONN)qword_18010DFF8 )
  {
    v9 = &g_ActiveUserProfile;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 262, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    v8 = 1;
  }
  else
  {
    if ( a1 != (HRASCONN)qword_18010E258 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 261, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      goto LABEL_128;
    }
    v8 = 0;
    v9 = &g_ActiveDeviceProfile;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 263, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
  }
  StopNewRetryWaitPeriod(v8);
  if ( v4 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          264,
          &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
          (unsigned int)v4,
          v3);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 4) != 0 )
      {
        WPP_SF_ddd(
          v10[1].Flink,
          265,
          &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
          *((unsigned int *)v9 + 7),
          0,
          *((_DWORD *)v9 + 145));
        v10 = WPP_GLOBAL_Control;
      }
    }
    *((_DWORD *)v9 + 7) = 0;
    v9[5] = 0;
    v9[6] = 0;
    *((_DWORD *)v9 + 145) = 0;
    if ( v4 == 868 )
    {
      ProbeNcsi();
      v10 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v10, VpnAutoTriggerConnectionAttemptFailed, v9[1]);
      v10 = WPP_GLOBAL_Control;
    }
    if ( !v8 )
    {
      if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 4) != 0 )
        WPP_SF_(v10[1].Flink, 272, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      if ( !g_IsActiveDeviceProfile || !IsErrorRecoverable(v4, 0) )
      {
        v7 = 1;
        EventActivityIdControl(3u, &stru_18010E550);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 274, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        }
        StartNewRetryWaitPeriod(dword_18010E548, v17);
        goto LABEL_80;
      }
      if ( !*(_DWORD *)(qword_18010E480 + 128) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 273, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        }
        v7 = 1;
        AddVPNCanceledEvent(16, 0);
        EventActivityIdControl(3u, &stru_18010E550);
        goto LABEL_80;
      }
      v13 = g_pReConnectDeviceTunnelWorkItem;
      goto LABEL_71;
    }
    v11 = FwpiVpnTriggerSetStateDisconnected(g_FwpEngineHandle, 0);
    v6 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 266, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v11);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v6,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          2708,
          "DoProcessRasTriggerConnectionCallback");
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      LOBYTE(v12) = g_IsActiveUserProfile != 0;
      WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 267, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
    }
    if ( g_IsActiveUserProfile && IsErrorRecoverable(v4, 1) )
    {
      if ( !*(_DWORD *)(qword_18010E220 + 128) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 269, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        }
        VpnCriticalSectionEnter(&g_CsActiveTriggerPeriod);
        v14 = g_fIsActiveAppTriggerPeriod;
        VpnCriticalSectionLeave(&g_CsActiveTriggerPeriod);
        if ( !v14 || g_fIsInside )
        {
          LOBYTE(v16) = (_BYTE)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            LOBYTE(v15) = v14;
            v28[0] = g_fIsInside != 0;
            WPP_SF_cc(
              WPP_GLOBAL_Control[1].Flink,
              270,
              &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              v15,
              *(_DWORD *)v28);
          }
        }
        else
        {
          int_AttemptToConnect(1);
        }
        goto LABEL_80;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 268, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      v13 = g_pReConnectUserTunnelWorkItem;
LABEL_71:
      SubmitThreadpoolWork(v13);
LABEL_80:
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_127;
    }
    v7 = 1;
    EventActivityIdControl(3u, &ActivityId);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl'::`2'::impl) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      qword_18010E928 = GetTickCount64();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_80;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) == 0 )
        goto LABEL_61;
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    v16 = WPP_GLOBAL_Control;
LABEL_61:
    if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v16[1].Blink) & 4) != 0 )
      WPP_SF_(v16[1].Flink, 271, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    goto LABEL_80;
  }
  InitializeLastConnError(v8);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_ddd(
      WPP_GLOBAL_Control[1].Flink,
      275,
      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      *((unsigned int *)v9 + 7),
      1,
      *((_DWORD *)v9 + 145));
    v18 = WPP_GLOBAL_Control;
  }
  *((_DWORD *)v9 + 7) = 1;
  if ( v8 )
    g_fUserTunnelRetryAttempted = 0;
  else
    g_fDeviceTunnelRetryAttempted = 0;
  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
    WPP_SF_q(v18[1].Flink, 276, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9[5]);
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v18, VpnAutoTriggerConnectionConnected, v9[1]);
  InterfaceInfo = int_VpnProfileGetInterfaceInfo(
                    (wchar_t *)v9[1],
                    (unsigned int *)v9 + 145,
                    (unsigned __int16 *)v9 + 28);
  v6 = InterfaceInfo;
  if ( InterfaceInfo )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 277, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, InterfaceInfo);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v20 = 2823;
LABEL_106:
      TraceVpnWppErrorW32Impl(
        v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v20,
        "DoProcessRasTriggerConnectionCallback");
    }
  }
  else if ( *(_DWORD *)v9[74] )
  {
    v21 = int_VpnProfilePlumbWfpFilter();
    v6 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 278, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v21);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v20 = 2831;
        goto LABEL_106;
      }
    }
  }
  if ( !v9[5] )
  {
LABEL_127:
    LogEndPhysicalConnection((bool)v16, a1, v4, v8, v7);
    goto LABEL_128;
  }
  ProcessHeap = GetProcessHeap();
  v23 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( v23 )
  {
    v23[2] = v9[5];
    *((_DWORD *)v23 + 6) = 0;
    VpnCriticalSectionEnter(&g_CsDisconnectionNotifications);
    v24 = (_QWORD *)qword_18010E658;
    if ( *(LPVOID **)qword_18010E658 != &g_DisconnectNotificationsList )
      __fastfail(3u);
    *v23 = &g_DisconnectNotificationsList;
    v23[1] = v24;
    *v24 = v23;
    qword_18010E658 = (__int64)v23;
    VpnCriticalSectionLeave(&g_CsDisconnectionNotifications);
    SetThreadpoolWait(g_ConnectionDisconnectWait, g_ConnectionDisconnectEvent, 0);
    v25 = g_ConnectionDisconnectEvent;
    v9[6] = v9[5];
    ResetEvent(v25);
    v26 = RasConnectionNotificationW((HRASCONN)v9[5], g_ConnectionDisconnectEvent, 2u);
    v6 = v26;
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 281, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v26);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v6,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          2859,
          "DoProcessRasTriggerConnectionCallback");
    }
    goto LABEL_127;
  }
  v6 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 279, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      2841,
      "DoProcessRasTriggerConnectionCallback");
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 280, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      2843,
      "DoProcessRasTriggerConnectionCallback");
LABEL_128:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 282, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        2870,
        "DoProcessRasTriggerConnectionCallback");
  }
  return v6;
}

```

## disassembly

```asm
0x1800bfad0  push    rbx
0x1800bfad2  push    rbp
0x1800bfad3  push    rsi
0x1800bfad4  push    rdi
0x1800bfad5  push    r12
0x1800bfad7  push    r13
0x1800bfad9  push    r14
0x1800bfadb  push    r15
0x1800bfadd  sub     rsp, 38h
0x1800bfae1  mov     ebp, r8d
0x1800bfae4  mov     r14d, edx
0x1800bfae7  mov     r12, rcx
0x1800bfaea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfaf1  lea     r15, WPP_GLOBAL_Control
0x1800bfaf8  cmp     rcx, r15
0x1800bfafb  jz      short loc_1800BFB1E
0x1800bfafd  test    byte ptr [rcx+1Ch], 8
0x1800bfb01  jz      short loc_1800BFB1E
0x1800bfb03  mov     rcx, [rcx+10h]
0x1800bfb07  mov     edx, 104h
0x1800bfb0c  mov     [rsp+78h+var_50], r8d
0x1800bfb11  mov     r9, r12
0x1800bfb14  mov     dword ptr [rsp+78h+var_58], r14d
0x1800bfb19  call    WPP_SF_qDD
0x1800bfb1e  xor     r13d, r13d
0x1800bfb21  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800bfb28  test    r14d, r14d
0x1800bfb2b  mov     ebx, r13d
0x1800bfb2e  setz    sil
0x1800bfb32  call    VpnCriticalSectionEnter
0x1800bfb37  cmp     r12, cs:qword_18010DFF8
0x1800bfb3e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfb45  mov     dl, 4
0x1800bfb47  jz      short loc_1800BFBB7
0x1800bfb49  cmp     r12, cs:qword_18010E258
0x1800bfb50  jz      short loc_1800BFB85
0x1800bfb52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfb59  lea     rbp, WPP_GLOBAL_Control
0x1800bfb60  cmp     rcx, rbp
0x1800bfb63  jz      loc_1800C037C
0x1800bfb69  test    [rcx+1Ch], dl
0x1800bfb6c  jz      loc_1800C037C
0x1800bfb72  mov     rcx, [rcx+10h]
0x1800bfb76  mov     edx, 105h
0x1800bfb7b  call    WPP_SF_
0x1800bfb80  jmp     loc_1800C037C
0x1800bfb85  mov     r15b, r13b
0x1800bfb88  lea     rdi, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800bfb8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfb96  lea     rax, WPP_GLOBAL_Control
0x1800bfb9d  cmp     rcx, rax
0x1800bfba0  jz      short loc_1800BFBE0
0x1800bfba2  test    [rcx+1Ch], dl
0x1800bfba5  jz      short loc_1800BFBE0
0x1800bfba7  mov     rcx, [rcx+10h]
0x1800bfbab  mov     edx, 107h
0x1800bfbb0  call    WPP_SF_
0x1800bfbb5  jmp     short loc_1800BFBE0
0x1800bfbb7  lea     rdi, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800bfbbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfbc5  cmp     rcx, r15
0x1800bfbc8  jz      short loc_1800BFBDD
0x1800bfbca  test    [rcx+1Ch], dl
0x1800bfbcd  jz      short loc_1800BFBDD
0x1800bfbcf  mov     rcx, [rcx+10h]
0x1800bfbd3  mov     edx, 106h
0x1800bfbd8  call    WPP_SF_
0x1800bfbdd  mov     r15b, 1
0x1800bfbe0  mov     cl, r15b; bool
0x1800bfbe3  call    ?StopNewRetryWaitPeriod@@YAX_N@Z; StopNewRetryWaitPeriod(bool)
0x1800bfbe8  test    r14d, r14d
0x1800bfbeb  jz      loc_1800C0024
0x1800bfbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfbf8  lea     rax, WPP_GLOBAL_Control
0x1800bfbff  cmp     rcx, rax
0x1800bfc02  jz      short loc_1800BFC70
0x1800bfc04  test    byte ptr [rcx+1Ch], 1
0x1800bfc08  jz      short loc_1800BFC2D
0x1800bfc0a  mov     rcx, [rcx+10h]
0x1800bfc0e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfc15  mov     edx, 108h
0x1800bfc1a  mov     dword ptr [rsp+78h+var_58], ebp
0x1800bfc1e  mov     r9d, r14d
0x1800bfc21  call    WPP_SF_Dd
0x1800bfc26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfc2d  lea     rbp, WPP_GLOBAL_Control
0x1800bfc34  cmp     rcx, rbp
0x1800bfc37  jz      short loc_1800BFC77
0x1800bfc39  test    byte ptr [rcx+1Ch], 4
0x1800bfc3d  jz      short loc_1800BFC77
0x1800bfc3f  mov     eax, [rdi+244h]
0x1800bfc45  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfc4c  mov     r9d, [rdi+1Ch]
0x1800bfc50  mov     edx, 109h
0x1800bfc55  mov     rcx, [rcx+10h]
0x1800bfc59  mov     [rsp+78h+var_50], eax
0x1800bfc5d  mov     dword ptr [rsp+78h+var_58], r13d
0x1800bfc62  call    WPP_SF_ddd
0x1800bfc67  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfc6e  jmp     short loc_1800BFC77
0x1800bfc70  lea     rbp, WPP_GLOBAL_Control
0x1800bfc77  mov     [rdi+1Ch], r13d
0x1800bfc7b  mov     [rdi+28h], r13
0x1800bfc7f  mov     [rdi+30h], r13
0x1800bfc83  mov     [rdi+244h], r13d
0x1800bfc8a  cmp     r14d, 364h
0x1800bfc91  jnz     short loc_1800BFC9F
0x1800bfc93  call    ?ProbeNcsi@@YAXXZ; ProbeNcsi(void)
0x1800bfc98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfc9f  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800bfca6  jz      short loc_1800BFCBF
0x1800bfca8  mov     r8, [rdi+8]
0x1800bfcac  lea     rdx, VpnAutoTriggerConnectionAttemptFailed
0x1800bfcb3  call    McTemplateU0z_EventWriteTransfer
0x1800bfcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfcbf  test    r15b, r15b
0x1800bfcc2  jz      loc_1800BFF1F
0x1800bfcc8  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800bfccf  xor     edx, edx
0x1800bfcd1  call    cs:__imp_FwpiVpnTriggerSetStateDisconnected
0x1800bfcd7  mov     ebx, eax
0x1800bfcd9  test    eax, eax
0x1800bfcdb  jz      short loc_1800BFD32
0x1800bfcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfce4  cmp     rcx, rbp
0x1800bfce7  jz      short loc_1800BFD07
0x1800bfce9  test    byte ptr [rcx+1Ch], 1
0x1800bfced  jz      short loc_1800BFD07
0x1800bfcef  mov     rcx, [rcx+10h]
0x1800bfcf3  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfcfa  mov     edx, 10Ah
0x1800bfcff  mov     r9d, eax
0x1800bfd02  call    WPP_SF_d
0x1800bfd07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800bfd0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800bfd13  test    al, al
0x1800bfd15  jz      short loc_1800BFD32
0x1800bfd17  lea     r9, aDoprocessrastr; "DoProcessRasTriggerConnectionCallback"
0x1800bfd1e  mov     r8d, 0A94h
0x1800bfd24  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800bfd2b  mov     ecx, ebx
0x1800bfd2d  call    TraceVpnWppErrorW32Impl
0x1800bfd32  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd39  cmp     rcx, rbp
0x1800bfd3c  jz      short loc_1800BFD64
0x1800bfd3e  test    byte ptr [rcx+1Ch], 4
0x1800bfd42  jz      short loc_1800BFD64
0x1800bfd44  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800bfd4b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfd52  mov     rcx, [rcx+10h]
0x1800bfd56  mov     edx, 10Bh
0x1800bfd5b  setnz   r9b
0x1800bfd5f  call    WPP_SF_c
0x1800bfd64  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800bfd6b  jz      loc_1800BFE67
0x1800bfd71  mov     dl, 1; bool
0x1800bfd73  mov     ecx, r14d; unsigned int
0x1800bfd76  call    ?IsErrorRecoverable@@YA_NK_N@Z; IsErrorRecoverable(ulong,bool)
0x1800bfd7b  test    al, al
0x1800bfd7d  jz      loc_1800BFE67
0x1800bfd83  mov     rax, cs:qword_18010E220
0x1800bfd8a  cmp     [rax+80h], r13d
0x1800bfd91  jz      short loc_1800BFDC6
0x1800bfd93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd9a  cmp     rcx, rbp
0x1800bfd9d  jz      short loc_1800BFDBA
0x1800bfd9f  test    byte ptr [rcx+1Ch], 4
0x1800bfda3  jz      short loc_1800BFDBA
0x1800bfda5  mov     rcx, [rcx+10h]
0x1800bfda9  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfdb0  mov     edx, 10Ch
0x1800bfdb5  call    WPP_SF_
0x1800bfdba  mov     rcx, cs:?g_pReConnectUserTunnelWorkItem@@3PEAU_TP_WORK@@EA; _TP_WORK * g_pReConnectUserTunnelWorkItem
0x1800bfdc1  jmp     loc_1800BFF6D
0x1800bfdc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfdcd  cmp     rcx, rbp
0x1800bfdd0  jz      short loc_1800BFDED
0x1800bfdd2  test    byte ptr [rcx+1Ch], 4
0x1800bfdd6  jz      short loc_1800BFDED
0x1800bfdd8  mov     rcx, [rcx+10h]
0x1800bfddc  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfde3  mov     edx, 10Dh
0x1800bfde8  call    WPP_SF_
0x1800bfded  lea     rcx, ?g_CsActiveTriggerPeriod@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsActiveTriggerPeriod
0x1800bfdf4  call    VpnCriticalSectionEnter
0x1800bfdf9  mov     dil, cs:?g_fIsActiveAppTriggerPeriod@@3_NA; bool g_fIsActiveAppTriggerPeriod
0x1800bfe00  lea     rcx, ?g_CsActiveTriggerPeriod@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsActiveTriggerPeriod
0x1800bfe07  call    VpnCriticalSectionLeave
0x1800bfe0c  mov     eax, cs:?g_fIsInside@@3HA; int g_fIsInside
0x1800bfe12  test    dil, dil
0x1800bfe15  jz      short loc_1800BFE27
0x1800bfe17  test    eax, eax
0x1800bfe19  jnz     short loc_1800BFE27
0x1800bfe1b  mov     cl, 1; bool
0x1800bfe1d  call    ?int_AttemptToConnect@@YAX_N@Z; int_AttemptToConnect(bool)
0x1800bfe22  jmp     loc_1800C000B
0x1800bfe27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfe2e  cmp     rcx, rbp
0x1800bfe31  jz      loc_1800C000B
0x1800bfe37  test    byte ptr [rcx+1Ch], 4
0x1800bfe3b  jz      loc_1800C000B
0x1800bfe41  mov     rcx, [rcx+10h]
0x1800bfe45  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfe4c  test    eax, eax
0x1800bfe4e  mov     edx, 10Eh
0x1800bfe53  mov     r9b, dil
0x1800bfe56  setnz   al
0x1800bfe59  mov     [rsp+78h+var_58], al
0x1800bfe5d  call    WPP_SF_cc
0x1800bfe62  jmp     loc_1800C000B
0x1800bfe67  lea     rdx, ActivityId; ActivityId
0x1800bfe6e  mov     ecx, 3; ControlCode
0x1800bfe73  mov     sil, 1
0x1800bfe76  call    cs:__imp_EventActivityIdControl
0x1800bfe7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl(void)'::`2'::impl
0x1800bfe83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(void)
0x1800bfe88  test    al, al
0x1800bfe8a  jz      short loc_1800BFEEB
0x1800bfe8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfe93  cmp     rcx, rbp
0x1800bfe96  jz      short loc_1800BFEB3
0x1800bfe98  test    byte ptr [rcx+1Ch], 8
0x1800bfe9c  jz      short loc_1800BFEB3
0x1800bfe9e  mov     rcx, [rcx+10h]
0x1800bfea2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfea9  mov     edx, 0Ah
0x1800bfeae  call    WPP_SF_
0x1800bfeb3  call    cs:__imp_GetTickCount64
0x1800bfeb9  mov     cs:qword_18010E928, rax
0x1800bfec0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfec7  cmp     rcx, rbp
0x1800bfeca  jz      loc_1800C000B
0x1800bfed0  test    byte ptr [rcx+1Ch], 8
0x1800bfed4  jz      short loc_1800BFEF2
0x1800bfed6  mov     rcx, [rcx+10h]
0x1800bfeda  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfee1  mov     edx, 0Bh
0x1800bfee6  call    WPP_SF_
0x1800bfeeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfef2  cmp     rcx, rbp
0x1800bfef5  jz      loc_1800C000B
0x1800bfefb  test    byte ptr [rcx+1Ch], 4
0x1800bfeff  jz      loc_1800C000B
0x1800bff05  mov     rcx, [rcx+10h]
0x1800bff09  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bff10  mov     edx, 10Fh
0x1800bff15  call    WPP_SF_
0x1800bff1a  jmp     loc_1800C000B
0x1800bff1f  cmp     rcx, rbp
0x1800bff22  jz      short loc_1800BFF3F
0x1800bff24  test    byte ptr [rcx+1Ch], 4
0x1800bff28  jz      short loc_1800BFF3F
0x1800bff2a  mov     rcx, [rcx+10h]
0x1800bff2e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bff35  mov     edx, 110h
0x1800bff3a  call    WPP_SF_
0x1800bff3f  cmp     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800bff46  jz      short loc_1800BFFC4
0x1800bff48  xor     edx, edx; bool
0x1800bff4a  mov     ecx, r14d; unsigned int
0x1800bff4d  call    ?IsErrorRecoverable@@YA_NK_N@Z; IsErrorRecoverable(ulong,bool)
0x1800bff52  test    al, al
0x1800bff54  jz      short loc_1800BFFC4
0x1800bff56  mov     rax, cs:qword_18010E480
0x1800bff5d  cmp     [rax+80h], r13d
0x1800bff64  jz      short loc_1800BFF78
0x1800bff66  mov     rcx, cs:?g_pReConnectDeviceTunnelWorkItem@@3PEAU_TP_WORK@@EA; pwk
0x1800bff6d  call    cs:__imp_SubmitThreadpoolWork
0x1800bff73  jmp     loc_1800C000B
0x1800bff78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bff7f  cmp     rcx, rbp
0x1800bff82  jz      short loc_1800BFF9F
0x1800bff84  test    byte ptr [rcx+1Ch], 4
0x1800bff88  jz      short loc_1800BFF9F
0x1800bff8a  mov     rcx, [rcx+10h]
0x1800bff8e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bff95  mov     edx, 111h
0x1800bff9a  call    WPP_SF_
0x1800bff9f  movzx   edx, r15b
0x1800bffa3  mov     ecx, 10h
0x1800bffa8  mov     sil, 1
0x1800bffab  call    ?AddVPNCanceledEvent@@YAXW4_LOGICAL_CONNECTION_CANCEL_REASON@@H@Z; AddVPNCanceledEvent(_LOGICAL_CONNECTION_CANCEL_REASON,int)
0x1800bffb0  lea     rdx, stru_18010E550; ActivityId
0x1800bffb7  mov     ecx, 3; ControlCode
0x1800bffbc  call    cs:__imp_EventActivityIdControl
0x1800bffc2  jmp     short loc_1800C000B
0x1800bffc4  lea     rdx, stru_18010E550; ActivityId
0x1800bffcb  mov     ecx, 3; ControlCode
0x1800bffd0  mov     sil, 1
0x1800bffd3  call    cs:__imp_EventActivityIdControl
0x1800bffd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bffe0  cmp     rcx, rbp
0x1800bffe3  jz      short loc_1800C0000
0x1800bffe5  test    byte ptr [rcx+1Ch], 4
0x1800bffe9  jz      short loc_1800C0000
0x1800bffeb  mov     rcx, [rcx+10h]
0x1800bffef  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800bfff6  mov     edx, 112h
0x1800bfffb  call    WPP_SF_
0x1800c0000  mov     ecx, cs:dword_18010E548; unsigned int
  ... truncated ...
```
