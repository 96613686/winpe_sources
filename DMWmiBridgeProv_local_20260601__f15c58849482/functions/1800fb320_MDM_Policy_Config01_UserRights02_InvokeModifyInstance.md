# MDM_Policy_Config01_UserRights02_InvokeModifyInstance

- ea: `0x1800fb320`
- end: `0x1800fbcfa`
- name: `MDM_Policy_Config01_UserRights02_InvokeModifyInstance`
- size: `2522`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fbd00`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1800fb320`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800fb4b7`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fb4f4`: `AccessFromNetwork`
- `0x1800fb634`: `CreateGlobalObjects`
- `0x1800fb674`: `CreatePageFile`
- `0x1800fb6b4`: `CreatePermanentSharedObjects`
- `0x1800fb6f4`: `CreateSymbolicLinks`
- `0x1800fb734`: `CreateToken`
- `0x1800fb7b4`: `DenyAccessFromNetwork`
- `0x1800fb834`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fb8b4`: `GenerateSecurityAudits`
- `0x1800fb8f4`: `ImpersonateClient`
- `0x1800fb9f4`: `ManageAuditingAndSecurityLog`
- `0x1800fb36b`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v7; // r14
  const char *v9; // rax
  int v10; // eax
  WmiRequestHandler *v11; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-80h] BYREF
  const exception *v13[2]; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h] BYREF
  char v16; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-38h] BYREF

  v15 = 0;
  v16 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v15;
  v12[2] = "MDM_Policy_Config01_UserRights02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18035D6A4,
      v17,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v12,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    try
    {
      v11 = 0;
      inserted = (unsigned int)CreateRequestHandlerInstance(
                                 a1,
                                 *(_QWORD *)(a2 + 80),
                                 *(_QWORD *)(a2 + 64),
                                 &MDM_Policy_Config01_UserRights02_NodeList,
                                 31,
                                 3,
                                 &v11);
      if ( inserted == MI_RESULT_OK )
      {
        v13[1] = (const exception *)&v11;
        v14 = 1;
        v7 = v11;
        if ( v11 )
        {
          WmiRequestHandler::SetRequestMIInstance(
            v11,
            (const struct _MI_Instance *)a2,
            (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
            0x1Fu);
          if ( *(_BYTE *)(a2 + 104) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                             v7,
                             L"AccessCredentialManagerAsTrustedCaller",
                             (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 120) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AccessFromNetwork", (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 136) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ActAsPartOfTheOperatingSystem",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 152) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowLocalLogOn", (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 168) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"BackupFilesAndDirectories",
                                  (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 184) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ChangeSystemTime", (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 200) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateGlobalObjects", (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 216) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreatePageFile", (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 232) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"CreatePermanentSharedObjects",
                                  (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 248) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateSymbolicLinks", (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 264) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateToken", (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 280) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DebugPrograms", (void *)(a2 + 272))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 296) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DenyAccessFromNetwork",
                                  (void *)(a2 + 288))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 312) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DenyLocalLogOn", (void *)(a2 + 304))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 328) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DenyRemoteDesktopServicesLogOn",
                                  (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 344) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"EnableDelegation", (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 360) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"GenerateSecurityAudits",
                                  (void *)(a2 + 352))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 376) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ImpersonateClient", (void *)(a2 + 368))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 392) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IncreaseSchedulingPriority",
                                  (void *)(a2 + 384))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 408) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"LoadUnloadDeviceDrivers",
                                  (void *)(a2 + 400))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 424) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockMemory", (void *)(a2 + 416))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 440) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ManageAuditingAndSecurityLog",
                                  (void *)(a2 + 432))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 456) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ManageVolume", (void *)(a2 + 448))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 472) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ModifyFirmwareEnvironment",
                                  (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 488) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ModifyObjectLabel", (void *)(a2 + 480))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 504) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProfileSingleProcess", (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 520) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"RemoteShutdown", (void *)(a2 + 512))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 536) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RestoreFilesAndDirectories",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 552) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"TakeOwnership", (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
              v5 = v11;
              if ( inserted )
              {
                if ( v11 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
              else if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
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
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "ModifyInstanceEnd", inserted);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180364DC8,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800fb320  mov     r11, rsp
0x1800fb323  mov     [r11+18h], rsi
0x1800fb327  push    rdi
0x1800fb328  push    r14
0x1800fb32a  push    r15
0x1800fb32c  sub     rsp, 0B0h
0x1800fb333  mov     rax, cs:__security_cookie
0x1800fb33a  xor     rax, rsp
0x1800fb33d  mov     [rsp+0C8h+var_28], rax
0x1800fb345  mov     rsi, rdx
0x1800fb348  mov     rdi, rcx
0x1800fb34b  mov     [rsp+0C8h+var_50], 0
0x1800fb353  mov     [rsp+0C8h+var_4C], 0
0x1800fb358  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800fb35f  mov     [r11-80h], rax
0x1800fb363  lea     rax, [r11-50h]
0x1800fb367  mov     [r11-78h], rax
0x1800fb36b  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800fb372  mov     [r11-70h], rax
0x1800fb376  lea     rcx, [r11-50h]
0x1800fb37a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800fb37f  mov     eax, cs:dword_180380B68
0x1800fb385  cmp     eax, 5
0x1800fb388  jbe     short loc_1800FB3FB
0x1800fb38a  mov     rdx, 200000000000h
0x1800fb394  lea     rcx, dword_180380B68
0x1800fb39b  call    _tlgKeywordOn
0x1800fb3a0  test    al, al
0x1800fb3a2  jz      short loc_1800FB3FB
0x1800fb3a4  cmp     [rsp+0C8h+var_4C], 0
0x1800fb3a9  jz      short loc_1800FB3DD
0x1800fb3ab  cmp     [rsp+0C8h+var_38], 0
0x1800fb3b3  jnz     short loc_1800FB3D3
0x1800fb3b5  cmp     [rsp+0C8h+var_34], 0
0x1800fb3bd  jnz     short loc_1800FB3D3
0x1800fb3bf  cmp     [rsp+0C8h+var_30], 0
0x1800fb3c7  jnz     short loc_1800FB3D3
0x1800fb3c9  cmp     [rsp+0C8h+var_2C], 0
0x1800fb3d1  jz      short loc_1800FB3DD
0x1800fb3d3  lea     r9, [rsp+0C8h+var_38]
0x1800fb3db  jmp     short loc_1800FB3E0
0x1800fb3dd  xor     r9d, r9d
0x1800fb3e0  lea     r8, [rsp+0C8h+var_48]
0x1800fb3e8  lea     rdx, dword_18035D6A4
0x1800fb3ef  lea     rcx, dword_180380B68
0x1800fb3f6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fb3fb  cmp     byte ptr [rsi+48h], 0
0x1800fb3ff  jz      loc_1800FBC63
0x1800fb405  cmp     byte ptr [rsi+58h], 0
0x1800fb409  jz      loc_1800FBC63
0x1800fb40f  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800fb413  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800fb417  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800fb41e  lea     rcx, [rsp+0C8h+var_80]; this
0x1800fb423  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800fb428  nop
0x1800fb429  mov     [rsp+0C8h+var_88], 0
0x1800fb432  lea     rax, [rsp+0C8h+var_88]
0x1800fb437  mov     [rsp+0C8h+var_98], rax
0x1800fb43c  mov     [rsp+0C8h+var_A0], 3
0x1800fb444  mov     [rsp+0C8h+var_A8], 1Fh
0x1800fb44c  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fb453  mov     r8, [rsi+40h]
0x1800fb457  mov     rdx, [rsi+50h]
0x1800fb45b  mov     rcx, rdi
0x1800fb45e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fb463  mov     edi, eax
0x1800fb465  test    eax, eax
0x1800fb467  jz      short loc_1800FB46E
0x1800fb469  jmp     loc_1800FBC68
0x1800fb46e  lea     rax, [rsp+0C8h+var_88]
0x1800fb473  mov     [rsp+0C8h+var_60], rax
0x1800fb478  mov     r15d, 1
0x1800fb47e  mov     [rsp+0C8h+var_58], r15b
0x1800fb483  mov     r14, [rsp+0C8h+var_88]
0x1800fb488  test    r14, r14
0x1800fb48b  jnz     short loc_1800FB495
0x1800fb48d  mov     edi, r15d
0x1800fb490  jmp     loc_1800FBC68
0x1800fb495  mov     r9d, 1Fh; unsigned int
0x1800fb49b  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800fb4a2  mov     rdx, rsi; struct _MI_Instance *
0x1800fb4a5  mov     rcx, r14; this
0x1800fb4a8  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800fb4ad  lea     r8, [rsi+60h]; void *
0x1800fb4b1  cmp     [r8+8], r15b
0x1800fb4b5  jnz     short loc_1800FB4EA
0x1800fb4b7  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800fb4be  mov     rcx, r14; this
0x1800fb4c1  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb4c6  mov     edi, eax
0x1800fb4c8  test    eax, eax
0x1800fb4ca  jz      short loc_1800FB4EA
0x1800fb4cc  mov     rcx, [rsp+0C8h+var_88]
0x1800fb4d1  test    rcx, rcx
0x1800fb4d4  jz      short loc_1800FB4E5
0x1800fb4d6  mov     rax, [rcx]
0x1800fb4d9  mov     edx, r15d
0x1800fb4dc  mov     rax, [rax]
0x1800fb4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb4e4  nop
0x1800fb4e5  jmp     loc_1800FBC68
0x1800fb4ea  lea     r8, [rsi+70h]; void *
0x1800fb4ee  cmp     [r8+8], r15b
0x1800fb4f2  jnz     short loc_1800FB527
0x1800fb4f4  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800fb4fb  mov     rcx, r14; this
0x1800fb4fe  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb503  mov     edi, eax
0x1800fb505  test    eax, eax
0x1800fb507  jz      short loc_1800FB527
0x1800fb509  mov     rcx, [rsp+0C8h+var_88]
0x1800fb50e  test    rcx, rcx
0x1800fb511  jz      short loc_1800FB522
0x1800fb513  mov     rax, [rcx]
0x1800fb516  mov     edx, r15d
0x1800fb519  mov     rax, [rax]
0x1800fb51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb521  nop
0x1800fb522  jmp     loc_1800FBC68
0x1800fb527  lea     r8, [rsi+80h]; void *
0x1800fb52e  cmp     [r8+8], r15b
0x1800fb532  jnz     short loc_1800FB567
0x1800fb534  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fb53b  mov     rcx, r14; this
0x1800fb53e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb543  mov     edi, eax
0x1800fb545  test    eax, eax
0x1800fb547  jz      short loc_1800FB567
0x1800fb549  mov     rcx, [rsp+0C8h+var_88]
0x1800fb54e  test    rcx, rcx
0x1800fb551  jz      short loc_1800FB562
0x1800fb553  mov     rax, [rcx]
0x1800fb556  mov     edx, r15d
0x1800fb559  mov     rax, [rax]
0x1800fb55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb561  nop
0x1800fb562  jmp     loc_1800FBC68
0x1800fb567  lea     r8, [rsi+90h]; void *
0x1800fb56e  cmp     [r8+8], r15b
0x1800fb572  jnz     short loc_1800FB5A7
0x1800fb574  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800fb57b  mov     rcx, r14; this
0x1800fb57e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb583  mov     edi, eax
0x1800fb585  test    eax, eax
0x1800fb587  jz      short loc_1800FB5A7
0x1800fb589  mov     rcx, [rsp+0C8h+var_88]
0x1800fb58e  test    rcx, rcx
0x1800fb591  jz      short loc_1800FB5A2
0x1800fb593  mov     rax, [rcx]
0x1800fb596  mov     edx, r15d
0x1800fb599  mov     rax, [rax]
0x1800fb59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb5a1  nop
0x1800fb5a2  jmp     loc_1800FBC68
0x1800fb5a7  lea     r8, [rsi+0A0h]; void *
0x1800fb5ae  cmp     [r8+8], r15b
0x1800fb5b2  jnz     short loc_1800FB5E7
0x1800fb5b4  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fb5bb  mov     rcx, r14; this
0x1800fb5be  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb5c3  mov     edi, eax
0x1800fb5c5  test    eax, eax
0x1800fb5c7  jz      short loc_1800FB5E7
0x1800fb5c9  mov     rcx, [rsp+0C8h+var_88]
0x1800fb5ce  test    rcx, rcx
0x1800fb5d1  jz      short loc_1800FB5E2
0x1800fb5d3  mov     rax, [rcx]
0x1800fb5d6  mov     edx, r15d
0x1800fb5d9  mov     rax, [rax]
0x1800fb5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb5e1  nop
0x1800fb5e2  jmp     loc_1800FBC68
0x1800fb5e7  lea     r8, [rsi+0B0h]; void *
0x1800fb5ee  cmp     [r8+8], r15b
0x1800fb5f2  jnz     short loc_1800FB627
0x1800fb5f4  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800fb5fb  mov     rcx, r14; this
0x1800fb5fe  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb603  mov     edi, eax
0x1800fb605  test    eax, eax
0x1800fb607  jz      short loc_1800FB627
0x1800fb609  mov     rcx, [rsp+0C8h+var_88]
0x1800fb60e  test    rcx, rcx
0x1800fb611  jz      short loc_1800FB622
0x1800fb613  mov     rax, [rcx]
0x1800fb616  mov     edx, r15d
0x1800fb619  mov     rax, [rax]
0x1800fb61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb621  nop
0x1800fb622  jmp     loc_1800FBC68
0x1800fb627  lea     r8, [rsi+0C0h]; void *
0x1800fb62e  cmp     [r8+8], r15b
0x1800fb632  jnz     short loc_1800FB667
0x1800fb634  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800fb63b  mov     rcx, r14; this
0x1800fb63e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb643  mov     edi, eax
0x1800fb645  test    eax, eax
0x1800fb647  jz      short loc_1800FB667
0x1800fb649  mov     rcx, [rsp+0C8h+var_88]
0x1800fb64e  test    rcx, rcx
0x1800fb651  jz      short loc_1800FB662
0x1800fb653  mov     rax, [rcx]
0x1800fb656  mov     edx, r15d
0x1800fb659  mov     rax, [rax]
0x1800fb65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb661  nop
0x1800fb662  jmp     loc_1800FBC68
0x1800fb667  lea     r8, [rsi+0D0h]; void *
0x1800fb66e  cmp     [r8+8], r15b
0x1800fb672  jnz     short loc_1800FB6A7
0x1800fb674  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800fb67b  mov     rcx, r14; this
0x1800fb67e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb683  mov     edi, eax
0x1800fb685  test    eax, eax
0x1800fb687  jz      short loc_1800FB6A7
0x1800fb689  mov     rcx, [rsp+0C8h+var_88]
0x1800fb68e  test    rcx, rcx
0x1800fb691  jz      short loc_1800FB6A2
0x1800fb693  mov     rax, [rcx]
0x1800fb696  mov     edx, r15d
0x1800fb699  mov     rax, [rax]
0x1800fb69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb6a1  nop
0x1800fb6a2  jmp     loc_1800FBC68
0x1800fb6a7  lea     r8, [rsi+0E0h]; void *
0x1800fb6ae  cmp     [r8+8], r15b
0x1800fb6b2  jnz     short loc_1800FB6E7
0x1800fb6b4  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fb6bb  mov     rcx, r14; this
0x1800fb6be  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb6c3  mov     edi, eax
0x1800fb6c5  test    eax, eax
0x1800fb6c7  jz      short loc_1800FB6E7
0x1800fb6c9  mov     rcx, [rsp+0C8h+var_88]
0x1800fb6ce  test    rcx, rcx
0x1800fb6d1  jz      short loc_1800FB6E2
0x1800fb6d3  mov     rax, [rcx]
0x1800fb6d6  mov     edx, r15d
0x1800fb6d9  mov     rax, [rax]
0x1800fb6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb6e1  nop
0x1800fb6e2  jmp     loc_1800FBC68
0x1800fb6e7  lea     r8, [rsi+0F0h]; void *
0x1800fb6ee  cmp     [r8+8], r15b
0x1800fb6f2  jnz     short loc_1800FB727
0x1800fb6f4  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800fb6fb  mov     rcx, r14; this
0x1800fb6fe  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb703  mov     edi, eax
0x1800fb705  test    eax, eax
0x1800fb707  jz      short loc_1800FB727
0x1800fb709  mov     rcx, [rsp+0C8h+var_88]
0x1800fb70e  test    rcx, rcx
0x1800fb711  jz      short loc_1800FB722
0x1800fb713  mov     rax, [rcx]
0x1800fb716  mov     edx, r15d
0x1800fb719  mov     rax, [rax]
0x1800fb71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb721  nop
0x1800fb722  jmp     loc_1800FBC68
0x1800fb727  lea     r8, [rsi+100h]; void *
0x1800fb72e  cmp     [r8+8], r15b
0x1800fb732  jnz     short loc_1800FB767
0x1800fb734  lea     rdx, aCreatetoken; "CreateToken"
0x1800fb73b  mov     rcx, r14; this
0x1800fb73e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb743  mov     edi, eax
0x1800fb745  test    eax, eax
0x1800fb747  jz      short loc_1800FB767
0x1800fb749  mov     rcx, [rsp+0C8h+var_88]
0x1800fb74e  test    rcx, rcx
0x1800fb751  jz      short loc_1800FB762
0x1800fb753  mov     rax, [rcx]
0x1800fb756  mov     edx, r15d
0x1800fb759  mov     rax, [rax]
0x1800fb75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb761  nop
0x1800fb762  jmp     loc_1800FBC68
0x1800fb767  lea     r8, [rsi+110h]; void *
0x1800fb76e  cmp     [r8+8], r15b
0x1800fb772  jnz     short loc_1800FB7A7
0x1800fb774  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800fb77b  mov     rcx, r14; this
0x1800fb77e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb783  mov     edi, eax
0x1800fb785  test    eax, eax
0x1800fb787  jz      short loc_1800FB7A7
0x1800fb789  mov     rcx, [rsp+0C8h+var_88]
0x1800fb78e  test    rcx, rcx
0x1800fb791  jz      short loc_1800FB7A2
0x1800fb793  mov     rax, [rcx]
0x1800fb796  mov     edx, r15d
0x1800fb799  mov     rax, [rax]
0x1800fb79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb7a1  nop
0x1800fb7a2  jmp     loc_1800FBC68
  ... truncated ...
```
