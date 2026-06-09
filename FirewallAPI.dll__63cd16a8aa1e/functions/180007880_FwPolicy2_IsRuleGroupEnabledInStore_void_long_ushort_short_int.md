# FwPolicy2::IsRuleGroupEnabledInStore(void *,long,ushort *,short *,int)

- ea: `0x180007880`
- end: `0x1800088c1`
- name: `?IsRuleGroupEnabledInStore@FwPolicy2@@AEAAJPEAXJPEAGPEAFH@Z`
- size: `4161`
- prototype: `int(FwPolicy2 *__hidden this, void *, int, unsigned __int16 *, __int16 *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800069b0`
- `0x18000bcd0`

## callees

- `0x180005954`
- `0x180006910`
- `0x180007880`
- `0x180008b30`
- `0x180009080`
- `0x180009fb0`
- `0x18000acd4`
- `0x18000b8c0`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007b55`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007b55`
- `ntdll!EtwEventWrite` at `0x180007983`
- `ntdll!EtwEventWrite` at `0x180007a0e`
- `ntdll!EtwEventWrite` at `0x180007a5b`
- `ntdll!EtwEventWrite` at `0x180007add`
- `ntdll!EtwEventWrite` at `0x180007c08`
- `ntdll!EtwEventWrite` at `0x180007cb6`
- `ntdll!EtwEventWrite` at `0x180007ede`
- `ntdll!EtwEventWrite` at `0x180007f67`
- `ntdll!EtwEventWrite` at `0x180007fa5`
- `ntdll!EtwEventWrite` at `0x18000802f`
- `ntdll!EtwEventWrite` at `0x180008071`
- `ntdll!EtwEventWrite` at `0x1800080f7`
- `ntdll!EtwEventWrite` at `0x180008194`
- `ntdll!EtwEventWrite` at `0x1800081eb`
- `ntdll!EtwEventWrite` at `0x180007983`
- `ntdll!EtwEventWrite` at `0x180007a0e`
- `ntdll!EtwEventWrite` at `0x180007a5b`
- `ntdll!EtwEventWrite` at `0x180007add`
- `ntdll!EtwEventWrite` at `0x180007c08`
- `ntdll!EtwEventWrite` at `0x180007cb6`
- `ntdll!EtwEventWrite` at `0x180007ede`
- `ntdll!EtwEventWrite` at `0x180007f67`
- `ntdll!EtwEventWrite` at `0x180007fa5`
- `ntdll!EtwEventWrite` at `0x18000802f`
- `ntdll!EtwEventWrite` at `0x180008071`
- `ntdll!EtwEventWrite` at `0x1800080f7`
- `ntdll!EtwEventWrite` at `0x180008194`
- `ntdll!EtwEventWrite` at `0x1800081eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800079a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007a7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007c2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007f01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007fc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008095`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800079a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007a7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007c2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007f01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007fc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008095`
- `OLEAUT32!__imp_SysStringLen` at `0x180007b13`
- `OLEAUT32!__imp_SysStringLen` at `0x180007b13`
- `fwbase!FwBaseFree` at `0x180007cf7`
- `fwbase!FwBaseFree` at `0x180008636`
- `fwbase!FwBaseFree` at `0x1800087b8`
- `fwbase!FwBaseFree` at `0x180007cf7`
- `fwbase!FwBaseFree` at `0x180008636`
- `fwbase!FwBaseFree` at `0x1800087b8`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000795e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007d46`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007d96`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007de6`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007e69`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000795e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007d46`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007d96`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007de6`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180007e69`
- `fwbase!FwHResultToWindowsError` at `0x1800081c4`
- `fwbase!FwHResultToWindowsError` at `0x1800081c4`
- `fwbase!FwReportErrorAsWinError` at `0x18000816d`
- `fwbase!FwReportErrorAsWinError` at `0x18000816d`
- `fwbase!FwLoadIndirectString` at `0x18000858c`
- `fwbase!FwLoadIndirectString` at `0x18000858c`
- `fwbase!FwReportReturnError` at `0x1800082e5`
- `fwbase!FwReportReturnError` at `0x1800082f5`
- `fwbase!FwReportReturnError` at `0x18000844b`
- `fwbase!FwReportReturnError` at `0x180008619`
- `fwbase!FwReportReturnError` at `0x180008646`
- `fwbase!FwReportReturnError` at `0x180008688`
- `fwbase!FwReportReturnError` at `0x180008762`
- `fwbase!FwReportReturnError` at `0x18000879b`
- `fwbase!FwReportReturnError` at `0x1800082e5`
- `fwbase!FwReportReturnError` at `0x1800082f5`
- `fwbase!FwReportReturnError` at `0x18000844b`
- `fwbase!FwReportReturnError` at `0x180008619`
- `fwbase!FwReportReturnError` at `0x180008646`
- `fwbase!FwReportReturnError` at `0x180008688`
- `fwbase!FwReportReturnError` at `0x180008762`
- `fwbase!FwReportReturnError` at `0x18000879b`
- `fwbase!FwStringCopy` at `0x180008777`
- `fwbase!FwStringCopy` at `0x18000878c`
- `fwbase!FwStringCopy` at `0x180008777`
- `fwbase!FwStringCopy` at `0x18000878c`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800081bc`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800081bc`

## string_xrefs

- `0x180007b37`: `@FirewallAPI.dll,-`
- `0x18000815f`: `FWGetConfig`

## pseudocode

```c
__int64 __fastcall FwPolicy2::IsRuleGroupEnabledInStore(
        FwPolicy2 *this,
        void *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        __int16 *a5,
        unsigned int a6)
{
  unsigned int v8; // esi
  unsigned int i; // edi
  unsigned __int64 v10; // rbx
  int ProfileTypeFromProfileIndex; // esi
  signed int v12; // r15d
  FwPolicy2 *v13; // r11
  __int64 v14; // r10
  bool v15; // sf
  bool v16; // sf
  struct _tag_FW_RULE *v17; // r13
  unsigned int v18; // eax
  bool v19; // sf
  __int64 v20; // r8
  bool v21; // cc
  __int16 v22; // r12
  struct _tag_FW_RULE *j; // rbx
  __int64 v24; // rcx
  int v25; // edx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // edx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // edx
  int v32; // eax
  __int64 v33; // rbx
  int v34; // edi
  int v35; // r14d
  int k; // edx
  __int64 v37; // rcx
  __int64 v38; // rcx
  FwPolicy2 *v39; // r10
  FwPolicy2 *v40; // r10
  __int64 v41; // rcx
  unsigned int v42; // edi
  __int64 v43; // r8
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v47; // edx
  int v48; // r8d
  int v49; // edx
  int v50; // r8d
  int v51; // edx
  int v52; // eax
  int v53; // eax
  struct _tag_FW_RULE *v54; // rbx
  struct _tag_FW_RULE **v55; // rdi
  __int64 v56; // rdx
  unsigned int v57; // eax
  int v59; // [rsp+70h] [rbp-90h]
  struct _tag_FW_RULE *v60; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v61; // [rsp+80h] [rbp-80h] BYREF
  struct _tag_FW_RULE *v62; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v63[2]; // [rsp+90h] [rbp-70h] BYREF
  int *v64; // [rsp+98h] [rbp-68h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  int v66; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v67; // [rsp+ACh] [rbp-54h] BYREF
  int v68; // [rsp+B0h] [rbp-50h] BYREF
  int v69; // [rsp+B4h] [rbp-4Ch] BYREF
  int v70; // [rsp+B8h] [rbp-48h] BYREF
  int v71; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v72; // [rsp+C8h] [rbp-38h]
  _QWORD v73[7]; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+108h] [rbp+8h]
  _DWORD v75[33]; // [rsp+10Ch] [rbp+Ch]
  __int64 v76; // [rsp+190h] [rbp+90h] BYREF
  int v77; // [rsp+198h] [rbp+98h]
  unsigned int v78; // [rsp+1A0h] [rbp+A0h]
  __int64 v79; // [rsp+1A8h] [rbp+A8h]
  int v80; // [rsp+1B0h] [rbp+B0h]
  int v81; // [rsp+1B8h] [rbp+B8h]
  int v82; // [rsp+1C0h] [rbp+C0h]
  int v83; // [rsp+1C4h] [rbp+C4h]
  int v84; // [rsp+1C8h] [rbp+C8h]
  unsigned __int16 *v85; // [rsp+1D0h] [rbp+D0h]

  v59 = (int)a2;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v8 = a6;
  for ( i = 0; i < 3; ++i )
  {
    v10 = (unsigned __int64)i << 6;
    *(_QWORD *)((char *)v73 + v10) = 0;
    *(_QWORD *)((char *)&v73[1] + v10) = 0;
    *(_QWORD *)((char *)&v73[2] + v10) = 0;
    *(_QWORD *)((char *)&v73[3] + v10) = 0;
    *(_QWORD *)((char *)&v73[4] + v10) = 0;
    *(_QWORD *)((char *)&v73[5] + v10) = 0;
    *(_QWORD *)((char *)&v73[6] + v10) = 0;
    if ( !v8 )
      continue;
    v66 = 0;
    v68 = 4;
    ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(i);
    v67 = 0;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v12 = Int_FWGetOrSetConfig(
            1,
            (_DWORD)a2,
            17,
            ProfileTypeFromProfileIndex,
            1,
            (__int64)&v66,
            (__int64)&v68,
            (__int64)&v67);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
        (unsigned int)v12);
    }
    v13 = WPP_GLOBAL_Control;
LABEL_14:
    v14 = g_Provider;
    if ( g_Provider )
    {
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      v13 = WPP_GLOBAL_Control;
      v14 = g_Provider;
    }
    v15 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v15 = v12 < 0;
    }
    if ( v15 )
      goto LABEL_154;
    v67 = 0;
    v75[16 * (unsigned __int64)i - 1] = 3 - (v66 != 0);
    if ( v14 )
    {
      EtwEventWrite(v14, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v12 = Int_FWGetOrSetConfig(
            1,
            (_DWORD)a2,
            16,
            ProfileTypeFromProfileIndex,
            1,
            (__int64)&v66,
            (__int64)&v68,
            (__int64)&v67);
    if ( v12 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
        (unsigned int)v12);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v16 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v16 = v12 < 0;
    }
    if ( v16 )
      goto LABEL_154;
    v8 = a6;
    v75[16 * (unsigned __int64)i] = 3 - (v66 != 0);
  }
  if ( !SysStringLen(a4) )
  {
    v12 = -2147024809;
LABEL_154:
    FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
    return FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
  }
  if ( !a5 )
  {
    v12 = -2147467261;
    goto LABEL_154;
  }
  v61 = 0;
  v62 = 0;
  v60 = 0;
  v17 = 0;
  v70 = 0;
  v67 = 0;
  if ( (unsigned int)_o__wcsnicmp(a4, L"@FirewallAPI.dll,-", 18) )
  {
    v52 = FwQueryRulesInRuleGroup(a2, a3, 7u, a4, &v67, &v60);
    v12 = v52;
    if ( v52 < 0 )
    {
      v56 = (unsigned int)v52;
      goto LABEL_200;
    }
    if ( v67 )
      goto LABEL_46;
    if ( (int)FwLoadIndirectString(a4, &v61) < 0 && (int)FwStringCopy(a4, &v61) < 0 )
    {
      v57 = FwStringCopy(a4, &v61);
      FwReportReturnError("FwEnumRulesFromRuleGroup", v57);
      FWFreeFirewallRules(v62);
      FWFreeFirewallRules(v60);
      FwBaseFree(v61);
      goto LABEL_202;
    }
    v53 = FWEnumFirewallRules((_DWORD)a2, 196608, a3, 7, (__int64)&v70, (__int64)&v62);
    v12 = v53;
    if ( v53 > 0 )
      v12 = (unsigned __int16)v53 | 0x80070000;
    if ( v12 < 0 )
      goto LABEL_212;
    v54 = v62;
    v55 = &v62;
    if ( v62 )
    {
      do
      {
        if ( FwRuleInGroup(v54, v61) )
        {
          *v55 = *(struct _tag_FW_RULE **)v54;
          *(_QWORD *)v54 = v60;
          ++v67;
          v60 = v54;
        }
        else
        {
          v55 = (struct _tag_FW_RULE **)v54;
        }
        v54 = *v55;
      }
      while ( *v55 );
    }
LABEL_46:
    v17 = v60;
    v60 = 0;
    v67 = 0;
    FWFreeFirewallRules(v62);
    FWFreeFirewallRules(v60);
    FwBaseFree(v61);
    v21 = v12 <= 0;
    if ( v12 < 0 )
      goto LABEL_201;
  }
  else
  {
    v71 = 3;
    v63[1] = 1;
    v79 = 1;
    v83 = 1;
    v72 = &v76;
    v63[0] = 545;
    v64 = &v71;
    v65 = 0x10000;
    v76 = 0;
    v77 = 3;
    v78 = a3;
    v80 = 3;
    v81 = 196608;
    v82 = 8;
    v84 = 5;
    v85 = a4;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v18 = Int_FWQueryObject(
            0,
            (unsigned int)FWVerifyFirewallRuleQuery,
            (unsigned int)RPC_FWQueryFirewallRules,
            (unsigned int)RRPC_FWQueryFirewallRules,
            (__int64)Int_RPC_FWEnumFirewallRules2_0,
            (__int64)Int_RRPC_FWEnumFirewallRules2_0,
            (__int64)a2,
            (__int64)v63,
            7,
            (__int64)&v67,
            (__int64)&v60,
            0);
    v12 = v18;
    if ( v18 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v18);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
    v19 = v12 < 0;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
      v19 = v12 < 0;
    }
    if ( !v19 )
      goto LABEL_46;
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v12);
LABEL_212:
    v56 = (unsigned int)v12;
LABEL_200:
    FwReportReturnError("FwEnumRulesFromRuleGroup", v56);
    FWFreeFirewallRules(v62);
    FWFreeFirewallRules(v60);
    FwBaseFree(v61);
LABEL_201:
    v12 = FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v12);
LABEL_202:
    v21 = v12 <= 0;
  }
  if ( !v21 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 >= 0 )
  {
    v22 = 0;
    for ( j = v17; j; j = *(struct _tag_FW_RULE **)j )
    {
      if ( (unsigned int)(*((_DWORD *)j + 85) - 1) > 5 )
      {
        FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", 2147549183LL);
        goto LABEL_126;
      }
      if ( *((_DWORD *)j + 11) == 1 )
        v22 = -1;
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(0) & *((_DWORD *)j + 10)) != 0 )
      {
        v24 = *((int *)j + 85);
        ++LODWORD(v73[v24]);
        if ( (*((_BYTE *)j + 292) & 1) == 0 )
        {
          v25 = *((_DWORD *)j + 72);
          if ( ((v25 - 1) & 0xFFFFFFFD) != 0 )
          {
            v26 = 0;
            if ( v25 == 2 )
              v26 = 2;
          }
          else
          {
            v26 = 3;
          }
          if ( !HIDWORD(v73[v24]) )
          {
            v47 = 1;
            if ( v8 )
            {
              if ( (v48 = *((_DWORD *)j + 11), v48 == 1) && v26 != v74 || (v47 = 0, v48 == 2) && v26 != v75[0] )
                v47 = 1;
            }
            HIDWORD(v73[v24]) = v47;
          }
        }
      }
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(1) & *((_DWORD *)j + 10)) != 0 )
      {
        v27 = 8LL * *((int *)j + 85) + 64;
        ++*(_DWORD *)((char *)v73 + v27);
        if ( (*((_BYTE *)j + 292) & 1) == 0 )
        {
          v28 = *((_DWORD *)j + 72);
          if ( ((v28 - 1) & 0xFFFFFFFD) != 0 )
          {
            v29 = 0;
            if ( v28 == 2 )
              v29 = 2;
          }
          else
          {
            v29 = 3;
          }
          if ( !*(_DWORD *)((char *)v73 + v27 + 4) )
          {
            v49 = 1;
            if ( v8 )
            {
              if ( (v50 = *((_DWORD *)j + 11), v50 == 1) && v29 != v75[15] || (v49 = 0, v50 == 2) && v29 != v75[16] )
                v49 = 1;
            }
            *(_DWORD *)((char *)v73 + v27 + 4) = v49;
          }
        }
      }
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(2) & *((_DWORD *)j + 10)) != 0 )
      {
        v30 = 8LL * *((int *)j + 85) + 128;
        ++*(_DWORD *)((char *)v73 + v30);
        if ( (*((_BYTE *)j + 292) & 1) == 0 )
        {
          v31 = *((_DWORD *)j + 72);
          if ( ((v31 - 1) & 0xFFFFFFFD) != 0 )
          {
            v32 = 0;
            if ( v31 == 2 )
              v32 = 2;
          }
          else
          {
            v32 = 3;
          }
          if ( !*(_DWORD *)((char *)v73 + v30 + 4) )
          {
            v51 = 1;
            if ( v8 )
            {
              if ( (v20 = *((unsigned int *)j + 11), (_DWORD)v20 == 1) && v32 != v75[31]
                || (v51 = 0, (_DWORD)v20 == 2) && v32 != v75[32] )
              {
                v51 = 1;
              }
            }
            *(_DWORD *)((char *)v73 + v30 + 4) = v51;
          }
        }
      }
    }
    v33 = 0;
    v12 = 1;
    *a5 = 0;
    while ( 1 )
    {
      if ( (unsigned int)v33 >= 3 )
        goto LABEL_126;
      v66 = 0;
      v68 = 4;
      v34 = FwGetProfileTypeFromProfileIndex((unsigned int)v33);
      if ( (v34 & a3) == 0 )
        goto LABEL_121;
      v35 = 1;
      if ( !v8 )
      {
        v20 = 0;
LABEL_76:
        for ( k = 0; k < 7; ++k )
        {
          if ( (_DWORD)v20 != 1 || k == 2 )
          {
            v37 = k + 8 * v33;
            if ( LODWORD(v73[v37]) )
            {
              if ( !HIDWORD(v73[v37]) )
                goto LABEL_118;
              v35 = 0;
              v8 = 0;
            }
          }
        }
        goto LABEL_116;
      }
      v38 = g_Provider;
      if ( v22 != -1 )
      {
        v39 = WPP_GLOBAL_Control;
        goto LABEL_94;
      }
      v69 = 0;
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v8 = Int_FWGetOrSetConfig(1, v59, 3, v34, 1, (__int64)&v66, (__int64)&v68, (__int64)&v69);
      if ( v8 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_89;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v8);
      }
      v39 = WPP_GLOBAL_Control;
LABEL_89:
      v38 = g_Provider;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
        v39 = WPP_GLOBAL_Control;
        v38 = g_Provider;
      }
      if ( v8 )
      {
LABEL_124:
        v43 = v8;
LABEL_125:
        v12 = FwReportErrorAsWinError("FwPolicy2::IsRuleGroupEnabledInStore", "FWGetConfig", v43);
        goto LABEL_126;
      }
      if ( v66 )
        v35 = 0;
LABEL_94:
      v69 = 0;
      if ( v38 )
      {
        EtwEventWrite(v38, MPS_CLNT_API_Enter_GetConfig, 0, 0);
        v39 = WPP_GLOBAL_Control;
      }
      if ( v39 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v39 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v8 = Int_FWGetOrSetConfig(1, v59, 1, v34, 1, (__int64)&v66, (__int64)&v68, (__int64)&v69);
      if ( !v8 )
        goto LABEL_100;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v8);
LABEL_100:
        v40 = WPP_GLOBAL_Control;
      }
      v41 = g_Provider;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
        v40 = WPP_GLOBAL_Control;
        v41 = g_Provider;
      }
      if ( v8 )
        goto LABEL_124;
      if ( !v66 )
      {
        v8 = 1;
        v35 = 0;
      }
      v69 = 0;
      if ( v41 )
      {
        EtwEventWrite(v41, MPS_CLNT_API_Enter_GetConfig, 0, 0);
        v40 = WPP_GLOBAL_Control;
      }
      if ( v40 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v40 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v42 = Int_FWGetOrSetConfig(1, v59, 13, v34, 1, (__int64)&v66, (__int64)&v68, (__int64)&v69);
      if ( v42
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v42);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v42 )
      {
        v43 = v42;
        goto LABEL_125;
      }
      v20 = v66 == 0;
      if ( v35 == 1 )
        goto LABEL_76;
LABEL_116:
      if ( v35 )
      {
        v8 = a6;
LABEL_121:
        v33 = (unsigned int)(v33 + 1);
        continue;
      }
      if ( v8 )
      {
LABEL_118:
        if ( v12 != 1 )
        {
          v8 = a6;
          if ( !*a5 )
          {
            *a5 = -1;
            v12 = 1;
          }
          goto LABEL_121;
        }
        v8 = a6;
        if ( *a5 )
          goto LABEL_121;
        v12 = 0;
        *a5 = -1;
        v33 = (unsigned int)(v33 + 1);
      }
      else if ( v12 == 1 )
      {
        v8 = a6;
        if ( *a5 )
          goto LABEL_121;
        v12 = 0;
        v33 = (unsigned int)(v33 + 1);
      }
      else
      {
        v8 = a6;
        if ( *a5 != -1 )
          goto LABEL_121;
        v12 = 1;
        v33 = (unsigned int)(v33 + 1);
      }
    }
  }
  FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
LABEL_126:
  if ( v17 )
  {
    if ( g_Provider )
      EtwEventWrite(g_Provider, &MPS_CLNT_API_Enter_FreeFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v44 = FwFreeRules(v17, 0, v20);
    v45 = FwHResultToWindowsError(v44);
    if ( v45 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v45);
    if ( g_Provider )
      EtwEventWrite(g_Provider, &MPS_CLNT_API_Exit_FreeFirewallRules, 0, 0);
  }
  if ( v12 >= 0 )
    return (unsigned int)v12;
  return FwReportReturnError("FwPolicy2::IsRuleGroupEnabledInStore", (unsigned int)v12);
}

```

## disassembly

```asm
0x180007880  mov     [rsp-8+arg_0], rbx
0x180007885  push    rbp
0x180007886  push    rsi
0x180007887  push    rdi
0x180007888  push    r12
0x18000788a  push    r13
0x18000788c  push    r14
0x18000788e  push    r15
0x180007890  lea     rbp, [rsp-0F0h]
0x180007898  sub     rsp, 1F0h
0x18000789f  mov     rax, cs:__security_cookie
0x1800078a6  xor     rax, rsp
0x1800078a9  mov     [rbp+120h+var_40], rax
0x1800078b0  mov     rbx, [rbp+120h+arg_20]
0x1800078b7  mov     r14, r9
0x1800078ba  mov     [rsp+220h+var_1B8], rbx
0x1800078bf  mov     r12, rdx
0x1800078c2  mov     [rsp+220h+var_1C0], r8d
0x1800078c7  mov     [rsp+220h+var_1B0], rdx
0x1800078cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078d3  lea     rbx, WPP_GLOBAL_Control
0x1800078da  cmp     rcx, rbx
0x1800078dd  jz      short loc_1800078E9
0x1800078df  test    byte ptr [rcx+1Ch], 8
0x1800078e3  jnz     loc_1800086A3
0x1800078e9  mov     esi, [rbp+120h+arg_28]
0x1800078ef  xor     r15d, r15d
0x1800078f2  mov     edi, r15d
0x1800078f5  mov     r13d, 1
0x1800078fb  cmp     edi, 3
0x1800078fe  jnb     loc_180007B10
0x180007904  mov     ebx, edi
0x180007906  shl     rbx, 6
0x18000790a  mov     [rbp+rbx+120h+var_150], 0
0x180007913  mov     [rbp+rbx+120h+var_148], 0
0x18000791c  mov     [rbp+rbx+120h+var_140], 0
0x180007925  mov     [rbp+rbx+120h+var_138], 0
0x18000792e  mov     [rbp+rbx+120h+var_130], 0
0x180007937  mov     [rbp+rbx+120h+var_128], 0
0x180007940  mov     [rbp+rbx+120h+var_120], 0
0x180007949  test    esi, esi
0x18000794b  jz      loc_180007B09
0x180007951  mov     ecx, edi
0x180007953  mov     [rbp+120h+var_178], r15d
0x180007957  mov     [rbp+120h+var_170], 4
0x18000795e  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180007964  mov     rcx, cs:g_Provider
0x18000796b  mov     esi, eax
0x18000796d  mov     [rbp+120h+var_174], r15d
0x180007971  test    rcx, rcx
0x180007974  jz      short loc_180007989
0x180007976  xor     r9d, r9d
0x180007979  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007980  xor     r8d, r8d
0x180007983  call    cs:__imp_EtwEventWrite
0x180007989  mov     rcx, cs:WPP_GLOBAL_Control
0x180007990  lea     rax, WPP_GLOBAL_Control
0x180007997  cmp     rcx, rax
0x18000799a  jz      short loc_1800079A6
0x18000799c  test    byte ptr [rcx+1Ch], 8
0x1800079a0  jnz     loc_1800086BD
0x1800079a6  call    cs:__imp_GetTickCount64
0x1800079ac  lea     rax, [rbp+120h+var_174]
0x1800079b0  mov     r9d, esi
0x1800079b3  mov     [rsp+220h+var_1E8], rax
0x1800079b8  mov     r8d, 11h
0x1800079be  lea     rax, [rbp+120h+var_170]
0x1800079c2  mov     rdx, r12
0x1800079c5  mov     [rsp+220h+var_1F0], rax
0x1800079ca  mov     ecx, r13d
0x1800079cd  lea     rax, [rbp+120h+var_178]
0x1800079d1  mov     [rsp+220h+var_1F8], rax
0x1800079d6  mov     dword ptr [rsp+220h+var_200], r13d
0x1800079db  call    Int_FWGetOrSetConfig
0x1800079e0  mov     r15d, eax
0x1800079e3  test    eax, eax
0x1800079e5  jnz     loc_1800083A0
0x1800079eb  mov     r11, cs:WPP_GLOBAL_Control
0x1800079f2  mov     r10, cs:g_Provider
0x1800079f9  test    r10, r10
0x1800079fc  jz      short loc_180007A22
0x1800079fe  xor     r9d, r9d
0x180007a01  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007a08  xor     r8d, r8d
0x180007a0b  mov     rcx, r10
0x180007a0e  call    cs:__imp_EtwEventWrite
0x180007a14  mov     r11, cs:WPP_GLOBAL_Control
0x180007a1b  mov     r10, cs:g_Provider
0x180007a22  test    r15d, r15d
0x180007a25  jg      loc_180008329
0x180007a2b  js      loc_1800082DB
0x180007a31  mov     eax, [rbp+120h+var_178]
0x180007a34  neg     eax
0x180007a36  mov     [rbp+120h+var_174], 0
0x180007a3d  sbb     ecx, ecx
0x180007a3f  add     ecx, 3
0x180007a42  mov     [rbp+rbx+120h+var_118], ecx
0x180007a46  test    r10, r10
0x180007a49  jz      short loc_180007A68
0x180007a4b  xor     r9d, r9d
0x180007a4e  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007a55  xor     r8d, r8d
0x180007a58  mov     rcx, r10
0x180007a5b  call    cs:__imp_EtwEventWrite
0x180007a61  mov     r11, cs:WPP_GLOBAL_Control
0x180007a68  lea     rax, WPP_GLOBAL_Control
0x180007a6f  cmp     r11, rax
0x180007a72  jz      short loc_180007A7F
0x180007a74  test    byte ptr [r11+1Ch], 8
0x180007a79  jnz     loc_1800086D7
0x180007a7f  call    cs:__imp_GetTickCount64
0x180007a85  lea     rax, [rbp+120h+var_174]
0x180007a89  mov     r9d, esi
0x180007a8c  mov     [rsp+220h+var_1E8], rax
0x180007a91  mov     r8d, 10h
0x180007a97  lea     rax, [rbp+120h+var_170]
0x180007a9b  mov     rdx, r12
0x180007a9e  mov     [rsp+220h+var_1F0], rax
0x180007aa3  mov     ecx, r13d
0x180007aa6  lea     rax, [rbp+120h+var_178]
0x180007aaa  mov     [rsp+220h+var_1F8], rax
0x180007aaf  mov     dword ptr [rsp+220h+var_200], r13d
0x180007ab4  call    Int_FWGetOrSetConfig
0x180007ab9  mov     r15d, eax
0x180007abc  test    eax, eax
0x180007abe  jnz     loc_1800083DE
0x180007ac4  mov     rcx, cs:g_Provider
0x180007acb  test    rcx, rcx
0x180007ace  jz      short loc_180007AE3
0x180007ad0  xor     r9d, r9d
0x180007ad3  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007ada  xor     r8d, r8d
0x180007add  call    cs:__imp_EtwEventWrite
0x180007ae3  test    r15d, r15d
0x180007ae6  jg      loc_18000838D
0x180007aec  js      loc_1800082DB
0x180007af2  mov     eax, [rbp+120h+var_178]
0x180007af5  mov     esi, [rbp+120h+arg_28]
0x180007afb  neg     eax
0x180007afd  sbb     ecx, ecx
0x180007aff  add     ecx, 3
0x180007b02  mov     [rbp+rbx+120h+var_114], ecx
0x180007b06  xor     r15d, r15d
0x180007b09  inc     edi
0x180007b0b  jmp     loc_1800078FB
0x180007b10  mov     rcx, r14; pbstr
0x180007b13  call    cs:__imp_SysStringLen
0x180007b19  test    eax, eax
0x180007b1b  jz      loc_1800086F1
0x180007b21  cmp     [rsp+220h+var_1B8], 0
0x180007b27  jz      loc_1800086FC
0x180007b2d  mov     r8d, 12h
0x180007b33  mov     [rbp+120h+var_1A0], r15
0x180007b37  lea     rdx, aFirewallapiDll_14; "@FirewallAPI.dll,-"
0x180007b3e  mov     [rbp+120h+var_198], r15
0x180007b42  mov     rcx, r14
0x180007b45  mov     [rsp+220h+var_1A8], r15
0x180007b4a  mov     r13, r15
0x180007b4d  mov     [rbp+120h+var_168], r15d
0x180007b51  mov     [rbp+120h+var_174], r15d
0x180007b55  call    cs:__imp__o__wcsnicmp
0x180007b5b  mov     edi, [rsp+220h+var_1C0]
0x180007b5f  test    eax, eax
0x180007b61  jnz     loc_180008548
0x180007b67  mov     ecx, 1
0x180007b6c  mov     [rbp+120h+var_160], 3
0x180007b73  lea     rax, [rbp+120h+var_90]
0x180007b7a  mov     [rbp+120h+var_18C], ecx
0x180007b7d  mov     [rbp+120h+var_78], rcx
0x180007b84  mov     [rbp+120h+var_5C], ecx
0x180007b8a  mov     rcx, cs:g_Provider
0x180007b91  mov     [rbp+120h+var_158], rax
0x180007b95  lea     rax, [rbp+120h+var_160]
0x180007b99  mov     [rbp+120h+var_190], 221h
0x180007ba0  mov     [rbp+120h+var_188], rax
0x180007ba4  mov     [rbp+120h+var_180], 10000h
0x180007bac  mov     [rbp+120h+var_90], 0
0x180007bb7  mov     [rbp+120h+var_88], 3
0x180007bc1  mov     [rbp+120h+var_80], edi
0x180007bc7  mov     [rbp+120h+var_70], 3
0x180007bd1  mov     [rbp+120h+var_68], 30000h
0x180007bdb  mov     [rbp+120h+var_60], 8
0x180007be5  mov     [rbp+120h+var_58], 5
0x180007bef  mov     [rbp+120h+var_50], r14
0x180007bf6  test    rcx, rcx
0x180007bf9  jz      short loc_180007C0E
0x180007bfb  xor     r9d, r9d
0x180007bfe  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180007c05  xor     r8d, r8d
0x180007c08  call    cs:__imp_EtwEventWrite
0x180007c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c15  lea     rdi, WPP_GLOBAL_Control
0x180007c1c  cmp     rcx, rdi
0x180007c1f  jz      short loc_180007C2B
0x180007c21  test    byte ptr [rcx+1Ch], 8
0x180007c25  jnz     loc_180008707
0x180007c2b  call    cs:__imp_GetTickCount64
0x180007c31  mov     [rsp+220h+var_1C8], r15d
0x180007c36  lea     rax, [rsp+220h+var_1A8]
0x180007c3b  mov     [rsp+220h+var_1D0], rax
0x180007c40  lea     r9, RRPC_FWQueryFirewallRules
0x180007c47  lea     rax, [rbp+120h+var_174]
0x180007c4b  xor     ecx, ecx
0x180007c4d  mov     [rsp+220h+var_1D8], rax
0x180007c52  lea     r8, RPC_FWQueryFirewallRules
0x180007c59  mov     [rsp+220h+var_1E0], 7
0x180007c60  lea     rax, [rbp+120h+var_190]
0x180007c64  mov     [rsp+220h+var_1E8], rax
0x180007c69  lea     rdx, FWVerifyFirewallRuleQuery
0x180007c70  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180007c77  mov     [rsp+220h+var_1F0], r12
0x180007c7c  mov     [rsp+220h+var_1F8], rax
0x180007c81  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180007c88  mov     [rsp+220h+var_200], rax
0x180007c8d  call    Int_FWQueryObject
0x180007c92  mov     r15d, eax
0x180007c95  test    eax, eax
0x180007c97  jnz     loc_180008721
0x180007c9d  mov     rcx, cs:g_Provider
0x180007ca4  test    rcx, rcx
0x180007ca7  jz      short loc_180007CBC
0x180007ca9  xor     r9d, r9d
0x180007cac  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x180007cb3  xor     r8d, r8d
0x180007cb6  call    cs:__imp_EtwEventWrite
0x180007cbc  test    r15d, r15d
0x180007cbf  jg      loc_18000842C
0x180007cc5  js      loc_180008758
0x180007ccb  mov     r13, [rsp+220h+var_1A8]
0x180007cd0  mov     [rsp+220h+var_1A8], 0
0x180007cd9  mov     [rbp+120h+var_174], 0
0x180007ce0  mov     rcx, [rbp+120h+var_198]
0x180007ce4  call    FWFreeFirewallRules
0x180007ce9  mov     rcx, [rsp+220h+var_1A8]
0x180007cee  call    FWFreeFirewallRules
0x180007cf3  mov     rcx, [rbp+120h+var_1A0]
0x180007cf7  call    cs:__imp_FwBaseFree
0x180007cfd  test    r15d, r15d
0x180007d00  js      loc_18000863C
0x180007d06  jg      loc_18000841C
0x180007d0c  test    r15d, r15d
0x180007d0f  js      loc_18000867E
0x180007d15  xor     r12d, r12d
0x180007d18  mov     rbx, r13
0x180007d1b  mov     ecx, 0FFFFFFFFh
0x180007d20  test    rbx, rbx
0x180007d23  jz      loc_180007E39
0x180007d29  mov     eax, [rbx+154h]
0x180007d2f  dec     eax
0x180007d31  cmp     eax, 5
0x180007d34  ja      loc_18000843F
0x180007d3a  cmp     dword ptr [rbx+2Ch], 1
0x180007d3e  jnz     short loc_180007D44
0x180007d40  movzx   r12d, cx
0x180007d44  xor     ecx, ecx
0x180007d46  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180007d4c  test    [rbx+28h], eax
0x180007d4f  jz      short loc_180007D91
0x180007d51  movsxd  rax, dword ptr [rbx+154h]
0x180007d58  lea     rcx, ds:0[rax*8]
0x180007d60  inc     dword ptr [rbp+rcx+120h+var_150]
0x180007d64  test    byte ptr [rbx+124h], 1
0x180007d6b  jnz     short loc_180007D91
0x180007d6d  mov     edx, [rbx+120h]
0x180007d73  lea     eax, [rdx-1]
0x180007d76  test    eax, 0FFFFFFFDh
0x180007d7b  jnz     loc_1800087DE
0x180007d81  mov     eax, 3
0x180007d86  cmp     dword ptr [rbp+rcx+120h+var_150+4], 0
0x180007d8b  jz      loc_180008227
0x180007d91  mov     ecx, 1
0x180007d96  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180007d9c  test    [rbx+28h], eax
0x180007d9f  jz      short loc_180007DE1
0x180007da1  movsxd  rax, dword ptr [rbx+154h]
0x180007da8  lea     rcx, ds:40h[rax*8]
0x180007db0  inc     dword ptr [rbp+rcx+120h+var_150]
0x180007db4  test    byte ptr [rbx+124h], 1
0x180007dbb  jnz     short loc_180007DE1
0x180007dbd  mov     edx, [rbx+120h]
0x180007dc3  lea     eax, [rdx-1]
0x180007dc6  test    eax, 0FFFFFFFDh
0x180007dcb  jnz     loc_1800087F0
0x180007dd1  mov     eax, 3
0x180007dd6  cmp     dword ptr [rbp+rcx+120h+var_150+4], 0
0x180007ddb  jz      loc_180008254
0x180007de1  mov     ecx, 2
0x180007de6  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180007dec  test    [rbx+28h], eax
0x180007def  jz      short loc_180007E31
0x180007df1  movsxd  rax, dword ptr [rbx+154h]
0x180007df8  lea     rcx, ds:80h[rax*8]
0x180007e00  inc     dword ptr [rbp+rcx+120h+var_150]
0x180007e04  test    byte ptr [rbx+124h], 1
0x180007e0b  jnz     short loc_180007E31
0x180007e0d  mov     edx, [rbx+120h]
0x180007e13  lea     eax, [rdx-1]
0x180007e16  test    eax, 0FFFFFFFDh
0x180007e1b  jnz     loc_180008802
0x180007e21  mov     eax, 3
  ... truncated ...
```
