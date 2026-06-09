# VpnProfileGetEntryByName(ushort const *,ushort const *,ulong,tagRASENTRYW * *,tagRASENTRYADVANCED * *)

- ea: `0x1800ca0e4`
- end: `0x1800ca58b`
- name: `?VpnProfileGetEntryByName@@YAKPEBG0KPEAPEAUtagRASENTRYW@@PEAPEAUtagRASENTRYADVANCED@@@Z`
- size: `1191`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR@<rcx>, LPCWSTR@<rdx>, unsigned int@<r8d>, struct tagRASENTRYW **@<r9>, struct tagRASENTRYADVANCED **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dc964`

## callees

- `0x180005e34`
- `0x18000e650`
- `0x18007b46c`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800ca0e4`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800ca1a4`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800ca33f`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800ca1a4`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800ca33f`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800ca23b`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800ca23b`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasGetEntryAdvancedProperties` at `0x1800ca488`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasGetEntryAdvancedProperties` at `0x1800ca488`

## string_xrefs

- `0x1800ca200`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca2ab`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca300`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca38f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca409`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca45e`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca4d8`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ca55e`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`

## pseudocode

```c
__int64 __fastcall VpnProfileGetEntryByName(
        LPCWSTR a1,
        const char *a2,
        DWORD a3,
        struct tagRASENTRYW **a4,
        struct tagRASENTRYADVANCED **a5)
{
  const char *v8; // rax
  const char *v9; // r9
  struct tagRASENTRYADVANCED **v10; // r15
  DWORD EntryPropertiesW; // eax
  unsigned int v12; // ebx
  struct tagRASENTRYW *v13; // rax
  struct tagRASENTRYW *v14; // rsi
  DWORD v15; // eax
  const char *v16; // rdx
  unsigned int EntryAdvancedProperties; // eax
  DWORD v19; // [rsp+70h] [rbp+18h] BYREF
  struct tagRASENTRYADVANCED *v20; // [rsp+78h] [rbp+20h] BYREF

  v19 = a3;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v8 = a2;
    if ( !a2 )
      v8 = L"<NULL>";
    LODWORD(v9) = (_DWORD)a1;
    if ( !a1 )
      v9 = L"<NULL>";
    WPP_SF_SSD(
      WPP_GLOBAL_Control[1].Flink,
      897,
      (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      (_DWORD)v9,
      (__int64)v8,
      224);
  }
  v10 = a5;
  v19 = 0;
  v20 = 0;
  *a5 = 0;
  *a4 = 0;
  EntryPropertiesW = RasGetEntryPropertiesW(a1, (LPCWSTR)a2, 0, &v19, 0, 0);
  v12 = 0;
  if ( EntryPropertiesW != 603 )
    v12 = EntryPropertiesW;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 898, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8637,
        "VpnProfileGetEntryByName");
    VpnReportError("VpnProfileGetEntryByName", "RasGetEntryProperties", v12);
    goto LABEL_17;
  }
  v13 = (struct tagRASENTRYW *)VpnAlloc(v19);
  v14 = v13;
  if ( !v13 )
  {
    v12 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 899, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8644,
        "VpnProfileGetEntryByName");
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 900, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8646,
        "VpnProfileGetEntryByName");
    goto LABEL_17;
  }
  v13->dwSize = 6724;
  v15 = RasGetEntryPropertiesW(a1, (LPCWSTR)a2, v13, &v19, 0, 0);
  v12 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 901, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v15);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8656,
        "VpnProfileGetEntryByName");
    v16 = "RasGetEntryPropertiesW";
  }
  else
  {
    if ( v14->dwType != 2 )
    {
      v12 = 13;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control[1].Flink,
          902,
          (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
          (_DWORD)a2,
          13);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          13,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8663,
          "VpnProfileGetEntryByName");
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 903, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 13);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          13,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8664,
          "VpnProfileGetEntryByName");
      goto LABEL_56;
    }
    EntryAdvancedProperties = RasGetEntryAdvancedProperties(a1, a2, 3040, &v20);
    v12 = EntryAdvancedProperties;
    if ( !EntryAdvancedProperties )
    {
      *v10 = v20;
      *a4 = v14;
      goto LABEL_58;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        904,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        EntryAdvancedProperties);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8672,
        "VpnProfileGetEntryByName");
    v16 = "RasGetEntryAdvancedProperties";
  }
  VpnReportError("VpnProfileGetEntryByName", v16, v12);
LABEL_56:
  MprCommonFree(v14);
LABEL_17:
  if ( v20 )
  {
    RasFreeEntryAdvancedProperties(v20);
    v20 = 0;
  }
LABEL_58:
  if ( (v12 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 905, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8695,
        "VpnProfileGetEntryByName");
  }
  return v12;
}

```

## disassembly

```asm
0x1800ca0e4  mov     r11, rsp
0x1800ca0e7  mov     [r11+8], rbx
0x1800ca0eb  mov     [r11+10h], rbp
0x1800ca0ef  mov     [r11+18h], r8d
0x1800ca0f3  push    rsi
0x1800ca0f4  push    rdi
0x1800ca0f5  push    r13
0x1800ca0f7  push    r14
0x1800ca0f9  push    r15
0x1800ca0fb  sub     rsp, 30h
0x1800ca0ff  mov     r14, r9
0x1800ca102  mov     rdi, rdx
0x1800ca105  mov     rbp, rcx
0x1800ca108  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca10f  lea     rsi, WPP_GLOBAL_Control
0x1800ca116  cmp     rcx, rsi
0x1800ca119  jz      short loc_1800CA15D
0x1800ca11b  test    byte ptr [rcx+1Ch], 8
0x1800ca11f  jz      short loc_1800CA15D
0x1800ca121  mov     rcx, [rcx+10h]
0x1800ca125  lea     rdx, aNull_5; "<NULL>"
0x1800ca12c  test    rdi, rdi
0x1800ca12f  mov     dword ptr [rsp+58h+var_30], 0BE0h
0x1800ca137  mov     rax, rdi
0x1800ca13a  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca141  cmovz   rax, rdx
0x1800ca145  mov     r9, rbp
0x1800ca148  test    rbp, rbp
0x1800ca14b  mov     [r11-38h], rax
0x1800ca14f  cmovz   r9, rdx
0x1800ca153  mov     edx, 381h
0x1800ca158  call    WPP_SF_SSD
0x1800ca15d  mov     r15, [rsp+58h+arg_20]
0x1800ca165  lea     r9, [rsp+58h+arg_10]; LPDWORD
0x1800ca16a  mov     [rsp+58h+var_30], 0; LPDWORD
0x1800ca173  xor     r8d, r8d; struct tagRASENTRYW *
0x1800ca176  mov     rdx, rdi; LPCWSTR
0x1800ca179  mov     [rsp+58h+arg_10], 0
0x1800ca181  mov     rcx, rbp; LPCWSTR
0x1800ca184  mov     [rsp+58h+arg_18], 0
0x1800ca18d  mov     qword ptr [r15], 0
0x1800ca194  mov     qword ptr [r14], 0
0x1800ca19b  mov     [rsp+58h+var_38], 0; LPBYTE
0x1800ca1a4  call    cs:__imp_RasGetEntryPropertiesW
0x1800ca1aa  xor     ebx, ebx
0x1800ca1ac  lea     r13, aVpnprofilegete; "VpnProfileGetEntryByName"
0x1800ca1b3  cmp     eax, 25Bh
0x1800ca1b8  cmovnz  ebx, eax
0x1800ca1bb  test    ebx, ebx
0x1800ca1bd  jz      loc_1800CA24F
0x1800ca1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca1ca  cmp     rcx, rsi
0x1800ca1cd  jz      short loc_1800CA1ED
0x1800ca1cf  test    byte ptr [rcx+1Ch], 1
0x1800ca1d3  jz      short loc_1800CA1ED
0x1800ca1d5  mov     rcx, [rcx+10h]
0x1800ca1d9  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca1e0  mov     edx, 382h
0x1800ca1e5  mov     r9d, ebx
0x1800ca1e8  call    WPP_SF_d
0x1800ca1ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca1f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca1f9  test    al, al
0x1800ca1fb  jz      short loc_1800CA214
0x1800ca1fd  mov     r9, r13
0x1800ca200  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca207  mov     r8d, 21BDh
0x1800ca20d  mov     ecx, ebx
0x1800ca20f  call    TraceVpnWppErrorW32Impl
0x1800ca214  mov     r8d, ebx
0x1800ca217  lea     rdx, aRasgetentrypro_0; "RasGetEntryProperties"
0x1800ca21e  mov     rcx, r13
0x1800ca221  call    VpnReportError
0x1800ca226  lea     rbp, WPP_GLOBAL_Control
0x1800ca22d  mov     rcx, [rsp+58h+arg_18]
0x1800ca232  test    rcx, rcx
0x1800ca235  jz      loc_1800CA51D
0x1800ca23b  call    cs:__imp_RasFreeEntryAdvancedProperties
0x1800ca241  mov     [rsp+58h+arg_18], 0
0x1800ca24a  jmp     loc_1800CA51D
0x1800ca24f  mov     ecx, [rsp+58h+arg_10]
0x1800ca253  call    VpnAlloc
0x1800ca258  mov     rsi, rax
0x1800ca25b  test    rax, rax
0x1800ca25e  jnz     loc_1800CA319
0x1800ca264  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca26b  lea     rsi, WPP_GLOBAL_Control
0x1800ca272  lea     ebx, [rax+0Eh]
0x1800ca275  cmp     rcx, rsi
0x1800ca278  jz      short loc_1800CA298
0x1800ca27a  test    byte ptr [rcx+1Ch], 1
0x1800ca27e  jz      short loc_1800CA298
0x1800ca280  mov     rcx, [rcx+10h]
0x1800ca284  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca28b  mov     edx, 383h
0x1800ca290  mov     r9d, ebx
0x1800ca293  call    WPP_SF_d
0x1800ca298  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca29f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca2a4  test    al, al
0x1800ca2a6  jz      short loc_1800CA2BF
0x1800ca2a8  mov     r9, r13
0x1800ca2ab  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca2b2  mov     r8d, 21C4h
0x1800ca2b8  mov     ecx, ebx
0x1800ca2ba  call    TraceVpnWppErrorW32Impl
0x1800ca2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca2c6  cmp     rcx, rsi
0x1800ca2c9  jz      short loc_1800CA2E9
0x1800ca2cb  test    byte ptr [rcx+1Ch], 1
0x1800ca2cf  jz      short loc_1800CA2E9
0x1800ca2d1  mov     rcx, [rcx+10h]
0x1800ca2d5  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca2dc  mov     edx, 384h
0x1800ca2e1  mov     r9d, ebx
0x1800ca2e4  call    WPP_SF_d
0x1800ca2e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca2f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca2f5  test    al, al
0x1800ca2f7  jz      loc_1800CA226
0x1800ca2fd  mov     r9, r13
0x1800ca300  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca307  mov     r8d, 21C6h
0x1800ca30d  mov     ecx, ebx
0x1800ca30f  call    TraceVpnWppErrorW32Impl
0x1800ca314  jmp     loc_1800CA226
0x1800ca319  mov     [rsp+58h+var_30], 0; LPDWORD
0x1800ca322  lea     r9, [rsp+58h+arg_10]; LPDWORD
0x1800ca327  mov     r8, rsi; struct tagRASENTRYW *
0x1800ca32a  mov     [rsp+58h+var_38], 0; LPBYTE
0x1800ca333  mov     rdx, rdi; LPCWSTR
0x1800ca336  mov     dword ptr [rax], 1A44h
0x1800ca33c  mov     rcx, rbp; LPCWSTR
0x1800ca33f  call    cs:__imp_RasGetEntryPropertiesW
0x1800ca345  mov     ebx, eax
0x1800ca347  test    eax, eax
0x1800ca349  jz      short loc_1800CA3AF
0x1800ca34b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca352  lea     rbp, WPP_GLOBAL_Control
0x1800ca359  cmp     rcx, rbp
0x1800ca35c  jz      short loc_1800CA37C
0x1800ca35e  test    byte ptr [rcx+1Ch], 1
0x1800ca362  jz      short loc_1800CA37C
0x1800ca364  mov     rcx, [rcx+10h]
0x1800ca368  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca36f  mov     edx, 385h
0x1800ca374  mov     r9d, eax
0x1800ca377  call    WPP_SF_d
0x1800ca37c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca383  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca388  test    al, al
0x1800ca38a  jz      short loc_1800CA3A3
0x1800ca38c  mov     r9, r13
0x1800ca38f  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca396  mov     r8d, 21D0h
0x1800ca39c  mov     ecx, ebx
0x1800ca39e  call    TraceVpnWppErrorW32Impl
0x1800ca3a3  lea     rdx, aRasgetentrypro_1; "RasGetEntryPropertiesW"
0x1800ca3aa  jmp     loc_1800CA4F3
0x1800ca3af  cmp     dword ptr [rsi+0DA8h], 2
0x1800ca3b6  jz      loc_1800CA477
0x1800ca3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca3c3  lea     rbp, WPP_GLOBAL_Control
0x1800ca3ca  mov     ebx, 0Dh
0x1800ca3cf  cmp     rcx, rbp
0x1800ca3d2  jz      short loc_1800CA3F6
0x1800ca3d4  test    byte ptr [rcx+1Ch], 1
0x1800ca3d8  jz      short loc_1800CA3F6
0x1800ca3da  mov     rcx, [rcx+10h]
0x1800ca3de  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca3e5  mov     edx, 386h
0x1800ca3ea  mov     dword ptr [rsp+58h+var_38], ebx
0x1800ca3ee  mov     r9, rdi
0x1800ca3f1  call    WPP_SF_Sd
0x1800ca3f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca3fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca402  test    al, al
0x1800ca404  jz      short loc_1800CA41D
0x1800ca406  mov     r9, r13
0x1800ca409  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca410  mov     r8d, 21D7h
0x1800ca416  mov     ecx, ebx
0x1800ca418  call    TraceVpnWppErrorW32Impl
0x1800ca41d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca424  cmp     rcx, rbp
0x1800ca427  jz      short loc_1800CA447
0x1800ca429  test    byte ptr [rcx+1Ch], 1
0x1800ca42d  jz      short loc_1800CA447
0x1800ca42f  mov     rcx, [rcx+10h]
0x1800ca433  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca43a  mov     edx, 387h
0x1800ca43f  mov     r9d, ebx
0x1800ca442  call    WPP_SF_d
0x1800ca447  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca44e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca453  test    al, al
0x1800ca455  jz      loc_1800CA4FE
0x1800ca45b  mov     r9, r13
0x1800ca45e  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca465  mov     r8d, 21D8h
0x1800ca46b  mov     ecx, ebx
0x1800ca46d  call    TraceVpnWppErrorW32Impl
0x1800ca472  jmp     loc_1800CA4FE
0x1800ca477  lea     r9, [rsp+58h+arg_18]
0x1800ca47c  mov     r8d, 0BE0h
0x1800ca482  mov     rdx, rdi
0x1800ca485  mov     rcx, rbp
0x1800ca488  call    cs:__imp_RasGetEntryAdvancedProperties
0x1800ca48e  mov     ebx, eax
0x1800ca490  test    eax, eax
0x1800ca492  jz      short loc_1800CA50B
0x1800ca494  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca49b  lea     rbp, WPP_GLOBAL_Control
0x1800ca4a2  cmp     rcx, rbp
0x1800ca4a5  jz      short loc_1800CA4C5
0x1800ca4a7  test    byte ptr [rcx+1Ch], 1
0x1800ca4ab  jz      short loc_1800CA4C5
0x1800ca4ad  mov     rcx, [rcx+10h]
0x1800ca4b1  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca4b8  mov     edx, 388h
0x1800ca4bd  mov     r9d, eax
0x1800ca4c0  call    WPP_SF_d
0x1800ca4c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca4cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca4d1  test    al, al
0x1800ca4d3  jz      short loc_1800CA4EC
0x1800ca4d5  mov     r9, r13
0x1800ca4d8  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca4df  mov     r8d, 21E0h
0x1800ca4e5  mov     ecx, ebx
0x1800ca4e7  call    TraceVpnWppErrorW32Impl
0x1800ca4ec  lea     rdx, aRasgetentryadv_0; "RasGetEntryAdvancedProperties"
0x1800ca4f3  mov     r8d, ebx
0x1800ca4f6  mov     rcx, r13
0x1800ca4f9  call    VpnReportError
0x1800ca4fe  mov     rcx, rsi; lpMem
0x1800ca501  call    MprCommonFree
0x1800ca506  jmp     loc_1800CA22D
0x1800ca50b  mov     rax, [rsp+58h+arg_18]
0x1800ca510  lea     rbp, WPP_GLOBAL_Control
0x1800ca517  mov     [r15], rax
0x1800ca51a  mov     [r14], rsi
0x1800ca51d  test    ebx, ebx
0x1800ca51f  jns     short loc_1800CA572
0x1800ca521  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca528  cmp     rcx, rbp
0x1800ca52b  jz      short loc_1800CA54B
0x1800ca52d  test    byte ptr [rcx+1Ch], 8
0x1800ca531  jz      short loc_1800CA54B
0x1800ca533  mov     rcx, [rcx+10h]
0x1800ca537  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800ca53e  mov     edx, 389h
0x1800ca543  mov     r9d, ebx
0x1800ca546  call    WPP_SF_d
0x1800ca54b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800ca552  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ca557  test    al, al
0x1800ca559  jz      short loc_1800CA572
0x1800ca55b  mov     r9, r13
0x1800ca55e  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ca565  mov     r8d, 21F7h
0x1800ca56b  mov     ecx, ebx
0x1800ca56d  call    TraceVpnWppErrorHRImpl
0x1800ca572  mov     rbp, [rsp+58h+arg_8]
0x1800ca577  mov     eax, ebx
0x1800ca579  mov     rbx, [rsp+58h+arg_0]
0x1800ca57e  add     rsp, 30h
0x1800ca582  pop     r15
0x1800ca584  pop     r14
0x1800ca586  pop     r13
0x1800ca588  pop     rdi
0x1800ca589  pop     rsi
0x1800ca58a  retn
```
