# MDM_Policy_Config01_UserRights02_InvokeCreateInstance

- ea: `0x1800f978c`
- end: `0x1800fa231`
- name: `MDM_Policy_Config01_UserRights02_InvokeCreateInstance`
- size: `2725`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9690`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800f978c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800f9955`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800f9992`: `AccessFromNetwork`
- `0x1800f9ad2`: `CreateGlobalObjects`
- `0x1800f9b12`: `CreatePageFile`
- `0x1800f9b52`: `CreatePermanentSharedObjects`
- `0x1800f9b92`: `CreateSymbolicLinks`
- `0x1800f9bd2`: `CreateToken`
- `0x1800f9c52`: `DenyAccessFromNetwork`
- `0x1800f9cd2`: `DenyRemoteDesktopServicesLogOn`
- `0x1800f9d52`: `GenerateSecurityAudits`
- `0x1800f9d92`: `ImpersonateClient`
- `0x1800f9e92`: `ManageAuditingAndSecurityLog`
- `0x1800f98b5`: `CreateInstanceStart`
- `0x1800fa198`: `CreateInstanceEnd`
- `0x1800f97fc`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = 4;
    goto LABEL_145;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
               0x1Fu,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_145;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
      0x1Fu);
    if ( LOBYTE(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AccessCredentialManagerAsTrustedCaller",
                   (LONG *)a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessFromNetwork", (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActAsPartOfTheOperatingSystem", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BackupFilesAndDirectories", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ChangeSystemTime", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePermanentSharedObjects", (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateSymbolicLinks", (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyAccessFromNetwork", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", (LONG *)&a2[4].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyRemoteDesktopServicesLogOn", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableDelegation", (LONG *)&a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"GenerateSecurityAudits", (LONG *)a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[5].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ImpersonateClient", (LONG *)&a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IncreaseSchedulingPriority", (LONG *)&a2[6]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LoadUnloadDeviceDrivers", (LONG *)&a2[6].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", (LONG *)a2[6].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ManageAuditingAndSecurityLog",
                   (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", (LONG *)&a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyFirmwareEnvironment", (LONG *)&a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", (LONG *)a2[7].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[7].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProfileSingleProcess", (LONG *)&a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", (LONG *)&a2[8]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RestoreFilesAndDirectories", (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    if ( LOBYTE(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_145;
        goto LABEL_140;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_145;
      goto LABEL_140;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return inserted;
}

```

## disassembly

```asm
0x1800f978c  mov     [rsp+arg_10], rsi
0x1800f9791  mov     [rsp+arg_18], rdi
0x1800f9796  push    r12
0x1800f9798  push    r14
0x1800f979a  push    r15
0x1800f979c  sub     rsp, 2F0h
0x1800f97a3  mov     rax, cs:__security_cookie
0x1800f97aa  xor     rax, rsp
0x1800f97ad  mov     [rsp+308h+var_28], rax
0x1800f97b5  mov     rsi, rdx
0x1800f97b8  mov     r15, rcx
0x1800f97bb  xor     edx, edx; Val
0x1800f97bd  mov     r8d, 230h; Size
0x1800f97c3  lea     rcx, [rsp+308h+instance]; void *
0x1800f97cb  call    memset_0
0x1800f97d0  mov     [rsp+308h+var_288], 0
0x1800f97db  mov     [rsp+308h+var_284], 0
0x1800f97e3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f97ea  mov     [rsp+308h+var_2B8], rax
0x1800f97ef  lea     rax, [rsp+308h+var_288]
0x1800f97f7  mov     [rsp+308h+var_2B0], rax
0x1800f97fc  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800f9803  mov     [rsp+308h+var_2A8], rax
0x1800f9808  lea     rcx, [rsp+308h+var_288]
0x1800f9810  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f9815  mov     eax, cs:dword_180380B68
0x1800f981b  cmp     eax, 5
0x1800f981e  jbe     short loc_1800F9894
0x1800f9820  mov     rdx, 200000000000h
0x1800f982a  lea     rcx, dword_180380B68
0x1800f9831  call    _tlgKeywordOn
0x1800f9836  test    al, al
0x1800f9838  jz      short loc_1800F9894
0x1800f983a  cmp     [rsp+308h+var_284], 0
0x1800f9842  jz      short loc_1800F9876
0x1800f9844  cmp     [rsp+308h+var_270], 0
0x1800f984c  jnz     short loc_1800F986C
0x1800f984e  cmp     [rsp+308h+var_26C], 0
0x1800f9856  jnz     short loc_1800F986C
0x1800f9858  cmp     [rsp+308h+var_268], 0
0x1800f9860  jnz     short loc_1800F986C
0x1800f9862  cmp     [rsp+308h+var_264], 0
0x1800f986a  jz      short loc_1800F9876
0x1800f986c  lea     r9, [rsp+308h+var_270]
0x1800f9874  jmp     short loc_1800F9879
0x1800f9876  xor     r9d, r9d
0x1800f9879  lea     r8, [rsp+308h+var_280]
0x1800f9881  lea     rdx, dword_180367264
0x1800f9888  lea     rcx, dword_180380B68
0x1800f988f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f9894  cmp     byte ptr [rsi+48h], 0
0x1800f9898  jz      loc_1800FA190
0x1800f989e  mov     [rsp+308h+var_2C0], 0
0x1800f98a3  cmp     byte ptr [rsi+58h], 0
0x1800f98a7  jz      loc_1800FA190
0x1800f98ad  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f98b1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f98b5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800f98bc  lea     rcx, [rsp+308h+var_2B8]; this
0x1800f98c1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f98c6  nop
0x1800f98c7  mov     [rsp+308h+var_2C8], 0
0x1800f98d0  lea     rax, [rsp+308h+var_2C8]
0x1800f98d5  mov     [rsp+308h+var_2D8], rax
0x1800f98da  mov     [rsp+308h+var_2E0], 4
0x1800f98e2  mov     [rsp+308h+var_2E8], 1Fh
0x1800f98ea  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800f98f1  mov     r8, [rsi+40h]
0x1800f98f5  mov     rdx, [rsi+50h]
0x1800f98f9  mov     rcx, r15
0x1800f98fc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f9901  mov     edi, eax
0x1800f9903  test    eax, eax
0x1800f9905  jz      short loc_1800F990C
0x1800f9907  jmp     loc_1800FA195
0x1800f990c  lea     rax, [rsp+308h+var_2C8]
0x1800f9911  mov     [rsp+308h+var_298], rax
0x1800f9916  mov     r12d, 1
0x1800f991c  mov     [rsp+308h+var_290], r12b
0x1800f9921  mov     r14, [rsp+308h+var_2C8]
0x1800f9926  test    r14, r14
0x1800f9929  jnz     short loc_1800F9933
0x1800f992b  mov     edi, r12d
0x1800f992e  jmp     loc_1800FA195
0x1800f9933  mov     r9d, 1Fh; unsigned int
0x1800f9939  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f9940  mov     rdx, rsi; struct _MI_Instance *
0x1800f9943  mov     rcx, r14; this
0x1800f9946  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f994b  lea     r8, [rsi+60h]; void *
0x1800f994f  cmp     [r8+8], r12b
0x1800f9953  jnz     short loc_1800F9988
0x1800f9955  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800f995c  mov     rcx, r14; this
0x1800f995f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9964  mov     edi, eax
0x1800f9966  test    eax, eax
0x1800f9968  jz      short loc_1800F9988
0x1800f996a  mov     rcx, [rsp+308h+var_2C8]
0x1800f996f  test    rcx, rcx
0x1800f9972  jz      short loc_1800F9983
0x1800f9974  mov     rax, [rcx]
0x1800f9977  mov     edx, r12d
0x1800f997a  mov     rax, [rax]
0x1800f997d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9982  nop
0x1800f9983  jmp     loc_1800FA195
0x1800f9988  lea     r8, [rsi+70h]; void *
0x1800f998c  cmp     [r8+8], r12b
0x1800f9990  jnz     short loc_1800F99C5
0x1800f9992  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800f9999  mov     rcx, r14; this
0x1800f999c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f99a1  mov     edi, eax
0x1800f99a3  test    eax, eax
0x1800f99a5  jz      short loc_1800F99C5
0x1800f99a7  mov     rcx, [rsp+308h+var_2C8]
0x1800f99ac  test    rcx, rcx
0x1800f99af  jz      short loc_1800F99C0
0x1800f99b1  mov     rax, [rcx]
0x1800f99b4  mov     edx, r12d
0x1800f99b7  mov     rax, [rax]
0x1800f99ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f99bf  nop
0x1800f99c0  jmp     loc_1800FA195
0x1800f99c5  lea     r8, [rsi+80h]; void *
0x1800f99cc  cmp     [r8+8], r12b
0x1800f99d0  jnz     short loc_1800F9A05
0x1800f99d2  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800f99d9  mov     rcx, r14; this
0x1800f99dc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f99e1  mov     edi, eax
0x1800f99e3  test    eax, eax
0x1800f99e5  jz      short loc_1800F9A05
0x1800f99e7  mov     rcx, [rsp+308h+var_2C8]
0x1800f99ec  test    rcx, rcx
0x1800f99ef  jz      short loc_1800F9A00
0x1800f99f1  mov     rax, [rcx]
0x1800f99f4  mov     edx, r12d
0x1800f99f7  mov     rax, [rax]
0x1800f99fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f99ff  nop
0x1800f9a00  jmp     loc_1800FA195
0x1800f9a05  lea     r8, [rsi+90h]; void *
0x1800f9a0c  cmp     [r8+8], r12b
0x1800f9a10  jnz     short loc_1800F9A45
0x1800f9a12  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800f9a19  mov     rcx, r14; this
0x1800f9a1c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9a21  mov     edi, eax
0x1800f9a23  test    eax, eax
0x1800f9a25  jz      short loc_1800F9A45
0x1800f9a27  mov     rcx, [rsp+308h+var_2C8]
0x1800f9a2c  test    rcx, rcx
0x1800f9a2f  jz      short loc_1800F9A40
0x1800f9a31  mov     rax, [rcx]
0x1800f9a34  mov     edx, r12d
0x1800f9a37  mov     rax, [rax]
0x1800f9a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a3f  nop
0x1800f9a40  jmp     loc_1800FA195
0x1800f9a45  lea     r8, [rsi+0A0h]; void *
0x1800f9a4c  cmp     [r8+8], r12b
0x1800f9a50  jnz     short loc_1800F9A85
0x1800f9a52  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800f9a59  mov     rcx, r14; this
0x1800f9a5c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9a61  mov     edi, eax
0x1800f9a63  test    eax, eax
0x1800f9a65  jz      short loc_1800F9A85
0x1800f9a67  mov     rcx, [rsp+308h+var_2C8]
0x1800f9a6c  test    rcx, rcx
0x1800f9a6f  jz      short loc_1800F9A80
0x1800f9a71  mov     rax, [rcx]
0x1800f9a74  mov     edx, r12d
0x1800f9a77  mov     rax, [rax]
0x1800f9a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a7f  nop
0x1800f9a80  jmp     loc_1800FA195
0x1800f9a85  lea     r8, [rsi+0B0h]; void *
0x1800f9a8c  cmp     [r8+8], r12b
0x1800f9a90  jnz     short loc_1800F9AC5
0x1800f9a92  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800f9a99  mov     rcx, r14; this
0x1800f9a9c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9aa1  mov     edi, eax
0x1800f9aa3  test    eax, eax
0x1800f9aa5  jz      short loc_1800F9AC5
0x1800f9aa7  mov     rcx, [rsp+308h+var_2C8]
0x1800f9aac  test    rcx, rcx
0x1800f9aaf  jz      short loc_1800F9AC0
0x1800f9ab1  mov     rax, [rcx]
0x1800f9ab4  mov     edx, r12d
0x1800f9ab7  mov     rax, [rax]
0x1800f9aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9abf  nop
0x1800f9ac0  jmp     loc_1800FA195
0x1800f9ac5  lea     r8, [rsi+0C0h]; void *
0x1800f9acc  cmp     [r8+8], r12b
0x1800f9ad0  jnz     short loc_1800F9B05
0x1800f9ad2  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800f9ad9  mov     rcx, r14; this
0x1800f9adc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9ae1  mov     edi, eax
0x1800f9ae3  test    eax, eax
0x1800f9ae5  jz      short loc_1800F9B05
0x1800f9ae7  mov     rcx, [rsp+308h+var_2C8]
0x1800f9aec  test    rcx, rcx
0x1800f9aef  jz      short loc_1800F9B00
0x1800f9af1  mov     rax, [rcx]
0x1800f9af4  mov     edx, r12d
0x1800f9af7  mov     rax, [rax]
0x1800f9afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9aff  nop
0x1800f9b00  jmp     loc_1800FA195
0x1800f9b05  lea     r8, [rsi+0D0h]; void *
0x1800f9b0c  cmp     [r8+8], r12b
0x1800f9b10  jnz     short loc_1800F9B45
0x1800f9b12  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800f9b19  mov     rcx, r14; this
0x1800f9b1c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9b21  mov     edi, eax
0x1800f9b23  test    eax, eax
0x1800f9b25  jz      short loc_1800F9B45
0x1800f9b27  mov     rcx, [rsp+308h+var_2C8]
0x1800f9b2c  test    rcx, rcx
0x1800f9b2f  jz      short loc_1800F9B40
0x1800f9b31  mov     rax, [rcx]
0x1800f9b34  mov     edx, r12d
0x1800f9b37  mov     rax, [rax]
0x1800f9b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9b3f  nop
0x1800f9b40  jmp     loc_1800FA195
0x1800f9b45  lea     r8, [rsi+0E0h]; void *
0x1800f9b4c  cmp     [r8+8], r12b
0x1800f9b50  jnz     short loc_1800F9B85
0x1800f9b52  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800f9b59  mov     rcx, r14; this
0x1800f9b5c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9b61  mov     edi, eax
0x1800f9b63  test    eax, eax
0x1800f9b65  jz      short loc_1800F9B85
0x1800f9b67  mov     rcx, [rsp+308h+var_2C8]
0x1800f9b6c  test    rcx, rcx
0x1800f9b6f  jz      short loc_1800F9B80
0x1800f9b71  mov     rax, [rcx]
0x1800f9b74  mov     edx, r12d
0x1800f9b77  mov     rax, [rax]
0x1800f9b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9b7f  nop
0x1800f9b80  jmp     loc_1800FA195
0x1800f9b85  lea     r8, [rsi+0F0h]; void *
0x1800f9b8c  cmp     [r8+8], r12b
0x1800f9b90  jnz     short loc_1800F9BC5
0x1800f9b92  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800f9b99  mov     rcx, r14; this
0x1800f9b9c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9ba1  mov     edi, eax
0x1800f9ba3  test    eax, eax
0x1800f9ba5  jz      short loc_1800F9BC5
0x1800f9ba7  mov     rcx, [rsp+308h+var_2C8]
0x1800f9bac  test    rcx, rcx
0x1800f9baf  jz      short loc_1800F9BC0
0x1800f9bb1  mov     rax, [rcx]
0x1800f9bb4  mov     edx, r12d
0x1800f9bb7  mov     rax, [rax]
0x1800f9bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9bbf  nop
0x1800f9bc0  jmp     loc_1800FA195
0x1800f9bc5  lea     r8, [rsi+100h]; void *
0x1800f9bcc  cmp     [r8+8], r12b
0x1800f9bd0  jnz     short loc_1800F9C05
0x1800f9bd2  lea     rdx, aCreatetoken; "CreateToken"
0x1800f9bd9  mov     rcx, r14; this
0x1800f9bdc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9be1  mov     edi, eax
0x1800f9be3  test    eax, eax
0x1800f9be5  jz      short loc_1800F9C05
0x1800f9be7  mov     rcx, [rsp+308h+var_2C8]
0x1800f9bec  test    rcx, rcx
0x1800f9bef  jz      short loc_1800F9C00
0x1800f9bf1  mov     rax, [rcx]
0x1800f9bf4  mov     edx, r12d
0x1800f9bf7  mov     rax, [rax]
0x1800f9bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9bff  nop
0x1800f9c00  jmp     loc_1800FA195
0x1800f9c05  lea     r8, [rsi+110h]; void *
0x1800f9c0c  cmp     [r8+8], r12b
0x1800f9c10  jnz     short loc_1800F9C45
0x1800f9c12  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800f9c19  mov     rcx, r14; this
0x1800f9c1c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800f9c21  mov     edi, eax
0x1800f9c23  test    eax, eax
0x1800f9c25  jz      short loc_1800F9C45
0x1800f9c27  mov     rcx, [rsp+308h+var_2C8]
0x1800f9c2c  test    rcx, rcx
0x1800f9c2f  jz      short loc_1800F9C40
0x1800f9c31  mov     rax, [rcx]
  ... truncated ...
```
