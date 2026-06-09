# MDM_Policy_Result01_System02_InvokeGetInstance

- ea: `0x18019b020`
- end: `0x18019baef`
- name: `MDM_Policy_Result01_System02_InvokeGetInstance`
- size: `2767`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180199550`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x1800052e8`
- `0x180005470`
- `0x1800055f8`
- `0x180005aac`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18019b020`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019b2bf`
- `msvcrt!_wtoi` at `0x18019b2fc`
- `msvcrt!_wtoi` at `0x18019b339`
- `msvcrt!_wtoi` at `0x18019b376`
- `msvcrt!_wtoi` at `0x18019b3b3`
- `msvcrt!_wtoi` at `0x18019b3f0`
- `msvcrt!_wtoi` at `0x18019b42d`
- `msvcrt!_wtoi` at `0x18019b46a`
- `msvcrt!_wtoi` at `0x18019b4a7`
- `msvcrt!_wtoi` at `0x18019b4e4`
- `msvcrt!_wtoi` at `0x18019b521`
- `msvcrt!_wtoi` at `0x18019b55e`
- `msvcrt!_wtoi` at `0x18019b59b`
- `msvcrt!_wtoi` at `0x18019b5d8`
- `msvcrt!_wtoi` at `0x18019b673`
- `msvcrt!_wtoi` at `0x18019b6b0`
- `msvcrt!_wtoi` at `0x18019b6ed`
- `msvcrt!_wtoi` at `0x18019b72a`
- `msvcrt!_wtoi` at `0x18019b767`
- `msvcrt!_wtoi` at `0x18019b7a4`
- `msvcrt!_wtoi` at `0x18019b7e1`
- `msvcrt!_wtoi` at `0x18019b81e`
- `msvcrt!_wtoi` at `0x18019b88a`
- `msvcrt!_wtoi` at `0x18019b8c7`
- `msvcrt!_wtoi` at `0x18019b904`
- `msvcrt!_wtoi` at `0x18019b941`
- `msvcrt!_wtoi` at `0x18019b97e`
- `msvcrt!_wtoi` at `0x18019b9ea`
- `msvcrt!_wtoi` at `0x18019b2bf`
- `msvcrt!_wtoi` at `0x18019b2fc`
- `msvcrt!_wtoi` at `0x18019b339`
- `msvcrt!_wtoi` at `0x18019b376`
- `msvcrt!_wtoi` at `0x18019b3b3`
- `msvcrt!_wtoi` at `0x18019b3f0`
- `msvcrt!_wtoi` at `0x18019b42d`
- `msvcrt!_wtoi` at `0x18019b46a`
- `msvcrt!_wtoi` at `0x18019b4a7`
- `msvcrt!_wtoi` at `0x18019b4e4`
- `msvcrt!_wtoi` at `0x18019b521`
- `msvcrt!_wtoi` at `0x18019b55e`
- `msvcrt!_wtoi` at `0x18019b59b`
- `msvcrt!_wtoi` at `0x18019b5d8`
- `msvcrt!_wtoi` at `0x18019b673`
- `msvcrt!_wtoi` at `0x18019b6b0`
- `msvcrt!_wtoi` at `0x18019b6ed`
- `msvcrt!_wtoi` at `0x18019b72a`
- `msvcrt!_wtoi` at `0x18019b767`
- `msvcrt!_wtoi` at `0x18019b7a4`
- `msvcrt!_wtoi` at `0x18019b7e1`
- `msvcrt!_wtoi` at `0x18019b81e`
- `msvcrt!_wtoi` at `0x18019b88a`
- `msvcrt!_wtoi` at `0x18019b8c7`
- `msvcrt!_wtoi` at `0x18019b904`
- `msvcrt!_wtoi` at `0x18019b941`
- `msvcrt!_wtoi` at `0x18019b97e`
- `msvcrt!_wtoi` at `0x18019b9ea`

## string_xrefs

- `0x18019b2df`: `AllowCommercialDataPipeline`
- `0x18019b541`: `AllowUpdateComplianceProcessing`
- `0x18019b627`: `ConfigureMicrosoft365UploadEndpoint`
- `0x18019b656`: `ConfigureTelemetryOptInChangeNotification`
- `0x18019b693`: `ConfigureTelemetryOptInSettingsUx`
- `0x18019b6d0`: `DisableDeviceDelete`
- `0x18019b74a`: `DisableDirectXDatabaseUpdate`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_System02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-228h] BYREF
  char v9; // [rsp+48h] [rbp-220h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-218h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-210h] BYREF
  char v12; // [rsp+80h] [rbp-1E8h]
  int v13; // [rsp+88h] [rbp-1E0h] BYREF
  char v14; // [rsp+8Ch] [rbp-1DCh]
  _BYTE v15[16]; // [rsp+90h] [rbp-1D8h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-1C8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-1B8h] BYREF
  int v18; // [rsp+110h] [rbp-158h]
  char v19; // [rsp+114h] [rbp-154h]
  int v20; // [rsp+118h] [rbp-150h]
  char v21; // [rsp+11Ch] [rbp-14Ch]
  int v22; // [rsp+120h] [rbp-148h]
  char v23; // [rsp+124h] [rbp-144h]
  int v24; // [rsp+128h] [rbp-140h]
  char v25; // [rsp+12Ch] [rbp-13Ch]
  int v26; // [rsp+130h] [rbp-138h]
  char v27; // [rsp+134h] [rbp-134h]
  int v28; // [rsp+138h] [rbp-130h]
  char v29; // [rsp+13Ch] [rbp-12Ch]
  int v30; // [rsp+140h] [rbp-128h]
  char v31; // [rsp+144h] [rbp-124h]
  int v32; // [rsp+148h] [rbp-120h]
  char v33; // [rsp+14Ch] [rbp-11Ch]
  int v34; // [rsp+150h] [rbp-118h]
  char v35; // [rsp+154h] [rbp-114h]
  int v36; // [rsp+158h] [rbp-110h]
  char v37; // [rsp+15Ch] [rbp-10Ch]
  int v38; // [rsp+160h] [rbp-108h]
  char v39; // [rsp+164h] [rbp-104h]
  int v40; // [rsp+168h] [rbp-100h]
  char v41; // [rsp+16Ch] [rbp-FCh]
  int v42; // [rsp+170h] [rbp-F8h]
  char v43; // [rsp+174h] [rbp-F4h]
  int v44; // [rsp+178h] [rbp-F0h]
  char v45; // [rsp+17Ch] [rbp-ECh]
  int v46; // [rsp+1A0h] [rbp-C8h]
  char v47; // [rsp+1A4h] [rbp-C4h]
  int v48; // [rsp+1A8h] [rbp-C0h]
  char v49; // [rsp+1ACh] [rbp-BCh]
  int v50; // [rsp+1B0h] [rbp-B8h]
  char v51; // [rsp+1B4h] [rbp-B4h]
  int v52; // [rsp+1B8h] [rbp-B0h]
  char v53; // [rsp+1BCh] [rbp-ACh]
  int v54; // [rsp+1C0h] [rbp-A8h]
  char v55; // [rsp+1C4h] [rbp-A4h]
  int v56; // [rsp+1C8h] [rbp-A0h]
  char v57; // [rsp+1CCh] [rbp-9Ch]
  int v58; // [rsp+1D0h] [rbp-98h]
  char v59; // [rsp+1D4h] [rbp-94h]
  int v60; // [rsp+1D8h] [rbp-90h]
  char v61; // [rsp+1DCh] [rbp-8Ch]
  int v62; // [rsp+1F0h] [rbp-78h]
  char v63; // [rsp+1F4h] [rbp-74h]
  int v64; // [rsp+1F8h] [rbp-70h]
  char v65; // [rsp+1FCh] [rbp-6Ch]
  int v66; // [rsp+200h] [rbp-68h]
  char v67; // [rsp+204h] [rbp-64h]
  int v68; // [rsp+208h] [rbp-60h]
  char v69; // [rsp+20Ch] [rbp-5Ch]
  int v70; // [rsp+210h] [rbp-58h]
  char v71; // [rsp+214h] [rbp-54h]
  int v72; // [rsp+228h] [rbp-40h]
  char v73; // [rsp+22Ch] [rbp-3Ch]

  String = 0;
  memset_0(&instance, 0, 0x180u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_System02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180359FC4,
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
                         &MDM_Policy_Result01_System02_NodeList,
                         34,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_System02_NodeList,
          0x22u);
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
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_System02_rtti, &instance);
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
                     L"AllowBuildPreview",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowCommercialDataPipeline",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowDesktopAnalyticsProcessing",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowDeviceNameInDiagnosticData",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowEmbeddedMode",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowExperimentation",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowFontProviders",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowLocation", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowMicrosoftManagedDesktopProcessing",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowStorageCard", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowTelemetry", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowUpdateComplianceProcessing",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowUserToResetPhone",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowWUfBCloudProcessing",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"BootStartDriverInitialization",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureMicrosoft365UploadEndpoint",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureTelemetryOptInChangeNotification",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureTelemetryOptInSettingsUx",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableDeviceDelete",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableDiagnosticDataViewer",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableDirectXDatabaseUpdate",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableEnterpriseAuthProxy",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableOneDriveFileSync",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableOneSettingsDownloads",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableSystemRestore",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnableOneSettingsAuditing",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"LimitDiagnosticLogCollection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"LimitDumpCollection",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"TelemetryProxy", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"TurnOffFileHistory",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
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
      &word_18033E66E,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18019b020  mov     [rsp+arg_10], rbx
0x18019b025  push    rsi
0x18019b026  push    rdi
0x18019b027  push    r12
0x18019b029  push    r14
0x18019b02b  push    r15
0x18019b02d  sub     rsp, 240h
0x18019b034  mov     rax, cs:__security_cookie
0x18019b03b  xor     rax, rsp
0x18019b03e  mov     [rsp+268h+var_38], rax
0x18019b046  mov     rsi, rdx
0x18019b049  mov     r15, rcx
0x18019b04c  xor     ebx, ebx
0x18019b04e  mov     [rsp+268h+String], rbx
0x18019b053  xor     edx, edx; Val
0x18019b055  mov     r8d, 180h; Size
0x18019b05b  lea     rcx, [rsp+268h+instance]; void *
0x18019b063  call    memset_0
0x18019b068  mov     [rsp+268h+var_1E0], ebx
0x18019b06f  mov     [rsp+268h+var_1DC], bl
0x18019b076  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019b07d  mov     [rsp+268h+var_210], rax
0x18019b082  lea     rax, [rsp+268h+var_1E0]
0x18019b08a  mov     [rsp+268h+var_208], rax
0x18019b08f  lea     rax, aMdmPolicyResul_159; "MDM_Policy_Result01_System02"
0x18019b096  mov     [rsp+268h+var_200], rax
0x18019b09b  lea     rcx, [rsp+268h+var_1E0]
0x18019b0a3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019b0a8  mov     eax, cs:dword_180380B68
0x18019b0ae  cmp     eax, 5
0x18019b0b1  jbe     short loc_18019B122
0x18019b0b3  mov     rdx, 200000000000h
0x18019b0bd  lea     rcx, dword_180380B68
0x18019b0c4  call    _tlgKeywordOn
0x18019b0c9  test    al, al
0x18019b0cb  jz      short loc_18019B122
0x18019b0cd  cmp     [rsp+268h+var_1DC], bl
0x18019b0d4  jz      short loc_18019B104
0x18019b0d6  cmp     [rsp+268h+var_1C8], ebx
0x18019b0dd  jnz     short loc_18019B0FA
0x18019b0df  cmp     [rsp+268h+var_1C4], ebx
0x18019b0e6  jnz     short loc_18019B0FA
0x18019b0e8  cmp     [rsp+268h+var_1C0], ebx
0x18019b0ef  jnz     short loc_18019B0FA
0x18019b0f1  cmp     [rsp+268h+var_1BC], ebx
0x18019b0f8  jz      short loc_18019B104
0x18019b0fa  lea     r9, [rsp+268h+var_1C8]
0x18019b102  jmp     short loc_18019B107
0x18019b104  mov     r9, rbx
0x18019b107  lea     r8, [rsp+268h+var_1D8]
0x18019b10f  lea     rdx, dword_180359FC4
0x18019b116  lea     rcx, dword_180380B68
0x18019b11d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019b122  cmp     [rsi+48h], bl
0x18019b125  jz      loc_18019BA4D
0x18019b12b  mov     [rsp+268h+var_220], bl
0x18019b12f  cmp     [rsi+58h], bl
0x18019b132  jz      loc_18019BA4D
0x18019b138  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019b13c  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019b140  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18019b147  lea     rcx, [rsp+268h+var_210]; this
0x18019b14c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019b151  nop
0x18019b152  mov     [rsp+268h+var_218], rbx
0x18019b157  lea     rax, [rsp+268h+var_218]
0x18019b15c  mov     [rsp+268h+var_238], rax
0x18019b161  mov     [rsp+268h+var_240], ebx
0x18019b165  mov     [rsp+268h+var_248], 22h ; '"'
0x18019b16d  lea     r9, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_System02_NodeList
0x18019b174  mov     r8, [rsi+40h]
0x18019b178  mov     rdx, [rsi+50h]
0x18019b17c  mov     rcx, r15
0x18019b17f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019b184  mov     r14d, eax
0x18019b187  test    eax, eax
0x18019b189  jz      short loc_18019B190
0x18019b18b  jmp     loc_18019BA53
0x18019b190  lea     rax, [rsp+268h+var_218]
0x18019b195  mov     [rsp+268h+var_1F0], rax
0x18019b19a  mov     r12d, 1
0x18019b1a0  mov     [rsp+268h+var_1E8], r12b
0x18019b1a8  mov     rdi, [rsp+268h+var_218]
0x18019b1ad  test    rdi, rdi
0x18019b1b0  jnz     short loc_18019B1BA
0x18019b1b2  mov     r14d, r12d
0x18019b1b5  jmp     loc_18019BA53
0x18019b1ba  mov     r9d, 22h ; '"'; unsigned int
0x18019b1c0  lea     r8, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019b1c7  mov     rdx, rsi; struct _MI_Instance *
0x18019b1ca  mov     rcx, rdi; this
0x18019b1cd  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019b1d2  mov     rax, [rdi]
0x18019b1d5  mov     rcx, rdi
0x18019b1d8  mov     rax, [rax+10h]
0x18019b1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b1e1  mov     r14d, eax
0x18019b1e4  test    eax, eax
0x18019b1e6  jz      short loc_18019B206
0x18019b1e8  mov     rcx, [rsp+268h+var_218]
0x18019b1ed  test    rcx, rcx
0x18019b1f0  jz      short loc_18019B201
0x18019b1f2  mov     rax, [rcx]
0x18019b1f5  mov     edx, r12d
0x18019b1f8  mov     rax, [rax]
0x18019b1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b200  nop
0x18019b201  jmp     loc_18019BA53
0x18019b206  mov     rax, [rdi]
0x18019b209  mov     rcx, rdi
0x18019b20c  mov     rax, [rax+8]
0x18019b210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b215  mov     r14d, eax
0x18019b218  test    eax, eax
0x18019b21a  jz      short loc_18019B23A
0x18019b21c  mov     rcx, [rsp+268h+var_218]
0x18019b221  test    rcx, rcx
0x18019b224  jz      short loc_18019B235
0x18019b226  mov     rax, [rcx]
0x18019b229  mov     edx, r12d
0x18019b22c  mov     rax, [rax]
0x18019b22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b234  nop
0x18019b235  jmp     loc_18019BA53
0x18019b23a  lea     r8, [rsp+268h+instance]; instance
0x18019b242  lea     rdx, MDM_Policy_Result01_System02_rtti; classDecl
0x18019b249  mov     rcx, r15; context
0x18019b24c  call    MI_Context_ConstructInstance
0x18019b251  mov     r14d, eax
0x18019b254  test    eax, eax
0x18019b256  jz      short loc_18019B276
0x18019b258  mov     rcx, [rsp+268h+var_218]
0x18019b25d  test    rcx, rcx
0x18019b260  jz      short loc_18019B271
0x18019b262  mov     rax, [rcx]
0x18019b265  mov     edx, r12d
0x18019b268  mov     rax, [rax]
0x18019b26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b270  nop
0x18019b271  jmp     loc_18019BA53
0x18019b276  mov     [rsp+268h+var_220], r12b
0x18019b27b  mov     rdx, [rsi+40h]
0x18019b27f  lea     rcx, [rsp+268h+instance]
0x18019b287  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019b28c  mov     rdx, [rsi+50h]
0x18019b290  lea     rcx, [rsp+268h+instance]
0x18019b298  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019b29d  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b2a2  lea     rdx, aAllowbuildprev; "AllowBuildPreview"
0x18019b2a9  mov     rcx, rdi; this
0x18019b2ac  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b2b1  test    eax, eax
0x18019b2b3  jnz     short loc_18019B2DA
0x18019b2b5  mov     rcx, [rsp+268h+String]; String
0x18019b2ba  test    rcx, rcx
0x18019b2bd  jz      short loc_18019B2DA
0x18019b2bf  call    cs:__imp__wtoi
0x18019b2c6  nop     dword ptr [rax+rax+00h]
0x18019b2cb  mov     [rsp+268h+var_158], eax
0x18019b2d2  mov     [rsp+268h+var_154], r12b
0x18019b2da  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b2df  lea     rdx, aAllowcommercia; "AllowCommercialDataPipeline"
0x18019b2e6  mov     rcx, rdi; this
0x18019b2e9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b2ee  test    eax, eax
0x18019b2f0  jnz     short loc_18019B317
0x18019b2f2  mov     rcx, [rsp+268h+String]; String
0x18019b2f7  test    rcx, rcx
0x18019b2fa  jz      short loc_18019B317
0x18019b2fc  call    cs:__imp__wtoi
0x18019b303  nop     dword ptr [rax+rax+00h]
0x18019b308  mov     [rsp+268h+var_150], eax
0x18019b30f  mov     [rsp+268h+var_14C], r12b
0x18019b317  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b31c  lea     rdx, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x18019b323  mov     rcx, rdi; this
0x18019b326  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b32b  test    eax, eax
0x18019b32d  jnz     short loc_18019B354
0x18019b32f  mov     rcx, [rsp+268h+String]; String
0x18019b334  test    rcx, rcx
0x18019b337  jz      short loc_18019B354
0x18019b339  call    cs:__imp__wtoi
0x18019b340  nop     dword ptr [rax+rax+00h]
0x18019b345  mov     [rsp+268h+var_148], eax
0x18019b34c  mov     [rsp+268h+var_144], r12b
0x18019b354  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b359  lea     rdx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x18019b360  mov     rcx, rdi; this
0x18019b363  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b368  test    eax, eax
0x18019b36a  jnz     short loc_18019B391
0x18019b36c  mov     rcx, [rsp+268h+String]; String
0x18019b371  test    rcx, rcx
0x18019b374  jz      short loc_18019B391
0x18019b376  call    cs:__imp__wtoi
0x18019b37d  nop     dword ptr [rax+rax+00h]
0x18019b382  mov     [rsp+268h+var_140], eax
0x18019b389  mov     [rsp+268h+var_13C], r12b
0x18019b391  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b396  lea     rdx, aAllowembeddedm; "AllowEmbeddedMode"
0x18019b39d  mov     rcx, rdi; this
0x18019b3a0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b3a5  test    eax, eax
0x18019b3a7  jnz     short loc_18019B3CE
0x18019b3a9  mov     rcx, [rsp+268h+String]; String
0x18019b3ae  test    rcx, rcx
0x18019b3b1  jz      short loc_18019B3CE
0x18019b3b3  call    cs:__imp__wtoi
0x18019b3ba  nop     dword ptr [rax+rax+00h]
0x18019b3bf  mov     [rsp+268h+var_138], eax
0x18019b3c6  mov     [rsp+268h+var_134], r12b
0x18019b3ce  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b3d3  lea     rdx, aAllowexperimen; "AllowExperimentation"
0x18019b3da  mov     rcx, rdi; this
0x18019b3dd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b3e2  test    eax, eax
0x18019b3e4  jnz     short loc_18019B40B
0x18019b3e6  mov     rcx, [rsp+268h+String]; String
0x18019b3eb  test    rcx, rcx
0x18019b3ee  jz      short loc_18019B40B
0x18019b3f0  call    cs:__imp__wtoi
0x18019b3f7  nop     dword ptr [rax+rax+00h]
0x18019b3fc  mov     [rsp+268h+var_130], eax
0x18019b403  mov     [rsp+268h+var_12C], r12b
0x18019b40b  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b410  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x18019b417  mov     rcx, rdi; this
0x18019b41a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b41f  test    eax, eax
0x18019b421  jnz     short loc_18019B448
0x18019b423  mov     rcx, [rsp+268h+String]; String
0x18019b428  test    rcx, rcx
0x18019b42b  jz      short loc_18019B448
0x18019b42d  call    cs:__imp__wtoi
0x18019b434  nop     dword ptr [rax+rax+00h]
0x18019b439  mov     [rsp+268h+var_128], eax
0x18019b440  mov     [rsp+268h+var_124], r12b
0x18019b448  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b44d  lea     rdx, aAllowlocation; "AllowLocation"
0x18019b454  mov     rcx, rdi; this
0x18019b457  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b45c  test    eax, eax
0x18019b45e  jnz     short loc_18019B485
0x18019b460  mov     rcx, [rsp+268h+String]; String
0x18019b465  test    rcx, rcx
0x18019b468  jz      short loc_18019B485
0x18019b46a  call    cs:__imp__wtoi
0x18019b471  nop     dword ptr [rax+rax+00h]
0x18019b476  mov     [rsp+268h+var_120], eax
0x18019b47d  mov     [rsp+268h+var_11C], r12b
0x18019b485  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b48a  lea     rdx, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x18019b491  mov     rcx, rdi; this
0x18019b494  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b499  test    eax, eax
0x18019b49b  jnz     short loc_18019B4C2
0x18019b49d  mov     rcx, [rsp+268h+String]; String
0x18019b4a2  test    rcx, rcx
0x18019b4a5  jz      short loc_18019B4C2
0x18019b4a7  call    cs:__imp__wtoi
0x18019b4ae  nop     dword ptr [rax+rax+00h]
0x18019b4b3  mov     [rsp+268h+var_118], eax
0x18019b4ba  mov     [rsp+268h+var_114], r12b
0x18019b4c2  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b4c7  lea     rdx, aAllowstorageca; "AllowStorageCard"
0x18019b4ce  mov     rcx, rdi; this
0x18019b4d1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b4d6  test    eax, eax
0x18019b4d8  jnz     short loc_18019B4FF
0x18019b4da  mov     rcx, [rsp+268h+String]; String
0x18019b4df  test    rcx, rcx
0x18019b4e2  jz      short loc_18019B4FF
0x18019b4e4  call    cs:__imp__wtoi
0x18019b4eb  nop     dword ptr [rax+rax+00h]
0x18019b4f0  mov     [rsp+268h+var_110], eax
0x18019b4f7  mov     [rsp+268h+var_10C], r12b
0x18019b4ff  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b504  lea     rdx, aAllowtelemetry; "AllowTelemetry"
0x18019b50b  mov     rcx, rdi; this
0x18019b50e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b513  test    eax, eax
0x18019b515  jnz     short loc_18019B53C
0x18019b517  mov     rcx, [rsp+268h+String]; String
0x18019b51c  test    rcx, rcx
0x18019b51f  jz      short loc_18019B53C
0x18019b521  call    cs:__imp__wtoi
0x18019b528  nop     dword ptr [rax+rax+00h]
0x18019b52d  mov     [rsp+268h+var_108], eax
0x18019b534  mov     [rsp+268h+var_104], r12b
0x18019b53c  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b541  lea     rdx, aAllowupdatecom; "AllowUpdateComplianceProcessing"
0x18019b548  mov     rcx, rdi; this
0x18019b54b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b550  test    eax, eax
0x18019b552  jnz     short loc_18019B579
0x18019b554  mov     rcx, [rsp+268h+String]; String
0x18019b559  test    rcx, rcx
0x18019b55c  jz      short loc_18019B579
0x18019b55e  call    cs:__imp__wtoi
  ... truncated ...
```
