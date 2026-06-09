# MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance

- ea: `0x1801b8a28`
- end: `0x1801b9228`
- name: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance`
- size: `2048`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801b7500`

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
- `0x1801b8a28`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801b8cf6`
- `msvcrt!_wtoi` at `0x1801b8d2d`
- `msvcrt!_wtoi` at `0x1801b8d64`
- `msvcrt!_wtoi` at `0x1801b8d9b`
- `msvcrt!_wtoi` at `0x1801b8dd2`
- `msvcrt!_wtoi` at `0x1801b8e09`
- `msvcrt!_wtoi` at `0x1801b8e40`
- `msvcrt!_wtoi` at `0x1801b8e77`
- `msvcrt!_wtoi` at `0x1801b8eae`
- `msvcrt!_wtoi` at `0x1801b8ee5`
- `msvcrt!_wtoi` at `0x1801b8f1c`
- `msvcrt!_wtoi` at `0x1801b8f53`
- `msvcrt!_wtoi` at `0x1801b8fb9`
- `msvcrt!_wtoi` at `0x1801b8ff0`
- `msvcrt!_wtoi` at `0x1801b9027`
- `msvcrt!_wtoi` at `0x1801b905e`
- `msvcrt!_wtoi` at `0x1801b9095`
- `msvcrt!_wtoi` at `0x1801b90cc`
- `msvcrt!_wtoi` at `0x1801b8cf6`
- `msvcrt!_wtoi` at `0x1801b8d2d`
- `msvcrt!_wtoi` at `0x1801b8d64`
- `msvcrt!_wtoi` at `0x1801b8d9b`
- `msvcrt!_wtoi` at `0x1801b8dd2`
- `msvcrt!_wtoi` at `0x1801b8e09`
- `msvcrt!_wtoi` at `0x1801b8e40`
- `msvcrt!_wtoi` at `0x1801b8e77`
- `msvcrt!_wtoi` at `0x1801b8eae`
- `msvcrt!_wtoi` at `0x1801b8ee5`
- `msvcrt!_wtoi` at `0x1801b8f1c`
- `msvcrt!_wtoi` at `0x1801b8f53`
- `msvcrt!_wtoi` at `0x1801b8fb9`
- `msvcrt!_wtoi` at `0x1801b8ff0`
- `msvcrt!_wtoi` at `0x1801b9027`
- `msvcrt!_wtoi` at `0x1801b905e`
- `msvcrt!_wtoi` at `0x1801b9095`
- `msvcrt!_wtoi` at `0x1801b90cc`

## string_xrefs

- `0x1801b8caa`: `CompanyName`
- `0x1801b8d7e`: `DisableDeviceSecurityUI`
- `0x1801b8ec8`: `DisableTpmFirmwareUpdateWarning`
- `0x1801b90af`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801b8a97`: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-1D8h] BYREF
  char v9; // [rsp+48h] [rbp-1D0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-1C0h] BYREF
  char v12; // [rsp+80h] [rbp-198h]
  int v13; // [rsp+88h] [rbp-190h] BYREF
  char v14; // [rsp+8Ch] [rbp-18Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-188h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-178h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-168h] BYREF
  int v18; // [rsp+120h] [rbp-F8h]
  char v19; // [rsp+124h] [rbp-F4h]
  int v20; // [rsp+128h] [rbp-F0h]
  char v21; // [rsp+12Ch] [rbp-ECh]
  int v22; // [rsp+130h] [rbp-E8h]
  char v23; // [rsp+134h] [rbp-E4h]
  int v24; // [rsp+138h] [rbp-E0h]
  char v25; // [rsp+13Ch] [rbp-DCh]
  int v26; // [rsp+140h] [rbp-D8h]
  char v27; // [rsp+144h] [rbp-D4h]
  int v28; // [rsp+148h] [rbp-D0h]
  char v29; // [rsp+14Ch] [rbp-CCh]
  int v30; // [rsp+150h] [rbp-C8h]
  char v31; // [rsp+154h] [rbp-C4h]
  int v32; // [rsp+158h] [rbp-C0h]
  char v33; // [rsp+15Ch] [rbp-BCh]
  int v34; // [rsp+160h] [rbp-B8h]
  char v35; // [rsp+164h] [rbp-B4h]
  int v36; // [rsp+168h] [rbp-B0h]
  char v37; // [rsp+16Ch] [rbp-ACh]
  int v38; // [rsp+170h] [rbp-A8h]
  char v39; // [rsp+174h] [rbp-A4h]
  int v40; // [rsp+178h] [rbp-A0h]
  char v41; // [rsp+17Ch] [rbp-9Ch]
  int v42; // [rsp+190h] [rbp-88h]
  char v43; // [rsp+194h] [rbp-84h]
  int v44; // [rsp+198h] [rbp-80h]
  char v45; // [rsp+19Ch] [rbp-7Ch]
  int v46; // [rsp+1A0h] [rbp-78h]
  char v47; // [rsp+1A4h] [rbp-74h]
  int v48; // [rsp+1A8h] [rbp-70h]
  char v49; // [rsp+1ACh] [rbp-6Ch]
  int v50; // [rsp+1B0h] [rbp-68h]
  char v51; // [rsp+1B4h] [rbp-64h]
  int v52; // [rsp+1B8h] [rbp-60h]
  char v53; // [rsp+1BCh] [rbp-5Ch]

  String = 0;
  memset_0(&instance, 0, 0x130u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_WindowsDefenderSecurityCenter02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180361D84,
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
           (struct WmiNodeInfo *)&MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
           0x18u,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
          0x18u);
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
            v5 = MI_Context_ConstructInstance(
                   self,
                   &MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti,
                   &instance);
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
                                    L"CompanyName",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableAccountProtectionUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableAppBrowserUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableClearTpmButton",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableDeviceSecurityUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableEnhancedNotifications",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableFamilyUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableHealthUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableNetworkUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableNotifications",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableTpmFirmwareUpdateWarning",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableVirusUI",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisallowExploitProtectionOverride",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"Email",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableCustomizedToasts",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnableInAppCustomization",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"HideRansomwareDataRecovery",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"HideSecureBoot",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"HideTPMTroubleshooting",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"HideWindowsSecurityNotificationAreaControl",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"Phone",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"URL",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
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
      word_180334782,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x1801b8a28  mov     [rsp+arg_10], rbx
0x1801b8a2d  push    rsi
0x1801b8a2e  push    rdi
0x1801b8a2f  push    r12
0x1801b8a31  push    r14
0x1801b8a33  push    r15
0x1801b8a35  sub     rsp, 1F0h
0x1801b8a3c  mov     rax, cs:__security_cookie
0x1801b8a43  xor     rax, rsp
0x1801b8a46  mov     [rsp+218h+var_38], rax
0x1801b8a4e  mov     rsi, rdx
0x1801b8a51  mov     r15, rcx
0x1801b8a54  xor     ebx, ebx
0x1801b8a56  mov     [rsp+218h+String], rbx
0x1801b8a5b  xor     edx, edx; Val
0x1801b8a5d  mov     r8d, 130h; Size
0x1801b8a63  lea     rcx, [rsp+218h+instance]; void *
0x1801b8a6b  call    memset_0
0x1801b8a70  mov     [rsp+218h+var_190], ebx
0x1801b8a77  mov     [rsp+218h+var_18C], bl
0x1801b8a7e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b8a85  mov     [rsp+218h+var_1C0], rax
0x1801b8a8a  lea     rax, [rsp+218h+var_190]
0x1801b8a92  mov     [rsp+218h+var_1B8], rax
0x1801b8a97  lea     rax, aMdmPolicyResul_186; "MDM_Policy_Result01_WindowsDefenderSecu"...
0x1801b8a9e  mov     [rsp+218h+var_1B0], rax
0x1801b8aa3  lea     rcx, [rsp+218h+var_190]
0x1801b8aab  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b8ab0  mov     eax, cs:dword_180380B68
0x1801b8ab6  cmp     eax, 5
0x1801b8ab9  jbe     short loc_1801B8B2A
0x1801b8abb  mov     rdx, 200000000000h
0x1801b8ac5  lea     rcx, dword_180380B68
0x1801b8acc  call    _tlgKeywordOn
0x1801b8ad1  test    al, al
0x1801b8ad3  jz      short loc_1801B8B2A
0x1801b8ad5  cmp     [rsp+218h+var_18C], bl
0x1801b8adc  jz      short loc_1801B8B0C
0x1801b8ade  cmp     [rsp+218h+var_178], ebx
0x1801b8ae5  jnz     short loc_1801B8B02
0x1801b8ae7  cmp     [rsp+218h+var_174], ebx
0x1801b8aee  jnz     short loc_1801B8B02
0x1801b8af0  cmp     [rsp+218h+var_170], ebx
0x1801b8af7  jnz     short loc_1801B8B02
0x1801b8af9  cmp     [rsp+218h+var_16C], ebx
0x1801b8b00  jz      short loc_1801B8B0C
0x1801b8b02  lea     r9, [rsp+218h+var_178]
0x1801b8b0a  jmp     short loc_1801B8B0F
0x1801b8b0c  mov     r9, rbx
0x1801b8b0f  lea     r8, [rsp+218h+var_188]
0x1801b8b17  lea     rdx, dword_180361D84
0x1801b8b1e  lea     rcx, dword_180380B68
0x1801b8b25  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b8b2a  cmp     [rsi+48h], bl
0x1801b8b2d  jz      loc_1801B9187
0x1801b8b33  mov     [rsp+218h+var_1D0], bl
0x1801b8b37  cmp     [rsi+58h], bl
0x1801b8b3a  jz      loc_1801B9187
0x1801b8b40  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b8b44  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b8b48  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801b8b4f  lea     rcx, [rsp+218h+var_1C0]; this
0x1801b8b54  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b8b59  nop
0x1801b8b5a  mov     [rsp+218h+var_1C8], rbx
0x1801b8b5f  lea     rax, [rsp+218h+var_1C8]
0x1801b8b64  mov     [rsp+218h+var_1E8], rax
0x1801b8b69  mov     [rsp+218h+var_1F0], ebx
0x1801b8b6d  mov     [rsp+218h+var_1F8], 18h
0x1801b8b75  lea     r9, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList
0x1801b8b7c  mov     r8, [rsi+40h]
0x1801b8b80  mov     rdx, [rsi+50h]
0x1801b8b84  mov     rcx, r15
0x1801b8b87  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b8b8c  mov     r14d, eax
0x1801b8b8f  test    eax, eax
0x1801b8b91  jz      short loc_1801B8B98
0x1801b8b93  jmp     loc_1801B918D
0x1801b8b98  lea     rax, [rsp+218h+var_1C8]
0x1801b8b9d  mov     [rsp+218h+var_1A0], rax
0x1801b8ba2  mov     r12d, 1
0x1801b8ba8  mov     [rsp+218h+var_198], r12b
0x1801b8bb0  mov     rdi, [rsp+218h+var_1C8]
0x1801b8bb5  test    rdi, rdi
0x1801b8bb8  jnz     short loc_1801B8BC2
0x1801b8bba  mov     r14d, r12d
0x1801b8bbd  jmp     loc_1801B918D
0x1801b8bc2  mov     r9d, 18h; unsigned int
0x1801b8bc8  lea     r8, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b8bcf  mov     rdx, rsi; struct _MI_Instance *
0x1801b8bd2  mov     rcx, rdi; this
0x1801b8bd5  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b8bda  mov     rax, [rdi]
0x1801b8bdd  mov     rcx, rdi
0x1801b8be0  mov     rax, [rax+10h]
0x1801b8be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8be9  mov     r14d, eax
0x1801b8bec  test    eax, eax
0x1801b8bee  jz      short loc_1801B8C0E
0x1801b8bf0  mov     rcx, [rsp+218h+var_1C8]
0x1801b8bf5  test    rcx, rcx
0x1801b8bf8  jz      short loc_1801B8C09
0x1801b8bfa  mov     rax, [rcx]
0x1801b8bfd  mov     edx, r12d
0x1801b8c00  mov     rax, [rax]
0x1801b8c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8c08  nop
0x1801b8c09  jmp     loc_1801B918D
0x1801b8c0e  mov     rax, [rdi]
0x1801b8c11  mov     rcx, rdi
0x1801b8c14  mov     rax, [rax+8]
0x1801b8c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8c1d  mov     r14d, eax
0x1801b8c20  test    eax, eax
0x1801b8c22  jz      short loc_1801B8C42
0x1801b8c24  mov     rcx, [rsp+218h+var_1C8]
0x1801b8c29  test    rcx, rcx
0x1801b8c2c  jz      short loc_1801B8C3D
0x1801b8c2e  mov     rax, [rcx]
0x1801b8c31  mov     edx, r12d
0x1801b8c34  mov     rax, [rax]
0x1801b8c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8c3c  nop
0x1801b8c3d  jmp     loc_1801B918D
0x1801b8c42  lea     r8, [rsp+218h+instance]; instance
0x1801b8c4a  lea     rdx, MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x1801b8c51  mov     rcx, r15; context
0x1801b8c54  call    MI_Context_ConstructInstance
0x1801b8c59  mov     r14d, eax
0x1801b8c5c  test    eax, eax
0x1801b8c5e  jz      short loc_1801B8C7E
0x1801b8c60  mov     rcx, [rsp+218h+var_1C8]
0x1801b8c65  test    rcx, rcx
0x1801b8c68  jz      short loc_1801B8C79
0x1801b8c6a  mov     rax, [rcx]
0x1801b8c6d  mov     edx, r12d
0x1801b8c70  mov     rax, [rax]
0x1801b8c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8c78  nop
0x1801b8c79  jmp     loc_1801B918D
0x1801b8c7e  mov     [rsp+218h+var_1D0], r12b
0x1801b8c83  mov     rdx, [rsi+40h]
0x1801b8c87  lea     rcx, [rsp+218h+instance]
0x1801b8c8f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b8c94  mov     rdx, [rsi+50h]
0x1801b8c98  lea     rcx, [rsp+218h+instance]
0x1801b8ca0  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b8ca5  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8caa  lea     rdx, aCompanyname; "CompanyName"
0x1801b8cb1  mov     rcx, rdi; this
0x1801b8cb4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8cb9  test    eax, eax
0x1801b8cbb  jnz     short loc_1801B8CD4
0x1801b8cbd  mov     rdx, [rsp+218h+String]
0x1801b8cc2  test    rdx, rdx
0x1801b8cc5  jz      short loc_1801B8CD4
0x1801b8cc7  lea     rcx, [rsp+218h+instance]
0x1801b8ccf  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b8cd4  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8cd9  lea     rdx, aDisableaccount; "DisableAccountProtectionUI"
0x1801b8ce0  mov     rcx, rdi; this
0x1801b8ce3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8ce8  test    eax, eax
0x1801b8cea  jnz     short loc_1801B8D0B
0x1801b8cec  mov     rcx, [rsp+218h+String]; String
0x1801b8cf1  test    rcx, rcx
0x1801b8cf4  jz      short loc_1801B8D0B
0x1801b8cf6  call    cs:__imp__wtoi
0x1801b8cfc  mov     [rsp+218h+var_F8], eax
0x1801b8d03  mov     [rsp+218h+var_F4], r12b
0x1801b8d0b  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8d10  lea     rdx, aDisableappbrow; "DisableAppBrowserUI"
0x1801b8d17  mov     rcx, rdi; this
0x1801b8d1a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8d1f  test    eax, eax
0x1801b8d21  jnz     short loc_1801B8D42
0x1801b8d23  mov     rcx, [rsp+218h+String]; String
0x1801b8d28  test    rcx, rcx
0x1801b8d2b  jz      short loc_1801B8D42
0x1801b8d2d  call    cs:__imp__wtoi
0x1801b8d33  mov     [rsp+218h+var_F0], eax
0x1801b8d3a  mov     [rsp+218h+var_EC], r12b
0x1801b8d42  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8d47  lea     rdx, aDisablecleartp; "DisableClearTpmButton"
0x1801b8d4e  mov     rcx, rdi; this
0x1801b8d51  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8d56  test    eax, eax
0x1801b8d58  jnz     short loc_1801B8D79
0x1801b8d5a  mov     rcx, [rsp+218h+String]; String
0x1801b8d5f  test    rcx, rcx
0x1801b8d62  jz      short loc_1801B8D79
0x1801b8d64  call    cs:__imp__wtoi
0x1801b8d6a  mov     [rsp+218h+var_E8], eax
0x1801b8d71  mov     [rsp+218h+var_E4], r12b
0x1801b8d79  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8d7e  lea     rdx, aDisabledevices; "DisableDeviceSecurityUI"
0x1801b8d85  mov     rcx, rdi; this
0x1801b8d88  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8d8d  test    eax, eax
0x1801b8d8f  jnz     short loc_1801B8DB0
0x1801b8d91  mov     rcx, [rsp+218h+String]; String
0x1801b8d96  test    rcx, rcx
0x1801b8d99  jz      short loc_1801B8DB0
0x1801b8d9b  call    cs:__imp__wtoi
0x1801b8da1  mov     [rsp+218h+var_E0], eax
0x1801b8da8  mov     [rsp+218h+var_DC], r12b
0x1801b8db0  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8db5  lea     rdx, aDisableenhance; "DisableEnhancedNotifications"
0x1801b8dbc  mov     rcx, rdi; this
0x1801b8dbf  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8dc4  test    eax, eax
0x1801b8dc6  jnz     short loc_1801B8DE7
0x1801b8dc8  mov     rcx, [rsp+218h+String]; String
0x1801b8dcd  test    rcx, rcx
0x1801b8dd0  jz      short loc_1801B8DE7
0x1801b8dd2  call    cs:__imp__wtoi
0x1801b8dd8  mov     [rsp+218h+var_D8], eax
0x1801b8ddf  mov     [rsp+218h+var_D4], r12b
0x1801b8de7  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8dec  lea     rdx, aDisablefamilyu; "DisableFamilyUI"
0x1801b8df3  mov     rcx, rdi; this
0x1801b8df6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8dfb  test    eax, eax
0x1801b8dfd  jnz     short loc_1801B8E1E
0x1801b8dff  mov     rcx, [rsp+218h+String]; String
0x1801b8e04  test    rcx, rcx
0x1801b8e07  jz      short loc_1801B8E1E
0x1801b8e09  call    cs:__imp__wtoi
0x1801b8e0f  mov     [rsp+218h+var_D0], eax
0x1801b8e16  mov     [rsp+218h+var_CC], r12b
0x1801b8e1e  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8e23  lea     rdx, aDisablehealthu; "DisableHealthUI"
0x1801b8e2a  mov     rcx, rdi; this
0x1801b8e2d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8e32  test    eax, eax
0x1801b8e34  jnz     short loc_1801B8E55
0x1801b8e36  mov     rcx, [rsp+218h+String]; String
0x1801b8e3b  test    rcx, rcx
0x1801b8e3e  jz      short loc_1801B8E55
0x1801b8e40  call    cs:__imp__wtoi
0x1801b8e46  mov     [rsp+218h+var_C8], eax
0x1801b8e4d  mov     [rsp+218h+var_C4], r12b
0x1801b8e55  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8e5a  lea     rdx, aDisablenetwork; "DisableNetworkUI"
0x1801b8e61  mov     rcx, rdi; this
0x1801b8e64  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8e69  test    eax, eax
0x1801b8e6b  jnz     short loc_1801B8E8C
0x1801b8e6d  mov     rcx, [rsp+218h+String]; String
0x1801b8e72  test    rcx, rcx
0x1801b8e75  jz      short loc_1801B8E8C
0x1801b8e77  call    cs:__imp__wtoi
0x1801b8e7d  mov     [rsp+218h+var_C0], eax
0x1801b8e84  mov     [rsp+218h+var_BC], r12b
0x1801b8e8c  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8e91  lea     rdx, aDisablenotific; "DisableNotifications"
0x1801b8e98  mov     rcx, rdi; this
0x1801b8e9b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8ea0  test    eax, eax
0x1801b8ea2  jnz     short loc_1801B8EC3
0x1801b8ea4  mov     rcx, [rsp+218h+String]; String
0x1801b8ea9  test    rcx, rcx
0x1801b8eac  jz      short loc_1801B8EC3
0x1801b8eae  call    cs:__imp__wtoi
0x1801b8eb4  mov     [rsp+218h+var_B8], eax
0x1801b8ebb  mov     [rsp+218h+var_B4], r12b
0x1801b8ec3  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8ec8  lea     rdx, aDisabletpmfirm; "DisableTpmFirmwareUpdateWarning"
0x1801b8ecf  mov     rcx, rdi; this
0x1801b8ed2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8ed7  test    eax, eax
0x1801b8ed9  jnz     short loc_1801B8EFA
0x1801b8edb  mov     rcx, [rsp+218h+String]; String
0x1801b8ee0  test    rcx, rcx
0x1801b8ee3  jz      short loc_1801B8EFA
0x1801b8ee5  call    cs:__imp__wtoi
0x1801b8eeb  mov     [rsp+218h+var_B0], eax
0x1801b8ef2  mov     [rsp+218h+var_AC], r12b
0x1801b8efa  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8eff  lea     rdx, aDisablevirusui; "DisableVirusUI"
0x1801b8f06  mov     rcx, rdi; this
0x1801b8f09  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8f0e  test    eax, eax
0x1801b8f10  jnz     short loc_1801B8F31
0x1801b8f12  mov     rcx, [rsp+218h+String]; String
0x1801b8f17  test    rcx, rcx
0x1801b8f1a  jz      short loc_1801B8F31
0x1801b8f1c  call    cs:__imp__wtoi
0x1801b8f22  mov     [rsp+218h+var_A8], eax
0x1801b8f29  mov     [rsp+218h+var_A4], r12b
0x1801b8f31  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8f36  lea     rdx, aDisallowexploi; "DisallowExploitProtectionOverride"
0x1801b8f3d  mov     rcx, rdi; this
0x1801b8f40  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8f45  test    eax, eax
0x1801b8f47  jnz     short loc_1801B8F68
0x1801b8f49  mov     rcx, [rsp+218h+String]; String
0x1801b8f4e  test    rcx, rcx
0x1801b8f51  jz      short loc_1801B8F68
0x1801b8f53  call    cs:__imp__wtoi
  ... truncated ...
```
