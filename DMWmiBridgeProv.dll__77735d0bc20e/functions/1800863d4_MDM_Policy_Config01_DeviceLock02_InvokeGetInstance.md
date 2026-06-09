# MDM_Policy_Config01_DeviceLock02_InvokeGetInstance

- ea: `0x1800863d4`
- end: `0x180086a8a`
- name: `MDM_Policy_Config01_DeviceLock02_InvokeGetInstance`
- size: `1718`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800851b0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004f1c`
- `0x180004f8c`
- `0x180004fc4`
- `0x180004ffc`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800863d4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180086673`
- `msvcrt!_wtoi` at `0x180086708`
- `msvcrt!_wtoi` at `0x18008679d`
- `msvcrt!_wtoi` at `0x1800867d4`
- `msvcrt!_wtoi` at `0x18008680b`
- `msvcrt!_wtoi` at `0x180086842`
- `msvcrt!_wtoi` at `0x180086879`
- `msvcrt!_wtoi` at `0x1800868b0`
- `msvcrt!_wtoi` at `0x1800868e7`
- `msvcrt!_wtoi` at `0x18008691e`
- `msvcrt!_wtoi` at `0x180086955`
- `msvcrt!_wtoi` at `0x18008698c`
- `msvcrt!_wtoi` at `0x180086673`
- `msvcrt!_wtoi` at `0x180086708`
- `msvcrt!_wtoi` at `0x18008679d`
- `msvcrt!_wtoi` at `0x1800867d4`
- `msvcrt!_wtoi` at `0x18008680b`
- `msvcrt!_wtoi` at `0x180086842`
- `msvcrt!_wtoi` at `0x180086879`
- `msvcrt!_wtoi` at `0x1800868b0`
- `msvcrt!_wtoi` at `0x1800868e7`
- `msvcrt!_wtoi` at `0x18008691e`
- `msvcrt!_wtoi` at `0x180086955`
- `msvcrt!_wtoi` at `0x18008698c`

## string_xrefs

- `0x180086656`: `AllowScreenTimeoutWhileLockedUserConfig`
- `0x180086893`: `MinDevicePasswordComplexCharacters`
- `0x180086938`: `MaxDevicePasswordFailedAttempts`
- `0x180086443`: `MDM_Policy_Config01_DeviceLock02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_DeviceLock02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_77;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_DeviceLock02_NodeList,
         0x12u,
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
      goto LABEL_77;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_DeviceLock02_NodeList,
      0x12u);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_77;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_77;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowScreenTimeoutWhileLockedUserConfig",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnforceLockScreenAndLogonImage",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnforceLockScreenProvider",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MinimumPasswordAge",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PreventEnablingLockScreenCamera",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"PreventLockScreenSlideShow",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ScreenTimeoutWhileLocked",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DevicePasswordEnabled",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowSimpleDevicePassword",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MinDevicePasswordLength",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AlphanumericDevicePasswordRequired",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MinDevicePasswordComplexCharacters",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DevicePasswordExpiration",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DevicePasswordHistory",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MaxDevicePasswordFailedAttempts",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"MaxInactivityTimeDeviceLock",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x1800863d4  mov     [rsp+arg_10], rbx
0x1800863d9  push    rsi
0x1800863da  push    rdi
0x1800863db  push    r12
0x1800863dd  push    r14
0x1800863df  push    r15
0x1800863e1  sub     rsp, 1C0h
0x1800863e8  mov     rax, cs:__security_cookie
0x1800863ef  xor     rax, rsp
0x1800863f2  mov     [rsp+1E8h+var_38], rax
0x1800863fa  mov     rsi, rdx
0x1800863fd  mov     r15, rcx
0x180086400  xor     ebx, ebx
0x180086402  mov     [rsp+1E8h+String], rbx
0x180086407  xor     edx, edx; Val
0x180086409  mov     r8d, 100h; Size
0x18008640f  lea     rcx, [rsp+1E8h+instance]; void *
0x180086417  call    memset_0
0x18008641c  mov     [rsp+1E8h+var_160], ebx
0x180086423  mov     [rsp+1E8h+var_15C], bl
0x18008642a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180086431  mov     [rsp+1E8h+var_190], rax
0x180086436  lea     rax, [rsp+1E8h+var_160]
0x18008643e  mov     [rsp+1E8h+var_188], rax
0x180086443  lea     rax, aMdmPolicyConfi_133; "MDM_Policy_Config01_DeviceLock02"
0x18008644a  mov     [rsp+1E8h+var_180], rax
0x18008644f  lea     rcx, [rsp+1E8h+var_160]
0x180086457  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18008645c  mov     eax, cs:dword_180380B68
0x180086462  cmp     eax, 5
0x180086465  jbe     short loc_1800864D6
0x180086467  mov     rdx, 200000000000h
0x180086471  lea     rcx, dword_180380B68
0x180086478  call    _tlgKeywordOn
0x18008647d  test    al, al
0x18008647f  jz      short loc_1800864D6
0x180086481  cmp     [rsp+1E8h+var_15C], bl
0x180086488  jz      short loc_1800864B8
0x18008648a  cmp     [rsp+1E8h+var_148], ebx
0x180086491  jnz     short loc_1800864AE
0x180086493  cmp     [rsp+1E8h+var_144], ebx
0x18008649a  jnz     short loc_1800864AE
0x18008649c  cmp     [rsp+1E8h+var_140], ebx
0x1800864a3  jnz     short loc_1800864AE
0x1800864a5  cmp     [rsp+1E8h+var_13C], ebx
0x1800864ac  jz      short loc_1800864B8
0x1800864ae  lea     r9, [rsp+1E8h+var_148]
0x1800864b6  jmp     short loc_1800864BB
0x1800864b8  mov     r9, rbx
0x1800864bb  lea     r8, [rsp+1E8h+var_158]
0x1800864c3  lea     rdx, byte_18036CBCD
0x1800864ca  lea     rcx, dword_180380B68
0x1800864d1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800864d6  cmp     [rsi+48h], bl
0x1800864d9  jz      loc_1800869E9
0x1800864df  mov     [rsp+1E8h+var_1A0], bl
0x1800864e3  cmp     [rsi+58h], bl
0x1800864e6  jz      loc_1800869E9
0x1800864ec  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800864f0  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800864f4  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800864fb  lea     rcx, [rsp+1E8h+var_190]; this
0x180086500  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180086505  nop
0x180086506  mov     [rsp+1E8h+var_198], rbx
0x18008650b  lea     rax, [rsp+1E8h+var_198]
0x180086510  mov     [rsp+1E8h+var_1B8], rax
0x180086515  mov     [rsp+1E8h+var_1C0], ebx
0x180086519  mov     [rsp+1E8h+var_1C8], 12h
0x180086521  lea     r9, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceLock02_NodeList
0x180086528  mov     r8, [rsi+40h]
0x18008652c  mov     rdx, [rsi+50h]
0x180086530  mov     rcx, r15
0x180086533  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180086538  mov     r14d, eax
0x18008653b  test    eax, eax
0x18008653d  jz      short loc_180086544
0x18008653f  jmp     loc_1800869EF
0x180086544  lea     rax, [rsp+1E8h+var_198]
0x180086549  mov     [rsp+1E8h+var_170], rax
0x18008654e  mov     r12d, 1
0x180086554  mov     [rsp+1E8h+var_168], r12b
0x18008655c  mov     rdi, [rsp+1E8h+var_198]
0x180086561  test    rdi, rdi
0x180086564  jnz     short loc_18008656E
0x180086566  mov     r14d, r12d
0x180086569  jmp     loc_1800869EF
0x18008656e  mov     r9d, 12h; unsigned int
0x180086574  lea     r8, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18008657b  mov     rdx, rsi; struct _MI_Instance *
0x18008657e  mov     rcx, rdi; this
0x180086581  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180086586  mov     rax, [rdi]
0x180086589  mov     rcx, rdi
0x18008658c  mov     rax, [rax+10h]
0x180086590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086595  mov     r14d, eax
0x180086598  test    eax, eax
0x18008659a  jz      short loc_1800865BA
0x18008659c  mov     rcx, [rsp+1E8h+var_198]
0x1800865a1  test    rcx, rcx
0x1800865a4  jz      short loc_1800865B5
0x1800865a6  mov     rax, [rcx]
0x1800865a9  mov     edx, r12d
0x1800865ac  mov     rax, [rax]
0x1800865af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865b4  nop
0x1800865b5  jmp     loc_1800869EF
0x1800865ba  mov     rax, [rdi]
0x1800865bd  mov     rcx, rdi
0x1800865c0  mov     rax, [rax+8]
0x1800865c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865c9  mov     r14d, eax
0x1800865cc  test    eax, eax
0x1800865ce  jz      short loc_1800865EE
0x1800865d0  mov     rcx, [rsp+1E8h+var_198]
0x1800865d5  test    rcx, rcx
0x1800865d8  jz      short loc_1800865E9
0x1800865da  mov     rax, [rcx]
0x1800865dd  mov     edx, r12d
0x1800865e0  mov     rax, [rax]
0x1800865e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865e8  nop
0x1800865e9  jmp     loc_1800869EF
0x1800865ee  lea     r8, [rsp+1E8h+instance]; instance
0x1800865f6  lea     rdx, MDM_Policy_Config01_DeviceLock02_rtti; classDecl
0x1800865fd  mov     rcx, r15; context
0x180086600  call    MI_Context_ConstructInstance
0x180086605  mov     r14d, eax
0x180086608  test    eax, eax
0x18008660a  jz      short loc_18008662A
0x18008660c  mov     rcx, [rsp+1E8h+var_198]
0x180086611  test    rcx, rcx
0x180086614  jz      short loc_180086625
0x180086616  mov     rax, [rcx]
0x180086619  mov     edx, r12d
0x18008661c  mov     rax, [rax]
0x18008661f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086624  nop
0x180086625  jmp     loc_1800869EF
0x18008662a  mov     [rsp+1E8h+var_1A0], r12b
0x18008662f  mov     rdx, [rsi+40h]
0x180086633  lea     rcx, [rsp+1E8h+instance]
0x18008663b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180086640  mov     rdx, [rsi+50h]
0x180086644  lea     rcx, [rsp+1E8h+instance]
0x18008664c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180086651  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086656  lea     rdx, aAllowscreentim; "AllowScreenTimeoutWhileLockedUserConfig"
0x18008665d  mov     rcx, rdi; this
0x180086660  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086665  test    eax, eax
0x180086667  jnz     short loc_180086688
0x180086669  mov     rcx, [rsp+1E8h+String]; String
0x18008666e  test    rcx, rcx
0x180086671  jz      short loc_180086688
0x180086673  call    cs:__imp__wtoi
0x180086679  mov     [rsp+1E8h+var_D8], eax
0x180086680  mov     [rsp+1E8h+var_D4], r12b
0x180086688  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x18008668d  lea     rdx, aEnforcelockscr; "EnforceLockScreenAndLogonImage"
0x180086694  mov     rcx, rdi; this
0x180086697  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18008669c  test    eax, eax
0x18008669e  jnz     short loc_1800866B7
0x1800866a0  mov     rdx, [rsp+1E8h+String]
0x1800866a5  test    rdx, rdx
0x1800866a8  jz      short loc_1800866B7
0x1800866aa  lea     rcx, [rsp+1E8h+instance]
0x1800866b2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800866b7  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800866bc  lea     rdx, aEnforcelockscr_0; "EnforceLockScreenProvider"
0x1800866c3  mov     rcx, rdi; this
0x1800866c6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800866cb  test    eax, eax
0x1800866cd  jnz     short loc_1800866E6
0x1800866cf  mov     rdx, [rsp+1E8h+String]
0x1800866d4  test    rdx, rdx
0x1800866d7  jz      short loc_1800866E6
0x1800866d9  lea     rcx, [rsp+1E8h+instance]
0x1800866e1  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800866e6  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800866eb  lea     rdx, aMinimumpasswor; "MinimumPasswordAge"
0x1800866f2  mov     rcx, rdi; this
0x1800866f5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800866fa  test    eax, eax
0x1800866fc  jnz     short loc_18008671D
0x1800866fe  mov     rcx, [rsp+1E8h+String]; String
0x180086703  test    rcx, rcx
0x180086706  jz      short loc_18008671D
0x180086708  call    cs:__imp__wtoi
0x18008670e  mov     [rsp+1E8h+var_B0], eax
0x180086715  mov     [rsp+1E8h+var_AC], r12b
0x18008671d  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086722  lea     rdx, aPreventenablin; "PreventEnablingLockScreenCamera"
0x180086729  mov     rcx, rdi; this
0x18008672c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086731  test    eax, eax
0x180086733  jnz     short loc_18008674C
0x180086735  mov     rdx, [rsp+1E8h+String]
0x18008673a  test    rdx, rdx
0x18008673d  jz      short loc_18008674C
0x18008673f  lea     rcx, [rsp+1E8h+instance]
0x180086747  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18008674c  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086751  lea     rdx, aPreventlockscr; "PreventLockScreenSlideShow"
0x180086758  mov     rcx, rdi; this
0x18008675b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086760  test    eax, eax
0x180086762  jnz     short loc_18008677B
0x180086764  mov     rdx, [rsp+1E8h+String]
0x180086769  test    rdx, rdx
0x18008676c  jz      short loc_18008677B
0x18008676e  lea     rcx, [rsp+1E8h+instance]
0x180086776  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x18008677b  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086780  lea     rdx, aScreentimeoutw; "ScreenTimeoutWhileLocked"
0x180086787  mov     rcx, rdi; this
0x18008678a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18008678f  test    eax, eax
0x180086791  jnz     short loc_1800867B2
0x180086793  mov     rcx, [rsp+1E8h+String]; String
0x180086798  test    rcx, rcx
0x18008679b  jz      short loc_1800867B2
0x18008679d  call    cs:__imp__wtoi
0x1800867a3  mov     [rsp+1E8h+var_88], eax
0x1800867aa  mov     [rsp+1E8h+var_84], r12b
0x1800867b2  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800867b7  lea     rdx, aDevicepassword; "DevicePasswordEnabled"
0x1800867be  mov     rcx, rdi; this
0x1800867c1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800867c6  test    eax, eax
0x1800867c8  jnz     short loc_1800867E9
0x1800867ca  mov     rcx, [rsp+1E8h+String]; String
0x1800867cf  test    rcx, rcx
0x1800867d2  jz      short loc_1800867E9
0x1800867d4  call    cs:__imp__wtoi
0x1800867da  mov     [rsp+1E8h+var_80], eax
0x1800867e1  mov     [rsp+1E8h+var_7C], r12b
0x1800867e9  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800867ee  lea     rdx, aAllowsimpledev; "AllowSimpleDevicePassword"
0x1800867f5  mov     rcx, rdi; this
0x1800867f8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800867fd  test    eax, eax
0x1800867ff  jnz     short loc_180086820
0x180086801  mov     rcx, [rsp+1E8h+String]; String
0x180086806  test    rcx, rcx
0x180086809  jz      short loc_180086820
0x18008680b  call    cs:__imp__wtoi
0x180086811  mov     [rsp+1E8h+var_78], eax
0x180086818  mov     [rsp+1E8h+var_74], r12b
0x180086820  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086825  lea     rdx, aMindevicepassw_0; "MinDevicePasswordLength"
0x18008682c  mov     rcx, rdi; this
0x18008682f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180086834  test    eax, eax
0x180086836  jnz     short loc_180086857
0x180086838  mov     rcx, [rsp+1E8h+String]; String
0x18008683d  test    rcx, rcx
0x180086840  jz      short loc_180086857
0x180086842  call    cs:__imp__wtoi
0x180086848  mov     [rsp+1E8h+var_70], eax
0x18008684f  mov     [rsp+1E8h+var_6C], r12b
0x180086857  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x18008685c  lea     rdx, aAlphanumericde; "AlphanumericDevicePasswordRequired"
0x180086863  mov     rcx, rdi; this
0x180086866  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18008686b  test    eax, eax
0x18008686d  jnz     short loc_18008688E
0x18008686f  mov     rcx, [rsp+1E8h+String]; String
0x180086874  test    rcx, rcx
0x180086877  jz      short loc_18008688E
0x180086879  call    cs:__imp__wtoi
0x18008687f  mov     [rsp+1E8h+var_68], eax
0x180086886  mov     [rsp+1E8h+var_64], r12b
0x18008688e  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x180086893  lea     rdx, aMindevicepassw; "MinDevicePasswordComplexCharacters"
0x18008689a  mov     rcx, rdi; this
0x18008689d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800868a2  test    eax, eax
0x1800868a4  jnz     short loc_1800868C5
0x1800868a6  mov     rcx, [rsp+1E8h+String]; String
0x1800868ab  test    rcx, rcx
0x1800868ae  jz      short loc_1800868C5
0x1800868b0  call    cs:__imp__wtoi
0x1800868b6  mov     [rsp+1E8h+var_60], eax
0x1800868bd  mov     [rsp+1E8h+var_5C], r12b
0x1800868c5  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
0x1800868ca  lea     rdx, aDevicepassword_0; "DevicePasswordExpiration"
0x1800868d1  mov     rcx, rdi; this
0x1800868d4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800868d9  test    eax, eax
0x1800868db  jnz     short loc_1800868FC
0x1800868dd  mov     rcx, [rsp+1E8h+String]; String
0x1800868e2  test    rcx, rcx
0x1800868e5  jz      short loc_1800868FC
0x1800868e7  call    cs:__imp__wtoi
0x1800868ed  mov     [rsp+1E8h+var_58], eax
0x1800868f4  mov     [rsp+1E8h+var_54], r12b
0x1800868fc  lea     r8, [rsp+1E8h+String]; unsigned __int16 **
  ... truncated ...
```
