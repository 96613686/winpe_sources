# MDM_Policy_Config01_UserRights02_InvokeCreateInstance

- ea: `0x1800f92ac`
- end: `0x1800f9d52`
- name: `MDM_Policy_Config01_UserRights02_InvokeCreateInstance`
- size: `2726`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f91f0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800f92ac`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800f9475`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800f94b2`: `AccessFromNetwork`
- `0x1800f95f2`: `CreateGlobalObjects`
- `0x1800f9632`: `CreatePageFile`
- `0x1800f9672`: `CreatePermanentSharedObjects`
- `0x1800f96b2`: `CreateSymbolicLinks`
- `0x1800f96f2`: `CreateToken`
- `0x1800f9772`: `DenyAccessFromNetwork`
- `0x1800f97f2`: `DenyRemoteDesktopServicesLogOn`
- `0x1800f9872`: `GenerateSecurityAudits`
- `0x1800f98b2`: `ImpersonateClient`
- `0x1800f99b2`: `ManageAuditingAndSecurityLog`
- `0x1800f93d5`: `CreateInstanceStart`
- `0x1800f9cb8`: `CreateInstanceEnd`
- `0x1800f931c`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-2C8h] BYREF
  char v9; // [rsp+48h] [rbp-2C0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-2B8h] BYREF
  char v11; // [rsp+78h] [rbp-290h]
  int v12; // [rsp+80h] [rbp-288h] BYREF
  char v13; // [rsp+84h] [rbp-284h]
  _BYTE v14[16]; // [rsp+88h] [rbp-280h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-270h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-258h] BYREF

  memset_0(&instance, 0, 0x230u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180367264,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_145;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_UserRights02_NodeList,
                             31,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_145;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
      0x1Fu);
    if ( LOBYTE(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessCredentialManagerAsTrustedCaller", a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
LABEL_140:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_145;
      }
    }
    if ( LOBYTE(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessFromNetwork", &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActAsPartOfTheOperatingSystem", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BackupFilesAndDirectories", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ChangeSystemTime", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePermanentSharedObjects", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateSymbolicLinks", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyAccessFromNetwork", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", &a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyRemoteDesktopServicesLogOn", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableDelegation", &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"GenerateSecurityAudits", a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ImpersonateClient", &a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IncreaseSchedulingPriority", &a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LoadUnloadDeviceDrivers", &a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageAuditingAndSecurityLog", &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyFirmwareEnvironment", &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", a2[7].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProfileSingleProcess", &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", &a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RestoreFilesAndDirectories", &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_145;
      goto LABEL_140;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_145;
      goto LABEL_140;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_UserRights02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_145;
      goto LABEL_140;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_145:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_18036F2F0,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800f92ac  mov     [rsp+arg_10], rsi
0x1800f92b1  mov     [rsp+arg_18], rdi
0x1800f92b6  push    r12
0x1800f92b8  push    r14
0x1800f92ba  push    r15
0x1800f92bc  sub     rsp, 2F0h
0x1800f92c3  mov     rax, cs:__security_cookie
0x1800f92ca  xor     rax, rsp
0x1800f92cd  mov     [rsp+308h+var_28], rax
0x1800f92d5  mov     rsi, rdx
0x1800f92d8  mov     r15, rcx
0x1800f92db  xor     edx, edx; Val
0x1800f92dd  mov     r8d, 230h; Size
0x1800f92e3  lea     rcx, [rsp+308h+instance]; void *
0x1800f92eb  call    memset_0
0x1800f92f0  mov     [rsp+308h+var_288], 0
0x1800f92fb  mov     [rsp+308h+var_284], 0
0x1800f9303  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f930a  mov     [rsp+308h+var_2B8], rax
0x1800f930f  lea     rax, [rsp+308h+var_288]
0x1800f9317  mov     [rsp+308h+var_2B0], rax
0x1800f931c  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800f9323  mov     [rsp+308h+var_2A8], rax
0x1800f9328  lea     rcx, [rsp+308h+var_288]
0x1800f9330  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f9335  mov     eax, cs:dword_180380B68
0x1800f933b  cmp     eax, 5
0x1800f933e  jbe     short loc_1800F93B4
0x1800f9340  mov     rdx, 200000000000h
0x1800f934a  lea     rcx, dword_180380B68
0x1800f9351  call    _tlgKeywordOn
0x1800f9356  test    al, al
0x1800f9358  jz      short loc_1800F93B4
0x1800f935a  cmp     [rsp+308h+var_284], 0
0x1800f9362  jz      short loc_1800F9396
0x1800f9364  cmp     [rsp+308h+var_270], 0
0x1800f936c  jnz     short loc_1800F938C
0x1800f936e  cmp     [rsp+308h+var_26C], 0
0x1800f9376  jnz     short loc_1800F938C
0x1800f9378  cmp     [rsp+308h+var_268], 0
0x1800f9380  jnz     short loc_1800F938C
0x1800f9382  cmp     [rsp+308h+var_264], 0
0x1800f938a  jz      short loc_1800F9396
0x1800f938c  lea     r9, [rsp+308h+var_270]
0x1800f9394  jmp     short loc_1800F9399
0x1800f9396  xor     r9d, r9d
0x1800f9399  lea     r8, [rsp+308h+var_280]
0x1800f93a1  lea     rdx, dword_180367264
0x1800f93a8  lea     rcx, dword_180380B68
0x1800f93af  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f93b4  cmp     byte ptr [rsi+48h], 0
0x1800f93b8  jz      loc_1800F9CB0
0x1800f93be  mov     [rsp+308h+var_2C0], 0
0x1800f93c3  cmp     byte ptr [rsi+58h], 0
0x1800f93c7  jz      loc_1800F9CB0
0x1800f93cd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f93d1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f93d5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800f93dc  lea     rcx, [rsp+308h+var_2B8]; this
0x1800f93e1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f93e6  nop
0x1800f93e7  mov     [rsp+308h+var_2C8], 0
0x1800f93f0  lea     rax, [rsp+308h+var_2C8]
0x1800f93f5  mov     [rsp+308h+var_2D8], rax
0x1800f93fa  mov     [rsp+308h+var_2E0], 4
0x1800f9402  mov     [rsp+308h+var_2E8], 1Fh
0x1800f940a  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800f9411  mov     r8, [rsi+40h]
0x1800f9415  mov     rdx, [rsi+50h]
0x1800f9419  mov     rcx, r15
0x1800f941c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f9421  mov     edi, eax
0x1800f9423  test    eax, eax
0x1800f9425  jz      short loc_1800F942C
0x1800f9427  jmp     loc_1800F9CB5
0x1800f942c  lea     rax, [rsp+308h+var_2C8]
0x1800f9431  mov     [rsp+308h+var_298], rax
0x1800f9436  mov     r12d, 1
0x1800f943c  mov     [rsp+308h+var_290], r12b
0x1800f9441  mov     r14, [rsp+308h+var_2C8]
0x1800f9446  test    r14, r14
0x1800f9449  jnz     short loc_1800F9453
0x1800f944b  mov     edi, r12d
0x1800f944e  jmp     loc_1800F9CB5
0x1800f9453  mov     r9d, 1Fh; unsigned int
0x1800f9459  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f9460  mov     rdx, rsi; struct _MI_Instance *
0x1800f9463  mov     rcx, r14; this
0x1800f9466  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f946b  lea     r8, [rsi+60h]; void *
0x1800f946f  cmp     [r8+8], r12b
0x1800f9473  jnz     short loc_1800F94A8
0x1800f9475  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800f947c  mov     rcx, r14; this
0x1800f947f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9484  mov     edi, eax
0x1800f9486  test    eax, eax
0x1800f9488  jz      short loc_1800F94A8
0x1800f948a  mov     rcx, [rsp+308h+var_2C8]
0x1800f948f  test    rcx, rcx
0x1800f9492  jz      short loc_1800F94A3
0x1800f9494  mov     rax, [rcx]
0x1800f9497  mov     edx, r12d
0x1800f949a  mov     rax, [rax]
0x1800f949d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f94a2  nop
0x1800f94a3  jmp     loc_1800F9CB5
0x1800f94a8  lea     r8, [rsi+70h]; void *
0x1800f94ac  cmp     [r8+8], r12b
0x1800f94b0  jnz     short loc_1800F94E5
0x1800f94b2  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800f94b9  mov     rcx, r14; this
0x1800f94bc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f94c1  mov     edi, eax
0x1800f94c3  test    eax, eax
0x1800f94c5  jz      short loc_1800F94E5
0x1800f94c7  mov     rcx, [rsp+308h+var_2C8]
0x1800f94cc  test    rcx, rcx
0x1800f94cf  jz      short loc_1800F94E0
0x1800f94d1  mov     rax, [rcx]
0x1800f94d4  mov     edx, r12d
0x1800f94d7  mov     rax, [rax]
0x1800f94da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f94df  nop
0x1800f94e0  jmp     loc_1800F9CB5
0x1800f94e5  lea     r8, [rsi+80h]; void *
0x1800f94ec  cmp     [r8+8], r12b
0x1800f94f0  jnz     short loc_1800F9525
0x1800f94f2  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800f94f9  mov     rcx, r14; this
0x1800f94fc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9501  mov     edi, eax
0x1800f9503  test    eax, eax
0x1800f9505  jz      short loc_1800F9525
0x1800f9507  mov     rcx, [rsp+308h+var_2C8]
0x1800f950c  test    rcx, rcx
0x1800f950f  jz      short loc_1800F9520
0x1800f9511  mov     rax, [rcx]
0x1800f9514  mov     edx, r12d
0x1800f9517  mov     rax, [rax]
0x1800f951a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f951f  nop
0x1800f9520  jmp     loc_1800F9CB5
0x1800f9525  lea     r8, [rsi+90h]; void *
0x1800f952c  cmp     [r8+8], r12b
0x1800f9530  jnz     short loc_1800F9565
0x1800f9532  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800f9539  mov     rcx, r14; this
0x1800f953c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9541  mov     edi, eax
0x1800f9543  test    eax, eax
0x1800f9545  jz      short loc_1800F9565
0x1800f9547  mov     rcx, [rsp+308h+var_2C8]
0x1800f954c  test    rcx, rcx
0x1800f954f  jz      short loc_1800F9560
0x1800f9551  mov     rax, [rcx]
0x1800f9554  mov     edx, r12d
0x1800f9557  mov     rax, [rax]
0x1800f955a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f955f  nop
0x1800f9560  jmp     loc_1800F9CB5
0x1800f9565  lea     r8, [rsi+0A0h]; void *
0x1800f956c  cmp     [r8+8], r12b
0x1800f9570  jnz     short loc_1800F95A5
0x1800f9572  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800f9579  mov     rcx, r14; this
0x1800f957c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9581  mov     edi, eax
0x1800f9583  test    eax, eax
0x1800f9585  jz      short loc_1800F95A5
0x1800f9587  mov     rcx, [rsp+308h+var_2C8]
0x1800f958c  test    rcx, rcx
0x1800f958f  jz      short loc_1800F95A0
0x1800f9591  mov     rax, [rcx]
0x1800f9594  mov     edx, r12d
0x1800f9597  mov     rax, [rax]
0x1800f959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f959f  nop
0x1800f95a0  jmp     loc_1800F9CB5
0x1800f95a5  lea     r8, [rsi+0B0h]; void *
0x1800f95ac  cmp     [r8+8], r12b
0x1800f95b0  jnz     short loc_1800F95E5
0x1800f95b2  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800f95b9  mov     rcx, r14; this
0x1800f95bc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f95c1  mov     edi, eax
0x1800f95c3  test    eax, eax
0x1800f95c5  jz      short loc_1800F95E5
0x1800f95c7  mov     rcx, [rsp+308h+var_2C8]
0x1800f95cc  test    rcx, rcx
0x1800f95cf  jz      short loc_1800F95E0
0x1800f95d1  mov     rax, [rcx]
0x1800f95d4  mov     edx, r12d
0x1800f95d7  mov     rax, [rax]
0x1800f95da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f95df  nop
0x1800f95e0  jmp     loc_1800F9CB5
0x1800f95e5  lea     r8, [rsi+0C0h]; void *
0x1800f95ec  cmp     [r8+8], r12b
0x1800f95f0  jnz     short loc_1800F9625
0x1800f95f2  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800f95f9  mov     rcx, r14; this
0x1800f95fc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9601  mov     edi, eax
0x1800f9603  test    eax, eax
0x1800f9605  jz      short loc_1800F9625
0x1800f9607  mov     rcx, [rsp+308h+var_2C8]
0x1800f960c  test    rcx, rcx
0x1800f960f  jz      short loc_1800F9620
0x1800f9611  mov     rax, [rcx]
0x1800f9614  mov     edx, r12d
0x1800f9617  mov     rax, [rax]
0x1800f961a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f961f  nop
0x1800f9620  jmp     loc_1800F9CB5
0x1800f9625  lea     r8, [rsi+0D0h]; void *
0x1800f962c  cmp     [r8+8], r12b
0x1800f9630  jnz     short loc_1800F9665
0x1800f9632  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800f9639  mov     rcx, r14; this
0x1800f963c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9641  mov     edi, eax
0x1800f9643  test    eax, eax
0x1800f9645  jz      short loc_1800F9665
0x1800f9647  mov     rcx, [rsp+308h+var_2C8]
0x1800f964c  test    rcx, rcx
0x1800f964f  jz      short loc_1800F9660
0x1800f9651  mov     rax, [rcx]
0x1800f9654  mov     edx, r12d
0x1800f9657  mov     rax, [rax]
0x1800f965a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f965f  nop
0x1800f9660  jmp     loc_1800F9CB5
0x1800f9665  lea     r8, [rsi+0E0h]; void *
0x1800f966c  cmp     [r8+8], r12b
0x1800f9670  jnz     short loc_1800F96A5
0x1800f9672  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800f9679  mov     rcx, r14; this
0x1800f967c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9681  mov     edi, eax
0x1800f9683  test    eax, eax
0x1800f9685  jz      short loc_1800F96A5
0x1800f9687  mov     rcx, [rsp+308h+var_2C8]
0x1800f968c  test    rcx, rcx
0x1800f968f  jz      short loc_1800F96A0
0x1800f9691  mov     rax, [rcx]
0x1800f9694  mov     edx, r12d
0x1800f9697  mov     rax, [rax]
0x1800f969a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f969f  nop
0x1800f96a0  jmp     loc_1800F9CB5
0x1800f96a5  lea     r8, [rsi+0F0h]; void *
0x1800f96ac  cmp     [r8+8], r12b
0x1800f96b0  jnz     short loc_1800F96E5
0x1800f96b2  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800f96b9  mov     rcx, r14; this
0x1800f96bc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f96c1  mov     edi, eax
0x1800f96c3  test    eax, eax
0x1800f96c5  jz      short loc_1800F96E5
0x1800f96c7  mov     rcx, [rsp+308h+var_2C8]
0x1800f96cc  test    rcx, rcx
0x1800f96cf  jz      short loc_1800F96E0
0x1800f96d1  mov     rax, [rcx]
0x1800f96d4  mov     edx, r12d
0x1800f96d7  mov     rax, [rax]
0x1800f96da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f96df  nop
0x1800f96e0  jmp     loc_1800F9CB5
0x1800f96e5  lea     r8, [rsi+100h]; void *
0x1800f96ec  cmp     [r8+8], r12b
0x1800f96f0  jnz     short loc_1800F9725
0x1800f96f2  lea     rdx, aCreatetoken; "CreateToken"
0x1800f96f9  mov     rcx, r14; this
0x1800f96fc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9701  mov     edi, eax
0x1800f9703  test    eax, eax
0x1800f9705  jz      short loc_1800F9725
0x1800f9707  mov     rcx, [rsp+308h+var_2C8]
0x1800f970c  test    rcx, rcx
0x1800f970f  jz      short loc_1800F9720
0x1800f9711  mov     rax, [rcx]
0x1800f9714  mov     edx, r12d
0x1800f9717  mov     rax, [rax]
0x1800f971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f971f  nop
0x1800f9720  jmp     loc_1800F9CB5
0x1800f9725  lea     r8, [rsi+110h]; void *
0x1800f972c  cmp     [r8+8], r12b
0x1800f9730  jnz     short loc_1800F9765
0x1800f9732  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800f9739  mov     rcx, r14; this
0x1800f973c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9741  mov     edi, eax
0x1800f9743  test    eax, eax
0x1800f9745  jz      short loc_1800F9765
0x1800f9747  mov     rcx, [rsp+308h+var_2C8]
0x1800f974c  test    rcx, rcx
0x1800f974f  jz      short loc_1800F9760
0x1800f9751  mov     rax, [rcx]
  ... truncated ...
```
