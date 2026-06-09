# MDM_Policy_Config01_System02_InvokeEnumerateInstances

- ea: `0x1800e35f4`
- end: `0x1800e41dc`
- name: `MDM_Policy_Config01_System02_InvokeEnumerateInstances`
- size: `3048`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e2770`

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
- `0x1800e35f4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e3906`
- `msvcrt!_wtoi` at `0x1800e3947`
- `msvcrt!_wtoi` at `0x1800e3988`
- `msvcrt!_wtoi` at `0x1800e39c9`
- `msvcrt!_wtoi` at `0x1800e3a0a`
- `msvcrt!_wtoi` at `0x1800e3a4b`
- `msvcrt!_wtoi` at `0x1800e3a8c`
- `msvcrt!_wtoi` at `0x1800e3acd`
- `msvcrt!_wtoi` at `0x1800e3b0e`
- `msvcrt!_wtoi` at `0x1800e3b4f`
- `msvcrt!_wtoi` at `0x1800e3b90`
- `msvcrt!_wtoi` at `0x1800e3bd1`
- `msvcrt!_wtoi` at `0x1800e3c12`
- `msvcrt!_wtoi` at `0x1800e3c53`
- `msvcrt!_wtoi` at `0x1800e3d06`
- `msvcrt!_wtoi` at `0x1800e3d47`
- `msvcrt!_wtoi` at `0x1800e3d88`
- `msvcrt!_wtoi` at `0x1800e3dc9`
- `msvcrt!_wtoi` at `0x1800e3e0a`
- `msvcrt!_wtoi` at `0x1800e3e4b`
- `msvcrt!_wtoi` at `0x1800e3e8c`
- `msvcrt!_wtoi` at `0x1800e3ecd`
- `msvcrt!_wtoi` at `0x1800e3f47`
- `msvcrt!_wtoi` at `0x1800e3f88`
- `msvcrt!_wtoi` at `0x1800e3fc9`
- `msvcrt!_wtoi` at `0x1800e400a`
- `msvcrt!_wtoi` at `0x1800e404b`
- `msvcrt!_wtoi` at `0x1800e40c5`
- `msvcrt!_wtoi` at `0x1800e3906`
- `msvcrt!_wtoi` at `0x1800e3947`
- `msvcrt!_wtoi` at `0x1800e3988`
- `msvcrt!_wtoi` at `0x1800e39c9`
- `msvcrt!_wtoi` at `0x1800e3a0a`
- `msvcrt!_wtoi` at `0x1800e3a4b`
- `msvcrt!_wtoi` at `0x1800e3a8c`
- `msvcrt!_wtoi` at `0x1800e3acd`
- `msvcrt!_wtoi` at `0x1800e3b0e`
- `msvcrt!_wtoi` at `0x1800e3b4f`
- `msvcrt!_wtoi` at `0x1800e3b90`
- `msvcrt!_wtoi` at `0x1800e3bd1`
- `msvcrt!_wtoi` at `0x1800e3c12`
- `msvcrt!_wtoi` at `0x1800e3c53`
- `msvcrt!_wtoi` at `0x1800e3d06`
- `msvcrt!_wtoi` at `0x1800e3d47`
- `msvcrt!_wtoi` at `0x1800e3d88`
- `msvcrt!_wtoi` at `0x1800e3dc9`
- `msvcrt!_wtoi` at `0x1800e3e0a`
- `msvcrt!_wtoi` at `0x1800e3e4b`
- `msvcrt!_wtoi` at `0x1800e3e8c`
- `msvcrt!_wtoi` at `0x1800e3ecd`
- `msvcrt!_wtoi` at `0x1800e3f47`
- `msvcrt!_wtoi` at `0x1800e3f88`
- `msvcrt!_wtoi` at `0x1800e3fc9`
- `msvcrt!_wtoi` at `0x1800e400a`
- `msvcrt!_wtoi` at `0x1800e404b`
- `msvcrt!_wtoi` at `0x1800e40c5`

## string_xrefs

- `0x1800e3923`: `AllowCommercialDataPipeline`
- `0x1800e3bad`: `AllowUpdateComplianceProcessing`
- `0x1800e3ca9`: `ConfigureMicrosoft365UploadEndpoint`
- `0x1800e3ce2`: `ConfigureTelemetryOptInChangeNotification`
- `0x1800e3d23`: `ConfigureTelemetryOptInSettingsUx`
- `0x1800e3d64`: `DisableDeviceDelete`
- `0x1800e3de6`: `DisableDirectXDatabaseUpdate`
- `0x1800e3848`: `./Vendor/MSFT/Policy/Config`
- `0x1800e366f`: `MDM_Policy_Config01_System02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_System02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-228h] BYREF
  char v14; // [rsp+48h] [rbp-220h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-218h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-210h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1F8h] BYREF
  char v18; // [rsp+80h] [rbp-1E8h]
  int v19; // [rsp+88h] [rbp-1E0h] BYREF
  char v20; // [rsp+8Ch] [rbp-1DCh]
  _BYTE v21[16]; // [rsp+90h] [rbp-1D8h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-1C8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-1B8h] BYREF
  int v24; // [rsp+110h] [rbp-158h]
  char v25; // [rsp+114h] [rbp-154h]
  int v26; // [rsp+118h] [rbp-150h]
  char v27; // [rsp+11Ch] [rbp-14Ch]
  int v28; // [rsp+120h] [rbp-148h]
  char v29; // [rsp+124h] [rbp-144h]
  int v30; // [rsp+128h] [rbp-140h]
  char v31; // [rsp+12Ch] [rbp-13Ch]
  int v32; // [rsp+130h] [rbp-138h]
  char v33; // [rsp+134h] [rbp-134h]
  int v34; // [rsp+138h] [rbp-130h]
  char v35; // [rsp+13Ch] [rbp-12Ch]
  int v36; // [rsp+140h] [rbp-128h]
  char v37; // [rsp+144h] [rbp-124h]
  int v38; // [rsp+148h] [rbp-120h]
  char v39; // [rsp+14Ch] [rbp-11Ch]
  int v40; // [rsp+150h] [rbp-118h]
  char v41; // [rsp+154h] [rbp-114h]
  int v42; // [rsp+158h] [rbp-110h]
  char v43; // [rsp+15Ch] [rbp-10Ch]
  int v44; // [rsp+160h] [rbp-108h]
  char v45; // [rsp+164h] [rbp-104h]
  int v46; // [rsp+168h] [rbp-100h]
  char v47; // [rsp+16Ch] [rbp-FCh]
  int v48; // [rsp+170h] [rbp-F8h]
  char v49; // [rsp+174h] [rbp-F4h]
  int v50; // [rsp+178h] [rbp-F0h]
  char v51; // [rsp+17Ch] [rbp-ECh]
  int v52; // [rsp+1A0h] [rbp-C8h]
  char v53; // [rsp+1A4h] [rbp-C4h]
  int v54; // [rsp+1A8h] [rbp-C0h]
  char v55; // [rsp+1ACh] [rbp-BCh]
  int v56; // [rsp+1B0h] [rbp-B8h]
  char v57; // [rsp+1B4h] [rbp-B4h]
  int v58; // [rsp+1B8h] [rbp-B0h]
  char v59; // [rsp+1BCh] [rbp-ACh]
  int v60; // [rsp+1C0h] [rbp-A8h]
  char v61; // [rsp+1C4h] [rbp-A4h]
  int v62; // [rsp+1C8h] [rbp-A0h]
  char v63; // [rsp+1CCh] [rbp-9Ch]
  int v64; // [rsp+1D0h] [rbp-98h]
  char v65; // [rsp+1D4h] [rbp-94h]
  int v66; // [rsp+1D8h] [rbp-90h]
  char v67; // [rsp+1DCh] [rbp-8Ch]
  int v68; // [rsp+1F0h] [rbp-78h]
  char v69; // [rsp+1F4h] [rbp-74h]
  int v70; // [rsp+1F8h] [rbp-70h]
  char v71; // [rsp+1FCh] [rbp-6Ch]
  int v72; // [rsp+200h] [rbp-68h]
  char v73; // [rsp+204h] [rbp-64h]
  int v74; // [rsp+208h] [rbp-60h]
  char v75; // [rsp+20Ch] [rbp-5Ch]
  int v76; // [rsp+210h] [rbp-58h]
  char v77; // [rsp+214h] [rbp-54h]
  int v78; // [rsp+228h] [rbp-40h]
  char v79; // [rsp+22Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0x180u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_System02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033F9EF,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_System02_NodeList,
           0x22u,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_System02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_145;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"System",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowBuildPreview",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCommercialDataPipeline",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDesktopAnalyticsProcessing",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDeviceNameInDiagnosticData",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowEmbeddedMode",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowExperimentation",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFontProviders",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLocation",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowMicrosoftManagedDesktopProcessing",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageCard",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowTelemetry",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUpdateComplianceProcessing",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowUserToResetPhone",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowWUfBCloudProcessing",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"BootStartDriverInitialization",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMicrosoft365UploadEndpoint",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTelemetryOptInChangeNotification",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTelemetryOptInSettingsUx",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDeviceDelete",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDiagnosticDataViewer",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDirectXDatabaseUpdate",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableEnterpriseAuthProxy",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableOneDriveFileSync",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableOneSettingsDownloads",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableSystemRestore",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowsRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableOneSettingsAuditing",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"FeedbackHubAlwaysSaveDiagnosticsLocally",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LimitDiagnosticLogCollection",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LimitDumpCollection",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LimitEnhancedDiagnosticDataWindowsAnalytics",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TelemetryProxy",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_ConsistentMimeHandlingInternetExplorerProcesses(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffFileHistory",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_136;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_136:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (unsigned int)v15;
  }
LABEL_145:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18034BBE7,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return v7;
}

```

## disassembly

```asm
0x1800e35f4  mov     [rsp+arg_8], rbx
0x1800e35f9  mov     [rsp+arg_10], rsi
0x1800e35fe  push    rdi
0x1800e35ff  push    r12
0x1800e3601  push    r13
0x1800e3603  push    r14
0x1800e3605  push    r15
0x1800e3607  sub     rsp, 240h
0x1800e360e  mov     rax, cs:__security_cookie
0x1800e3615  xor     rax, rsp
0x1800e3618  mov     [rsp+268h+var_38], rax
0x1800e3620  mov     r13b, dl
0x1800e3623  mov     r12, rcx
0x1800e3626  xor     edx, edx; Val
0x1800e3628  mov     r8d, 180h; Size
0x1800e362e  lea     rcx, [rsp+268h+instance]; void *
0x1800e3636  call    memset_0
0x1800e363b  xor     edi, edi
0x1800e363d  mov     [rsp+268h+var_220], dil
0x1800e3642  mov     [rsp+268h+String], rdi
0x1800e3647  mov     [rsp+268h+var_1E0], edi
0x1800e364e  mov     [rsp+268h+var_1DC], dil
0x1800e3656  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e365d  mov     [rsp+268h+var_210], rax
0x1800e3662  lea     rax, [rsp+268h+var_1E0]
0x1800e366a  mov     [rsp+268h+var_208], rax
0x1800e366f  lea     rax, aMdmPolicyConfi_18; "MDM_Policy_Config01_System02"
0x1800e3676  mov     [rsp+268h+var_200], rax
0x1800e367b  lea     rcx, [rsp+268h+var_1E0]
0x1800e3683  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e3688  mov     eax, cs:dword_180380B68
0x1800e368e  cmp     eax, 5
0x1800e3691  jbe     short loc_1800E3703
0x1800e3693  mov     rdx, 200000000000h
0x1800e369d  lea     rcx, dword_180380B68
0x1800e36a4  call    _tlgKeywordOn
0x1800e36a9  test    al, al
0x1800e36ab  jz      short loc_1800E3703
0x1800e36ad  cmp     [rsp+268h+var_1DC], dil
0x1800e36b5  jz      short loc_1800E36E5
0x1800e36b7  cmp     [rsp+268h+var_1C8], edi
0x1800e36be  jnz     short loc_1800E36DB
0x1800e36c0  cmp     [rsp+268h+var_1C4], edi
0x1800e36c7  jnz     short loc_1800E36DB
0x1800e36c9  cmp     [rsp+268h+var_1C0], edi
0x1800e36d0  jnz     short loc_1800E36DB
0x1800e36d2  cmp     [rsp+268h+var_1BC], edi
0x1800e36d9  jz      short loc_1800E36E5
0x1800e36db  lea     r9, [rsp+268h+var_1C8]
0x1800e36e3  jmp     short loc_1800E36E8
0x1800e36e5  mov     r9, rdi
0x1800e36e8  lea     r8, [rsp+268h+var_1D8]
0x1800e36f0  lea     rdx, byte_18033F9EF
0x1800e36f7  lea     rcx, dword_180380B68
0x1800e36fe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e3703  lea     rcx, [rsp+268h+var_210]; this
0x1800e3708  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e370d  nop
0x1800e370e  mov     [rsp+268h+var_218], rdi
0x1800e3713  lea     rax, [rsp+268h+var_218]
0x1800e3718  mov     [rsp+268h+var_238], rax
0x1800e371d  mov     [rsp+268h+var_240], 2
0x1800e3725  mov     [rsp+268h+var_248], 22h ; '"'
0x1800e372d  lea     r9, ?MDM_Policy_Config01_System02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_System02_NodeList
0x1800e3734  xor     r8d, r8d
0x1800e3737  xor     edx, edx
0x1800e3739  mov     rcx, r12
0x1800e373c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e3741  mov     r15d, eax
0x1800e3744  test    eax, eax
0x1800e3746  jz      short loc_1800E374D
0x1800e3748  jmp     loc_1800E413C
0x1800e374d  lea     rbx, [rsp+268h+var_218]
0x1800e3752  mov     [rsp+268h+var_1F0], rbx
0x1800e3757  mov     r14d, 1
0x1800e375d  mov     [rsp+268h+var_1E8], r14b
0x1800e3765  mov     rsi, [rsp+268h+var_218]
0x1800e376a  test    rsi, rsi
0x1800e376d  jnz     short loc_1800E3777
0x1800e376f  mov     r15d, r14d
0x1800e3772  jmp     loc_1800E413C
0x1800e3777  mov     rax, [rsi]
0x1800e377a  mov     rcx, rsi
0x1800e377d  mov     rax, [rax+10h]
0x1800e3781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3786  mov     r15d, eax
0x1800e3789  test    eax, eax
0x1800e378b  jz      short loc_1800E37AB
0x1800e378d  mov     rcx, [rsp+268h+var_218]
0x1800e3792  test    rcx, rcx
0x1800e3795  jz      short loc_1800E37A6
0x1800e3797  mov     rax, [rcx]
0x1800e379a  mov     edx, r14d
0x1800e379d  mov     rax, [rax]
0x1800e37a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37a5  nop
0x1800e37a6  jmp     loc_1800E413C
0x1800e37ab  mov     rax, [rsi]
0x1800e37ae  mov     rcx, rsi
0x1800e37b1  mov     rax, [rax+8]
0x1800e37b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37ba  mov     r15d, eax
0x1800e37bd  test    eax, eax
0x1800e37bf  jz      short loc_1800E37DF
0x1800e37c1  mov     rcx, [rsp+268h+var_218]
0x1800e37c6  test    rcx, rcx
0x1800e37c9  jz      short loc_1800E37DA
0x1800e37cb  mov     rax, [rcx]
0x1800e37ce  mov     edx, r14d
0x1800e37d1  mov     rax, [rax]
0x1800e37d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37d9  nop
0x1800e37da  jmp     loc_1800E413C
0x1800e37df  mov     r14d, edi
0x1800e37e2  mov     rax, [rsi+108h]
0x1800e37e9  sub     rax, [rsi+100h]
0x1800e37f0  sar     rax, 4
0x1800e37f4  cmp     r14d, eax
0x1800e37f7  jnb     loc_1800E4104
0x1800e37fd  lea     r8, [rsp+268h+instance]; instance
0x1800e3805  lea     rdx, MDM_Policy_Config01_System02_rtti; classDecl
0x1800e380c  mov     rcx, r12; context
0x1800e380f  call    MI_Context_ConstructInstance
0x1800e3814  mov     r15d, eax
0x1800e3817  test    eax, eax
0x1800e3819  jz      short loc_1800E383B
0x1800e381b  mov     rcx, [rbx]
0x1800e381e  test    rcx, rcx
0x1800e3821  jz      short loc_1800E3836
0x1800e3823  mov     rax, [rcx]
0x1800e3826  mov     edx, 1
0x1800e382b  mov     rax, [rax]
0x1800e382e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3833  mov     [rbx], rdi
0x1800e3836  jmp     loc_1800E413C
0x1800e383b  mov     [rsp+268h+var_220], 1
0x1800e3840  mov     rax, [rsi]
0x1800e3843  lea     r9, [rsp+268h+String]
0x1800e3848  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e384f  mov     edx, r14d
0x1800e3852  mov     rcx, rsi
0x1800e3855  mov     rax, [rax+18h]
0x1800e3859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e385e  test    eax, eax
0x1800e3860  jnz     short loc_1800E3879
0x1800e3862  mov     rdx, [rsp+268h+String]
0x1800e3867  test    rdx, rdx
0x1800e386a  jz      short loc_1800E3879
0x1800e386c  lea     rcx, [rsp+268h+instance]
0x1800e3874  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e3879  mov     rax, [rsi]
0x1800e387c  lea     r9, [rsp+268h+String]
0x1800e3881  lea     r8, aSystem; "System"
0x1800e3888  mov     edx, r14d
0x1800e388b  mov     rcx, rsi
0x1800e388e  mov     rax, [rax+18h]
0x1800e3892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3897  test    eax, eax
0x1800e3899  jnz     short loc_1800E38B2
0x1800e389b  mov     rdx, [rsp+268h+String]
0x1800e38a0  test    rdx, rdx
0x1800e38a3  jz      short loc_1800E38B2
0x1800e38a5  lea     rcx, [rsp+268h+instance]
0x1800e38ad  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e38b2  cmp     r13b, 1
0x1800e38b6  jnz     short loc_1800E38DA
0x1800e38b8  lea     rdx, [rsp+268h+instance]
0x1800e38c0  mov     rcx, r12; self
0x1800e38c3  call    MI_Instance_Destruct
0x1800e38c8  lea     rcx, [rsp+268h+instance]; self
0x1800e38d0  call    MI_Instance_Destruct
0x1800e38d5  jmp     loc_1800E40F7
0x1800e38da  mov     rax, [rsi]
0x1800e38dd  lea     r9, [rsp+268h+String]
0x1800e38e2  lea     r8, aAllowbuildprev; "AllowBuildPreview"
0x1800e38e9  mov     edx, r14d
0x1800e38ec  mov     rcx, rsi
0x1800e38ef  mov     rax, [rax+18h]
0x1800e38f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e38f8  test    eax, eax
0x1800e38fa  jnz     short loc_1800E391B
0x1800e38fc  mov     rcx, [rsp+268h+String]; String
0x1800e3901  test    rcx, rcx
0x1800e3904  jz      short loc_1800E391B
0x1800e3906  call    cs:__imp__wtoi
0x1800e390c  mov     [rsp+268h+var_158], eax
0x1800e3913  mov     [rsp+268h+var_154], 1
0x1800e391b  mov     rax, [rsi]
0x1800e391e  lea     r9, [rsp+268h+String]
0x1800e3923  lea     r8, aAllowcommercia; "AllowCommercialDataPipeline"
0x1800e392a  mov     edx, r14d
0x1800e392d  mov     rcx, rsi
0x1800e3930  mov     rax, [rax+18h]
0x1800e3934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3939  test    eax, eax
0x1800e393b  jnz     short loc_1800E395C
0x1800e393d  mov     rcx, [rsp+268h+String]; String
0x1800e3942  test    rcx, rcx
0x1800e3945  jz      short loc_1800E395C
0x1800e3947  call    cs:__imp__wtoi
0x1800e394d  mov     [rsp+268h+var_150], eax
0x1800e3954  mov     [rsp+268h+var_14C], 1
0x1800e395c  mov     rax, [rsi]
0x1800e395f  lea     r9, [rsp+268h+String]
0x1800e3964  lea     r8, aAllowdesktopan; "AllowDesktopAnalyticsProcessing"
0x1800e396b  mov     edx, r14d
0x1800e396e  mov     rcx, rsi
0x1800e3971  mov     rax, [rax+18h]
0x1800e3975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e397a  test    eax, eax
0x1800e397c  jnz     short loc_1800E399D
0x1800e397e  mov     rcx, [rsp+268h+String]; String
0x1800e3983  test    rcx, rcx
0x1800e3986  jz      short loc_1800E399D
0x1800e3988  call    cs:__imp__wtoi
0x1800e398e  mov     [rsp+268h+var_148], eax
0x1800e3995  mov     [rsp+268h+var_144], 1
0x1800e399d  mov     rax, [rsi]
0x1800e39a0  lea     r9, [rsp+268h+String]
0x1800e39a5  lea     r8, aAllowdevicenam; "AllowDeviceNameInDiagnosticData"
0x1800e39ac  mov     edx, r14d
0x1800e39af  mov     rcx, rsi
0x1800e39b2  mov     rax, [rax+18h]
0x1800e39b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e39bb  test    eax, eax
0x1800e39bd  jnz     short loc_1800E39DE
0x1800e39bf  mov     rcx, [rsp+268h+String]; String
0x1800e39c4  test    rcx, rcx
0x1800e39c7  jz      short loc_1800E39DE
0x1800e39c9  call    cs:__imp__wtoi
0x1800e39cf  mov     [rsp+268h+var_140], eax
0x1800e39d6  mov     [rsp+268h+var_13C], 1
0x1800e39de  mov     rax, [rsi]
0x1800e39e1  lea     r9, [rsp+268h+String]
0x1800e39e6  lea     r8, aAllowembeddedm; "AllowEmbeddedMode"
0x1800e39ed  mov     edx, r14d
0x1800e39f0  mov     rcx, rsi
0x1800e39f3  mov     rax, [rax+18h]
0x1800e39f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e39fc  test    eax, eax
0x1800e39fe  jnz     short loc_1800E3A1F
0x1800e3a00  mov     rcx, [rsp+268h+String]; String
0x1800e3a05  test    rcx, rcx
0x1800e3a08  jz      short loc_1800E3A1F
0x1800e3a0a  call    cs:__imp__wtoi
0x1800e3a10  mov     [rsp+268h+var_138], eax
0x1800e3a17  mov     [rsp+268h+var_134], 1
0x1800e3a1f  mov     rax, [rsi]
0x1800e3a22  lea     r9, [rsp+268h+String]
0x1800e3a27  lea     r8, aAllowexperimen; "AllowExperimentation"
0x1800e3a2e  mov     edx, r14d
0x1800e3a31  mov     rcx, rsi
0x1800e3a34  mov     rax, [rax+18h]
0x1800e3a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3a3d  test    eax, eax
0x1800e3a3f  jnz     short loc_1800E3A60
0x1800e3a41  mov     rcx, [rsp+268h+String]; String
0x1800e3a46  test    rcx, rcx
0x1800e3a49  jz      short loc_1800E3A60
0x1800e3a4b  call    cs:__imp__wtoi
0x1800e3a51  mov     [rsp+268h+var_130], eax
0x1800e3a58  mov     [rsp+268h+var_12C], 1
0x1800e3a60  mov     rax, [rsi]
0x1800e3a63  lea     r9, [rsp+268h+String]
0x1800e3a68  lea     r8, aAllowfontprovi; "AllowFontProviders"
0x1800e3a6f  mov     edx, r14d
0x1800e3a72  mov     rcx, rsi
0x1800e3a75  mov     rax, [rax+18h]
0x1800e3a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3a7e  test    eax, eax
0x1800e3a80  jnz     short loc_1800E3AA1
0x1800e3a82  mov     rcx, [rsp+268h+String]; String
0x1800e3a87  test    rcx, rcx
0x1800e3a8a  jz      short loc_1800E3AA1
0x1800e3a8c  call    cs:__imp__wtoi
0x1800e3a92  mov     [rsp+268h+var_128], eax
0x1800e3a99  mov     [rsp+268h+var_124], 1
0x1800e3aa1  mov     rax, [rsi]
0x1800e3aa4  lea     r9, [rsp+268h+String]
0x1800e3aa9  lea     r8, aAllowlocation; "AllowLocation"
0x1800e3ab0  mov     edx, r14d
0x1800e3ab3  mov     rcx, rsi
0x1800e3ab6  mov     rax, [rax+18h]
0x1800e3aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3abf  test    eax, eax
0x1800e3ac1  jnz     short loc_1800E3AE2
0x1800e3ac3  mov     rcx, [rsp+268h+String]; String
0x1800e3ac8  test    rcx, rcx
0x1800e3acb  jz      short loc_1800E3AE2
0x1800e3acd  call    cs:__imp__wtoi
0x1800e3ad3  mov     [rsp+268h+var_120], eax
0x1800e3ada  mov     [rsp+268h+var_11C], 1
0x1800e3ae2  mov     rax, [rsi]
0x1800e3ae5  lea     r9, [rsp+268h+String]
0x1800e3aea  lea     r8, aAllowmicrosoft_3; "AllowMicrosoftManagedDesktopProcessing"
0x1800e3af1  mov     edx, r14d
0x1800e3af4  mov     rcx, rsi
0x1800e3af7  mov     rax, [rax+18h]
0x1800e3afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b00  test    eax, eax
  ... truncated ...
```
