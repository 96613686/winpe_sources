# MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance

- ea: `0x18005c3f4`
- end: `0x18005cad2`
- name: `MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance`
- size: `1758`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18005b200`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x1800053c8`
- `0x180005470`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18005c3f4`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005c693`
- `msvcrt!_wtoi` at `0x18005c6d0`
- `msvcrt!_wtoi` at `0x18005c70d`
- `msvcrt!_wtoi` at `0x18005c74a`
- `msvcrt!_wtoi` at `0x18005c787`
- `msvcrt!_wtoi` at `0x18005c7c4`
- `msvcrt!_wtoi` at `0x18005c801`
- `msvcrt!_wtoi` at `0x18005c83e`
- `msvcrt!_wtoi` at `0x18005c8aa`
- `msvcrt!_wtoi` at `0x18005c8e7`
- `msvcrt!_wtoi` at `0x18005c924`
- `msvcrt!_wtoi` at `0x18005c961`
- `msvcrt!_wtoi` at `0x18005c99e`
- `msvcrt!_wtoi` at `0x18005c693`
- `msvcrt!_wtoi` at `0x18005c6d0`
- `msvcrt!_wtoi` at `0x18005c70d`
- `msvcrt!_wtoi` at `0x18005c74a`
- `msvcrt!_wtoi` at `0x18005c787`
- `msvcrt!_wtoi` at `0x18005c7c4`
- `msvcrt!_wtoi` at `0x18005c801`
- `msvcrt!_wtoi` at `0x18005c83e`
- `msvcrt!_wtoi` at `0x18005c8aa`
- `msvcrt!_wtoi` at `0x18005c8e7`
- `msvcrt!_wtoi` at `0x18005c924`
- `msvcrt!_wtoi` at `0x18005c961`
- `msvcrt!_wtoi` at `0x18005c99e`

## string_xrefs

- `0x18005c6b3`: `AllowAppStoreAutoUpdate`
- `0x18005c7e4`: `BlockNonAdminUserInstall`
- `0x18005c88d`: `MSIAllowUserControlOverInstall`
- `0x18005c8ca`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x18005c9be`: `ScheduleForceRestartForUpdateFailures`
- `0x18005c463`: `MDM_Policy_Config01_ApplicationManagement02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-198h] BYREF
  char v9; // [rsp+48h] [rbp-190h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-180h] BYREF
  char v12; // [rsp+80h] [rbp-158h]
  int v13; // [rsp+88h] [rbp-150h] BYREF
  char v14; // [rsp+8Ch] [rbp-14Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-148h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-138h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-128h] BYREF
  int v18; // [rsp+110h] [rbp-C8h]
  char v19; // [rsp+114h] [rbp-C4h]
  int v20; // [rsp+118h] [rbp-C0h]
  char v21; // [rsp+11Ch] [rbp-BCh]
  int v22; // [rsp+120h] [rbp-B8h]
  char v23; // [rsp+124h] [rbp-B4h]
  int v24; // [rsp+128h] [rbp-B0h]
  char v25; // [rsp+12Ch] [rbp-ACh]
  int v26; // [rsp+130h] [rbp-A8h]
  char v27; // [rsp+134h] [rbp-A4h]
  int v28; // [rsp+138h] [rbp-A0h]
  char v29; // [rsp+13Ch] [rbp-9Ch]
  int v30; // [rsp+140h] [rbp-98h]
  char v31; // [rsp+144h] [rbp-94h]
  int v32; // [rsp+148h] [rbp-90h]
  char v33; // [rsp+14Ch] [rbp-8Ch]
  int v34; // [rsp+160h] [rbp-78h]
  char v35; // [rsp+164h] [rbp-74h]
  int v36; // [rsp+168h] [rbp-70h]
  char v37; // [rsp+16Ch] [rbp-6Ch]
  int v38; // [rsp+170h] [rbp-68h]
  char v39; // [rsp+174h] [rbp-64h]
  int v40; // [rsp+178h] [rbp-60h]
  char v41; // [rsp+17Ch] [rbp-5Ch]
  int v42; // [rsp+180h] [rbp-58h]
  char v43; // [rsp+184h] [rbp-54h]

  String = 0;
  memset_0(&instance, 0, 0xE8u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_ApplicationManagement02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180346545,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_74;
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
                       &MDM_Policy_Config01_ApplicationManagement02_NodeList,
                       17,
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
      goto LABEL_74;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_ApplicationManagement02_NodeList,
      0x11u);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_74;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_74;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_74;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_ApplicationManagement02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_74;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowAllTrustedApps", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowAppStoreAutoUpdate", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowAutomaticAppArchiving", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowDeveloperUnlock", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowGameDVR", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowSharedUserAppData", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"BlockNonAdminUserInstall", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DisableStoreOriginatedApps", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"LaunchAppAfterLogOn", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"MSIAllowUserControlOverInstall",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"MSIAlwaysInstallWithElevatedPrivileges",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"RequirePrivateStoreOnly", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"RestrictAppDataToSystemVolume",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"RestrictAppToSystemVolume", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ScheduleForceRestartForUpdateFailures",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_74:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18033B266,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005c3f4  mov     [rsp+arg_10], rbx
0x18005c3f9  push    rsi
0x18005c3fa  push    rdi
0x18005c3fb  push    r12
0x18005c3fd  push    r14
0x18005c3ff  push    r15
0x18005c401  sub     rsp, 1B0h
0x18005c408  mov     rax, cs:__security_cookie
0x18005c40f  xor     rax, rsp
0x18005c412  mov     [rsp+1D8h+var_38], rax
0x18005c41a  mov     rsi, rdx
0x18005c41d  mov     r15, rcx
0x18005c420  xor     ebx, ebx
0x18005c422  mov     [rsp+1D8h+String], rbx
0x18005c427  xor     edx, edx; Val
0x18005c429  mov     r8d, 0E8h; Size
0x18005c42f  lea     rcx, [rsp+1D8h+instance]; void *
0x18005c437  call    memset_0
0x18005c43c  mov     [rsp+1D8h+var_150], ebx
0x18005c443  mov     [rsp+1D8h+var_14C], bl
0x18005c44a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005c451  mov     [rsp+1D8h+var_180], rax
0x18005c456  lea     rax, [rsp+1D8h+var_150]
0x18005c45e  mov     [rsp+1D8h+var_178], rax
0x18005c463  lea     rax, aMdmPolicyConfi_160; "MDM_Policy_Config01_ApplicationManageme"...
0x18005c46a  mov     [rsp+1D8h+var_170], rax
0x18005c46f  lea     rcx, [rsp+1D8h+var_150]
0x18005c477  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005c47c  mov     eax, cs:dword_180380B68
0x18005c482  cmp     eax, 5
0x18005c485  jbe     short loc_18005C4F6
0x18005c487  mov     rdx, 200000000000h
0x18005c491  lea     rcx, dword_180380B68
0x18005c498  call    _tlgKeywordOn
0x18005c49d  test    al, al
0x18005c49f  jz      short loc_18005C4F6
0x18005c4a1  cmp     [rsp+1D8h+var_14C], bl
0x18005c4a8  jz      short loc_18005C4D8
0x18005c4aa  cmp     [rsp+1D8h+var_138], ebx
0x18005c4b1  jnz     short loc_18005C4CE
0x18005c4b3  cmp     [rsp+1D8h+var_134], ebx
0x18005c4ba  jnz     short loc_18005C4CE
0x18005c4bc  cmp     [rsp+1D8h+var_130], ebx
0x18005c4c3  jnz     short loc_18005C4CE
0x18005c4c5  cmp     [rsp+1D8h+var_12C], ebx
0x18005c4cc  jz      short loc_18005C4D8
0x18005c4ce  lea     r9, [rsp+1D8h+var_138]
0x18005c4d6  jmp     short loc_18005C4DB
0x18005c4d8  mov     r9, rbx
0x18005c4db  lea     r8, [rsp+1D8h+var_148]
0x18005c4e3  lea     rdx, byte_180346545
0x18005c4ea  lea     rcx, dword_180380B68
0x18005c4f1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005c4f6  cmp     [rsi+48h], bl
0x18005c4f9  jz      loc_18005CA30
0x18005c4ff  mov     [rsp+1D8h+var_190], bl
0x18005c503  cmp     [rsi+58h], bl
0x18005c506  jz      loc_18005CA30
0x18005c50c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18005c510  mov     r8, [rsi+50h]; unsigned __int16 *
0x18005c514  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18005c51b  lea     rcx, [rsp+1D8h+var_180]; this
0x18005c520  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18005c525  nop
0x18005c526  mov     [rsp+1D8h+var_188], rbx
0x18005c52b  lea     rax, [rsp+1D8h+var_188]
0x18005c530  mov     [rsp+1D8h+var_1A8], rax
0x18005c535  mov     [rsp+1D8h+var_1B0], ebx
0x18005c539  mov     [rsp+1D8h+var_1B8], 11h
0x18005c541  lea     r9, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_ApplicationManagement02_NodeList
0x18005c548  mov     r8, [rsi+40h]
0x18005c54c  mov     rdx, [rsi+50h]
0x18005c550  mov     rcx, r15
0x18005c553  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005c558  mov     r14d, eax
0x18005c55b  test    eax, eax
0x18005c55d  jz      short loc_18005C564
0x18005c55f  jmp     loc_18005CA36
0x18005c564  lea     rax, [rsp+1D8h+var_188]
0x18005c569  mov     [rsp+1D8h+var_160], rax
0x18005c56e  mov     r12d, 1
0x18005c574  mov     [rsp+1D8h+var_158], r12b
0x18005c57c  mov     rdi, [rsp+1D8h+var_188]
0x18005c581  test    rdi, rdi
0x18005c584  jnz     short loc_18005C58E
0x18005c586  mov     r14d, r12d
0x18005c589  jmp     loc_18005CA36
0x18005c58e  mov     r9d, 11h; unsigned int
0x18005c594  lea     r8, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18005c59b  mov     rdx, rsi; struct _MI_Instance *
0x18005c59e  mov     rcx, rdi; this
0x18005c5a1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18005c5a6  mov     rax, [rdi]
0x18005c5a9  mov     rcx, rdi
0x18005c5ac  mov     rax, [rax+10h]
0x18005c5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5b5  mov     r14d, eax
0x18005c5b8  test    eax, eax
0x18005c5ba  jz      short loc_18005C5DA
0x18005c5bc  mov     rcx, [rsp+1D8h+var_188]
0x18005c5c1  test    rcx, rcx
0x18005c5c4  jz      short loc_18005C5D5
0x18005c5c6  mov     rax, [rcx]
0x18005c5c9  mov     edx, r12d
0x18005c5cc  mov     rax, [rax]
0x18005c5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5d4  nop
0x18005c5d5  jmp     loc_18005CA36
0x18005c5da  mov     rax, [rdi]
0x18005c5dd  mov     rcx, rdi
0x18005c5e0  mov     rax, [rax+8]
0x18005c5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5e9  mov     r14d, eax
0x18005c5ec  test    eax, eax
0x18005c5ee  jz      short loc_18005C60E
0x18005c5f0  mov     rcx, [rsp+1D8h+var_188]
0x18005c5f5  test    rcx, rcx
0x18005c5f8  jz      short loc_18005C609
0x18005c5fa  mov     rax, [rcx]
0x18005c5fd  mov     edx, r12d
0x18005c600  mov     rax, [rax]
0x18005c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c608  nop
0x18005c609  jmp     loc_18005CA36
0x18005c60e  lea     r8, [rsp+1D8h+instance]; instance
0x18005c616  lea     rdx, MDM_Policy_Config01_ApplicationManagement02_rtti; classDecl
0x18005c61d  mov     rcx, r15; context
0x18005c620  call    MI_Context_ConstructInstance
0x18005c625  mov     r14d, eax
0x18005c628  test    eax, eax
0x18005c62a  jz      short loc_18005C64A
0x18005c62c  mov     rcx, [rsp+1D8h+var_188]
0x18005c631  test    rcx, rcx
0x18005c634  jz      short loc_18005C645
0x18005c636  mov     rax, [rcx]
0x18005c639  mov     edx, r12d
0x18005c63c  mov     rax, [rax]
0x18005c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c644  nop
0x18005c645  jmp     loc_18005CA36
0x18005c64a  mov     [rsp+1D8h+var_190], r12b
0x18005c64f  mov     rdx, [rsi+40h]
0x18005c653  lea     rcx, [rsp+1D8h+instance]
0x18005c65b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005c660  mov     rdx, [rsi+50h]
0x18005c664  lea     rcx, [rsp+1D8h+instance]
0x18005c66c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005c671  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c676  lea     rdx, aAllowalltruste; "AllowAllTrustedApps"
0x18005c67d  mov     rcx, rdi; this
0x18005c680  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c685  test    eax, eax
0x18005c687  jnz     short loc_18005C6AE
0x18005c689  mov     rcx, [rsp+1D8h+String]; String
0x18005c68e  test    rcx, rcx
0x18005c691  jz      short loc_18005C6AE
0x18005c693  call    cs:__imp__wtoi
0x18005c69a  nop     dword ptr [rax+rax+00h]
0x18005c69f  mov     [rsp+1D8h+var_C8], eax
0x18005c6a6  mov     [rsp+1D8h+var_C4], r12b
0x18005c6ae  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c6b3  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18005c6ba  mov     rcx, rdi; this
0x18005c6bd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c6c2  test    eax, eax
0x18005c6c4  jnz     short loc_18005C6EB
0x18005c6c6  mov     rcx, [rsp+1D8h+String]; String
0x18005c6cb  test    rcx, rcx
0x18005c6ce  jz      short loc_18005C6EB
0x18005c6d0  call    cs:__imp__wtoi
0x18005c6d7  nop     dword ptr [rax+rax+00h]
0x18005c6dc  mov     [rsp+1D8h+var_C0], eax
0x18005c6e3  mov     [rsp+1D8h+var_BC], r12b
0x18005c6eb  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c6f0  lea     rdx, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18005c6f7  mov     rcx, rdi; this
0x18005c6fa  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c6ff  test    eax, eax
0x18005c701  jnz     short loc_18005C728
0x18005c703  mov     rcx, [rsp+1D8h+String]; String
0x18005c708  test    rcx, rcx
0x18005c70b  jz      short loc_18005C728
0x18005c70d  call    cs:__imp__wtoi
0x18005c714  nop     dword ptr [rax+rax+00h]
0x18005c719  mov     [rsp+1D8h+var_B8], eax
0x18005c720  mov     [rsp+1D8h+var_B4], r12b
0x18005c728  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c72d  lea     rdx, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x18005c734  mov     rcx, rdi; this
0x18005c737  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c73c  test    eax, eax
0x18005c73e  jnz     short loc_18005C765
0x18005c740  mov     rcx, [rsp+1D8h+String]; String
0x18005c745  test    rcx, rcx
0x18005c748  jz      short loc_18005C765
0x18005c74a  call    cs:__imp__wtoi
0x18005c751  nop     dword ptr [rax+rax+00h]
0x18005c756  mov     [rsp+1D8h+var_B0], eax
0x18005c75d  mov     [rsp+1D8h+var_AC], r12b
0x18005c765  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c76a  lea     rdx, aAllowgamedvr; "AllowGameDVR"
0x18005c771  mov     rcx, rdi; this
0x18005c774  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c779  test    eax, eax
0x18005c77b  jnz     short loc_18005C7A2
0x18005c77d  mov     rcx, [rsp+1D8h+String]; String
0x18005c782  test    rcx, rcx
0x18005c785  jz      short loc_18005C7A2
0x18005c787  call    cs:__imp__wtoi
0x18005c78e  nop     dword ptr [rax+rax+00h]
0x18005c793  mov     [rsp+1D8h+var_A8], eax
0x18005c79a  mov     [rsp+1D8h+var_A4], r12b
0x18005c7a2  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c7a7  lea     rdx, aAllowshareduse; "AllowSharedUserAppData"
0x18005c7ae  mov     rcx, rdi; this
0x18005c7b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c7b6  test    eax, eax
0x18005c7b8  jnz     short loc_18005C7DF
0x18005c7ba  mov     rcx, [rsp+1D8h+String]; String
0x18005c7bf  test    rcx, rcx
0x18005c7c2  jz      short loc_18005C7DF
0x18005c7c4  call    cs:__imp__wtoi
0x18005c7cb  nop     dword ptr [rax+rax+00h]
0x18005c7d0  mov     [rsp+1D8h+var_A0], eax
0x18005c7d7  mov     [rsp+1D8h+var_9C], r12b
0x18005c7df  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c7e4  lea     rdx, aBlocknonadminu; "BlockNonAdminUserInstall"
0x18005c7eb  mov     rcx, rdi; this
0x18005c7ee  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c7f3  test    eax, eax
0x18005c7f5  jnz     short loc_18005C81C
0x18005c7f7  mov     rcx, [rsp+1D8h+String]; String
0x18005c7fc  test    rcx, rcx
0x18005c7ff  jz      short loc_18005C81C
0x18005c801  call    cs:__imp__wtoi
0x18005c808  nop     dword ptr [rax+rax+00h]
0x18005c80d  mov     [rsp+1D8h+var_98], eax
0x18005c814  mov     [rsp+1D8h+var_94], r12b
0x18005c81c  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c821  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x18005c828  mov     rcx, rdi; this
0x18005c82b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c830  test    eax, eax
0x18005c832  jnz     short loc_18005C859
0x18005c834  mov     rcx, [rsp+1D8h+String]; String
0x18005c839  test    rcx, rcx
0x18005c83c  jz      short loc_18005C859
0x18005c83e  call    cs:__imp__wtoi
0x18005c845  nop     dword ptr [rax+rax+00h]
0x18005c84a  mov     [rsp+1D8h+var_90], eax
0x18005c851  mov     [rsp+1D8h+var_8C], r12b
0x18005c859  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c85e  lea     rdx, aLaunchappafter; "LaunchAppAfterLogOn"
0x18005c865  mov     rcx, rdi; this
0x18005c868  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c86d  test    eax, eax
0x18005c86f  jnz     short loc_18005C888
0x18005c871  mov     rdx, [rsp+1D8h+String]
0x18005c876  test    rdx, rdx
0x18005c879  jz      short loc_18005C888
0x18005c87b  lea     rcx, [rsp+1D8h+instance]
0x18005c883  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x18005c888  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c88d  lea     rdx, aMsiallowuserco; "MSIAllowUserControlOverInstall"
0x18005c894  mov     rcx, rdi; this
0x18005c897  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c89c  test    eax, eax
0x18005c89e  jnz     short loc_18005C8C5
0x18005c8a0  mov     rcx, [rsp+1D8h+String]; String
0x18005c8a5  test    rcx, rcx
0x18005c8a8  jz      short loc_18005C8C5
0x18005c8aa  call    cs:__imp__wtoi
0x18005c8b1  nop     dword ptr [rax+rax+00h]
0x18005c8b6  mov     [rsp+1D8h+var_78], eax
0x18005c8bd  mov     [rsp+1D8h+var_74], r12b
0x18005c8c5  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c8ca  lea     rdx, aMsialwaysinsta; "MSIAlwaysInstallWithElevatedPrivileges"
0x18005c8d1  mov     rcx, rdi; this
0x18005c8d4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c8d9  test    eax, eax
0x18005c8db  jnz     short loc_18005C902
0x18005c8dd  mov     rcx, [rsp+1D8h+String]; String
0x18005c8e2  test    rcx, rcx
0x18005c8e5  jz      short loc_18005C902
0x18005c8e7  call    cs:__imp__wtoi
0x18005c8ee  nop     dword ptr [rax+rax+00h]
0x18005c8f3  mov     [rsp+1D8h+var_70], eax
0x18005c8fa  mov     [rsp+1D8h+var_6C], r12b
0x18005c902  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005c907  lea     rdx, aRequireprivate; "RequirePrivateStoreOnly"
0x18005c90e  mov     rcx, rdi; this
0x18005c911  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005c916  test    eax, eax
0x18005c918  jnz     short loc_18005C93F
0x18005c91a  mov     rcx, [rsp+1D8h+String]; String
0x18005c91f  test    rcx, rcx
0x18005c922  jz      short loc_18005C93F
0x18005c924  call    cs:__imp__wtoi
0x18005c92b  nop     dword ptr [rax+rax+00h]
0x18005c930  mov     [rsp+1D8h+var_68], eax
  ... truncated ...
```
