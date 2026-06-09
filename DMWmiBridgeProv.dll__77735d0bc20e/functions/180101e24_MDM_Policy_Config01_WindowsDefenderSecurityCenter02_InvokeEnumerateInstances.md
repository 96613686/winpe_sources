# MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances

- ea: `0x180101e24`
- end: `0x180102782`
- name: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances`
- size: `2398`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180101220`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f54`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000522c`
- `0x180005344`
- `0x18000537c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180101e24`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18010216f`
- `msvcrt!_wtoi` at `0x1801021b0`
- `msvcrt!_wtoi` at `0x1801021f1`
- `msvcrt!_wtoi` at `0x180102232`
- `msvcrt!_wtoi` at `0x180102273`
- `msvcrt!_wtoi` at `0x1801022b4`
- `msvcrt!_wtoi` at `0x1801022f5`
- `msvcrt!_wtoi` at `0x180102336`
- `msvcrt!_wtoi` at `0x180102377`
- `msvcrt!_wtoi` at `0x1801023b8`
- `msvcrt!_wtoi` at `0x1801023f9`
- `msvcrt!_wtoi` at `0x18010243a`
- `msvcrt!_wtoi` at `0x1801024b4`
- `msvcrt!_wtoi` at `0x1801024f5`
- `msvcrt!_wtoi` at `0x180102536`
- `msvcrt!_wtoi` at `0x180102577`
- `msvcrt!_wtoi` at `0x1801025b8`
- `msvcrt!_wtoi` at `0x1801025f9`
- `msvcrt!_wtoi` at `0x18010216f`
- `msvcrt!_wtoi` at `0x1801021b0`
- `msvcrt!_wtoi` at `0x1801021f1`
- `msvcrt!_wtoi` at `0x180102232`
- `msvcrt!_wtoi` at `0x180102273`
- `msvcrt!_wtoi` at `0x1801022b4`
- `msvcrt!_wtoi` at `0x1801022f5`
- `msvcrt!_wtoi` at `0x180102336`
- `msvcrt!_wtoi` at `0x180102377`
- `msvcrt!_wtoi` at `0x1801023b8`
- `msvcrt!_wtoi` at `0x1801023f9`
- `msvcrt!_wtoi` at `0x18010243a`
- `msvcrt!_wtoi` at `0x1801024b4`
- `msvcrt!_wtoi` at `0x1801024f5`
- `msvcrt!_wtoi` at `0x180102536`
- `msvcrt!_wtoi` at `0x180102577`
- `msvcrt!_wtoi` at `0x1801025b8`
- `msvcrt!_wtoi` at `0x1801025f9`

## string_xrefs

- `0x180102112`: `CompanyName`
- `0x18010220e`: `DisableDeviceSecurityUI`
- `0x180102394`: `DisableTpmFirmwareUpdateWarning`
- `0x1801025d5`: `HideWindowsSecurityNotificationAreaControl`
- `0x180102078`: `./Vendor/MSFT/Policy/Config`
- `0x180101e9f`: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02`
- `0x1801020b1`: `WindowsDefenderSecurityCenter`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances(
        MI_Context *self,
        char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1D8h] BYREF
  char v14; // [rsp+48h] [rbp-1D0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-1C0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1A8h] BYREF
  char v18; // [rsp+80h] [rbp-198h]
  int v19; // [rsp+88h] [rbp-190h] BYREF
  char v20; // [rsp+8Ch] [rbp-18Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-188h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-178h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-168h] BYREF
  int v24; // [rsp+120h] [rbp-F8h]
  char v25; // [rsp+124h] [rbp-F4h]
  int v26; // [rsp+128h] [rbp-F0h]
  char v27; // [rsp+12Ch] [rbp-ECh]
  int v28; // [rsp+130h] [rbp-E8h]
  char v29; // [rsp+134h] [rbp-E4h]
  int v30; // [rsp+138h] [rbp-E0h]
  char v31; // [rsp+13Ch] [rbp-DCh]
  int v32; // [rsp+140h] [rbp-D8h]
  char v33; // [rsp+144h] [rbp-D4h]
  int v34; // [rsp+148h] [rbp-D0h]
  char v35; // [rsp+14Ch] [rbp-CCh]
  int v36; // [rsp+150h] [rbp-C8h]
  char v37; // [rsp+154h] [rbp-C4h]
  int v38; // [rsp+158h] [rbp-C0h]
  char v39; // [rsp+15Ch] [rbp-BCh]
  int v40; // [rsp+160h] [rbp-B8h]
  char v41; // [rsp+164h] [rbp-B4h]
  int v42; // [rsp+168h] [rbp-B0h]
  char v43; // [rsp+16Ch] [rbp-ACh]
  int v44; // [rsp+170h] [rbp-A8h]
  char v45; // [rsp+174h] [rbp-A4h]
  int v46; // [rsp+178h] [rbp-A0h]
  char v47; // [rsp+17Ch] [rbp-9Ch]
  int v48; // [rsp+190h] [rbp-88h]
  char v49; // [rsp+194h] [rbp-84h]
  int v50; // [rsp+198h] [rbp-80h]
  char v51; // [rsp+19Ch] [rbp-7Ch]
  int v52; // [rsp+1A0h] [rbp-78h]
  char v53; // [rsp+1A4h] [rbp-74h]
  int v54; // [rsp+1A8h] [rbp-70h]
  char v55; // [rsp+1ACh] [rbp-6Ch]
  int v56; // [rsp+1B0h] [rbp-68h]
  char v57; // [rsp+1B4h] [rbp-64h]
  int v58; // [rsp+1B8h] [rbp-60h]
  char v59; // [rsp+1BCh] [rbp-5Ch]

  memset_0(&instance, 0, 0x130u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_WindowsDefenderSecurityCenter02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180366AAD,
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
           (struct WmiNodeInfo *)&MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
           0x18u,
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
              v7 = MI_Context_ConstructInstance(
                     self,
                     &MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti,
                     &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_115;
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
                      L"WindowsDefenderSecurityCenter",
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
                        L"CompanyName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableAccountProtectionUI",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableAppBrowserUI",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableClearTpmButton",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDeviceSecurityUI",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableEnhancedNotifications",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableFamilyUI",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableHealthUI",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableNetworkUI",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableNotifications",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableTpmFirmwareUpdateWarning",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableVirusUI",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisallowExploitProtectionOverride",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"Email",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableCustomizedToasts",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableInAppCustomization",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HideRansomwareDataRecovery",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HideSecureBoot",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HideTPMTroubleshooting",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HideWindowsSecurityNotificationAreaControl",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"Phone",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"URL",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
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
    goto LABEL_106;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_106:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (unsigned int)v15;
  }
LABEL_115:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033BCCC,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return v7;
}

```

## disassembly

```asm
0x180101e24  mov     [rsp+arg_8], rbx
0x180101e29  mov     [rsp+arg_10], rsi
0x180101e2e  push    rdi
0x180101e2f  push    r12
0x180101e31  push    r13
0x180101e33  push    r14
0x180101e35  push    r15
0x180101e37  sub     rsp, 1F0h
0x180101e3e  mov     rax, cs:__security_cookie
0x180101e45  xor     rax, rsp
0x180101e48  mov     [rsp+218h+var_38], rax
0x180101e50  mov     r13b, dl
0x180101e53  mov     r12, rcx
0x180101e56  xor     edx, edx; Val
0x180101e58  mov     r8d, 130h; Size
0x180101e5e  lea     rcx, [rsp+218h+instance]; void *
0x180101e66  call    memset_0
0x180101e6b  xor     edi, edi
0x180101e6d  mov     [rsp+218h+var_1D0], dil
0x180101e72  mov     [rsp+218h+String], rdi
0x180101e77  mov     [rsp+218h+var_190], edi
0x180101e7e  mov     [rsp+218h+var_18C], dil
0x180101e86  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180101e8d  mov     [rsp+218h+var_1C0], rax
0x180101e92  lea     rax, [rsp+218h+var_190]
0x180101e9a  mov     [rsp+218h+var_1B8], rax
0x180101e9f  lea     rax, aMdmPolicyConfi_102; "MDM_Policy_Config01_WindowsDefenderSecu"...
0x180101ea6  mov     [rsp+218h+var_1B0], rax
0x180101eab  lea     rcx, [rsp+218h+var_190]
0x180101eb3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180101eb8  mov     eax, cs:dword_180380B68
0x180101ebe  cmp     eax, 5
0x180101ec1  jbe     short loc_180101F33
0x180101ec3  mov     rdx, 200000000000h
0x180101ecd  lea     rcx, dword_180380B68
0x180101ed4  call    _tlgKeywordOn
0x180101ed9  test    al, al
0x180101edb  jz      short loc_180101F33
0x180101edd  cmp     [rsp+218h+var_18C], dil
0x180101ee5  jz      short loc_180101F15
0x180101ee7  cmp     [rsp+218h+var_178], edi
0x180101eee  jnz     short loc_180101F0B
0x180101ef0  cmp     [rsp+218h+var_174], edi
0x180101ef7  jnz     short loc_180101F0B
0x180101ef9  cmp     [rsp+218h+var_170], edi
0x180101f00  jnz     short loc_180101F0B
0x180101f02  cmp     [rsp+218h+var_16C], edi
0x180101f09  jz      short loc_180101F15
0x180101f0b  lea     r9, [rsp+218h+var_178]
0x180101f13  jmp     short loc_180101F18
0x180101f15  mov     r9, rdi
0x180101f18  lea     r8, [rsp+218h+var_188]
0x180101f20  lea     rdx, byte_180366AAD
0x180101f27  lea     rcx, dword_180380B68
0x180101f2e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180101f33  lea     rcx, [rsp+218h+var_1C0]; this
0x180101f38  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180101f3d  nop
0x180101f3e  mov     [rsp+218h+var_1C8], rdi
0x180101f43  lea     rax, [rsp+218h+var_1C8]
0x180101f48  mov     [rsp+218h+var_1E8], rax
0x180101f4d  mov     [rsp+218h+var_1F0], 2
0x180101f55  mov     [rsp+218h+var_1F8], 18h
0x180101f5d  lea     r9, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList
0x180101f64  xor     r8d, r8d
0x180101f67  xor     edx, edx
0x180101f69  mov     rcx, r12
0x180101f6c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180101f71  mov     r15d, eax
0x180101f74  test    eax, eax
0x180101f76  jz      short loc_180101F7D
0x180101f78  jmp     loc_1801026E2
0x180101f7d  lea     rbx, [rsp+218h+var_1C8]
0x180101f82  mov     [rsp+218h+var_1A0], rbx
0x180101f87  mov     r14d, 1
0x180101f8d  mov     [rsp+218h+var_198], r14b
0x180101f95  mov     rsi, [rsp+218h+var_1C8]
0x180101f9a  test    rsi, rsi
0x180101f9d  jnz     short loc_180101FA7
0x180101f9f  mov     r15d, r14d
0x180101fa2  jmp     loc_1801026E2
0x180101fa7  mov     rax, [rsi]
0x180101faa  mov     rcx, rsi
0x180101fad  mov     rax, [rax+10h]
0x180101fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101fb6  mov     r15d, eax
0x180101fb9  test    eax, eax
0x180101fbb  jz      short loc_180101FDB
0x180101fbd  mov     rcx, [rsp+218h+var_1C8]
0x180101fc2  test    rcx, rcx
0x180101fc5  jz      short loc_180101FD6
0x180101fc7  mov     rax, [rcx]
0x180101fca  mov     edx, r14d
0x180101fcd  mov     rax, [rax]
0x180101fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101fd5  nop
0x180101fd6  jmp     loc_1801026E2
0x180101fdb  mov     rax, [rsi]
0x180101fde  mov     rcx, rsi
0x180101fe1  mov     rax, [rax+8]
0x180101fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101fea  mov     r15d, eax
0x180101fed  test    eax, eax
0x180101fef  jz      short loc_18010200F
0x180101ff1  mov     rcx, [rsp+218h+var_1C8]
0x180101ff6  test    rcx, rcx
0x180101ff9  jz      short loc_18010200A
0x180101ffb  mov     rax, [rcx]
0x180101ffe  mov     edx, r14d
0x180102001  mov     rax, [rax]
0x180102004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102009  nop
0x18010200a  jmp     loc_1801026E2
0x18010200f  mov     r14d, edi
0x180102012  mov     rax, [rsi+108h]
0x180102019  sub     rax, [rsi+100h]
0x180102020  sar     rax, 4
0x180102024  cmp     r14d, eax
0x180102027  jnb     loc_1801026AA
0x18010202d  lea     r8, [rsp+218h+instance]; instance
0x180102035  lea     rdx, MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x18010203c  mov     rcx, r12; context
0x18010203f  call    MI_Context_ConstructInstance
0x180102044  mov     r15d, eax
0x180102047  test    eax, eax
0x180102049  jz      short loc_18010206B
0x18010204b  mov     rcx, [rbx]
0x18010204e  test    rcx, rcx
0x180102051  jz      short loc_180102066
0x180102053  mov     rax, [rcx]
0x180102056  mov     edx, 1
0x18010205b  mov     rax, [rax]
0x18010205e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102063  mov     [rbx], rdi
0x180102066  jmp     loc_1801026E2
0x18010206b  mov     [rsp+218h+var_1D0], 1
0x180102070  mov     rax, [rsi]
0x180102073  lea     r9, [rsp+218h+String]
0x180102078  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18010207f  mov     edx, r14d
0x180102082  mov     rcx, rsi
0x180102085  mov     rax, [rax+18h]
0x180102089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010208e  test    eax, eax
0x180102090  jnz     short loc_1801020A9
0x180102092  mov     rdx, [rsp+218h+String]
0x180102097  test    rdx, rdx
0x18010209a  jz      short loc_1801020A9
0x18010209c  lea     rcx, [rsp+218h+instance]
0x1801020a4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801020a9  mov     rax, [rsi]
0x1801020ac  lea     r9, [rsp+218h+String]
0x1801020b1  lea     r8, aWindowsdefende; "WindowsDefenderSecurityCenter"
0x1801020b8  mov     edx, r14d
0x1801020bb  mov     rcx, rsi
0x1801020be  mov     rax, [rax+18h]
0x1801020c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801020c7  test    eax, eax
0x1801020c9  jnz     short loc_1801020E2
0x1801020cb  mov     rdx, [rsp+218h+String]
0x1801020d0  test    rdx, rdx
0x1801020d3  jz      short loc_1801020E2
0x1801020d5  lea     rcx, [rsp+218h+instance]
0x1801020dd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801020e2  cmp     r13b, 1
0x1801020e6  jnz     short loc_18010210A
0x1801020e8  lea     rdx, [rsp+218h+instance]
0x1801020f0  mov     rcx, r12; self
0x1801020f3  call    MI_Instance_Destruct
0x1801020f8  lea     rcx, [rsp+218h+instance]; self
0x180102100  call    MI_Instance_Destruct
0x180102105  jmp     loc_18010269D
0x18010210a  mov     rax, [rsi]
0x18010210d  lea     r9, [rsp+218h+String]
0x180102112  lea     r8, aCompanyname; "CompanyName"
0x180102119  mov     edx, r14d
0x18010211c  mov     rcx, rsi
0x18010211f  mov     rax, [rax+18h]
0x180102123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102128  test    eax, eax
0x18010212a  jnz     short loc_180102143
0x18010212c  mov     rdx, [rsp+218h+String]
0x180102131  test    rdx, rdx
0x180102134  jz      short loc_180102143
0x180102136  lea     rcx, [rsp+218h+instance]
0x18010213e  call    MDM_VPNv2_User_01_Set_EdpModeId
0x180102143  mov     rax, [rsi]
0x180102146  lea     r9, [rsp+218h+String]
0x18010214b  lea     r8, aDisableaccount; "DisableAccountProtectionUI"
0x180102152  mov     edx, r14d
0x180102155  mov     rcx, rsi
0x180102158  mov     rax, [rax+18h]
0x18010215c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102161  test    eax, eax
0x180102163  jnz     short loc_180102184
0x180102165  mov     rcx, [rsp+218h+String]; String
0x18010216a  test    rcx, rcx
0x18010216d  jz      short loc_180102184
0x18010216f  call    cs:__imp__wtoi
0x180102175  mov     [rsp+218h+var_F8], eax
0x18010217c  mov     [rsp+218h+var_F4], 1
0x180102184  mov     rax, [rsi]
0x180102187  lea     r9, [rsp+218h+String]
0x18010218c  lea     r8, aDisableappbrow; "DisableAppBrowserUI"
0x180102193  mov     edx, r14d
0x180102196  mov     rcx, rsi
0x180102199  mov     rax, [rax+18h]
0x18010219d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021a2  test    eax, eax
0x1801021a4  jnz     short loc_1801021C5
0x1801021a6  mov     rcx, [rsp+218h+String]; String
0x1801021ab  test    rcx, rcx
0x1801021ae  jz      short loc_1801021C5
0x1801021b0  call    cs:__imp__wtoi
0x1801021b6  mov     [rsp+218h+var_F0], eax
0x1801021bd  mov     [rsp+218h+var_EC], 1
0x1801021c5  mov     rax, [rsi]
0x1801021c8  lea     r9, [rsp+218h+String]
0x1801021cd  lea     r8, aDisablecleartp; "DisableClearTpmButton"
0x1801021d4  mov     edx, r14d
0x1801021d7  mov     rcx, rsi
0x1801021da  mov     rax, [rax+18h]
0x1801021de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021e3  test    eax, eax
0x1801021e5  jnz     short loc_180102206
0x1801021e7  mov     rcx, [rsp+218h+String]; String
0x1801021ec  test    rcx, rcx
0x1801021ef  jz      short loc_180102206
0x1801021f1  call    cs:__imp__wtoi
0x1801021f7  mov     [rsp+218h+var_E8], eax
0x1801021fe  mov     [rsp+218h+var_E4], 1
0x180102206  mov     rax, [rsi]
0x180102209  lea     r9, [rsp+218h+String]
0x18010220e  lea     r8, aDisabledevices; "DisableDeviceSecurityUI"
0x180102215  mov     edx, r14d
0x180102218  mov     rcx, rsi
0x18010221b  mov     rax, [rax+18h]
0x18010221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102224  test    eax, eax
0x180102226  jnz     short loc_180102247
0x180102228  mov     rcx, [rsp+218h+String]; String
0x18010222d  test    rcx, rcx
0x180102230  jz      short loc_180102247
0x180102232  call    cs:__imp__wtoi
0x180102238  mov     [rsp+218h+var_E0], eax
0x18010223f  mov     [rsp+218h+var_DC], 1
0x180102247  mov     rax, [rsi]
0x18010224a  lea     r9, [rsp+218h+String]
0x18010224f  lea     r8, aDisableenhance; "DisableEnhancedNotifications"
0x180102256  mov     edx, r14d
0x180102259  mov     rcx, rsi
0x18010225c  mov     rax, [rax+18h]
0x180102260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102265  test    eax, eax
0x180102267  jnz     short loc_180102288
0x180102269  mov     rcx, [rsp+218h+String]; String
0x18010226e  test    rcx, rcx
0x180102271  jz      short loc_180102288
0x180102273  call    cs:__imp__wtoi
0x180102279  mov     [rsp+218h+var_D8], eax
0x180102280  mov     [rsp+218h+var_D4], 1
0x180102288  mov     rax, [rsi]
0x18010228b  lea     r9, [rsp+218h+String]
0x180102290  lea     r8, aDisablefamilyu; "DisableFamilyUI"
0x180102297  mov     edx, r14d
0x18010229a  mov     rcx, rsi
0x18010229d  mov     rax, [rax+18h]
0x1801022a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801022a6  test    eax, eax
0x1801022a8  jnz     short loc_1801022C9
0x1801022aa  mov     rcx, [rsp+218h+String]; String
0x1801022af  test    rcx, rcx
0x1801022b2  jz      short loc_1801022C9
0x1801022b4  call    cs:__imp__wtoi
0x1801022ba  mov     [rsp+218h+var_D0], eax
0x1801022c1  mov     [rsp+218h+var_CC], 1
0x1801022c9  mov     rax, [rsi]
0x1801022cc  lea     r9, [rsp+218h+String]
0x1801022d1  lea     r8, aDisablehealthu; "DisableHealthUI"
0x1801022d8  mov     edx, r14d
0x1801022db  mov     rcx, rsi
0x1801022de  mov     rax, [rax+18h]
0x1801022e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801022e7  test    eax, eax
0x1801022e9  jnz     short loc_18010230A
0x1801022eb  mov     rcx, [rsp+218h+String]; String
0x1801022f0  test    rcx, rcx
0x1801022f3  jz      short loc_18010230A
0x1801022f5  call    cs:__imp__wtoi
0x1801022fb  mov     [rsp+218h+var_C8], eax
0x180102302  mov     [rsp+218h+var_C4], 1
0x18010230a  mov     rax, [rsi]
0x18010230d  lea     r9, [rsp+218h+String]
0x180102312  lea     r8, aDisablenetwork; "DisableNetworkUI"
0x180102319  mov     edx, r14d
0x18010231c  mov     rcx, rsi
0x18010231f  mov     rax, [rax+18h]
0x180102323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102328  test    eax, eax
0x18010232a  jnz     short loc_18010234B
  ... truncated ...
```
