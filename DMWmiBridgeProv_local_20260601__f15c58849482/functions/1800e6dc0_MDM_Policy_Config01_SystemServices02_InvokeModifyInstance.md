# MDM_Policy_Config01_SystemServices02_InvokeModifyInstance

- ea: `0x1800e6dc0`
- end: `0x1800e75d4`
- name: `MDM_Policy_Config01_SystemServices02_InvokeModifyInstance`
- size: `2068`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e75e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1800e6dc0`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800e6f57`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e6f94`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e6fd1`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e700e`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e704e`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e708e`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e70ce`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e710e`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e714e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e718e`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e71ce`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e720e`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e724e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e728e`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e72ce`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e730e`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e734e`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e738e`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e73ce`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e740e`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e744e`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e748e`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e6e0b`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v12[2] = "MDM_Policy_Config01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180356434,
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
                                 &MDM_Policy_Config01_SystemServices02_NodeList,
                                 24,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
            0x18u);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                             v7,
                             L"ConfigureComputerBrowserServiceStartupMode",
                             (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureHomeGroupListenerServiceStartupMode",
                                  (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureHomeGroupProviderServiceStartupMode",
                                  (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureIISAdminServiceStartupMode",
                                  (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureInfraredMonitorServiceStartupMode",
                                  (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureInternetConnectionSharingServiceStartupMode",
                                  (void *)(a2 + 136))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureLxssManagerServiceStartupMode",
                                  (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureMicrosoftFTPServiceStartupMode",
                                  (void *)(a2 + 152))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                  (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                  (void *)(a2 + 168))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSimpleTCPIPServicesStartupMode",
                                  (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                  (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSSDPDiscoveryServiceStartupMode",
                                  (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureUPnPDeviceHostServiceStartupMode",
                                  (void *)(a2 + 200))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWebManagementServiceStartupMode",
                                  (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                  (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                  (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                  (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                  (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                  (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                  (void *)(a2 + 264))) != MI_RESULT_OK )
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
      &byte_18036000F,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800e6dc0  mov     r11, rsp
0x1800e6dc3  mov     [r11+18h], rsi
0x1800e6dc7  push    rdi
0x1800e6dc8  push    r14
0x1800e6dca  push    r15
0x1800e6dcc  sub     rsp, 0B0h
0x1800e6dd3  mov     rax, cs:__security_cookie
0x1800e6dda  xor     rax, rsp
0x1800e6ddd  mov     [rsp+0C8h+var_28], rax
0x1800e6de5  mov     rsi, rdx
0x1800e6de8  mov     rdi, rcx
0x1800e6deb  mov     [rsp+0C8h+var_50], 0
0x1800e6df3  mov     [rsp+0C8h+var_4C], 0
0x1800e6df8  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e6dff  mov     [r11-80h], rax
0x1800e6e03  lea     rax, [r11-50h]
0x1800e6e07  mov     [r11-78h], rax
0x1800e6e0b  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e6e12  mov     [r11-70h], rax
0x1800e6e16  lea     rcx, [r11-50h]
0x1800e6e1a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e6e1f  mov     eax, cs:dword_180380B68
0x1800e6e25  cmp     eax, 5
0x1800e6e28  jbe     short loc_1800E6E9B
0x1800e6e2a  mov     rdx, 200000000000h
0x1800e6e34  lea     rcx, dword_180380B68
0x1800e6e3b  call    _tlgKeywordOn
0x1800e6e40  test    al, al
0x1800e6e42  jz      short loc_1800E6E9B
0x1800e6e44  cmp     [rsp+0C8h+var_4C], 0
0x1800e6e49  jz      short loc_1800E6E7D
0x1800e6e4b  cmp     [rsp+0C8h+var_38], 0
0x1800e6e53  jnz     short loc_1800E6E73
0x1800e6e55  cmp     [rsp+0C8h+var_34], 0
0x1800e6e5d  jnz     short loc_1800E6E73
0x1800e6e5f  cmp     [rsp+0C8h+var_30], 0
0x1800e6e67  jnz     short loc_1800E6E73
0x1800e6e69  cmp     [rsp+0C8h+var_2C], 0
0x1800e6e71  jz      short loc_1800E6E7D
0x1800e6e73  lea     r9, [rsp+0C8h+var_38]
0x1800e6e7b  jmp     short loc_1800E6E80
0x1800e6e7d  xor     r9d, r9d
0x1800e6e80  lea     r8, [rsp+0C8h+var_48]
0x1800e6e88  lea     rdx, dword_180356434
0x1800e6e8f  lea     rcx, dword_180380B68
0x1800e6e96  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e6e9b  cmp     byte ptr [rsi+48h], 0
0x1800e6e9f  jz      loc_1800E753D
0x1800e6ea5  cmp     byte ptr [rsi+58h], 0
0x1800e6ea9  jz      loc_1800E753D
0x1800e6eaf  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e6eb3  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e6eb7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800e6ebe  lea     rcx, [rsp+0C8h+var_80]; this
0x1800e6ec3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e6ec8  nop
0x1800e6ec9  mov     [rsp+0C8h+var_88], 0
0x1800e6ed2  lea     rax, [rsp+0C8h+var_88]
0x1800e6ed7  mov     [rsp+0C8h+var_98], rax
0x1800e6edc  mov     [rsp+0C8h+var_A0], 3
0x1800e6ee4  mov     [rsp+0C8h+var_A8], 18h
0x1800e6eec  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e6ef3  mov     r8, [rsi+40h]
0x1800e6ef7  mov     rdx, [rsi+50h]
0x1800e6efb  mov     rcx, rdi
0x1800e6efe  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e6f03  mov     edi, eax
0x1800e6f05  test    eax, eax
0x1800e6f07  jz      short loc_1800E6F0E
0x1800e6f09  jmp     loc_1800E7542
0x1800e6f0e  lea     rax, [rsp+0C8h+var_88]
0x1800e6f13  mov     [rsp+0C8h+var_60], rax
0x1800e6f18  mov     r15d, 1
0x1800e6f1e  mov     [rsp+0C8h+var_58], r15b
0x1800e6f23  mov     r14, [rsp+0C8h+var_88]
0x1800e6f28  test    r14, r14
0x1800e6f2b  jnz     short loc_1800E6F35
0x1800e6f2d  mov     edi, r15d
0x1800e6f30  jmp     loc_1800E7542
0x1800e6f35  mov     r9d, 18h; unsigned int
0x1800e6f3b  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e6f42  mov     rdx, rsi; struct _MI_Instance *
0x1800e6f45  mov     rcx, r14; this
0x1800e6f48  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e6f4d  lea     r8, [rsi+60h]; void *
0x1800e6f51  cmp     [r8+4], r15b
0x1800e6f55  jnz     short loc_1800E6F8A
0x1800e6f57  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e6f5e  mov     rcx, r14; this
0x1800e6f61  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e6f66  mov     edi, eax
0x1800e6f68  test    eax, eax
0x1800e6f6a  jz      short loc_1800E6F8A
0x1800e6f6c  mov     rcx, [rsp+0C8h+var_88]
0x1800e6f71  test    rcx, rcx
0x1800e6f74  jz      short loc_1800E6F85
0x1800e6f76  mov     rax, [rcx]
0x1800e6f79  mov     edx, r15d
0x1800e6f7c  mov     rax, [rax]
0x1800e6f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6f84  nop
0x1800e6f85  jmp     loc_1800E7542
0x1800e6f8a  lea     r8, [rsi+68h]; void *
0x1800e6f8e  cmp     [r8+4], r15b
0x1800e6f92  jnz     short loc_1800E6FC7
0x1800e6f94  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e6f9b  mov     rcx, r14; this
0x1800e6f9e  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e6fa3  mov     edi, eax
0x1800e6fa5  test    eax, eax
0x1800e6fa7  jz      short loc_1800E6FC7
0x1800e6fa9  mov     rcx, [rsp+0C8h+var_88]
0x1800e6fae  test    rcx, rcx
0x1800e6fb1  jz      short loc_1800E6FC2
0x1800e6fb3  mov     rax, [rcx]
0x1800e6fb6  mov     edx, r15d
0x1800e6fb9  mov     rax, [rax]
0x1800e6fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6fc1  nop
0x1800e6fc2  jmp     loc_1800E7542
0x1800e6fc7  lea     r8, [rsi+70h]; void *
0x1800e6fcb  cmp     [r8+4], r15b
0x1800e6fcf  jnz     short loc_1800E7004
0x1800e6fd1  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e6fd8  mov     rcx, r14; this
0x1800e6fdb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e6fe0  mov     edi, eax
0x1800e6fe2  test    eax, eax
0x1800e6fe4  jz      short loc_1800E7004
0x1800e6fe6  mov     rcx, [rsp+0C8h+var_88]
0x1800e6feb  test    rcx, rcx
0x1800e6fee  jz      short loc_1800E6FFF
0x1800e6ff0  mov     rax, [rcx]
0x1800e6ff3  mov     edx, r15d
0x1800e6ff6  mov     rax, [rax]
0x1800e6ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6ffe  nop
0x1800e6fff  jmp     loc_1800E7542
0x1800e7004  lea     r8, [rsi+78h]; void *
0x1800e7008  cmp     [r8+4], r15b
0x1800e700c  jnz     short loc_1800E7041
0x1800e700e  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e7015  mov     rcx, r14; this
0x1800e7018  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e701d  mov     edi, eax
0x1800e701f  test    eax, eax
0x1800e7021  jz      short loc_1800E7041
0x1800e7023  mov     rcx, [rsp+0C8h+var_88]
0x1800e7028  test    rcx, rcx
0x1800e702b  jz      short loc_1800E703C
0x1800e702d  mov     rax, [rcx]
0x1800e7030  mov     edx, r15d
0x1800e7033  mov     rax, [rax]
0x1800e7036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e703b  nop
0x1800e703c  jmp     loc_1800E7542
0x1800e7041  lea     r8, [rsi+80h]; void *
0x1800e7048  cmp     [r8+4], r15b
0x1800e704c  jnz     short loc_1800E7081
0x1800e704e  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e7055  mov     rcx, r14; this
0x1800e7058  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e705d  mov     edi, eax
0x1800e705f  test    eax, eax
0x1800e7061  jz      short loc_1800E7081
0x1800e7063  mov     rcx, [rsp+0C8h+var_88]
0x1800e7068  test    rcx, rcx
0x1800e706b  jz      short loc_1800E707C
0x1800e706d  mov     rax, [rcx]
0x1800e7070  mov     edx, r15d
0x1800e7073  mov     rax, [rax]
0x1800e7076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e707b  nop
0x1800e707c  jmp     loc_1800E7542
0x1800e7081  lea     r8, [rsi+88h]; void *
0x1800e7088  cmp     [r8+4], r15b
0x1800e708c  jnz     short loc_1800E70C1
0x1800e708e  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e7095  mov     rcx, r14; this
0x1800e7098  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e709d  mov     edi, eax
0x1800e709f  test    eax, eax
0x1800e70a1  jz      short loc_1800E70C1
0x1800e70a3  mov     rcx, [rsp+0C8h+var_88]
0x1800e70a8  test    rcx, rcx
0x1800e70ab  jz      short loc_1800E70BC
0x1800e70ad  mov     rax, [rcx]
0x1800e70b0  mov     edx, r15d
0x1800e70b3  mov     rax, [rax]
0x1800e70b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e70bb  nop
0x1800e70bc  jmp     loc_1800E7542
0x1800e70c1  lea     r8, [rsi+90h]; void *
0x1800e70c8  cmp     [r8+4], r15b
0x1800e70cc  jnz     short loc_1800E7101
0x1800e70ce  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e70d5  mov     rcx, r14; this
0x1800e70d8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e70dd  mov     edi, eax
0x1800e70df  test    eax, eax
0x1800e70e1  jz      short loc_1800E7101
0x1800e70e3  mov     rcx, [rsp+0C8h+var_88]
0x1800e70e8  test    rcx, rcx
0x1800e70eb  jz      short loc_1800E70FC
0x1800e70ed  mov     rax, [rcx]
0x1800e70f0  mov     edx, r15d
0x1800e70f3  mov     rax, [rax]
0x1800e70f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e70fb  nop
0x1800e70fc  jmp     loc_1800E7542
0x1800e7101  lea     r8, [rsi+98h]; void *
0x1800e7108  cmp     [r8+4], r15b
0x1800e710c  jnz     short loc_1800E7141
0x1800e710e  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e7115  mov     rcx, r14; this
0x1800e7118  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e711d  mov     edi, eax
0x1800e711f  test    eax, eax
0x1800e7121  jz      short loc_1800E7141
0x1800e7123  mov     rcx, [rsp+0C8h+var_88]
0x1800e7128  test    rcx, rcx
0x1800e712b  jz      short loc_1800E713C
0x1800e712d  mov     rax, [rcx]
0x1800e7130  mov     edx, r15d
0x1800e7133  mov     rax, [rax]
0x1800e7136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e713b  nop
0x1800e713c  jmp     loc_1800E7542
0x1800e7141  lea     r8, [rsi+0A0h]; void *
0x1800e7148  cmp     [r8+4], r15b
0x1800e714c  jnz     short loc_1800E7181
0x1800e714e  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e7155  mov     rcx, r14; this
0x1800e7158  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e715d  mov     edi, eax
0x1800e715f  test    eax, eax
0x1800e7161  jz      short loc_1800E7181
0x1800e7163  mov     rcx, [rsp+0C8h+var_88]
0x1800e7168  test    rcx, rcx
0x1800e716b  jz      short loc_1800E717C
0x1800e716d  mov     rax, [rcx]
0x1800e7170  mov     edx, r15d
0x1800e7173  mov     rax, [rax]
0x1800e7176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e717b  nop
0x1800e717c  jmp     loc_1800E7542
0x1800e7181  lea     r8, [rsi+0A8h]; void *
0x1800e7188  cmp     [r8+4], r15b
0x1800e718c  jnz     short loc_1800E71C1
0x1800e718e  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e7195  mov     rcx, r14; this
0x1800e7198  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e719d  mov     edi, eax
0x1800e719f  test    eax, eax
0x1800e71a1  jz      short loc_1800E71C1
0x1800e71a3  mov     rcx, [rsp+0C8h+var_88]
0x1800e71a8  test    rcx, rcx
0x1800e71ab  jz      short loc_1800E71BC
0x1800e71ad  mov     rax, [rcx]
0x1800e71b0  mov     edx, r15d
0x1800e71b3  mov     rax, [rax]
0x1800e71b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e71bb  nop
0x1800e71bc  jmp     loc_1800E7542
0x1800e71c1  lea     r8, [rsi+0B0h]; void *
0x1800e71c8  cmp     [r8+4], r15b
0x1800e71cc  jnz     short loc_1800E7201
0x1800e71ce  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e71d5  mov     rcx, r14; this
0x1800e71d8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e71dd  mov     edi, eax
0x1800e71df  test    eax, eax
0x1800e71e1  jz      short loc_1800E7201
0x1800e71e3  mov     rcx, [rsp+0C8h+var_88]
0x1800e71e8  test    rcx, rcx
0x1800e71eb  jz      short loc_1800E71FC
0x1800e71ed  mov     rax, [rcx]
0x1800e71f0  mov     edx, r15d
0x1800e71f3  mov     rax, [rax]
0x1800e71f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e71fb  nop
0x1800e71fc  jmp     loc_1800E7542
0x1800e7201  lea     r8, [rsi+0B8h]; void *
0x1800e7208  cmp     [r8+4], r15b
0x1800e720c  jnz     short loc_1800E7241
0x1800e720e  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e7215  mov     rcx, r14; this
0x1800e7218  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e721d  mov     edi, eax
0x1800e721f  test    eax, eax
0x1800e7221  jz      short loc_1800E7241
0x1800e7223  mov     rcx, [rsp+0C8h+var_88]
0x1800e7228  test    rcx, rcx
0x1800e722b  jz      short loc_1800E723C
0x1800e722d  mov     rax, [rcx]
0x1800e7230  mov     edx, r15d
0x1800e7233  mov     rax, [rax]
0x1800e7236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e723b  nop
0x1800e723c  jmp     loc_1800E7542
  ... truncated ...
```
