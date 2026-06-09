# RepairServicingStackStateIfNeeded

- ea: `0x180070418`
- end: `0x180070e2a`
- name: `RepairServicingStackStateIfNeeded`
- size: `2578`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069378`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000c468`
- `0x18000f614`
- `0x18000f874`
- `0x180016558`
- `0x18001a810`
- `0x1800296a4`
- `0x180044170`
- `0x180044214`
- `0x1800443e4`
- `0x180045544`
- `0x180045cc4`
- `0x180045e6c`
- `0x18004e028`
- `0x18004e0d4`
- `0x180050278`
- `0x180067094`
- `0x180070418`
- `0x180112e48`
- `0x1801a04ac`
- `0x1801a0654`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070737`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070c3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070737`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070c3f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800709a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800709a5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070c09`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070c09`

## string_xrefs

- `0x18007077f`: `Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x1800709eb`: `Failed to delete registry value: {}`
- `0x18007053f`: `Failed reading Exclusive value from SessionsPending`
- `0x180070478`: `Microsoft\Windows\CurrentVersion\Component Based Servicing\SessionsPending`
- `0x1800704a4`: `Failed getting win32 path to software hive`
- `0x1800707a9`: `Failed getting win32 path to software hive`
- `0x180070847`: `Failed reading PostponeOnlineActions value from CBS key`
- `0x180070614`: `Failed opening SessionsPending key with backup/restore`
- `0x180070938`: `Failed opening CBS key with backup/restore`
- `0x180070b34`: `Failed to change Trusted Installer to an auto start service`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RepairServicingStackStateIfNeeded(__int64 a1)
{
  int Win32RegistryPath; // eax
  unsigned int v3; // r8d
  int v4; // ebx
  __int64 v5; // rdx
  wchar_t *v6; // rsi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rdx
  HKEY v15; // rdi
  int v16; // eax
  int v17; // ebx
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r8d
  int v22; // ebx
  __int64 v23; // rdx
  wchar_t *v24; // rdi
  int v25; // eax
  int v26; // ebx
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // r8d
  int v30; // eax
  int v31; // ebx
  __int64 v32; // rdx
  HKEY v33; // r15
  LSTATUS v34; // ebx
  __int64 v35; // rdx
  unsigned int v36; // eax
  int v37; // eax
  int v38; // ebx
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  int v43; // eax
  HKEY v44; // rbx
  __int64 v45; // rdx
  bool v46; // r13
  __int64 v47; // rdx
  HKEY *p_Handle; // [rsp+20h] [rbp-108h]
  HKEY *v50; // [rsp+20h] [rbp-108h]
  PHKEY v51; // [rsp+20h] [rbp-108h]
  HKEY Handle; // [rsp+68h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+78h] [rbp-B0h] BYREF
  wchar_t *v55; // [rsp+80h] [rbp-A8h] BYREF
  wchar_t *v56; // [rsp+88h] [rbp-A0h] BYREF
  int v57[2]; // [rsp+90h] [rbp-98h] BYREF
  int v58[2]; // [rsp+98h] [rbp-90h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-88h]
  const wchar_t *v60; // [rsp+A8h] [rbp-80h] BYREF
  int v61; // [rsp+B0h] [rbp-78h] BYREF
  int v62; // [rsp+B4h] [rbp-74h] BYREF
  unsigned int v63; // [rsp+B8h] [rbp-70h] BYREF
  unsigned int v64; // [rsp+BCh] [rbp-6Ch] BYREF
  unsigned int v65[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-60h]
  HKEY v67; // [rsp+D0h] [rbp-58h] BYREF
  int v68; // [rsp+D8h] [rbp-50h] BYREF
  const int near *const *v69; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v70; // [rsp+E8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v59 = -2;
  try
  {
    v63 = 0;
    v64 = 0;
    v55 = 0;
    v56 = 0;
    Win32RegistryPath = DeviceContext::GetWin32RegistryPath(
                          a1,
                          0,
                          L"Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\SessionsPending",
                          &v55);
    v4 = Win32RegistryPath;
    if ( Win32RegistryPath < 0 )
    {
      v61 = Win32RegistryPath;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting win32 path to software hive");
        Handle = (HKEY)&v61;
        p_Handle = &Handle;
        LOBYTE(v5) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v5,
          3,
          ": {}");
      }
    }
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x225,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v4,
        (int)p_Handle);
    v6 = v55;
    v7 = CbsRegQueryDWORDValue(HKEY_LOCAL_MACHINE, v55, v3, L"Exclusive", &v63);
    v8 = v7;
    if ( v7 != -2147024894 )
    {
      if ( v7 < 0 )
      {
        v61 = v7;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed reading Exclusive value from SessionsPending");
          Handle = (HKEY)&v61;
          v50 = &Handle;
          LOBYTE(v9) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v9,
            3,
            ": {}");
        }
      }
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x230,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v8,
          (int)v50);
    }
    if ( v63 )
    {
      *(_QWORD *)v65 = 0;
      LOBYTE(v66) = 0;
      hKey = 0;
      v69 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
      v70 = 3;
      v10 = RtlSystemUtil::PrivilegeAcquisition::Acquire(v65, &v69);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x238,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v10,
          (int)v50);
      v12 = CbsRegOpenKeyWithBackupRestore((HKEY)retaddr, v6, v11, &hKey);
      v13 = v12;
      if ( v12 < 0 )
      {
        v61 = v12;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed opening SessionsPending key with backup/restore");
          Handle = (HKEY)&v61;
          v50 = &Handle;
          LOBYTE(v14) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v14,
            3,
            ": {}");
        }
      }
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23C,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v13,
          (int)v50);
      v15 = hKey;
      v16 = CbsRegSetDWORDValue(hKey, 0, 0, L"Exclusive", 0);
      v17 = v16;
      if ( v16 < 0 )
      {
        v61 = v16;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed resetting SessionsPending Exclusive flag");
          Handle = (HKEY)&v61;
          v50 = &Handle;
          LOBYTE(v18) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v18,
            3,
            ": {}");
        }
      }
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23F,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v17,
          (int)v50);
      v19 = RtlSystemUtil::PrivilegeAcquisition::Restore((RtlSystemUtil::PrivilegeAcquisition *)v65);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x241,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v19,
          (int)v50);
      LogAdapter::TraceInfo<unsigned long>("arbiter: Reset Exclusive flag from {0} to 0 [EXCLUSIVITY_TYPE::NO]", &v63);
      if ( v15 && ((unsigned __int64)v15 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v15) )
      {
        GetLastError();
        __fastfail(7u);
      }
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)v65);
    }
    v20 = DeviceContext::GetWin32RegistryPath(
            a1,
            0,
            L"Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
            &v56);
    v22 = v20;
    if ( v20 < 0 )
    {
      v61 = v20;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting win32 path to software hive");
        Handle = (HKEY)&v61;
        v50 = &Handle;
        LOBYTE(v23) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v23,
          3,
          ": {}");
      }
    }
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x258,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v22,
        (int)v50);
    v24 = v56;
    v25 = CbsRegQueryDWORDValue(HKEY_LOCAL_MACHINE, v56, v21, L"PostponeOnlineActions", &v64);
    v26 = v25;
    if ( v25 != -2147024894 )
    {
      if ( v25 < 0 )
      {
        v61 = v25;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed reading PostponeOnlineActions value from CBS key");
          *(_QWORD *)v57 = &v61;
          v51 = (PHKEY)v57;
          LOBYTE(v27) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v27,
            3,
            ": {}");
        }
      }
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v26,
          (int)v51);
    }
    if ( v64 != 2 )
    {
      v46 = 0;
LABEL_75:
      if ( v24 )
        operator delete(v24 - 4);
      if ( v6 )
        operator delete(v6 - 4);
      goto LABEL_100;
    }
    v69 = 0;
    LOBYTE(v70) = 0;
    Handle = 0;
    hKey = 0;
    v67 = 0;
    *(_QWORD *)v65 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
    v66 = 3;
    v28 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v69, v65);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v28,
        (int)v51);
    v30 = CbsRegOpenKeyWithBackupRestore((HKEY)retaddr, v24, v29, &Handle);
    v31 = v30;
    if ( v30 < 0 )
    {
      v68 = v30;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed opening CBS key with backup/restore");
        *(_QWORD *)v58 = &v68;
        v51 = (PHKEY)v58;
        LOBYTE(v32) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v32,
          3,
          ": {}");
      }
    }
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v31,
        (int)v51);
    v60 = L"PostponeOnlineActions";
    v33 = Handle;
    v34 = RegDeleteValueW(Handle, L"PostponeOnlineActions");
    if ( v34 == 5 )
    {
      DumpHandleInfo(v33);
      DumpKeySecurityInfo(v33);
    }
    else if ( !v34 )
    {
      v38 = 0;
LABEL_54:
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x277,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v38,
          (int)v51);
      v40 = RtlSystemUtil::PrivilegeAcquisition::Restore((RtlSystemUtil::PrivilegeAcquisition *)&v69);
      if ( v40 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x279,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v40,
          (int)v51);
      LogAdapter::TraceInfo<unsigned long>("arbiter: Clear PostponeOnlineActions: {0}", &v64);
      v43 = SvcOpen(v42, v41, &hKey);
      v44 = hKey;
      if ( v43 >= 0 )
      {
        v62 = SvcChangeConfig(hKey);
        if ( v62 < 0 )
        {
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              1,
              "Failed to change Trusted Installer to an auto start service");
            *(_QWORD *)v65 = &v62;
            LOBYTE(v45) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v45,
              1,
              ": {0}");
          }
        }
      }
      if ( v67 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180070E28LL);
      }
      v46 = CbsRegOpenKeyExW(v33, L"RebootInProgress", 0, 0x20019u, &v67) == 0;
      if ( v67 )
      {
        if ( ((unsigned __int64)v67 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v67) )
        {
          GetLastError();
          __fastfail(7u);
        }
        v67 = 0;
      }
      if ( v44 && !CloseServiceHandle((SC_HANDLE)v44) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( v33 && ((unsigned __int64)v33 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v33) )
      {
        GetLastError();
        __fastfail(7u);
      }
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v69);
      goto LABEL_75;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to delete registry value: {}",
        &v60);
      if ( v34 > 0 )
        v36 = (unsigned __int16)v34 | 0x80070000;
      else
        v36 = v34;
      v54 = v36;
      *(_QWORD *)v65 = &v54;
      v51 = (PHKEY)v65;
      LOBYTE(v35) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v35,
        3,
        ": {0}");
    }
    v37 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3DA,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v34,
            (unsigned int)v51);
    v38 = v37;
    if ( v37 < 0 )
    {
      v62 = v37;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed resetting CBS PostponeOnlineActions flag");
        *(_QWORD *)v65 = &v62;
        v51 = (PHKEY)v65;
        LOBYTE(v39) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v39,
          3,
          ": {}");
      }
    }
    goto LABEL_54;
  }
  catch ( ... )
  {
    return 0;
  }
LABEL_100:
  if ( !v46 )
    return 0;
  v62 = -2147021879;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "arbiter: Reporting that a reboot is required");
    *(_QWORD *)v65 = &v62;
    LOBYTE(v47) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v47,
      3,
      ": {}");
  }
  return 2147945417LL;
}

```

## disassembly

```asm
0x180070418  mov     r11, rsp
0x18007041b  push    rdi
0x18007041c  push    r12
0x18007041e  push    r13
0x180070420  push    r14
0x180070422  push    r15
0x180070424  sub     rsp, 100h
0x18007042b  mov     qword ptr [r11-88h], 0FFFFFFFFFFFFFFFEh
0x180070436  mov     [r11+10h], rbx
0x18007043a  mov     [r11+18h], rsi
0x18007043e  mov     rax, cs:__security_cookie
0x180070445  xor     rax, rsp
0x180070448  mov     [rsp+128h+var_38], rax
0x180070450  mov     r15, rcx
0x180070453  xor     r12d, r12d
0x180070456  mov     [rsp+128h+var_C8], r12b
0x18007045b  mov     [r11-70h], r12d
0x18007045f  mov     [r11-6Ch], r12d
0x180070463  mov     [r11-0A8h], r12
0x18007046a  mov     [r11-0A0h], r12
0x180070471  lea     r9, [r11-0A8h]
0x180070478  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Com"...
0x18007047f  xor     edx, edx
0x180070481  call    ?GetWin32RegistryPath@DeviceContext@@QEAAJW4RegistryHive@1@PEB_WPEAVAutoScz@@@Z; DeviceContext::GetWin32RegistryPath(DeviceContext::RegistryHive,wchar_t const *,AutoScz *)
0x180070486  mov     ebx, eax
0x180070488  lea     r14d, [r12+3]
0x18007048d  test    eax, eax
0x18007048f  jns     short loc_1800704E4
0x180070491  mov     [rsp+128h+var_78], eax
0x180070498  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007049f  test    rcx, rcx
0x1800704a2  jz      short loc_1800704E4
0x1800704a4  lea     r9, aFailedGettingW_4; "Failed getting win32 path to software h"...
0x1800704ab  mov     r8d, r14d
0x1800704ae  xor     edx, edx
0x1800704b0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800704b5  lea     rax, [rsp+128h+var_78]
0x1800704bd  mov     [rsp+128h+Handle], rax
0x1800704c2  lea     rax, [rsp+128h+Handle]
0x1800704c7  mov     [rsp+128h+var_108], rax; int
0x1800704cc  lea     r9, asc_1801CAFB4; ": {}"
0x1800704d3  mov     r8d, r14d
0x1800704d6  mov     dl, 1
0x1800704d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800704df  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800704e4  mov     rcx, [rsp+128h]; this
0x1800704ec  test    ebx, ebx
0x1800704ee  js      loc_180070D2B
0x1800704f4  lea     rax, [rsp+128h+var_70]
0x1800704fc  mov     [rsp+128h+var_108], rax; unsigned int *
0x180070501  lea     r9, aExclusive; "Exclusive"
0x180070508  mov     rsi, [rsp+128h+var_A8]
0x180070510  mov     rdx, rsi; wchar_t *
0x180070513  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18007051a  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x18007051f  mov     ebx, eax
0x180070521  cmp     eax, 80070002h
0x180070526  jz      short loc_18007058F
0x180070528  test    eax, eax
0x18007052a  jns     short loc_18007057F
0x18007052c  mov     [rsp+128h+var_78], eax
0x180070533  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007053a  test    rcx, rcx
0x18007053d  jz      short loc_18007057F
0x18007053f  lea     r9, aFailedReadingE; "Failed reading Exclusive value from Ses"...
0x180070546  mov     r8d, r14d
0x180070549  xor     edx, edx
0x18007054b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180070550  lea     rax, [rsp+128h+var_78]
0x180070558  mov     [rsp+128h+Handle], rax
0x18007055d  lea     rax, [rsp+128h+Handle]
0x180070562  mov     [rsp+128h+var_108], rax; int
0x180070567  lea     r9, asc_1801CAFB4; ": {}"
0x18007056e  mov     r8d, r14d
0x180070571  mov     dl, 1
0x180070573  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007057a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007057f  mov     rcx, [rsp+128h]; this
0x180070587  test    ebx, ebx
0x180070589  js      loc_180070D3F
0x18007058f  cmp     [rsp+128h+var_70], r12d
0x180070597  jz      loc_180070769
0x18007059d  mov     qword ptr [rsp+128h+var_68], r12
0x1800705a5  mov     byte ptr [rsp+128h+var_60], r12b
0x1800705ad  mov     [rsp+128h+hKey], r12
0x1800705b2  lea     r13, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1800705b9  mov     [rsp+128h+var_48], r13
0x1800705c1  mov     [rsp+128h+var_40], r14
0x1800705c9  lea     rdx, [rsp+128h+var_48]
0x1800705d1  lea     rcx, [rsp+128h+var_68]
0x1800705d9  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1800705de  mov     rcx, [rsp+128h]; this
0x1800705e6  test    eax, eax
0x1800705e8  js      loc_180070D54
0x1800705ee  lea     r9, [rsp+128h+hKey]; HKEY *
0x1800705f3  mov     rdx, rsi; wchar_t *
0x1800705f6  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800705fb  mov     ebx, eax
0x1800705fd  test    eax, eax
0x1800705ff  jns     short loc_180070654
0x180070601  mov     [rsp+128h+var_78], eax
0x180070608  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007060f  test    rcx, rcx
0x180070612  jz      short loc_180070654
0x180070614  lea     r9, aFailedOpeningS; "Failed opening SessionsPending key with"...
0x18007061b  mov     r8d, r14d
0x18007061e  xor     edx, edx
0x180070620  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180070625  lea     rax, [rsp+128h+var_78]
0x18007062d  mov     [rsp+128h+Handle], rax
0x180070632  lea     rax, [rsp+128h+Handle]
0x180070637  mov     [rsp+128h+var_108], rax; int
0x18007063c  lea     r9, asc_1801CAFB4; ": {}"
0x180070643  mov     r8d, r14d
0x180070646  mov     dl, 1
0x180070648  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007064f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180070654  mov     rcx, [rsp+128h]; this
0x18007065c  test    ebx, ebx
0x18007065e  js      loc_180070D68
0x180070664  mov     dword ptr [rsp+128h+var_108], r12d; unsigned int
0x180070669  lea     r9, aExclusive; "Exclusive"
0x180070670  xor     r8d, r8d; unsigned int
0x180070673  xor     edx, edx; wchar_t *
0x180070675  mov     rdi, [rsp+128h+hKey]
0x18007067a  mov     rcx, rdi; HKEY
0x18007067d  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x180070682  mov     ebx, eax
0x180070684  test    eax, eax
0x180070686  jns     short loc_1800706DB
0x180070688  mov     [rsp+128h+var_78], eax
0x18007068f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180070696  test    rcx, rcx
0x180070699  jz      short loc_1800706DB
0x18007069b  lea     r9, aFailedResettin_0; "Failed resetting SessionsPending Exclus"...
0x1800706a2  mov     r8d, r14d
0x1800706a5  xor     edx, edx
0x1800706a7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800706ac  lea     rax, [rsp+128h+var_78]
0x1800706b4  mov     [rsp+128h+Handle], rax
0x1800706b9  lea     rax, [rsp+128h+Handle]
0x1800706be  mov     [rsp+128h+var_108], rax; int
0x1800706c3  lea     r9, asc_1801CAFB4; ": {}"
0x1800706ca  mov     r8d, r14d
0x1800706cd  mov     dl, 1
0x1800706cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800706d6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800706db  mov     rcx, [rsp+128h]; this
0x1800706e3  test    ebx, ebx
0x1800706e5  js      loc_180070D7C
0x1800706eb  lea     rcx, [rsp+128h+var_68]; this
0x1800706f3  call    ?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::PrivilegeAcquisition::Restore(void)
0x1800706f8  mov     rcx, [rsp+128h]; this
0x180070700  test    eax, eax
0x180070702  js      loc_180070D90
0x180070708  lea     rdx, [rsp+128h+var_70]
0x180070710  lea     rcx, aArbiterResetEx; "arbiter: Reset Exclusive flag from {0} "...
0x180070717  call    ??$TraceInfo@K@LogAdapter@@YAXQEBDAEBK@Z; LogAdapter::TraceInfo<ulong>(char const * const,ulong const &)
0x18007071c  nop
0x18007071d  mov     r12, 0FFFFFFFF80000000h
0x180070724  test    rdi, rdi
0x180070727  jz      short loc_18007075A
0x180070729  mov     rax, rdi
0x18007072c  and     rax, r12
0x18007072f  cmp     rax, r12
0x180070732  jz      short loc_18007075A
0x180070734  mov     rcx, rdi; hKey
0x180070737  call    cs:__imp_RegCloseKey
0x18007073e  nop     dword ptr [rax+rax+00h]
0x180070743  test    eax, eax
0x180070745  jz      short loc_18007075A
0x180070747  call    cs:__imp_GetLastError
0x18007074e  nop     dword ptr [rax+rax+00h]
0x180070753  mov     ecx, 7
0x180070758  int     29h; Win8: RtlFailFast(ecx)
0x18007075a  lea     rcx, [rsp+128h+var_68]; this
0x180070762  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180070767  jmp     short loc_180070777
0x180070769  lea     r13, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x180070770  mov     r12, 0FFFFFFFF80000000h
0x180070777  lea     r9, [rsp+128h+var_A0]
0x18007077f  lea     r8, aMicrosoftWindo_6; "Microsoft\\Windows\\CurrentVersion\\Com"...
0x180070786  xor     edx, edx
0x180070788  mov     rcx, r15
0x18007078b  call    ?GetWin32RegistryPath@DeviceContext@@QEAAJW4RegistryHive@1@PEB_WPEAVAutoScz@@@Z; DeviceContext::GetWin32RegistryPath(DeviceContext::RegistryHive,wchar_t const *,AutoScz *)
0x180070790  mov     ebx, eax
0x180070792  test    eax, eax
0x180070794  jns     short loc_1800707E9
0x180070796  mov     [rsp+128h+var_78], eax
0x18007079d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800707a4  test    rcx, rcx
0x1800707a7  jz      short loc_1800707E9
0x1800707a9  lea     r9, aFailedGettingW_4; "Failed getting win32 path to software h"...
0x1800707b0  mov     r8d, r14d
0x1800707b3  xor     edx, edx
0x1800707b5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800707ba  lea     rax, [rsp+128h+var_78]
0x1800707c2  mov     [rsp+128h+Handle], rax
0x1800707c7  lea     rax, [rsp+128h+Handle]
0x1800707cc  mov     [rsp+128h+var_108], rax; int
0x1800707d1  lea     r9, asc_1801CAFB4; ": {}"
0x1800707d8  mov     r8d, r14d
0x1800707db  mov     dl, 1
0x1800707dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800707e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800707e9  mov     rcx, [rsp+128h]; this
0x1800707f1  test    ebx, ebx
0x1800707f3  js      loc_180070DA5
0x1800707f9  lea     rax, [rsp+128h+var_6C]
0x180070801  mov     [rsp+128h+var_108], rax; unsigned int *
0x180070806  lea     r15, aPostponeonline; "PostponeOnlineActions"
0x18007080d  mov     r9, r15; wchar_t *
0x180070810  mov     rdi, [rsp+128h+var_A0]
0x180070818  mov     rdx, rdi; wchar_t *
0x18007081b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180070822  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x180070827  mov     ebx, eax
0x180070829  cmp     eax, 80070002h
0x18007082e  jz      short loc_18007089D
0x180070830  test    eax, eax
0x180070832  jns     short loc_18007088D
0x180070834  mov     [rsp+128h+var_78], eax
0x18007083b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180070842  test    rcx, rcx
0x180070845  jz      short loc_18007088D
0x180070847  lea     r9, aFailedReadingP; "Failed reading PostponeOnlineActions va"...
0x18007084e  mov     r8d, r14d
0x180070851  xor     edx, edx
0x180070853  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180070858  lea     rax, [rsp+128h+var_78]
0x180070860  mov     qword ptr [rsp+128h+var_98], rax
0x180070868  lea     rax, [rsp+128h+var_98]
0x180070870  mov     [rsp+128h+var_108], rax; int
0x180070875  lea     r9, asc_1801CAFB4; ": {}"
0x18007087c  mov     r8d, r14d
0x18007087f  mov     dl, 1
0x180070881  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180070888  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007088d  mov     rcx, [rsp+128h]; this
0x180070895  test    ebx, ebx
0x180070897  js      loc_180070DB9
0x18007089d  cmp     [rsp+128h+var_6C], 2
0x1800708a5  jnz     loc_180070C71
0x1800708ab  mov     [rsp+128h+var_48], 0
0x1800708b7  mov     byte ptr [rsp+128h+var_40], 0
0x1800708bf  mov     [rsp+128h+Handle], 0
0x1800708c8  mov     [rsp+128h+hKey], 0
0x1800708d1  mov     [rsp+128h+var_58], 0
0x1800708dd  mov     qword ptr [rsp+128h+var_68], r13
0x1800708e5  mov     [rsp+128h+var_60], r14
0x1800708ed  lea     rdx, [rsp+128h+var_68]
0x1800708f5  lea     rcx, [rsp+128h+var_48]
0x1800708fd  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x180070902  mov     rcx, [rsp+128h]; this
0x18007090a  test    eax, eax
0x18007090c  js      loc_180070DCE
0x180070912  lea     r9, [rsp+128h+Handle]; HKEY *
0x180070917  mov     rdx, rdi; wchar_t *
0x18007091a  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x18007091f  mov     ebx, eax
0x180070921  test    eax, eax
0x180070923  jns     short loc_18007097E
0x180070925  mov     [rsp+128h+var_50], eax
0x18007092c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180070933  test    rcx, rcx
0x180070936  jz      short loc_18007097E
0x180070938  lea     r9, aFailedOpeningC_0; "Failed opening CBS key with backup/rest"...
0x18007093f  mov     r8d, r14d
0x180070942  xor     edx, edx
0x180070944  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180070949  lea     rax, [rsp+128h+var_50]
0x180070951  mov     qword ptr [rsp+128h+var_90], rax
0x180070959  lea     rax, [rsp+128h+var_90]
0x180070961  mov     [rsp+128h+var_108], rax; int
0x180070966  lea     r9, asc_1801CAFB4; ": {}"
0x18007096d  mov     r8d, r14d
0x180070970  mov     dl, 1
0x180070972  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180070979  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007097e  mov     rcx, [rsp+128h]; this
0x180070986  test    ebx, ebx
0x180070988  js      loc_180070DE2
0x18007098e  mov     [rsp+128h+var_80], r15
0x180070996  mov     r15, [rsp+128h+Handle]
0x18007099b  lea     rdx, aPostponeonline; "PostponeOnlineActions"
0x1800709a2  mov     rcx, r15; hKey
0x1800709a5  call    cs:__imp_RegDeleteValueW
0x1800709ac  nop     dword ptr [rax+rax+00h]
0x1800709b1  mov     ebx, eax
0x1800709b3  cmp     eax, 5
0x1800709b6  jnz     short loc_1800709CA
0x1800709b8  mov     rcx, r15; Handle
0x1800709bb  call    ?DumpHandleInfo@@YAXPEAUHKEY__@@@Z; DumpHandleInfo(HKEY__ *)
0x1800709c0  mov     rcx, r15; hKey
0x1800709c3  call    ?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z; DumpKeySecurityInfo(HKEY__ *)
0x1800709c8  jmp     short loc_1800709D2
0x1800709ca  test    ebx, ebx
0x1800709cc  jz      loc_180070ABF
0x1800709d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800709d9  test    rcx, rcx
  ... truncated ...
```
