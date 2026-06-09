# SvcInitialize(ulong,ushort * *)

- ea: `0x1801a3984`
- end: `0x1801a3eda`
- name: `?SvcInitialize@@YAJKPEAPEAG@Z`
- size: `1366`
- prototype: `__int64 __fastcall(int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0090`

## callees

- `0x180017a58`
- `0x180018400`
- `0x18001a9e0`
- `0x18004e66c`
- `0x1800680c8`
- `0x18006a278`
- `0x18009d38c`
- `0x1800af7cc`
- `0x1800af804`
- `0x1800befec`
- `0x1800c0420`
- `0x1801a2a78`
- `0x1801a2d5c`
- `0x1801a3984`
- `0x1801a3fc8`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3b8c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801a3b71`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801a3b71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801a3bf0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801a3bf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801a3b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801a3b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a3b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a3b0f`
- `combase!__imp_CoGetSharedServiceId` at `0x1801a39f0`
- `combase!__imp_CoGetSharedServiceId` at `0x1801a3c5d`
- `combase!__imp_CoGetSharedServiceId` at `0x1801a39f0`
- `combase!__imp_CoGetSharedServiceId` at `0x1801a3c5d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1801a3a1a`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1801a3cc5`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1801a3a1a`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1801a3cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3a57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3d4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3a57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3d4c`

## string_xrefs

- `0x1801a3adb`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3bbb`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3c2d`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3c7f`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3ce7`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3d5f`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3dbf`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3e04`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3e54`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1801a3bac`: `CreateThreadpoolTimer`

## pseudocode

```c
__int64 __fastcall SvcInitialize(int a1, unsigned __int16 **a2)
{
  char IsEnabled; // al
  StateRepository::Time *v3; // rcx
  HRESULT v4; // eax
  signed int SharedServiceId; // ebx
  __int64 v6; // rdx
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v9; // rcx
  int UnbiasedInterruptTimeAsMSec; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  StateRepository::Time *v13; // rcx
  StateRepository::Time *v14; // rcx
  StateRepository::Time *v15; // rcx
  int v16; // edi
  StateRepository::Time *v17; // rcx
  StateRepository::Time *v18; // rcx
  StateRepository::Time *v19; // rcx
  int v20; // edi
  StateRepository::Time *v21; // rcx
  StateRepository::Time *v22; // rcx
  StateRepository::Time *v23; // rcx
  unsigned __int64 v24; // rdi
  HRESULT Instance; // eax
  StateRepository::Time *v26; // rcx
  int v27; // eax
  StateRepository::Time *v28; // rcx
  int v29; // edi
  StateRepository::Time *v30; // rcx
  StateRepository::Time *v31; // rcx
  int ppv; // [rsp+20h] [rbp-39h]
  int ppva; // [rsp+20h] [rbp-39h]
  char *v35; // [rsp+28h] [rbp-31h]
  char **v36; // [rsp+40h] [rbp-19h] BYREF
  int v37; // [rsp+48h] [rbp-11h]
  char *v38; // [rsp+50h] [rbp-9h]
  unsigned __int64 v39; // [rsp+58h] [rbp-1h]
  _QWORD v40[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v41; // [rsp+70h] [rbp+17h]
  __int64 v42; // [rsp+78h] [rbp+1Fh] BYREF
  int v43; // [rsp+80h] [rbp+27h]
  StateRepository::Time *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v45; // [rsp+C0h] [rbp+67h] BYREF
  char *v46; // [rsp+C8h] [rbp+6Fh] BYREF
  PTP_TIMER pti; // [rsp+D0h] [rbp+77h] BYREF
  struct _FILETIME pftDueTime; // [rsp+D8h] [rbp+7Fh] BYREF

  v46 = (char *)a2;
  v45 = a1;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification>::GetImpl'::`2'::impl);
  LODWORD(v46) = 0;
  v36 = &v46;
  if ( IsEnabled )
  {
    v40[0] = 0;
    v40[1] = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v37 = 50;
    pti = 0;
    UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v3);
    ThreadpoolTimer = CreateThreadpoolTimer(NotifyScmTimerCallback, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &pti,
      ThreadpoolTimer);
    if ( !pti )
    {
      LastError = GetLastError();
      SharedServiceId = LastError;
      if ( LastError > 0 )
        SharedServiceId = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v46) = SharedServiceId;
      if ( SharedServiceId < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1FD,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
          (const char *)(unsigned int)SharedServiceId,
          (int)"CreateThreadpoolTimer",
          v35);
      LODWORD(v40[0]) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v13) - UnbiasedInterruptTimeAsMSec;
      goto LABEL_40;
    }
    pftDueTime = (struct _FILETIME)-40000000LL;
    SetThreadpoolTimer(pti, &pftDueTime, 0xFA0u, 0);
    LODWORD(v40[0]) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v14) - UnbiasedInterruptTimeAsMSec;
    LOBYTE(v45) = 0;
    SharedServiceId = StateRepository::ServiceMain::AutoShutdown::Initialize(
                        (StateRepository::ServiceMain::AutoShutdown *)&v45,
                        (struct StateRepository::Service::MonitorInitialization *)v40);
    LODWORD(v46) = SharedServiceId;
    if ( SharedServiceId >= 0 )
    {
      v37 = 900;
      v16 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v15);
      SharedServiceId = CoGetSharedServiceId((char *)g_module + 16);
      LODWORD(v46) = SharedServiceId;
      if ( SharedServiceId >= 0 )
      {
        HIDWORD(v41) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v17) - v16;
        v37 = 1000;
        v20 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v19);
        SharedServiceId = CoRegisterServerShutdownDelay(qword_1804DFA40, dword_1804DF2D0);
        LODWORD(v46) = SharedServiceId;
        if ( SharedServiceId >= 0 )
        {
          LODWORD(v42) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v21) - v20;
          v37 = 1100;
          v38 = (char *)&v42 + 4;
          v24 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v23);
          v39 = v24;
          Instance = CoCreateInstance(
                       &CLSID_ContextSwitcher,
                       0,
                       1u,
                       &GUID_000001da_0000_0000_c000_000000000046,
                       &disconnectableContextCallback);
          SharedServiceId = Instance;
          if ( Instance >= 0 )
          {
            v27 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *))(*(_QWORD *)disconnectableContextCallback + 24LL))(
                    disconnectableContextCallback,
                    RegisterActivationFactoryCallback,
                    0,
                    &IID_IContextCallback);
            LODWORD(v46) = v27;
            if ( v27 >= 0 )
            {
              HIDWORD(v42) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(retaddr) - v24;
              v37 = 1200;
              v29 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v28);
              SharedServiceId = StateRepository::ServiceRpc::Initialize();
              LODWORD(v46) = SharedServiceId;
              if ( SharedServiceId >= 0 )
              {
                v43 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v30) - v29;
                v36 = 0;
                v37 = 0;
                LOBYTE(v45) = 0;
                StateRepository::Service::MonitorInitialization::Log((StateRepository::Service::MonitorInitialization *)v40);
                StateRepository::ServiceMain::AutoShutdown::~AutoShutdown((StateRepository::ServiceMain::AutoShutdown *)&v45);
                wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&pti);
                goto LABEL_43;
              }
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x230,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
                (const char *)(unsigned int)SharedServiceId,
                (int)"RpcInitialize",
                0);
              v43 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v31) - v29;
              goto LABEL_39;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x224,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
              (const char *)(unsigned int)v27,
              5);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)disconnectableContextCallback + 16LL))(disconnectableContextCallback);
            disconnectableContextCallback = 0;
            SharedServiceId = (int)v46;
            if ( (int)v46 < 0 )
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x228,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
                (const char *)(unsigned int)v46,
                (int)"RegisterDisconnectableContext",
                0);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x222,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
              (const char *)(unsigned int)Instance,
              ppva);
          }
          HIDWORD(v42) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v26) - v24;
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x218,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
            (const char *)(unsigned int)SharedServiceId,
            (int)"CoRegisterServerShutdownDelay",
            v35);
          LODWORD(v42) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v22) - v20;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x211,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
          (const char *)(unsigned int)SharedServiceId,
          (int)"module.Initialize",
          v35);
        HIDWORD(v41) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v18) - v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x20B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
        (const char *)(unsigned int)SharedServiceId,
        (int)"AutoShutdown.Initialize",
        v35);
    }
LABEL_39:
    StateRepository::ServiceMain::AutoShutdown::~AutoShutdown((StateRepository::ServiceMain::AutoShutdown *)&v45);
LABEL_40:
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&pti);
    goto LABEL_41;
  }
  v37 = 0;
  LOBYTE(v45) = 0;
  v4 = StateRepository::ServiceMain::AutoShutdown::Initialize((StateRepository::ServiceMain::AutoShutdown *)&v45);
  SharedServiceId = v4;
  if ( v4 < 0 )
  {
    v6 = 575;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    goto LABEL_15;
  }
  v37 = 900;
  v4 = CoGetSharedServiceId((char *)g_module + 16);
  SharedServiceId = v4;
  if ( v4 < 0 )
  {
    v6 = 578;
    goto LABEL_14;
  }
  v37 = 1000;
  v4 = CoRegisterServerShutdownDelay(qword_1804DFA40, dword_1804DF2D0);
  SharedServiceId = v4;
  if ( v4 < 0 )
  {
    v6 = 582;
    goto LABEL_14;
  }
  v37 = 1100;
  v4 = CoCreateInstance(
         &CLSID_ContextSwitcher,
         0,
         1u,
         &GUID_000001da_0000_0000_c000_000000000046,
         &disconnectableContextCallback);
  SharedServiceId = v4;
  if ( v4 < 0 )
  {
    v6 = 589;
    goto LABEL_14;
  }
  ppv = 5;
  LODWORD(v46) = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *))(*(_QWORD *)disconnectableContextCallback + 24LL))(
                   disconnectableContextCallback,
                   RegisterActivationFactoryCallback,
                   0,
                   &IID_IContextCallback);
  if ( (int)v46 < 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)disconnectableContextCallback + 16LL))(disconnectableContextCallback);
    disconnectableContextCallback = 0;
    SharedServiceId = (int)v46;
LABEL_15:
    StateRepository::ServiceMain::AutoShutdown::~AutoShutdown((StateRepository::ServiceMain::AutoShutdown *)&v45);
LABEL_41:
    StateRepository::ServiceMain::AutoLog_ServiceStart::~AutoLog_ServiceStart((StateRepository::ServiceMain::AutoLog_ServiceStart *)&v36);
    return (unsigned int)SharedServiceId;
  }
  v37 = 1200;
  v4 = StateRepository::ServiceRpc::Initialize();
  SharedServiceId = v4;
  if ( v4 < 0 )
  {
    v6 = 599;
    goto LABEL_14;
  }
  v36 = 0;
  v37 = 0;
  LOBYTE(v45) = 0;
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0qq_EventWriteTransfer(v9, RepositoryInitialized, CurrentProcessId, CurrentThreadId);
  }
  StateRepository::ServiceMain::AutoShutdown::~AutoShutdown((StateRepository::ServiceMain::AutoShutdown *)&v45);
LABEL_43:
  StateRepository::ServiceMain::AutoLog_ServiceStart::~AutoLog_ServiceStart((StateRepository::ServiceMain::AutoLog_ServiceStart *)&v36);
  return 0;
}

```

## disassembly

```asm
0x1801a3984  mov     [rsp-8+arg_8], rdx
0x1801a3989  mov     [rsp-8+arg_0], ecx
0x1801a398d  push    rbp
0x1801a398e  push    rbx
0x1801a398f  push    rsi
0x1801a3990  push    rdi
0x1801a3991  lea     rbp, [rsp-3Fh]
0x1801a3996  sub     rsp, 98h
0x1801a399d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification> `wil::Feature<__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification>::GetImpl(void)'::`2'::impl
0x1801a39a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_ServiceStartingMoreInProgressNotification>::__private_IsEnabled(void)
0x1801a39a9  xor     esi, esi
0x1801a39ab  mov     dword ptr [rbp+57h+arg_8], esi
0x1801a39ae  test    al, al
0x1801a39b0  lea     rax, [rbp+57h+arg_8]
0x1801a39b4  mov     [rbp+57h+var_70], rax
0x1801a39b8  jnz     loc_1801A3B3F
0x1801a39be  mov     [rbp+57h+var_68], esi
0x1801a39c1  mov     byte ptr [rbp+57h+arg_0], sil
0x1801a39c5  lea     rcx, [rbp+57h+arg_0]; this
0x1801a39c9  call    ?Initialize@AutoShutdown@ServiceMain@StateRepository@@QEAAJXZ; StateRepository::ServiceMain::AutoShutdown::Initialize(void)
0x1801a39ce  mov     ebx, eax
0x1801a39d0  test    eax, eax
0x1801a39d2  jns     short loc_1801A39DE
0x1801a39d4  mov     edx, 23Fh
0x1801a39d9  jmp     loc_1801A3AD8
0x1801a39de  mov     [rbp+57h+var_68], 384h
0x1801a39e5  mov     rcx, cs:?g_module@@3AEAVMyServiceModule@@EA; MyServiceModule & g_module
0x1801a39ec  add     rcx, 10h
0x1801a39f0  call    cs:__imp_CoGetSharedServiceId
0x1801a39f6  mov     ebx, eax
0x1801a39f8  test    eax, eax
0x1801a39fa  jns     short loc_1801A3A06
0x1801a39fc  mov     edx, 242h
0x1801a3a01  jmp     loc_1801A3AD8
0x1801a3a06  mov     [rbp+57h+var_68], 3E8h
0x1801a3a0d  mov     edx, cs:dword_1804DF2D0
0x1801a3a13  mov     rcx, cs:qword_1804DFA40
0x1801a3a1a  call    cs:__imp_CoRegisterServerShutdownDelay
0x1801a3a20  mov     ebx, eax
0x1801a3a22  test    eax, eax
0x1801a3a24  jns     short loc_1801A3A30
0x1801a3a26  mov     edx, 246h
0x1801a3a2b  jmp     loc_1801A3AD8
0x1801a3a30  mov     [rbp+57h+var_68], 44Ch
0x1801a3a37  lea     rax, ?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3a3e  mov     [rsp+0B0h+ppv], rax; ppv
0x1801a3a43  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1801a3a4a  xor     edx, edx; pUnkOuter
0x1801a3a4c  lea     r8d, [rdx+1]; dwClsContext
0x1801a3a50  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1801a3a57  call    cs:__imp_CoCreateInstance
0x1801a3a5d  mov     ebx, eax
0x1801a3a5f  test    eax, eax
0x1801a3a61  jns     short loc_1801A3A6A
0x1801a3a63  mov     edx, 24Dh
0x1801a3a68  jmp     short loc_1801A3AD8
0x1801a3a6a  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3a71  mov     rax, [rcx]
0x1801a3a74  mov     [rsp+0B0h+var_88], rsi
0x1801a3a79  mov     dword ptr [rsp+0B0h+ppv], 5; int
0x1801a3a81  lea     r9, IID_IContextCallback
0x1801a3a88  xor     r8d, r8d
0x1801a3a8b  lea     rdx, ?RegisterActivationFactoryCallback@@YAJPEAUtagComCallData@@@Z; RegisterActivationFactoryCallback(tagComCallData *)
0x1801a3a92  mov     rax, [rax+18h]
0x1801a3a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3a9b  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3a9e  test    eax, eax
0x1801a3aa0  jns     short loc_1801A3AC1
0x1801a3aa2  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3aa9  mov     rax, [rcx]
0x1801a3aac  mov     rax, [rax+10h]
0x1801a3ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3ab5  mov     cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA, rsi; IContextCallback * disconnectableContextCallback
0x1801a3abc  mov     ebx, dword ptr [rbp+57h+arg_8]
0x1801a3abf  jmp     short loc_1801A3AEC
0x1801a3ac1  mov     [rbp+57h+var_68], 4B0h
0x1801a3ac8  call    ?Initialize@ServiceRpc@StateRepository@@SAJXZ; StateRepository::ServiceRpc::Initialize(void)
0x1801a3acd  mov     ebx, eax
0x1801a3acf  test    eax, eax
0x1801a3ad1  jns     short loc_1801A3AFB
0x1801a3ad3  mov     edx, 257h; void *
0x1801a3ad8  mov     r9d, eax; char *
0x1801a3adb  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3ae2  mov     rcx, [rbp+5Fh]; this
0x1801a3ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a3aeb  nop
0x1801a3aec  lea     rcx, [rbp+57h+arg_0]; this
0x1801a3af0  call    ??1AutoShutdown@ServiceMain@StateRepository@@QEAA@XZ; StateRepository::ServiceMain::AutoShutdown::~AutoShutdown(void)
0x1801a3af5  nop
0x1801a3af6  jmp     loc_1801A3E83
0x1801a3afb  mov     [rbp+57h+var_70], rsi
0x1801a3aff  mov     [rbp+57h+var_68], esi
0x1801a3b02  mov     byte ptr [rbp+57h+arg_0], sil
0x1801a3b06  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 20h
0x1801a3b0d  jz      short loc_1801A3B30
0x1801a3b0f  call    cs:__imp_GetCurrentThreadId
0x1801a3b15  mov     ebx, eax
0x1801a3b17  call    cs:__imp_GetCurrentProcessId
0x1801a3b1d  mov     r9d, ebx
0x1801a3b20  mov     r8d, eax
0x1801a3b23  lea     rdx, RepositoryInitialized
0x1801a3b2a  call    McTemplateU0qq_EventWriteTransfer
0x1801a3b2f  nop
0x1801a3b30  lea     rcx, [rbp+57h+arg_0]; this
0x1801a3b34  call    ??1AutoShutdown@ServiceMain@StateRepository@@QEAA@XZ; StateRepository::ServiceMain::AutoShutdown::~AutoShutdown(void)
0x1801a3b39  nop
0x1801a3b3a  jmp     loc_1801A3EC3
0x1801a3b3f  mov     [rbp+57h+var_50], rsi
0x1801a3b43  mov     [rbp+57h+var_48], rsi
0x1801a3b47  mov     [rbp+57h+var_40], rsi
0x1801a3b4b  mov     [rbp+57h+var_38], rsi
0x1801a3b4f  mov     [rbp+57h+var_30], esi
0x1801a3b52  mov     [rbp+57h+var_68], 32h ; '2'
0x1801a3b59  mov     [rbp+57h+pti], rsi
0x1801a3b5d  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3b62  mov     rdi, rax
0x1801a3b65  xor     r8d, r8d; pcbe
0x1801a3b68  xor     edx, edx; pv
0x1801a3b6a  lea     rcx, NotifyScmTimerCallback; pfnti
0x1801a3b71  call    cs:__imp_CreateThreadpoolTimer
0x1801a3b77  mov     rdx, rax
0x1801a3b7a  lea     rcx, [rbp+57h+pti]
0x1801a3b7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801a3b83  mov     rcx, [rbp+57h+pti]; pti
0x1801a3b87  test    rcx, rcx
0x1801a3b8a  jnz     short loc_1801A3BDB
0x1801a3b8c  call    cs:__imp_GetLastError
0x1801a3b92  mov     ebx, eax
0x1801a3b94  test    eax, eax
0x1801a3b96  jle     short loc_1801A3BA1
0x1801a3b98  movzx   ebx, ax
0x1801a3b9b  or      ebx, 80070000h
0x1801a3ba1  mov     dword ptr [rbp+57h+arg_8], ebx
0x1801a3ba4  test    ebx, ebx
0x1801a3ba6  jns     short loc_1801A3BCC
0x1801a3ba8  mov     rcx, [rbp+5Fh]; this
0x1801a3bac  lea     rax, aCreatethreadpo; "CreateThreadpoolTimer"
0x1801a3bb3  mov     [rsp+0B0h+ppv], rax; int
0x1801a3bb8  mov     r9d, ebx; char *
0x1801a3bbb  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3bc2  mov     edx, 1FDh; void *
0x1801a3bc7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3bcc  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3bd1  sub     eax, edi
0x1801a3bd3  mov     dword ptr [rbp+57h+var_50], eax
0x1801a3bd6  jmp     loc_1801A3E79
0x1801a3bdb  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD9DA600h
0x1801a3be3  xor     r9d, r9d; msWindowLength
0x1801a3be6  mov     r8d, 0FA0h; msPeriod
0x1801a3bec  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x1801a3bf0  call    cs:__imp_SetThreadpoolTimer
0x1801a3bf6  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3bfb  sub     eax, edi
0x1801a3bfd  mov     dword ptr [rbp+57h+var_50], eax
0x1801a3c00  mov     byte ptr [rbp+57h+arg_0], sil
0x1801a3c04  lea     rdx, [rbp+57h+var_50]; struct StateRepository::Service::MonitorInitialization *
0x1801a3c08  lea     rcx, [rbp+57h+arg_0]; this
0x1801a3c0c  call    ?Initialize@AutoShutdown@ServiceMain@StateRepository@@QEAAJAEAUMonitorInitialization@Service@3@@Z; StateRepository::ServiceMain::AutoShutdown::Initialize(StateRepository::Service::MonitorInitialization &)
0x1801a3c11  mov     ebx, eax
0x1801a3c13  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3c16  test    eax, eax
0x1801a3c18  jns     short loc_1801A3C43
0x1801a3c1a  mov     rcx, [rbp+5Fh]; this
0x1801a3c1e  lea     rax, aAutoshutdownIn; "AutoShutdown.Initialize"
0x1801a3c25  mov     [rsp+0B0h+ppv], rax; int
0x1801a3c2a  mov     r9d, ebx; char *
0x1801a3c2d  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3c34  mov     edx, 20Bh; void *
0x1801a3c39  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3c3e  jmp     loc_1801A3E6F
0x1801a3c43  mov     [rbp+57h+var_68], 384h
0x1801a3c4a  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3c4f  mov     rdi, rax
0x1801a3c52  mov     rcx, cs:?g_module@@3AEAVMyServiceModule@@EA; MyServiceModule & g_module
0x1801a3c59  add     rcx, 10h
0x1801a3c5d  call    cs:__imp_CoGetSharedServiceId
0x1801a3c63  mov     ebx, eax
0x1801a3c65  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3c68  test    eax, eax
0x1801a3c6a  jns     short loc_1801A3C9F
0x1801a3c6c  mov     rcx, [rbp+5Fh]; this
0x1801a3c70  lea     rax, aModuleInitiali; "module.Initialize"
0x1801a3c77  mov     [rsp+0B0h+ppv], rax; int
0x1801a3c7c  mov     r9d, ebx; char *
0x1801a3c7f  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3c86  mov     edx, 211h; void *
0x1801a3c8b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3c90  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3c95  sub     eax, edi
0x1801a3c97  mov     dword ptr [rbp+57h+var_40+4], eax
0x1801a3c9a  jmp     loc_1801A3E6F
0x1801a3c9f  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3ca4  sub     eax, edi
0x1801a3ca6  mov     dword ptr [rbp+57h+var_40+4], eax
0x1801a3ca9  mov     [rbp+57h+var_68], 3E8h
0x1801a3cb0  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3cb5  mov     rdi, rax
0x1801a3cb8  mov     edx, cs:dword_1804DF2D0
0x1801a3cbe  mov     rcx, cs:qword_1804DFA40
0x1801a3cc5  call    cs:__imp_CoRegisterServerShutdownDelay
0x1801a3ccb  mov     ebx, eax
0x1801a3ccd  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3cd0  test    eax, eax
0x1801a3cd2  jns     short loc_1801A3D07
0x1801a3cd4  mov     rcx, [rbp+5Fh]; this
0x1801a3cd8  lea     rax, aCoregisterserv; "CoRegisterServerShutdownDelay"
0x1801a3cdf  mov     [rsp+0B0h+ppv], rax; int
0x1801a3ce4  mov     r9d, ebx; char *
0x1801a3ce7  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3cee  mov     edx, 218h; void *
0x1801a3cf3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3cf8  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3cfd  sub     eax, edi
0x1801a3cff  mov     dword ptr [rbp+57h+var_38], eax
0x1801a3d02  jmp     loc_1801A3E6F
0x1801a3d07  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3d0c  sub     eax, edi
0x1801a3d0e  mov     dword ptr [rbp+57h+var_38], eax
0x1801a3d11  mov     [rbp+57h+var_68], 44Ch
0x1801a3d18  lea     rax, [rbp+57h+var_38+4]
0x1801a3d1c  mov     [rbp+57h+var_60], rax
0x1801a3d20  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3d25  mov     rdi, rax
0x1801a3d28  mov     [rbp+57h+var_58], rax
0x1801a3d2c  lea     rax, ?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3d33  mov     [rsp+0B0h+ppv], rax; int
0x1801a3d38  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1801a3d3f  xor     edx, edx; pUnkOuter
0x1801a3d41  lea     r8d, [rdx+1]; dwClsContext
0x1801a3d45  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1801a3d4c  call    cs:__imp_CoCreateInstance
0x1801a3d52  mov     ebx, eax
0x1801a3d54  test    eax, eax
0x1801a3d56  jns     short loc_1801A3D80
0x1801a3d58  mov     rcx, [rbp+5Fh]; this
0x1801a3d5c  mov     r9d, eax; char *
0x1801a3d5f  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3d66  mov     edx, 222h; void *
0x1801a3d6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a3d70  nop
0x1801a3d71  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3d76  sub     eax, edi
0x1801a3d78  mov     dword ptr [rbp+57h+var_38+4], eax
0x1801a3d7b  jmp     loc_1801A3E6F
0x1801a3d80  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3d87  mov     rax, [rcx]
0x1801a3d8a  mov     [rsp+0B0h+var_88], rsi; char *
0x1801a3d8f  mov     dword ptr [rsp+0B0h+ppv], 5; int
0x1801a3d97  lea     r9, IID_IContextCallback
0x1801a3d9e  xor     r8d, r8d
0x1801a3da1  lea     rdx, ?RegisterActivationFactoryCallback@@YAJPEAUtagComCallData@@@Z; RegisterActivationFactoryCallback(tagComCallData *)
0x1801a3da8  mov     rax, [rax+18h]
0x1801a3dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3db1  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3db4  mov     rcx, [rbp+5Fh]; this
0x1801a3db8  test    eax, eax
0x1801a3dba  jns     short loc_1801A3E1A
0x1801a3dbc  mov     r9d, eax; char *
0x1801a3dbf  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3dc6  mov     edx, 224h; void *
0x1801a3dcb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801a3dd0  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1801a3dd7  mov     rax, [rcx]
0x1801a3dda  mov     rax, [rax+10h]
0x1801a3dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3de3  mov     cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA, rsi; IContextCallback * disconnectableContextCallback
0x1801a3dea  mov     ebx, dword ptr [rbp+57h+arg_8]
0x1801a3ded  test    ebx, ebx
0x1801a3def  jns     short loc_1801A3D71
0x1801a3df1  mov     rcx, [rbp+5Fh]; this
0x1801a3df5  lea     rax, aRegisterdiscon; "RegisterDisconnectableContext"
0x1801a3dfc  mov     [rsp+0B0h+ppv], rax; int
0x1801a3e01  mov     r9d, ebx; char *
0x1801a3e04  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3e0b  mov     edx, 228h; void *
0x1801a3e10  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3e15  jmp     loc_1801A3D71
0x1801a3e1a  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3e1f  sub     eax, edi
0x1801a3e21  mov     dword ptr [rbp+57h+var_38+4], eax
0x1801a3e24  mov     [rbp+57h+var_68], 4B0h
0x1801a3e2b  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3e30  mov     rdi, rax
0x1801a3e33  call    ?Initialize@ServiceRpc@StateRepository@@SAJXZ; StateRepository::ServiceRpc::Initialize(void)
0x1801a3e38  mov     ebx, eax
0x1801a3e3a  mov     dword ptr [rbp+57h+arg_8], eax
0x1801a3e3d  test    eax, eax
0x1801a3e3f  jns     short loc_1801A3E90
0x1801a3e41  mov     rcx, [rbp+5Fh]; this
0x1801a3e45  lea     rax, aRpcinitialize; "RpcInitialize"
0x1801a3e4c  mov     [rsp+0B0h+ppv], rax; int
0x1801a3e51  mov     r9d, ebx; char *
0x1801a3e54  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1801a3e5b  mov     edx, 230h; void *
0x1801a3e60  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801a3e65  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1801a3e6a  sub     eax, edi
0x1801a3e6c  mov     [rbp+57h+var_30], eax
0x1801a3e6f  lea     rcx, [rbp+57h+arg_0]; this
0x1801a3e73  call    ??1AutoShutdown@ServiceMain@StateRepository@@QEAA@XZ; StateRepository::ServiceMain::AutoShutdown::~AutoShutdown(void)
  ... truncated ...
```
