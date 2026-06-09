# MDM_Policy_Result01_UserRights02_InvokeModifyInstance

- ea: `0x1801b18b0`
- end: `0x1801b228a`
- name: `MDM_Policy_Result01_UserRights02_InvokeModifyInstance`
- size: `2522`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b2290`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801b18b0`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801b1a47`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b1a84`: `AccessFromNetwork`
- `0x1801b1bc4`: `CreateGlobalObjects`
- `0x1801b1c04`: `CreatePageFile`
- `0x1801b1c44`: `CreatePermanentSharedObjects`
- `0x1801b1c84`: `CreateSymbolicLinks`
- `0x1801b1cc4`: `CreateToken`
- `0x1801b1d44`: `DenyAccessFromNetwork`
- `0x1801b1dc4`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b1e44`: `GenerateSecurityAudits`
- `0x1801b1e84`: `ImpersonateClient`
- `0x1801b1f84`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-80h] BYREF
  char v10; // [rsp+70h] [rbp-58h]
  int v11; // [rsp+78h] [rbp-50h] BYREF
  char v12; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v13[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp-38h] BYREF

  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_Result01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_1803520EF,
      v13,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v9,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    v8 = 0;
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               a1,
                               *(_QWORD *)(a2 + 80),
                               *(_QWORD *)(a2 + 64),
                               &MDM_Policy_Result01_UserRights02_NodeList,
                               31,
                               3,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v9[4] = &v8;
      v10 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          (const struct _MI_Instance *)a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
          0x1Fu);
        if ( *(_BYTE *)(a2 + 104) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"AccessCredentialManagerAsTrustedCaller",
                           (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 120) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessFromNetwork", (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 136) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ActAsPartOfTheOperatingSystem",
                                (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 152) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 168) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"BackupFilesAndDirectories",
                                (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 184) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ChangeSystemTime", (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 200) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 216) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", (void *)(a2 + 208))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 232) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CreatePermanentSharedObjects",
                                (void *)(a2 + 224))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 248) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateSymbolicLinks", (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 264) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", (void *)(a2 + 256))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 280) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", (void *)(a2 + 272))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 296) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyAccessFromNetwork", (void *)(a2 + 288))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 312) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", (void *)(a2 + 304))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 328) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DenyRemoteDesktopServicesLogOn",
                                (void *)(a2 + 320))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 344) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableDelegation", (void *)(a2 + 336))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 360) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"GenerateSecurityAudits", (void *)(a2 + 352))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 376) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ImpersonateClient", (void *)(a2 + 368))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 392) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"IncreaseSchedulingPriority",
                                (void *)(a2 + 384))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 408) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"LoadUnloadDeviceDrivers",
                                (void *)(a2 + 400))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 424) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", (void *)(a2 + 416))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 440) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ManageAuditingAndSecurityLog",
                                (void *)(a2 + 432))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 456) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", (void *)(a2 + 448))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 472) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ModifyFirmwareEnvironment",
                                (void *)(a2 + 464))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 488) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", (void *)(a2 + 480))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 504) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProfileSingleProcess", (void *)(a2 + 496))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 520) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", (void *)(a2 + 512))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 536) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"RestoreFilesAndDirectories",
                                (void *)(a2 + 528))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 552) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", (void *)(a2 + 544))) != MI_RESULT_OK )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180369B48,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801b18b0  mov     r11, rsp
0x1801b18b3  mov     [r11+18h], rsi
0x1801b18b7  push    rdi
0x1801b18b8  push    r14
0x1801b18ba  push    r15
0x1801b18bc  sub     rsp, 0B0h
0x1801b18c3  mov     rax, cs:__security_cookie
0x1801b18ca  xor     rax, rsp
0x1801b18cd  mov     [rsp+0C8h+var_28], rax
0x1801b18d5  mov     rsi, rdx
0x1801b18d8  mov     rdi, rcx
0x1801b18db  mov     [rsp+0C8h+var_50], 0
0x1801b18e3  mov     [rsp+0C8h+var_4C], 0
0x1801b18e8  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b18ef  mov     [r11-80h], rax
0x1801b18f3  lea     rax, [r11-50h]
0x1801b18f7  mov     [r11-78h], rax
0x1801b18fb  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b1902  mov     [r11-70h], rax
0x1801b1906  lea     rcx, [r11-50h]
0x1801b190a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b190f  mov     eax, cs:dword_180380B68
0x1801b1915  cmp     eax, 5
0x1801b1918  jbe     short loc_1801B198B
0x1801b191a  mov     rdx, 200000000000h
0x1801b1924  lea     rcx, dword_180380B68
0x1801b192b  call    _tlgKeywordOn
0x1801b1930  test    al, al
0x1801b1932  jz      short loc_1801B198B
0x1801b1934  cmp     [rsp+0C8h+var_4C], 0
0x1801b1939  jz      short loc_1801B196D
0x1801b193b  cmp     [rsp+0C8h+var_38], 0
0x1801b1943  jnz     short loc_1801B1963
0x1801b1945  cmp     [rsp+0C8h+var_34], 0
0x1801b194d  jnz     short loc_1801B1963
0x1801b194f  cmp     [rsp+0C8h+var_30], 0
0x1801b1957  jnz     short loc_1801B1963
0x1801b1959  cmp     [rsp+0C8h+var_2C], 0
0x1801b1961  jz      short loc_1801B196D
0x1801b1963  lea     r9, [rsp+0C8h+var_38]
0x1801b196b  jmp     short loc_1801B1970
0x1801b196d  xor     r9d, r9d
0x1801b1970  lea     r8, [rsp+0C8h+var_48]
0x1801b1978  lea     rdx, byte_1803520EF
0x1801b197f  lea     rcx, dword_180380B68
0x1801b1986  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b198b  cmp     byte ptr [rsi+48h], 0
0x1801b198f  jz      loc_1801B21F3
0x1801b1995  cmp     byte ptr [rsi+58h], 0
0x1801b1999  jz      loc_1801B21F3
0x1801b199f  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b19a3  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b19a7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801b19ae  lea     rcx, [rsp+0C8h+var_80]; this
0x1801b19b3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b19b8  nop
0x1801b19b9  mov     [rsp+0C8h+var_88], 0
0x1801b19c2  lea     rax, [rsp+0C8h+var_88]
0x1801b19c7  mov     [rsp+0C8h+var_98], rax
0x1801b19cc  mov     [rsp+0C8h+var_A0], 3
0x1801b19d4  mov     [rsp+0C8h+var_A8], 1Fh
0x1801b19dc  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b19e3  mov     r8, [rsi+40h]
0x1801b19e7  mov     rdx, [rsi+50h]
0x1801b19eb  mov     rcx, rdi
0x1801b19ee  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b19f3  mov     edi, eax
0x1801b19f5  test    eax, eax
0x1801b19f7  jz      short loc_1801B19FE
0x1801b19f9  jmp     loc_1801B21F8
0x1801b19fe  lea     rax, [rsp+0C8h+var_88]
0x1801b1a03  mov     [rsp+0C8h+var_60], rax
0x1801b1a08  mov     r15d, 1
0x1801b1a0e  mov     [rsp+0C8h+var_58], r15b
0x1801b1a13  mov     r14, [rsp+0C8h+var_88]
0x1801b1a18  test    r14, r14
0x1801b1a1b  jnz     short loc_1801B1A25
0x1801b1a1d  mov     edi, r15d
0x1801b1a20  jmp     loc_1801B21F8
0x1801b1a25  mov     r9d, 1Fh; unsigned int
0x1801b1a2b  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b1a32  mov     rdx, rsi; struct _MI_Instance *
0x1801b1a35  mov     rcx, r14; this
0x1801b1a38  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b1a3d  lea     r8, [rsi+60h]; void *
0x1801b1a41  cmp     [r8+8], r15b
0x1801b1a45  jnz     short loc_1801B1A7A
0x1801b1a47  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b1a4e  mov     rcx, r14; this
0x1801b1a51  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1a56  mov     edi, eax
0x1801b1a58  test    eax, eax
0x1801b1a5a  jz      short loc_1801B1A7A
0x1801b1a5c  mov     rcx, [rsp+0C8h+var_88]
0x1801b1a61  test    rcx, rcx
0x1801b1a64  jz      short loc_1801B1A75
0x1801b1a66  mov     rax, [rcx]
0x1801b1a69  mov     edx, r15d
0x1801b1a6c  mov     rax, [rax]
0x1801b1a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1a74  nop
0x1801b1a75  jmp     loc_1801B21F8
0x1801b1a7a  lea     r8, [rsi+70h]; void *
0x1801b1a7e  cmp     [r8+8], r15b
0x1801b1a82  jnz     short loc_1801B1AB7
0x1801b1a84  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801b1a8b  mov     rcx, r14; this
0x1801b1a8e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1a93  mov     edi, eax
0x1801b1a95  test    eax, eax
0x1801b1a97  jz      short loc_1801B1AB7
0x1801b1a99  mov     rcx, [rsp+0C8h+var_88]
0x1801b1a9e  test    rcx, rcx
0x1801b1aa1  jz      short loc_1801B1AB2
0x1801b1aa3  mov     rax, [rcx]
0x1801b1aa6  mov     edx, r15d
0x1801b1aa9  mov     rax, [rax]
0x1801b1aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1ab1  nop
0x1801b1ab2  jmp     loc_1801B21F8
0x1801b1ab7  lea     r8, [rsi+80h]; void *
0x1801b1abe  cmp     [r8+8], r15b
0x1801b1ac2  jnz     short loc_1801B1AF7
0x1801b1ac4  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b1acb  mov     rcx, r14; this
0x1801b1ace  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1ad3  mov     edi, eax
0x1801b1ad5  test    eax, eax
0x1801b1ad7  jz      short loc_1801B1AF7
0x1801b1ad9  mov     rcx, [rsp+0C8h+var_88]
0x1801b1ade  test    rcx, rcx
0x1801b1ae1  jz      short loc_1801B1AF2
0x1801b1ae3  mov     rax, [rcx]
0x1801b1ae6  mov     edx, r15d
0x1801b1ae9  mov     rax, [rax]
0x1801b1aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1af1  nop
0x1801b1af2  jmp     loc_1801B21F8
0x1801b1af7  lea     r8, [rsi+90h]; void *
0x1801b1afe  cmp     [r8+8], r15b
0x1801b1b02  jnz     short loc_1801B1B37
0x1801b1b04  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801b1b0b  mov     rcx, r14; this
0x1801b1b0e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1b13  mov     edi, eax
0x1801b1b15  test    eax, eax
0x1801b1b17  jz      short loc_1801B1B37
0x1801b1b19  mov     rcx, [rsp+0C8h+var_88]
0x1801b1b1e  test    rcx, rcx
0x1801b1b21  jz      short loc_1801B1B32
0x1801b1b23  mov     rax, [rcx]
0x1801b1b26  mov     edx, r15d
0x1801b1b29  mov     rax, [rax]
0x1801b1b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1b31  nop
0x1801b1b32  jmp     loc_1801B21F8
0x1801b1b37  lea     r8, [rsi+0A0h]; void *
0x1801b1b3e  cmp     [r8+8], r15b
0x1801b1b42  jnz     short loc_1801B1B77
0x1801b1b44  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b1b4b  mov     rcx, r14; this
0x1801b1b4e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1b53  mov     edi, eax
0x1801b1b55  test    eax, eax
0x1801b1b57  jz      short loc_1801B1B77
0x1801b1b59  mov     rcx, [rsp+0C8h+var_88]
0x1801b1b5e  test    rcx, rcx
0x1801b1b61  jz      short loc_1801B1B72
0x1801b1b63  mov     rax, [rcx]
0x1801b1b66  mov     edx, r15d
0x1801b1b69  mov     rax, [rax]
0x1801b1b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1b71  nop
0x1801b1b72  jmp     loc_1801B21F8
0x1801b1b77  lea     r8, [rsi+0B0h]; void *
0x1801b1b7e  cmp     [r8+8], r15b
0x1801b1b82  jnz     short loc_1801B1BB7
0x1801b1b84  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801b1b8b  mov     rcx, r14; this
0x1801b1b8e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1b93  mov     edi, eax
0x1801b1b95  test    eax, eax
0x1801b1b97  jz      short loc_1801B1BB7
0x1801b1b99  mov     rcx, [rsp+0C8h+var_88]
0x1801b1b9e  test    rcx, rcx
0x1801b1ba1  jz      short loc_1801B1BB2
0x1801b1ba3  mov     rax, [rcx]
0x1801b1ba6  mov     edx, r15d
0x1801b1ba9  mov     rax, [rax]
0x1801b1bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1bb1  nop
0x1801b1bb2  jmp     loc_1801B21F8
0x1801b1bb7  lea     r8, [rsi+0C0h]; void *
0x1801b1bbe  cmp     [r8+8], r15b
0x1801b1bc2  jnz     short loc_1801B1BF7
0x1801b1bc4  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801b1bcb  mov     rcx, r14; this
0x1801b1bce  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1bd3  mov     edi, eax
0x1801b1bd5  test    eax, eax
0x1801b1bd7  jz      short loc_1801B1BF7
0x1801b1bd9  mov     rcx, [rsp+0C8h+var_88]
0x1801b1bde  test    rcx, rcx
0x1801b1be1  jz      short loc_1801B1BF2
0x1801b1be3  mov     rax, [rcx]
0x1801b1be6  mov     edx, r15d
0x1801b1be9  mov     rax, [rax]
0x1801b1bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1bf1  nop
0x1801b1bf2  jmp     loc_1801B21F8
0x1801b1bf7  lea     r8, [rsi+0D0h]; void *
0x1801b1bfe  cmp     [r8+8], r15b
0x1801b1c02  jnz     short loc_1801B1C37
0x1801b1c04  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801b1c0b  mov     rcx, r14; this
0x1801b1c0e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1c13  mov     edi, eax
0x1801b1c15  test    eax, eax
0x1801b1c17  jz      short loc_1801B1C37
0x1801b1c19  mov     rcx, [rsp+0C8h+var_88]
0x1801b1c1e  test    rcx, rcx
0x1801b1c21  jz      short loc_1801B1C32
0x1801b1c23  mov     rax, [rcx]
0x1801b1c26  mov     edx, r15d
0x1801b1c29  mov     rax, [rax]
0x1801b1c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1c31  nop
0x1801b1c32  jmp     loc_1801B21F8
0x1801b1c37  lea     r8, [rsi+0E0h]; void *
0x1801b1c3e  cmp     [r8+8], r15b
0x1801b1c42  jnz     short loc_1801B1C77
0x1801b1c44  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b1c4b  mov     rcx, r14; this
0x1801b1c4e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1c53  mov     edi, eax
0x1801b1c55  test    eax, eax
0x1801b1c57  jz      short loc_1801B1C77
0x1801b1c59  mov     rcx, [rsp+0C8h+var_88]
0x1801b1c5e  test    rcx, rcx
0x1801b1c61  jz      short loc_1801B1C72
0x1801b1c63  mov     rax, [rcx]
0x1801b1c66  mov     edx, r15d
0x1801b1c69  mov     rax, [rax]
0x1801b1c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1c71  nop
0x1801b1c72  jmp     loc_1801B21F8
0x1801b1c77  lea     r8, [rsi+0F0h]; void *
0x1801b1c7e  cmp     [r8+8], r15b
0x1801b1c82  jnz     short loc_1801B1CB7
0x1801b1c84  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801b1c8b  mov     rcx, r14; this
0x1801b1c8e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1c93  mov     edi, eax
0x1801b1c95  test    eax, eax
0x1801b1c97  jz      short loc_1801B1CB7
0x1801b1c99  mov     rcx, [rsp+0C8h+var_88]
0x1801b1c9e  test    rcx, rcx
0x1801b1ca1  jz      short loc_1801B1CB2
0x1801b1ca3  mov     rax, [rcx]
0x1801b1ca6  mov     edx, r15d
0x1801b1ca9  mov     rax, [rax]
0x1801b1cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1cb1  nop
0x1801b1cb2  jmp     loc_1801B21F8
0x1801b1cb7  lea     r8, [rsi+100h]; void *
0x1801b1cbe  cmp     [r8+8], r15b
0x1801b1cc2  jnz     short loc_1801B1CF7
0x1801b1cc4  lea     rdx, aCreatetoken; "CreateToken"
0x1801b1ccb  mov     rcx, r14; this
0x1801b1cce  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1cd3  mov     edi, eax
0x1801b1cd5  test    eax, eax
0x1801b1cd7  jz      short loc_1801B1CF7
0x1801b1cd9  mov     rcx, [rsp+0C8h+var_88]
0x1801b1cde  test    rcx, rcx
0x1801b1ce1  jz      short loc_1801B1CF2
0x1801b1ce3  mov     rax, [rcx]
0x1801b1ce6  mov     edx, r15d
0x1801b1ce9  mov     rax, [rax]
0x1801b1cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1cf1  nop
0x1801b1cf2  jmp     loc_1801B21F8
0x1801b1cf7  lea     r8, [rsi+110h]; void *
0x1801b1cfe  cmp     [r8+8], r15b
0x1801b1d02  jnz     short loc_1801B1D37
0x1801b1d04  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801b1d0b  mov     rcx, r14; this
0x1801b1d0e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1d13  mov     edi, eax
0x1801b1d15  test    eax, eax
0x1801b1d17  jz      short loc_1801B1D37
0x1801b1d19  mov     rcx, [rsp+0C8h+var_88]
0x1801b1d1e  test    rcx, rcx
0x1801b1d21  jz      short loc_1801B1D32
0x1801b1d23  mov     rax, [rcx]
0x1801b1d26  mov     edx, r15d
0x1801b1d29  mov     rax, [rax]
0x1801b1d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1d31  nop
0x1801b1d32  jmp     loc_1801B21F8
  ... truncated ...
```
