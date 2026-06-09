# CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(WmiAllocator &,IUnknown *,IWbemServices *,WmiContainerController<_GUID> *,IWbemContext *,CServerObject_ProviderRegistrationV1 &,_GUID &)

- ea: `0x14001eec0`
- end: `0x14001f87d`
- name: `??0CInterceptor_IWbemSyncProvider@@QEAA@AEAVWmiAllocator@@PEAUIUnknown@@PEAUIWbemServices@@PEAV?$WmiContainerController@U_GUID@@@@PEAUIWbemContext@@AEAVCServerObject_ProviderRegistrationV1@@AEAU_GUID@@@Z`
- size: `2493`
- prototype: `CInterceptor_IWbemSyncProvider *__fastcall(CInterceptor_IWbemSyncProvider *this, struct WmiAllocator *, __int64, __int64, __int64, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000aaf4`
- `0x14001d55c`

## callees

- `0x14000a414`
- `0x14000a530`
- `0x14001eec0`
- `0x14001f978`
- `0x140020288`
- `0x1400207cc`
- `0x1400234b8`
- `0x14002929c`
- `0x14002944c`
- `0x14002a55c`
- `0x14002a5b4`
- `0x14002ffe4`
- `0x140036e20`
- `0x140038374`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f76b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001f63a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001f63a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfQueryInstance` at `0x14001f690`
- `api-ms-win-core-perfcounters-l1-1-0!PerfQueryInstance` at `0x14001f690`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x14001f628`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x14001f628`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001f655`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001f655`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x14001f827`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x14001f827`

## pseudocode

```c
CInterceptor_IWbemSyncProvider *__fastcall CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(
        CInterceptor_IWbemSyncProvider *this,
        struct WmiAllocator *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8)
{
  _QWORD *v12; // rdi
  unsigned int v13; // r9d
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  ULONG CurrentProcessId; // eax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  LPVOID v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // r11
  char LastError; // al
  _QWORD *v38; // rax
  signed int v39; // eax
  _QWORD Recipient[2]; // [rsp+30h] [rbp-10h] BYREF

  v12 = (_QWORD *)((char *)this + 176);
  WmiContainerController<_GUID>::WmiContainerElement::WmiContainerElement((char *)this + 176, a5, a8);
  WmiContainerController<void *>::WmiContainerController<void *>((char *)this + 232, a2);
  *(_QWORD *)this = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemServices'};
  *((_QWORD *)this + 1) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemPropertyProvider'};
  *((_QWORD *)this + 2) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProvider'};
  *((_QWORD *)this + 3) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderQuerySink'};
  *((_QWORD *)this + 4) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderSecurity'};
  *((_QWORD *)this + 5) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemProviderIdentity'};
  *((_QWORD *)this + 6) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventConsumerProviderEx'};
  *((_QWORD *)this + 7) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemUnboundObjectSink'};
  *((_QWORD *)this + 8) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemHiPerfProvider'};
  *((_QWORD *)this + 9) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemServices'};
  *((_QWORD *)this + 10) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemPropertyProvider'};
  *((_QWORD *)this + 11) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProvider'};
  *((_QWORD *)this + 12) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderQuerySink'};
  *((_QWORD *)this + 13) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderSecurity'};
  *((_QWORD *)this + 14) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventConsumerProviderEx'};
  *((_QWORD *)this + 15) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemUnboundObjectSink'};
  *((_QWORD *)this + 16) = &CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderInitialize'};
  *((_QWORD *)this + 17) = &CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemShutdown'};
  *((_QWORD *)this + 18) = &CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderQuota'};
  *((_QWORD *)this + 19) = &CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderSite'};
  *((_QWORD *)this + 20) = &CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderConfiguration'};
  *((_QWORD *)this + 21) = &CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWmiProviderConfiguration'};
  *v12 = &CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<_GUID>::WmiContainerElement'};
  *((_QWORD *)this + 29) = &CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<void *>'};
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = a4;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = a2;
  ProxyContainer::ProxyContainer((CInterceptor_IWbemSyncProvider *)((char *)this + 440), a2, 0x17u, v13);
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  v14 = (__int64)a6;
  *((_QWORD *)this + 67) = a6;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  _bstr_t::_bstr_t((CInterceptor_IWbemSyncProvider *)((char *)this + 568), &word_14004EE4C);
  *((_DWORD *)this + 144) = 1;
  *(_QWORD *)((char *)this + 580) = 1;
  *((_DWORD *)this + 147) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = a7;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  _InterlockedIncrement(&ProviderSubSystem_Globals::s_CInterceptor_IWbemSyncProvider_ObjectsInProgress);
  _InterlockedIncrement(&ProviderSubSystem_Globals::s_ObjectsInProgress);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v15 = (volatile signed __int32 *)*((_QWORD *)this + 75);
  if ( v15 )
    _InterlockedIncrement(v15);
  v16 = *((_QWORD *)this + 52);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  if ( a3 )
  {
    *((_QWORD *)this + 40) = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(a3, &IID_IWbemServices, (char *)this + 328);
    v18 = v17;
    if ( v17 >= 0 )
    {
      v21 = 1;
    }
    else
    {
      if ( v17 != -2147467262 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_15;
        }
        v20 = 18;
LABEL_14:
        WPP_SF_d(v19[2], v20, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v18);
LABEL_15:
        *((_DWORD *)this + 131) = v18;
        return this;
      }
      v21 = 0;
    }
    v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(a3, &IID_IWbemPropertyProvider, (char *)this + 336);
    v18 = v22;
    if ( v22 >= 0 )
    {
      v21 = 1;
    }
    else if ( v22 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 19;
      goto LABEL_14;
    }
    v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(a3, &IID_IWbemEventProvider, (char *)this + 352);
    v18 = v23;
    if ( v23 >= 0 )
    {
      v21 = 1;
    }
    else if ( v23 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 20;
      goto LABEL_14;
    }
    v24 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(
            a3,
            &IID_IWbemEventProviderQuerySink,
            (char *)this + 360);
    v18 = v24;
    if ( v24 >= 0 )
    {
      v21 = 1;
    }
    else if ( v24 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 21;
      goto LABEL_14;
    }
    v25 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(
            a3,
            &IID_IWbemEventProviderSecurity,
            (char *)this + 368);
    v18 = v25;
    if ( v25 >= 0 )
    {
      v21 = 1;
    }
    else if ( v25 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 22;
      goto LABEL_14;
    }
    v26 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(
            a3,
            &IID_IWbemEventConsumerProviderEx,
            (char *)this + 392);
    v18 = v26;
    if ( v26 >= 0 )
    {
      v21 = 1;
    }
    else if ( v26 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 23;
      goto LABEL_14;
    }
    v27 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(
            a3,
            &IID_IWbemEventConsumerProvider,
            (char *)this + 384);
    v18 = v27;
    if ( v27 >= 0 )
    {
      v21 = 1;
    }
    else if ( v27 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 24;
      goto LABEL_14;
    }
    v28 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(a3, &IID_IWbemUnboundObjectSink, (char *)this + 400);
    v18 = v28;
    if ( v28 >= 0 )
    {
      v21 = 1;
    }
    else if ( v28 != -2147467262 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_15;
      }
      v20 = 25;
      goto LABEL_14;
    }
    v29 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))a3)(a3, &IID_IWbemHiPerfProvider, (char *)this + 344);
    v18 = v29;
    if ( v29 < 0 )
    {
      if ( v29 != -2147467262 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_15;
        }
        v20 = 26;
        goto LABEL_14;
      }
      if ( !v21 )
        *((_DWORD *)this + 131) = -2147467262;
    }
  }
  if ( *((int *)this + 131) < 0 )
    return this;
  if ( !WmiprvSePerfCounter )
    goto LABEL_97;
  if ( !*((_QWORD *)this + 68) )
  {
    Instance = PerfCreateInstance(
                 WmiprvSePerfCounter,
                 &WMI_PROVIDERHOST_HEALTHGuid,
                 *(PCWSTR *)(*((_QWORD *)this + 75) + 1768LL),
                 0);
    *((_QWORD *)this + 68) = Instance;
    if ( Instance )
    {
      CurrentProcessId = GetCurrentProcessId();
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 1u, CurrentProcessId);
      goto LABEL_97;
    }
    if ( GetLastError() != 183 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LastError = GetLastError();
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 75) + 1768LL),
          LastError);
      }
LABEL_97:
      if ( !*((_QWORD *)this + 68) )
        return this;
      goto LABEL_98;
    }
    *((_QWORD *)this + 68) = PerfQueryInstance(
                               WmiprvSePerfCounter,
                               &WMI_PROVIDERHOST_HEALTHGuid,
                               *(PCWSTR *)(*((_QWORD *)this + 75) + 1768LL),
                               0);
    if ( dword_140061638 )
    {
LABEL_90:
      LODWORD(a6) = 0;
      a7 = *((_QWORD *)this + 68);
      if ( !(unsigned int)WmiHashTable<unsigned __int64,unsigned long,4>::Find(v32, &a7, &a6) )
      {
        a7 = v36;
        WmiHashTable<unsigned __int64,unsigned long,4>::Delete(v35, &a7);
      }
      LODWORD(a6) = (_DWORD)a6 + 1;
      a7 = *((_QWORD *)this + 68);
      WmiHashTable<unsigned __int64,unsigned long,4>::Insert(v35, &a7, &a6);
      goto LABEL_97;
    }
    if ( !lpMem )
    {
      v33 = operator new(0x10u);
      a6 = v33;
      if ( !v33 )
      {
        lpMem = 0;
        goto LABEL_89;
      }
      v34 = ProviderSubSystem_Globals::s_Allocator;
      *v33 = 0;
      v33[1] = v34;
      lpMem = v33;
    }
    if ( !(unsigned int)WmiHashTable<unsigned __int64,unsigned long,4>::Initialize() )
    {
      dword_140061638 = 1;
      goto LABEL_90;
    }
    dword_140061638 = 0;
LABEL_89:
    if ( !dword_140061638 )
      goto LABEL_97;
    goto LABEL_90;
  }
LABEL_98:
  if ( !*((_QWORD *)this + 69) )
  {
    v38 = operator new(0x10u);
    a6 = v38;
    if ( v38 )
    {
      *v38 = 0;
      v38[1] = a2;
      *((_QWORD *)this + 69) = v38;
      WmiHashTable<unsigned __int64,unsigned short *,4>::Initialize(v38);
    }
    else
    {
      *((_QWORD *)this + 69) = 0;
    }
  }
  CInterceptor_IWbemSyncProvider::RefreshCPURawData(this);
  if ( !*((_QWORD *)this + 74) )
  {
    Recipient[1] = 0;
    Recipient[0] = CInterceptor_IWbemSyncProvider::PowerNotificationCallback;
    v39 = PowerSettingRegisterNotification(&GUID_CONSOLE_DISPLAY_STATE, 2u, Recipient, (PHPOWERNOTIFY)this + 74);
    if ( v39 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v39);
    }
  }
  return this;
}

```

## disassembly

```asm
0x14001eec0  mov     [rsp-38h+arg_10], rbx
0x14001eec5  mov     [rsp-38h+arg_8], rdx
0x14001eeca  mov     [rsp-38h+arg_0], rcx
0x14001eecf  push    rbp
0x14001eed0  push    rsi
0x14001eed1  push    rdi
0x14001eed2  push    r12
0x14001eed4  push    r13
0x14001eed6  push    r14
0x14001eed8  push    r15
0x14001eeda  mov     rbp, rsp
0x14001eedd  sub     rsp, 40h
0x14001eee1  mov     rsi, r9
0x14001eee4  mov     r15, r8
0x14001eee7  mov     r12, rdx
0x14001eeea  mov     r14, rcx
0x14001eeed  lea     rdi, [rcx+0B0h]
0x14001eef4  mov     r8, [rbp+arg_38]
0x14001eef8  mov     rdx, [rbp+arg_20]
0x14001eefc  mov     rcx, rdi
0x14001eeff  call    ??0WmiContainerElement@?$WmiContainerController@U_GUID@@@@QEAA@PEAV1@AEBU_GUID@@@Z; WmiContainerController<_GUID>::WmiContainerElement::WmiContainerElement(WmiContainerController<_GUID> *,_GUID const &)
0x14001ef04  nop
0x14001ef05  lea     rbx, [r14+0E8h]
0x14001ef0c  mov     rdx, r12
0x14001ef0f  mov     rcx, rbx
0x14001ef12  call    ??0?$WmiContainerController@PEAX@@QEAA@AEAVWmiAllocator@@@Z; WmiContainerController<void *>::WmiContainerController<void *>(WmiAllocator &)
0x14001ef17  nop
0x14001ef18  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemServices@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemServices'}
0x14001ef1f  mov     [r14], rax
0x14001ef22  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemPropertyProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemPropertyProvider'}
0x14001ef29  mov     [r14+8], rax
0x14001ef2d  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProvider'}
0x14001ef34  mov     [r14+10h], rax
0x14001ef38  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProviderQuerySink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderQuerySink'}
0x14001ef3f  mov     [r14+18h], rax
0x14001ef43  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProviderSecurity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderSecurity'}
0x14001ef4a  mov     [r14+20h], rax
0x14001ef4e  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemProviderIdentity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemProviderIdentity'}
0x14001ef55  mov     [r14+28h], rax
0x14001ef59  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventConsumerProviderEx@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventConsumerProviderEx'}
0x14001ef60  mov     [r14+30h], rax
0x14001ef64  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemUnboundObjectSink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemUnboundObjectSink'}
0x14001ef6b  mov     [r14+38h], rax
0x14001ef6f  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemHiPerfProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemHiPerfProvider'}
0x14001ef76  mov     [r14+40h], rax
0x14001ef7a  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemServices@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemServices'}
0x14001ef81  mov     [r14+48h], rax
0x14001ef85  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemPropertyProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemPropertyProvider'}
0x14001ef8c  mov     [r14+50h], rax
0x14001ef90  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProvider'}
0x14001ef97  mov     [r14+58h], rax
0x14001ef9b  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProviderQuerySink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderQuerySink'}
0x14001efa2  mov     [r14+60h], rax
0x14001efa6  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProviderSecurity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderSecurity'}
0x14001efad  mov     [r14+68h], rax
0x14001efb1  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventConsumerProviderEx@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventConsumerProviderEx'}
0x14001efb8  mov     [r14+70h], rax
0x14001efbc  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemUnboundObjectSink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemUnboundObjectSink'}
0x14001efc3  mov     [r14+78h], rax
0x14001efc7  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderInitialize@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderInitialize'}
0x14001efce  mov     [r14+80h], rax
0x14001efd5  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemShutdown'}
0x14001efdc  mov     [r14+88h], rax
0x14001efe3  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderQuota@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderQuota'}
0x14001efea  mov     [r14+90h], rax
0x14001eff1  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderSite@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderSite'}
0x14001eff8  mov     [r14+98h], rax
0x14001efff  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderConfiguration@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderConfiguration'}
0x14001f006  mov     [r14+0A0h], rax
0x14001f00d  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWmiProviderConfiguration@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWmiProviderConfiguration'}
0x14001f014  mov     [r14+0A8h], rax
0x14001f01b  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BWmiContainerElement@?$WmiContainerController@U_GUID@@@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<_GUID>::WmiContainerElement'}
0x14001f022  mov     [rdi], rax
0x14001f025  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<void *>'}
0x14001f02c  mov     [rbx], rax
0x14001f02f  xor     ebx, ebx
0x14001f031  mov     [r14+140h], rbx
0x14001f038  lea     rdi, [r14+148h]
0x14001f03f  mov     [rdi], rbx
0x14001f042  lea     r12, [r14+150h]
0x14001f049  mov     [r12], rbx
0x14001f04d  mov     [r14+158h], rbx
0x14001f054  lea     r13, [r14+160h]
0x14001f05b  mov     [r13+0], rbx
0x14001f05f  mov     [r14+168h], rbx
0x14001f066  mov     [r14+170h], rbx
0x14001f06d  mov     [r14+180h], rbx
0x14001f074  mov     [r14+188h], rbx
0x14001f07b  mov     [r14+190h], rbx
0x14001f082  mov     [r14+198h], rbx
0x14001f089  mov     [r14+1A0h], rsi
0x14001f090  mov     [r14+1A8h], rbx
0x14001f097  mov     rax, [rbp+arg_8]
0x14001f09b  mov     [r14+1B0h], rax
0x14001f0a2  lea     rcx, [r14+1B8h]; this
0x14001f0a9  lea     r8d, [rbx+17h]; unsigned int
0x14001f0ad  mov     rdx, rax; struct WmiAllocator *
0x14001f0b0  call    ??0ProxyContainer@@QEAA@AEAVWmiAllocator@@KK@Z; ProxyContainer::ProxyContainer(WmiAllocator &,ulong,ulong)
0x14001f0b5  nop
0x14001f0b6  mov     [r14+208h], rbx
0x14001f0bd  mov     [r14+210h], rbx
0x14001f0c4  mov     rbx, [rbp+arg_28]
0x14001f0c8  mov     [r14+218h], rbx
0x14001f0cf  mov     qword ptr [r14+220h], 0
0x14001f0da  mov     qword ptr [r14+228h], 0
0x14001f0e5  mov     qword ptr [r14+230h], 0
0x14001f0f0  lea     rcx, [r14+238h]; this
0x14001f0f7  lea     rdx, word_14004EE4C; unsigned __int16 *
0x14001f0fe  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001f103  nop
0x14001f104  mov     dword ptr [r14+240h], 1
0x14001f10f  mov     qword ptr [r14+244h], 1
0x14001f11a  xor     edx, edx
0x14001f11c  mov     [r14+24Ch], edx
0x14001f123  lea     rsi, [r14+250h]
0x14001f12a  mov     [rsi], rdx
0x14001f12d  mov     rax, [rbp+arg_30]
0x14001f131  mov     [r14+258h], rax
0x14001f138  mov     [r14+260h], rdx
0x14001f13f  mov     [r14+268h], rdx
0x14001f146  mov     [r14+270h], rdx
0x14001f14d  mov     [r14+280h], rdx
0x14001f154  mov     [r14+288h], rdx
0x14001f15b  mov     [r14+290h], rdx
0x14001f162  mov     [r14+298h], rdx
0x14001f169  mov     [r14+2A0h], rdx
0x14001f170  mov     [r14+2A8h], rdx
0x14001f177  mov     [r14+2B0h], rdx
0x14001f17e  mov     [r14+2B8h], rdx
0x14001f185  mov     [r14+2C0h], rdx
0x14001f18c  mov     [r14+2C8h], rdx
0x14001f193  mov     [r14+2F0h], rdx
0x14001f19a  mov     [r14+2F8h], rdx
0x14001f1a1  mov     [r14+300h], rdx
0x14001f1a8  mov     [r14+308h], rdx
0x14001f1af  mov     [r14+310h], rdx
0x14001f1b6  mov     [r14+318h], rdx
0x14001f1bd  mov     [r14+320h], rdx
0x14001f1c4  mov     [r14+328h], rdx
0x14001f1cb  mov     [r14+330h], rdx
0x14001f1d2  mov     [r14+338h], rdx
0x14001f1d9  mov     [r14+340h], rdx
0x14001f1e0  mov     [r14+348h], rdx
0x14001f1e7  mov     [r14+350h], rdx
0x14001f1ee  mov     [r14+358h], rdx
0x14001f1f5  mov     [r14+360h], rdx
0x14001f1fc  lock inc cs:?s_CInterceptor_IWbemSyncProvider_ObjectsInProgress@ProviderSubSystem_Globals@@2JA; long ProviderSubSystem_Globals::s_CInterceptor_IWbemSyncProvider_ObjectsInProgress
0x14001f203  lock inc cs:?s_ObjectsInProgress@ProviderSubSystem_Globals@@2JA; long ProviderSubSystem_Globals::s_ObjectsInProgress
0x14001f20a  test    rbx, rbx
0x14001f20d  jz      short loc_14001F220
0x14001f20f  mov     rax, [rbx]
0x14001f212  mov     rcx, rbx
0x14001f215  mov     rax, [rax+8]
0x14001f219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f21e  xor     edx, edx
0x14001f220  mov     rax, [r14+258h]
0x14001f227  test    rax, rax
0x14001f22a  jz      short loc_14001F22F
0x14001f22c  lock inc dword ptr [rax]
0x14001f22f  mov     rcx, [r14+1A0h]
0x14001f236  test    rcx, rcx
0x14001f239  jz      short loc_14001F249
0x14001f23b  mov     rax, [rcx]
0x14001f23e  mov     rax, [rax+8]
0x14001f242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f247  xor     edx, edx
0x14001f249  test    r15, r15
0x14001f24c  jz      loc_14001F5DA
0x14001f252  mov     [r14+140h], r15
0x14001f259  mov     rax, [r15]
0x14001f25c  mov     rcx, r15
0x14001f25f  mov     rax, [rax+8]
0x14001f263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f268  mov     rax, [r15]
0x14001f26b  mov     r8, rdi
0x14001f26e  lea     rdx, IID_IWbemServices
0x14001f275  mov     rcx, r15
0x14001f278  mov     rax, [rax]
0x14001f27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f280  mov     edi, eax
0x14001f282  test    eax, eax
0x14001f284  jns     short loc_14001F2D4
0x14001f286  cmp     eax, 80004002h
0x14001f28b  jz      short loc_14001F2D0
0x14001f28d  lea     rbx, WPP_GLOBAL_Control
0x14001f294  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f29b  cmp     rcx, rbx
0x14001f29e  jz      short loc_14001F2C4
0x14001f2a0  test    byte ptr [rcx+1Ch], 4
0x14001f2a4  jz      short loc_14001F2C4
0x14001f2a6  cmp     byte ptr [rcx+19h], 5
0x14001f2aa  jb      short loc_14001F2C4
0x14001f2ac  mov     edx, 12h
0x14001f2b1  mov     r9d, edi
0x14001f2b4  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001f2bb  mov     rcx, [rcx+10h]
0x14001f2bf  call    WPP_SF_d
0x14001f2c4  mov     [r14+20Ch], edi
0x14001f2cb  jmp     loc_14001F862
0x14001f2d0  xor     ebx, ebx
0x14001f2d2  jmp     short loc_14001F2D9
0x14001f2d4  mov     ebx, 1
0x14001f2d9  mov     rax, [r15]
0x14001f2dc  mov     r8, r12
0x14001f2df  lea     rdx, IID_IWbemPropertyProvider
0x14001f2e6  mov     rcx, r15
0x14001f2e9  mov     rax, [rax]
0x14001f2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f2f1  mov     edi, eax
0x14001f2f3  test    eax, eax
0x14001f2f5  jns     short loc_14001F324
0x14001f2f7  cmp     eax, 80004002h
0x14001f2fc  jz      short loc_14001F32F
0x14001f2fe  lea     rbx, WPP_GLOBAL_Control
0x14001f305  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f30c  cmp     rcx, rbx
0x14001f30f  jz      short loc_14001F2C4
0x14001f311  test    byte ptr [rcx+1Ch], 4
0x14001f315  jz      short loc_14001F2C4
0x14001f317  cmp     byte ptr [rcx+19h], 5
0x14001f31b  jb      short loc_14001F2C4
0x14001f31d  mov     edx, 13h
0x14001f322  jmp     short loc_14001F2B1
0x14001f324  mov     r12d, 1
0x14001f32a  mov     ebx, r12d
0x14001f32d  jmp     short loc_14001F335
0x14001f32f  mov     r12d, 1
0x14001f335  mov     rax, [r15]
0x14001f338  mov     r8, r13
0x14001f33b  lea     rdx, IID_IWbemEventProvider
0x14001f342  mov     rcx, r15
0x14001f345  mov     rax, [rax]
0x14001f348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f34d  mov     edi, eax
0x14001f34f  mov     r13d, 80004002h
0x14001f355  test    eax, eax
0x14001f357  jns     short loc_14001F393
0x14001f359  cmp     eax, r13d
0x14001f35c  jz      short loc_14001F396
0x14001f35e  lea     rbx, WPP_GLOBAL_Control
0x14001f365  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f36c  cmp     rcx, rbx
0x14001f36f  jz      loc_14001F2C4
0x14001f375  test    byte ptr [rcx+1Ch], 4
0x14001f379  jz      loc_14001F2C4
0x14001f37f  cmp     byte ptr [rcx+19h], 5
0x14001f383  jb      loc_14001F2C4
0x14001f389  mov     edx, 14h
0x14001f38e  jmp     loc_14001F2B1
0x14001f393  mov     ebx, r12d
0x14001f396  mov     rax, [r15]
0x14001f399  lea     r8, [r14+168h]
0x14001f3a0  lea     rdx, IID_IWbemEventProviderQuerySink
0x14001f3a7  mov     rcx, r15
0x14001f3aa  mov     rax, [rax]
0x14001f3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3b2  mov     edi, eax
0x14001f3b4  test    eax, eax
0x14001f3b6  jns     short loc_14001F3F2
0x14001f3b8  cmp     eax, r13d
0x14001f3bb  jz      short loc_14001F3F5
0x14001f3bd  lea     rbx, WPP_GLOBAL_Control
0x14001f3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3cb  cmp     rcx, rbx
0x14001f3ce  jz      loc_14001F2C4
0x14001f3d4  test    byte ptr [rcx+1Ch], 4
0x14001f3d8  jz      loc_14001F2C4
0x14001f3de  cmp     byte ptr [rcx+19h], 5
0x14001f3e2  jb      loc_14001F2C4
0x14001f3e8  mov     edx, 15h
0x14001f3ed  jmp     loc_14001F2B1
0x14001f3f2  mov     ebx, r12d
0x14001f3f5  mov     rax, [r15]
0x14001f3f8  lea     r8, [r14+170h]
0x14001f3ff  lea     rdx, IID_IWbemEventProviderSecurity
0x14001f406  mov     rcx, r15
0x14001f409  mov     rax, [rax]
0x14001f40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f411  mov     edi, eax
0x14001f413  test    eax, eax
0x14001f415  jns     short loc_14001F451
0x14001f417  cmp     eax, r13d
0x14001f41a  jz      short loc_14001F454
0x14001f41c  lea     rbx, WPP_GLOBAL_Control
0x14001f423  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f42a  cmp     rcx, rbx
0x14001f42d  jz      loc_14001F2C4
0x14001f433  test    byte ptr [rcx+1Ch], 4
0x14001f437  jz      loc_14001F2C4
0x14001f43d  cmp     byte ptr [rcx+19h], 5
0x14001f441  jb      loc_14001F2C4
0x14001f447  mov     edx, 16h
0x14001f44c  jmp     loc_14001F2B1
0x14001f451  mov     ebx, r12d
0x14001f454  mov     rax, [r15]
0x14001f457  lea     r8, [r14+188h]
0x14001f45e  lea     rdx, IID_IWbemEventConsumerProviderEx
0x14001f465  mov     rcx, r15
0x14001f468  mov     rax, [rax]
0x14001f46b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
