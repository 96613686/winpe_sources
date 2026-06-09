# Int_FWImportPolicy(ushort const *,_tag_FW_STORE_TYPE,ushort const *,int *)

- ea: `0x1800587a0`
- end: `0x1800596db`
- name: `?Int_FWImportPolicy@@YAKPEBGW4_tag_FW_STORE_TYPE@@0PEAH@Z`
- size: `3899`
- prototype: `unsigned int __high(const unsigned __int16 *, enum _tag_FW_STORE_TYPE, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e410`

## callees

- `0x180005954`
- `0x18000c130`
- `0x18000c560`
- `0x1800140b0`
- `0x1800240a4`
- `0x18002514c`
- `0x1800266b0`
- `0x180027190`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x18004a930`
- `0x18004a970`
- `0x18004ab00`
- `0x18004aca0`
- `0x18004b130`
- `0x18004b4a0`
- `0x18004bae0`
- `0x18004bbd0`
- `0x18004bcb0`
- `0x18004bda0`
- `0x18004be80`
- `0x1800502a0`
- `0x180058318`
- `0x180058368`
- `0x18005856c`
- `0x1800587a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18005899d`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18005899d`
- `fwbase!FwBaseAlloc` at `0x180058b31`
- `fwbase!FwBaseAlloc` at `0x180058b31`
- `fwbase!FwBaseFree` at `0x180058b28`
- `fwbase!FwBaseFree` at `0x180058c18`
- `fwbase!FwBaseFree` at `0x180059595`
- `fwbase!FwBaseFree` at `0x180058b28`
- `fwbase!FwBaseFree` at `0x180058c18`
- `fwbase!FwBaseFree` at `0x180059595`
- `fwbase!FwHResultToWindowsError` at `0x18005959d`
- `fwbase!FwHResultToWindowsError` at `0x18005959d`
- `fwbase!FwReleasePrivilege` at `0x180058955`
- `fwbase!FwReleasePrivilege` at `0x180058960`
- `fwbase!FwReleasePrivilege` at `0x1800589de`
- `fwbase!FwReleasePrivilege` at `0x1800589e9`
- `fwbase!FwReleasePrivilege` at `0x180058955`
- `fwbase!FwReleasePrivilege` at `0x180058960`
- `fwbase!FwReleasePrivilege` at `0x1800589de`
- `fwbase!FwReleasePrivilege` at `0x1800589e9`
- `FWPolicyIOMgr!FwEnumRules` at `0x180059149`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800592ba`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800593c8`
- `FWPolicyIOMgr!FwEnumRules` at `0x180059149`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800592ba`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800593c8`
- `FWPolicyIOMgr!FwGetConfig` at `0x180058e34`
- `FWPolicyIOMgr!FwGetConfig` at `0x180058e34`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005928e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005939c`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800594a3`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005954e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005955b`
- `FWPolicyIOMgr!FwFreeRules` at `0x180059567`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005928e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005939c`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800594a3`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005954e`
- `FWPolicyIOMgr!FwFreeRules` at `0x18005955b`
- `FWPolicyIOMgr!FwFreeRules` at `0x180059567`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005904b`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059103`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059573`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059580`
- `FWPolicyIOMgr!FwFreeSets` at `0x18005904b`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059103`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059573`
- `FWPolicyIOMgr!FwFreeSets` at `0x180059580`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x1800589fb`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x1800589fb`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x18005951c`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x18005951c`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180058b50`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180058b50`
- `FWPolicyIOMgr!FwEnumSets` at `0x180058fc6`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005907d`
- `FWPolicyIOMgr!FwEnumSets` at `0x180058fc6`
- `FWPolicyIOMgr!FwEnumSets` at `0x18005907d`

## string_xrefs

- `0x1800594d6`: `Imported %lu rules: %lu firewall rules, %lu connection security rules, %lu main mode rules`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Int_FWImportPolicy(__int64 a1, unsigned int a2, const WCHAR *a3, _DWORD *a4)
{
  unsigned int v6; // r14d
  _BYTE *v8; // r13
  signed int v9; // ebx
  __int64 v10; // r8
  FwPolicy2 *v11; // rcx
  __int64 v12; // rdx
  FwPolicy2 *v13; // rcx
  __int64 v14; // rdx
  LSTATUS v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int i; // edi
  int GlobalConfigFromLocalTempStore; // eax
  __int64 v20; // r9
  int v21; // eax
  FwPolicy2 *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rsi
  unsigned int v29; // edi
  int Config; // eax
  char v31; // al
  int v32; // eax
  FwPolicy2 *v33; // rcx
  __int64 v34; // rdx
  FwPolicy2 *v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  unsigned int j; // esi
  int v39; // eax
  _DWORD *v40; // rdi
  int v41; // eax
  int v42; // eax
  _DWORD *v43; // rdi
  int v44; // eax
  int v45; // r15d
  _DWORD *v46; // rdi
  int v47; // esi
  int v48; // eax
  int v49; // r14d
  _DWORD *v50; // rdi
  int v51; // eax
  _DWORD *v52; // rdi
  int v53; // eax
  __int64 v54; // r8
  __int64 v55; // r8
  unsigned int v56; // ebx
  __int64 v58; // [rsp+20h] [rbp-E0h]
  __int64 v59; // [rsp+28h] [rbp-D8h]
  __int64 v60; // [rsp+30h] [rbp-D0h]
  __int128 v62; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+58h] [rbp-A8h]
  __int128 v64; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h]
  const WCHAR *v66; // [rsp+78h] [rbp-88h]
  unsigned int v67; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h] BYREF
  __int64 v69; // [rsp+90h] [rbp-70h] BYREF
  void *v70; // [rsp+98h] [rbp-68h] BYREF
  void *v71; // [rsp+A0h] [rbp-60h] BYREF
  void *v72; // [rsp+A8h] [rbp-58h] BYREF
  void *Src; // [rsp+B0h] [rbp-50h] BYREF
  void *v74; // [rsp+B8h] [rbp-48h] BYREF
  void **v75; // [rsp+C0h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-38h]
  __int128 v77; // [rsp+D0h] [rbp-30h]
  _BYTE v78[176]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v79[120]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v80[1024]; // [rsp+280h] [rbp+180h] BYREF

  v66 = a3;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  v69 = 0;
  v68 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  Src = 0;
  v74 = 0;
  v8 = 0;
  v67 = 0;
  memset_0(v79, 0, 0xEEu);
  *a4 = 0;
  memset_0(&v75, 0, 0xD0u);
  v75 = &CTempRegKey::`vftable';
  hKey = 0;
  v77 = 0;
  v9 = CTempRegKey::Init((CTempRegKey *)&v75);
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 42;
    goto LABEL_8;
  }
  v64 = 0;
  v65 = 0;
  CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v64, 0x11u);
  v62 = 0;
  v63 = 0;
  CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v62, 0x12u);
  v9 = DWORD2(v62);
  if ( SDWORD2(v62) < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v14 = 43;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
LABEL_14:
    FwReleasePrivilege(v63);
    FwReleasePrivilege(v65);
    goto LABEL_234;
  }
  v9 = DWORD2(v64);
  if ( SDWORD2(v64) < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v14 = 44;
    goto LABEL_13;
  }
  v15 = RegRestoreKeyW(hKey, a3, 0);
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( v9 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v14 = 45;
    goto LABEL_13;
  }
  FwReleasePrivilege(v63);
  FwReleasePrivilege(v65);
  v9 = FwCreateLocalTempStore(v78, hKey, &v69);
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 46;
    goto LABEL_8;
  }
  v16 = FWOpenPolicyStore(0x221u, a1, v6, 2u, 0, &v68);
  v9 = v16;
  if ( v16 > 0 )
    v9 = (unsigned __int16)v16 | 0x80070000;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 47;
    goto LABEL_8;
  }
  if ( v6 == 6 )
  {
    v17 = FWChangeTransactionalState(v68, 1);
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_234;
      v12 = 48;
      goto LABEL_8;
    }
  }
  for ( i = 1; i < 0x13; ++i )
  {
    if ( i - 1 > 1 && i != 11 )
    {
      v8 = v80;
      v67 = 1024;
      v9 = 0;
      do
      {
        if ( v9 == -2147024662 )
        {
          if ( v8 != v80 )
            FwBaseFree(v8);
          v8 = (_BYTE *)FwBaseAlloc(v67);
          if ( !v8 )
          {
            v9 = -2147024882;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v12 = 49;
            goto LABEL_8;
          }
        }
        GlobalConfigFromLocalTempStore = FwGetGlobalConfigFromLocalTempStore(hKey, i, v8, &v67);
        v9 = GlobalConfigFromLocalTempStore;
      }
      while ( GlobalConfigFromLocalTempStore == -2147024662 );
      if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
      {
        if ( GlobalConfigFromLocalTempStore >= 0 )
        {
          v20 = v67;
          goto LABEL_57;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_234;
        v12 = 52;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
        goto LABEL_234;
      }
      if ( i == 10 )
      {
        *(_DWORD *)v8 = 545;
        v20 = 4;
        v67 = 4;
LABEL_57:
        if ( !(_DWORD)v20 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v20 = v67;
        }
        if ( i == 10 && *(_DWORD *)v8 > 0x221u )
        {
          *a4 = 1;
          *(_DWORD *)v8 = 545;
          v20 = 4;
          v67 = 4;
        }
        v21 = FWSetGlobalConfig2(v68, i, v8, v20);
        v9 = v21;
        if ( v21 == 50 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v23 = 53;
LABEL_75:
            WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, i);
            continue;
          }
        }
        else
        {
          if ( v21 > 0 )
            v9 = (unsigned __int16)v21 | 0x80070000;
          if ( v9 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v12 = 54;
            goto LABEL_8;
          }
          if ( v8 != v80 )
          {
            FwBaseFree(v8);
            v8 = 0;
          }
        }
      }
      else
      {
        v24 = FWSetGlobalConfig2(v68, i, 0, 0);
        v9 = v24;
        if ( v24 == 50 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v23 = 50;
            goto LABEL_75;
          }
        }
        else
        {
          if ( v24 > 0 )
            v9 = (unsigned __int16)v24 | 0x80070000;
          if ( v9 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_234;
            }
            v12 = 51;
            goto LABEL_8;
          }
        }
      }
    }
  }
  v25 = FWDeleteAllMainModeRules(v68);
  v9 = v25;
  if ( v25 > 0 )
    v9 = (unsigned __int16)v25 | 0x80070000;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 55;
    goto LABEL_8;
  }
  v26 = FWDeleteAllConnectionSecurityRules(v68);
  v9 = v26;
  if ( v26 > 0 )
    v9 = (unsigned __int16)v26 | 0x80070000;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 56;
    goto LABEL_8;
  }
  v27 = FWDeleteAllFirewallRules(v68);
  v9 = v27;
  if ( v27 > 0 )
    v9 = (unsigned __int16)v27 | 0x80070000;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_234;
    v12 = 57;
    goto LABEL_8;
  }
  v28 = 0;
  while ( 2 )
  {
    v29 = 1;
    while ( 2 )
    {
      v67 = 1024;
      Config = FwGetConfig(v69, v29, *((unsigned int *)qword_18008A2B0 + v28), v80, &v67);
      v9 = Config;
      if ( Config == -2147024894 || Config == -2147024846 )
      {
        v37 = FWSetConfig(v68, v29, *((_DWORD *)qword_18008A2B0 + v28), 0, 0);
        v9 = v37;
        if ( v37 == 50 )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v34 = (unsigned int)(v37 + 8);
LABEL_133:
            WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, v29);
          }
        }
        else
        {
          if ( v37 > 0 )
            v9 = (unsigned __int16)v37 | 0x80070000;
          if ( v9 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_233;
            }
            v36 = 59;
LABEL_128:
            WPP_SF_d(*((_QWORD *)v35 + 2), v36, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
            goto LABEL_233;
          }
        }
      }
      else
      {
        if ( Config < 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v36 = 60;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        v31 = v67;
        if ( !v67 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v31 = v67;
        }
        v32 = FWSetConfig(v68, v29, *((_DWORD *)qword_18008A2B0 + v28), (unsigned int)v80, v31);
        v9 = v32;
        if ( v32 == 50 )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v34 = (unsigned int)(v32 + 11);
            goto LABEL_133;
          }
        }
        else
        {
          if ( v32 > 0 )
            v9 = (unsigned __int16)v32 | 0x80070000;
          if ( v9 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 62;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
      }
      if ( ++v29 < 0x13 )
        continue;
      break;
    }
    v28 = (unsigned int)(v28 + 1);
    if ( (unsigned int)v28 < 3 )
      continue;
    break;
  }
  for ( j = 1; j <= 2; ++j )
  {
    v9 = FwEnumSets(v69, 0, j, &Src, &v67, 458752, 0);
    if ( v9 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v36 = 63;
      goto LABEL_128;
    }
    v39 = FWDeleteAllAuthenticationSets(v68, j);
    v9 = v39;
    if ( v39 > 0 )
      v9 = (unsigned __int16)v39 | 0x80070000;
    if ( v9 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v36 = 64;
      goto LABEL_128;
    }
    v40 = Src;
    if ( Src )
    {
      do
      {
        if ( (v40[20] & 0x60000) != 0 )
          *a4 = 1;
        if ( (v40[20] & 0x40000) == 0 )
        {
          v41 = FWAddAuthenticationSet(v68, v40);
          v9 = v41;
          if ( v41 > 0 )
            v9 = (unsigned __int16)v41 | 0x80070000;
          if ( v9 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 65;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
        v40 = *(_DWORD **)v40;
      }
      while ( v40 );
      v40 = Src;
    }
    FwFreeSets(v40, 0);
    Src = 0;
    v9 = FwEnumSets(v69, 1, j, &v74, &v67, 458752, 0);
    if ( v9 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v36 = 66;
      goto LABEL_128;
    }
    v42 = FWDeleteAllCryptoSets(v68, j);
    v9 = v42;
    if ( v42 > 0 )
      v9 = (unsigned __int16)v42 | 0x80070000;
    if ( v9 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v36 = 67;
      goto LABEL_128;
    }
    v43 = v74;
    if ( v74 )
    {
      do
      {
        if ( (v43[22] & 0x60000) != 0 )
          *a4 = 1;
        if ( (v43[22] & 0x40000) == 0 )
        {
          v44 = FWAddCryptoSet(v68, v43);
          v9 = v44;
          if ( v44 > 0 )
            v9 = (unsigned __int16)v44 | 0x80070000;
          if ( v9 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 68;
              goto LABEL_128;
            }
            goto LABEL_233;
          }
        }
        v43 = *(_DWORD **)v43;
      }
      while ( v43 );
      v43 = v74;
    }
    FwFreeSets(v43, 1);
    v74 = 0;
  }
  v9 = FwEnumRules(v69, 2, &v70, &v67, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v36 = 69;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v45 = 0;
  v46 = v70;
  v47 = 0;
  if ( v70 )
  {
    do
    {
      if ( (v46[64] & 0x60000) != 0 )
        *a4 = 1;
      if ( (v46[64] & 0x40000) == 0 )
      {
        v48 = FWAddMainModeRule(v68, v46);
        v9 = v48;
        if ( v48 == 50 )
        {
          v9 = 0;
          *a4 = 1;
        }
        else if ( v48 > 0 )
        {
          v9 = (unsigned __int16)v48 | 0x80070000;
        }
        if ( v9 < 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v36 = 70;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
          ++v45;
      }
      v46 = *(_DWORD **)v46;
    }
    while ( v46 );
    v46 = v70;
  }
  FwFreeRules(v46, 2, v10);
  v70 = 0;
  v9 = FwEnumRules(v69, 1, &v71, &v67, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v36 = 71;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v49 = 0;
  v50 = v71;
  if ( v71 )
  {
    do
    {
      if ( (v50[96] & 0x60000) != 0 )
        *a4 = 1;
      if ( (v50[96] & 0x40000) == 0 )
      {
        v51 = FWAddConnectionSecurityRule(v68, v50);
        v9 = v51;
        if ( v51 > 0 )
          v9 = (unsigned __int16)v51 | 0x80070000;
        if ( v9 < 0 )
        {
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v36 = 72;
            goto LABEL_128;
          }
          goto LABEL_233;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
          ++v49;
      }
      v50 = *(_DWORD **)v50;
    }
    while ( v50 );
    v50 = v71;
  }
  FwFreeRules(v50, 1, v10);
  v71 = 0;
  v9 = FwEnumRules(v69, 0, &v72, &v67, 458752, 0x7FFFFFFF, 0);
  if ( v9 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v36 = 73;
      goto LABEL_128;
    }
    goto LABEL_233;
  }
  v52 = v72;
  if ( !v72 )
  {
LABEL_229:
    FwFreeRules(v52, 0, v10);
    v72 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
    {
      LODWORD(v60) = v45;
      LODWORD(v59) = v49;
      LODWORD(v58) = v47;
      if ( (int)StringCchPrintfW(
                  v79,
                  0x77u,
                  L"Imported %lu rules: %lu firewall rules, %lu connection security rules, %lu main mode rules",
                  (unsigned int)(v45 + v47 + v49),
                  v58,
                  v59,
                  v60) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      FWAuditLogPolicyImported(v66, v79);
    }
    goto LABEL_233;
  }
  while ( 2 )
  {
    if ( (v52[84] & 0x60000) != 0 )
      *a4 = 1;
    if ( (v52[84] & 0x40000) != 0 )
    {
LABEL_227:
      v52 = *(_DWORD **)v52;
      if ( !v52 )
      {
        v52 = v72;
        goto LABEL_229;
      }
      continue;
    }
    break;
  }
  v53 = FWAddFirewallRule(v68, v52);
  v9 = v53;
  if ( v53 > 0 )
    v9 = (unsigned __int16)v53 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetImpl'::`2'::impl) )
      ++v47;
    goto LABEL_227;
  }
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v36 = 74;
    goto LABEL_128;
  }
LABEL_233:
  v6 = a2;
LABEL_234:
  if ( v69 )
    FwDestroyLocalTempStore();
  if ( v68 )
  {
    if ( v6 == 6 && v9 >= 0 )
      FWChangeTransactionalState(v68, 0);
    FWClosePolicyStore();
  }
  FwFreeRules(v70, 2, v10);
  FwFreeRules(v71, 1, v54);
  FwFreeRules(v72, 0, v55);
  FwFreeSets(Src, 0);
  FwFreeSets(v74, 1);
  if ( v8 != v80 )
    FwBaseFree(v8);
  v56 = FwHResultToWindowsError((unsigned int)v9);
  CTempRegKey::~CTempRegKey((CTempRegKey *)&v75);
  return v56;
}

```

## disassembly

```asm
0x1800587a0  push    rbp
0x1800587a2  push    rbx
0x1800587a3  push    rsi
0x1800587a4  push    rdi
0x1800587a5  push    r12
0x1800587a7  push    r13
0x1800587a9  push    r14
0x1800587ab  push    r15
0x1800587ad  lea     rbp, [rsp-598h]
0x1800587b5  sub     rsp, 698h
0x1800587bc  mov     rax, cs:__security_cookie
0x1800587c3  xor     rax, rsp
0x1800587c6  mov     [rbp+5D0h+var_50], rax
0x1800587cd  mov     r12, r9
0x1800587d0  mov     rsi, r8
0x1800587d3  mov     [rsp+6D0h+var_658], r8
0x1800587d8  mov     r14d, edx
0x1800587db  mov     [rsp+6D0h+var_690], edx
0x1800587df  mov     rdi, rcx
0x1800587e2  lea     rax, WPP_GLOBAL_Control
0x1800587e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800587f0  cmp     rcx, rax
0x1800587f3  jz      short loc_180058810
0x1800587f5  test    byte ptr [rcx+1Ch], 8
0x1800587f9  jz      short loc_180058810
0x1800587fb  mov     edx, 29h ; ')'
0x180058800  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x180058807  mov     rcx, [rcx+10h]
0x18005880b  call    WPP_SF_
0x180058810  mov     [rbp+5D0h+var_640], 0
0x180058818  mov     [rbp+5D0h+var_648], 0
0x180058820  mov     [rbp+5D0h+var_628], 0
0x180058828  mov     [rbp+5D0h+var_630], 0
0x180058830  mov     [rbp+5D0h+var_638], 0
0x180058838  mov     [rbp+5D0h+Src], 0
0x180058840  mov     [rbp+5D0h+var_618], 0
0x180058848  xor     r13d, r13d
0x18005884b  mov     [rbp+5D0h+var_650], r13d
0x18005884f  xor     edx, edx; Val
0x180058851  mov     r8d, 0EEh; Size
0x180058857  lea     rcx, [rbp+5D0h+var_540]; void *
0x18005885e  call    memset_0
0x180058863  mov     [r12], r13d
0x180058867  xor     edx, edx; Val
0x180058869  mov     r8d, 0D0h; Size
0x18005886f  lea     rcx, [rbp+5D0h+var_610]; void *
0x180058873  call    memset_0
0x180058878  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x18005887f  mov     [rbp+5D0h+var_610], rax
0x180058883  mov     [rbp+5D0h+hKey], r13
0x180058887  xorps   xmm0, xmm0
0x18005888a  movdqa  [rbp+5D0h+var_600], xmm0
0x18005888f  lea     rcx, [rbp+5D0h+var_610]; this
0x180058893  call    ?Init@CTempRegKey@@QEAAJXZ; CTempRegKey::Init(void)
0x180058898  mov     ebx, eax
0x18005889a  lea     r15d, [r13+1]
0x18005889e  test    eax, eax
0x1800588a0  jns     short loc_1800588DF
0x1800588a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800588a9  lea     rax, WPP_GLOBAL_Control
0x1800588b0  cmp     rcx, rax
0x1800588b3  jz      loc_180059513
0x1800588b9  test    [rcx+1Ch], r15b
0x1800588bd  jz      loc_180059513
0x1800588c3  lea     edx, [r13+2Ah]
0x1800588c7  mov     r9d, ebx
0x1800588ca  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x1800588d1  mov     rcx, [rcx+10h]
0x1800588d5  call    WPP_SF_d
0x1800588da  jmp     loc_180059513
0x1800588df  xorps   xmm0, xmm0
0x1800588e2  xor     eax, eax
0x1800588e4  movups  [rsp+6D0h+var_670], xmm0
0x1800588e9  mov     [rsp+6D0h+var_660], rax
0x1800588ee  lea     edx, [rax+11h]; unsigned int
0x1800588f1  lea     rcx, [rsp+6D0h+var_670]; this
0x1800588f6  call    ??0CPrivilegeEnabler@@QEAA@K@Z; CPrivilegeEnabler::CPrivilegeEnabler(ulong)
0x1800588fb  xorps   xmm0, xmm0
0x1800588fe  xor     eax, eax
0x180058900  movups  [rsp+6D0h+var_688], xmm0
0x180058905  mov     [rsp+6D0h+var_678], rax
0x18005890a  lea     edx, [rax+12h]; unsigned int
0x18005890d  lea     rcx, [rsp+6D0h+var_688]; this
0x180058912  call    ??0CPrivilegeEnabler@@QEAA@K@Z; CPrivilegeEnabler::CPrivilegeEnabler(ulong)
0x180058917  mov     ebx, dword ptr [rsp+6D0h+var_688+8]
0x18005891b  test    ebx, ebx
0x18005891d  jns     short loc_18005896B
0x18005891f  mov     rcx, cs:WPP_GLOBAL_Control
0x180058926  lea     rax, WPP_GLOBAL_Control
0x18005892d  cmp     rcx, rax
0x180058930  jz      short loc_180058950
0x180058932  test    [rcx+1Ch], r15b
0x180058936  jz      short loc_180058950
0x180058938  mov     edx, 2Bh ; '+'
0x18005893d  mov     r9d, ebx
0x180058940  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x180058947  mov     rcx, [rcx+10h]
0x18005894b  call    WPP_SF_d
0x180058950  mov     rcx, [rsp+6D0h+var_678]
0x180058955  call    cs:__imp_FwReleasePrivilege
0x18005895b  mov     rcx, [rsp+6D0h+var_660]
0x180058960  call    cs:__imp_FwReleasePrivilege
0x180058966  jmp     loc_180059513
0x18005896b  mov     ebx, dword ptr [rsp+6D0h+var_670+8]
0x18005896f  test    ebx, ebx
0x180058971  jns     short loc_180058993
0x180058973  mov     rcx, cs:WPP_GLOBAL_Control
0x18005897a  lea     rax, WPP_GLOBAL_Control
0x180058981  cmp     rcx, rax
0x180058984  jz      short loc_180058950
0x180058986  test    [rcx+1Ch], r15b
0x18005898a  jz      short loc_180058950
0x18005898c  mov     edx, 2Ch ; ','
0x180058991  jmp     short loc_18005893D
0x180058993  xor     r8d, r8d; dwFlags
0x180058996  mov     rdx, rsi; lpFile
0x180058999  mov     rcx, [rbp+5D0h+hKey]; hKey
0x18005899d  call    cs:__imp_RegRestoreKeyW
0x1800589a3  mov     ebx, eax
0x1800589a5  test    eax, eax
0x1800589a7  jle     short loc_1800589B2
0x1800589a9  movzx   ebx, ax
0x1800589ac  or      ebx, 80070000h
0x1800589b2  test    ebx, ebx
0x1800589b4  jns     short loc_1800589D9
0x1800589b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800589bd  lea     rax, WPP_GLOBAL_Control
0x1800589c4  cmp     rcx, rax
0x1800589c7  jz      short loc_180058950
0x1800589c9  test    [rcx+1Ch], r15b
0x1800589cd  jz      short loc_180058950
0x1800589cf  mov     edx, 2Dh ; '-'
0x1800589d4  jmp     loc_18005893D
0x1800589d9  mov     rcx, [rsp+6D0h+var_678]
0x1800589de  call    cs:__imp_FwReleasePrivilege
0x1800589e4  mov     rcx, [rsp+6D0h+var_660]
0x1800589e9  call    cs:__imp_FwReleasePrivilege
0x1800589ef  lea     r8, [rbp+5D0h+var_640]
0x1800589f3  mov     rdx, [rbp+5D0h+hKey]
0x1800589f7  lea     rcx, [rbp+5D0h+var_5F0]
0x1800589fb  call    cs:__imp_FwCreateLocalTempStore
0x180058a01  mov     ebx, eax
0x180058a03  test    eax, eax
0x180058a05  jns     short loc_180058A32
0x180058a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180058a0e  lea     rax, WPP_GLOBAL_Control
0x180058a15  cmp     rcx, rax
0x180058a18  jz      loc_180059513
0x180058a1e  test    [rcx+1Ch], r15b
0x180058a22  jz      loc_180059513
0x180058a28  mov     edx, 2Eh ; '.'
0x180058a2d  jmp     loc_1800588C7
0x180058a32  mov     esi, 221h
0x180058a37  mov     ecx, esi
0x180058a39  lea     rax, [rbp+5D0h+var_648]
0x180058a3d  mov     [rsp+6D0h+var_6A8], rax
0x180058a42  mov     dword ptr [rsp+6D0h+var_6B0], 0
0x180058a4a  mov     r9d, 2
0x180058a50  mov     r8d, r14d
0x180058a53  mov     rdx, rdi
0x180058a56  call    FWOpenPolicyStore
0x180058a5b  mov     ebx, eax
0x180058a5d  test    eax, eax
0x180058a5f  jle     short loc_180058A6A
0x180058a61  movzx   ebx, ax
0x180058a64  or      ebx, 80070000h
0x180058a6a  test    ebx, ebx
0x180058a6c  jns     short loc_180058A99
0x180058a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058a75  lea     rax, WPP_GLOBAL_Control
0x180058a7c  cmp     rcx, rax
0x180058a7f  jz      loc_180059513
0x180058a85  test    [rcx+1Ch], r15b
0x180058a89  jz      loc_180059513
0x180058a8f  mov     edx, 2Fh ; '/'
0x180058a94  jmp     loc_1800588C7
0x180058a99  cmp     r14d, 6
0x180058a9d  jnz     short loc_180058AE9
0x180058a9f  mov     edx, r15d
0x180058aa2  mov     rcx, [rbp+5D0h+var_648]
0x180058aa6  call    FWChangeTransactionalState
0x180058aab  mov     ebx, eax
0x180058aad  test    eax, eax
0x180058aaf  jle     short loc_180058ABA
0x180058ab1  movzx   ebx, ax
0x180058ab4  or      ebx, 80070000h
0x180058aba  test    ebx, ebx
0x180058abc  jns     short loc_180058AE9
0x180058abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180058ac5  lea     rax, WPP_GLOBAL_Control
0x180058acc  cmp     rcx, rax
0x180058acf  jz      loc_180059513
0x180058ad5  test    [rcx+1Ch], r15b
0x180058ad9  jz      loc_180059513
0x180058adf  mov     edx, 30h ; '0'
0x180058ae4  jmp     loc_1800588C7
0x180058ae9  mov     edi, r15d
0x180058aec  lea     eax, [rdi-1]
0x180058aef  cmp     eax, r15d
0x180058af2  jbe     loc_180058C80
0x180058af8  cmp     edi, 0Bh
0x180058afb  jz      loc_180058C80
0x180058b01  lea     r13, [rbp+5D0h+var_450]
0x180058b08  mov     [rbp+5D0h+var_650], 400h
0x180058b0f  xor     ebx, ebx
0x180058b11  cmp     ebx, 800700EAh
0x180058b17  jnz     short loc_180058B43
0x180058b19  lea     rax, [rbp+5D0h+var_450]
0x180058b20  cmp     r13, rax
0x180058b23  jz      short loc_180058B2E
0x180058b25  mov     rcx, r13
0x180058b28  call    cs:__imp_FwBaseFree
0x180058b2e  mov     ecx, [rbp+5D0h+var_650]
0x180058b31  call    cs:__imp_FwBaseAlloc
0x180058b37  mov     r13, rax
0x180058b3a  test    rax, rax
0x180058b3d  jz      loc_180058C9D
0x180058b43  lea     r9, [rbp+5D0h+var_650]
0x180058b47  mov     r8, r13
0x180058b4a  mov     edx, edi
0x180058b4c  mov     rcx, [rbp+5D0h+hKey]
0x180058b50  call    cs:__imp_FwGetGlobalConfigFromLocalTempStore
0x180058b56  mov     ebx, eax
0x180058b58  cmp     eax, 800700EAh
0x180058b5d  jz      short loc_180058B11
0x180058b5f  cmp     eax, 80070002h
0x180058b64  jz      short loc_180058B7B
0x180058b66  cmp     eax, 80070032h
0x180058b6b  jz      short loc_180058B7B
0x180058b6d  test    eax, eax
0x180058b6f  js      loc_180058CCD
0x180058b75  mov     r9d, [rbp+5D0h+var_650]
0x180058b79  jmp     short loc_180058B90
0x180058b7b  cmp     edi, 0Ah
0x180058b7e  jnz     loc_180058C23
0x180058b84  mov     [r13+0], esi
0x180058b88  lea     r9d, [rdi-6]
0x180058b8c  mov     [rbp+5D0h+var_650], r9d
0x180058b90  test    r9d, r9d
0x180058b93  jnz     short loc_180058B9E
0x180058b95  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180058b9a  mov     r9d, [rbp+5D0h+var_650]
0x180058b9e  cmp     edi, 0Ah
0x180058ba1  jnz     short loc_180058BB9
0x180058ba3  cmp     [r13+0], esi
0x180058ba7  jbe     short loc_180058BB9
0x180058ba9  mov     [r12], r15d
0x180058bad  mov     [r13+0], esi
0x180058bb1  lea     r9d, [rdi-6]
0x180058bb5  mov     [rbp+5D0h+var_650], r9d
0x180058bb9  mov     r8, r13
0x180058bbc  mov     edx, edi
0x180058bbe  mov     rcx, [rbp+5D0h+var_648]
0x180058bc2  call    FWSetGlobalConfig2
0x180058bc7  mov     ebx, eax
0x180058bc9  cmp     eax, 32h ; '2'
0x180058bcc  jnz     short loc_180058BF4
0x180058bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180058bd5  lea     rsi, WPP_GLOBAL_Control
0x180058bdc  cmp     rcx, rsi
0x180058bdf  jz      loc_180058C87
0x180058be5  test    byte ptr [rcx+1Ch], 2
0x180058be9  jz      loc_180058C87
0x180058bef  lea     edx, [rax+3]
0x180058bf2  jmp     short loc_180058C56
0x180058bf4  test    eax, eax
0x180058bf6  jle     short loc_180058C01
0x180058bf8  movzx   ebx, ax
0x180058bfb  or      ebx, 80070000h
0x180058c01  test    ebx, ebx
0x180058c03  js      loc_180058CF8
0x180058c09  lea     rax, [rbp+5D0h+var_450]
0x180058c10  cmp     r13, rax
0x180058c13  jz      short loc_180058C80
0x180058c15  mov     rcx, r13
0x180058c18  call    cs:__imp_FwBaseFree
0x180058c1e  xor     r13d, r13d
0x180058c21  jmp     short loc_180058C80
0x180058c23  xor     r9d, r9d
0x180058c26  xor     r8d, r8d
0x180058c29  mov     edx, edi
0x180058c2b  mov     rcx, [rbp+5D0h+var_648]
0x180058c2f  call    FWSetGlobalConfig2
0x180058c34  mov     ebx, eax
0x180058c36  cmp     eax, 32h ; '2'
0x180058c39  jnz     short loc_180058C6B
0x180058c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058c42  lea     rsi, WPP_GLOBAL_Control
0x180058c49  cmp     rcx, rsi
0x180058c4c  jz      short loc_180058C87
0x180058c4e  test    byte ptr [rcx+1Ch], 2
0x180058c52  jz      short loc_180058C87
0x180058c54  mov     edx, eax
0x180058c56  mov     r9d, edi
0x180058c59  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x180058c60  mov     rcx, [rcx+10h]
0x180058c64  call    WPP_SF_d
0x180058c69  jmp     short loc_180058C87
0x180058c6b  test    eax, eax
0x180058c6d  jle     short loc_180058C78
  ... truncated ...
```
