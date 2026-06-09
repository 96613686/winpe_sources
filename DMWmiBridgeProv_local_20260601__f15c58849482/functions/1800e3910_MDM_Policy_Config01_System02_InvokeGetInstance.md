# MDM_Policy_Config01_System02_InvokeGetInstance

- ea: `0x1800e3910`
- end: `0x1800e43df`
- name: `MDM_Policy_Config01_System02_InvokeGetInstance`
- size: `2767`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e1e40`

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
- `0x1800e3910`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e3baf`
- `msvcrt!_wtoi` at `0x1800e3bec`
- `msvcrt!_wtoi` at `0x1800e3c29`
- `msvcrt!_wtoi` at `0x1800e3c66`
- `msvcrt!_wtoi` at `0x1800e3ca3`
- `msvcrt!_wtoi` at `0x1800e3ce0`
- `msvcrt!_wtoi` at `0x1800e3d1d`
- `msvcrt!_wtoi` at `0x1800e3d5a`
- `msvcrt!_wtoi` at `0x1800e3d97`
- `msvcrt!_wtoi` at `0x1800e3dd4`
- `msvcrt!_wtoi` at `0x1800e3e11`
- `msvcrt!_wtoi` at `0x1800e3e4e`
- `msvcrt!_wtoi` at `0x1800e3e8b`
- `msvcrt!_wtoi` at `0x1800e3ec8`
- `msvcrt!_wtoi` at `0x1800e3f63`
- `msvcrt!_wtoi` at `0x1800e3fa0`
- `msvcrt!_wtoi` at `0x1800e3fdd`
- `msvcrt!_wtoi` at `0x1800e401a`
- `msvcrt!_wtoi` at `0x1800e4057`
- `msvcrt!_wtoi` at `0x1800e4094`
- `msvcrt!_wtoi` at `0x1800e40d1`
- `msvcrt!_wtoi` at `0x1800e410e`
- `msvcrt!_wtoi` at `0x1800e417a`
- `msvcrt!_wtoi` at `0x1800e41b7`
- `msvcrt!_wtoi` at `0x1800e41f4`
- `msvcrt!_wtoi` at `0x1800e4231`
- `msvcrt!_wtoi` at `0x1800e426e`
- `msvcrt!_wtoi` at `0x1800e42da`
- `msvcrt!_wtoi` at `0x1800e3baf`
- `msvcrt!_wtoi` at `0x1800e3bec`
- `msvcrt!_wtoi` at `0x1800e3c29`
- `msvcrt!_wtoi` at `0x1800e3c66`
- `msvcrt!_wtoi` at `0x1800e3ca3`
- `msvcrt!_wtoi` at `0x1800e3ce0`
- `msvcrt!_wtoi` at `0x1800e3d1d`
- `msvcrt!_wtoi` at `0x1800e3d5a`
- `msvcrt!_wtoi` at `0x1800e3d97`
- `msvcrt!_wtoi` at `0x1800e3dd4`
- `msvcrt!_wtoi` at `0x1800e3e11`
- `msvcrt!_wtoi` at `0x1800e3e4e`
- `msvcrt!_wtoi` at `0x1800e3e8b`
- `msvcrt!_wtoi` at `0x1800e3ec8`
- `msvcrt!_wtoi` at `0x1800e3f63`
- `msvcrt!_wtoi` at `0x1800e3fa0`
- `msvcrt!_wtoi` at `0x1800e3fdd`
- `msvcrt!_wtoi` at `0x1800e401a`
- `msvcrt!_wtoi` at `0x1800e4057`
- `msvcrt!_wtoi` at `0x1800e4094`
- `msvcrt!_wtoi` at `0x1800e40d1`
- `msvcrt!_wtoi` at `0x1800e410e`
- `msvcrt!_wtoi` at `0x1800e417a`
- `msvcrt!_wtoi` at `0x1800e41b7`
- `msvcrt!_wtoi` at `0x1800e41f4`
- `msvcrt!_wtoi` at `0x1800e4231`
- `msvcrt!_wtoi` at `0x1800e426e`
- `msvcrt!_wtoi` at `0x1800e42da`

## string_xrefs

- `0x1800e3bcf`: `AllowCommercialDataPipeline`
- `0x1800e3e31`: `AllowUpdateComplianceProcessing`
- `0x1800e3f17`: `ConfigureMicrosoft365UploadEndpoint`
- `0x1800e3f46`: `ConfigureTelemetryOptInChangeNotification`
- `0x1800e3f83`: `ConfigureTelemetryOptInSettingsUx`
- `0x1800e3fc0`: `DisableDeviceDelete`
- `0x1800e403a`: `DisableDirectXDatabaseUpdate`
- `0x1800e397f`: `MDM_Policy_Config01_System02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_System02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_125;
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
                       &MDM_Policy_Config01_System02_NodeList,
                       34,
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
      goto LABEL_125;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_System02_NodeList,
      0x22u);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_125;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_125;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowBuildPreview", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowEmbeddedMode", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowExperimentation", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowFontProviders", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowUserToResetPhone", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowWUfBCloudProcessing", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableDeviceDelete", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableEnterpriseAuthProxy", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableOneDriveFileSync", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableSystemRestore", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableOneSettingsAuditing", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"LimitDumpCollection", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"TurnOffFileHistory", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e3910  mov     [rsp+arg_10], rbx
0x1800e3915  push    rsi
0x1800e3916  push    rdi
0x1800e3917  push    r12
0x1800e3919  push    r14
0x1800e391b  push    r15
0x1800e391d  sub     rsp, 240h
0x1800e3924  mov     rax, cs:__security_cookie
0x1800e392b  xor     rax, rsp
0x1800e392e  mov     [rsp+268h+var_38], rax
0x1800e3936  mov     rsi, rdx
0x1800e3939  mov     r15, rcx
0x1800e393c  xor     ebx, ebx
0x1800e393e  mov     [rsp+268h+String], rbx
0x1800e3943  xor     edx, edx; Val
0x1800e3945  mov     r8d, 180h; Size
0x1800e394b  lea     rcx, [rsp+268h+instance]; void *
0x1800e3953  call    memset_0
0x1800e3958  mov     [rsp+268h+var_1E0], ebx
0x1800e395f  mov     [rsp+268h+var_1DC], bl
0x1800e3966  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e396d  mov     [rsp+268h+var_210], rax
0x1800e3972  lea     rax, [rsp+268h+var_1E0]
0x1800e397a  mov     [rsp+268h+var_208], rax
0x1800e397f  lea     rax, aMdmPolicyConfi_18; "MDM_Policy_Config01_System02"
0x1800e3986  mov     [rsp+268h+var_200], rax
0x1800e398b  lea     rcx, [rsp+268h+var_1E0]
0x1800e3993  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e3998  mov     eax, cs:dword_180380B68
0x1800e399e  cmp     eax, 5
0x1800e39a1  jbe     short loc_1800E3A12
0x1800e39a3  mov     rdx, 200000000000h
0x1800e39ad  lea     rcx, dword_180380B68
0x1800e39b4  call    _tlgKeywordOn
0x1800e39b9  test    al, al
0x1800e39bb  jz      short loc_1800E3A12
0x1800e39bd  cmp     [rsp+268h+var_1DC], bl
0x1800e39c4  jz      short loc_1800E39F4
0x1800e39c6  cmp     [rsp+268h+var_1C8], ebx
0x1800e39cd  jnz     short loc_1800E39EA
0x1800e39cf  cmp     [rsp+268h+var_1C4], ebx
0x1800e39d6  jnz     short loc_1800E39EA
0x1800e39d8  cmp     [rsp+268h+var_1C0], ebx
0x1800e39df  jnz     short loc_1800E39EA
0x1800e39e1  cmp     [rsp+268h+var_1BC], ebx
0x1800e39e8  jz      short loc_1800E39F4
0x1800e39ea  lea     r9, [rsp+268h+var_1C8]
0x1800e39f2  jmp     short loc_1800E39F7
0x1800e39f4  mov     r9, rbx
0x1800e39f7  lea     r8, [rsp+268h+var_1D8]
0x1800e39ff  lea     rdx, dword_18033F5D4
0x1800e3a06  lea     rcx, dword_180380B68
0x1800e3a0d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e3a12  cmp     [rsi+48h], bl
0x1800e3a15  jz      loc_1800E433D
0x1800e3a1b  mov     [rsp+268h+var_220], bl
0x1800e3a1f  cmp     [rsi+58h], bl
0x1800e3a22  jz      loc_1800E433D
0x1800e3a28  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e3a2c  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e3a30  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e3a37  lea     rcx, [rsp+268h+var_210]; this
0x1800e3a3c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e3a41  nop
0x1800e3a42  mov     [rsp+268h+var_218], rbx
0x1800e3a47  lea     rax, [rsp+268h+var_218]
0x1800e3a4c  mov     [rsp+268h+var_238], rax
0x1800e3a51  mov     [rsp+268h+var_240], ebx
0x1800e3a55  mov     [rsp+268h+var_248], 22h ; '"'
0x1800e3a5d  lea     r9, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_System02_NodeList
0x1800e3a64  mov     r8, [rsi+40h]
0x1800e3a68  mov     rdx, [rsi+50h]
0x1800e3a6c  mov     rcx, r15
0x1800e3a6f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e3a74  mov     r14d, eax
0x1800e3a77  test    eax, eax
0x1800e3a79  jz      short loc_1800E3A80
0x1800e3a7b  jmp     loc_1800E4343
0x1800e3a80  lea     rax, [rsp+268h+var_218]
0x1800e3a85  mov     [rsp+268h+var_1F0], rax
0x1800e3a8a  mov     r12d, 1
0x1800e3a90  mov     [rsp+268h+var_1E8], r12b
0x1800e3a98  mov     rdi, [rsp+268h+var_218]
0x1800e3a9d  test    rdi, rdi
0x1800e3aa0  jnz     short loc_1800E3AAA
0x1800e3aa2  mov     r14d, r12d
0x1800e3aa5  jmp     loc_1800E4343
0x1800e3aaa  mov     r9d, 22h ; '"'; unsigned int
0x1800e3ab0  lea     r8, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e3ab7  mov     rdx, rsi; struct _MI_Instance *
0x1800e3aba  mov     rcx, rdi; this
0x1800e3abd  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e3ac2  mov     rax, [rdi]
0x1800e3ac5  mov     rcx, rdi
0x1800e3ac8  mov     rax, [rax+10h]
0x1800e3acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3ad1  mov     r14d, eax
0x1800e3ad4  test    eax, eax
0x1800e3ad6  jz      short loc_1800E3AF6
0x1800e3ad8  mov     rcx, [rsp+268h+var_218]
0x1800e3add  test    rcx, rcx
0x1800e3ae0  jz      short loc_1800E3AF1
0x1800e3ae2  mov     rax, [rcx]
0x1800e3ae5  mov     edx, r12d
0x1800e3ae8  mov     rax, [rax]
0x1800e3aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3af0  nop
0x1800e3af1  jmp     loc_1800E4343
0x1800e3af6  mov     rax, [rdi]
0x1800e3af9  mov     rcx, rdi
0x1800e3afc  mov     rax, [rax+8]
0x1800e3b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b05  mov     r14d, eax
0x1800e3b08  test    eax, eax
0x1800e3b0a  jz      short loc_1800E3B2A
0x1800e3b0c  mov     rcx, [rsp+268h+var_218]
0x1800e3b11  test    rcx, rcx
0x1800e3b14  jz      short loc_1800E3B25
0x1800e3b16  mov     rax, [rcx]
0x1800e3b19  mov     edx, r12d
0x1800e3b1c  mov     rax, [rax]
0x1800e3b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b24  nop
0x1800e3b25  jmp     loc_1800E4343
0x1800e3b2a  lea     r8, [rsp+268h+instance]; instance
0x1800e3b32  lea     rdx, MDM_Policy_Config01_System02_rtti; classDecl
0x1800e3b39  mov     rcx, r15; context
0x1800e3b3c  call    MI_Context_ConstructInstance
0x1800e3b41  mov     r14d, eax
0x1800e3b44  test    eax, eax
0x1800e3b46  jz      short loc_1800E3B66
0x1800e3b48  mov     rcx, [rsp+268h+var_218]
0x1800e3b4d  test    rcx, rcx
0x1800e3b50  jz      short loc_1800E3B61
0x1800e3b52  mov     rax, [rcx]
0x1800e3b55  mov     edx, r12d
0x1800e3b58  mov     rax, [rax]
0x1800e3b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b60  nop
0x1800e3b61  jmp     loc_1800E4343
0x1800e3b66  mov     [rsp+268h+var_220], r12b
0x1800e3b6b  mov     rdx, [rsi+40h]
0x1800e3b6f  lea     rcx, [rsp+268h+instance]
0x1800e3b77  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e3b7c  mov     rdx, [rsi+50h]
0x1800e3b80  lea     rcx, [rsp+268h+instance]
0x1800e3b88  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e3b8d  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3b92  lea     rdx, aAllowbuildprev; "AllowBuildPreview"
0x1800e3b99  mov     rcx, rdi; this
0x1800e3b9c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3ba1  test    eax, eax
0x1800e3ba3  jnz     short loc_1800E3BCA
0x1800e3ba5  mov     rcx, [rsp+268h+String]; String
0x1800e3baa  test    rcx, rcx
0x1800e3bad  jz      short loc_1800E3BCA
0x1800e3baf  call    cs:__imp__wtoi
0x1800e3bb6  nop     dword ptr [rax+rax+00h]
0x1800e3bbb  mov     [rsp+268h+var_158], eax
0x1800e3bc2  mov     [rsp+268h+var_154], r12b
0x1800e3bca  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3bcf  lea     rdx, aAllowcommercia; "AllowCommercialDataPipeline"
0x1800e3bd6  mov     rcx, rdi; this
0x1800e3bd9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3bde  test    eax, eax
0x1800e3be0  jnz     short loc_1800E3C07
0x1800e3be2  mov     rcx, [rsp+268h+String]; String
0x1800e3be7  test    rcx, rcx
0x1800e3bea  jz      short loc_1800E3C07
0x1800e3bec  call    cs:__imp__wtoi
0x1800e3bf3  nop     dword ptr [rax+rax+00h]
0x1800e3bf8  mov     [rsp+268h+var_150], eax
0x1800e3bff  mov     [rsp+268h+var_14C], r12b
0x1800e3c07  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3c0c  lea     rdx, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x1800e3c13  mov     rcx, rdi; this
0x1800e3c16  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3c1b  test    eax, eax
0x1800e3c1d  jnz     short loc_1800E3C44
0x1800e3c1f  mov     rcx, [rsp+268h+String]; String
0x1800e3c24  test    rcx, rcx
0x1800e3c27  jz      short loc_1800E3C44
0x1800e3c29  call    cs:__imp__wtoi
0x1800e3c30  nop     dword ptr [rax+rax+00h]
0x1800e3c35  mov     [rsp+268h+var_148], eax
0x1800e3c3c  mov     [rsp+268h+var_144], r12b
0x1800e3c44  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3c49  lea     rdx, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800e3c50  mov     rcx, rdi; this
0x1800e3c53  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3c58  test    eax, eax
0x1800e3c5a  jnz     short loc_1800E3C81
0x1800e3c5c  mov     rcx, [rsp+268h+String]; String
0x1800e3c61  test    rcx, rcx
0x1800e3c64  jz      short loc_1800E3C81
0x1800e3c66  call    cs:__imp__wtoi
0x1800e3c6d  nop     dword ptr [rax+rax+00h]
0x1800e3c72  mov     [rsp+268h+var_140], eax
0x1800e3c79  mov     [rsp+268h+var_13C], r12b
0x1800e3c81  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3c86  lea     rdx, aAllowembeddedm; "AllowEmbeddedMode"
0x1800e3c8d  mov     rcx, rdi; this
0x1800e3c90  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3c95  test    eax, eax
0x1800e3c97  jnz     short loc_1800E3CBE
0x1800e3c99  mov     rcx, [rsp+268h+String]; String
0x1800e3c9e  test    rcx, rcx
0x1800e3ca1  jz      short loc_1800E3CBE
0x1800e3ca3  call    cs:__imp__wtoi
0x1800e3caa  nop     dword ptr [rax+rax+00h]
0x1800e3caf  mov     [rsp+268h+var_138], eax
0x1800e3cb6  mov     [rsp+268h+var_134], r12b
0x1800e3cbe  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3cc3  lea     rdx, aAllowexperimen; "AllowExperimentation"
0x1800e3cca  mov     rcx, rdi; this
0x1800e3ccd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3cd2  test    eax, eax
0x1800e3cd4  jnz     short loc_1800E3CFB
0x1800e3cd6  mov     rcx, [rsp+268h+String]; String
0x1800e3cdb  test    rcx, rcx
0x1800e3cde  jz      short loc_1800E3CFB
0x1800e3ce0  call    cs:__imp__wtoi
0x1800e3ce7  nop     dword ptr [rax+rax+00h]
0x1800e3cec  mov     [rsp+268h+var_130], eax
0x1800e3cf3  mov     [rsp+268h+var_12C], r12b
0x1800e3cfb  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3d00  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x1800e3d07  mov     rcx, rdi; this
0x1800e3d0a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3d0f  test    eax, eax
0x1800e3d11  jnz     short loc_1800E3D38
0x1800e3d13  mov     rcx, [rsp+268h+String]; String
0x1800e3d18  test    rcx, rcx
0x1800e3d1b  jz      short loc_1800E3D38
0x1800e3d1d  call    cs:__imp__wtoi
0x1800e3d24  nop     dword ptr [rax+rax+00h]
0x1800e3d29  mov     [rsp+268h+var_128], eax
0x1800e3d30  mov     [rsp+268h+var_124], r12b
0x1800e3d38  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3d3d  lea     rdx, aAllowlocation; "AllowLocation"
0x1800e3d44  mov     rcx, rdi; this
0x1800e3d47  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3d4c  test    eax, eax
0x1800e3d4e  jnz     short loc_1800E3D75
0x1800e3d50  mov     rcx, [rsp+268h+String]; String
0x1800e3d55  test    rcx, rcx
0x1800e3d58  jz      short loc_1800E3D75
0x1800e3d5a  call    cs:__imp__wtoi
0x1800e3d61  nop     dword ptr [rax+rax+00h]
0x1800e3d66  mov     [rsp+268h+var_120], eax
0x1800e3d6d  mov     [rsp+268h+var_11C], r12b
0x1800e3d75  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3d7a  lea     rdx, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x1800e3d81  mov     rcx, rdi; this
0x1800e3d84  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3d89  test    eax, eax
0x1800e3d8b  jnz     short loc_1800E3DB2
0x1800e3d8d  mov     rcx, [rsp+268h+String]; String
0x1800e3d92  test    rcx, rcx
0x1800e3d95  jz      short loc_1800E3DB2
0x1800e3d97  call    cs:__imp__wtoi
0x1800e3d9e  nop     dword ptr [rax+rax+00h]
0x1800e3da3  mov     [rsp+268h+var_118], eax
0x1800e3daa  mov     [rsp+268h+var_114], r12b
0x1800e3db2  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3db7  lea     rdx, aAllowstorageca; "AllowStorageCard"
0x1800e3dbe  mov     rcx, rdi; this
0x1800e3dc1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3dc6  test    eax, eax
0x1800e3dc8  jnz     short loc_1800E3DEF
0x1800e3dca  mov     rcx, [rsp+268h+String]; String
0x1800e3dcf  test    rcx, rcx
0x1800e3dd2  jz      short loc_1800E3DEF
0x1800e3dd4  call    cs:__imp__wtoi
0x1800e3ddb  nop     dword ptr [rax+rax+00h]
0x1800e3de0  mov     [rsp+268h+var_110], eax
0x1800e3de7  mov     [rsp+268h+var_10C], r12b
0x1800e3def  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3df4  lea     rdx, aAllowtelemetry; "AllowTelemetry"
0x1800e3dfb  mov     rcx, rdi; this
0x1800e3dfe  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3e03  test    eax, eax
0x1800e3e05  jnz     short loc_1800E3E2C
0x1800e3e07  mov     rcx, [rsp+268h+String]; String
0x1800e3e0c  test    rcx, rcx
0x1800e3e0f  jz      short loc_1800E3E2C
0x1800e3e11  call    cs:__imp__wtoi
0x1800e3e18  nop     dword ptr [rax+rax+00h]
0x1800e3e1d  mov     [rsp+268h+var_108], eax
0x1800e3e24  mov     [rsp+268h+var_104], r12b
0x1800e3e2c  lea     r8, [rsp+268h+String]; unsigned __int16 **
0x1800e3e31  lea     rdx, aAllowupdatecom; "AllowUpdateComplianceProcessing"
0x1800e3e38  mov     rcx, rdi; this
0x1800e3e3b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e3e40  test    eax, eax
0x1800e3e42  jnz     short loc_1800E3E69
0x1800e3e44  mov     rcx, [rsp+268h+String]; String
0x1800e3e49  test    rcx, rcx
0x1800e3e4c  jz      short loc_1800E3E69
0x1800e3e4e  call    cs:__imp__wtoi
  ... truncated ...
```
