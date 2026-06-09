# MDM_Policy_Result01_UserRights02_InvokeModifyInstance

- ea: `0x1801b1a9c`
- end: `0x1801b2475`
- name: `MDM_Policy_Result01_UserRights02_InvokeModifyInstance`
- size: `2521`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b2480`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1801b1a9c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801b1c33`: `AccessCredentialManagerAsTrustedCaller`
- `0x1801b1c70`: `AccessFromNetwork`
- `0x1801b1db0`: `CreateGlobalObjects`
- `0x1801b1df0`: `CreatePageFile`
- `0x1801b1e30`: `CreatePermanentSharedObjects`
- `0x1801b1e70`: `CreateSymbolicLinks`
- `0x1801b1eb0`: `CreateToken`
- `0x1801b1f30`: `DenyAccessFromNetwork`
- `0x1801b1fb0`: `DenyRemoteDesktopServicesLogOn`
- `0x1801b2030`: `GenerateSecurityAudits`
- `0x1801b2070`: `ImpersonateClient`
- `0x1801b2170`: `ManageAuditingAndSecurityLog`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_UserRights02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_UserRights02_NodeList,
                 0x1Fu,
                 3,
                 &v8);
    if ( !inserted )
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
                           (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 120) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AccessFromNetwork", (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 136) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ActAsPartOfTheOperatingSystem",
                                (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 152) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowLocalLogOn", (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 168) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"BackupFilesAndDirectories",
                                (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 184) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ChangeSystemTime", (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 200) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateGlobalObjects", (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 216) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreatePageFile", (LONG *)(a2 + 208))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 232) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"CreatePermanentSharedObjects",
                                (LONG *)(a2 + 224))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 248) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateSymbolicLinks", (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 264) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"CreateToken", (LONG *)(a2 + 256))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 280) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DebugPrograms", (LONG *)(a2 + 272))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 296) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyAccessFromNetwork", (LONG *)(a2 + 288))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 312) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DenyLocalLogOn", (LONG *)(a2 + 304))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 328) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DenyRemoteDesktopServicesLogOn",
                                (LONG *)(a2 + 320))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 344) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableDelegation", (LONG *)(a2 + 336))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 360) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"GenerateSecurityAudits", (LONG *)(a2 + 352))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 376) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ImpersonateClient", (LONG *)(a2 + 368))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 392) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"IncreaseSchedulingPriority",
                                (LONG *)(a2 + 384))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 408) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"LoadUnloadDeviceDrivers",
                                (LONG *)(a2 + 400))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 424) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockMemory", (LONG *)(a2 + 416))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 440) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ManageAuditingAndSecurityLog",
                                (LONG *)(a2 + 432))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 456) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ManageVolume", (LONG *)(a2 + 448))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 472) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ModifyFirmwareEnvironment",
                                (LONG *)(a2 + 464))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 488) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ModifyObjectLabel", (LONG *)(a2 + 480))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 504) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProfileSingleProcess", (LONG *)(a2 + 496))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 520) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemoteShutdown", (LONG *)(a2 + 512))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 536) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"RestoreFilesAndDirectories",
                                (LONG *)(a2 + 528))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 552) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"TakeOwnership", (LONG *)(a2 + 544))) != 0 )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180369B48,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x1801b1a9c  mov     r11, rsp
0x1801b1a9f  mov     [r11+18h], rsi
0x1801b1aa3  push    rdi
0x1801b1aa4  push    r14
0x1801b1aa6  push    r15
0x1801b1aa8  sub     rsp, 0B0h
0x1801b1aaf  mov     rax, cs:__security_cookie
0x1801b1ab6  xor     rax, rsp
0x1801b1ab9  mov     [rsp+0C8h+var_28], rax
0x1801b1ac1  mov     rsi, rdx
0x1801b1ac4  mov     rdi, rcx
0x1801b1ac7  mov     [rsp+0C8h+var_50], 0
0x1801b1acf  mov     [rsp+0C8h+var_4C], 0
0x1801b1ad4  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b1adb  mov     [r11-80h], rax
0x1801b1adf  lea     rax, [r11-50h]
0x1801b1ae3  mov     [r11-78h], rax
0x1801b1ae7  lea     rax, aMdmPolicyResul_164; "MDM_Policy_Result01_UserRights02"
0x1801b1aee  mov     [r11-70h], rax
0x1801b1af2  lea     rcx, [r11-50h]
0x1801b1af6  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b1afb  mov     eax, cs:dword_180380B68
0x1801b1b01  cmp     eax, 5
0x1801b1b04  jbe     short loc_1801B1B77
0x1801b1b06  mov     rdx, 200000000000h
0x1801b1b10  lea     rcx, dword_180380B68
0x1801b1b17  call    _tlgKeywordOn
0x1801b1b1c  test    al, al
0x1801b1b1e  jz      short loc_1801B1B77
0x1801b1b20  cmp     [rsp+0C8h+var_4C], 0
0x1801b1b25  jz      short loc_1801B1B59
0x1801b1b27  cmp     [rsp+0C8h+var_38], 0
0x1801b1b2f  jnz     short loc_1801B1B4F
0x1801b1b31  cmp     [rsp+0C8h+var_34], 0
0x1801b1b39  jnz     short loc_1801B1B4F
0x1801b1b3b  cmp     [rsp+0C8h+var_30], 0
0x1801b1b43  jnz     short loc_1801B1B4F
0x1801b1b45  cmp     [rsp+0C8h+var_2C], 0
0x1801b1b4d  jz      short loc_1801B1B59
0x1801b1b4f  lea     r9, [rsp+0C8h+var_38]
0x1801b1b57  jmp     short loc_1801B1B5C
0x1801b1b59  xor     r9d, r9d
0x1801b1b5c  lea     r8, [rsp+0C8h+var_48]
0x1801b1b64  lea     rdx, byte_1803520EF
0x1801b1b6b  lea     rcx, dword_180380B68
0x1801b1b72  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b1b77  cmp     byte ptr [rsi+48h], 0
0x1801b1b7b  jz      loc_1801B23DF
0x1801b1b81  cmp     byte ptr [rsi+58h], 0
0x1801b1b85  jz      loc_1801B23DF
0x1801b1b8b  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801b1b8f  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801b1b93  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801b1b9a  lea     rcx, [rsp+0C8h+var_80]; this
0x1801b1b9f  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801b1ba4  nop
0x1801b1ba5  mov     [rsp+0C8h+var_88], 0
0x1801b1bae  lea     rax, [rsp+0C8h+var_88]
0x1801b1bb3  mov     [rsp+0C8h+var_98], rax
0x1801b1bb8  mov     [rsp+0C8h+var_A0], 3
0x1801b1bc0  mov     [rsp+0C8h+var_A8], 1Fh
0x1801b1bc8  lea     r9, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_UserRights02_NodeList
0x1801b1bcf  mov     r8, [rsi+40h]
0x1801b1bd3  mov     rdx, [rsi+50h]
0x1801b1bd7  mov     rcx, rdi
0x1801b1bda  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b1bdf  mov     edi, eax
0x1801b1be1  test    eax, eax
0x1801b1be3  jz      short loc_1801B1BEA
0x1801b1be5  jmp     loc_1801B23E4
0x1801b1bea  lea     rax, [rsp+0C8h+var_88]
0x1801b1bef  mov     [rsp+0C8h+var_60], rax
0x1801b1bf4  mov     r15d, 1
0x1801b1bfa  mov     [rsp+0C8h+var_58], r15b
0x1801b1bff  mov     r14, [rsp+0C8h+var_88]
0x1801b1c04  test    r14, r14
0x1801b1c07  jnz     short loc_1801B1C11
0x1801b1c09  mov     edi, r15d
0x1801b1c0c  jmp     loc_1801B23E4
0x1801b1c11  mov     r9d, 1Fh; unsigned int
0x1801b1c17  lea     r8, ?MDM_Policy_Result01_UserRights02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801b1c1e  mov     rdx, rsi; struct _MI_Instance *
0x1801b1c21  mov     rcx, r14; this
0x1801b1c24  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801b1c29  lea     r8, [rsi+60h]; void *
0x1801b1c2d  cmp     [r8+8], r15b
0x1801b1c31  jnz     short loc_1801B1C66
0x1801b1c33  lea     rdx, aAccesscredenti; "AccessCredentialManagerAsTrustedCaller"
0x1801b1c3a  mov     rcx, r14; this
0x1801b1c3d  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1c42  mov     edi, eax
0x1801b1c44  test    eax, eax
0x1801b1c46  jz      short loc_1801B1C66
0x1801b1c48  mov     rcx, [rsp+0C8h+var_88]
0x1801b1c4d  test    rcx, rcx
0x1801b1c50  jz      short loc_1801B1C61
0x1801b1c52  mov     rax, [rcx]
0x1801b1c55  mov     edx, r15d
0x1801b1c58  mov     rax, [rax]
0x1801b1c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1c60  nop
0x1801b1c61  jmp     loc_1801B23E4
0x1801b1c66  lea     r8, [rsi+70h]; void *
0x1801b1c6a  cmp     [r8+8], r15b
0x1801b1c6e  jnz     short loc_1801B1CA3
0x1801b1c70  lea     rdx, aAccessfromnetw; "AccessFromNetwork"
0x1801b1c77  mov     rcx, r14; this
0x1801b1c7a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1c7f  mov     edi, eax
0x1801b1c81  test    eax, eax
0x1801b1c83  jz      short loc_1801B1CA3
0x1801b1c85  mov     rcx, [rsp+0C8h+var_88]
0x1801b1c8a  test    rcx, rcx
0x1801b1c8d  jz      short loc_1801B1C9E
0x1801b1c8f  mov     rax, [rcx]
0x1801b1c92  mov     edx, r15d
0x1801b1c95  mov     rax, [rax]
0x1801b1c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1c9d  nop
0x1801b1c9e  jmp     loc_1801B23E4
0x1801b1ca3  lea     r8, [rsi+80h]; void *
0x1801b1caa  cmp     [r8+8], r15b
0x1801b1cae  jnz     short loc_1801B1CE3
0x1801b1cb0  lea     rdx, aActaspartofthe; "ActAsPartOfTheOperatingSystem"
0x1801b1cb7  mov     rcx, r14; this
0x1801b1cba  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1cbf  mov     edi, eax
0x1801b1cc1  test    eax, eax
0x1801b1cc3  jz      short loc_1801B1CE3
0x1801b1cc5  mov     rcx, [rsp+0C8h+var_88]
0x1801b1cca  test    rcx, rcx
0x1801b1ccd  jz      short loc_1801B1CDE
0x1801b1ccf  mov     rax, [rcx]
0x1801b1cd2  mov     edx, r15d
0x1801b1cd5  mov     rax, [rax]
0x1801b1cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1cdd  nop
0x1801b1cde  jmp     loc_1801B23E4
0x1801b1ce3  lea     r8, [rsi+90h]; void *
0x1801b1cea  cmp     [r8+8], r15b
0x1801b1cee  jnz     short loc_1801B1D23
0x1801b1cf0  lea     rdx, aAllowlocallogo; "AllowLocalLogOn"
0x1801b1cf7  mov     rcx, r14; this
0x1801b1cfa  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1cff  mov     edi, eax
0x1801b1d01  test    eax, eax
0x1801b1d03  jz      short loc_1801B1D23
0x1801b1d05  mov     rcx, [rsp+0C8h+var_88]
0x1801b1d0a  test    rcx, rcx
0x1801b1d0d  jz      short loc_1801B1D1E
0x1801b1d0f  mov     rax, [rcx]
0x1801b1d12  mov     edx, r15d
0x1801b1d15  mov     rax, [rax]
0x1801b1d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1d1d  nop
0x1801b1d1e  jmp     loc_1801B23E4
0x1801b1d23  lea     r8, [rsi+0A0h]; void *
0x1801b1d2a  cmp     [r8+8], r15b
0x1801b1d2e  jnz     short loc_1801B1D63
0x1801b1d30  lea     rdx, aBackupfilesand; "BackupFilesAndDirectories"
0x1801b1d37  mov     rcx, r14; this
0x1801b1d3a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1d3f  mov     edi, eax
0x1801b1d41  test    eax, eax
0x1801b1d43  jz      short loc_1801B1D63
0x1801b1d45  mov     rcx, [rsp+0C8h+var_88]
0x1801b1d4a  test    rcx, rcx
0x1801b1d4d  jz      short loc_1801B1D5E
0x1801b1d4f  mov     rax, [rcx]
0x1801b1d52  mov     edx, r15d
0x1801b1d55  mov     rax, [rax]
0x1801b1d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1d5d  nop
0x1801b1d5e  jmp     loc_1801B23E4
0x1801b1d63  lea     r8, [rsi+0B0h]; void *
0x1801b1d6a  cmp     [r8+8], r15b
0x1801b1d6e  jnz     short loc_1801B1DA3
0x1801b1d70  lea     rdx, aChangesystemti; "ChangeSystemTime"
0x1801b1d77  mov     rcx, r14; this
0x1801b1d7a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1d7f  mov     edi, eax
0x1801b1d81  test    eax, eax
0x1801b1d83  jz      short loc_1801B1DA3
0x1801b1d85  mov     rcx, [rsp+0C8h+var_88]
0x1801b1d8a  test    rcx, rcx
0x1801b1d8d  jz      short loc_1801B1D9E
0x1801b1d8f  mov     rax, [rcx]
0x1801b1d92  mov     edx, r15d
0x1801b1d95  mov     rax, [rax]
0x1801b1d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1d9d  nop
0x1801b1d9e  jmp     loc_1801B23E4
0x1801b1da3  lea     r8, [rsi+0C0h]; void *
0x1801b1daa  cmp     [r8+8], r15b
0x1801b1dae  jnz     short loc_1801B1DE3
0x1801b1db0  lea     rdx, aCreateglobalob; "CreateGlobalObjects"
0x1801b1db7  mov     rcx, r14; this
0x1801b1dba  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1dbf  mov     edi, eax
0x1801b1dc1  test    eax, eax
0x1801b1dc3  jz      short loc_1801B1DE3
0x1801b1dc5  mov     rcx, [rsp+0C8h+var_88]
0x1801b1dca  test    rcx, rcx
0x1801b1dcd  jz      short loc_1801B1DDE
0x1801b1dcf  mov     rax, [rcx]
0x1801b1dd2  mov     edx, r15d
0x1801b1dd5  mov     rax, [rax]
0x1801b1dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1ddd  nop
0x1801b1dde  jmp     loc_1801B23E4
0x1801b1de3  lea     r8, [rsi+0D0h]; void *
0x1801b1dea  cmp     [r8+8], r15b
0x1801b1dee  jnz     short loc_1801B1E23
0x1801b1df0  lea     rdx, aCreatepagefile; "CreatePageFile"
0x1801b1df7  mov     rcx, r14; this
0x1801b1dfa  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1dff  mov     edi, eax
0x1801b1e01  test    eax, eax
0x1801b1e03  jz      short loc_1801B1E23
0x1801b1e05  mov     rcx, [rsp+0C8h+var_88]
0x1801b1e0a  test    rcx, rcx
0x1801b1e0d  jz      short loc_1801B1E1E
0x1801b1e0f  mov     rax, [rcx]
0x1801b1e12  mov     edx, r15d
0x1801b1e15  mov     rax, [rax]
0x1801b1e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1e1d  nop
0x1801b1e1e  jmp     loc_1801B23E4
0x1801b1e23  lea     r8, [rsi+0E0h]; void *
0x1801b1e2a  cmp     [r8+8], r15b
0x1801b1e2e  jnz     short loc_1801B1E63
0x1801b1e30  lea     rdx, aCreatepermanen; "CreatePermanentSharedObjects"
0x1801b1e37  mov     rcx, r14; this
0x1801b1e3a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1e3f  mov     edi, eax
0x1801b1e41  test    eax, eax
0x1801b1e43  jz      short loc_1801B1E63
0x1801b1e45  mov     rcx, [rsp+0C8h+var_88]
0x1801b1e4a  test    rcx, rcx
0x1801b1e4d  jz      short loc_1801B1E5E
0x1801b1e4f  mov     rax, [rcx]
0x1801b1e52  mov     edx, r15d
0x1801b1e55  mov     rax, [rax]
0x1801b1e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1e5d  nop
0x1801b1e5e  jmp     loc_1801B23E4
0x1801b1e63  lea     r8, [rsi+0F0h]; void *
0x1801b1e6a  cmp     [r8+8], r15b
0x1801b1e6e  jnz     short loc_1801B1EA3
0x1801b1e70  lea     rdx, aCreatesymbolic; "CreateSymbolicLinks"
0x1801b1e77  mov     rcx, r14; this
0x1801b1e7a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1e7f  mov     edi, eax
0x1801b1e81  test    eax, eax
0x1801b1e83  jz      short loc_1801B1EA3
0x1801b1e85  mov     rcx, [rsp+0C8h+var_88]
0x1801b1e8a  test    rcx, rcx
0x1801b1e8d  jz      short loc_1801B1E9E
0x1801b1e8f  mov     rax, [rcx]
0x1801b1e92  mov     edx, r15d
0x1801b1e95  mov     rax, [rax]
0x1801b1e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1e9d  nop
0x1801b1e9e  jmp     loc_1801B23E4
0x1801b1ea3  lea     r8, [rsi+100h]; void *
0x1801b1eaa  cmp     [r8+8], r15b
0x1801b1eae  jnz     short loc_1801B1EE3
0x1801b1eb0  lea     rdx, aCreatetoken; "CreateToken"
0x1801b1eb7  mov     rcx, r14; this
0x1801b1eba  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1ebf  mov     edi, eax
0x1801b1ec1  test    eax, eax
0x1801b1ec3  jz      short loc_1801B1EE3
0x1801b1ec5  mov     rcx, [rsp+0C8h+var_88]
0x1801b1eca  test    rcx, rcx
0x1801b1ecd  jz      short loc_1801B1EDE
0x1801b1ecf  mov     rax, [rcx]
0x1801b1ed2  mov     edx, r15d
0x1801b1ed5  mov     rax, [rax]
0x1801b1ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1edd  nop
0x1801b1ede  jmp     loc_1801B23E4
0x1801b1ee3  lea     r8, [rsi+110h]; void *
0x1801b1eea  cmp     [r8+8], r15b
0x1801b1eee  jnz     short loc_1801B1F23
0x1801b1ef0  lea     rdx, aDebugprograms; "DebugPrograms"
0x1801b1ef7  mov     rcx, r14; this
0x1801b1efa  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801b1eff  mov     edi, eax
0x1801b1f01  test    eax, eax
0x1801b1f03  jz      short loc_1801B1F23
0x1801b1f05  mov     rcx, [rsp+0C8h+var_88]
0x1801b1f0a  test    rcx, rcx
0x1801b1f0d  jz      short loc_1801B1F1E
0x1801b1f0f  mov     rax, [rcx]
0x1801b1f12  mov     edx, r15d
0x1801b1f15  mov     rax, [rax]
0x1801b1f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1f1d  nop
0x1801b1f1e  jmp     loc_1801B23E4
  ... truncated ...
```
