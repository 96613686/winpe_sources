# MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances

- ea: `0x1801b7dfc`
- end: `0x1801b87c7`
- name: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances`
- size: `2507`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801b7210`

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
- `0x1801b7dfc`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801b8147`
- `msvcrt!_wtoi` at `0x1801b818e`
- `msvcrt!_wtoi` at `0x1801b81d5`
- `msvcrt!_wtoi` at `0x1801b821c`
- `msvcrt!_wtoi` at `0x1801b8263`
- `msvcrt!_wtoi` at `0x1801b82aa`
- `msvcrt!_wtoi` at `0x1801b82f1`
- `msvcrt!_wtoi` at `0x1801b8338`
- `msvcrt!_wtoi` at `0x1801b837f`
- `msvcrt!_wtoi` at `0x1801b83c6`
- `msvcrt!_wtoi` at `0x1801b840d`
- `msvcrt!_wtoi` at `0x1801b8454`
- `msvcrt!_wtoi` at `0x1801b84d4`
- `msvcrt!_wtoi` at `0x1801b851b`
- `msvcrt!_wtoi` at `0x1801b8562`
- `msvcrt!_wtoi` at `0x1801b85a9`
- `msvcrt!_wtoi` at `0x1801b85f0`
- `msvcrt!_wtoi` at `0x1801b8637`
- `msvcrt!_wtoi` at `0x1801b8147`
- `msvcrt!_wtoi` at `0x1801b818e`
- `msvcrt!_wtoi` at `0x1801b81d5`
- `msvcrt!_wtoi` at `0x1801b821c`
- `msvcrt!_wtoi` at `0x1801b8263`
- `msvcrt!_wtoi` at `0x1801b82aa`
- `msvcrt!_wtoi` at `0x1801b82f1`
- `msvcrt!_wtoi` at `0x1801b8338`
- `msvcrt!_wtoi` at `0x1801b837f`
- `msvcrt!_wtoi` at `0x1801b83c6`
- `msvcrt!_wtoi` at `0x1801b840d`
- `msvcrt!_wtoi` at `0x1801b8454`
- `msvcrt!_wtoi` at `0x1801b84d4`
- `msvcrt!_wtoi` at `0x1801b851b`
- `msvcrt!_wtoi` at `0x1801b8562`
- `msvcrt!_wtoi` at `0x1801b85a9`
- `msvcrt!_wtoi` at `0x1801b85f0`
- `msvcrt!_wtoi` at `0x1801b8637`

## string_xrefs

- `0x1801b80ea`: `CompanyName`
- `0x1801b81f8`: `DisableDeviceSecurityUI`
- `0x1801b83a2`: `DisableTpmFirmwareUpdateWarning`
- `0x1801b8613`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801b7e77`: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02`
- `0x1801b8089`: `WindowsDefenderSecurityCenter`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances(
        MI_Context *self,
        char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1D8h] BYREF
  char v11; // [rsp+48h] [rbp-1D0h]
  _QWORD *v12; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-1C0h] BYREF
  char v14; // [rsp+80h] [rbp-198h]
  int v15; // [rsp+88h] [rbp-190h] BYREF
  char v16; // [rsp+8Ch] [rbp-18Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-188h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-178h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-168h] BYREF
  int v20; // [rsp+120h] [rbp-F8h]
  char v21; // [rsp+124h] [rbp-F4h]
  int v22; // [rsp+128h] [rbp-F0h]
  char v23; // [rsp+12Ch] [rbp-ECh]
  int v24; // [rsp+130h] [rbp-E8h]
  char v25; // [rsp+134h] [rbp-E4h]
  int v26; // [rsp+138h] [rbp-E0h]
  char v27; // [rsp+13Ch] [rbp-DCh]
  int v28; // [rsp+140h] [rbp-D8h]
  char v29; // [rsp+144h] [rbp-D4h]
  int v30; // [rsp+148h] [rbp-D0h]
  char v31; // [rsp+14Ch] [rbp-CCh]
  int v32; // [rsp+150h] [rbp-C8h]
  char v33; // [rsp+154h] [rbp-C4h]
  int v34; // [rsp+158h] [rbp-C0h]
  char v35; // [rsp+15Ch] [rbp-BCh]
  int v36; // [rsp+160h] [rbp-B8h]
  char v37; // [rsp+164h] [rbp-B4h]
  int v38; // [rsp+168h] [rbp-B0h]
  char v39; // [rsp+16Ch] [rbp-ACh]
  int v40; // [rsp+170h] [rbp-A8h]
  char v41; // [rsp+174h] [rbp-A4h]
  int v42; // [rsp+178h] [rbp-A0h]
  char v43; // [rsp+17Ch] [rbp-9Ch]
  int v44; // [rsp+190h] [rbp-88h]
  char v45; // [rsp+194h] [rbp-84h]
  int v46; // [rsp+198h] [rbp-80h]
  char v47; // [rsp+19Ch] [rbp-7Ch]
  int v48; // [rsp+1A0h] [rbp-78h]
  char v49; // [rsp+1A4h] [rbp-74h]
  int v50; // [rsp+1A8h] [rbp-70h]
  char v51; // [rsp+1ACh] [rbp-6Ch]
  int v52; // [rsp+1B0h] [rbp-68h]
  char v53; // [rsp+1B4h] [rbp-64h]
  int v54; // [rsp+1B8h] [rbp-60h]
  char v55; // [rsp+1BCh] [rbp-5Ch]

  memset_0(&instance, 0, 0x130u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_WindowsDefenderSecurityCenter02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_1803558D8,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       0,
                       0,
                       &MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
                       24,
                       2,
                       &v12);
  if ( v6 == MI_RESULT_OK )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(
                   self,
                   &MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti,
                   &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_104;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"WindowsDefenderSecurityCenter",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"CompanyName",
                      &String)
                && String )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableAccountProtectionUI",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableAppBrowserUI",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableClearTpmButton",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDeviceSecurityUI",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableEnhancedNotifications",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableFamilyUI",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableHealthUI",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableNetworkUI",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableNotifications",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableTpmFirmwareUpdateWarning",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableVirusUI",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisallowExploitProtectionOverride",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"Email",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableCustomizedToasts",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableInAppCustomization",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"HideRansomwareDataRecovery",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"HideSecureBoot",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"HideTPMTroubleshooting",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"HideWindowsSecurityNotificationAreaControl",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"Phone",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
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
            v11 = 0;
          }
          if ( v12 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
    }
  }
LABEL_104:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033584B,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801b7dfc  mov     [rsp+arg_8], rbx
0x1801b7e01  mov     [rsp+arg_10], rsi
0x1801b7e06  push    rdi
0x1801b7e07  push    r12
0x1801b7e09  push    r13
0x1801b7e0b  push    r14
0x1801b7e0d  push    r15
0x1801b7e0f  sub     rsp, 1F0h
0x1801b7e16  mov     rax, cs:__security_cookie
0x1801b7e1d  xor     rax, rsp
0x1801b7e20  mov     [rsp+218h+var_38], rax
0x1801b7e28  mov     r13b, dl
0x1801b7e2b  mov     r12, rcx
0x1801b7e2e  xor     edx, edx; Val
0x1801b7e30  mov     r8d, 130h; Size
0x1801b7e36  lea     rcx, [rsp+218h+instance]; void *
0x1801b7e3e  call    memset_0
0x1801b7e43  xor     edi, edi
0x1801b7e45  mov     [rsp+218h+var_1D0], dil
0x1801b7e4a  mov     [rsp+218h+String], rdi
0x1801b7e4f  mov     [rsp+218h+var_190], edi
0x1801b7e56  mov     [rsp+218h+var_18C], dil
0x1801b7e5e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b7e65  mov     [rsp+218h+var_1C0], rax
0x1801b7e6a  lea     rax, [rsp+218h+var_190]
0x1801b7e72  mov     [rsp+218h+var_1B8], rax
0x1801b7e77  lea     rax, aMdmPolicyResul_186; "MDM_Policy_Result01_WindowsDefenderSecu"...
0x1801b7e7e  mov     [rsp+218h+var_1B0], rax
0x1801b7e83  lea     rcx, [rsp+218h+var_190]
0x1801b7e8b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b7e90  mov     eax, cs:dword_180380B68
0x1801b7e96  cmp     eax, 5
0x1801b7e99  jbe     short loc_1801B7F0B
0x1801b7e9b  mov     rdx, 200000000000h
0x1801b7ea5  lea     rcx, dword_180380B68
0x1801b7eac  call    _tlgKeywordOn
0x1801b7eb1  test    al, al
0x1801b7eb3  jz      short loc_1801B7F0B
0x1801b7eb5  cmp     [rsp+218h+var_18C], dil
0x1801b7ebd  jz      short loc_1801B7EED
0x1801b7ebf  cmp     [rsp+218h+var_178], edi
0x1801b7ec6  jnz     short loc_1801B7EE3
0x1801b7ec8  cmp     [rsp+218h+var_174], edi
0x1801b7ecf  jnz     short loc_1801B7EE3
0x1801b7ed1  cmp     [rsp+218h+var_170], edi
0x1801b7ed8  jnz     short loc_1801B7EE3
0x1801b7eda  cmp     [rsp+218h+var_16C], edi
0x1801b7ee1  jz      short loc_1801B7EED
0x1801b7ee3  lea     r9, [rsp+218h+var_178]
0x1801b7eeb  jmp     short loc_1801B7EF0
0x1801b7eed  mov     r9, rdi
0x1801b7ef0  lea     r8, [rsp+218h+var_188]
0x1801b7ef8  lea     rdx, qword_1803558D8
0x1801b7eff  lea     rcx, dword_180380B68
0x1801b7f06  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b7f0b  lea     rcx, [rsp+218h+var_1C0]; this
0x1801b7f10  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801b7f15  nop
0x1801b7f16  mov     [rsp+218h+var_1C8], rdi
0x1801b7f1b  lea     rax, [rsp+218h+var_1C8]
0x1801b7f20  mov     [rsp+218h+var_1E8], rax
0x1801b7f25  mov     [rsp+218h+var_1F0], 2
0x1801b7f2d  mov     [rsp+218h+var_1F8], 18h
0x1801b7f35  lea     r9, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList
0x1801b7f3c  xor     r8d, r8d
0x1801b7f3f  xor     edx, edx
0x1801b7f41  mov     rcx, r12
0x1801b7f44  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b7f49  mov     r15d, eax
0x1801b7f4c  test    eax, eax
0x1801b7f4e  jz      short loc_1801B7F55
0x1801b7f50  jmp     loc_1801B8726
0x1801b7f55  lea     rbx, [rsp+218h+var_1C8]
0x1801b7f5a  mov     [rsp+218h+var_1A0], rbx
0x1801b7f5f  mov     r14d, 1
0x1801b7f65  mov     [rsp+218h+var_198], r14b
0x1801b7f6d  mov     rsi, [rsp+218h+var_1C8]
0x1801b7f72  test    rsi, rsi
0x1801b7f75  jnz     short loc_1801B7F7F
0x1801b7f77  mov     r15d, r14d
0x1801b7f7a  jmp     loc_1801B8726
0x1801b7f7f  mov     rax, [rsi]
0x1801b7f82  mov     rcx, rsi
0x1801b7f85  mov     rax, [rax+10h]
0x1801b7f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7f8e  mov     r15d, eax
0x1801b7f91  test    eax, eax
0x1801b7f93  jz      short loc_1801B7FB3
0x1801b7f95  mov     rcx, [rsp+218h+var_1C8]
0x1801b7f9a  test    rcx, rcx
0x1801b7f9d  jz      short loc_1801B7FAE
0x1801b7f9f  mov     rax, [rcx]
0x1801b7fa2  mov     edx, r14d
0x1801b7fa5  mov     rax, [rax]
0x1801b7fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7fad  nop
0x1801b7fae  jmp     loc_1801B8726
0x1801b7fb3  mov     rax, [rsi]
0x1801b7fb6  mov     rcx, rsi
0x1801b7fb9  mov     rax, [rax+8]
0x1801b7fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7fc2  mov     r15d, eax
0x1801b7fc5  test    eax, eax
0x1801b7fc7  jz      short loc_1801B7FE7
0x1801b7fc9  mov     rcx, [rsp+218h+var_1C8]
0x1801b7fce  test    rcx, rcx
0x1801b7fd1  jz      short loc_1801B7FE2
0x1801b7fd3  mov     rax, [rcx]
0x1801b7fd6  mov     edx, r14d
0x1801b7fd9  mov     rax, [rax]
0x1801b7fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7fe1  nop
0x1801b7fe2  jmp     loc_1801B8726
0x1801b7fe7  mov     r14d, edi
0x1801b7fea  mov     rax, [rsi+108h]
0x1801b7ff1  sub     rax, [rsi+100h]
0x1801b7ff8  sar     rax, 4
0x1801b7ffc  cmp     r14d, eax
0x1801b7fff  jnb     loc_1801B86EE
0x1801b8005  lea     r8, [rsp+218h+instance]; instance
0x1801b800d  lea     rdx, MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x1801b8014  mov     rcx, r12; context
0x1801b8017  call    MI_Context_ConstructInstance
0x1801b801c  mov     r15d, eax
0x1801b801f  test    eax, eax
0x1801b8021  jz      short loc_1801B8043
0x1801b8023  mov     rcx, [rbx]
0x1801b8026  test    rcx, rcx
0x1801b8029  jz      short loc_1801B803E
0x1801b802b  mov     rax, [rcx]
0x1801b802e  mov     edx, 1
0x1801b8033  mov     rax, [rax]
0x1801b8036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b803b  mov     [rbx], rdi
0x1801b803e  jmp     loc_1801B8726
0x1801b8043  mov     [rsp+218h+var_1D0], 1
0x1801b8048  mov     rax, [rsi]
0x1801b804b  lea     r9, [rsp+218h+String]
0x1801b8050  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801b8057  mov     edx, r14d
0x1801b805a  mov     rcx, rsi
0x1801b805d  mov     rax, [rax+18h]
0x1801b8061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8066  test    eax, eax
0x1801b8068  jnz     short loc_1801B8081
0x1801b806a  mov     rdx, [rsp+218h+String]
0x1801b806f  test    rdx, rdx
0x1801b8072  jz      short loc_1801B8081
0x1801b8074  lea     rcx, [rsp+218h+instance]
0x1801b807c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b8081  mov     rax, [rsi]
0x1801b8084  lea     r9, [rsp+218h+String]
0x1801b8089  lea     r8, aWindowsdefende; "WindowsDefenderSecurityCenter"
0x1801b8090  mov     edx, r14d
0x1801b8093  mov     rcx, rsi
0x1801b8096  mov     rax, [rax+18h]
0x1801b809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b809f  test    eax, eax
0x1801b80a1  jnz     short loc_1801B80BA
0x1801b80a3  mov     rdx, [rsp+218h+String]
0x1801b80a8  test    rdx, rdx
0x1801b80ab  jz      short loc_1801B80BA
0x1801b80ad  lea     rcx, [rsp+218h+instance]
0x1801b80b5  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b80ba  cmp     r13b, 1
0x1801b80be  jnz     short loc_1801B80E2
0x1801b80c0  lea     rdx, [rsp+218h+instance]
0x1801b80c8  mov     rcx, r12; self
0x1801b80cb  call    MI_Instance_Destruct
0x1801b80d0  lea     rcx, [rsp+218h+instance]; self
0x1801b80d8  call    MI_Instance_Destruct
0x1801b80dd  jmp     loc_1801B86E1
0x1801b80e2  mov     rax, [rsi]
0x1801b80e5  lea     r9, [rsp+218h+String]
0x1801b80ea  lea     r8, aCompanyname; "CompanyName"
0x1801b80f1  mov     edx, r14d
0x1801b80f4  mov     rcx, rsi
0x1801b80f7  mov     rax, [rax+18h]
0x1801b80fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8100  test    eax, eax
0x1801b8102  jnz     short loc_1801B811B
0x1801b8104  mov     rdx, [rsp+218h+String]
0x1801b8109  test    rdx, rdx
0x1801b810c  jz      short loc_1801B811B
0x1801b810e  lea     rcx, [rsp+218h+instance]
0x1801b8116  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b811b  mov     rax, [rsi]
0x1801b811e  lea     r9, [rsp+218h+String]
0x1801b8123  lea     r8, aDisableaccount; "DisableAccountProtectionUI"
0x1801b812a  mov     edx, r14d
0x1801b812d  mov     rcx, rsi
0x1801b8130  mov     rax, [rax+18h]
0x1801b8134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8139  test    eax, eax
0x1801b813b  jnz     short loc_1801B8162
0x1801b813d  mov     rcx, [rsp+218h+String]; String
0x1801b8142  test    rcx, rcx
0x1801b8145  jz      short loc_1801B8162
0x1801b8147  call    cs:__imp__wtoi
0x1801b814e  nop     dword ptr [rax+rax+00h]
0x1801b8153  mov     [rsp+218h+var_F8], eax
0x1801b815a  mov     [rsp+218h+var_F4], 1
0x1801b8162  mov     rax, [rsi]
0x1801b8165  lea     r9, [rsp+218h+String]
0x1801b816a  lea     r8, aDisableappbrow; "DisableAppBrowserUI"
0x1801b8171  mov     edx, r14d
0x1801b8174  mov     rcx, rsi
0x1801b8177  mov     rax, [rax+18h]
0x1801b817b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8180  test    eax, eax
0x1801b8182  jnz     short loc_1801B81A9
0x1801b8184  mov     rcx, [rsp+218h+String]; String
0x1801b8189  test    rcx, rcx
0x1801b818c  jz      short loc_1801B81A9
0x1801b818e  call    cs:__imp__wtoi
0x1801b8195  nop     dword ptr [rax+rax+00h]
0x1801b819a  mov     [rsp+218h+var_F0], eax
0x1801b81a1  mov     [rsp+218h+var_EC], 1
0x1801b81a9  mov     rax, [rsi]
0x1801b81ac  lea     r9, [rsp+218h+String]
0x1801b81b1  lea     r8, aDisablecleartp; "DisableClearTpmButton"
0x1801b81b8  mov     edx, r14d
0x1801b81bb  mov     rcx, rsi
0x1801b81be  mov     rax, [rax+18h]
0x1801b81c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b81c7  test    eax, eax
0x1801b81c9  jnz     short loc_1801B81F0
0x1801b81cb  mov     rcx, [rsp+218h+String]; String
0x1801b81d0  test    rcx, rcx
0x1801b81d3  jz      short loc_1801B81F0
0x1801b81d5  call    cs:__imp__wtoi
0x1801b81dc  nop     dword ptr [rax+rax+00h]
0x1801b81e1  mov     [rsp+218h+var_E8], eax
0x1801b81e8  mov     [rsp+218h+var_E4], 1
0x1801b81f0  mov     rax, [rsi]
0x1801b81f3  lea     r9, [rsp+218h+String]
0x1801b81f8  lea     r8, aDisabledevices; "DisableDeviceSecurityUI"
0x1801b81ff  mov     edx, r14d
0x1801b8202  mov     rcx, rsi
0x1801b8205  mov     rax, [rax+18h]
0x1801b8209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b820e  test    eax, eax
0x1801b8210  jnz     short loc_1801B8237
0x1801b8212  mov     rcx, [rsp+218h+String]; String
0x1801b8217  test    rcx, rcx
0x1801b821a  jz      short loc_1801B8237
0x1801b821c  call    cs:__imp__wtoi
0x1801b8223  nop     dword ptr [rax+rax+00h]
0x1801b8228  mov     [rsp+218h+var_E0], eax
0x1801b822f  mov     [rsp+218h+var_DC], 1
0x1801b8237  mov     rax, [rsi]
0x1801b823a  lea     r9, [rsp+218h+String]
0x1801b823f  lea     r8, aDisableenhance; "DisableEnhancedNotifications"
0x1801b8246  mov     edx, r14d
0x1801b8249  mov     rcx, rsi
0x1801b824c  mov     rax, [rax+18h]
0x1801b8250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8255  test    eax, eax
0x1801b8257  jnz     short loc_1801B827E
0x1801b8259  mov     rcx, [rsp+218h+String]; String
0x1801b825e  test    rcx, rcx
0x1801b8261  jz      short loc_1801B827E
0x1801b8263  call    cs:__imp__wtoi
0x1801b826a  nop     dword ptr [rax+rax+00h]
0x1801b826f  mov     [rsp+218h+var_D8], eax
0x1801b8276  mov     [rsp+218h+var_D4], 1
0x1801b827e  mov     rax, [rsi]
0x1801b8281  lea     r9, [rsp+218h+String]
0x1801b8286  lea     r8, aDisablefamilyu; "DisableFamilyUI"
0x1801b828d  mov     edx, r14d
0x1801b8290  mov     rcx, rsi
0x1801b8293  mov     rax, [rax+18h]
0x1801b8297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b829c  test    eax, eax
0x1801b829e  jnz     short loc_1801B82C5
0x1801b82a0  mov     rcx, [rsp+218h+String]; String
0x1801b82a5  test    rcx, rcx
0x1801b82a8  jz      short loc_1801B82C5
0x1801b82aa  call    cs:__imp__wtoi
0x1801b82b1  nop     dword ptr [rax+rax+00h]
0x1801b82b6  mov     [rsp+218h+var_D0], eax
0x1801b82bd  mov     [rsp+218h+var_CC], 1
0x1801b82c5  mov     rax, [rsi]
0x1801b82c8  lea     r9, [rsp+218h+String]
0x1801b82cd  lea     r8, aDisablehealthu; "DisableHealthUI"
0x1801b82d4  mov     edx, r14d
0x1801b82d7  mov     rcx, rsi
0x1801b82da  mov     rax, [rax+18h]
0x1801b82de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b82e3  test    eax, eax
0x1801b82e5  jnz     short loc_1801B830C
0x1801b82e7  mov     rcx, [rsp+218h+String]; String
0x1801b82ec  test    rcx, rcx
0x1801b82ef  jz      short loc_1801B830C
0x1801b82f1  call    cs:__imp__wtoi
0x1801b82f8  nop     dword ptr [rax+rax+00h]
0x1801b82fd  mov     [rsp+218h+var_C8], eax
0x1801b8304  mov     [rsp+218h+var_C4], 1
0x1801b830c  mov     rax, [rsi]
0x1801b830f  lea     r9, [rsp+218h+String]
  ... truncated ...
```
