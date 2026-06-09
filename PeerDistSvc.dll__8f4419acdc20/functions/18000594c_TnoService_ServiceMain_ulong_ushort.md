# TnoService::ServiceMain(ulong,ushort * *)

- ea: `0x18000594c`
- end: `0x1800069ce`
- name: `?ServiceMain@TnoService@@QEAAJKPEAPEAG@Z`
- size: `4226`
- prototype: `__int64 __fastcall(TnoService *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `32`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004250`

## callees

- `0x1800034a4`
- `0x180004374`
- `0x180004b74`
- `0x18000573c`
- `0x18000594c`
- `0x1800069d4`
- `0x18000801c`
- `0x180008168`
- `0x180008218`
- `0x180008290`
- `0x180008310`
- `0x180009ec4`
- `0x18000e840`
- `0x18002155c`
- `0x18002babc`
- `0x180036a5c`
- `0x180097738`
- `0x1800a28b4`
- `0x1800abbf4`
- `0x1800ef7f4`
- `0x1800f3658`
- `0x180103be8`
- `0x180113b64`
- `0x180114020`
- `0x1801140e0`
- `0x180118f2c`
- `0x180120d2c`
- `0x18012655c`
- `0x18012cff0`
- `0x180133a2c`
- `0x18013668c`
- `0x180159010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005a3d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006874`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005a3d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006874`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800059d9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800059d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000687e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000687e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18000690b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18000690b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000684c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000684c`
- `ntdll!EtwEventRegister` at `0x180005b58`
- `ntdll!EtwEventRegister` at `0x180005b58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TnoService::ServiceMain(TnoService *this, int a2, const WCHAR **a3)
{
  CHostedCacheMsgEncoding *v6; // rcx
  const WCHAR *v7; // rax
  SERVICE_STATUS_HANDLE v8; // rax
  DWORD LastError; // eax
  signed int inited; // ebx
  DWORD v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  CHostedCacheMsgEncoding *v17; // rcx
  unsigned int v18; // eax
  int v19; // eax
  CHostedCacheMsgEncoding *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // ecx
  unsigned int v24; // eax
  bool v25; // sf
  _QWORD *v26; // r13
  int v27; // eax
  CHostedCacheMsgEncoding *v28; // rcx
  CRoamingMonitor *v29; // rax
  CRoamingMonitor *v30; // rax
  CHostedCacheMsgEncoding *v31; // rcx
  __int64 v32; // rdx
  CHostedCacheMsgEncoding *v33; // rcx
  __int64 v34; // rdx
  int PerfCounters; // eax
  int v36; // eax
  int v37; // r14d
  int v38; // eax
  int v39; // ecx
  HPOWERNOTIFY *v40; // r14
  __int64 v41; // rcx
  void *v42; // rcx
  DWORD v43; // eax
  int v44; // r15d
  CHostedCacheMsgEncoding *v45; // rcx
  DWORD v46; // eax
  __int64 v47; // [rsp+40h] [rbp-29h] BYREF
  __int64 v48; // [rsp+48h] [rbp-21h] BYREF
  __int64 v49; // [rsp+50h] [rbp-19h] BYREF
  struct IPeerDistADLoader *v50; // [rsp+58h] [rbp-11h] BYREF
  struct ITnoCfgMgr *v51; // [rsp+60h] [rbp-9h] BYREF
  struct ITnoNetCostMonitor *v52; // [rsp+68h] [rbp-1h] BYREF
  const WCHAR *v53; // [rsp+70h] [rbp+7h]
  __int64 v54; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v7 = *a3;
    v53 = v7;
    if ( v7 )
    {
      v8 = RegisterServiceCtrlHandlerExW(v7, ServiceCtrlHandler, this);
      *((_QWORD *)this + 6) = v8;
      if ( !v8 )
      {
        LastError = GetLastError();
        inited = LastError;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            12,
            WPP_09eff81643953ecc218449769581d5a4_Traceguids,
            this,
            LastError);
        }
LABEL_12:
        if ( inited > 0 )
          return (unsigned __int16)inited | 0x80070000;
        return (unsigned int)inited;
      }
      if ( !SetServiceStatus(v8, (LPSERVICE_STATUS)this + 2) )
      {
        v12 = GetLastError();
        inited = v12;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v12);
        }
        goto LABEL_12;
      }
      PeerDistTelemetryInitialize();
      v14 = McGenEventRegister_EtwEventRegister(
              &MICROSOFT_PEERDIST_EVENTS_PROVIDER,
              v13,
              MICROSOFT_PEERDIST_EVENTS_PROVIDER_Context,
              MICROSOFT_PEERDIST_EVENTS_PROVIDER_Context);
      if ( v14
        && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v14);
      }
      v16 = McGenEventRegister_EtwEventRegister(
              MICROSOFT_PEERDIST_MONITORING_PROVIDER,
              v15,
              &MICROSOFT_PEERDIST_MONITORING_PROVIDER_Context,
              &MICROSOFT_PEERDIST_MONITORING_PROVIDER_Context);
      if ( v16 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
LABEL_31:
          if ( (Microsoft_Windows_BranchCacheMonitoringEnableBits & 1) != 0 )
          {
            McTemplateU0zq_EtwEventWriteTransfer(v17, ProviderArrivalEvent);
            v17 = WPP_GLOBAL_Control;
          }
          if ( !Microsoft_Windows_Networking_CorrelationHandle )
          {
            v18 = EtwEventRegister(
                    Microsoft_Windows_Networking_CorrelationId,
                    Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                    0,
                    &Microsoft_Windows_Networking_CorrelationHandle);
            if ( v18 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                goto LABEL_45;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v18);
                v17 = WPP_GLOBAL_Control;
              }
LABEL_41:
              if ( v17 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)v17 + 27) & 0x800) != 0
                && *((_BYTE *)v17 + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)v17 + 12), 17, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
LABEL_45:
              v50 = 0;
              v19 = IPeerDistADLoader::CreateSingletonInstance(&v50);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 18;
                goto LABEL_50;
              }
              *((_QWORD *)this + 57) = v50;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v51 = 0;
              v19 = ITnoCfgMgr::Create(&v51);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 20;
                goto LABEL_50;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 144, v51);
              v23 = (unsigned int)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v24 = ICacheMgr::Create(v23, &v52);
              inited = v24;
              if ( v24 )
              {
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    22,
                    WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                    v24);
                }
                v25 = inited < 0;
                if ( inited <= 0 )
                {
LABEL_235:
                  if ( !v25 )
                  {
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 32LL))(*((_QWORD *)this + 48));
                    *((_DWORD *)this + 16) = 69;
                    v38 = 0;
                    v39 = 4;
                    v40 = (HPOWERNOTIFY *)((char *)this + 88);
                    goto LABEL_249;
                  }
LABEL_242:
                  v41 = *((_QWORD *)this + 48);
                  if ( v41 )
                  {
                    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, (unsigned int)inited);
                    *((_BYTE *)this + 137) = 1;
                  }
                  if ( *((_DWORD *)this + 35) )
                    TnoService::ShutdownService(this);
                  v40 = (HPOWERNOTIFY *)((char *)this + 88);
                  v42 = (void *)*((_QWORD *)this + 11);
                  if ( v42 )
                  {
                    PowerSettingUnregisterNotification(v42);
                    *v40 = 0;
                  }
                  *((_DWORD *)this + 18) = TnoWin32ErrFromHR(inited);
                  v38 = 1066;
                  v39 = 1;
LABEL_249:
                  *((_DWORD *)this + 15) = v39;
                  *((_DWORD *)this + 17) = v38;
                  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 6), (LPSERVICE_STATUS)this + 2) )
                  {
                    v45 = WPP_GLOBAL_Control;
                  }
                  else
                  {
                    v43 = GetLastError();
                    v44 = v43;
                    v45 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        55,
                        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                        v43);
                      v45 = WPP_GLOBAL_Control;
                    }
                    if ( inited < 0 )
                      goto LABEL_267;
                    if ( v44 > 0 )
                      inited = (unsigned __int16)v44 | 0x80070000;
                    else
                      inited = v44;
                  }
                  if ( inited >= 0 )
                  {
                    v46 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 1u, *((HANDLE *)this + 6), v40);
                    if ( v46 )
                    {
                      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                      {
                        WPP_SF_qD(
                          *((_QWORD *)WPP_GLOBAL_Control + 12),
                          56,
                          WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                          this,
                          v46);
                      }
                      *v40 = 0;
                    }
                    v45 = WPP_GLOBAL_Control;
                  }
LABEL_267:
                  if ( v45 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)v45 + 27) & 0x800) != 0
                    && *((_BYTE *)v45 + 105) >= 4u )
                  {
                    WPP_SF_(*((_QWORD *)v45 + 12), 57, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                  }
                  return (unsigned int)inited;
                }
                inited = (unsigned __int16)inited;
                goto LABEL_72;
              }
              SmartPointer<CHostedCacheListManager>::Release((char *)this + 168);
              *((_QWORD *)this + 21) = v52;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v19 = DiscoveryProviderProxy::Create(&v52);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 24;
                goto LABEL_50;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 192, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v19 = ISecurityManager::Create(&v52);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 26;
                goto LABEL_50;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 216, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v19 = ITnoDriverLayer::Create(&v52);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 28;
                goto LABEL_50;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 336, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v19 = ITnoPublisher::Create(&v52);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 30;
                goto LABEL_50;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 240, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              v19 = ITnoDownldMgr::Create(&v52);
              inited = v19;
              if ( v19 < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 32;
                goto LABEL_50;
              }
              v26 = (_QWORD *)((char *)this + 264);
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 264, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              inited = ITnoRetrievalMgr::CreateInstance(&v52);
              if ( inited < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 34;
                goto LABEL_127;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 288, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              inited = ITnoHostedCacheMgr::Create(&v52);
              if ( inited < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 36;
                goto LABEL_127;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 360, v52);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              inited = ITnoLoggingMgr::Create((struct ITnoLoggingMgr **)this + 48);
              if ( inited < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 38;
                goto LABEL_127;
              }
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v27 = ITnoNetworkCfg::Create((struct ITnoNetworkCfg **)this + 54);
              inited = v27;
              if ( v27 )
              {
                if ( v27 <= 0 )
                  goto LABEL_234;
                inited = (unsigned __int16)v27;
LABEL_72:
                inited |= 0x80070000;
LABEL_234:
                v25 = inited < 0;
                goto LABEL_235;
              }
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                v28 = WPP_GLOBAL_Control;
              }
              if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)v28 + 27) & 0x10000000) != 0
                && *((_BYTE *)v28 + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)v28 + 12), 14, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
              }
              v29 = (CRoamingMonitor *)operator new(0x100u, (const struct std::nothrow_t *)std::nothrow);
              if ( v29 && (v30 = CRoamingMonitor::CRoamingMonitor(v29)) != 0 )
              {
                inited = 0;
              }
              else
              {
                v30 = 0;
                inited = -2147024882;
              }
              if ( inited < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v21 = 41;
                goto LABEL_127;
              }
              std::auto_ptr<IPeerDiscovery>::reset((char *)this + 408, v30);
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
              }
              v52 = 0;
              inited = ITnoNetCostMonitor::Create(&v52);
              if ( inited >= 0 )
              {
                std::auto_ptr<IPeerDiscovery>::reset((char *)this + 480, v52);
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                }
                inited = CTnoRPCServerImpl::InstantiateSingleton();
                if ( inited >= 0 )
                {
                  std::auto_ptr<IPeerDiscovery>::reset((char *)this + 312, CTnoRPCServerImpl::s_pSingleton);
                  *((_QWORD *)this + 63) = *((_QWORD *)this + 18);
                  *((_QWORD *)this + 64) = *((_QWORD *)this + 21);
                  *((_QWORD *)this + 65) = *((_QWORD *)this + 24);
                  *((_QWORD *)this + 66) = *((_QWORD *)this + 27);
                  *((_QWORD *)this + 67) = *((_QWORD *)this + 42);
                  *((_QWORD *)this + 68) = *((_QWORD *)this + 30);
                  *((_QWORD *)this + 69) = *v26;
                  *((_QWORD *)this + 70) = *((_QWORD *)this + 36);
                  *((_QWORD *)this + 71) = *((_QWORD *)this + 39);
                  *((_QWORD *)this + 72) = *((_QWORD *)this + 45);
                  *((_QWORD *)this + 73) = *((_QWORD *)this + 48);
                  *((_QWORD *)this + 74) = *((_QWORD *)this + 51);
                  *((_QWORD *)this + 75) = *((_QWORD *)this + 54);
                  *((_BYTE *)this + 656) = 0;
                  *((_BYTE *)this + 657) = BYTE1(v54);
                  *(_DWORD *)((char *)this + 658) = 0;
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 46, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                  }
                  v47 = 0;
                  inited = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 21) + 16LL))(
                             *((_QWORD *)this + 21),
                             &IID_HandleMgr,
                             &v47);
                  if ( inited >= 0 )
                  {
                    v54 = 0;
                    inited = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 36) + 32LL))(
                               *((_QWORD *)this + 36),
                               &v54);
                    if ( inited >= 0 )
                    {
                      v48 = 0;
                      inited = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)*v26 + 16LL))(
                                 *v26,
                                 &IID_PUITracker,
                                 &v48);
                      if ( inited >= 0 )
                      {
                        v49 = 0;
                        inited = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)*v26 + 16LL))(
                                   *v26,
                                   &IID_NetworkObserver,
                                   &v49);
                        if ( inited >= 0 )
                        {
                          *((_QWORD *)this + 80) = (*((_QWORD *)this + 39) + 8LL)
                                                 & -(__int64)(*((_QWORD *)this + 39) != 0);
                          *((_QWORD *)this + 81) = v54;
                          *((_QWORD *)this + 79) = v47;
                          *((_QWORD *)this + 77) = v48;
                          *((_QWORD *)this + 78) = v49;
                          v54 = 0;
                          v47 = 0;
                          v48 = 0;
                          v49 = 0;
                          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 12),
                              51,
                              WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                          }
                          inited = PeerDistSvcInitPerfLibrary();
                          if ( inited < 0 )
                            goto LABEL_234;
                          *((_BYTE *)this + 136) = 1;
                          inited = PeerDistSvcCreatePerfInstance();
                          if ( inited < 0 )
                            goto LABEL_234;
                          v19 = TnoService::InitializeService(this);
                          inited = v19;
                          if ( v19 >= 0 )
                          {
                            PerfCounters = PeerDistSvcLoadPerfCounters(*((PVOID *)this + 18));
                            inited = PerfCounters;
                            if ( PerfCounters < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                              {
                                WPP_SF_d(
                                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                                  53,
                                  WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                                  (unsigned int)PerfCounters);
                              }
                              inited = 0;
                            }
                            v36 = (*((__int64 (__fastcall **)(char *, const WCHAR *, _QWORD, void (__fastcall *)(TnoService *, unsigned __int8), TnoService *, int))s_pSvcsGlobalData
                                   + 24))(
                                    (char *)this + 128,
                                    v53,
                                    *((_QWORD *)this + 13),
                                    TorinoShutdownCallback,
                                    this,
                                    8);
                            v37 = v36;
                            if ( v36 )
                            {
                              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                              {
                                WPP_SF_qD(
                                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                                  54,
                                  WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                                  this,
                                  v36);
                              }
                              if ( v37 > 0 )
                                inited = (unsigned __int16)v37 | 0x80070000;
                              else
                                inited = v37;
                            }
                            goto LABEL_234;
                          }
                          v20 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                          {
                            goto LABEL_242;
                          }
                          v21 = 52;
LABEL_50:
                          v22 = (unsigned int)v19;
LABEL_51:
                          WPP_SF_d(*((_QWORD *)v20 + 12), v21, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v22);
                          goto LABEL_242;
                        }
                        v33 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                        {
                          return (unsigned int)inited;
                        }
                        v34 = 50;
                      }
                      else
                      {
                        v33 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                        {
                          return (unsigned int)inited;
                        }
                        v34 = 49;
                      }
                    }
                    else
                    {
                      v33 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                      {
                        return (unsigned int)inited;
                      }
                      v34 = 48;
                    }
                    WPP_SF_d(
                      *((_QWORD *)v33 + 12),
                      v34,
                      WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                      (unsigned int)inited);
                    return (unsigned int)inited;
                  }
                  v20 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                    || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    goto LABEL_242;
                  }
                  v21 = 47;
LABEL_127:
                  v22 = (unsigned int)inited;
                  goto LABEL_51;
                }
                v31 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v32 = 45;
              }
              else
              {
                v31 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_242;
                }
                v32 = 43;
              }
              WPP_SF_d(
                *((_QWORD *)v31 + 12),
                v32,
                WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                (unsigned int)inited);
              goto LABEL_242;
            }
            v17 = WPP_GLOBAL_Control;
          }
          Microsoft_Windows_Networking_ProviderId = MICROSOFT_PEERDIST_EVENTS_PROVIDER;
          goto LABEL_41;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v16);
      }
      v17 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
  }
  if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v6 + 27) & 0x800) != 0
    && *((_BYTE *)v6 + 105) )
  {
    WPP_SF_(*((_QWORD *)v6 + 12), 11, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000594c  push    rbp
0x18000594e  push    rbx
0x18000594f  push    rsi
0x180005950  push    rdi
0x180005951  push    r12
0x180005953  push    r13
0x180005955  push    r14
0x180005957  push    r15
0x180005959  lea     rbp, [rsp-1Fh]
0x18000595e  sub     rsp, 88h
0x180005965  mov     rdi, r8
0x180005968  mov     ebx, edx
0x18000596a  mov     rsi, rcx
0x18000596d  lea     r13, WPP_GLOBAL_Control
0x180005974  lea     r14, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x18000597b  mov     r12d, 800h
0x180005981  mov     rcx, cs:WPP_GLOBAL_Control
0x180005988  cmp     rcx, r13
0x18000598b  jz      short loc_1800059B1
0x18000598d  test    [rcx+6Ch], r12d
0x180005991  jz      short loc_1800059B1
0x180005993  cmp     byte ptr [rcx+69h], 4
0x180005997  jb      short loc_1800059B1
0x180005999  mov     edx, 0Ah
0x18000599e  mov     r8, r14
0x1800059a1  mov     rcx, [rcx+60h]
0x1800059a5  call    WPP_SF_
0x1800059aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b1  xor     r15d, r15d
0x1800059b4  test    ebx, ebx
0x1800059b6  jz      loc_180006990
0x1800059bc  mov     rax, [rdi]
0x1800059bf  mov     [rbp+57h+var_50], rax
0x1800059c3  test    rax, rax
0x1800059c6  jz      loc_180006990
0x1800059cc  mov     r8, rsi; lpContext
0x1800059cf  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800059d6  mov     rcx, rax; lpServiceName
0x1800059d9  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800059df  mov     [rsi+30h], rax
0x1800059e3  test    rax, rax
0x1800059e6  jnz     short loc_180005A36
0x1800059e8  call    cs:__imp_GetLastError
0x1800059ee  mov     ebx, eax
0x1800059f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059f7  cmp     rcx, r13
0x1800059fa  jz      short loc_180005A22
0x1800059fc  test    [rcx+6Ch], r12d
0x180005a00  jz      short loc_180005A22
0x180005a02  lea     edi, [r15+1]
0x180005a06  cmp     [rcx+69h], dil
0x180005a0a  jb      short loc_180005A22
0x180005a0c  lea     edx, [rdi+0Bh]
0x180005a0f  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180005a13  mov     r9, rsi
0x180005a16  mov     r8, r14
0x180005a19  mov     rcx, [rcx+60h]
0x180005a1d  call    WPP_SF_qD
0x180005a22  test    ebx, ebx
0x180005a24  jle     short loc_180005A2F
0x180005a26  movzx   ebx, bx
0x180005a29  or      ebx, 80070000h
0x180005a2f  mov     eax, ebx
0x180005a31  jmp     loc_1800069BA
0x180005a36  lea     rdx, [rsi+38h]; lpServiceStatus
0x180005a3a  mov     rcx, rax; hServiceStatus
0x180005a3d  call    cs:__imp_SetServiceStatus
0x180005a43  test    eax, eax
0x180005a45  jnz     short loc_180005A80
0x180005a47  call    cs:__imp_GetLastError
0x180005a4d  mov     ebx, eax
0x180005a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a56  cmp     rcx, r13
0x180005a59  jz      short loc_180005A22
0x180005a5b  test    [rcx+6Ch], r12d
0x180005a5f  jz      short loc_180005A22
0x180005a61  mov     edi, 1
0x180005a66  cmp     [rcx+69h], dil
0x180005a6a  jb      short loc_180005A22
0x180005a6c  lea     edx, [rdi+0Ch]
0x180005a6f  mov     r9d, eax
0x180005a72  mov     r8, r14
0x180005a75  mov     rcx, [rcx+60h]
0x180005a79  call    WPP_SF_d
0x180005a7e  jmp     short loc_180005A22
0x180005a80  call    ?PeerDistTelemetryInitialize@@YAXXZ; PeerDistTelemetryInitialize(void)
0x180005a85  lea     r8, MICROSOFT_PEERDIST_EVENTS_PROVIDER_Context
0x180005a8c  mov     r9, r8
0x180005a8f  lea     rcx, MICROSOFT_PEERDIST_EVENTS_PROVIDER
0x180005a96  call    McGenEventRegister_EtwEventRegister
0x180005a9b  mov     edi, 1
0x180005aa0  test    eax, eax
0x180005aa2  jz      short loc_180005ACE
0x180005aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aab  cmp     rcx, r13
0x180005aae  jz      short loc_180005ACE
0x180005ab0  test    [rcx+6Ch], r12d
0x180005ab4  jz      short loc_180005ACE
0x180005ab6  cmp     [rcx+69h], dil
0x180005aba  jb      short loc_180005ACE
0x180005abc  lea     edx, [rdi+0Dh]
0x180005abf  mov     r9d, eax
0x180005ac2  mov     r8, r14
0x180005ac5  mov     rcx, [rcx+60h]
0x180005ac9  call    WPP_SF_d
0x180005ace  lea     r8, MICROSOFT_PEERDIST_MONITORING_PROVIDER_Context
0x180005ad5  mov     r9, r8
0x180005ad8  lea     rcx, MICROSOFT_PEERDIST_MONITORING_PROVIDER
0x180005adf  call    McGenEventRegister_EtwEventRegister
0x180005ae4  test    eax, eax
0x180005ae6  jz      short loc_180005B14
0x180005ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aef  cmp     rcx, r13
0x180005af2  jz      short loc_180005B1B
0x180005af4  test    [rcx+6Ch], r12d
0x180005af8  jz      short loc_180005B1B
0x180005afa  cmp     [rcx+69h], dil
0x180005afe  jb      short loc_180005B1B
0x180005b00  mov     edx, 0Fh
0x180005b05  mov     r9d, eax
0x180005b08  mov     r8, r14
0x180005b0b  mov     rcx, [rcx+60h]
0x180005b0f  call    WPP_SF_d
0x180005b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b1b  test    cs:Microsoft_Windows_BranchCacheMonitoringEnableBits, dil
0x180005b22  jz      short loc_180005B37
0x180005b24  lea     rdx, ProviderArrivalEvent
0x180005b2b  call    McTemplateU0zq_EtwEventWriteTransfer
0x180005b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b37  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, r15
0x180005b3e  jnz     short loc_180005B9E
0x180005b40  lea     r9, Microsoft_Windows_Networking_CorrelationHandle
0x180005b47  xor     r8d, r8d
0x180005b4a  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback
0x180005b51  lea     rcx, Microsoft_Windows_Networking_CorrelationId
0x180005b58  call    cs:__imp_EtwEventRegister
0x180005b5e  test    eax, eax
0x180005b60  jz      short loc_180005B97
0x180005b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b69  cmp     rcx, r13
0x180005b6c  jz      short loc_180005BCF
0x180005b6e  test    [rcx+6Ch], r12d
0x180005b72  jz      short loc_180005BAD
0x180005b74  cmp     [rcx+69h], dil
0x180005b78  jb      short loc_180005BAD
0x180005b7a  mov     edx, 10h
0x180005b7f  mov     r9d, eax
0x180005b82  mov     r8, r14
0x180005b85  mov     rcx, [rcx+60h]
0x180005b89  call    WPP_SF_d
0x180005b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b95  jmp     short loc_180005BAD
0x180005b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b9e  movups  xmm0, cs:MICROSOFT_PEERDIST_EVENTS_PROVIDER
0x180005ba5  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x180005bad  cmp     rcx, r13
0x180005bb0  jz      short loc_180005BCF
0x180005bb2  test    [rcx+6Ch], r12d
0x180005bb6  jz      short loc_180005BCF
0x180005bb8  cmp     byte ptr [rcx+69h], 4
0x180005bbc  jb      short loc_180005BCF
0x180005bbe  mov     edx, 11h
0x180005bc3  mov     r8, r14
0x180005bc6  mov     rcx, [rcx+60h]
0x180005bca  call    WPP_SF_
0x180005bcf  mov     [rbp+57h+var_68], r15
0x180005bd3  lea     rcx, [rbp+57h+var_68]; struct IPeerDistADLoader **
0x180005bd7  call    ?CreateSingletonInstance@IPeerDistADLoader@@SAJPEAPEAV1@@Z; IPeerDistADLoader::CreateSingletonInstance(IPeerDistADLoader * *)
0x180005bdc  mov     ebx, eax
0x180005bde  mov     r14d, 80070000h
0x180005be4  test    eax, eax
0x180005be6  jns     short loc_180005C29
0x180005be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bef  cmp     rcx, r13
0x180005bf2  jz      loc_18000680E
0x180005bf8  test    [rcx+6Ch], r12d
0x180005bfc  jz      loc_18000680E
0x180005c02  cmp     [rcx+69h], dil
0x180005c06  jb      loc_18000680E
0x180005c0c  mov     edx, 12h
0x180005c11  mov     r9d, eax
0x180005c14  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005c1b  mov     rcx, [rcx+60h]
0x180005c1f  call    WPP_SF_d
0x180005c24  jmp     loc_18000680E
0x180005c29  mov     rax, [rbp+57h+var_68]
0x180005c2d  mov     [rsi+1C8h], rax
0x180005c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c3b  cmp     rcx, r13
0x180005c3e  jz      short loc_180005C61
0x180005c40  test    [rcx+6Ch], r12d
0x180005c44  jz      short loc_180005C61
0x180005c46  cmp     byte ptr [rcx+69h], 4
0x180005c4a  jb      short loc_180005C61
0x180005c4c  mov     edx, 13h
0x180005c51  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005c58  mov     rcx, [rcx+60h]
0x180005c5c  call    WPP_SF_
0x180005c61  mov     [rbp+57h+var_60], r15
0x180005c65  lea     rcx, [rbp+57h+var_60]; struct ITnoCfgMgr **
0x180005c69  call    ?Create@ITnoCfgMgr@@SAJPEAPEAV1@@Z; ITnoCfgMgr::Create(ITnoCfgMgr * *)
0x180005c6e  mov     ebx, eax
0x180005c70  test    eax, eax
0x180005c72  jns     short loc_180005CA2
0x180005c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c7b  cmp     rcx, r13
0x180005c7e  jz      loc_18000680E
0x180005c84  test    [rcx+6Ch], r12d
0x180005c88  jz      loc_18000680E
0x180005c8e  cmp     [rcx+69h], dil
0x180005c92  jb      loc_18000680E
0x180005c98  mov     edx, 14h
0x180005c9d  jmp     loc_180005C11
0x180005ca2  lea     rcx, [rsi+90h]
0x180005ca9  mov     rdx, [rbp+57h+var_60]
0x180005cad  call    ?reset@?$auto_ptr@VIPeerDiscovery@@@std@@QEAAXPEAVIPeerDiscovery@@@Z; std::auto_ptr<IPeerDiscovery>::reset(IPeerDiscovery *)
0x180005cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cb9  cmp     rcx, r13
0x180005cbc  jz      short loc_180005CDF
0x180005cbe  test    [rcx+6Ch], r12d
0x180005cc2  jz      short loc_180005CDF
0x180005cc4  cmp     byte ptr [rcx+69h], 4
0x180005cc8  jb      short loc_180005CDF
0x180005cca  mov     edx, 15h
0x180005ccf  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005cd6  mov     rcx, [rcx+60h]
0x180005cda  call    WPP_SF_
0x180005cdf  mov     [rbp+57h+var_58], r15
0x180005ce3  lea     rdx, [rbp+57h+var_58]; struct ICacheMgr **
0x180005ce7  call    ?Create@ICacheMgr@@SAKKPEAPEAV1@@Z; ICacheMgr::Create(ulong,ICacheMgr * *)
0x180005cec  mov     ebx, eax
0x180005cee  test    eax, eax
0x180005cf0  jz      short loc_180005D35
0x180005cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cf9  cmp     rcx, r13
0x180005cfc  jz      short loc_180005D22
0x180005cfe  test    [rcx+6Ch], r12d
0x180005d02  jz      short loc_180005D22
0x180005d04  cmp     [rcx+69h], dil
0x180005d08  jb      short loc_180005D22
0x180005d0a  mov     edx, 16h
0x180005d0f  mov     r9d, eax
0x180005d12  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005d19  mov     rcx, [rcx+60h]
0x180005d1d  call    WPP_SF_d
0x180005d22  test    ebx, ebx
0x180005d24  jle     loc_1800067A7
0x180005d2a  movzx   ebx, bx
0x180005d2d  or      ebx, r14d
0x180005d30  jmp     loc_1800067A5
0x180005d35  lea     rbx, [rsi+0A8h]
0x180005d3c  mov     rcx, rbx
0x180005d3f  call    ?Release@?$SmartPointer@VCHostedCacheListManager@@@@IEAAXXZ; SmartPointer<CHostedCacheListManager>::Release(void)
0x180005d44  mov     rax, [rbp+57h+var_58]
0x180005d48  mov     [rbx], rax
0x180005d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d52  cmp     rcx, r13
0x180005d55  jz      short loc_180005D78
0x180005d57  test    [rcx+6Ch], r12d
0x180005d5b  jz      short loc_180005D78
0x180005d5d  cmp     byte ptr [rcx+69h], 4
0x180005d61  jb      short loc_180005D78
0x180005d63  mov     edx, 17h
0x180005d68  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005d6f  mov     rcx, [rcx+60h]
0x180005d73  call    WPP_SF_
0x180005d78  mov     [rbp+57h+var_58], r15
0x180005d7c  lea     rcx, [rbp+57h+var_58]; struct IPeerDiscovery **
0x180005d80  call    ?Create@DiscoveryProviderProxy@@SAJPEAPEAVIPeerDiscovery@@@Z; DiscoveryProviderProxy::Create(IPeerDiscovery * *)
0x180005d85  mov     ebx, eax
0x180005d87  test    eax, eax
0x180005d89  jns     short loc_180005DB9
0x180005d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d92  cmp     rcx, r13
0x180005d95  jz      loc_18000680E
0x180005d9b  test    [rcx+6Ch], r12d
0x180005d9f  jz      loc_18000680E
0x180005da5  cmp     [rcx+69h], dil
0x180005da9  jb      loc_18000680E
0x180005daf  mov     edx, 18h
0x180005db4  jmp     loc_180005C11
0x180005db9  lea     rcx, [rsi+0C0h]
0x180005dc0  mov     rdx, [rbp+57h+var_58]
0x180005dc4  call    ?reset@?$auto_ptr@VIPeerDiscovery@@@std@@QEAAXPEAVIPeerDiscovery@@@Z; std::auto_ptr<IPeerDiscovery>::reset(IPeerDiscovery *)
0x180005dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dd0  cmp     rcx, r13
0x180005dd3  jz      short loc_180005DF6
0x180005dd5  test    [rcx+6Ch], r12d
0x180005dd9  jz      short loc_180005DF6
0x180005ddb  cmp     byte ptr [rcx+69h], 4
0x180005ddf  jb      short loc_180005DF6
0x180005de1  mov     edx, 19h
0x180005de6  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005ded  mov     rcx, [rcx+60h]
0x180005df1  call    WPP_SF_
0x180005df6  mov     [rbp+57h+var_58], r15
0x180005dfa  lea     rcx, [rbp+57h+var_58]; struct ISecurityManager **
0x180005dfe  call    ?Create@ISecurityManager@@SAJPEAPEAV1@@Z; ISecurityManager::Create(ISecurityManager * *)
0x180005e03  mov     ebx, eax
0x180005e05  test    eax, eax
  ... truncated ...
```
