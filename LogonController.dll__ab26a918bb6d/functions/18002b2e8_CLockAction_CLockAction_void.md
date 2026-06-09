# CLockAction::~CLockAction(void)

- ea: `0x18002b2e8`
- end: `0x18002b7e1`
- name: `??1CLockAction@@UEAA@XZ`
- size: `1273`
- prototype: `void __fastcall(CLockAction *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c630`

## callees

- `0x180008094`
- `0x18000df10`
- `0x18000f730`
- `0x180017dec`
- `0x18001c8f8`
- `0x18001ec34`
- `0x180028260`
- `0x180029f64`
- `0x18002a060`
- `0x18002a8e8`
- `0x18002b2e8`
- `0x18002b7e8`
- `0x18002b824`
- `0x18002bc20`
- `0x18002bc54`
- `0x18002bc8c`
- `0x18002bdf0`
- `0x18002fdec`
- `0x18002fe2c`
- `0x1800314a0`
- `0x180048f54`
- `0x18005f980`
- `0x180061188`
- `0x180063584`
- `0x18008d940`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18002b505`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18002b505`
- `KERNEL32!FreeLibrary` at `0x18002b620`
- `KERNEL32!FreeLibrary` at `0x18002b620`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b493`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b493`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b3ba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b3ba`
- `KERNEL32!CloseHandle` at `0x18002b63f`
- `KERNEL32!CloseHandle` at `0x18002b719`
- `KERNEL32!CloseHandle` at `0x18002b63f`
- `KERNEL32!CloseHandle` at `0x18002b719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7b5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002b4f0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002b4f0`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x18002b59d`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x18002b59d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CLockAction::~CLockAction(CLockAction *this)
{
  bool v2; // dl
  __int64 v3; // rcx
  __int64 v4; // r14
  char v5; // di
  void **v6; // rax
  int v7; // eax
  CLockAction *v8; // rcx
  unsigned int v9; // edx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  struct _TP_TIMER *v15; // rcx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  struct _TP_TIMER *v17; // rcx
  struct _TP_TIMER *v18; // rcx
  HMODULE v19; // rcx
  char *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  char *v27; // rcx
  int Parameter; // [rsp+20h] [rbp-20h] BYREF
  char v29; // [rsp+24h] [rbp-1Ch]
  int v30; // [rsp+28h] [rbp-18h]
  HANDLE Timer; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  CLockAction *v33; // [rsp+80h] [rbp+40h] BYREF
  CLockAction *v34; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)this = &CLockAction::`vftable'{for `Windows::Internal::UI::Logon::Controller::IUnlockTrigger'};
  *((_QWORD *)this + 1) = &CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>'};
  *((_QWORD *)this + 2) = &CLockAction::`vftable'{for `Windows::Internal::UI::Logon::Controller::ILockInfo'};
  *((_QWORD *)this + 3) = &CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>'};
  *((_QWORD *)this + 4) = &CLockAction::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &CLockAction::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 22) = &CLockAction::`vftable'{for `ILockAppHostDataCallback'};
  *((_QWORD *)this + 23) = &CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ILockAppHostDataSharedVisualCallback>'};
  CLockAction::UnboostLogonUI(this);
  v4 = v3 + 592;
  if ( *(_QWORD *)(v3 + 592) && *(_BYTE *)(v3 + 602) )
    *(_BYTE *)(v3 + 602) = 0;
  CLockAction::_OnLockAppShownWatchdogTimerExpired((CLockAction *)v3, v2);
  CLockAction::_OnTransitionFromLockAppWatchdogTimerExpired(this);
  CLockAction::_CleanupLockAppShownWatchdogTimer(this);
  if ( *((_BYTE *)this + 464) || (v5 = 0, *((_BYTE *)this + 465)) )
    v5 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v33 = 0;
  if ( *((_QWORD *)this + 43) )
  {
    v6 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(&v33);
    AgileGitPtr::CopyLocal((CLockAction *)((char *)this + 344), &GUID_d72586df_0aac_4c94_9370_9863360cdb6b, v6);
  }
  *((_BYTE *)this + 336) = 1;
  CTSmartObj<CLockAppHostDataConsumer *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release((char *)this + 352);
  if ( v5 )
  {
    if ( !v33 )
      goto LABEL_19;
    LogonControllerTelemetry::UnlockingFromLockAction();
    v34 = v33;
    if ( v33 )
      (*(void (__fastcall **)(CLockAction *))(*(_QWORD *)v33 + 8LL))(v33);
    v7 = InvokeWithRPCTimeout(
           *((void **)this + 56),
           CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_a6bc780042f7a252454a467f2d25944d___,
           &v34);
    if ( v7 < 0 )
      LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(v7);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v34);
  }
  if ( v33 )
  {
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v33);
    AgileGitPtr::Revoke((CLockAction *)((char *)this + 344));
    v8 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(CLockAction *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
LABEL_19:
  if ( this != (CLockAction *)-328LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 41);
  CLockAction::_CleanupThumbnail(this);
  CLockAction::_CleanupSharedVisual(this);
  v33 = this;
  if ( (unsigned int)IsDebuggerPresent(*((HANDLE *)this + 56)) )
  {
    v10 = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_950e8b8eee9887de371f2d3724243751___(&v33);
  }
  else
  {
    CRPCTimeout::CRPCTimeout(&Parameter, v9);
    v10 = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_950e8b8eee9887de371f2d3724243751___(&v33);
    if ( v10 < 0 && v29 )
      v10 = -2147417825;
    if ( v30 >= 0 )
    {
      v30 = -2147467259;
      CoDisableCallCancellation(0);
      if ( Timer )
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
  }
  if ( v10 < 0 )
  {
    LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(v10);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
      (const char *)(unsigned int)v10,
      Parameter);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 608);
  CTSmartObj<LockScreenCpuBooster *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(v4);
  v11 = *((_QWORD *)this + 73);
  if ( v11 )
  {
    *((_QWORD *)this + 73) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = *((_QWORD *)this + 72);
  if ( v12 )
  {
    *((_QWORD *)this + 72) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = (void *)*((_QWORD *)this + 71);
  if ( v13 )
    UnregisterPowerSettingNotification(v13);
  v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 69);
  if ( v14 )
    (**v14)(v14, 1);
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 67);
  if ( v15 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v15);
  v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 63);
  if ( v16 )
    (**v16)(v16, 1);
  v17 = (struct _TP_TIMER *)*((_QWORD *)this + 61);
  if ( v17 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v17);
  v18 = (struct _TP_TIMER *)*((_QWORD *)this + 60);
  if ( v18 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v18);
  v19 = (HMODULE)*((_QWORD *)this + 57);
  if ( v19 )
    FreeLibrary(v19);
  v20 = (char *)*((_QWORD *)this + 56);
  *((_QWORD *)this + 56) = 0;
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v20);
  v21 = *((_QWORD *)this + 54);
  if ( v21 )
  {
    *((_QWORD *)this + 54) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = *((_QWORD *)this + 53);
  if ( v22 )
  {
    *((_QWORD *)this + 53) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = *((_QWORD *)this + 52);
  if ( v23 )
  {
    *((_QWORD *)this + 52) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = *((_QWORD *)this + 51);
  if ( v24 )
  {
    *((_QWORD *)this + 51) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = *((_QWORD *)this + 50);
  if ( v25 )
  {
    *((_QWORD *)this + 50) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = *((_QWORD *)this + 49);
  if ( v26 )
  {
    *((_QWORD *)this + 49) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = (char *)*((_QWORD *)this + 47);
  *((_QWORD *)this + 47) = 0;
  if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v27);
  CTSmartObj<CLockAppHostDataConsumer *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release((char *)this + 352);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 344);
  if ( *((_QWORD *)this + 33) )
  {
    *((_QWORD *)this + 33) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  WindowsDeleteString(*((HSTRING *)this + 30));
  *((_QWORD *)this + 30) = 0;
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  WindowsDeleteString(*((HSTRING *)this + 28));
  *((_QWORD *)this + 28) = 0;
  WindowsDeleteString(*((HSTRING *)this + 27));
  *((_QWORD *)this + 27) = 0;
  WindowsDeleteString(*((HSTRING *)this + 26));
  *((_QWORD *)this + 26) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>(this);
}

```

## disassembly

```asm
0x18002b2e8  mov     [rsp-38h+arg_10], rbx
0x18002b2ed  push    rbp
0x18002b2ee  push    rsi
0x18002b2ef  push    rdi
0x18002b2f0  push    r12
0x18002b2f2  push    r13
0x18002b2f4  push    r14
0x18002b2f6  push    r15
0x18002b2f8  mov     rbp, rsp
0x18002b2fb  sub     rsp, 40h
0x18002b2ff  mov     rbx, rcx
0x18002b302  lea     rax, ??_7CLockAction@@6BIUnlockTrigger@Controller@Logon@UI@Internal@Windows@@@; const CLockAction::`vftable'{for `Windows::Internal::UI::Logon::Controller::IUnlockTrigger'}
0x18002b309  mov     [rcx], rax
0x18002b30c  lea     rax, ??_7CLockAction@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UILockInfo@Controller@Logon@UI@Internal@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@9Windows@@UILockAppHostDataCallback@@UILockAppHostDataSharedVisualCallback@@@Details@WRL@Microsoft@@@; const CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Internal::UI::Logon::Controller::ILockInfo,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>'}
0x18002b313  mov     [rcx+8], rax
0x18002b317  lea     rax, ??_7CLockAction@@6BILockInfo@Controller@Logon@UI@Internal@Windows@@@; const CLockAction::`vftable'{for `Windows::Internal::UI::Logon::Controller::ILockInfo'}
0x18002b31e  mov     [rcx+10h], rax
0x18002b322  lea     rax, ??_7CLockAction@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@6@UILockAppHostDataCallback@@UILockAppHostDataSharedVisualCallback@@@Details@WRL@Microsoft@@@; const CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,ILockAppHostDataCallback,ILockAppHostDataSharedVisualCallback>'}
0x18002b329  mov     [rcx+18h], rax
0x18002b32d  lea     rax, ??_7CLockAction@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const CLockAction::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18002b334  mov     [rcx+20h], rax
0x18002b338  lea     rax, ??_7CLockAction@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CLockAction::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18002b33f  mov     [rcx+70h], rax
0x18002b343  lea     rax, ??_7CLockAction@@6BILockAppHostDataCallback@@@; const CLockAction::`vftable'{for `ILockAppHostDataCallback'}
0x18002b34a  mov     [rcx+0B0h], rax
0x18002b351  lea     rax, ??_7CLockAction@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UILockAppHostDataSharedVisualCallback@@@Details@WRL@Microsoft@@@; const CLockAction::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ILockAppHostDataSharedVisualCallback>'}
0x18002b358  mov     [rcx+0B8h], rax
0x18002b35f  call    ?UnboostLogonUI@CLockAction@@AEAAXXZ; CLockAction::UnboostLogonUI(void)
0x18002b364  lea     r14, [rcx+250h]
0x18002b36b  xor     r13d, r13d
0x18002b36e  cmp     [r14], r13
0x18002b371  jz      short loc_18002B383
0x18002b373  cmp     [rcx+25Ah], r13b
0x18002b37a  jz      short loc_18002B383
0x18002b37c  mov     [rcx+25Ah], r13b
0x18002b383  call    ?_OnLockAppShownWatchdogTimerExpired@CLockAction@@AEAAX_N@Z; CLockAction::_OnLockAppShownWatchdogTimerExpired(bool)
0x18002b388  mov     rcx, rbx; this
0x18002b38b  call    ?_OnTransitionFromLockAppWatchdogTimerExpired@CLockAction@@AEAAXXZ; CLockAction::_OnTransitionFromLockAppWatchdogTimerExpired(void)
0x18002b390  mov     rcx, rbx; this
0x18002b393  call    ?_CleanupLockAppShownWatchdogTimer@CLockAction@@AEAAJXZ; CLockAction::_CleanupLockAppShownWatchdogTimer(void)
0x18002b398  cmp     [rbx+1D0h], r13b
0x18002b39f  jnz     short loc_18002B3AD
0x18002b3a1  cmp     [rbx+1D1h], r13b
0x18002b3a8  mov     dil, r13b
0x18002b3ab  jz      short loc_18002B3B0
0x18002b3ad  mov     dil, 1
0x18002b3b0  lea     rsi, [rbx+148h]
0x18002b3b7  mov     rcx, rsi; SRWLock
0x18002b3ba  call    cs:__imp_AcquireSRWLockExclusive
0x18002b3c0  mov     [rbp+arg_0], r13
0x18002b3c4  lea     r15, [rbx+158h]
0x18002b3cb  cmp     [r15], r13
0x18002b3ce  jz      short loc_18002B3EB
0x18002b3d0  lea     rcx, [rbp+arg_0]
0x18002b3d4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>)
0x18002b3d9  mov     r8, rax; void **
0x18002b3dc  lea     rdx, _GUID_d72586df_0aac_4c94_9370_9863360cdb6b; struct _GUID *
0x18002b3e3  mov     rcx, r15; this
0x18002b3e6  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18002b3eb  mov     byte ptr [rbx+150h], 1
0x18002b3f2  lea     r12, [rbx+160h]
0x18002b3f9  mov     rcx, r12
0x18002b3fc  call    ?Release@?$CTSmartObj@PEAVCLockAppHostDataConsumer@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CLockAppHostDataConsumer *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x18002b401  test    dil, dil
0x18002b404  jz      short loc_18002B458
0x18002b406  mov     rcx, [rbp+arg_0]
0x18002b40a  test    rcx, rcx
0x18002b40d  jz      short loc_18002B48B
0x18002b40f  call    ?UnlockingFromLockAction@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::UnlockingFromLockAction(void)
0x18002b414  mov     rcx, [rbp+arg_0]
0x18002b418  mov     [rbp+arg_8], rcx
0x18002b41c  test    rcx, rcx
0x18002b41f  jz      short loc_18002B42D
0x18002b421  mov     rax, [rcx]
0x18002b424  mov     rax, [rax+8]
0x18002b428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b42d  lea     r8, [rbp+arg_8]; void *
0x18002b431  lea     rdx, CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_a6bc780042f7a252454a467f2d25944d___; int (*)(void *)
0x18002b438  mov     rcx, [rbx+1C0h]; void *
0x18002b43f  call    ?InvokeWithRPCTimeout@@YAJPEAXP6AJ0@Z0@Z; InvokeWithRPCTimeout(void *,long (*)(void *),void *)
0x18002b444  test    eax, eax
0x18002b446  jns     short loc_18002B44F
0x18002b448  mov     ecx, eax; int
0x18002b44a  call    ?RPCTimeoutToLockScreenFailure@LogonControllerTelemetry@@SAXJ@Z; LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(long)
0x18002b44f  lea     rcx, [rbp+arg_8]
0x18002b453  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b458  mov     rcx, [rbp+arg_0]
0x18002b45c  test    rcx, rcx
0x18002b45f  jz      short loc_18002B48B
0x18002b461  lea     rcx, [rbp+arg_0]
0x18002b465  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b46a  mov     rcx, r15; this
0x18002b46d  call    ?Revoke@AgileGitPtr@@QEAAJXZ; AgileGitPtr::Revoke(void)
0x18002b472  mov     rcx, [rbp+arg_0]
0x18002b476  test    rcx, rcx
0x18002b479  jz      short loc_18002B48B
0x18002b47b  mov     [rbp+arg_0], r13
0x18002b47f  mov     rax, [rcx]
0x18002b482  mov     rax, [rax+10h]
0x18002b486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b48b  test    rsi, rsi
0x18002b48e  jz      short loc_18002B499
0x18002b490  mov     rcx, rsi; SRWLock
0x18002b493  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b499  mov     rcx, rbx; this
0x18002b49c  call    ?_CleanupThumbnail@CLockAction@@AEAAXXZ; CLockAction::_CleanupThumbnail(void)
0x18002b4a1  mov     rcx, rbx; this
0x18002b4a4  call    ?_CleanupSharedVisual@CLockAction@@AEAAXXZ; CLockAction::_CleanupSharedVisual(void)
0x18002b4a9  mov     [rbp+arg_0], rbx
0x18002b4ad  mov     rcx, [rbx+1C0h]; hProcess
0x18002b4b4  call    ?IsDebuggerPresent@@YAHPEAX@Z; IsDebuggerPresent(void *)
0x18002b4b9  test    eax, eax
0x18002b4bb  jnz     short loc_18002B50D
0x18002b4bd  lea     rcx, [rbp+Parameter]; Parameter
0x18002b4c1  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18002b4c6  lea     rcx, [rbp+arg_0]
0x18002b4ca  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_950e8b8eee9887de371f2d3724243751___
0x18002b4cf  mov     edi, eax
0x18002b4d1  test    eax, eax
0x18002b4d3  jns     short loc_18002B4E1
0x18002b4d5  mov     eax, 8001011Fh
0x18002b4da  cmp     [rbp+var_1C], r13b
0x18002b4de  cmovnz  edi, eax
0x18002b4e1  cmp     [rbp+var_18], r13d
0x18002b4e5  jl      short loc_18002B518
0x18002b4e7  mov     [rbp+var_18], 80004005h
0x18002b4ee  xor     ecx, ecx; pReserved
0x18002b4f0  call    cs:__imp_CoDisableCallCancellation
0x18002b4f6  mov     rdx, [rbp+Timer]; Timer
0x18002b4fa  test    rdx, rdx
0x18002b4fd  jz      short loc_18002B518
0x18002b4ff  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002b503  xor     ecx, ecx; TimerQueue
0x18002b505  call    cs:__imp_DeleteTimerQueueTimer
0x18002b50b  jmp     short loc_18002B518
0x18002b50d  lea     rcx, [rbp+arg_0]
0x18002b511  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_950e8b8eee9887de371f2d3724243751___
0x18002b516  mov     edi, eax
0x18002b518  test    edi, edi
0x18002b51a  jns     short loc_18002B523
0x18002b51c  mov     ecx, edi; int
0x18002b51e  call    ?RPCTimeoutToLockScreenFailure@LogonControllerTelemetry@@SAXJ@Z; LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(long)
0x18002b523  mov     rcx, [rbp+38h]; this
0x18002b527  test    edi, edi
0x18002b529  jns     short loc_18002B53F
0x18002b52b  mov     r9d, edi; char *
0x18002b52e  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002b535  mov     edx, 5Ah ; 'Z'; void *
0x18002b53a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b53f  lea     rcx, [rbx+260h]
0x18002b546  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002b54b  mov     rcx, r14
0x18002b54e  call    ?Release@?$CTSmartObj@PEAVLockScreenCpuBooster@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<LockScreenCpuBooster *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x18002b553  mov     rcx, [rbx+248h]
0x18002b55a  test    rcx, rcx
0x18002b55d  jz      short loc_18002B572
0x18002b55f  mov     [rbx+248h], r13
0x18002b566  mov     rax, [rcx]
0x18002b569  mov     rax, [rax+10h]
0x18002b56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b572  mov     rcx, [rbx+240h]
0x18002b579  test    rcx, rcx
0x18002b57c  jz      short loc_18002B591
0x18002b57e  mov     [rbx+240h], r13
0x18002b585  mov     rax, [rcx]
0x18002b588  mov     rax, [rax+10h]
0x18002b58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b591  mov     rcx, [rbx+238h]; Handle
0x18002b598  test    rcx, rcx
0x18002b59b  jz      short loc_18002B5A4
0x18002b59d  call    cs:__imp_UnregisterPowerSettingNotification
0x18002b5a3  nop
0x18002b5a4  mov     rcx, [rbx+228h]
0x18002b5ab  test    rcx, rcx
0x18002b5ae  jz      short loc_18002B5C1
0x18002b5b0  mov     rax, [rcx]
0x18002b5b3  mov     edx, 1
0x18002b5b8  mov     rax, [rax]
0x18002b5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5c0  nop
0x18002b5c1  mov     rcx, [rbx+218h]; pti
0x18002b5c8  test    rcx, rcx
0x18002b5cb  jz      short loc_18002B5D3
0x18002b5cd  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002b5d2  nop
0x18002b5d3  mov     rcx, [rbx+1F8h]
0x18002b5da  test    rcx, rcx
0x18002b5dd  jz      short loc_18002B5F0
0x18002b5df  mov     rax, [rcx]
0x18002b5e2  mov     edx, 1
0x18002b5e7  mov     rax, [rax]
0x18002b5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ef  nop
0x18002b5f0  mov     rcx, [rbx+1E8h]; pti
0x18002b5f7  test    rcx, rcx
0x18002b5fa  jz      short loc_18002B602
0x18002b5fc  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002b601  nop
0x18002b602  mov     rcx, [rbx+1E0h]; pti
0x18002b609  test    rcx, rcx
0x18002b60c  jz      short loc_18002B614
0x18002b60e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002b613  nop
0x18002b614  mov     rcx, [rbx+1C8h]; hLibModule
0x18002b61b  test    rcx, rcx
0x18002b61e  jz      short loc_18002B627
0x18002b620  call    cs:__imp_FreeLibrary
0x18002b626  nop
0x18002b627  mov     rcx, [rbx+1C0h]; hObject
0x18002b62e  mov     [rbx+1C0h], r13
0x18002b635  lea     rax, [rcx-1]
0x18002b639  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b63d  ja      short loc_18002B646
0x18002b63f  call    cs:__imp_CloseHandle
0x18002b645  nop
0x18002b646  mov     rcx, [rbx+1B0h]
0x18002b64d  test    rcx, rcx
0x18002b650  jz      short loc_18002B665
0x18002b652  mov     [rbx+1B0h], r13
0x18002b659  mov     rax, [rcx]
0x18002b65c  mov     rax, [rax+10h]
0x18002b660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b665  mov     rcx, [rbx+1A8h]
0x18002b66c  test    rcx, rcx
0x18002b66f  jz      short loc_18002B684
0x18002b671  mov     [rbx+1A8h], r13
0x18002b678  mov     rax, [rcx]
0x18002b67b  mov     rax, [rax+10h]
0x18002b67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b684  mov     rcx, [rbx+1A0h]
0x18002b68b  test    rcx, rcx
0x18002b68e  jz      short loc_18002B6A3
0x18002b690  mov     [rbx+1A0h], r13
0x18002b697  mov     rax, [rcx]
0x18002b69a  mov     rax, [rax+10h]
0x18002b69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6a3  mov     rcx, [rbx+198h]
0x18002b6aa  test    rcx, rcx
0x18002b6ad  jz      short loc_18002B6C2
0x18002b6af  mov     [rbx+198h], r13
0x18002b6b6  mov     rax, [rcx]
0x18002b6b9  mov     rax, [rax+10h]
0x18002b6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6c2  mov     rcx, [rbx+190h]
0x18002b6c9  test    rcx, rcx
0x18002b6cc  jz      short loc_18002B6E1
0x18002b6ce  mov     [rbx+190h], r13
0x18002b6d5  mov     rax, [rcx]
0x18002b6d8  mov     rax, [rax+10h]
0x18002b6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6e1  mov     rcx, [rbx+188h]
0x18002b6e8  test    rcx, rcx
0x18002b6eb  jz      short loc_18002B701
0x18002b6ed  mov     [rbx+188h], r13
0x18002b6f4  mov     rax, [rcx]
0x18002b6f7  mov     rax, [rax+10h]
0x18002b6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b700  nop
0x18002b701  mov     rcx, [rbx+178h]; hObject
0x18002b708  mov     [rbx+178h], r13
0x18002b70f  lea     rax, [rcx-1]
0x18002b713  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b717  ja      short loc_18002B720
0x18002b719  call    cs:__imp_CloseHandle
0x18002b71f  nop
0x18002b720  mov     rcx, r12
0x18002b723  call    ?Release@?$CTSmartObj@PEAVCLockAppHostDataConsumer@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CLockAppHostDataConsumer *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x18002b728  nop
0x18002b729  mov     rcx, r15
0x18002b72c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002b731  nop
0x18002b732  mov     rcx, [rbx+108h]
0x18002b739  test    rcx, rcx
0x18002b73c  jz      short loc_18002B74A
0x18002b73e  mov     [rbx+108h], r13
0x18002b745  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18002b74a  mov     rcx, [rbx+0F8h]; string
0x18002b751  call    cs:__imp_WindowsDeleteString
0x18002b757  mov     [rbx+0F8h], r13
0x18002b75e  mov     rcx, [rbx+0F0h]; string
0x18002b765  call    cs:__imp_WindowsDeleteString
0x18002b76b  mov     [rbx+0F0h], r13
0x18002b772  mov     rcx, [rbx+0E8h]; string
0x18002b779  call    cs:__imp_WindowsDeleteString
0x18002b77f  mov     [rbx+0E8h], r13
0x18002b786  mov     rcx, [rbx+0E0h]; string
0x18002b78d  call    cs:__imp_WindowsDeleteString
0x18002b793  mov     [rbx+0E0h], r13
0x18002b79a  mov     rcx, [rbx+0D8h]; string
0x18002b7a1  call    cs:__imp_WindowsDeleteString
0x18002b7a7  mov     [rbx+0D8h], r13
0x18002b7ae  mov     rcx, [rbx+0D0h]; string
0x18002b7b5  call    cs:__imp_WindowsDeleteString
0x18002b7bb  mov     [rbx+0D0h], r13
0x18002b7c2  mov     rcx, rbx
0x18002b7c5  mov     rbx, [rsp+40h+arg_10]
0x18002b7cd  add     rsp, 40h
0x18002b7d1  pop     r15
0x18002b7d3  pop     r14
0x18002b7d5  pop     r13
  ... truncated ...
```
