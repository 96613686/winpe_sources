# MDM_Policy_Result01_SystemServices02_InvokeModifyInstance

- ea: `0x18019e8e0`
- end: `0x18019f0f3`
- name: `MDM_Policy_Result01_SystemServices02_InvokeModifyInstance`
- size: `2067`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019f100`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x18019e8e0`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18019ea77`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019eab4`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019eaf1`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019eb2e`: `ConfigureIISAdminServiceStartupMode`
- `0x18019eb6e`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019ebae`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019ebee`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019ec2e`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019ec6e`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019ecae`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019ecee`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019ed2e`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019ed6e`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019edae`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019edee`: `ConfigureWebManagementServiceStartupMode`
- `0x18019ee2e`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019ee6e`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019eeae`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019eeee`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019ef2e`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019ef6e`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019efae`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019e92b`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
                 0x18u,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
          0x18u);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"ConfigureComputerBrowserServiceStartupMode",
                           (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupListenerServiceStartupMode",
                                (LONG *)(a2 + 104))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupProviderServiceStartupMode",
                                (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureIISAdminServiceStartupMode",
                                (LONG *)(a2 + 120))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInfraredMonitorServiceStartupMode",
                                (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInternetConnectionSharingServiceStartupMode",
                                (LONG *)(a2 + 136))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureLxssManagerServiceStartupMode",
                                (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureMicrosoftFTPServiceStartupMode",
                                (LONG *)(a2 + 152))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                (LONG *)(a2 + 168))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSimpleTCPIPServicesStartupMode",
                                (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                (LONG *)(a2 + 184))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSSDPDiscoveryServiceStartupMode",
                                (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureUPnPDeviceHostServiceStartupMode",
                                (LONG *)(a2 + 200))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWebManagementServiceStartupMode",
                                (LONG *)(a2 + 208))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                (LONG *)(a2 + 216))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                (LONG *)(a2 + 224))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                (LONG *)(a2 + 232))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                (LONG *)(a2 + 248))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                (LONG *)(a2 + 256))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                (LONG *)(a2 + 264))) != 0 )
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
      &dword_1803687C4,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x18019e8e0  mov     r11, rsp
0x18019e8e3  mov     [r11+18h], rsi
0x18019e8e7  push    rdi
0x18019e8e8  push    r14
0x18019e8ea  push    r15
0x18019e8ec  sub     rsp, 0B0h
0x18019e8f3  mov     rax, cs:__security_cookie
0x18019e8fa  xor     rax, rsp
0x18019e8fd  mov     [rsp+0C8h+var_28], rax
0x18019e905  mov     rsi, rdx
0x18019e908  mov     rdi, rcx
0x18019e90b  mov     [rsp+0C8h+var_50], 0
0x18019e913  mov     [rsp+0C8h+var_4C], 0
0x18019e918  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019e91f  mov     [r11-80h], rax
0x18019e923  lea     rax, [r11-50h]
0x18019e927  mov     [r11-78h], rax
0x18019e92b  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019e932  mov     [r11-70h], rax
0x18019e936  lea     rcx, [r11-50h]
0x18019e93a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019e93f  mov     eax, cs:dword_180380B68
0x18019e945  cmp     eax, 5
0x18019e948  jbe     short loc_18019E9BB
0x18019e94a  mov     rdx, 200000000000h
0x18019e954  lea     rcx, dword_180380B68
0x18019e95b  call    _tlgKeywordOn
0x18019e960  test    al, al
0x18019e962  jz      short loc_18019E9BB
0x18019e964  cmp     [rsp+0C8h+var_4C], 0
0x18019e969  jz      short loc_18019E99D
0x18019e96b  cmp     [rsp+0C8h+var_38], 0
0x18019e973  jnz     short loc_18019E993
0x18019e975  cmp     [rsp+0C8h+var_34], 0
0x18019e97d  jnz     short loc_18019E993
0x18019e97f  cmp     [rsp+0C8h+var_30], 0
0x18019e987  jnz     short loc_18019E993
0x18019e989  cmp     [rsp+0C8h+var_2C], 0
0x18019e991  jz      short loc_18019E99D
0x18019e993  lea     r9, [rsp+0C8h+var_38]
0x18019e99b  jmp     short loc_18019E9A0
0x18019e99d  xor     r9d, r9d
0x18019e9a0  lea     r8, [rsp+0C8h+var_48]
0x18019e9a8  lea     rdx, qword_180363750
0x18019e9af  lea     rcx, dword_180380B68
0x18019e9b6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019e9bb  cmp     byte ptr [rsi+48h], 0
0x18019e9bf  jz      loc_18019F05D
0x18019e9c5  cmp     byte ptr [rsi+58h], 0
0x18019e9c9  jz      loc_18019F05D
0x18019e9cf  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019e9d3  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019e9d7  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18019e9de  lea     rcx, [rsp+0C8h+var_80]; this
0x18019e9e3  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019e9e8  nop
0x18019e9e9  mov     [rsp+0C8h+var_88], 0
0x18019e9f2  lea     rax, [rsp+0C8h+var_88]
0x18019e9f7  mov     [rsp+0C8h+var_98], rax
0x18019e9fc  mov     [rsp+0C8h+var_A0], 3
0x18019ea04  mov     [rsp+0C8h+var_A8], 18h
0x18019ea0c  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019ea13  mov     r8, [rsi+40h]
0x18019ea17  mov     rdx, [rsi+50h]
0x18019ea1b  mov     rcx, rdi
0x18019ea1e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019ea23  mov     edi, eax
0x18019ea25  test    eax, eax
0x18019ea27  jz      short loc_18019EA2E
0x18019ea29  jmp     loc_18019F062
0x18019ea2e  lea     rax, [rsp+0C8h+var_88]
0x18019ea33  mov     [rsp+0C8h+var_60], rax
0x18019ea38  mov     r15d, 1
0x18019ea3e  mov     [rsp+0C8h+var_58], r15b
0x18019ea43  mov     r14, [rsp+0C8h+var_88]
0x18019ea48  test    r14, r14
0x18019ea4b  jnz     short loc_18019EA55
0x18019ea4d  mov     edi, r15d
0x18019ea50  jmp     loc_18019F062
0x18019ea55  mov     r9d, 18h; unsigned int
0x18019ea5b  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019ea62  mov     rdx, rsi; struct _MI_Instance *
0x18019ea65  mov     rcx, r14; this
0x18019ea68  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019ea6d  lea     r8, [rsi+60h]; void *
0x18019ea71  cmp     [r8+4], r15b
0x18019ea75  jnz     short loc_18019EAAA
0x18019ea77  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019ea7e  mov     rcx, r14; this
0x18019ea81  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ea86  mov     edi, eax
0x18019ea88  test    eax, eax
0x18019ea8a  jz      short loc_18019EAAA
0x18019ea8c  mov     rcx, [rsp+0C8h+var_88]
0x18019ea91  test    rcx, rcx
0x18019ea94  jz      short loc_18019EAA5
0x18019ea96  mov     rax, [rcx]
0x18019ea99  mov     edx, r15d
0x18019ea9c  mov     rax, [rax]
0x18019ea9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eaa4  nop
0x18019eaa5  jmp     loc_18019F062
0x18019eaaa  lea     r8, [rsi+68h]; void *
0x18019eaae  cmp     [r8+4], r15b
0x18019eab2  jnz     short loc_18019EAE7
0x18019eab4  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019eabb  mov     rcx, r14; this
0x18019eabe  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019eac3  mov     edi, eax
0x18019eac5  test    eax, eax
0x18019eac7  jz      short loc_18019EAE7
0x18019eac9  mov     rcx, [rsp+0C8h+var_88]
0x18019eace  test    rcx, rcx
0x18019ead1  jz      short loc_18019EAE2
0x18019ead3  mov     rax, [rcx]
0x18019ead6  mov     edx, r15d
0x18019ead9  mov     rax, [rax]
0x18019eadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eae1  nop
0x18019eae2  jmp     loc_18019F062
0x18019eae7  lea     r8, [rsi+70h]; void *
0x18019eaeb  cmp     [r8+4], r15b
0x18019eaef  jnz     short loc_18019EB24
0x18019eaf1  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019eaf8  mov     rcx, r14; this
0x18019eafb  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019eb00  mov     edi, eax
0x18019eb02  test    eax, eax
0x18019eb04  jz      short loc_18019EB24
0x18019eb06  mov     rcx, [rsp+0C8h+var_88]
0x18019eb0b  test    rcx, rcx
0x18019eb0e  jz      short loc_18019EB1F
0x18019eb10  mov     rax, [rcx]
0x18019eb13  mov     edx, r15d
0x18019eb16  mov     rax, [rax]
0x18019eb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb1e  nop
0x18019eb1f  jmp     loc_18019F062
0x18019eb24  lea     r8, [rsi+78h]; void *
0x18019eb28  cmp     [r8+4], r15b
0x18019eb2c  jnz     short loc_18019EB61
0x18019eb2e  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019eb35  mov     rcx, r14; this
0x18019eb38  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019eb3d  mov     edi, eax
0x18019eb3f  test    eax, eax
0x18019eb41  jz      short loc_18019EB61
0x18019eb43  mov     rcx, [rsp+0C8h+var_88]
0x18019eb48  test    rcx, rcx
0x18019eb4b  jz      short loc_18019EB5C
0x18019eb4d  mov     rax, [rcx]
0x18019eb50  mov     edx, r15d
0x18019eb53  mov     rax, [rax]
0x18019eb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb5b  nop
0x18019eb5c  jmp     loc_18019F062
0x18019eb61  lea     r8, [rsi+80h]; void *
0x18019eb68  cmp     [r8+4], r15b
0x18019eb6c  jnz     short loc_18019EBA1
0x18019eb6e  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019eb75  mov     rcx, r14; this
0x18019eb78  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019eb7d  mov     edi, eax
0x18019eb7f  test    eax, eax
0x18019eb81  jz      short loc_18019EBA1
0x18019eb83  mov     rcx, [rsp+0C8h+var_88]
0x18019eb88  test    rcx, rcx
0x18019eb8b  jz      short loc_18019EB9C
0x18019eb8d  mov     rax, [rcx]
0x18019eb90  mov     edx, r15d
0x18019eb93  mov     rax, [rax]
0x18019eb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019eb9b  nop
0x18019eb9c  jmp     loc_18019F062
0x18019eba1  lea     r8, [rsi+88h]; void *
0x18019eba8  cmp     [r8+4], r15b
0x18019ebac  jnz     short loc_18019EBE1
0x18019ebae  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019ebb5  mov     rcx, r14; this
0x18019ebb8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ebbd  mov     edi, eax
0x18019ebbf  test    eax, eax
0x18019ebc1  jz      short loc_18019EBE1
0x18019ebc3  mov     rcx, [rsp+0C8h+var_88]
0x18019ebc8  test    rcx, rcx
0x18019ebcb  jz      short loc_18019EBDC
0x18019ebcd  mov     rax, [rcx]
0x18019ebd0  mov     edx, r15d
0x18019ebd3  mov     rax, [rax]
0x18019ebd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ebdb  nop
0x18019ebdc  jmp     loc_18019F062
0x18019ebe1  lea     r8, [rsi+90h]; void *
0x18019ebe8  cmp     [r8+4], r15b
0x18019ebec  jnz     short loc_18019EC21
0x18019ebee  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019ebf5  mov     rcx, r14; this
0x18019ebf8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ebfd  mov     edi, eax
0x18019ebff  test    eax, eax
0x18019ec01  jz      short loc_18019EC21
0x18019ec03  mov     rcx, [rsp+0C8h+var_88]
0x18019ec08  test    rcx, rcx
0x18019ec0b  jz      short loc_18019EC1C
0x18019ec0d  mov     rax, [rcx]
0x18019ec10  mov     edx, r15d
0x18019ec13  mov     rax, [rax]
0x18019ec16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ec1b  nop
0x18019ec1c  jmp     loc_18019F062
0x18019ec21  lea     r8, [rsi+98h]; void *
0x18019ec28  cmp     [r8+4], r15b
0x18019ec2c  jnz     short loc_18019EC61
0x18019ec2e  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019ec35  mov     rcx, r14; this
0x18019ec38  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ec3d  mov     edi, eax
0x18019ec3f  test    eax, eax
0x18019ec41  jz      short loc_18019EC61
0x18019ec43  mov     rcx, [rsp+0C8h+var_88]
0x18019ec48  test    rcx, rcx
0x18019ec4b  jz      short loc_18019EC5C
0x18019ec4d  mov     rax, [rcx]
0x18019ec50  mov     edx, r15d
0x18019ec53  mov     rax, [rax]
0x18019ec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ec5b  nop
0x18019ec5c  jmp     loc_18019F062
0x18019ec61  lea     r8, [rsi+0A0h]; void *
0x18019ec68  cmp     [r8+4], r15b
0x18019ec6c  jnz     short loc_18019ECA1
0x18019ec6e  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019ec75  mov     rcx, r14; this
0x18019ec78  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ec7d  mov     edi, eax
0x18019ec7f  test    eax, eax
0x18019ec81  jz      short loc_18019ECA1
0x18019ec83  mov     rcx, [rsp+0C8h+var_88]
0x18019ec88  test    rcx, rcx
0x18019ec8b  jz      short loc_18019EC9C
0x18019ec8d  mov     rax, [rcx]
0x18019ec90  mov     edx, r15d
0x18019ec93  mov     rax, [rax]
0x18019ec96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ec9b  nop
0x18019ec9c  jmp     loc_18019F062
0x18019eca1  lea     r8, [rsi+0A8h]; void *
0x18019eca8  cmp     [r8+4], r15b
0x18019ecac  jnz     short loc_18019ECE1
0x18019ecae  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019ecb5  mov     rcx, r14; this
0x18019ecb8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ecbd  mov     edi, eax
0x18019ecbf  test    eax, eax
0x18019ecc1  jz      short loc_18019ECE1
0x18019ecc3  mov     rcx, [rsp+0C8h+var_88]
0x18019ecc8  test    rcx, rcx
0x18019eccb  jz      short loc_18019ECDC
0x18019eccd  mov     rax, [rcx]
0x18019ecd0  mov     edx, r15d
0x18019ecd3  mov     rax, [rax]
0x18019ecd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ecdb  nop
0x18019ecdc  jmp     loc_18019F062
0x18019ece1  lea     r8, [rsi+0B0h]; void *
0x18019ece8  cmp     [r8+4], r15b
0x18019ecec  jnz     short loc_18019ED21
0x18019ecee  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019ecf5  mov     rcx, r14; this
0x18019ecf8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ecfd  mov     edi, eax
0x18019ecff  test    eax, eax
0x18019ed01  jz      short loc_18019ED21
0x18019ed03  mov     rcx, [rsp+0C8h+var_88]
0x18019ed08  test    rcx, rcx
0x18019ed0b  jz      short loc_18019ED1C
0x18019ed0d  mov     rax, [rcx]
0x18019ed10  mov     edx, r15d
0x18019ed13  mov     rax, [rax]
0x18019ed16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ed1b  nop
0x18019ed1c  jmp     loc_18019F062
0x18019ed21  lea     r8, [rsi+0B8h]; void *
0x18019ed28  cmp     [r8+4], r15b
0x18019ed2c  jnz     short loc_18019ED61
0x18019ed2e  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019ed35  mov     rcx, r14; this
0x18019ed38  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ed3d  mov     edi, eax
0x18019ed3f  test    eax, eax
0x18019ed41  jz      short loc_18019ED61
0x18019ed43  mov     rcx, [rsp+0C8h+var_88]
0x18019ed48  test    rcx, rcx
0x18019ed4b  jz      short loc_18019ED5C
0x18019ed4d  mov     rax, [rcx]
0x18019ed50  mov     edx, r15d
0x18019ed53  mov     rax, [rax]
0x18019ed56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ed5b  nop
0x18019ed5c  jmp     loc_18019F062
  ... truncated ...
```
