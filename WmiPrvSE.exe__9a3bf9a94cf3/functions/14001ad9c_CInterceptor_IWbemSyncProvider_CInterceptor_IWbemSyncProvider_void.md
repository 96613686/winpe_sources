# CInterceptor_IWbemSyncProvider::~CInterceptor_IWbemSyncProvider(void)

- ea: `0x14001ad9c`
- end: `0x14001b3bb`
- name: `??1CInterceptor_IWbemSyncProvider@@UEAA@XZ`
- size: `1567`
- prototype: `void __fastcall(CInterceptor_IWbemSyncProvider *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14001ad64`

## callees

- `0x140001988`
- `0x140002f20`
- `0x140002fc4`
- `0x140004e7c`
- `0x140004ff0`
- `0x140005738`
- `0x14000a0f0`
- `0x14001ad9c`
- `0x14001b3d0`
- `0x14001b40c`
- `0x1400234b8`
- `0x14002929c`
- `0x14002944c`
- `0x140029f8c`
- `0x140036e20`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001b37d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001b37d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b355`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b355`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b336`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b08f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x14001b23a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x14001b23a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14001b1f0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14001b1f0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b1ba`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b1d5`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b20b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b226`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b1ba`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b1d5`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b20b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14001b226`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001b261`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001b261`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001af1e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001af1e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0b3`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0c5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0a1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0b3`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b0c5`
- `OLEAUT32!__imp_SysStringLen` at `0x14001b2c3`
- `OLEAUT32!__imp_SysStringLen` at `0x14001b2c3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14001b2f0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14001b2f0`

## pseudocode

```c
void __fastcall CInterceptor_IWbemSyncProvider::~CInterceptor_IWbemSyncProvider(CInterceptor_IWbemSyncProvider *this)
{
  char *v2; // r12
  char *v3; // r15
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  ProxyContainer *v17; // r14
  __int64 v18; // rcx
  void *v19; // rcx
  OLECHAR *v20; // rcx
  OLECHAR *v21; // rcx
  OLECHAR *v22; // rcx
  CServerObject_ProviderRegistrationV1 *v23; // rcx
  __int64 v24; // rcx
  int v25; // edi
  __int64 v26; // rcx
  __int64 v27; // r11
  __int64 v28; // rcx
  void *v29; // rsi
  void *v30; // rcx
  signed int v31; // eax
  volatile signed __int32 **v32; // rsi
  OLECHAR **v33; // rax
  OLECHAR *v34; // rcx
  const WCHAR *v35; // rdx
  __int64 v36; // rcx
  void *v37; // rdi
  void *v38; // rbx
  unsigned int v39; // edx
  int v40; // [rsp+38h] [rbp-8h]
  int v41; // [rsp+70h] [rbp+30h] BYREF
  __int64 v42; // [rsp+78h] [rbp+38h] BYREF

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
  v2 = (char *)this + 176;
  *((_QWORD *)this + 22) = &CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<_GUID>::WmiContainerElement'};
  v3 = (char *)this + 232;
  *((_QWORD *)this + 29) = &CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<void *>'};
  WmiSetAndCommitObject(
    qword_140061390,
    1,
    *((_QWORD *)this + 78),
    *(_QWORD *)(*((_QWORD *)this + 75) + 1768LL),
    *((_QWORD *)this + 77),
    *((_QWORD *)this + 76),
    0,
    v40);
  v4 = *((_QWORD *)this + 53);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 40);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 41);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 42);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 43);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 44);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 45);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *((_QWORD *)this + 46);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = *((_QWORD *)this + 49);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = *((_QWORD *)this + 48);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = *((_QWORD *)this + 50);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v15 = *((_QWORD *)this + 52);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = *((_QWORD *)this + 51);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = (CInterceptor_IWbemSyncProvider *)((char *)this + 440);
  ProxyContainer::UnInitialize((char *)this + 440);
  v18 = *((_QWORD *)this + 67);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = (void *)*((_QWORD *)this + 66);
  if ( v19 )
    CloseHandle(v19);
  v20 = (OLECHAR *)*((_QWORD *)this + 78);
  if ( v20 )
    SysFreeString(v20);
  v21 = (OLECHAR *)*((_QWORD *)this + 76);
  if ( v21 )
    SysFreeString(v21);
  v22 = (OLECHAR *)*((_QWORD *)this + 77);
  if ( v22 )
    SysFreeString(v22);
  v23 = (CServerObject_ProviderRegistrationV1 *)*((_QWORD *)this + 75);
  if ( v23 )
    CServerObject_ProviderRegistrationV1::Release(v23);
  WmiContainerController<void *>::UnInitialize(v3);
  _InterlockedDecrement(&ProviderSubSystem_Globals::s_CInterceptor_IWbemSyncProvider_ObjectsInProgress);
  v25 = 0;
  v41 = 0;
  if ( *((_QWORD *)this + 68) )
  {
    if ( !dword_140061638 )
      goto LABEL_50;
    v42 = *((_QWORD *)this + 68);
    if ( (unsigned int)WmiHashTable<unsigned __int64,unsigned long,4>::Find(v24, &v42, &v41) )
    {
      v25 = v41;
    }
    else
    {
      v42 = v27;
      WmiHashTable<unsigned __int64,unsigned long,4>::Delete(v26, &v42);
      v25 = v41;
      if ( v41 )
      {
        --v41;
        v42 = *((_QWORD *)this + 68);
        WmiHashTable<unsigned __int64,unsigned long,4>::Insert(v28, &v42, &v41);
      }
      v29 = lpMem;
      if ( !*(_DWORD *)(*(_QWORD *)lpMem + 8LL) )
      {
        lpMem = 0;
        dword_140061638 = 0;
        WmiHashTable<unsigned __int64,unsigned short *,4>::UnInitialize(v29);
        if ( v29 )
        {
          WmiHashTable<unsigned __int64,unsigned short *,4>::UnInitialize(v29);
          operator delete(v29);
        }
        v25 = 0;
      }
    }
    if ( !v25 )
    {
LABEL_50:
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 2u, 0);
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 3u, 0);
      PerfSetULongLongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 4u, 0);
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 1u, 0);
      PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 6u, 0);
      PerfDeleteInstance(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68));
      *((_QWORD *)this + 68) = 0;
      *((_DWORD *)this + 147) = 0;
    }
  }
  v30 = (void *)*((_QWORD *)this + 74);
  if ( v30 )
  {
    v31 = PowerSettingUnregisterNotification(v30);
    if ( v31 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v31);
    }
    *((_QWORD *)this + 74) = 0;
  }
  v32 = (volatile signed __int32 **)((char *)this + 568);
  v33 = (OLECHAR **)*((_QWORD *)this + 71);
  if ( v33 )
    v34 = *v33;
  else
    v34 = 0;
  if ( SysStringLen(v34) && *((_DWORD *)this + 144) && !v25 )
  {
    if ( *v32 )
      v35 = *(const WCHAR **)*v32;
    else
      v35 = 0;
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, v35);
  }
  v36 = *((_QWORD *)this + 69);
  if ( v36 )
  {
    WmiHashTable<unsigned __int64,unsigned short *,4>::UnInitialize(v36);
    v37 = (void *)*((_QWORD *)this + 69);
    if ( v37 )
    {
      WmiHashTable<unsigned __int64,unsigned short *,4>::UnInitialize(*((_QWORD *)this + 69));
      operator delete(v37);
    }
    *((_QWORD *)this + 69) = 0;
  }
  AcquireSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
  v38 = CInterceptor_IWbemSyncProvider::s_pProcessDATA;
  CInterceptor_IWbemSyncProvider::s_pProcessDATA = 0;
  ReleaseSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
  if ( v38 )
    operator delete(v38);
  ProviderSubSystem_Globals::Decrement_Global_Object_Count();
  if ( g_TaskFreeLib )
    SetEvent(*((HANDLE *)g_TaskFreeLib + 5));
  _bstr_t::~_bstr_t(v32, v39);
  ProxyContainer::~ProxyContainer(v17);
  WmiContainerController<void *>::~WmiContainerController<void *>(v3);
  WmiContainerController<_GUID>::WmiContainerElement::~WmiContainerElement(v2);
}

```

## disassembly

```asm
0x14001ad9c  mov     r11, rsp
0x14001ad9f  mov     [r11+18h], rbx
0x14001ada3  mov     [r11+20h], rsi
0x14001ada7  push    rbp
0x14001ada8  push    rdi
0x14001ada9  push    r12
0x14001adab  push    r14
0x14001adad  push    r15
0x14001adaf  mov     rbp, rsp
0x14001adb2  sub     rsp, 40h
0x14001adb6  mov     rbx, rcx
0x14001adb9  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemServices@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemServices'}
0x14001adc0  mov     [rcx], rax
0x14001adc3  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemPropertyProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemPropertyProvider'}
0x14001adca  mov     [rcx+8], rax
0x14001adce  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProvider'}
0x14001add5  mov     [rcx+10h], rax
0x14001add9  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProviderQuerySink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderQuerySink'}
0x14001ade0  mov     [rcx+18h], rax
0x14001ade4  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventProviderSecurity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventProviderSecurity'}
0x14001adeb  mov     [rcx+20h], rax
0x14001adef  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemProviderIdentity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemProviderIdentity'}
0x14001adf6  mov     [rcx+28h], rax
0x14001adfa  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemEventConsumerProviderEx@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemEventConsumerProviderEx'}
0x14001ae01  mov     [rcx+30h], rax
0x14001ae05  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemUnboundObjectSink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemUnboundObjectSink'}
0x14001ae0c  mov     [rcx+38h], rax
0x14001ae10  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemHiPerfProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemHiPerfProvider'}
0x14001ae17  mov     [rcx+40h], rax
0x14001ae1b  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemServices@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemServices'}
0x14001ae22  mov     [rcx+48h], rax
0x14001ae26  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemPropertyProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemPropertyProvider'}
0x14001ae2d  mov     [rcx+50h], rax
0x14001ae31  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProvider@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProvider'}
0x14001ae38  mov     [rcx+58h], rax
0x14001ae3c  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProviderQuerySink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderQuerySink'}
0x14001ae43  mov     [rcx+60h], rax
0x14001ae47  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventProviderSecurity@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventProviderSecurity'}
0x14001ae4e  mov     [rcx+68h], rax
0x14001ae52  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemEventConsumerProviderEx@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemEventConsumerProviderEx'}
0x14001ae59  mov     [rcx+70h], rax
0x14001ae5d  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWbemUnboundObjectSink@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWbemUnboundObjectSink'}
0x14001ae64  mov     [rcx+78h], rax
0x14001ae68  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderInitialize@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderInitialize'}
0x14001ae6f  mov     [rcx+80h], rax
0x14001ae76  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `IWbemShutdown'}
0x14001ae7d  mov     [rcx+88h], rax
0x14001ae84  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderQuota@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderQuota'}
0x14001ae8b  mov     [rcx+90h], rax
0x14001ae92  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderSite@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderSite'}
0x14001ae99  mov     [rcx+98h], rax
0x14001aea0  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B_IWmiProviderConfiguration@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `_IWmiProviderConfiguration'}
0x14001aea7  mov     [rcx+0A0h], rax
0x14001aeae  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BInternal_IWmiProviderConfiguration@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `Internal_IWmiProviderConfiguration'}
0x14001aeb5  mov     [rcx+0A8h], rax
0x14001aebc  lea     r12, [rcx+0B0h]
0x14001aec3  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6BWmiContainerElement@?$WmiContainerController@U_GUID@@@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<_GUID>::WmiContainerElement'}
0x14001aeca  mov     [r12], rax
0x14001aece  lea     r15, [rcx+0E8h]
0x14001aed5  lea     rax, ??_7CInterceptor_IWbemSyncProvider@@6B?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncProvider::`vftable'{for `WmiContainerController<void *>'}
0x14001aedc  mov     [r15], rax
0x14001aedf  mov     r9, [rcx+258h]
0x14001aee6  mov     qword ptr [r11-38h], 0
0x14001aeee  mov     rax, [rcx+260h]
0x14001aef5  mov     [r11-40h], rax
0x14001aef9  mov     rax, [rcx+268h]
0x14001af00  mov     [r11-48h], rax
0x14001af04  mov     r9, [r9+6E8h]
0x14001af0b  mov     r8, [rcx+270h]
0x14001af12  mov     edx, 1
0x14001af17  mov     rcx, cs:qword_140061390
0x14001af1e  call    cs:__imp_WmiSetAndCommitObject
0x14001af24  mov     rcx, [rbx+1A8h]
0x14001af2b  test    rcx, rcx
0x14001af2e  jz      short loc_14001AF3C
0x14001af30  mov     rax, [rcx]
0x14001af33  mov     rax, [rax+10h]
0x14001af37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af3c  mov     rcx, [rbx+140h]
0x14001af43  test    rcx, rcx
0x14001af46  jz      short loc_14001AF54
0x14001af48  mov     rax, [rcx]
0x14001af4b  mov     rax, [rax+10h]
0x14001af4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af54  mov     rcx, [rbx+148h]
0x14001af5b  test    rcx, rcx
0x14001af5e  jz      short loc_14001AF6C
0x14001af60  mov     rax, [rcx]
0x14001af63  mov     rax, [rax+10h]
0x14001af67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af6c  mov     rcx, [rbx+150h]
0x14001af73  test    rcx, rcx
0x14001af76  jz      short loc_14001AF84
0x14001af78  mov     rax, [rcx]
0x14001af7b  mov     rax, [rax+10h]
0x14001af7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af84  mov     rcx, [rbx+158h]
0x14001af8b  test    rcx, rcx
0x14001af8e  jz      short loc_14001AF9C
0x14001af90  mov     rax, [rcx]
0x14001af93  mov     rax, [rax+10h]
0x14001af97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af9c  mov     rcx, [rbx+160h]
0x14001afa3  test    rcx, rcx
0x14001afa6  jz      short loc_14001AFB4
0x14001afa8  mov     rax, [rcx]
0x14001afab  mov     rax, [rax+10h]
0x14001afaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afb4  mov     rcx, [rbx+168h]
0x14001afbb  test    rcx, rcx
0x14001afbe  jz      short loc_14001AFCC
0x14001afc0  mov     rax, [rcx]
0x14001afc3  mov     rax, [rax+10h]
0x14001afc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afcc  mov     rcx, [rbx+170h]
0x14001afd3  test    rcx, rcx
0x14001afd6  jz      short loc_14001AFE4
0x14001afd8  mov     rax, [rcx]
0x14001afdb  mov     rax, [rax+10h]
0x14001afdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afe4  mov     rcx, [rbx+188h]
0x14001afeb  test    rcx, rcx
0x14001afee  jz      short loc_14001AFFC
0x14001aff0  mov     rax, [rcx]
0x14001aff3  mov     rax, [rax+10h]
0x14001aff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001affc  mov     rcx, [rbx+180h]
0x14001b003  test    rcx, rcx
0x14001b006  jz      short loc_14001B014
0x14001b008  mov     rax, [rcx]
0x14001b00b  mov     rax, [rax+10h]
0x14001b00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b014  mov     rcx, [rbx+190h]
0x14001b01b  test    rcx, rcx
0x14001b01e  jz      short loc_14001B02C
0x14001b020  mov     rax, [rcx]
0x14001b023  mov     rax, [rax+10h]
0x14001b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b02c  mov     rcx, [rbx+1A0h]
0x14001b033  test    rcx, rcx
0x14001b036  jz      short loc_14001B044
0x14001b038  mov     rax, [rcx]
0x14001b03b  mov     rax, [rax+10h]
0x14001b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b044  mov     rcx, [rbx+198h]
0x14001b04b  test    rcx, rcx
0x14001b04e  jz      short loc_14001B05C
0x14001b050  mov     rax, [rcx]
0x14001b053  mov     rax, [rax+10h]
0x14001b057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b05c  lea     r14, [rbx+1B8h]
0x14001b063  mov     rcx, r14
0x14001b066  call    ?UnInitialize@ProxyContainer@@QEAA?AW4WmiStatusCode@@XZ; ProxyContainer::UnInitialize(void)
0x14001b06b  mov     rcx, [rbx+218h]
0x14001b072  test    rcx, rcx
0x14001b075  jz      short loc_14001B083
0x14001b077  mov     rax, [rcx]
0x14001b07a  mov     rax, [rax+10h]
0x14001b07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b083  mov     rcx, [rbx+210h]; hObject
0x14001b08a  test    rcx, rcx
0x14001b08d  jz      short loc_14001B095
0x14001b08f  call    cs:__imp_CloseHandle
0x14001b095  mov     rcx, [rbx+270h]; bstrString
0x14001b09c  test    rcx, rcx
0x14001b09f  jz      short loc_14001B0A7
0x14001b0a1  call    cs:__imp_SysFreeString
0x14001b0a7  mov     rcx, [rbx+260h]; bstrString
0x14001b0ae  test    rcx, rcx
0x14001b0b1  jz      short loc_14001B0B9
0x14001b0b3  call    cs:__imp_SysFreeString
0x14001b0b9  mov     rcx, [rbx+268h]; bstrString
0x14001b0c0  test    rcx, rcx
0x14001b0c3  jz      short loc_14001B0CB
0x14001b0c5  call    cs:__imp_SysFreeString
0x14001b0cb  mov     rcx, [rbx+258h]; this
0x14001b0d2  test    rcx, rcx
0x14001b0d5  jz      short loc_14001B0DC
0x14001b0d7  call    ?Release@CServerObject_ProviderRegistrationV1@@QEAAKXZ; CServerObject_ProviderRegistrationV1::Release(void)
0x14001b0dc  mov     rcx, r15
0x14001b0df  call    ?UnInitialize@?$WmiContainerController@PEAX@@UEAA?AW4WmiStatusCode@@XZ; WmiContainerController<void *>::UnInitialize(void)
0x14001b0e4  lock dec cs:?s_CInterceptor_IWbemSyncProvider_ObjectsInProgress@ProviderSubSystem_Globals@@2JA; long ProviderSubSystem_Globals::s_CInterceptor_IWbemSyncProvider_ObjectsInProgress
0x14001b0eb  xor     edi, edi
0x14001b0ed  mov     [rbp+arg_0], edi
0x14001b0f0  mov     r11, [rbx+220h]
0x14001b0f7  test    r11, r11
0x14001b0fa  jz      loc_14001B255
0x14001b100  cmp     cs:dword_140061638, edi
0x14001b106  jz      loc_14001B1A5
0x14001b10c  mov     [rbp+arg_8], r11
0x14001b110  lea     r8, [rbp+arg_0]
0x14001b114  lea     rdx, [rbp+arg_8]
0x14001b118  call    ?Find@?$WmiHashTable@_KK$03@@QEAA?AW4WmiStatusCode@@AEB_KAEAK@Z; WmiHashTable<unsigned __int64,ulong,4>::Find(unsigned __int64 const &,ulong &)
0x14001b11d  test    eax, eax
0x14001b11f  jnz     short loc_14001B19A
0x14001b121  mov     [rbp+arg_8], r11
0x14001b125  lea     rdx, [rbp+arg_8]
0x14001b129  call    ?Delete@?$WmiHashTable@_KK$03@@QEAA?AW4WmiStatusCode@@AEB_K@Z; WmiHashTable<unsigned __int64,ulong,4>::Delete(unsigned __int64 const &)
0x14001b12e  mov     edi, [rbp+arg_0]
0x14001b131  test    edi, edi
0x14001b133  jz      short loc_14001B153
0x14001b135  lea     eax, [rdi-1]
0x14001b138  mov     [rbp+arg_0], eax
0x14001b13b  mov     rax, [rbx+220h]
0x14001b142  mov     [rbp+arg_8], rax
0x14001b146  lea     r8, [rbp+arg_0]
0x14001b14a  lea     rdx, [rbp+arg_8]
0x14001b14e  call    ?Insert@?$WmiHashTable@_KK$03@@QEAA?AW4WmiStatusCode@@AEB_KAEBK@Z; WmiHashTable<unsigned __int64,ulong,4>::Insert(unsigned __int64 const &,ulong const &)
0x14001b153  mov     rsi, cs:lpMem
0x14001b15a  mov     rax, [rsi]
0x14001b15d  cmp     dword ptr [rax+8], 0
0x14001b161  jnz     short loc_14001B19D
0x14001b163  mov     cs:lpMem, 0
0x14001b16e  mov     cs:dword_140061638, 0
0x14001b178  mov     rcx, rsi
0x14001b17b  call    ?UnInitialize@?$WmiHashTable@_KPEAG$03@@QEAA?AW4WmiStatusCode@@XZ; WmiHashTable<unsigned __int64,ushort *,4>::UnInitialize(void)
0x14001b180  test    rsi, rsi
0x14001b183  jz      short loc_14001B196
0x14001b185  mov     rcx, rsi
0x14001b188  call    ?UnInitialize@?$WmiHashTable@_KPEAG$03@@QEAA?AW4WmiStatusCode@@XZ; WmiHashTable<unsigned __int64,ushort *,4>::UnInitialize(void)
0x14001b18d  nop
0x14001b18e  mov     rcx, rsi; lpMem
0x14001b191  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001b196  xor     edi, edi
0x14001b198  jmp     short loc_14001B19D
0x14001b19a  mov     edi, [rbp+arg_0]
0x14001b19d  test    edi, edi
0x14001b19f  jnz     loc_14001B255
0x14001b1a5  xor     r9d, r9d; Value
0x14001b1a8  lea     r8d, [r9+2]; CounterId
0x14001b1ac  mov     rdx, [rbx+220h]; Instance
0x14001b1b3  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b1ba  call    cs:__imp_PerfSetULongCounterValue
0x14001b1c0  xor     r9d, r9d; Value
0x14001b1c3  lea     r8d, [r9+3]; CounterId
0x14001b1c7  mov     rdx, [rbx+220h]; Instance
0x14001b1ce  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b1d5  call    cs:__imp_PerfSetULongCounterValue
0x14001b1db  xor     r9d, r9d; Value
0x14001b1de  lea     r8d, [r9+4]; CounterId
0x14001b1e2  mov     rdx, [rbx+220h]; Instance
0x14001b1e9  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b1f0  call    cs:__imp_PerfSetULongLongCounterValue
0x14001b1f6  xor     r9d, r9d; Value
0x14001b1f9  lea     r8d, [r9+1]; CounterId
0x14001b1fd  mov     rdx, [rbx+220h]; Instance
0x14001b204  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b20b  call    cs:__imp_PerfSetULongCounterValue
0x14001b211  xor     r9d, r9d; Value
0x14001b214  lea     r8d, [r9+6]; CounterId
0x14001b218  mov     rdx, [rbx+220h]; Instance
0x14001b21f  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b226  call    cs:__imp_PerfSetULongCounterValue
0x14001b22c  mov     rdx, [rbx+220h]; InstanceBlock
0x14001b233  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14001b23a  call    cs:__imp_PerfDeleteInstance
0x14001b240  mov     qword ptr [rbx+220h], 0
0x14001b24b  mov     dword ptr [rbx+24Ch], 0
0x14001b255  mov     rcx, [rbx+250h]; RegistrationHandle
0x14001b25c  test    rcx, rcx
0x14001b25f  jz      short loc_14001B2AD
0x14001b261  call    cs:__imp_PowerSettingUnregisterNotification
0x14001b267  test    eax, eax
0x14001b269  jns     short loc_14001B2A2
0x14001b26b  lea     rdx, WPP_GLOBAL_Control
0x14001b272  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b279  cmp     rcx, rdx
0x14001b27c  jz      short loc_14001B2A2
0x14001b27e  test    byte ptr [rcx+1Ch], 4
0x14001b282  jz      short loc_14001B2A2
0x14001b284  cmp     byte ptr [rcx+19h], 5
0x14001b288  jb      short loc_14001B2A2
0x14001b28a  mov     edx, 1Dh
0x14001b28f  mov     r9d, eax
0x14001b292  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001b299  mov     rcx, [rcx+10h]
0x14001b29d  call    WPP_SF_d
0x14001b2a2  mov     qword ptr [rbx+250h], 0
0x14001b2ad  lea     rsi, [rbx+238h]
0x14001b2b4  mov     rax, [rsi]
0x14001b2b7  test    rax, rax
0x14001b2ba  jz      short loc_14001B2C1
0x14001b2bc  mov     rcx, [rax]
0x14001b2bf  jmp     short loc_14001B2C3
0x14001b2c1  xor     ecx, ecx; pbstr
0x14001b2c3  call    cs:__imp_SysStringLen
0x14001b2c9  test    eax, eax
0x14001b2cb  jz      short loc_14001B2F6
0x14001b2cd  cmp     dword ptr [rbx+240h], 0
0x14001b2d4  jz      short loc_14001B2F6
0x14001b2d6  test    edi, edi
0x14001b2d8  jnz     short loc_14001B2F6
0x14001b2da  mov     rax, [rsi]
0x14001b2dd  test    rax, rax
0x14001b2e0  jz      short loc_14001B2E7
0x14001b2e2  mov     rdx, [rax]
0x14001b2e5  jmp     short loc_14001B2E9
0x14001b2e7  xor     edx, edx; lpSubKey
0x14001b2e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001b2f0  call    cs:__imp_RegDeleteKeyW
  ... truncated ...
```
