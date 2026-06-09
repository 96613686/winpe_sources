# MDM_Policy_Config01_SystemServices02_InvokeModifyInstance

- ea: `0x1800e7520`
- end: `0x1800e7d33`
- name: `MDM_Policy_Config01_SystemServices02_InvokeModifyInstance`
- size: `2067`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e7d40`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1800e7520`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800e76b7`: `ConfigureComputerBrowserServiceStartupMode`
- `0x1800e76f4`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x1800e7731`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x1800e776e`: `ConfigureIISAdminServiceStartupMode`
- `0x1800e77ae`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x1800e77ee`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x1800e782e`: `ConfigureLxssManagerServiceStartupMode`
- `0x1800e786e`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x1800e78ae`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x1800e78ee`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x1800e792e`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x1800e796e`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x1800e79ae`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x1800e79ee`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x1800e7a2e`: `ConfigureWebManagementServiceStartupMode`
- `0x1800e7a6e`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x1800e7aae`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x1800e7aee`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x1800e7b2e`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x1800e7b6e`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x1800e7bae`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x1800e7bee`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x1800e756b`: `MDM_Policy_Config01_SystemServices02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_SystemServices02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
                   0x18u,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_SystemServices02_NodeList,
            0x18u);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                             v7,
                             L"ConfigureComputerBrowserServiceStartupMode",
                             (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureHomeGroupListenerServiceStartupMode",
                                  (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureHomeGroupProviderServiceStartupMode",
                                  (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureIISAdminServiceStartupMode",
                                  (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureInfraredMonitorServiceStartupMode",
                                  (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureInternetConnectionSharingServiceStartupMode",
                                  (LONG *)(a2 + 136))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureLxssManagerServiceStartupMode",
                                  (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureMicrosoftFTPServiceStartupMode",
                                  (LONG *)(a2 + 152))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                  (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                  (LONG *)(a2 + 168))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSimpleTCPIPServicesStartupMode",
                                  (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                  (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureSSDPDiscoveryServiceStartupMode",
                                  (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureUPnPDeviceHostServiceStartupMode",
                                  (LONG *)(a2 + 200))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWebManagementServiceStartupMode",
                                  (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                  (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                  (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                  (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                  (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                  (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                  (LONG *)(a2 + 264))) != 0 )
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
      &byte_18036000F,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x1800e7520  mov     r11, rsp
0x1800e7523  mov     [r11+18h], rsi
0x1800e7527  push    rdi
0x1800e7528  push    r14
0x1800e752a  push    r15
0x1800e752c  sub     rsp, 0B0h
0x1800e7533  mov     rax, cs:__security_cookie
0x1800e753a  xor     rax, rsp
0x1800e753d  mov     [rsp+0C8h+var_28], rax
0x1800e7545  mov     rsi, rdx
0x1800e7548  mov     rdi, rcx
0x1800e754b  mov     [rsp+0C8h+var_50], 0
0x1800e7553  mov     [rsp+0C8h+var_4C], 0
0x1800e7558  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e755f  mov     [r11-80h], rax
0x1800e7563  lea     rax, [r11-50h]
0x1800e7567  mov     [r11-78h], rax
0x1800e756b  lea     rax, aMdmPolicyConfi_72; "MDM_Policy_Config01_SystemServices02"
0x1800e7572  mov     [r11-70h], rax
0x1800e7576  lea     rcx, [r11-50h]
0x1800e757a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e757f  mov     eax, cs:dword_180380B68
0x1800e7585  cmp     eax, 5
0x1800e7588  jbe     short loc_1800E75FB
0x1800e758a  mov     rdx, 200000000000h
0x1800e7594  lea     rcx, dword_180380B68
0x1800e759b  call    _tlgKeywordOn
0x1800e75a0  test    al, al
0x1800e75a2  jz      short loc_1800E75FB
0x1800e75a4  cmp     [rsp+0C8h+var_4C], 0
0x1800e75a9  jz      short loc_1800E75DD
0x1800e75ab  cmp     [rsp+0C8h+var_38], 0
0x1800e75b3  jnz     short loc_1800E75D3
0x1800e75b5  cmp     [rsp+0C8h+var_34], 0
0x1800e75bd  jnz     short loc_1800E75D3
0x1800e75bf  cmp     [rsp+0C8h+var_30], 0
0x1800e75c7  jnz     short loc_1800E75D3
0x1800e75c9  cmp     [rsp+0C8h+var_2C], 0
0x1800e75d1  jz      short loc_1800E75DD
0x1800e75d3  lea     r9, [rsp+0C8h+var_38]
0x1800e75db  jmp     short loc_1800E75E0
0x1800e75dd  xor     r9d, r9d
0x1800e75e0  lea     r8, [rsp+0C8h+var_48]
0x1800e75e8  lea     rdx, dword_180356434
0x1800e75ef  lea     rcx, dword_180380B68
0x1800e75f6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e75fb  cmp     byte ptr [rsi+48h], 0
0x1800e75ff  jz      loc_1800E7C9D
0x1800e7605  cmp     byte ptr [rsi+58h], 0
0x1800e7609  jz      loc_1800E7C9D
0x1800e760f  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e7613  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e7617  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1800e761e  lea     rcx, [rsp+0C8h+var_80]; this
0x1800e7623  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e7628  nop
0x1800e7629  mov     [rsp+0C8h+var_88], 0
0x1800e7632  lea     rax, [rsp+0C8h+var_88]
0x1800e7637  mov     [rsp+0C8h+var_98], rax
0x1800e763c  mov     [rsp+0C8h+var_A0], 3
0x1800e7644  mov     [rsp+0C8h+var_A8], 18h
0x1800e764c  lea     r9, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_SystemServices02_NodeList
0x1800e7653  mov     r8, [rsi+40h]
0x1800e7657  mov     rdx, [rsi+50h]
0x1800e765b  mov     rcx, rdi
0x1800e765e  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e7663  mov     edi, eax
0x1800e7665  test    eax, eax
0x1800e7667  jz      short loc_1800E766E
0x1800e7669  jmp     loc_1800E7CA2
0x1800e766e  lea     rax, [rsp+0C8h+var_88]
0x1800e7673  mov     [rsp+0C8h+var_60], rax
0x1800e7678  mov     r15d, 1
0x1800e767e  mov     [rsp+0C8h+var_58], r15b
0x1800e7683  mov     r14, [rsp+0C8h+var_88]
0x1800e7688  test    r14, r14
0x1800e768b  jnz     short loc_1800E7695
0x1800e768d  mov     edi, r15d
0x1800e7690  jmp     loc_1800E7CA2
0x1800e7695  mov     r9d, 18h; unsigned int
0x1800e769b  lea     r8, ?MDM_Policy_Config01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e76a2  mov     rdx, rsi; struct _MI_Instance *
0x1800e76a5  mov     rcx, r14; this
0x1800e76a8  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e76ad  lea     r8, [rsi+60h]; void *
0x1800e76b1  cmp     [r8+4], r15b
0x1800e76b5  jnz     short loc_1800E76EA
0x1800e76b7  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x1800e76be  mov     rcx, r14; this
0x1800e76c1  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e76c6  mov     edi, eax
0x1800e76c8  test    eax, eax
0x1800e76ca  jz      short loc_1800E76EA
0x1800e76cc  mov     rcx, [rsp+0C8h+var_88]
0x1800e76d1  test    rcx, rcx
0x1800e76d4  jz      short loc_1800E76E5
0x1800e76d6  mov     rax, [rcx]
0x1800e76d9  mov     edx, r15d
0x1800e76dc  mov     rax, [rax]
0x1800e76df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e76e4  nop
0x1800e76e5  jmp     loc_1800E7CA2
0x1800e76ea  lea     r8, [rsi+68h]; void *
0x1800e76ee  cmp     [r8+4], r15b
0x1800e76f2  jnz     short loc_1800E7727
0x1800e76f4  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x1800e76fb  mov     rcx, r14; this
0x1800e76fe  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e7703  mov     edi, eax
0x1800e7705  test    eax, eax
0x1800e7707  jz      short loc_1800E7727
0x1800e7709  mov     rcx, [rsp+0C8h+var_88]
0x1800e770e  test    rcx, rcx
0x1800e7711  jz      short loc_1800E7722
0x1800e7713  mov     rax, [rcx]
0x1800e7716  mov     edx, r15d
0x1800e7719  mov     rax, [rax]
0x1800e771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7721  nop
0x1800e7722  jmp     loc_1800E7CA2
0x1800e7727  lea     r8, [rsi+70h]; void *
0x1800e772b  cmp     [r8+4], r15b
0x1800e772f  jnz     short loc_1800E7764
0x1800e7731  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x1800e7738  mov     rcx, r14; this
0x1800e773b  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e7740  mov     edi, eax
0x1800e7742  test    eax, eax
0x1800e7744  jz      short loc_1800E7764
0x1800e7746  mov     rcx, [rsp+0C8h+var_88]
0x1800e774b  test    rcx, rcx
0x1800e774e  jz      short loc_1800E775F
0x1800e7750  mov     rax, [rcx]
0x1800e7753  mov     edx, r15d
0x1800e7756  mov     rax, [rax]
0x1800e7759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e775e  nop
0x1800e775f  jmp     loc_1800E7CA2
0x1800e7764  lea     r8, [rsi+78h]; void *
0x1800e7768  cmp     [r8+4], r15b
0x1800e776c  jnz     short loc_1800E77A1
0x1800e776e  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x1800e7775  mov     rcx, r14; this
0x1800e7778  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e777d  mov     edi, eax
0x1800e777f  test    eax, eax
0x1800e7781  jz      short loc_1800E77A1
0x1800e7783  mov     rcx, [rsp+0C8h+var_88]
0x1800e7788  test    rcx, rcx
0x1800e778b  jz      short loc_1800E779C
0x1800e778d  mov     rax, [rcx]
0x1800e7790  mov     edx, r15d
0x1800e7793  mov     rax, [rax]
0x1800e7796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e779b  nop
0x1800e779c  jmp     loc_1800E7CA2
0x1800e77a1  lea     r8, [rsi+80h]; void *
0x1800e77a8  cmp     [r8+4], r15b
0x1800e77ac  jnz     short loc_1800E77E1
0x1800e77ae  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x1800e77b5  mov     rcx, r14; this
0x1800e77b8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e77bd  mov     edi, eax
0x1800e77bf  test    eax, eax
0x1800e77c1  jz      short loc_1800E77E1
0x1800e77c3  mov     rcx, [rsp+0C8h+var_88]
0x1800e77c8  test    rcx, rcx
0x1800e77cb  jz      short loc_1800E77DC
0x1800e77cd  mov     rax, [rcx]
0x1800e77d0  mov     edx, r15d
0x1800e77d3  mov     rax, [rax]
0x1800e77d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e77db  nop
0x1800e77dc  jmp     loc_1800E7CA2
0x1800e77e1  lea     r8, [rsi+88h]; void *
0x1800e77e8  cmp     [r8+4], r15b
0x1800e77ec  jnz     short loc_1800E7821
0x1800e77ee  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x1800e77f5  mov     rcx, r14; this
0x1800e77f8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e77fd  mov     edi, eax
0x1800e77ff  test    eax, eax
0x1800e7801  jz      short loc_1800E7821
0x1800e7803  mov     rcx, [rsp+0C8h+var_88]
0x1800e7808  test    rcx, rcx
0x1800e780b  jz      short loc_1800E781C
0x1800e780d  mov     rax, [rcx]
0x1800e7810  mov     edx, r15d
0x1800e7813  mov     rax, [rax]
0x1800e7816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e781b  nop
0x1800e781c  jmp     loc_1800E7CA2
0x1800e7821  lea     r8, [rsi+90h]; void *
0x1800e7828  cmp     [r8+4], r15b
0x1800e782c  jnz     short loc_1800E7861
0x1800e782e  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x1800e7835  mov     rcx, r14; this
0x1800e7838  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e783d  mov     edi, eax
0x1800e783f  test    eax, eax
0x1800e7841  jz      short loc_1800E7861
0x1800e7843  mov     rcx, [rsp+0C8h+var_88]
0x1800e7848  test    rcx, rcx
0x1800e784b  jz      short loc_1800E785C
0x1800e784d  mov     rax, [rcx]
0x1800e7850  mov     edx, r15d
0x1800e7853  mov     rax, [rax]
0x1800e7856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e785b  nop
0x1800e785c  jmp     loc_1800E7CA2
0x1800e7861  lea     r8, [rsi+98h]; void *
0x1800e7868  cmp     [r8+4], r15b
0x1800e786c  jnz     short loc_1800E78A1
0x1800e786e  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x1800e7875  mov     rcx, r14; this
0x1800e7878  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e787d  mov     edi, eax
0x1800e787f  test    eax, eax
0x1800e7881  jz      short loc_1800E78A1
0x1800e7883  mov     rcx, [rsp+0C8h+var_88]
0x1800e7888  test    rcx, rcx
0x1800e788b  jz      short loc_1800E789C
0x1800e788d  mov     rax, [rcx]
0x1800e7890  mov     edx, r15d
0x1800e7893  mov     rax, [rax]
0x1800e7896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e789b  nop
0x1800e789c  jmp     loc_1800E7CA2
0x1800e78a1  lea     r8, [rsi+0A0h]; void *
0x1800e78a8  cmp     [r8+4], r15b
0x1800e78ac  jnz     short loc_1800E78E1
0x1800e78ae  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x1800e78b5  mov     rcx, r14; this
0x1800e78b8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e78bd  mov     edi, eax
0x1800e78bf  test    eax, eax
0x1800e78c1  jz      short loc_1800E78E1
0x1800e78c3  mov     rcx, [rsp+0C8h+var_88]
0x1800e78c8  test    rcx, rcx
0x1800e78cb  jz      short loc_1800E78DC
0x1800e78cd  mov     rax, [rcx]
0x1800e78d0  mov     edx, r15d
0x1800e78d3  mov     rax, [rax]
0x1800e78d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e78db  nop
0x1800e78dc  jmp     loc_1800E7CA2
0x1800e78e1  lea     r8, [rsi+0A8h]; void *
0x1800e78e8  cmp     [r8+4], r15b
0x1800e78ec  jnz     short loc_1800E7921
0x1800e78ee  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x1800e78f5  mov     rcx, r14; this
0x1800e78f8  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e78fd  mov     edi, eax
0x1800e78ff  test    eax, eax
0x1800e7901  jz      short loc_1800E7921
0x1800e7903  mov     rcx, [rsp+0C8h+var_88]
0x1800e7908  test    rcx, rcx
0x1800e790b  jz      short loc_1800E791C
0x1800e790d  mov     rax, [rcx]
0x1800e7910  mov     edx, r15d
0x1800e7913  mov     rax, [rax]
0x1800e7916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e791b  nop
0x1800e791c  jmp     loc_1800E7CA2
0x1800e7921  lea     r8, [rsi+0B0h]; void *
0x1800e7928  cmp     [r8+4], r15b
0x1800e792c  jnz     short loc_1800E7961
0x1800e792e  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x1800e7935  mov     rcx, r14; this
0x1800e7938  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e793d  mov     edi, eax
0x1800e793f  test    eax, eax
0x1800e7941  jz      short loc_1800E7961
0x1800e7943  mov     rcx, [rsp+0C8h+var_88]
0x1800e7948  test    rcx, rcx
0x1800e794b  jz      short loc_1800E795C
0x1800e794d  mov     rax, [rcx]
0x1800e7950  mov     edx, r15d
0x1800e7953  mov     rax, [rax]
0x1800e7956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e795b  nop
0x1800e795c  jmp     loc_1800E7CA2
0x1800e7961  lea     r8, [rsi+0B8h]; void *
0x1800e7968  cmp     [r8+4], r15b
0x1800e796c  jnz     short loc_1800E79A1
0x1800e796e  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x1800e7975  mov     rcx, r14; this
0x1800e7978  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e797d  mov     edi, eax
0x1800e797f  test    eax, eax
0x1800e7981  jz      short loc_1800E79A1
0x1800e7983  mov     rcx, [rsp+0C8h+var_88]
0x1800e7988  test    rcx, rcx
0x1800e798b  jz      short loc_1800E799C
0x1800e798d  mov     rax, [rcx]
0x1800e7990  mov     edx, r15d
0x1800e7993  mov     rax, [rax]
0x1800e7996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e799b  nop
0x1800e799c  jmp     loc_1800E7CA2
  ... truncated ...
```
