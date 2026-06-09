# ModifyEntryListInRegistry

- ea: `0x180089e30`
- end: `0x18008c1bd`
- name: `ModifyEntryListInRegistry`
- size: `9101`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b698`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18005cb9c`
- `0x18005d748`
- `0x18005dec8`
- `0x18007c0c8`
- `0x18007c5d8`
- `0x180080e7c`
- `0x180089b70`
- `0x180089df8`
- `0x180089e30`
- `0x18008c1c4`
- `0x18008c348`
- `0x18008c5b0`
- `0x18008c624`
- `0x18008dcbc`
- `0x18008dd34`
- `0x18008e488`
- `0x18008e54c`
- `0x18008e634`
- `0x18008e6bc`
- `0x18008e89c`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x18008b5a8`
- `msvcrt!_ultoa_s` at `0x18008b5a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008a08f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008a08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b80f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b82d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b86f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b8c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b80f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b82d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b86f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b8c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c04e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180089fe3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a06e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a0d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008b787`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180089fe3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a06e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a0d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008b787`

## string_xrefs

- `0x18008a2cf`: `NegotiateMultilinkAlways`
- `0x18008a2a7`: `SwCompression`
- `0x18008a361`: `RedialAttempts`
- `0x18008a23d`: `ExcludedProtocols`
- `0x18008a25e`: `LcpExtensions`
- `0x18008a3c4`: `RedialOnLinkFailure`
- `0x18008a40d`: `CustomDialDll`
- `0x18008a470`: `ForceSecureCompartment`
- `0x18008a44f`: `CustomRasDialDll`
- `0x18008a750`: `ShowMonitorIconInTaskBar`
- `0x18008a65b`: `PreferredCompression`
- `0x18008a636`: `PreferredProtocol`
- `0x18008a69e`: `PreferredMdmProtocol`
- `0x18008a830`: `IpHeaderCompression`
- `0x18008ac7d`: `ImsConfig`
- `0x18008ad29`: `CacheCredentials`
- `0x18008b189`: `ApnInfoAccessPoint`
- `0x18008b1fa`: `DeviceComplianceEnabled`
- `0x18008b1d6`: `ApnInfoCompression`
- `0x18008b24a`: `DeviceComplianceSsoEku`
- `0x18008b222`: `DeviceComplianceSsoEnabled`
- `0x18008b105`: `SecurityDescriptor`
- `0x18008b3c8`: `PowershellCreatedProfile`
- `0x18008b4b5`: `AutoConfigScript`
- `0x18008b26b`: `DeviceComplianceSsoIssuer`
- `0x18008b6cc`: `PluginStorage`

## pseudocode

```c
__int64 __fastcall ModifyEntryListInRegistry(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // r14
  struct _LIST_ENTRY *v4; // rcx
  __int64 *v5; // rax
  unsigned int ProvisionedProfilePath; // ebx
  int v7; // esi
  __int64 v8; // r13
  __int64 v9; // rdi
  _DWORD *v10; // r15
  int v11; // eax
  WCHAR *v12; // rbx
  const WCHAR *v13; // rcx
  unsigned int v14; // esi
  __int64 result; // rax
  HGLOBAL v16; // r14
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rax
  void *v19; // rsi
  unsigned int v20; // eax
  unsigned int inserted; // eax
  const char *v22; // r8
  const char *v23; // r8
  __int64 v24; // r8
  const char *v25; // r8
  const char *v26; // r8
  const char *v27; // r8
  const char *v28; // r8
  const char *v29; // r8
  const char *v30; // r8
  const char *v31; // r8
  const char *v32; // r8
  const char *v33; // r8
  const char *v34; // r8
  const char *v35; // r8
  const char *v36; // r8
  const char *v37; // r8
  const char *v38; // r8
  const char *v39; // r8
  const char *v40; // r8
  const char *v41; // r8
  const char *v42; // r8
  const char *v43; // r8
  __int64 v44; // r8
  const char *v45; // r8
  const char *v46; // r8
  const WCHAR *v47; // r8
  const WCHAR *v48; // r8
  const WCHAR *v49; // r8
  const WCHAR *v50; // r8
  const WCHAR *v51; // r8
  const WCHAR *v52; // r8
  const char *v53; // r8
  const WCHAR *v54; // r8
  const WCHAR *v55; // r8
  const char *v56; // r8
  const char *v57; // r8
  const char *v58; // r8
  const char *v59; // r8
  __int64 v60; // r8
  __int64 v61; // r8
  __int64 v62; // r9
  const char *v63; // r8
  __int64 v64; // r8
  __int64 v65; // r9
  const char *v66; // r8
  const char *v67; // r8
  __int64 v68; // r8
  __int64 v69; // r8
  const char *v70; // r8
  void *v71; // rcx
  HGLOBAL v72; // rsi
  unsigned int v73; // eax
  void *v74; // rcx
  HGLOBAL v75; // rsi
  const char *v76; // r8
  const char *v77; // r8
  const char *v78; // r8
  const char *v79; // r8
  __int64 v80; // r8
  __int64 v81; // r8
  __int64 v82; // r8
  const char *v83; // r8
  const char *v84; // r8
  const char *v85; // r8
  const char *v86; // r8
  const char *v87; // r8
  unsigned int v88; // ebx
  HKEY v89; // rsi
  __int64 v90; // r8
  const char *v91; // r8
  const char *v92; // r8
  unsigned int v93; // eax
  const char *v94; // r8
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 *v97; // rax
  __int64 i; // r14
  __int64 v99; // rsi
  __int64 v100; // rax
  void *v101; // r15
  __int64 v102; // r8
  struct _LIST_ENTRY *v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // r9
  struct _LIST_ENTRY *v106; // rcx
  __int64 v107; // rdx
  struct _LIST_ENTRY *v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rdx
  unsigned int v111; // edi
  HKEY v112; // [rsp+20h] [rbp-59h] BYREF
  HGLOBAL v113; // [rsp+28h] [rbp-51h]
  int v114; // [rsp+30h] [rbp-49h]
  HKEY v115; // [rsp+38h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-39h] BYREF
  HGLOBAL hMem; // [rsp+48h] [rbp-31h]
  __int64 v118; // [rsp+50h] [rbp-29h]
  HKEY v119; // [rsp+58h] [rbp-21h] BYREF
  unsigned int *v120; // [rsp+60h] [rbp-19h]
  char Buffer[16]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v122; // [rsp+78h] [rbp-1h]
  __int16 v123; // [rsp+88h] [rbp+Fh]

  v2 = a2;
  v120 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 134, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(__int64 **)(a1 + 16);
  ProvisionedProfilePath = 0;
  v7 = 0;
  hKey = 0;
  v112 = 0;
  v114 = 0;
  v8 = *v5;
  if ( !*v5 )
    goto LABEL_524;
  while ( 1 )
  {
    v9 = *(_QWORD *)(v8 + 16);
    v10 = (_DWORD *)(v9 + 540);
    if ( !*(_DWORD *)(v9 + 532) && !*v10 )
      goto LABEL_15;
    v11 = *(_DWORD *)(a1 + 32) & 0x100;
    if ( v11 && *(_DWORD *)(v9 + 548) )
    {
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
        WPP_SF_S(v4[1].Flink, 135, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, *(_QWORD *)(v9 + 8));
      *(_DWORD *)(v9 + 532) = 0;
      *(_DWORD *)(v9 + 540) = 0;
      v4 = WPP_GLOBAL_Control;
      goto LABEL_15;
    }
    v113 = 0;
    v118 = 0;
    hMem = 0;
    if ( *(_DWORD *)(v9 + 548) && *(_DWORD *)(a1 + 8) != 4 )
    {
      ProvisionedProfilePath = GetProvisionedProfilePath(*(STRSAFE_LPCWSTR *)a1, *(STRSAFE_LPCWSTR *)(v9 + 8));
      if ( ProvisionedProfilePath )
        goto LABEL_520;
      v12 = (WCHAR *)hMem;
      goto LABEL_26;
    }
    v13 = *(const WCHAR **)a1;
    if ( v11 )
    {
      ProvisionedProfilePath = GetLUAPhonebookPath(v13);
      if ( ProvisionedProfilePath )
        goto LABEL_520;
      v12 = (WCHAR *)hMem;
    }
    else
    {
      v12 = (WCHAR *)StrDup(v13);
    }
    if ( !v12 )
      break;
LABEL_26:
    v14 = RegistryPathConverter(v12);
    if ( v12 )
      GlobalFree(v12);
    result = 235;
    if ( v14 == 235 )
      return result;
    v16 = v113;
    if ( !(unsigned int)RegSetKeySecurityInfo((LPCSTR)v113) )
      goto LABEL_34;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 137, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
LABEL_34:
      v17 = WPP_GLOBAL_Control;
    }
    if ( v14 )
    {
      if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v17[1].Blink) < 0 && BYTE1(v17[1].Blink) >= 2u )
        WPP_SF_d(v17[1].Flink, 138, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v14);
      return v14;
    }
    ProvisionedProfilePath = CreateOrOpenSubkey(v118, v16, &hKey);
    if ( v16 )
      GlobalFree(v16);
    if ( ProvisionedProfilePath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v110 = 139;
        goto LABEL_533;
      }
      return ProvisionedProfilePath;
    }
    UpdateEntryTimeStamp(v9);
    RegDeleteTreeW(hKey, *(LPCWSTR *)(v9 + 8));
    if ( !*v10 )
    {
      v18 = StrdupWtoA(*(LPCWCH *)(v9 + 8));
      v19 = (void *)v18;
      if ( v18 )
      {
        v20 = CreateOrOpenSubkey(hKey, v18, &v112);
        ProvisionedProfilePath = v20;
        if ( !v20 )
        {
          GlobalFree(v19);
          inserted = RegInsertLong(v112, "Encoding", 1);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 142;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "PBVersion", 8);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 143;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "Type", *(unsigned int *)(v9 + 24));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 144;
            goto LABEL_489;
          }
          v22 = "1";
          if ( !*(_DWORD *)(v9 + 176) )
            v22 = "0";
          inserted = RegInsertStringA(v112, "AutoLogon", v22);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 145;
            goto LABEL_489;
          }
          v23 = "1";
          if ( !*(_DWORD *)(v9 + 180) )
            v23 = "0";
          inserted = RegInsertStringA(v112, "UseRasCredentials", v23);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 146;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "LowDateTime", *(unsigned int *)(v9 + 16));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 147;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "HighDateTime", *(unsigned int *)(v9 + 20));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 148;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "DialParamsUID", *(unsigned int *)(v9 + 456));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 149;
            goto LABEL_489;
          }
          v24 = *(_QWORD *)(v9 + 464);
          if ( v24 )
          {
            inserted = RegInsertBinary(v112, "Guid", v24, 16);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v104 = 150;
                goto LABEL_489;
              }
              goto LABEL_392;
            }
          }
          inserted = RegInsertLong(v112, "VpnStrategy", *(unsigned int *)(v9 + 168));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 151;
            goto LABEL_489;
          }
          inserted = RegInsertLong(v112, "ExcludedProtocols", *(unsigned int *)(v9 + 236));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 152;
            goto LABEL_489;
          }
          v25 = "1";
          if ( !*(_DWORD *)(v9 + 240) )
            v25 = "0";
          inserted = RegInsertStringA(v112, "LcpExtensions", v25);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 153;
LABEL_489:
            v105 = inserted;
            goto LABEL_490;
          }
          inserted = RegInsertLong(v112, "DataEncryption", *(unsigned int *)(v9 + 172));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v104 = 154;
            goto LABEL_489;
          }
          v26 = "1";
          if ( !*(_DWORD *)(v9 + 244) )
            v26 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "SwCompression", v26);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v27 = "1";
          if ( !*(_DWORD *)(v9 + 248) )
            v27 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "NegotiateMultilinkAlways", v27);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v28 = "1";
          if ( !*(_DWORD *)(v9 + 252) )
            v28 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "SkipDoubleDialDialog", v28);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "DialMode", *(unsigned int *)(v9 + 132));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "OverridePref", *(unsigned int *)(v9 + 144));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "RedialAttempts", *(unsigned int *)(v9 + 148));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "RedialSeconds", *(unsigned int *)(v9 + 152));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IdleDisconnectSeconds", *(unsigned int *)(v9 + 156));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v29 = "1";
          if ( !*(_DWORD *)(v9 + 160) )
            v29 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "RedialOnLinkFailure", v29);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "CallbackMode", *(unsigned int *)(v9 + 420));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "CustomDialDll", *(_QWORD *)(v9 + 432));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "CustomDialFunc", *(_QWORD *)(v9 + 440));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "CustomRasDialDll", *(_QWORD *)(v9 + 448));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          *(_DWORD *)(v9 + 184) = 0;
          ProvisionedProfilePath = RegInsertStringA(v112, "ForceSecureCompartment", "0");
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v30 = "1";
          if ( !*(_DWORD *)(v9 + 188) )
            v30 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DisableIKENameEkuCheck", v30);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v31 = "1";
          if ( !*(_DWORD *)(v9 + 424) )
            v31 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "AuthenticateServer", v31);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v32 = "1";
          if ( !*(_DWORD *)(v9 + 256) )
            v32 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "ShareMsFilePrint", v32);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v33 = "1";
          if ( !*(_DWORD *)(v9 + 260) )
            v33 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "BindMsNetClient", v33);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v34 = "1";
          if ( !*(_DWORD *)(v9 + 40) )
            v34 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "SharedPhoneNumbers", v34);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v35 = "1";
          if ( !*(_DWORD *)(v9 + 44) )
            v35 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "GlobalDeviceSettings", v35);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "PrerequisiteEntry", *(_QWORD *)(v9 + 56));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "PrerequisitePbk", *(_QWORD *)(v9 + 64));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "PreferredPort", *(_QWORD *)(v9 + 72));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "PreferredDevice", *(_QWORD *)(v9 + 80));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "PreferredBps", *(unsigned int *)(v9 + 88));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v36 = "1";
          if ( !*(_DWORD *)(v9 + 92) )
            v36 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreferredHwFlow", v36);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v37 = "1";
          if ( !*(_DWORD *)(v9 + 96) )
            v37 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreferredProtocol", v37);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v38 = "1";
          if ( !*(_DWORD *)(v9 + 100) )
            v38 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreferredCompression", v38);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "PreferredSpeaker", *(unsigned int *)(v9 + 104));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "PreferredMdmProtocol", *(unsigned int *)(v9 + 108));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v39 = "1";
          if ( !*(_DWORD *)(v9 + 116) )
            v39 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreviewUserPw", v39);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v40 = "1";
          if ( !*(_DWORD *)(v9 + 120) )
            v40 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreviewDomain", v40);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v41 = "1";
          if ( !*(_DWORD *)(v9 + 124) )
            v41 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PreviewPhoneNumber", v41);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v42 = "1";
          if ( !*(_DWORD *)(v9 + 112) )
            v42 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "ShowDialingProgress", v42);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v43 = "1";
          if ( !*(_DWORD *)(v9 + 48) )
            v43 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "ShowMonitorIconInTaskBar", v43);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "CustomAuthKey", *(unsigned int *)(v9 + 192));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v44 = *(_QWORD *)(v9 + 200);
          if ( v44 )
          {
            ProvisionedProfilePath = RegInsertBinary(v112, "CustomAuthData", v44, *(unsigned int *)(v9 + 208));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "AuthRestrictions", *(unsigned int *)(v9 + 164));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v45 = "1";
          if ( !*(_DWORD *)(v9 + 272) )
            v45 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "IpPrioritizeRemote", v45);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpInterfaceMetric", *(unsigned int *)(v9 + 352));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v46 = "1";
          if ( !*(_DWORD *)(v9 + 276) )
            v46 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "IpHeaderCompression", v46);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v47 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 280) )
            v47 = *(const WCHAR **)(v9 + 280);
          ProvisionedProfilePath = RegInsertString(v112, "IpAddress", v47);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v48 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 288) )
            v48 = *(const WCHAR **)(v9 + 288);
          ProvisionedProfilePath = RegInsertString(v112, "IpDnsAddress", v48);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v49 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 296) )
            v49 = *(const WCHAR **)(v9 + 296);
          ProvisionedProfilePath = RegInsertString(v112, "IpDns2Address", v49);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v50 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 304) )
            v50 = *(const WCHAR **)(v9 + 304);
          ProvisionedProfilePath = RegInsertString(v112, "IpWinsAddress", v50);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v51 = L"0.0.0.0";
          if ( *(_QWORD *)(v9 + 312) )
            v51 = *(const WCHAR **)(v9 + 312);
          ProvisionedProfilePath = RegInsertString(v112, "IpWins2Address", v51);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpAssign", *(unsigned int *)(v9 + 320));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpNameAssign", *(unsigned int *)(v9 + 324));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpDnsFlags", *(unsigned int *)(v9 + 328));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpNBTFlags", *(unsigned int *)(v9 + 332));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "TcpWindowSize", *(unsigned int *)(v9 + 336));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "UseFlags", *(unsigned int *)(v9 + 136));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "IpSecFlags", *(unsigned int *)(v9 + 140));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "IpDnsSuffix", *(_QWORD *)(v9 + 344));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "Ipv6Assign", *(unsigned int *)(v9 + 356));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v52 = L"::";
          if ( *(_QWORD *)(v9 + 360) )
            v52 = *(const WCHAR **)(v9 + 360);
          ProvisionedProfilePath = RegInsertString(v112, "Ipv6Address", v52);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "Ipv6PrefixLength", *(unsigned int *)(v9 + 368));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v53 = "1";
          if ( !*(_DWORD *)(v9 + 372) )
            v53 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "Ipv6PrioritizeRemote", v53);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "Ipv6InterfaceMetric", *(unsigned int *)(v9 + 416));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "Ipv6NameAssign", *(unsigned int *)(v9 + 376));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v54 = L"::";
          if ( *(_QWORD *)(v9 + 384) )
            v54 = *(const WCHAR **)(v9 + 384);
          ProvisionedProfilePath = RegInsertString(v112, "Ipv6DnsAddress", v54);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v55 = L"::";
          if ( *(_QWORD *)(v9 + 392) )
            v55 = *(const WCHAR **)(v9 + 392);
          ProvisionedProfilePath = RegInsertString(v112, "Ipv6Dns2Address", v55);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertBinary(v112, "Ipv6Prefix", v9 + 408, 8);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertBinary(v112, "Ipv6InterfaceId", v9 + 400, 8);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v56 = "1";
          if ( !*(_DWORD *)(v9 + 544) )
            v56 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DisableClassBasedDefaultRoute", v56);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v57 = "1";
          if ( !*(_DWORD *)(v9 + 488) )
            v57 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DisableMobility", v57);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "NetworkOutageTime", *(unsigned int *)(v9 + 492));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          if ( (unsigned int)RegInsertString(v112, "IDI", *(_QWORD *)(v9 + 496)) )
          {
            inserted = 1;
            ProvisionedProfilePath = 1;
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 155;
              goto LABEL_489;
            }
LABEL_392:
            RegCloseKey(v112);
LABEL_504:
            RegCloseKey(hKey);
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v110 = 179;
              goto LABEL_533;
            }
            return ProvisionedProfilePath;
          }
          if ( (unsigned int)RegInsertString(v112, "IDR", *(_QWORD *)(v9 + 504)) )
          {
            inserted = 1;
            ProvisionedProfilePath = 1;
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 156;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          v58 = "1";
          if ( !*(_DWORD *)(v9 + 512) )
            v58 = "0";
          inserted = RegInsertStringA(v112, "ImsConfig", v58);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 157;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          inserted = RegInsertLong(v112, "IdiType", *(unsigned int *)(v9 + 516));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 158;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          inserted = RegInsertLong(v112, "IdrType", *(unsigned int *)(v9 + 520));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 159;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "ProvisionType", *(unsigned int *)(v9 + 548));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "PreSharedKey", *(_QWORD *)(v9 + 552));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v59 = "1";
          if ( !*(_DWORD *)(v9 + 128) )
            v59 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "CacheCredentials", v59);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "NumCustomPolicy", *(unsigned int *)(v9 + 596));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v60 = *(_QWORD *)(v9 + 608);
          if ( v60 )
          {
            if ( *(_DWORD *)(v9 + 596) )
            {
              ProvisionedProfilePath = RegInsertBinary(v112, "CustomIPSecPolicies", v60, *(unsigned int *)(v9 + 600));
              if ( ProvisionedProfilePath )
                goto LABEL_392;
            }
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumEku", *(unsigned int *)(v9 + 616));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v61 = *(_QWORD *)(v9 + 624);
          if ( v61 )
          {
            if ( *(_DWORD *)(v9 + 616) )
            {
              v62 = *(unsigned int *)(v9 + 620);
              if ( (_DWORD)v62 )
              {
                ProvisionedProfilePath = RegInsertBinary(v112, "CertificateEKU", v61, v62);
                if ( ProvisionedProfilePath )
                  goto LABEL_392;
              }
            }
          }
          v63 = "1";
          if ( !*(_DWORD *)(v9 + 632) )
            v63 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "UseMachineRootCert", v63);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          if ( *(_DWORD *)(v9 + 632) == 1 )
          {
            v64 = *(_QWORD *)(v9 + 648);
            if ( v64 )
            {
              v65 = *(unsigned int *)(v9 + 640);
              if ( (_DWORD)v65 )
              {
                ProvisionedProfilePath = RegInsertBinary(v112, "RootCertificate", v64, v65);
                if ( ProvisionedProfilePath )
                  goto LABEL_392;
              }
            }
          }
          v66 = "1";
          if ( !*(_DWORD *)(v9 + 524) )
            v66 = "0";
          inserted = RegInsertStringA(v112, "Disable_IKEv2_Fragmentation", v66);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 160;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          v67 = "1";
          if ( !*(_DWORD *)(v9 + 528) )
            v67 = "0";
          inserted = RegInsertStringA(v112, "PlumbIKEv2TSAsRoutes", v67);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 161;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumServers", *(unsigned int *)(v9 + 656));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          if ( *(_QWORD *)(v9 + 664) )
          {
            if ( *(_DWORD *)(v9 + 656) )
            {
              inserted = RegCreateServerLists(v112);
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v103 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v104 = 162;
                  goto LABEL_489;
                }
                goto LABEL_392;
              }
            }
          }
          inserted = RegInsertLong(v112, "RouteVersion", 1);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 163;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          inserted = RegInsertLong(v112, "NumRoutes", *(unsigned int *)(v9 + 672));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 164;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          v68 = *(_QWORD *)(v9 + 680);
          if ( v68 )
          {
            if ( *(_DWORD *)(v9 + 672) )
            {
              inserted = RegInsertBinary(v112, "Routes", v68, *(unsigned int *)(v9 + 676));
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v103 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v104 = 165;
                  goto LABEL_489;
                }
                goto LABEL_392;
              }
            }
          }
          inserted = RegInsertLong(v112, "NumNrptRules", *(unsigned int *)(v9 + 688));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 166;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          v69 = *(_QWORD *)(v9 + 696);
          if ( v69 )
          {
            if ( *(_DWORD *)(v9 + 688) )
            {
              inserted = RegInsertBinary(v112, "NrptRules", v69, *(unsigned int *)(v9 + 692));
              ProvisionedProfilePath = inserted;
              if ( inserted )
              {
                v103 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v104 = 167;
                  goto LABEL_489;
                }
                goto LABEL_392;
              }
            }
          }
          v70 = "1";
          if ( !*(_DWORD *)(v9 + 704) )
            v70 = "0";
          inserted = RegInsertStringA(v112, "AutoTiggerCapable", v70);
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 168;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumAppIds", *(unsigned int *)(v9 + 728));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v71 = *(void **)(v9 + 736);
          if ( v71 && *(_DWORD *)(v9 + 728) )
          {
            v113 = 0;
            inserted = RegCreateDtlList(v71);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v104 = 169;
                goto LABEL_489;
              }
              goto LABEL_392;
            }
            v72 = v113;
            v73 = RegInsertStringList(v112, "ApplicationIds");
            ProvisionedProfilePath = v73;
            if ( v73 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 170, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v73);
              }
              DtlDestroyList(v72);
              goto LABEL_392;
            }
            DtlDestroyList(v72);
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumClassicAppIds", *(unsigned int *)(v9 + 708));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v74 = *(void **)(v9 + 720);
          if ( v74 && *(_DWORD *)(v9 + 708) )
          {
            v113 = 0;
            inserted = RegCreateDtlList(v74);
            ProvisionedProfilePath = inserted;
            if ( inserted )
            {
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v104 = 171;
                goto LABEL_489;
              }
              goto LABEL_392;
            }
            v75 = v113;
            ProvisionedProfilePath = RegInsertStringList(v112, "ClassicApplicationIds");
            if ( ProvisionedProfilePath )
            {
              DtlDestroyList(v75);
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_392;
              }
              v104 = 172;
              v105 = ProvisionedProfilePath;
LABEL_490:
              WPP_SF_d(v103[1].Flink, v104, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v105);
              goto LABEL_392;
            }
            DtlDestroyList(v75);
          }
          inserted = RegInsertString(v112, "SecurityDescriptor", *(_QWORD *)(v9 + 744));
          ProvisionedProfilePath = inserted;
          if ( inserted )
          {
            v103 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v104 = 173;
              goto LABEL_489;
            }
            goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertString(v112, "ApnInfoProviderId", *(_QWORD *)(v9 + 864));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "ApnInfoUsername", *(_QWORD *)(v9 + 880));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "ApnInfoPassword", *(_QWORD *)(v9 + 888));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "ApnInfoAccessPoint", *(_QWORD *)(v9 + 872));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "ApnInfoAuthentication", *(unsigned int *)(v9 + 900));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v76 = "1";
          if ( !*(_DWORD *)(v9 + 896) )
            v76 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "ApnInfoCompression", v76);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v77 = "1";
          if ( !*(_DWORD *)(v9 + 904) )
            v77 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DeviceComplianceEnabled", v77);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v78 = "1";
          if ( !*(_DWORD *)(v9 + 912) )
            v78 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DeviceComplianceSsoEnabled", v78);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "DeviceComplianceSsoEku", *(_QWORD *)(v9 + 920));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertString(v112, "DeviceComplianceSsoIssuer", *(_QWORD *)(v9 + 928));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "FlagsSet", *(unsigned int *)(v9 + 952));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "Options", *(unsigned int *)(v9 + 956));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v79 = "1";
          if ( !*(_DWORD *)(v9 + 788) )
            v79 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "DisableDefaultDnsSuffixes", v79);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "NumTrustedNetworks", *(unsigned int *)(v9 + 792));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v80 = *(_QWORD *)(v9 + 800);
          if ( v80 )
          {
            if ( *(_DWORD *)(v9 + 792) )
            {
              ProvisionedProfilePath = RegInsertBinary(v112, "TrustedNetworks", v80, *(unsigned int *)(v9 + 796));
              if ( ProvisionedProfilePath )
                goto LABEL_392;
            }
          }
          v81 = *(_QWORD *)(v9 + 760);
          if ( v81 )
          {
            ProvisionedProfilePath = RegInsertBinary(v112, "ThirdPartyProfileInfo", v81, *(unsigned int *)(v9 + 752));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumDnsSearchSuffixes", *(unsigned int *)(v9 + 768));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v82 = *(_QWORD *)(v9 + 776);
          if ( v82 )
          {
            ProvisionedProfilePath = RegInsertBinary(v112, "DnsSuffixSearchList", v82, *(unsigned int *)(v9 + 772));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          v83 = "1";
          if ( !*(_DWORD *)(v9 + 784) )
            v83 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PowershellCreatedProfile", v83);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          ProvisionedProfilePath = RegInsertLong(v112, "ProxyFlags", *(unsigned int *)(v9 + 560));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v84 = "1";
          if ( !*(_DWORD *)(v9 + 820) )
            v84 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "ProxySettingsModified", v84);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          if ( (*(_BYTE *)(v9 + 560) & 2) != 0 )
          {
            ProvisionedProfilePath = RegInsertString(v112, "Proxy", *(_QWORD *)(v9 + 576));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
            ProvisionedProfilePath = RegInsertString(v112, "ExcludeList", *(_QWORD *)(v9 + 584));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
            v85 = "1";
            if ( !*(_DWORD *)(v9 + 592) )
              v85 = "0";
            ProvisionedProfilePath = RegInsertStringA(v112, "BypassProxyForLocal", v85);
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          if ( (*(_BYTE *)(v9 + 560) & 4) != 0 )
          {
            ProvisionedProfilePath = RegInsertString(v112, "AutoConfigScript", *(_QWORD *)(v9 + 568));
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertString(v112, "ProvisioningAuthority", *(_QWORD *)(v9 + 808));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v86 = "1";
          if ( !*(_DWORD *)(v9 + 816) )
            v86 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "AuthTypeOTP", v86);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v87 = "1";
          if ( !*(_DWORD *)(v9 + 824) )
            v87 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "GREKeyDefined", v87);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          if ( *(_DWORD *)(v9 + 824) )
          {
            v88 = *(_DWORD *)(v9 + 828);
            v89 = v112;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
            }
            v123 = 0;
            *(_OWORD *)Buffer = 0;
            v122 = 0;
            _ultoa_s(v88, Buffer, 0x22u, 10);
            ProvisionedProfilePath = RegInsertStringA(v89, "GREKey", Buffer);
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          ProvisionedProfilePath = RegInsertLong(v112, "NumPerAppTrafficFilters", *(unsigned int *)(v9 + 832));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v90 = *(_QWORD *)(v9 + 840);
          if ( v90 )
          {
            if ( *(_DWORD *)(v9 + 832) )
            {
              ProvisionedProfilePath = RegInsertBinary(v112, "PerAppTrafficFilters", v90, *(unsigned int *)(v9 + 836));
              if ( ProvisionedProfilePath )
                goto LABEL_392;
            }
          }
          v91 = "1";
          if ( !*(_DWORD *)(v9 + 848) )
            v91 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "AlwaysOnCapable", v91);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v92 = "1";
          if ( !*(_DWORD *)(v9 + 856) )
            v92 = "0";
          v93 = RegInsertStringA(v112, "DeviceTunnel", v92);
          ProvisionedProfilePath = v93;
          if ( v93 )
          {
            v106 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v107 = 174;
LABEL_391:
            WPP_SF_d(v106[1].Flink, v107, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v93);
            goto LABEL_392;
          }
          v94 = "1";
          if ( !*(_DWORD *)(v9 + 852) )
            v94 = "0";
          ProvisionedProfilePath = RegInsertStringA(v112, "PrivateNetwork", v94);
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          v95 = *(_QWORD *)(v9 + 944);
          if ( v95 )
          {
            v96 = *(unsigned int *)(v9 + 936);
            if ( (_DWORD)v96 )
            {
              ProvisionedProfilePath = RegInsertBinary(v112, "PluginStorage", v95, v96);
              if ( ProvisionedProfilePath )
                goto LABEL_392;
            }
          }
          ProvisionedProfilePath = RegInsertString(v112, "ManagementApp", *(_QWORD *)(v9 + 960));
          if ( ProvisionedProfilePath )
            goto LABEL_392;
          RegInsertNetComponents(v112, *(_QWORD *)(v9 + 264));
          v119 = 0;
          v93 = CreateOrOpenSubkey(v112, "MEDIA", &v119);
          ProvisionedProfilePath = v93;
          if ( v93 )
          {
            v106 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_392;
            }
            v107 = 175;
            goto LABEL_391;
          }
          v97 = *(__int64 **)(v9 + 32);
          v115 = 0;
          for ( i = *v97; i; i = *(_QWORD *)(i + 8) )
          {
            v99 = *(_QWORD *)(i + 16);
            v100 = StrdupWtoA(*(LPCWCH *)(v99 + 24));
            v101 = (void *)v100;
            if ( !v100 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 176, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 8);
              }
              break;
            }
            ProvisionedProfilePath = CreateOrOpenSubkey(v119, v100, &v115);
            if ( ProvisionedProfilePath )
              break;
            GlobalFree(v101);
            ProvisionedProfilePath = RegInsertString(v115, "Port", *(_QWORD *)v99);
            if ( ProvisionedProfilePath
              || (v102 = *(_QWORD *)(v99 + 16)) != 0
              && (ProvisionedProfilePath = RegInsertString(v115, "Device", v102)) != 0
              || (*(_DWORD *)(v99 + 40) == 3 || (*(_BYTE *)(v99 + 48) & 4) != 0)
              && (ProvisionedProfilePath = RegInsertLong(v115, "ConnectBPS", *(unsigned int *)(v99 + 104))) != 0
              || (ProvisionedProfilePath = RegInsertDeviceList(a1, v115, v9, v99)) != 0 )
            {
              RegCloseKey(v115);
              break;
            }
            RegCloseKey(v115);
          }
          RegCloseKey(v119);
          if ( *(_DWORD *)(v9 + 548) )
          {
            ProvisionedProfilePath = RegInsertProxySettings(v112, v9);
            if ( ProvisionedProfilePath )
              goto LABEL_392;
          }
          *(_DWORD *)(v9 + 532) = 0;
          RegCloseKey(v112);
          v7 = v114;
          goto LABEL_353;
        }
        v108 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_504;
        }
        v109 = 141;
      }
      else
      {
        v20 = 8;
        ProvisionedProfilePath = 8;
        v108 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_504;
        }
        v109 = 140;
      }
      WPP_SF_d(v108[1].Flink, v109, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v20);
      goto LABEL_504;
    }
    v7 = ++v114;
LABEL_353:
    RegCloseKey(hKey);
    v4 = WPP_GLOBAL_Control;
LABEL_15:
    v8 = *(_QWORD *)(v8 + 8);
    if ( !v8 )
    {
      if ( ProvisionedProfilePath )
        goto LABEL_529;
      v2 = v120;
LABEL_524:
      v111 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) - v7;
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
        WPP_SF_d(v4[1].Flink, 177, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v111);
      *v2 = v111;
      v4 = WPP_GLOBAL_Control;
LABEL_529:
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
      {
        v110 = 178;
LABEL_533:
        WPP_SF_d(v4[1].Flink, v110, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, ProvisionedProfilePath);
      }
      return ProvisionedProfilePath;
    }
  }
  ProvisionedProfilePath = 8;
LABEL_520:
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v110 = 136;
    goto LABEL_533;
  }
  return ProvisionedProfilePath;
}

```

## disassembly

```asm
0x180089e30  mov     [rsp-8+arg_10], rbx
0x180089e35  push    rbp
0x180089e36  push    rsi
0x180089e37  push    rdi
0x180089e38  push    r12
0x180089e3a  push    r13
0x180089e3c  push    r14
0x180089e3e  push    r15
0x180089e40  lea     rbp, [rsp-27h]
0x180089e45  sub     rsp, 0A0h
0x180089e4c  mov     rax, cs:__security_cookie
0x180089e53  xor     rax, rsp
0x180089e56  mov     [rbp+57h+var_40], rax
0x180089e5a  mov     r14, rdx
0x180089e5d  mov     [rbp+57h+var_70], rdx
0x180089e61  mov     r12, rcx
0x180089e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180089e6b  lea     rdx, WPP_GLOBAL_Control
0x180089e72  cmp     rcx, rdx
0x180089e75  jz      short loc_180089EA6
0x180089e77  test    byte ptr [rcx+1Ch], 80h
0x180089e7b  jz      short loc_180089EA6
0x180089e7d  cmp     byte ptr [rcx+19h], 6
0x180089e81  jb      short loc_180089EA6
0x180089e83  mov     rcx, [rcx+10h]
0x180089e87  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180089e8e  mov     edx, 86h
0x180089e93  call    WPP_SF_
0x180089e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180089e9f  lea     rdx, WPP_GLOBAL_Control
0x180089ea6  mov     rax, [r12+10h]
0x180089eab  xor     ebx, ebx
0x180089ead  xor     esi, esi
0x180089eaf  mov     [rbp+57h+hKey], rbx
0x180089eb3  mov     [rbp+57h+var_B0], rbx
0x180089eb7  mov     [rbp+57h+var_A0], esi
0x180089eba  mov     r13, [rax]
0x180089ebd  test    r13, r13
0x180089ec0  jz      loc_18008C127
0x180089ec6  xor     r14d, r14d
0x180089ec9  mov     rdi, [r13+10h]
0x180089ecd  lea     r15, [rdi+21Ch]
0x180089ed4  cmp     [rdi+214h], r14d
0x180089edb  jnz     short loc_180089EE2
0x180089edd  cmp     [r15], r14d
0x180089ee0  jz      short loc_180089F36
0x180089ee2  mov     eax, [r12+20h]
0x180089ee7  and     eax, 100h
0x180089eec  jz      short loc_180089F56
0x180089eee  cmp     [rdi+224h], r14d
0x180089ef5  jz      short loc_180089F56
0x180089ef7  cmp     rcx, rdx
0x180089efa  jz      short loc_180089F21
0x180089efc  test    byte ptr [rcx+1Ch], 80h
0x180089f00  jz      short loc_180089F21
0x180089f02  cmp     byte ptr [rcx+19h], 5
0x180089f06  jb      short loc_180089F21
0x180089f08  mov     r9, [rdi+8]
0x180089f0c  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180089f13  mov     rcx, [rcx+10h]
0x180089f17  mov     edx, 87h
0x180089f1c  call    WPP_SF_S
0x180089f21  mov     [rdi+214h], r14d
0x180089f28  mov     [rdi+21Ch], r14d
0x180089f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180089f36  lea     r15, WPP_GLOBAL_Control
0x180089f3d  mov     r13, [r13+8]
0x180089f41  test    r13, r13
0x180089f44  jz      loc_18008C082
0x180089f4a  lea     rdx, WPP_GLOBAL_Control
0x180089f51  jmp     loc_180089EC9
0x180089f56  mov     [rbp+57h+var_A8], r14
0x180089f5a  mov     [rbp+57h+var_80], r14
0x180089f5e  mov     [rbp+57h+hMem], r14
0x180089f62  cmp     [rdi+224h], r14d
0x180089f69  jz      short loc_180089F94
0x180089f6b  cmp     dword ptr [r12+8], 4
0x180089f71  jz      short loc_180089F94
0x180089f73  mov     rdx, [rdi+8]; STRSAFE_LPCWSTR
0x180089f77  lea     r8, [rbp+57h+hMem]
0x180089f7b  mov     rcx, [r12]; pszSrc
0x180089f7f  call    GetProvisionedProfilePath
0x180089f84  mov     ebx, eax
0x180089f86  test    eax, eax
0x180089f88  jnz     loc_18008C0FD
0x180089f8e  mov     rbx, [rbp+57h+hMem]
0x180089f92  jmp     short loc_180089FC6
0x180089f94  mov     rcx, [r12]; pszSrc
0x180089f98  test    eax, eax
0x180089f9a  jz      short loc_180089FB5
0x180089f9c  lea     rdx, [rbp+57h+hMem]
0x180089fa0  call    GetLUAPhonebookPath
0x180089fa5  mov     ebx, eax
0x180089fa7  test    eax, eax
0x180089fa9  jnz     loc_18008C0FD
0x180089faf  mov     rbx, [rbp+57h+hMem]
0x180089fb3  jmp     short loc_180089FBD
0x180089fb5  call    StrDup
0x180089fba  mov     rbx, rax
0x180089fbd  test    rbx, rbx
0x180089fc0  jz      loc_18008C0F8
0x180089fc6  lea     r9, [rbp+57h+var_A8]
0x180089fca  mov     rdx, r12
0x180089fcd  lea     r8, [rbp+57h+var_80]
0x180089fd1  mov     rcx, rbx; lpWideCharStr
0x180089fd4  call    RegistryPathConverter
0x180089fd9  mov     esi, eax
0x180089fdb  test    rbx, rbx
0x180089fde  jz      short loc_180089FE9
0x180089fe0  mov     rcx, rbx; hMem
0x180089fe3  call    cs:__imp_GlobalFree
0x180089fe9  mov     eax, 0EBh
0x180089fee  cmp     esi, eax
0x180089ff0  jz      loc_18008C196
0x180089ff6  mov     r14, [rbp+57h+var_A8]
0x180089ffa  mov     rdx, [rbp+57h+var_80]
0x180089ffe  mov     rcx, r14; lpSubKey
0x18008a001  call    RegSetKeySecurityInfo
0x18008a006  test    eax, eax
0x18008a008  jz      short loc_18008A03E
0x18008a00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a011  lea     rax, WPP_GLOBAL_Control
0x18008a018  cmp     rcx, rax
0x18008a01b  jz      short loc_18008A04C
0x18008a01d  test    byte ptr [rcx+1Ch], 80h
0x18008a021  jz      short loc_18008A04C
0x18008a023  cmp     byte ptr [rcx+19h], 2
0x18008a027  jb      short loc_18008A04C
0x18008a029  mov     rcx, [rcx+10h]
0x18008a02d  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008a034  mov     edx, 89h
0x18008a039  call    WPP_SF_
0x18008a03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a045  lea     rax, WPP_GLOBAL_Control
0x18008a04c  test    esi, esi
0x18008a04e  jnz     loc_18008C0C8
0x18008a054  mov     rcx, [rbp+57h+var_80]
0x18008a058  lea     r8, [rbp+57h+hKey]
0x18008a05c  mov     rdx, r14
0x18008a05f  call    CreateOrOpenSubkey
0x18008a064  mov     ebx, eax
0x18008a066  test    r14, r14
0x18008a069  jz      short loc_18008A074
0x18008a06b  mov     rcx, r14; hMem
0x18008a06e  call    cs:__imp_GlobalFree
0x18008a074  xor     r14d, r14d
0x18008a077  test    ebx, ebx
0x18008a079  jnz     loc_18008C093
0x18008a07f  mov     rcx, rdi
0x18008a082  call    UpdateEntryTimeStamp
0x18008a087  mov     rdx, [rdi+8]; lpSubKey
0x18008a08b  mov     rcx, [rbp+57h+hKey]; hKey
0x18008a08f  call    cs:__imp_RegDeleteTreeW
0x18008a095  cmp     [r15], r14d
0x18008a098  jnz     loc_18008B8B6
0x18008a09e  mov     rcx, [rdi+8]; lpWideCharStr
0x18008a0a2  call    _StrdupWtoA
0x18008a0a7  mov     rsi, rax
0x18008a0aa  test    rax, rax
0x18008a0ad  jz      loc_18008C00C
0x18008a0b3  mov     rcx, [rbp+57h+hKey]
0x18008a0b7  lea     r8, [rbp+57h+var_B0]
0x18008a0bb  mov     rdx, rax
0x18008a0be  call    CreateOrOpenSubkey
0x18008a0c3  mov     ebx, eax
0x18008a0c5  test    eax, eax
0x18008a0c7  jnz     loc_18008BFE6
0x18008a0cd  mov     rcx, rsi; hMem
0x18008a0d0  call    cs:__imp_GlobalFree
0x18008a0d6  mov     rcx, [rbp+57h+var_B0]
0x18008a0da  lea     r8d, [r14+1]
0x18008a0de  lea     rdx, aEncoding; "Encoding"
0x18008a0e5  call    RegInsertLong
0x18008a0ea  mov     ebx, eax
0x18008a0ec  test    eax, eax
0x18008a0ee  jnz     loc_18008BFB4
0x18008a0f4  mov     rcx, [rbp+57h+var_B0]
0x18008a0f8  lea     r8d, [r14+8]
0x18008a0fc  lea     rdx, aPbversion; "PBVersion"
0x18008a103  call    RegInsertLong
0x18008a108  mov     ebx, eax
0x18008a10a  test    eax, eax
0x18008a10c  jnz     loc_18008BF6C
0x18008a112  mov     r8d, [rdi+18h]
0x18008a116  lea     rdx, aType; "Type"
0x18008a11d  mov     rcx, [rbp+57h+var_B0]
0x18008a121  call    RegInsertLong
0x18008a126  mov     ebx, eax
0x18008a128  test    eax, eax
0x18008a12a  jnz     loc_18008BF3A
0x18008a130  cmp     [rdi+0B0h], r14d
0x18008a137  lea     rsi, a1; "1"
0x18008a13e  mov     rcx, [rbp+57h+var_B0]
0x18008a142  lea     r15, a0; "0"
0x18008a149  mov     r8, rsi
0x18008a14c  lea     rdx, aAutologon; "AutoLogon"
0x18008a153  cmovz   r8, r15
0x18008a157  call    RegInsertStringA
0x18008a15c  mov     ebx, eax
0x18008a15e  test    eax, eax
0x18008a160  jnz     loc_18008BF08
0x18008a166  cmp     [rdi+0B4h], r14d
0x18008a16d  lea     rdx, aUserascredenti; "UseRasCredentials"
0x18008a174  mov     rcx, [rbp+57h+var_B0]
0x18008a178  mov     r8, rsi
0x18008a17b  cmovz   r8, r15
0x18008a17f  call    RegInsertStringA
0x18008a184  mov     ebx, eax
0x18008a186  test    eax, eax
0x18008a188  jnz     loc_18008BED3
0x18008a18e  mov     r8d, [rdi+10h]
0x18008a192  lea     rdx, aLowdatetime; "LowDateTime"
0x18008a199  mov     rcx, [rbp+57h+var_B0]
0x18008a19d  call    RegInsertLong
0x18008a1a2  mov     ebx, eax
0x18008a1a4  test    eax, eax
0x18008a1a6  jnz     loc_18008BE9E
0x18008a1ac  mov     r8d, [rdi+14h]
0x18008a1b0  lea     rdx, aHighdatetime; "HighDateTime"
0x18008a1b7  mov     rcx, [rbp+57h+var_B0]
0x18008a1bb  call    RegInsertLong
0x18008a1c0  mov     ebx, eax
0x18008a1c2  test    eax, eax
0x18008a1c4  jnz     loc_18008BE69
0x18008a1ca  mov     r8d, [rdi+1C8h]
0x18008a1d1  lea     rdx, aDialparamsuid; "DialParamsUID"
0x18008a1d8  mov     rcx, [rbp+57h+var_B0]
0x18008a1dc  call    RegInsertLong
0x18008a1e1  mov     ebx, eax
0x18008a1e3  test    eax, eax
0x18008a1e5  jnz     loc_18008BE34
0x18008a1eb  mov     r8, [rdi+1D0h]
0x18008a1f2  test    r8, r8
0x18008a1f5  jz      short loc_18008A215
0x18008a1f7  mov     rcx, [rbp+57h+var_B0]
0x18008a1fb  lea     r9d, [r14+10h]
0x18008a1ff  lea     rdx, aGuid; "Guid"
0x18008a206  call    RegInsertBinary
0x18008a20b  mov     ebx, eax
0x18008a20d  test    eax, eax
0x18008a20f  jnz     loc_18008B8DB
0x18008a215  mov     r8d, [rdi+0A8h]
0x18008a21c  lea     rdx, aVpnstrategy; "VpnStrategy"
0x18008a223  mov     rcx, [rbp+57h+var_B0]
0x18008a227  call    RegInsertLong
0x18008a22c  mov     ebx, eax
0x18008a22e  test    eax, eax
0x18008a230  jnz     loc_18008BDFF
0x18008a236  mov     r8d, [rdi+0ECh]
0x18008a23d  lea     rdx, aExcludedprotoc; "ExcludedProtocols"
0x18008a244  mov     rcx, [rbp+57h+var_B0]
0x18008a248  call    RegInsertLong
0x18008a24d  mov     ebx, eax
0x18008a24f  test    eax, eax
0x18008a251  jnz     loc_18008BDCA
0x18008a257  cmp     [rdi+0F0h], r14d
0x18008a25e  lea     rdx, aLcpextensions; "LcpExtensions"
0x18008a265  mov     rcx, [rbp+57h+var_B0]
0x18008a269  mov     r8, rsi
0x18008a26c  cmovz   r8, r15
0x18008a270  call    RegInsertStringA
0x18008a275  mov     ebx, eax
0x18008a277  test    eax, eax
0x18008a279  jnz     loc_18008BD95
0x18008a27f  mov     r8d, [rdi+0ACh]
0x18008a286  lea     rdx, aDataencryption; "DataEncryption"
0x18008a28d  mov     rcx, [rbp+57h+var_B0]
0x18008a291  call    RegInsertLong
0x18008a296  mov     ebx, eax
0x18008a298  test    eax, eax
0x18008a29a  jnz     loc_18008BD60
0x18008a2a0  cmp     [rdi+0F4h], r14d
0x18008a2a7  lea     rdx, aSwcompression; "SwCompression"
0x18008a2ae  mov     rcx, [rbp+57h+var_B0]
0x18008a2b2  mov     r8, rsi
0x18008a2b5  cmovz   r8, r15
0x18008a2b9  call    RegInsertStringA
0x18008a2be  mov     ebx, eax
0x18008a2c0  test    eax, eax
0x18008a2c2  jnz     loc_18008BAB9
0x18008a2c8  cmp     [rdi+0F8h], r14d
0x18008a2cf  lea     rdx, aNegotiatemulti; "NegotiateMultilinkAlways"
0x18008a2d6  mov     rcx, [rbp+57h+var_B0]
0x18008a2da  mov     r8, rsi
0x18008a2dd  cmovz   r8, r15
0x18008a2e1  call    RegInsertStringA
0x18008a2e6  mov     ebx, eax
0x18008a2e8  test    eax, eax
0x18008a2ea  jnz     loc_18008BAB9
0x18008a2f0  cmp     [rdi+0FCh], r14d
0x18008a2f7  lea     rdx, aSkipdoubledial; "SkipDoubleDialDialog"
0x18008a2fe  mov     rcx, [rbp+57h+var_B0]
0x18008a302  mov     r8, rsi
0x18008a305  cmovz   r8, r15
0x18008a309  call    RegInsertStringA
0x18008a30e  mov     ebx, eax
0x18008a310  test    eax, eax
0x18008a312  jnz     loc_18008BAB9
0x18008a318  mov     r8d, [rdi+84h]
0x18008a31f  lea     rdx, aDialmode; "DialMode"
  ... truncated ...
```
