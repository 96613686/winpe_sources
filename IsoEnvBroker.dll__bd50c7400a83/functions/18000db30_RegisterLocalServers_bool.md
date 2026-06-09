# RegisterLocalServers(bool)

- ea: `0x18000db30`
- end: `0x18000dedb`
- name: `?RegisterLocalServers@@YAJ_N@Z`
- size: `939`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800075e4`
- `0x18000a464`
- `0x18000d19c`
- `0x18000db30`
- `0x18000e0a8`
- `0x180068010`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000dd31`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000dd31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de6b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000dc81`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000dc81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ddb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ddb0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000dbeb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000dc4e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000de89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000dbeb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000dc4e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000de89`

## string_xrefs

- `0x18000dc9b`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000dce7`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000dd45`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000ddc4`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000de24`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000db5e`: `KeepServiceAlive`
- `0x18000db65`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker`
- `0x18000dba5`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker`
- `0x18000de44`: `onecoreuap\windows\core\isoenvbroker\dll\service.cpp`
- `0x18000deb4`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18000dec6`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RegisterLocalServers(char a1)
{
  int v1; // ebx
  const char *v2; // r9
  unsigned int v3; // eax
  unsigned int v4; // r14d
  HANDLE v5; // r15
  bool v6; // bp
  bool v7; // si
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  LPVOID v12; // rcx
  HRESULT Instance; // eax
  int v14; // eax
  __int64 v15; // rdx
  const char *v17; // r9
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v21; // [rsp+88h] [rbp+10h] BYREF
  char v22; // [rsp+8Ch] [rbp+14h]

  v1 = dword_1800B9160;
  if ( a1 )
  {
    if ( v1 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v2);
    wil::reg::try_get_value<unsigned int>(
      (__int64)&v21,
      HKEY_LOCAL_MACHINE,
      L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker",
      L"KeepServiceAlive");
    if ( v22 && v21 )
      g_keepServiceAlive = 1;
    wil::reg::try_get_value<unsigned int>(
      (__int64)&v21,
      HKEY_LOCAL_MACHINE,
      L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker",
      L"ShutdownDelayInSeconds");
    v3 = 30;
    if ( v22 )
      v3 = v21;
    g_shutdownDelayInSeconds = v3;
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_1800B92C0 = 1;
    if ( !qword_1800B92B0 )
    {
      byte_1800B9278 = 1;
      byte_1800B9268 = 0;
      Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>::`vftable';
      qword_1800B9270 = (__int64)ModuleReleaseNotifier;
      qword_1800B92B0 = (__int64)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_;
    }
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_1800B92C0 = 1;
    v4 = 1000 * g_shutdownDelayInSeconds;
    v5 = g_shutdownEvent;
    v6 = g_shutdownDelayInSeconds != 0;
    v7 = g_keepServiceAlive;
    v8 = RoInitialize(1);
    v9 = v8;
    dword_1800B9290 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v8,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
LABEL_26:
      v15 = 78;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\dll\\service.cpp",
        (const char *)(unsigned int)v9,
        ppv);
      return (unsigned int)v9;
    }
    v10 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                            + 32LL))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v10,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      goto LABEL_26;
    }
    if ( v7 )
    {
      (*(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                     + 16LL))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      LOBYTE(dword_1800B9294) = 1;
    }
    if ( v6 )
    {
      v11 = CoRegisterServerShutdownDelay(v5, v4);
      v9 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
          (const char *)(unsigned int)v11,
          ppv);
        Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
        goto LABEL_26;
      }
      BYTE1(dword_1800B9294) = 1;
    }
    v12 = ::ppv;
    if ( ::ppv )
    {
      ::ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &::ppv);
    v9 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)Instance,
        ppva);
      Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      goto LABEL_26;
    }
    v14 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), void *, GUID *))(*(_QWORD *)::ppv + 24LL))(
            ::ppv,
            Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
            &Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_,
            &IID_IContextCallback);
    v9 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v14,
        5);
      Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      goto LABEL_26;
    }
  }
  else
  {
    if ( v1 == GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2C,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v17);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_1800B92C0 = 1;
    v9 = Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
    if ( v9 < 0 )
    {
      v15 = 87;
      goto LABEL_27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000db30  push    rbx
0x18000db32  push    rbp
0x18000db33  push    rsi
0x18000db34  push    rdi
0x18000db35  push    r14
0x18000db37  push    r15
0x18000db39  sub     rsp, 48h
0x18000db3d  mov     ebx, cs:dword_1800B9160
0x18000db43  test    cl, cl
0x18000db45  jz      loc_18000DE6B
0x18000db4b  mov     rdi, [rsp+78h]
0x18000db50  call    cs:__imp_GetCurrentThreadId
0x18000db56  cmp     ebx, eax
0x18000db58  jnz     loc_18000DEC6
0x18000db5e  lea     r9, aKeepserviceali; "KeepServiceAlive"
0x18000db65  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18000db6c  mov     rbx, 0FFFFFFFF80000002h
0x18000db73  mov     rdx, rbx
0x18000db76  lea     rcx, [rsp+78h+arg_8]
0x18000db7e  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x18000db83  cmp     [rsp+78h+arg_C], 0
0x18000db8b  jz      short loc_18000DB9E
0x18000db8d  cmp     [rsp+78h+arg_8], 0
0x18000db95  jz      short loc_18000DB9E
0x18000db97  mov     cs:?g_keepServiceAlive@@3_NA, 1; bool g_keepServiceAlive
0x18000db9e  lea     r9, aShutdowndelayi; "ShutdownDelayInSeconds"
0x18000dba5  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18000dbac  mov     rdx, rbx
0x18000dbaf  lea     rcx, [rsp+78h+arg_8]
0x18000dbb7  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x18000dbbc  mov     eax, 1Eh
0x18000dbc1  cmp     [rsp+78h+arg_C], 0
0x18000dbc9  cmovnz  eax, [rsp+78h+arg_8]
0x18000dbd1  mov     cs:?g_shutdownDelayInSeconds@@3KA, eax; ulong g_shutdownDelayInSeconds
0x18000dbd7  xor     r9d, r9d; Context
0x18000dbda  xor     r8d, r8d; Parameter
0x18000dbdd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000dbe4  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000dbeb  call    cs:__imp_InitOnceExecuteOnce
0x18000dbf1  mov     cs:byte_1800B92C0, 1
0x18000dbf8  cmp     cs:qword_1800B92B0, 0
0x18000dc00  jnz     short loc_18000DC3A
0x18000dc02  mov     cs:byte_1800B9278, 1
0x18000dc09  mov     cs:byte_1800B9268, 0
0x18000dc10  lea     rax, ??_7?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>::`vftable'
0x18000dc17  mov     cs:?instance_@?$StaticStorage@V?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$01VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_
0x18000dc1e  lea     rax, ?ModuleReleaseNotifier@@YAXXZ; ModuleReleaseNotifier(void)
0x18000dc25  mov     cs:qword_1800B9270, rax
0x18000dc2c  lea     rax, ?instance_@?$StaticStorage@V?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$01VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_
0x18000dc33  mov     cs:qword_1800B92B0, rax
0x18000dc3a  xor     r9d, r9d; Context
0x18000dc3d  xor     r8d, r8d; Parameter
0x18000dc40  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000dc47  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000dc4e  call    cs:__imp_InitOnceExecuteOnce
0x18000dc54  mov     cs:byte_1800B92C0, 1
0x18000dc5b  mov     eax, cs:?g_shutdownDelayInSeconds@@3KA; ulong g_shutdownDelayInSeconds
0x18000dc61  imul    r14d, eax, 3E8h
0x18000dc68  mov     r15, cs:?g_shutdownEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18000dc6f  test    eax, eax
0x18000dc71  setnz   bpl
0x18000dc75  mov     sil, cs:?g_keepServiceAlive@@3_NA; bool g_keepServiceAlive
0x18000dc7c  mov     ecx, 1
0x18000dc81  call    cs:__imp_RoInitialize
0x18000dc87  mov     ebx, eax
0x18000dc89  mov     cs:dword_1800B9290, eax
0x18000dc8f  test    eax, eax
0x18000dc91  jns     short loc_18000DCBF
0x18000dc93  mov     rcx, [rsp+78h]; this
0x18000dc98  mov     r9d, eax; char *
0x18000dc9b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000dca2  mov     edx, 63h ; 'c'; void *
0x18000dca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcac  nop
0x18000dcad  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; this
0x18000dcb4  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000dcb9  nop
0x18000dcba  jmp     loc_18000DE3F
0x18000dcbf  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18000dcc6  lea     rdi, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18000dccd  mov     rcx, rdi
0x18000dcd0  mov     rax, [rax+20h]
0x18000dcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd9  mov     ebx, eax
0x18000dcdb  test    eax, eax
0x18000dcdd  jns     short loc_18000DD07
0x18000dcdf  mov     rcx, [rsp+78h]; this
0x18000dce4  mov     r9d, eax; char *
0x18000dce7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000dcee  mov     edx, 7Bh ; '{'; void *
0x18000dcf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcf8  nop
0x18000dcf9  mov     rcx, rdi; this
0x18000dcfc  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000dd01  nop
0x18000dd02  jmp     loc_18000DE3F
0x18000dd07  test    sil, sil
0x18000dd0a  jz      short loc_18000DD26
0x18000dd0c  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18000dd13  mov     rcx, rdi
0x18000dd16  mov     rax, [rax+10h]
0x18000dd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1f  mov     byte ptr cs:dword_1800B9294, 1
0x18000dd26  test    bpl, bpl
0x18000dd29  jz      short loc_18000DD6C
0x18000dd2b  mov     edx, r14d
0x18000dd2e  mov     rcx, r15
0x18000dd31  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000dd37  mov     ebx, eax
0x18000dd39  test    eax, eax
0x18000dd3b  jns     short loc_18000DD65
0x18000dd3d  mov     rcx, [rsp+78h]; this
0x18000dd42  mov     r9d, eax; char *
0x18000dd45  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000dd4c  mov     edx, 89h; void *
0x18000dd51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd56  nop
0x18000dd57  mov     rcx, rdi; this
0x18000dd5a  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000dd5f  nop
0x18000dd60  jmp     loc_18000DE3F
0x18000dd65  mov     byte ptr cs:dword_1800B9294+1, 1
0x18000dd6c  mov     rcx, qword ptr cs:ppv
0x18000dd73  test    rcx, rcx
0x18000dd76  jz      short loc_18000DD90
0x18000dd78  mov     qword ptr cs:ppv, 0
0x18000dd83  mov     rax, [rcx]
0x18000dd86  mov     rax, [rax+10h]
0x18000dd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd8f  nop
0x18000dd90  lea     rax, ppv
0x18000dd97  mov     [rsp+78h+ppv], rax; int
0x18000dd9c  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000dda3  xor     edx, edx; pUnkOuter
0x18000dda5  lea     r8d, [rdx+1]; dwClsContext
0x18000dda9  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000ddb0  call    cs:__imp_CoCreateInstance
0x18000ddb6  mov     ebx, eax
0x18000ddb8  test    eax, eax
0x18000ddba  jns     short loc_18000DDE1
0x18000ddbc  mov     rcx, [rsp+78h]; this
0x18000ddc1  mov     r9d, eax; char *
0x18000ddc4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000ddcb  mov     edx, 8Dh; void *
0x18000ddd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddd5  nop
0x18000ddd6  mov     rcx, rdi; this
0x18000ddd9  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000ddde  nop
0x18000dddf  jmp     short loc_18000DE3F
0x18000dde1  mov     rcx, qword ptr cs:ppv
0x18000dde8  mov     rax, [rcx]
0x18000ddeb  mov     [rsp+78h+var_50], 0
0x18000ddf4  mov     dword ptr [rsp+78h+ppv], 5; int
0x18000ddfc  lea     r9, IID_IContextCallback
0x18000de03  mov     r8, rdi
0x18000de06  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x18000de0d  mov     rax, [rax+18h]
0x18000de11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de16  mov     ebx, eax
0x18000de18  test    eax, eax
0x18000de1a  jns     short loc_18000DE5C
0x18000de1c  mov     rcx, [rsp+78h]; this
0x18000de21  mov     r9d, eax; char *
0x18000de24  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000de2b  mov     edx, 90h; void *
0x18000de30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de35  nop
0x18000de36  mov     rcx, rdi; this
0x18000de39  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000de3e  nop
0x18000de3f  mov     edx, 4Eh ; 'N'; void *
0x18000de44  lea     r8, aOnecoreuapWind_25; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18000de4b  mov     r9d, ebx; char *
0x18000de4e  mov     rcx, [rsp+78h]; this
0x18000de53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de58  mov     eax, ebx
0x18000de5a  jmp     short loc_18000DE5E
0x18000de5c  xor     eax, eax
0x18000de5e  add     rsp, 48h
0x18000de62  pop     r15
0x18000de64  pop     r14
0x18000de66  pop     rdi
0x18000de67  pop     rsi
0x18000de68  pop     rbp
0x18000de69  pop     rbx
0x18000de6a  retn
0x18000de6b  call    cs:__imp_GetCurrentThreadId
0x18000de71  cmp     ebx, eax
0x18000de73  jz      short loc_18000DEAF
0x18000de75  xor     r9d, r9d; Context
0x18000de78  xor     r8d, r8d; Parameter
0x18000de7b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000de82  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000de89  call    cs:__imp_InitOnceExecuteOnce
0x18000de8f  mov     cs:byte_1800B92C0, 1
0x18000de96  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; this
0x18000de9d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000dea2  mov     ebx, eax
0x18000dea4  test    eax, eax
0x18000dea6  jns     short loc_18000DE5C
0x18000dea8  mov     edx, 57h ; 'W'
0x18000dead  jmp     short loc_18000DE44
0x18000deaf  mov     rcx, [rsp+78h]; this
0x18000deb4  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18000debb  mov     edx, 2Ch ; ','; void *
0x18000dec0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000dec6  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18000decd  mov     edx, 15Dh; void *
0x18000ded2  mov     rcx, rdi; this
0x18000ded5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
