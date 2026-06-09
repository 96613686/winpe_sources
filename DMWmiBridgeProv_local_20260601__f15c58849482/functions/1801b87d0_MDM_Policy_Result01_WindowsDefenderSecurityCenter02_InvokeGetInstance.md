# MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance

- ea: `0x1801b87d0`
- end: `0x1801b903d`
- name: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance`
- size: `2157`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801b7240`

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
- `0x1801b87d0`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801b8a9e`
- `msvcrt!_wtoi` at `0x1801b8adb`
- `msvcrt!_wtoi` at `0x1801b8b18`
- `msvcrt!_wtoi` at `0x1801b8b55`
- `msvcrt!_wtoi` at `0x1801b8b92`
- `msvcrt!_wtoi` at `0x1801b8bcf`
- `msvcrt!_wtoi` at `0x1801b8c0c`
- `msvcrt!_wtoi` at `0x1801b8c49`
- `msvcrt!_wtoi` at `0x1801b8c86`
- `msvcrt!_wtoi` at `0x1801b8cc3`
- `msvcrt!_wtoi` at `0x1801b8d00`
- `msvcrt!_wtoi` at `0x1801b8d3d`
- `msvcrt!_wtoi` at `0x1801b8da9`
- `msvcrt!_wtoi` at `0x1801b8de6`
- `msvcrt!_wtoi` at `0x1801b8e23`
- `msvcrt!_wtoi` at `0x1801b8e60`
- `msvcrt!_wtoi` at `0x1801b8e9d`
- `msvcrt!_wtoi` at `0x1801b8eda`
- `msvcrt!_wtoi` at `0x1801b8a9e`
- `msvcrt!_wtoi` at `0x1801b8adb`
- `msvcrt!_wtoi` at `0x1801b8b18`
- `msvcrt!_wtoi` at `0x1801b8b55`
- `msvcrt!_wtoi` at `0x1801b8b92`
- `msvcrt!_wtoi` at `0x1801b8bcf`
- `msvcrt!_wtoi` at `0x1801b8c0c`
- `msvcrt!_wtoi` at `0x1801b8c49`
- `msvcrt!_wtoi` at `0x1801b8c86`
- `msvcrt!_wtoi` at `0x1801b8cc3`
- `msvcrt!_wtoi` at `0x1801b8d00`
- `msvcrt!_wtoi` at `0x1801b8d3d`
- `msvcrt!_wtoi` at `0x1801b8da9`
- `msvcrt!_wtoi` at `0x1801b8de6`
- `msvcrt!_wtoi` at `0x1801b8e23`
- `msvcrt!_wtoi` at `0x1801b8e60`
- `msvcrt!_wtoi` at `0x1801b8e9d`
- `msvcrt!_wtoi` at `0x1801b8eda`

## string_xrefs

- `0x1801b8a52`: `CompanyName`
- `0x1801b8b38`: `DisableDeviceSecurityUI`
- `0x1801b8ca6`: `DisableTpmFirmwareUpdateWarning`
- `0x1801b8ebd`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801b883f`: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
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
    v5 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         a2[1].serverName,
                         a2[1].ft,
                         &MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
                         24,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
          0x18u);
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
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"CompanyName", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableAccountProtectionUI",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableAppBrowserUI",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableClearTpmButton",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableDeviceSecurityUI",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableEnhancedNotifications",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableFamilyUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableHealthUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableNetworkUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableNotifications",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableTpmFirmwareUpdateWarning",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableVirusUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisallowExploitProtectionOverride",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"Email", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnableCustomizedToasts",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnableInAppCustomization",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"HideRansomwareDataRecovery",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"HideSecureBoot", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"HideTPMTroubleshooting",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"HideWindowsSecurityNotificationAreaControl",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"Phone", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"URL", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
      word_180334782,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801b87d0  mov     [rsp+arg_10], rbx
0x1801b87d5  push    rsi
0x1801b87d6  push    rdi
0x1801b87d7  push    r12
0x1801b87d9  push    r14
0x1801b87db  push    r15
0x1801b87dd  sub     rsp, 1F0h
0x1801b87e4  mov     rax, cs:__security_cookie
0x1801b87eb  xor     rax, rsp
0x1801b87ee  mov     [rsp+218h+var_38], rax
0x1801b87f6  mov     rsi, rdx
0x1801b87f9  mov     r15, rcx
0x1801b87fc  xor     ebx, ebx
0x1801b87fe  mov     [rsp+218h+String], rbx
0x1801b8803  xor     edx, edx; Val
0x1801b8805  mov     r8d, 130h; Size
0x1801b880b  lea     rcx, [rsp+218h+instance]; void *
0x1801b8813  call    memset_0
0x1801b8818  mov     [rsp+218h+var_190], ebx
0x1801b881f  mov     [rsp+218h+var_18C], bl
0x1801b8826  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b882d  mov     [rsp+218h+var_1C0], rax
0x1801b8832  lea     rax, [rsp+218h+var_190]
0x1801b883a  mov     [rsp+218h+var_1B8], rax
0x1801b883f  lea     rax, aMdmPolicyResul_186; "MDM_Policy_Result01_WindowsDefenderSecu"...
0x1801b8846  mov     [rsp+218h+var_1B0], rax
0x1801b884b  lea     rcx, [rsp+218h+var_190]
0x1801b8853  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b8858  mov     eax, cs:dword_180380B68
0x1801b885e  cmp     eax, 5
0x1801b8861  jbe     short loc_1801B88D2
0x1801b8863  mov     rdx, 200000000000h
0x1801b886d  lea     rcx, dword_180380B68
0x1801b8874  call    _tlgKeywordOn
0x1801b8879  test    al, al
0x1801b887b  jz      short loc_1801B88D2
0x1801b887d  cmp     [rsp+218h+var_18C], bl
0x1801b8884  jz      short loc_1801B88B4
0x1801b8886  cmp     [rsp+218h+var_178], ebx
0x1801b888d  jnz     short loc_1801B88AA
0x1801b888f  cmp     [rsp+218h+var_174], ebx
0x1801b8896  jnz     short loc_1801B88AA
0x1801b8898  cmp     [rsp+218h+var_170], ebx
0x1801b889f  jnz     short loc_1801B88AA
0x1801b88a1  cmp     [rsp+218h+var_16C], ebx
0x1801b88a8  jz      short loc_1801B88B4
0x1801b88aa  lea     r9, [rsp+218h+var_178]
0x1801b88b2  jmp     short loc_1801B88B7
0x1801b88b4  mov     r9, rbx
0x1801b88b7  lea     r8, [rsp+218h+var_188]
0x1801b88bf  lea     rdx, dword_180361D84
0x1801b88c6  lea     rcx, dword_180380B68
0x1801b88cd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b88d2  cmp     [rsi+48h], bl
0x1801b88d5  jz      loc_1801B8F9B
0x1801b88db  mov     [rsp+218h+var_1D0], bl
0x1801b88df  cmp     [rsi+58h], bl
0x1801b88e2  jz      loc_1801B8F9B
0x1801b88e8  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b88ec  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b88f0  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801b88f7  lea     rcx, [rsp+218h+var_1C0]; this
0x1801b88fc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b8901  nop
0x1801b8902  mov     [rsp+218h+var_1C8], rbx
0x1801b8907  lea     rax, [rsp+218h+var_1C8]
0x1801b890c  mov     [rsp+218h+var_1E8], rax
0x1801b8911  mov     [rsp+218h+var_1F0], ebx
0x1801b8915  mov     [rsp+218h+var_1F8], 18h
0x1801b891d  lea     r9, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList
0x1801b8924  mov     r8, [rsi+40h]
0x1801b8928  mov     rdx, [rsi+50h]
0x1801b892c  mov     rcx, r15
0x1801b892f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b8934  mov     r14d, eax
0x1801b8937  test    eax, eax
0x1801b8939  jz      short loc_1801B8940
0x1801b893b  jmp     loc_1801B8FA1
0x1801b8940  lea     rax, [rsp+218h+var_1C8]
0x1801b8945  mov     [rsp+218h+var_1A0], rax
0x1801b894a  mov     r12d, 1
0x1801b8950  mov     [rsp+218h+var_198], r12b
0x1801b8958  mov     rdi, [rsp+218h+var_1C8]
0x1801b895d  test    rdi, rdi
0x1801b8960  jnz     short loc_1801B896A
0x1801b8962  mov     r14d, r12d
0x1801b8965  jmp     loc_1801B8FA1
0x1801b896a  mov     r9d, 18h; unsigned int
0x1801b8970  lea     r8, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b8977  mov     rdx, rsi; struct _MI_Instance *
0x1801b897a  mov     rcx, rdi; this
0x1801b897d  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b8982  mov     rax, [rdi]
0x1801b8985  mov     rcx, rdi
0x1801b8988  mov     rax, [rax+10h]
0x1801b898c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8991  mov     r14d, eax
0x1801b8994  test    eax, eax
0x1801b8996  jz      short loc_1801B89B6
0x1801b8998  mov     rcx, [rsp+218h+var_1C8]
0x1801b899d  test    rcx, rcx
0x1801b89a0  jz      short loc_1801B89B1
0x1801b89a2  mov     rax, [rcx]
0x1801b89a5  mov     edx, r12d
0x1801b89a8  mov     rax, [rax]
0x1801b89ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b89b0  nop
0x1801b89b1  jmp     loc_1801B8FA1
0x1801b89b6  mov     rax, [rdi]
0x1801b89b9  mov     rcx, rdi
0x1801b89bc  mov     rax, [rax+8]
0x1801b89c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b89c5  mov     r14d, eax
0x1801b89c8  test    eax, eax
0x1801b89ca  jz      short loc_1801B89EA
0x1801b89cc  mov     rcx, [rsp+218h+var_1C8]
0x1801b89d1  test    rcx, rcx
0x1801b89d4  jz      short loc_1801B89E5
0x1801b89d6  mov     rax, [rcx]
0x1801b89d9  mov     edx, r12d
0x1801b89dc  mov     rax, [rax]
0x1801b89df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b89e4  nop
0x1801b89e5  jmp     loc_1801B8FA1
0x1801b89ea  lea     r8, [rsp+218h+instance]; instance
0x1801b89f2  lea     rdx, MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x1801b89f9  mov     rcx, r15; context
0x1801b89fc  call    MI_Context_ConstructInstance
0x1801b8a01  mov     r14d, eax
0x1801b8a04  test    eax, eax
0x1801b8a06  jz      short loc_1801B8A26
0x1801b8a08  mov     rcx, [rsp+218h+var_1C8]
0x1801b8a0d  test    rcx, rcx
0x1801b8a10  jz      short loc_1801B8A21
0x1801b8a12  mov     rax, [rcx]
0x1801b8a15  mov     edx, r12d
0x1801b8a18  mov     rax, [rax]
0x1801b8a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8a20  nop
0x1801b8a21  jmp     loc_1801B8FA1
0x1801b8a26  mov     [rsp+218h+var_1D0], r12b
0x1801b8a2b  mov     rdx, [rsi+40h]
0x1801b8a2f  lea     rcx, [rsp+218h+instance]
0x1801b8a37  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b8a3c  mov     rdx, [rsi+50h]
0x1801b8a40  lea     rcx, [rsp+218h+instance]
0x1801b8a48  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b8a4d  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8a52  lea     rdx, aCompanyname; "CompanyName"
0x1801b8a59  mov     rcx, rdi; this
0x1801b8a5c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8a61  test    eax, eax
0x1801b8a63  jnz     short loc_1801B8A7C
0x1801b8a65  mov     rdx, [rsp+218h+String]
0x1801b8a6a  test    rdx, rdx
0x1801b8a6d  jz      short loc_1801B8A7C
0x1801b8a6f  lea     rcx, [rsp+218h+instance]
0x1801b8a77  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b8a7c  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8a81  lea     rdx, aDisableaccount; "DisableAccountProtectionUI"
0x1801b8a88  mov     rcx, rdi; this
0x1801b8a8b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8a90  test    eax, eax
0x1801b8a92  jnz     short loc_1801B8AB9
0x1801b8a94  mov     rcx, [rsp+218h+String]; String
0x1801b8a99  test    rcx, rcx
0x1801b8a9c  jz      short loc_1801B8AB9
0x1801b8a9e  call    cs:__imp__wtoi
0x1801b8aa5  nop     dword ptr [rax+rax+00h]
0x1801b8aaa  mov     [rsp+218h+var_F8], eax
0x1801b8ab1  mov     [rsp+218h+var_F4], r12b
0x1801b8ab9  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8abe  lea     rdx, aDisableappbrow; "DisableAppBrowserUI"
0x1801b8ac5  mov     rcx, rdi; this
0x1801b8ac8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8acd  test    eax, eax
0x1801b8acf  jnz     short loc_1801B8AF6
0x1801b8ad1  mov     rcx, [rsp+218h+String]; String
0x1801b8ad6  test    rcx, rcx
0x1801b8ad9  jz      short loc_1801B8AF6
0x1801b8adb  call    cs:__imp__wtoi
0x1801b8ae2  nop     dword ptr [rax+rax+00h]
0x1801b8ae7  mov     [rsp+218h+var_F0], eax
0x1801b8aee  mov     [rsp+218h+var_EC], r12b
0x1801b8af6  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8afb  lea     rdx, aDisablecleartp; "DisableClearTpmButton"
0x1801b8b02  mov     rcx, rdi; this
0x1801b8b05  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8b0a  test    eax, eax
0x1801b8b0c  jnz     short loc_1801B8B33
0x1801b8b0e  mov     rcx, [rsp+218h+String]; String
0x1801b8b13  test    rcx, rcx
0x1801b8b16  jz      short loc_1801B8B33
0x1801b8b18  call    cs:__imp__wtoi
0x1801b8b1f  nop     dword ptr [rax+rax+00h]
0x1801b8b24  mov     [rsp+218h+var_E8], eax
0x1801b8b2b  mov     [rsp+218h+var_E4], r12b
0x1801b8b33  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8b38  lea     rdx, aDisabledevices; "DisableDeviceSecurityUI"
0x1801b8b3f  mov     rcx, rdi; this
0x1801b8b42  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8b47  test    eax, eax
0x1801b8b49  jnz     short loc_1801B8B70
0x1801b8b4b  mov     rcx, [rsp+218h+String]; String
0x1801b8b50  test    rcx, rcx
0x1801b8b53  jz      short loc_1801B8B70
0x1801b8b55  call    cs:__imp__wtoi
0x1801b8b5c  nop     dword ptr [rax+rax+00h]
0x1801b8b61  mov     [rsp+218h+var_E0], eax
0x1801b8b68  mov     [rsp+218h+var_DC], r12b
0x1801b8b70  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8b75  lea     rdx, aDisableenhance; "DisableEnhancedNotifications"
0x1801b8b7c  mov     rcx, rdi; this
0x1801b8b7f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8b84  test    eax, eax
0x1801b8b86  jnz     short loc_1801B8BAD
0x1801b8b88  mov     rcx, [rsp+218h+String]; String
0x1801b8b8d  test    rcx, rcx
0x1801b8b90  jz      short loc_1801B8BAD
0x1801b8b92  call    cs:__imp__wtoi
0x1801b8b99  nop     dword ptr [rax+rax+00h]
0x1801b8b9e  mov     [rsp+218h+var_D8], eax
0x1801b8ba5  mov     [rsp+218h+var_D4], r12b
0x1801b8bad  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8bb2  lea     rdx, aDisablefamilyu; "DisableFamilyUI"
0x1801b8bb9  mov     rcx, rdi; this
0x1801b8bbc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8bc1  test    eax, eax
0x1801b8bc3  jnz     short loc_1801B8BEA
0x1801b8bc5  mov     rcx, [rsp+218h+String]; String
0x1801b8bca  test    rcx, rcx
0x1801b8bcd  jz      short loc_1801B8BEA
0x1801b8bcf  call    cs:__imp__wtoi
0x1801b8bd6  nop     dword ptr [rax+rax+00h]
0x1801b8bdb  mov     [rsp+218h+var_D0], eax
0x1801b8be2  mov     [rsp+218h+var_CC], r12b
0x1801b8bea  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8bef  lea     rdx, aDisablehealthu; "DisableHealthUI"
0x1801b8bf6  mov     rcx, rdi; this
0x1801b8bf9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8bfe  test    eax, eax
0x1801b8c00  jnz     short loc_1801B8C27
0x1801b8c02  mov     rcx, [rsp+218h+String]; String
0x1801b8c07  test    rcx, rcx
0x1801b8c0a  jz      short loc_1801B8C27
0x1801b8c0c  call    cs:__imp__wtoi
0x1801b8c13  nop     dword ptr [rax+rax+00h]
0x1801b8c18  mov     [rsp+218h+var_C8], eax
0x1801b8c1f  mov     [rsp+218h+var_C4], r12b
0x1801b8c27  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8c2c  lea     rdx, aDisablenetwork; "DisableNetworkUI"
0x1801b8c33  mov     rcx, rdi; this
0x1801b8c36  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8c3b  test    eax, eax
0x1801b8c3d  jnz     short loc_1801B8C64
0x1801b8c3f  mov     rcx, [rsp+218h+String]; String
0x1801b8c44  test    rcx, rcx
0x1801b8c47  jz      short loc_1801B8C64
0x1801b8c49  call    cs:__imp__wtoi
0x1801b8c50  nop     dword ptr [rax+rax+00h]
0x1801b8c55  mov     [rsp+218h+var_C0], eax
0x1801b8c5c  mov     [rsp+218h+var_BC], r12b
0x1801b8c64  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8c69  lea     rdx, aDisablenotific; "DisableNotifications"
0x1801b8c70  mov     rcx, rdi; this
0x1801b8c73  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8c78  test    eax, eax
0x1801b8c7a  jnz     short loc_1801B8CA1
0x1801b8c7c  mov     rcx, [rsp+218h+String]; String
0x1801b8c81  test    rcx, rcx
0x1801b8c84  jz      short loc_1801B8CA1
0x1801b8c86  call    cs:__imp__wtoi
0x1801b8c8d  nop     dword ptr [rax+rax+00h]
0x1801b8c92  mov     [rsp+218h+var_B8], eax
0x1801b8c99  mov     [rsp+218h+var_B4], r12b
0x1801b8ca1  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8ca6  lea     rdx, aDisabletpmfirm; "DisableTpmFirmwareUpdateWarning"
0x1801b8cad  mov     rcx, rdi; this
0x1801b8cb0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8cb5  test    eax, eax
0x1801b8cb7  jnz     short loc_1801B8CDE
0x1801b8cb9  mov     rcx, [rsp+218h+String]; String
0x1801b8cbe  test    rcx, rcx
0x1801b8cc1  jz      short loc_1801B8CDE
0x1801b8cc3  call    cs:__imp__wtoi
0x1801b8cca  nop     dword ptr [rax+rax+00h]
0x1801b8ccf  mov     [rsp+218h+var_B0], eax
0x1801b8cd6  mov     [rsp+218h+var_AC], r12b
0x1801b8cde  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801b8ce3  lea     rdx, aDisablevirusui; "DisableVirusUI"
0x1801b8cea  mov     rcx, rdi; this
0x1801b8ced  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801b8cf2  test    eax, eax
0x1801b8cf4  jnz     short loc_1801B8D1B
0x1801b8cf6  mov     rcx, [rsp+218h+String]; String
0x1801b8cfb  test    rcx, rcx
0x1801b8cfe  jz      short loc_1801B8D1B
0x1801b8d00  call    cs:__imp__wtoi
0x1801b8d07  nop     dword ptr [rax+rax+00h]
0x1801b8d0c  mov     [rsp+218h+var_A8], eax
  ... truncated ...
```
