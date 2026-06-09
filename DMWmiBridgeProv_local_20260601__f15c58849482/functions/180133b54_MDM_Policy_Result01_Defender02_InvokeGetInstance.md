# MDM_Policy_Result01_Defender02_InvokeGetInstance

- ea: `0x180133b54`
- end: `0x180134823`
- name: `MDM_Policy_Result01_Defender02_InvokeGetInstance`
- size: `3279`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180131ba0`

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
- `0x180133b54`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180133df3`
- `msvcrt!_wtoi` at `0x180133e30`
- `msvcrt!_wtoi` at `0x180133e6d`
- `msvcrt!_wtoi` at `0x180133eaa`
- `msvcrt!_wtoi` at `0x180133ee7`
- `msvcrt!_wtoi` at `0x180133f24`
- `msvcrt!_wtoi` at `0x180133f61`
- `msvcrt!_wtoi` at `0x180133f9e`
- `msvcrt!_wtoi` at `0x180133fdb`
- `msvcrt!_wtoi` at `0x180134018`
- `msvcrt!_wtoi` at `0x180134055`
- `msvcrt!_wtoi` at `0x180134092`
- `msvcrt!_wtoi` at `0x1801340cf`
- `msvcrt!_wtoi` at `0x18013416a`
- `msvcrt!_wtoi` at `0x1801341a7`
- `msvcrt!_wtoi` at `0x1801341e4`
- `msvcrt!_wtoi` at `0x180134221`
- `msvcrt!_wtoi` at `0x1801342bc`
- `msvcrt!_wtoi` at `0x1801342f9`
- `msvcrt!_wtoi` at `0x180134336`
- `msvcrt!_wtoi` at `0x180134373`
- `msvcrt!_wtoi` at `0x1801343b0`
- `msvcrt!_wtoi` at `0x1801343ed`
- `msvcrt!_wtoi` at `0x1801344b7`
- `msvcrt!_wtoi` at `0x1801344f4`
- `msvcrt!_wtoi` at `0x180134531`
- `msvcrt!_wtoi` at `0x18013456e`
- `msvcrt!_wtoi` at `0x1801345ab`
- `msvcrt!_wtoi` at `0x1801345e8`
- `msvcrt!_wtoi` at `0x1801346b2`
- `msvcrt!_wtoi` at `0x1801346ef`
- `msvcrt!_wtoi` at `0x180133df3`
- `msvcrt!_wtoi` at `0x180133e30`
- `msvcrt!_wtoi` at `0x180133e6d`
- `msvcrt!_wtoi` at `0x180133eaa`
- `msvcrt!_wtoi` at `0x180133ee7`
- `msvcrt!_wtoi` at `0x180133f24`
- `msvcrt!_wtoi` at `0x180133f61`
- `msvcrt!_wtoi` at `0x180133f9e`
- `msvcrt!_wtoi` at `0x180133fdb`
- `msvcrt!_wtoi` at `0x180134018`
- `msvcrt!_wtoi` at `0x180134055`
- `msvcrt!_wtoi` at `0x180134092`
- `msvcrt!_wtoi` at `0x1801340cf`
- `msvcrt!_wtoi` at `0x18013416a`
- `msvcrt!_wtoi` at `0x1801341a7`
- `msvcrt!_wtoi` at `0x1801341e4`
- `msvcrt!_wtoi` at `0x180134221`
- `msvcrt!_wtoi` at `0x1801342bc`
- `msvcrt!_wtoi` at `0x1801342f9`
- `msvcrt!_wtoi` at `0x180134336`
- `msvcrt!_wtoi` at `0x180134373`
- `msvcrt!_wtoi` at `0x1801343b0`
- `msvcrt!_wtoi` at `0x1801343ed`
- `msvcrt!_wtoi` at `0x1801344b7`
- `msvcrt!_wtoi` at `0x1801344f4`
- `msvcrt!_wtoi` at `0x180134531`
- `msvcrt!_wtoi` at `0x18013456e`
- `msvcrt!_wtoi` at `0x1801345ab`
- `msvcrt!_wtoi` at `0x1801345e8`
- `msvcrt!_wtoi` at `0x1801346b2`
- `msvcrt!_wtoi` at `0x1801346ef`

## string_xrefs

- `0x180133fbe`: `AllowOnAccessProtection`
- `0x1801340b2`: `AllowUserUIAccess`
- `0x180134241`: `ControlledFolderAccessAllowedApplications`
- `0x180134270`: `ControlledFolderAccessProtectedFolders`
- `0x180134356`: `EnableControlledFolderAccess`
- `0x18013440d`: `ExcludedExtensions`
- `0x18013443c`: `ExcludedPaths`
- `0x180134608`: `SecurityIntelligenceLocation`
- `0x180134637`: `SignatureUpdateFallbackOrder`
- `0x180134666`: `SignatureUpdateFileSharesSources`
- `0x180134695`: `SignatureUpdateInterval`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Defender02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v11[2] = "MDM_Policy_Result01_Defender02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180353BCA,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                         &MDM_Policy_Result01_Defender02_NodeList,
                         44,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Defender02_NodeList,
          0x2Cu);
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Defender02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
              v9 = 1;
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowArchiveScanning",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowBehaviorMonitoring",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowCloudProtection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowEmailScanning",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowIOAVProtection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowOnAccessProtection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowRealtimeMonitoring",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowScanningNetworkFiles",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowScriptScanning",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowUserUIAccess",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"CloudExtendedTimeout",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DaysToRetainCleanedMalware",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableCatchupFullScan",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableCatchupQuickScan",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnableLowCPUPriority",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnableNetworkProtection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ExcludedExtensions",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckServerCertificateRevocation(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"ExcludedPaths", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_CheckSignaturesOnDownloadedPrograms(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ExcludedProcesses",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RealTimeScanDirection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ScheduleQuickScanTime",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"SignatureUpdateInterval",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v76 = _wtoi(String);
                v77 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"SubmitSamplesConsent",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036FC3F,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180133b54  mov     [rsp+arg_10], rbx
0x180133b59  push    rsi
0x180133b5a  push    rdi
0x180133b5b  push    r12
0x180133b5d  push    r14
0x180133b5f  push    r15
0x180133b61  sub     rsp, 2D0h
0x180133b68  mov     rax, cs:__security_cookie
0x180133b6f  xor     rax, rsp
0x180133b72  mov     [rsp+2F8h+var_38], rax
0x180133b7a  mov     rsi, rdx
0x180133b7d  mov     r15, rcx
0x180133b80  xor     ebx, ebx
0x180133b82  mov     [rsp+2F8h+String], rbx
0x180133b87  xor     edx, edx; Val
0x180133b89  mov     r8d, 208h; Size
0x180133b8f  lea     rcx, [rsp+2F8h+instance]; void *
0x180133b97  call    memset_0
0x180133b9c  mov     [rsp+2F8h+var_270], ebx
0x180133ba3  mov     [rsp+2F8h+var_26C], bl
0x180133baa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180133bb1  mov     [rsp+2F8h+var_2A0], rax
0x180133bb6  lea     rax, [rsp+2F8h+var_270]
0x180133bbe  mov     [rsp+2F8h+var_298], rax
0x180133bc3  lea     rax, aMdmPolicyResul_181; "MDM_Policy_Result01_Defender02"
0x180133bca  mov     [rsp+2F8h+var_290], rax
0x180133bcf  lea     rcx, [rsp+2F8h+var_270]
0x180133bd7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180133bdc  mov     eax, cs:dword_180380B68
0x180133be2  cmp     eax, 5
0x180133be5  jbe     short loc_180133C56
0x180133be7  mov     rdx, 200000000000h
0x180133bf1  lea     rcx, dword_180380B68
0x180133bf8  call    _tlgKeywordOn
0x180133bfd  test    al, al
0x180133bff  jz      short loc_180133C56
0x180133c01  cmp     [rsp+2F8h+var_26C], bl
0x180133c08  jz      short loc_180133C38
0x180133c0a  cmp     [rsp+2F8h+var_258], ebx
0x180133c11  jnz     short loc_180133C2E
0x180133c13  cmp     [rsp+2F8h+var_254], ebx
0x180133c1a  jnz     short loc_180133C2E
0x180133c1c  cmp     [rsp+2F8h+var_250], ebx
0x180133c23  jnz     short loc_180133C2E
0x180133c25  cmp     [rsp+2F8h+var_24C], ebx
0x180133c2c  jz      short loc_180133C38
0x180133c2e  lea     r9, [rsp+2F8h+var_258]
0x180133c36  jmp     short loc_180133C3B
0x180133c38  mov     r9, rbx
0x180133c3b  lea     r8, [rsp+2F8h+var_268]
0x180133c43  lea     rdx, word_180353BCA
0x180133c4a  lea     rcx, dword_180380B68
0x180133c51  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180133c56  cmp     [rsi+48h], bl
0x180133c59  jz      loc_180134781
0x180133c5f  mov     [rsp+2F8h+var_2B0], bl
0x180133c63  cmp     [rsi+58h], bl
0x180133c66  jz      loc_180134781
0x180133c6c  mov     r9, [rsi+40h]; unsigned __int16 *
0x180133c70  mov     r8, [rsi+50h]; unsigned __int16 *
0x180133c74  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180133c7b  lea     rcx, [rsp+2F8h+var_2A0]; this
0x180133c80  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180133c85  nop
0x180133c86  mov     [rsp+2F8h+var_2A8], rbx
0x180133c8b  lea     rax, [rsp+2F8h+var_2A8]
0x180133c90  mov     [rsp+2F8h+var_2C8], rax
0x180133c95  mov     [rsp+2F8h+var_2D0], ebx
0x180133c99  mov     [rsp+2F8h+var_2D8], 2Ch ; ','
0x180133ca1  lea     r9, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Defender02_NodeList
0x180133ca8  mov     r8, [rsi+40h]
0x180133cac  mov     rdx, [rsi+50h]
0x180133cb0  mov     rcx, r15
0x180133cb3  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180133cb8  mov     r14d, eax
0x180133cbb  test    eax, eax
0x180133cbd  jz      short loc_180133CC4
0x180133cbf  jmp     loc_180134787
0x180133cc4  lea     rax, [rsp+2F8h+var_2A8]
0x180133cc9  mov     [rsp+2F8h+var_280], rax
0x180133cce  mov     r12d, 1
0x180133cd4  mov     [rsp+2F8h+var_278], r12b
0x180133cdc  mov     rdi, [rsp+2F8h+var_2A8]
0x180133ce1  test    rdi, rdi
0x180133ce4  jnz     short loc_180133CEE
0x180133ce6  mov     r14d, r12d
0x180133ce9  jmp     loc_180134787
0x180133cee  mov     r9d, 2Ch ; ','; unsigned int
0x180133cf4  lea     r8, ?MDM_Policy_Result01_Defender02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180133cfb  mov     rdx, rsi; struct _MI_Instance *
0x180133cfe  mov     rcx, rdi; this
0x180133d01  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180133d06  mov     rax, [rdi]
0x180133d09  mov     rcx, rdi
0x180133d0c  mov     rax, [rax+10h]
0x180133d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d15  mov     r14d, eax
0x180133d18  test    eax, eax
0x180133d1a  jz      short loc_180133D3A
0x180133d1c  mov     rcx, [rsp+2F8h+var_2A8]
0x180133d21  test    rcx, rcx
0x180133d24  jz      short loc_180133D35
0x180133d26  mov     rax, [rcx]
0x180133d29  mov     edx, r12d
0x180133d2c  mov     rax, [rax]
0x180133d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d34  nop
0x180133d35  jmp     loc_180134787
0x180133d3a  mov     rax, [rdi]
0x180133d3d  mov     rcx, rdi
0x180133d40  mov     rax, [rax+8]
0x180133d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d49  mov     r14d, eax
0x180133d4c  test    eax, eax
0x180133d4e  jz      short loc_180133D6E
0x180133d50  mov     rcx, [rsp+2F8h+var_2A8]
0x180133d55  test    rcx, rcx
0x180133d58  jz      short loc_180133D69
0x180133d5a  mov     rax, [rcx]
0x180133d5d  mov     edx, r12d
0x180133d60  mov     rax, [rax]
0x180133d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133d68  nop
0x180133d69  jmp     loc_180134787
0x180133d6e  lea     r8, [rsp+2F8h+instance]; instance
0x180133d76  lea     rdx, MDM_Policy_Result01_Defender02_rtti; classDecl
0x180133d7d  mov     rcx, r15; context
0x180133d80  call    MI_Context_ConstructInstance
0x180133d85  mov     r14d, eax
0x180133d88  test    eax, eax
0x180133d8a  jz      short loc_180133DAA
0x180133d8c  mov     rcx, [rsp+2F8h+var_2A8]
0x180133d91  test    rcx, rcx
0x180133d94  jz      short loc_180133DA5
0x180133d96  mov     rax, [rcx]
0x180133d99  mov     edx, r12d
0x180133d9c  mov     rax, [rax]
0x180133d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133da4  nop
0x180133da5  jmp     loc_180134787
0x180133daa  mov     [rsp+2F8h+var_2B0], r12b
0x180133daf  mov     rdx, [rsi+40h]
0x180133db3  lea     rcx, [rsp+2F8h+instance]
0x180133dbb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180133dc0  mov     rdx, [rsi+50h]
0x180133dc4  lea     rcx, [rsp+2F8h+instance]
0x180133dcc  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180133dd1  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133dd6  lea     rdx, aAllowarchivesc; "AllowArchiveScanning"
0x180133ddd  mov     rcx, rdi; this
0x180133de0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133de5  test    eax, eax
0x180133de7  jnz     short loc_180133E0E
0x180133de9  mov     rcx, [rsp+2F8h+String]; String
0x180133dee  test    rcx, rcx
0x180133df1  jz      short loc_180133E0E
0x180133df3  call    cs:__imp__wtoi
0x180133dfa  nop     dword ptr [rax+rax+00h]
0x180133dff  mov     [rsp+2F8h+var_1E8], eax
0x180133e06  mov     [rsp+2F8h+var_1E4], r12b
0x180133e0e  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133e13  lea     rdx, aAllowbehaviorm; "AllowBehaviorMonitoring"
0x180133e1a  mov     rcx, rdi; this
0x180133e1d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133e22  test    eax, eax
0x180133e24  jnz     short loc_180133E4B
0x180133e26  mov     rcx, [rsp+2F8h+String]; String
0x180133e2b  test    rcx, rcx
0x180133e2e  jz      short loc_180133E4B
0x180133e30  call    cs:__imp__wtoi
0x180133e37  nop     dword ptr [rax+rax+00h]
0x180133e3c  mov     [rsp+2F8h+var_1E0], eax
0x180133e43  mov     [rsp+2F8h+var_1DC], r12b
0x180133e4b  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133e50  lea     rdx, aAllowcloudprot; "AllowCloudProtection"
0x180133e57  mov     rcx, rdi; this
0x180133e5a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133e5f  test    eax, eax
0x180133e61  jnz     short loc_180133E88
0x180133e63  mov     rcx, [rsp+2F8h+String]; String
0x180133e68  test    rcx, rcx
0x180133e6b  jz      short loc_180133E88
0x180133e6d  call    cs:__imp__wtoi
0x180133e74  nop     dword ptr [rax+rax+00h]
0x180133e79  mov     [rsp+2F8h+var_1D8], eax
0x180133e80  mov     [rsp+2F8h+var_1D4], r12b
0x180133e88  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133e8d  lea     rdx, aAllowemailscan; "AllowEmailScanning"
0x180133e94  mov     rcx, rdi; this
0x180133e97  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133e9c  test    eax, eax
0x180133e9e  jnz     short loc_180133EC5
0x180133ea0  mov     rcx, [rsp+2F8h+String]; String
0x180133ea5  test    rcx, rcx
0x180133ea8  jz      short loc_180133EC5
0x180133eaa  call    cs:__imp__wtoi
0x180133eb1  nop     dword ptr [rax+rax+00h]
0x180133eb6  mov     [rsp+2F8h+var_1D0], eax
0x180133ebd  mov     [rsp+2F8h+var_1CC], r12b
0x180133ec5  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133eca  lea     rdx, aAllowfullscano; "AllowFullScanOnMappedNetworkDrives"
0x180133ed1  mov     rcx, rdi; this
0x180133ed4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133ed9  test    eax, eax
0x180133edb  jnz     short loc_180133F02
0x180133edd  mov     rcx, [rsp+2F8h+String]; String
0x180133ee2  test    rcx, rcx
0x180133ee5  jz      short loc_180133F02
0x180133ee7  call    cs:__imp__wtoi
0x180133eee  nop     dword ptr [rax+rax+00h]
0x180133ef3  mov     [rsp+2F8h+var_1C8], eax
0x180133efa  mov     [rsp+2F8h+var_1C4], r12b
0x180133f02  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133f07  lea     rdx, aAllowfullscanr; "AllowFullScanRemovableDriveScanning"
0x180133f0e  mov     rcx, rdi; this
0x180133f11  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133f16  test    eax, eax
0x180133f18  jnz     short loc_180133F3F
0x180133f1a  mov     rcx, [rsp+2F8h+String]; String
0x180133f1f  test    rcx, rcx
0x180133f22  jz      short loc_180133F3F
0x180133f24  call    cs:__imp__wtoi
0x180133f2b  nop     dword ptr [rax+rax+00h]
0x180133f30  mov     [rsp+2F8h+var_1C0], eax
0x180133f37  mov     [rsp+2F8h+var_1BC], r12b
0x180133f3f  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133f44  lea     rdx, aAllowintrusion; "AllowIntrusionPreventionSystem"
0x180133f4b  mov     rcx, rdi; this
0x180133f4e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133f53  test    eax, eax
0x180133f55  jnz     short loc_180133F7C
0x180133f57  mov     rcx, [rsp+2F8h+String]; String
0x180133f5c  test    rcx, rcx
0x180133f5f  jz      short loc_180133F7C
0x180133f61  call    cs:__imp__wtoi
0x180133f68  nop     dword ptr [rax+rax+00h]
0x180133f6d  mov     [rsp+2F8h+var_1B8], eax
0x180133f74  mov     [rsp+2F8h+var_1B4], r12b
0x180133f7c  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133f81  lea     rdx, aAllowioavprote; "AllowIOAVProtection"
0x180133f88  mov     rcx, rdi; this
0x180133f8b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133f90  test    eax, eax
0x180133f92  jnz     short loc_180133FB9
0x180133f94  mov     rcx, [rsp+2F8h+String]; String
0x180133f99  test    rcx, rcx
0x180133f9c  jz      short loc_180133FB9
0x180133f9e  call    cs:__imp__wtoi
0x180133fa5  nop     dword ptr [rax+rax+00h]
0x180133faa  mov     [rsp+2F8h+var_1B0], eax
0x180133fb1  mov     [rsp+2F8h+var_1AC], r12b
0x180133fb9  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133fbe  lea     rdx, aAllowonaccessp; "AllowOnAccessProtection"
0x180133fc5  mov     rcx, rdi; this
0x180133fc8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180133fcd  test    eax, eax
0x180133fcf  jnz     short loc_180133FF6
0x180133fd1  mov     rcx, [rsp+2F8h+String]; String
0x180133fd6  test    rcx, rcx
0x180133fd9  jz      short loc_180133FF6
0x180133fdb  call    cs:__imp__wtoi
0x180133fe2  nop     dword ptr [rax+rax+00h]
0x180133fe7  mov     [rsp+2F8h+var_1A8], eax
0x180133fee  mov     [rsp+2F8h+var_1A4], r12b
0x180133ff6  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180133ffb  lea     rdx, aAllowrealtimem; "AllowRealtimeMonitoring"
0x180134002  mov     rcx, rdi; this
0x180134005  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18013400a  test    eax, eax
0x18013400c  jnz     short loc_180134033
0x18013400e  mov     rcx, [rsp+2F8h+String]; String
0x180134013  test    rcx, rcx
0x180134016  jz      short loc_180134033
0x180134018  call    cs:__imp__wtoi
0x18013401f  nop     dword ptr [rax+rax+00h]
0x180134024  mov     [rsp+2F8h+var_1A0], eax
0x18013402b  mov     [rsp+2F8h+var_19C], r12b
0x180134033  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134038  lea     rdx, aAllowscanningn; "AllowScanningNetworkFiles"
0x18013403f  mov     rcx, rdi; this
0x180134042  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134047  test    eax, eax
0x180134049  jnz     short loc_180134070
0x18013404b  mov     rcx, [rsp+2F8h+String]; String
0x180134050  test    rcx, rcx
0x180134053  jz      short loc_180134070
0x180134055  call    cs:__imp__wtoi
0x18013405c  nop     dword ptr [rax+rax+00h]
0x180134061  mov     [rsp+2F8h+var_198], eax
0x180134068  mov     [rsp+2F8h+var_194], r12b
0x180134070  lea     r8, [rsp+2F8h+String]; unsigned __int16 **
0x180134075  lea     rdx, aAllowscriptsca; "AllowScriptScanning"
0x18013407c  mov     rcx, rdi; this
0x18013407f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180134084  test    eax, eax
0x180134086  jnz     short loc_1801340AD
0x180134088  mov     rcx, [rsp+2F8h+String]; String
0x18013408d  test    rcx, rcx
0x180134090  jz      short loc_1801340AD
0x180134092  call    cs:__imp__wtoi
  ... truncated ...
```
