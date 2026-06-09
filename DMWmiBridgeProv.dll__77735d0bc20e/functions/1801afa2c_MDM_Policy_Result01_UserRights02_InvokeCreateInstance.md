# MDM_Policy_Result01_UserRights02_InvokeCreateInstance

- ea: `0x1801afa2c`
- end: `0x1801b04d1`
- name: `MDM_Policy_Result01_UserRights02_InvokeCreateInstance`
- size: `2725`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af930`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801afa2c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801afbf5`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801afc32`: `AccessFromNetwork`
- `0x1801afd72`: `CreateGlobalObjects`
- `0x1801afdb2`: `CreatePageFile`
- `0x1801afdf2`: `CreatePermanentSharedObjects`
- `0x1801afe32`: `CreateSymbolicLinks`
- `0x1801afe72`: `CreateToken`
- `0x1801afef2`: `DenyAccessFromNetwork`
- `0x1801aff72`: `DenyRemoteDesktopServicesLogOn`
- `0x1801afff2`: `GenerateSecurityAudits`
- `0x1801b0032`: `ImpersonateClient`
- `0x1801b0132`: `ManageAuditingAndSecurityLog`
- `0x1801afb55`: `CreateInstanceStart`
- `0x1801b0438`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_Result01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_1803681DA,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
                 0x1Fu,
                 4,
                 &v8);
    if ( !inserted )
    {
      v10[4] = &v8;
      v11 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
          0x1Fu);
        if ( LOBYTE(a2[1].reserved[1]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"AccessCredentialManagerAsTrustedCaller",
                           (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AccessFromNetwork",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ActAsPartOfTheOperatingSystem",
                                (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"BackupFilesAndDirectories",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ChangeSystemTime",
                                (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", (LONG *)&a2[3].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CreatePermanentSharedObjects",
                                (LONG *)a2[3].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CreateSymbolicLinks",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", (LONG *)&a2[4])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", (LONG *)&a2[4].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DenyAccessFromNetwork",
                                (LONG *)a2[4].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", (LONG *)&a2[4].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DenyRemoteDesktopServicesLogOn",
                                (LONG *)&a2[5])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableDelegation",
                                (LONG *)&a2[5].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"GenerateSecurityAudits",
                                (LONG *)a2[5].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ImpersonateClient",
                                (LONG *)&a2[5].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IncreaseSchedulingPriority", (LONG *)&a2[6])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"LoadUnloadDeviceDrivers",
                                (LONG *)&a2[6].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", (LONG *)a2[6].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ManageAuditingAndSecurityLog",
                                (LONG *)&a2[6].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", (LONG *)&a2[7])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ModifyFirmwareEnvironment",
                                (LONG *)&a2[7].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", (LONG *)a2[7].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ProfileSingleProcess",
                                (LONG *)&a2[7].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", (LONG *)&a2[8])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"RestoreFilesAndDirectories",
                                (LONG *)&a2[8].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", (LONG *)a2[8].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( inserted )
            {
              if ( v8 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
            else
            {
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_UserRights02_rtti, &instance);
              if ( inserted )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
              }
              else
              {
                v9 = 1;
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
                MI_Instance_Destruct((MI_Instance *)self);
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
                MI_Instance_Destruct(&instance);
              }
            }
          }
        }
      }
      else
      {
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803622FB,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1801afa2c  mov     [rsp+arg_10], rsi
0x1801afa31  mov     [rsp+arg_18], rdi
0x1801afa36  push    r12
0x1801afa38  push    r14
0x1801afa3a  push    r15
0x1801afa3c  sub     rsp, 2F0h
0x1801afa43  mov     rax, cs:__security_cookie
0x1801afa4a  xor     rax, rsp
0x1801afa4d  mov     [rsp+308h+var_28], rax
0x1801afa55  mov     rsi, rdx
0x1801afa58  mov     r15, rcx
0x1801afa5b  xor     edx, edx; Val
0x1801afa5d  mov     r8d, 230h; Size
0x1801afa63  lea     rcx, [rsp+308h+instance]; void *
0x1801afa6b  call    memset_0
0x1801afa70  mov     [rsp+308h+var_288], 0
0x1801afa7b  mov     [rsp+308h+var_284], 0
0x1801afa83  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801afa8a  mov     [rsp+308h+var_2B8], rax
0x1801afa8f  lea     rax, [rsp+308h+var_288]
0x1801afa97  mov     [rsp+308h+var_2B0], rax
0x1801afa9c  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801afaa3  mov     [rsp+308h+var_2A8], rax
0x1801afaa8  lea     rcx, [rsp+308h+var_288]
0x1801afab0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801afab5  mov     eax, cs:dword_180380B68
0x1801afabb  cmp     eax, 5
0x1801afabe  jbe     short loc_1801AFB34
0x1801afac0  mov     rdx, 200000000000h
0x1801afaca  lea     rcx, dword_180380B68
0x1801afad1  call    _tlgKeywordOn
0x1801afad6  test    al, al
0x1801afad8  jz      short loc_1801AFB34
0x1801afada  cmp     [rsp+308h+var_284], 0
0x1801afae2  jz      short loc_1801AFB16
0x1801afae4  cmp     [rsp+308h+var_270], 0
0x1801afaec  jnz     short loc_1801AFB0C
0x1801afaee  cmp     [rsp+308h+var_26C], 0
0x1801afaf6  jnz     short loc_1801AFB0C
0x1801afaf8  cmp     [rsp+308h+var_268], 0
0x1801afb00  jnz     short loc_1801AFB0C
0x1801afb02  cmp     [rsp+308h+var_264], 0
0x1801afb0a  jz      short loc_1801AFB16
0x1801afb0c  lea     r9, [rsp+308h+var_270]
0x1801afb14  jmp     short loc_1801AFB19
0x1801afb16  xor     r9d, r9d
0x1801afb19  lea     r8, [rsp+308h+var_280]
0x1801afb21  lea     rdx, word_1803681DA
0x1801afb28  lea     rcx, dword_180380B68
0x1801afb2f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801afb34  cmp     byte ptr [rsi+48h], 0
0x1801afb38  jz      loc_1801B0430
0x1801afb3e  mov     [rsp+308h+var_2C0], 0
0x1801afb43  cmp     byte ptr [rsi+58h], 0
0x1801afb47  jz      loc_1801B0430
0x1801afb4d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801afb51  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801afb55  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801afb5c  lea     rcx, [rsp+308h+var_2B8]; this
0x1801afb61  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801afb66  nop
0x1801afb67  mov     [rsp+308h+var_2C8], 0
0x1801afb70  lea     rax, [rsp+308h+var_2C8]
0x1801afb75  mov     [rsp+308h+var_2D8], rax
0x1801afb7a  mov     [rsp+308h+var_2E0], 4
0x1801afb82  mov     [rsp+308h+var_2E8], 1Fh
0x1801afb8a  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801afb91  mov     r8, [rsi+40h]
0x1801afb95  mov     rdx, [rsi+50h]
0x1801afb99  mov     rcx, r15
0x1801afb9c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801afba1  mov     edi, eax
0x1801afba3  test    eax, eax
0x1801afba5  jz      short loc_1801AFBAC
0x1801afba7  jmp     loc_1801B0435
0x1801afbac  lea     rax, [rsp+308h+var_2C8]
0x1801afbb1  mov     [rsp+308h+var_298], rax
0x1801afbb6  mov     r12d, 1
0x1801afbbc  mov     [rsp+308h+var_290], r12b
0x1801afbc1  mov     r14, [rsp+308h+var_2C8]
0x1801afbc6  test    r14, r14
0x1801afbc9  jnz     short loc_1801AFBD3
0x1801afbcb  mov     edi, r12d
0x1801afbce  jmp     loc_1801B0435
0x1801afbd3  mov     r9d, 1Fh; unsigned int
0x1801afbd9  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801afbe0  mov     rdx, rsi; struct _MI_Instance *
0x1801afbe3  mov     rcx, r14; this
0x1801afbe6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801afbeb  lea     r8, [rsi+60h]; void *
0x1801afbef  cmp     [r8+8], r12b
0x1801afbf3  jnz     short loc_1801AFC28
0x1801afbf5  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801afbfc  mov     rcx, r14; this
0x1801afbff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc04  mov     edi, eax
0x1801afc06  test    eax, eax
0x1801afc08  jz      short loc_1801AFC28
0x1801afc0a  mov     rcx, [rsp+308h+var_2C8]
0x1801afc0f  test    rcx, rcx
0x1801afc12  jz      short loc_1801AFC23
0x1801afc14  mov     rax, [rcx]
0x1801afc17  mov     edx, r12d
0x1801afc1a  mov     rax, [rax]
0x1801afc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc22  nop
0x1801afc23  jmp     loc_1801B0435
0x1801afc28  lea     r8, [rsi+70h]; void *
0x1801afc2c  cmp     [r8+8], r12b
0x1801afc30  jnz     short loc_1801AFC65
0x1801afc32  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801afc39  mov     rcx, r14; this
0x1801afc3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc41  mov     edi, eax
0x1801afc43  test    eax, eax
0x1801afc45  jz      short loc_1801AFC65
0x1801afc47  mov     rcx, [rsp+308h+var_2C8]
0x1801afc4c  test    rcx, rcx
0x1801afc4f  jz      short loc_1801AFC60
0x1801afc51  mov     rax, [rcx]
0x1801afc54  mov     edx, r12d
0x1801afc57  mov     rax, [rax]
0x1801afc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc5f  nop
0x1801afc60  jmp     loc_1801B0435
0x1801afc65  lea     r8, [rsi+80h]; void *
0x1801afc6c  cmp     [r8+8], r12b
0x1801afc70  jnz     short loc_1801AFCA5
0x1801afc72  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801afc79  mov     rcx, r14; this
0x1801afc7c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc81  mov     edi, eax
0x1801afc83  test    eax, eax
0x1801afc85  jz      short loc_1801AFCA5
0x1801afc87  mov     rcx, [rsp+308h+var_2C8]
0x1801afc8c  test    rcx, rcx
0x1801afc8f  jz      short loc_1801AFCA0
0x1801afc91  mov     rax, [rcx]
0x1801afc94  mov     edx, r12d
0x1801afc97  mov     rax, [rax]
0x1801afc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc9f  nop
0x1801afca0  jmp     loc_1801B0435
0x1801afca5  lea     r8, [rsi+90h]; void *
0x1801afcac  cmp     [r8+8], r12b
0x1801afcb0  jnz     short loc_1801AFCE5
0x1801afcb2  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801afcb9  mov     rcx, r14; this
0x1801afcbc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afcc1  mov     edi, eax
0x1801afcc3  test    eax, eax
0x1801afcc5  jz      short loc_1801AFCE5
0x1801afcc7  mov     rcx, [rsp+308h+var_2C8]
0x1801afccc  test    rcx, rcx
0x1801afccf  jz      short loc_1801AFCE0
0x1801afcd1  mov     rax, [rcx]
0x1801afcd4  mov     edx, r12d
0x1801afcd7  mov     rax, [rax]
0x1801afcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afcdf  nop
0x1801afce0  jmp     loc_1801B0435
0x1801afce5  lea     r8, [rsi+0A0h]; void *
0x1801afcec  cmp     [r8+8], r12b
0x1801afcf0  jnz     short loc_1801AFD25
0x1801afcf2  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801afcf9  mov     rcx, r14; this
0x1801afcfc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afd01  mov     edi, eax
0x1801afd03  test    eax, eax
0x1801afd05  jz      short loc_1801AFD25
0x1801afd07  mov     rcx, [rsp+308h+var_2C8]
0x1801afd0c  test    rcx, rcx
0x1801afd0f  jz      short loc_1801AFD20
0x1801afd11  mov     rax, [rcx]
0x1801afd14  mov     edx, r12d
0x1801afd17  mov     rax, [rax]
0x1801afd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afd1f  nop
0x1801afd20  jmp     loc_1801B0435
0x1801afd25  lea     r8, [rsi+0B0h]; void *
0x1801afd2c  cmp     [r8+8], r12b
0x1801afd30  jnz     short loc_1801AFD65
0x1801afd32  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801afd39  mov     rcx, r14; this
0x1801afd3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afd41  mov     edi, eax
0x1801afd43  test    eax, eax
0x1801afd45  jz      short loc_1801AFD65
0x1801afd47  mov     rcx, [rsp+308h+var_2C8]
0x1801afd4c  test    rcx, rcx
0x1801afd4f  jz      short loc_1801AFD60
0x1801afd51  mov     rax, [rcx]
0x1801afd54  mov     edx, r12d
0x1801afd57  mov     rax, [rax]
0x1801afd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afd5f  nop
0x1801afd60  jmp     loc_1801B0435
0x1801afd65  lea     r8, [rsi+0C0h]; void *
0x1801afd6c  cmp     [r8+8], r12b
0x1801afd70  jnz     short loc_1801AFDA5
0x1801afd72  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801afd79  mov     rcx, r14; this
0x1801afd7c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afd81  mov     edi, eax
0x1801afd83  test    eax, eax
0x1801afd85  jz      short loc_1801AFDA5
0x1801afd87  mov     rcx, [rsp+308h+var_2C8]
0x1801afd8c  test    rcx, rcx
0x1801afd8f  jz      short loc_1801AFDA0
0x1801afd91  mov     rax, [rcx]
0x1801afd94  mov     edx, r12d
0x1801afd97  mov     rax, [rax]
0x1801afd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afd9f  nop
0x1801afda0  jmp     loc_1801B0435
0x1801afda5  lea     r8, [rsi+0D0h]; void *
0x1801afdac  cmp     [r8+8], r12b
0x1801afdb0  jnz     short loc_1801AFDE5
0x1801afdb2  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801afdb9  mov     rcx, r14; this
0x1801afdbc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afdc1  mov     edi, eax
0x1801afdc3  test    eax, eax
0x1801afdc5  jz      short loc_1801AFDE5
0x1801afdc7  mov     rcx, [rsp+308h+var_2C8]
0x1801afdcc  test    rcx, rcx
0x1801afdcf  jz      short loc_1801AFDE0
0x1801afdd1  mov     rax, [rcx]
0x1801afdd4  mov     edx, r12d
0x1801afdd7  mov     rax, [rax]
0x1801afdda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afddf  nop
0x1801afde0  jmp     loc_1801B0435
0x1801afde5  lea     r8, [rsi+0E0h]; void *
0x1801afdec  cmp     [r8+8], r12b
0x1801afdf0  jnz     short loc_1801AFE25
0x1801afdf2  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801afdf9  mov     rcx, r14; this
0x1801afdfc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afe01  mov     edi, eax
0x1801afe03  test    eax, eax
0x1801afe05  jz      short loc_1801AFE25
0x1801afe07  mov     rcx, [rsp+308h+var_2C8]
0x1801afe0c  test    rcx, rcx
0x1801afe0f  jz      short loc_1801AFE20
0x1801afe11  mov     rax, [rcx]
0x1801afe14  mov     edx, r12d
0x1801afe17  mov     rax, [rax]
0x1801afe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afe1f  nop
0x1801afe20  jmp     loc_1801B0435
0x1801afe25  lea     r8, [rsi+0F0h]; void *
0x1801afe2c  cmp     [r8+8], r12b
0x1801afe30  jnz     short loc_1801AFE65
0x1801afe32  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801afe39  mov     rcx, r14; this
0x1801afe3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afe41  mov     edi, eax
0x1801afe43  test    eax, eax
0x1801afe45  jz      short loc_1801AFE65
0x1801afe47  mov     rcx, [rsp+308h+var_2C8]
0x1801afe4c  test    rcx, rcx
0x1801afe4f  jz      short loc_1801AFE60
0x1801afe51  mov     rax, [rcx]
0x1801afe54  mov     edx, r12d
0x1801afe57  mov     rax, [rax]
0x1801afe5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afe5f  nop
0x1801afe60  jmp     loc_1801B0435
0x1801afe65  lea     r8, [rsi+100h]; void *
0x1801afe6c  cmp     [r8+8], r12b
0x1801afe70  jnz     short loc_1801AFEA5
0x1801afe72  lea     rdx, aCreatetoken; "CreateToken"
0x1801afe79  mov     rcx, r14; this
0x1801afe7c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afe81  mov     edi, eax
0x1801afe83  test    eax, eax
0x1801afe85  jz      short loc_1801AFEA5
0x1801afe87  mov     rcx, [rsp+308h+var_2C8]
0x1801afe8c  test    rcx, rcx
0x1801afe8f  jz      short loc_1801AFEA0
0x1801afe91  mov     rax, [rcx]
0x1801afe94  mov     edx, r12d
0x1801afe97  mov     rax, [rax]
0x1801afe9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afe9f  nop
0x1801afea0  jmp     loc_1801B0435
0x1801afea5  lea     r8, [rsi+110h]; void *
0x1801afeac  cmp     [r8+8], r12b
0x1801afeb0  jnz     short loc_1801AFEE5
0x1801afeb2  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801afeb9  mov     rcx, r14; this
0x1801afebc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afec1  mov     edi, eax
0x1801afec3  test    eax, eax
0x1801afec5  jz      short loc_1801AFEE5
0x1801afec7  mov     rcx, [rsp+308h+var_2C8]
0x1801afecc  test    rcx, rcx
0x1801afecf  jz      short loc_1801AFEE0
0x1801afed1  mov     rax, [rcx]
  ... truncated ...
```
