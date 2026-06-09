# MDM_Policy_Config01_DeviceLock02_InvokeGetInstance

- ea: `0x180085d14`
- end: `0x180086413`
- name: `MDM_Policy_Config01_DeviceLock02_InvokeGetInstance`
- size: `1791`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084ab0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050f0`
- `0x180005160`
- `0x180005198`
- `0x1800051d0`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180085d14`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180085fb3`
- `msvcrt!_wtoi` at `0x18008604e`
- `msvcrt!_wtoi` at `0x1800860e9`
- `msvcrt!_wtoi` at `0x180086126`
- `msvcrt!_wtoi` at `0x180086163`
- `msvcrt!_wtoi` at `0x1800861a0`
- `msvcrt!_wtoi` at `0x1800861dd`
- `msvcrt!_wtoi` at `0x18008621a`
- `msvcrt!_wtoi` at `0x180086257`
- `msvcrt!_wtoi` at `0x180086294`
- `msvcrt!_wtoi` at `0x1800862d1`
- `msvcrt!_wtoi` at `0x18008630e`
- `msvcrt!_wtoi` at `0x180085fb3`
- `msvcrt!_wtoi` at `0x18008604e`
- `msvcrt!_wtoi` at `0x1800860e9`
- `msvcrt!_wtoi` at `0x180086126`
- `msvcrt!_wtoi` at `0x180086163`
- `msvcrt!_wtoi` at `0x1800861a0`
- `msvcrt!_wtoi` at `0x1800861dd`
- `msvcrt!_wtoi` at `0x18008621a`
- `msvcrt!_wtoi` at `0x180086257`
- `msvcrt!_wtoi` at `0x180086294`
- `msvcrt!_wtoi` at `0x1800862d1`
- `msvcrt!_wtoi` at `0x18008630e`

## string_xrefs

- `0x180085f96`: `AllowScreenTimeoutWhileLockedUserConfig`
- `0x1800861fd`: `MinDevicePasswordComplexCharacters`
- `0x1800862b4`: `MaxDevicePasswordFailedAttempts`
- `0x180085d83`: `MDM_Policy_Config01_DeviceLock02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeviceLock02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-1A8h] BYREF
  char v9; // [rsp+48h] [rbp-1A0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-198h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-190h] BYREF
  char v12; // [rsp+80h] [rbp-168h]
  int v13; // [rsp+88h] [rbp-160h] BYREF
  char v14; // [rsp+8Ch] [rbp-15Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-158h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-148h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-138h] BYREF
  int v18; // [rsp+110h] [rbp-D8h]
  char v19; // [rsp+114h] [rbp-D4h]
  int v20; // [rsp+138h] [rbp-B0h]
  char v21; // [rsp+13Ch] [rbp-ACh]
  int v22; // [rsp+160h] [rbp-88h]
  char v23; // [rsp+164h] [rbp-84h]
  int v24; // [rsp+168h] [rbp-80h]
  char v25; // [rsp+16Ch] [rbp-7Ch]
  int v26; // [rsp+170h] [rbp-78h]
  char v27; // [rsp+174h] [rbp-74h]
  int v28; // [rsp+178h] [rbp-70h]
  char v29; // [rsp+17Ch] [rbp-6Ch]
  int v30; // [rsp+180h] [rbp-68h]
  char v31; // [rsp+184h] [rbp-64h]
  int v32; // [rsp+188h] [rbp-60h]
  char v33; // [rsp+18Ch] [rbp-5Ch]
  int v34; // [rsp+190h] [rbp-58h]
  char v35; // [rsp+194h] [rbp-54h]
  int v36; // [rsp+198h] [rbp-50h]
  char v37; // [rsp+19Ch] [rbp-4Ch]
  int v38; // [rsp+1A0h] [rbp-48h]
  char v39; // [rsp+1A4h] [rbp-44h]
  int v40; // [rsp+1A8h] [rbp-40h]
  char v41; // [rsp+1ACh] [rbp-3Ch]

  String = 0;
  memset_0(&instance, 0, 0x100u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_DeviceLock02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18036CBCD,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_77;
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
                       &MDM_Policy_Config01_DeviceLock02_NodeList,
                       18,
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
      goto LABEL_77;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeviceLock02_NodeList,
      0x12u);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_77;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_77;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_77;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeviceLock02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_77;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowScreenTimeoutWhileLockedUserConfig",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"EnforceLockScreenAndLogonImage",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnforceLockScreenProvider", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"MinimumPasswordAge", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PreventEnablingLockScreenCamera",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"PreventLockScreenSlideShow", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ScreenTimeoutWhileLocked", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DevicePasswordEnabled", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowSimpleDevicePassword", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"MinDevicePasswordLength", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AlphanumericDevicePasswordRequired",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"MinDevicePasswordComplexCharacters",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DevicePasswordExpiration", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DevicePasswordHistory", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"MaxDevicePasswordFailedAttempts",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"MaxInactivityTimeDeviceLock",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_77:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18035A09C,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180085d14  mov     [rsp+arg_10], rbx
0x180085d19  push    rsi
0x180085d1a  push    rdi
0x180085d1b  push    r12
0x180085d1d  push    r14
0x180085d1f  push    r15
0x180085d21  sub     rsp, 1C0h
0x180085d28  mov     rax, cs:__security_cookie
0x180085d2f  xor     rax, rsp
0x180085d32  mov     [rsp+1E8h+var_38], rax
0x180085d3a  mov     rsi, rdx
0x180085d3d  mov     r15, rcx
0x180085d40  xor     ebx, ebx
0x180085d42  mov     [rsp+1E8h+String], rbx
0x180085d47  xor     edx, edx; Val
0x180085d49  mov     r8d, 100h; Size
0x180085d4f  lea     rcx, [rsp+1E8h+instance]; void *
0x180085d57  call    memset_0
0x180085d5c  mov     [rsp+1E8h+var_160], ebx
0x180085d63  mov     [rsp+1E8h+var_15C], bl
0x180085d6a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180085d71  mov     [rsp+1E8h+var_190], rax
0x180085d76  lea     rax, [rsp+1E8h+var_160]
0x180085d7e  mov     [rsp+1E8h+var_188], rax
0x180085d83  lea     rax, aMdmPolicyConfi_133; "MDM_Policy_Config01_DeviceLock02"
0x180085d8a  mov     [rsp+1E8h+var_180], rax
0x180085d8f  lea     rcx, [rsp+1E8h+var_160]
0x180085d97  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180085d9c  mov     eax, cs:dword_180380B68
0x180085da2  cmp     eax, 5
0x180085da5  jbe     short loc_180085E16
0x180085da7  mov     rdx, 200000000000h
0x180085db1  lea     rcx, dword_180380B68
0x180085db8  call    _tlgKeywordOn
0x180085dbd  test    al, al
0x180085dbf  jz      short loc_180085E16
0x180085dc1  cmp     [rsp+1E8h+var_15C], bl
0x180085dc8  jz      short loc_180085DF8
0x180085dca  cmp     [rsp+1E8h+var_148], ebx
0x180085dd1  jnz     short loc_180085DEE
0x180085dd3  cmp     [rsp+1E8h+var_144], ebx
0x180085dda  jnz     short loc_180085DEE
0x180085ddc  cmp     [rsp+1E8h+var_140], ebx
0x180085de3  jnz     short loc_180085DEE
0x180085de5  cmp     [rsp+1E8h+var_13C], ebx
0x180085dec  jz      short loc_180085DF8
0x180085dee  lea     r9, [rsp+1E8h+var_148]
0x180085df6  jmp     short loc_180085DFB
0x180085df8  mov     r9, rbx
0x180085dfb  lea     r8, [rsp+1E8h+var_158]
0x180085e03  lea     rdx, byte_18036CBCD
0x180085e0a  lea     rcx, dword_180380B68
0x180085e11  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180085e16  cmp     [rsi+48h], bl
0x180085e19  jz      loc_180086371
0x180085e1f  mov     [rsp+1E8h+var_1A0], bl
0x180085e23  cmp     [rsi+58h], bl
0x180085e26  jz      loc_180086371
0x180085e2c  mov     r9, [rsi+40h]; unsigned __int16 *
0x180085e30  mov     r8, [rsi+50h]; unsigned __int16 *
0x180085e34  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180085e3b  lea     rcx, [rsp+1E8h+var_190]; this
0x180085e40  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180085e45  nop
0x180085e46  mov     [rsp+1E8h+var_198], rbx
0x180085e4b  lea     rax, [rsp+1E8h+var_198]
0x180085e50  mov     [rsp+1E8h+var_1B8], rax
0x180085e55  mov     [rsp+1E8h+var_1C0], ebx
0x180085e59  mov     [rsp+1E8h+var_1C8], 12h
0x180085e61  lea     r9, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceLock02_NodeList
0x180085e68  mov     r8, [rsi+40h]
0x180085e6c  mov     rdx, [rsi+50h]
0x180085e70  mov     rcx, r15
0x180085e73  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180085e78  mov     r14d, eax
0x180085e7b  test    eax, eax
0x180085e7d  jz      short loc_180085E84
0x180085e7f  jmp     loc_180086377
0x180085e84  lea     rax, [rsp+1E8h+var_198]
0x180085e89  mov     [rsp+1E8h+var_170], rax
0x180085e8e  mov     r12d, 1
0x180085e94  mov     [rsp+1E8h+var_168], r12b
0x180085e9c  mov     rdi, [rsp+1E8h+var_198]
0x180085ea1  test    rdi, rdi
0x180085ea4  jnz     short loc_180085EAE
0x180085ea6  mov     r14d, r12d
0x180085ea9  jmp     loc_180086377
0x180085eae  mov     r9d, 12h; unsigned int
0x180085eb4  lea     r8, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180085ebb  mov     rdx, rsi; struct _MI_Instance *
0x180085ebe  mov     rcx, rdi; this
0x180085ec1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180085ec6  mov     rax, [rdi]
0x180085ec9  mov     rcx, rdi
0x180085ecc  mov     rax, [rax+10h]
0x180085ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ed5  mov     r14d, eax
0x180085ed8  test    eax, eax
0x180085eda  jz      short loc_180085EFA
0x180085edc  mov     rcx, [rsp+1E8h+var_198]
0x180085ee1  test    rcx, rcx
0x180085ee4  jz      short loc_180085EF5
0x180085ee6  mov     rax, [rcx]
0x180085ee9  mov     edx, r12d
0x180085eec  mov     rax, [rax]
0x180085eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ef4  nop
0x180085ef5  jmp     loc_180086377
0x180085efa  mov     rax, [rdi]
0x180085efd  mov     rcx, rdi
0x180085f00  mov     rax, [rax+8]
0x180085f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f09  mov     r14d, eax
0x180085f0c  test    eax, eax
0x180085f0e  jz      short loc_180085F2E
0x180085f10  mov     rcx, [rsp+1E8h+var_198]
0x180085f15  test    rcx, rcx
0x180085f18  jz      short loc_180085F29
0x180085f1a  mov     rax, [rcx]
0x180085f1d  mov     edx, r12d
0x180085f20  mov     rax, [rax]
0x180085f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f28  nop
0x180085f29  jmp     loc_180086377
0x180085f2e  lea     r8, [rsp+1E8h+instance]; instance
0x180085f36  lea     rdx, MDM_Policy_Config01_DeviceLock02_rtti; classDecl
0x180085f3d  mov     rcx, r15; context
0x180085f40  call    MI_Context_ConstructInstance
0x180085f45  mov     r14d, eax
0x180085f48  test    eax, eax
0x180085f4a  jz      short loc_180085F6A
0x180085f4c  mov     rcx, [rsp+1E8h+var_198]
0x180085f51  test    rcx, rcx
0x180085f54  jz      short loc_180085F65
0x180085f56  mov     rax, [rcx]
0x180085f59  mov     edx, r12d
0x180085f5c  mov     rax, [rax]
0x180085f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f64  nop
0x180085f65  jmp     loc_180086377
0x180085f6a  mov     [rsp+1E8h+var_1A0], r12b
0x180085f6f  mov     rdx, [rsi+40h]
0x180085f73  lea     rcx, [rsp+1E8h+instance]
0x180085f7b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180085f80  mov     rdx, [rsi+50h]
0x180085f84  lea     rcx, [rsp+1E8h+instance]
0x180085f8c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180085f91  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180085f96  lea     rdx, aAllowscreentim; "AllowScreenTimeoutWhileLockedUserConfig"
0x180085f9d  mov     rcx, rdi; this
0x180085fa0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180085fa5  test    eax, eax
0x180085fa7  jnz     short loc_180085FCE
0x180085fa9  mov     rcx, [rsp+1E8h+String]; String
0x180085fae  test    rcx, rcx
0x180085fb1  jz      short loc_180085FCE
0x180085fb3  call    cs:__imp__wtoi
0x180085fba  nop     dword ptr [rax+rax+00h]
0x180085fbf  mov     [rsp+1E8h+var_D8], eax
0x180085fc6  mov     [rsp+1E8h+var_D4], r12b
0x180085fce  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180085fd3  lea     rdx, aEnforcelockscr; "EnforceLockScreenAndLogonImage"
0x180085fda  mov     rcx, rdi; this
0x180085fdd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180085fe2  test    eax, eax
0x180085fe4  jnz     short loc_180085FFD
0x180085fe6  mov     rdx, [rsp+1E8h+String]
0x180085feb  test    rdx, rdx
0x180085fee  jz      short loc_180085FFD
0x180085ff0  lea     rcx, [rsp+1E8h+instance]
0x180085ff8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x180085ffd  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086002  lea     rdx, aEnforcelockscr_0; "EnforceLockScreenProvider"
0x180086009  mov     rcx, rdi; this
0x18008600c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086011  test    eax, eax
0x180086013  jnz     short loc_18008602C
0x180086015  mov     rdx, [rsp+1E8h+String]
0x18008601a  test    rdx, rdx
0x18008601d  jz      short loc_18008602C
0x18008601f  lea     rcx, [rsp+1E8h+instance]
0x180086027  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18008602c  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086031  lea     rdx, aMinimumpasswor; "MinimumPasswordAge"
0x180086038  mov     rcx, rdi; this
0x18008603b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086040  test    eax, eax
0x180086042  jnz     short loc_180086069
0x180086044  mov     rcx, [rsp+1E8h+String]; String
0x180086049  test    rcx, rcx
0x18008604c  jz      short loc_180086069
0x18008604e  call    cs:__imp__wtoi
0x180086055  nop     dword ptr [rax+rax+00h]
0x18008605a  mov     [rsp+1E8h+var_B0], eax
0x180086061  mov     [rsp+1E8h+var_AC], r12b
0x180086069  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x18008606e  lea     rdx, aPreventenablin; "PreventEnablingLockScreenCamera"
0x180086075  mov     rcx, rdi; this
0x180086078  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18008607d  test    eax, eax
0x18008607f  jnz     short loc_180086098
0x180086081  mov     rdx, [rsp+1E8h+String]
0x180086086  test    rdx, rdx
0x180086089  jz      short loc_180086098
0x18008608b  lea     rcx, [rsp+1E8h+instance]
0x180086093  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x180086098  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x18008609d  lea     rdx, aPreventlockscr; "PreventLockScreenSlideShow"
0x1800860a4  mov     rcx, rdi; this
0x1800860a7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800860ac  test    eax, eax
0x1800860ae  jnz     short loc_1800860C7
0x1800860b0  mov     rdx, [rsp+1E8h+String]
0x1800860b5  test    rdx, rdx
0x1800860b8  jz      short loc_1800860C7
0x1800860ba  lea     rcx, [rsp+1E8h+instance]
0x1800860c2  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1800860c7  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800860cc  lea     rdx, aScreentimeoutw; "ScreenTimeoutWhileLocked"
0x1800860d3  mov     rcx, rdi; this
0x1800860d6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800860db  test    eax, eax
0x1800860dd  jnz     short loc_180086104
0x1800860df  mov     rcx, [rsp+1E8h+String]; String
0x1800860e4  test    rcx, rcx
0x1800860e7  jz      short loc_180086104
0x1800860e9  call    cs:__imp__wtoi
0x1800860f0  nop     dword ptr [rax+rax+00h]
0x1800860f5  mov     [rsp+1E8h+var_88], eax
0x1800860fc  mov     [rsp+1E8h+var_84], r12b
0x180086104  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086109  lea     rdx, aDevicepassword; "DevicePasswordEnabled"
0x180086110  mov     rcx, rdi; this
0x180086113  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086118  test    eax, eax
0x18008611a  jnz     short loc_180086141
0x18008611c  mov     rcx, [rsp+1E8h+String]; String
0x180086121  test    rcx, rcx
0x180086124  jz      short loc_180086141
0x180086126  call    cs:__imp__wtoi
0x18008612d  nop     dword ptr [rax+rax+00h]
0x180086132  mov     [rsp+1E8h+var_80], eax
0x180086139  mov     [rsp+1E8h+var_7C], r12b
0x180086141  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086146  lea     rdx, aAllowsimpledev; "AllowSimpleDevicePassword"
0x18008614d  mov     rcx, rdi; this
0x180086150  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086155  test    eax, eax
0x180086157  jnz     short loc_18008617E
0x180086159  mov     rcx, [rsp+1E8h+String]; String
0x18008615e  test    rcx, rcx
0x180086161  jz      short loc_18008617E
0x180086163  call    cs:__imp__wtoi
0x18008616a  nop     dword ptr [rax+rax+00h]
0x18008616f  mov     [rsp+1E8h+var_78], eax
0x180086176  mov     [rsp+1E8h+var_74], r12b
0x18008617e  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086183  lea     rdx, aMindevicepassw_0; "MinDevicePasswordLength"
0x18008618a  mov     rcx, rdi; this
0x18008618d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086192  test    eax, eax
0x180086194  jnz     short loc_1800861BB
0x180086196  mov     rcx, [rsp+1E8h+String]; String
0x18008619b  test    rcx, rcx
0x18008619e  jz      short loc_1800861BB
0x1800861a0  call    cs:__imp__wtoi
0x1800861a7  nop     dword ptr [rax+rax+00h]
0x1800861ac  mov     [rsp+1E8h+var_70], eax
0x1800861b3  mov     [rsp+1E8h+var_6C], r12b
0x1800861bb  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800861c0  lea     rdx, aAlphanumericde; "AlphanumericDevicePasswordRequired"
0x1800861c7  mov     rcx, rdi; this
0x1800861ca  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800861cf  test    eax, eax
0x1800861d1  jnz     short loc_1800861F8
0x1800861d3  mov     rcx, [rsp+1E8h+String]; String
0x1800861d8  test    rcx, rcx
0x1800861db  jz      short loc_1800861F8
0x1800861dd  call    cs:__imp__wtoi
0x1800861e4  nop     dword ptr [rax+rax+00h]
0x1800861e9  mov     [rsp+1E8h+var_68], eax
0x1800861f0  mov     [rsp+1E8h+var_64], r12b
0x1800861f8  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800861fd  lea     rdx, aMindevicepassw; "MinDevicePasswordComplexCharacters"
0x180086204  mov     rcx, rdi; this
0x180086207  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18008620c  test    eax, eax
0x18008620e  jnz     short loc_180086235
0x180086210  mov     rcx, [rsp+1E8h+String]; String
0x180086215  test    rcx, rcx
0x180086218  jz      short loc_180086235
0x18008621a  call    cs:__imp__wtoi
0x180086221  nop     dword ptr [rax+rax+00h]
0x180086226  mov     [rsp+1E8h+var_60], eax
0x18008622d  mov     [rsp+1E8h+var_5C], r12b
0x180086235  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x18008623a  lea     rdx, aDevicepassword_0; "DevicePasswordExpiration"
0x180086241  mov     rcx, rdi; this
0x180086244  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086249  test    eax, eax
  ... truncated ...
```
