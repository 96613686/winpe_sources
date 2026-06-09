# GetTmInstanceInfoFromTm(void *,ulong,_GUID *,ushort * *)

- ea: `0x180022928`
- end: `0x18002353f`
- name: `?GetTmInstanceInfoFromTm@@YAJPEAXKPEAU_GUID@@PEAPEAG@Z`
- size: `3095`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022460`

## callees

- `0x180003cf0`
- `0x180006054`
- `0x180006214`
- `0x18000d5f4`
- `0x180014e80`
- `0x180017358`
- `0x180021e78`
- `0x180022928`
- `0x18004de14`
- `0x18004e078`
- `0x18007f7d8`
- `0x180081d92`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800233ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800233ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022afc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022afc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232db`
- `RPCRT4!UuidFromStringW` at `0x180022f66`
- `RPCRT4!UuidFromStringW` at `0x180022f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022c49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022c49`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022b52`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022b72`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022b52`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022b72`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180022aaa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180022aaa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180022a8a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180022a8a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180022ac9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180022ac9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180022b21`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180022b21`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x180022feb`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x180022feb`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x180022ee7`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x180022ee7`

## string_xrefs

- `0x180022a28`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180022a4e`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180022c32`: `ConstructMsgToTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@342): ConstructMsgToTm - NULL != wszExeName`
- `0x180022d0f`: `ConstructMsgToTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@378): ConstructMsgToTm - cbCummalative <= cbVarArea for Exe Name`
- `0x180022d35`: `StringCchCopyW failed for .EXE into message buffer.`
- `0x1800231f7`: `ParseResponseFromTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@413): ParseResponseFromTm - NULL != pRspMsg`
- `0x18002320d`: `ParseResponseFromTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@414): ParseResponseFromTm - 0 != dwcbRspMsg`
- `0x180023346`: `StringCchCopyW failed when copying virtual server name from response buffer from TM.`
- `0x1800229ca`: `GetTmInstanceInfoFromTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@537): GetTmInstanceInfoFromTm, NULL != o_pTmInstanceGuid`
- `0x1800229dc`: `GetTmInstanceInfoFromTm (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@538): GetTmInstanceInfoFromTm, NULL != o_ppVirtualServerName`
- `0x180022ba1`: `IsLocalDTCServiceEnabled returned an error.`
- `0x180022bf6`: `ConfigArgs version >= OLE_TM_CONFIG_VERSION_2, extracting resource id.`
- `0x180022db2`: `CreateLocalTmInstance failed.`
- `0x180022e13`: `CreateLocalTmInstance failed for retry.`
- `0x180022e52`: `Failed while attempting to check if DTC is online, hr = 0x%x.`
- `0x180022e95`: `Failed to start local DTC service, hr = 0x%x.`
- `0x180022ff7`: `MtxCluCreateClusterProxyTmInstance failed`
- `0x1800230b7`: `CSendReceive::CreateInstance2 failed.`

## pseudocode

```c
__int64 __fastcall GetTmInstanceInfoFromTm(char *a1, unsigned int a2, struct _GUID *a3, unsigned __int16 **a4)
{
  GUID v4; // xmm6
  unsigned __int16 *v6; // r13
  struct _QUERY_SERVICE_CONFIGW *v7; // r12
  signed int ExeNameAndAppId; // ebx
  BOOL v9; // r15d
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // r13
  SC_HANDLE v12; // rax
  SC_HANDLE v13; // r15
  signed int v14; // eax
  int v15; // ebx
  struct _QUERY_SERVICE_CONFIGW *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  _WORD *v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // r12
  unsigned __int64 v23; // rbx
  _DWORD *v24; // rax
  _DWORD *v25; // r15
  __int64 v26; // r9
  unsigned int v27; // r12d
  struct _GUID v28; // xmm0
  unsigned int v29; // eax
  _DWORD *v30; // r11
  const wchar_t *v31; // rax
  __int64 v32; // r9
  const wchar_t *v33; // rax
  __int64 v34; // r9
  __int64 v35; // rax
  int v36; // eax
  int v37; // eax
  RPC_STATUS v38; // ecx
  __int64 v39; // rcx
  struct INameObject *v40; // r13
  struct CSendReceive *Instance2; // rax
  struct CSendReceive *v42; // r15
  const wchar_t *v43; // rax
  __int64 v44; // r9
  signed int *v45; // rbx
  int v46; // r13d
  GUID v47; // xmm6
  unsigned __int16 *v48; // r12
  int v49; // eax
  unsigned __int16 *v50; // r11
  unsigned __int16 *v51; // r13
  GUID v52; // xmm7
  unsigned __int16 *v53; // r13
  unsigned __int64 v54; // rbx
  unsigned __int16 *v55; // rax
  const wchar_t *v56; // rcx
  __int64 v57; // r9
  __int64 v59; // [rsp+28h] [rbp-D8h]
  __int64 v60; // [rsp+28h] [rbp-D8h]
  const wchar_t *v61; // [rsp+30h] [rbp-D0h]
  __int64 v62; // [rsp+38h] [rbp-C8h]
  __int64 v63; // [rsp+38h] [rbp-C8h]
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v65; // [rsp+58h] [rbp-A8h]
  BOOL v66; // [rsp+60h] [rbp-A0h]
  unsigned int cb[3]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v68; // [rsp+70h] [rbp-90h]
  unsigned int v69; // [rsp+78h] [rbp-88h] BYREF
  int v70; // [rsp+7Ch] [rbp-84h] BYREF
  int v71; // [rsp+80h] [rbp-80h] BYREF
  int v72; // [rsp+84h] [rbp-7Ch] BYREF
  LPVOID v73; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v74; // [rsp+90h] [rbp-70h] BYREF
  signed int *v75; // [rsp+98h] [rbp-68h] BYREF
  struct ITmInstance *v76; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  RPC_WSTR StringUuid; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v79; // [rsp+B8h] [rbp-48h] BYREF
  struct INameObject *v80; // [rsp+C0h] [rbp-40h] BYREF
  struct INameObject *v81; // [rsp+C8h] [rbp-38h] BYREF
  void *v82; // [rsp+D0h] [rbp-30h] BYREF
  GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v84; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 **v85; // [rsp+F8h] [rbp-8h]
  struct _GUID *v86; // [rsp+100h] [rbp+0h]
  UUID Uuid; // [rsp+110h] [rbp+10h] BYREF

  v4 = GUID_NULL;
  v86 = a3;
  cb[0] = a2;
  v85 = a4;
  v82 = a1;
  pv = 0;
  v74 = (unsigned __int16 *)0x600000001LL;
  v70 = 1;
  v75 = 0;
  v72 = 0;
  *(_QWORD *)&cb[1] = 0;
  v76 = 0;
  v81 = 0;
  v80 = 0;
  v71 = 0;
  v84 = 0;
  v79 = 0;
  StringUuid = 0;
  v73 = 0;
  Buf2 = GUID_NULL;
  Uuid = GUID_NULL;
  if ( !a3 )
    DtcInternalErrorW(
      L"GetTmInstanceInfoFromTm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@537): GetTmInstanceInfoFromTm, NU"
       "LL != o_pTmInstanceGuid");
  if ( !a4 )
    DtcInternalErrorW(
      L"GetTmInstanceInfoFromTm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@538): GetTmInstanceInfoFromTm, NU"
       "LL != o_ppVirtualServerName");
  *a3 = GUID_NULL;
  *a4 = 0;
  v65 = 0;
  v6 = 0;
  v7 = 0;
  ExeNameAndAppId = GetExeNameAndAppId((unsigned __int16 **)&pv, &Buf2);
  if ( ExeNameAndAppId < 0 )
  {
    LODWORD(v59) = ExeNameAndAppId;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      546,
      L"GetTmInstanceInfoFromTm",
      v59,
      L"GetExeNameAndAppId failed.");
    goto LABEL_132;
  }
  if ( !a1 || *(_DWORD *)a1 < 2u )
    goto LABEL_38;
  if ( *((_DWORD *)a1 + 2) )
  {
    if ( *((_DWORD *)a1 + 2) == 1 )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
        582,
        L"GetTmInstanceInfoFromTm",
        0,
        L"ConfigArgs version >= OLE_TM_CONFIG_VERSION_2, extracting resource id.");
      v4 = *(GUID *)(a1 + 12);
    }
    goto LABEL_38;
  }
  pcbBytesNeeded = 0;
  v66 = 0;
  v9 = 0;
  v10 = OpenSCManagerW(0, 0, 1u);
  v11 = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    ExeNameAndAppId = LastError;
    if ( LastError > 0 )
      ExeNameAndAppId = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_31;
  }
  v12 = OpenServiceW(v10, L"MSDTC", 1u);
  v13 = v12;
  if ( !v12 )
  {
    v18 = GetLastError();
    ExeNameAndAppId = v18;
    if ( v18 > 0 )
      ExeNameAndAppId = (unsigned __int16)v18 | 0x80070000;
    goto LABEL_28;
  }
  if ( QueryServiceConfigA(v12, 0, 0, &pcbBytesNeeded) )
    goto LABEL_13;
  v14 = GetLastError();
  ExeNameAndAppId = v14;
  if ( v14 != 122 )
  {
    if ( !v14 )
    {
LABEL_13:
      ExeNameAndAppId = -2147418113;
      goto LABEL_25;
    }
    if ( v14 <= 0 )
      goto LABEL_25;
    v15 = (unsigned __int16)v14;
LABEL_18:
    ExeNameAndAppId = v15 | 0x80070000;
    goto LABEL_25;
  }
  v16 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(pcbBytesNeeded);
  v7 = v16;
  if ( !v16 )
  {
    ExeNameAndAppId = -2147024882;
    goto LABEL_25;
  }
  if ( QueryServiceConfigW(v13, v16, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    ExeNameAndAppId = 0;
    v66 = v7->dwStartType != 4;
    goto LABEL_25;
  }
  v17 = GetLastError();
  ExeNameAndAppId = v17;
  if ( v17 > 0 )
  {
    v15 = (unsigned __int16)v17;
    goto LABEL_18;
  }
LABEL_25:
  CloseServiceHandle(v13);
LABEL_28:
  CloseServiceHandle(v11);
  v9 = v66;
LABEL_31:
  CoTaskMemFree(v7);
  if ( ExeNameAndAppId < 0 )
  {
    LODWORD(v59) = ExeNameAndAppId;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      565,
      L"GetTmInstanceInfoFromTm",
      v59,
      L"IsLocalDTCServiceEnabled returned an error.");
    v7 = (struct _QUERY_SERVICE_CONFIGW *)v65;
    v6 = v65;
    goto LABEL_132;
  }
  if ( v9 )
    v4 = (GUID)LOCAL_DTC_TM_RESOURCE_ID;
  else
    v4 = GUID_NULL;
LABEL_38:
  v20 = pv;
  if ( !pv )
    DtcInternalErrorW(
      L"ConstructMsgToTm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@342): ConstructMsgToTm - NULL != wszExeName");
  v68 = 0;
  v66 = 0;
  pcbBytesNeeded = GetCurrentProcessId();
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  v69 = 2 * v21 + 2;
  v22 = ((unsigned __int64)v69 + 3) >> 2;
  v23 = v69;
  v24 = CoTaskMemAlloc((unsigned int)(4 * v22 + 44));
  v25 = v24;
  if ( !v24 )
  {
    v61 = L"Unable to allocate memory for message to TM.";
    ExeNameAndAppId = -2147024882;
    LODWORD(v59) = -2147024882;
    v26 = 361;
LABEL_44:
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      v26,
      L"ConstructMsgToTm",
      v59,
      v61);
    v27 = v66;
    goto LABEL_48;
  }
  v28 = Buf2;
  *v24 = cb[0];
  v24[9] = pcbBytesNeeded;
  v29 = v69;
  *(GUID *)(v25 + 1) = v4;
  *(struct _GUID *)(v25 + 5) = v28;
  v25[10] = v29;
  ExeNameAndAppId = StringCchCopyW((unsigned __int16 *)v25 + 22, v23 >> 1, (const unsigned __int16 *)pv);
  if ( ExeNameAndAppId < 0 )
  {
    v26 = 382;
    v61 = L"StringCchCopyW failed for .EXE into message buffer.";
    LODWORD(v59) = ExeNameAndAppId;
    goto LABEL_44;
  }
  v68 = (unsigned __int16 *)v25;
  v27 = 4 * v22 + 44;
  v25 = v30;
LABEL_48:
  CoTaskMemFree(v25);
  if ( ExeNameAndAppId >= 0 )
  {
    ExeNameAndAppId = CreateLocalTmInstance(0, &v76);
    if ( ExeNameAndAppId < 0 )
    {
      v31 = L"CreateLocalTmInstance failed.";
      v32 = 614;
      goto LABEL_50;
    }
    ExeNameAndAppId = GetLocalNameObject(v76, &v80);
    if ( ExeNameAndAppId < 0 )
    {
      v33 = L"GetLocalNameObject failed.";
      v34 = 621;
LABEL_55:
      LODWORD(v59) = ExeNameAndAppId;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
        v34,
        L"GetTmInstanceInfoFromTm",
        v59,
        v33);
LABEL_126:
      if ( v80 )
        (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v80 + 16LL))(v80);
      if ( v81 )
        (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v81 + 16LL))(v81);
      v7 = (struct _QUERY_SERVICE_CONFIGW *)v65;
      goto LABEL_131;
    }
    ExeNameAndAppId = CreateLocalTmInstance(0, (struct ITmInstance **)&cb[1]);
    if ( ExeNameAndAppId < 0 )
    {
      v33 = L"CreateLocalTmInstance failed for retry.";
      v34 = 632;
      goto LABEL_55;
    }
    v35 = **(_QWORD **)&cb[1];
    if ( (cb[0] & 1) != 0 )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, int *))(v35 + 336))(*(_QWORD *)&cb[1], &v70);
      ExeNameAndAppId = v36;
      if ( v36 < 0 )
      {
        LODWORD(v59) = v36;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
          643,
          L"GetTmInstanceInfoFromTm",
          v59,
          L"Failed while attempting to check if DTC is online, hr = 0x%x.",
          v36);
        goto LABEL_126;
      }
    }
    else
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v35 + 320))(*(_QWORD *)&cb[1], 0);
      if ( v37 < 0 )
      {
        TraceStringInline(
          15,
          2,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
          653,
          L"GetTmInstanceInfoFromTm",
          0,
          L"Failed to start local DTC service, hr = 0x%x.",
          v37);
LABEL_64:
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&cb[1] + 16LL))(*(_QWORD *)&cb[1]);
        *(_QWORD *)&cb[1] = 0;
        ExeNameAndAppId = MtxCluGetDefaultClusterResourceNonAdmin(0, &StringUuid, &v73);
        if ( ExeNameAndAppId < 0 )
        {
          LODWORD(v59) = 0;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            671,
            L"GetTmInstanceInfoFromTm",
            v59,
            L"MtxCluGetDefaultClusterResourceNonAdmin failed");
          goto LABEL_126;
        }
        if ( !StringUuid )
        {
          ExeNameAndAppId = -2147467259;
          LODWORD(v59) = -2147467259;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            678,
            L"GetTmInstanceInfoFromTm",
            v59,
            L"MtxCluGetDefaultClusterResourceNonAdmin did not return a default TM instance");
          goto LABEL_126;
        }
        if ( !v73 )
        {
          ExeNameAndAppId = -2147467259;
          LODWORD(v59) = -2147467259;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            685,
            L"GetTmInstanceInfoFromTm",
            v59,
            L"MtxCluGetDefaultClusterResourceNonAdmin did not return a default Virtual Server Name");
          goto LABEL_126;
        }
        v38 = UuidFromStringW(StringUuid, &Uuid);
        if ( v38 )
        {
          LODWORD(v62) = v38;
          ExeNameAndAppId = -2147467259;
          LODWORD(v59) = -2147467259;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            696,
            L"GetTmInstanceInfoFromTm",
            v59,
            L"UuidFromStringW failed: RPC error = %d",
            v62);
          goto LABEL_126;
        }
        TraceStringInline(
          15,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
          700,
          L"GetTmInstanceInfoFromTm",
          0,
          L"Creating a ClusterProxyTmInstance for default TM id %s, Virtual Server %s",
          StringUuid,
          v73);
        Buf2 = Uuid;
        ExeNameAndAppId = MtxCluCreateClusterProxyTmInstance(v73, &Buf2, &cb[1]);
        if ( ExeNameAndAppId < 0 )
        {
          v33 = L"MtxCluCreateClusterProxyTmInstance failed";
          v34 = 708;
          goto LABEL_55;
        }
LABEL_74:
        ExeNameAndAppId = GetTmNameObjectForDescription(*(struct ITmInstance **)&cb[1], L"MSDTC", &v81);
        if ( ExeNameAndAppId < 0 )
        {
          v33 = L"GetTmNameObjectForDescription failed.";
          v34 = 716;
          goto LABEL_55;
        }
        v39 = 0;
        if ( v82 && *(_DWORD *)v82 )
          v39 = *((unsigned int *)v82 + 1);
        v40 = v81;
        ExeNameAndAppId = InitializeCm(v39, v74, v80, v81, &v84, &v79);
        if ( ExeNameAndAppId < 0 )
        {
          LODWORD(v60) = ExeNameAndAppId;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            740,
            L"GetTmInstanceInfoFromTm",
            v60,
            L"InitCm failed.");
LABEL_122:
          if ( v79 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
          if ( v84 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
          goto LABEL_126;
        }
        Instance2 = CSendReceive::CreateInstance2();
        v42 = Instance2;
        if ( !Instance2 )
        {
          LODWORD(v60) = -2147024882;
          ExeNameAndAppId = -2147024882;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            750,
            L"GetTmInstanceInfoFromTm",
            v60,
            L"CSendReceive::CreateInstance2 failed.");
          goto LABEL_122;
        }
        ExeNameAndAppId = (*(__int64 (__fastcall **)(struct CSendReceive *, __int64, struct INameObject *, __int64, int))(*(_QWORD *)Instance2 + 256LL))(
                            Instance2,
                            v79,
                            v40,
                            1,
                            272);
        if ( ExeNameAndAppId < 0 )
        {
          v43 = L"CSendReceive::ConnectSync failed.";
          v44 = 764;
LABEL_118:
          LODWORD(v60) = ExeNameAndAppId;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            v44,
            L"GetTmInstanceInfoFromTm",
            v60,
            v43);
          goto LABEL_119;
        }
        ExeNameAndAppId = (*(__int64 (__fastcall **)(struct CSendReceive *, __int64, _QWORD, unsigned __int16 *, int *, signed int **, _DWORD, int *))(*(_QWORD *)v42 + 96LL))(
                            v42,
                            32769,
                            v27,
                            v68,
                            &v71,
                            &v75,
                            0,
                            &v72);
        if ( ExeNameAndAppId < 0 )
        {
          v43 = L"CSendReceive::SendReceive failed.";
          v44 = 779;
          goto LABEL_118;
        }
        if ( v71 == 3 )
        {
          ExeNameAndAppId = -2147024891;
          v43 = L"Connection request denied - This shouldn't happen because the TM should support this connection request.";
          v44 = 787;
          goto LABEL_118;
        }
        if ( v71 != 32770 )
        {
          if ( v71 == 32771 )
          {
            v44 = 796;
            ExeNameAndAppId = *v75;
            v43 = L"Error returned from TM";
            goto LABEL_118;
          }
          LODWORD(v63) = v71;
          ExeNameAndAppId = -2147168229;
          LODWORD(v60) = -2147168229;
          TraceStringInline(
            15,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
            815,
            L"GetTmInstanceInfoFromTm",
            v60,
            L"Unexpected response MTAG from TM - 0x%x.",
            v63);
LABEL_119:
          if ( v75 )
            (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)v42 + 120LL))(v42);
          (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)v42 + 272LL))(v42);
          (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)v42 + 168LL))(v42);
          goto LABEL_122;
        }
        v45 = v75;
        v74 = 0;
        cb[0] = 0;
        if ( !v75 )
          DtcInternalErrorW(
            L"ParseResponseFromTm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@413): ParseResponseFromTm - NULL != pRspMsg");
        v46 = v72;
        if ( !v72 )
          DtcInternalErrorW(
            L"ParseResponseFromTm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@414): ParseResponseFromTm - 0 != dwcbRspMsg");
        v47 = *(GUID *)v75;
        v48 = 0;
        Buf2 = *(GUID *)v75;
        v49 = memcmp_0(&GUID_NULL, &Buf2, 0x10u);
        v50 = 0;
        if ( !v49 )
        {
          ExeNameAndAppId = 0;
LABEL_98:
          v51 = v48;
          v65 = v48;
          v48 = v50;
          v52 = v47;
LABEL_114:
          CoTaskMemFree(v48);
          if ( ExeNameAndAppId < 0 )
          {
            v43 = L"ParseResponseFromTm failed.";
            v44 = 805;
            goto LABEL_118;
          }
          v65 = 0;
          *v85 = v51;
          *v86 = v52;
          goto LABEL_119;
        }
        v52 = GUID_NULL;
        v65 = 0;
        v69 = v46 - 16;
        v82 = v45 + 4;
        if ( v46 == 16 )
        {
          v56 = L"The TM did not give us a virtual server name - bad TM.";
          v57 = 474;
        }
        else
        {
          ExeNameAndAppId = CTxStatusInfo::GetNextVarItemWithinBounds(&v82, (void **)&v74, cb, &v69);
          if ( ExeNameAndAppId < 0 )
          {
            LODWORD(v60) = ExeNameAndAppId;
            TraceStringInline(
              15,
              1,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
              441,
              L"ParseResponseFromTm",
              v60,
              L"GetNextVarItemWithinBounds failed for virtual server name in response from TM.");
LABEL_113:
            v51 = 0;
            goto LABEL_114;
          }
          if ( cb[0] )
          {
            v53 = v74;
            if ( v74 )
            {
              if ( *v74 )
              {
                v54 = cb[0];
                v55 = (unsigned __int16 *)CoTaskMemAlloc(cb[0]);
                v48 = v55;
                if ( v55 )
                {
                  ExeNameAndAppId = StringCchCopyW(v55, v54 >> 1, v53);
                  if ( ExeNameAndAppId >= 0 )
                    goto LABEL_98;
                  LODWORD(v60) = ExeNameAndAppId;
                  TraceStringInline(
                    15,
                    1,
                    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
                    466,
                    L"ParseResponseFromTm",
                    v60,
                    L"StringCchCopyW failed when copying virtual server name from response buffer from TM.");
                }
                else
                {
                  ExeNameAndAppId = -2147024882;
                  LODWORD(v60) = -2147024882;
                  TraceStringInline(
                    15,
                    1,
                    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
                    459,
                    L"ParseResponseFromTm",
                    v60,
                    L"Unable to allocate memory for virtual server name.");
                }
                v51 = v65;
                goto LABEL_114;
              }
            }
          }
          v56 = L"Virtual server name in response from TM is invalid.";
          v57 = 450;
        }
        LODWORD(v60) = -2147467259;
        ExeNameAndAppId = -2147467259;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
          v57,
          L"ParseResponseFromTm",
          v60,
          v56);
        goto LABEL_113;
      }
    }
    if ( v70 )
      goto LABEL_74;
    goto LABEL_64;
  }
  v31 = L"ConstructMsgToTm failed.";
  v32 = 597;
LABEL_50:
  LODWORD(v59) = ExeNameAndAppId;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
    v32,
    L"GetTmInstanceInfoFromTm",
    v59,
    v31);
  v7 = 0;
LABEL_131:
  v6 = v68;
LABEL_132:
  if ( *(_QWORD *)&cb[1] )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&cb[1] + 16LL))(*(_QWORD *)&cb[1]);
    *(_QWORD *)&cb[1] = 0;
  }
  if ( v76 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v6);
  CoTaskMemFree(v7);
  CoTaskMemFree(StringUuid);
  CoTaskMemFree(v73);
  return (unsigned int)ExeNameAndAppId;
}

```

## disassembly

```asm
0x180022928  mov     rax, rsp
0x18002292b  mov     [rax+10h], rbx
0x18002292f  push    rbp
0x180022930  push    rsi
0x180022931  push    rdi
0x180022932  push    r12
0x180022934  push    r13
0x180022936  push    r14
0x180022938  push    r15
0x18002293a  lea     rbp, [rsp-50h]
0x18002293f  sub     rsp, 150h
0x180022946  movaps  xmmword ptr [rax-48h], xmm6
0x18002294a  movaps  xmmword ptr [rax-58h], xmm7
0x18002294e  mov     rax, cs:__security_cookie
0x180022955  xor     rax, rsp
0x180022958  mov     [rbp+80h+var_60], rax
0x18002295c  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180022963  xor     edi, edi
0x180022965  mov     [rbp+80h+var_80], r8
0x180022969  mov     dword ptr [rsp+180h+cb], edx
0x18002296d  mov     rax, r9
0x180022970  mov     [rbp+80h+var_88], rax
0x180022974  mov     r15, rcx
0x180022977  mov     [rbp+80h+var_B0], rcx
0x18002297b  mov     [rbp+80h+pv], rdi
0x18002297f  lea     esi, [rdi+1]
0x180022982  mov     dword ptr [rbp+80h+var_F0], esi
0x180022985  mov     [rsp+180h+var_104], esi
0x180022989  mov     [rbp+80h+var_E8], rdi
0x18002298d  mov     [rbp+80h+var_FC], edi
0x180022990  mov     qword ptr [rsp+180h+cb+4], rdi
0x180022995  mov     [rbp+80h+var_E0], rdi
0x180022999  mov     [rbp+80h+var_B8], rdi
0x18002299d  mov     [rbp+80h+var_C0], rdi
0x1800229a1  mov     dword ptr [rbp+80h+var_F0+4], 6
0x1800229a8  mov     [rbp+80h+var_100], edi
0x1800229ab  mov     [rbp+80h+var_90], rdi
0x1800229af  mov     [rbp+80h+var_C8], rdi
0x1800229b3  mov     [rbp+80h+StringUuid], rdi
0x1800229b7  mov     [rbp+80h+var_F8], rdi
0x1800229bb  movdqu  [rbp+80h+Buf2], xmm6
0x1800229c0  movdqu  xmmword ptr [rbp+80h+Uuid.Data1], xmm6
0x1800229c5  test    r8, r8
0x1800229c8  jnz     short loc_1800229D7
0x1800229ca  lea     rcx, aGettminstancei_3; "GetTmInstanceInfoFromTm (com\\complus\\"...
0x1800229d1  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800229d7  test    rax, rax
0x1800229da  jnz     short loc_1800229E9
0x1800229dc  lea     rcx, aGettminstancei; "GetTmInstanceInfoFromTm (com\\complus\\"...
0x1800229e3  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800229e9  movdqu  xmmword ptr [r8], xmm6
0x1800229ee  lea     rdx, [rbp+80h+Buf2]; struct _GUID *
0x1800229f2  mov     [r9], rdi
0x1800229f5  lea     rcx, [rbp+80h+pv]; unsigned __int16 **
0x1800229f9  mov     [rsp+180h+var_128], rdi
0x1800229fe  mov     r13, rdi
0x180022a01  mov     r12, rdi
0x180022a04  call    ?GetExeNameAndAppId@@YAJPEAPEAGPEAU_GUID@@@Z; GetExeNameAndAppId(ushort * *,_GUID *)
0x180022a09  lea     r14, aGettminstancei_2; "GetTmInstanceInfoFromTm"
0x180022a10  mov     ebx, eax
0x180022a12  test    eax, eax
0x180022a14  jns     short loc_180022A4C
0x180022a16  lea     rax, aGetexenameanda_0; "GetExeNameAndAppId failed."
0x180022a1d  mov     r9d, 222h
0x180022a23  mov     [rsp+180h+var_150], rax
0x180022a28  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180022a2f  mov     dword ptr [rsp+180h+var_158], ebx
0x180022a33  mov     edx, esi
0x180022a35  mov     ecx, 0Fh
0x180022a3a  mov     [rsp+180h+var_160], r14
0x180022a3f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022a44  xor     r15d, r15d
0x180022a47  jmp     loc_1800234A8
0x180022a4c  xor     ebx, ebx
0x180022a4e  lea     rdi, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180022a55  mov     esi, 0Fh
0x180022a5a  test    r15, r15
0x180022a5d  jz      loc_180022C26
0x180022a63  cmp     dword ptr [r15], 2
0x180022a67  jb      loc_180022C26
0x180022a6d  cmp     [r15+8], ebx
0x180022a71  jnz     loc_180022BEF
0x180022a77  xor     edx, edx; lpDatabaseName
0x180022a79  mov     [rsp+180h+pcbBytesNeeded], ebx
0x180022a7d  xor     ecx, ecx; lpMachineName
0x180022a7f  mov     [rsp+180h+var_120], ebx
0x180022a83  lea     r8d, [rsi-0Eh]; dwDesiredAccess
0x180022a87  mov     r15d, ebx
0x180022a8a  call    cs:__imp_OpenSCManagerW
0x180022a90  mov     r13, rax
0x180022a93  test    rax, rax
0x180022a96  jz      loc_180022B7F
0x180022a9c  lea     r8d, [rsi-0Eh]; dwDesiredAccess
0x180022aa0  mov     rcx, rax; hSCManager
0x180022aa3  lea     rdx, aMsdtc; "MSDTC"
0x180022aaa  call    cs:__imp_OpenServiceW
0x180022ab0  mov     r15, rax
0x180022ab3  test    rax, rax
0x180022ab6  jz      loc_180022B5A
0x180022abc  lea     r9, [rsp+180h+pcbBytesNeeded]; pcbBytesNeeded
0x180022ac1  xor     r8d, r8d; cbBufSize
0x180022ac4  xor     edx, edx; lpServiceConfig
0x180022ac6  mov     rcx, rax; hService
0x180022ac9  call    cs:__imp_QueryServiceConfigA
0x180022acf  test    eax, eax
0x180022ad1  jz      short loc_180022ADA
0x180022ad3  mov     ebx, 8000FFFFh
0x180022ad8  jmp     short loc_180022B4F
0x180022ada  call    cs:__imp_GetLastError
0x180022ae0  mov     ebx, eax
0x180022ae2  cmp     eax, 7Ah ; 'z'
0x180022ae5  jz      short loc_180022AF8
0x180022ae7  test    eax, eax
0x180022ae9  jz      short loc_180022AD3
0x180022aeb  jle     short loc_180022B4F
0x180022aed  movzx   ebx, bx
0x180022af0  or      ebx, 80070000h
0x180022af6  jmp     short loc_180022B4F
0x180022af8  mov     ecx, [rsp+180h+pcbBytesNeeded]; cb
0x180022afc  call    cs:__imp_CoTaskMemAlloc
0x180022b02  mov     r12, rax
0x180022b05  test    rax, rax
0x180022b08  jnz     short loc_180022B11
0x180022b0a  mov     ebx, 8007000Eh
0x180022b0f  jmp     short loc_180022B4F
0x180022b11  mov     r8d, [rsp+180h+pcbBytesNeeded]; cbBufSize
0x180022b16  lea     r9, [rsp+180h+pcbBytesNeeded]; pcbBytesNeeded
0x180022b1b  mov     rdx, r12; lpServiceConfig
0x180022b1e  mov     rcx, r15; hService
0x180022b21  call    cs:__imp_QueryServiceConfigW
0x180022b27  xor     ecx, ecx
0x180022b29  test    eax, eax
0x180022b2b  jnz     short loc_180022B3E
0x180022b2d  call    cs:__imp_GetLastError
0x180022b33  mov     ebx, eax
0x180022b35  test    eax, eax
0x180022b37  jle     short loc_180022B4F
0x180022b39  movzx   ebx, ax
0x180022b3c  jmp     short loc_180022AF0
0x180022b3e  cmp     dword ptr [r12+4], 4
0x180022b44  mov     eax, ecx
0x180022b46  mov     ebx, ecx
0x180022b48  setnz   al
0x180022b4b  mov     [rsp+180h+var_120], eax
0x180022b4f  mov     rcx, r15; hSCObject
0x180022b52  call    cs:__imp_CloseServiceHandle
0x180022b58  jmp     short loc_180022B6F
0x180022b5a  call    cs:__imp_GetLastError
0x180022b60  mov     ebx, eax
0x180022b62  test    eax, eax
0x180022b64  jle     short loc_180022B6F
0x180022b66  movzx   ebx, ax
0x180022b69  or      ebx, 80070000h
0x180022b6f  mov     rcx, r13; hSCObject
0x180022b72  call    cs:__imp_CloseServiceHandle
0x180022b78  mov     r15d, [rsp+180h+var_120]
0x180022b7d  jmp     short loc_180022B94
0x180022b7f  call    cs:__imp_GetLastError
0x180022b85  mov     ebx, eax
0x180022b87  test    eax, eax
0x180022b89  jle     short loc_180022B94
0x180022b8b  movzx   ebx, ax
0x180022b8e  or      ebx, 80070000h
0x180022b94  mov     rcx, r12; pv
0x180022b97  call    cs:__imp_CoTaskMemFree
0x180022b9d  test    ebx, ebx
0x180022b9f  jns     short loc_180022BD8
0x180022ba1  lea     rax, aIslocaldtcserv_0; "IsLocalDTCServiceEnabled returned an er"...
0x180022ba8  mov     r9d, 235h
0x180022bae  mov     [rsp+180h+var_150], rax
0x180022bb3  mov     r8, rdi
0x180022bb6  mov     dword ptr [rsp+180h+var_158], ebx
0x180022bba  mov     edx, 1
0x180022bbf  mov     ecx, esi
0x180022bc1  mov     [rsp+180h+var_160], r14
0x180022bc6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022bcb  mov     r12, [rsp+180h+var_128]
0x180022bd0  mov     r13, r12
0x180022bd3  jmp     loc_180022A44
0x180022bd8  test    r15d, r15d
0x180022bdb  jz      short loc_180022BE6
0x180022bdd  movups  xmm6, cs:LOCAL_DTC_TM_RESOURCE_ID
0x180022be4  jmp     short loc_180022C26
0x180022be6  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180022bed  jmp     short loc_180022C26
0x180022bef  cmp     dword ptr [r15+8], 1
0x180022bf4  jnz     short loc_180022C26
0x180022bf6  lea     rax, aConfigargsVers; "ConfigArgs version >= OLE_TM_CONFIG_VER"...
0x180022bfd  mov     r9d, 246h
0x180022c03  mov     [rsp+180h+var_150], rax
0x180022c08  mov     r8, rdi
0x180022c0b  mov     [rsp+180h+var_158], rbx
0x180022c10  mov     edx, 4
0x180022c15  mov     ecx, esi
0x180022c17  mov     [rsp+180h+var_160], r14
0x180022c1c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022c21  movups  xmm6, xmmword ptr [r15+0Ch]
0x180022c26  mov     rbx, [rbp+80h+pv]
0x180022c2a  xor     r15d, r15d
0x180022c2d  test    rbx, rbx
0x180022c30  jnz     short loc_180022C3F
0x180022c32  lea     rcx, aConstructmsgto; "ConstructMsgToTm (com\\complus\\dtc\\dt"...
0x180022c39  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180022c3f  mov     [rsp+180h+var_110], r15
0x180022c44  mov     [rsp+180h+var_120], r15d
0x180022c49  call    cs:__imp_GetCurrentProcessId
0x180022c4f  mov     [rsp+180h+pcbBytesNeeded], eax
0x180022c53  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022c57  inc     rcx
0x180022c5a  cmp     [rbx+rcx*2], r15w
0x180022c5f  jnz     short loc_180022C57
0x180022c61  lea     eax, ds:2[rcx*2]
0x180022c68  lea     r12, [rax+3]
0x180022c6c  mov     [rsp+180h+var_108], eax
0x180022c70  shr     r12, 2
0x180022c74  mov     ebx, eax
0x180022c76  lea     r13d, ds:2Ch[r12*4]
0x180022c7e  mov     ecx, r13d; cb
0x180022c81  call    cs:__imp_CoTaskMemAlloc
0x180022c87  xor     r11d, r11d
0x180022c8a  mov     r15, rax
0x180022c8d  test    rax, rax
0x180022c90  jnz     short loc_180022CD8
0x180022c92  mov     ecx, 8007000Eh
0x180022c97  lea     rax, aUnableToAlloca_0; "Unable to allocate memory for message t"...
0x180022c9e  mov     [rsp+180h+var_150], rax
0x180022ca3  mov     ebx, ecx
0x180022ca5  mov     dword ptr [rsp+180h+var_158], ecx
0x180022ca9  mov     r9d, 169h
0x180022caf  lea     rax, aConstructmsgto_2; "ConstructMsgToTm"
0x180022cb6  mov     r13d, 1
0x180022cbc  mov     edx, r13d
0x180022cbf  mov     [rsp+180h+var_160], rax
0x180022cc4  mov     r8, rdi
0x180022cc7  mov     ecx, esi
0x180022cc9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022cce  mov     r12d, [rsp+180h+var_120]
0x180022cd3  jmp     loc_180022D61
0x180022cd8  mov     eax, dword ptr [rsp+180h+cb]
0x180022cdc  lea     ecx, ds:4[r12*4]
0x180022ce4  movaps  xmm0, [rbp+80h+Buf2]
0x180022ce8  mov     [r15], eax
0x180022ceb  mov     eax, [rsp+180h+pcbBytesNeeded]
0x180022cef  mov     [r15+24h], eax
0x180022cf3  mov     eax, [rsp+180h+var_108]
0x180022cf7  movdqu  xmmword ptr [r15+4], xmm6
0x180022cfd  movdqu  xmmword ptr [r15+14h], xmm0
0x180022d03  mov     [r15+28h], eax
0x180022d07  lea     eax, [r13-28h]
0x180022d0b  cmp     ecx, eax
0x180022d0d  jbe     short loc_180022D1C
0x180022d0f  lea     rcx, aConstructmsgto_0; "ConstructMsgToTm (com\\complus\\dtc\\dt"...
0x180022d16  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180022d1c  mov     r8, [rbp+80h+pv]; unsigned __int16 *
0x180022d20  lea     rcx, [r15+2Ch]; unsigned __int16 *
0x180022d24  shr     rbx, 1
0x180022d27  mov     rdx, rbx; unsigned __int64
0x180022d2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022d2f  mov     ebx, eax
0x180022d31  test    eax, eax
0x180022d33  jns     short loc_180022D50
0x180022d35  lea     rax, aStringcchcopyw_1; "StringCchCopyW failed for .EXE into mes"...
0x180022d3c  mov     r9d, 17Eh
0x180022d42  mov     [rsp+180h+var_150], rax
0x180022d47  mov     dword ptr [rsp+180h+var_158], ebx
0x180022d4b  jmp     loc_180022CAF
0x180022d50  mov     [rsp+180h+var_110], r15
0x180022d55  mov     r12d, r13d
0x180022d58  mov     r15, r11
0x180022d5b  mov     r13d, 1
0x180022d61  mov     rcx, r15; pv
0x180022d64  call    cs:__imp_CoTaskMemFree
0x180022d6a  xor     r15d, r15d
0x180022d6d  test    ebx, ebx
0x180022d6f  jns     short loc_180022DA1
0x180022d71  lea     rax, aConstructmsgto_1; "ConstructMsgToTm failed."
0x180022d78  mov     r9d, 255h
0x180022d7e  mov     [rsp+180h+var_150], rax
0x180022d83  mov     r8, rdi
0x180022d86  mov     dword ptr [rsp+180h+var_158], ebx
0x180022d8a  mov     edx, r13d
0x180022d8d  mov     ecx, esi
0x180022d8f  mov     [rsp+180h+var_160], r14
0x180022d94  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022d99  mov     r12, r15
0x180022d9c  jmp     loc_1800234A3
0x180022da1  lea     rdx, [rbp+80h+var_E0]; struct ITmInstance **
0x180022da5  xor     ecx, ecx; unsigned __int16 *
0x180022da7  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x180022dac  mov     ebx, eax
0x180022dae  test    eax, eax
0x180022db0  jns     short loc_180022DC1
0x180022db2  lea     rax, aCreatelocaltmi_2; "CreateLocalTmInstance failed."
0x180022db9  mov     r9d, 266h
0x180022dbf  jmp     short loc_180022D7E
0x180022dc1  mov     rcx, [rbp+80h+var_E0]; struct ITmInstance *
0x180022dc5  lea     rdx, [rbp+80h+var_C0]; struct INameObject **
0x180022dc9  call    ?GetLocalNameObject@@YAJPEAUITmInstance@@PEAPEAUINameObject@@@Z; GetLocalNameObject(ITmInstance *,INameObject * *)
0x180022dce  mov     ebx, eax
0x180022dd0  test    eax, eax
  ... truncated ...
```
