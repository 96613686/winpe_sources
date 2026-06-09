# MDM_Policy_Config01_Defender02_InvokeGetInstance

- ea: `0x18007c8f4`
- end: `0x18007d508`
- name: `MDM_Policy_Config01_Defender02_InvokeGetInstance`
- size: `3092`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a9f0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000522c`
- `0x18000529c`
- `0x18000530c`
- `0x180005344`
- `0x1800054cc`
- `0x1800055e4`
- `0x18000561c`
- `0x18000568c`
- `0x180005814`
- `0x18000584c`
- `0x180005884`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18007c8f4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007cb93`
- `msvcrt!_wtoi` at `0x18007cbca`
- `msvcrt!_wtoi` at `0x18007cc01`
- `msvcrt!_wtoi` at `0x18007cc38`
- `msvcrt!_wtoi` at `0x18007cc6f`
- `msvcrt!_wtoi` at `0x18007cca6`
- `msvcrt!_wtoi` at `0x18007ccdd`
- `msvcrt!_wtoi` at `0x18007cd14`
- `msvcrt!_wtoi` at `0x18007cd4b`
- `msvcrt!_wtoi` at `0x18007cd82`
- `msvcrt!_wtoi` at `0x18007cdb9`
- `msvcrt!_wtoi` at `0x18007cdf0`
- `msvcrt!_wtoi` at `0x18007ce27`
- `msvcrt!_wtoi` at `0x18007cebc`
- `msvcrt!_wtoi` at `0x18007cef3`
- `msvcrt!_wtoi` at `0x18007cf2a`
- `msvcrt!_wtoi` at `0x18007cf61`
- `msvcrt!_wtoi` at `0x18007cff6`
- `msvcrt!_wtoi` at `0x18007d02d`
- `msvcrt!_wtoi` at `0x18007d064`
- `msvcrt!_wtoi` at `0x18007d09b`
- `msvcrt!_wtoi` at `0x18007d0d2`
- `msvcrt!_wtoi` at `0x18007d109`
- `msvcrt!_wtoi` at `0x18007d1cd`
- `msvcrt!_wtoi` at `0x18007d204`
- `msvcrt!_wtoi` at `0x18007d23b`
- `msvcrt!_wtoi` at `0x18007d272`
- `msvcrt!_wtoi` at `0x18007d2a9`
- `msvcrt!_wtoi` at `0x18007d2e0`
- `msvcrt!_wtoi` at `0x18007d3a4`
- `msvcrt!_wtoi` at `0x18007d3db`
- `msvcrt!_wtoi` at `0x18007cb93`
- `msvcrt!_wtoi` at `0x18007cbca`
- `msvcrt!_wtoi` at `0x18007cc01`
- `msvcrt!_wtoi` at `0x18007cc38`
- `msvcrt!_wtoi` at `0x18007cc6f`
- `msvcrt!_wtoi` at `0x18007cca6`
- `msvcrt!_wtoi` at `0x18007ccdd`
- `msvcrt!_wtoi` at `0x18007cd14`
- `msvcrt!_wtoi` at `0x18007cd4b`
- `msvcrt!_wtoi` at `0x18007cd82`
- `msvcrt!_wtoi` at `0x18007cdb9`
- `msvcrt!_wtoi` at `0x18007cdf0`
- `msvcrt!_wtoi` at `0x18007ce27`
- `msvcrt!_wtoi` at `0x18007cebc`
- `msvcrt!_wtoi` at `0x18007cef3`
- `msvcrt!_wtoi` at `0x18007cf2a`
- `msvcrt!_wtoi` at `0x18007cf61`
- `msvcrt!_wtoi` at `0x18007cff6`
- `msvcrt!_wtoi` at `0x18007d02d`
- `msvcrt!_wtoi` at `0x18007d064`
- `msvcrt!_wtoi` at `0x18007d09b`
- `msvcrt!_wtoi` at `0x18007d0d2`
- `msvcrt!_wtoi` at `0x18007d109`
- `msvcrt!_wtoi` at `0x18007d1cd`
- `msvcrt!_wtoi` at `0x18007d204`
- `msvcrt!_wtoi` at `0x18007d23b`
- `msvcrt!_wtoi` at `0x18007d272`
- `msvcrt!_wtoi` at `0x18007d2a9`
- `msvcrt!_wtoi` at `0x18007d2e0`
- `msvcrt!_wtoi` at `0x18007d3a4`
- `msvcrt!_wtoi` at `0x18007d3db`

## string_xrefs

- `0x18007cd2e`: `AllowOnAccessProtection`
- `0x18007ce0a`: `AllowUserUIAccess`
- `0x18007cf7b`: `ControlledFolderAccessAllowedApplications`
- `0x18007cfaa`: `ControlledFolderAccessProtectedFolders`
- `0x18007d07e`: `EnableControlledFolderAccess`
- `0x18007d123`: `ExcludedExtensions`
- `0x18007d152`: `ExcludedPaths`
- `0x18007d2fa`: `SecurityIntelligenceLocation`
- `0x18007d329`: `SignatureUpdateFallbackOrder`
- `0x18007d358`: `SignatureUpdateFileSharesSources`
- `0x18007d387`: `SignatureUpdateInterval`
- `0x18007c963`: `MDM_Policy_Config01_Defender02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Defender02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_155;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = CreateRequestHandlerInstance(
         (__int64)self,
         (wchar_t *)a2[1].serverName,
         (const unsigned __int16 *)a2[1].ft,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
         0x2Cu,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_155;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Defender02_NodeList,
      0x2Cu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_155;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_155;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowArchiveScanning",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowBehaviorMonitoring",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowCloudProtection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowEmailScanning",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowFullScanOnMappedNetworkDrives",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowFullScanRemovableDriveScanning",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowIntrusionPreventionSystem",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowIOAVProtection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowOnAccessProtection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowRealtimeMonitoring",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowScanningNetworkFiles",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowScriptScanning",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowUserUIAccess",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AttackSurfaceReductionOnlyExclusions",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AttackSurfaceReductionRules",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AvgCPULoadFactor",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CheckForSignaturesBeforeRunningScan",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CloudBlockLevel",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"CloudExtendedTimeout",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ControlledFolderAccessAllowedApplications",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowOneWordEntry(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ControlledFolderAccessProtectedFolders",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DaysToRetainCleanedMalware",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisableCatchupFullScan",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisableCatchupQuickScan",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnableControlledFolderAccess",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnableLowCPUPriority",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnableNetworkProtection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludedExtensions",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludedPaths",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludedProcesses",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_ConfigureEdgeRedirectChannel(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PUAProtection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"RealTimeScanDirection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScanParameter",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScheduleQuickScanTime",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScheduleScanDay",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v72 = _wtoi(String);
      v73 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScheduleScanTime",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v74 = _wtoi(String);
      v75 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"SecurityIntelligenceLocation",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCrashDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"SignatureUpdateFallbackOrder",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableCustomerExperienceImprovementProgramParticipation(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"SignatureUpdateFileSharesSources",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_DisableDeletingUserVisitedWebsites(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"SignatureUpdateInterval",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v76 = _wtoi(String);
      v77 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"SubmitSamplesConsent",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v78 = _wtoi(String);
      v79 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ThreatSeverityDefaultAction",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x18007c8f4  mov     [rsp+arg_10], rbx
0x18007c8f9  push    rsi
0x18007c8fa  push    rdi
0x18007c8fb  push    r12
0x18007c8fd  push    r14
0x18007c8ff  push    r15
0x18007c901  sub     rsp, 2D0h
0x18007c908  mov     rax, cs:__security_cookie
0x18007c90f  xor     rax, rsp
0x18007c912  mov     [rsp+2F8h+var_38], rax
0x18007c91a  mov     rsi, rdx
0x18007c91d  mov     r15, rcx
0x18007c920  xor     ebx, ebx
0x18007c922  mov     [rsp+2F8h+String], rbx
0x18007c927  xor     edx, edx; Val
0x18007c929  mov     r8d, 208h; Size
0x18007c92f  lea     rcx, [rsp+2F8h+instance]; void *
0x18007c937  call    memset_0
0x18007c93c  mov     [rsp+2F8h+var_270], ebx
0x18007c943  mov     [rsp+2F8h+var_26C], bl
0x18007c94a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007c951  mov     [rsp+2F8h+var_2A0], rax
0x18007c956  lea     rax, [rsp+2F8h+var_270]
0x18007c95e  mov     [rsp+2F8h+var_298], rax
0x18007c963  lea     rax, aMdmPolicyConfi_40; "MDM_Policy_Config01_Defender02"
0x18007c96a  mov     [rsp+2F8h+var_290], rax
0x18007c96f  lea     rcx, [rsp+2F8h+var_270]
0x18007c977  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007c97c  mov     eax, cs:dword_180380B68
0x18007c982  cmp     eax, 5
0x18007c985  jbe     short loc_18007C9F6
0x18007c987  mov     rdx, 200000000000h
0x18007c991  lea     rcx, dword_180380B68
0x18007c998  call    _tlgKeywordOn
0x18007c99d  test    al, al
0x18007c99f  jz      short loc_18007C9F6
0x18007c9a1  cmp     [rsp+2F8h+var_26C], bl
0x18007c9a8  jz      short loc_18007C9D8
0x18007c9aa  cmp     [rsp+2F8h+var_258], ebx
0x18007c9b1  jnz     short loc_18007C9CE
0x18007c9b3  cmp     [rsp+2F8h+var_254], ebx
0x18007c9ba  jnz     short loc_18007C9CE
0x18007c9bc  cmp     [rsp+2F8h+var_250], ebx
0x18007c9c3  jnz     short loc_18007C9CE
0x18007c9c5  cmp     [rsp+2F8h+var_24C], ebx
0x18007c9cc  jz      short loc_18007C9D8
0x18007c9ce  lea     r9, [rsp+2F8h+var_258]
0x18007c9d6  jmp     short loc_18007C9DB
0x18007c9d8  mov     r9, rbx
0x18007c9db  lea     r8, [rsp+2F8h+var_268]
0x18007c9e3  lea     rdx, qword_180358950
0x18007c9ea  lea     rcx, dword_180380B68
0x18007c9f1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007c9f6  cmp     [rsi+48h], bl
0x18007c9f9  jz      loc_18007D467
0x18007c9ff  mov     [rsp+2F8h+var_2B0], bl
0x18007ca03  cmp     [rsi+58h], bl
0x18007ca06  jz      loc_18007D467
0x18007ca0c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18007ca10  mov     r8, [rsi+50h]; unsigned __int16 *
0x18007ca14  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18007ca1b  lea     rcx, [rsp+2F8h+var_2A0]; this
0x18007ca20  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18007ca25  nop
0x18007ca26  mov     [rsp+2F8h+var_2A8], rbx
0x18007ca2b  lea     rax, [rsp+2F8h+var_2A8]
0x18007ca30  mov     [rsp+2F8h+var_2C8], rax
0x18007ca35  mov     [rsp+2F8h+var_2D0], ebx
0x18007ca39  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x18007ca41  lea     r9, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Defender02_NodeList
0x18007ca48  mov     r8, [rsi+40h]
0x18007ca4c  mov     rdx, [rsi+50h]
0x18007ca50  mov     rcx, r15
0x18007ca53  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18007ca58  mov     r14d, eax
0x18007ca5b  test    eax, eax
0x18007ca5d  jz      short loc_18007CA64
0x18007ca5f  jmp     loc_18007D46D
0x18007ca64  lea     rax, [rsp+2F8h+var_2A8]
0x18007ca69  mov     [rsp+2F8h+var_280], rax
0x18007ca6e  mov     r12d, 1
0x18007ca74  mov     [rsp+2F8h+var_278], r12b
0x18007ca7c  mov     rdi, [rsp+2F8h+var_2A8]
0x18007ca81  test    rdi, rdi
0x18007ca84  jnz     short loc_18007CA8E
0x18007ca86  mov     r14d, r12d
0x18007ca89  jmp     loc_18007D46D
0x18007ca8e  mov     r9d, 2Ch ; ','; unsigned int
0x18007ca94  lea     r8, ?MDM_Policy_Config01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18007ca9b  mov     rdx, rsi; struct _MI_Instance *
0x18007ca9e  mov     rcx, rdi; this
0x18007caa1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007caa6  mov     rax, [rdi]
0x18007caa9  mov     rcx, rdi
0x18007caac  mov     rax, [rax+10h]
0x18007cab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cab5  mov     r14d, eax
0x18007cab8  test    eax, eax
0x18007caba  jz      short loc_18007CADA
0x18007cabc  mov     rcx, [rsp+2F8h+var_2A8]
0x18007cac1  test    rcx, rcx
0x18007cac4  jz      short loc_18007CAD5
0x18007cac6  mov     rax, [rcx]
0x18007cac9  mov     edx, r12d
0x18007cacc  mov     rax, [rax]
0x18007cacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cad4  nop
0x18007cad5  jmp     loc_18007D46D
0x18007cada  mov     rax, [rdi]
0x18007cadd  mov     rcx, rdi
0x18007cae0  mov     rax, [rax+8]
0x18007cae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cae9  mov     r14d, eax
0x18007caec  test    eax, eax
0x18007caee  jz      short loc_18007CB0E
0x18007caf0  mov     rcx, [rsp+2F8h+var_2A8]
0x18007caf5  test    rcx, rcx
0x18007caf8  jz      short loc_18007CB09
0x18007cafa  mov     rax, [rcx]
0x18007cafd  mov     edx, r12d
0x18007cb00  mov     rax, [rax]
0x18007cb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb08  nop
0x18007cb09  jmp     loc_18007D46D
0x18007cb0e  lea     r8, [rsp+2F8h+instance]; instance
0x18007cb16  lea     rdx, MDM_Policy_Config01_Defender02_rtti; classDecl
0x18007cb1d  mov     rcx, r15; context
0x18007cb20  call    MI_Context_ConstructInstance
0x18007cb25  mov     r14d, eax
0x18007cb28  test    eax, eax
0x18007cb2a  jz      short loc_18007CB4A
0x18007cb2c  mov     rcx, [rsp+2F8h+var_2A8]
0x18007cb31  test    rcx, rcx
0x18007cb34  jz      short loc_18007CB45
0x18007cb36  mov     rax, [rcx]
0x18007cb39  mov     edx, r12d
0x18007cb3c  mov     rax, [rax]
0x18007cb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb44  nop
0x18007cb45  jmp     loc_18007D46D
0x18007cb4a  mov     [rsp+2F8h+var_2B0], r12b
0x18007cb4f  mov     rdx, [rsi+40h]
0x18007cb53  lea     rcx, [rsp+2F8h+instance]
0x18007cb5b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18007cb60  mov     rdx, [rsi+50h]
0x18007cb64  lea     rcx, [rsp+2F8h+instance]
0x18007cb6c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18007cb71  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cb76  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x18007cb7d  mov     rcx, rdi; this
0x18007cb80  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cb85  test    eax, eax
0x18007cb87  jnz     short loc_18007CBA8
0x18007cb89  mov     rcx, [rsp+2F8h+String]; String
0x18007cb8e  test    rcx, rcx
0x18007cb91  jz      short loc_18007CBA8
0x18007cb93  call    cs:__imp__wtoi
0x18007cb99  mov     [rsp+2F8h+var_1E8], eax
0x18007cba0  mov     [rsp+2F8h+var_1E4], r12b
0x18007cba8  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cbad  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x18007cbb4  mov     rcx, rdi; this
0x18007cbb7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cbbc  test    eax, eax
0x18007cbbe  jnz     short loc_18007CBDF
0x18007cbc0  mov     rcx, [rsp+2F8h+String]; String
0x18007cbc5  test    rcx, rcx
0x18007cbc8  jz      short loc_18007CBDF
0x18007cbca  call    cs:__imp__wtoi
0x18007cbd0  mov     [rsp+2F8h+var_1E0], eax
0x18007cbd7  mov     [rsp+2F8h+var_1DC], r12b
0x18007cbdf  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cbe4  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x18007cbeb  mov     rcx, rdi; this
0x18007cbee  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cbf3  test    eax, eax
0x18007cbf5  jnz     short loc_18007CC16
0x18007cbf7  mov     rcx, [rsp+2F8h+String]; String
0x18007cbfc  test    rcx, rcx
0x18007cbff  jz      short loc_18007CC16
0x18007cc01  call    cs:__imp__wtoi
0x18007cc07  mov     [rsp+2F8h+var_1D8], eax
0x18007cc0e  mov     [rsp+2F8h+var_1D4], r12b
0x18007cc16  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cc1b  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x18007cc22  mov     rcx, rdi; this
0x18007cc25  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cc2a  test    eax, eax
0x18007cc2c  jnz     short loc_18007CC4D
0x18007cc2e  mov     rcx, [rsp+2F8h+String]; String
0x18007cc33  test    rcx, rcx
0x18007cc36  jz      short loc_18007CC4D
0x18007cc38  call    cs:__imp__wtoi
0x18007cc3e  mov     [rsp+2F8h+var_1D0], eax
0x18007cc45  mov     [rsp+2F8h+var_1CC], r12b
0x18007cc4d  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cc52  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x18007cc59  mov     rcx, rdi; this
0x18007cc5c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cc61  test    eax, eax
0x18007cc63  jnz     short loc_18007CC84
0x18007cc65  mov     rcx, [rsp+2F8h+String]; String
0x18007cc6a  test    rcx, rcx
0x18007cc6d  jz      short loc_18007CC84
0x18007cc6f  call    cs:__imp__wtoi
0x18007cc75  mov     [rsp+2F8h+var_1C8], eax
0x18007cc7c  mov     [rsp+2F8h+var_1C4], r12b
0x18007cc84  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cc89  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x18007cc90  mov     rcx, rdi; this
0x18007cc93  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cc98  test    eax, eax
0x18007cc9a  jnz     short loc_18007CCBB
0x18007cc9c  mov     rcx, [rsp+2F8h+String]; String
0x18007cca1  test    rcx, rcx
0x18007cca4  jz      short loc_18007CCBB
0x18007cca6  call    cs:__imp__wtoi
0x18007ccac  mov     [rsp+2F8h+var_1C0], eax
0x18007ccb3  mov     [rsp+2F8h+var_1BC], r12b
0x18007ccbb  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007ccc0  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x18007ccc7  mov     rcx, rdi; this
0x18007ccca  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cccf  test    eax, eax
0x18007ccd1  jnz     short loc_18007CCF2
0x18007ccd3  mov     rcx, [rsp+2F8h+String]; String
0x18007ccd8  test    rcx, rcx
0x18007ccdb  jz      short loc_18007CCF2
0x18007ccdd  call    cs:__imp__wtoi
0x18007cce3  mov     [rsp+2F8h+var_1B8], eax
0x18007ccea  mov     [rsp+2F8h+var_1B4], r12b
0x18007ccf2  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007ccf7  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x18007ccfe  mov     rcx, rdi; this
0x18007cd01  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cd06  test    eax, eax
0x18007cd08  jnz     short loc_18007CD29
0x18007cd0a  mov     rcx, [rsp+2F8h+String]; String
0x18007cd0f  test    rcx, rcx
0x18007cd12  jz      short loc_18007CD29
0x18007cd14  call    cs:__imp__wtoi
0x18007cd1a  mov     [rsp+2F8h+var_1B0], eax
0x18007cd21  mov     [rsp+2F8h+var_1AC], r12b
0x18007cd29  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cd2e  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x18007cd35  mov     rcx, rdi; this
0x18007cd38  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cd3d  test    eax, eax
0x18007cd3f  jnz     short loc_18007CD60
0x18007cd41  mov     rcx, [rsp+2F8h+String]; String
0x18007cd46  test    rcx, rcx
0x18007cd49  jz      short loc_18007CD60
0x18007cd4b  call    cs:__imp__wtoi
0x18007cd51  mov     [rsp+2F8h+var_1A8], eax
0x18007cd58  mov     [rsp+2F8h+var_1A4], r12b
0x18007cd60  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cd65  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x18007cd6c  mov     rcx, rdi; this
0x18007cd6f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cd74  test    eax, eax
0x18007cd76  jnz     short loc_18007CD97
0x18007cd78  mov     rcx, [rsp+2F8h+String]; String
0x18007cd7d  test    rcx, rcx
0x18007cd80  jz      short loc_18007CD97
0x18007cd82  call    cs:__imp__wtoi
0x18007cd88  mov     [rsp+2F8h+var_1A0], eax
0x18007cd8f  mov     [rsp+2F8h+var_19C], r12b
0x18007cd97  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cd9c  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18007cda3  mov     rcx, rdi; this
0x18007cda6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cdab  test    eax, eax
0x18007cdad  jnz     short loc_18007CDCE
0x18007cdaf  mov     rcx, [rsp+2F8h+String]; String
0x18007cdb4  test    rcx, rcx
0x18007cdb7  jz      short loc_18007CDCE
0x18007cdb9  call    cs:__imp__wtoi
0x18007cdbf  mov     [rsp+2F8h+var_198], eax
0x18007cdc6  mov     [rsp+2F8h+var_194], r12b
0x18007cdce  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007cdd3  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18007cdda  mov     rcx, rdi; this
0x18007cddd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007cde2  test    eax, eax
0x18007cde4  jnz     short loc_18007CE05
0x18007cde6  mov     rcx, [rsp+2F8h+String]; String
0x18007cdeb  test    rcx, rcx
0x18007cdee  jz      short loc_18007CE05
0x18007cdf0  call    cs:__imp__wtoi
0x18007cdf6  mov     [rsp+2F8h+var_190], eax
0x18007cdfd  mov     [rsp+2F8h+var_18C], r12b
0x18007ce05  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x18007ce0a  lea     rdx, aAllowuseruiacc; "AllowUserUIAccess"
0x18007ce11  mov     rcx, rdi; this
0x18007ce14  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007ce19  test    eax, eax
0x18007ce1b  jnz     short loc_18007CE3C
0x18007ce1d  mov     rcx, [rsp+2F8h+String]; String
0x18007ce22  test    rcx, rcx
0x18007ce25  jz      short loc_18007CE3C
  ... truncated ...
```
