# CLogonController::InformLogonUI(_WLUI_INFORMATION,_WLUI_STATE,_WLUI_REASON)

- ea: `0x180059510`
- end: `0x180059a00`
- name: `?InformLogonUI@CLogonController@@UEAAJW4_WLUI_INFORMATION@@W4_WLUI_STATE@@W4_WLUI_REASON@@@Z`
- size: `1264`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `broker_com_uri`

## callees

- `0x180008094`
- `0x180015920`
- `0x18001db70`
- `0x18001f3a0`
- `0x180026e70`
- `0x18002f554`
- `0x180031a38`
- `0x180039bb0`
- `0x180042c18`
- `0x180043d0c`
- `0x18004505c`
- `0x180047914`
- `0x18004ae38`
- `0x18004b4ec`
- `0x18004bfb4`
- `0x18004cce8`
- `0x18004d9ac`
- `0x18004dc4c`
- `0x1800507e4`
- `0x180059510`
- `0x180059a08`
- `0x18005b3e4`
- `0x18005c528`
- `0x18005d488`
- `0x18005f1a0`
- `0x18006c000`
- `0x180077e08`
- `0x18007bf9c`
- `0x180083a98`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18005973a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18005973a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005963b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180059650`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005963b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180059650`
- `SHCORE!SHDeleteValueW` at `0x1800598f9`
- `SHCORE!SHDeleteValueW` at `0x180059910`
- `SHCORE!SHDeleteValueW` at `0x1800598f9`
- `SHCORE!SHDeleteValueW` at `0x180059910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLogonController::InformLogonUI(__int64 a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v8; // rcx
  unsigned int v9; // r14d
  CProcessStateManager *v10; // rcx
  int IsFirstLogonAfterSignOut; // eax
  unsigned int v12; // ebx
  int IsSessionTearingDown; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  char IsPowerTransitionState; // r15
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  int v25; // eax
  __int64 v26; // rdx
  int v27; // [rsp+20h] [rbp-E0h]
  _BYTE v28[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "CLogonController_InformLogonUI_Activity");
  v31[0] = &LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v31,
      &Buf1);
  LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::StartActivity((LogonControllerTelemetry::CLogonController_InformLogonUI_Activity *)v31);
  v9 = CLogonController::_WinRTLogonStateFromWLUIState(v8, a3);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&Buf1, a1 + 256);
  *(_DWORD *)(a1 - 32 + 296) = v9;
  if ( v9 != 5
    || (v29[0] = 0,
        SHRegGetDWORD(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          L"DefaultAccountAction",
          v29),
        v29[0] == 2)
    || (IsFirstLogonAfterSignOut = CProcessStateManager::SetIsFirstLogonAfterSignOut(v10, 1u),
        v12 = IsFirstLogonAfterSignOut,
        IsFirstLogonAfterSignOut >= 0) )
  {
    if ( *(_QWORD *)&Buf1.Data1 )
      ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
    IsSessionTearingDown = CProcessStateManager::SetWinLogonReason(*(_QWORD *)(a1 + 112), a4);
    v12 = IsSessionTearingDown;
    if ( IsSessionTearingDown < 0 )
    {
      v15 = 1917;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)IsSessionTearingDown,
        v27);
      goto LABEL_32;
    }
    IsPowerTransitionState = CLogonController::_IsPowerTransitionState(v14, v9);
    IsSessionTearingDown = CProcessStateManager::SetIsSessionTearingDown(
                             *(CProcessStateManager **)(a1 + 112),
                             IsPowerTransitionState);
    v12 = IsSessionTearingDown;
    if ( IsSessionTearingDown < 0 )
    {
      v15 = 1918;
      goto LABEL_12;
    }
    if ( IsPowerTransitionState )
    {
      IsSessionTearingDown = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) + 56LL))(*(_QWORD *)(a1 + 112) + 16LL);
      v12 = IsSessionTearingDown;
      if ( IsSessionTearingDown < 0 )
      {
        v15 = 1922;
        goto LABEL_12;
      }
    }
    v18 = CLogonController::_WinRTLogonInformationFromWLUIInformation(v17, a2);
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 2;
          if ( v21 )
          {
            if ( v21 == 1 )
            {
              *(_QWORD *)v29 = 0;
              Microsoft::WRL::Wrappers::SRWLock::LockShared(&Buf1, a1 + 312);
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=(v29, a1 + 328);
              if ( *(_QWORD *)&Buf1.Data1 )
                ReleaseSRWLockShared(*(PSRWLOCK *)&Buf1.Data1);
              v22 = CLogonController::_EnsureFSIA((CLogonController *)(a1 - 32));
              v12 = v22;
              if ( v22 < 0 )
              {
                v23 = 2009;
LABEL_27:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v23,
                  (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                  (const char *)(unsigned int)v22,
                  v27);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
                goto LABEL_32;
              }
              LOBYTE(v27) = 0;
              v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 376) + 48LL))(
                      *(_QWORD *)(a1 + 376),
                      *(_QWORD *)(a1 + 144),
                      *(_QWORD *)(a1 + 136),
                      *(_QWORD *)v29);
              v12 = v22;
              if ( v22 < 0 )
              {
                v23 = 2010;
                goto LABEL_27;
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
            }
          }
          else
          {
            IsSessionTearingDown = CLogonController::_EnsureSoundPlayer((CLogonController *)(a1 - 32));
            v12 = IsSessionTearingDown;
            if ( IsSessionTearingDown < 0 )
            {
              v15 = 1969;
              goto LABEL_12;
            }
            if ( IsPowerTransitionState )
            {
              IsSessionTearingDown = LogonSound::StartLogoffSound(*(_QWORD *)(a1 + 384), v9 == 5);
              v12 = IsSessionTearingDown;
              if ( IsSessionTearingDown < 0 )
              {
                v15 = 1972;
                goto LABEL_12;
              }
            }
          }
        }
        else
        {
          if ( (unsigned __int8)CProcessStateManager::ShouldHideAutoLogonUI(*(_QWORD *)(a1 + 112), 1) )
          {
            IsSessionTearingDown = CLogonController::_HideLogonUI((CLogonController *)(a1 - 32));
            v12 = IsSessionTearingDown;
            if ( IsSessionTearingDown < 0 )
            {
              v15 = 1959;
              goto LABEL_12;
            }
          }
          IsSessionTearingDown = CLogonController::_EnsureSoundPlayer((CLogonController *)(a1 - 32));
          v12 = IsSessionTearingDown;
          if ( IsSessionTearingDown < 0 )
          {
            v15 = 1963;
            goto LABEL_12;
          }
          v25 = LogonSound::PlayLogonSoundIfNecessary(*(LogonSound **)(a1 + 384), *(struct IInspectable **)(a1 + 144));
          if ( v25 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7AC,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
              (const char *)(unsigned int)v25,
              v27);
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8LL) + 72LL))(*(_QWORD *)(a1 + 144) + 8LL);
        CProcessStateManager::ResetIsBoot(*(CProcessStateManager **)(a1 + 112));
        if ( *(_QWORD *)(a1 + 384) )
        {
          SHDeleteValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\LogonSoundPlayed",
            L"LogonUIChecked");
          SHDeleteValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\LogonSoundPlayed",
            L"SoundPlayed");
        }
        LOBYTE(v26) = 1;
        IsSessionTearingDown = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL)
                                                                           + 144LL))(
                                 *(_QWORD *)(a1 + 112) + 16LL,
                                 v26);
        v12 = IsSessionTearingDown;
        if ( IsSessionTearingDown < 0 )
        {
          v15 = 1945;
          goto LABEL_12;
        }
        IsSessionTearingDown = CLogonController::_HideLogonUI((CLogonController *)(a1 - 32));
        v12 = IsSessionTearingDown;
        if ( IsSessionTearingDown < 0 )
        {
          v15 = 1947;
          goto LABEL_12;
        }
      }
    }
    else if ( IsOobeInEnduserSession() && *(_DWORD *)(a1 + 264) == 5 )
    {
      v29[0] = 0;
      SHRegGetDWORD(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
        L"DefaultAccountAction",
        v29);
      if ( v29[0] == 2 )
      {
        v28[0] = 0;
        IsSessionTearingDown = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL)
                                                                           + 224LL))(
                                 *(_QWORD *)(a1 + 112) + 16LL,
                                 v28);
        v12 = IsSessionTearingDown;
        if ( IsSessionTearingDown < 0 )
        {
          v15 = 1990;
          goto LABEL_12;
        }
        if ( !v28[0] )
        {
          IsSessionTearingDown = CLogonController::_HideLogonUI((CLogonController *)(a1 - 32));
          v12 = IsSessionTearingDown;
          if ( IsSessionTearingDown < 0 )
          {
            v15 = 1993;
            goto LABEL_12;
          }
        }
      }
    }
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31, 0);
    v12 = 0;
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x778,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)IsFirstLogonAfterSignOut,
    v27);
  if ( *(_QWORD *)&Buf1.Data1 )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
LABEL_32:
  LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::~CLogonController_InformLogonUI_Activity((LogonControllerTelemetry::CLogonController_InformLogonUI_Activity *)v31);
  return v12;
}

```

## disassembly

```asm
0x180059510  push    rbp
0x180059512  push    rbx
0x180059513  push    rsi
0x180059514  push    rdi
0x180059515  push    r12
0x180059517  push    r14
0x180059519  push    r15
0x18005951b  lea     rbp, [rsp-0C0h]
0x180059523  sub     rsp, 1C0h
0x18005952a  mov     rax, cs:__security_cookie
0x180059531  xor     rax, rsp
0x180059534  mov     [rbp+0F0h+var_40], rax
0x18005953b  mov     r15d, r9d
0x18005953e  mov     ebx, r8d
0x180059541  mov     r12d, edx
0x180059544  mov     rdi, rcx
0x180059547  lea     rdx, aClogoncontroll_6; "CLogonController_InformLogonUI_Activity"
0x18005954e  lea     rcx, [rsp+1F0h+var_190]
0x180059553  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180059558  lea     rax, ??_7CLogonController_InformLogonUI_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::`vftable'
0x18005955f  mov     [rsp+1F0h+var_190], rax
0x180059564  lea     rcx, [rsp+1F0h+Buf1]; retstr
0x180059569  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18005956e  movups  xmm0, xmmword ptr [rax]
0x180059571  movdqu  [rsp+1F0h+Buf1], xmm0
0x180059577  mov     r8d, 10h; Size
0x18005957d  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180059584  lea     rcx, [rsp+1F0h+Buf1]; Buf1
0x180059589  call    memcmp_0
0x18005958e  test    eax, eax
0x180059590  jz      short loc_1800595A1
0x180059592  lea     rdx, [rsp+1F0h+Buf1]
0x180059597  lea     rcx, [rsp+1F0h+var_190]
0x18005959c  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1800595a1  lea     rcx, [rsp+1F0h+var_190]; this
0x1800595a6  call    ?StartActivity@CLogonController_InformLogonUI_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::StartActivity(void)
0x1800595ab  mov     edx, ebx
0x1800595ad  call    ?_WinRTLogonStateFromWLUIState@CLogonController@@AEAA?AW4LogonUIState@Controller@Logon@UI@Internal@Windows@@W4_WLUI_STATE@@@Z; CLogonController::_WinRTLogonStateFromWLUIState(_WLUI_STATE)
0x1800595b2  mov     r14d, eax
0x1800595b5  lea     rdx, [rdi+100h]
0x1800595bc  lea     rcx, [rsp+1F0h+Buf1]
0x1800595c1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800595c6  lea     rsi, [rdi-20h]
0x1800595ca  mov     [rsi+128h], r14d
0x1800595d1  cmp     r14d, 5
0x1800595d5  jnz     short loc_180059646
0x1800595d7  mov     [rsp+1F0h+var_1A8], 0
0x1800595df  lea     r9, [rsp+1F0h+var_1A8]; unsigned int *
0x1800595e4  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x1800595eb  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800595f2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800595f9  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800595fe  cmp     [rsp+1F0h+var_1A8], 2
0x180059603  jz      short loc_180059646
0x180059605  mov     dl, 1; unsigned __int8
0x180059607  call    ?SetIsFirstLogonAfterSignOut@CProcessStateManager@@QEAAJE@Z; CProcessStateManager::SetIsFirstLogonAfterSignOut(uchar)
0x18005960c  mov     ebx, eax
0x18005960e  test    eax, eax
0x180059610  jns     short loc_180059646
0x180059612  mov     rcx, [rbp+0F8h]; this
0x180059619  mov     r9d, eax; char *
0x18005961c  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180059623  mov     edx, 778h; void *
0x180059628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005962d  mov     rcx, qword ptr [rsp+1F0h+Buf1]; SRWLock
0x180059632  test    rcx, rcx
0x180059635  jz      loc_1800597CB
0x18005963b  call    cs:__imp_ReleaseSRWLockExclusive
0x180059641  jmp     loc_1800597CB
0x180059646  mov     rcx, qword ptr [rsp+1F0h+Buf1]; SRWLock
0x18005964b  test    rcx, rcx
0x18005964e  jz      short loc_180059656
0x180059650  call    cs:__imp_ReleaseSRWLockExclusive
0x180059656  mov     edx, r15d
0x180059659  mov     rcx, [rdi+70h]
0x18005965d  call    ?SetWinLogonReason@CProcessStateManager@@QEAAJW4_WLUI_REASON@@@Z; CProcessStateManager::SetWinLogonReason(_WLUI_REASON)
0x180059662  mov     ebx, eax
0x180059664  test    eax, eax
0x180059666  jns     short loc_180059688
0x180059668  mov     edx, 77Dh; void *
0x18005966d  mov     rcx, [rbp+0F8h]; this
0x180059674  mov     r9d, eax; char *
0x180059677  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005967e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059683  jmp     loc_1800597CB
0x180059688  mov     edx, r14d
0x18005968b  call    ?_IsPowerTransitionState@CLogonController@@AEAA_NW4LogonUIState@Controller@Logon@UI@Internal@Windows@@@Z; CLogonController::_IsPowerTransitionState(Windows::Internal::UI::Logon::Controller::LogonUIState)
0x180059690  mov     r15b, al
0x180059693  mov     dl, al; bool
0x180059695  mov     rcx, [rdi+70h]; this
0x180059699  call    ?SetIsSessionTearingDown@CProcessStateManager@@QEAAJ_N@Z; CProcessStateManager::SetIsSessionTearingDown(bool)
0x18005969e  mov     ebx, eax
0x1800596a0  test    eax, eax
0x1800596a2  jns     short loc_1800596AB
0x1800596a4  mov     edx, 77Eh
0x1800596a9  jmp     short loc_18005966D
0x1800596ab  test    r15b, r15b
0x1800596ae  jz      short loc_1800596D1
0x1800596b0  mov     rcx, [rdi+70h]
0x1800596b4  add     rcx, 10h
0x1800596b8  mov     rax, [rcx]
0x1800596bb  mov     rax, [rax+38h]
0x1800596bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596c4  mov     ebx, eax
0x1800596c6  test    eax, eax
0x1800596c8  jns     short loc_1800596D1
0x1800596ca  mov     edx, 782h
0x1800596cf  jmp     short loc_18005966D
0x1800596d1  mov     edx, r12d
0x1800596d4  call    ?_WinRTLogonInformationFromWLUIInformation@CLogonController@@AEAA?AW4LogonUIInformation@Controller@Logon@UI@Internal@Windows@@W4_WLUI_INFORMATION@@@Z; CLogonController::_WinRTLogonInformationFromWLUIInformation(_WLUI_INFORMATION)
0x1800596d9  test    eax, eax
0x1800596db  jz      loc_18005995B
0x1800596e1  sub     eax, 1
0x1800596e4  jz      loc_1800598B7
0x1800596ea  sub     eax, 1
0x1800596ed  jz      loc_18005983A
0x1800596f3  sub     eax, 2
0x1800596f6  jz      loc_1800597F8
0x1800596fc  cmp     eax, 1
0x1800596ff  jnz     loc_1800597BD
0x180059705  mov     qword ptr [rsp+1F0h+var_1A8], 0
0x18005970e  lea     rdx, [rdi+138h]
0x180059715  lea     rcx, [rsp+1F0h+Buf1]
0x18005971a  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18005971f  lea     rdx, [rdi+148h]
0x180059726  lea     rcx, [rsp+1F0h+var_1A8]
0x18005972b  call    ??4?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>> const &)
0x180059730  mov     rcx, qword ptr [rsp+1F0h+Buf1]; SRWLock
0x180059735  test    rcx, rcx
0x180059738  jz      short loc_180059740
0x18005973a  call    cs:__imp_ReleaseSRWLockShared
0x180059740  mov     rcx, rsi; this
0x180059743  call    ?_EnsureFSIA@CLogonController@@AEAAJXZ; CLogonController::_EnsureFSIA(void)
0x180059748  mov     ebx, eax
0x18005974a  test    eax, eax
0x18005974c  jns     short loc_180059776
0x18005974e  mov     edx, 7D9h; void *
0x180059753  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005975a  mov     r9d, eax; char *
0x18005975d  mov     rcx, [rbp+0F8h]; this
0x180059764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059769  nop
0x18005976a  lea     rcx, [rsp+1F0h+var_1A8]
0x18005976f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180059774  jmp     short loc_1800597CB
0x180059776  mov     rcx, [rdi+178h]
0x18005977d  mov     rax, [rcx]
0x180059780  mov     [rsp+1F0h+var_1C8], r14d
0x180059785  mov     [rsp+1F0h+var_1D0], 0
0x18005978a  mov     r9, qword ptr [rsp+1F0h+var_1A8]
0x18005978f  mov     r8, [rdi+88h]
0x180059796  mov     rdx, [rdi+90h]
0x18005979d  mov     rax, [rax+30h]
0x1800597a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597a6  mov     ebx, eax
0x1800597a8  test    eax, eax
0x1800597aa  jns     short loc_1800597B3
0x1800597ac  mov     edx, 7DAh
0x1800597b1  jmp     short loc_180059753
0x1800597b3  lea     rcx, [rsp+1F0h+var_1A8]
0x1800597b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800597bd  xor     edx, edx
0x1800597bf  lea     rcx, [rsp+1F0h+var_190]
0x1800597c4  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800597c9  xor     ebx, ebx
0x1800597cb  lea     rcx, [rsp+1F0h+var_190]; this
0x1800597d0  call    ??1CLogonController_InformLogonUI_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLogonController_InformLogonUI_Activity::~CLogonController_InformLogonUI_Activity(void)
0x1800597d5  mov     eax, ebx
0x1800597d7  mov     rcx, [rbp+0F0h+var_40]
0x1800597de  xor     rcx, rsp; StackCookie
0x1800597e1  call    __security_check_cookie
0x1800597e6  add     rsp, 1C0h
0x1800597ed  pop     r15
0x1800597ef  pop     r14
0x1800597f1  pop     r12
0x1800597f3  pop     rdi
0x1800597f4  pop     rsi
0x1800597f5  pop     rbx
0x1800597f6  pop     rbp
0x1800597f7  retn
0x1800597f8  mov     rcx, rsi; this
0x1800597fb  call    ?_EnsureSoundPlayer@CLogonController@@AEAAJXZ; CLogonController::_EnsureSoundPlayer(void)
0x180059800  mov     ebx, eax
0x180059802  test    eax, eax
0x180059804  jns     short loc_180059810
0x180059806  mov     edx, 7B1h
0x18005980b  jmp     loc_18005966D
0x180059810  test    r15b, r15b
0x180059813  jz      short loc_1800597BD
0x180059815  xor     edx, edx
0x180059817  cmp     r14d, 5
0x18005981b  setz    dl
0x18005981e  mov     rcx, [rdi+180h]
0x180059825  call    ?StartLogoffSound@LogonSound@@QEAAJW4SoundScenario@@@Z; LogonSound::StartLogoffSound(SoundScenario)
0x18005982a  mov     ebx, eax
0x18005982c  test    eax, eax
0x18005982e  jns     short loc_1800597BD
0x180059830  mov     edx, 7B4h
0x180059835  jmp     loc_18005966D
0x18005983a  mov     edx, 1
0x18005983f  mov     rcx, [rdi+70h]
0x180059843  call    ?ShouldHideAutoLogonUI@CProcessStateManager@@QEAA_NW4CacheBehavior@1@@Z; CProcessStateManager::ShouldHideAutoLogonUI(CProcessStateManager::CacheBehavior)
0x180059848  test    al, al
0x18005984a  jz      short loc_180059864
0x18005984c  mov     rcx, rsi; this
0x18005984f  call    ?_HideLogonUI@CLogonController@@AEAAJXZ; CLogonController::_HideLogonUI(void)
0x180059854  mov     ebx, eax
0x180059856  test    eax, eax
0x180059858  jns     short loc_180059864
0x18005985a  mov     edx, 7A7h
0x18005985f  jmp     loc_18005966D
0x180059864  mov     rcx, rsi; this
0x180059867  call    ?_EnsureSoundPlayer@CLogonController@@AEAAJXZ; CLogonController::_EnsureSoundPlayer(void)
0x18005986c  mov     ebx, eax
0x18005986e  test    eax, eax
0x180059870  jns     short loc_18005987C
0x180059872  mov     edx, 7ABh
0x180059877  jmp     loc_18005966D
0x18005987c  mov     rdx, [rdi+90h]; struct IInspectable *
0x180059883  mov     rcx, [rdi+180h]; this
0x18005988a  call    ?PlayLogonSoundIfNecessary@LogonSound@@QEAAJPEAUIInspectable@@@Z; LogonSound::PlayLogonSoundIfNecessary(IInspectable *)
0x18005988f  mov     rcx, [rbp+0F8h]; this
0x180059896  test    eax, eax
0x180059898  jns     loc_1800597BD
0x18005989e  mov     r9d, eax; char *
0x1800598a1  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800598a8  mov     edx, 7ACh; void *
0x1800598ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800598b2  jmp     loc_1800597BD
0x1800598b7  mov     rcx, [rdi+90h]
0x1800598be  add     rcx, 8
0x1800598c2  mov     rax, [rcx]
0x1800598c5  mov     rax, [rax+48h]
0x1800598c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598ce  mov     rcx, [rdi+70h]; this
0x1800598d2  call    ?ResetIsBoot@CProcessStateManager@@QEAAXXZ; CProcessStateManager::ResetIsBoot(void)
0x1800598d7  cmp     qword ptr [rdi+180h], 0
0x1800598df  jz      short loc_180059916
0x1800598e1  lea     r8, aLogonuichecked; "LogonUIChecked"
0x1800598e8  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800598ef  mov     rbx, 0FFFFFFFF80000002h
0x1800598f6  mov     rcx, rbx; hkey
0x1800598f9  call    cs:__imp_SHDeleteValueW
0x1800598ff  lea     r8, aSoundplayed; "SoundPlayed"
0x180059906  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005990d  mov     rcx, rbx; hkey
0x180059910  call    cs:__imp_SHDeleteValueW
0x180059916  mov     rcx, [rdi+70h]
0x18005991a  add     rcx, 10h
0x18005991e  mov     rax, [rcx]
0x180059921  mov     dl, 1
0x180059923  mov     rax, [rax+90h]
0x18005992a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005992f  mov     ebx, eax
0x180059931  test    eax, eax
0x180059933  jns     short loc_18005993F
0x180059935  mov     edx, 799h
0x18005993a  jmp     loc_18005966D
0x18005993f  mov     rcx, rsi; this
0x180059942  call    ?_HideLogonUI@CLogonController@@AEAAJXZ; CLogonController::_HideLogonUI(void)
0x180059947  mov     ebx, eax
0x180059949  test    eax, eax
0x18005994b  jns     loc_1800597BD
0x180059951  mov     edx, 79Bh
0x180059956  jmp     loc_18005966D
0x18005995b  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x180059960  test    al, al
0x180059962  jz      loc_1800597BD
0x180059968  cmp     dword ptr [rdi+108h], 5
0x18005996f  jnz     loc_1800597BD
0x180059975  mov     [rsp+1F0h+var_1A8], 0
0x18005997d  lea     r9, [rsp+1F0h+var_1A8]; unsigned int *
0x180059982  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x180059989  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180059990  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180059997  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18005999c  cmp     [rsp+1F0h+var_1A8], 2
0x1800599a1  jnz     loc_1800597BD
0x1800599a7  mov     [rsp+1F0h+var_1B0], 0
0x1800599ac  mov     rcx, [rdi+70h]
0x1800599b0  add     rcx, 10h
0x1800599b4  mov     rax, [rcx]
0x1800599b7  lea     rdx, [rsp+1F0h+var_1B0]
0x1800599bc  mov     rax, [rax+0E0h]
0x1800599c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599c8  mov     ebx, eax
0x1800599ca  test    eax, eax
0x1800599cc  jns     short loc_1800599D8
0x1800599ce  mov     edx, 7C6h
0x1800599d3  jmp     loc_18005966D
0x1800599d8  cmp     [rsp+1F0h+var_1B0], 0
0x1800599dd  jnz     loc_1800597BD
0x1800599e3  mov     rcx, rsi; this
0x1800599e6  call    ?_HideLogonUI@CLogonController@@AEAAJXZ; CLogonController::_HideLogonUI(void)
0x1800599eb  mov     ebx, eax
0x1800599ed  test    eax, eax
0x1800599ef  jns     loc_1800597BD
0x1800599f5  mov     edx, 7C9h
0x1800599fa  jmp     loc_18005966D
```
