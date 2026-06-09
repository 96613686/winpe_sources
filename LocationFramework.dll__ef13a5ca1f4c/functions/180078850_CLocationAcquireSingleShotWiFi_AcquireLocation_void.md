# CLocationAcquireSingleShotWiFi::AcquireLocation(void)

- ea: `0x180078850`
- end: `0x180078d41`
- name: `?AcquireLocation@CLocationAcquireSingleShotWiFi@@UEAAJXZ`
- size: `1265`
- prototype: `__int64 __fastcall(CLocationAcquireSingleShotWiFi *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c974`
- `0x18000c9a4`
- `0x180012398`
- `0x18001be08`
- `0x18003a940`
- `0x18003b92c`
- `0x1800451d4`
- `0x18004b714`
- `0x18004ce9c`
- `0x180053618`
- `0x180055534`
- `0x180058b78`
- `0x18005bcd4`
- `0x180078850`
- `0x1800791e4`
- `0x180079290`
- `0x180079a74`
- `0x1800a98c0`
- `0x1800b8410`
- `0x180110868`
- `0x180110c74`
- `0x1801135c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180078ca3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180078ca3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078884`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800789a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078aca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078cac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078884`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800789a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078aca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b37`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180078cd0`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180078cd0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180078b2d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180078b2d`

## string_xrefs

- `0x18007894d`: `pWiFiProvider->get_UseScanCache(&useScanCache)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLocationAcquireSingleShotWiFi::AcquireLocation(CLocationAcquireSingleShotWiFi *this)
{
  struct ILocationSessionInternal *v2; // rbx
  int v3; // r8d
  int v4; // r9d
  unsigned int v5; // r15d
  int v6; // eax
  __int64 v7; // rsi
  bool v8; // di
  int v9; // edi
  char v10; // si
  int FirstSubscriberSession; // eax
  wil::details::in1diag5 *v12; // rcx
  const char *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // r8d
  int v19; // edi
  int v20; // eax
  struct _TP_WAIT *v21; // rcx
  char *v23; // [rsp+28h] [rbp-81h]
  struct ILocationSessionInternal *v24; // [rsp+30h] [rbp-79h] BYREF
  struct ILocationInformation *v25; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v27[2]; // [rsp+50h] [rbp-59h] BYREF
  int v28; // [rsp+70h] [rbp-39h]
  char v29[8]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v30; // [rsp+88h] [rbp-21h] BYREF
  __int128 v31; // [rsp+90h] [rbp-19h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-9h]
  int v33; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag5 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = (CLocationAcquireSingleShotWiFi *)((char *)this + 328);
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v24 = v2;
  v5 = 0;
  if ( *((_DWORD *)this + 86) )
  {
    if ( (unsigned int)dword_1801DDF30 > 5 )
    {
      LODWORD(v25) = *((_DWORD *)this + 86);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1801DDF30,
        (unsigned int)byte_1801B31B9,
        v3,
        v4,
        (__int64)&v25);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    return 0;
  }
  if ( (unsigned int)dword_1801DDF30 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801DDF30,
      qword_1801B3228);
  *((_DWORD *)this + 86) = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
  CLocationThreadpoolWait_Impl<0>::StartWait((char *)this + 400, 0xFFFFFFFFLL);
  v30 = 0;
  ATL::CComQIPtr<ILocationProviderWiFi,&__s_GUID const _GUID_819da25d_7a97_47b2_b7bc_d07145a4b5b3>::CComQIPtr<ILocationProviderWiFi,&__s_GUID const _GUID_819da25d_7a97_47b2_b7bc_d07145a4b5b3>(
    &v30,
    *((_QWORD *)this + 3));
  v29[0] = 1;
  v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v30 + 256LL))(v30, v29);
  if ( v6 < 0 )
  {
    LODWORD(v23) = v6;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\wifi\\locationacquiresingleshotwifi.cpp",
      "CLocationAcquireSingleShotWiFi::AcquireLocation",
      "pWiFiProvider->get_UseScanCache(&useScanCache)",
      v23,
      (int)v24);
  }
  v7 = *((_QWORD *)this + 48);
  v8 = v29[0] != 0;
  v24 = 0;
  wil::EnterCriticalSection(&v24, v7);
  *(_BYTE *)(v7 + 48) = v8;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v24);
  AcquireSRWLockExclusive((PSRWLOCK)v2);
  v24 = v2;
  ATL::CComPtr<ILocationProvider>::operator=((char *)this + 376, 0);
  ATL::CComPtr<ILocationProvider>::operator=((char *)this + 360, 0);
  *((_DWORD *)this + 87) = CLocationAcquireSingleShotWiFi::GetPositioningMode(this);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
  if ( !*((_QWORD *)this + 37) || (v9 = 0, (unsigned int)CLocationAcquireSingleShotWiFi::GetPositioningMode(this) != 1) )
    v9 = 1;
  v10 = 0;
  v25 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v24 = 0;
  do
  {
    FirstSubscriberSession = CLocationAcquireBase::GetFirstSubscriberSession(this, &v24);
    v12 = retaddr;
    if ( FirstSubscriberSession < 0 )
    {
      LODWORD(v23) = FirstSubscriberSession;
      v13 = "hr";
      v14 = 187;
LABEL_17:
      wil::details::in1diag5::_Log_Hr(
        v12,
        (void *)v14,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\wifi\\locationacquiresingleshotwifi.cpp",
        "CLocationAcquireSingleShotWiFi::AcquireLocation",
        v13,
        v23,
        (int)v24);
      goto LABEL_18;
    }
    v15 = (*(__int64 (__fastcall **)(struct ILocationSessionInternal *, __int128 *))(*(_QWORD *)v24 + 72LL))(v24, &v31);
    v12 = retaddr;
    if ( v15 < 0 )
    {
      LODWORD(v23) = v15;
      v13 = "session->get_LocationRequest(&locationRequest)";
      v14 = 191;
      goto LABEL_17;
    }
LABEL_18:
    if ( (unsigned int)(v9 - 1) <= 1 )
    {
      v27[0] = v31;
      v27[1] = v32;
      v28 = v33;
      CLocationInferenceAcquire::Initiate(*((_QWORD *)this + 39), v27);
    }
    else if ( !v9 )
    {
      CLocationFtmAcquire::Initiate(*((CLocationFtmAcquire **)this + 37));
    }
    AcquireSRWLockExclusive((PSRWLOCK)v2);
    v26[0] = v2;
    while ( 1 )
    {
      if ( *((_BYTE *)this + 536) )
      {
        if ( (unsigned int)dword_1801DDF30 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1801DDF30,
            &word_1801B328E);
        v10 = 1;
        goto LABEL_36;
      }
      v16 = *((_DWORD *)this + 92);
      if ( v16 >= 0 && *((_QWORD *)this + 47) )
      {
        ATL::CComPtr<ILocationInformation>::operator=(&v25);
        v5 = 1;
LABEL_36:
        v9 = 3;
        goto LABEL_37;
      }
      v17 = *((_DWORD *)this + 88);
      if ( v17 >= 0 )
      {
        if ( !*((_QWORD *)this + 45) )
          goto LABEL_29;
        if ( v16 != -2147483638 )
        {
          ATL::CComPtr<ILocationInformation>::operator=(&v25);
          v5 = 0;
          goto LABEL_36;
        }
      }
      if ( v17 == -2147483638 )
        goto LABEL_30;
LABEL_29:
      if ( v16 != -2147483638 )
        break;
LABEL_30:
      if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 42, (PSRWLOCK)v2, 0xFFFFFFFF, 0)
        && GetLastError() != 1460 )
      {
        wil::details::in1diag5::FailFast_Unexpected(
          retaddr,
          (void *)0xF46,
          v18,
          "wil::condition_variable::wait_for",
          "result || ::GetLastError() == ERROR_TIMEOUT",
          v23);
      }
    }
    if ( v9 )
      goto LABEL_36;
    v9 = 2;
    *((_DWORD *)this + 87) = 0;
    if ( (unsigned int)dword_1801DDF30 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1801DDF30,
        &unk_1801B3310);
LABEL_37:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
  }
  while ( v9 != 3 );
  if ( !v10 )
  {
    if ( v25 )
    {
      CLocationAcquireSingleShotWiFi::PostPositionToSubscribersInternal(this, v25);
      AcquireSRWLockExclusive((PSRWLOCK)v2);
      v26[0] = v2;
      v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 62) + 24LL))((char *)this + 496);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
      if ( (unsigned int)CLocationAcquireSingleShotWiFi::GetPositioningMode(this) != 1 || !v19 )
      {
        v20 = CLocationAcquireSingleShotWiFi::SetPositioningMode(this, v5);
        if ( v20 < 0 )
        {
          LODWORD(v23) = v20;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x12F,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\wifi\\locationacquiresingleshotwifi.cpp",
            "CLocationAcquireSingleShotWiFi::AcquireLocation",
            "SetPositioningMode(positioningModeUsed)",
            v23,
            (int)v24);
        }
      }
    }
    else
    {
      CLocationAcquireSingleShotWiFi::PostErrorToSubscribers(this, -2147024664);
    }
  }
  CLocationThreadpoolWait_Impl<0>::CancelWait((char *)this + 400);
  v21 = (struct _TP_WAIT *)*((_QWORD *)this + 52);
  if ( v21 )
    WaitForThreadpoolWaitCallbacks(v21, 1);
  AcquireSRWLockExclusive((PSRWLOCK)v2);
  v26[0] = v2;
  *((_BYTE *)this + 536) = 0;
  *((_DWORD *)this + 86) = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 42);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  return 0;
}

```

## disassembly

```asm
0x180078850  push    rbp
0x180078852  push    rbx
0x180078853  push    rsi
0x180078854  push    rdi
0x180078855  push    r12
0x180078857  push    r13
0x180078859  push    r14
0x18007885b  push    r15
0x18007885d  lea     rbp, [rsp-1Fh]
0x180078862  sub     rsp, 0C8h
0x180078869  mov     rax, cs:__security_cookie
0x180078870  xor     rax, rsp
0x180078873  mov     [rbp+57h+var_48], rax
0x180078877  mov     r14, rcx
0x18007887a  lea     rbx, [rcx+148h]
0x180078881  mov     rcx, rbx; SRWLock
0x180078884  call    cs:__imp_AcquireSRWLockExclusive
0x18007888a  mov     [rbp+57h+var_D0], rbx
0x18007888e  xor     r15d, r15d
0x180078891  cmp     [r14+158h], r15d
0x180078898  mov     eax, cs:dword_1801DDF30
0x18007889e  jz      short loc_1800788D9
0x1800788a0  cmp     eax, 5
0x1800788a3  jbe     short loc_1800788CB
0x1800788a5  mov     eax, [r14+158h]
0x1800788ac  mov     dword ptr [rbp+57h+var_C8], eax
0x1800788af  lea     rax, [rbp+57h+var_C8]
0x1800788b3  mov     [rsp+100h+var_E0], rax
0x1800788b8  lea     rdx, byte_1801B31B9
0x1800788bf  lea     rcx, dword_1801DDF30
0x1800788c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800788cb  lea     rcx, [rbp+57h+var_D0]
0x1800788cf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800788d4  jmp     loc_180078CFD
0x1800788d9  cmp     eax, 5
0x1800788dc  jbe     short loc_1800788F1
0x1800788de  lea     rdx, qword_1801B3228
0x1800788e5  lea     rcx, dword_1801DDF30
0x1800788ec  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800788f1  mov     dword ptr [r14+158h], 1
0x1800788fc  lea     rcx, [rbp+57h+var_D0]
0x180078900  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180078905  lea     rcx, [r14+190h]
0x18007890c  or      edx, 0FFFFFFFFh
0x18007890f  call    ?StartWait@?$CLocationThreadpoolWait_Impl@$0A@@@QEAAXK@Z; CLocationThreadpoolWait_Impl<0>::StartWait(ulong)
0x180078914  mov     [rbp+57h+var_78], r15
0x180078918  mov     rdx, [r14+18h]
0x18007891c  lea     rcx, [rbp+57h+var_78]
0x180078920  call    ??0?$CComQIPtr@UILocationProviderWiFi@@$1?_GUID_819da25d_7a97_47b2_b7bc_d07145a4b5b3@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ILocationProviderWiFi,&__s_GUID const _GUID_819da25d_7a97_47b2_b7bc_d07145a4b5b3>::CComQIPtr<ILocationProviderWiFi,&__s_GUID const _GUID_819da25d_7a97_47b2_b7bc_d07145a4b5b3>(IUnknown *)
0x180078925  nop
0x180078926  mov     [rbp+57h+var_80], 1
0x18007892a  mov     rcx, [rbp+57h+var_78]
0x18007892e  mov     rax, [rcx]
0x180078931  lea     rdx, [rbp+57h+var_80]
0x180078935  mov     rax, [rax+100h]
0x18007893c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078941  mov     rcx, [rbp+5Fh]; this
0x180078945  test    eax, eax
0x180078947  jns     short loc_180078971
0x180078949  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x18007894d  lea     rax, aPwifiproviderG_0; "pWiFiProvider->get_UseScanCache(&useSca"...
0x180078954  mov     [rsp+100h+var_E0], rax; char *
0x180078959  lea     r9, aClocationacqui_9; "CLocationAcquireSingleShotWiFi::Acquire"...
0x180078960  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\location"...
0x180078967  mov     edx, 94h; void *
0x18007896c  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180078971  mov     rsi, [r14+180h]
0x180078978  cmp     [rbp+57h+var_80], r15b
0x18007897c  setnz   dil
0x180078980  mov     [rbp+57h+var_D0], r15
0x180078984  mov     rdx, rsi
0x180078987  lea     rcx, [rbp+57h+var_D0]
0x18007898b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180078990  mov     [rsi+30h], dil
0x180078994  lea     rcx, [rbp+57h+var_D0]
0x180078998  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18007899d  mov     rcx, rbx; SRWLock
0x1800789a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800789a6  mov     [rbp+57h+var_D0], rbx
0x1800789aa  lea     r12, [r14+178h]
0x1800789b1  xor     edx, edx
0x1800789b3  mov     rcx, r12
0x1800789b6  call    ??4?$CComPtr@UILocationProvider@@@ATL@@QEAAPEAUILocationProvider@@PEAU2@@Z; ATL::CComPtr<ILocationProvider>::operator=(ILocationProvider *)
0x1800789bb  lea     r13, [r14+168h]
0x1800789c2  xor     edx, edx
0x1800789c4  mov     rcx, r13
0x1800789c7  call    ??4?$CComPtr@UILocationProvider@@@ATL@@QEAAPEAUILocationProvider@@PEAU2@@Z; ATL::CComPtr<ILocationProvider>::operator=(ILocationProvider *)
0x1800789cc  mov     rcx, r14
0x1800789cf  call    ?GetPositioningMode@CLocationAcquireSingleShotWiFi@@AEAA?AW4__MIDL___MIDL_itf_wifipe_0000_0000_0013@@XZ; CLocationAcquireSingleShotWiFi::GetPositioningMode(void)
0x1800789d4  mov     [r14+15Ch], eax
0x1800789db  lea     rcx, [rbp+57h+var_D0]
0x1800789df  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800789e4  cmp     [r14+128h], r15
0x1800789eb  jz      short loc_1800789FD
0x1800789ed  mov     rcx, r14
0x1800789f0  call    ?GetPositioningMode@CLocationAcquireSingleShotWiFi@@AEAA?AW4__MIDL___MIDL_itf_wifipe_0000_0000_0013@@XZ; CLocationAcquireSingleShotWiFi::GetPositioningMode(void)
0x1800789f5  cmp     eax, 1
0x1800789f8  mov     edi, r15d
0x1800789fb  jz      short loc_180078A02
0x1800789fd  mov     edi, 1
0x180078a02  mov     sil, r15b
0x180078a05  mov     [rbp+57h+var_C8], r15
0x180078a09  xorps   xmm0, xmm0
0x180078a0c  xor     eax, eax
0x180078a0e  movups  [rbp+57h+var_70], xmm0
0x180078a12  movups  [rbp+57h+var_60], xmm0
0x180078a16  mov     [rbp+57h+var_50], eax
0x180078a19  mov     [rbp+57h+var_D0], rax
0x180078a1d  lea     rdx, [rbp+57h+var_D0]; struct ILocationSessionInternal **
0x180078a21  mov     rcx, r14; this
0x180078a24  call    ?GetFirstSubscriberSession@CLocationAcquireBase@@QEAAJPEAPEAUILocationSessionInternal@@@Z; CLocationAcquireBase::GetFirstSubscriberSession(ILocationSessionInternal * *)
0x180078a29  mov     rcx, [rbp+5Fh]
0x180078a2d  test    eax, eax
0x180078a2f  jns     short loc_180078A43
0x180078a31  mov     dword ptr [rsp+100h+var_D8], eax
0x180078a35  lea     rax, aHr; "hr"
0x180078a3c  mov     edx, 0BBh
0x180078a41  jmp     short loc_180078A6F
0x180078a43  mov     rcx, [rbp+57h+var_D0]
0x180078a47  mov     rax, [rcx]
0x180078a4a  lea     rdx, [rbp+57h+var_70]
0x180078a4e  mov     rax, [rax+48h]
0x180078a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a57  mov     rcx, [rbp+5Fh]; this
0x180078a5b  test    eax, eax
0x180078a5d  jns     short loc_180078A87
0x180078a5f  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180078a63  lea     rax, aSessionGetLoca; "session->get_LocationRequest(&locationR"...
0x180078a6a  mov     edx, 0BFh; void *
0x180078a6f  mov     [rsp+100h+var_E0], rax; char *
0x180078a74  lea     r9, aClocationacqui_9; "CLocationAcquireSingleShotWiFi::Acquire"...
0x180078a7b  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\location"...
0x180078a82  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180078a87  lea     eax, [rdi-1]
0x180078a8a  cmp     eax, 1
0x180078a8d  jbe     short loc_180078AA1
0x180078a8f  test    edi, edi
0x180078a91  jnz     short loc_180078AC7
0x180078a93  mov     rcx, [r14+128h]; this
0x180078a9a  call    ?Initiate@CLocationFtmAcquire@@QEAAXXZ; CLocationFtmAcquire::Initiate(void)
0x180078a9f  jmp     short loc_180078AC7
0x180078aa1  movups  xmm0, [rbp+57h+var_70]
0x180078aa5  movaps  [rbp+57h+var_B0], xmm0
0x180078aa9  movups  xmm1, [rbp+57h+var_60]
0x180078aad  movaps  [rbp+57h+var_A0], xmm1
0x180078ab1  mov     eax, [rbp+57h+var_50]
0x180078ab4  mov     [rbp+57h+var_90], eax
0x180078ab7  lea     rdx, [rbp+57h+var_B0]
0x180078abb  mov     rcx, [r14+138h]
0x180078ac2  call    ?Initiate@CLocationInferenceAcquire@@QEAAXULOCATIONREQUEST@@@Z; CLocationInferenceAcquire::Initiate(LOCATIONREQUEST)
0x180078ac7  mov     rcx, rbx; SRWLock
0x180078aca  call    cs:__imp_AcquireSRWLockExclusive
0x180078ad0  mov     [rbp+57h+var_C0], rbx
0x180078ad4  jmp     short loc_180078B48
0x180078ad6  mov     eax, [r14+170h]
0x180078add  test    eax, eax
0x180078adf  js      short loc_180078AEC
0x180078ae1  cmp     qword ptr [r12], 0
0x180078ae6  jnz     loc_180078BAE
0x180078aec  mov     ecx, [r14+160h]
0x180078af3  test    ecx, ecx
0x180078af5  js      short loc_180078B09
0x180078af7  cmp     qword ptr [r13+0], 0
0x180078afc  jz      short loc_180078B11
0x180078afe  cmp     eax, 8000000Ah
0x180078b03  jnz     loc_180078BC2
0x180078b09  cmp     ecx, 8000000Ah
0x180078b0f  jz      short loc_180078B1C
0x180078b11  cmp     eax, 8000000Ah
0x180078b16  jnz     loc_180078BD3
0x180078b1c  lea     rcx, [r14+150h]; ConditionVariable
0x180078b23  xor     r9d, r9d; Flags
0x180078b26  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180078b2a  mov     rdx, rbx; SRWLock
0x180078b2d  call    cs:__imp_SleepConditionVariableSRW
0x180078b33  test    eax, eax
0x180078b35  jnz     short loc_180078B48
0x180078b37  call    cs:__imp_GetLastError
0x180078b3d  cmp     eax, 5B4h
0x180078b42  jnz     loc_180078D1F
0x180078b48  cmp     byte ptr [r14+218h], 0
0x180078b50  jz      short loc_180078AD6
0x180078b52  mov     eax, cs:dword_1801DDF30
0x180078b58  cmp     eax, 5
0x180078b5b  jbe     short loc_180078B70
0x180078b5d  lea     rdx, word_1801B328E
0x180078b64  lea     rcx, dword_1801DDF30
0x180078b6b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180078b70  mov     sil, 1
0x180078b73  mov     edi, 3
0x180078b78  lea     rcx, [rbp+57h+var_C0]
0x180078b7c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180078b81  cmp     edi, 3
0x180078b84  jnz     loc_180078A1D
0x180078b8a  test    sil, sil
0x180078b8d  jnz     loc_180078C86
0x180078b93  mov     rdx, [rbp+57h+var_C8]; struct ILocationInformation *
0x180078b97  mov     rcx, r14; this
0x180078b9a  test    rdx, rdx
0x180078b9d  jnz     short loc_180078C0A
0x180078b9f  mov     edx, 800700E8h; int
0x180078ba4  call    ?PostErrorToSubscribers@CLocationAcquireSingleShotWiFi@@AEAAXJ@Z; CLocationAcquireSingleShotWiFi::PostErrorToSubscribers(long)
0x180078ba9  jmp     loc_180078C86
0x180078bae  mov     rdx, r12
0x180078bb1  lea     rcx, [rbp+57h+var_C8]
0x180078bb5  call    ??4?$CComPtr@UILocationInformation@@@ATL@@QEAAPEAUILocationInformation@@AEBV01@@Z; ATL::CComPtr<ILocationInformation>::operator=(ATL::CComPtr<ILocationInformation> const &)
0x180078bba  mov     r15d, 1
0x180078bc0  jmp     short loc_180078B73
0x180078bc2  mov     rdx, r13
0x180078bc5  lea     rcx, [rbp+57h+var_C8]
0x180078bc9  call    ??4?$CComPtr@UILocationInformation@@@ATL@@QEAAPEAUILocationInformation@@AEBV01@@Z; ATL::CComPtr<ILocationInformation>::operator=(ATL::CComPtr<ILocationInformation> const &)
0x180078bce  xor     r15d, r15d
0x180078bd1  jmp     short loc_180078B73
0x180078bd3  test    edi, edi
0x180078bd5  jnz     short loc_180078B73
0x180078bd7  mov     edi, 2
0x180078bdc  mov     dword ptr [r14+15Ch], 0
0x180078be7  mov     eax, cs:dword_1801DDF30
0x180078bed  cmp     eax, 5
0x180078bf0  jbe     short loc_180078B78
0x180078bf2  lea     rdx, unk_1801B3310
0x180078bf9  lea     rcx, dword_1801DDF30
0x180078c00  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180078c05  jmp     loc_180078B78
0x180078c0a  call    ?PostPositionToSubscribersInternal@CLocationAcquireSingleShotWiFi@@AEAAXPEAUILocationInformation@@@Z; CLocationAcquireSingleShotWiFi::PostPositionToSubscribersInternal(ILocationInformation *)
0x180078c0f  mov     rcx, rbx; SRWLock
0x180078c12  call    cs:__imp_AcquireSRWLockExclusive
0x180078c18  mov     [rbp+57h+var_C0], rbx
0x180078c1c  lea     rcx, [r14+1F0h]
0x180078c23  mov     rax, [rcx]
0x180078c26  mov     rax, [rax+18h]
0x180078c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c2f  mov     edi, eax
0x180078c31  lea     rcx, [rbp+57h+var_C0]
0x180078c35  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180078c3a  mov     rcx, r14
0x180078c3d  call    ?GetPositioningMode@CLocationAcquireSingleShotWiFi@@AEAA?AW4__MIDL___MIDL_itf_wifipe_0000_0000_0013@@XZ; CLocationAcquireSingleShotWiFi::GetPositioningMode(void)
0x180078c42  cmp     eax, 1
0x180078c45  jnz     short loc_180078C4B
0x180078c47  test    edi, edi
0x180078c49  jnz     short loc_180078C86
0x180078c4b  mov     edx, r15d
0x180078c4e  mov     rcx, r14
0x180078c51  call    ?SetPositioningMode@CLocationAcquireSingleShotWiFi@@AEAAJW4__MIDL___MIDL_itf_wifipe_0000_0000_0013@@@Z; CLocationAcquireSingleShotWiFi::SetPositioningMode(__MIDL___MIDL_itf_wifipe_0000_0000_0013)
0x180078c56  mov     rcx, [rbp+5Fh]; this
0x180078c5a  test    eax, eax
0x180078c5c  jns     short loc_180078C86
0x180078c5e  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180078c62  lea     rax, aSetpositioning; "SetPositioningMode(positioningModeUsed)"
0x180078c69  mov     [rsp+100h+var_E0], rax; char *
0x180078c6e  lea     r9, aClocationacqui_9; "CLocationAcquireSingleShotWiFi::Acquire"...
0x180078c75  lea     r8, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\location"...
0x180078c7c  mov     edx, 12Fh; void *
0x180078c81  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180078c86  lea     rcx, [r14+190h]
0x180078c8d  call    ?CancelWait@?$CLocationThreadpoolWait_Impl@$0A@@@QEAAXXZ; CLocationThreadpoolWait_Impl<0>::CancelWait(void)
0x180078c92  mov     rcx, [r14+1A0h]; pwa
0x180078c99  test    rcx, rcx
0x180078c9c  jz      short loc_180078CA9
0x180078c9e  mov     edx, 1; fCancelPendingCallbacks
0x180078ca3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180078ca9  mov     rcx, rbx; SRWLock
0x180078cac  call    cs:__imp_AcquireSRWLockExclusive
0x180078cb2  mov     [rbp+57h+var_C0], rbx
0x180078cb6  mov     byte ptr [r14+218h], 0
0x180078cbe  mov     dword ptr [r14+158h], 0
0x180078cc9  lea     rcx, [r14+150h]; ConditionVariable
0x180078cd0  call    cs:__imp_WakeAllConditionVariable
0x180078cd6  lea     rcx, [rbp+57h+var_C0]
0x180078cda  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180078cdf  nop
0x180078ce0  lea     rcx, [rbp+57h+var_D0]
0x180078ce4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180078ce9  nop
0x180078cea  lea     rcx, [rbp+57h+var_C8]
0x180078cee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180078cf3  nop
0x180078cf4  lea     rcx, [rbp+57h+var_78]
0x180078cf8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180078cfd  xor     eax, eax
0x180078cff  mov     rcx, [rbp+57h+var_48]
0x180078d03  xor     rcx, rsp; StackCookie
0x180078d06  call    __security_check_cookie
0x180078d0b  add     rsp, 0C8h
0x180078d12  pop     r15
0x180078d14  pop     r14
0x180078d16  pop     r13
0x180078d18  pop     r12
0x180078d1a  pop     rdi
0x180078d1b  pop     rsi
0x180078d1c  pop     rbx
0x180078d1d  pop     rbp
0x180078d1e  retn
0x180078d1f  mov     rcx, [rbp+5Fh]; this
0x180078d23  lea     rax, aResultGetlaste; "result || ::GetLastError() == ERROR_TIM"...
0x180078d2a  mov     [rsp+100h+var_E0], rax; char *
0x180078d2f  lea     r9, aWilConditionVa; "wil::condition_variable::wait_for"
0x180078d36  mov     edx, 0F46h; void *
0x180078d3b  call    ?FailFast_Unexpected@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::FailFast_Unexpected(void *,uint,char const *,char const *,char const *)
```
