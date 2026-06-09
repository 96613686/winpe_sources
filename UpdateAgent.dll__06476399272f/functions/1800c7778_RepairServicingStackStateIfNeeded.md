# RepairServicingStackStateIfNeeded

- ea: `0x1800c7778`
- end: `0x1800c8185`
- name: `RepairServicingStackStateIfNeeded`
- size: `2573`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c02fc`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18001273c`
- `0x1800692fc`
- `0x18008b3ec`
- `0x180094d0c`
- `0x18009b6cc`
- `0x1800c7778`
- `0x18014d3d4`
- `0x18014d478`
- `0x18014d69c`
- `0x18014ebd0`
- `0x18014f190`
- `0x18014f34c`
- `0x18014f514`
- `0x18014f6bc`
- `0x18017600c`
- `0x1801f2558`
- `0x1801f2604`
- `0x1801f47a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7a92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7a92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7f9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c7d00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c7d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7faa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c7f64`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c7f64`

## string_xrefs

- `0x1800c77d8`: `Microsoft\Windows\CurrentVersion\Component Based Servicing\SessionsPending`
- `0x1800c7804`: `Failed getting win32 path to software hive`
- `0x1800c7b04`: `Failed getting win32 path to software hive`
- `0x1800c7974`: `Failed opening SessionsPending key with backup/restore`
- `0x1800c789f`: `Failed reading Exclusive value from SessionsPending`
- `0x1800c7ada`: `Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x1800c7c93`: `Failed opening CBS key with backup/restore`
- `0x1800c7ba2`: `Failed reading PostponeOnlineActions value from CBS key`
- `0x1800c7e8f`: `Failed to change Trusted Installer to an auto start service`
- `0x1800c7d46`: `Failed to delete registry value: {}`

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
  const wchar_t *v13; // rdx
  unsigned int v14; // r8d
  int v15; // ebx
  __int64 v16; // rdx
  HKEY v17; // rdi
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  unsigned int v23; // r8d
  int v24; // ebx
  __int64 v25; // rdx
  wchar_t *v26; // rdi
  int v27; // eax
  const struct std::nothrow_t *v28; // rdx
  int v29; // ebx
  __int64 v30; // rdx
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // eax
  int v34; // ebx
  __int64 v35; // rdx
  HKEY v36; // r15
  LSTATUS v37; // ebx
  __int64 v38; // rdx
  unsigned int v39; // eax
  int v40; // eax
  int v41; // ebx
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  int v46; // eax
  HKEY v47; // rbx
  __int64 v48; // rdx
  bool v49; // r13
  __int64 v50; // rdx
  HKEY *p_Handle; // [rsp+20h] [rbp-108h]
  HKEY *v53; // [rsp+20h] [rbp-108h]
  PHKEY v54; // [rsp+20h] [rbp-108h]
  HKEY Handle; // [rsp+68h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v57; // [rsp+78h] [rbp-B0h] BYREF
  wchar_t *v58; // [rsp+80h] [rbp-A8h] BYREF
  wchar_t *v59; // [rsp+88h] [rbp-A0h] BYREF
  int v60[2]; // [rsp+90h] [rbp-98h] BYREF
  int v61[2]; // [rsp+98h] [rbp-90h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-88h]
  const wchar_t *v63; // [rsp+A8h] [rbp-80h]
  int v64; // [rsp+B0h] [rbp-78h] BYREF
  int v65; // [rsp+B4h] [rbp-74h] BYREF
  unsigned int v66; // [rsp+B8h] [rbp-70h] BYREF
  unsigned int v67; // [rsp+BCh] [rbp-6Ch] BYREF
  unsigned int v68[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-60h]
  HKEY v70; // [rsp+D0h] [rbp-58h] BYREF
  int v71; // [rsp+D8h] [rbp-50h] BYREF
  void *v72; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v62 = -2;
  try
  {
    v66 = 0;
    v67 = 0;
    v58 = 0;
    v59 = 0;
    Win32RegistryPath = DeviceContext::GetWin32RegistryPath(
                          a1,
                          0,
                          L"Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\SessionsPending",
                          &v58);
    v4 = Win32RegistryPath;
    if ( Win32RegistryPath < 0 )
    {
      v64 = Win32RegistryPath;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting win32 path to software hive");
        Handle = (HKEY)&v64;
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
    v6 = v58;
    v7 = CbsRegQueryDWORDValue(HKEY_LOCAL_MACHINE, v58, v3, L"Exclusive", &v66);
    v8 = v7;
    if ( v7 != -2147024894 )
    {
      if ( v7 < 0 )
      {
        v64 = v7;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed reading Exclusive value from SessionsPending");
          Handle = (HKEY)&v64;
          v53 = &Handle;
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
          (int)v53);
    }
    if ( v66 )
    {
      *(_QWORD *)v68 = 0;
      LOBYTE(v69) = 0;
      hKey = 0;
      v72 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
      v73 = 3;
      v10 = RtlSystemUtil::PrivilegeAcquisition::Acquire(v68, &v72);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x238,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v10,
          (int)v53);
      v12 = CbsRegOpenKeyWithBackupRestore((HKEY)retaddr, v6, v11, &hKey);
      v15 = v12;
      if ( v12 < 0 )
      {
        v64 = v12;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed opening SessionsPending key with backup/restore");
          Handle = (HKEY)&v64;
          v53 = &Handle;
          LOBYTE(v16) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v16,
            3,
            ": {}");
        }
      }
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23C,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v15,
          (int)v53);
      v17 = hKey;
      v18 = CbsRegSetDWORDValue(hKey, v13, v14, L"Exclusive", 0);
      v19 = v18;
      if ( v18 < 0 )
      {
        v64 = v18;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed resetting SessionsPending Exclusive flag");
          Handle = (HKEY)&v64;
          v53 = &Handle;
          LOBYTE(v20) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v20,
            3,
            ": {}");
        }
      }
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23F,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v19,
          (int)v53);
      v21 = RtlSystemUtil::PrivilegeAcquisition::Restore((RtlSystemUtil::PrivilegeAcquisition *)v68);
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x241,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v21,
          (int)v53);
      LogAdapter::TraceInfo<unsigned long>("arbiter: Reset Exclusive flag from {0} to 0 [EXCLUSIVITY_TYPE::NO]", &v66);
      if ( v17 && ((unsigned __int64)v17 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v17) )
      {
        GetLastError();
        __fastfail(7u);
      }
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)v68);
    }
    v22 = DeviceContext::GetWin32RegistryPath(
            a1,
            0,
            L"Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
            &v59);
    v24 = v22;
    if ( v22 < 0 )
    {
      v64 = v22;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting win32 path to software hive");
        Handle = (HKEY)&v64;
        v53 = &Handle;
        LOBYTE(v25) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v25,
          3,
          ": {}");
      }
    }
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x258,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v24,
        (int)v53);
    v26 = v59;
    v27 = CbsRegQueryDWORDValue(HKEY_LOCAL_MACHINE, v59, v23, L"PostponeOnlineActions", &v67);
    v29 = v27;
    if ( v27 != -2147024894 )
    {
      if ( v27 < 0 )
      {
        v64 = v27;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed reading PostponeOnlineActions value from CBS key");
          *(_QWORD *)v60 = &v64;
          v54 = (PHKEY)v60;
          LOBYTE(v30) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v30,
            3,
            ": {}");
        }
      }
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v29,
          (int)v54);
    }
    if ( v67 != 2 )
    {
      v49 = 0;
LABEL_75:
      if ( v26 )
        operator delete(v26 - 4, v28);
      if ( v6 )
        operator delete(v6 - 4, v28);
      goto LABEL_100;
    }
    v72 = 0;
    LOBYTE(v73) = 0;
    Handle = 0;
    hKey = 0;
    v70 = 0;
    *(_QWORD *)v68 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
    v69 = 3;
    v31 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v72, v68);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v31,
        (int)v54);
    v33 = CbsRegOpenKeyWithBackupRestore((HKEY)retaddr, v26, v32, &Handle);
    v34 = v33;
    if ( v33 < 0 )
    {
      v71 = v33;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed opening CBS key with backup/restore");
        *(_QWORD *)v61 = &v71;
        v54 = (PHKEY)v61;
        LOBYTE(v35) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v35,
          3,
          ": {}");
      }
    }
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v34,
        (int)v54);
    v63 = L"PostponeOnlineActions";
    v36 = Handle;
    v37 = RegDeleteValueW(Handle, L"PostponeOnlineActions");
    if ( v37 == 5 )
    {
      DumpHandleInfo(v36);
      DumpKeySecurityInfo(v36);
    }
    else if ( !v37 )
    {
      v41 = 0;
LABEL_54:
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x277,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v41,
          (int)v54);
      v43 = RtlSystemUtil::PrivilegeAcquisition::Restore((RtlSystemUtil::PrivilegeAcquisition *)&v72);
      if ( v43 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x279,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v43,
          (int)v54);
      LogAdapter::TraceInfo<unsigned long>("arbiter: Clear PostponeOnlineActions: {0}", &v67);
      v46 = SvcOpen(v45, v44, &hKey);
      v47 = hKey;
      if ( v46 >= 0 )
      {
        v65 = SvcChangeConfig(hKey);
        if ( v65 < 0 )
        {
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              1,
              "Failed to change Trusted Installer to an auto start service");
            *(_QWORD *)v68 = &v65;
            LOBYTE(v48) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v48,
              1,
              ": {0}");
          }
        }
      }
      if ( v70 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x1800C8183LL);
      }
      v49 = CbsRegOpenKeyExW(v36, L"RebootInProgress", 0, 0x20019u, &v70) == 0;
      if ( v70 )
      {
        if ( ((unsigned __int64)v70 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v70) )
        {
          GetLastError();
          __fastfail(7u);
        }
        v70 = 0;
      }
      if ( v47 && !CloseServiceHandle((SC_HANDLE)v47) )
      {
        GetLastError();
        __fastfail(7u);
      }
      if ( v36 && ((unsigned __int64)v36 & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(v36) )
      {
        GetLastError();
        __fastfail(7u);
      }
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v72);
      goto LABEL_75;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to delete registry value: {}");
      if ( v37 > 0 )
        v39 = (unsigned __int16)v37 | 0x80070000;
      else
        v39 = v37;
      v57 = v39;
      *(_QWORD *)v68 = &v57;
      v54 = (PHKEY)v68;
      LOBYTE(v38) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v38,
        3,
        ": {0}");
    }
    v40 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3DA,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v37,
            (unsigned int)v54);
    v41 = v40;
    if ( v40 < 0 )
    {
      v65 = v40;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed resetting CBS PostponeOnlineActions flag");
        *(_QWORD *)v68 = &v65;
        v54 = (PHKEY)v68;
        LOBYTE(v42) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v42,
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
  if ( !v49 )
    return 0;
  v65 = -2147021879;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "arbiter: Reporting that a reboot is required");
    *(_QWORD *)v68 = &v65;
    LOBYTE(v50) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v50,
      3,
      ": {}");
  }
  return 2147945417LL;
}

```

## disassembly

```asm
0x1800c7778  mov     r11, rsp
0x1800c777b  push    rdi
0x1800c777c  push    r12
0x1800c777e  push    r13
0x1800c7780  push    r14
0x1800c7782  push    r15
0x1800c7784  sub     rsp, 100h
0x1800c778b  mov     qword ptr [r11-88h], 0FFFFFFFFFFFFFFFEh
0x1800c7796  mov     [r11+10h], rbx
0x1800c779a  mov     [r11+18h], rsi
0x1800c779e  mov     rax, cs:__security_cookie
0x1800c77a5  xor     rax, rsp
0x1800c77a8  mov     [rsp+128h+var_38], rax
0x1800c77b0  mov     r15, rcx
0x1800c77b3  xor     r12d, r12d
0x1800c77b6  mov     [rsp+128h+var_C8], r12b
0x1800c77bb  mov     [r11-70h], r12d
0x1800c77bf  mov     [r11-6Ch], r12d
0x1800c77c3  mov     [r11-0A8h], r12
0x1800c77ca  mov     [r11-0A0h], r12
0x1800c77d1  lea     r9, [r11-0A8h]
0x1800c77d8  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Com"...
0x1800c77df  xor     edx, edx
0x1800c77e1  call    ?GetWin32RegistryPath@DeviceContext@@QEAAJW4RegistryHive@1@PEB_WPEAVAutoScz@@@Z; DeviceContext::GetWin32RegistryPath(DeviceContext::RegistryHive,wchar_t const *,AutoScz *)
0x1800c77e6  mov     ebx, eax
0x1800c77e8  lea     r14d, [r12+3]
0x1800c77ed  test    eax, eax
0x1800c77ef  jns     short loc_1800C7844
0x1800c77f1  mov     [rsp+128h+var_78], eax
0x1800c77f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c77ff  test    rcx, rcx
0x1800c7802  jz      short loc_1800C7844
0x1800c7804  lea     r9, aFailedGettingW_4; "Failed getting win32 path to software h"...
0x1800c780b  mov     r8d, r14d
0x1800c780e  xor     edx, edx
0x1800c7810  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7815  lea     rax, [rsp+128h+var_78]
0x1800c781d  mov     [rsp+128h+Handle], rax
0x1800c7822  lea     rax, [rsp+128h+Handle]
0x1800c7827  mov     [rsp+128h+var_108], rax; int
0x1800c782c  lea     r9, asc_1802C6678; ": {}"
0x1800c7833  mov     r8d, r14d
0x1800c7836  mov     dl, 1
0x1800c7838  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c783f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7844  mov     rcx, [rsp+128h]; this
0x1800c784c  test    ebx, ebx
0x1800c784e  js      loc_1800C8086
0x1800c7854  lea     rax, [rsp+128h+var_70]
0x1800c785c  mov     [rsp+128h+var_108], rax; unsigned int *
0x1800c7861  lea     r9, aExclusive_0; "Exclusive"
0x1800c7868  mov     rsi, [rsp+128h+var_A8]
0x1800c7870  mov     rdx, rsi; wchar_t *
0x1800c7873  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800c787a  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800c787f  mov     ebx, eax
0x1800c7881  cmp     eax, 80070002h
0x1800c7886  jz      short loc_1800C78EF
0x1800c7888  test    eax, eax
0x1800c788a  jns     short loc_1800C78DF
0x1800c788c  mov     [rsp+128h+var_78], eax
0x1800c7893  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c789a  test    rcx, rcx
0x1800c789d  jz      short loc_1800C78DF
0x1800c789f  lea     r9, aFailedReadingE; "Failed reading Exclusive value from Ses"...
0x1800c78a6  mov     r8d, r14d
0x1800c78a9  xor     edx, edx
0x1800c78ab  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c78b0  lea     rax, [rsp+128h+var_78]
0x1800c78b8  mov     [rsp+128h+Handle], rax
0x1800c78bd  lea     rax, [rsp+128h+Handle]
0x1800c78c2  mov     [rsp+128h+var_108], rax; int
0x1800c78c7  lea     r9, asc_1802C6678; ": {}"
0x1800c78ce  mov     r8d, r14d
0x1800c78d1  mov     dl, 1
0x1800c78d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c78da  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c78df  mov     rcx, [rsp+128h]; this
0x1800c78e7  test    ebx, ebx
0x1800c78e9  js      loc_1800C809A
0x1800c78ef  cmp     [rsp+128h+var_70], r12d
0x1800c78f7  jz      loc_1800C7AC4
0x1800c78fd  mov     qword ptr [rsp+128h+var_68], r12
0x1800c7905  mov     byte ptr [rsp+128h+var_60], r12b
0x1800c790d  mov     [rsp+128h+hKey], r12
0x1800c7912  lea     r13, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1800c7919  mov     [rsp+128h+var_48], r13
0x1800c7921  mov     [rsp+128h+var_40], r14
0x1800c7929  lea     rdx, [rsp+128h+var_48]
0x1800c7931  lea     rcx, [rsp+128h+var_68]
0x1800c7939  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1800c793e  mov     rcx, [rsp+128h]; this
0x1800c7946  test    eax, eax
0x1800c7948  js      loc_1800C80AF
0x1800c794e  lea     r9, [rsp+128h+hKey]; HKEY *
0x1800c7953  mov     rdx, rsi; wchar_t *
0x1800c7956  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c795b  mov     ebx, eax
0x1800c795d  test    eax, eax
0x1800c795f  jns     short loc_1800C79B4
0x1800c7961  mov     [rsp+128h+var_78], eax
0x1800c7968  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c796f  test    rcx, rcx
0x1800c7972  jz      short loc_1800C79B4
0x1800c7974  lea     r9, aFailedOpeningS; "Failed opening SessionsPending key with"...
0x1800c797b  mov     r8d, r14d
0x1800c797e  xor     edx, edx
0x1800c7980  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7985  lea     rax, [rsp+128h+var_78]
0x1800c798d  mov     [rsp+128h+Handle], rax
0x1800c7992  lea     rax, [rsp+128h+Handle]
0x1800c7997  mov     [rsp+128h+var_108], rax; int
0x1800c799c  lea     r9, asc_1802C6678; ": {}"
0x1800c79a3  mov     r8d, r14d
0x1800c79a6  mov     dl, 1
0x1800c79a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c79af  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c79b4  mov     rcx, [rsp+128h]; this
0x1800c79bc  test    ebx, ebx
0x1800c79be  js      loc_1800C80C3
0x1800c79c4  mov     dword ptr [rsp+128h+var_108], r12d; unsigned int
0x1800c79c9  lea     r9, aExclusive_0; "Exclusive"
0x1800c79d0  mov     rdi, [rsp+128h+hKey]
0x1800c79d5  mov     rcx, rdi; HKEY
0x1800c79d8  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x1800c79dd  mov     ebx, eax
0x1800c79df  test    eax, eax
0x1800c79e1  jns     short loc_1800C7A36
0x1800c79e3  mov     [rsp+128h+var_78], eax
0x1800c79ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c79f1  test    rcx, rcx
0x1800c79f4  jz      short loc_1800C7A36
0x1800c79f6  lea     r9, aFailedResettin_0; "Failed resetting SessionsPending Exclus"...
0x1800c79fd  mov     r8d, r14d
0x1800c7a00  xor     edx, edx
0x1800c7a02  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7a07  lea     rax, [rsp+128h+var_78]
0x1800c7a0f  mov     [rsp+128h+Handle], rax
0x1800c7a14  lea     rax, [rsp+128h+Handle]
0x1800c7a19  mov     [rsp+128h+var_108], rax; int
0x1800c7a1e  lea     r9, asc_1802C6678; ": {}"
0x1800c7a25  mov     r8d, r14d
0x1800c7a28  mov     dl, 1
0x1800c7a2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7a31  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7a36  mov     rcx, [rsp+128h]; this
0x1800c7a3e  test    ebx, ebx
0x1800c7a40  js      loc_1800C80D7
0x1800c7a46  lea     rcx, [rsp+128h+var_68]; this
0x1800c7a4e  call    ?Restore@PrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::PrivilegeAcquisition::Restore(void)
0x1800c7a53  mov     rcx, [rsp+128h]; this
0x1800c7a5b  test    eax, eax
0x1800c7a5d  js      loc_1800C80EB
0x1800c7a63  lea     rdx, [rsp+128h+var_70]
0x1800c7a6b  lea     rcx, aArbiterResetEx; "arbiter: Reset Exclusive flag from {0} "...
0x1800c7a72  call    ??$TraceInfo@K@LogAdapter@@YAXQEBDAEBK@Z; LogAdapter::TraceInfo<ulong>(char const * const,ulong const &)
0x1800c7a77  nop
0x1800c7a78  mov     r12, 0FFFFFFFF80000000h
0x1800c7a7f  test    rdi, rdi
0x1800c7a82  jz      short loc_1800C7AB5
0x1800c7a84  mov     rax, rdi
0x1800c7a87  and     rax, r12
0x1800c7a8a  cmp     rax, r12
0x1800c7a8d  jz      short loc_1800C7AB5
0x1800c7a8f  mov     rcx, rdi; hKey
0x1800c7a92  call    cs:__imp_RegCloseKey
0x1800c7a99  nop     dword ptr [rax+rax+00h]
0x1800c7a9e  test    eax, eax
0x1800c7aa0  jz      short loc_1800C7AB5
0x1800c7aa2  call    cs:__imp_GetLastError
0x1800c7aa9  nop     dword ptr [rax+rax+00h]
0x1800c7aae  mov     ecx, 7
0x1800c7ab3  int     29h; Win8: RtlFailFast(ecx)
0x1800c7ab5  lea     rcx, [rsp+128h+var_68]; this
0x1800c7abd  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x1800c7ac2  jmp     short loc_1800C7AD2
0x1800c7ac4  lea     r13, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1800c7acb  mov     r12, 0FFFFFFFF80000000h
0x1800c7ad2  lea     r9, [rsp+128h+var_A0]
0x1800c7ada  lea     r8, aMicrosoftWindo_7; "Microsoft\\Windows\\CurrentVersion\\Com"...
0x1800c7ae1  xor     edx, edx
0x1800c7ae3  mov     rcx, r15
0x1800c7ae6  call    ?GetWin32RegistryPath@DeviceContext@@QEAAJW4RegistryHive@1@PEB_WPEAVAutoScz@@@Z; DeviceContext::GetWin32RegistryPath(DeviceContext::RegistryHive,wchar_t const *,AutoScz *)
0x1800c7aeb  mov     ebx, eax
0x1800c7aed  test    eax, eax
0x1800c7aef  jns     short loc_1800C7B44
0x1800c7af1  mov     [rsp+128h+var_78], eax
0x1800c7af8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7aff  test    rcx, rcx
0x1800c7b02  jz      short loc_1800C7B44
0x1800c7b04  lea     r9, aFailedGettingW_4; "Failed getting win32 path to software h"...
0x1800c7b0b  mov     r8d, r14d
0x1800c7b0e  xor     edx, edx
0x1800c7b10  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7b15  lea     rax, [rsp+128h+var_78]
0x1800c7b1d  mov     [rsp+128h+Handle], rax
0x1800c7b22  lea     rax, [rsp+128h+Handle]
0x1800c7b27  mov     [rsp+128h+var_108], rax; int
0x1800c7b2c  lea     r9, asc_1802C6678; ": {}"
0x1800c7b33  mov     r8d, r14d
0x1800c7b36  mov     dl, 1
0x1800c7b38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7b3f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7b44  mov     rcx, [rsp+128h]; this
0x1800c7b4c  test    ebx, ebx
0x1800c7b4e  js      loc_1800C8100
0x1800c7b54  lea     rax, [rsp+128h+var_6C]
0x1800c7b5c  mov     [rsp+128h+var_108], rax; unsigned int *
0x1800c7b61  lea     r15, aPostponeonline; "PostponeOnlineActions"
0x1800c7b68  mov     r9, r15; wchar_t *
0x1800c7b6b  mov     rdi, [rsp+128h+var_A0]
0x1800c7b73  mov     rdx, rdi; wchar_t *
0x1800c7b76  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800c7b7d  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800c7b82  mov     ebx, eax
0x1800c7b84  cmp     eax, 80070002h
0x1800c7b89  jz      short loc_1800C7BF8
0x1800c7b8b  test    eax, eax
0x1800c7b8d  jns     short loc_1800C7BE8
0x1800c7b8f  mov     [rsp+128h+var_78], eax
0x1800c7b96  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7b9d  test    rcx, rcx
0x1800c7ba0  jz      short loc_1800C7BE8
0x1800c7ba2  lea     r9, aFailedReadingP; "Failed reading PostponeOnlineActions va"...
0x1800c7ba9  mov     r8d, r14d
0x1800c7bac  xor     edx, edx
0x1800c7bae  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7bb3  lea     rax, [rsp+128h+var_78]
0x1800c7bbb  mov     qword ptr [rsp+128h+var_98], rax
0x1800c7bc3  lea     rax, [rsp+128h+var_98]
0x1800c7bcb  mov     [rsp+128h+var_108], rax; int
0x1800c7bd0  lea     r9, asc_1802C6678; ": {}"
0x1800c7bd7  mov     r8d, r14d
0x1800c7bda  mov     dl, 1
0x1800c7bdc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7be3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7be8  mov     rcx, [rsp+128h]; this
0x1800c7bf0  test    ebx, ebx
0x1800c7bf2  js      loc_1800C8114
0x1800c7bf8  cmp     [rsp+128h+var_6C], 2
0x1800c7c00  jnz     loc_1800C7FCC
0x1800c7c06  mov     [rsp+128h+var_48], 0
0x1800c7c12  mov     byte ptr [rsp+128h+var_40], 0
0x1800c7c1a  mov     [rsp+128h+Handle], 0
0x1800c7c23  mov     [rsp+128h+hKey], 0
0x1800c7c2c  mov     [rsp+128h+var_58], 0
0x1800c7c38  mov     qword ptr [rsp+128h+var_68], r13
0x1800c7c40  mov     [rsp+128h+var_60], r14
0x1800c7c48  lea     rdx, [rsp+128h+var_68]
0x1800c7c50  lea     rcx, [rsp+128h+var_48]
0x1800c7c58  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1800c7c5d  mov     rcx, [rsp+128h]; this
0x1800c7c65  test    eax, eax
0x1800c7c67  js      loc_1800C8129
0x1800c7c6d  lea     r9, [rsp+128h+Handle]; HKEY *
0x1800c7c72  mov     rdx, rdi; wchar_t *
0x1800c7c75  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800c7c7a  mov     ebx, eax
0x1800c7c7c  test    eax, eax
0x1800c7c7e  jns     short loc_1800C7CD9
0x1800c7c80  mov     [rsp+128h+var_50], eax
0x1800c7c87  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7c8e  test    rcx, rcx
0x1800c7c91  jz      short loc_1800C7CD9
0x1800c7c93  lea     r9, aFailedOpeningC_0; "Failed opening CBS key with backup/rest"...
0x1800c7c9a  mov     r8d, r14d
0x1800c7c9d  xor     edx, edx
0x1800c7c9f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7ca4  lea     rax, [rsp+128h+var_50]
0x1800c7cac  mov     qword ptr [rsp+128h+var_90], rax
0x1800c7cb4  lea     rax, [rsp+128h+var_90]
0x1800c7cbc  mov     [rsp+128h+var_108], rax; int
0x1800c7cc1  lea     r9, asc_1802C6678; ": {}"
0x1800c7cc8  mov     r8d, r14d
0x1800c7ccb  mov     dl, 1
0x1800c7ccd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7cd4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7cd9  mov     rcx, [rsp+128h]; this
0x1800c7ce1  test    ebx, ebx
0x1800c7ce3  js      loc_1800C813D
0x1800c7ce9  mov     [rsp+128h+var_80], r15
0x1800c7cf1  mov     r15, [rsp+128h+Handle]
0x1800c7cf6  lea     rdx, aPostponeonline; "PostponeOnlineActions"
0x1800c7cfd  mov     rcx, r15; hKey
0x1800c7d00  call    cs:__imp_RegDeleteValueW
0x1800c7d07  nop     dword ptr [rax+rax+00h]
0x1800c7d0c  mov     ebx, eax
0x1800c7d0e  cmp     eax, 5
0x1800c7d11  jnz     short loc_1800C7D25
0x1800c7d13  mov     rcx, r15; Handle
0x1800c7d16  call    ?DumpHandleInfo@@YAXPEAUHKEY__@@@Z; DumpHandleInfo(HKEY__ *)
0x1800c7d1b  mov     rcx, r15; hKey
0x1800c7d1e  call    ?DumpKeySecurityInfo@@YAXPEAUHKEY__@@@Z; DumpKeySecurityInfo(HKEY__ *)
0x1800c7d23  jmp     short loc_1800C7D2D
0x1800c7d25  test    ebx, ebx
0x1800c7d27  jz      loc_1800C7E1A
0x1800c7d2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7d34  test    rcx, rcx
0x1800c7d37  jz      short loc_1800C7D9D
0x1800c7d39  lea     rax, [rsp+128h+var_80]
  ... truncated ...
```
