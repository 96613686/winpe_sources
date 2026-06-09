# MDM_Policy_Result01_SystemServices02_InvokeModifyInstance

- ea: `0x18019e4d0`
- end: `0x18019ece4`
- name: `MDM_Policy_Result01_SystemServices02_InvokeModifyInstance`
- size: `2068`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019ecf0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x18019e4d0`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18019e667`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019e6a4`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019e6e1`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019e71e`: `ConfigureIISAdminServiceStartupMode`
- `0x18019e75e`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019e79e`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019e7de`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019e81e`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019e85e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019e89e`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019e8de`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019e91e`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019e95e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019e99e`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019e9de`: `ConfigureWebManagementServiceStartupMode`
- `0x18019ea1e`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019ea5e`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019ea9e`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019eade`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019eb1e`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019eb5e`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019eb9e`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019e51b`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v9[2] = "MDM_Policy_Result01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180363750,
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
                               &MDM_Policy_Result01_SystemServices02_NodeList,
                               24,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
          0x18u);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"ConfigureComputerBrowserServiceStartupMode",
                           (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupListenerServiceStartupMode",
                                (void *)(a2 + 104))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupProviderServiceStartupMode",
                                (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureIISAdminServiceStartupMode",
                                (void *)(a2 + 120))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInfraredMonitorServiceStartupMode",
                                (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInternetConnectionSharingServiceStartupMode",
                                (void *)(a2 + 136))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureLxssManagerServiceStartupMode",
                                (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureMicrosoftFTPServiceStartupMode",
                                (void *)(a2 + 152))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                (void *)(a2 + 168))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSimpleTCPIPServicesStartupMode",
                                (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                (void *)(a2 + 184))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSSDPDiscoveryServiceStartupMode",
                                (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureUPnPDeviceHostServiceStartupMode",
                                (void *)(a2 + 200))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWebManagementServiceStartupMode",
                                (void *)(a2 + 208))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                (void *)(a2 + 216))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                (void *)(a2 + 224))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                (void *)(a2 + 232))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                (void *)(a2 + 248))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                (void *)(a2 + 256))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                (void *)(a2 + 264))) != MI_RESULT_OK )
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
      &dword_1803687C4,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18019e4d0  mov     r11, rsp
0x18019e4d3  mov     [r11+18h], rsi
0x18019e4d7  push    rdi
0x18019e4d8  push    r14
0x18019e4da  push    r15
0x18019e4dc  sub     rsp, 0B0h
0x18019e4e3  mov     rax, cs:__security_cookie
0x18019e4ea  xor     rax, rsp
0x18019e4ed  mov     [rsp+0C8h+var_28], rax
0x18019e4f5  mov     rsi, rdx
0x18019e4f8  mov     rdi, rcx
0x18019e4fb  mov     [rsp+0C8h+var_50], 0
0x18019e503  mov     [rsp+0C8h+var_4C], 0
0x18019e508  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019e50f  mov     [r11-80h], rax
0x18019e513  lea     rax, [r11-50h]
0x18019e517  mov     [r11-78h], rax
0x18019e51b  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019e522  mov     [r11-70h], rax
0x18019e526  lea     rcx, [r11-50h]
0x18019e52a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019e52f  mov     eax, cs:dword_180380B68
0x18019e535  cmp     eax, 5
0x18019e538  jbe     short loc_18019E5AB
0x18019e53a  mov     rdx, 200000000000h
0x18019e544  lea     rcx, dword_180380B68
0x18019e54b  call    _tlgKeywordOn
0x18019e550  test    al, al
0x18019e552  jz      short loc_18019E5AB
0x18019e554  cmp     [rsp+0C8h+var_4C], 0
0x18019e559  jz      short loc_18019E58D
0x18019e55b  cmp     [rsp+0C8h+var_38], 0
0x18019e563  jnz     short loc_18019E583
0x18019e565  cmp     [rsp+0C8h+var_34], 0
0x18019e56d  jnz     short loc_18019E583
0x18019e56f  cmp     [rsp+0C8h+var_30], 0
0x18019e577  jnz     short loc_18019E583
0x18019e579  cmp     [rsp+0C8h+var_2C], 0
0x18019e581  jz      short loc_18019E58D
0x18019e583  lea     r9, [rsp+0C8h+var_38]
0x18019e58b  jmp     short loc_18019E590
0x18019e58d  xor     r9d, r9d
0x18019e590  lea     r8, [rsp+0C8h+var_48]
0x18019e598  lea     rdx, qword_180363750
0x18019e59f  lea     rcx, dword_180380B68
0x18019e5a6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019e5ab  cmp     byte ptr [rsi+48h], 0
0x18019e5af  jz      loc_18019EC4D
0x18019e5b5  cmp     byte ptr [rsi+58h], 0
0x18019e5b9  jz      loc_18019EC4D
0x18019e5bf  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019e5c3  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019e5c7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18019e5ce  lea     rcx, [rsp+0C8h+var_80]; this
0x18019e5d3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019e5d8  nop
0x18019e5d9  mov     [rsp+0C8h+var_88], 0
0x18019e5e2  lea     rax, [rsp+0C8h+var_88]
0x18019e5e7  mov     [rsp+0C8h+var_98], rax
0x18019e5ec  mov     [rsp+0C8h+var_A0], 3
0x18019e5f4  mov     [rsp+0C8h+var_A8], 18h
0x18019e5fc  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019e603  mov     r8, [rsi+40h]
0x18019e607  mov     rdx, [rsi+50h]
0x18019e60b  mov     rcx, rdi
0x18019e60e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019e613  mov     edi, eax
0x18019e615  test    eax, eax
0x18019e617  jz      short loc_18019E61E
0x18019e619  jmp     loc_18019EC52
0x18019e61e  lea     rax, [rsp+0C8h+var_88]
0x18019e623  mov     [rsp+0C8h+var_60], rax
0x18019e628  mov     r15d, 1
0x18019e62e  mov     [rsp+0C8h+var_58], r15b
0x18019e633  mov     r14, [rsp+0C8h+var_88]
0x18019e638  test    r14, r14
0x18019e63b  jnz     short loc_18019E645
0x18019e63d  mov     edi, r15d
0x18019e640  jmp     loc_18019EC52
0x18019e645  mov     r9d, 18h; unsigned int
0x18019e64b  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019e652  mov     rdx, rsi; struct _MI_Instance *
0x18019e655  mov     rcx, r14; this
0x18019e658  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019e65d  lea     r8, [rsi+60h]; void *
0x18019e661  cmp     [r8+4], r15b
0x18019e665  jnz     short loc_18019E69A
0x18019e667  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019e66e  mov     rcx, r14; this
0x18019e671  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e676  mov     edi, eax
0x18019e678  test    eax, eax
0x18019e67a  jz      short loc_18019E69A
0x18019e67c  mov     rcx, [rsp+0C8h+var_88]
0x18019e681  test    rcx, rcx
0x18019e684  jz      short loc_18019E695
0x18019e686  mov     rax, [rcx]
0x18019e689  mov     edx, r15d
0x18019e68c  mov     rax, [rax]
0x18019e68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e694  nop
0x18019e695  jmp     loc_18019EC52
0x18019e69a  lea     r8, [rsi+68h]; void *
0x18019e69e  cmp     [r8+4], r15b
0x18019e6a2  jnz     short loc_18019E6D7
0x18019e6a4  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019e6ab  mov     rcx, r14; this
0x18019e6ae  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e6b3  mov     edi, eax
0x18019e6b5  test    eax, eax
0x18019e6b7  jz      short loc_18019E6D7
0x18019e6b9  mov     rcx, [rsp+0C8h+var_88]
0x18019e6be  test    rcx, rcx
0x18019e6c1  jz      short loc_18019E6D2
0x18019e6c3  mov     rax, [rcx]
0x18019e6c6  mov     edx, r15d
0x18019e6c9  mov     rax, [rax]
0x18019e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e6d1  nop
0x18019e6d2  jmp     loc_18019EC52
0x18019e6d7  lea     r8, [rsi+70h]; void *
0x18019e6db  cmp     [r8+4], r15b
0x18019e6df  jnz     short loc_18019E714
0x18019e6e1  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019e6e8  mov     rcx, r14; this
0x18019e6eb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e6f0  mov     edi, eax
0x18019e6f2  test    eax, eax
0x18019e6f4  jz      short loc_18019E714
0x18019e6f6  mov     rcx, [rsp+0C8h+var_88]
0x18019e6fb  test    rcx, rcx
0x18019e6fe  jz      short loc_18019E70F
0x18019e700  mov     rax, [rcx]
0x18019e703  mov     edx, r15d
0x18019e706  mov     rax, [rax]
0x18019e709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e70e  nop
0x18019e70f  jmp     loc_18019EC52
0x18019e714  lea     r8, [rsi+78h]; void *
0x18019e718  cmp     [r8+4], r15b
0x18019e71c  jnz     short loc_18019E751
0x18019e71e  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019e725  mov     rcx, r14; this
0x18019e728  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e72d  mov     edi, eax
0x18019e72f  test    eax, eax
0x18019e731  jz      short loc_18019E751
0x18019e733  mov     rcx, [rsp+0C8h+var_88]
0x18019e738  test    rcx, rcx
0x18019e73b  jz      short loc_18019E74C
0x18019e73d  mov     rax, [rcx]
0x18019e740  mov     edx, r15d
0x18019e743  mov     rax, [rax]
0x18019e746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e74b  nop
0x18019e74c  jmp     loc_18019EC52
0x18019e751  lea     r8, [rsi+80h]; void *
0x18019e758  cmp     [r8+4], r15b
0x18019e75c  jnz     short loc_18019E791
0x18019e75e  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019e765  mov     rcx, r14; this
0x18019e768  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e76d  mov     edi, eax
0x18019e76f  test    eax, eax
0x18019e771  jz      short loc_18019E791
0x18019e773  mov     rcx, [rsp+0C8h+var_88]
0x18019e778  test    rcx, rcx
0x18019e77b  jz      short loc_18019E78C
0x18019e77d  mov     rax, [rcx]
0x18019e780  mov     edx, r15d
0x18019e783  mov     rax, [rax]
0x18019e786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e78b  nop
0x18019e78c  jmp     loc_18019EC52
0x18019e791  lea     r8, [rsi+88h]; void *
0x18019e798  cmp     [r8+4], r15b
0x18019e79c  jnz     short loc_18019E7D1
0x18019e79e  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019e7a5  mov     rcx, r14; this
0x18019e7a8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e7ad  mov     edi, eax
0x18019e7af  test    eax, eax
0x18019e7b1  jz      short loc_18019E7D1
0x18019e7b3  mov     rcx, [rsp+0C8h+var_88]
0x18019e7b8  test    rcx, rcx
0x18019e7bb  jz      short loc_18019E7CC
0x18019e7bd  mov     rax, [rcx]
0x18019e7c0  mov     edx, r15d
0x18019e7c3  mov     rax, [rax]
0x18019e7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e7cb  nop
0x18019e7cc  jmp     loc_18019EC52
0x18019e7d1  lea     r8, [rsi+90h]; void *
0x18019e7d8  cmp     [r8+4], r15b
0x18019e7dc  jnz     short loc_18019E811
0x18019e7de  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019e7e5  mov     rcx, r14; this
0x18019e7e8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e7ed  mov     edi, eax
0x18019e7ef  test    eax, eax
0x18019e7f1  jz      short loc_18019E811
0x18019e7f3  mov     rcx, [rsp+0C8h+var_88]
0x18019e7f8  test    rcx, rcx
0x18019e7fb  jz      short loc_18019E80C
0x18019e7fd  mov     rax, [rcx]
0x18019e800  mov     edx, r15d
0x18019e803  mov     rax, [rax]
0x18019e806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e80b  nop
0x18019e80c  jmp     loc_18019EC52
0x18019e811  lea     r8, [rsi+98h]; void *
0x18019e818  cmp     [r8+4], r15b
0x18019e81c  jnz     short loc_18019E851
0x18019e81e  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019e825  mov     rcx, r14; this
0x18019e828  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e82d  mov     edi, eax
0x18019e82f  test    eax, eax
0x18019e831  jz      short loc_18019E851
0x18019e833  mov     rcx, [rsp+0C8h+var_88]
0x18019e838  test    rcx, rcx
0x18019e83b  jz      short loc_18019E84C
0x18019e83d  mov     rax, [rcx]
0x18019e840  mov     edx, r15d
0x18019e843  mov     rax, [rax]
0x18019e846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e84b  nop
0x18019e84c  jmp     loc_18019EC52
0x18019e851  lea     r8, [rsi+0A0h]; void *
0x18019e858  cmp     [r8+4], r15b
0x18019e85c  jnz     short loc_18019E891
0x18019e85e  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019e865  mov     rcx, r14; this
0x18019e868  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e86d  mov     edi, eax
0x18019e86f  test    eax, eax
0x18019e871  jz      short loc_18019E891
0x18019e873  mov     rcx, [rsp+0C8h+var_88]
0x18019e878  test    rcx, rcx
0x18019e87b  jz      short loc_18019E88C
0x18019e87d  mov     rax, [rcx]
0x18019e880  mov     edx, r15d
0x18019e883  mov     rax, [rax]
0x18019e886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e88b  nop
0x18019e88c  jmp     loc_18019EC52
0x18019e891  lea     r8, [rsi+0A8h]; void *
0x18019e898  cmp     [r8+4], r15b
0x18019e89c  jnz     short loc_18019E8D1
0x18019e89e  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019e8a5  mov     rcx, r14; this
0x18019e8a8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e8ad  mov     edi, eax
0x18019e8af  test    eax, eax
0x18019e8b1  jz      short loc_18019E8D1
0x18019e8b3  mov     rcx, [rsp+0C8h+var_88]
0x18019e8b8  test    rcx, rcx
0x18019e8bb  jz      short loc_18019E8CC
0x18019e8bd  mov     rax, [rcx]
0x18019e8c0  mov     edx, r15d
0x18019e8c3  mov     rax, [rax]
0x18019e8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e8cb  nop
0x18019e8cc  jmp     loc_18019EC52
0x18019e8d1  lea     r8, [rsi+0B0h]; void *
0x18019e8d8  cmp     [r8+4], r15b
0x18019e8dc  jnz     short loc_18019E911
0x18019e8de  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019e8e5  mov     rcx, r14; this
0x18019e8e8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e8ed  mov     edi, eax
0x18019e8ef  test    eax, eax
0x18019e8f1  jz      short loc_18019E911
0x18019e8f3  mov     rcx, [rsp+0C8h+var_88]
0x18019e8f8  test    rcx, rcx
0x18019e8fb  jz      short loc_18019E90C
0x18019e8fd  mov     rax, [rcx]
0x18019e900  mov     edx, r15d
0x18019e903  mov     rax, [rax]
0x18019e906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e90b  nop
0x18019e90c  jmp     loc_18019EC52
0x18019e911  lea     r8, [rsi+0B8h]; void *
0x18019e918  cmp     [r8+4], r15b
0x18019e91c  jnz     short loc_18019E951
0x18019e91e  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019e925  mov     rcx, r14; this
0x18019e928  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019e92d  mov     edi, eax
0x18019e92f  test    eax, eax
0x18019e931  jz      short loc_18019E951
0x18019e933  mov     rcx, [rsp+0C8h+var_88]
0x18019e938  test    rcx, rcx
0x18019e93b  jz      short loc_18019E94C
0x18019e93d  mov     rax, [rcx]
0x18019e940  mov     edx, r15d
0x18019e943  mov     rax, [rax]
0x18019e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e94b  nop
0x18019e94c  jmp     loc_18019EC52
  ... truncated ...
```
