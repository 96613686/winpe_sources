# MDM_Policy_Config01_System02_InvokeGetInstance

- ea: `0x1800e41e4`
- end: `0x1800e4c0a`
- name: `MDM_Policy_Config01_System02_InvokeGetInstance`
- size: `2598`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e27b0`

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
- `0x1800e41e4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e4483`
- `msvcrt!_wtoi` at `0x1800e44ba`
- `msvcrt!_wtoi` at `0x1800e44f1`
- `msvcrt!_wtoi` at `0x1800e4528`
- `msvcrt!_wtoi` at `0x1800e455f`
- `msvcrt!_wtoi` at `0x1800e4596`
- `msvcrt!_wtoi` at `0x1800e45cd`
- `msvcrt!_wtoi` at `0x1800e4604`
- `msvcrt!_wtoi` at `0x1800e463b`
- `msvcrt!_wtoi` at `0x1800e4672`
- `msvcrt!_wtoi` at `0x1800e46a9`
- `msvcrt!_wtoi` at `0x1800e46e0`
- `msvcrt!_wtoi` at `0x1800e4717`
- `msvcrt!_wtoi` at `0x1800e474e`
- `msvcrt!_wtoi` at `0x1800e47e3`
- `msvcrt!_wtoi` at `0x1800e481a`
- `msvcrt!_wtoi` at `0x1800e4851`
- `msvcrt!_wtoi` at `0x1800e4888`
- `msvcrt!_wtoi` at `0x1800e48bf`
- `msvcrt!_wtoi` at `0x1800e48f6`
- `msvcrt!_wtoi` at `0x1800e492d`
- `msvcrt!_wtoi` at `0x1800e4964`
- `msvcrt!_wtoi` at `0x1800e49ca`
- `msvcrt!_wtoi` at `0x1800e4a01`
- `msvcrt!_wtoi` at `0x1800e4a38`
- `msvcrt!_wtoi` at `0x1800e4a6f`
- `msvcrt!_wtoi` at `0x1800e4aa6`
- `msvcrt!_wtoi` at `0x1800e4b0c`
- `msvcrt!_wtoi` at `0x1800e4483`
- `msvcrt!_wtoi` at `0x1800e44ba`
- `msvcrt!_wtoi` at `0x1800e44f1`
- `msvcrt!_wtoi` at `0x1800e4528`
- `msvcrt!_wtoi` at `0x1800e455f`
- `msvcrt!_wtoi` at `0x1800e4596`
- `msvcrt!_wtoi` at `0x1800e45cd`
- `msvcrt!_wtoi` at `0x1800e4604`
- `msvcrt!_wtoi` at `0x1800e463b`
- `msvcrt!_wtoi` at `0x1800e4672`
- `msvcrt!_wtoi` at `0x1800e46a9`
- `msvcrt!_wtoi` at `0x1800e46e0`
- `msvcrt!_wtoi` at `0x1800e4717`
- `msvcrt!_wtoi` at `0x1800e474e`
- `msvcrt!_wtoi` at `0x1800e47e3`
- `msvcrt!_wtoi` at `0x1800e481a`
- `msvcrt!_wtoi` at `0x1800e4851`
- `msvcrt!_wtoi` at `0x1800e4888`
- `msvcrt!_wtoi` at `0x1800e48bf`
- `msvcrt!_wtoi` at `0x1800e48f6`
- `msvcrt!_wtoi` at `0x1800e492d`
- `msvcrt!_wtoi` at `0x1800e4964`
- `msvcrt!_wtoi` at `0x1800e49ca`
- `msvcrt!_wtoi` at `0x1800e4a01`
- `msvcrt!_wtoi` at `0x1800e4a38`
- `msvcrt!_wtoi` at `0x1800e4a6f`
- `msvcrt!_wtoi` at `0x1800e4aa6`
- `msvcrt!_wtoi` at `0x1800e4b0c`

## string_xrefs

- `0x1800e449d`: `AllowCommercialDataPipeline`
- `0x1800e46c3`: `AllowUpdateComplianceProcessing`
- `0x1800e4797`: `ConfigureMicrosoft365UploadEndpoint`
- `0x1800e47c6`: `ConfigureTelemetryOptInChangeNotification`
- `0x1800e47fd`: `ConfigureTelemetryOptInSettingsUx`
- `0x1800e4834`: `DisableDeviceDelete`
- `0x1800e48a2`: `DisableDirectXDatabaseUpdate`
- `0x1800e4253`: `MDM_Policy_Config01_System02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_System02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v11[2] = "MDM_Policy_Config01_System02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033F5D4,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = 4;
    goto LABEL_125;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_System02_NodeList,
         0x22u,
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
      goto LABEL_125;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_System02_NodeList,
      0x22u);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_125;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_125;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_125;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_System02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_125;
      goto LABEL_24;
    }
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
LABEL_125:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180369FDF,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x1800e41e4  mov     [rsp+arg_10], rbx
0x1800e41e9  push    rsi
0x1800e41ea  push    rdi
0x1800e41eb  push    r12
0x1800e41ed  push    r14
0x1800e41ef  push    r15
0x1800e41f1  sub     rsp, 240h
0x1800e41f8  mov     rax, cs:__security_cookie
0x1800e41ff  xor     rax, rsp
0x1800e4202  mov     [rsp+268h+var_38], rax
0x1800e420a  mov     rsi, rdx
0x1800e420d  mov     r15, rcx
0x1800e4210  xor     ebx, ebx
0x1800e4212  mov     [rsp+268h+String], rbx
0x1800e4217  xor     edx, edx; Val
0x1800e4219  mov     r8d, 180h; Size
0x1800e421f  lea     rcx, [rsp+268h+instance]; void *
0x1800e4227  call    memset_0
0x1800e422c  mov     [rsp+268h+var_1E0], ebx
0x1800e4233  mov     [rsp+268h+var_1DC], bl
0x1800e423a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e4241  mov     [rsp+268h+var_210], rax
0x1800e4246  lea     rax, [rsp+268h+var_1E0]
0x1800e424e  mov     [rsp+268h+var_208], rax
0x1800e4253  lea     rax, aMdmPolicyConfi_18; "MDM_Policy_Config01_System02"
0x1800e425a  mov     [rsp+268h+var_200], rax
0x1800e425f  lea     rcx, [rsp+268h+var_1E0]
0x1800e4267  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e426c  mov     eax, cs:dword_180380B68
0x1800e4272  cmp     eax, 5
0x1800e4275  jbe     short loc_1800E42E6
0x1800e4277  mov     rdx, 200000000000h
0x1800e4281  lea     rcx, dword_180380B68
0x1800e4288  call    _tlgKeywordOn
0x1800e428d  test    al, al
0x1800e428f  jz      short loc_1800E42E6
0x1800e4291  cmp     [rsp+268h+var_1DC], bl
0x1800e4298  jz      short loc_1800E42C8
0x1800e429a  cmp     [rsp+268h+var_1C8], ebx
0x1800e42a1  jnz     short loc_1800E42BE
0x1800e42a3  cmp     [rsp+268h+var_1C4], ebx
0x1800e42aa  jnz     short loc_1800E42BE
0x1800e42ac  cmp     [rsp+268h+var_1C0], ebx
0x1800e42b3  jnz     short loc_1800E42BE
0x1800e42b5  cmp     [rsp+268h+var_1BC], ebx
0x1800e42bc  jz      short loc_1800E42C8
0x1800e42be  lea     r9, [rsp+268h+var_1C8]
0x1800e42c6  jmp     short loc_1800E42CB
0x1800e42c8  mov     r9, rbx
0x1800e42cb  lea     r8, [rsp+268h+var_1D8]
0x1800e42d3  lea     rdx, dword_18033F5D4
0x1800e42da  lea     rcx, dword_180380B68
0x1800e42e1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e42e6  cmp     [rsi+48h], bl
0x1800e42e9  jz      loc_1800E4B69
0x1800e42ef  mov     [rsp+268h+var_220], bl
0x1800e42f3  cmp     [rsi+58h], bl
0x1800e42f6  jz      loc_1800E4B69
0x1800e42fc  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e4300  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e4304  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e430b  lea     rcx, [rsp+268h+var_210]; this
0x1800e4310  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e4315  nop
0x1800e4316  mov     [rsp+268h+var_218], rbx
0x1800e431b  lea     rax, [rsp+268h+var_218]
0x1800e4320  mov     [rsp+268h+var_238], rax
0x1800e4325  mov     [rsp+268h+var_240], ebx
0x1800e4329  mov     [rsp+268h+var_248], 22h ; '"'
0x1800e4331  lea     r9, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_System02_NodeList
0x1800e4338  mov     r8, [rsi+40h]
0x1800e433c  mov     rdx, [rsi+50h]
0x1800e4340  mov     rcx, r15
0x1800e4343  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e4348  mov     r14d, eax
0x1800e434b  test    eax, eax
0x1800e434d  jz      short loc_1800E4354
0x1800e434f  jmp     loc_1800E4B6F
0x1800e4354  lea     rax, [rsp+268h+var_218]
0x1800e4359  mov     [rsp+268h+var_1F0], rax
0x1800e435e  mov     r12d, 1
0x1800e4364  mov     [rsp+268h+var_1E8], r12b
0x1800e436c  mov     rdi, [rsp+268h+var_218]
0x1800e4371  test    rdi, rdi
0x1800e4374  jnz     short loc_1800E437E
0x1800e4376  mov     r14d, r12d
0x1800e4379  jmp     loc_1800E4B6F
0x1800e437e  mov     r9d, 22h ; '"'; unsigned int
0x1800e4384  lea     r8, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e438b  mov     rdx, rsi; struct _MI_Instance *
0x1800e438e  mov     rcx, rdi; this
0x1800e4391  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e4396  mov     rax, [rdi]
0x1800e4399  mov     rcx, rdi
0x1800e439c  mov     rax, [rax+10h]
0x1800e43a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e43a5  mov     r14d, eax
0x1800e43a8  test    eax, eax
0x1800e43aa  jz      short loc_1800E43CA
0x1800e43ac  mov     rcx, [rsp+268h+var_218]
0x1800e43b1  test    rcx, rcx
0x1800e43b4  jz      short loc_1800E43C5
0x1800e43b6  mov     rax, [rcx]
0x1800e43b9  mov     edx, r12d
0x1800e43bc  mov     rax, [rax]
0x1800e43bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e43c4  nop
0x1800e43c5  jmp     loc_1800E4B6F
0x1800e43ca  mov     rax, [rdi]
0x1800e43cd  mov     rcx, rdi
0x1800e43d0  mov     rax, [rax+8]
0x1800e43d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e43d9  mov     r14d, eax
0x1800e43dc  test    eax, eax
0x1800e43de  jz      short loc_1800E43FE
0x1800e43e0  mov     rcx, [rsp+268h+var_218]
0x1800e43e5  test    rcx, rcx
0x1800e43e8  jz      short loc_1800E43F9
0x1800e43ea  mov     rax, [rcx]
0x1800e43ed  mov     edx, r12d
0x1800e43f0  mov     rax, [rax]
0x1800e43f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e43f8  nop
0x1800e43f9  jmp     loc_1800E4B6F
0x1800e43fe  lea     r8, [rsp+268h+instance]; instance
0x1800e4406  lea     rdx, MDM_Policy_Config01_System02_rtti; classDecl
0x1800e440d  mov     rcx, r15; context
0x1800e4410  call    MI_Context_ConstructInstance
0x1800e4415  mov     r14d, eax
0x1800e4418  test    eax, eax
0x1800e441a  jz      short loc_1800E443A
0x1800e441c  mov     rcx, [rsp+268h+var_218]
0x1800e4421  test    rcx, rcx
0x1800e4424  jz      short loc_1800E4435
0x1800e4426  mov     rax, [rcx]
0x1800e4429  mov     edx, r12d
0x1800e442c  mov     rax, [rax]
0x1800e442f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4434  nop
0x1800e4435  jmp     loc_1800E4B6F
0x1800e443a  mov     [rsp+268h+var_220], r12b
0x1800e443f  mov     rdx, [rsi+40h]
0x1800e4443  lea     rcx, [rsp+268h+instance]
0x1800e444b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e4450  mov     rdx, [rsi+50h]
0x1800e4454  lea     rcx, [rsp+268h+instance]
0x1800e445c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e4461  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e4466  lea     rdx, aAllowbuildprev; "AllowBuildPreview"
0x1800e446d  mov     rcx, rdi; this
0x1800e4470  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e4475  test    eax, eax
0x1800e4477  jnz     short loc_1800E4498
0x1800e4479  mov     rcx, [rsp+268h+String]; String
0x1800e447e  test    rcx, rcx
0x1800e4481  jz      short loc_1800E4498
0x1800e4483  call    cs:__imp__wtoi
0x1800e4489  mov     [rsp+268h+var_158], eax
0x1800e4490  mov     [rsp+268h+var_154], r12b
0x1800e4498  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e449d  lea     rdx, aAllowcommercia; "AllowCommercialDataPipeline"
0x1800e44a4  mov     rcx, rdi; this
0x1800e44a7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e44ac  test    eax, eax
0x1800e44ae  jnz     short loc_1800E44CF
0x1800e44b0  mov     rcx, [rsp+268h+String]; String
0x1800e44b5  test    rcx, rcx
0x1800e44b8  jz      short loc_1800E44CF
0x1800e44ba  call    cs:__imp__wtoi
0x1800e44c0  mov     [rsp+268h+var_150], eax
0x1800e44c7  mov     [rsp+268h+var_14C], r12b
0x1800e44cf  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e44d4  lea     rdx, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x1800e44db  mov     rcx, rdi; this
0x1800e44de  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e44e3  test    eax, eax
0x1800e44e5  jnz     short loc_1800E4506
0x1800e44e7  mov     rcx, [rsp+268h+String]; String
0x1800e44ec  test    rcx, rcx
0x1800e44ef  jz      short loc_1800E4506
0x1800e44f1  call    cs:__imp__wtoi
0x1800e44f7  mov     [rsp+268h+var_148], eax
0x1800e44fe  mov     [rsp+268h+var_144], r12b
0x1800e4506  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e450b  lea     rdx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800e4512  mov     rcx, rdi; this
0x1800e4515  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e451a  test    eax, eax
0x1800e451c  jnz     short loc_1800E453D
0x1800e451e  mov     rcx, [rsp+268h+String]; String
0x1800e4523  test    rcx, rcx
0x1800e4526  jz      short loc_1800E453D
0x1800e4528  call    cs:__imp__wtoi
0x1800e452e  mov     [rsp+268h+var_140], eax
0x1800e4535  mov     [rsp+268h+var_13C], r12b
0x1800e453d  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e4542  lea     rdx, aAllowembeddedm; "AllowEmbeddedMode"
0x1800e4549  mov     rcx, rdi; this
0x1800e454c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e4551  test    eax, eax
0x1800e4553  jnz     short loc_1800E4574
0x1800e4555  mov     rcx, [rsp+268h+String]; String
0x1800e455a  test    rcx, rcx
0x1800e455d  jz      short loc_1800E4574
0x1800e455f  call    cs:__imp__wtoi
0x1800e4565  mov     [rsp+268h+var_138], eax
0x1800e456c  mov     [rsp+268h+var_134], r12b
0x1800e4574  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e4579  lea     rdx, aAllowexperimen; "AllowExperimentation"
0x1800e4580  mov     rcx, rdi; this
0x1800e4583  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e4588  test    eax, eax
0x1800e458a  jnz     short loc_1800E45AB
0x1800e458c  mov     rcx, [rsp+268h+String]; String
0x1800e4591  test    rcx, rcx
0x1800e4594  jz      short loc_1800E45AB
0x1800e4596  call    cs:__imp__wtoi
0x1800e459c  mov     [rsp+268h+var_130], eax
0x1800e45a3  mov     [rsp+268h+var_12C], r12b
0x1800e45ab  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e45b0  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x1800e45b7  mov     rcx, rdi; this
0x1800e45ba  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e45bf  test    eax, eax
0x1800e45c1  jnz     short loc_1800E45E2
0x1800e45c3  mov     rcx, [rsp+268h+String]; String
0x1800e45c8  test    rcx, rcx
0x1800e45cb  jz      short loc_1800E45E2
0x1800e45cd  call    cs:__imp__wtoi
0x1800e45d3  mov     [rsp+268h+var_128], eax
0x1800e45da  mov     [rsp+268h+var_124], r12b
0x1800e45e2  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e45e7  lea     rdx, aAllowlocation; "AllowLocation"
0x1800e45ee  mov     rcx, rdi; this
0x1800e45f1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e45f6  test    eax, eax
0x1800e45f8  jnz     short loc_1800E4619
0x1800e45fa  mov     rcx, [rsp+268h+String]; String
0x1800e45ff  test    rcx, rcx
0x1800e4602  jz      short loc_1800E4619
0x1800e4604  call    cs:__imp__wtoi
0x1800e460a  mov     [rsp+268h+var_120], eax
0x1800e4611  mov     [rsp+268h+var_11C], r12b
0x1800e4619  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e461e  lea     rdx, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x1800e4625  mov     rcx, rdi; this
0x1800e4628  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e462d  test    eax, eax
0x1800e462f  jnz     short loc_1800E4650
0x1800e4631  mov     rcx, [rsp+268h+String]; String
0x1800e4636  test    rcx, rcx
0x1800e4639  jz      short loc_1800E4650
0x1800e463b  call    cs:__imp__wtoi
0x1800e4641  mov     [rsp+268h+var_118], eax
0x1800e4648  mov     [rsp+268h+var_114], r12b
0x1800e4650  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e4655  lea     rdx, aAllowstorageca; "AllowStorageCard"
0x1800e465c  mov     rcx, rdi; this
0x1800e465f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e4664  test    eax, eax
0x1800e4666  jnz     short loc_1800E4687
0x1800e4668  mov     rcx, [rsp+268h+String]; String
0x1800e466d  test    rcx, rcx
0x1800e4670  jz      short loc_1800E4687
0x1800e4672  call    cs:__imp__wtoi
0x1800e4678  mov     [rsp+268h+var_110], eax
0x1800e467f  mov     [rsp+268h+var_10C], r12b
0x1800e4687  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e468c  lea     rdx, aAllowtelemetry; "AllowTelemetry"
0x1800e4693  mov     rcx, rdi; this
0x1800e4696  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e469b  test    eax, eax
0x1800e469d  jnz     short loc_1800E46BE
0x1800e469f  mov     rcx, [rsp+268h+String]; String
0x1800e46a4  test    rcx, rcx
0x1800e46a7  jz      short loc_1800E46BE
0x1800e46a9  call    cs:__imp__wtoi
0x1800e46af  mov     [rsp+268h+var_108], eax
0x1800e46b6  mov     [rsp+268h+var_104], r12b
0x1800e46be  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e46c3  lea     rdx, aAllowupdatecom; "AllowUpdateComplianceProcessing"
0x1800e46ca  mov     rcx, rdi; this
0x1800e46cd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e46d2  test    eax, eax
0x1800e46d4  jnz     short loc_1800E46F5
0x1800e46d6  mov     rcx, [rsp+268h+String]; String
0x1800e46db  test    rcx, rcx
0x1800e46de  jz      short loc_1800E46F5
0x1800e46e0  call    cs:__imp__wtoi
0x1800e46e6  mov     [rsp+268h+var_100], eax
0x1800e46ed  mov     [rsp+268h+var_FC], r12b
0x1800e46f5  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e46fa  lea     rdx, aAllowusertores; "AllowUserToResetPhone"
0x1800e4701  mov     rcx, rdi; this
0x1800e4704  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e4709  test    eax, eax
0x1800e470b  jnz     short loc_1800E472C
0x1800e470d  mov     rcx, [rsp+268h+String]; String
0x1800e4712  test    rcx, rcx
0x1800e4715  jz      short loc_1800E472C
  ... truncated ...
```
