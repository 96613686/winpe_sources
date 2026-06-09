# MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance

- ea: `0x180102240`
- end: `0x180102aad`
- name: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance`
- size: `2157`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180100cb0`

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
- `0x180102240`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18010250e`
- `msvcrt!_wtoi` at `0x18010254b`
- `msvcrt!_wtoi` at `0x180102588`
- `msvcrt!_wtoi` at `0x1801025c5`
- `msvcrt!_wtoi` at `0x180102602`
- `msvcrt!_wtoi` at `0x18010263f`
- `msvcrt!_wtoi` at `0x18010267c`
- `msvcrt!_wtoi` at `0x1801026b9`
- `msvcrt!_wtoi` at `0x1801026f6`
- `msvcrt!_wtoi` at `0x180102733`
- `msvcrt!_wtoi` at `0x180102770`
- `msvcrt!_wtoi` at `0x1801027ad`
- `msvcrt!_wtoi` at `0x180102819`
- `msvcrt!_wtoi` at `0x180102856`
- `msvcrt!_wtoi` at `0x180102893`
- `msvcrt!_wtoi` at `0x1801028d0`
- `msvcrt!_wtoi` at `0x18010290d`
- `msvcrt!_wtoi` at `0x18010294a`
- `msvcrt!_wtoi` at `0x18010250e`
- `msvcrt!_wtoi` at `0x18010254b`
- `msvcrt!_wtoi` at `0x180102588`
- `msvcrt!_wtoi` at `0x1801025c5`
- `msvcrt!_wtoi` at `0x180102602`
- `msvcrt!_wtoi` at `0x18010263f`
- `msvcrt!_wtoi` at `0x18010267c`
- `msvcrt!_wtoi` at `0x1801026b9`
- `msvcrt!_wtoi` at `0x1801026f6`
- `msvcrt!_wtoi` at `0x180102733`
- `msvcrt!_wtoi` at `0x180102770`
- `msvcrt!_wtoi` at `0x1801027ad`
- `msvcrt!_wtoi` at `0x180102819`
- `msvcrt!_wtoi` at `0x180102856`
- `msvcrt!_wtoi` at `0x180102893`
- `msvcrt!_wtoi` at `0x1801028d0`
- `msvcrt!_wtoi` at `0x18010290d`
- `msvcrt!_wtoi` at `0x18010294a`

## string_xrefs

- `0x1801024c2`: `CompanyName`
- `0x1801025a8`: `DisableDeviceSecurityUI`
- `0x180102716`: `DisableTpmFirmwareUpdateWarning`
- `0x18010292d`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801022af`: `MDM_Policy_Config01_WindowsDefenderSecurityCenter02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_WindowsDefenderSecurityCenter02_InvokeGetInstance(
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_95;
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
                       &MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
                       24,
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
      goto LABEL_95;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList,
      0x18u);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_95;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_95;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"CompanyName", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_User_01_Set_EdpModeId(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableAccountProtectionUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableAppBrowserUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableClearTpmButton", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableDeviceSecurityUI", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableNotifications", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableCustomizedToasts", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnableInAppCustomization", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"HideRansomwareDataRecovery", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"HideTPMTroubleshooting", (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180102240  mov     [rsp+arg_10], rbx
0x180102245  push    rsi
0x180102246  push    rdi
0x180102247  push    r12
0x180102249  push    r14
0x18010224b  push    r15
0x18010224d  sub     rsp, 1F0h
0x180102254  mov     rax, cs:__security_cookie
0x18010225b  xor     rax, rsp
0x18010225e  mov     [rsp+218h+var_38], rax
0x180102266  mov     rsi, rdx
0x180102269  mov     r15, rcx
0x18010226c  xor     ebx, ebx
0x18010226e  mov     [rsp+218h+String], rbx
0x180102273  xor     edx, edx; Val
0x180102275  mov     r8d, 130h; Size
0x18010227b  lea     rcx, [rsp+218h+instance]; void *
0x180102283  call    memset_0
0x180102288  mov     [rsp+218h+var_190], ebx
0x18010228f  mov     [rsp+218h+var_18C], bl
0x180102296  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18010229d  mov     [rsp+218h+var_1C0], rax
0x1801022a2  lea     rax, [rsp+218h+var_190]
0x1801022aa  mov     [rsp+218h+var_1B8], rax
0x1801022af  lea     rax, aMdmPolicyConfi_102; "MDM_Policy_Config01_WindowsDefenderSecu"...
0x1801022b6  mov     [rsp+218h+var_1B0], rax
0x1801022bb  lea     rcx, [rsp+218h+var_190]
0x1801022c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801022c8  mov     eax, cs:dword_180380B68
0x1801022ce  cmp     eax, 5
0x1801022d1  jbe     short loc_180102342
0x1801022d3  mov     rdx, 200000000000h
0x1801022dd  lea     rcx, dword_180380B68
0x1801022e4  call    _tlgKeywordOn
0x1801022e9  test    al, al
0x1801022eb  jz      short loc_180102342
0x1801022ed  cmp     [rsp+218h+var_18C], bl
0x1801022f4  jz      short loc_180102324
0x1801022f6  cmp     [rsp+218h+var_178], ebx
0x1801022fd  jnz     short loc_18010231A
0x1801022ff  cmp     [rsp+218h+var_174], ebx
0x180102306  jnz     short loc_18010231A
0x180102308  cmp     [rsp+218h+var_170], ebx
0x18010230f  jnz     short loc_18010231A
0x180102311  cmp     [rsp+218h+var_16C], ebx
0x180102318  jz      short loc_180102324
0x18010231a  lea     r9, [rsp+218h+var_178]
0x180102322  jmp     short loc_180102327
0x180102324  mov     r9, rbx
0x180102327  lea     r8, [rsp+218h+var_188]
0x18010232f  lea     rdx, byte_180363BD3
0x180102336  lea     rcx, dword_180380B68
0x18010233d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180102342  cmp     [rsi+48h], bl
0x180102345  jz      loc_180102A0B
0x18010234b  mov     [rsp+218h+var_1D0], bl
0x18010234f  cmp     [rsi+58h], bl
0x180102352  jz      loc_180102A0B
0x180102358  mov     r9, [rsi+40h]; unsigned __int16 *
0x18010235c  mov     r8, [rsi+50h]; unsigned __int16 *
0x180102360  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180102367  lea     rcx, [rsp+218h+var_1C0]; this
0x18010236c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180102371  nop
0x180102372  mov     [rsp+218h+var_1C8], rbx
0x180102377  lea     rax, [rsp+218h+var_1C8]
0x18010237c  mov     [rsp+218h+var_1E8], rax
0x180102381  mov     [rsp+218h+var_1F0], ebx
0x180102385  mov     [rsp+218h+var_1F8], 18h
0x18010238d  lea     r9, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList
0x180102394  mov     r8, [rsi+40h]
0x180102398  mov     rdx, [rsi+50h]
0x18010239c  mov     rcx, r15
0x18010239f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801023a4  mov     r14d, eax
0x1801023a7  test    eax, eax
0x1801023a9  jz      short loc_1801023B0
0x1801023ab  jmp     loc_180102A11
0x1801023b0  lea     rax, [rsp+218h+var_1C8]
0x1801023b5  mov     [rsp+218h+var_1A0], rax
0x1801023ba  mov     r12d, 1
0x1801023c0  mov     [rsp+218h+var_198], r12b
0x1801023c8  mov     rdi, [rsp+218h+var_1C8]
0x1801023cd  test    rdi, rdi
0x1801023d0  jnz     short loc_1801023DA
0x1801023d2  mov     r14d, r12d
0x1801023d5  jmp     loc_180102A11
0x1801023da  mov     r9d, 18h; unsigned int
0x1801023e0  lea     r8, ?MDM_Policy_Config01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801023e7  mov     rdx, rsi; struct _MI_Instance *
0x1801023ea  mov     rcx, rdi; this
0x1801023ed  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801023f2  mov     rax, [rdi]
0x1801023f5  mov     rcx, rdi
0x1801023f8  mov     rax, [rax+10h]
0x1801023fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102401  mov     r14d, eax
0x180102404  test    eax, eax
0x180102406  jz      short loc_180102426
0x180102408  mov     rcx, [rsp+218h+var_1C8]
0x18010240d  test    rcx, rcx
0x180102410  jz      short loc_180102421
0x180102412  mov     rax, [rcx]
0x180102415  mov     edx, r12d
0x180102418  mov     rax, [rax]
0x18010241b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102420  nop
0x180102421  jmp     loc_180102A11
0x180102426  mov     rax, [rdi]
0x180102429  mov     rcx, rdi
0x18010242c  mov     rax, [rax+8]
0x180102430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102435  mov     r14d, eax
0x180102438  test    eax, eax
0x18010243a  jz      short loc_18010245A
0x18010243c  mov     rcx, [rsp+218h+var_1C8]
0x180102441  test    rcx, rcx
0x180102444  jz      short loc_180102455
0x180102446  mov     rax, [rcx]
0x180102449  mov     edx, r12d
0x18010244c  mov     rax, [rax]
0x18010244f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102454  nop
0x180102455  jmp     loc_180102A11
0x18010245a  lea     r8, [rsp+218h+instance]; instance
0x180102462  lea     rdx, MDM_Policy_Config01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x180102469  mov     rcx, r15; context
0x18010246c  call    MI_Context_ConstructInstance
0x180102471  mov     r14d, eax
0x180102474  test    eax, eax
0x180102476  jz      short loc_180102496
0x180102478  mov     rcx, [rsp+218h+var_1C8]
0x18010247d  test    rcx, rcx
0x180102480  jz      short loc_180102491
0x180102482  mov     rax, [rcx]
0x180102485  mov     edx, r12d
0x180102488  mov     rax, [rax]
0x18010248b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102490  nop
0x180102491  jmp     loc_180102A11
0x180102496  mov     [rsp+218h+var_1D0], r12b
0x18010249b  mov     rdx, [rsi+40h]
0x18010249f  lea     rcx, [rsp+218h+instance]
0x1801024a7  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801024ac  mov     rdx, [rsi+50h]
0x1801024b0  lea     rcx, [rsp+218h+instance]
0x1801024b8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801024bd  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801024c2  lea     rdx, aCompanyname; "CompanyName"
0x1801024c9  mov     rcx, rdi; this
0x1801024cc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801024d1  test    eax, eax
0x1801024d3  jnz     short loc_1801024EC
0x1801024d5  mov     rdx, [rsp+218h+String]
0x1801024da  test    rdx, rdx
0x1801024dd  jz      short loc_1801024EC
0x1801024df  lea     rcx, [rsp+218h+instance]
0x1801024e7  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801024ec  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801024f1  lea     rdx, aDisableaccount; "DisableAccountProtectionUI"
0x1801024f8  mov     rcx, rdi; this
0x1801024fb  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102500  test    eax, eax
0x180102502  jnz     short loc_180102529
0x180102504  mov     rcx, [rsp+218h+String]; String
0x180102509  test    rcx, rcx
0x18010250c  jz      short loc_180102529
0x18010250e  call    cs:__imp__wtoi
0x180102515  nop     dword ptr [rax+rax+00h]
0x18010251a  mov     [rsp+218h+var_F8], eax
0x180102521  mov     [rsp+218h+var_F4], r12b
0x180102529  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x18010252e  lea     rdx, aDisableappbrow; "DisableAppBrowserUI"
0x180102535  mov     rcx, rdi; this
0x180102538  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18010253d  test    eax, eax
0x18010253f  jnz     short loc_180102566
0x180102541  mov     rcx, [rsp+218h+String]; String
0x180102546  test    rcx, rcx
0x180102549  jz      short loc_180102566
0x18010254b  call    cs:__imp__wtoi
0x180102552  nop     dword ptr [rax+rax+00h]
0x180102557  mov     [rsp+218h+var_F0], eax
0x18010255e  mov     [rsp+218h+var_EC], r12b
0x180102566  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x18010256b  lea     rdx, aDisablecleartp; "DisableClearTpmButton"
0x180102572  mov     rcx, rdi; this
0x180102575  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18010257a  test    eax, eax
0x18010257c  jnz     short loc_1801025A3
0x18010257e  mov     rcx, [rsp+218h+String]; String
0x180102583  test    rcx, rcx
0x180102586  jz      short loc_1801025A3
0x180102588  call    cs:__imp__wtoi
0x18010258f  nop     dword ptr [rax+rax+00h]
0x180102594  mov     [rsp+218h+var_E8], eax
0x18010259b  mov     [rsp+218h+var_E4], r12b
0x1801025a3  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801025a8  lea     rdx, aDisabledevices; "DisableDeviceSecurityUI"
0x1801025af  mov     rcx, rdi; this
0x1801025b2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801025b7  test    eax, eax
0x1801025b9  jnz     short loc_1801025E0
0x1801025bb  mov     rcx, [rsp+218h+String]; String
0x1801025c0  test    rcx, rcx
0x1801025c3  jz      short loc_1801025E0
0x1801025c5  call    cs:__imp__wtoi
0x1801025cc  nop     dword ptr [rax+rax+00h]
0x1801025d1  mov     [rsp+218h+var_E0], eax
0x1801025d8  mov     [rsp+218h+var_DC], r12b
0x1801025e0  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801025e5  lea     rdx, aDisableenhance; "DisableEnhancedNotifications"
0x1801025ec  mov     rcx, rdi; this
0x1801025ef  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801025f4  test    eax, eax
0x1801025f6  jnz     short loc_18010261D
0x1801025f8  mov     rcx, [rsp+218h+String]; String
0x1801025fd  test    rcx, rcx
0x180102600  jz      short loc_18010261D
0x180102602  call    cs:__imp__wtoi
0x180102609  nop     dword ptr [rax+rax+00h]
0x18010260e  mov     [rsp+218h+var_D8], eax
0x180102615  mov     [rsp+218h+var_D4], r12b
0x18010261d  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102622  lea     rdx, aDisablefamilyu; "DisableFamilyUI"
0x180102629  mov     rcx, rdi; this
0x18010262c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102631  test    eax, eax
0x180102633  jnz     short loc_18010265A
0x180102635  mov     rcx, [rsp+218h+String]; String
0x18010263a  test    rcx, rcx
0x18010263d  jz      short loc_18010265A
0x18010263f  call    cs:__imp__wtoi
0x180102646  nop     dword ptr [rax+rax+00h]
0x18010264b  mov     [rsp+218h+var_D0], eax
0x180102652  mov     [rsp+218h+var_CC], r12b
0x18010265a  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x18010265f  lea     rdx, aDisablehealthu; "DisableHealthUI"
0x180102666  mov     rcx, rdi; this
0x180102669  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18010266e  test    eax, eax
0x180102670  jnz     short loc_180102697
0x180102672  mov     rcx, [rsp+218h+String]; String
0x180102677  test    rcx, rcx
0x18010267a  jz      short loc_180102697
0x18010267c  call    cs:__imp__wtoi
0x180102683  nop     dword ptr [rax+rax+00h]
0x180102688  mov     [rsp+218h+var_C8], eax
0x18010268f  mov     [rsp+218h+var_C4], r12b
0x180102697  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x18010269c  lea     rdx, aDisablenetwork; "DisableNetworkUI"
0x1801026a3  mov     rcx, rdi; this
0x1801026a6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801026ab  test    eax, eax
0x1801026ad  jnz     short loc_1801026D4
0x1801026af  mov     rcx, [rsp+218h+String]; String
0x1801026b4  test    rcx, rcx
0x1801026b7  jz      short loc_1801026D4
0x1801026b9  call    cs:__imp__wtoi
0x1801026c0  nop     dword ptr [rax+rax+00h]
0x1801026c5  mov     [rsp+218h+var_C0], eax
0x1801026cc  mov     [rsp+218h+var_BC], r12b
0x1801026d4  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x1801026d9  lea     rdx, aDisablenotific; "DisableNotifications"
0x1801026e0  mov     rcx, rdi; this
0x1801026e3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801026e8  test    eax, eax
0x1801026ea  jnz     short loc_180102711
0x1801026ec  mov     rcx, [rsp+218h+String]; String
0x1801026f1  test    rcx, rcx
0x1801026f4  jz      short loc_180102711
0x1801026f6  call    cs:__imp__wtoi
0x1801026fd  nop     dword ptr [rax+rax+00h]
0x180102702  mov     [rsp+218h+var_B8], eax
0x180102709  mov     [rsp+218h+var_B4], r12b
0x180102711  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102716  lea     rdx, aDisabletpmfirm; "DisableTpmFirmwareUpdateWarning"
0x18010271d  mov     rcx, rdi; this
0x180102720  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102725  test    eax, eax
0x180102727  jnz     short loc_18010274E
0x180102729  mov     rcx, [rsp+218h+String]; String
0x18010272e  test    rcx, rcx
0x180102731  jz      short loc_18010274E
0x180102733  call    cs:__imp__wtoi
0x18010273a  nop     dword ptr [rax+rax+00h]
0x18010273f  mov     [rsp+218h+var_B0], eax
0x180102746  mov     [rsp+218h+var_AC], r12b
0x18010274e  lea     r8, [rsp+218h+String]; unsigned __int16 **
0x180102753  lea     rdx, aDisablevirusui; "DisableVirusUI"
0x18010275a  mov     rcx, rdi; this
0x18010275d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180102762  test    eax, eax
0x180102764  jnz     short loc_18010278B
0x180102766  mov     rcx, [rsp+218h+String]; String
0x18010276b  test    rcx, rcx
0x18010276e  jz      short loc_18010278B
0x180102770  call    cs:__imp__wtoi
0x180102777  nop     dword ptr [rax+rax+00h]
0x18010277c  mov     [rsp+218h+var_A8], eax
  ... truncated ...
```
