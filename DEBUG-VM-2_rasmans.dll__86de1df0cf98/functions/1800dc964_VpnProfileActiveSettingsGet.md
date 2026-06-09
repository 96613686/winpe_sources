# VpnProfileActiveSettingsGet

- ea: `0x1800dc964`
- end: `0x1800dde25`
- name: `VpnProfileActiveSettingsGet`
- size: `5313`
- prototype: `__int64 __fastcall(LPCWSTR, LPCWSTR)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c945c`
- `0x1800d4f20`
- `0x1800de2d8`

## callees

- `0x180005e34`
- `0x180005e74`
- `0x18000e650`
- `0x180065328`
- `0x180065f10`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800ca0e4`
- `0x1800cc4e4`
- `0x1800d77e0`
- `0x1800d80ec`
- `0x1800dc76c`
- `0x1800dc964`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e2294`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e71ee`

## import_xrefs

- `msvcrt!tolower` at `0x1800dd858`
- `msvcrt!tolower` at `0x1800ddb29`
- `msvcrt!tolower` at `0x1800dd858`
- `msvcrt!tolower` at `0x1800ddb29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dcab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dd992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dcab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dd992`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dcac5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dd9a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dcac5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dd9a4`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800dd2e4`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800dd2e4`
- `fwpuclnt!FwpmGetAppIdFromFileName0` at `0x1800dd016`
- `fwpuclnt!FwpmGetAppIdFromFileName0` at `0x1800dd016`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800dd5b6`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800dd5b6`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dcbde`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dcdb4`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dcbde`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dcdb4`

## string_xrefs

- `0x1800dca7a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dcb25`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dcbc7`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dd8bb`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ddb49`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800ddc21`: `VpnStringCopy for szDnsSuffix`

## pseudocode

```c
__int64 __fastcall VpnProfileActiveSettingsGet(LPCWSTR a1, const char *a2, __int64 a3, struct tagRASENTRYADVANCED **a4)
{
  const char *v8; // rax
  const char *v9; // r9
  unsigned int EntryByName; // eax
  struct tagRASENTRYADVANCED *v11; // r15
  unsigned int v12; // edi
  struct tagRASENTRYADVANCED *v13; // rbx
  HANDLE ProcessHeap; // rax
  struct tagRASENTRYADVANCED *v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  struct tagRASENTRYADVANCED *v20; // r9
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  struct tagRASENTRYW *v24; // r8
  unsigned int v25; // eax
  int v26; // eax
  struct _LIST_ENTRY *v27; // rcx
  struct tagRASENTRYADVANCED *v28; // r8
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  WCHAR *v32; // rcx
  DWORD AppIdFromFileName0; // eax
  unsigned int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  unsigned __int16 *v39; // rdx
  __int64 v40; // rax
  void *v41; // rcx
  __int64 v42; // rdx
  UINT32 size; // ecx
  __int64 v44; // rax
  __int64 v45; // rdx
  void *v46; // rcx
  _WORD *v47; // rax
  __int64 v48; // r8
  unsigned __int64 v49; // rbx
  __int64 v50; // rax
  struct tagRASENTRYADVANCED *v51; // rax
  _WORD *v52; // rdx
  unsigned __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  _WORD *v59; // rcx
  bool v60; // zf
  _WORD *v61; // rcx
  unsigned int v62; // eax
  struct tagRASENTRYADVANCED *v63; // rdi
  unsigned int v64; // r15d
  struct tagRASENTRYADVANCED *v65; // r12
  __int64 v66; // rsi
  __int128 *v67; // rcx
  __int64 v68; // r8
  _OWORD *v69; // rax
  __int64 v70; // rdx
  __int128 v71; // xmm0
  __int64 v72; // r13
  __int64 v73; // r15
  __int64 v74; // rbx
  unsigned int v75; // eax
  __int64 v76; // rax
  HANDLE v77; // rax
  LPVOID v78; // rax
  unsigned __int16 *v79; // r8
  int v80; // eax
  unsigned int v81; // ebx
  int v82; // eax
  unsigned int v83; // ecx
  unsigned __int16 *v84; // r8
  __int64 v85; // rsi
  unsigned __int16 *v86; // r12
  unsigned int v87; // esi
  int v88; // eax
  unsigned int v89; // ebx
  int v90; // eax
  unsigned int v91; // ecx
  struct tagRASENTRYADVANCED *v92; // rsi
  struct tagRASENTRYADVANCED *v93; // rdx
  LPCWSTR v94; // rsi
  unsigned int v95; // eax
  unsigned int ExemptionNrptRules; // eax
  int v97; // [rsp+30h] [rbp-50h]
  int v98; // [rsp+34h] [rbp-4Ch]
  unsigned int v99; // [rsp+34h] [rbp-4Ch]
  unsigned int v100; // [rsp+34h] [rbp-4Ch]
  int v101; // [rsp+34h] [rbp-4Ch]
  struct tagRASENTRYADVANCED *v102; // [rsp+38h] [rbp-48h]
  struct tagRASENTRYADVANCED *v103; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v104; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v105; // [rsp+50h] [rbp-30h] BYREF
  struct tagRASENTRYW *v106; // [rsp+58h] [rbp-28h] BYREF
  void *Src; // [rsp+60h] [rbp-20h]
  FWP_BYTE_BLOB *appId; // [rsp+68h] [rbp-18h] BYREF
  __int64 v109; // [rsp+70h] [rbp-10h]
  LPVOID lpMem; // [rsp+78h] [rbp-8h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v8 = a2;
    LODWORD(v9) = (_DWORD)a1;
    if ( !a2 )
      v8 = L"<NULL>";
    if ( !a1 )
      v9 = L"<NULL>";
    WPP_SF_SS(
      WPP_GLOBAL_Control[1].Flink,
      906,
      (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      (_DWORD)v9,
      (__int64)v8);
  }
  v106 = 0;
  Src = 0;
  v105 = 0;
  v103 = 0;
  appId = 0;
  *a4 = 0;
  EntryByName = VpnProfileGetEntryByName(a1, (LPCWSTR)a2, a3, &v106, &v103);
  v11 = v103;
  v12 = EntryByName;
  v97 = EntryByName;
  lpMem = v106;
  v102 = v103;
  if ( EntryByName )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 907, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, EntryByName);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8732,
        "VpnProfileActiveSettingsGet");
    v13 = 0;
    VpnReportError("VpnProfileActiveSettingsGet", "VpnProfileGetEntryByName", v12);
    goto LABEL_314;
  }
  ProcessHeap = GetProcessHeap();
  v15 = (struct tagRASENTRYADVANCED *)HeapAlloc(ProcessHeap, 8u, 0x88u);
  v103 = v15;
  v13 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 908, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8739,
        "VpnProfileActiveSettingsGet");
    v12 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 909, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_174;
    v16 = 8741;
LABEL_26:
    v17 = 14;
LABEL_27:
    TraceVpnWppErrorW32Impl(
      v17,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v16,
      "VpnProfileActiveSettingsGet");
    goto LABEL_174;
  }
  if ( (*((_BYTE *)v11 + 4) & 0x40) != 0 )
    *((_DWORD *)v15 + 32) = 1;
  v18 = *((_QWORD *)v11 + 18);
  if ( v18 )
  {
    v19 = AppContainerDeriveSidFromMoniker(v18 + 4, a3);
    v97 = v19;
    v12 = v19;
    if ( v19 >= 0 )
    {
      v12 = 0;
      v97 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 910, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v19);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          v12,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8752,
          "VpnProfileActiveSettingsGet");
      if ( (v12 & 0x1FFF0000) == 0x70000 )
      {
        v12 = (unsigned __int16)v12;
        v97 = (unsigned __int16)v12;
      }
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 911, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          goto LABEL_174;
        v16 = 8753;
LABEL_45:
        v17 = v12;
        goto LABEL_27;
      }
    }
  }
  v20 = v102;
  v21 = *((_DWORD *)v102 + 26);
  if ( v21 )
  {
    v22 = VpnAlloc((unsigned int)(8 * v21));
    *((_QWORD *)v13 + 4) = v22;
    if ( !v22 )
    {
      v12 = 14;
      v97 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 912, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          14,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8764,
          "VpnProfileActiveSettingsGet");
    }
    if ( !*((_QWORD *)v13 + 4) )
    {
      v12 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 913, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_174;
      v16 = 8766;
      goto LABEL_26;
    }
    v20 = v102;
    v23 = 0;
    v98 = 0;
    v24 = (struct tagRASENTRYW *)*((_QWORD *)v102 + 14);
    v25 = *((_DWORD *)v102 + 26);
    v106 = v24;
    if ( v25 )
    {
      do
      {
        v97 = AppContainerDeriveSidFromMoniker(&v24->dwCountryID, *((_QWORD *)v13 + 4) + 8 * v23);
        v12 = v97;
        if ( v97 >= 0 )
        {
          v12 = 0;
          v97 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              914,
              &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              (unsigned int)v97);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorHRImpl(
              (unsigned int)v97,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              8772,
              "VpnProfileActiveSettingsGet");
          if ( (v97 & 0x1FFF0000) == 0x70000 )
          {
            v12 = (unsigned __int16)v97;
            v97 = (unsigned __int16)v97;
          }
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 915, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v12,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                8773,
                "VpnProfileActiveSettingsGet");
            goto LABEL_174;
          }
        }
        v24 = (struct tagRASENTRYW *)&v106->szScript[102];
        v20 = v102;
        v23 = (unsigned int)(v98 + 1);
        v106 = (struct tagRASENTRYW *)((char *)v106 + 536);
        v98 = v23;
        v25 = *((_DWORD *)v102 + 26);
      }
      while ( (unsigned int)v23 < v25 );
    }
    *((_DWORD *)v13 + 6) = v25;
  }
  v26 = *((_DWORD *)lpMem + 873);
  if ( !v26 )
    v26 = 300;
  *((_DWORD *)v13 + 31) = v26;
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      916,
      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      *((unsigned int *)v20 + 30));
    v27 = WPP_GLOBAL_Control;
  }
  v28 = v102;
  v29 = *((_DWORD *)v102 + 30);
  if ( !v29 )
  {
LABEL_157:
    v47 = (_WORD *)*((_QWORD *)v28 + 17);
    if ( !v47 )
    {
LABEL_193:
      if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v27[1].Blink) & 4) != 0 )
        WPP_SF_d(v27[1].Flink, 929, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, *((unsigned int *)v28 + 42));
      v55 = *((unsigned int *)v102 + 42);
      if ( (_DWORD)v55 )
      {
        v56 = VpnAlloc(520 * v55);
        *((_QWORD *)v13 + 9) = v56;
        if ( !v56 )
        {
          v12 = 14;
          v97 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 930, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              14,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              8909,
              "VpnProfileActiveSettingsGet");
        }
        v57 = *((_QWORD *)v13 + 9);
        if ( !v57 )
        {
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 931, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v16 = 8911;
          goto LABEL_26;
        }
        v62 = *((_DWORD *)v102 + 42);
        if ( v62 )
        {
          v63 = v102;
          v64 = 0;
          v65 = v103;
          v100 = 0;
          v66 = *((_QWORD *)v102 + 22);
          do
          {
            v67 = (__int128 *)v66;
            v68 = 520LL * v64;
            v69 = (_OWORD *)(v68 + v57);
            v70 = 2;
            do
            {
              v71 = *v67;
              v67 += 8;
              *v69 = v71;
              v69 += 8;
              *(v69 - 7) = *(v67 - 7);
              *(v69 - 6) = *(v67 - 6);
              *(v69 - 5) = *(v67 - 5);
              *(v69 - 4) = *(v67 - 4);
              *(v69 - 3) = *(v67 - 3);
              *(v69 - 2) = *(v67 - 2);
              *(v69 - 1) = *(v67 - 1);
              --v70;
            }
            while ( v70 );
            v57 = *((_QWORD *)v65 + 9);
            if ( *(_WORD *)(v68 + v57) )
            {
              LODWORD(v72) = 0;
              v73 = 520LL * v64;
              do
              {
                v74 = v73 + 2LL * (unsigned int)v72;
                v72 = (unsigned int)(v72 + 1);
                *(_WORD *)(v74 + *((_QWORD *)v65 + 9)) = tolower(*(unsigned __int16 *)(v74 + v57));
                v57 = *((_QWORD *)v65 + 9);
              }
              while ( *(_WORD *)(v73 + 2 * v72 + v57) );
              v64 = v100;
              v63 = v102;
            }
            v62 = *((_DWORD *)v63 + 42);
            ++v64;
            v66 = *(_QWORD *)(v66 + 512);
            v100 = v64;
          }
          while ( v64 < v62 );
          v12 = v97;
          v13 = v103;
        }
        *((_DWORD *)v13 + 16) = v62;
      }
      v75 = *((_DWORD *)v102 + 38);
      if ( v75 )
      {
        v76 = VpnAlloc(8LL * v75);
        *((_QWORD *)v13 + 11) = v76;
        if ( !v76 )
        {
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 932, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              14,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              8937,
              "VpnProfileActiveSettingsGet");
        }
        if ( *((_QWORD *)v13 + 11) )
        {
          v77 = GetProcessHeap();
          v78 = HeapAlloc(v77, 8u, 0x18u);
          *((_QWORD *)v13 + 13) = v78;
          if ( !v78 )
          {
            v12 = 14;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 934, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                14,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                8945,
                "VpnProfileActiveSettingsGet");
          }
          if ( *((_QWORD *)v13 + 13) )
          {
            v101 = 0;
            v79 = (unsigned __int16 *)*((_QWORD *)v102 + 20);
            v105 = v79;
            if ( *((_DWORD *)v102 + 38) )
            {
              while ( 1 )
              {
                v80 = VpnStringCopy(v79);
                v81 = v80;
                if ( v80 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control[1].Flink,
                      936,
                      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                      (unsigned int)v80);
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                    TraceVpnWppErrorHRImpl(
                      v81,
                      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                      8953,
                      "VpnProfileActiveSettingsGet");
                  v82 = v81 & 0x1FFF0000;
                  if ( (v81 & 0x1FFF0000) == 0x70000 )
                  {
                    v83 = (unsigned __int16)v81;
                    v82 = 458752;
                  }
                  else
                  {
                    v83 = v81;
                  }
                  if ( v83 )
                    break;
                }
                v84 = v105;
                v85 = 0;
                if ( *v105 )
                {
                  v86 = v105;
                  do
                  {
                    v86[v85] = tolower(v86[v85]);
                    v85 = (unsigned int)(v85 + 1);
                  }
                  while ( v86[v85] );
                  v84 = v105;
                }
                v79 = (unsigned __int16 *)*((_QWORD *)v84 + 64);
                v13 = v103;
                v105 = v79;
                if ( (unsigned int)++v101 >= *((_DWORD *)v102 + 38) )
                  goto LABEL_268;
              }
              if ( v82 == 458752 )
                v81 = (unsigned __int16)v81;
              VpnReportError("VpnProfileActiveSettingsGet", "VpnStringCopy for szDnsSuffix", v81);
              v13 = v103;
            }
            else
            {
LABEL_268:
              v87 = 0;
              while ( 1 )
              {
                v88 = VpnStringBuild(*((_QWORD *)v13 + 13) + 8LL * v87, (&g_ExemptionEntry)[v87], v79);
                v89 = v88;
                if ( v88 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control[1].Flink,
                      937,
                      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                      (unsigned int)v88);
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                    TraceVpnWppErrorHRImpl(
                      v89,
                      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                      8970,
                      "VpnProfileActiveSettingsGet");
                  v90 = v89 & 0x1FFF0000;
                  if ( (v89 & 0x1FFF0000) == 0x70000 )
                  {
                    v91 = (unsigned __int16)v89;
                    v90 = 458752;
                  }
                  else
                  {
                    v91 = v89;
                  }
                  if ( v91 )
                    break;
                }
                v13 = v103;
                if ( ++v87 >= 3 )
                {
                  v92 = v102;
                  *((_DWORD *)v103 + 20) = *((_DWORD *)v102 + 38);
                  *((_DWORD *)v13 + 24) = 3;
                  goto LABEL_289;
                }
                v79 = v105;
              }
              if ( v90 == 458752 )
                v89 = (unsigned __int16)v89;
              VpnReportError("VpnProfileActiveSettingsGet", "VpnStringBuild for szDnsSuffix", v89);
              v13 = v103;
            }
LABEL_314:
            if ( v12 )
              goto LABEL_174;
            goto LABEL_175;
          }
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 935, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v16 = 8947;
        }
        else
        {
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 933, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v16 = 8939;
        }
        goto LABEL_26;
      }
      v92 = v102;
LABEL_289:
      if ( *((_DWORD *)v92 + 22) )
      {
        v93 = v92;
        v94 = (LPCWSTR)a2;
        v95 = int_VpnProfileCopyNrptRules(a2, v93, v13);
        v12 = v95;
        if ( v95 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 938, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v95);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              v12,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              8981,
              "VpnProfileActiveSettingsGet");
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 939, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v16 = 8982;
          goto LABEL_45;
        }
        ExemptionNrptRules = int_VpnProfileCreateExemptionNrptRules(v13);
        v12 = ExemptionNrptRules;
        if ( ExemptionNrptRules )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              940,
              &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              ExemptionNrptRules);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              v12,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              8985,
              "VpnProfileActiveSettingsGet");
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 941, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            goto LABEL_174;
          v16 = 8986;
          goto LABEL_45;
        }
      }
      else
      {
        v94 = (LPCWSTR)a2;
      }
      *((_DWORD *)v13 + 33) = ProfileIsLockDown(v94, a1);
      *a4 = v13;
      goto LABEL_314;
    }
    v48 = 0x7FFFFFFF;
    do
    {
      if ( !*v47 )
        break;
      ++v47;
      --v48;
    }
    while ( v48 );
    v49 = 2 * ((0x7FFFFFFF - v48) & ((unsigned __int128)-(__int128)(unsigned __int64)v48 >> 64) & -(__int64)(v48 != 0))
        + 2;
    v50 = VpnAlloc(v49);
    *((_QWORD *)v103 + 7) = v50;
    if ( !v50 )
    {
      v12 = 14;
      v97 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 927, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          14,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8893,
          "VpnProfileActiveSettingsGet");
    }
    v51 = v103;
    v52 = (_WORD *)*((_QWORD *)v103 + 7);
    if ( !v52 )
    {
      v12 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 928, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          14,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8895,
          "VpnProfileActiveSettingsGet");
      v13 = v103;
      goto LABEL_174;
    }
    v54 = v49 >> 1;
    if ( v54 )
    {
      if ( v54 <= 0x7FFFFFFF )
      {
        v58 = 2147483646;
        v59 = (_WORD *)*((_QWORD *)v102 + 17);
        do
        {
          if ( !v58 )
            break;
          if ( !*v59 )
            break;
          *v52++ = *v59++;
          --v58;
          --v54;
        }
        while ( v54 );
        v60 = v54 == 0;
        v61 = v52 - 1;
        v13 = v103;
        if ( !v60 )
          v61 = v52;
        *v61 = 0;
        goto LABEL_192;
      }
      *v52 = 0;
    }
    v13 = v51;
LABEL_192:
    v27 = WPP_GLOBAL_Control;
    v28 = v102;
    goto LABEL_193;
  }
  v30 = VpnAlloc((unsigned int)(16 * v29));
  *((_QWORD *)v13 + 6) = v30;
  if ( !v30 )
  {
    v12 = 14;
    v97 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 917, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8799,
        "VpnProfileActiveSettingsGet");
  }
  if ( !*((_QWORD *)v13 + 6) )
  {
    v12 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 918, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_174;
    v16 = 8801;
    goto LABEL_26;
  }
  v28 = v102;
  v31 = 0;
  v104 = 0;
  v99 = 0;
  v32 = (WCHAR *)*((_QWORD *)v102 + 16);
  v106 = (struct tagRASENTRYW *)v32;
  if ( !*((_DWORD *)v102 + 30) )
  {
LABEL_156:
    *((_DWORD *)v13 + 10) = v31;
    v27 = WPP_GLOBAL_Control;
    goto LABEL_157;
  }
  while ( 1 )
  {
    AppIdFromFileName0 = FwpmGetAppIdFromFileName0(v32 + 4, &appId);
    v97 = AppIdFromFileName0;
    v12 = AppIdFromFileName0;
    if ( !AppIdFromFileName0 )
      break;
    if ( AppIdFromFileName0 - 2 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          919,
          &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
          v99,
          AppIdFromFileName0);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v12,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          8812,
          "VpnProfileActiveSettingsGet");
      v34 = int_ConvertClassicAppPathToDevicePath((LPCWSTR)&v106->dwCountryID, &v105);
      v97 = v34;
      v12 = v34;
      if ( v34 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control[1].Flink,
            922,
            (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
            (_DWORD)v106 + 8,
            v34);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v12,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            8843,
            "VpnProfileActiveSettingsGet");
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 923, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v12,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            8844,
            "VpnProfileActiveSettingsGet");
        Src = v105;
        goto LABEL_174;
      }
      v35 = -1;
      Src = v105;
      do
        ++v35;
      while ( v105[v35] );
      v36 = *((_QWORD *)v13 + 6);
      v37 = (unsigned __int16 *)(16LL * v104);
      v105 = v37;
      *(_DWORD *)((char *)v37 + v36) = 2 * v35 + 2;
      v38 = VpnAlloc(*(unsigned int *)((char *)v37 + *((_QWORD *)v13 + 6)));
      v39 = v105;
      *(_QWORD *)((char *)v105 + *((_QWORD *)v13 + 6) + 8) = v38;
      if ( !*(_QWORD *)((char *)v39 + *((_QWORD *)v13 + 6) + 8) )
      {
        v12 = 14;
        v97 = 14;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 920, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            14,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            8825,
            "VpnProfileActiveSettingsGet");
        v39 = v105;
      }
      v40 = *((_QWORD *)v13 + 6);
      v41 = *(void **)((char *)v39 + v40 + 8);
      if ( !v41 )
      {
        v12 = 14;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 921, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v16 = 8829;
          goto LABEL_26;
        }
        goto LABEL_174;
      }
      memcpy_0(v41, Src, *(unsigned int *)((char *)v39 + v40));
      MprCommonFree(Src);
      Src = 0;
      v105 = 0;
      goto LABEL_124;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_Sd(
        WPP_GLOBAL_Control[1].Flink,
        924,
        (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (_DWORD)v106 + 8,
        AppIdFromFileName0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8853,
        "VpnProfileActiveSettingsGet");
    v31 = v104;
LABEL_105:
    v28 = v102;
    if ( ++v99 >= *((_DWORD *)v102 + 30) )
      goto LABEL_156;
    v32 = &v106->szScript[102];
    v106 = (struct tagRASENTRYW *)((char *)v106 + 536);
  }
  v42 = *((_QWORD *)v13 + 6);
  size = appId->size;
  v109 = 16LL * v104;
  *(_DWORD *)(v109 + v42) = size;
  v44 = VpnAlloc(appId->size);
  v45 = v109;
  *(_QWORD *)(*((_QWORD *)v13 + 6) + v109 + 8) = v44;
  if ( !*(_QWORD *)(*((_QWORD *)v13 + 6) + v45 + 8) )
  {
    v12 = 14;
    v97 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 925, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        8868,
        "VpnProfileActiveSettingsGet");
    v45 = v109;
  }
  v46 = *(void **)(*((_QWORD *)v13 + 6) + v45 + 8);
  if ( v46 )
  {
    memcpy_0(v46, appId->data, appId->size);
    FwpmFreeMemory0((void **)&appId);
    appId = 0;
LABEL_124:
    v31 = ++v104;
    goto LABEL_105;
  }
  v12 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 926, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
  {
    v16 = 8872;
    goto LABEL_26;
  }
LABEL_174:
  VpnProfileActiveSettingsFree(v13);
LABEL_175:
  if ( Src )
    MprCommonFree(Src);
  if ( lpMem )
    MprCommonFree(lpMem);
  if ( v102 )
    RasFreeEntryAdvancedProperties(v102);
  if ( (v12 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 942, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        9018,
        "VpnProfileActiveSettingsGet");
  }
  return v12;
}

```

## disassembly

```asm
0x1800dc964  mov     rax, rsp
0x1800dc967  mov     [rax+18h], rbx
0x1800dc96b  mov     [rax+20h], r9
0x1800dc96f  mov     [rax+10h], rdx
0x1800dc973  mov     [rax+8], rcx
0x1800dc977  push    rbp
0x1800dc978  push    rsi
0x1800dc979  push    rdi
0x1800dc97a  push    r12
0x1800dc97c  push    r13
0x1800dc97e  push    r14
0x1800dc980  push    r15
0x1800dc982  mov     rbp, rsp
0x1800dc985  sub     rsp, 80h
0x1800dc98c  mov     r14, r9
0x1800dc98f  mov     rsi, r8
0x1800dc992  mov     rbx, rdx
0x1800dc995  mov     rdi, rcx
0x1800dc998  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc99f  lea     r13, WPP_GLOBAL_Control
0x1800dc9a6  xor     r12d, r12d
0x1800dc9a9  cmp     rcx, r13
0x1800dc9ac  jz      short loc_1800DC9E9
0x1800dc9ae  test    byte ptr [rcx+1Ch], 8
0x1800dc9b2  jz      short loc_1800DC9E9
0x1800dc9b4  mov     rcx, [rcx+10h]
0x1800dc9b8  lea     rdx, aNull_5; "<NULL>"
0x1800dc9bf  test    rbx, rbx
0x1800dc9c2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc9c9  mov     rax, rbx
0x1800dc9cc  mov     r9, rdi
0x1800dc9cf  cmovz   rax, rdx
0x1800dc9d3  test    rdi, rdi
0x1800dc9d6  mov     [rsp+80h+var_60], rax
0x1800dc9db  cmovz   r9, rdx
0x1800dc9df  mov     edx, 38Ah
0x1800dc9e4  call    WPP_SF_SS
0x1800dc9e9  mov     rax, r12
0x1800dc9ec  mov     [rbp+var_28], r12
0x1800dc9f0  mov     [rbp+Src], rax
0x1800dc9f4  lea     r9, [rbp+var_28]; struct tagRASENTRYW **
0x1800dc9f8  mov     [rbp+var_30], rax
0x1800dc9fc  mov     rdx, rbx; LPCWSTR
0x1800dc9ff  lea     rax, [rbp+var_40]
0x1800dca03  mov     [rbp+var_40], r12
0x1800dca07  mov     rcx, rdi; LPCWSTR
0x1800dca0a  mov     [rsp+80h+var_60], rax; struct tagRASENTRYADVANCED **
0x1800dca0f  mov     [rbp+appId], r12
0x1800dca13  mov     [r14], r12
0x1800dca16  call    ?VpnProfileGetEntryByName@@YAKPEBG0KPEAPEAUtagRASENTRYW@@PEAPEAUtagRASENTRYADVANCED@@@Z; VpnProfileGetEntryByName(ushort const *,ushort const *,ulong,tagRASENTRYW * *,tagRASENTRYADVANCED * *)
0x1800dca1b  mov     r15, [rbp+var_40]
0x1800dca1f  mov     edi, eax
0x1800dca21  mov     [rbp+var_50], eax
0x1800dca24  mov     rax, [rbp+var_28]
0x1800dca28  mov     [rbp+lpMem], rax
0x1800dca2c  mov     [rbp+var_48], r15
0x1800dca30  test    edi, edi
0x1800dca32  jz      short loc_1800DCAB1
0x1800dca34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dca3b  cmp     rcx, r13
0x1800dca3e  jz      short loc_1800DCA64
0x1800dca40  mov     r14d, 1
0x1800dca46  test    [rcx+1Ch], r14b
0x1800dca4a  jz      short loc_1800DCA64
0x1800dca4c  mov     rcx, [rcx+10h]
0x1800dca50  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dca57  mov     edx, 38Bh
0x1800dca5c  mov     r9d, edi
0x1800dca5f  call    WPP_SF_d
0x1800dca64  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dca6b  mov     rcx, r12
0x1800dca6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dca73  lea     r15, aVpnprofileacti_2; "VpnProfileActiveSettingsGet"
0x1800dca7a  lea     r13, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dca81  test    al, al
0x1800dca83  jz      short loc_1800DCA98
0x1800dca85  mov     r9, r15
0x1800dca88  mov     r8d, 221Ch
0x1800dca8e  mov     rdx, r13
0x1800dca91  mov     ecx, edi
0x1800dca93  call    TraceVpnWppErrorW32Impl
0x1800dca98  xor     ebx, ebx
0x1800dca9a  lea     rdx, aVpnprofilegete; "VpnProfileGetEntryByName"
0x1800dcaa1  mov     r8d, edi
0x1800dcaa4  mov     rcx, r15
0x1800dcaa7  call    VpnReportError
0x1800dcaac  jmp     loc_1800DDE11
0x1800dcab1  call    cs:__imp_GetProcessHeap
0x1800dcab7  mov     edx, 8; dwFlags
0x1800dcabc  mov     r8d, 88h; dwBytes
0x1800dcac2  mov     rcx, rax; hHeap
0x1800dcac5  call    cs:__imp_HeapAlloc
0x1800dcacb  xor     r10d, r10d
0x1800dcace  mov     [rbp+var_40], rax
0x1800dcad2  mov     rbx, rax
0x1800dcad5  test    rax, rax
0x1800dcad8  jnz     loc_1800DCB9E
0x1800dcade  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcae5  lea     esi, [rax+0Eh]
0x1800dcae8  lea     r14d, [rax+1]
0x1800dcaec  cmp     rcx, r13
0x1800dcaef  jz      short loc_1800DCB0F
0x1800dcaf1  test    [rcx+1Ch], r14b
0x1800dcaf5  jz      short loc_1800DCB0F
0x1800dcaf7  mov     rcx, [rcx+10h]
0x1800dcafb  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcb02  mov     edx, 38Ch
0x1800dcb07  mov     r9d, esi
0x1800dcb0a  call    WPP_SF_d
0x1800dcb0f  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dcb16  mov     rcx, r12
0x1800dcb19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcb1e  lea     r15, aVpnprofileacti_2; "VpnProfileActiveSettingsGet"
0x1800dcb25  lea     r13, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dcb2c  test    al, al
0x1800dcb2e  jz      short loc_1800DCB43
0x1800dcb30  mov     r9, r15
0x1800dcb33  mov     r8d, 2223h
0x1800dcb39  mov     rdx, r13
0x1800dcb3c  mov     ecx, esi
0x1800dcb3e  call    TraceVpnWppErrorW32Impl
0x1800dcb43  mov     edi, esi
0x1800dcb45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcb4c  lea     rax, WPP_GLOBAL_Control
0x1800dcb53  cmp     rcx, rax
0x1800dcb56  jz      short loc_1800DCB76
0x1800dcb58  test    [rcx+1Ch], r14b
0x1800dcb5c  jz      short loc_1800DCB76
0x1800dcb5e  mov     rcx, [rcx+10h]
0x1800dcb62  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcb69  mov     edx, 38Dh
0x1800dcb6e  mov     r9d, esi
0x1800dcb71  call    WPP_SF_d
0x1800dcb76  mov     rcx, r12
0x1800dcb79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcb7e  test    al, al
0x1800dcb80  jz      loc_1800DD579
0x1800dcb86  mov     r8d, 2225h
0x1800dcb8c  mov     ecx, esi
0x1800dcb8e  mov     r9, r15
0x1800dcb91  mov     rdx, r13
0x1800dcb94  call    TraceVpnWppErrorW32Impl
0x1800dcb99  jmp     loc_1800DD579
0x1800dcb9e  test    byte ptr [r15+4], 40h
0x1800dcba3  mov     r14d, 1
0x1800dcba9  jz      short loc_1800DCBB2
0x1800dcbab  mov     [rax+80h], r14d
0x1800dcbb2  mov     rcx, [r15+90h]
0x1800dcbb9  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dcbc0  lea     r15, aVpnprofileacti_2; "VpnProfileActiveSettingsGet"
0x1800dcbc7  lea     r13, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dcbce  test    rcx, rcx
0x1800dcbd1  jz      loc_1800DCCB0
0x1800dcbd7  add     rcx, 4
0x1800dcbdb  mov     rdx, rsi
0x1800dcbde  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1800dcbe4  xor     r10d, r10d
0x1800dcbe7  mov     [rbp+var_50], eax
0x1800dcbea  mov     edi, eax
0x1800dcbec  test    eax, eax
0x1800dcbee  jns     loc_1800DCCA9
0x1800dcbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcbfb  lea     rsi, WPP_GLOBAL_Control
0x1800dcc02  cmp     rcx, rsi
0x1800dcc05  jz      short loc_1800DCC25
0x1800dcc07  test    [rcx+1Ch], r14b
0x1800dcc0b  jz      short loc_1800DCC25
0x1800dcc0d  mov     rcx, [rcx+10h]
0x1800dcc11  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcc18  mov     edx, 38Eh
0x1800dcc1d  mov     r9d, eax
0x1800dcc20  call    WPP_SF_d
0x1800dcc25  mov     rcx, r12
0x1800dcc28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcc2d  xor     r10d, r10d
0x1800dcc30  test    al, al
0x1800dcc32  jz      short loc_1800DCC4A
0x1800dcc34  mov     r9, r15
0x1800dcc37  mov     r8d, 2230h
0x1800dcc3d  mov     rdx, r13
0x1800dcc40  mov     ecx, edi
0x1800dcc42  call    TraceVpnWppErrorHRImpl
0x1800dcc47  xor     r10d, r10d
0x1800dcc4a  mov     eax, edi
0x1800dcc4c  and     eax, 1FFF0000h
0x1800dcc51  cmp     eax, 70000h
0x1800dcc56  jnz     short loc_1800DCC5E
0x1800dcc58  movzx   edi, di
0x1800dcc5b  mov     [rbp+var_50], edi
0x1800dcc5e  test    edi, edi
0x1800dcc60  jz      short loc_1800DCCB0
0x1800dcc62  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcc69  cmp     rcx, rsi
0x1800dcc6c  jz      short loc_1800DCC8C
0x1800dcc6e  test    [rcx+1Ch], r14b
0x1800dcc72  jz      short loc_1800DCC8C
0x1800dcc74  mov     rcx, [rcx+10h]
0x1800dcc78  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcc7f  mov     edx, 38Fh
0x1800dcc84  mov     r9d, edi
0x1800dcc87  call    WPP_SF_d
0x1800dcc8c  mov     rcx, r12
0x1800dcc8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcc94  test    al, al
0x1800dcc96  jz      loc_1800DD579
0x1800dcc9c  mov     r8d, 2231h
0x1800dcca2  mov     ecx, edi
0x1800dcca4  jmp     loc_1800DCB8E
0x1800dcca9  mov     edi, r10d
0x1800dccac  mov     [rbp+var_50], r10d
0x1800dccb0  mov     r9, [rbp+var_48]
0x1800dccb4  mov     esi, 0Eh
0x1800dccb9  mov     eax, [r9+68h]
0x1800dccbd  test    eax, eax
0x1800dccbf  jz      loc_1800DCEC3
0x1800dccc5  shl     eax, 3
0x1800dccc8  mov     ecx, eax
0x1800dccca  call    VpnAlloc
0x1800dcccf  xor     r10d, r10d
0x1800dccd2  mov     [rbx+20h], rax
0x1800dccd6  test    rax, rax
0x1800dccd9  jnz     short loc_1800DCD36
0x1800dccdb  mov     edi, esi
0x1800dccdd  mov     [rbp+var_50], esi
0x1800dcce0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcce7  lea     rax, WPP_GLOBAL_Control
0x1800dccee  cmp     rcx, rax
0x1800dccf1  jz      short loc_1800DCD11
0x1800dccf3  test    [rcx+1Ch], r14b
0x1800dccf7  jz      short loc_1800DCD11
0x1800dccf9  mov     rcx, [rcx+10h]
0x1800dccfd  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcd04  mov     edx, 390h
0x1800dcd09  mov     r9d, esi
0x1800dcd0c  call    WPP_SF_d
0x1800dcd11  mov     rcx, r12
0x1800dcd14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcd19  xor     r10d, r10d
0x1800dcd1c  test    al, al
0x1800dcd1e  jz      short loc_1800DCD36
0x1800dcd20  mov     r9, r15
0x1800dcd23  mov     r8d, 223Ch
0x1800dcd29  mov     rdx, r13
0x1800dcd2c  mov     ecx, esi
0x1800dcd2e  call    TraceVpnWppErrorW32Impl
0x1800dcd33  xor     r10d, r10d
0x1800dcd36  cmp     [rbx+20h], r10
0x1800dcd3a  jnz     short loc_1800DCD8A
0x1800dcd3c  mov     edi, esi
0x1800dcd3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcd45  lea     rax, WPP_GLOBAL_Control
0x1800dcd4c  cmp     rcx, rax
0x1800dcd4f  jz      short loc_1800DCD6F
0x1800dcd51  test    [rcx+1Ch], r14b
0x1800dcd55  jz      short loc_1800DCD6F
0x1800dcd57  mov     rcx, [rcx+10h]
0x1800dcd5b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcd62  mov     edx, 391h
0x1800dcd67  mov     r9d, esi
0x1800dcd6a  call    WPP_SF_d
0x1800dcd6f  mov     rcx, r12
0x1800dcd72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dcd77  test    al, al
0x1800dcd79  jz      loc_1800DD579
0x1800dcd7f  mov     r8d, 223Eh
0x1800dcd85  jmp     loc_1800DCB8C
0x1800dcd8a  mov     r9, [rbp+var_48]
0x1800dcd8e  mov     ecx, r10d
0x1800dcd91  mov     [rbp+var_4C], ecx
0x1800dcd94  mov     r8, [r9+70h]
0x1800dcd98  mov     eax, [r9+68h]
0x1800dcd9c  mov     [rbp+var_28], r8
0x1800dcda0  test    eax, eax
0x1800dcda2  jz      loc_1800DCEC0
0x1800dcda8  mov     rax, [rbx+20h]
0x1800dcdac  lea     rdx, [rax+rcx*8]
0x1800dcdb0  lea     rcx, [r8+8]
0x1800dcdb4  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1800dcdba  xor     r10d, r10d
0x1800dcdbd  mov     [rbp+var_50], eax
0x1800dcdc0  mov     edi, eax
0x1800dcdc2  test    eax, eax
0x1800dcdc4  jns     loc_1800DCE91
0x1800dcdca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcdd1  lea     rax, WPP_GLOBAL_Control
0x1800dcdd8  cmp     rcx, rax
0x1800dcddb  jz      short loc_1800DCDFB
0x1800dcddd  test    [rcx+1Ch], r14b
0x1800dcde1  jz      short loc_1800DCDFB
0x1800dcde3  mov     rcx, [rcx+10h]
0x1800dcde7  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dcdee  mov     edx, 392h
0x1800dcdf3  mov     r9d, edi
0x1800dcdf6  call    WPP_SF_d
0x1800dcdfb  mov     rcx, r12
0x1800dcdfe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dce03  xor     r10d, r10d
0x1800dce06  test    al, al
0x1800dce08  jz      short loc_1800DCE20
0x1800dce0a  mov     r9, r15
  ... truncated ...
```
