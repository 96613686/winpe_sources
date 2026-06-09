# MDM_Policy_Config01_UserRights02_InvokeModifyInstance

- ea: `0x1800fb7fc`
- end: `0x1800fc1d5`
- name: `MDM_Policy_Config01_UserRights02_InvokeModifyInstance`
- size: `2521`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fc1e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1800fb7fc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800fb993`: `AccessCredentialManagerAsTrustedCaller`
- `0x1800fb9d0`: `AccessFromNetwork`
- `0x1800fbb10`: `CreateGlobalObjects`
- `0x1800fbb50`: `CreatePageFile`
- `0x1800fbb90`: `CreatePermanentSharedObjects`
- `0x1800fbbd0`: `CreateSymbolicLinks`
- `0x1800fbc10`: `CreateToken`
- `0x1800fbc90`: `DenyAccessFromNetwork`
- `0x1800fbd10`: `DenyRemoteDesktopServicesLogOn`
- `0x1800fbd90`: `GenerateSecurityAudits`
- `0x1800fbdd0`: `ImpersonateClient`
- `0x1800fbed0`: `ManageAuditingAndSecurityLog`
- `0x1800fb847`: `MDM_Policy_Config01_UserRights02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_UserRights02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  unsigned int inserted; // edi
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_UserRights02_NodeList,
                   0x1Fu,
                   3,
                   &v11);
      if ( !inserted )
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
                             (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 120) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AccessFromNetwork", (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 136) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ActAsPartOfTheOperatingSystem",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 152) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowLocalLogOn", (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 168) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"BackupFilesAndDirectories",
                                  (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 184) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ChangeSystemTime", (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 200) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateGlobalObjects", (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 216) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreatePageFile", (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 232) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"CreatePermanentSharedObjects",
                                  (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 248) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateSymbolicLinks", (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 264) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"CreateToken", (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 280) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DebugPrograms", (LONG *)(a2 + 272))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 296) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DenyAccessFromNetwork",
                                  (LONG *)(a2 + 288))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 312) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"DenyLocalLogOn", (LONG *)(a2 + 304))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 328) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DenyRemoteDesktopServicesLogOn",
                                  (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 344) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"EnableDelegation", (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 360) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"GenerateSecurityAudits",
                                  (LONG *)(a2 + 352))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 376) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ImpersonateClient", (LONG *)(a2 + 368))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 392) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"IncreaseSchedulingPriority",
                                  (LONG *)(a2 + 384))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 408) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"LoadUnloadDeviceDrivers",
                                  (LONG *)(a2 + 400))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 424) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockMemory", (LONG *)(a2 + 416))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 440) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ManageAuditingAndSecurityLog",
                                  (LONG *)(a2 + 432))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 456) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ManageVolume", (LONG *)(a2 + 448))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 472) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ModifyFirmwareEnvironment",
                                  (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 488) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ModifyObjectLabel", (LONG *)(a2 + 480))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 504) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProfileSingleProcess", (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 520) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"RemoteShutdown", (LONG *)(a2 + 512))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 536) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"RestoreFilesAndDirectories",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 552) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"TakeOwnership", (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
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
          inserted = 1;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = 1;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = 1;
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x1800fb7fc  mov     r11, rsp
0x1800fb7ff  mov     [r11+18h], rsi
0x1800fb803  push    rdi
0x1800fb804  push    r14
0x1800fb806  push    r15
0x1800fb808  sub     rsp, 0B0h
0x1800fb80f  mov     rax, cs:__security_cookie
0x1800fb816  xor     rax, rsp
0x1800fb819  mov     [rsp+0C8h+var_28], rax
0x1800fb821  mov     rsi, rdx
0x1800fb824  mov     rdi, rcx
0x1800fb827  mov     [rsp+0C8h+var_50], 0
0x1800fb82f  mov     [rsp+0C8h+var_4C], 0
0x1800fb834  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800fb83b  mov     [r11-80h], rax
0x1800fb83f  lea     rax, [r11-50h]
0x1800fb843  mov     [r11-78h], rax
0x1800fb847  lea     rax, aMdmPolicyConfi_97; "MDM_Policy_Config01_UserRights02"
0x1800fb84e  mov     [r11-70h], rax
0x1800fb852  lea     rcx, [r11-50h]
0x1800fb856  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800fb85b  mov     eax, cs:dword_180380B68
0x1800fb861  cmp     eax, 5
0x1800fb864  jbe     short loc_1800FB8D7
0x1800fb866  mov     rdx, 200000000000h
0x1800fb870  lea     rcx, dword_180380B68
0x1800fb877  call    _tlgKeywordOn
0x1800fb87c  test    al, al
0x1800fb87e  jz      short loc_1800FB8D7
0x1800fb880  cmp     [rsp+0C8h+var_4C], 0
0x1800fb885  jz      short loc_1800FB8B9
0x1800fb887  cmp     [rsp+0C8h+var_38], 0
0x1800fb88f  jnz     short loc_1800FB8AF
0x1800fb891  cmp     [rsp+0C8h+var_34], 0
0x1800fb899  jnz     short loc_1800FB8AF
0x1800fb89b  cmp     [rsp+0C8h+var_30], 0
0x1800fb8a3  jnz     short loc_1800FB8AF
0x1800fb8a5  cmp     [rsp+0C8h+var_2C], 0
0x1800fb8ad  jz      short loc_1800FB8B9
0x1800fb8af  lea     r9, [rsp+0C8h+var_38]
0x1800fb8b7  jmp     short loc_1800FB8BC
0x1800fb8b9  xor     r9d, r9d
0x1800fb8bc  lea     r8, [rsp+0C8h+var_48]
0x1800fb8c4  lea     rdx, dword_18035D6A4
0x1800fb8cb  lea     rcx, dword_180380B68
0x1800fb8d2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800fb8d7  cmp     byte ptr [rsi+48h], 0
0x1800fb8db  jz      loc_1800FC13F
0x1800fb8e1  cmp     byte ptr [rsi+58h], 0
0x1800fb8e5  jz      loc_1800FC13F
0x1800fb8eb  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800fb8ef  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800fb8f3  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800fb8fa  lea     rcx, [rsp+0C8h+var_80]; this
0x1800fb8ff  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800fb904  nop
0x1800fb905  mov     [rsp+0C8h+var_88], 0
0x1800fb90e  lea     rax, [rsp+0C8h+var_88]
0x1800fb913  mov     [rsp+0C8h+var_98], rax
0x1800fb918  mov     [rsp+0C8h+var_A0], 3
0x1800fb920  mov     [rsp+0C8h+var_A8], 1Fh
0x1800fb928  lea     r9, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_UserRights02_NodeList
0x1800fb92f  mov     r8, [rsi+40h]
0x1800fb933  mov     rdx, [rsi+50h]
0x1800fb937  mov     rcx, rdi
0x1800fb93a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800fb93f  mov     edi, eax
0x1800fb941  test    eax, eax
0x1800fb943  jz      short loc_1800FB94A
0x1800fb945  jmp     loc_1800FC144
0x1800fb94a  lea     rax, [rsp+0C8h+var_88]
0x1800fb94f  mov     [rsp+0C8h+var_60], rax
0x1800fb954  mov     r15d, 1
0x1800fb95a  mov     [rsp+0C8h+var_58], r15b
0x1800fb95f  mov     r14, [rsp+0C8h+var_88]
0x1800fb964  test    r14, r14
0x1800fb967  jnz     short loc_1800FB971
0x1800fb969  mov     edi, r15d
0x1800fb96c  jmp     loc_1800FC144
0x1800fb971  mov     r9d, 1Fh; unsigned int
0x1800fb977  lea     r8, ?MDM_Policy_Config01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800fb97e  mov     rdx, rsi; struct _MI_Instance *
0x1800fb981  mov     rcx, r14; this
0x1800fb984  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800fb989  lea     r8, [rsi+60h]; void *
0x1800fb98d  cmp     [r8+8], r15b
0x1800fb991  jnz     short loc_1800FB9C6
0x1800fb993  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1800fb99a  mov     rcx, r14; this
0x1800fb99d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb9a2  mov     edi, eax
0x1800fb9a4  test    eax, eax
0x1800fb9a6  jz      short loc_1800FB9C6
0x1800fb9a8  mov     rcx, [rsp+0C8h+var_88]
0x1800fb9ad  test    rcx, rcx
0x1800fb9b0  jz      short loc_1800FB9C1
0x1800fb9b2  mov     rax, [rcx]
0x1800fb9b5  mov     edx, r15d
0x1800fb9b8  mov     rax, [rax]
0x1800fb9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb9c0  nop
0x1800fb9c1  jmp     loc_1800FC144
0x1800fb9c6  lea     r8, [rsi+70h]; void *
0x1800fb9ca  cmp     [r8+8], r15b
0x1800fb9ce  jnz     short loc_1800FBA03
0x1800fb9d0  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1800fb9d7  mov     rcx, r14; this
0x1800fb9da  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fb9df  mov     edi, eax
0x1800fb9e1  test    eax, eax
0x1800fb9e3  jz      short loc_1800FBA03
0x1800fb9e5  mov     rcx, [rsp+0C8h+var_88]
0x1800fb9ea  test    rcx, rcx
0x1800fb9ed  jz      short loc_1800FB9FE
0x1800fb9ef  mov     rax, [rcx]
0x1800fb9f2  mov     edx, r15d
0x1800fb9f5  mov     rax, [rax]
0x1800fb9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb9fd  nop
0x1800fb9fe  jmp     loc_1800FC144
0x1800fba03  lea     r8, [rsi+80h]; void *
0x1800fba0a  cmp     [r8+8], r15b
0x1800fba0e  jnz     short loc_1800FBA43
0x1800fba10  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1800fba17  mov     rcx, r14; this
0x1800fba1a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fba1f  mov     edi, eax
0x1800fba21  test    eax, eax
0x1800fba23  jz      short loc_1800FBA43
0x1800fba25  mov     rcx, [rsp+0C8h+var_88]
0x1800fba2a  test    rcx, rcx
0x1800fba2d  jz      short loc_1800FBA3E
0x1800fba2f  mov     rax, [rcx]
0x1800fba32  mov     edx, r15d
0x1800fba35  mov     rax, [rax]
0x1800fba38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fba3d  nop
0x1800fba3e  jmp     loc_1800FC144
0x1800fba43  lea     r8, [rsi+90h]; void *
0x1800fba4a  cmp     [r8+8], r15b
0x1800fba4e  jnz     short loc_1800FBA83
0x1800fba50  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1800fba57  mov     rcx, r14; this
0x1800fba5a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fba5f  mov     edi, eax
0x1800fba61  test    eax, eax
0x1800fba63  jz      short loc_1800FBA83
0x1800fba65  mov     rcx, [rsp+0C8h+var_88]
0x1800fba6a  test    rcx, rcx
0x1800fba6d  jz      short loc_1800FBA7E
0x1800fba6f  mov     rax, [rcx]
0x1800fba72  mov     edx, r15d
0x1800fba75  mov     rax, [rax]
0x1800fba78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fba7d  nop
0x1800fba7e  jmp     loc_1800FC144
0x1800fba83  lea     r8, [rsi+0A0h]; void *
0x1800fba8a  cmp     [r8+8], r15b
0x1800fba8e  jnz     short loc_1800FBAC3
0x1800fba90  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1800fba97  mov     rcx, r14; this
0x1800fba9a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fba9f  mov     edi, eax
0x1800fbaa1  test    eax, eax
0x1800fbaa3  jz      short loc_1800FBAC3
0x1800fbaa5  mov     rcx, [rsp+0C8h+var_88]
0x1800fbaaa  test    rcx, rcx
0x1800fbaad  jz      short loc_1800FBABE
0x1800fbaaf  mov     rax, [rcx]
0x1800fbab2  mov     edx, r15d
0x1800fbab5  mov     rax, [rax]
0x1800fbab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbabd  nop
0x1800fbabe  jmp     loc_1800FC144
0x1800fbac3  lea     r8, [rsi+0B0h]; void *
0x1800fbaca  cmp     [r8+8], r15b
0x1800fbace  jnz     short loc_1800FBB03
0x1800fbad0  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1800fbad7  mov     rcx, r14; this
0x1800fbada  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbadf  mov     edi, eax
0x1800fbae1  test    eax, eax
0x1800fbae3  jz      short loc_1800FBB03
0x1800fbae5  mov     rcx, [rsp+0C8h+var_88]
0x1800fbaea  test    rcx, rcx
0x1800fbaed  jz      short loc_1800FBAFE
0x1800fbaef  mov     rax, [rcx]
0x1800fbaf2  mov     edx, r15d
0x1800fbaf5  mov     rax, [rax]
0x1800fbaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbafd  nop
0x1800fbafe  jmp     loc_1800FC144
0x1800fbb03  lea     r8, [rsi+0C0h]; void *
0x1800fbb0a  cmp     [r8+8], r15b
0x1800fbb0e  jnz     short loc_1800FBB43
0x1800fbb10  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1800fbb17  mov     rcx, r14; this
0x1800fbb1a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbb1f  mov     edi, eax
0x1800fbb21  test    eax, eax
0x1800fbb23  jz      short loc_1800FBB43
0x1800fbb25  mov     rcx, [rsp+0C8h+var_88]
0x1800fbb2a  test    rcx, rcx
0x1800fbb2d  jz      short loc_1800FBB3E
0x1800fbb2f  mov     rax, [rcx]
0x1800fbb32  mov     edx, r15d
0x1800fbb35  mov     rax, [rax]
0x1800fbb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbb3d  nop
0x1800fbb3e  jmp     loc_1800FC144
0x1800fbb43  lea     r8, [rsi+0D0h]; void *
0x1800fbb4a  cmp     [r8+8], r15b
0x1800fbb4e  jnz     short loc_1800FBB83
0x1800fbb50  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1800fbb57  mov     rcx, r14; this
0x1800fbb5a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbb5f  mov     edi, eax
0x1800fbb61  test    eax, eax
0x1800fbb63  jz      short loc_1800FBB83
0x1800fbb65  mov     rcx, [rsp+0C8h+var_88]
0x1800fbb6a  test    rcx, rcx
0x1800fbb6d  jz      short loc_1800FBB7E
0x1800fbb6f  mov     rax, [rcx]
0x1800fbb72  mov     edx, r15d
0x1800fbb75  mov     rax, [rax]
0x1800fbb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbb7d  nop
0x1800fbb7e  jmp     loc_1800FC144
0x1800fbb83  lea     r8, [rsi+0E0h]; void *
0x1800fbb8a  cmp     [r8+8], r15b
0x1800fbb8e  jnz     short loc_1800FBBC3
0x1800fbb90  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1800fbb97  mov     rcx, r14; this
0x1800fbb9a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbb9f  mov     edi, eax
0x1800fbba1  test    eax, eax
0x1800fbba3  jz      short loc_1800FBBC3
0x1800fbba5  mov     rcx, [rsp+0C8h+var_88]
0x1800fbbaa  test    rcx, rcx
0x1800fbbad  jz      short loc_1800FBBBE
0x1800fbbaf  mov     rax, [rcx]
0x1800fbbb2  mov     edx, r15d
0x1800fbbb5  mov     rax, [rax]
0x1800fbbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbbbd  nop
0x1800fbbbe  jmp     loc_1800FC144
0x1800fbbc3  lea     r8, [rsi+0F0h]; void *
0x1800fbbca  cmp     [r8+8], r15b
0x1800fbbce  jnz     short loc_1800FBC03
0x1800fbbd0  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1800fbbd7  mov     rcx, r14; this
0x1800fbbda  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbbdf  mov     edi, eax
0x1800fbbe1  test    eax, eax
0x1800fbbe3  jz      short loc_1800FBC03
0x1800fbbe5  mov     rcx, [rsp+0C8h+var_88]
0x1800fbbea  test    rcx, rcx
0x1800fbbed  jz      short loc_1800FBBFE
0x1800fbbef  mov     rax, [rcx]
0x1800fbbf2  mov     edx, r15d
0x1800fbbf5  mov     rax, [rax]
0x1800fbbf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbbfd  nop
0x1800fbbfe  jmp     loc_1800FC144
0x1800fbc03  lea     r8, [rsi+100h]; void *
0x1800fbc0a  cmp     [r8+8], r15b
0x1800fbc0e  jnz     short loc_1800FBC43
0x1800fbc10  lea     rdx, aCreatetoken; "CreateToken"
0x1800fbc17  mov     rcx, r14; this
0x1800fbc1a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbc1f  mov     edi, eax
0x1800fbc21  test    eax, eax
0x1800fbc23  jz      short loc_1800FBC43
0x1800fbc25  mov     rcx, [rsp+0C8h+var_88]
0x1800fbc2a  test    rcx, rcx
0x1800fbc2d  jz      short loc_1800FBC3E
0x1800fbc2f  mov     rax, [rcx]
0x1800fbc32  mov     edx, r15d
0x1800fbc35  mov     rax, [rax]
0x1800fbc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc3d  nop
0x1800fbc3e  jmp     loc_1800FC144
0x1800fbc43  lea     r8, [rsi+110h]; void *
0x1800fbc4a  cmp     [r8+8], r15b
0x1800fbc4e  jnz     short loc_1800FBC83
0x1800fbc50  lea     rdx, aDebugprograms; "DebugPrograms"
0x1800fbc57  mov     rcx, r14; this
0x1800fbc5a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800fbc5f  mov     edi, eax
0x1800fbc61  test    eax, eax
0x1800fbc63  jz      short loc_1800FBC83
0x1800fbc65  mov     rcx, [rsp+0C8h+var_88]
0x1800fbc6a  test    rcx, rcx
0x1800fbc6d  jz      short loc_1800FBC7E
0x1800fbc6f  mov     rax, [rcx]
0x1800fbc72  mov     edx, r15d
0x1800fbc75  mov     rax, [rax]
0x1800fbc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc7d  nop
0x1800fbc7e  jmp     loc_1800FC144
  ... truncated ...
```
