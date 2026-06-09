# MDM_Policy_Config01_Defender02_InvokeGetInstance

- ea: `0x18007c144`
- end: `0x18007ce13`
- name: `MDM_Policy_Config01_Defender02_InvokeGetInstance`
- size: `3279`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a190`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005400`
- `0x180005470`
- `0x1800054e0`
- `0x180005518`
- `0x1800056a0`
- `0x1800057b8`
- `0x1800057f0`
- `0x180005860`
- `0x1800059e8`
- `0x180005a20`
- `0x180005a58`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18007c144`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007c3e3`
- `msvcrt!_wtoi` at `0x18007c420`
- `msvcrt!_wtoi` at `0x18007c45d`
- `msvcrt!_wtoi` at `0x18007c49a`
- `msvcrt!_wtoi` at `0x18007c4d7`
- `msvcrt!_wtoi` at `0x18007c514`
- `msvcrt!_wtoi` at `0x18007c551`
- `msvcrt!_wtoi` at `0x18007c58e`
- `msvcrt!_wtoi` at `0x18007c5cb`
- `msvcrt!_wtoi` at `0x18007c608`
- `msvcrt!_wtoi` at `0x18007c645`
- `msvcrt!_wtoi` at `0x18007c682`
- `msvcrt!_wtoi` at `0x18007c6bf`
- `msvcrt!_wtoi` at `0x18007c75a`
- `msvcrt!_wtoi` at `0x18007c797`
- `msvcrt!_wtoi` at `0x18007c7d4`
- `msvcrt!_wtoi` at `0x18007c811`
- `msvcrt!_wtoi` at `0x18007c8ac`
- `msvcrt!_wtoi` at `0x18007c8e9`
- `msvcrt!_wtoi` at `0x18007c926`
- `msvcrt!_wtoi` at `0x18007c963`
- `msvcrt!_wtoi` at `0x18007c9a0`
- `msvcrt!_wtoi` at `0x18007c9dd`
- `msvcrt!_wtoi` at `0x18007caa7`
- `msvcrt!_wtoi` at `0x18007cae4`
- `msvcrt!_wtoi` at `0x18007cb21`
- `msvcrt!_wtoi` at `0x18007cb5e`
- `msvcrt!_wtoi` at `0x18007cb9b`
- `msvcrt!_wtoi` at `0x18007cbd8`
- `msvcrt!_wtoi` at `0x18007cca2`
- `msvcrt!_wtoi` at `0x18007ccdf`
- `msvcrt!_wtoi` at `0x18007c3e3`
- `msvcrt!_wtoi` at `0x18007c420`
- `msvcrt!_wtoi` at `0x18007c45d`
- `msvcrt!_wtoi` at `0x18007c49a`
- `msvcrt!_wtoi` at `0x18007c4d7`
- `msvcrt!_wtoi` at `0x18007c514`
- `msvcrt!_wtoi` at `0x18007c551`
- `msvcrt!_wtoi` at `0x18007c58e`
- `msvcrt!_wtoi` at `0x18007c5cb`
- `msvcrt!_wtoi` at `0x18007c608`
- `msvcrt!_wtoi` at `0x18007c645`
- `msvcrt!_wtoi` at `0x18007c682`
- `msvcrt!_wtoi` at `0x18007c6bf`
- `msvcrt!_wtoi` at `0x18007c75a`
- `msvcrt!_wtoi` at `0x18007c797`
- `msvcrt!_wtoi` at `0x18007c7d4`
- `msvcrt!_wtoi` at `0x18007c811`
- `msvcrt!_wtoi` at `0x18007c8ac`
- `msvcrt!_wtoi` at `0x18007c8e9`
- `msvcrt!_wtoi` at `0x18007c926`
- `msvcrt!_wtoi` at `0x18007c963`
- `msvcrt!_wtoi` at `0x18007c9a0`
- `msvcrt!_wtoi` at `0x18007c9dd`
- `msvcrt!_wtoi` at `0x18007caa7`
- `msvcrt!_wtoi` at `0x18007cae4`
- `msvcrt!_wtoi` at `0x18007cb21`
- `msvcrt!_wtoi` at `0x18007cb5e`
- `msvcrt!_wtoi` at `0x18007cb9b`
- `msvcrt!_wtoi` at `0x18007cbd8`
- `msvcrt!_wtoi` at `0x18007cca2`
- `msvcrt!_wtoi` at `0x18007ccdf`

## string_xrefs

- `0x18007c5ae`: `AllowOnAccessProtection`
- `0x18007c6a2`: `AllowUserUIAccess`
- `0x18007c831`: `ControlledFolderAccessAllowedApplications`
- `0x18007c860`: `ControlledFolderAccessProtectedFolders`
- `0x18007c946`: `EnableControlledFolderAccess`
- `0x18007c9fd`: `ExcludedExtensions`
- `0x18007ca2c`: `ExcludedPaths`
- `0x18007cbf8`: `SecurityIntelligenceLocation`
- `0x18007cc27`: `SignatureUpdateFallbackOrder`
- `0x18007cc56`: `SignatureUpdateFileSharesSources`
- `0x18007cc85`: `SignatureUpdateInterval`
- `0x18007c1b3`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-2B8h] BYREF
  char v9; // [rsp+48h] [rbp-2B0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-2A8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-2A0h] BYREF
  char v12; // [rsp+80h] [rbp-278h]
  int v13; // [rsp+88h] [rbp-270h] BYREF
  char v14; // [rsp+8Ch] [rbp-26Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-268h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-258h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-248h] BYREF
  int v18; // [rsp+110h] [rbp-1E8h]
  char v19; // [rsp+114h] [rbp-1E4h]
  int v20; // [rsp+118h] [rbp-1E0h]
  char v21; // [rsp+11Ch] [rbp-1DCh]
  int v22; // [rsp+120h] [rbp-1D8h]
  char v23; // [rsp+124h] [rbp-1D4h]
  int v24; // [rsp+128h] [rbp-1D0h]
  char v25; // [rsp+12Ch] [rbp-1CCh]
  int v26; // [rsp+130h] [rbp-1C8h]
  char v27; // [rsp+134h] [rbp-1C4h]
  int v28; // [rsp+138h] [rbp-1C0h]
  char v29; // [rsp+13Ch] [rbp-1BCh]
  int v30; // [rsp+140h] [rbp-1B8h]
  char v31; // [rsp+144h] [rbp-1B4h]
  int v32; // [rsp+148h] [rbp-1B0h]
  char v33; // [rsp+14Ch] [rbp-1ACh]
  int v34; // [rsp+150h] [rbp-1A8h]
  char v35; // [rsp+154h] [rbp-1A4h]
  int v36; // [rsp+158h] [rbp-1A0h]
  char v37; // [rsp+15Ch] [rbp-19Ch]
  int v38; // [rsp+160h] [rbp-198h]
  char v39; // [rsp+164h] [rbp-194h]
  int v40; // [rsp+168h] [rbp-190h]
  char v41; // [rsp+16Ch] [rbp-18Ch]
  int v42; // [rsp+170h] [rbp-188h]
  char v43; // [rsp+174h] [rbp-184h]
  int v44; // [rsp+198h] [rbp-160h]
  char v45; // [rsp+19Ch] [rbp-15Ch]
  int v46; // [rsp+1A0h] [rbp-158h]
  char v47; // [rsp+1A4h] [rbp-154h]
  int v48; // [rsp+1A8h] [rbp-150h]
  char v49; // [rsp+1ACh] [rbp-14Ch]
  int v50; // [rsp+1B0h] [rbp-148h]
  char v51; // [rsp+1B4h] [rbp-144h]
  int v52; // [rsp+1D8h] [rbp-120h]
  char v53; // [rsp+1DCh] [rbp-11Ch]
  int v54; // [rsp+1E0h] [rbp-118h]
  char v55; // [rsp+1E4h] [rbp-114h]
  int v56; // [rsp+1E8h] [rbp-110h]
  char v57; // [rsp+1ECh] [rbp-10Ch]
  int v58; // [rsp+1F0h] [rbp-108h]
  char v59; // [rsp+1F4h] [rbp-104h]
  int v60; // [rsp+1F8h] [rbp-100h]
  char v61; // [rsp+1FCh] [rbp-FCh]
  int v62; // [rsp+200h] [rbp-F8h]
  char v63; // [rsp+204h] [rbp-F4h]
  int v64; // [rsp+238h] [rbp-C0h]
  char v65; // [rsp+23Ch] [rbp-BCh]
  int v66; // [rsp+240h] [rbp-B8h]
  char v67; // [rsp+244h] [rbp-B4h]
  int v68; // [rsp+248h] [rbp-B0h]
  char v69; // [rsp+24Ch] [rbp-ACh]
  int v70; // [rsp+250h] [rbp-A8h]
  char v71; // [rsp+254h] [rbp-A4h]
  int v72; // [rsp+258h] [rbp-A0h]
  char v73; // [rsp+25Ch] [rbp-9Ch]
  int v74; // [rsp+260h] [rbp-98h]
  char v75; // [rsp+264h] [rbp-94h]
  int v76; // [rsp+298h] [rbp-60h]
  char v77; // [rsp+29Ch] [rbp-5Ch]
  int v78; // [rsp+2A0h] [rbp-58h]
  char v79; // [rsp+2A4h] [rbp-54h]

  String = 0;
  memset_0(&instance, 0, 0x208u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180358950,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_155;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_Defender02_NodeList,
                       44,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_155;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
      0x2Cu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_155;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_155;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_155;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Defender02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_155;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowArchiveScanning", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowBehaviorMonitoring", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowCloudProtection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowEmailScanning", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowFullScanOnMappedNetworkDrives",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowFullScanRemovableDriveScanning",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowIntrusionPreventionSystem",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowIOAVProtection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowOnAccessProtection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowRealtimeMonitoring", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowScanningNetworkFiles", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowScriptScanning", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowUserUIAccess", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AttackSurfaceReductionOnlyExclusions",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AttackSurfaceReductionRules",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AvgCPULoadFactor", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"CheckForSignaturesBeforeRunningScan",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"CloudBlockLevel", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"CloudExtendedTimeout", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ControlledFolderAccessAllowedApplications",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ControlledFolderAccessProtectedFolders",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DaysToRetainCleanedMalware", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableCatchupFullScan", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableCatchupQuickScan", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"EnableControlledFolderAccess",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableLowCPUPriority", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableNetworkProtection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ExcludedExtensions", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ExcludedPaths", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ExcludedProcesses", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"PUAProtection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"RealTimeScanDirection", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ScanParameter", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ScheduleQuickScanTime", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ScheduleScanDay", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v72 = _wtoi(String);
      v73 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ScheduleScanTime", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v74 = _wtoi(String);
      v75 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"SecurityIntelligenceLocation",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"SignatureUpdateFallbackOrder",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"SignatureUpdateFileSharesSources",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"SignatureUpdateInterval", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v76 = _wtoi(String);
      v77 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"SubmitSamplesConsent", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v78 = _wtoi(String);
      v79 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ThreatSeverityDefaultAction",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableFeedsBackgroundSync(&instance);
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_155:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033EA85,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007c144  mov     [rsp+arg_10], rbx
0x18007c149  push    rsi
0x18007c14a  push    rdi
0x18007c14b  push    r12
0x18007c14d  push    r14
0x18007c14f  push    r15
0x18007c151  sub     rsp, 2D0h
0x18007c158  mov     rax, cs:__security_cookie
0x18007c15f  xor     rax, rsp
0x18007c162  mov     [rsp+2F8h+var_38], rax
0x18007c16a  mov     rsi, rdx
0x18007c16d  mov     r15, rcx
0x18007c170  xor     ebx, ebx
0x18007c172  mov     [rsp+2F8h+String], rbx
0x18007c177  xor     edx, edx; Val
0x18007c179  mov     r8d, 208h; Size
0x18007c17f  lea     rcx, [rsp+2F8h+instance]; void *
0x18007c187  call    memset_0
0x18007c18c  mov     [rsp+2F8h+var_270], ebx
0x18007c193  mov     [rsp+2F8h+var_26C], bl
0x18007c19a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007c1a1  mov     [rsp+2F8h+var_2A0], rax
0x18007c1a6  lea     rax, [rsp+2F8h+var_270]
0x18007c1ae  mov     [rsp+2F8h+var_298], rax
0x18007c1b3  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007c1ba  mov     [rsp+2F8h+var_290], rax
0x18007c1bf  lea     rcx, [rsp+2F8h+var_270]
0x18007c1c7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007c1cc  mov     eax, cs:dword_180380B68
0x18007c1d2  cmp     eax, 5
0x18007c1d5  jbe     short loc_18007C246
0x18007c1d7  mov     rdx, 200000000000h
0x18007c1e1  lea     rcx, dword_180380B68
0x18007c1e8  call    _tlgKeywordOn
0x18007c1ed  test    al, al
0x18007c1ef  jz      short loc_18007C246
0x18007c1f1  cmp     [rsp+2F8h+var_26C], bl
0x18007c1f8  jz      short loc_18007C228
0x18007c1fa  cmp     [rsp+2F8h+var_258], ebx
0x18007c201  jnz     short loc_18007C21E
0x18007c203  cmp     [rsp+2F8h+var_254], ebx
0x18007c20a  jnz     short loc_18007C21E
0x18007c20c  cmp     [rsp+2F8h+var_250], ebx
0x18007c213  jnz     short loc_18007C21E
0x18007c215  cmp     [rsp+2F8h+var_24C], ebx
0x18007c21c  jz      short loc_18007C228
0x18007c21e  lea     r9, [rsp+2F8h+var_258]
0x18007c226  jmp     short loc_18007C22B
0x18007c228  mov     r9, rbx
0x18007c22b  lea     r8, [rsp+2F8h+var_268]
0x18007c233  lea     rdx, qword_180358950
0x18007c23a  lea     rcx, dword_180380B68
0x18007c241  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007c246  cmp     [rsi+48h], bl
0x18007c249  jz      loc_18007CD71
0x18007c24f  mov     [rsp+2F8h+var_2B0], bl
0x18007c253  cmp     [rsi+58h], bl
0x18007c256  jz      loc_18007CD71
0x18007c25c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007c260  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007c264  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18007c26b  lea     rcx, [rsp+2F8h+var_2A0]; this
0x18007c270  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007c275  nop
0x18007c276  mov     [rsp+2F8h+var_2A8], rbx
0x18007c27b  lea     rax, [rsp+2F8h+var_2A8]
0x18007c280  mov     [rsp+2F8h+var_2C8], rax
0x18007c285  mov     [rsp+2F8h+var_2D0], ebx
0x18007c289  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x18007c291  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007c298  mov     r8, [rsi+40h]
0x18007c29c  mov     rdx, [rsi+50h]
0x18007c2a0  mov     rcx, r15
0x18007c2a3  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007c2a8  mov     r14d, eax
0x18007c2ab  test    eax, eax
0x18007c2ad  jz      short loc_18007C2B4
0x18007c2af  jmp     loc_18007CD77
0x18007c2b4  lea     rax, [rsp+2F8h+var_2A8]
0x18007c2b9  mov     [rsp+2F8h+var_280], rax
0x18007c2be  mov     r12d, 1
0x18007c2c4  mov     [rsp+2F8h+var_278], r12b
0x18007c2cc  mov     rdi, [rsp+2F8h+var_2A8]
0x18007c2d1  test    rdi, rdi
0x18007c2d4  jnz     short loc_18007C2DE
0x18007c2d6  mov     r14d, r12d
0x18007c2d9  jmp     loc_18007CD77
0x18007c2de  mov     r9d, 2Ch ; ','; unsigned int
0x18007c2e4  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007c2eb  mov     rdx, rsi; struct _MI_Instance *
0x18007c2ee  mov     rcx, rdi; this
0x18007c2f1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007c2f6  mov     rax, [rdi]
0x18007c2f9  mov     rcx, rdi
0x18007c2fc  mov     rax, [rax+10h]
0x18007c300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c305  mov     r14d, eax
0x18007c308  test    eax, eax
0x18007c30a  jz      short loc_18007C32A
0x18007c30c  mov     rcx, [rsp+2F8h+var_2A8]
0x18007c311  test    rcx, rcx
0x18007c314  jz      short loc_18007C325
0x18007c316  mov     rax, [rcx]
0x18007c319  mov     edx, r12d
0x18007c31c  mov     rax, [rax]
0x18007c31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c324  nop
0x18007c325  jmp     loc_18007CD77
0x18007c32a  mov     rax, [rdi]
0x18007c32d  mov     rcx, rdi
0x18007c330  mov     rax, [rax+8]
0x18007c334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c339  mov     r14d, eax
0x18007c33c  test    eax, eax
0x18007c33e  jz      short loc_18007C35E
0x18007c340  mov     rcx, [rsp+2F8h+var_2A8]
0x18007c345  test    rcx, rcx
0x18007c348  jz      short loc_18007C359
0x18007c34a  mov     rax, [rcx]
0x18007c34d  mov     edx, r12d
0x18007c350  mov     rax, [rax]
0x18007c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c358  nop
0x18007c359  jmp     loc_18007CD77
0x18007c35e  lea     r8, [rsp+2F8h+instance]; instance
0x18007c366  lea     rdx, MDM_Policy_Config01_Defender02_rtti; classDecl
0x18007c36d  mov     rcx, r15; context
0x18007c370  call    MI_Context_ConstructInstance
0x18007c375  mov     r14d, eax
0x18007c378  test    eax, eax
0x18007c37a  jz      short loc_18007C39A
0x18007c37c  mov     rcx, [rsp+2F8h+var_2A8]
0x18007c381  test    rcx, rcx
0x18007c384  jz      short loc_18007C395
0x18007c386  mov     rax, [rcx]
0x18007c389  mov     edx, r12d
0x18007c38c  mov     rax, [rax]
0x18007c38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c394  nop
0x18007c395  jmp     loc_18007CD77
0x18007c39a  mov     [rsp+2F8h+var_2B0], r12b
0x18007c39f  mov     rdx, [rsi+40h]
0x18007c3a3  lea     rcx, [rsp+2F8h+instance]
0x18007c3ab  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007c3b0  mov     rdx, [rsi+50h]
0x18007c3b4  lea     rcx, [rsp+2F8h+instance]
0x18007c3bc  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007c3c1  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c3c6  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007c3cd  mov     rcx, rdi; this
0x18007c3d0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c3d5  test    eax, eax
0x18007c3d7  jnz     short loc_18007C3FE
0x18007c3d9  mov     rcx, [rsp+2F8h+String]; String
0x18007c3de  test    rcx, rcx
0x18007c3e1  jz      short loc_18007C3FE
0x18007c3e3  call    cs:__imp__wtoi
0x18007c3ea  nop     dword ptr [rax+rax+00h]
0x18007c3ef  mov     [rsp+2F8h+var_1E8], eax
0x18007c3f6  mov     [rsp+2F8h+var_1E4], r12b
0x18007c3fe  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c403  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007c40a  mov     rcx, rdi; this
0x18007c40d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c412  test    eax, eax
0x18007c414  jnz     short loc_18007C43B
0x18007c416  mov     rcx, [rsp+2F8h+String]; String
0x18007c41b  test    rcx, rcx
0x18007c41e  jz      short loc_18007C43B
0x18007c420  call    cs:__imp__wtoi
0x18007c427  nop     dword ptr [rax+rax+00h]
0x18007c42c  mov     [rsp+2F8h+var_1E0], eax
0x18007c433  mov     [rsp+2F8h+var_1DC], r12b
0x18007c43b  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c440  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007c447  mov     rcx, rdi; this
0x18007c44a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c44f  test    eax, eax
0x18007c451  jnz     short loc_18007C478
0x18007c453  mov     rcx, [rsp+2F8h+String]; String
0x18007c458  test    rcx, rcx
0x18007c45b  jz      short loc_18007C478
0x18007c45d  call    cs:__imp__wtoi
0x18007c464  nop     dword ptr [rax+rax+00h]
0x18007c469  mov     [rsp+2F8h+var_1D8], eax
0x18007c470  mov     [rsp+2F8h+var_1D4], r12b
0x18007c478  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c47d  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007c484  mov     rcx, rdi; this
0x18007c487  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c48c  test    eax, eax
0x18007c48e  jnz     short loc_18007C4B5
0x18007c490  mov     rcx, [rsp+2F8h+String]; String
0x18007c495  test    rcx, rcx
0x18007c498  jz      short loc_18007C4B5
0x18007c49a  call    cs:__imp__wtoi
0x18007c4a1  nop     dword ptr [rax+rax+00h]
0x18007c4a6  mov     [rsp+2F8h+var_1D0], eax
0x18007c4ad  mov     [rsp+2F8h+var_1CC], r12b
0x18007c4b5  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c4ba  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007c4c1  mov     rcx, rdi; this
0x18007c4c4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c4c9  test    eax, eax
0x18007c4cb  jnz     short loc_18007C4F2
0x18007c4cd  mov     rcx, [rsp+2F8h+String]; String
0x18007c4d2  test    rcx, rcx
0x18007c4d5  jz      short loc_18007C4F2
0x18007c4d7  call    cs:__imp__wtoi
0x18007c4de  nop     dword ptr [rax+rax+00h]
0x18007c4e3  mov     [rsp+2F8h+var_1C8], eax
0x18007c4ea  mov     [rsp+2F8h+var_1C4], r12b
0x18007c4f2  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c4f7  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007c4fe  mov     rcx, rdi; this
0x18007c501  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c506  test    eax, eax
0x18007c508  jnz     short loc_18007C52F
0x18007c50a  mov     rcx, [rsp+2F8h+String]; String
0x18007c50f  test    rcx, rcx
0x18007c512  jz      short loc_18007C52F
0x18007c514  call    cs:__imp__wtoi
0x18007c51b  nop     dword ptr [rax+rax+00h]
0x18007c520  mov     [rsp+2F8h+var_1C0], eax
0x18007c527  mov     [rsp+2F8h+var_1BC], r12b
0x18007c52f  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c534  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007c53b  mov     rcx, rdi; this
0x18007c53e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c543  test    eax, eax
0x18007c545  jnz     short loc_18007C56C
0x18007c547  mov     rcx, [rsp+2F8h+String]; String
0x18007c54c  test    rcx, rcx
0x18007c54f  jz      short loc_18007C56C
0x18007c551  call    cs:__imp__wtoi
0x18007c558  nop     dword ptr [rax+rax+00h]
0x18007c55d  mov     [rsp+2F8h+var_1B8], eax
0x18007c564  mov     [rsp+2F8h+var_1B4], r12b
0x18007c56c  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c571  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007c578  mov     rcx, rdi; this
0x18007c57b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c580  test    eax, eax
0x18007c582  jnz     short loc_18007C5A9
0x18007c584  mov     rcx, [rsp+2F8h+String]; String
0x18007c589  test    rcx, rcx
0x18007c58c  jz      short loc_18007C5A9
0x18007c58e  call    cs:__imp__wtoi
0x18007c595  nop     dword ptr [rax+rax+00h]
0x18007c59a  mov     [rsp+2F8h+var_1B0], eax
0x18007c5a1  mov     [rsp+2F8h+var_1AC], r12b
0x18007c5a9  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c5ae  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007c5b5  mov     rcx, rdi; this
0x18007c5b8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c5bd  test    eax, eax
0x18007c5bf  jnz     short loc_18007C5E6
0x18007c5c1  mov     rcx, [rsp+2F8h+String]; String
0x18007c5c6  test    rcx, rcx
0x18007c5c9  jz      short loc_18007C5E6
0x18007c5cb  call    cs:__imp__wtoi
0x18007c5d2  nop     dword ptr [rax+rax+00h]
0x18007c5d7  mov     [rsp+2F8h+var_1A8], eax
0x18007c5de  mov     [rsp+2F8h+var_1A4], r12b
0x18007c5e6  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c5eb  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007c5f2  mov     rcx, rdi; this
0x18007c5f5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c5fa  test    eax, eax
0x18007c5fc  jnz     short loc_18007C623
0x18007c5fe  mov     rcx, [rsp+2F8h+String]; String
0x18007c603  test    rcx, rcx
0x18007c606  jz      short loc_18007C623
0x18007c608  call    cs:__imp__wtoi
0x18007c60f  nop     dword ptr [rax+rax+00h]
0x18007c614  mov     [rsp+2F8h+var_1A0], eax
0x18007c61b  mov     [rsp+2F8h+var_19C], r12b
0x18007c623  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c628  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007c62f  mov     rcx, rdi; this
0x18007c632  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c637  test    eax, eax
0x18007c639  jnz     short loc_18007C660
0x18007c63b  mov     rcx, [rsp+2F8h+String]; String
0x18007c640  test    rcx, rcx
0x18007c643  jz      short loc_18007C660
0x18007c645  call    cs:__imp__wtoi
0x18007c64c  nop     dword ptr [rax+rax+00h]
0x18007c651  mov     [rsp+2F8h+var_198], eax
0x18007c658  mov     [rsp+2F8h+var_194], r12b
0x18007c660  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007c665  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007c66c  mov     rcx, rdi; this
0x18007c66f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007c674  test    eax, eax
0x18007c676  jnz     short loc_18007C69D
0x18007c678  mov     rcx, [rsp+2F8h+String]; String
0x18007c67d  test    rcx, rcx
0x18007c680  jz      short loc_18007C69D
0x18007c682  call    cs:__imp__wtoi
  ... truncated ...
```
