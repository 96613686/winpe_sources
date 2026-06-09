# VpnProfileSetRasManServiceState

- ea: `0x1800e014c`
- end: `0x1800e05fd`
- name: `VpnProfileSetRasManServiceState`
- size: `1201`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800c945c`
- `0x1800d4f20`
- `0x1800de2d8`

## callees

- `0x180005e34`
- `0x18000bf70`
- `0x1800b81fc`
- `0x1800d3064`
- `0x1800e014c`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e01bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e023f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e031f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e03e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e04c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e01bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e023f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e031f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e03e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e04c9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e057e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e0587`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e057e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e0587`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e01ae`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e01ae`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e0231`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e0231`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800e03d5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800e03d5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e0311`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e04bb`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e0311`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e04bb`

## string_xrefs

- `0x1800e0210`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e0372`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e0436`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e051c`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e056f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e05d4`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800e0207`: `VpnProfileSetRasManServiceState`
- `0x1800e0365`: `VpnProfileSetRasManServiceState`
- `0x1800e0429`: `VpnProfileSetRasManServiceState`
- `0x1800e050f`: `VpnProfileSetRasManServiceState`
- `0x1800e0566`: `VpnProfileSetRasManServiceState`
- `0x1800e05c7`: `VpnProfileSetRasManServiceState`

## pseudocode

```c
__int64 __fastcall VpnProfileSetRasManServiceState(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  DWORD LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rbp
  DWORD v12; // eax
  DWORD v13; // eax
  __int64 v14; // r8
  DWORD v15; // eax
  DWORD v16; // eax
  unsigned int Info; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 998, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, a4);
  }
  Info = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 999, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v9 = 9634;
LABEL_10:
      TraceVpnWppErrorW32Impl(
        v8,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v9,
        "VpnProfileSetRasManServiceState");
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  v10 = OpenServiceW(v5, L"Rasman", 0xF01FFu);
  v11 = v10;
  if ( v10 )
  {
    v8 = 0;
    if ( (unsigned int)int_QueryServiceConfiguration(v10, &Info) )
    {
      if ( a1 )
      {
        if ( Info != 2 )
          goto LABEL_23;
LABEL_60:
        CloseServiceHandle(v11);
        CloseServiceHandle(v6);
        goto LABEL_61;
      }
      if ( Info == 3 )
        goto LABEL_60;
    }
    if ( !a1 )
    {
      if ( ChangeServiceConfigW(v11, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        goto LABEL_60;
      v16 = GetLastError();
      v8 = v16;
      if ( !v16 )
        goto LABEL_60;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1005, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v16);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v8,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          9704,
          "VpnProfileSetRasManServiceState");
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1006, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_60;
      v14 = 9705;
LABEL_59:
      TraceVpnWppErrorW32Impl(
        v8,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v14,
        "VpnProfileSetRasManServiceState");
      goto LABEL_60;
    }
LABEL_23:
    Info = 0;
    if ( ChangeServiceConfigW(v11, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)
      || (v13 = GetLastError(), (v8 = v13) == 0) )
    {
      if ( ChangeServiceConfig2W(v11, 3u, &Info) )
        goto LABEL_60;
      v15 = GetLastError();
      v8 = v15;
      if ( !v15 )
        goto LABEL_60;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1003, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v15);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v8,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          9685,
          "VpnProfileSetRasManServiceState");
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1004, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_60;
      v14 = 9686;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1001, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v13);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v8,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          9677,
          "VpnProfileSetRasManServiceState");
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1002, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_60;
      v14 = 9678;
    }
    goto LABEL_59;
  }
  v12 = GetLastError();
  v8 = v12;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1000, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
  {
    v9 = 9641;
    goto LABEL_10;
  }
LABEL_61:
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1007, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v8,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        9722,
        "VpnProfileSetRasManServiceState");
  }
  return v8;
}

```

## disassembly

```asm
0x1800e014c  mov     [rsp+arg_0], rbx
0x1800e0151  mov     [rsp+arg_10], rbp
0x1800e0156  push    rsi
0x1800e0157  push    rdi
0x1800e0158  push    r13
0x1800e015a  push    r14
0x1800e015c  push    r15
0x1800e015e  sub     rsp, 60h
0x1800e0162  mov     esi, ecx
0x1800e0164  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e016b  lea     r13, WPP_GLOBAL_Control
0x1800e0172  xor     r15d, r15d
0x1800e0175  lea     rdi, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e017c  cmp     rcx, r13
0x1800e017f  jz      short loc_1800E019E
0x1800e0181  test    byte ptr [rcx+1Ch], 8
0x1800e0185  jz      short loc_1800E019E
0x1800e0187  mov     rcx, [rcx+10h]
0x1800e018b  test    esi, esi
0x1800e018d  mov     edx, 3E6h
0x1800e0192  mov     r8, rdi
0x1800e0195  setnz   r9b
0x1800e0199  call    WPP_SF_c
0x1800e019e  xor     edx, edx; lpDatabaseName
0x1800e01a0  mov     [rsp+88h+Info], r15d
0x1800e01a8  xor     ecx, ecx; lpMachineName
0x1800e01aa  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800e01ae  call    cs:__imp_OpenSCManagerW
0x1800e01b4  mov     r14, rax
0x1800e01b7  test    rax, rax
0x1800e01ba  jnz     short loc_1800E0221
0x1800e01bc  call    cs:__imp_GetLastError
0x1800e01c2  mov     ebx, eax
0x1800e01c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e01cb  cmp     rcx, r13
0x1800e01ce  jz      short loc_1800E01EA
0x1800e01d0  test    byte ptr [rcx+1Ch], 1
0x1800e01d4  jz      short loc_1800E01EA
0x1800e01d6  mov     rcx, [rcx+10h]
0x1800e01da  mov     edx, 3E7h
0x1800e01df  mov     r9d, eax
0x1800e01e2  mov     r8, rdi
0x1800e01e5  call    WPP_SF_d
0x1800e01ea  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800e01f1  mov     rcx, rdi
0x1800e01f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e01f9  test    al, al
0x1800e01fb  jz      loc_1800E058D
0x1800e0201  mov     r8d, 25A2h
0x1800e0207  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e020e  mov     ecx, ebx
0x1800e0210  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e0217  call    TraceVpnWppErrorW32Impl
0x1800e021c  jmp     loc_1800E058D
0x1800e0221  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800e0227  lea     rdx, aRasman_2; "Rasman"
0x1800e022e  mov     rcx, r14; hSCManager
0x1800e0231  call    cs:__imp_OpenServiceW
0x1800e0237  mov     rbp, rax
0x1800e023a  test    rax, rax
0x1800e023d  jnz     short loc_1800E028F
0x1800e023f  call    cs:__imp_GetLastError
0x1800e0245  mov     ebx, eax
0x1800e0247  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e024e  cmp     rcx, r13
0x1800e0251  jz      short loc_1800E026D
0x1800e0253  test    byte ptr [rcx+1Ch], 1
0x1800e0257  jz      short loc_1800E026D
0x1800e0259  mov     rcx, [rcx+10h]
0x1800e025d  mov     edx, 3E8h
0x1800e0262  mov     r9d, eax
0x1800e0265  mov     r8, rdi
0x1800e0268  call    WPP_SF_d
0x1800e026d  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800e0274  mov     rcx, rdi
0x1800e0277  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e027c  test    al, al
0x1800e027e  jz      loc_1800E058D
0x1800e0284  mov     r8d, 25A9h
0x1800e028a  jmp     loc_1800E0207
0x1800e028f  lea     rdx, [rsp+88h+Info]; unsigned int *
0x1800e0297  mov     rcx, rbp; hService
0x1800e029a  mov     ebx, r15d
0x1800e029d  call    ?int_QueryServiceConfiguration@@YAHQEAUSC_HANDLE__@@PEAK@Z; int_QueryServiceConfiguration(SC_HANDLE__ * const,ulong *)
0x1800e02a2  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800e02a9  mov     r8d, 2; dwStartType
0x1800e02af  test    eax, eax
0x1800e02b1  jz      short loc_1800E02D5
0x1800e02b3  test    esi, esi
0x1800e02b5  jz      short loc_1800E02C7
0x1800e02b7  cmp     [rsp+88h+Info], r8d
0x1800e02bf  jz      loc_1800E057B
0x1800e02c5  jmp     short loc_1800E02DD
0x1800e02c7  cmp     [rsp+88h+Info], 3
0x1800e02cf  jz      loc_1800E057B
0x1800e02d5  test    esi, esi
0x1800e02d7  jz      loc_1800E0489
0x1800e02dd  mov     [rsp+88h+lpDisplayName], r15; lpDisplayName
0x1800e02e2  or      edx, 0FFFFFFFFh; dwServiceType
0x1800e02e5  mov     [rsp+88h+lpPassword], r15; lpPassword
0x1800e02ea  mov     r9d, edx; dwErrorControl
0x1800e02ed  mov     [rsp+88h+lpServiceStartName], r15; lpServiceStartName
0x1800e02f2  mov     rcx, rbp; hService
0x1800e02f5  mov     [rsp+88h+lpDependencies], r15; lpDependencies
0x1800e02fa  mov     [rsp+88h+lpdwTagId], r15; lpdwTagId
0x1800e02ff  mov     [rsp+88h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x1800e0304  mov     [rsp+88h+lpBinaryPathName], r15; lpBinaryPathName
0x1800e0309  mov     [rsp+88h+Info], r15d
0x1800e0311  call    cs:__imp_ChangeServiceConfigW
0x1800e0317  test    eax, eax
0x1800e0319  jnz     loc_1800E03C5
0x1800e031f  call    cs:__imp_GetLastError
0x1800e0325  mov     ebx, eax
0x1800e0327  test    eax, eax
0x1800e0329  jz      loc_1800E03C5
0x1800e032f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0336  cmp     rcx, r13
0x1800e0339  jz      short loc_1800E0359
0x1800e033b  test    byte ptr [rcx+1Ch], 1
0x1800e033f  jz      short loc_1800E0359
0x1800e0341  mov     rcx, [rcx+10h]
0x1800e0345  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e034c  mov     edx, 3E9h
0x1800e0351  mov     r9d, eax
0x1800e0354  call    WPP_SF_d
0x1800e0359  mov     rcx, rdi
0x1800e035c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e0361  test    al, al
0x1800e0363  jz      short loc_1800E0380
0x1800e0365  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e036c  mov     r8d, 25CDh
0x1800e0372  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e0379  mov     ecx, ebx
0x1800e037b  call    TraceVpnWppErrorW32Impl
0x1800e0380  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0387  cmp     rcx, r13
0x1800e038a  jz      short loc_1800E03AA
0x1800e038c  test    byte ptr [rcx+1Ch], 1
0x1800e0390  jz      short loc_1800E03AA
0x1800e0392  mov     rcx, [rcx+10h]
0x1800e0396  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e039d  mov     edx, 3EAh
0x1800e03a2  mov     r9d, ebx
0x1800e03a5  call    WPP_SF_d
0x1800e03aa  mov     rcx, rdi
0x1800e03ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e03b2  test    al, al
0x1800e03b4  jz      loc_1800E057B
0x1800e03ba  mov     r8d, 25CEh
0x1800e03c0  jmp     loc_1800E0566
0x1800e03c5  lea     r8, [rsp+88h+Info]; lpInfo
0x1800e03cd  mov     edx, 3; dwInfoLevel
0x1800e03d2  mov     rcx, rbp; hService
0x1800e03d5  call    cs:__imp_ChangeServiceConfig2W
0x1800e03db  test    eax, eax
0x1800e03dd  jnz     loc_1800E057B
0x1800e03e3  call    cs:__imp_GetLastError
0x1800e03e9  mov     ebx, eax
0x1800e03eb  test    eax, eax
0x1800e03ed  jz      loc_1800E057B
0x1800e03f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e03fa  cmp     rcx, r13
0x1800e03fd  jz      short loc_1800E041D
0x1800e03ff  test    byte ptr [rcx+1Ch], 1
0x1800e0403  jz      short loc_1800E041D
0x1800e0405  mov     rcx, [rcx+10h]
0x1800e0409  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e0410  mov     edx, 3EBh
0x1800e0415  mov     r9d, eax
0x1800e0418  call    WPP_SF_d
0x1800e041d  mov     rcx, rdi
0x1800e0420  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e0425  test    al, al
0x1800e0427  jz      short loc_1800E0444
0x1800e0429  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e0430  mov     r8d, 25D5h
0x1800e0436  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e043d  mov     ecx, ebx
0x1800e043f  call    TraceVpnWppErrorW32Impl
0x1800e0444  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e044b  cmp     rcx, r13
0x1800e044e  jz      short loc_1800E046E
0x1800e0450  test    byte ptr [rcx+1Ch], 1
0x1800e0454  jz      short loc_1800E046E
0x1800e0456  mov     rcx, [rcx+10h]
0x1800e045a  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e0461  mov     edx, 3ECh
0x1800e0466  mov     r9d, ebx
0x1800e0469  call    WPP_SF_d
0x1800e046e  mov     rcx, rdi
0x1800e0471  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e0476  test    al, al
0x1800e0478  jz      loc_1800E057B
0x1800e047e  mov     r8d, 25D6h
0x1800e0484  jmp     loc_1800E0566
0x1800e0489  mov     [rsp+88h+lpDisplayName], r15; lpDisplayName
0x1800e048e  or      edx, 0FFFFFFFFh; dwServiceType
0x1800e0491  mov     [rsp+88h+lpPassword], r15; lpPassword
0x1800e0496  mov     r9d, edx; dwErrorControl
0x1800e0499  mov     [rsp+88h+lpServiceStartName], r15; lpServiceStartName
0x1800e049e  mov     r8d, 3; dwStartType
0x1800e04a4  mov     [rsp+88h+lpDependencies], r15; lpDependencies
0x1800e04a9  mov     rcx, rbp; hService
0x1800e04ac  mov     [rsp+88h+lpdwTagId], r15; lpdwTagId
0x1800e04b1  mov     [rsp+88h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x1800e04b6  mov     [rsp+88h+lpBinaryPathName], r15; lpBinaryPathName
0x1800e04bb  call    cs:__imp_ChangeServiceConfigW
0x1800e04c1  test    eax, eax
0x1800e04c3  jnz     loc_1800E057B
0x1800e04c9  call    cs:__imp_GetLastError
0x1800e04cf  mov     ebx, eax
0x1800e04d1  test    eax, eax
0x1800e04d3  jz      loc_1800E057B
0x1800e04d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e04e0  cmp     rcx, r13
0x1800e04e3  jz      short loc_1800E0503
0x1800e04e5  test    byte ptr [rcx+1Ch], 1
0x1800e04e9  jz      short loc_1800E0503
0x1800e04eb  mov     rcx, [rcx+10h]
0x1800e04ef  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e04f6  mov     edx, 3EDh
0x1800e04fb  mov     r9d, eax
0x1800e04fe  call    WPP_SF_d
0x1800e0503  mov     rcx, rdi
0x1800e0506  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e050b  test    al, al
0x1800e050d  jz      short loc_1800E052A
0x1800e050f  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e0516  mov     r8d, 25E8h
0x1800e051c  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e0523  mov     ecx, ebx
0x1800e0525  call    TraceVpnWppErrorW32Impl
0x1800e052a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0531  cmp     rcx, r13
0x1800e0534  jz      short loc_1800E0554
0x1800e0536  test    byte ptr [rcx+1Ch], 1
0x1800e053a  jz      short loc_1800E0554
0x1800e053c  mov     rcx, [rcx+10h]
0x1800e0540  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e0547  mov     edx, 3EEh
0x1800e054c  mov     r9d, ebx
0x1800e054f  call    WPP_SF_d
0x1800e0554  mov     rcx, rdi
0x1800e0557  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e055c  test    al, al
0x1800e055e  jz      short loc_1800E057B
0x1800e0560  mov     r8d, 25E9h
0x1800e0566  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e056d  mov     ecx, ebx
0x1800e056f  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e0576  call    TraceVpnWppErrorW32Impl
0x1800e057b  mov     rcx, rbp; hSCObject
0x1800e057e  call    cs:__imp_CloseServiceHandle
0x1800e0584  mov     rcx, r14; hSCObject
0x1800e0587  call    cs:__imp_CloseServiceHandle
0x1800e058d  test    ebx, ebx
0x1800e058f  jns     short loc_1800E05E2
0x1800e0591  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0598  cmp     rcx, r13
0x1800e059b  jz      short loc_1800E05BB
0x1800e059d  test    byte ptr [rcx+1Ch], 8
0x1800e05a1  jz      short loc_1800E05BB
0x1800e05a3  mov     rcx, [rcx+10h]
0x1800e05a7  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800e05ae  mov     edx, 3EFh
0x1800e05b3  mov     r9d, ebx
0x1800e05b6  call    WPP_SF_d
0x1800e05bb  mov     rcx, rdi
0x1800e05be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800e05c3  test    al, al
0x1800e05c5  jz      short loc_1800E05E2
0x1800e05c7  lea     r9, aVpnprofilesetr; "VpnProfileSetRasManServiceState"
0x1800e05ce  mov     r8d, 25FAh
0x1800e05d4  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800e05db  mov     ecx, ebx
0x1800e05dd  call    TraceVpnWppErrorHRImpl
0x1800e05e2  lea     r11, [rsp+88h+var_28]
0x1800e05e7  mov     eax, ebx
0x1800e05e9  mov     rbx, [r11+30h]
0x1800e05ed  mov     rbp, [r11+40h]
0x1800e05f1  mov     rsp, r11
0x1800e05f4  pop     r15
0x1800e05f6  pop     r14
0x1800e05f8  pop     r13
0x1800e05fa  pop     rdi
0x1800e05fb  pop     rsi
0x1800e05fc  retn
```
