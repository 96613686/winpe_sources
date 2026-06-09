# MDM_Policy_Result01_SystemServices02_InvokeCreateInstance

- ea: `0x18019cbac`
- end: `0x18019d48b`
- name: `MDM_Policy_Result01_SystemServices02_InvokeCreateInstance`
- size: `2271`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019cab0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18019cbac`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18019cd75`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019cdb2`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019cdef`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019ce2c`: `ConfigureIISAdminServiceStartupMode`
- `0x18019ce6c`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019ceac`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019ceec`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019cf2c`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019cf6c`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019cfac`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019cfec`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019d02c`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019d06c`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019d0ac`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019d0ec`: `ConfigureWebManagementServiceStartupMode`
- `0x18019d12c`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019d16c`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019d1ac`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019d1ec`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019d22c`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019d26c`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019d2ac`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019ccd5`: `CreateInstanceStart`
- `0x18019d3f2`: `CreateInstanceEnd`
- `0x18019cc1c`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-1A8h] BYREF
  char v9; // [rsp+48h] [rbp-1A0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-198h] BYREF
  char v11; // [rsp+78h] [rbp-170h]
  int v12; // [rsp+80h] [rbp-168h] BYREF
  char v13; // [rsp+84h] [rbp-164h]
  _BYTE v14[16]; // [rsp+88h] [rbp-160h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-150h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-138h] BYREF

  memset_0(&instance, 0, 0x110u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Result01_SystemServices02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180343FAE,
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
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
                 0x18u,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
          0x18u);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"ConfigureComputerBrowserServiceStartupMode",
                           (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupListenerServiceStartupMode",
                                (LONG *)&a2[1].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupProviderServiceStartupMode",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureIISAdminServiceStartupMode",
                                (LONG *)&a2[1].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInfraredMonitorServiceStartupMode",
                                (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInternetConnectionSharingServiceStartupMode",
                                (LONG *)&a2[2].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureLxssManagerServiceStartupMode",
                                (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureMicrosoftFTPServiceStartupMode",
                                (LONG *)&a2[2].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                (LONG *)&a2[2].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSimpleTCPIPServicesStartupMode",
                                (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                (LONG *)&a2[2].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSSDPDiscoveryServiceStartupMode",
                                (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureUPnPDeviceHostServiceStartupMode",
                                (LONG *)&a2[3].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWebManagementServiceStartupMode",
                                (LONG *)&a2[3].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                (LONG *)&a2[3].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                (LONG *)a2[3].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                (LONG *)&a2[3].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                (LONG *)&a2[3].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                (LONG *)&a2[4])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                (LONG *)&a2[4].classDecl)) != 0 )
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
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_SystemServices02_rtti, &instance);
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
      &word_180350096,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x18019cbac  mov     [rsp+arg_10], rsi
0x18019cbb1  mov     [rsp+arg_18], rdi
0x18019cbb6  push    r12
0x18019cbb8  push    r14
0x18019cbba  push    r15
0x18019cbbc  sub     rsp, 1D0h
0x18019cbc3  mov     rax, cs:__security_cookie
0x18019cbca  xor     rax, rsp
0x18019cbcd  mov     [rsp+1E8h+var_28], rax
0x18019cbd5  mov     rsi, rdx
0x18019cbd8  mov     r15, rcx
0x18019cbdb  xor     edx, edx; Val
0x18019cbdd  mov     r8d, 110h; Size
0x18019cbe3  lea     rcx, [rsp+1E8h+instance]; void *
0x18019cbeb  call    memset_0
0x18019cbf0  mov     [rsp+1E8h+var_168], 0
0x18019cbfb  mov     [rsp+1E8h+var_164], 0
0x18019cc03  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019cc0a  mov     [rsp+1E8h+var_198], rax
0x18019cc0f  lea     rax, [rsp+1E8h+var_168]
0x18019cc17  mov     [rsp+1E8h+var_190], rax
0x18019cc1c  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019cc23  mov     [rsp+1E8h+var_188], rax
0x18019cc28  lea     rcx, [rsp+1E8h+var_168]
0x18019cc30  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019cc35  mov     eax, cs:dword_180380B68
0x18019cc3b  cmp     eax, 5
0x18019cc3e  jbe     short loc_18019CCB4
0x18019cc40  mov     rdx, 200000000000h
0x18019cc4a  lea     rcx, dword_180380B68
0x18019cc51  call    _tlgKeywordOn
0x18019cc56  test    al, al
0x18019cc58  jz      short loc_18019CCB4
0x18019cc5a  cmp     [rsp+1E8h+var_164], 0
0x18019cc62  jz      short loc_18019CC96
0x18019cc64  cmp     [rsp+1E8h+var_150], 0
0x18019cc6c  jnz     short loc_18019CC8C
0x18019cc6e  cmp     [rsp+1E8h+var_14C], 0
0x18019cc76  jnz     short loc_18019CC8C
0x18019cc78  cmp     [rsp+1E8h+var_148], 0
0x18019cc80  jnz     short loc_18019CC8C
0x18019cc82  cmp     [rsp+1E8h+var_144], 0
0x18019cc8a  jz      short loc_18019CC96
0x18019cc8c  lea     r9, [rsp+1E8h+var_150]
0x18019cc94  jmp     short loc_18019CC99
0x18019cc96  xor     r9d, r9d
0x18019cc99  lea     r8, [rsp+1E8h+var_160]
0x18019cca1  lea     rdx, word_180343FAE
0x18019cca8  lea     rcx, dword_180380B68
0x18019ccaf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019ccb4  cmp     byte ptr [rsi+48h], 0
0x18019ccb8  jz      loc_18019D3EA
0x18019ccbe  mov     [rsp+1E8h+var_1A0], 0
0x18019ccc3  cmp     byte ptr [rsi+58h], 0
0x18019ccc7  jz      loc_18019D3EA
0x18019cccd  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019ccd1  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019ccd5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18019ccdc  lea     rcx, [rsp+1E8h+var_198]; this
0x18019cce1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019cce6  nop
0x18019cce7  mov     [rsp+1E8h+var_1A8], 0
0x18019ccf0  lea     rax, [rsp+1E8h+var_1A8]
0x18019ccf5  mov     [rsp+1E8h+var_1B8], rax
0x18019ccfa  mov     [rsp+1E8h+var_1C0], 4
0x18019cd02  mov     [rsp+1E8h+var_1C8], 18h
0x18019cd0a  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019cd11  mov     r8, [rsi+40h]
0x18019cd15  mov     rdx, [rsi+50h]
0x18019cd19  mov     rcx, r15
0x18019cd1c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019cd21  mov     edi, eax
0x18019cd23  test    eax, eax
0x18019cd25  jz      short loc_18019CD2C
0x18019cd27  jmp     loc_18019D3EF
0x18019cd2c  lea     rax, [rsp+1E8h+var_1A8]
0x18019cd31  mov     [rsp+1E8h+var_178], rax
0x18019cd36  mov     r12d, 1
0x18019cd3c  mov     [rsp+1E8h+var_170], r12b
0x18019cd41  mov     r14, [rsp+1E8h+var_1A8]
0x18019cd46  test    r14, r14
0x18019cd49  jnz     short loc_18019CD53
0x18019cd4b  mov     edi, r12d
0x18019cd4e  jmp     loc_18019D3EF
0x18019cd53  mov     r9d, 18h; unsigned int
0x18019cd59  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019cd60  mov     rdx, rsi; struct _MI_Instance *
0x18019cd63  mov     rcx, r14; this
0x18019cd66  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019cd6b  lea     r8, [rsi+60h]; void *
0x18019cd6f  cmp     [r8+4], r12b
0x18019cd73  jnz     short loc_18019CDA8
0x18019cd75  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019cd7c  mov     rcx, r14; this
0x18019cd7f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cd84  mov     edi, eax
0x18019cd86  test    eax, eax
0x18019cd88  jz      short loc_18019CDA8
0x18019cd8a  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cd8f  test    rcx, rcx
0x18019cd92  jz      short loc_18019CDA3
0x18019cd94  mov     rax, [rcx]
0x18019cd97  mov     edx, r12d
0x18019cd9a  mov     rax, [rax]
0x18019cd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cda2  nop
0x18019cda3  jmp     loc_18019D3EF
0x18019cda8  lea     r8, [rsi+68h]; void *
0x18019cdac  cmp     [r8+4], r12b
0x18019cdb0  jnz     short loc_18019CDE5
0x18019cdb2  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019cdb9  mov     rcx, r14; this
0x18019cdbc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cdc1  mov     edi, eax
0x18019cdc3  test    eax, eax
0x18019cdc5  jz      short loc_18019CDE5
0x18019cdc7  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cdcc  test    rcx, rcx
0x18019cdcf  jz      short loc_18019CDE0
0x18019cdd1  mov     rax, [rcx]
0x18019cdd4  mov     edx, r12d
0x18019cdd7  mov     rax, [rax]
0x18019cdda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cddf  nop
0x18019cde0  jmp     loc_18019D3EF
0x18019cde5  lea     r8, [rsi+70h]; void *
0x18019cde9  cmp     [r8+4], r12b
0x18019cded  jnz     short loc_18019CE22
0x18019cdef  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019cdf6  mov     rcx, r14; this
0x18019cdf9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cdfe  mov     edi, eax
0x18019ce00  test    eax, eax
0x18019ce02  jz      short loc_18019CE22
0x18019ce04  mov     rcx, [rsp+1E8h+var_1A8]
0x18019ce09  test    rcx, rcx
0x18019ce0c  jz      short loc_18019CE1D
0x18019ce0e  mov     rax, [rcx]
0x18019ce11  mov     edx, r12d
0x18019ce14  mov     rax, [rax]
0x18019ce17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ce1c  nop
0x18019ce1d  jmp     loc_18019D3EF
0x18019ce22  lea     r8, [rsi+78h]; void *
0x18019ce26  cmp     [r8+4], r12b
0x18019ce2a  jnz     short loc_18019CE5F
0x18019ce2c  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019ce33  mov     rcx, r14; this
0x18019ce36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ce3b  mov     edi, eax
0x18019ce3d  test    eax, eax
0x18019ce3f  jz      short loc_18019CE5F
0x18019ce41  mov     rcx, [rsp+1E8h+var_1A8]
0x18019ce46  test    rcx, rcx
0x18019ce49  jz      short loc_18019CE5A
0x18019ce4b  mov     rax, [rcx]
0x18019ce4e  mov     edx, r12d
0x18019ce51  mov     rax, [rax]
0x18019ce54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ce59  nop
0x18019ce5a  jmp     loc_18019D3EF
0x18019ce5f  lea     r8, [rsi+80h]; void *
0x18019ce66  cmp     [r8+4], r12b
0x18019ce6a  jnz     short loc_18019CE9F
0x18019ce6c  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019ce73  mov     rcx, r14; this
0x18019ce76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ce7b  mov     edi, eax
0x18019ce7d  test    eax, eax
0x18019ce7f  jz      short loc_18019CE9F
0x18019ce81  mov     rcx, [rsp+1E8h+var_1A8]
0x18019ce86  test    rcx, rcx
0x18019ce89  jz      short loc_18019CE9A
0x18019ce8b  mov     rax, [rcx]
0x18019ce8e  mov     edx, r12d
0x18019ce91  mov     rax, [rax]
0x18019ce94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ce99  nop
0x18019ce9a  jmp     loc_18019D3EF
0x18019ce9f  lea     r8, [rsi+88h]; void *
0x18019cea6  cmp     [r8+4], r12b
0x18019ceaa  jnz     short loc_18019CEDF
0x18019ceac  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019ceb3  mov     rcx, r14; this
0x18019ceb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cebb  mov     edi, eax
0x18019cebd  test    eax, eax
0x18019cebf  jz      short loc_18019CEDF
0x18019cec1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cec6  test    rcx, rcx
0x18019cec9  jz      short loc_18019CEDA
0x18019cecb  mov     rax, [rcx]
0x18019cece  mov     edx, r12d
0x18019ced1  mov     rax, [rax]
0x18019ced4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ced9  nop
0x18019ceda  jmp     loc_18019D3EF
0x18019cedf  lea     r8, [rsi+90h]; void *
0x18019cee6  cmp     [r8+4], r12b
0x18019ceea  jnz     short loc_18019CF1F
0x18019ceec  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019cef3  mov     rcx, r14; this
0x18019cef6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cefb  mov     edi, eax
0x18019cefd  test    eax, eax
0x18019ceff  jz      short loc_18019CF1F
0x18019cf01  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cf06  test    rcx, rcx
0x18019cf09  jz      short loc_18019CF1A
0x18019cf0b  mov     rax, [rcx]
0x18019cf0e  mov     edx, r12d
0x18019cf11  mov     rax, [rax]
0x18019cf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf19  nop
0x18019cf1a  jmp     loc_18019D3EF
0x18019cf1f  lea     r8, [rsi+98h]; void *
0x18019cf26  cmp     [r8+4], r12b
0x18019cf2a  jnz     short loc_18019CF5F
0x18019cf2c  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019cf33  mov     rcx, r14; this
0x18019cf36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cf3b  mov     edi, eax
0x18019cf3d  test    eax, eax
0x18019cf3f  jz      short loc_18019CF5F
0x18019cf41  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cf46  test    rcx, rcx
0x18019cf49  jz      short loc_18019CF5A
0x18019cf4b  mov     rax, [rcx]
0x18019cf4e  mov     edx, r12d
0x18019cf51  mov     rax, [rax]
0x18019cf54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf59  nop
0x18019cf5a  jmp     loc_18019D3EF
0x18019cf5f  lea     r8, [rsi+0A0h]; void *
0x18019cf66  cmp     [r8+4], r12b
0x18019cf6a  jnz     short loc_18019CF9F
0x18019cf6c  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019cf73  mov     rcx, r14; this
0x18019cf76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cf7b  mov     edi, eax
0x18019cf7d  test    eax, eax
0x18019cf7f  jz      short loc_18019CF9F
0x18019cf81  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cf86  test    rcx, rcx
0x18019cf89  jz      short loc_18019CF9A
0x18019cf8b  mov     rax, [rcx]
0x18019cf8e  mov     edx, r12d
0x18019cf91  mov     rax, [rax]
0x18019cf94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf99  nop
0x18019cf9a  jmp     loc_18019D3EF
0x18019cf9f  lea     r8, [rsi+0A8h]; void *
0x18019cfa6  cmp     [r8+4], r12b
0x18019cfaa  jnz     short loc_18019CFDF
0x18019cfac  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019cfb3  mov     rcx, r14; this
0x18019cfb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cfbb  mov     edi, eax
0x18019cfbd  test    eax, eax
0x18019cfbf  jz      short loc_18019CFDF
0x18019cfc1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cfc6  test    rcx, rcx
0x18019cfc9  jz      short loc_18019CFDA
0x18019cfcb  mov     rax, [rcx]
0x18019cfce  mov     edx, r12d
0x18019cfd1  mov     rax, [rax]
0x18019cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cfd9  nop
0x18019cfda  jmp     loc_18019D3EF
0x18019cfdf  lea     r8, [rsi+0B0h]; void *
0x18019cfe6  cmp     [r8+4], r12b
0x18019cfea  jnz     short loc_18019D01F
0x18019cfec  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019cff3  mov     rcx, r14; this
0x18019cff6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cffb  mov     edi, eax
0x18019cffd  test    eax, eax
0x18019cfff  jz      short loc_18019D01F
0x18019d001  mov     rcx, [rsp+1E8h+var_1A8]
0x18019d006  test    rcx, rcx
0x18019d009  jz      short loc_18019D01A
0x18019d00b  mov     rax, [rcx]
0x18019d00e  mov     edx, r12d
0x18019d011  mov     rax, [rax]
0x18019d014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d019  nop
0x18019d01a  jmp     loc_18019D3EF
0x18019d01f  lea     r8, [rsi+0B8h]; void *
0x18019d026  cmp     [r8+4], r12b
0x18019d02a  jnz     short loc_18019D05F
0x18019d02c  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019d033  mov     rcx, r14; this
0x18019d036  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019d03b  mov     edi, eax
0x18019d03d  test    eax, eax
0x18019d03f  jz      short loc_18019D05F
0x18019d041  mov     rcx, [rsp+1E8h+var_1A8]
0x18019d046  test    rcx, rcx
0x18019d049  jz      short loc_18019D05A
0x18019d04b  mov     rax, [rcx]
  ... truncated ...
```
