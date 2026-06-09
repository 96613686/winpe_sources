# MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance

- ea: `0x18005cdf4`
- end: `0x18005d483`
- name: `MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance`
- size: `1679`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18005bc40`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x1800051f4`
- `0x18000529c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18005cdf4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005d093`
- `msvcrt!_wtoi` at `0x18005d0ca`
- `msvcrt!_wtoi` at `0x18005d101`
- `msvcrt!_wtoi` at `0x18005d138`
- `msvcrt!_wtoi` at `0x18005d16f`
- `msvcrt!_wtoi` at `0x18005d1a6`
- `msvcrt!_wtoi` at `0x18005d1dd`
- `msvcrt!_wtoi` at `0x18005d214`
- `msvcrt!_wtoi` at `0x18005d27a`
- `msvcrt!_wtoi` at `0x18005d2b1`
- `msvcrt!_wtoi` at `0x18005d2e8`
- `msvcrt!_wtoi` at `0x18005d31f`
- `msvcrt!_wtoi` at `0x18005d356`
- `msvcrt!_wtoi` at `0x18005d093`
- `msvcrt!_wtoi` at `0x18005d0ca`
- `msvcrt!_wtoi` at `0x18005d101`
- `msvcrt!_wtoi` at `0x18005d138`
- `msvcrt!_wtoi` at `0x18005d16f`
- `msvcrt!_wtoi` at `0x18005d1a6`
- `msvcrt!_wtoi` at `0x18005d1dd`
- `msvcrt!_wtoi` at `0x18005d214`
- `msvcrt!_wtoi` at `0x18005d27a`
- `msvcrt!_wtoi` at `0x18005d2b1`
- `msvcrt!_wtoi` at `0x18005d2e8`
- `msvcrt!_wtoi` at `0x18005d31f`
- `msvcrt!_wtoi` at `0x18005d356`

## string_xrefs

- `0x18005d0ad`: `AllowAppStoreAutoUpdate`
- `0x18005d1c0`: `BlockNonAdminUserInstall`
- `0x18005d25d`: `MSIAllowUserControlOverInstall`
- `0x18005d294`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x18005d370`: `ScheduleForceRestartForUpdateFailures`
- `0x18005ce63`: `MDM_Policy_Config01_ApplicationManagement02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_ApplicationManagement02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_74;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_ApplicationManagement02_NodeList,
         0x11u,
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
      goto LABEL_74;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_ApplicationManagement02_NodeList,
      0x11u);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_74;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_74;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowAllTrustedApps",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowAppStoreAutoUpdate",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowAutomaticAppArchiving",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowDeveloperUnlock",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowGameDVR",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowSharedUserAppData",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"BlockNonAdminUserInstall",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisableStoreOriginatedApps",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"LaunchAppAfterLogOn",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MSIAllowUserControlOverInstall",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MSIAlwaysInstallWithElevatedPrivileges",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"RequirePrivateStoreOnly",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"RestrictAppDataToSystemVolume",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"RestrictAppToSystemVolume",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScheduleForceRestartForUpdateFailures",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x18005cdf4  mov     [rsp+arg_10], rbx
0x18005cdf9  push    rsi
0x18005cdfa  push    rdi
0x18005cdfb  push    r12
0x18005cdfd  push    r14
0x18005cdff  push    r15
0x18005ce01  sub     rsp, 1B0h
0x18005ce08  mov     rax, cs:__security_cookie
0x18005ce0f  xor     rax, rsp
0x18005ce12  mov     [rsp+1D8h+var_38], rax
0x18005ce1a  mov     rsi, rdx
0x18005ce1d  mov     r15, rcx
0x18005ce20  xor     ebx, ebx
0x18005ce22  mov     [rsp+1D8h+String], rbx
0x18005ce27  xor     edx, edx; Val
0x18005ce29  mov     r8d, 0E8h; Size
0x18005ce2f  lea     rcx, [rsp+1D8h+instance]; void *
0x18005ce37  call    memset_0
0x18005ce3c  mov     [rsp+1D8h+var_150], ebx
0x18005ce43  mov     [rsp+1D8h+var_14C], bl
0x18005ce4a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005ce51  mov     [rsp+1D8h+var_180], rax
0x18005ce56  lea     rax, [rsp+1D8h+var_150]
0x18005ce5e  mov     [rsp+1D8h+var_178], rax
0x18005ce63  lea     rax, aMdmPolicyConfi_160; "MDM_Policy_Config01_ApplicationManageme"...
0x18005ce6a  mov     [rsp+1D8h+var_170], rax
0x18005ce6f  lea     rcx, [rsp+1D8h+var_150]
0x18005ce77  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005ce7c  mov     eax, cs:dword_180380B68
0x18005ce82  cmp     eax, 5
0x18005ce85  jbe     short loc_18005CEF6
0x18005ce87  mov     rdx, 200000000000h
0x18005ce91  lea     rcx, dword_180380B68
0x18005ce98  call    _tlgKeywordOn
0x18005ce9d  test    al, al
0x18005ce9f  jz      short loc_18005CEF6
0x18005cea1  cmp     [rsp+1D8h+var_14C], bl
0x18005cea8  jz      short loc_18005CED8
0x18005ceaa  cmp     [rsp+1D8h+var_138], ebx
0x18005ceb1  jnz     short loc_18005CECE
0x18005ceb3  cmp     [rsp+1D8h+var_134], ebx
0x18005ceba  jnz     short loc_18005CECE
0x18005cebc  cmp     [rsp+1D8h+var_130], ebx
0x18005cec3  jnz     short loc_18005CECE
0x18005cec5  cmp     [rsp+1D8h+var_12C], ebx
0x18005cecc  jz      short loc_18005CED8
0x18005cece  lea     r9, [rsp+1D8h+var_138]
0x18005ced6  jmp     short loc_18005CEDB
0x18005ced8  mov     r9, rbx
0x18005cedb  lea     r8, [rsp+1D8h+var_148]
0x18005cee3  lea     rdx, byte_180346545
0x18005ceea  lea     rcx, dword_180380B68
0x18005cef1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005cef6  cmp     [rsi+48h], bl
0x18005cef9  jz      loc_18005D3E2
0x18005ceff  mov     [rsp+1D8h+var_190], bl
0x18005cf03  cmp     [rsi+58h], bl
0x18005cf06  jz      loc_18005D3E2
0x18005cf0c  mov     r9, [rsi+40h]; unsigned __int16 *
0x18005cf10  mov     r8, [rsi+50h]; unsigned __int16 *
0x18005cf14  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18005cf1b  lea     rcx, [rsp+1D8h+var_180]; this
0x18005cf20  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18005cf25  nop
0x18005cf26  mov     [rsp+1D8h+var_188], rbx
0x18005cf2b  lea     rax, [rsp+1D8h+var_188]
0x18005cf30  mov     [rsp+1D8h+var_1A8], rax
0x18005cf35  mov     [rsp+1D8h+var_1B0], ebx
0x18005cf39  mov     [rsp+1D8h+var_1B8], 11h
0x18005cf41  lea     r9, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_ApplicationManagement02_NodeList
0x18005cf48  mov     r8, [rsi+40h]
0x18005cf4c  mov     rdx, [rsi+50h]
0x18005cf50  mov     rcx, r15
0x18005cf53  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005cf58  mov     r14d, eax
0x18005cf5b  test    eax, eax
0x18005cf5d  jz      short loc_18005CF64
0x18005cf5f  jmp     loc_18005D3E8
0x18005cf64  lea     rax, [rsp+1D8h+var_188]
0x18005cf69  mov     [rsp+1D8h+var_160], rax
0x18005cf6e  mov     r12d, 1
0x18005cf74  mov     [rsp+1D8h+var_158], r12b
0x18005cf7c  mov     rdi, [rsp+1D8h+var_188]
0x18005cf81  test    rdi, rdi
0x18005cf84  jnz     short loc_18005CF8E
0x18005cf86  mov     r14d, r12d
0x18005cf89  jmp     loc_18005D3E8
0x18005cf8e  mov     r9d, 11h; unsigned int
0x18005cf94  lea     r8, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18005cf9b  mov     rdx, rsi; struct _MI_Instance *
0x18005cf9e  mov     rcx, rdi; this
0x18005cfa1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18005cfa6  mov     rax, [rdi]
0x18005cfa9  mov     rcx, rdi
0x18005cfac  mov     rax, [rax+10h]
0x18005cfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfb5  mov     r14d, eax
0x18005cfb8  test    eax, eax
0x18005cfba  jz      short loc_18005CFDA
0x18005cfbc  mov     rcx, [rsp+1D8h+var_188]
0x18005cfc1  test    rcx, rcx
0x18005cfc4  jz      short loc_18005CFD5
0x18005cfc6  mov     rax, [rcx]
0x18005cfc9  mov     edx, r12d
0x18005cfcc  mov     rax, [rax]
0x18005cfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfd4  nop
0x18005cfd5  jmp     loc_18005D3E8
0x18005cfda  mov     rax, [rdi]
0x18005cfdd  mov     rcx, rdi
0x18005cfe0  mov     rax, [rax+8]
0x18005cfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfe9  mov     r14d, eax
0x18005cfec  test    eax, eax
0x18005cfee  jz      short loc_18005D00E
0x18005cff0  mov     rcx, [rsp+1D8h+var_188]
0x18005cff5  test    rcx, rcx
0x18005cff8  jz      short loc_18005D009
0x18005cffa  mov     rax, [rcx]
0x18005cffd  mov     edx, r12d
0x18005d000  mov     rax, [rax]
0x18005d003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d008  nop
0x18005d009  jmp     loc_18005D3E8
0x18005d00e  lea     r8, [rsp+1D8h+instance]; instance
0x18005d016  lea     rdx, MDM_Policy_Config01_ApplicationManagement02_rtti; classDecl
0x18005d01d  mov     rcx, r15; context
0x18005d020  call    MI_Context_ConstructInstance
0x18005d025  mov     r14d, eax
0x18005d028  test    eax, eax
0x18005d02a  jz      short loc_18005D04A
0x18005d02c  mov     rcx, [rsp+1D8h+var_188]
0x18005d031  test    rcx, rcx
0x18005d034  jz      short loc_18005D045
0x18005d036  mov     rax, [rcx]
0x18005d039  mov     edx, r12d
0x18005d03c  mov     rax, [rax]
0x18005d03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d044  nop
0x18005d045  jmp     loc_18005D3E8
0x18005d04a  mov     [rsp+1D8h+var_190], r12b
0x18005d04f  mov     rdx, [rsi+40h]
0x18005d053  lea     rcx, [rsp+1D8h+instance]
0x18005d05b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005d060  mov     rdx, [rsi+50h]
0x18005d064  lea     rcx, [rsp+1D8h+instance]
0x18005d06c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005d071  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d076  lea     rdx, aAllowalltruste; "AllowAllTrustedApps"
0x18005d07d  mov     rcx, rdi; this
0x18005d080  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d085  test    eax, eax
0x18005d087  jnz     short loc_18005D0A8
0x18005d089  mov     rcx, [rsp+1D8h+String]; String
0x18005d08e  test    rcx, rcx
0x18005d091  jz      short loc_18005D0A8
0x18005d093  call    cs:__imp__wtoi
0x18005d099  mov     [rsp+1D8h+var_C8], eax
0x18005d0a0  mov     [rsp+1D8h+var_C4], r12b
0x18005d0a8  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d0ad  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18005d0b4  mov     rcx, rdi; this
0x18005d0b7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d0bc  test    eax, eax
0x18005d0be  jnz     short loc_18005D0DF
0x18005d0c0  mov     rcx, [rsp+1D8h+String]; String
0x18005d0c5  test    rcx, rcx
0x18005d0c8  jz      short loc_18005D0DF
0x18005d0ca  call    cs:__imp__wtoi
0x18005d0d0  mov     [rsp+1D8h+var_C0], eax
0x18005d0d7  mov     [rsp+1D8h+var_BC], r12b
0x18005d0df  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d0e4  lea     rdx, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18005d0eb  mov     rcx, rdi; this
0x18005d0ee  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d0f3  test    eax, eax
0x18005d0f5  jnz     short loc_18005D116
0x18005d0f7  mov     rcx, [rsp+1D8h+String]; String
0x18005d0fc  test    rcx, rcx
0x18005d0ff  jz      short loc_18005D116
0x18005d101  call    cs:__imp__wtoi
0x18005d107  mov     [rsp+1D8h+var_B8], eax
0x18005d10e  mov     [rsp+1D8h+var_B4], r12b
0x18005d116  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d11b  lea     rdx, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x18005d122  mov     rcx, rdi; this
0x18005d125  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d12a  test    eax, eax
0x18005d12c  jnz     short loc_18005D14D
0x18005d12e  mov     rcx, [rsp+1D8h+String]; String
0x18005d133  test    rcx, rcx
0x18005d136  jz      short loc_18005D14D
0x18005d138  call    cs:__imp__wtoi
0x18005d13e  mov     [rsp+1D8h+var_B0], eax
0x18005d145  mov     [rsp+1D8h+var_AC], r12b
0x18005d14d  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d152  lea     rdx, aAllowgamedvr; "AllowGameDVR"
0x18005d159  mov     rcx, rdi; this
0x18005d15c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d161  test    eax, eax
0x18005d163  jnz     short loc_18005D184
0x18005d165  mov     rcx, [rsp+1D8h+String]; String
0x18005d16a  test    rcx, rcx
0x18005d16d  jz      short loc_18005D184
0x18005d16f  call    cs:__imp__wtoi
0x18005d175  mov     [rsp+1D8h+var_A8], eax
0x18005d17c  mov     [rsp+1D8h+var_A4], r12b
0x18005d184  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d189  lea     rdx, aAllowshareduse; "AllowSharedUserAppData"
0x18005d190  mov     rcx, rdi; this
0x18005d193  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d198  test    eax, eax
0x18005d19a  jnz     short loc_18005D1BB
0x18005d19c  mov     rcx, [rsp+1D8h+String]; String
0x18005d1a1  test    rcx, rcx
0x18005d1a4  jz      short loc_18005D1BB
0x18005d1a6  call    cs:__imp__wtoi
0x18005d1ac  mov     [rsp+1D8h+var_A0], eax
0x18005d1b3  mov     [rsp+1D8h+var_9C], r12b
0x18005d1bb  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d1c0  lea     rdx, aBlocknonadminu; "BlockNonAdminUserInstall"
0x18005d1c7  mov     rcx, rdi; this
0x18005d1ca  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d1cf  test    eax, eax
0x18005d1d1  jnz     short loc_18005D1F2
0x18005d1d3  mov     rcx, [rsp+1D8h+String]; String
0x18005d1d8  test    rcx, rcx
0x18005d1db  jz      short loc_18005D1F2
0x18005d1dd  call    cs:__imp__wtoi
0x18005d1e3  mov     [rsp+1D8h+var_98], eax
0x18005d1ea  mov     [rsp+1D8h+var_94], r12b
0x18005d1f2  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d1f7  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x18005d1fe  mov     rcx, rdi; this
0x18005d201  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d206  test    eax, eax
0x18005d208  jnz     short loc_18005D229
0x18005d20a  mov     rcx, [rsp+1D8h+String]; String
0x18005d20f  test    rcx, rcx
0x18005d212  jz      short loc_18005D229
0x18005d214  call    cs:__imp__wtoi
0x18005d21a  mov     [rsp+1D8h+var_90], eax
0x18005d221  mov     [rsp+1D8h+var_8C], r12b
0x18005d229  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d22e  lea     rdx, aLaunchappafter; "LaunchAppAfterLogOn"
0x18005d235  mov     rcx, rdi; this
0x18005d238  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d23d  test    eax, eax
0x18005d23f  jnz     short loc_18005D258
0x18005d241  mov     rdx, [rsp+1D8h+String]
0x18005d246  test    rdx, rdx
0x18005d249  jz      short loc_18005D258
0x18005d24b  lea     rcx, [rsp+1D8h+instance]
0x18005d253  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x18005d258  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d25d  lea     rdx, aMsiallowuserco; "MSIAllowUserControlOverInstall"
0x18005d264  mov     rcx, rdi; this
0x18005d267  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d26c  test    eax, eax
0x18005d26e  jnz     short loc_18005D28F
0x18005d270  mov     rcx, [rsp+1D8h+String]; String
0x18005d275  test    rcx, rcx
0x18005d278  jz      short loc_18005D28F
0x18005d27a  call    cs:__imp__wtoi
0x18005d280  mov     [rsp+1D8h+var_78], eax
0x18005d287  mov     [rsp+1D8h+var_74], r12b
0x18005d28f  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d294  lea     rdx, aMsialwaysinsta; "MSIAlwaysInstallWithElevatedPrivileges"
0x18005d29b  mov     rcx, rdi; this
0x18005d29e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d2a3  test    eax, eax
0x18005d2a5  jnz     short loc_18005D2C6
0x18005d2a7  mov     rcx, [rsp+1D8h+String]; String
0x18005d2ac  test    rcx, rcx
0x18005d2af  jz      short loc_18005D2C6
0x18005d2b1  call    cs:__imp__wtoi
0x18005d2b7  mov     [rsp+1D8h+var_70], eax
0x18005d2be  mov     [rsp+1D8h+var_6C], r12b
0x18005d2c6  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d2cb  lea     rdx, aRequireprivate; "RequirePrivateStoreOnly"
0x18005d2d2  mov     rcx, rdi; this
0x18005d2d5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d2da  test    eax, eax
0x18005d2dc  jnz     short loc_18005D2FD
0x18005d2de  mov     rcx, [rsp+1D8h+String]; String
0x18005d2e3  test    rcx, rcx
0x18005d2e6  jz      short loc_18005D2FD
0x18005d2e8  call    cs:__imp__wtoi
0x18005d2ee  mov     [rsp+1D8h+var_68], eax
0x18005d2f5  mov     [rsp+1D8h+var_64], r12b
0x18005d2fd  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18005d302  lea     rdx, aRestrictappdat; "RestrictAppDataToSystemVolume"
0x18005d309  mov     rcx, rdi; this
0x18005d30c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18005d311  test    eax, eax
0x18005d313  jnz     short loc_18005D334
0x18005d315  mov     rcx, [rsp+1D8h+String]; String
0x18005d31a  test    rcx, rcx
0x18005d31d  jz      short loc_18005D334
0x18005d31f  call    cs:__imp__wtoi
  ... truncated ...
```
