# MDM_Policy_Result01_System02_InvokeGetInstance

- ea: `0x18019b5a4`
- end: `0x18019bfca`
- name: `MDM_Policy_Result01_System02_InvokeGetInstance`
- size: `2598`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180199b70`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x180005114`
- `0x18000529c`
- `0x180005424`
- `0x1800058d8`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18019b5a4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18019b843`
- `msvcrt!_wtoi` at `0x18019b87a`
- `msvcrt!_wtoi` at `0x18019b8b1`
- `msvcrt!_wtoi` at `0x18019b8e8`
- `msvcrt!_wtoi` at `0x18019b91f`
- `msvcrt!_wtoi` at `0x18019b956`
- `msvcrt!_wtoi` at `0x18019b98d`
- `msvcrt!_wtoi` at `0x18019b9c4`
- `msvcrt!_wtoi` at `0x18019b9fb`
- `msvcrt!_wtoi` at `0x18019ba32`
- `msvcrt!_wtoi` at `0x18019ba69`
- `msvcrt!_wtoi` at `0x18019baa0`
- `msvcrt!_wtoi` at `0x18019bad7`
- `msvcrt!_wtoi` at `0x18019bb0e`
- `msvcrt!_wtoi` at `0x18019bba3`
- `msvcrt!_wtoi` at `0x18019bbda`
- `msvcrt!_wtoi` at `0x18019bc11`
- `msvcrt!_wtoi` at `0x18019bc48`
- `msvcrt!_wtoi` at `0x18019bc7f`
- `msvcrt!_wtoi` at `0x18019bcb6`
- `msvcrt!_wtoi` at `0x18019bced`
- `msvcrt!_wtoi` at `0x18019bd24`
- `msvcrt!_wtoi` at `0x18019bd8a`
- `msvcrt!_wtoi` at `0x18019bdc1`
- `msvcrt!_wtoi` at `0x18019bdf8`
- `msvcrt!_wtoi` at `0x18019be2f`
- `msvcrt!_wtoi` at `0x18019be66`
- `msvcrt!_wtoi` at `0x18019becc`
- `msvcrt!_wtoi` at `0x18019b843`
- `msvcrt!_wtoi` at `0x18019b87a`
- `msvcrt!_wtoi` at `0x18019b8b1`
- `msvcrt!_wtoi` at `0x18019b8e8`
- `msvcrt!_wtoi` at `0x18019b91f`
- `msvcrt!_wtoi` at `0x18019b956`
- `msvcrt!_wtoi` at `0x18019b98d`
- `msvcrt!_wtoi` at `0x18019b9c4`
- `msvcrt!_wtoi` at `0x18019b9fb`
- `msvcrt!_wtoi` at `0x18019ba32`
- `msvcrt!_wtoi` at `0x18019ba69`
- `msvcrt!_wtoi` at `0x18019baa0`
- `msvcrt!_wtoi` at `0x18019bad7`
- `msvcrt!_wtoi` at `0x18019bb0e`
- `msvcrt!_wtoi` at `0x18019bba3`
- `msvcrt!_wtoi` at `0x18019bbda`
- `msvcrt!_wtoi` at `0x18019bc11`
- `msvcrt!_wtoi` at `0x18019bc48`
- `msvcrt!_wtoi` at `0x18019bc7f`
- `msvcrt!_wtoi` at `0x18019bcb6`
- `msvcrt!_wtoi` at `0x18019bced`
- `msvcrt!_wtoi` at `0x18019bd24`
- `msvcrt!_wtoi` at `0x18019bd8a`
- `msvcrt!_wtoi` at `0x18019bdc1`
- `msvcrt!_wtoi` at `0x18019bdf8`
- `msvcrt!_wtoi` at `0x18019be2f`
- `msvcrt!_wtoi` at `0x18019be66`
- `msvcrt!_wtoi` at `0x18019becc`

## string_xrefs

- `0x18019b85d`: `AllowCommercialDataPipeline`
- `0x18019ba83`: `AllowUpdateComplianceProcessing`
- `0x18019bb57`: `ConfigureMicrosoft365UploadEndpoint`
- `0x18019bb86`: `ConfigureTelemetryOptInChangeNotification`
- `0x18019bbbd`: `ConfigureTelemetryOptInSettingsUx`
- `0x18019bbf4`: `DisableDeviceDelete`
- `0x18019bc62`: `DisableDirectXDatabaseUpdate`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_System02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_System02_NodeList,
           0x22u,
           0,
           &v10);
    if ( !v5 )
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
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowBuildPreview",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowCommercialDataPipeline",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowDesktopAnalyticsProcessing",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowDeviceNameInDiagnosticData",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowEmbeddedMode",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowExperimentation",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowFontProviders",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowLocation",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowMicrosoftManagedDesktopProcessing",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowStorageCard",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowTelemetry",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowUpdateComplianceProcessing",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowUserToResetPhone",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowWUfBCloudProcessing",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"BootStartDriverInitialization",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigureMicrosoft365UploadEndpoint",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigureTelemetryOptInChangeNotification",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigureTelemetryOptInSettingsUx",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableDeviceDelete",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableDiagnosticDataViewer",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableDirectXDatabaseUpdate",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableEnterpriseAuthProxy",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableOneDriveFileSync",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableOneSettingsDownloads",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableSystemRestore",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableOneSettingsAuditing",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"LimitDiagnosticLogCollection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"LimitDumpCollection",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"TelemetryProxy",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"TurnOffFileHistory",
                                    (const unsigned __int16 **)&String)
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
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
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
  return v5;
}

```

## disassembly

```asm
0x18019b5a4  mov     [rsp+arg_10], rbx
0x18019b5a9  push    rsi
0x18019b5aa  push    rdi
0x18019b5ab  push    r12
0x18019b5ad  push    r14
0x18019b5af  push    r15
0x18019b5b1  sub     rsp, 240h
0x18019b5b8  mov     rax, cs:__security_cookie
0x18019b5bf  xor     rax, rsp
0x18019b5c2  mov     [rsp+268h+var_38], rax
0x18019b5ca  mov     rsi, rdx
0x18019b5cd  mov     r15, rcx
0x18019b5d0  xor     ebx, ebx
0x18019b5d2  mov     [rsp+268h+String], rbx
0x18019b5d7  xor     edx, edx; Val
0x18019b5d9  mov     r8d, 180h; Size
0x18019b5df  lea     rcx, [rsp+268h+instance]; void *
0x18019b5e7  call    memset_0
0x18019b5ec  mov     [rsp+268h+var_1E0], ebx
0x18019b5f3  mov     [rsp+268h+var_1DC], bl
0x18019b5fa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019b601  mov     [rsp+268h+var_210], rax
0x18019b606  lea     rax, [rsp+268h+var_1E0]
0x18019b60e  mov     [rsp+268h+var_208], rax
0x18019b613  lea     rax, aMdmPolicyResul_159; "MDM_Policy_Result01_System02"
0x18019b61a  mov     [rsp+268h+var_200], rax
0x18019b61f  lea     rcx, [rsp+268h+var_1E0]
0x18019b627  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019b62c  mov     eax, cs:dword_180380B68
0x18019b632  cmp     eax, 5
0x18019b635  jbe     short loc_18019B6A6
0x18019b637  mov     rdx, 200000000000h
0x18019b641  lea     rcx, dword_180380B68
0x18019b648  call    _tlgKeywordOn
0x18019b64d  test    al, al
0x18019b64f  jz      short loc_18019B6A6
0x18019b651  cmp     [rsp+268h+var_1DC], bl
0x18019b658  jz      short loc_18019B688
0x18019b65a  cmp     [rsp+268h+var_1C8], ebx
0x18019b661  jnz     short loc_18019B67E
0x18019b663  cmp     [rsp+268h+var_1C4], ebx
0x18019b66a  jnz     short loc_18019B67E
0x18019b66c  cmp     [rsp+268h+var_1C0], ebx
0x18019b673  jnz     short loc_18019B67E
0x18019b675  cmp     [rsp+268h+var_1BC], ebx
0x18019b67c  jz      short loc_18019B688
0x18019b67e  lea     r9, [rsp+268h+var_1C8]
0x18019b686  jmp     short loc_18019B68B
0x18019b688  mov     r9, rbx
0x18019b68b  lea     r8, [rsp+268h+var_1D8]
0x18019b693  lea     rdx, dword_180359FC4
0x18019b69a  lea     rcx, dword_180380B68
0x18019b6a1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019b6a6  cmp     [rsi+48h], bl
0x18019b6a9  jz      loc_18019BF29
0x18019b6af  mov     [rsp+268h+var_220], bl
0x18019b6b3  cmp     [rsi+58h], bl
0x18019b6b6  jz      loc_18019BF29
0x18019b6bc  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019b6c0  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019b6c4  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18019b6cb  lea     rcx, [rsp+268h+var_210]; this
0x18019b6d0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019b6d5  nop
0x18019b6d6  mov     [rsp+268h+var_218], rbx
0x18019b6db  lea     rax, [rsp+268h+var_218]
0x18019b6e0  mov     [rsp+268h+var_238], rax
0x18019b6e5  mov     [rsp+268h+var_240], ebx
0x18019b6e9  mov     [rsp+268h+var_248], 22h ; '"'
0x18019b6f1  lea     r9, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_System02_NodeList
0x18019b6f8  mov     r8, [rsi+40h]
0x18019b6fc  mov     rdx, [rsi+50h]
0x18019b700  mov     rcx, r15
0x18019b703  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019b708  mov     r14d, eax
0x18019b70b  test    eax, eax
0x18019b70d  jz      short loc_18019B714
0x18019b70f  jmp     loc_18019BF2F
0x18019b714  lea     rax, [rsp+268h+var_218]
0x18019b719  mov     [rsp+268h+var_1F0], rax
0x18019b71e  mov     r12d, 1
0x18019b724  mov     [rsp+268h+var_1E8], r12b
0x18019b72c  mov     rdi, [rsp+268h+var_218]
0x18019b731  test    rdi, rdi
0x18019b734  jnz     short loc_18019B73E
0x18019b736  mov     r14d, r12d
0x18019b739  jmp     loc_18019BF2F
0x18019b73e  mov     r9d, 22h ; '"'; unsigned int
0x18019b744  lea     r8, ?MDM_Policy_Result01_System02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019b74b  mov     rdx, rsi; struct _MI_Instance *
0x18019b74e  mov     rcx, rdi; this
0x18019b751  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019b756  mov     rax, [rdi]
0x18019b759  mov     rcx, rdi
0x18019b75c  mov     rax, [rax+10h]
0x18019b760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b765  mov     r14d, eax
0x18019b768  test    eax, eax
0x18019b76a  jz      short loc_18019B78A
0x18019b76c  mov     rcx, [rsp+268h+var_218]
0x18019b771  test    rcx, rcx
0x18019b774  jz      short loc_18019B785
0x18019b776  mov     rax, [rcx]
0x18019b779  mov     edx, r12d
0x18019b77c  mov     rax, [rax]
0x18019b77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b784  nop
0x18019b785  jmp     loc_18019BF2F
0x18019b78a  mov     rax, [rdi]
0x18019b78d  mov     rcx, rdi
0x18019b790  mov     rax, [rax+8]
0x18019b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b799  mov     r14d, eax
0x18019b79c  test    eax, eax
0x18019b79e  jz      short loc_18019B7BE
0x18019b7a0  mov     rcx, [rsp+268h+var_218]
0x18019b7a5  test    rcx, rcx
0x18019b7a8  jz      short loc_18019B7B9
0x18019b7aa  mov     rax, [rcx]
0x18019b7ad  mov     edx, r12d
0x18019b7b0  mov     rax, [rax]
0x18019b7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b7b8  nop
0x18019b7b9  jmp     loc_18019BF2F
0x18019b7be  lea     r8, [rsp+268h+instance]; instance
0x18019b7c6  lea     rdx, MDM_Policy_Result01_System02_rtti; classDecl
0x18019b7cd  mov     rcx, r15; context
0x18019b7d0  call    MI_Context_ConstructInstance
0x18019b7d5  mov     r14d, eax
0x18019b7d8  test    eax, eax
0x18019b7da  jz      short loc_18019B7FA
0x18019b7dc  mov     rcx, [rsp+268h+var_218]
0x18019b7e1  test    rcx, rcx
0x18019b7e4  jz      short loc_18019B7F5
0x18019b7e6  mov     rax, [rcx]
0x18019b7e9  mov     edx, r12d
0x18019b7ec  mov     rax, [rax]
0x18019b7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b7f4  nop
0x18019b7f5  jmp     loc_18019BF2F
0x18019b7fa  mov     [rsp+268h+var_220], r12b
0x18019b7ff  mov     rdx, [rsi+40h]
0x18019b803  lea     rcx, [rsp+268h+instance]
0x18019b80b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18019b810  mov     rdx, [rsi+50h]
0x18019b814  lea     rcx, [rsp+268h+instance]
0x18019b81c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18019b821  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b826  lea     rdx, aAllowbuildprev; "AllowBuildPreview"
0x18019b82d  mov     rcx, rdi; this
0x18019b830  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b835  test    eax, eax
0x18019b837  jnz     short loc_18019B858
0x18019b839  mov     rcx, [rsp+268h+String]; String
0x18019b83e  test    rcx, rcx
0x18019b841  jz      short loc_18019B858
0x18019b843  call    cs:__imp__wtoi
0x18019b849  mov     [rsp+268h+var_158], eax
0x18019b850  mov     [rsp+268h+var_154], r12b
0x18019b858  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b85d  lea     rdx, aAllowcommercia; "AllowCommercialDataPipeline"
0x18019b864  mov     rcx, rdi; this
0x18019b867  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b86c  test    eax, eax
0x18019b86e  jnz     short loc_18019B88F
0x18019b870  mov     rcx, [rsp+268h+String]; String
0x18019b875  test    rcx, rcx
0x18019b878  jz      short loc_18019B88F
0x18019b87a  call    cs:__imp__wtoi
0x18019b880  mov     [rsp+268h+var_150], eax
0x18019b887  mov     [rsp+268h+var_14C], r12b
0x18019b88f  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b894  lea     rdx, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x18019b89b  mov     rcx, rdi; this
0x18019b89e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b8a3  test    eax, eax
0x18019b8a5  jnz     short loc_18019B8C6
0x18019b8a7  mov     rcx, [rsp+268h+String]; String
0x18019b8ac  test    rcx, rcx
0x18019b8af  jz      short loc_18019B8C6
0x18019b8b1  call    cs:__imp__wtoi
0x18019b8b7  mov     [rsp+268h+var_148], eax
0x18019b8be  mov     [rsp+268h+var_144], r12b
0x18019b8c6  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b8cb  lea     rdx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x18019b8d2  mov     rcx, rdi; this
0x18019b8d5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b8da  test    eax, eax
0x18019b8dc  jnz     short loc_18019B8FD
0x18019b8de  mov     rcx, [rsp+268h+String]; String
0x18019b8e3  test    rcx, rcx
0x18019b8e6  jz      short loc_18019B8FD
0x18019b8e8  call    cs:__imp__wtoi
0x18019b8ee  mov     [rsp+268h+var_140], eax
0x18019b8f5  mov     [rsp+268h+var_13C], r12b
0x18019b8fd  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b902  lea     rdx, aAllowembeddedm; "AllowEmbeddedMode"
0x18019b909  mov     rcx, rdi; this
0x18019b90c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b911  test    eax, eax
0x18019b913  jnz     short loc_18019B934
0x18019b915  mov     rcx, [rsp+268h+String]; String
0x18019b91a  test    rcx, rcx
0x18019b91d  jz      short loc_18019B934
0x18019b91f  call    cs:__imp__wtoi
0x18019b925  mov     [rsp+268h+var_138], eax
0x18019b92c  mov     [rsp+268h+var_134], r12b
0x18019b934  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b939  lea     rdx, aAllowexperimen; "AllowExperimentation"
0x18019b940  mov     rcx, rdi; this
0x18019b943  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b948  test    eax, eax
0x18019b94a  jnz     short loc_18019B96B
0x18019b94c  mov     rcx, [rsp+268h+String]; String
0x18019b951  test    rcx, rcx
0x18019b954  jz      short loc_18019B96B
0x18019b956  call    cs:__imp__wtoi
0x18019b95c  mov     [rsp+268h+var_130], eax
0x18019b963  mov     [rsp+268h+var_12C], r12b
0x18019b96b  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b970  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x18019b977  mov     rcx, rdi; this
0x18019b97a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b97f  test    eax, eax
0x18019b981  jnz     short loc_18019B9A2
0x18019b983  mov     rcx, [rsp+268h+String]; String
0x18019b988  test    rcx, rcx
0x18019b98b  jz      short loc_18019B9A2
0x18019b98d  call    cs:__imp__wtoi
0x18019b993  mov     [rsp+268h+var_128], eax
0x18019b99a  mov     [rsp+268h+var_124], r12b
0x18019b9a2  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b9a7  lea     rdx, aAllowlocation; "AllowLocation"
0x18019b9ae  mov     rcx, rdi; this
0x18019b9b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b9b6  test    eax, eax
0x18019b9b8  jnz     short loc_18019B9D9
0x18019b9ba  mov     rcx, [rsp+268h+String]; String
0x18019b9bf  test    rcx, rcx
0x18019b9c2  jz      short loc_18019B9D9
0x18019b9c4  call    cs:__imp__wtoi
0x18019b9ca  mov     [rsp+268h+var_120], eax
0x18019b9d1  mov     [rsp+268h+var_11C], r12b
0x18019b9d9  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019b9de  lea     rdx, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x18019b9e5  mov     rcx, rdi; this
0x18019b9e8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019b9ed  test    eax, eax
0x18019b9ef  jnz     short loc_18019BA10
0x18019b9f1  mov     rcx, [rsp+268h+String]; String
0x18019b9f6  test    rcx, rcx
0x18019b9f9  jz      short loc_18019BA10
0x18019b9fb  call    cs:__imp__wtoi
0x18019ba01  mov     [rsp+268h+var_118], eax
0x18019ba08  mov     [rsp+268h+var_114], r12b
0x18019ba10  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019ba15  lea     rdx, aAllowstorageca; "AllowStorageCard"
0x18019ba1c  mov     rcx, rdi; this
0x18019ba1f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019ba24  test    eax, eax
0x18019ba26  jnz     short loc_18019BA47
0x18019ba28  mov     rcx, [rsp+268h+String]; String
0x18019ba2d  test    rcx, rcx
0x18019ba30  jz      short loc_18019BA47
0x18019ba32  call    cs:__imp__wtoi
0x18019ba38  mov     [rsp+268h+var_110], eax
0x18019ba3f  mov     [rsp+268h+var_10C], r12b
0x18019ba47  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019ba4c  lea     rdx, aAllowtelemetry; "AllowTelemetry"
0x18019ba53  mov     rcx, rdi; this
0x18019ba56  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019ba5b  test    eax, eax
0x18019ba5d  jnz     short loc_18019BA7E
0x18019ba5f  mov     rcx, [rsp+268h+String]; String
0x18019ba64  test    rcx, rcx
0x18019ba67  jz      short loc_18019BA7E
0x18019ba69  call    cs:__imp__wtoi
0x18019ba6f  mov     [rsp+268h+var_108], eax
0x18019ba76  mov     [rsp+268h+var_104], r12b
0x18019ba7e  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019ba83  lea     rdx, aAllowupdatecom; "AllowUpdateComplianceProcessing"
0x18019ba8a  mov     rcx, rdi; this
0x18019ba8d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019ba92  test    eax, eax
0x18019ba94  jnz     short loc_18019BAB5
0x18019ba96  mov     rcx, [rsp+268h+String]; String
0x18019ba9b  test    rcx, rcx
0x18019ba9e  jz      short loc_18019BAB5
0x18019baa0  call    cs:__imp__wtoi
0x18019baa6  mov     [rsp+268h+var_100], eax
0x18019baad  mov     [rsp+268h+var_FC], r12b
0x18019bab5  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x18019baba  lea     rdx, aAllowusertores; "AllowUserToResetPhone"
0x18019bac1  mov     rcx, rdi; this
0x18019bac4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019bac9  test    eax, eax
0x18019bacb  jnz     short loc_18019BAEC
0x18019bacd  mov     rcx, [rsp+268h+String]; String
0x18019bad2  test    rcx, rcx
0x18019bad5  jz      short loc_18019BAEC
  ... truncated ...
```
