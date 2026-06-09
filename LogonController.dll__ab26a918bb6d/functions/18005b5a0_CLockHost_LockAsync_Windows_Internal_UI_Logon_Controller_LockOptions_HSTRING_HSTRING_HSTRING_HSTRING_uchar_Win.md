# CLockHost::LockAsync(Windows::Internal::UI::Logon::Controller::LockOptions,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar *,Windows::Internal::UI::Logon::Controller::IUnlockTrigger * *)

- ea: `0x18005b5a0`
- end: `0x18005bc84`
- name: `?LockAsync@CLockHost@@UEAAJW4LockOptions@Controller@Logon@UI@Internal@Windows@@PEAUHSTRING__@@111PEAEPEAPEAUIUnlockTrigger@34567@@Z`
- size: `1764`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x180017dec`
- `0x18001db70`
- `0x18001f3a0`
- `0x180025ac0`
- `0x180028f70`
- `0x18002bc20`
- `0x18002f554`
- `0x1800315a0`
- `0x180033480`
- `0x18003fa40`
- `0x180048f84`
- `0x180049bf4`
- `0x18004c628`
- `0x180053438`
- `0x1800534a4`
- `0x180053554`
- `0x18005b3e4`
- `0x18005b47c`
- `0x18005b5a0`
- `0x18005d488`
- `0x1800629ec`
- `0x180064588`
- `0x18006c000`
- `0x18006c100`
- `0x18006f0d8`
- `0x180087a7c`
- `0x180088124`
- `0x180089fa0`
- `0x18008ab5c`
- `0x18008ac14`
- `0x18008ad04`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005b80b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b78a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b86a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b88a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b78a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b86a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b88a`
- `SLC!SLGetWindowsInformationDWORD` at `0x18005b6ea`
- `SLC!SLGetWindowsInformationDWORD` at `0x18005b6ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLockHost::LockAsync(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        HSTRING string,
        char *a7,
        _QWORD *a8)
{
  char v8; // r15
  unsigned int v10; // r9d
  CLockHost *v11; // rcx
  char v12; // r12
  DWORD v13; // ebx
  __int64 v14; // rdx
  bool v15; // r14
  int v16; // r13d
  int v17; // esi
  const WCHAR *StringRawBuffer; // rax
  unsigned int v19; // eax
  HKEY v20; // rbx
  const unsigned __int16 *v21; // rax
  int LockAppAndAppType; // eax
  bool *v23; // rax
  bool *v24; // rdi
  int SecureGestureString; // eax
  __int64 v26; // rdx
  int v27; // r15d
  __int64 v28; // rbx
  unsigned int v29; // r13d
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD); // rbx
  __int64 v32; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  _BYTE v36[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  bool v38[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwValue[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, _QWORD); // [rsp+68h] [rbp-98h] BYREF
  unsigned __int128 Buf1; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v49; // [rsp+A8h] [rbp-58h]
  char *v50; // [rsp+B0h] [rbp-50h]
  _QWORD v51[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v8 = a2;
  v37 = a2;
  v45 = a1;
  v48 = a3;
  v47 = a4;
  v46 = a5;
  v41 = string;
  v50 = a7;
  v49 = a8;
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v51,
    "CLockHost_LockAsync_Activity");
  v51[0] = &LogonControllerTelemetry::CLockHost_LockAsync_Activity::`vftable';
  Buf1 = (unsigned __int128)*GetFirstRunTelemetryCorrelationId((struct _GUID *)&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v51,
      &Buf1);
  LogonControllerTelemetry::CLockHost_LockAsync_Activity::StartActivity((LogonControllerTelemetry::CLockHost_LockAsync_Activity *)v51);
  *a8 = 0;
  v11 = *(CLockHost **)(a1 + 144);
  *(_QWORD *)(a1 + 144) = 0;
  if ( v11 )
    (*(void (__fastcall **)(CLockHost *))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = 1;
  v15 = 1;
  if ( (v8 & 1) == 0 )
  {
    if ( (v8 & 4) == 0
      || (pdwValue[0] = 0,
          (int)SHRegGetBOOLWithREGSAM(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Policies\\Microsoft\\Windows\\System",
                 L"DisableLockScreenAppNotifications",
                 v10,
                 (int *)pdwValue) < 0)
      || !pdwValue[0]
      || (pdwValue[0] = 0,
          SLGetWindowsInformationDWORD(L"ContentDeliveryManager-License-ContentDeliveryAllowed", pdwValue),
          v13 = pdwValue[0],
          LOBYTE(v14) = 1,
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions>::GetImpl'::`2'::impl,
            v14),
          v13 - 3 <= 2) )
    {
      v15 = 0;
    }
  }
  v16 = 0;
  pdwValue[0] = 0;
  if ( v15 )
  {
    v36[0] = (v8 & 0x40) != 0;
    LogonControllerTelemetry::BeginSecureLock<bool>(v36);
  }
  else
  {
    if ( !CLockHost::CanUseUwpLockApp(v11) )
    {
      v17 = -2144927743;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)0x80270001LL,
        phkResult);
      goto LABEL_59;
    }
    Buf1 = 0u;
    v44 = 0;
    if ( string )
    {
      hKey = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v19 = RegOpenKeyExW(HKEY_USERS, StringRawBuffer, 0, 1u, &hKey);
      if ( v19 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0xF6,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
          (const char *)v19,
          phkResulta);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&Buf1);
      *((_QWORD *)&Buf1 + 1) = -1;
      v44 = -1;
      v20 = hKey;
      v21 = WindowsGetStringRawBuffer(string, 0);
      LockAppAndAppType = GetLockAppAndAppType(
                            v21,
                            (v8 & 0x20) != 0,
                            v20,
                            0,
                            (enum LockAppType *)pdwValue,
                            (unsigned __int16 **)&Buf1);
      v17 = LockAppAndAppType;
      if ( LockAppAndAppType < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF9,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
          (const char *)(unsigned int)LockAppAndAppType,
          phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&Buf1);
        goto LABEL_59;
      }
      if ( hKey )
        RegCloseKey(hKey);
      v16 = pdwValue[0];
    }
    v36[0] = v8 < 0;
    LogonControllerTelemetry::BeginUserDesktopLock<enum LockAppType &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &,bool>(
      pdwValue,
      &Buf1,
      v36);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&Buf1);
  }
  v23 = (bool *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v24 = v23;
  if ( !v23 )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_56:
    if ( v15 )
      goto LABEL_59;
    v37 = 0;
    pdwValue[0] = 0;
LABEL_58:
    LogonControllerTelemetry::LockAppDidntShow<int,unsigned int>(pdwValue, &v37);
    goto LABEL_59;
  }
  *(_WORD *)(v23 + 5) = 0;
  v23[7] = 0;
  *((_QWORD *)v23 + 4) = 1;
  *(_DWORD *)v23 = 0;
  v23[4] = 0;
  *((_QWORD *)v23 + 1) = 0;
  *((_QWORD *)v23 + 2) = 0;
  *((_QWORD *)v23 + 3) = 0;
  _InterlockedAdd((volatile signed __int32 *)v23 + 8, 1u);
  *v23 = (v8 & 4) != 0;
  v23[1] = (v8 & 2) != 0;
  v23[2] = (v8 & 8) != 0;
  v23[3] = (v8 & 0x10) != 0;
  v23[4] = (v8 & 0x20) != 0;
  if ( (v8 & 4) != 0 )
  {
    WindowsDeleteString(*((HSTRING *)v23 + 1));
    *((_QWORD *)v24 + 1) = 0;
    SecureGestureString = CLockHost::_s_GetSecureGestureString((HSTRING *)v24 + 1);
    v17 = SecureGestureString;
    if ( SecureGestureString < 0 )
    {
      v26 = 319;
      goto LABEL_31;
    }
  }
  if ( v24[1] )
  {
    WindowsDeleteString(*((HSTRING *)v24 + 2));
    *((_QWORD *)v24 + 2) = 0;
    SecureGestureString = CLockHost::_s_GetSpeedBumpString((HSTRING *)v24 + 2);
    v17 = SecureGestureString;
    if ( SecureGestureString < 0 )
    {
      v26 = 324;
      goto LABEL_31;
    }
  }
  SecureGestureString = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v24 + 3, &v41);
  v17 = SecureGestureString;
  if ( SecureGestureString < 0 )
  {
    v26 = 327;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
      (const char *)(unsigned int)SecureGestureString,
      phkResult);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 8, 0xFFFFFFFF) == 1 )
    {
      LockActionArgs::~LockActionArgs((LockActionArgs *)v24);
      operator delete(v24, (const struct std::nothrow_t *)0x28);
    }
    goto LABEL_56;
  }
  v27 = 0;
  v42 = 0;
  if ( v15 )
  {
    *(_QWORD *)&Buf1 = v24;
    v17 = Microsoft::WRL::Details::MakeAndInitialize<CSecureLockAction,Windows::Internal::UI::Logon::Controller::IUnlockTrigger,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,LockActionArgs *>(
            (_DWORD)v49,
            (unsigned int)&v48,
            (unsigned int)&v47,
            (unsigned int)&v46,
            (__int64)&Buf1);
    v29 = v17;
    pdwValue[0] = v17;
    v38[0] = !v15;
    v36[0] = 1;
    LogonControllerTelemetry::LockOnDesktop<long &,bool,unsigned int,bool>(pdwValue, v36, &v37, v38);
    goto LABEL_46;
  }
  v41 = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v41);
  v28 = v45;
  v17 = CLockHost::_EnsureLockAppHost(v45, v16, (struct IUnknown **)&v41);
  v29 = v17;
  pdwValue[0] = v17;
  if ( v17 >= 0 )
  {
    *(_QWORD *)pdwValue = v41;
    *(_QWORD *)&Buf1 = v24;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v42);
    v30 = Microsoft::WRL::Details::MakeAndInitialize<CLockAction,CLockAction,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &,LockActionArgs *,ILockAppHost *,CAutoHandle<void *> &>(
            (unsigned int)&v42,
            (unsigned int)&v48,
            (unsigned int)&v47,
            (unsigned int)&v46,
            (__int64)&Buf1,
            (__int64)pdwValue,
            v28 + 104);
    v27 = v30;
    v29 = v30;
    pdwValue[0] = v30;
    if ( v30 < 0 )
    {
LABEL_43:
      v17 = v30;
      goto LABEL_44;
    }
    v31 = v42;
    v17 = (**v42)(v42, &GUID_bd4fd664_fd5e_4ea2_8a71_48a75a4529c0, v49);
    v29 = v17;
    pdwValue[0] = v17;
    if ( v17 >= 0 )
    {
      *(_QWORD *)&Buf1 = v45 + 144;
      v32 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&Buf1);
      v30 = Microsoft::WRL::AsWeak<Windows::Internal::UI::Logon::Controller::IUnlockTrigger>(v31, v32);
      v29 = v30;
      pdwValue[0] = v30;
      goto LABEL_43;
    }
  }
LABEL_44:
  v36[0] = 0;
  v38[0] = 0;
  LogonControllerTelemetry::LockOnDesktop<long &,bool,unsigned int,bool>(pdwValue, v38, &v37, v36);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v41);
LABEL_46:
  if ( v15 || v17 < 0 )
    v12 = 0;
  *v50 = v12;
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51, v29);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v42);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 8, 0xFFFFFFFF) == 1 )
  {
    LockActionArgs::~LockActionArgs((LockActionArgs *)v24);
    operator delete(v24, (const struct std::nothrow_t *)0x28);
  }
  if ( v17 < 0 && !v15 && (unsigned int)(v27 + 2144927744) > 2 )
  {
    v37 = 0;
    pdwValue[0] = 0;
    goto LABEL_58;
  }
LABEL_59:
  LogonControllerTelemetry::CLockHost_LockAsync_Activity::~CLockHost_LockAsync_Activity((LogonControllerTelemetry::CLockHost_LockAsync_Activity *)v51);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18005b5a0  push    rbp
0x18005b5a2  push    rbx
0x18005b5a3  push    rsi
0x18005b5a4  push    rdi
0x18005b5a5  push    r12
0x18005b5a7  push    r13
0x18005b5a9  push    r14
0x18005b5ab  push    r15
0x18005b5ad  lea     rbp, [rsp-128h]
0x18005b5b5  sub     rsp, 228h
0x18005b5bc  mov     rax, cs:__security_cookie
0x18005b5c3  xor     rax, rsp
0x18005b5c6  mov     [rbp+160h+var_50], rax
0x18005b5cd  mov     r15d, edx
0x18005b5d0  mov     [rsp+260h+var_21C], edx
0x18005b5d4  mov     rbx, rcx
0x18005b5d7  mov     [rbp+160h+var_1D8], rcx
0x18005b5db  mov     [rbp+160h+var_1C0], r8
0x18005b5df  mov     [rbp+160h+var_1C8], r9
0x18005b5e3  mov     rax, [rbp+160h+arg_20]
0x18005b5ea  mov     [rbp+160h+var_1D0], rax
0x18005b5ee  mov     rdi, [rbp+160h+string]
0x18005b5f5  mov     [rsp+260h+var_200], rdi
0x18005b5fa  mov     rax, [rbp+160h+arg_30]
0x18005b601  mov     [rbp+160h+var_1B0], rax
0x18005b605  mov     rsi, [rbp+160h+arg_38]
0x18005b60c  mov     [rbp+160h+var_1B8], rsi
0x18005b610  lea     rdx, aClockhostLocka; "CLockHost_LockAsync_Activity"
0x18005b617  lea     rcx, [rbp+160h+var_1A0]
0x18005b61b  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005b620  lea     rax, ??_7CLockHost_LockAsync_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost_LockAsync_Activity::`vftable'
0x18005b627  mov     [rbp+160h+var_1A0], rax
0x18005b62b  lea     rcx, [rsp+260h+Buf1]; retstr
0x18005b630  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18005b635  movups  xmm0, xmmword ptr [rax]
0x18005b638  movdqu  [rsp+260h+Buf1], xmm0
0x18005b63e  mov     r8d, 10h; Size
0x18005b644  lea     rdx, GUID_NULL; Buf2
0x18005b64b  lea     rcx, [rsp+260h+Buf1]; Buf1
0x18005b650  call    memcmp_0
0x18005b655  test    eax, eax
0x18005b657  jz      short loc_18005B667
0x18005b659  lea     rdx, [rsp+260h+Buf1]
0x18005b65e  lea     rcx, [rbp+160h+var_1A0]
0x18005b662  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18005b667  lea     rcx, [rbp+160h+var_1A0]; this
0x18005b66b  call    ?StartActivity@CLockHost_LockAsync_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockHost_LockAsync_Activity::StartActivity(void)
0x18005b670  mov     qword ptr [rsi], 0
0x18005b677  lea     rax, [rbx+90h]
0x18005b67e  mov     rcx, [rax]
0x18005b681  xor     ebx, ebx
0x18005b683  mov     [rax], rbx
0x18005b686  test    rcx, rcx
0x18005b689  jz      short loc_18005B697
0x18005b68b  mov     rax, [rcx]
0x18005b68e  mov     rax, [rax+10h]
0x18005b692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b697  mov     r12d, 1
0x18005b69d  test    r12b, r15b
0x18005b6a0  jnz     short loc_18005B712
0x18005b6a2  test    r15b, 4
0x18005b6a6  jz      short loc_18005B70D
0x18005b6a8  mov     [rsp+260h+pdwValue], ebx
0x18005b6ac  lea     rax, [rsp+260h+pdwValue]
0x18005b6b1  mov     [rsp+260h+phkResult], rax; int *
0x18005b6b6  lea     r8, aDisablelockscr; "DisableLockScreenAppNotifications"
0x18005b6bd  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18005b6c4  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18005b6cb  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18005b6d0  test    eax, eax
0x18005b6d2  js      short loc_18005B70D
0x18005b6d4  cmp     [rsp+260h+pdwValue], ebx
0x18005b6d8  jz      short loc_18005B70D
0x18005b6da  mov     [rsp+260h+pdwValue], ebx
0x18005b6de  lea     rdx, [rsp+260h+pdwValue]; pdwValue
0x18005b6e3  lea     rcx, aContentdeliver; "ContentDeliveryManager-License-ContentD"...
0x18005b6ea  call    cs:__imp_SLGetWindowsInformationDWORD
0x18005b6f0  mov     ebx, [rsp+260h+pdwValue]
0x18005b6f4  mov     dl, r12b
0x18005b6f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions> `wil::Feature<__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions>::GetImpl(void)'::`2'::impl
0x18005b6fe  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ContentDeliveryPolicyRestrictions>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005b703  lea     eax, [rbx-3]
0x18005b706  xor     ebx, ebx
0x18005b708  cmp     eax, 2
0x18005b70b  ja      short loc_18005B712
0x18005b70d  mov     r14b, bl
0x18005b710  jmp     short loc_18005B715
0x18005b712  mov     r14b, r12b
0x18005b715  mov     r13d, ebx
0x18005b718  mov     [rsp+260h+pdwValue], ebx
0x18005b71c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005b720  test    r14b, r14b
0x18005b723  jnz     loc_18005B8C3
0x18005b729  call    ?CanUseUwpLockApp@CLockHost@@AEAA_NXZ; CLockHost::CanUseUwpLockApp(void)
0x18005b72e  test    al, al
0x18005b730  jnz     short loc_18005B757
0x18005b732  mov     rcx, [rbp+168h]; this
0x18005b739  mov     esi, 80270001h
0x18005b73e  mov     r9d, esi; char *
0x18005b741  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005b748  mov     edx, 0EDh; void *
0x18005b74d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b752  jmp     loc_18005BC56
0x18005b757  mov     qword ptr [rsp+260h+Buf1], rbx
0x18005b75c  mov     qword ptr [rsp+260h+Buf1+8], rbx
0x18005b761  mov     [rbp+160h+var_1E0], rbx
0x18005b765  test    rdi, rdi
0x18005b768  jz      loc_18005B896
0x18005b76e  mov     [rsp+260h+hKey], rbx
0x18005b773  mov     rbx, [rsp+260h+hKey]
0x18005b778  test    rbx, rbx
0x18005b77b  jz      short loc_18005B79B
0x18005b77d  lea     rcx, [rsp+260h+var_1F8]; this
0x18005b782  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005b787  mov     rcx, rbx; hKey
0x18005b78a  call    cs:__imp_RegCloseKey
0x18005b790  lea     rcx, [rsp+260h+var_1F8]; this
0x18005b795  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005b79a  nop
0x18005b79b  mov     [rsp+260h+hKey], 0
0x18005b7a4  xor     edx, edx; length
0x18005b7a6  mov     rcx, rdi; string
0x18005b7a9  call    cs:__imp_WindowsGetStringRawBuffer
0x18005b7af  lea     rcx, [rsp+260h+hKey]
0x18005b7b4  mov     [rsp+260h+phkResult], rcx; unsigned int
0x18005b7b9  mov     r9d, r12d; samDesired
0x18005b7bc  xor     r8d, r8d; ulOptions
0x18005b7bf  mov     rdx, rax; lpSubKey
0x18005b7c2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18005b7c9  call    cs:__imp_RegOpenKeyExW
0x18005b7cf  mov     rcx, [rbp+168h]; this
0x18005b7d6  test    eax, eax
0x18005b7d8  jz      short loc_18005B7EE
0x18005b7da  mov     r9d, eax; char *
0x18005b7dd  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005b7e4  mov     edx, 0F6h; void *
0x18005b7e9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b7ee  lea     rcx, [rsp+260h+Buf1]
0x18005b7f3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005b7f8  mov     qword ptr [rsp+260h+Buf1+8], rsi
0x18005b7fd  mov     [rbp+160h+var_1E0], rsi
0x18005b801  mov     rbx, [rsp+260h+hKey]
0x18005b806  xor     edx, edx; length
0x18005b808  mov     rcx, rdi; string
0x18005b80b  call    cs:__imp_WindowsGetStringRawBuffer
0x18005b811  mov     edx, r15d
0x18005b814  shr     edx, 5
0x18005b817  and     dl, r12b; bool
0x18005b81a  lea     rcx, [rsp+260h+Buf1]
0x18005b81f  mov     [rsp+260h+var_238], rcx; unsigned __int16 **
0x18005b824  lea     rcx, [rsp+260h+pdwValue]
0x18005b829  mov     [rsp+260h+phkResult], rcx; int
0x18005b82e  xor     r9d, r9d; bool
0x18005b831  mov     r8, rbx; HKEY
0x18005b834  mov     rcx, rax; unsigned __int16 *
0x18005b837  call    ?GetLockAppAndAppType@@YAJPEBG_NPEAUHKEY__@@1PEAW4LockAppType@@PEAPEAG@Z; GetLockAppAndAppType(ushort const *,bool,HKEY__ *,bool,LockAppType *,ushort * *)
0x18005b83c  mov     esi, eax
0x18005b83e  xor     ebx, ebx
0x18005b840  test    eax, eax
0x18005b842  jns     short loc_18005B880
0x18005b844  mov     rcx, [rbp+168h]; this
0x18005b84b  mov     r9d, eax; char *
0x18005b84e  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005b855  mov     edx, 0F9h; void *
0x18005b85a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b85f  nop
0x18005b860  mov     rcx, [rsp+260h+hKey]; hKey
0x18005b865  test    rcx, rcx
0x18005b868  jz      short loc_18005B871
0x18005b86a  call    cs:__imp_RegCloseKey
0x18005b870  nop
0x18005b871  lea     rcx, [rsp+260h+Buf1]
0x18005b876  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005b87b  jmp     loc_18005BC56
0x18005b880  mov     rcx, [rsp+260h+hKey]; hKey
0x18005b885  test    rcx, rcx
0x18005b888  jz      short loc_18005B891
0x18005b88a  call    cs:__imp_RegCloseKey
0x18005b890  nop
0x18005b891  mov     r13d, [rsp+260h+pdwValue]
0x18005b896  mov     eax, r15d
0x18005b899  shr     eax, 7
0x18005b89c  and     al, r12b
0x18005b89f  mov     [rsp+260h+var_220], al
0x18005b8a3  lea     r8, [rsp+260h+var_220]
0x18005b8a8  lea     rdx, [rsp+260h+Buf1]
0x18005b8ad  lea     rcx, [rsp+260h+pdwValue]
0x18005b8b2  call    ??$BeginUserDesktopLock@AEAW4LockAppType@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@_N@LogonControllerTelemetry@@SAXAEAW4LockAppType@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$QEA_N@Z; LogonControllerTelemetry::BeginUserDesktopLock<LockAppType &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,bool>(LockAppType &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,bool &&)
0x18005b8b7  lea     rcx, [rsp+260h+Buf1]
0x18005b8bc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005b8c1  jmp     short loc_18005B8DA
0x18005b8c3  mov     eax, r15d
0x18005b8c6  shr     eax, 6
0x18005b8c9  and     al, r12b
0x18005b8cc  mov     [rsp+260h+var_220], al
0x18005b8d0  lea     rcx, [rsp+260h+var_220]
0x18005b8d5  call    ??$BeginSecureLock@_N@LogonControllerTelemetry@@SAX$$QEA_N@Z; LogonControllerTelemetry::BeginSecureLock<bool>(bool &&)
0x18005b8da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b8e1  mov     ecx, 28h ; '('; unsigned __int64
0x18005b8e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b8eb  mov     rdi, rax
0x18005b8ee  test    rax, rax
0x18005b8f1  jz      loc_18005BC1A
0x18005b8f7  mov     [rax+5], bx
0x18005b8fb  mov     [rax+7], bl
0x18005b8fe  mov     qword ptr [rax+20h], 1
0x18005b906  mov     dword ptr [rax], 0
0x18005b90c  mov     [rax+4], bl
0x18005b90f  mov     [rax+8], rbx
0x18005b913  mov     [rax+10h], rbx
0x18005b917  mov     [rax+18h], rbx
0x18005b91b  lock add [rax+20h], r12d
0x18005b920  bt      r15d, 2
0x18005b925  setb    al
0x18005b928  mov     [rdi], al
0x18005b92a  mov     eax, r15d
0x18005b92d  shr     eax, 1
0x18005b92f  and     al, r12b
0x18005b932  mov     [rdi+1], al
0x18005b935  mov     eax, r15d
0x18005b938  shr     eax, 3
0x18005b93b  and     al, r12b
0x18005b93e  mov     [rdi+2], al
0x18005b941  mov     eax, r15d
0x18005b944  shr     eax, 4
0x18005b947  and     al, r12b
0x18005b94a  mov     [rdi+3], al
0x18005b94d  mov     eax, r15d
0x18005b950  shr     eax, 5
0x18005b953  and     al, r12b
0x18005b956  mov     [rdi+4], al
0x18005b959  bt      r15d, 2
0x18005b95e  jnb     short loc_18005B9CA
0x18005b960  lea     rbx, [rdi+8]
0x18005b964  mov     rcx, [rbx]; string
0x18005b967  call    cs:__imp_WindowsDeleteString
0x18005b96d  mov     qword ptr [rbx], 0
0x18005b974  mov     rcx, rbx; HSTRING *
0x18005b977  call    ?_s_GetSecureGestureString@CLockHost@@CAJPEAPEAUHSTRING__@@@Z; CLockHost::_s_GetSecureGestureString(HSTRING__ * *)
0x18005b97c  mov     esi, eax
0x18005b97e  xor     ebx, ebx
0x18005b980  test    eax, eax
0x18005b982  jns     short loc_18005B9CA
0x18005b984  mov     edx, 13Fh; void *
0x18005b989  mov     rcx, [rbp+168h]; this
0x18005b990  mov     r9d, eax; char *
0x18005b993  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005b99a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b99f  or      eax, 0FFFFFFFFh
0x18005b9a2  lock xadd [rdi+20h], eax
0x18005b9a7  cmp     eax, 1
0x18005b9aa  jnz     loc_18005BC3A
0x18005b9b0  mov     rcx, rdi; this
0x18005b9b3  call    ??1LockActionArgs@@QEAA@XZ; LockActionArgs::~LockActionArgs(void)
0x18005b9b8  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18005b9bd  mov     rcx, rdi; void *
0x18005b9c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b9c5  jmp     loc_18005BC3A
0x18005b9ca  cmp     [rdi+1], bl
0x18005b9cd  jz      short loc_18005B9FA
0x18005b9cf  lea     rbx, [rdi+10h]
0x18005b9d3  mov     rcx, [rbx]; string
0x18005b9d6  call    cs:__imp_WindowsDeleteString
0x18005b9dc  mov     qword ptr [rbx], 0
0x18005b9e3  mov     rcx, rbx; HSTRING *
0x18005b9e6  call    ?_s_GetSpeedBumpString@CLockHost@@CAJPEAPEAUHSTRING__@@@Z; CLockHost::_s_GetSpeedBumpString(HSTRING__ * *)
0x18005b9eb  mov     esi, eax
0x18005b9ed  xor     ebx, ebx
0x18005b9ef  test    eax, eax
0x18005b9f1  jns     short loc_18005B9FA
0x18005b9f3  mov     edx, 144h
0x18005b9f8  jmp     short loc_18005B989
0x18005b9fa  lea     rcx, [rdi+18h]; newString
0x18005b9fe  lea     rdx, [rsp+260h+var_200]; HSTRING *
0x18005ba03  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18005ba08  mov     esi, eax
0x18005ba0a  test    eax, eax
0x18005ba0c  jns     short loc_18005BA18
0x18005ba0e  mov     edx, 147h
0x18005ba13  jmp     loc_18005B989
0x18005ba18  mov     r15d, ebx
0x18005ba1b  mov     [rsp+260h+var_1F8], rbx
0x18005ba20  test    r14b, r14b
0x18005ba23  jnz     loc_18005BB46
0x18005ba29  mov     [rsp+260h+var_200], rbx
0x18005ba2e  lea     rcx, [rsp+260h+var_200]
0x18005ba33  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ba38  lea     r8, [rsp+260h+var_200]
0x18005ba3d  mov     edx, r13d
0x18005ba40  mov     rbx, [rbp+160h+var_1D8]
0x18005ba44  mov     rcx, rbx
0x18005ba47  call    ?_EnsureLockAppHost@CLockHost@@AEAAJW4LockAppType@@PEAPEAUILockAppHost@@@Z; CLockHost::_EnsureLockAppHost(LockAppType,ILockAppHost * *)
0x18005ba4c  mov     esi, eax
0x18005ba4e  mov     r13d, eax
0x18005ba51  mov     [rsp+260h+pdwValue], eax
0x18005ba55  test    eax, eax
0x18005ba57  js      loc_18005BB0F
0x18005ba5d  mov     rax, [rsp+260h+var_200]
0x18005ba62  mov     qword ptr [rsp+260h+pdwValue], rax
0x18005ba67  mov     qword ptr [rsp+260h+Buf1], rdi
  ... truncated ...
```
