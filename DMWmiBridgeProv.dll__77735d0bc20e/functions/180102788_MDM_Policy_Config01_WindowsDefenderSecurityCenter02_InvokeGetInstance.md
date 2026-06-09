# MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance

- ea: `0x180102788`
- end: `0x180102f88`
- name: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance`
- size: `2048`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180101260`

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
- `0x180102788`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180102a56`
- `msvcrt!_wtoi` at `0x180102a8d`
- `msvcrt!_wtoi` at `0x180102ac4`
- `msvcrt!_wtoi` at `0x180102afb`
- `msvcrt!_wtoi` at `0x180102b32`
- `msvcrt!_wtoi` at `0x180102b69`
- `msvcrt!_wtoi` at `0x180102ba0`
- `msvcrt!_wtoi` at `0x180102bd7`
- `msvcrt!_wtoi` at `0x180102c0e`
- `msvcrt!_wtoi` at `0x180102c45`
- `msvcrt!_wtoi` at `0x180102c7c`
- `msvcrt!_wtoi` at `0x180102cb3`
- `msvcrt!_wtoi` at `0x180102d19`
- `msvcrt!_wtoi` at `0x180102d50`
- `msvcrt!_wtoi` at `0x180102d87`
- `msvcrt!_wtoi` at `0x180102dbe`
- `msvcrt!_wtoi` at `0x180102df5`
- `msvcrt!_wtoi` at `0x180102e2c`
- `msvcrt!_wtoi` at `0x180102a56`
- `msvcrt!_wtoi` at `0x180102a8d`
- `msvcrt!_wtoi` at `0x180102ac4`
- `msvcrt!_wtoi` at `0x180102afb`
- `msvcrt!_wtoi` at `0x180102b32`
- `msvcrt!_wtoi` at `0x180102b69`
- `msvcrt!_wtoi` at `0x180102ba0`
- `msvcrt!_wtoi` at `0x180102bd7`
- `msvcrt!_wtoi` at `0x180102c0e`
- `msvcrt!_wtoi` at `0x180102c45`
- `msvcrt!_wtoi` at `0x180102c7c`
- `msvcrt!_wtoi` at `0x180102cb3`
- `msvcrt!_wtoi` at `0x180102d19`
- `msvcrt!_wtoi` at `0x180102d50`
- `msvcrt!_wtoi` at `0x180102d87`
- `msvcrt!_wtoi` at `0x180102dbe`
- `msvcrt!_wtoi` at `0x180102df5`
- `msvcrt!_wtoi` at `0x180102e2c`

## string_xrefs

- `0x180102a0a`: `CompanyName`
- `0x180102ade`: `DisableDeviceSecurityUI`
- `0x180102c28`: `DisableTpmFirmwareUpdateWarning`
- `0x180102e0f`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801027f7`: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance(
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
  v11[2] = "MDM_Policy_Config01_WindowsDefenderSecurityCenter02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180363BD3,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = 4;
    goto LABEL_95;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
         0x18u,
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
      goto LABEL_95;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
      0x18u);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_95;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"CompanyName", (const unsigned __int16 **)&String)
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"Email", (const unsigned __int16 **)&String)
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"Phone", (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(v6, L"URL", (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_95:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18036D193,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180102788  mov     [rsp+arg_10], rbx
0x18010278d  push    rsi
0x18010278e  push    rdi
0x18010278f  push    r12
0x180102791  push    r14
0x180102793  push    r15
0x180102795  sub     rsp, 1F0h
0x18010279c  mov     rax, cs:__security_cookie
0x1801027a3  xor     rax, rsp
0x1801027a6  mov     [rsp+218h+var_38], rax
0x1801027ae  mov     rsi, rdx
0x1801027b1  mov     r15, rcx
0x1801027b4  xor     ebx, ebx
0x1801027b6  mov     [rsp+218h+String], rbx
0x1801027bb  xor     edx, edx; Val
0x1801027bd  mov     r8d, 130h; Size
0x1801027c3  lea     rcx, [rsp+218h+instance]; void *
0x1801027cb  call    memset_0
0x1801027d0  mov     [rsp+218h+var_190], ebx
0x1801027d7  mov     [rsp+218h+var_18C], bl
0x1801027de  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801027e5  mov     [rsp+218h+var_1C0], rax
0x1801027ea  lea     rax, [rsp+218h+var_190]
0x1801027f2  mov     [rsp+218h+var_1B8], rax
0x1801027f7  lea     rax, aMdmPolicyConfi_102; "MDM_Policy_Config01_WindowsDefenderSecu"...
0x1801027fe  mov     [rsp+218h+var_1B0], rax
0x180102803  lea     rcx, [rsp+218h+var_190]
0x18010280b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180102810  mov     eax, cs:dword_180380B68
0x180102816  cmp     eax, 5
0x180102819  jbe     short loc_18010288A
0x18010281b  mov     rdx, 200000000000h
0x180102825  lea     rcx, dword_180380B68
0x18010282c  call    _tlgKeywordOn
0x180102831  test    al, al
0x180102833  jz      short loc_18010288A
0x180102835  cmp     [rsp+218h+var_18C], bl
0x18010283c  jz      short loc_18010286C
0x18010283e  cmp     [rsp+218h+var_178], ebx
0x180102845  jnz     short loc_180102862
0x180102847  cmp     [rsp+218h+var_174], ebx
0x18010284e  jnz     short loc_180102862
0x180102850  cmp     [rsp+218h+var_170], ebx
0x180102857  jnz     short loc_180102862
0x180102859  cmp     [rsp+218h+var_16C], ebx
0x180102860  jz      short loc_18010286C
0x180102862  lea     r9, [rsp+218h+var_178]
0x18010286a  jmp     short loc_18010286F
0x18010286c  mov     r9, rbx
0x18010286f  lea     r8, [rsp+218h+var_188]
0x180102877  lea     rdx, byte_180363BD3
0x18010287e  lea     rcx, dword_180380B68
0x180102885  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010288a  cmp     [rsi+48h], bl
0x18010288d  jz      loc_180102EE7
0x180102893  mov     [rsp+218h+var_1D0], bl
0x180102897  cmp     [rsi+58h], bl
0x18010289a  jz      loc_180102EE7
0x1801028a0  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801028a4  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801028a8  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801028af  lea     rcx, [rsp+218h+var_1C0]; this
0x1801028b4  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801028b9  nop
0x1801028ba  mov     [rsp+218h+var_1C8], rbx
0x1801028bf  lea     rax, [rsp+218h+var_1C8]
0x1801028c4  mov     [rsp+218h+var_1E8], rax
0x1801028c9  mov     [rsp+218h+var_1F0], ebx
0x1801028cd  mov     [rsp+218h+var_1F8], 18h
0x1801028d5  lea     r9, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList
0x1801028dc  mov     r8, [rsi+40h]
0x1801028e0  mov     rdx, [rsi+50h]
0x1801028e4  mov     rcx, r15
0x1801028e7  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801028ec  mov     r14d, eax
0x1801028ef  test    eax, eax
0x1801028f1  jz      short loc_1801028F8
0x1801028f3  jmp     loc_180102EED
0x1801028f8  lea     rax, [rsp+218h+var_1C8]
0x1801028fd  mov     [rsp+218h+var_1A0], rax
0x180102902  mov     r12d, 1
0x180102908  mov     [rsp+218h+var_198], r12b
0x180102910  mov     rdi, [rsp+218h+var_1C8]
0x180102915  test    rdi, rdi
0x180102918  jnz     short loc_180102922
0x18010291a  mov     r14d, r12d
0x18010291d  jmp     loc_180102EED
0x180102922  mov     r9d, 18h; unsigned int
0x180102928  lea     r8, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18010292f  mov     rdx, rsi; struct _MI_Instance *
0x180102932  mov     rcx, rdi; this
0x180102935  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18010293a  mov     rax, [rdi]
0x18010293d  mov     rcx, rdi
0x180102940  mov     rax, [rax+10h]
0x180102944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102949  mov     r14d, eax
0x18010294c  test    eax, eax
0x18010294e  jz      short loc_18010296E
0x180102950  mov     rcx, [rsp+218h+var_1C8]
0x180102955  test    rcx, rcx
0x180102958  jz      short loc_180102969
0x18010295a  mov     rax, [rcx]
0x18010295d  mov     edx, r12d
0x180102960  mov     rax, [rax]
0x180102963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102968  nop
0x180102969  jmp     loc_180102EED
0x18010296e  mov     rax, [rdi]
0x180102971  mov     rcx, rdi
0x180102974  mov     rax, [rax+8]
0x180102978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010297d  mov     r14d, eax
0x180102980  test    eax, eax
0x180102982  jz      short loc_1801029A2
0x180102984  mov     rcx, [rsp+218h+var_1C8]
0x180102989  test    rcx, rcx
0x18010298c  jz      short loc_18010299D
0x18010298e  mov     rax, [rcx]
0x180102991  mov     edx, r12d
0x180102994  mov     rax, [rax]
0x180102997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010299c  nop
0x18010299d  jmp     loc_180102EED
0x1801029a2  lea     r8, [rsp+218h+instance]; instance
0x1801029aa  lea     rdx, MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x1801029b1  mov     rcx, r15; context
0x1801029b4  call    MI_Context_ConstructInstance
0x1801029b9  mov     r14d, eax
0x1801029bc  test    eax, eax
0x1801029be  jz      short loc_1801029DE
0x1801029c0  mov     rcx, [rsp+218h+var_1C8]
0x1801029c5  test    rcx, rcx
0x1801029c8  jz      short loc_1801029D9
0x1801029ca  mov     rax, [rcx]
0x1801029cd  mov     edx, r12d
0x1801029d0  mov     rax, [rax]
0x1801029d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801029d8  nop
0x1801029d9  jmp     loc_180102EED
0x1801029de  mov     [rsp+218h+var_1D0], r12b
0x1801029e3  mov     rdx, [rsi+40h]
0x1801029e7  lea     rcx, [rsp+218h+instance]
0x1801029ef  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801029f4  mov     rdx, [rsi+50h]
0x1801029f8  lea     rcx, [rsp+218h+instance]
0x180102a00  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180102a05  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102a0a  lea     rdx, aCompanyname; "CompanyName"
0x180102a11  mov     rcx, rdi; this
0x180102a14  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102a19  test    eax, eax
0x180102a1b  jnz     short loc_180102A34
0x180102a1d  mov     rdx, [rsp+218h+String]
0x180102a22  test    rdx, rdx
0x180102a25  jz      short loc_180102A34
0x180102a27  lea     rcx, [rsp+218h+instance]
0x180102a2f  call    MDM_VPNv2_User_01_Set_EdpModeId
0x180102a34  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102a39  lea     rdx, aDisableaccount; "DisableAccountProtectionUI"
0x180102a40  mov     rcx, rdi; this
0x180102a43  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102a48  test    eax, eax
0x180102a4a  jnz     short loc_180102A6B
0x180102a4c  mov     rcx, [rsp+218h+String]; String
0x180102a51  test    rcx, rcx
0x180102a54  jz      short loc_180102A6B
0x180102a56  call    cs:__imp__wtoi
0x180102a5c  mov     [rsp+218h+var_F8], eax
0x180102a63  mov     [rsp+218h+var_F4], r12b
0x180102a6b  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102a70  lea     rdx, aDisableappbrow; "DisableAppBrowserUI"
0x180102a77  mov     rcx, rdi; this
0x180102a7a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102a7f  test    eax, eax
0x180102a81  jnz     short loc_180102AA2
0x180102a83  mov     rcx, [rsp+218h+String]; String
0x180102a88  test    rcx, rcx
0x180102a8b  jz      short loc_180102AA2
0x180102a8d  call    cs:__imp__wtoi
0x180102a93  mov     [rsp+218h+var_F0], eax
0x180102a9a  mov     [rsp+218h+var_EC], r12b
0x180102aa2  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102aa7  lea     rdx, aDisablecleartp; "DisableClearTpmButton"
0x180102aae  mov     rcx, rdi; this
0x180102ab1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102ab6  test    eax, eax
0x180102ab8  jnz     short loc_180102AD9
0x180102aba  mov     rcx, [rsp+218h+String]; String
0x180102abf  test    rcx, rcx
0x180102ac2  jz      short loc_180102AD9
0x180102ac4  call    cs:__imp__wtoi
0x180102aca  mov     [rsp+218h+var_E8], eax
0x180102ad1  mov     [rsp+218h+var_E4], r12b
0x180102ad9  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102ade  lea     rdx, aDisabledevices; "DisableDeviceSecurityUI"
0x180102ae5  mov     rcx, rdi; this
0x180102ae8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102aed  test    eax, eax
0x180102aef  jnz     short loc_180102B10
0x180102af1  mov     rcx, [rsp+218h+String]; String
0x180102af6  test    rcx, rcx
0x180102af9  jz      short loc_180102B10
0x180102afb  call    cs:__imp__wtoi
0x180102b01  mov     [rsp+218h+var_E0], eax
0x180102b08  mov     [rsp+218h+var_DC], r12b
0x180102b10  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102b15  lea     rdx, aDisableenhance; "DisableEnhancedNotifications"
0x180102b1c  mov     rcx, rdi; this
0x180102b1f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102b24  test    eax, eax
0x180102b26  jnz     short loc_180102B47
0x180102b28  mov     rcx, [rsp+218h+String]; String
0x180102b2d  test    rcx, rcx
0x180102b30  jz      short loc_180102B47
0x180102b32  call    cs:__imp__wtoi
0x180102b38  mov     [rsp+218h+var_D8], eax
0x180102b3f  mov     [rsp+218h+var_D4], r12b
0x180102b47  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102b4c  lea     rdx, aDisablefamilyu; "DisableFamilyUI"
0x180102b53  mov     rcx, rdi; this
0x180102b56  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102b5b  test    eax, eax
0x180102b5d  jnz     short loc_180102B7E
0x180102b5f  mov     rcx, [rsp+218h+String]; String
0x180102b64  test    rcx, rcx
0x180102b67  jz      short loc_180102B7E
0x180102b69  call    cs:__imp__wtoi
0x180102b6f  mov     [rsp+218h+var_D0], eax
0x180102b76  mov     [rsp+218h+var_CC], r12b
0x180102b7e  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102b83  lea     rdx, aDisablehealthu; "DisableHealthUI"
0x180102b8a  mov     rcx, rdi; this
0x180102b8d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102b92  test    eax, eax
0x180102b94  jnz     short loc_180102BB5
0x180102b96  mov     rcx, [rsp+218h+String]; String
0x180102b9b  test    rcx, rcx
0x180102b9e  jz      short loc_180102BB5
0x180102ba0  call    cs:__imp__wtoi
0x180102ba6  mov     [rsp+218h+var_C8], eax
0x180102bad  mov     [rsp+218h+var_C4], r12b
0x180102bb5  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102bba  lea     rdx, aDisablenetwork; "DisableNetworkUI"
0x180102bc1  mov     rcx, rdi; this
0x180102bc4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102bc9  test    eax, eax
0x180102bcb  jnz     short loc_180102BEC
0x180102bcd  mov     rcx, [rsp+218h+String]; String
0x180102bd2  test    rcx, rcx
0x180102bd5  jz      short loc_180102BEC
0x180102bd7  call    cs:__imp__wtoi
0x180102bdd  mov     [rsp+218h+var_C0], eax
0x180102be4  mov     [rsp+218h+var_BC], r12b
0x180102bec  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102bf1  lea     rdx, aDisablenotific; "DisableNotifications"
0x180102bf8  mov     rcx, rdi; this
0x180102bfb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102c00  test    eax, eax
0x180102c02  jnz     short loc_180102C23
0x180102c04  mov     rcx, [rsp+218h+String]; String
0x180102c09  test    rcx, rcx
0x180102c0c  jz      short loc_180102C23
0x180102c0e  call    cs:__imp__wtoi
0x180102c14  mov     [rsp+218h+var_B8], eax
0x180102c1b  mov     [rsp+218h+var_B4], r12b
0x180102c23  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102c28  lea     rdx, aDisabletpmfirm; "DisableTpmFirmwareUpdateWarning"
0x180102c2f  mov     rcx, rdi; this
0x180102c32  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102c37  test    eax, eax
0x180102c39  jnz     short loc_180102C5A
0x180102c3b  mov     rcx, [rsp+218h+String]; String
0x180102c40  test    rcx, rcx
0x180102c43  jz      short loc_180102C5A
0x180102c45  call    cs:__imp__wtoi
0x180102c4b  mov     [rsp+218h+var_B0], eax
0x180102c52  mov     [rsp+218h+var_AC], r12b
0x180102c5a  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102c5f  lea     rdx, aDisablevirusui; "DisableVirusUI"
0x180102c66  mov     rcx, rdi; this
0x180102c69  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102c6e  test    eax, eax
0x180102c70  jnz     short loc_180102C91
0x180102c72  mov     rcx, [rsp+218h+String]; String
0x180102c77  test    rcx, rcx
0x180102c7a  jz      short loc_180102C91
0x180102c7c  call    cs:__imp__wtoi
0x180102c82  mov     [rsp+218h+var_A8], eax
0x180102c89  mov     [rsp+218h+var_A4], r12b
0x180102c91  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102c96  lea     rdx, aDisallowexploi; "DisallowExploitProtectionOverride"
0x180102c9d  mov     rcx, rdi; this
0x180102ca0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102ca5  test    eax, eax
0x180102ca7  jnz     short loc_180102CC8
0x180102ca9  mov     rcx, [rsp+218h+String]; String
0x180102cae  test    rcx, rcx
0x180102cb1  jz      short loc_180102CC8
0x180102cb3  call    cs:__imp__wtoi
  ... truncated ...
```
