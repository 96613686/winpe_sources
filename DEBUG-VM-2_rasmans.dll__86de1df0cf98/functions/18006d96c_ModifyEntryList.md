# ModifyEntryList

- ea: `0x18006d96c`
- end: `0x180070bcc`
- name: `ModifyEntryList`
- size: `12896`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b698`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18005cb9c`
- `0x18005cc20`
- `0x18005d1e0`
- `0x18005d5f8`
- `0x18005d748`
- `0x1800671c8`
- `0x1800675a8`
- `0x180067d64`
- `0x18006ae54`
- `0x18006b02c`
- `0x18006c57c`
- `0x18006c6c0`
- `0x18006c734`
- `0x18006cda4`
- `0x18006d00c`
- `0x18006d11c`
- `0x18006d24c`
- `0x18006d3b0`
- `0x18006d740`
- `0x18006d96c`
- `0x18007be38`
- `0x18007c0c8`
- `0x18007c5d8`
- `0x18007d338`
- `0x180080e7c`
- `0x18008ecb8`
- `0x18008fec8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dbe5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dd38`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dbe5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dd38`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006f593`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006f593`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f511`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f511`

## string_xrefs

- `0x18006df67`: `NegotiateMultilinkAlways`
- `0x18006df3d`: `SwCompression`
- `0x18006dff2`: `RedialAttempts`
- `0x18006dece`: `ExcludedProtocols`
- `0x18006def4`: `LcpExtensions`
- `0x18006e056`: `RedialOnLinkFailure`
- `0x18006e098`: `CustomDialDll`
- `0x18006e0f8`: `ForceSecureCompartment`
- `0x18006e0d6`: `CustomRasDialDll`
- `0x18006e3e6`: `ShowMonitorIconInTaskBar`
- `0x18006e2eb`: `PreferredCompression`
- `0x18006e2c4`: `PreferredProtocol`
- `0x18006e327`: `PreferredMdmProtocol`
- `0x18006e4c2`: `IpHeaderCompression`
- `0x18006e8e5`: `ImsConfig`
- `0x18006e98b`: `CacheCredentials`
- `0x18006edd8`: `ApnInfoAccessPoint`
- `0x18006ee4e`: `DeviceComplianceEnabled`
- `0x18006ee2a`: `ApnInfoCompression`
- `0x18006ee9b`: `DeviceComplianceSsoEku`
- `0x18006ee78`: `DeviceComplianceSsoEnabled`
- `0x18006ed5c`: `SecurityDescriptor`
- `0x18006f010`: `PowershellCreatedProfile`
- `0x18006f0f6`: `AutoConfigScript`
- `0x18006f49f`: `AutoConfigScript`
- `0x18006eeba`: `DeviceComplianceSsoIssuer`
- `0x18006f292`: `PluginStorage`
- `0x18006f2dd`: `ProtocolListLength`
- `0x18006f31f`: `ProtocolListRetryTimeInHours`
- `0x18006f302`: `ProtocolList`
- `0x18006f35d`: `ProtocolListTimeOfLastProtocolSelectionLow`
- `0x18006f33e`: `ProtocolListCurrentProtocol`
- `0x18006f37c`: `ProtocolListTimeOfLastProtocolSelectionHigh`

## pseudocode

```c
__int64 __fastcall ModifyEntryList(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rsi
  __int64 v3; // rbx
  struct _LIST_ENTRY *v4; // rcx
  int v5; // edx
  unsigned int LUAPhonebookPath; // edi
  __int64 v7; // r8
  PCNZWCH *v8; // r13
  __int64 v9; // rsi
  _DWORD *v10; // r12
  WCHAR *v11; // r14
  __int64 *v12; // rbx
  __int64 v13; // rbx
  const WCHAR *v14; // rcx
  int v15; // ebx
  unsigned int v16; // ebx
  __int64 HRasfileNode; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // r14
  int v27; // edx
  int v28; // r9d
  unsigned int inserted; // eax
  const char *v30; // r8
  const char *v31; // r8
  __int64 v32; // r8
  unsigned int v33; // eax
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
  const char *v44; // r8
  const char *v45; // r8
  const char *v46; // r8
  const char *v47; // r8
  const char *v48; // r8
  const char *v49; // r8
  const char *v50; // r8
  const char *v51; // r8
  const char *v52; // r8
  __int64 v53; // r8
  const char *v54; // r8
  const char *v55; // r8
  const WCHAR *v56; // r8
  const WCHAR *v57; // r8
  const WCHAR *v58; // r8
  const WCHAR *v59; // r8
  const WCHAR *v60; // r8
  const WCHAR *v61; // r8
  const char *v62; // r8
  const WCHAR *v63; // r8
  const WCHAR *v64; // r8
  const char *v65; // r8
  const char *v66; // r8
  const char *v67; // r8
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  const char *v71; // r8
  __int64 v72; // r8
  __int64 v73; // r8
  __int64 v74; // r9
  const char *v75; // r8
  __int64 v76; // r8
  __int64 v77; // r9
  const char *v78; // r8
  const char *v79; // r8
  __int64 v80; // r8
  __int64 v81; // r8
  const char *v82; // r8
  __int64 v83; // rcx
  __int64 v84; // rdx
  unsigned int v85; // eax
  __int64 v86; // rcx
  __int64 v87; // rdx
  const char *v88; // r8
  const char *v89; // r8
  const char *v90; // r8
  const char *v91; // r8
  __int64 v92; // r8
  __int64 v93; // r8
  __int64 v94; // r8
  const char *v95; // r8
  const char *v96; // r8
  const char *v97; // r8
  const char *v98; // r8
  const char *v99; // r8
  __int64 v100; // r8
  const char *v101; // r8
  const char *v102; // r8
  const char *v103; // r8
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // r15
  __int64 v107; // r14
  int v108; // edx
  int v109; // r9d
  __int64 v110; // r8
  const WCHAR *v111; // r15
  unsigned int v112; // r14d
  __int64 cbMultiByte; // r12
  __int64 v114; // rdx
  __int64 v115; // rdx
  __int64 v116; // r9
  struct _LIST_ENTRY *v117; // rcx
  __int64 v118; // rdx
  unsigned int v120; // ebx
  int v121; // [rsp+40h] [rbp-C0h]
  __int64 v122; // [rsp+50h] [rbp-B0h]
  PCNZWCH *v123; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[272]; // [rsp+70h] [rbp-90h] BYREF

  v2 = a2;
  v3 = a1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 230, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  LUAPhonebookPath = 0;
  v121 = 0;
  v7 = **(_QWORD **)(v3 + 16);
  v122 = v7;
  if ( !v7 )
  {
LABEL_797:
    v120 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 16LL) - v5;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
      WPP_SF_d(v4[1].Flink, 336, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v120);
    *v2 = v120;
LABEL_802:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_803;
  }
  v8 = 0;
  v123 = 0;
  while ( 1 )
  {
    v9 = *(_QWORD *)(v7 + 16);
    v10 = (_DWORD *)(v9 + 540);
    if ( !*(_DWORD *)(v9 + 532) && !*v10 )
      goto LABEL_48;
    if ( (*(_DWORD *)(v3 + 32) & 0x100) == 0 || !*(_DWORD *)(v9 + 548) )
      break;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 231, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v9 + 8));
      v5 = v121;
      v7 = v122;
    }
    *(_DWORD *)(v9 + 532) = 0;
    *(_DWORD *)(v9 + 540) = 0;
    v4 = WPP_GLOBAL_Control;
LABEL_48:
    v7 = *(_QWORD *)(v7 + 8);
    v122 = v7;
    if ( !v7 )
    {
      if ( LUAPhonebookPath )
        goto LABEL_803;
      v3 = a1;
      v2 = a2;
      goto LABEL_797;
    }
    v3 = a1;
  }
  if ( *(_DWORD *)v9 == -1 )
  {
    if ( !*(_DWORD *)(v9 + 548) || *(_DWORD *)(v3 + 8) == 4 )
    {
      v14 = *(const WCHAR **)v3;
      if ( (*(_DWORD *)(v3 + 32) & 0x100) != 0 )
      {
        LUAPhonebookPath = GetLUAPhonebookPath(v14);
        if ( LUAPhonebookPath )
          goto LABEL_26;
        v11 = 0;
      }
      else
      {
        LUAPhonebookPath = 0;
        v11 = (WCHAR *)StrDup(v14);
      }
      if ( v11 )
      {
LABEL_21:
        v12 = *(__int64 **)(v3 + 48);
        v8 = 0;
        v123 = 0;
        if ( !v12 )
          goto LABEL_35;
        v13 = *v12;
        while ( v13 )
        {
          v8 = *(PCNZWCH **)(v13 + 16);
          v123 = v8;
          if ( !v8 )
            goto LABEL_35;
          if ( !(unsigned int)CompareStringWrapW(v8[1], v11) )
            break;
          v13 = *(_QWORD *)(v13 + 8);
          v8 = 0;
          v123 = 0;
        }
        if ( !v8 )
        {
LABEL_35:
          v15 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
          LUAPhonebookPath = CreateProfileDirAndSetAcls(*(HANDLE *)(a1 + 40), 1);
          if ( !LUAPhonebookPath )
          {
            LUAPhonebookPath = LoadFile(v11);
            if ( !LUAPhonebookPath )
            {
              v16 = v15 + 1;
              HRasfileNode = CreateHRasfileNode(0xFFFFFFFFLL, v11, v16);
              *(_DWORD *)v9 = v16;
              DtlAddNodeLast(*(_QWORD *)(a1 + 48), HRasfileNode);
              v8 = *(PCNZWCH **)(v18 + 16);
              v123 = v8;
            }
          }
        }
      }
      else
      {
        LUAPhonebookPath = 8;
      }
    }
    else
    {
      LUAPhonebookPath = GetProvisionedProfilePath(*(STRSAFE_LPCWSTR *)v3, *(STRSAFE_LPCWSTR *)(v9 + 8));
      if ( !LUAPhonebookPath )
      {
        v11 = 0;
        goto LABEL_21;
      }
LABEL_26:
      v11 = 0;
    }
    if ( v11 )
      GlobalFree(v11);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v19 = 232;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    v20 = *(__int64 **)(v3 + 48);
    v8 = 0;
    v123 = 0;
    if ( v20 )
    {
      v21 = *v20;
      while ( v21 )
      {
        v8 = *(PCNZWCH **)(v21 + 16);
        v123 = v8;
        if ( !v8 )
          goto LABEL_58;
        if ( *((_DWORD *)v8 + 4) == *(_DWORD *)v9 )
          break;
        v21 = *(_QWORD *)(v21 + 8);
        v8 = 0;
        v123 = 0;
      }
    }
  }
  if ( !v8 )
  {
LABEL_58:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 233, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v9 + 8));
      v4 = WPP_GLOBAL_Control;
    }
    LUAPhonebookPath = 622;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 2u )
    {
      v19 = 234;
LABEL_45:
      WPP_SF_d(v4[1].Flink, v19, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_46:
    v5 = v121;
LABEL_47:
    v7 = v122;
    goto LABEL_48;
  }
  v22 = *(_DWORD *)v8;
  UpdateEntryTimeStamp(v9);
  v23 = StrDupAFromTInternal(*(LPCWCH *)(v9 + 8));
  v26 = (void *)v23;
  if ( !v23 )
  {
    inserted = 8;
    LUAPhonebookPath = 8;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 235;
    goto LABEL_406;
  }
  if ( (unsigned int)RasfileFindSectionLine(v22, v23, v24, v25) )
    DeleteCurrentSection(v22);
  GlobalFree(v26);
  if ( *v10 )
  {
    *((_DWORD *)v8 + 5) |= 1u;
    v4 = WPP_GLOBAL_Control;
    v5 = ++v121;
    goto LABEL_47;
  }
  LOBYTE(v28) = 2;
  LOBYTE(v27) = 63;
  rasFindLine(v22, v27, 0, v28, 2);
  inserted = InsertSection(v22, *(_QWORD *)(v9 + 8));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 236;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "Encoding", 1);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 237;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "PBVersion", 8);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 238;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "Type", *(unsigned int *)(v9 + 24));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 239;
    goto LABEL_406;
  }
  v30 = "1";
  if ( !*(_DWORD *)(v9 + 176) )
    v30 = "0";
  inserted = InsertStringA(v22, "AutoLogon", v30);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 240;
    goto LABEL_406;
  }
  v31 = "1";
  if ( !*(_DWORD *)(v9 + 180) )
    v31 = "0";
  inserted = InsertStringA(v22, "UseRasCredentials", v31);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 241;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "LowDateTime", *(unsigned int *)(v9 + 16));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 242;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "HighDateTime", *(unsigned int *)(v9 + 20));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 243;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "DialParamsUID", *(unsigned int *)(v9 + 456));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 244;
LABEL_406:
    v116 = inserted;
    goto LABEL_407;
  }
  v32 = *(_QWORD *)(v9 + 464);
  if ( v32 )
  {
    v33 = InsertBinary(v22, "Guid", v32, 16);
    LUAPhonebookPath = v33;
    if ( v33 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 245, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v33);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 246;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
  }
  inserted = InsertLong(v22, "VpnStrategy", *(unsigned int *)(v9 + 168));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 247;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  inserted = InsertLong(v22, "ExcludedProtocols", *(unsigned int *)(v9 + 236));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 248;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  v34 = "1";
  if ( !*(_DWORD *)(v9 + 240) )
    v34 = "0";
  inserted = InsertStringA(v22, "LcpExtensions", v34);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 249;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  inserted = InsertLong(v22, "DataEncryption", *(unsigned int *)(v9 + 172));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 250;
      goto LABEL_406;
    }
LABEL_803:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    {
      v114 = 337;
LABEL_807:
      WPP_SF_d(v4[1].Flink, v114, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
    }
    return LUAPhonebookPath;
  }
  v35 = "1";
  if ( !*(_DWORD *)(v9 + 244) )
    v35 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SwCompression", v35);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v36 = "1";
  if ( !*(_DWORD *)(v9 + 248) )
    v36 = "0";
  LUAPhonebookPath = InsertStringA(v22, "NegotiateMultilinkAlways", v36);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v37 = "1";
  if ( !*(_DWORD *)(v9 + 252) )
    v37 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SkipDoubleDialDialog", v37);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "DialMode", *(unsigned int *)(v9 + 132));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "OverridePref", *(unsigned int *)(v9 + 144));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "RedialAttempts", *(unsigned int *)(v9 + 148));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "RedialSeconds", *(unsigned int *)(v9 + 152));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "IdleDisconnectSeconds", *(unsigned int *)(v9 + 156));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v38 = "1";
  if ( !*(_DWORD *)(v9 + 160) )
    v38 = "0";
  LUAPhonebookPath = InsertStringA(v22, "RedialOnLinkFailure", v38);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "CallbackMode", *(unsigned int *)(v9 + 420));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertString(v22, "CustomDialDll", *(_QWORD *)(v9 + 432));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 251;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "CustomDialFunc", *(_QWORD *)(v9 + 440));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 252;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "CustomRasDialDll", *(_QWORD *)(v9 + 448));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 253;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  *(_DWORD *)(v9 + 184) = 0;
  LUAPhonebookPath = InsertStringA(v22, "ForceSecureCompartment", "0");
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 254;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v39 = "1";
  if ( !*(_DWORD *)(v9 + 188) )
    v39 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableIKENameEkuCheck", v39);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 255;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v40 = "1";
  if ( !*(_DWORD *)(v9 + 424) )
    v40 = "0";
  LUAPhonebookPath = InsertStringA(v22, "AuthenticateServer", v40);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 256;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v41 = "1";
  if ( !*(_DWORD *)(v9 + 256) )
    v41 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShareMsFilePrint", v41);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 257;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v42 = "1";
  if ( !*(_DWORD *)(v9 + 260) )
    v42 = "0";
  LUAPhonebookPath = InsertStringA(v22, "BindMsNetClient", v42);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 258;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v43 = "1";
  if ( !*(_DWORD *)(v9 + 40) )
    v43 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SharedPhoneNumbers", v43);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 259;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v44 = "1";
  if ( !*(_DWORD *)(v9 + 44) )
    v44 = "0";
  LUAPhonebookPath = InsertStringA(v22, "GlobalDeviceSettings", v44);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 260;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PrerequisiteEntry", *(_QWORD *)(v9 + 56));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 261;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PrerequisitePbk", *(_QWORD *)(v9 + 64));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 262;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PreferredPort", *(_QWORD *)(v9 + 72));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 263;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PreferredDevice", *(_QWORD *)(v9 + 80));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 264;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredBps", *(unsigned int *)(v9 + 88));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 265;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v45 = "1";
  if ( !*(_DWORD *)(v9 + 92) )
    v45 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredHwFlow", v45);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 266;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v46 = "1";
  if ( !*(_DWORD *)(v9 + 96) )
    v46 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredProtocol", v46);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 267;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v47 = "1";
  if ( !*(_DWORD *)(v9 + 100) )
    v47 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredCompression", v47);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 268;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredSpeaker", *(unsigned int *)(v9 + 104));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 269;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredMdmProtocol", *(unsigned int *)(v9 + 108));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 270;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v48 = "1";
  if ( !*(_DWORD *)(v9 + 116) )
    v48 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewUserPw", v48);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 271;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v49 = "1";
  if ( !*(_DWORD *)(v9 + 120) )
    v49 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewDomain", v49);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 272;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v50 = "1";
  if ( !*(_DWORD *)(v9 + 124) )
    v50 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewPhoneNumber", v50);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 273;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v51 = "1";
  if ( !*(_DWORD *)(v9 + 112) )
    v51 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShowDialingProgress", v51);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 274;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v52 = "1";
  if ( !*(_DWORD *)(v9 + 48) )
    v52 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShowMonitorIconInTaskBar", v52);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 275;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "CustomAuthKey", *(unsigned int *)(v9 + 192));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 276;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v53 = *(_QWORD *)(v9 + 200);
  if ( v53 )
  {
    LUAPhonebookPath = InsertBinary(v22, "CustomAuthData", v53, *(unsigned int *)(v9 + 208));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 277;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
  }
  LUAPhonebookPath = InsertLong(v22, "AuthRestrictions", *(unsigned int *)(v9 + 164));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 278;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v54 = "1";
  if ( !*(_DWORD *)(v9 + 272) )
    v54 = "0";
  LUAPhonebookPath = InsertStringA(v22, "IpPrioritizeRemote", v54);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 279;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpInterfaceMetric", *(unsigned int *)(v9 + 352));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 280;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v55 = "1";
  if ( !*(_DWORD *)(v9 + 276) )
    v55 = "0";
  LUAPhonebookPath = InsertStringA(v22, "IpHeaderCompression", v55);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 281;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v56 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 280) )
    v56 = *(const WCHAR **)(v9 + 280);
  LUAPhonebookPath = InsertString(v22, "IpAddress", v56);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 282;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v57 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 288) )
    v57 = *(const WCHAR **)(v9 + 288);
  LUAPhonebookPath = InsertString(v22, "IpDnsAddress", v57);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 283;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v58 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 296) )
    v58 = *(const WCHAR **)(v9 + 296);
  LUAPhonebookPath = InsertString(v22, "IpDns2Address", v58);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 284;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v59 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 304) )
    v59 = *(const WCHAR **)(v9 + 304);
  LUAPhonebookPath = InsertString(v22, "IpWinsAddress", v59);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 285;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v60 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 312) )
    v60 = *(const WCHAR **)(v9 + 312);
  LUAPhonebookPath = InsertString(v22, "IpWins2Address", v60);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 286;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpAssign", *(unsigned int *)(v9 + 320));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 287;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpNameAssign", *(unsigned int *)(v9 + 324));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 288;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpDnsFlags", *(unsigned int *)(v9 + 328));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 289;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpNBTFlags", *(unsigned int *)(v9 + 332));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 290;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "TcpWindowSize", *(unsigned int *)(v9 + 336));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 291;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "UseFlags", *(unsigned int *)(v9 + 136));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 292;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpSecFlags", *(unsigned int *)(v9 + 140));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 293;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "IpDnsSuffix", *(_QWORD *)(v9 + 344));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 294;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6Assign", *(unsigned int *)(v9 + 356));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 295;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v61 = L"::";
  if ( *(_QWORD *)(v9 + 360) )
    v61 = *(const WCHAR **)(v9 + 360);
  LUAPhonebookPath = InsertString(v22, "Ipv6Address", v61);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 296;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6PrefixLength", *(unsigned int *)(v9 + 368));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 297;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v62 = "1";
  if ( !*(_DWORD *)(v9 + 372) )
    v62 = "0";
  LUAPhonebookPath = InsertStringA(v22, "Ipv6PrioritizeRemote", v62);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 298;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6InterfaceMetric", *(unsigned int *)(v9 + 416));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 299;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6NameAssign", *(unsigned int *)(v9 + 376));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 300;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v63 = L"::";
  if ( *(_QWORD *)(v9 + 384) )
    v63 = *(const WCHAR **)(v9 + 384);
  LUAPhonebookPath = InsertString(v22, "Ipv6DnsAddress", v63);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 301;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v64 = L"::";
  if ( *(_QWORD *)(v9 + 392) )
    v64 = *(const WCHAR **)(v9 + 392);
  LUAPhonebookPath = InsertString(v22, "Ipv6Dns2Address", v64);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 302;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v22, "Ipv6Prefix", v9 + 408, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 303;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v22, "Ipv6InterfaceId", v9 + 400, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 304;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v65 = "1";
  if ( !*(_DWORD *)(v9 + 544) )
    v65 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableClassBasedDefaultRoute", v65);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 305;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v66 = "1";
  if ( !*(_DWORD *)(v9 + 488) )
    v66 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableMobility", v66);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 306;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "NetworkOutageTime", *(unsigned int *)(v9 + 492));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 307;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  if ( !(unsigned int)InsertString(v22, "IDI", *(_QWORD *)(v9 + 496)) )
  {
    if ( (unsigned int)InsertString(v22, "IDR", *(_QWORD *)(v9 + 504)) )
    {
      v117 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 310, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
          v117 = WPP_GLOBAL_Control;
        }
        if ( v117 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(v117[1].Blink) < 0
          && BYTE1(v117[1].Blink) >= 6u )
        {
          v118 = 311;
          goto LABEL_517;
        }
      }
      return 1;
    }
    v67 = "1";
    if ( !*(_DWORD *)(v9 + 512) )
      v67 = "0";
    v68 = InsertStringA(v22, "ImsConfig", v67);
    LUAPhonebookPath = v68;
    if ( v68 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v68);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 313;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    v69 = InsertLong(v22, "IdiType", *(unsigned int *)(v9 + 516));
    LUAPhonebookPath = v69;
    if ( v69 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v69);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 315;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    v70 = InsertLong(v22, "IdrType", *(unsigned int *)(v9 + 520));
    LUAPhonebookPath = v70;
    if ( v70 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v70);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 317;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v22, "ProvisionType", *(unsigned int *)(v9 + 548));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "PreSharedKey", *(_QWORD *)(v9 + 552));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v71 = "1";
    if ( !*(_DWORD *)(v9 + 128) )
      v71 = "0";
    LUAPhonebookPath = InsertStringA(v22, "CacheCredentials", v71);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 318;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v22, "NumCustomPolicy", *(unsigned int *)(v9 + 596));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v72 = *(_QWORD *)(v9 + 608);
    if ( v72 )
    {
      if ( *(_DWORD *)(v9 + 596) )
      {
        LUAPhonebookPath = InsertBinary(v22, "CustomIPSecPolicies", v72, *(unsigned int *)(v9 + 600));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    LUAPhonebookPath = InsertLong(v22, "NumEku", *(unsigned int *)(v9 + 616));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v73 = *(_QWORD *)(v9 + 624);
    if ( v73 )
    {
      if ( *(_DWORD *)(v9 + 616) )
      {
        v74 = *(unsigned int *)(v9 + 620);
        if ( (_DWORD)v74 )
        {
          LUAPhonebookPath = InsertBinary(v22, "CertificateEKU", v73, v74);
          if ( LUAPhonebookPath )
            goto LABEL_802;
        }
      }
    }
    v75 = "1";
    if ( !*(_DWORD *)(v9 + 632) )
      v75 = "0";
    LUAPhonebookPath = InsertStringA(v22, "UseMachineRootCert", v75);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 632) == 1 )
    {
      v76 = *(_QWORD *)(v9 + 648);
      if ( v76 )
      {
        v77 = *(unsigned int *)(v9 + 640);
        if ( (_DWORD)v77 )
        {
          LUAPhonebookPath = InsertBinary(v22, "RootCertificate", v76, v77);
          if ( LUAPhonebookPath )
            goto LABEL_802;
        }
      }
    }
    v78 = "1";
    if ( !*(_DWORD *)(v9 + 524) )
      v78 = "0";
    inserted = InsertStringA(v22, "Disable_IKEv2_Fragmentation", v78);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 319;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v79 = "1";
    if ( !*(_DWORD *)(v9 + 528) )
      v79 = "0";
    inserted = InsertStringA(v22, "PlumbIKEv2TSAsRoutes", v79);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 320;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertLong(v22, "NumServers", *(unsigned int *)(v9 + 656));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_QWORD *)(v9 + 664) )
    {
      if ( *(_DWORD *)(v9 + 656) )
      {
        inserted = CreateServerLists(v22);
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 321;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    inserted = InsertLong(v22, "RouteVersion", 1);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 322;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    inserted = InsertLong(v22, "NumRoutes", *(unsigned int *)(v9 + 672));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 323;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v80 = *(_QWORD *)(v9 + 680);
    if ( v80 )
    {
      if ( *(_DWORD *)(v9 + 672) )
      {
        inserted = InsertBinary(v22, "Routes", v80, *(unsigned int *)(v9 + 676));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 324;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    inserted = InsertLong(v22, "NumNrptRules", *(unsigned int *)(v9 + 688));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 325;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v81 = *(_QWORD *)(v9 + 696);
    if ( v81 )
    {
      if ( *(_DWORD *)(v9 + 688) )
      {
        inserted = InsertBinary(v22, "NrptRules", v81, *(unsigned int *)(v9 + 692));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 326;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    v82 = "1";
    if ( !*(_DWORD *)(v9 + 704) )
      v82 = "0";
    inserted = InsertStringA(v22, "AutoTiggerCapable", v82);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 327;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertLong(v22, "NumAppIds", *(unsigned int *)(v9 + 728));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v84 = *(_QWORD *)(v9 + 736);
    if ( v84 && *(_DWORD *)(v9 + 728) )
    {
      inserted = CreateDtlList(v83, v84, *(unsigned int *)(v9 + 732));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v115 = 328;
          goto LABEL_406;
        }
        goto LABEL_803;
      }
      v85 = InsertStringList(v22, "ApplicationIds", 0);
      LUAPhonebookPath = v85;
      if ( v85 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v85);
        }
        DtlDestroyList(0);
        goto LABEL_802;
      }
      DtlDestroyList(0);
    }
    LUAPhonebookPath = InsertLong(v22, "NumClassicAppIds", *(unsigned int *)(v9 + 708));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v87 = *(_QWORD *)(v9 + 720);
    if ( v87 && *(_DWORD *)(v9 + 708) )
    {
      inserted = CreateDtlList(v86, v87, *(unsigned int *)(v9 + 712));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v115 = 330;
          goto LABEL_406;
        }
        goto LABEL_803;
      }
      LUAPhonebookPath = InsertStringList(v22, "ClassicApplicationIds", 0);
      if ( LUAPhonebookPath )
      {
        DtlDestroyList(0);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_803;
        v115 = 331;
        v116 = LUAPhonebookPath;
LABEL_407:
        WPP_SF_d(v4[1].Flink, v115, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v116);
        goto LABEL_802;
      }
      DtlDestroyList(0);
    }
    inserted = InsertString(v22, "SecurityDescriptor", *(_QWORD *)(v9 + 744));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 332;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertString(v22, "ApnInfoProviderId", *(_QWORD *)(v9 + 864));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoUsername", *(_QWORD *)(v9 + 880));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoPassword", *(_QWORD *)(v9 + 888));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoAccessPoint", *(_QWORD *)(v9 + 872));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "ApnInfoAuthentication", *(unsigned int *)(v9 + 900));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v88 = "1";
    if ( !*(_DWORD *)(v9 + 896) )
      v88 = "0";
    LUAPhonebookPath = InsertStringA(v22, "ApnInfoCompression", v88);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v89 = "1";
    if ( !*(_DWORD *)(v9 + 904) )
      v89 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DeviceComplianceEnabled", v89);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v90 = "1";
    if ( !*(_DWORD *)(v9 + 912) )
      v90 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DeviceComplianceSsoEnabled", v90);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "DeviceComplianceSsoEku", *(_QWORD *)(v9 + 920));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "DeviceComplianceSsoIssuer", *(_QWORD *)(v9 + 928));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "FlagsSet", *(unsigned int *)(v9 + 952));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "Options", *(unsigned int *)(v9 + 956));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v91 = "1";
    if ( !*(_DWORD *)(v9 + 788) )
      v91 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DisableDefaultDnsSuffixes", v91);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "NumTrustedNetworks", *(unsigned int *)(v9 + 792));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v92 = *(_QWORD *)(v9 + 800);
    if ( v92 )
    {
      if ( *(_DWORD *)(v9 + 792) )
      {
        LUAPhonebookPath = InsertBinary(v22, "TrustedNetworks", v92, *(unsigned int *)(v9 + 796));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    v93 = *(_QWORD *)(v9 + 760);
    if ( v93 )
    {
      LUAPhonebookPath = InsertBinary(v22, "ThirdPartyProfileInfo", v93, *(unsigned int *)(v9 + 752));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    LUAPhonebookPath = InsertLong(v22, "NumDnsSearchSuffixes", *(unsigned int *)(v9 + 768));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v94 = *(_QWORD *)(v9 + 776);
    if ( v94 )
    {
      LUAPhonebookPath = InsertBinary(v22, "DnsSuffixSearchList", v94, *(unsigned int *)(v9 + 772));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    v95 = "1";
    if ( !*(_DWORD *)(v9 + 784) )
      v95 = "0";
    LUAPhonebookPath = InsertStringA(v22, "PowershellCreatedProfile", v95);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "ProxyFlags", *(unsigned int *)(v9 + 560));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v96 = "1";
    if ( !*(_DWORD *)(v9 + 820) )
      v96 = "0";
    LUAPhonebookPath = InsertStringA(v22, "ProxySettingsModified", v96);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( (*(_BYTE *)(v9 + 560) & 2) != 0 )
    {
      LUAPhonebookPath = InsertString(v22, "Proxy", *(_QWORD *)(v9 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "ExcludeList", *(_QWORD *)(v9 + 584));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      v97 = "1";
      if ( !*(_DWORD *)(v9 + 592) )
        v97 = "0";
      LUAPhonebookPath = InsertStringA(v22, "BypassProxyForLocal", v97);
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    if ( (*(_BYTE *)(v9 + 560) & 4) != 0 )
    {
      LUAPhonebookPath = InsertString(v22, "AutoConfigScript", *(_QWORD *)(v9 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    LUAPhonebookPath = InsertString(v22, "ProvisioningAuthority", *(_QWORD *)(v9 + 808));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 333;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
    v98 = "1";
    if ( !*(_DWORD *)(v9 + 816) )
      v98 = "0";
    LUAPhonebookPath = InsertStringA(v22, "AuthTypeOTP", v98);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v99 = "1";
    if ( !*(_DWORD *)(v9 + 824) )
      v99 = "0";
    LUAPhonebookPath = InsertStringA(v22, "GREKeyDefined", v99);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 824) )
    {
      LUAPhonebookPath = InsertULong(v22, "GREKey", *(unsigned int *)(v9 + 828));
      if ( LUAPhonebookPath )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          v114 = 334;
          goto LABEL_807;
        }
        return LUAPhonebookPath;
      }
    }
    LUAPhonebookPath = InsertLong(v22, "NumPerAppTrafficFilters", *(unsigned int *)(v9 + 832));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v100 = *(_QWORD *)(v9 + 840);
    if ( v100 )
    {
      if ( *(_DWORD *)(v9 + 832) )
      {
        LUAPhonebookPath = InsertBinary(v22, "PerAppTrafficFilters", v100, *(unsigned int *)(v9 + 836));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    v101 = "1";
    if ( !*(_DWORD *)(v9 + 848) )
      v101 = "0";
    LUAPhonebookPath = InsertStringA(v22, "AlwaysOnCapable", v101);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v102 = "1";
    if ( !*(_DWORD *)(v9 + 856) )
      v102 = "0";
    inserted = InsertStringA(v22, "DeviceTunnel", v102);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 335;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v103 = "1";
    if ( !*(_DWORD *)(v9 + 852) )
      v103 = "0";
    LUAPhonebookPath = InsertStringA(v22, "PrivateNetwork", v103);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v104 = *(_QWORD *)(v9 + 944);
    if ( v104 )
    {
      v105 = *(unsigned int *)(v9 + 936);
      if ( (_DWORD)v105 )
      {
        LUAPhonebookPath = InsertBinary(v22, "PluginStorage", v104, v105);
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    LUAPhonebookPath = InsertString(v22, "ManagementApp", *(_QWORD *)(v9 + 960));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 168) == 15 )
    {
      LUAPhonebookPath = InsertULong(v22, "ProtocolListLength", *(unsigned int *)(v9 + 968));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertBinary(v22, "ProtocolList", v9 + 972, 16);
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListRetryTimeInHours", *(unsigned int *)(v9 + 988));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListCurrentProtocol", *(unsigned int *)(v9 + 992));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListTimeOfLastProtocolSelectionLow", *(unsigned int *)(v9 + 1000));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListTimeOfLastProtocolSelectionHigh", *(unsigned int *)(v9 + 1004));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    InsertNetComponents(v22, *(_QWORD *)(v9 + 264));
    v106 = **(_QWORD **)(v9 + 32);
    if ( v106 )
    {
      do
      {
        v107 = *(_QWORD *)(v106 + 16);
        LUAPhonebookPath = InsertGroup(v22, "MEDIA", *(_QWORD *)(v107 + 24));
        if ( LUAPhonebookPath )
          break;
        LUAPhonebookPath = InsertString(v22, "Port", *(_QWORD *)v107);
        if ( LUAPhonebookPath )
          break;
        v110 = *(_QWORD *)(v107 + 16);
        if ( v110 )
        {
          LUAPhonebookPath = InsertString(v22, "Device", v110);
          if ( LUAPhonebookPath )
            break;
        }
        if ( *(_DWORD *)(v107 + 40) == 3 || (*(_BYTE *)(v107 + 48) & 4) != 0 )
        {
          LUAPhonebookPath = InsertLong(v22, "ConnectBPS", *(unsigned int *)(v107 + 104));
          if ( LUAPhonebookPath )
            break;
        }
        LOBYTE(v109) = 2;
        LOBYTE(v108) = 48;
        rasFindLine(v22, v108, 2, v109, 2);
        LUAPhonebookPath = InsertDeviceList(a1, v22, v9, v107);
        if ( LUAPhonebookPath )
          break;
        v106 = *(_QWORD *)(v106 + 8);
      }
      while ( v106 );
      v8 = v123;
    }
    if ( *(_DWORD *)(v9 + 548) )
    {
      LUAPhonebookPath = InsertGroup(v22, "PROXYSETTINGS", 0);
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "AutoConfigScript", *(_QWORD *)(v9 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "Proxy", *(_QWORD *)(v9 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertLong(v22, "ProxyFlags", *(unsigned int *)(v9 + 560));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      v111 = *(const WCHAR **)(v9 + 584);
      memset_0(MultiByteStr, 0, 0x101u);
      v112 = lstrlenW(v111);
      if ( v112 )
      {
        while ( 1 )
        {
          memset_0(MultiByteStr, 0, 0x101u);
          cbMultiByte = v112;
          if ( v112 >= 0x100 )
            cbMultiByte = 256;
          if ( !WideCharToMultiByte(0xFDE9u, 0, v111, -1, MultiByteStr, cbMultiByte, 0, 0) )
            GetLastError();
          LUAPhonebookPath = InsertStringA(v22, "ExcludeList", MultiByteStr);
          if ( LUAPhonebookPath )
            goto LABEL_802;
          v111 += cbMultiByte;
          v112 -= cbMultiByte;
          if ( !v112 )
            goto LABEL_387;
        }
      }
      LUAPhonebookPath = InsertStringA(v22, "ExcludeList", MultiByteStr);
      if ( LUAPhonebookPath )
        goto LABEL_802;
LABEL_387:
      LUAPhonebookPath = 0;
    }
    *(_DWORD *)(v9 + 532) = 0;
    v4 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v117 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 308, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
      v117 = WPP_GLOBAL_Control;
    }
    if ( v117 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v117[1].Blink) < 0 && BYTE1(v117[1].Blink) >= 6u )
    {
      v118 = 309;
LABEL_517:
      WPP_SF_d(v117[1].Flink, v118, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18006d96c  mov     [rsp-8+arg_10], rbx
0x18006d971  push    rbp
0x18006d972  push    rsi
0x18006d973  push    rdi
0x18006d974  push    r12
0x18006d976  push    r13
0x18006d978  push    r14
0x18006d97a  push    r15
0x18006d97c  lea     rbp, [rsp-90h]
0x18006d984  sub     rsp, 190h
0x18006d98b  mov     rax, cs:__security_cookie
0x18006d992  xor     rax, rsp
0x18006d995  mov     [rbp+0C0h+var_40], rax
0x18006d99c  mov     rsi, rdx
0x18006d99f  mov     [rsp+1C0h+var_158], rdx
0x18006d9a4  mov     rbx, rcx
0x18006d9a7  mov     [rsp+1C0h+var_160], rcx
0x18006d9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9b3  lea     r14, WPP_GLOBAL_Control
0x18006d9ba  cmp     rcx, r14
0x18006d9bd  jz      short loc_18006D9E7
0x18006d9bf  test    byte ptr [rcx+1Ch], 80h
0x18006d9c3  jz      short loc_18006D9E7
0x18006d9c5  cmp     byte ptr [rcx+19h], 6
0x18006d9c9  jb      short loc_18006D9E7
0x18006d9cb  mov     rcx, [rcx+10h]
0x18006d9cf  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d9d6  mov     edx, 0E6h
0x18006d9db  call    WPP_SF_
0x18006d9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9e7  mov     rax, [rbx+10h]
0x18006d9eb  xor     r15d, r15d
0x18006d9ee  mov     edx, r15d
0x18006d9f1  mov     edi, r15d
0x18006d9f4  mov     [rsp+1C0h+var_180], edx
0x18006d9f8  mov     r8, [rax]
0x18006d9fb  mov     [rsp+1C0h+var_170], r8
0x18006da00  test    r8, r8
0x18006da03  jz      loc_180070AF8
0x18006da09  mov     r13d, r15d
0x18006da0c  mov     [rsp+1C0h+var_168], r15
0x18006da11  mov     rsi, [r8+10h]
0x18006da15  mov     r9d, 100h
0x18006da1b  lea     r12, [rsi+21Ch]
0x18006da22  cmp     [rsi+214h], r15d
0x18006da29  jnz     short loc_18006DA35
0x18006da2b  cmp     [r12], r15d
0x18006da2f  jz      loc_18006DC36
0x18006da35  mov     eax, [rbx+20h]
0x18006da38  and     eax, r9d
0x18006da3b  jz      short loc_18006DA93
0x18006da3d  cmp     [rsi+224h], r15d
0x18006da44  jz      short loc_18006DA93
0x18006da46  cmp     rcx, r14
0x18006da49  jz      short loc_18006DA79
0x18006da4b  test    byte ptr [rcx+1Ch], 80h
0x18006da4f  jz      short loc_18006DA79
0x18006da51  cmp     byte ptr [rcx+19h], 5
0x18006da55  jb      short loc_18006DA79
0x18006da57  mov     r9, [rsi+8]
0x18006da5b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006da62  mov     rcx, [rcx+10h]
0x18006da66  mov     edx, 0E7h
0x18006da6b  call    WPP_SF_S
0x18006da70  mov     edx, [rsp+1C0h+var_180]
0x18006da74  mov     r8, [rsp+1C0h+var_170]
0x18006da79  mov     [rsi+214h], r15d
0x18006da80  mov     [rsi+21Ch], r15d
0x18006da87  mov     rcx, cs:WPP_GLOBAL_Control
0x18006da8e  jmp     loc_18006DC36
0x18006da93  mov     edx, [rsi]
0x18006da95  cmp     edx, 0FFFFFFFFh
0x18006da98  jnz     loc_18006DC62
0x18006da9e  mov     [rsp+1C0h+hMem], r15
0x18006daa3  cmp     [rsi+224h], r15d
0x18006daaa  jz      short loc_18006DAEA
0x18006daac  cmp     dword ptr [rbx+8], 4
0x18006dab0  mov     r15d, 1
0x18006dab6  jz      short loc_18006DAEA
0x18006dab8  mov     rdx, [rsi+8]; STRSAFE_LPCWSTR
0x18006dabc  lea     r8, [rsp+1C0h+hMem]
0x18006dac1  mov     rcx, [rbx]; pszSrc
0x18006dac4  call    GetProvisionedProfilePath
0x18006dac9  mov     edi, eax
0x18006dacb  test    eax, eax
0x18006dacd  jnz     short loc_18006DB08
0x18006dacf  mov     r14, [rsp+1C0h+hMem]
0x18006dad4  mov     rbx, [rbx+30h]
0x18006dad8  xor     r13d, r13d
0x18006dadb  mov     [rsp+1C0h+var_168], r13
0x18006dae0  test    rbx, rbx
0x18006dae3  jz      short loc_18006DB5E
0x18006dae5  mov     rbx, [rbx]
0x18006dae8  jmp     short loc_18006DB54
0x18006daea  mov     rcx, [rbx]; pszSrc
0x18006daed  test    eax, eax
0x18006daef  jz      short loc_18006DB12
0x18006daf1  lea     rdx, [rsp+1C0h+hMem]
0x18006daf6  call    GetLUAPhonebookPath
0x18006dafb  mov     edi, eax
0x18006dafd  test    eax, eax
0x18006daff  jnz     short loc_18006DB08
0x18006db01  mov     r14, [rsp+1C0h+hMem]
0x18006db06  jmp     short loc_18006DB1C
0x18006db08  mov     r14, [rsp+1C0h+hMem]
0x18006db0d  jmp     loc_18006DBDA
0x18006db12  xor     edi, edi
0x18006db14  call    StrDup
0x18006db19  mov     r14, rax
0x18006db1c  test    r14, r14
0x18006db1f  jnz     short loc_18006DAD4
0x18006db21  lea     edi, [r14+8]
0x18006db25  jmp     loc_18006DBDA
0x18006db2a  mov     r13, [rbx+10h]
0x18006db2e  mov     [rsp+1C0h+var_168], r13
0x18006db33  test    r13, r13
0x18006db36  jz      short loc_18006DB5E
0x18006db38  mov     rcx, [r13+8]; lpString1
0x18006db3c  mov     rdx, r14; lpString2
0x18006db3f  call    CompareStringWrapW
0x18006db44  test    eax, eax
0x18006db46  jz      short loc_18006DB59
0x18006db48  mov     rbx, [rbx+8]
0x18006db4c  xor     r13d, r13d
0x18006db4f  mov     [rsp+1C0h+var_168], r13
0x18006db54  test    rbx, rbx
0x18006db57  jnz     short loc_18006DB2A
0x18006db59  test    r13, r13
0x18006db5c  jnz     short loc_18006DBDA
0x18006db5e  mov     rax, [rsp+1C0h+var_160]
0x18006db63  mov     r9d, r15d
0x18006db66  mov     r15, [rsp+1C0h+var_160]
0x18006db6b  mov     rdx, r14
0x18006db6e  mov     dword ptr [rsp+1C0h+hMem], 0FFFFFFFFh
0x18006db76  mov     dword ptr [rsp+1C0h+lpMultiByteStr], 1; int
0x18006db7e  mov     rax, [rax+30h]
0x18006db82  mov     r8d, [r15+8]
0x18006db86  mov     rcx, [r15+28h]; hToken
0x18006db8a  mov     ebx, [rax+10h]
0x18006db8d  call    CreateProfileDirAndSetAcls
0x18006db92  mov     edi, eax
0x18006db94  test    eax, eax
0x18006db96  jnz     short loc_18006DBDA
0x18006db98  mov     edx, [r15+20h]
0x18006db9c  lea     r8, [rsp+1C0h+hMem]
0x18006dba1  xor     r9d, r9d
0x18006dba4  mov     rcx, r14; lpFileName
0x18006dba7  call    LoadFile
0x18006dbac  mov     edi, eax
0x18006dbae  test    eax, eax
0x18006dbb0  jnz     short loc_18006DBDA
0x18006dbb2  mov     ecx, dword ptr [rsp+1C0h+hMem]
0x18006dbb6  inc     ebx
0x18006dbb8  mov     r8d, ebx
0x18006dbbb  mov     rdx, r14
0x18006dbbe  call    CreateHRasfileNode
0x18006dbc3  mov     [rsi], ebx
0x18006dbc5  mov     rdx, rax
0x18006dbc8  mov     rcx, [r15+30h]
0x18006dbcc  call    DtlAddNodeLast
0x18006dbd1  mov     r13, [rdx+10h]
0x18006dbd5  mov     [rsp+1C0h+var_168], r13
0x18006dbda  xor     r15d, r15d
0x18006dbdd  test    r14, r14
0x18006dbe0  jz      short loc_18006DBEB
0x18006dbe2  mov     rcx, r14; hMem
0x18006dbe5  call    cs:__imp_GlobalFree
0x18006dbeb  test    edi, edi
0x18006dbed  jz      short loc_18006DC52
0x18006dbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbf6  lea     r14, WPP_GLOBAL_Control
0x18006dbfd  cmp     rcx, r14
0x18006dc00  jz      short loc_18006DC2D
0x18006dc02  test    byte ptr [rcx+1Ch], 80h
0x18006dc06  jz      short loc_18006DC2D
0x18006dc08  cmp     byte ptr [rcx+19h], 2
0x18006dc0c  jb      short loc_18006DC2D
0x18006dc0e  mov     edx, 0E8h
0x18006dc13  mov     rcx, [rcx+10h]
0x18006dc17  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006dc1e  mov     r9d, edi
0x18006dc21  call    WPP_SF_d
0x18006dc26  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc2d  mov     edx, [rsp+1C0h+var_180]
0x18006dc31  mov     r8, [rsp+1C0h+var_170]
0x18006dc36  mov     r8, [r8+8]
0x18006dc3a  mov     [rsp+1C0h+var_170], r8
0x18006dc3f  test    r8, r8
0x18006dc42  jz      loc_180070AE6
0x18006dc48  mov     rbx, [rsp+1C0h+var_160]
0x18006dc4d  jmp     loc_18006DA11
0x18006dc52  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc59  lea     r14, WPP_GLOBAL_Control
0x18006dc60  jmp     short loc_18006DC9D
0x18006dc62  mov     rax, [rbx+30h]
0x18006dc66  mov     r13, r15
0x18006dc69  mov     [rsp+1C0h+var_168], r15
0x18006dc6e  test    rax, rax
0x18006dc71  jz      short loc_18006DC9D
0x18006dc73  mov     rax, [rax]
0x18006dc76  jmp     short loc_18006DC98
0x18006dc78  mov     r13, [rax+10h]
0x18006dc7c  mov     [rsp+1C0h+var_168], r13
0x18006dc81  test    r13, r13
0x18006dc84  jz      short loc_18006DCA2
0x18006dc86  cmp     [r13+10h], edx
0x18006dc8a  jz      short loc_18006DC9D
0x18006dc8c  mov     rax, [rax+8]
0x18006dc90  mov     r13, r15
0x18006dc93  mov     [rsp+1C0h+var_168], r15
0x18006dc98  test    rax, rax
0x18006dc9b  jnz     short loc_18006DC78
0x18006dc9d  test    r13, r13
0x18006dca0  jnz     short loc_18006DCFF
0x18006dca2  cmp     rcx, r14
0x18006dca5  jz      short loc_18006DCD3
0x18006dca7  test    byte ptr [rcx+1Ch], 80h
0x18006dcab  jz      short loc_18006DCD3
0x18006dcad  cmp     byte ptr [rcx+19h], 5
0x18006dcb1  jb      short loc_18006DCD3
0x18006dcb3  mov     r9, [rsi+8]
0x18006dcb7  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006dcbe  mov     rcx, [rcx+10h]
0x18006dcc2  mov     edx, 0E9h
0x18006dcc7  call    WPP_SF_S
0x18006dccc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dcd3  mov     edi, 26Eh
0x18006dcd8  cmp     rcx, r14
0x18006dcdb  jz      loc_18006DC2D
0x18006dce1  test    byte ptr [rcx+1Ch], 80h
0x18006dce5  jz      loc_18006DC2D
0x18006dceb  cmp     byte ptr [rcx+19h], 2
0x18006dcef  jb      loc_18006DC2D
0x18006dcf5  mov     edx, 0EAh
0x18006dcfa  jmp     loc_18006DC13
0x18006dcff  mov     ebx, [r13+0]
0x18006dd03  mov     rcx, rsi
0x18006dd06  call    UpdateEntryTimeStamp
0x18006dd0b  mov     rcx, [rsi+8]; lpWideCharStr
0x18006dd0f  call    StrDupAFromTInternal
0x18006dd14  mov     r14, rax
0x18006dd17  test    rax, rax
0x18006dd1a  jz      loc_180070B98
0x18006dd20  mov     rdx, rax
0x18006dd23  mov     ecx, ebx
0x18006dd25  call    RasfileFindSectionLine
0x18006dd2a  test    eax, eax
0x18006dd2c  jz      short loc_18006DD35
0x18006dd2e  mov     ecx, ebx
0x18006dd30  call    DeleteCurrentSection
0x18006dd35  mov     rcx, r14; hMem
0x18006dd38  call    cs:__imp_GlobalFree
0x18006dd3e  cmp     [r12], r15d
0x18006dd42  jnz     loc_18006F5ED
0x18006dd48  mov     r12d, 2
0x18006dd4e  xor     r8d, r8d
0x18006dd51  mov     r9b, r12b
0x18006dd54  mov     byte ptr [rsp+1C0h+lpMultiByteStr], r12b
0x18006dd59  mov     dl, 3Fh ; '?'
0x18006dd5b  mov     ecx, ebx
0x18006dd5d  call    rasFindLine
0x18006dd62  mov     rdx, [rsi+8]
0x18006dd66  mov     ecx, ebx
0x18006dd68  call    InsertSection
0x18006dd6d  mov     edi, eax
0x18006dd6f  test    eax, eax
0x18006dd71  jnz     loc_180070AB9
0x18006dd77  lea     r8d, [r12-1]
0x18006dd7c  mov     ecx, ebx
0x18006dd7e  lea     rdx, aEncoding; "Encoding"
0x18006dd85  call    InsertLong
0x18006dd8a  mov     edi, eax
0x18006dd8c  test    eax, eax
0x18006dd8e  jnz     loc_180070A84
0x18006dd94  lea     r8d, [r12+6]
0x18006dd99  mov     ecx, ebx
0x18006dd9b  lea     rdx, aPbversion; "PBVersion"
0x18006dda2  call    InsertLong
0x18006dda7  mov     edi, eax
0x18006dda9  test    eax, eax
0x18006ddab  jnz     loc_180070A4F
0x18006ddb1  mov     r8d, [rsi+18h]
0x18006ddb5  lea     rdx, aType; "Type"
0x18006ddbc  mov     ecx, ebx
0x18006ddbe  call    InsertLong
0x18006ddc3  mov     edi, eax
0x18006ddc5  test    eax, eax
0x18006ddc7  jnz     loc_180070A1A
0x18006ddcd  cmp     [rsi+0B0h], r15d
0x18006ddd4  lea     r8, a1; "1"
0x18006dddb  lea     r14, a0; "0"
0x18006dde2  mov     ecx, ebx
0x18006dde4  cmovz   r8, r14
0x18006dde8  lea     rdx, aAutologon; "AutoLogon"
0x18006ddef  call    InsertStringA
0x18006ddf4  mov     edi, eax
0x18006ddf6  test    eax, eax
0x18006ddf8  jnz     loc_1800709E5
0x18006ddfe  cmp     [rsi+0B4h], r15d
0x18006de05  lea     r8, a1; "1"
  ... truncated ...
```
