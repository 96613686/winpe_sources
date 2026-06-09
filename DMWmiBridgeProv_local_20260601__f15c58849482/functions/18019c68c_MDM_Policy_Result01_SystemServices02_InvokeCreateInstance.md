# MDM_Policy_Result01_SystemServices02_InvokeCreateInstance

- ea: `0x18019c68c`
- end: `0x18019cf6c`
- name: `MDM_Policy_Result01_SystemServices02_InvokeCreateInstance`
- size: `2272`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019c5d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18019c68c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18019c855`: `ConfigureComputerBrowserServiceStartupMode`
- `0x18019c892`: `ConfigureHomeGroupListenerServiceStartupMode`
- `0x18019c8cf`: `ConfigureHomeGroupProviderServiceStartupMode`
- `0x18019c90c`: `ConfigureIISAdminServiceStartupMode`
- `0x18019c94c`: `ConfigureInfraredMonitorServiceStartupMode`
- `0x18019c98c`: `ConfigureInternetConnectionSharingServiceStartupMode`
- `0x18019c9cc`: `ConfigureLxssManagerServiceStartupMode`
- `0x18019ca0c`: `ConfigureMicrosoftFTPServiceStartupMode`
- `0x18019ca4c`: `ConfigureRemoteProcedureCallLocatorServiceStartupMode`
- `0x18019ca8c`: `ConfigureRoutingAndRemoteAccessServiceStartupMode`
- `0x18019cacc`: `ConfigureSimpleTCPIPServicesStartupMode`
- `0x18019cb0c`: `ConfigureSpecialAdministrationConsoleHelperServiceStartupMode`
- `0x18019cb4c`: `ConfigureSSDPDiscoveryServiceStartupMode`
- `0x18019cb8c`: `ConfigureUPnPDeviceHostServiceStartupMode`
- `0x18019cbcc`: `ConfigureWebManagementServiceStartupMode`
- `0x18019cc0c`: `ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode`
- `0x18019cc4c`: `ConfigureWindowsMobileHotspotServiceStartupMode`
- `0x18019cc8c`: `ConfigureWorldWideWebPublishingServiceStartupMode`
- `0x18019cccc`: `ConfigureXboxAccessoryManagementServiceStartupMode`
- `0x18019cd0c`: `ConfigureXboxLiveAuthManagerServiceStartupMode`
- `0x18019cd4c`: `ConfigureXboxLiveGameSaveServiceStartupMode`
- `0x18019cd8c`: `ConfigureXboxLiveNetworkingServiceStartupMode`
- `0x18019c7b5`: `CreateInstanceStart`
- `0x18019ced2`: `CreateInstanceEnd`
- `0x18019c6fc`: `MDM_Policy_Result01_SystemServices02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_SystemServices02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               self,
                               a2[1].serverName,
                               a2[1].ft,
                               &MDM_Policy_Result01_SystemServices02_NodeList,
                               24,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_SystemServices02_NodeList,
          0x18u);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                           v6,
                           L"ConfigureComputerBrowserServiceStartupMode",
                           a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupListenerServiceStartupMode",
                                &a2[1].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureHomeGroupProviderServiceStartupMode",
                                &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureIISAdminServiceStartupMode",
                                &a2[1].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInfraredMonitorServiceStartupMode",
                                &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureInternetConnectionSharingServiceStartupMode",
                                &a2[2].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureLxssManagerServiceStartupMode",
                                &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureMicrosoftFTPServiceStartupMode",
                                &a2[2].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRemoteProcedureCallLocatorServiceStartupMode",
                                a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureRoutingAndRemoteAccessServiceStartupMode",
                                &a2[2].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSimpleTCPIPServicesStartupMode",
                                &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSpecialAdministrationConsoleHelperServiceStartupMode",
                                &a2[2].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureSSDPDiscoveryServiceStartupMode",
                                &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureUPnPDeviceHostServiceStartupMode",
                                &a2[3].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWebManagementServiceStartupMode",
                                &a2[3].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMediaPlayerNetworkSharingServiceStartupMode",
                                &a2[3].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWindowsMobileHotspotServiceStartupMode",
                                a2[3].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureWorldWideWebPublishingServiceStartupMode",
                                &a2[3].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxAccessoryManagementServiceStartupMode",
                                &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveAuthManagerServiceStartupMode",
                                &a2[3].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveGameSaveServiceStartupMode",
                                &a2[4])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureXboxLiveNetworkingServiceStartupMode",
                                &a2[4].classDecl)) != MI_RESULT_OK )
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
      &word_180350096,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18019c68c  mov     [rsp+arg_10], rsi
0x18019c691  mov     [rsp+arg_18], rdi
0x18019c696  push    r12
0x18019c698  push    r14
0x18019c69a  push    r15
0x18019c69c  sub     rsp, 1D0h
0x18019c6a3  mov     rax, cs:__security_cookie
0x18019c6aa  xor     rax, rsp
0x18019c6ad  mov     [rsp+1E8h+var_28], rax
0x18019c6b5  mov     rsi, rdx
0x18019c6b8  mov     r15, rcx
0x18019c6bb  xor     edx, edx; Val
0x18019c6bd  mov     r8d, 110h; Size
0x18019c6c3  lea     rcx, [rsp+1E8h+instance]; void *
0x18019c6cb  call    memset_0
0x18019c6d0  mov     [rsp+1E8h+var_168], 0
0x18019c6db  mov     [rsp+1E8h+var_164], 0
0x18019c6e3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019c6ea  mov     [rsp+1E8h+var_198], rax
0x18019c6ef  lea     rax, [rsp+1E8h+var_168]
0x18019c6f7  mov     [rsp+1E8h+var_190], rax
0x18019c6fc  lea     rax, aMdmPolicyResul_19; "MDM_Policy_Result01_SystemServices02"
0x18019c703  mov     [rsp+1E8h+var_188], rax
0x18019c708  lea     rcx, [rsp+1E8h+var_168]
0x18019c710  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18019c715  mov     eax, cs:dword_180380B68
0x18019c71b  cmp     eax, 5
0x18019c71e  jbe     short loc_18019C794
0x18019c720  mov     rdx, 200000000000h
0x18019c72a  lea     rcx, dword_180380B68
0x18019c731  call    _tlgKeywordOn
0x18019c736  test    al, al
0x18019c738  jz      short loc_18019C794
0x18019c73a  cmp     [rsp+1E8h+var_164], 0
0x18019c742  jz      short loc_18019C776
0x18019c744  cmp     [rsp+1E8h+var_150], 0
0x18019c74c  jnz     short loc_18019C76C
0x18019c74e  cmp     [rsp+1E8h+var_14C], 0
0x18019c756  jnz     short loc_18019C76C
0x18019c758  cmp     [rsp+1E8h+var_148], 0
0x18019c760  jnz     short loc_18019C76C
0x18019c762  cmp     [rsp+1E8h+var_144], 0
0x18019c76a  jz      short loc_18019C776
0x18019c76c  lea     r9, [rsp+1E8h+var_150]
0x18019c774  jmp     short loc_18019C779
0x18019c776  xor     r9d, r9d
0x18019c779  lea     r8, [rsp+1E8h+var_160]
0x18019c781  lea     rdx, word_180343FAE
0x18019c788  lea     rcx, dword_180380B68
0x18019c78f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019c794  cmp     byte ptr [rsi+48h], 0
0x18019c798  jz      loc_18019CECA
0x18019c79e  mov     [rsp+1E8h+var_1A0], 0
0x18019c7a3  cmp     byte ptr [rsi+58h], 0
0x18019c7a7  jz      loc_18019CECA
0x18019c7ad  mov     r9, [rsi+40h]; unsigned __int16 *
0x18019c7b1  mov     r8, [rsi+50h]; unsigned __int16 *
0x18019c7b5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18019c7bc  lea     rcx, [rsp+1E8h+var_198]; this
0x18019c7c1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019c7c6  nop
0x18019c7c7  mov     [rsp+1E8h+var_1A8], 0
0x18019c7d0  lea     rax, [rsp+1E8h+var_1A8]
0x18019c7d5  mov     [rsp+1E8h+var_1B8], rax
0x18019c7da  mov     [rsp+1E8h+var_1C0], 4
0x18019c7e2  mov     [rsp+1E8h+var_1C8], 18h
0x18019c7ea  lea     r9, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_SystemServices02_NodeList
0x18019c7f1  mov     r8, [rsi+40h]
0x18019c7f5  mov     rdx, [rsi+50h]
0x18019c7f9  mov     rcx, r15
0x18019c7fc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18019c801  mov     edi, eax
0x18019c803  test    eax, eax
0x18019c805  jz      short loc_18019C80C
0x18019c807  jmp     loc_18019CECF
0x18019c80c  lea     rax, [rsp+1E8h+var_1A8]
0x18019c811  mov     [rsp+1E8h+var_178], rax
0x18019c816  mov     r12d, 1
0x18019c81c  mov     [rsp+1E8h+var_170], r12b
0x18019c821  mov     r14, [rsp+1E8h+var_1A8]
0x18019c826  test    r14, r14
0x18019c829  jnz     short loc_18019C833
0x18019c82b  mov     edi, r12d
0x18019c82e  jmp     loc_18019CECF
0x18019c833  mov     r9d, 18h; unsigned int
0x18019c839  lea     r8, ?MDM_Policy_Result01_SystemServices02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18019c840  mov     rdx, rsi; struct _MI_Instance *
0x18019c843  mov     rcx, r14; this
0x18019c846  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019c84b  lea     r8, [rsi+60h]; void *
0x18019c84f  cmp     [r8+4], r12b
0x18019c853  jnz     short loc_18019C888
0x18019c855  lea     rdx, aConfigurecompu; "ConfigureComputerBrowserServiceStartupM"...
0x18019c85c  mov     rcx, r14; this
0x18019c85f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c864  mov     edi, eax
0x18019c866  test    eax, eax
0x18019c868  jz      short loc_18019C888
0x18019c86a  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c86f  test    rcx, rcx
0x18019c872  jz      short loc_18019C883
0x18019c874  mov     rax, [rcx]
0x18019c877  mov     edx, r12d
0x18019c87a  mov     rax, [rax]
0x18019c87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c882  nop
0x18019c883  jmp     loc_18019CECF
0x18019c888  lea     r8, [rsi+68h]; void *
0x18019c88c  cmp     [r8+4], r12b
0x18019c890  jnz     short loc_18019C8C5
0x18019c892  lea     rdx, aConfigurehomeg_0; "ConfigureHomeGroupListenerServiceStartu"...
0x18019c899  mov     rcx, r14; this
0x18019c89c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c8a1  mov     edi, eax
0x18019c8a3  test    eax, eax
0x18019c8a5  jz      short loc_18019C8C5
0x18019c8a7  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c8ac  test    rcx, rcx
0x18019c8af  jz      short loc_18019C8C0
0x18019c8b1  mov     rax, [rcx]
0x18019c8b4  mov     edx, r12d
0x18019c8b7  mov     rax, [rax]
0x18019c8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c8bf  nop
0x18019c8c0  jmp     loc_18019CECF
0x18019c8c5  lea     r8, [rsi+70h]; void *
0x18019c8c9  cmp     [r8+4], r12b
0x18019c8cd  jnz     short loc_18019C902
0x18019c8cf  lea     rdx, aConfigurehomeg; "ConfigureHomeGroupProviderServiceStartu"...
0x18019c8d6  mov     rcx, r14; this
0x18019c8d9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c8de  mov     edi, eax
0x18019c8e0  test    eax, eax
0x18019c8e2  jz      short loc_18019C902
0x18019c8e4  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c8e9  test    rcx, rcx
0x18019c8ec  jz      short loc_18019C8FD
0x18019c8ee  mov     rax, [rcx]
0x18019c8f1  mov     edx, r12d
0x18019c8f4  mov     rax, [rax]
0x18019c8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c8fc  nop
0x18019c8fd  jmp     loc_18019CECF
0x18019c902  lea     r8, [rsi+78h]; void *
0x18019c906  cmp     [r8+4], r12b
0x18019c90a  jnz     short loc_18019C93F
0x18019c90c  lea     rdx, aConfigureiisad; "ConfigureIISAdminServiceStartupMode"
0x18019c913  mov     rcx, r14; this
0x18019c916  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c91b  mov     edi, eax
0x18019c91d  test    eax, eax
0x18019c91f  jz      short loc_18019C93F
0x18019c921  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c926  test    rcx, rcx
0x18019c929  jz      short loc_18019C93A
0x18019c92b  mov     rax, [rcx]
0x18019c92e  mov     edx, r12d
0x18019c931  mov     rax, [rax]
0x18019c934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c939  nop
0x18019c93a  jmp     loc_18019CECF
0x18019c93f  lea     r8, [rsi+80h]; void *
0x18019c946  cmp     [r8+4], r12b
0x18019c94a  jnz     short loc_18019C97F
0x18019c94c  lea     rdx, aConfigureinfra; "ConfigureInfraredMonitorServiceStartupM"...
0x18019c953  mov     rcx, r14; this
0x18019c956  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c95b  mov     edi, eax
0x18019c95d  test    eax, eax
0x18019c95f  jz      short loc_18019C97F
0x18019c961  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c966  test    rcx, rcx
0x18019c969  jz      short loc_18019C97A
0x18019c96b  mov     rax, [rcx]
0x18019c96e  mov     edx, r12d
0x18019c971  mov     rax, [rax]
0x18019c974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c979  nop
0x18019c97a  jmp     loc_18019CECF
0x18019c97f  lea     r8, [rsi+88h]; void *
0x18019c986  cmp     [r8+4], r12b
0x18019c98a  jnz     short loc_18019C9BF
0x18019c98c  lea     rdx, aConfigureinter; "ConfigureInternetConnectionSharingServi"...
0x18019c993  mov     rcx, r14; this
0x18019c996  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c99b  mov     edi, eax
0x18019c99d  test    eax, eax
0x18019c99f  jz      short loc_18019C9BF
0x18019c9a1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c9a6  test    rcx, rcx
0x18019c9a9  jz      short loc_18019C9BA
0x18019c9ab  mov     rax, [rcx]
0x18019c9ae  mov     edx, r12d
0x18019c9b1  mov     rax, [rax]
0x18019c9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c9b9  nop
0x18019c9ba  jmp     loc_18019CECF
0x18019c9bf  lea     r8, [rsi+90h]; void *
0x18019c9c6  cmp     [r8+4], r12b
0x18019c9ca  jnz     short loc_18019C9FF
0x18019c9cc  lea     rdx, aConfigurelxssm; "ConfigureLxssManagerServiceStartupMode"
0x18019c9d3  mov     rcx, r14; this
0x18019c9d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019c9db  mov     edi, eax
0x18019c9dd  test    eax, eax
0x18019c9df  jz      short loc_18019C9FF
0x18019c9e1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019c9e6  test    rcx, rcx
0x18019c9e9  jz      short loc_18019C9FA
0x18019c9eb  mov     rax, [rcx]
0x18019c9ee  mov     edx, r12d
0x18019c9f1  mov     rax, [rax]
0x18019c9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c9f9  nop
0x18019c9fa  jmp     loc_18019CECF
0x18019c9ff  lea     r8, [rsi+98h]; void *
0x18019ca06  cmp     [r8+4], r12b
0x18019ca0a  jnz     short loc_18019CA3F
0x18019ca0c  lea     rdx, aConfiguremicro_0; "ConfigureMicrosoftFTPServiceStartupMode"
0x18019ca13  mov     rcx, r14; this
0x18019ca16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ca1b  mov     edi, eax
0x18019ca1d  test    eax, eax
0x18019ca1f  jz      short loc_18019CA3F
0x18019ca21  mov     rcx, [rsp+1E8h+var_1A8]
0x18019ca26  test    rcx, rcx
0x18019ca29  jz      short loc_18019CA3A
0x18019ca2b  mov     rax, [rcx]
0x18019ca2e  mov     edx, r12d
0x18019ca31  mov     rax, [rax]
0x18019ca34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ca39  nop
0x18019ca3a  jmp     loc_18019CECF
0x18019ca3f  lea     r8, [rsi+0A0h]; void *
0x18019ca46  cmp     [r8+4], r12b
0x18019ca4a  jnz     short loc_18019CA7F
0x18019ca4c  lea     rdx, aConfigureremot; "ConfigureRemoteProcedureCallLocatorServ"...
0x18019ca53  mov     rcx, r14; this
0x18019ca56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ca5b  mov     edi, eax
0x18019ca5d  test    eax, eax
0x18019ca5f  jz      short loc_18019CA7F
0x18019ca61  mov     rcx, [rsp+1E8h+var_1A8]
0x18019ca66  test    rcx, rcx
0x18019ca69  jz      short loc_18019CA7A
0x18019ca6b  mov     rax, [rcx]
0x18019ca6e  mov     edx, r12d
0x18019ca71  mov     rax, [rax]
0x18019ca74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ca79  nop
0x18019ca7a  jmp     loc_18019CECF
0x18019ca7f  lea     r8, [rsi+0A8h]; void *
0x18019ca86  cmp     [r8+4], r12b
0x18019ca8a  jnz     short loc_18019CABF
0x18019ca8c  lea     rdx, aConfigurerouti; "ConfigureRoutingAndRemoteAccessServiceS"...
0x18019ca93  mov     rcx, r14; this
0x18019ca96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019ca9b  mov     edi, eax
0x18019ca9d  test    eax, eax
0x18019ca9f  jz      short loc_18019CABF
0x18019caa1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019caa6  test    rcx, rcx
0x18019caa9  jz      short loc_18019CABA
0x18019caab  mov     rax, [rcx]
0x18019caae  mov     edx, r12d
0x18019cab1  mov     rax, [rax]
0x18019cab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cab9  nop
0x18019caba  jmp     loc_18019CECF
0x18019cabf  lea     r8, [rsi+0B0h]; void *
0x18019cac6  cmp     [r8+4], r12b
0x18019caca  jnz     short loc_18019CAFF
0x18019cacc  lea     rdx, aConfiguresimpl; "ConfigureSimpleTCPIPServicesStartupMode"
0x18019cad3  mov     rcx, r14; this
0x18019cad6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cadb  mov     edi, eax
0x18019cadd  test    eax, eax
0x18019cadf  jz      short loc_18019CAFF
0x18019cae1  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cae6  test    rcx, rcx
0x18019cae9  jz      short loc_18019CAFA
0x18019caeb  mov     rax, [rcx]
0x18019caee  mov     edx, r12d
0x18019caf1  mov     rax, [rax]
0x18019caf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019caf9  nop
0x18019cafa  jmp     loc_18019CECF
0x18019caff  lea     r8, [rsi+0B8h]; void *
0x18019cb06  cmp     [r8+4], r12b
0x18019cb0a  jnz     short loc_18019CB3F
0x18019cb0c  lea     rdx, aConfigurespeci; "ConfigureSpecialAdministrationConsoleHe"...
0x18019cb13  mov     rcx, r14; this
0x18019cb16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18019cb1b  mov     edi, eax
0x18019cb1d  test    eax, eax
0x18019cb1f  jz      short loc_18019CB3F
0x18019cb21  mov     rcx, [rsp+1E8h+var_1A8]
0x18019cb26  test    rcx, rcx
0x18019cb29  jz      short loc_18019CB3A
0x18019cb2b  mov     rax, [rcx]
  ... truncated ...
```
