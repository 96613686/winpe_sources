# MDM_Policy_Result01_UserRights02_InvokeCreateInstance

- ea: `0x1801af83c`
- end: `0x1801b02e2`
- name: `MDM_Policy_Result01_UserRights02_InvokeCreateInstance`
- size: `2726`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801af780`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801af83c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801afa05`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801afa42`: `AccessFromNetwork`
- `0x1801afb82`: `CreateGlobalObjects`
- `0x1801afbc2`: `CreatePageFile`
- `0x1801afc02`: `CreatePermanentSharedObjects`
- `0x1801afc42`: `CreateSymbolicLinks`
- `0x1801afc82`: `CreateToken`
- `0x1801afd02`: `DenyAccessFromNetwork`
- `0x1801afd82`: `DenyRemoteDesktopServicesLogOn`
- `0x1801afe02`: `GenerateSecurityAudits`
- `0x1801afe42`: `ImpersonateClient`
- `0x1801aff42`: `ManageAuditingAndSecurityLog`
- `0x1801af965`: `CreateInstanceStart`
- `0x1801b0248`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               self,
                               a2[1].serverName,
                               a2[1].ft,
                               &MDM_Policy_Result01_UserRights02_NodeList,
                               31,
                               4,
                               &v8);
    if ( inserted == MI_RESULT_OK )
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
                           a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessFromNetwork", &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ActAsPartOfTheOperatingSystem", &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"BackupFilesAndDirectories", a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ChangeSystemTime", &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", &a2[3].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CreatePermanentSharedObjects",
                                a2[3].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateSymbolicLinks", &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", &a2[4])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", &a2[4].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyAccessFromNetwork", a2[4].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", &a2[4].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyRemoteDesktopServicesLogOn", &a2[5])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableDelegation", &a2[5].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"GenerateSecurityAudits", a2[5].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ImpersonateClient", &a2[5].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"IncreaseSchedulingPriority", &a2[6])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LoadUnloadDeviceDrivers", &a2[6].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", a2[6].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ManageAuditingAndSecurityLog",
                                &a2[6].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", &a2[7])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ModifyFirmwareEnvironment",
                                &a2[7].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", a2[7].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProfileSingleProcess", &a2[7].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", &a2[8])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"RestoreFilesAndDirectories",
                                &a2[8].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", a2[8].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
        inserted = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801af83c  mov     [rsp+arg_10], rsi
0x1801af841  mov     [rsp+arg_18], rdi
0x1801af846  push    r12
0x1801af848  push    r14
0x1801af84a  push    r15
0x1801af84c  sub     rsp, 2F0h
0x1801af853  mov     rax, cs:__security_cookie
0x1801af85a  xor     rax, rsp
0x1801af85d  mov     [rsp+308h+var_28], rax
0x1801af865  mov     rsi, rdx
0x1801af868  mov     r15, rcx
0x1801af86b  xor     edx, edx; Val
0x1801af86d  mov     r8d, 230h; Size
0x1801af873  lea     rcx, [rsp+308h+instance]; void *
0x1801af87b  call    memset_0
0x1801af880  mov     [rsp+308h+var_288], 0
0x1801af88b  mov     [rsp+308h+var_284], 0
0x1801af893  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801af89a  mov     [rsp+308h+var_2B8], rax
0x1801af89f  lea     rax, [rsp+308h+var_288]
0x1801af8a7  mov     [rsp+308h+var_2B0], rax
0x1801af8ac  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801af8b3  mov     [rsp+308h+var_2A8], rax
0x1801af8b8  lea     rcx, [rsp+308h+var_288]
0x1801af8c0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801af8c5  mov     eax, cs:dword_180380B68
0x1801af8cb  cmp     eax, 5
0x1801af8ce  jbe     short loc_1801AF944
0x1801af8d0  mov     rdx, 200000000000h
0x1801af8da  lea     rcx, dword_180380B68
0x1801af8e1  call    _tlgKeywordOn
0x1801af8e6  test    al, al
0x1801af8e8  jz      short loc_1801AF944
0x1801af8ea  cmp     [rsp+308h+var_284], 0
0x1801af8f2  jz      short loc_1801AF926
0x1801af8f4  cmp     [rsp+308h+var_270], 0
0x1801af8fc  jnz     short loc_1801AF91C
0x1801af8fe  cmp     [rsp+308h+var_26C], 0
0x1801af906  jnz     short loc_1801AF91C
0x1801af908  cmp     [rsp+308h+var_268], 0
0x1801af910  jnz     short loc_1801AF91C
0x1801af912  cmp     [rsp+308h+var_264], 0
0x1801af91a  jz      short loc_1801AF926
0x1801af91c  lea     r9, [rsp+308h+var_270]
0x1801af924  jmp     short loc_1801AF929
0x1801af926  xor     r9d, r9d
0x1801af929  lea     r8, [rsp+308h+var_280]
0x1801af931  lea     rdx, word_1803681DA
0x1801af938  lea     rcx, dword_180380B68
0x1801af93f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801af944  cmp     byte ptr [rsi+48h], 0
0x1801af948  jz      loc_1801B0240
0x1801af94e  mov     [rsp+308h+var_2C0], 0
0x1801af953  cmp     byte ptr [rsi+58h], 0
0x1801af957  jz      loc_1801B0240
0x1801af95d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801af961  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801af965  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801af96c  lea     rcx, [rsp+308h+var_2B8]; this
0x1801af971  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801af976  nop
0x1801af977  mov     [rsp+308h+var_2C8], 0
0x1801af980  lea     rax, [rsp+308h+var_2C8]
0x1801af985  mov     [rsp+308h+var_2D8], rax
0x1801af98a  mov     [rsp+308h+var_2E0], 4
0x1801af992  mov     [rsp+308h+var_2E8], 1Fh
0x1801af99a  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801af9a1  mov     r8, [rsi+40h]
0x1801af9a5  mov     rdx, [rsi+50h]
0x1801af9a9  mov     rcx, r15
0x1801af9ac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801af9b1  mov     edi, eax
0x1801af9b3  test    eax, eax
0x1801af9b5  jz      short loc_1801AF9BC
0x1801af9b7  jmp     loc_1801B0245
0x1801af9bc  lea     rax, [rsp+308h+var_2C8]
0x1801af9c1  mov     [rsp+308h+var_298], rax
0x1801af9c6  mov     r12d, 1
0x1801af9cc  mov     [rsp+308h+var_290], r12b
0x1801af9d1  mov     r14, [rsp+308h+var_2C8]
0x1801af9d6  test    r14, r14
0x1801af9d9  jnz     short loc_1801AF9E3
0x1801af9db  mov     edi, r12d
0x1801af9de  jmp     loc_1801B0245
0x1801af9e3  mov     r9d, 1Fh; unsigned int
0x1801af9e9  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801af9f0  mov     rdx, rsi; struct _MI_Instance *
0x1801af9f3  mov     rcx, r14; this
0x1801af9f6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801af9fb  lea     r8, [rsi+60h]; void *
0x1801af9ff  cmp     [r8+8], r12b
0x1801afa03  jnz     short loc_1801AFA38
0x1801afa05  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801afa0c  mov     rcx, r14; this
0x1801afa0f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afa14  mov     edi, eax
0x1801afa16  test    eax, eax
0x1801afa18  jz      short loc_1801AFA38
0x1801afa1a  mov     rcx, [rsp+308h+var_2C8]
0x1801afa1f  test    rcx, rcx
0x1801afa22  jz      short loc_1801AFA33
0x1801afa24  mov     rax, [rcx]
0x1801afa27  mov     edx, r12d
0x1801afa2a  mov     rax, [rax]
0x1801afa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afa32  nop
0x1801afa33  jmp     loc_1801B0245
0x1801afa38  lea     r8, [rsi+70h]; void *
0x1801afa3c  cmp     [r8+8], r12b
0x1801afa40  jnz     short loc_1801AFA75
0x1801afa42  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801afa49  mov     rcx, r14; this
0x1801afa4c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afa51  mov     edi, eax
0x1801afa53  test    eax, eax
0x1801afa55  jz      short loc_1801AFA75
0x1801afa57  mov     rcx, [rsp+308h+var_2C8]
0x1801afa5c  test    rcx, rcx
0x1801afa5f  jz      short loc_1801AFA70
0x1801afa61  mov     rax, [rcx]
0x1801afa64  mov     edx, r12d
0x1801afa67  mov     rax, [rax]
0x1801afa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afa6f  nop
0x1801afa70  jmp     loc_1801B0245
0x1801afa75  lea     r8, [rsi+80h]; void *
0x1801afa7c  cmp     [r8+8], r12b
0x1801afa80  jnz     short loc_1801AFAB5
0x1801afa82  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801afa89  mov     rcx, r14; this
0x1801afa8c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afa91  mov     edi, eax
0x1801afa93  test    eax, eax
0x1801afa95  jz      short loc_1801AFAB5
0x1801afa97  mov     rcx, [rsp+308h+var_2C8]
0x1801afa9c  test    rcx, rcx
0x1801afa9f  jz      short loc_1801AFAB0
0x1801afaa1  mov     rax, [rcx]
0x1801afaa4  mov     edx, r12d
0x1801afaa7  mov     rax, [rax]
0x1801afaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afaaf  nop
0x1801afab0  jmp     loc_1801B0245
0x1801afab5  lea     r8, [rsi+90h]; void *
0x1801afabc  cmp     [r8+8], r12b
0x1801afac0  jnz     short loc_1801AFAF5
0x1801afac2  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801afac9  mov     rcx, r14; this
0x1801afacc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afad1  mov     edi, eax
0x1801afad3  test    eax, eax
0x1801afad5  jz      short loc_1801AFAF5
0x1801afad7  mov     rcx, [rsp+308h+var_2C8]
0x1801afadc  test    rcx, rcx
0x1801afadf  jz      short loc_1801AFAF0
0x1801afae1  mov     rax, [rcx]
0x1801afae4  mov     edx, r12d
0x1801afae7  mov     rax, [rax]
0x1801afaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afaef  nop
0x1801afaf0  jmp     loc_1801B0245
0x1801afaf5  lea     r8, [rsi+0A0h]; void *
0x1801afafc  cmp     [r8+8], r12b
0x1801afb00  jnz     short loc_1801AFB35
0x1801afb02  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801afb09  mov     rcx, r14; this
0x1801afb0c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afb11  mov     edi, eax
0x1801afb13  test    eax, eax
0x1801afb15  jz      short loc_1801AFB35
0x1801afb17  mov     rcx, [rsp+308h+var_2C8]
0x1801afb1c  test    rcx, rcx
0x1801afb1f  jz      short loc_1801AFB30
0x1801afb21  mov     rax, [rcx]
0x1801afb24  mov     edx, r12d
0x1801afb27  mov     rax, [rax]
0x1801afb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afb2f  nop
0x1801afb30  jmp     loc_1801B0245
0x1801afb35  lea     r8, [rsi+0B0h]; void *
0x1801afb3c  cmp     [r8+8], r12b
0x1801afb40  jnz     short loc_1801AFB75
0x1801afb42  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801afb49  mov     rcx, r14; this
0x1801afb4c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afb51  mov     edi, eax
0x1801afb53  test    eax, eax
0x1801afb55  jz      short loc_1801AFB75
0x1801afb57  mov     rcx, [rsp+308h+var_2C8]
0x1801afb5c  test    rcx, rcx
0x1801afb5f  jz      short loc_1801AFB70
0x1801afb61  mov     rax, [rcx]
0x1801afb64  mov     edx, r12d
0x1801afb67  mov     rax, [rax]
0x1801afb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afb6f  nop
0x1801afb70  jmp     loc_1801B0245
0x1801afb75  lea     r8, [rsi+0C0h]; void *
0x1801afb7c  cmp     [r8+8], r12b
0x1801afb80  jnz     short loc_1801AFBB5
0x1801afb82  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801afb89  mov     rcx, r14; this
0x1801afb8c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afb91  mov     edi, eax
0x1801afb93  test    eax, eax
0x1801afb95  jz      short loc_1801AFBB5
0x1801afb97  mov     rcx, [rsp+308h+var_2C8]
0x1801afb9c  test    rcx, rcx
0x1801afb9f  jz      short loc_1801AFBB0
0x1801afba1  mov     rax, [rcx]
0x1801afba4  mov     edx, r12d
0x1801afba7  mov     rax, [rax]
0x1801afbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afbaf  nop
0x1801afbb0  jmp     loc_1801B0245
0x1801afbb5  lea     r8, [rsi+0D0h]; void *
0x1801afbbc  cmp     [r8+8], r12b
0x1801afbc0  jnz     short loc_1801AFBF5
0x1801afbc2  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801afbc9  mov     rcx, r14; this
0x1801afbcc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afbd1  mov     edi, eax
0x1801afbd3  test    eax, eax
0x1801afbd5  jz      short loc_1801AFBF5
0x1801afbd7  mov     rcx, [rsp+308h+var_2C8]
0x1801afbdc  test    rcx, rcx
0x1801afbdf  jz      short loc_1801AFBF0
0x1801afbe1  mov     rax, [rcx]
0x1801afbe4  mov     edx, r12d
0x1801afbe7  mov     rax, [rax]
0x1801afbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afbef  nop
0x1801afbf0  jmp     loc_1801B0245
0x1801afbf5  lea     r8, [rsi+0E0h]; void *
0x1801afbfc  cmp     [r8+8], r12b
0x1801afc00  jnz     short loc_1801AFC35
0x1801afc02  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801afc09  mov     rcx, r14; this
0x1801afc0c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc11  mov     edi, eax
0x1801afc13  test    eax, eax
0x1801afc15  jz      short loc_1801AFC35
0x1801afc17  mov     rcx, [rsp+308h+var_2C8]
0x1801afc1c  test    rcx, rcx
0x1801afc1f  jz      short loc_1801AFC30
0x1801afc21  mov     rax, [rcx]
0x1801afc24  mov     edx, r12d
0x1801afc27  mov     rax, [rax]
0x1801afc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc2f  nop
0x1801afc30  jmp     loc_1801B0245
0x1801afc35  lea     r8, [rsi+0F0h]; void *
0x1801afc3c  cmp     [r8+8], r12b
0x1801afc40  jnz     short loc_1801AFC75
0x1801afc42  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801afc49  mov     rcx, r14; this
0x1801afc4c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc51  mov     edi, eax
0x1801afc53  test    eax, eax
0x1801afc55  jz      short loc_1801AFC75
0x1801afc57  mov     rcx, [rsp+308h+var_2C8]
0x1801afc5c  test    rcx, rcx
0x1801afc5f  jz      short loc_1801AFC70
0x1801afc61  mov     rax, [rcx]
0x1801afc64  mov     edx, r12d
0x1801afc67  mov     rax, [rax]
0x1801afc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc6f  nop
0x1801afc70  jmp     loc_1801B0245
0x1801afc75  lea     r8, [rsi+100h]; void *
0x1801afc7c  cmp     [r8+8], r12b
0x1801afc80  jnz     short loc_1801AFCB5
0x1801afc82  lea     rdx, aCreatetoken; "CreateToken"
0x1801afc89  mov     rcx, r14; this
0x1801afc8c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afc91  mov     edi, eax
0x1801afc93  test    eax, eax
0x1801afc95  jz      short loc_1801AFCB5
0x1801afc97  mov     rcx, [rsp+308h+var_2C8]
0x1801afc9c  test    rcx, rcx
0x1801afc9f  jz      short loc_1801AFCB0
0x1801afca1  mov     rax, [rcx]
0x1801afca4  mov     edx, r12d
0x1801afca7  mov     rax, [rax]
0x1801afcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afcaf  nop
0x1801afcb0  jmp     loc_1801B0245
0x1801afcb5  lea     r8, [rsi+110h]; void *
0x1801afcbc  cmp     [r8+8], r12b
0x1801afcc0  jnz     short loc_1801AFCF5
0x1801afcc2  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801afcc9  mov     rcx, r14; this
0x1801afccc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801afcd1  mov     edi, eax
0x1801afcd3  test    eax, eax
0x1801afcd5  jz      short loc_1801AFCF5
0x1801afcd7  mov     rcx, [rsp+308h+var_2C8]
0x1801afcdc  test    rcx, rcx
0x1801afcdf  jz      short loc_1801AFCF0
0x1801afce1  mov     rax, [rcx]
  ... truncated ...
```
