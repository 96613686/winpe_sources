# CLockAction::_EnsureLockAppHost(ILockAppHost * *)

- ea: `0x180028280`
- end: `0x180028b83`
- name: `?_EnsureLockAppHost@CLockAction@@AEAAJPEAPEAUILockAppHost@@@Z`
- size: `2307`
- prototype: `__int64 __fastcall(CLockAction *__hidden this, struct IUnknown **)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002be30`

## callees

- `0x180017dec`
- `0x18001c56c`
- `0x18001c860`
- `0x18001d850`
- `0x18001db70`
- `0x18001f3a0`
- `0x180026f44`
- `0x180027760`
- `0x180027d00`
- `0x180028280`
- `0x18002a060`
- `0x18002a228`
- `0x18002a8e8`
- `0x18002bc20`
- `0x18002d714`
- `0x18002d790`
- `0x18005b3e4`
- `0x18005d488`
- `0x18005d4ac`
- `0x18005d4e8`
- `0x18005fbe8`
- `0x180063578`
- `0x180065b54`
- `0x18006c000`
- `0x18006c100`
- `0x18006cad0`
- `0x18006f0d8`
- `0x18008d940`
- `0x18008dd1c`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180028840`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800288d2`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180028840`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800288d2`
- `KERNEL32!DuplicateHandle` at `0x18002894c`
- `KERNEL32!DuplicateHandle` at `0x18002894c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028a76`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028af8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028b34`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028a76`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028af8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028b34`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800283a0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800283a0`
- `KERNEL32!GetCurrentProcess` at `0x18002891f`
- `KERNEL32!GetCurrentProcess` at `0x18002891f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800284ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800284ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002853d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002853d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800285ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800285ef`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002882b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800288bd`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002882b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800288bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CLockAction::_EnsureLockAppHost(CLockAction *this, struct IUnknown **a2)
{
  struct IUnknown **v2; // r15
  int LastError; // ebx
  __int64 v5; // rdx
  CLockAppHostDataConsumer *v6; // rax
  RTL_SRWLOCK *v7; // rbx
  CLockAppHostDataConsumer *v8; // rdi
  int v9; // eax
  unsigned __int64 v10; // r9
  void *v11; // r12
  PCWSTR StringRawBuffer; // rax
  int v13; // r15d
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rdi
  _WORD *v16; // rax
  unsigned __int64 v17; // rcx
  _WORD *v18; // rdx
  __int16 v19; // r8
  _WORD *v20; // rcx
  PCWSTR v21; // rax
  _WORD *v22; // r13
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rbx
  _WORD *v25; // rax
  _WORD *v26; // rdx
  unsigned __int64 v27; // rcx
  __int16 v28; // r8
  _WORD *v29; // rcx
  struct IUnknown *v30; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v32; // eax
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  unsigned int v35; // edx
  unsigned int v36; // edx
  unsigned __int64 v37; // r9
  __int64 v38; // rdx
  HANDLE CurrentProcess; // rax
  const char *v40; // r9
  int v41; // eax
  __int64 v42; // rcx
  struct IUnknown *v43; // rcx
  __int64 v44; // rcx
  struct IUnknown *v45; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  __int64 v48; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v49; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v51; // [rsp+60h] [rbp-A0h]
  _WORD *v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v53; // [rsp+78h] [rbp-88h]
  unsigned __int64 v54; // [rsp+80h] [rbp-80h]
  _WORD *v55; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v56; // [rsp+90h] [rbp-70h]
  unsigned __int64 v57; // [rsp+98h] [rbp-68h]
  _DWORD v58[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v59; // [rsp+A8h] [rbp-58h]
  __int128 v60; // [rsp+B8h] [rbp-48h]
  _BYTE Parameter[4]; // [rsp+C8h] [rbp-38h] BYREF
  char v62; // [rsp+CCh] [rbp-34h]
  int v63; // [rsp+D0h] [rbp-30h]
  HANDLE Timer; // [rsp+D8h] [rbp-28h]
  HANDLE TargetHandle; // [rsp+E8h] [rbp-18h] BYREF
  PCWSTR v66; // [rsp+F0h] [rbp-10h]
  struct IUnknown **v67; // [rsp+F8h] [rbp-8h]
  void **v68; // [rsp+100h] [rbp+0h] BYREF
  int v69; // [rsp+108h] [rbp+8h] BYREF
  char v70; // [rsp+10Ch] [rbp+Ch]
  int v71; // [rsp+130h] [rbp+30h] BYREF
  const char *v72; // [rsp+138h] [rbp+38h]
  __int64 v73; // [rsp+140h] [rbp+40h]
  char v74; // [rsp+148h] [rbp+48h]
  int v75; // [rsp+150h] [rbp+50h]
  _BYTE v76[152]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v77; // [rsp+1F0h] [rbp+F0h]
  int v78; // [rsp+200h] [rbp+100h]
  __int64 v79; // [rsp+208h] [rbp+108h]
  int *v80; // [rsp+210h] [rbp+110h]
  __int64 v81; // [rsp+218h] [rbp+118h]
  _BYTE v82[48]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v2 = a2;
  v67 = a2;
  v68 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v69 = 0;
  v70 = 0;
  v74 = 0;
  v71 = 0;
  v72 = "CLockAction__EnsureLockAppHost_Activity";
  v73 = 0;
  v75 = 0;
  v77 = 0;
  memset_0(v76, 0, sizeof(v76));
  v78 = 1;
  v79 = 0;
  v80 = &v69;
  v81 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v82,
    (struct wil::details::IFailureCallback *)&v68,
    (struct wil::CallContextInfo *)&v71,
    0);
  v68 = &LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v68,
      &Buf1);
  LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::StartActivity((LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity *)&v68);
  *v2 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  if ( *((_BYTE *)this + 336) )
  {
    LastError = -2147418113;
    v5 = 540;
LABEL_120:
    v10 = (unsigned int)LastError;
    goto LABEL_121;
  }
  if ( !*((_QWORD *)this + 44) )
  {
    v6 = (CLockAppHostDataConsumer *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
    if ( v6 )
      v7 = (RTL_SRWLOCK *)CLockAppHostDataConsumer::CLockAppHostDataConsumer(v6);
    else
      v7 = 0;
    v8 = (CLockAppHostDataConsumer *)*((_QWORD *)this + 44);
    *((_QWORD *)this + 44) = 0;
    if ( v8 )
    {
      CLockAppHostDataConsumer::~CLockAppHostDataConsumer(v8);
      operator delete(v8, (const struct std::nothrow_t *)0x58);
    }
    *((_QWORD *)this + 44) = v7;
    if ( !v7 )
    {
      LastError = -2147024882;
      v5 = 546;
      goto LABEL_120;
    }
    Buf1 = (struct _GUID)*((_OWORD *)this + 18);
    v9 = CLockAppHostDataConsumer::Initialize(
           v7,
           &Buf1,
           (struct ILockAppHostDataCallback *)(((unsigned __int64)this + 176) & -(__int64)(this != 0)),
           (struct ILockAppHostDataSharedVisualCallback *)(((unsigned __int64)this + 184) & -(__int64)(this != 0)));
    LastError = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v5 = 547;
LABEL_121:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)v10,
        dwDesiredAccess);
      goto LABEL_122;
    }
  }
  if ( *((_BYTE *)this + 304) )
    goto LABEL_105;
  v59 = 0;
  v60 = 0;
  v11 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v58[1] = *((_BYTE *)this + 257) != 0;
  v58[0] = *((_BYTE *)this + 256) != 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 30), 0);
  v66 = StringRawBuffer;
  v13 = -2147024362;
  if ( StringRawBuffer )
  {
    v14 = -1;
    do
      ++v14;
    while ( StringRawBuffer[v14] );
    v15 = v14 + 1;
    if ( v14 + 1 >= v14 && (*(_QWORD *)&Buf1.Data1 = 0, is_mul_ok(v15, 2u)) )
    {
      v16 = CoTaskMemAlloc(2 * v15);
      if ( !v16 )
      {
        LastError = -2147024882;
        goto LABEL_37;
      }
      v57 = v14 + 1;
      v11 = v16;
      v55 = v16;
      *v16 = 0;
      LastError = 0;
      if ( v14 != -1 )
      {
        if ( v14 > 0x7FFFFFFE || v15 > 0x7FFFFFFF )
        {
          *v16 = 0;
        }
        else
        {
          v17 = v14;
          v18 = v66;
          do
          {
            if ( !v17 )
              break;
            v19 = *v18;
            if ( !*v18 )
              break;
            ++v18;
            *v16++ = v19;
            --v17;
            --v15;
          }
          while ( v15 );
          v20 = v16 - 1;
          if ( v15 )
            v20 = v16;
          *v20 = 0;
        }
      }
      v56 = v14;
    }
    else
    {
      LastError = -2147024362;
    }
    if ( LastError < 0 )
    {
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)LastError,
        dwDesiredAccess);
      if ( v11 )
        CoTaskMemFree(v11);
LABEL_99:
      SafeFreeLogonUIDataContext(v58);
LABEL_122:
      if ( this != (CLockAction *)-328LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 41);
      v68 = &LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v68);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v68);
      return (unsigned int)LastError;
    }
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
    v11 = v55;
  }
  v21 = WindowsGetStringRawBuffer(*((HSTRING *)this + 29), 0);
  v22 = v21;
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    v24 = v23 + 1;
    if ( v23 + 1 >= v23 && (*(_QWORD *)&Buf1.Data1 = 0, is_mul_ok(v24, 2u)) )
    {
      v25 = CoTaskMemAlloc(2 * v24);
      v26 = v25;
      if ( !v25 )
      {
        LastError = -2147024882;
LABEL_61:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x233,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)LastError,
          dwDesiredAccess);
LABEL_115:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v55);
        SafeFreeLogonUIDataContext(v58);
        if ( this != (CLockAction *)-328LL )
          ReleaseSRWLockExclusive((PSRWLOCK)this + 41);
        LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::~CLockAction__EnsureLockAppHost_Activity((LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity *)&v68);
        return (unsigned int)LastError;
      }
      v54 = v23 + 1;
      v52 = v25;
      *v25 = 0;
      v13 = 0;
      if ( v23 != -1 )
      {
        if ( v23 > 0x7FFFFFFE || v24 > 0x7FFFFFFF )
        {
          *v25 = 0;
        }
        else
        {
          v27 = v23;
          do
          {
            if ( !v27 )
              break;
            v28 = *v22;
            if ( !*v22 )
              break;
            ++v22;
            *v25++ = v28;
            --v27;
            --v24;
          }
          while ( v24 );
          v29 = v25 - 1;
          if ( v24 )
            v29 = v25;
          *v29 = 0;
        }
      }
      v53 = v23;
    }
    else
    {
      v26 = 0;
    }
    LastError = v13;
    if ( v13 < 0 )
      goto LABEL_61;
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v52);
    v26 = v52;
  }
  v55 = 0;
  v57 = 0;
  v56 = 0;
  *((_QWORD *)&v59 + 1) = v11;
  v52 = 0;
  v54 = 0;
  v53 = 0;
  *(_QWORD *)&v59 = v26;
  LODWORD(v60) = *((_DWORD *)this + 77);
  DWORD1(v60) = *((unsigned __int8 *)this + 259);
  DWORD2(v60) = *((_BYTE *)this + 258) == 0;
  v49 = 0;
  v48 = 0;
  if ( !*((_QWORD *)this + 43) )
  {
    LastError = -2147024809;
    goto LABEL_111;
  }
  LastError = Microsoft::WRL::AgileRef::CopyTo(
                (CLockAction *)((char *)this + 344),
                &GUID_d72586df_0aac_4c94_9370_9863360cdb6b,
                &v49);
  if ( LastError < 0 )
  {
LABEL_111:
    v34 = 573;
    goto LABEL_112;
  }
  v30 = v49;
  QueryInterface = v49->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v48);
  v32 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
          v30,
          &GUID_0689ac07_5db1_488b_bc6d_9dfbc2cf7911,
          &v48);
  LastError = v32;
  if ( v32 < 0 )
  {
    v33 = (unsigned int)v32;
    v34 = 574;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
      (const char *)v33,
      dwDesiredAccess);
    goto LABEL_114;
  }
  *(_QWORD *)&Buf1.Data1 = &v49;
  *(_QWORD *)Buf1.Data4 = this;
  if ( (unsigned int)IsDebuggerPresent(*((HANDLE *)this + 56)) )
  {
    LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_55cebb6b7b1d75e682696da272805155___(&Buf1);
  }
  else
  {
    CRPCTimeout::CRPCTimeout(Parameter, v35);
    LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_55cebb6b7b1d75e682696da272805155___(&Buf1);
    if ( LastError < 0 && v62 )
      LastError = -2147417825;
    if ( v63 >= 0 )
    {
      v63 = -2147467259;
      CoDisableCallCancellation(0);
      if ( Timer )
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
  }
  if ( LastError < 0 )
  {
    LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(LastError);
    v34 = 575;
LABEL_112:
    v33 = (unsigned int)LastError;
    goto LABEL_113;
  }
  *(_QWORD *)&Buf1.Data1 = &v48;
  *(_QWORD *)Buf1.Data4 = this;
  v51 = v58;
  if ( (unsigned int)IsDebuggerPresent(*((HANDLE *)this + 56)) )
  {
    LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_d8a80680fedfaf690ab716e76812ad9d___(&Buf1);
  }
  else
  {
    CRPCTimeout::CRPCTimeout(Parameter, v36);
    LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_d8a80680fedfaf690ab716e76812ad9d___(&Buf1);
    if ( LastError < 0 && v62 )
      LastError = -2147417825;
    if ( v63 >= 0 )
    {
      v63 = -2147467259;
      CoDisableCallCancellation(0);
      if ( Timer )
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
  }
  if ( LastError < 0 )
    LogonControllerTelemetry::RPCTimeoutToLockScreenFailure(LastError);
  if ( (unsigned int)(LastError + 2144927744) <= 2 )
  {
    *((_BYTE *)this + 496) = 1;
    LogonControllerTelemetry::LockAppShownWatchdogTimerDisabled();
    CLockAction::_DisableUnlockIfLockAppDidntShowWatchdogTimer(this);
  }
  if ( LastError < 0 )
  {
    v37 = (unsigned int)LastError;
    v38 = 599;
LABEL_95:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
      (const char *)v37,
      dwDesiredAccess);
    v42 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
    }
    goto LABEL_99;
  }
  CurrentProcess = GetCurrentProcess();
  TargetHandle = 0;
  if ( !DuplicateHandle(CurrentProcess, CurrentProcess, *((HANDLE *)this + 56), &TargetHandle, 0x100000u, 0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x25B,
                  (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
                  v40);
LABEL_114:
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v49);
    goto LABEL_115;
  }
  v41 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v48 + 24LL))(v48, TargetHandle);
  LastError = v41;
  if ( v41 < 0 )
  {
    v37 = (unsigned int)v41;
    v38 = 604;
    goto LABEL_95;
  }
  *((_BYTE *)this + 304) = 1;
  v44 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
  }
  SafeFreeLogonUIDataContext(v58);
  v2 = v67;
LABEL_105:
  if ( !*((_QWORD *)this + 43) )
  {
    *v2 = 0;
    LastError = -2147024809;
    goto LABEL_119;
  }
  LastError = Microsoft::WRL::AgileRef::CopyTo(
                (CLockAction *)((char *)this + 344),
                &GUID_d72586df_0aac_4c94_9370_9863360cdb6b,
                v2);
  if ( LastError < 0 )
  {
LABEL_119:
    v5 = 609;
    goto LABEL_120;
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v68, 0);
  if ( this != (CLockAction *)-328LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 41);
  v68 = &LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v68);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v68);
  return 0;
}

```

## disassembly

```asm
0x180028280  mov     [rsp-8+arg_10], rbx
0x180028285  push    rbp
0x180028286  push    rsi
0x180028287  push    rdi
0x180028288  push    r12
0x18002828a  push    r13
0x18002828c  push    r14
0x18002828e  push    r15
0x180028290  lea     rbp, [rsp-160h]
0x180028298  sub     rsp, 260h
0x18002829f  mov     rax, cs:__security_cookie
0x1800282a6  xor     rax, rsp
0x1800282a9  mov     [rbp+190h+var_40], rax
0x1800282b0  mov     r15, rdx
0x1800282b3  mov     [rbp+190h+var_198], rdx
0x1800282b7  mov     r14, rcx
0x1800282ba  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x1800282c1  mov     [rbp+190h+var_190], rax
0x1800282c5  xor     r13d, r13d
0x1800282c8  mov     [rbp+190h+var_188], r13d
0x1800282cc  mov     [rbp+190h+var_184], r13b
0x1800282d0  mov     [rbp+190h+var_148], r13b
0x1800282d4  mov     [rbp+190h+var_160], r13d
0x1800282d8  lea     rax, aClockactionEns; "CLockAction__EnsureLockAppHost_Activity"
0x1800282df  mov     [rbp+190h+var_158], rax
0x1800282e3  mov     [rbp+190h+var_150], r13
0x1800282e7  mov     [rbp+190h+var_140], r13d
0x1800282eb  xorps   xmm0, xmm0
0x1800282ee  movdqa  [rbp+190h+var_A0], xmm0
0x1800282f6  xor     edx, edx; Val
0x1800282f8  mov     r8d, 98h; Size
0x1800282fe  lea     rcx, [rbp+190h+var_138]; void *
0x180028302  call    memset_0
0x180028307  nop
0x180028308  mov     [rbp+190h+var_90], 1
0x180028312  xor     eax, eax
0x180028314  mov     [rbp+190h+var_88], rax
0x18002831b  lea     rax, [rbp+190h+var_188]
0x18002831f  mov     [rbp+190h+var_80], rax
0x180028326  mov     [rbp+190h+var_78], r13
0x18002832d  xor     r9d, r9d; bool
0x180028330  lea     r8, [rbp+190h+var_160]; struct wil::CallContextInfo *
0x180028334  lea     rdx, [rbp+190h+var_190]; struct wil::details::IFailureCallback *
0x180028338  lea     rcx, [rbp+190h+var_70]; this
0x18002833f  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180028344  nop
0x180028345  lea     rax, ??_7CLockAction__EnsureLockAppHost_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::`vftable'
0x18002834c  mov     [rbp+190h+var_190], rax
0x180028350  lea     rcx, [rsp+290h+Buf1]; retstr
0x180028355  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18002835a  movups  xmm0, xmmword ptr [rax]
0x18002835d  movdqu  [rsp+290h+Buf1], xmm0
0x180028363  lea     r8d, [r13+10h]; Size
0x180028367  lea     rdx, GUID_NULL; Buf2
0x18002836e  lea     rcx, [rsp+290h+Buf1]; Buf1
0x180028373  call    memcmp_0
0x180028378  test    eax, eax
0x18002837a  jz      short loc_18002838A
0x18002837c  lea     rdx, [rsp+290h+Buf1]
0x180028381  lea     rcx, [rbp+190h+var_190]
0x180028385  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002838a  lea     rcx, [rbp+190h+var_190]; this
0x18002838e  call    ?StartActivity@CLockAction__EnsureLockAppHost_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction__EnsureLockAppHost_Activity::StartActivity(void)
0x180028393  mov     [r15], r13
0x180028396  lea     rsi, [r14+148h]
0x18002839d  mov     rcx, rsi; SRWLock
0x1800283a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800283a6  cmp     [r14+150h], r13b
0x1800283ad  jz      short loc_1800283BE
0x1800283af  mov     ebx, 8000FFFFh
0x1800283b4  mov     edx, 21Ch
0x1800283b9  jmp     loc_180028B16
0x1800283be  cmp     [r14+160h], r13
0x1800283c5  jnz     loc_18002848A
0x1800283cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800283d2  mov     r12d, 58h ; 'X'
0x1800283d8  mov     ecx, r12d; unsigned __int64
0x1800283db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800283e0  test    rax, rax
0x1800283e3  jz      short loc_1800283F2
0x1800283e5  mov     rcx, rax; this
0x1800283e8  call    ??0CLockAppHostDataConsumer@@QEAA@XZ; CLockAppHostDataConsumer::CLockAppHostDataConsumer(void)
0x1800283ed  mov     rbx, rax
0x1800283f0  jmp     short loc_1800283F5
0x1800283f2  mov     rbx, r13
0x1800283f5  mov     rdi, [r14+160h]
0x1800283fc  mov     [r14+160h], r13
0x180028403  test    rdi, rdi
0x180028406  jz      short loc_18002841B
0x180028408  mov     rcx, rdi; this
0x18002840b  call    ??1CLockAppHostDataConsumer@@QEAA@XZ; CLockAppHostDataConsumer::~CLockAppHostDataConsumer(void)
0x180028410  mov     rdx, r12; struct std::nothrow_t *
0x180028413  mov     rcx, rdi; void *
0x180028416  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002841b  mov     [r14+160h], rbx
0x180028422  test    rbx, rbx
0x180028425  jnz     short loc_180028436
0x180028427  mov     ebx, 8007000Eh
0x18002842c  mov     edx, 222h
0x180028431  jmp     loc_180028B16
0x180028436  movups  xmm0, xmmword ptr [r14+120h]
0x18002843e  movdqu  [rsp+290h+Buf1], xmm0
0x180028444  mov     rax, r14
0x180028447  lea     rcx, [r14+0B8h]
0x18002844e  neg     rax
0x180028451  sbb     r9, r9
0x180028454  and     r9, rcx; struct ILockAppHostDataSharedVisualCallback *
0x180028457  mov     rax, r14
0x18002845a  lea     rcx, [r14+0B0h]
0x180028461  neg     rax
0x180028464  sbb     r8, r8
0x180028467  and     r8, rcx; struct ILockAppHostDataCallback *
0x18002846a  lea     rdx, [rsp+290h+Buf1]; struct _GUID
0x18002846f  mov     rcx, rbx; Context
0x180028472  call    ?Initialize@CLockAppHostDataConsumer@@QEAAJU_GUID@@PEAUILockAppHostDataCallback@@PEAUILockAppHostDataSharedVisualCallback@@@Z; CLockAppHostDataConsumer::Initialize(_GUID,ILockAppHostDataCallback *,ILockAppHostDataSharedVisualCallback *)
0x180028477  mov     ebx, eax
0x180028479  test    eax, eax
0x18002847b  jns     short loc_18002848A
0x18002847d  mov     r9d, eax
0x180028480  mov     edx, 223h
0x180028485  jmp     loc_180028B19
0x18002848a  cmp     [r14+130h], r13b
0x180028491  jnz     loc_180028A3A
0x180028497  xorps   xmm0, xmm0
0x18002849a  movdqu  [rbp+190h+var_1E8], xmm0
0x18002849f  xorps   xmm1, xmm1
0x1800284a2  movdqu  [rbp+190h+var_1D8], xmm1
0x1800284a7  mov     r12, r13
0x1800284aa  mov     [rbp+190h+var_208], r13
0x1800284ae  mov     [rbp+190h+var_200], r13
0x1800284b2  mov     [rbp+190h+var_1F8], r13
0x1800284b6  mov     [rsp+290h+var_220], r13
0x1800284bb  mov     [rsp+290h+var_218], r13
0x1800284c0  mov     [rbp+190h+var_210], r13
0x1800284c4  mov     eax, r13d
0x1800284c7  cmp     [r14+101h], r13b
0x1800284ce  setnz   al
0x1800284d1  mov     [rbp+190h+var_1EC], eax
0x1800284d4  mov     eax, r13d
0x1800284d7  cmp     [r14+100h], r13b
0x1800284de  setnz   al
0x1800284e1  mov     [rbp+190h+var_1F0], eax
0x1800284e4  xor     edx, edx; length
0x1800284e6  mov     rcx, [r14+0F0h]; string
0x1800284ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800284f3  mov     [rbp+190h+var_1A0], rax
0x1800284f7  mov     r15d, 80070216h
0x1800284fd  test    rax, rax
0x180028500  jz      loc_1800285FA
0x180028506  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002850a  xor     r9d, r9d
0x18002850d  inc     r13
0x180028510  cmp     [rax+r13*2], r9w
0x180028515  jnz     short loc_18002850D
0x180028517  lea     rdi, [r13+1]
0x18002851b  cmp     rdi, r13
0x18002851e  jb      loc_1800285C1
0x180028524  mov     qword ptr [rsp+290h+Buf1], r9
0x180028529  mov     eax, 2
0x18002852e  mul     rdi
0x180028531  test    rdx, rdx
0x180028534  jnz     loc_1800285C1
0x18002853a  mov     rcx, rax; cb
0x18002853d  call    cs:__imp_CoTaskMemAlloc
0x180028543  xor     r9d, r9d
0x180028546  test    rax, rax
0x180028549  jz      short loc_1800285BA
0x18002854b  mov     [rbp+190h+var_1F8], rdi
0x18002854f  mov     r12, rax
0x180028552  mov     [rbp+190h+var_208], rax
0x180028556  mov     [rax], r9w
0x18002855a  mov     ebx, r9d
0x18002855d  test    rdi, rdi
0x180028560  jz      short loc_1800285B4
0x180028562  cmp     r13, 7FFFFFFEh
0x180028569  ja      short loc_1800285B0
0x18002856b  cmp     rdi, 7FFFFFFFh
0x180028572  ja      short loc_1800285B0
0x180028574  mov     rcx, r13
0x180028577  mov     rdx, [rbp+190h+var_1A0]
0x18002857b  test    rcx, rcx
0x18002857e  jz      short loc_18002859F
0x180028580  movzx   r8d, word ptr [rdx]
0x180028584  test    r8w, r8w
0x180028588  jz      short loc_18002859F
0x18002858a  add     rdx, 2
0x18002858e  mov     [rax], r8w
0x180028592  add     rax, 2
0x180028596  dec     rcx
0x180028599  sub     rdi, 1
0x18002859d  jnz     short loc_18002857B
0x18002859f  lea     rcx, [rax-2]
0x1800285a3  test    rdi, rdi
0x1800285a6  cmovnz  rcx, rax
0x1800285aa  mov     [rcx], r9w
0x1800285ae  jmp     short loc_1800285B4
0x1800285b0  mov     [rax], r9w
0x1800285b4  mov     [rbp+190h+var_200], r13
0x1800285b8  jmp     short loc_1800285C4
0x1800285ba  mov     ebx, 8007000Eh
0x1800285bf  jmp     short loc_1800285C8
0x1800285c1  mov     ebx, r15d
0x1800285c4  test    ebx, ebx
0x1800285c6  jns     short loc_180028607
0x1800285c8  mov     rcx, [rbp+198h]; this
0x1800285cf  mov     r9d, ebx; char *
0x1800285d2  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800285d9  mov     edx, 232h; void *
0x1800285de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285e3  test    r12, r12
0x1800285e6  jz      loc_1800289E1
0x1800285ec  mov     rcx, r12; pv
0x1800285ef  call    cs:__imp_CoTaskMemFree
0x1800285f5  jmp     loc_1800289E1
0x1800285fa  lea     rcx, [rbp+190h+var_208]
0x1800285fe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028603  mov     r12, [rbp+190h+var_208]
0x180028607  xor     edx, edx; length
0x180028609  mov     rcx, [r14+0E8h]; string
0x180028610  call    cs:__imp_WindowsGetStringRawBuffer
0x180028616  mov     r13, rax
0x180028619  xor     ecx, ecx
0x18002861b  test    rax, rax
0x18002861e  jz      loc_180028708
0x180028624  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028628  inc     rdi
0x18002862b  cmp     [rax+rdi*2], cx
0x18002862f  jnz     short loc_180028628
0x180028631  lea     rbx, [rdi+1]
0x180028635  cmp     rbx, rdi
0x180028638  jb      loc_1800286DA
0x18002863e  mov     qword ptr [rsp+290h+Buf1], rcx
0x180028643  mov     eax, 2
0x180028648  mul     rbx
0x18002864b  test    rdx, rdx
0x18002864e  jnz     loc_1800286DA
0x180028654  mov     rcx, rax; cb
0x180028657  call    cs:__imp_CoTaskMemAlloc
0x18002865d  mov     rdx, rax
0x180028660  xor     r9d, r9d
0x180028663  test    rax, rax
0x180028666  jz      short loc_1800286D3
0x180028668  mov     [rbp+190h+var_210], rbx
0x18002866c  mov     [rsp+290h+var_220], rax
0x180028671  mov     [rax], r9w
0x180028675  mov     r15d, r9d
0x180028678  test    rbx, rbx
0x18002867b  jz      short loc_1800286CC
0x18002867d  cmp     rdi, 7FFFFFFEh
0x180028684  ja      short loc_1800286C8
0x180028686  cmp     rbx, 7FFFFFFFh
0x18002868d  ja      short loc_1800286C8
0x18002868f  mov     rcx, rdi
0x180028692  test    rcx, rcx
0x180028695  jz      short loc_1800286B7
0x180028697  movzx   r8d, word ptr [r13+0]
0x18002869c  test    r8w, r8w
0x1800286a0  jz      short loc_1800286B7
0x1800286a2  add     r13, 2
0x1800286a6  mov     [rax], r8w
0x1800286aa  add     rax, 2
0x1800286ae  dec     rcx
0x1800286b1  sub     rbx, 1
0x1800286b5  jnz     short loc_180028692
0x1800286b7  lea     rcx, [rax-2]
0x1800286bb  test    rbx, rbx
0x1800286be  cmovnz  rcx, rax
0x1800286c2  mov     [rcx], r9w
0x1800286c6  jmp     short loc_1800286CC
0x1800286c8  mov     [rax], r9w
0x1800286cc  mov     [rsp+290h+var_218], rdi
0x1800286d1  jmp     short loc_1800286DD
0x1800286d3  mov     ebx, 8007000Eh
0x1800286d8  jmp     short loc_1800286E8
0x1800286da  mov     rdx, rcx
0x1800286dd  mov     ebx, r15d
0x1800286e0  xor     r13d, r13d
0x1800286e3  test    r15d, r15d
0x1800286e6  jns     short loc_18002871A
0x1800286e8  mov     rcx, [rbp+198h]; this
0x1800286ef  mov     r9d, ebx; char *
0x1800286f2  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800286f9  mov     edx, 233h; void *
0x1800286fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028703  jmp     loc_180028AD4
0x180028708  lea     rcx, [rsp+290h+var_220]
0x18002870d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028712  mov     rdx, [rsp+290h+var_220]
0x180028717  xor     r13d, r13d
0x18002871a  mov     [rbp+190h+var_208], r13
0x18002871e  mov     [rbp+190h+var_1F8], r13
0x180028722  mov     [rbp+190h+var_200], r13
0x180028726  mov     qword ptr [rbp+190h+var_1E8+8], r12
0x18002872a  mov     [rsp+290h+var_220], r13
0x18002872f  mov     [rbp+190h+var_210], r13
0x180028733  mov     [rsp+290h+var_218], r13
0x180028738  mov     qword ptr [rbp+190h+var_1E8], rdx
0x18002873c  mov     eax, [r14+134h]
0x180028743  mov     dword ptr [rbp+190h+var_1D8], eax
0x180028746  movzx   eax, byte ptr [r14+103h]
  ... truncated ...
```
