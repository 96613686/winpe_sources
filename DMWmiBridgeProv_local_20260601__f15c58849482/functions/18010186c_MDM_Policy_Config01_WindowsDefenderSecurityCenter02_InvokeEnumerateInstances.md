# MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances

- ea: `0x18010186c`
- end: `0x180102237`
- name: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances`
- size: `2507`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180100c80`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005128`
- `0x180005160`
- `0x180005198`
- `0x180005400`
- `0x180005518`
- `0x180005550`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18010186c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180101bb7`
- `msvcrt!_wtoi` at `0x180101bfe`
- `msvcrt!_wtoi` at `0x180101c45`
- `msvcrt!_wtoi` at `0x180101c8c`
- `msvcrt!_wtoi` at `0x180101cd3`
- `msvcrt!_wtoi` at `0x180101d1a`
- `msvcrt!_wtoi` at `0x180101d61`
- `msvcrt!_wtoi` at `0x180101da8`
- `msvcrt!_wtoi` at `0x180101def`
- `msvcrt!_wtoi` at `0x180101e36`
- `msvcrt!_wtoi` at `0x180101e7d`
- `msvcrt!_wtoi` at `0x180101ec4`
- `msvcrt!_wtoi` at `0x180101f44`
- `msvcrt!_wtoi` at `0x180101f8b`
- `msvcrt!_wtoi` at `0x180101fd2`
- `msvcrt!_wtoi` at `0x180102019`
- `msvcrt!_wtoi` at `0x180102060`
- `msvcrt!_wtoi` at `0x1801020a7`
- `msvcrt!_wtoi` at `0x180101bb7`
- `msvcrt!_wtoi` at `0x180101bfe`
- `msvcrt!_wtoi` at `0x180101c45`
- `msvcrt!_wtoi` at `0x180101c8c`
- `msvcrt!_wtoi` at `0x180101cd3`
- `msvcrt!_wtoi` at `0x180101d1a`
- `msvcrt!_wtoi` at `0x180101d61`
- `msvcrt!_wtoi` at `0x180101da8`
- `msvcrt!_wtoi` at `0x180101def`
- `msvcrt!_wtoi` at `0x180101e36`
- `msvcrt!_wtoi` at `0x180101e7d`
- `msvcrt!_wtoi` at `0x180101ec4`
- `msvcrt!_wtoi` at `0x180101f44`
- `msvcrt!_wtoi` at `0x180101f8b`
- `msvcrt!_wtoi` at `0x180101fd2`
- `msvcrt!_wtoi` at `0x180102019`
- `msvcrt!_wtoi` at `0x180102060`
- `msvcrt!_wtoi` at `0x1801020a7`

## string_xrefs

- `0x180101b5a`: `CompanyName`
- `0x180101c68`: `DisableDeviceSecurityUI`
- `0x180101e12`: `DisableTpmFirmwareUpdateWarning`
- `0x180102083`: `HideWindowsSecurityNotificationAreaControl`
- `0x180101ac0`: `./Vendor/MSFT/Policy/Config`
- `0x1801018e7`: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02`
- `0x180101af9`: `WindowsDefenderSecurityCenter`

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
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1D8h] BYREF
  char v14; // [rsp+48h] [rbp-1D0h]
  _QWORD *v15; // [rsp+50h] [rbp-1C8h] BYREF
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
    v7 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         0,
                         0,
                         &MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
                         24,
                         2,
                         &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(
                     self,
                     &MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti,
                     &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_115;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CompanyName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableAccountProtectionUI",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableAppBrowserUI",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableClearTpmButton",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDeviceSecurityUI",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableEnhancedNotifications",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableFamilyUI",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableHealthUI",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableNetworkUI",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableNotifications",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableTpmFirmwareUpdateWarning",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableVirusUI",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisallowExploitProtectionOverride",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"Email",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableCustomizedToasts",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableInAppCustomization",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HideRansomwareDataRecovery",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HideSecureBoot",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HideTPMTroubleshooting",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HideWindowsSecurityNotificationAreaControl",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"Phone",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
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
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
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
    v7 = (int)v15;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18010186c  mov     [rsp+arg_8], rbx
0x180101871  mov     [rsp+arg_10], rsi
0x180101876  push    rdi
0x180101877  push    r12
0x180101879  push    r13
0x18010187b  push    r14
0x18010187d  push    r15
0x18010187f  sub     rsp, 1F0h
0x180101886  mov     rax, cs:__security_cookie
0x18010188d  xor     rax, rsp
0x180101890  mov     [rsp+218h+var_38], rax
0x180101898  mov     r13b, dl
0x18010189b  mov     r12, rcx
0x18010189e  xor     edx, edx; Val
0x1801018a0  mov     r8d, 130h; Size
0x1801018a6  lea     rcx, [rsp+218h+instance]; void *
0x1801018ae  call    memset_0
0x1801018b3  xor     edi, edi
0x1801018b5  mov     [rsp+218h+var_1D0], dil
0x1801018ba  mov     [rsp+218h+String], rdi
0x1801018bf  mov     [rsp+218h+var_190], edi
0x1801018c6  mov     [rsp+218h+var_18C], dil
0x1801018ce  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801018d5  mov     [rsp+218h+var_1C0], rax
0x1801018da  lea     rax, [rsp+218h+var_190]
0x1801018e2  mov     [rsp+218h+var_1B8], rax
0x1801018e7  lea     rax, aMdmPolicyConfi_102; "MDM_Policy_Config01_WindowsDefenderSecu"...
0x1801018ee  mov     [rsp+218h+var_1B0], rax
0x1801018f3  lea     rcx, [rsp+218h+var_190]
0x1801018fb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180101900  mov     eax, cs:dword_180380B68
0x180101906  cmp     eax, 5
0x180101909  jbe     short loc_18010197B
0x18010190b  mov     rdx, 200000000000h
0x180101915  lea     rcx, dword_180380B68
0x18010191c  call    _tlgKeywordOn
0x180101921  test    al, al
0x180101923  jz      short loc_18010197B
0x180101925  cmp     [rsp+218h+var_18C], dil
0x18010192d  jz      short loc_18010195D
0x18010192f  cmp     [rsp+218h+var_178], edi
0x180101936  jnz     short loc_180101953
0x180101938  cmp     [rsp+218h+var_174], edi
0x18010193f  jnz     short loc_180101953
0x180101941  cmp     [rsp+218h+var_170], edi
0x180101948  jnz     short loc_180101953
0x18010194a  cmp     [rsp+218h+var_16C], edi
0x180101951  jz      short loc_18010195D
0x180101953  lea     r9, [rsp+218h+var_178]
0x18010195b  jmp     short loc_180101960
0x18010195d  mov     r9, rdi
0x180101960  lea     r8, [rsp+218h+var_188]
0x180101968  lea     rdx, byte_180366AAD
0x18010196f  lea     rcx, dword_180380B68
0x180101976  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010197b  lea     rcx, [rsp+218h+var_1C0]; this
0x180101980  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180101985  nop
0x180101986  mov     [rsp+218h+var_1C8], rdi
0x18010198b  lea     rax, [rsp+218h+var_1C8]
0x180101990  mov     [rsp+218h+var_1E8], rax
0x180101995  mov     [rsp+218h+var_1F0], 2
0x18010199d  mov     [rsp+218h+var_1F8], 18h
0x1801019a5  lea     r9, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList
0x1801019ac  xor     r8d, r8d
0x1801019af  xor     edx, edx
0x1801019b1  mov     rcx, r12
0x1801019b4  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801019b9  mov     r15d, eax
0x1801019bc  test    eax, eax
0x1801019be  jz      short loc_1801019C5
0x1801019c0  jmp     loc_180102196
0x1801019c5  lea     rbx, [rsp+218h+var_1C8]
0x1801019ca  mov     [rsp+218h+var_1A0], rbx
0x1801019cf  mov     r14d, 1
0x1801019d5  mov     [rsp+218h+var_198], r14b
0x1801019dd  mov     rsi, [rsp+218h+var_1C8]
0x1801019e2  test    rsi, rsi
0x1801019e5  jnz     short loc_1801019EF
0x1801019e7  mov     r15d, r14d
0x1801019ea  jmp     loc_180102196
0x1801019ef  mov     rax, [rsi]
0x1801019f2  mov     rcx, rsi
0x1801019f5  mov     rax, [rax+10h]
0x1801019f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801019fe  mov     r15d, eax
0x180101a01  test    eax, eax
0x180101a03  jz      short loc_180101A23
0x180101a05  mov     rcx, [rsp+218h+var_1C8]
0x180101a0a  test    rcx, rcx
0x180101a0d  jz      short loc_180101A1E
0x180101a0f  mov     rax, [rcx]
0x180101a12  mov     edx, r14d
0x180101a15  mov     rax, [rax]
0x180101a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a1d  nop
0x180101a1e  jmp     loc_180102196
0x180101a23  mov     rax, [rsi]
0x180101a26  mov     rcx, rsi
0x180101a29  mov     rax, [rax+8]
0x180101a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a32  mov     r15d, eax
0x180101a35  test    eax, eax
0x180101a37  jz      short loc_180101A57
0x180101a39  mov     rcx, [rsp+218h+var_1C8]
0x180101a3e  test    rcx, rcx
0x180101a41  jz      short loc_180101A52
0x180101a43  mov     rax, [rcx]
0x180101a46  mov     edx, r14d
0x180101a49  mov     rax, [rax]
0x180101a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a51  nop
0x180101a52  jmp     loc_180102196
0x180101a57  mov     r14d, edi
0x180101a5a  mov     rax, [rsi+108h]
0x180101a61  sub     rax, [rsi+100h]
0x180101a68  sar     rax, 4
0x180101a6c  cmp     r14d, eax
0x180101a6f  jnb     loc_18010215E
0x180101a75  lea     r8, [rsp+218h+instance]; instance
0x180101a7d  lea     rdx, MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x180101a84  mov     rcx, r12; context
0x180101a87  call    MI_Context_ConstructInstance
0x180101a8c  mov     r15d, eax
0x180101a8f  test    eax, eax
0x180101a91  jz      short loc_180101AB3
0x180101a93  mov     rcx, [rbx]
0x180101a96  test    rcx, rcx
0x180101a99  jz      short loc_180101AAE
0x180101a9b  mov     rax, [rcx]
0x180101a9e  mov     edx, 1
0x180101aa3  mov     rax, [rax]
0x180101aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101aab  mov     [rbx], rdi
0x180101aae  jmp     loc_180102196
0x180101ab3  mov     [rsp+218h+var_1D0], 1
0x180101ab8  mov     rax, [rsi]
0x180101abb  lea     r9, [rsp+218h+String]
0x180101ac0  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180101ac7  mov     edx, r14d
0x180101aca  mov     rcx, rsi
0x180101acd  mov     rax, [rax+18h]
0x180101ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ad6  test    eax, eax
0x180101ad8  jnz     short loc_180101AF1
0x180101ada  mov     rdx, [rsp+218h+String]
0x180101adf  test    rdx, rdx
0x180101ae2  jz      short loc_180101AF1
0x180101ae4  lea     rcx, [rsp+218h+instance]
0x180101aec  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180101af1  mov     rax, [rsi]
0x180101af4  lea     r9, [rsp+218h+String]
0x180101af9  lea     r8, aWindowsdefende; "WindowsDefenderSecurityCenter"
0x180101b00  mov     edx, r14d
0x180101b03  mov     rcx, rsi
0x180101b06  mov     rax, [rax+18h]
0x180101b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101b0f  test    eax, eax
0x180101b11  jnz     short loc_180101B2A
0x180101b13  mov     rdx, [rsp+218h+String]
0x180101b18  test    rdx, rdx
0x180101b1b  jz      short loc_180101B2A
0x180101b1d  lea     rcx, [rsp+218h+instance]
0x180101b25  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180101b2a  cmp     r13b, 1
0x180101b2e  jnz     short loc_180101B52
0x180101b30  lea     rdx, [rsp+218h+instance]
0x180101b38  mov     rcx, r12; self
0x180101b3b  call    MI_Instance_Destruct
0x180101b40  lea     rcx, [rsp+218h+instance]; self
0x180101b48  call    MI_Instance_Destruct
0x180101b4d  jmp     loc_180102151
0x180101b52  mov     rax, [rsi]
0x180101b55  lea     r9, [rsp+218h+String]
0x180101b5a  lea     r8, aCompanyname; "CompanyName"
0x180101b61  mov     edx, r14d
0x180101b64  mov     rcx, rsi
0x180101b67  mov     rax, [rax+18h]
0x180101b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101b70  test    eax, eax
0x180101b72  jnz     short loc_180101B8B
0x180101b74  mov     rdx, [rsp+218h+String]
0x180101b79  test    rdx, rdx
0x180101b7c  jz      short loc_180101B8B
0x180101b7e  lea     rcx, [rsp+218h+instance]
0x180101b86  call    MDM_VPNv2_User_01_Set_EdpModeId
0x180101b8b  mov     rax, [rsi]
0x180101b8e  lea     r9, [rsp+218h+String]
0x180101b93  lea     r8, aDisableaccount; "DisableAccountProtectionUI"
0x180101b9a  mov     edx, r14d
0x180101b9d  mov     rcx, rsi
0x180101ba0  mov     rax, [rax+18h]
0x180101ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ba9  test    eax, eax
0x180101bab  jnz     short loc_180101BD2
0x180101bad  mov     rcx, [rsp+218h+String]; String
0x180101bb2  test    rcx, rcx
0x180101bb5  jz      short loc_180101BD2
0x180101bb7  call    cs:__imp__wtoi
0x180101bbe  nop     dword ptr [rax+rax+00h]
0x180101bc3  mov     [rsp+218h+var_F8], eax
0x180101bca  mov     [rsp+218h+var_F4], 1
0x180101bd2  mov     rax, [rsi]
0x180101bd5  lea     r9, [rsp+218h+String]
0x180101bda  lea     r8, aDisableappbrow; "DisableAppBrowserUI"
0x180101be1  mov     edx, r14d
0x180101be4  mov     rcx, rsi
0x180101be7  mov     rax, [rax+18h]
0x180101beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101bf0  test    eax, eax
0x180101bf2  jnz     short loc_180101C19
0x180101bf4  mov     rcx, [rsp+218h+String]; String
0x180101bf9  test    rcx, rcx
0x180101bfc  jz      short loc_180101C19
0x180101bfe  call    cs:__imp__wtoi
0x180101c05  nop     dword ptr [rax+rax+00h]
0x180101c0a  mov     [rsp+218h+var_F0], eax
0x180101c11  mov     [rsp+218h+var_EC], 1
0x180101c19  mov     rax, [rsi]
0x180101c1c  lea     r9, [rsp+218h+String]
0x180101c21  lea     r8, aDisablecleartp; "DisableClearTpmButton"
0x180101c28  mov     edx, r14d
0x180101c2b  mov     rcx, rsi
0x180101c2e  mov     rax, [rax+18h]
0x180101c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101c37  test    eax, eax
0x180101c39  jnz     short loc_180101C60
0x180101c3b  mov     rcx, [rsp+218h+String]; String
0x180101c40  test    rcx, rcx
0x180101c43  jz      short loc_180101C60
0x180101c45  call    cs:__imp__wtoi
0x180101c4c  nop     dword ptr [rax+rax+00h]
0x180101c51  mov     [rsp+218h+var_E8], eax
0x180101c58  mov     [rsp+218h+var_E4], 1
0x180101c60  mov     rax, [rsi]
0x180101c63  lea     r9, [rsp+218h+String]
0x180101c68  lea     r8, aDisabledevices; "DisableDeviceSecurityUI"
0x180101c6f  mov     edx, r14d
0x180101c72  mov     rcx, rsi
0x180101c75  mov     rax, [rax+18h]
0x180101c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101c7e  test    eax, eax
0x180101c80  jnz     short loc_180101CA7
0x180101c82  mov     rcx, [rsp+218h+String]; String
0x180101c87  test    rcx, rcx
0x180101c8a  jz      short loc_180101CA7
0x180101c8c  call    cs:__imp__wtoi
0x180101c93  nop     dword ptr [rax+rax+00h]
0x180101c98  mov     [rsp+218h+var_E0], eax
0x180101c9f  mov     [rsp+218h+var_DC], 1
0x180101ca7  mov     rax, [rsi]
0x180101caa  lea     r9, [rsp+218h+String]
0x180101caf  lea     r8, aDisableenhance; "DisableEnhancedNotifications"
0x180101cb6  mov     edx, r14d
0x180101cb9  mov     rcx, rsi
0x180101cbc  mov     rax, [rax+18h]
0x180101cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101cc5  test    eax, eax
0x180101cc7  jnz     short loc_180101CEE
0x180101cc9  mov     rcx, [rsp+218h+String]; String
0x180101cce  test    rcx, rcx
0x180101cd1  jz      short loc_180101CEE
0x180101cd3  call    cs:__imp__wtoi
0x180101cda  nop     dword ptr [rax+rax+00h]
0x180101cdf  mov     [rsp+218h+var_D8], eax
0x180101ce6  mov     [rsp+218h+var_D4], 1
0x180101cee  mov     rax, [rsi]
0x180101cf1  lea     r9, [rsp+218h+String]
0x180101cf6  lea     r8, aDisablefamilyu; "DisableFamilyUI"
0x180101cfd  mov     edx, r14d
0x180101d00  mov     rcx, rsi
0x180101d03  mov     rax, [rax+18h]
0x180101d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101d0c  test    eax, eax
0x180101d0e  jnz     short loc_180101D35
0x180101d10  mov     rcx, [rsp+218h+String]; String
0x180101d15  test    rcx, rcx
0x180101d18  jz      short loc_180101D35
0x180101d1a  call    cs:__imp__wtoi
0x180101d21  nop     dword ptr [rax+rax+00h]
0x180101d26  mov     [rsp+218h+var_D0], eax
0x180101d2d  mov     [rsp+218h+var_CC], 1
0x180101d35  mov     rax, [rsi]
0x180101d38  lea     r9, [rsp+218h+String]
0x180101d3d  lea     r8, aDisablehealthu; "DisableHealthUI"
0x180101d44  mov     edx, r14d
0x180101d47  mov     rcx, rsi
0x180101d4a  mov     rax, [rax+18h]
0x180101d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101d53  test    eax, eax
0x180101d55  jnz     short loc_180101D7C
0x180101d57  mov     rcx, [rsp+218h+String]; String
0x180101d5c  test    rcx, rcx
0x180101d5f  jz      short loc_180101D7C
0x180101d61  call    cs:__imp__wtoi
0x180101d68  nop     dword ptr [rax+rax+00h]
0x180101d6d  mov     [rsp+218h+var_C8], eax
0x180101d74  mov     [rsp+218h+var_C4], 1
0x180101d7c  mov     rax, [rsi]
0x180101d7f  lea     r9, [rsp+218h+String]
  ... truncated ...
```
