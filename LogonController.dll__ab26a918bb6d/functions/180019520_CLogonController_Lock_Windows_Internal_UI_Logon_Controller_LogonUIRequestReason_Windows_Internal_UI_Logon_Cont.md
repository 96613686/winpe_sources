# CLogonController::_Lock(Windows::Internal::UI::Logon::Controller::LogonUIRequestReason,Windows::Internal::UI::Logon::Controller::LockOptions,bool,bool,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool *)

- ea: `0x180019520`
- end: `0x18001a31e`
- name: `?_Lock@CLogonController@@AEAAJW4LogonUIRequestReason@Controller@Logon@UI@Internal@Windows@@W4LockOptions@34567@_N2PEBG3333PEA_N@Z`
- size: `3582`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180023c60`
- `0x180024320`
- `0x180024690`

## callees

- `0x18000df10`
- `0x18000e750`
- `0x1800117c4`
- `0x180015920`
- `0x180019330`
- `0x180019520`
- `0x18001a324`
- `0x18001a4cc`
- `0x18001a83c`
- `0x18002e564`
- `0x180044f68`
- `0x18004ae38`
- `0x18005d488`
- `0x18006c000`
- `0x180073bc8`
- `0x180074364`
- `0x18007460c`
- `0x18009d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800196ce`
- `KERNEL32!RaiseException` at `0x180019729`
- `KERNEL32!RaiseException` at `0x180019786`
- `KERNEL32!RaiseException` at `0x1800197eb`
- `KERNEL32!RaiseException` at `0x180019999`
- `KERNEL32!RaiseException` at `0x1800199ad`
- `KERNEL32!RaiseException` at `0x1800199c1`
- `KERNEL32!RaiseException` at `0x1800199d5`
- `KERNEL32!RaiseException` at `0x180019e70`
- `KERNEL32!RaiseException` at `0x180019f0c`
- `KERNEL32!RaiseException` at `0x1800196ce`
- `KERNEL32!RaiseException` at `0x180019729`
- `KERNEL32!RaiseException` at `0x180019786`
- `KERNEL32!RaiseException` at `0x1800197eb`
- `KERNEL32!RaiseException` at `0x180019999`
- `KERNEL32!RaiseException` at `0x1800199ad`
- `KERNEL32!RaiseException` at `0x1800199c1`
- `KERNEL32!RaiseException` at `0x1800199d5`
- `KERNEL32!RaiseException` at `0x180019e70`
- `KERNEL32!RaiseException` at `0x180019f0c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001963b`
- `KERNEL32!ReleaseSRWLockShared` at `0x180019a48`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001963b`
- `KERNEL32!ReleaseSRWLockShared` at `0x180019a48`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019981`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019a36`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019cfe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019e55`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a04c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019981`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019a36`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019cfe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180019e55`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a04c`
- `KERNEL32!AcquireSRWLockShared` at `0x1800195ee`
- `KERNEL32!AcquireSRWLockShared` at `0x1800199e6`
- `KERNEL32!AcquireSRWLockShared` at `0x1800195ee`
- `KERNEL32!AcquireSRWLockShared` at `0x1800199e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001987e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019a20`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019c56`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019ce0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001987e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019a20`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019c56`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800196dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001973c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019a99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800196dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001973c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019a99`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CLogonController::_Lock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 a4,
        char a5,
        HSTRING sourceString,
        const WCHAR *a7,
        PCWSTR a8,
        unsigned __int64 a9,
        const WCHAR *a10,
        _BYTE *a11)
{
  char v11; // si
  const WCHAR *v13; // r15
  int v16; // eax
  unsigned int v17; // ebx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v18; // rbx
  const WCHAR *v19; // rsi
  int v20; // eax
  const WCHAR *v21; // rcx
  unsigned __int64 v22; // rdx
  HRESULT v23; // eax
  const WCHAR *v24; // rcx
  unsigned __int64 v25; // rdx
  HRESULT v26; // eax
  const WCHAR *v27; // rcx
  unsigned __int64 v28; // rdx
  int v29; // edi
  HRESULT v30; // eax
  unsigned __int64 v31; // rdx
  HSTRING v32; // rbx
  HRESULT v33; // eax
  int v34; // eax
  __int64 v35; // rax
  bool v36; // bl
  int active; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v39; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v40; // rcx
  unsigned int v41; // r15d
  char v42; // di
  unsigned int v43; // eax
  HRESULT v44; // eax
  char v45; // cl
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v46; // rbx
  void (__fastcall *v47)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, GUID *, struct Windows::Internal::UI::Logon::Controller::ILogonUX **); // rdi
  char v48; // r15
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v49; // rcx
  int v50; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v51; // rbx
  __int64 v52; // rdi
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v53; // r14
  int v54; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v55; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v56; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v57; // rcx
  __int64 v58; // rbx
  unsigned int v59; // edi
  char v60; // r12
  int v61; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v62; // rbx
  __int64 (__fastcall *v63)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, GUID *, struct Windows::Internal::UI::Logon::Controller::ILogonUX **); // rdi
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  int updated; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v68; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v69; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v70; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v71; // rcx
  __int64 v72; // rdx
  int v73; // eax
  int v74; // eax
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v75; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v76; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v77; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v78; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v79; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v80; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v81; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v82; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v83; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v84; // rcx
  __int64 (__fastcall *v85)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, HSTRING, __int64 *); // rbx
  int v86; // eax
  int v87; // [rsp+20h] [rbp-E0h]
  int v88; // [rsp+20h] [rbp-E0h]
  int v89; // [rsp+20h] [rbp-E0h]
  int v90; // [rsp+20h] [rbp-E0h]
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v91; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v92; // [rsp+58h] [rbp-A8h] BYREF
  char v93; // [rsp+60h] [rbp-A0h] BYREF
  char v94; // [rsp+61h] [rbp-9Fh]
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v95; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v96; // [rsp+70h] [rbp-90h]
  unsigned int v97; // [rsp+74h] [rbp-8Ch]
  __int64 v98; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v99; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v100; // [rsp+88h] [rbp-78h] BYREF
  char v101; // [rsp+90h] [rbp-70h]
  __int64 v102; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v103; // [rsp+A0h] [rbp-60h]
  int v104; // [rsp+A4h] [rbp-5Ch]
  PCWSTR v105; // [rsp+A8h] [rbp-58h]
  PCWSTR v106; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER v107; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v108; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER v111; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v112; // [rsp+110h] [rbp+10h] BYREF
  HSTRING_HEADER v113; // [rsp+118h] [rbp+18h] BYREF
  HSTRING v114; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v96 = a4;
  v11 = a3;
  v97 = a3;
  v103 = a2;
  v106 = a7;
  v13 = a8;
  v100 = (WCHAR *)a8;
  v105 = a10;
  v104 = 0;
  *a11 = 0;
  CLogonController::_CancelPowerTransition((CLogonController *)a1);
  v93 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 16LL) + 136LL))(
          *(_QWORD *)(a1 + 144) + 16LL,
          &v93);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF1,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v16,
      v87);
    return v17;
  }
  if ( !v93 && (v11 & 4) == 0 )
  {
    *a11 = 1;
    return 0;
  }
  v91 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 344));
  v18 = *(struct Windows::Internal::UI::Logon::Controller::ILogonUX **)(a1 + 360);
  if ( v18 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*(_QWORD *)(a1 + 360));
    v91 = v18;
  }
  if ( a1 != -344 )
    ReleaseSRWLockShared((PSRWLOCK)(a1 + 344));
  v19 = &::sourceString;
  if ( v91 )
    goto LABEL_58;
  while ( 1 )
  {
    v20 = CLogonController::_EnsureLockHost((CLogonController *)a1);
    v17 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1D,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v20,
        v87);
      goto LABEL_47;
    }
    v94 = 0;
    v95 = 0;
    v100 = *(WCHAR **)(a1 + 400);
    v102 = *(_QWORD *)v100;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v95);
    v21 = v19;
    if ( sourceString )
      v21 = (const WCHAR *)sourceString;
    string = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( v22 > 0xFFFFFFFF || (int)v22 + 1 < (unsigned int)v22 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v23 = WindowsCreateStringReference(v21, v22, &hstringHeader, &string);
    if ( v23 >= 0 )
      break;
    RaiseException(v23, 1u, 0, 0);
LABEL_55:
    RaiseException(v26, 1u, 0, 0);
LABEL_56:
    RaiseException(v30, 1u, 0, 0);
LABEL_57:
    RaiseException(v33, 1u, 0, 0);
LABEL_58:
    AcquireSRWLockShared((PSRWLOCK)(a1 + 288));
    v41 = *(_DWORD *)(a1 + 296);
    v42 = *(_BYTE *)(a1 + 303);
    if ( a1 != -288 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 288));
    if ( !v42 || (v97 & 1) != 0 )
    {
      v102 = 0;
      v85 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v91 + 104LL);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v102);
      v108 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v107, v19, 1u, 0);
      v86 = v85(v91, v41, v108, &v102);
      v17 = v86;
      if ( v86 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB19,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v86,
          v87);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v102);
        goto LABEL_47;
      }
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v102);
    }
    else
    {
      v97 |= 0x80u;
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 288));
      *(_BYTE *)(a1 + 303) = 0;
      if ( a1 != -288 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 288));
    }
    v13 = v100;
  }
  v24 = v19;
  if ( a9 )
    v24 = (const WCHAR *)a9;
  v112 = 0;
  a9 = -1;
  v25 = -1;
  do
    ++v25;
  while ( v24[v25] );
  if ( v25 > 0xFFFFFFFF || (int)v25 + 1 < (unsigned int)v25 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  sourceString = string;
  v26 = WindowsCreateStringReference(v24, v25, &v111, &v112);
  if ( v26 < 0 )
    goto LABEL_55;
  v27 = v19;
  if ( v13 )
    v27 = v13;
  v114 = 0;
  v28 = -1;
  do
    ++v28;
  while ( v27[v28] );
  if ( v28 > 0xFFFFFFFF || (int)v28 + 1 < (unsigned int)v28 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v29 = (int)v112;
  v30 = WindowsCreateStringReference(v27, v28, &v113, &v114);
  if ( v30 < 0 )
    goto LABEL_56;
  if ( v106 )
    v19 = v106;
  v108 = 0;
  v31 = -1;
  do
    ++v31;
  while ( v19[v31] );
  if ( v31 > 0xFFFFFFFF || (int)v31 + 1 < (unsigned int)v31 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v32 = v114;
  v33 = WindowsCreateStringReference(v19, v31, &v107, &v108);
  if ( v33 < 0 )
    goto LABEL_57;
  v88 = v29;
  v34 = (*(__int64 (__fastcall **)(WCHAR *, _QWORD, HSTRING, HSTRING))(v102 + 56))(v100, v97, v108, v32);
  v17 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB28,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v34,
      v29);
    v39 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v17;
  }
  v35 = lambda_7a58db99057318a0bceccc61c358fce7_::_lambda_7a58db99057318a0bceccc61c358fce7_(&v106, a1);
  wil::ScopeExit__lambda_7a58db99057318a0bceccc61c358fce7___(&v100, v35);
  v36 = v94 != 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 248));
  active = CLogonController::_SetLockScreenActiveLockHeld((CLogonController *)a1, 1, v36, 0);
  v17 = active;
  if ( active < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCA,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)active,
      v29);
    if ( a1 != -248 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 248));
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB33,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)v17,
      v89);
    goto LABEL_46;
  }
  if ( a1 != -248 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 248));
  v98 = 0;
  v92 = 0;
  v46 = v95;
  v47 = **(void (__fastcall ***)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, GUID *, struct Windows::Internal::UI::Logon::Controller::ILogonUX **))v95;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v92);
  v47(v46, &GUID_c1dee830_94c1_488c_82d0_3332c15a6f2d, &v92);
  hstringHeader.Reserved.Reserved1 = &v92;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v98;
  v48 = 1;
  hstringHeader.Reserved.Reserved2[16] = 1;
  if ( v92 )
  {
    v72 = a1 + 56;
    if ( !a1 )
      v72 = 0;
    v73 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, __int64, __int64 *))(*(_QWORD *)v92 + 128LL))(
            v92,
            v72,
            &v98);
    v17 = v73;
    if ( v73 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB42,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v73,
        v88);
      if ( v92 && v98 )
        (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v92);
LABEL_46:
      wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v95);
LABEL_47:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
      return v17;
    }
  }
  v49 = v91;
  if ( v91 )
  {
    v91 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = CLogonController::_EnsureLogonUX((CLogonController *)a1, &v91);
  v17 = v50;
  if ( v50 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB45,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v50,
      v88);
    if ( !v92 || !v98 )
      goto LABEL_148;
LABEL_167:
    (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
LABEL_148:
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v92);
    goto LABEL_46;
  }
  v45 = v97;
  if ( (v97 & 0x20) != 0 )
    goto LABEL_77;
  v74 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v95 + 56LL))(v95);
  v17 = v74;
  if ( v74 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4D,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v74,
      v88);
    v79 = v92;
    if ( v92 && v98 )
    {
      (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
      v79 = v92;
    }
    if ( v79 )
    {
      v92 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v79 + 16LL))(v79);
    }
    wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
    v80 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v80 + 16LL))(v80);
    }
    v81 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v81 + 16LL))(v81);
    }
    return v17;
  }
  v45 = v97;
LABEL_77:
  v51 = v91;
  v52 = *(_QWORD *)v91;
  v53 = v95;
  if ( v105 )
  {
    v108 = 0;
    do
      ++a9;
    while ( v105[a9] );
    if ( a9 <= 0xFFFFFFFF )
    {
      v43 = Microsoft::WRL::Wrappers::HStringReference::AddOne(a9);
      if ( (unsigned int)a9 >= v43 )
        LODWORD(a9) = v43 - 1;
      v44 = WindowsCreateStringReference(v105, a9, &v107, &v108);
      if ( v44 < 0 )
      {
        RaiseException(v44, 1u, 0, 0);
        __debugbreak();
      }
      v104 = 1;
      v45 = v97;
      goto LABEL_78;
    }
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_118;
  }
LABEL_78:
  LOBYTE(v88) = a5;
  v54 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, _QWORD, bool))(v52 + 64))(
          v51,
          v103,
          v96,
          (v45 & 0x40) != 0);
  v17 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB50,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v54,
      v88);
    v55 = v92;
    if ( v92 && v98 )
    {
      (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
      v55 = v92;
    }
    if ( v55 )
    {
      v92 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v55 + 16LL))(v55);
    }
    wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
    v56 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v57 + 16LL))(v57);
    }
    return v17;
  }
  v58 = *(_QWORD *)(a1 + 144);
  AcquireSRWLockExclusive((PSRWLOCK)(v58 + 504));
  v59 = *(_DWORD *)(v58 + 512);
  if ( (v59 & 0x80u) != 0 )
  {
    v60 = 0;
  }
  else
  {
    v59 ^= 0x80u;
    *(_DWORD *)(v58 + 512) = v59;
    v60 = 1;
  }
  if ( v58 != -504 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v58 + 504));
  if ( v60 )
  {
    v61 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(
            v58 + 480,
            v58,
            v59);
    v17 = v61;
    if ( v61 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55E,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)v61,
        v88);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB52,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)v17,
        v90);
      v82 = v92;
      if ( v92 && v98 )
      {
        (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
        v82 = v92;
      }
      if ( v82 )
      {
        v92 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v82 + 16LL))(v82);
      }
      wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
      v83 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v83 + 16LL))(v83);
      }
      v84 = v91;
      if ( v91 )
      {
        v91 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v84 + 16LL))(v84);
      }
      return v17;
    }
  }
  v53 = 0;
  v99 = 0;
  v62 = v95;
  v63 = **(__int64 (__fastcall ***)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, GUID *, struct Windows::Internal::UI::Logon::Controller::ILogonUX **))v95;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v99);
  v64 = v63(v62, &GUID_3e1fe603_f897_5263_b328_0806426b8a79, &v99);
  v17 = v64;
  if ( v64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB55,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v64,
      v88);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v99);
    if ( !v92 || !v98 )
      goto LABEL_148;
    goto LABEL_167;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 248));
  if ( !*(_QWORD *)(a1 + 256) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=(a1 + 256, &v99);
    *(_QWORD *)(a1 + 280) = v98;
    v101 = 0;
    v48 = 0;
    hstringHeader.Reserved.Reserved2[16] = 0;
  }
  if ( a1 != -248 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 248));
  LOBYTE(v66) = v103 == 1;
  updated = CProcessStateManager::UpdateLockScreenState(*(_QWORD *)(a1 + 144), v65, v66);
  v17 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB64,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)updated,
      v88);
    v68 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v68 + 16LL))(v68);
    }
    if ( v48 && v92 && v98 )
      (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
    v69 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v69 + 16LL))(v69);
    }
    wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
    v70 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v71 + 16LL))(v71);
    }
    return v17;
  }
LABEL_118:
  v75 = v99;
  if ( v99 )
  {
    v99 = v53;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v75 + 16LL))(v75);
  }
  if ( v48 && v92 && v98 )
    (*(void (**)(void))(*(_QWORD *)v92 + 136LL))();
  v76 = v92;
  if ( v92 )
  {
    v92 = v53;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v76 + 16LL))(v76);
  }
  wil::details::ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___::_ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___(&v100);
  v77 = v95;
  if ( v95 )
  {
    v95 = v53;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v77 + 16LL))(v77);
  }
  v78 = v91;
  if ( v91 )
  {
    v91 = v53;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v78 + 16LL))(v78);
  }
  return 0;
}

```

## disassembly

```asm
0x180019520  push    rbp
0x180019522  push    rbx
0x180019523  push    rsi
0x180019524  push    rdi
0x180019525  push    r12
0x180019527  push    r13
0x180019529  push    r14
0x18001952b  push    r15
0x18001952d  lea     rbp, [rsp-48h]
0x180019532  sub     rsp, 148h
0x180019539  mov     rax, cs:__security_cookie
0x180019540  xor     rax, rsp
0x180019543  mov     [rbp+80h+var_48], rax
0x180019547  mov     [rsp+180h+var_110], r9b
0x18001954c  mov     esi, r8d
0x18001954f  mov     [rsp+180h+var_10C], r8d
0x180019554  mov     [rbp+80h+var_E0], edx
0x180019557  mov     r13, rcx
0x18001955a  mov     rax, [rbp+80h+arg_30]
0x180019561  mov     [rbp+80h+var_D0], rax
0x180019565  mov     r15, [rbp+80h+arg_38]
0x18001956c  mov     [rbp+80h+var_F8], r15
0x180019570  mov     r12, [rbp+80h+arg_40]
0x180019577  mov     r14, [rbp+80h+sourceString]
0x18001957e  mov     rcx, [rbp+80h+arg_48]
0x180019585  mov     [rbp+80h+var_D8], rcx
0x180019589  mov     rdi, [rbp+80h+arg_50]
0x180019590  mov     [rbp+80h+var_DC], 0
0x180019597  mov     byte ptr [rdi], 0
0x18001959a  mov     rcx, r13; this
0x18001959d  call    ?_CancelPowerTransition@CLogonController@@AEAAXXZ; CLogonController::_CancelPowerTransition(void)
0x1800195a2  mov     [rsp+180h+var_120], 0
0x1800195a7  mov     rcx, [r13+90h]
0x1800195ae  add     rcx, 10h
0x1800195b2  mov     rax, [rcx]
0x1800195b5  lea     rdx, [rsp+180h+var_120]
0x1800195ba  mov     rax, [rax+88h]
0x1800195c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195c6  mov     ebx, eax
0x1800195c8  test    eax, eax
0x1800195ca  js      loc_18001A133
0x1800195d0  cmp     [rsp+180h+var_120], 0
0x1800195d5  jz      loc_18001A153
0x1800195db  mov     [rsp+180h+var_130], 0
0x1800195e4  lea     rdi, [r13+158h]
0x1800195eb  mov     rcx, rdi; SRWLock
0x1800195ee  call    cs:__imp_AcquireSRWLockShared
0x1800195f4  mov     rbx, [r13+168h]
0x1800195fb  cmp     [rsp+180h+var_130], rbx
0x180019600  jz      short loc_180019633
0x180019602  test    rbx, rbx
0x180019605  jz      short loc_180019617
0x180019607  mov     rax, [rbx]
0x18001960a  mov     rcx, rbx
0x18001960d  mov     rax, [rax+8]
0x180019611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019616  nop
0x180019617  mov     rcx, [rsp+180h+var_130]
0x18001961c  mov     [rsp+180h+var_130], rbx
0x180019621  test    rcx, rcx
0x180019624  jz      short loc_180019633
0x180019626  mov     rax, [rcx]
0x180019629  mov     rax, [rax+10h]
0x18001962d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019632  nop
0x180019633  test    rdi, rdi
0x180019636  jz      short loc_180019641
0x180019638  mov     rcx, rdi; SRWLock
0x18001963b  call    cs:__imp_ReleaseSRWLockShared
0x180019641  lea     rsi, sourceString
0x180019648  cmp     [rsp+180h+var_130], 0
0x18001964e  jnz     loc_1800199DC
0x180019654  mov     rcx, r13; this
0x180019657  call    ?_EnsureLockHost@CLogonController@@AEAAJXZ; CLogonController::_EnsureLockHost(void)
0x18001965c  mov     ebx, eax
0x18001965e  test    eax, eax
0x180019660  js      loc_18001A1F4
0x180019666  mov     [rsp+180h+var_11F], 0
0x18001966b  xor     ebx, ebx
0x18001966d  mov     [rsp+180h+var_118], rbx
0x180019672  mov     rax, [r13+190h]
0x180019679  mov     [rbp+80h+var_F8], rax
0x18001967d  mov     rax, [rax]
0x180019680  mov     [rbp+80h+var_E8], rax
0x180019684  lea     rcx, [rsp+180h+var_118]
0x180019689  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18001968e  mov     rcx, rsi
0x180019691  test    r14, r14
0x180019694  cmovnz  rcx, r14; sourceString
0x180019698  mov     [rbp+80h+string], rbx
0x18001969c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800196a3  inc     rdx; length
0x1800196a6  cmp     word ptr [rcx+rdx*2], 0
0x1800196ab  jnz     short loc_1800196A3
0x1800196ad  mov     edi, 0FFFFFFFFh
0x1800196b2  cmp     rdx, rdi
0x1800196b5  ja      short loc_1800196BE
0x1800196b7  lea     eax, [rdx+1]
0x1800196ba  cmp     eax, edx
0x1800196bc  jnb     short loc_1800196D5
0x1800196be  xor     r9d, r9d; lpArguments
0x1800196c1  xor     r8d, r8d; nNumberOfArguments
0x1800196c4  mov     edx, 1; dwExceptionFlags
0x1800196c9  mov     ecx, 80070216h; dwExceptionCode
0x1800196ce  call    cs:__imp_RaiseException
0x1800196d4  int     3; Trap to Debugger
0x1800196d5  lea     r9, [rbp+80h+string]; string
0x1800196d9  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x1800196dd  call    cs:__imp_WindowsCreateStringReference
0x1800196e3  test    eax, eax
0x1800196e5  js      loc_18001998C
0x1800196eb  mov     rcx, rsi
0x1800196ee  test    r12, r12
0x1800196f1  cmovnz  rcx, r12; sourceString
0x1800196f5  mov     [rbp+80h+var_70], rbx
0x1800196f9  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180019700  mov     rdx, r12
0x180019703  inc     rdx; length
0x180019706  cmp     word ptr [rcx+rdx*2], 0
0x18001970b  jnz     short loc_180019703
0x18001970d  cmp     rdx, rdi
0x180019710  ja      short loc_180019719
0x180019712  lea     eax, [rdx+1]
0x180019715  cmp     eax, edx
0x180019717  jnb     short loc_180019730
0x180019719  xor     r9d, r9d; lpArguments
0x18001971c  xor     r8d, r8d; nNumberOfArguments
0x18001971f  mov     edx, 1; dwExceptionFlags
0x180019724  mov     ecx, 80070216h; dwExceptionCode
0x180019729  call    cs:__imp_RaiseException
0x18001972f  int     3; Trap to Debugger
0x180019730  mov     r14, [rbp+80h+string]
0x180019734  lea     r9, [rbp+80h+var_70]; string
0x180019738  lea     r8, [rbp+80h+var_88]; hstringHeader
0x18001973c  call    cs:__imp_WindowsCreateStringReference
0x180019742  test    eax, eax
0x180019744  js      loc_1800199A0
0x18001974a  mov     rcx, rsi
0x18001974d  test    r15, r15
0x180019750  cmovnz  rcx, r15; sourceString
0x180019754  mov     [rbp+80h+var_50], rbx
0x180019758  mov     rdx, r12
0x18001975b  nop     dword ptr [rax+rax+00h]
0x180019760  inc     rdx; length
0x180019763  cmp     word ptr [rcx+rdx*2], 0
0x180019768  jnz     short loc_180019760
0x18001976a  cmp     rdx, rdi
0x18001976d  ja      short loc_180019776
0x18001976f  lea     eax, [rdx+1]
0x180019772  cmp     eax, edx
0x180019774  jnb     short loc_18001978D
0x180019776  xor     r9d, r9d; lpArguments
0x180019779  xor     r8d, r8d; nNumberOfArguments
0x18001977c  mov     edx, 1; dwExceptionFlags
0x180019781  mov     ecx, 80070216h; dwExceptionCode
0x180019786  call    cs:__imp_RaiseException
0x18001978c  int     3; Trap to Debugger
0x18001978d  mov     rdi, [rbp+80h+var_70]
0x180019791  lea     r9, [rbp+80h+var_50]; string
0x180019795  lea     r8, [rbp+80h+var_68]; hstringHeader
0x180019799  call    cs:__imp_WindowsCreateStringReference
0x18001979f  test    eax, eax
0x1800197a1  js      loc_1800199B4
0x1800197a7  mov     rax, [rbp+80h+var_D0]
0x1800197ab  test    rax, rax
0x1800197ae  cmovnz  rsi, rax
0x1800197b2  mov     [rbp+80h+var_B0], rbx
0x1800197b6  mov     rdx, r12
0x1800197b9  nop     dword ptr [rax+00000000h]
0x1800197c0  inc     rdx; length
0x1800197c3  cmp     word ptr [rsi+rdx*2], 0
0x1800197c8  jnz     short loc_1800197C0
0x1800197ca  mov     eax, 0FFFFFFFFh
0x1800197cf  cmp     rdx, rax
0x1800197d2  ja      short loc_1800197DB
0x1800197d4  lea     eax, [rdx+1]
0x1800197d7  cmp     eax, edx
0x1800197d9  jnb     short loc_1800197F2
0x1800197db  xor     r9d, r9d; lpArguments
0x1800197de  xor     r8d, r8d; nNumberOfArguments
0x1800197e1  mov     edx, 1; dwExceptionFlags
0x1800197e6  mov     ecx, 80070216h; dwExceptionCode
0x1800197eb  call    cs:__imp_RaiseException
0x1800197f1  int     3; Trap to Debugger
0x1800197f2  mov     rbx, [rbp+80h+var_50]
0x1800197f6  lea     r9, [rbp+80h+var_B0]; string
0x1800197fa  lea     r8, [rbp+80h+var_C8]; hstringHeader
0x1800197fe  mov     rcx, rsi; sourceString
0x180019801  call    cs:__imp_WindowsCreateStringReference
0x180019807  test    eax, eax
0x180019809  js      loc_1800199C8
0x18001980f  lea     rax, [rsp+180h+var_118]
0x180019814  mov     [rsp+180h+var_148], rax
0x180019819  lea     rax, [rsp+180h+var_11F]
0x18001981e  mov     [rsp+180h+var_150], rax
0x180019823  mov     [rsp+180h+var_158], r14
0x180019828  mov     qword ptr [rsp+180h+var_160], rdi; int
0x18001982d  mov     r9, rbx
0x180019830  mov     r8, [rbp+80h+var_B0]
0x180019834  mov     edx, [rsp+180h+var_10C]
0x180019838  mov     rcx, [rbp+80h+var_F8]
0x18001983c  mov     rax, [rbp+80h+var_E8]
0x180019840  mov     rax, [rax+38h]
0x180019844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019849  mov     ebx, eax
0x18001984b  test    eax, eax
0x18001984d  js      loc_180019920
0x180019853  mov     rdx, r13
0x180019856  lea     rcx, [rbp+80h+var_D0]
0x18001985a  call    _lambda_7a58db99057318a0bceccc61c358fce7____lambda_7a58db99057318a0bceccc61c358fce7_
0x18001985f  mov     rdx, rax
0x180019862  lea     rcx, [rbp+80h+var_F8]
0x180019866  call    wil__ScopeExit__lambda_7a58db99057318a0bceccc61c358fce7___
0x18001986b  nop
0x18001986c  cmp     [rsp+180h+var_11F], 0
0x180019871  setnz   bl
0x180019874  lea     rsi, [r13+0F8h]
0x18001987b  mov     rcx, rsi; SRWLock
0x18001987e  call    cs:__imp_AcquireSRWLockExclusive
0x180019884  xor     r9d, r9d; bool
0x180019887  movzx   r8d, bl; bool
0x18001988b  mov     dl, 1; bool
0x18001988d  mov     rcx, r13; this
0x180019890  call    ?_SetLockScreenActiveLockHeld@CLogonController@@AEAAJ_N00@Z; CLogonController::_SetLockScreenActiveLockHeld(bool,bool,bool)
0x180019895  mov     ebx, eax
0x180019897  test    eax, eax
0x180019899  jns     loc_18001A040
0x18001989f  mov     rcx, [rbp+88h]; this
0x1800198a6  mov     r9d, eax; char *
0x1800198a9  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800198b0  mov     edx, 0BCAh; void *
0x1800198b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198ba  test    rsi, rsi
0x1800198bd  jnz     loc_18001997E
0x1800198c3  mov     rcx, [rbp+88h]; this
0x1800198ca  mov     r9d, ebx; char *
0x1800198cd  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800198d4  mov     edx, 0B33h; void *
0x1800198d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198de  nop
0x1800198df  lea     rcx, [rbp+80h+var_F8]
0x1800198e3  call    wil__details__ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf______ScopeExitFn__lambda_0836191a2a8656f449a808cf41abc1bf___
0x1800198e8  nop
0x1800198e9  lea     rcx, [rsp+180h+var_118]
0x1800198ee  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800198f3  nop
0x1800198f4  lea     rcx, [rsp+180h+var_130]
0x1800198f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800198fe  mov     eax, ebx
0x180019900  mov     rcx, [rbp+80h+var_48]
0x180019904  xor     rcx, rsp; StackCookie
0x180019907  call    __security_check_cookie
0x18001990c  add     rsp, 148h
0x180019913  pop     r15
0x180019915  pop     r14
0x180019917  pop     r13
0x180019919  pop     r12
0x18001991b  pop     rdi
0x18001991c  pop     rsi
0x18001991d  pop     rbx
0x18001991e  pop     rbp
0x18001991f  retn
0x180019920  mov     rcx, [rbp+88h]; this
0x180019927  mov     r9d, ebx; char *
0x18001992a  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180019931  mov     edx, 0B28h; void *
0x180019936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001993b  nop
0x18001993c  mov     rcx, [rsp+180h+var_118]
0x180019941  test    rcx, rcx
0x180019944  jz      short loc_18001995C
0x180019946  mov     [rsp+180h+var_118], 0
0x18001994f  mov     rax, [rcx]
0x180019952  mov     rax, [rax+10h]
0x180019956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001995b  nop
0x18001995c  mov     rcx, [rsp+180h+var_130]
0x180019961  test    rcx, rcx
0x180019964  jz      short loc_18001997C
0x180019966  mov     [rsp+180h+var_130], 0
0x18001996f  mov     rax, [rcx]
0x180019972  mov     rax, [rax+10h]
0x180019976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001997b  nop
0x18001997c  jmp     short loc_1800198FE
0x18001997e  mov     rcx, rsi; SRWLock
0x180019981  call    cs:__imp_ReleaseSRWLockExclusive
0x180019987  jmp     loc_1800198C3
0x18001998c  xor     r9d, r9d; lpArguments
0x18001998f  xor     r8d, r8d; nNumberOfArguments
0x180019992  mov     edx, 1; dwExceptionFlags
0x180019997  mov     ecx, eax; dwExceptionCode
0x180019999  call    cs:__imp_RaiseException
0x18001999f  nop
0x1800199a0  xor     r9d, r9d; lpArguments
0x1800199a3  xor     r8d, r8d; nNumberOfArguments
0x1800199a6  mov     edx, 1; dwExceptionFlags
0x1800199ab  mov     ecx, eax; dwExceptionCode
0x1800199ad  call    cs:__imp_RaiseException
0x1800199b3  nop
  ... truncated ...
```
