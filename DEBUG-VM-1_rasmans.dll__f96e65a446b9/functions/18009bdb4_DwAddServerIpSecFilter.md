# DwAddServerIpSecFilter

- ea: `0x18009bdb4`
- end: `0x18009cba3`
- name: `DwAddServerIpSecFilter`
- size: `3567`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d82c`
- `0x18003e198`

## callees

- `0x18009a990`
- `0x18009ade0`
- `0x18009ae9c`
- `0x18009b07c`
- `0x18009b350`
- `0x18009b40c`
- `0x18009b4f8`
- `0x18009bdb4`
- `0x18009d178`
- `0x18009d558`
- `0x18009d698`
- `0x18009d7cc`
- `0x18009d8e8`
- `0x18009dda4`
- `0x18009e368`
- `0x1800a5770`
- `0x1800ab90c`
- `0x1800e54d8`
- `0x1800e61bc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009beae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bfb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009beae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bfb7`
- `RPCRT4!UuidCreate` at `0x18009c284`
- `RPCRT4!UuidCreate` at `0x18009c2a0`
- `RPCRT4!UuidCreate` at `0x18009c284`
- `RPCRT4!UuidCreate` at `0x18009c2a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009c025`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009c025`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009be8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009bfa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c092`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009be8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009bfa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c092`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cb0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cb43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cb0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cb43`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009c612`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009ca74`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009c612`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009ca74`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18009c328`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18009c328`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18009ca65`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18009ca65`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18009c2fc`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18009c2fc`

## string_xrefs

- `0x18009c031`: `DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d`
- `0x18009c0d6`: `DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d`
- `0x18009c290`: `DwAddServerIpsecFilter: UuidCreate failed with 0x%x`
- `0x18009bfec`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\L2TP`

## pseudocode

```c
__int64 __fastcall DwAddServerIpSecFilter(unsigned int a1, __int64 a2, int a3)
{
  _DWORD *v3; // r13
  int v4; // r15d
  _DWORD *v7; // r14
  char *v8; // rsi
  int v9; // r12d
  DWORD LastError; // ebx
  DWORD v11; // eax
  int v12; // r12d
  DWORD v13; // esi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  DWORD v17; // eax
  int L2tpConfigParams; // ebx
  int v19; // esi
  int v20; // ebx
  _DWORD *v21; // rcx
  bool v22; // cf
  HLOCAL v23; // rbx
  const CHAR *v24; // rcx
  const CHAR *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // edi
  unsigned int v28; // edi
  unsigned int v29; // edi
  unsigned int v30; // edi
  int v31; // edx
  int v32; // edx
  int v33; // edx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdi
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // edx
  int v43; // edx
  int v44; // edx
  int v45; // edx
  __int64 v46; // rdi
  void *v47; // rcx
  unsigned int v48; // r15d
  unsigned int i; // edi
  __int64 j; // rdi
  BYTE samDesired; // [rsp+28h] [rbp-D8h]
  REGSAM samDesireda; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredb; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredc; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredd; // [rsp+28h] [rbp-D8h]
  REGSAM samDesirede; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredf; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredg; // [rsp+28h] [rbp-D8h]
  DWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  int v61; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  int v63; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v65; // [rsp+68h] [rbp-98h]
  int v66; // [rsp+70h] [rbp-90h] BYREF
  int v67; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL v68; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h]
  __int64 v71; // [rsp+90h] [rbp-70h]
  HLOCAL v72; // [rsp+98h] [rbp-68h]
  __int128 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-50h]
  __int128 v75; // [rsp+C0h] [rbp-40h]
  __int64 v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h]
  __int64 v78; // [rsp+E0h] [rbp-20h]
  int v79; // [rsp+E8h] [rbp-18h]
  int v80; // [rsp+ECh] [rbp-14h]
  __int128 v81; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+110h] [rbp+10h]
  _BYTE v84[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v85[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v86[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v87[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v88[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v89[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v90[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v91[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v92[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v93[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v94[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v95[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v96[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v97[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v98[16]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v99[16]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v100[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v101[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v102[16]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v103[16]; // [rsp+250h] [rbp+150h] BYREF
  UUID v104; // [rsp+260h] [rbp+160h] BYREF
  const wchar_t *v105; // [rsp+270h] [rbp+170h]
  int v106; // [rsp+2A0h] [rbp+1A0h]
  __int128 *v107; // [rsp+2A8h] [rbp+1A8h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = 0;
  v70 = a2;
  v4 = a3;
  v65 = a2;
  v71 = a2;
  v61 = a3;
  v68 = 0;
  hMem = 0;
  v7 = 0;
  v8 = 0;
  memset_0(&v104, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v66 = 0;
  v63 = 0;
  v83 = 0;
  v67 = 0;
  hKey = 0;
  v81 = 0;
  v9 = 0;
  v82 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  memset_0(v84, 0, 0x140u);
  RasIpsecTrace("DwAddServerIpSecFilter");
  v72 = LocalAlloc(0x40u, 0x118u);
  if ( !v72 )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: failed to alloc");
    LastError = GetLastError();
    goto LABEL_139;
  }
  dwDisposition = 1;
  if ( !a2 )
  {
    DwGetPresharedKey(0, 256, (int)&v61);
    v4 = v61;
    v65 = v71;
  }
  if ( v4 )
    v9 = 1;
  v61 = v9;
  v11 = GenerateCertificatesList(1, &v68, &v61, &dwDisposition);
  v12 = v61;
  LastError = v11;
  if ( !v4 )
  {
    v13 = dwDisposition;
    if ( !v11 && v61 && !dwDisposition )
    {
      v7 = v68;
      goto LABEL_25;
    }
    RasIpsecTrace("PSK=NULL. Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
    if ( !v12 || v13 )
      LastError = 766;
    v7 = v68;
    if ( v68 )
    {
      FreeAuthInfoList(v68);
      v7 = 0;
    }
    v8 = (char *)hMem;
    goto LABEL_18;
  }
  v7 = v68;
  v14 = 1;
  if ( v68 )
  {
LABEL_24:
    v15 = v65;
    v16 = 10 * v14;
    v7[2 * v16] = 0;
    *(_QWORD *)&v7[2 * v16 + 4] = v15;
    v7[2 * v16 + 2] = v4;
    goto LABEL_25;
  }
  v7 = LocalAlloc(0x40u, 0x40u);
  if ( v7 )
  {
    v14 = 0;
    goto LABEL_24;
  }
  LastError = GetLastError();
LABEL_18:
  if ( LastError )
  {
    RasIpsecTrace("DwAddServerIpsecFilter: DwGetMMAuthMethodsForServer returned %d. PSK length is %d");
    goto LABEL_143;
  }
LABEL_25:
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\L2TP",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    RasIpsecTrace("DwAddServerIpSecFilter:OpenIkev2ConfigKey: Failed. error %d");
LABEL_27:
    v17 = BuildIpsecOffers(a1, &hMem, &v63);
    goto LABEL_28;
  }
  v3 = LocalAlloc(0x40u, 0x20u);
  if ( !v3 )
  {
    RasIpsecTrace("DwAddServerIpSecFilter: Memory allocation failed");
    RegCloseKey(hKey);
    goto LABEL_27;
  }
  L2tpConfigParams = GetL2tpConfigParams(hKey);
  RegCloseKey(hKey);
  if ( L2tpConfigParams )
    RasIpsecTrace("DwAddServerIpSecFilter:GetIkev2ConfigParams: Failed. error %d");
  a1 = v3[1];
  v19 = v3[2];
  v20 = v3[3];
  if ( a1 == 1 )
  {
    a1 = 4;
  }
  else if ( v3[1] == 2 )
  {
    a1 = 5;
  }
  v21 = (_DWORD *)*((_QWORD *)v3 + 2);
  if ( !v21 )
    goto LABEL_27;
  v22 = v21[2] < 9u;
  v80 = 0;
  if ( v22 )
    v77 = qword_1800EC600[v21[2]];
  else
    v77 = 0;
  if ( v21[3] >= 6u )
    v78 = 0;
  else
    v78 = off_1800EC648[v21[3]];
  v22 = v21[4] < 8u;
  v76 = 0;
  v79 = v22 ? v21[4] : 0;
  v17 = BuildCustomEncryption((int)&hMem, (int)&v63, 0, v20, v19, samDesired, (__int64)&v76, 1, lpdwDisposition);
LABEL_28:
  LastError = v17;
  if ( !v17 )
  {
    v8 = (char *)hMem;
    BuildQMPolicy((unsigned int)&Uuid, (unsigned int)&v81, a1, (_DWORD)hMem, v63, 0, 0);
    if ( v3 )
      DWORD2(v82) = *v3;
    v23 = v72;
    BuildMMOffers((int)v72, (int)&v67, (int)&v66, 1, 0, 0, (__int64)v3);
    v75 = (unsigned int)v66;
    LODWORD(v74) = 0;
    LODWORD(v73) = 28800;
    *((_QWORD *)&v74 + 1) = v23;
    DWORD1(v74) = v67;
    *((_QWORD *)&v73 + 1) = v7;
    DWORD1(v73) = v12;
    memset_0(&v104, 0, 0x58u);
    v106 = 5;
    v107 = &v73;
    v105 = L"L2TP Main Mode Policy";
    LastError = UuidCreate(&Uuid.providerContextKey);
    if ( LastError || (LastError = UuidCreate(&v104)) != 0 )
    {
      v24 = "DwAddServerIpsecFilter: UuidCreate failed with 0x%x";
LABEL_53:
      RasIpsecTrace(v24);
      goto LABEL_139;
    }
    gServerMMPolicyGuid = v104;
    gServerQMPolicyGuid = Uuid.providerContextKey;
    LastError = FwpmTransactionBegin0Wrapper();
    if ( LastError )
    {
      v24 = "FwpmTransactionBegin0 failed with 0x%x";
      goto LABEL_53;
    }
    LastError = FwpmProviderContextAdd2(gFwpEngineHandle, &v104, 0, 0);
    if ( LastError )
    {
      v25 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
LABEL_134:
      RasIpsecTrace(v25);
      FwpmTransactionAbort0(gFwpEngineHandle);
      goto LABEL_139;
    }
    LastError = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
    if ( LastError )
    {
      v25 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
      goto LABEL_134;
    }
    if ( a1 )
    {
      v27 = a1 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( !v28 || (v29 = v28 - 1) == 0 )
        {
LABEL_64:
          LastError = BuildOutTxFilter((unsigned int)v95, v26, 1, 1, 1);
          if ( LastError )
          {
LABEL_65:
            v25 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_134;
          }
          LastError = BuildOutTxFilter((unsigned int)v94, v31, 1, 1, 0);
          if ( LastError )
          {
LABEL_67:
            v25 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_134;
          }
          LastError = AddFilters(v95, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_69;
          LastError = AddFilters(v94, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_71:
            v25 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_133;
          }
          LastError = BuildOutTxFilter((unsigned int)v99, v32, 1, 0, 1);
          if ( LastError )
          {
LABEL_73:
            v25 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_133;
          }
          LastError = BuildOutTxFilter((unsigned int)v98, v33, 1, 0, 0);
          if ( LastError )
          {
            v25 = "BuildOutTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_133;
          }
          LastError = AddFilters(v99, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_69;
          LastError = AddFilters(v98, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_71;
          LastError = BuildInTxFilter((unsigned int)v97, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesireda, 1);
          if ( LastError )
          {
LABEL_79:
            v25 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_133;
          }
          LastError = BuildInTxFilter((unsigned int)v96, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesiredb, 0);
          if ( LastError )
          {
LABEL_81:
            v25 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_133;
          }
          LastError = AddFilters(v97, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_83:
            v25 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_133;
          }
          LastError = AddFilters(v96, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_85:
            v25 = "AddFilters for QM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_133;
          }
          LastError = BuildOutMMFilter(v101, v34, L"L2TP Server Inbound and Outbound Filter", 1);
          if ( LastError )
          {
            v25 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_133;
          }
          LastError = BuildOutMMFilter(v100, v35, L"L2TP Server Inbound and Outbound Filter", 0);
          if ( LastError )
          {
            v25 = "BuildOutMMFilter for MM policy failed with 0x%x  Ipv6: FALSE";
            goto LABEL_133;
          }
          LastError = AddFilters(v101, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
          {
LABEL_91:
            v25 = "AddFilters for MM policy failed with 0x%x  Ipv6: TRUE";
            goto LABEL_133;
          }
          LastError = AddFilters(v100, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = FwpmTransactionCommit0(gFwpEngineHandle);
            if ( v7 )
            {
              v36 = v65;
              FreeAuthInfoList(v7);
              v8 = (char *)hMem;
              v7 = 0;
              if ( v70 != v36 )
                v65 = 0;
              goto LABEL_139;
            }
            goto LABEL_138;
          }
LABEL_132:
          v25 = "AddFilters for MM policy failed with 0x%x  Ipv6: FALSE";
          goto LABEL_133;
        }
        v30 = v29 - 1;
        if ( v30 )
        {
          if ( v30 != 1 )
            goto LABEL_139;
          goto LABEL_64;
        }
      }
    }
    LastError = BuildOutMMFilter(v101, v26, L"L2TP Server Outbound Filter", 1);
    if ( LastError )
    {
      v25 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_134;
    }
    LastError = BuildOutMMFilter(v100, v37, L"L2TP Server Outbound Filter", 0);
    if ( LastError )
    {
      v25 = "BuildOutMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_134;
    }
    LastError = BuildInMMFilter(v103, v38, v39, 1);
    if ( LastError )
    {
      v25 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: TRUE";
      goto LABEL_134;
    }
    LastError = BuildInMMFilter(v102, v40, v41, 0);
    if ( LastError )
    {
      v25 = "BuildInMMFilter for MM policy failed with 0x%x  IPv6: FALSE";
      goto LABEL_134;
    }
    LastError = BuildOutTxFilter((unsigned int)v85, v42, 0, 1, 1);
    if ( LastError )
      goto LABEL_65;
    LastError = BuildOutTxFilter((unsigned int)v84, v43, 0, 1, 0);
    if ( LastError )
      goto LABEL_67;
    LastError = AddFilters(v85, gServerFilterIds, &gNumServerFilterIds, 0);
    if ( !LastError )
    {
      LastError = AddFilters(v84, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_71;
      LastError = BuildOutTxFilter((unsigned int)v87, v44, 0, 0, 1);
      if ( LastError )
        goto LABEL_73;
      LastError = BuildOutTxFilter((unsigned int)v86, v45, 0, 0, 0);
      if ( LastError )
      {
        v25 = "BuildOutTxFilter for QM policy failed with 0x%x";
        goto LABEL_133;
      }
      LastError = AddFilters(v87, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_69;
      LastError = AddFilters(v86, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( LastError )
        goto LABEL_71;
      LastError = BuildInTxFilter((unsigned int)v89, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", samDesireda, 1);
      if ( LastError )
      {
LABEL_114:
        v25 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: TRUE";
        goto LABEL_133;
      }
      LastError = BuildInTxFilter((unsigned int)v88, 0, 1701, 0, (__int64)L"L2TP Server Inbound Filter", samDesiredc, 0);
      if ( LastError )
      {
LABEL_116:
        v25 = "BuildInTxFilter for QM policy failed with 0x%x  Ipv6: FALSE";
        goto LABEL_133;
      }
      LastError = AddFilters(v89, gServerFilterIds, &gNumServerFilterIds, 0);
      if ( !LastError )
      {
        LastError = AddFilters(v88, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( LastError )
          goto LABEL_71;
        LastError = BuildInTxFilter(
                      (unsigned int)v91,
                      0,
                      1701,
                      1701,
                      (__int64)L"L2TP Server Inbound Filter",
                      samDesiredd,
                      1);
        if ( LastError )
          goto LABEL_114;
        LastError = BuildInTxFilter(
                      (unsigned int)v90,
                      0,
                      1701,
                      1701,
                      (__int64)L"L2TP Server Inbound Filter",
                      samDesirede,
                      0);
        if ( LastError )
          goto LABEL_116;
        LastError = AddFilters(v91, gServerFilterIds, &gNumServerFilterIds, 0);
        if ( !LastError )
        {
          LastError = AddFilters(v90, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_71;
          LastError = BuildInTxFilter((unsigned int)v93, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesiredf, 1);
          if ( LastError )
            goto LABEL_79;
          LastError = BuildInTxFilter((unsigned int)v92, 1, 0, 1701, (__int64)L"L2TP Server Filter1", samDesiredg, 0);
          if ( LastError )
            goto LABEL_81;
          LastError = AddFilters(v93, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_83;
          LastError = AddFilters(v92, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_85;
          LastError = AddFilters(v101, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( LastError )
            goto LABEL_91;
          LastError = AddFilters(v100, gServerFilterIds, &gNumServerFilterIds, 0);
          if ( !LastError )
          {
            LastError = AddFilters(v103, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( LastError )
            {
              v25 = "AddFilters for MM policy failed with 0x%x  Ipv6:  TRUE";
              goto LABEL_133;
            }
            LastError = AddFilters(v102, gServerFilterIds, &gNumServerFilterIds, 0);
            if ( !LastError )
            {
              LastError = FwpmTransactionCommit0(gFwpEngineHandle);
              if ( v7 )
              {
                v46 = v65;
                FreeAuthInfoList(v7);
                v7 = 0;
                if ( v70 != v46 )
                  v65 = 0;
              }
              goto LABEL_138;
            }
          }
          goto LABEL_132;
        }
      }
    }
LABEL_69:
    v25 = "AddFilters for QM policy failed with 0x%x  Ipv6: TRUE";
LABEL_133:
    v8 = (char *)hMem;
    goto LABEL_134;
  }
  RasIpsecTrace("DwAddServerIpsecFilter: BuildIpsecOffers returned %d");
LABEL_138:
  v8 = (char *)hMem;
LABEL_139:
  if ( v3 )
  {
    v47 = (void *)*((_QWORD *)v3 + 2);
    if ( v47 )
    {
      MprCommonFree(v47);
      *((_QWORD *)v3 + 2) = 0;
    }
    LocalFree(v3);
  }
LABEL_143:
  if ( v8 )
  {
    v48 = v63;
    for ( i = 0; i < v48; ++i )
      WfpClearIpsecProposal(&v8[32 * i]);
    LocalFree(v8);
  }
  for ( j = 0; j != 20; ++j )
    WfpFilterListDestroy(&v84[16 * j], &v84[16 * j + 8]);
  if ( v72 )
    LocalFree(v72);
  if ( v7 )
    FreeAuthInfoList(v7);
  RasIpsecTrace("DwAddServerIpSecFilter, rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x18009bdb4  mov     [rsp-8+arg_18], rbx
0x18009bdb9  push    rbp
0x18009bdba  push    rsi
0x18009bdbb  push    rdi
0x18009bdbc  push    r12
0x18009bdbe  push    r13
0x18009bdc0  push    r14
0x18009bdc2  push    r15
0x18009bdc4  lea     rbp, [rsp-230h]
0x18009bdcc  sub     rsp, 330h
0x18009bdd3  mov     rax, cs:__security_cookie
0x18009bdda  xor     rax, rsp
0x18009bddd  mov     [rbp+260h+var_40], rax
0x18009bde4  xor     r13d, r13d
0x18009bde7  mov     [rbp+260h+var_2D8], rdx
0x18009bdeb  mov     r15d, r8d
0x18009bdee  mov     [rsp+360h+var_2F8], rdx
0x18009bdf3  mov     rbx, rdx
0x18009bdf6  mov     [rbp+260h+var_2D0], rdx
0x18009bdfa  mov     edi, ecx
0x18009bdfc  mov     [rsp+360h+var_310], r8d
0x18009be01  lea     r12d, [r13+58h]
0x18009be05  mov     [rsp+360h+var_2E8], r13
0x18009be0a  mov     r8d, r12d; Size
0x18009be0d  mov     [rsp+360h+hMem], r13
0x18009be12  xor     edx, edx; Val
0x18009be14  lea     rcx, [rbp+260h+var_100]; void *
0x18009be1b  mov     r14d, r13d
0x18009be1e  mov     esi, r13d
0x18009be21  call    memset_0
0x18009be26  mov     r8d, r12d; Size
0x18009be29  lea     rcx, [rbp+260h+Uuid]; void *
0x18009be30  xor     edx, edx; Val
0x18009be32  call    memset_0
0x18009be37  xorps   xmm0, xmm0
0x18009be3a  mov     [rsp+360h+var_2F0], r13d
0x18009be3f  xor     eax, eax
0x18009be41  mov     [rsp+360h+var_300], r13d
0x18009be46  xor     edx, edx; Val
0x18009be48  mov     [rbp+260h+var_250], eax
0x18009be4b  mov     r8d, 140h; Size
0x18009be51  mov     [rsp+360h+var_2EC], r13d
0x18009be56  lea     rcx, [rbp+260h+var_240]; void *
0x18009be5a  mov     [rbp+260h+hKey], r13
0x18009be5e  movups  [rbp+260h+var_270], xmm0
0x18009be62  mov     r12d, r13d
0x18009be65  movups  [rbp+260h+var_260], xmm0
0x18009be69  movups  [rbp+260h+var_2C0], xmm0
0x18009be6d  movups  [rbp+260h+var_2B0], xmm0
0x18009be71  movups  [rbp+260h+var_2A0], xmm0
0x18009be75  call    memset_0
0x18009be7a  lea     rcx, aDwaddserverips_2
0x18009be81  call    RasIpsecTrace
0x18009be86  mov     edx, 118h; uBytes
0x18009be8b  lea     ecx, [r13+40h]; uFlags
0x18009be8f  call    cs:__imp_LocalAlloc
0x18009be95  mov     [rbp+260h+var_2C8], rax
0x18009be99  lea     ecx, [r13+1]
0x18009be9d  test    rax, rax
0x18009bea0  jnz     short loc_18009BEBB
0x18009bea2  lea     rcx, aDwaddserverips_4
0x18009bea9  call    RasIpsecTrace
0x18009beae  call    cs:__imp_GetLastError
0x18009beb4  mov     ebx, eax
0x18009beb6  jmp     loc_18009CABA
0x18009bebb  mov     [rsp+360h+dwDisposition], ecx
0x18009bebf  test    rbx, rbx
0x18009bec2  jnz     short loc_18009BEEA
0x18009bec4  lea     r9, [rbp+260h+var_2D0]
0x18009bec8  mov     edx, 100h; int
0x18009becd  lea     r8, [rsp+360h+var_310]; int
0x18009bed2  xor     ecx, ecx; int
0x18009bed4  call    DwGetPresharedKey
0x18009bed9  mov     rax, [rbp+260h+var_2D0]
0x18009bedd  lea     ecx, [rbx+1]
0x18009bee0  mov     r15d, [rsp+360h+var_310]
0x18009bee5  mov     [rsp+360h+var_2F8], rax
0x18009beea  test    r15d, r15d
0x18009beed  lea     r9, [rsp+360h+dwDisposition]
0x18009bef2  lea     r8, [rsp+360h+var_310]
0x18009bef7  cmovnz  r12d, ecx
0x18009befb  lea     rdx, [rsp+360h+var_2E8]
0x18009bf00  mov     [rsp+360h+var_310], r12d
0x18009bf05  call    GenerateCertificatesList
0x18009bf0a  mov     r12d, [rsp+360h+var_310]
0x18009bf0f  mov     ebx, eax
0x18009bf11  mov     [rsp+360h+var_310], r12d
0x18009bf16  test    r15d, r15d
0x18009bf19  jnz     short loc_18009BF92
0x18009bf1b  mov     esi, [rsp+360h+dwDisposition]
0x18009bf1f  test    eax, eax
0x18009bf21  jnz     short loc_18009BF36
0x18009bf23  test    r12d, r12d
0x18009bf26  jz      short loc_18009BF36
0x18009bf28  test    esi, esi
0x18009bf2a  jnz     short loc_18009BF36
0x18009bf2c  mov     r14, [rsp+360h+var_2E8]
0x18009bf31  jmp     loc_18009BFDD
0x18009bf36  mov     r9d, esi
0x18009bf39  lea     rcx, aPskNullFailedT
0x18009bf40  mov     r8d, r12d
0x18009bf43  mov     edx, eax
0x18009bf45  call    RasIpsecTrace
0x18009bf4a  test    r12d, r12d
0x18009bf4d  jz      short loc_18009BF53
0x18009bf4f  test    esi, esi
0x18009bf51  jz      short loc_18009BF58
0x18009bf53  mov     ebx, 2FEh
0x18009bf58  mov     r14, [rsp+360h+var_2E8]
0x18009bf5d  test    r14, r14
0x18009bf60  jz      short loc_18009BF73
0x18009bf62  xor     r8d, r8d
0x18009bf65  mov     edx, r12d
0x18009bf68  mov     rcx, r14; hMem
0x18009bf6b  call    FreeAuthInfoList
0x18009bf70  xor     r14d, r14d
0x18009bf73  mov     rsi, [rsp+360h+hMem]
0x18009bf78  test    ebx, ebx
0x18009bf7a  jz      short loc_18009BFDD
0x18009bf7c  mov     r8d, r15d
0x18009bf7f  lea     rcx, aDwaddserverips
0x18009bf86  mov     edx, ebx
0x18009bf88  call    RasIpsecTrace
0x18009bf8d  jmp     loc_18009CADE
0x18009bf92  mov     r14, [rsp+360h+var_2E8]
0x18009bf97  mov     eax, 1
0x18009bf9c  test    r14, r14
0x18009bf9f  jnz     short loc_18009BFC3
0x18009bfa1  lea     eax, [r14+40h]
0x18009bfa5  mov     edx, eax; uBytes
0x18009bfa7  mov     ecx, eax; uFlags
0x18009bfa9  call    cs:__imp_LocalAlloc
0x18009bfaf  mov     r14, rax
0x18009bfb2  test    rax, rax
0x18009bfb5  jnz     short loc_18009BFC1
0x18009bfb7  call    cs:__imp_GetLastError
0x18009bfbd  mov     ebx, eax
0x18009bfbf  jmp     short loc_18009BF78
0x18009bfc1  xor     eax, eax
0x18009bfc3  mov     rcx, [rsp+360h+var_2F8]
0x18009bfc8  lea     rax, [rax+rax*4]
0x18009bfcc  add     rax, rax
0x18009bfcf  mov     [r14+rax*8], r13d
0x18009bfd3  mov     [r14+rax*8+10h], rcx
0x18009bfd8  mov     [r14+rax*8+8], r15d
0x18009bfdd  lea     rax, [rsp+360h+dwDisposition]
0x18009bfe2  mov     [rsp+360h+dwDisposition], r13d
0x18009bfe7  mov     [rsp+360h+lpdwDisposition], rax; cbData
0x18009bfec  lea     rdx, aSystemCurrentc_4
0x18009bff3  lea     rax, [rbp+260h+hKey]
0x18009bff7  xor     r9d, r9d; lpClass
0x18009bffa  mov     [rsp+360h+phkResult], rax; phkResult
0x18009bfff  xor     r8d, r8d; Reserved
0x18009c002  mov     [rsp+360h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18009c007  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c00e  mov     [rsp+360h+samDesired], 0F003Fh; Data
0x18009c016  mov     ebx, 3D090h
0x18009c01b  mov     [rsp+360h+dwOptions], r13d; dwOptions
0x18009c020  mov     esi, 0E10h
0x18009c025  call    cs:__imp_RegCreateKeyExW
0x18009c02b  test    eax, eax
0x18009c02d  jz      short loc_18009C08A
0x18009c02f  mov     edx, eax
0x18009c031  lea     rcx, aDwaddserverips_1
0x18009c038  call    RasIpsecTrace
0x18009c03d  mov     [rsp+360h+var_318], 0
0x18009c045  lea     r8, [rsp+360h+var_300]
0x18009c04a  mov     [rsp+360h+lpdwDisposition], 0
0x18009c053  lea     rdx, [rsp+360h+hMem]
0x18009c058  mov     [rsp+360h+samDesired], esi
0x18009c05c  mov     ecx, edi
0x18009c05e  mov     [rsp+360h+dwOptions], ebx
0x18009c062  call    BuildIpsecOffers
0x18009c067  mov     r15d, 1
0x18009c06d  mov     ebx, eax
0x18009c06f  test    eax, eax
0x18009c071  jz      loc_18009C1A3
0x18009c077  mov     edx, eax
0x18009c079  lea     rcx, aDwaddserverips_7
0x18009c080  call    RasIpsecTrace
0x18009c085  jmp     loc_18009CAB5
0x18009c08a  mov     edx, 20h ; ' '; uBytes
0x18009c08f  lea     ecx, [rdx+20h]; uFlags
0x18009c092  call    cs:__imp_LocalAlloc
0x18009c098  mov     r13, rax
0x18009c09b  test    rax, rax
0x18009c09e  jnz     short loc_18009C0B8
0x18009c0a0  lea     rcx, aDwaddserverips_5
0x18009c0a7  call    RasIpsecTrace
0x18009c0ac  mov     rcx, [rbp+260h+hKey]; hKey
0x18009c0b0  call    cs:__imp_RegCloseKey
0x18009c0b6  jmp     short loc_18009C03D
0x18009c0b8  mov     rcx, [rbp+260h+hKey]; hKey
0x18009c0bc  mov     r8, r13
0x18009c0bf  call    GetL2tpConfigParams
0x18009c0c4  mov     rcx, [rbp+260h+hKey]; hKey
0x18009c0c8  mov     ebx, eax
0x18009c0ca  call    cs:__imp_RegCloseKey
0x18009c0d0  test    ebx, ebx
0x18009c0d2  jz      short loc_18009C0E2
0x18009c0d4  mov     edx, ebx
0x18009c0d6  lea     rcx, aDwaddserverips_6
0x18009c0dd  call    RasIpsecTrace
0x18009c0e2  mov     edi, [r13+4]
0x18009c0e6  mov     eax, edi
0x18009c0e8  mov     esi, [r13+8]
0x18009c0ec  mov     ebx, [r13+0Ch]
0x18009c0f0  sub     eax, 1
0x18009c0f3  jz      short loc_18009C0FF
0x18009c0f5  cmp     eax, 1
0x18009c0f8  jnz     short loc_18009C104
0x18009c0fa  lea     edi, [rax+4]
0x18009c0fd  jmp     short loc_18009C104
0x18009c0ff  mov     edi, 4
0x18009c104  mov     rcx, [r13+10h]
0x18009c108  test    rcx, rcx
0x18009c10b  jz      loc_18009C03D
0x18009c111  cmp     dword ptr [rcx+8], 9
0x18009c115  lea     rdx, __ImageBase
0x18009c11c  mov     [rbp+260h+var_274], 0
0x18009c123  jnb     short loc_18009C136
0x18009c125  mov     eax, [rcx+8]
0x18009c128  mov     rax, ds:rva qword_1800EC600[rdx+rax*8]
0x18009c130  mov     [rbp+260h+var_288], rax
0x18009c134  jmp     short loc_18009C13E
0x18009c136  mov     [rbp+260h+var_288], 0
0x18009c13e  cmp     dword ptr [rcx+0Ch], 6
0x18009c142  jnb     short loc_18009C155
0x18009c144  mov     eax, [rcx+0Ch]
0x18009c147  mov     rax, ds:rva off_1800EC648[rdx+rax*8]
0x18009c14f  mov     [rbp+260h+var_280], rax
0x18009c153  jmp     short loc_18009C15D
0x18009c155  mov     [rbp+260h+var_280], 0
0x18009c15d  cmp     dword ptr [rcx+10h], 8
0x18009c161  lea     rdx, [rsp+360h+var_300]; int
0x18009c166  mov     r15d, 1
0x18009c16c  mov     [rbp+260h+var_290], 0
0x18009c174  sbb     eax, eax
0x18009c176  mov     dword ptr [rsp+360h+phkResult], r15d; int
0x18009c17b  and     eax, [rcx+10h]
0x18009c17e  mov     r9d, ebx; int
0x18009c181  mov     [rbp+260h+var_278], eax
0x18009c184  lea     rcx, [rsp+360h+hMem]; int
0x18009c189  lea     rax, [rbp+260h+var_290]
0x18009c18d  xor     r8d, r8d; int
0x18009c190  mov     [rsp+360h+lpSecurityAttributes], rax; __int64
0x18009c195  mov     [rsp+360h+dwOptions], esi; int
0x18009c199  call    BuildCustomEncryption
0x18009c19e  jmp     loc_18009C06D
0x18009c1a3  mov     eax, [rsp+360h+var_300]
0x18009c1a7  lea     rdx, [rbp+260h+var_270]
0x18009c1ab  mov     rsi, [rsp+360h+hMem]
0x18009c1b0  lea     rcx, [rbp+260h+Uuid]
0x18009c1b7  mov     dword ptr [rsp+360h+lpSecurityAttributes], 0
0x18009c1bf  mov     r9, rsi
0x18009c1c2  mov     [rsp+360h+samDesired], 0
0x18009c1ca  mov     r8d, edi
0x18009c1cd  mov     [rsp+360h+dwOptions], eax
0x18009c1d1  call    BuildQMPolicy
0x18009c1d6  test    r13, r13
0x18009c1d9  jz      short loc_18009C1E2
0x18009c1db  mov     eax, [r13+0]
0x18009c1df  mov     dword ptr [rbp+260h+var_260+8], eax
0x18009c1e2  mov     rbx, [rbp+260h+var_2C8]
0x18009c1e6  lea     r8, [rsp+360h+var_2F0]; int
0x18009c1eb  mov     [rsp+360h+lpSecurityAttributes], r13; __int64
0x18009c1f0  lea     rdx, [rsp+360h+var_2EC]; int
0x18009c1f5  mov     rcx, rbx; int
0x18009c1f8  mov     [rsp+360h+samDesired], 0; cbData
0x18009c200  mov     r9d, r15d; int
0x18009c203  mov     qword ptr [rsp+360h+dwOptions], 0; __int64
0x18009c20c  call    BuildMMOffers
0x18009c211  mov     eax, [rsp+360h+var_2F0]
0x18009c215  lea     rcx, [rbp+260h+var_100]; void *
0x18009c21c  xor     edx, edx; Val
0x18009c21e  mov     dword ptr [rbp+260h+var_2A0], eax
0x18009c221  mov     eax, [rsp+360h+var_2EC]
0x18009c225  mov     dword ptr [rbp+260h+var_2B0], 0
0x18009c22c  mov     dword ptr [rbp+260h+var_2A0+4], 0
0x18009c233  lea     r8d, [rdx+58h]; Size
0x18009c237  mov     qword ptr [rbp+260h+var_2A0+8], 708h
0x18009c23f  mov     dword ptr [rbp+260h+var_2C0], 7080h
0x18009c246  mov     qword ptr [rbp+260h+var_2B0+8], rbx
0x18009c24a  mov     dword ptr [rbp+260h+var_2B0+4], eax
0x18009c24d  mov     qword ptr [rbp+260h+var_2C0+8], r14
0x18009c251  mov     dword ptr [rbp+260h+var_2C0+4], r12d
0x18009c255  call    memset_0
0x18009c25a  lea     rax, [rbp+260h+var_2C0]
0x18009c25e  mov     [rbp+260h+var_C0], 5
0x18009c268  mov     [rbp+260h+var_B8], rax
0x18009c26f  lea     rcx, [rbp+260h+Uuid]; Uuid
0x18009c276  lea     rax, aL2tpMainModePo
0x18009c27d  mov     [rbp+260h+var_F0], rax
0x18009c284  call    cs:__imp_UuidCreate
0x18009c28a  mov     ebx, eax
0x18009c28c  test    eax, eax
0x18009c28e  jz      short loc_18009C299
0x18009c290  lea     rcx, aDwaddserverips_0
0x18009c297  jmp     short loc_18009C2DC
0x18009c299  lea     rcx, [rbp+260h+var_100]; Uuid
  ... truncated ...
```
