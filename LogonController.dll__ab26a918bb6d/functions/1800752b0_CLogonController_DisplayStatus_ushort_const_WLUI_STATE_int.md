# CLogonController::DisplayStatus(ushort const *,_WLUI_STATE,int *)

- ea: `0x1800752b0`
- end: `0x180075909`
- name: `?DisplayStatus@CLogonController@@UEAAJPEBGW4_WLUI_STATE@@PEAH@Z`
- size: `1625`
- prototype: `int __high(const unsigned __int16 *, enum _WLUI_STATE, int *)`
- caller_count: `0`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000df10`
- `0x180015920`
- `0x18001a4cc`
- `0x18001a83c`
- `0x18001c6a4`
- `0x18001db70`
- `0x18001f3a0`
- `0x180023f60`
- `0x180026e70`
- `0x18002bc20`
- `0x18002e820`
- `0x18002ecb8`
- `0x18002f554`
- `0x18002f6ac`
- `0x1800328e0`
- `0x18003b910`
- `0x180041dec`
- `0x180041ed4`
- `0x180043d0c`
- `0x180045f60`
- `0x180047914`
- `0x180047a7c`
- `0x180049918`
- `0x18004bfb4`
- `0x18004d9ac`
- `0x18004dc4c`
- `0x18004e228`
- `0x18005074c`
- `0x18005b3e4`
- `0x18005c528`
- `0x18005d488`
- `0x180062fd4`
- `0x18006393c`
- `0x18006c000`
- `0x1800752b0`
- `0x180075aec`
- `0x180077e08`
- `0x18007c2e4`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18007543a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007543a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800753f5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800753f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800754a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800754e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007551a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800754a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800754e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007551a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CLogonController::DisplayStatus(__int64 a1, _WORD *a2, unsigned int a3, int *a4)
{
  __int64 v7; // rcx
  __int64 v8; // r15
  __int64 v9; // rcx
  char IsPowerTransitionState; // di
  int IsSessionTearingDown; // eax
  int v12; // ebx
  __int64 v13; // rdx
  bool v14; // di
  CProcessStateManager *v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int IsSIDSystemManagedAccount; // eax
  __int64 v19; // rdx
  bool IsUserOOBESignInOrSignOut; // al
  CProcessStateManager *v21; // rcx
  bool v22; // r12
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, int *); // rbx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  unsigned __int16 v28; // r8
  int v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v33; // rdi
  __int64 (__fastcall *v34)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v35; // rax
  int v36; // eax
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdx
  CLogonController *v40; // rcx
  int v42; // [rsp+20h] [rbp-E0h]
  bool v43[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v44; // [rsp+34h] [rbp-CCh] BYREF
  bool v45; // [rsp+38h] [rbp-C8h] BYREF
  bool v46; // [rsp+39h] [rbp-C7h] BYREF
  unsigned __int16 v47; // [rsp+3Ch] [rbp-C4h] BYREF
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v48; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  struct IAsyncInfo *v50; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v53[3]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v54; // [rsp+80h] [rbp-80h] BYREF
  PSRWLOCK Buf1[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v57; // [rsp+B8h] [rbp-48h]
  _QWORD v58[42]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v54 = a2;
  v50 = (struct IAsyncInfo *)a2;
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v58,
    "CLogonController_DisplayStatus_Activity");
  v58[0] = &LogonControllerTelemetry::CLogonController_DisplayStatus_Activity::`vftable';
  *(struct _GUID *)Buf1 = *GetFirstRunTelemetryCorrelationId((struct _GUID *)Buf1);
  if ( memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v58,
      Buf1);
  LogonControllerTelemetry::CLogonController_DisplayStatus_Activity::StartActivity((LogonControllerTelemetry::CLogonController_DisplayStatus_Activity *)v58);
  *a4 = 0;
  v8 = (unsigned int)CLogonController::_WinRTLogonStateFromWLUIState(v7, a3);
  IsPowerTransitionState = CLogonController::_IsPowerTransitionState(v9, v8);
  if ( !IsPowerTransitionState )
  {
    if ( (_DWORD)v8 )
      CLogonController::_CancelPowerTransition((CLogonController *)(a1 - 32));
LABEL_8:
    IsSessionTearingDown = CProcessStateManager::SetIsSessionTearingDown(
                             *(CProcessStateManager **)(a1 - 32 + 144),
                             IsPowerTransitionState);
    v12 = IsSessionTearingDown;
    if ( IsSessionTearingDown < 0 )
    {
      v13 = 835;
      goto LABEL_10;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(Buf1, a1 + 256);
    *(_DWORD *)(a1 + 264) = v8;
    if ( Buf1[0] )
      ReleaseSRWLockExclusive(Buf1[0]);
    v43[0] = 0;
    IsSessionTearingDown = CLogonController::_IsOOBEAutoLogon((CLogonController *)(a1 - 32), v43);
    v12 = IsSessionTearingDown;
    if ( IsSessionTearingDown < 0 )
    {
      v13 = 845;
      goto LABEL_10;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockShared(Buf1, a1 + 256);
    LOBYTE(v47) = *(_BYTE *)(a1 + 272);
    if ( Buf1[0] )
      ReleaseSRWLockShared(Buf1[0]);
    v14 = 0;
    v46 = 0;
    if ( CProcessStateManager::IsLoggedOnUserSidPresent(*(CProcessStateManager **)(a1 + 112)) && (_DWORD)v8 == 2 )
    {
      v45 = 0;
      IsSessionTearingDown = CLogonController::_IsSystemManagedAutologonSet((CLogonController *)(a1 - 32), &v45);
      v12 = IsSessionTearingDown;
      if ( IsSessionTearingDown < 0 )
      {
        v13 = 859;
        goto LABEL_10;
      }
      if ( v45 )
      {
        string = 0;
        v16 = *(_QWORD *)(a1 + 112);
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)(v16 + 16) + 80LL);
        WindowsDeleteString(0);
        string = 0;
        IsSIDSystemManagedAccount = v17(v16 + 16, &string);
        v12 = IsSIDSystemManagedAccount;
        if ( IsSIDSystemManagedAccount < 0 )
        {
          v19 = 864;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)IsSIDSystemManagedAccount,
            v42);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_75;
        }
        IsSIDSystemManagedAccount = CLogonController::_IsSIDSystemManagedAccount(
                                      (CLogonController *)(a1 - 32),
                                      string,
                                      &v46);
        v12 = IsSIDSystemManagedAccount;
        if ( IsSIDSystemManagedAccount < 0 )
        {
          v19 = 866;
          goto LABEL_24;
        }
        WindowsDeleteString(string);
        v14 = v46;
      }
    }
    IsUserOOBESignInOrSignOut = CProcessStateManager::IsUserOOBESignInOrSignOut(v15);
    v22 = IsUserOOBESignInOrSignOut;
    if ( (!(_BYTE)v47 && !v43[0]
       || IsUserOOBESignInOrSignOut
       || CProcessStateManager::IsFirstSignInAnimationDisabled(v21))
      && !v14 )
    {
      if ( !(unsigned __int8)SilentTSAutologonManager::IsSilentTSAutoLogon(*(_QWORD *)(a1 + 152), 4) )
        goto LABEL_37;
      v52 = 0;
      v23 = *(_QWORD *)(a1 + 112);
      v24 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v23 + 56LL);
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v56, &v50);
      IsSessionTearingDown = v24(v23, *(_QWORD *)(v25 + 24), &v52);
      v12 = IsSessionTearingDown;
      if ( IsSessionTearingDown < 0 )
      {
        v13 = 882;
        goto LABEL_10;
      }
      if ( v52 == 1 )
      {
LABEL_37:
        v44 = 0;
        IsSessionTearingDown = CLogonController::_TransitionToScheduling((CLogonController *)(a1 - 32), &v44);
        v12 = IsSessionTearingDown;
        if ( IsSessionTearingDown < 0 )
        {
          v13 = 894;
          goto LABEL_10;
        }
        v56[0] = a1 - 32;
        v56[1] = &v44;
        v57 = 1;
        v48 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        v26 = CLogonController::_EnsureLogonUX((CLogonController *)(a1 - 32), &v48);
        v12 = v26;
        if ( v26 < 0 )
        {
          v27 = 902;
LABEL_41:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)v26,
            v42);
LABEL_42:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          CLogonController::_TransitionToNone((CLogonController *)(a1 - 32), v44);
          goto LABEL_75;
        }
        if ( (unsigned __int8)CProcessStateManager::ShouldHideAutoLogonUI(*(_QWORD *)(a1 + 112), 0) )
        {
          v26 = CLogonController::_HideLogonUI((CLogonController *)(a1 - 32));
          v12 = v26;
          if ( v26 < 0 )
          {
            v27 = 906;
            goto LABEL_41;
          }
        }
        v43[0] = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) + 224LL))(
                *(_QWORD *)(a1 + 112) + 16LL,
                v43);
        v12 = v26;
        if ( v26 < 0 )
        {
          v27 = 910;
          goto LABEL_41;
        }
        memset(v53, 0, sizeof(v53));
        if ( !v22 || v43[0] )
        {
          v32 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  (__int64)v53,
                  v54,
                  0xFFFFFFFFFFFFFFFFuLL);
          v12 = v32;
          if ( v32 < 0 )
          {
            v30 = (unsigned int)v32;
            v31 = 927;
            goto LABEL_56;
          }
        }
        else
        {
          v12 = -2147467259;
          Buf1[0] = 0;
          v47 = 0;
          if ( !Windows::Internal::ResourceString::FindAndSize(
                  &_ImageBase,
                  0x70u,
                  v28,
                  (const unsigned __int16 **)Buf1,
                  &v47)
            || (v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        (__int64)v53,
                        Buf1[0],
                        v47),
                v12 < 0) )
          {
            v30 = (unsigned int)v12;
            v31 = 917;
            goto LABEL_56;
          }
          if ( IsOobeInEnduserSession() )
          {
            v29 = CLogonController::_HideLogonUI((CLogonController *)(a1 - 32));
            v12 = v29;
            if ( v29 < 0 )
            {
              v30 = (unsigned int)v29;
              v31 = 922;
LABEL_56:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v31,
                (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                (const char *)v30,
                v42);
LABEL_57:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v53);
              goto LABEL_42;
            }
          }
        }
        v49 = 0;
        v33 = v48;
        v34 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v48 + 104LL);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v49);
        v54 = (_WORD *)v53[0];
        v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(Buf1, &v54);
        v36 = v34(v33, (unsigned int)v8, *(_QWORD *)(v35 + 24), &v49);
        v12 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A2,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)v36,
            v42);
LABEL_62:
          Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v49);
          goto LABEL_57;
        }
        v50 = 0;
        v37 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::As<IAsyncInfo>(&v49, &v50);
        v12 = v37;
        if ( v37 < 0 )
        {
          v38 = 933;
LABEL_65:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)v37,
            v42);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          goto LABEL_62;
        }
        v37 = CLogonController::_TransitionToRunning((CLogonController *)(a1 - 32), v44, v50, a4);
        v12 = v37;
        if ( v37 < 0 )
        {
          v38 = 934;
          goto LABEL_65;
        }
        if ( !*a4 )
        {
          v37 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
                  v49,
                  v39,
                  0);
          v12 = v37;
          if ( v37 < 0 )
          {
            v38 = 937;
            goto LABEL_65;
          }
          v37 = CLogonController::_CheckOperationAborted(v40, v50, a4);
          v12 = v37;
          if ( v37 < 0 )
          {
            v38 = 938;
            goto LABEL_65;
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v49);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        CLogonController::_TransitionToNone((CLogonController *)(a1 - 32), v44);
      }
    }
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58, 0);
    v12 = 0;
    goto LABEL_75;
  }
  IsSessionTearingDown = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) + 56LL))(*(_QWORD *)(a1 + 112) + 16LL);
  v12 = IsSessionTearingDown;
  if ( IsSessionTearingDown >= 0 )
    goto LABEL_8;
  v13 = 826;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)IsSessionTearingDown,
    v42);
LABEL_75:
  LogonControllerTelemetry::CLogonController_DisplayStatus_Activity::~CLogonController_DisplayStatus_Activity((LogonControllerTelemetry::CLogonController_DisplayStatus_Activity *)v58);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800752b0  push    rbp
0x1800752b2  push    rbx
0x1800752b3  push    rsi
0x1800752b4  push    rdi
0x1800752b5  push    r12
0x1800752b7  push    r13
0x1800752b9  push    r14
0x1800752bb  push    r15
0x1800752bd  lea     rbp, [rsp-138h]
0x1800752c5  sub     rsp, 238h
0x1800752cc  mov     rax, cs:__security_cookie
0x1800752d3  xor     rax, rsp
0x1800752d6  mov     [rbp+170h+var_50], rax
0x1800752dd  mov     r13, r9
0x1800752e0  mov     ebx, r8d
0x1800752e3  mov     [rbp+170h+var_1F0], rdx
0x1800752e7  mov     r14, rcx
0x1800752ea  mov     [rsp+270h+var_220], rdx
0x1800752ef  lea     rdx, aClogoncontroll_8; "CLogonController_DisplayStatus_Activity"
0x1800752f6  lea     rcx, [rbp+170h+var_1A0]
0x1800752fa  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800752ff  lea     rax, ??_7CLogonController_DisplayStatus_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_DisplayStatus_Activity::`vftable'
0x180075306  mov     [rbp+170h+var_1A0], rax
0x18007530a  lea     rcx, [rbp+170h+Buf1]; retstr
0x18007530e  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x180075313  movups  xmm0, xmmword ptr [rax]
0x180075316  movdqu  xmmword ptr [rbp+170h+Buf1], xmm0
0x18007531b  mov     r8d, 10h; Size
0x180075321  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180075328  lea     rcx, [rbp+170h+Buf1]; Buf1
0x18007532c  call    memcmp_0
0x180075331  xor     r12d, r12d
0x180075334  test    eax, eax
0x180075336  jz      short loc_180075345
0x180075338  lea     rdx, [rbp+170h+Buf1]
0x18007533c  lea     rcx, [rbp+170h+var_1A0]
0x180075340  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x180075345  lea     rcx, [rbp+170h+var_1A0]; this
0x180075349  call    ?StartActivity@CLogonController_DisplayStatus_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_DisplayStatus_Activity::StartActivity(void)
0x18007534e  mov     [r13+0], r12d
0x180075352  mov     edx, ebx
0x180075354  call    ?_WinRTLogonStateFromWLUIState@CLogonController@@AEAA?AW4LogonUIState@Controller@Logon@UI@Internal@Windows@@W4_WLUI_STATE@@@Z; CLogonController::_WinRTLogonStateFromWLUIState(_WLUI_STATE)
0x180075359  mov     r15d, eax
0x18007535c  mov     edx, eax
0x18007535e  call    ?_IsPowerTransitionState@CLogonController@@AEAA_NW4LogonUIState@Controller@Logon@UI@Internal@Windows@@@Z; CLogonController::_IsPowerTransitionState(Windows::Internal::UI::Logon::Controller::LogonUIState)
0x180075363  mov     dil, al
0x180075366  test    al, al
0x180075368  jz      short loc_18007538B
0x18007536a  mov     rcx, [r14+70h]
0x18007536e  add     rcx, 10h
0x180075372  mov     rdx, [rcx]
0x180075375  mov     rax, [rdx+38h]
0x180075379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007537e  mov     ebx, eax
0x180075380  test    eax, eax
0x180075382  jns     short loc_180075399
0x180075384  mov     edx, 33Ah
0x180075389  jmp     short loc_1800753B7
0x18007538b  test    r15d, r15d
0x18007538e  jz      short loc_180075399
0x180075390  lea     rcx, [r14-20h]; this
0x180075394  call    ?_CancelPowerTransition@CLogonController@@AEAAXXZ; CLogonController::_CancelPowerTransition(void)
0x180075399  lea     rsi, [r14-20h]
0x18007539d  mov     dl, dil; bool
0x1800753a0  mov     rcx, [rsi+90h]; this
0x1800753a7  call    ?SetIsSessionTearingDown@CProcessStateManager@@QEAAJ_N@Z; CProcessStateManager::SetIsSessionTearingDown(bool)
0x1800753ac  mov     ebx, eax
0x1800753ae  test    eax, eax
0x1800753b0  jns     short loc_1800753D2
0x1800753b2  mov     edx, 343h; void *
0x1800753b7  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800753be  mov     r9d, eax; char *
0x1800753c1  mov     rcx, [rbp+178h]; this
0x1800753c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800753cd  jmp     loc_1800758DB
0x1800753d2  lea     rdi, [r14+100h]
0x1800753d9  mov     rdx, rdi
0x1800753dc  lea     rcx, [rbp+170h+Buf1]
0x1800753e0  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800753e5  mov     [r14+108h], r15d
0x1800753ec  mov     rcx, [rbp+170h+Buf1]; SRWLock
0x1800753f0  test    rcx, rcx
0x1800753f3  jz      short loc_1800753FB
0x1800753f5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800753fb  mov     [rsp+270h+var_240], r12b
0x180075400  lea     rdx, [rsp+270h+var_240]; bool *
0x180075405  mov     rcx, rsi; this
0x180075408  call    ?_IsOOBEAutoLogon@CLogonController@@AEAAJPEA_N@Z; CLogonController::_IsOOBEAutoLogon(bool *)
0x18007540d  mov     ebx, eax
0x18007540f  test    eax, eax
0x180075411  jns     short loc_18007541A
0x180075413  mov     edx, 34Dh
0x180075418  jmp     short loc_1800753B7
0x18007541a  mov     rdx, rdi
0x18007541d  lea     rcx, [rbp+170h+Buf1]
0x180075421  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180075426  mov     al, [r14+110h]
0x18007542d  mov     byte ptr [rsp+270h+var_234], al
0x180075431  mov     rcx, [rbp+170h+Buf1]; SRWLock
0x180075435  test    rcx, rcx
0x180075438  jz      short loc_180075440
0x18007543a  call    cs:__imp_ReleaseSRWLockShared
0x180075440  mov     dil, r12b
0x180075443  mov     [rsp+270h+var_237], r12b
0x180075448  mov     rcx, [r14+70h]; this
0x18007544c  call    ?IsLoggedOnUserSidPresent@CProcessStateManager@@QEAA_NXZ; CProcessStateManager::IsLoggedOnUserSidPresent(void)
0x180075451  test    al, al
0x180075453  jz      loc_180075525
0x180075459  cmp     r15d, 2
0x18007545d  jnz     loc_180075525
0x180075463  mov     [rsp+270h+var_238], r12b
0x180075468  lea     rdx, [rsp+270h+var_238]; bool *
0x18007546d  mov     rcx, rsi; this
0x180075470  call    ?_IsSystemManagedAutologonSet@CLogonController@@AEAAJPEA_N@Z; CLogonController::_IsSystemManagedAutologonSet(bool *)
0x180075475  mov     ebx, eax
0x180075477  test    eax, eax
0x180075479  jns     short loc_180075485
0x18007547b  mov     edx, 35Bh
0x180075480  jmp     loc_1800753B7
0x180075485  cmp     [rsp+270h+var_238], r12b
0x18007548a  jz      loc_180075525
0x180075490  mov     [rsp+270h+string], r12
0x180075495  mov     rdi, [r14+70h]
0x180075499  mov     rax, [rdi+10h]
0x18007549d  mov     rbx, [rax+50h]
0x1800754a1  xor     ecx, ecx; string
0x1800754a3  call    cs:__imp_WindowsDeleteString
0x1800754a9  mov     [rsp+270h+string], r12
0x1800754ae  lea     rdx, [rsp+270h+string]
0x1800754b3  lea     rcx, [rdi+10h]
0x1800754b7  mov     rax, rbx
0x1800754ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800754bf  mov     ebx, eax
0x1800754c1  test    eax, eax
0x1800754c3  jns     short loc_1800754F6
0x1800754c5  mov     edx, 360h; void *
0x1800754ca  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800754d1  mov     r9d, eax; char *
0x1800754d4  mov     rcx, [rbp+178h]; this
0x1800754db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800754e0  nop
0x1800754e1  mov     rcx, [rsp+270h+string]; string
0x1800754e6  call    cs:__imp_WindowsDeleteString
0x1800754ec  mov     [rsp+270h+string], r12
0x1800754f1  jmp     loc_1800758DB
0x1800754f6  lea     r8, [rsp+270h+var_237]; bool *
0x1800754fb  mov     rdx, [rsp+270h+string]; string
0x180075500  mov     rcx, rsi; this
0x180075503  call    ?_IsSIDSystemManagedAccount@CLogonController@@AEAAJPEAUHSTRING__@@PEA_N@Z; CLogonController::_IsSIDSystemManagedAccount(HSTRING__ *,bool *)
0x180075508  mov     ebx, eax
0x18007550a  test    eax, eax
0x18007550c  jns     short loc_180075515
0x18007550e  mov     edx, 362h
0x180075513  jmp     short loc_1800754CA
0x180075515  mov     rcx, [rsp+270h+string]; string
0x18007551a  call    cs:__imp_WindowsDeleteString
0x180075520  mov     dil, [rsp+270h+var_237]
0x180075525  call    ?IsUserOOBESignInOrSignOut@CProcessStateManager@@QEAA_NXZ; CProcessStateManager::IsUserOOBESignInOrSignOut(void)
0x18007552a  mov     r12b, al
0x18007552d  cmp     byte ptr [rsp+270h+var_234], 0
0x180075532  jnz     short loc_18007553B
0x180075534  cmp     [rsp+270h+var_240], 0
0x180075539  jz      short loc_18007554D
0x18007553b  test    r12b, r12b
0x18007553e  jnz     short loc_18007554D
0x180075540  call    ?IsFirstSignInAnimationDisabled@CProcessStateManager@@QEAA_NXZ; CProcessStateManager::IsFirstSignInAnimationDisabled(void)
0x180075545  test    al, al
0x180075547  jz      loc_1800758CC
0x18007554d  test    dil, dil
0x180075550  jnz     loc_1800758CC
0x180075556  mov     edx, 4
0x18007555b  mov     rcx, [r14+98h]
0x180075562  call    ?IsSilentTSAutoLogon@SilentTSAutologonManager@@QEAA_NW4LogonUIRequestReason@Controller@Logon@UI@Internal@Windows@@@Z; SilentTSAutologonManager::IsSilentTSAutoLogon(Windows::Internal::UI::Logon::Controller::LogonUIRequestReason)
0x180075567  xor     edi, edi
0x180075569  test    al, al
0x18007556b  jz      short loc_1800755BC
0x18007556d  mov     [rsp+270h+var_210], edi
0x180075571  mov     rdi, [r14+70h]
0x180075575  mov     rax, [rdi]
0x180075578  mov     rbx, [rax+38h]
0x18007557c  lea     rdx, [rsp+270h+var_220]
0x180075581  lea     rcx, [rbp+170h+var_1C8]
0x180075585  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007558a  nop
0x18007558b  lea     r8, [rsp+270h+var_210]
0x180075590  mov     rdx, [rax+18h]
0x180075594  mov     rcx, rdi
0x180075597  mov     rax, rbx
0x18007559a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007559f  mov     ebx, eax
0x1800755a1  xor     edi, edi
0x1800755a3  test    eax, eax
0x1800755a5  jns     short loc_1800755B1
0x1800755a7  mov     edx, 372h
0x1800755ac  jmp     loc_1800753B7
0x1800755b1  cmp     [rsp+270h+var_210], 1
0x1800755b6  jnz     loc_1800758CE
0x1800755bc  mov     [rsp+270h+var_23C], edi
0x1800755c0  lea     rdx, [rsp+270h+var_23C]; unsigned int *
0x1800755c5  mov     rcx, rsi; this
0x1800755c8  call    ?_TransitionToScheduling@CLogonController@@AEAAJPEAK@Z; CLogonController::_TransitionToScheduling(ulong *)
0x1800755cd  mov     ebx, eax
0x1800755cf  test    eax, eax
0x1800755d1  jns     short loc_1800755DD
0x1800755d3  mov     edx, 37Eh
0x1800755d8  jmp     loc_1800753B7
0x1800755dd  mov     [rbp+170h+var_1C8], rsi
0x1800755e1  lea     rax, [rsp+270h+var_23C]
0x1800755e6  mov     [rbp+170h+var_1C0], rax
0x1800755ea  mov     [rbp+170h+var_1B8], 1
0x1800755ee  mov     [rsp+270h+var_230], rdi
0x1800755f3  lea     rcx, [rsp+270h+var_230]
0x1800755f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800755fd  lea     rdx, [rsp+270h+var_230]; struct Windows::Internal::UI::Logon::Controller::ILogonUX **
0x180075602  mov     rcx, rsi; this
0x180075605  call    ?_EnsureLogonUX@CLogonController@@AEAAJPEAPEAUILogonUX@Controller@Logon@UI@Internal@Windows@@@Z; CLogonController::_EnsureLogonUX(Windows::Internal::UI::Logon::Controller::ILogonUX * *)
0x18007560a  mov     ebx, eax
0x18007560c  test    eax, eax
0x18007560e  jns     short loc_180075648
0x180075610  mov     edx, 386h; void *
0x180075615  mov     rcx, [rbp+178h]; this
0x18007561c  mov     r9d, eax; char *
0x18007561f  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180075626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007562b  nop
0x18007562c  lea     rcx, [rsp+270h+var_230]
0x180075631  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075636  nop
0x180075637  mov     edx, [rsp+270h+var_23C]; unsigned int
0x18007563b  mov     rcx, rsi; this
0x18007563e  call    ?_TransitionToNone@CLogonController@@AEAAXK@Z; CLogonController::_TransitionToNone(ulong)
0x180075643  jmp     loc_1800758DB
0x180075648  xor     edx, edx
0x18007564a  mov     rcx, [r14+70h]
0x18007564e  call    ?ShouldHideAutoLogonUI@CProcessStateManager@@QEAA_NW4CacheBehavior@1@@Z; CProcessStateManager::ShouldHideAutoLogonUI(CProcessStateManager::CacheBehavior)
0x180075653  test    al, al
0x180075655  jz      short loc_18007566C
0x180075657  mov     rcx, rsi; this
0x18007565a  call    ?_HideLogonUI@CLogonController@@AEAAJXZ; CLogonController::_HideLogonUI(void)
0x18007565f  mov     ebx, eax
0x180075661  test    eax, eax
0x180075663  jns     short loc_18007566C
0x180075665  mov     edx, 38Ah
0x18007566a  jmp     short loc_180075615
0x18007566c  mov     [rsp+270h+var_240], dil
0x180075671  mov     rcx, [r14+70h]
0x180075675  add     rcx, 10h
0x180075679  mov     rax, [rcx]
0x18007567c  lea     rdx, [rsp+270h+var_240]
0x180075681  mov     rax, [rax+0E0h]
0x180075688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007568d  mov     ebx, eax
0x18007568f  test    eax, eax
0x180075691  jns     short loc_18007569D
0x180075693  mov     edx, 38Eh
0x180075698  jmp     loc_180075615
0x18007569d  mov     [rsp+270h+var_208], rdi
0x1800756a2  mov     [rsp+270h+var_200], rdi
0x1800756a7  mov     [rsp+270h+var_1F8], rdi
0x1800756ac  test    r12b, r12b
0x1800756af  jz      loc_180075757
0x1800756b5  cmp     [rsp+270h+var_240], dil
0x1800756ba  jnz     loc_180075757
0x1800756c0  mov     ebx, 80004005h
0x1800756c5  mov     [rbp+170h+Buf1], rdi
0x1800756c9  mov     [rsp+270h+var_234], di
0x1800756ce  lea     rax, [rsp+270h+var_234]
0x1800756d3  mov     qword ptr [rsp+270h+var_250], rax; int
0x1800756d8  lea     r9, [rbp+170h+Buf1]; unsigned __int16 **
0x1800756dc  mov     edx, 70h ; 'p'; unsigned int
0x1800756e1  lea     rcx, __ImageBase; hModule
0x1800756e8  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x1800756ed  test    al, al
0x1800756ef  jz      short loc_18007572C
0x1800756f1  movzx   r8d, [rsp+270h+var_234]
0x1800756f7  mov     rdx, [rbp+170h+Buf1]
0x1800756fb  lea     rcx, [rsp+270h+var_208]
0x180075700  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180075705  mov     ebx, eax
0x180075707  test    eax, eax
0x180075709  js      short loc_18007572C
0x18007570b  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x180075710  test    al, al
0x180075712  jz      short loc_180075779
0x180075714  mov     rcx, rsi; this
0x180075717  call    ?_HideLogonUI@CLogonController@@AEAAJXZ; CLogonController::_HideLogonUI(void)
0x18007571c  mov     ebx, eax
0x18007571e  test    eax, eax
0x180075720  jns     short loc_180075779
0x180075722  mov     r9d, eax
0x180075725  mov     edx, 39Ah
0x18007572a  jmp     short loc_180075734
0x18007572c  mov     r9d, ebx; char *
0x18007572f  mov     edx, 395h; void *
0x180075734  mov     rcx, [rbp+178h]; this
0x18007573b  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180075742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075747  nop
0x180075748  lea     rcx, [rsp+270h+var_208]
0x18007574d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```
