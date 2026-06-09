# CDeviceInfo::PopulateHotPatchEligibility(DeviceContext *)

- ea: `0x1800d9b90`
- end: `0x1800da3ed`
- name: `?PopulateHotPatchEligibility@CDeviceInfo@@AEAAJPEAVDeviceContext@@@Z`
- size: `2141`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d53c8`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18001270c`
- `0x18001273c`
- `0x180012d94`
- `0x180023b20`
- `0x18008b38c`
- `0x18008b3bc`
- `0x18008b3ec`
- `0x1800cb3b0`
- `0x1800cb618`
- `0x1800d1518`
- `0x1800d308c`
- `0x1800d9b90`
- `0x180175618`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800da1c4`
- `ntdll!NtQuerySystemInformation` at `0x1800da1c4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d9e66`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d9ff6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d9e66`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800d9ff6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d9f0c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d9fc1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800da39f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d9f0c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800d9fc1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800da39f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d9e3b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d9e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da3af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da3af`

## string_xrefs

- `0x1800d9e96`: `arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.`
- `0x1800d9be9`: `HotPatchReadiness`
- `0x1800d9d0d`: `HotPatchReadiness`
- `0x1800d9d82`: `HotPatchReadiness`
- `0x1800da32c`: `HotPatchReadiness`
- `0x1800da368`: `HotPatchReadiness`
- `0x1800d9c74`: `EnableVirtualizationBasedSecurity`
- `0x1800d9c9e`: `arbiter: EnableVirtualizationBasedSecurity = {0}`
- `0x1800d9dcb`: `arbiter: Failed to get EnableVirtualizationBasedSecurity value.`
- `0x1800d9e5c`: `GetSystemReadyForHotPatchStatus`
- `0x1800d9e34`: `hotpatchutil.dll`
- `0x1800d9fec`: `GetSystemConfiguredForHotPatchStatus`
- `0x1800d9f65`: `arbiter: failed to query GetSystemReadyForHotPatchStatus`
- `0x1800da0b5`: `arbiter: failed to query GetSystemConfiguredForHotPatchStatus from hotpatchutil`
- `0x1800da026`: `arbiter: failed to get proc address for GetSystemConfiguredForHotPatchStatus.`
- `0x1800da299`: `arbiter: failed to query GetSystemConfiguredForHotPatchReadinessStatus`
- `0x1800da206`: `arbiter: failed to query GetSystemHotPatchReadinessStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CDeviceInfo::PopulateHotPatchEligibility(CDeviceInfo *this, struct DeviceContext *a2)
{
  unsigned int v4; // esi
  int RegValue; // edi
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // r14d
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // r14d
  __int64 v16; // rdx
  FARPROC v17; // rax
  unsigned int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  NTSTATUS v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int SystemConfiguredHotPatchReadinessStatus; // eax
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // [rsp+20h] [rbp-60h]
  int *v31; // [rsp+20h] [rbp-60h]
  char v32; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v33[7]; // [rsp+41h] [rbp-3Fh] BYREF
  __int128 SystemInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v35; // [rsp+58h] [rbp-28h]
  int v36; // [rsp+68h] [rbp-18h] BYREF
  int v37; // [rsp+6Ch] [rbp-14h] BYREF
  ULONG ReturnLength[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  SystemInformation = 0;
  v35 = 0;
  std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchReadiness", 0x11u);
  CDeviceInfo::AddValuePair(this, &SystemInformation, 0);
  std::wstring::~wstring(&SystemInformation);
  SystemInformation = 0;
  v35 = 0;
  std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchEligible", 0x10u);
  CDeviceInfo::AddValuePair(this, &SystemInformation, 0);
  std::wstring::~wstring(&SystemInformation);
  if ( *(_BYTE *)a2 )
  {
    v36 = 0;
    v31 = &v36;
    v4 = 1;
    RegValue = DeviceContext::GetRegValue(
                 a2,
                 1,
                 L"CurrentControlSet\\Control\\DeviceGuard",
                 L"EnableVirtualizationBasedSecurity");
    if ( RegValue < 0 )
    {
      if ( RegValue != -805306316 )
      {
        v37 = RegValue;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: Failed to get EnableVirtualizationBasedSecurity value.");
          *(_QWORD *)ReturnLength = &v37;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)ReturnLength);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93E,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
          (const char *)(unsigned int)RegValue,
          (int)v31);
        return (unsigned int)RegValue;
      }
    }
    else
    {
      LogAdapter::TraceInfo<unsigned long>("arbiter: EnableVirtualizationBasedSecurity = {0}", &v36);
      if ( v36 == 1 )
      {
        LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility in offline mode.");
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchEligible", 0x10u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
        std::wstring::~wstring(&SystemInformation);
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchReadiness", 0x11u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
      }
      else
      {
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchEligible", 0x10u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
        std::wstring::~wstring(&SystemInformation);
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchReadiness", 0x11u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
      }
      std::wstring::~wstring(&SystemInformation);
      return 0;
    }
    return v4;
  }
  Library = LoadLibraryExW(L"hotpatchutil.dll", 0, 0x800u);
  v8 = Library;
  if ( !Library )
    goto LABEL_52;
  ProcAddress = GetProcAddress(Library, "GetSystemReadyForHotPatchStatus");
  if ( ProcAddress )
  {
    v36 = 0;
    v14 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v36);
    v15 = v14;
    if ( v14 < 0 )
    {
      ReturnLength[0] = v14;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to query GetSystemReadyForHotPatchStatus");
        *(_QWORD *)&SystemInformation = ReturnLength;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&SystemInformation);
      }
      v16 = 2386;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
        (const char *)v15,
        v30);
      goto LABEL_30;
    }
    v17 = GetProcAddress(v8, "GetSystemConfiguredForHotPatchStatus");
    if ( !v17 )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to get proc address for GetSystemConfiguredF"
                                                            "orHotPatchStatus.");
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        ReturnLength[0] = v18;
        *(_QWORD *)&SystemInformation = ReturnLength;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&SystemInformation);
      }
      if ( LastError )
      {
        v12 = 2395;
        goto LABEL_21;
      }
      goto LABEL_71;
    }
    v37 = 0;
    v19 = ((__int64 (__fastcall *)(int *))v17)(&v37);
    v15 = v19;
    if ( v19 < 0 )
    {
      ReturnLength[0] = v19;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to query GetSystemConfiguredForHotPatchStatu"
                                                            "s from hotpatchutil");
        *(_QWORD *)&SystemInformation = ReturnLength;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&SystemInformation);
      }
      v16 = 2399;
      goto LABEL_29;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<enum PreCheckStatus,enum HPConfiguredStatus>(
        *(__int64 *)&LogAdapter::g_Logger,
        v20,
        v21,
        v22,
        (__int64)&v36,
        (__int64)&v37);
    if ( v36 == 1 && v37 == 1 )
    {
      LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility from hotpatchutil.");
      SystemInformation = 0;
      v35 = 0;
      std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchEligible", 0x10u);
      CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
    }
    else
    {
      SystemInformation = 0;
      v35 = 0;
      std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchEligible", 0x10u);
      CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
    }
    std::wstring::~wstring(&SystemInformation);
LABEL_52:
    v32 = 0;
    SystemInformation = 0;
    ReturnLength[0] = 0;
    v23 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, ReturnLength);
    if ( v23 >= 0 )
    {
      v32 = SystemInformation & 1;
    }
    else
    {
      v24 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x8C6,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
              (const char *)(unsigned int)v23,
              v30);
      v15 = v24;
      if ( v24 < 0 )
      {
        v37 = v24;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to query GetSystemHotPatchReadinessStatus");
          *(_QWORD *)&SystemInformation = &v37;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&SystemInformation);
        }
        v25 = 2416;
        goto LABEL_57;
      }
    }
    v33[0] = 0;
    SystemConfiguredHotPatchReadinessStatus = GetSystemConfiguredHotPatchReadinessStatus(v33);
    v15 = SystemConfiguredHotPatchReadinessStatus;
    if ( SystemConfiguredHotPatchReadinessStatus >= 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<bool,bool>(LogAdapter::g_Logger, v27, v28, v29, (__int64)&v32, (__int64)v33);
      if ( v32 && v33[0] )
      {
        LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility.");
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchReadiness", 0x11u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
      }
      else
      {
        SystemInformation = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>((__int64)&SystemInformation, L"HotPatchReadiness", 0x11u);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
      }
      std::wstring::~wstring(&SystemInformation);
      if ( !v8 )
        return 0;
      goto LABEL_71;
    }
    ReturnLength[0] = SystemConfiguredHotPatchReadinessStatus;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to query GetSystemConfiguredForHotPatchReadinessStatus");
      *(_QWORD *)&SystemInformation = ReturnLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&SystemInformation);
    }
    v25 = 2420;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)v15,
      v30);
    if ( !v8 )
      return v15;
LABEL_30:
    if ( !FreeLibrary(v8) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return v15;
  }
  LastError = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.");
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    else
      v11 = LastError;
    ReturnLength[0] = v11;
    *(_QWORD *)&SystemInformation = ReturnLength;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)&SystemInformation);
  }
  if ( !LastError )
  {
LABEL_71:
    if ( !FreeLibrary(v8) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return 0;
  }
  v12 = 2382;
LABEL_21:
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
          (const char *)(unsigned int)LastError,
          v30);
  if ( !FreeLibrary(v8) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return v13;
}

```

## disassembly

```asm
0x1800d9b90  mov     rax, rsp
0x1800d9b93  push    rbp
0x1800d9b94  push    rdi
0x1800d9b95  push    r12
0x1800d9b97  push    r13
0x1800d9b99  push    r14
0x1800d9b9b  mov     rbp, rsp
0x1800d9b9e  sub     rsp, 80h
0x1800d9ba5  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFEh
0x1800d9bad  mov     [rax+18h], rbx
0x1800d9bb1  mov     [rax+20h], rsi
0x1800d9bb5  mov     rax, cs:__security_cookie
0x1800d9bbc  xor     rax, rsp
0x1800d9bbf  mov     [rbp+var_8], rax
0x1800d9bc3  mov     rdi, rdx
0x1800d9bc6  mov     rbx, rcx
0x1800d9bc9  mov     [rbp+var_50], 0
0x1800d9bd1  xorps   xmm0, xmm0
0x1800d9bd4  movups  [rbp+SystemInformation], xmm0
0x1800d9bd8  xorps   xmm1, xmm1
0x1800d9bdb  movdqu  [rbp+var_28], xmm1
0x1800d9be0  mov     r14d, 11h
0x1800d9be6  mov     r8d, r14d
0x1800d9be9  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x1800d9bf0  lea     rcx, [rbp+SystemInformation]
0x1800d9bf4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9bf9  nop
0x1800d9bfa  xor     r8d, r8d
0x1800d9bfd  lea     rdx, [rbp+SystemInformation]
0x1800d9c01  mov     rcx, rbx
0x1800d9c04  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9c09  nop
0x1800d9c0a  lea     rcx, [rbp+SystemInformation]; void *
0x1800d9c0e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9c13  xorps   xmm0, xmm0
0x1800d9c16  movups  [rbp+SystemInformation], xmm0
0x1800d9c1a  xorps   xmm1, xmm1
0x1800d9c1d  movdqu  [rbp+var_28], xmm1
0x1800d9c22  lea     r12d, [r14-1]
0x1800d9c26  mov     r8d, r12d
0x1800d9c29  lea     r13, aHotpatcheligib; "HotPatchEligible"
0x1800d9c30  mov     rdx, r13
0x1800d9c33  lea     rcx, [rbp+SystemInformation]
0x1800d9c37  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9c3c  nop
0x1800d9c3d  xor     r8d, r8d
0x1800d9c40  lea     rdx, [rbp+SystemInformation]
0x1800d9c44  mov     rcx, rbx
0x1800d9c47  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9c4c  nop
0x1800d9c4d  lea     rcx, [rbp+SystemInformation]; void *
0x1800d9c51  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9c56  cmp     byte ptr [rdi], 0
0x1800d9c59  jz      loc_1800D9E2C
0x1800d9c5f  mov     [rbp+var_18], 0
0x1800d9c66  mov     byte ptr [rsp+80h+var_58], 0
0x1800d9c6b  lea     rax, [rbp+var_18]
0x1800d9c6f  mov     qword ptr [rsp+80h+var_60], rax
0x1800d9c74  lea     r9, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x1800d9c7b  lea     r8, aCurrentcontrol_2; "CurrentControlSet\\Control\\DeviceGuard"
0x1800d9c82  lea     esi, [r14-10h]
0x1800d9c86  mov     edx, esi
0x1800d9c88  mov     rcx, rdi
0x1800d9c8b  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x1800d9c90  mov     edi, eax
0x1800d9c92  test    eax, eax
0x1800d9c94  js      loc_1800D9DB4
0x1800d9c9a  lea     rdx, [rbp+var_18]
0x1800d9c9e  lea     rcx, aArbiterEnablev; "arbiter: EnableVirtualizationBasedSecur"...
0x1800d9ca5  call    ??$TraceInfo@K@LogAdapter@@YAXQEBDAEBK@Z; LogAdapter::TraceInfo<ulong>(char const * const,ulong const &)
0x1800d9caa  cmp     [rbp+var_18], esi
0x1800d9cad  jnz     loc_1800D9D34
0x1800d9cb3  lea     rcx, aArbiterPopulat_1; "arbiter: Populating HotPatch Eligibilit"...
0x1800d9cba  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800d9cbf  xorps   xmm0, xmm0
0x1800d9cc2  movups  [rbp+SystemInformation], xmm0
0x1800d9cc6  xorps   xmm1, xmm1
0x1800d9cc9  movdqu  [rbp+var_28], xmm1
0x1800d9cce  mov     r8d, r12d
0x1800d9cd1  mov     rdx, r13
0x1800d9cd4  lea     rcx, [rbp+SystemInformation]
0x1800d9cd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9cdd  nop
0x1800d9cde  lea     r8, a1; "1"
0x1800d9ce5  lea     rdx, [rbp+SystemInformation]
0x1800d9ce9  mov     rcx, rbx
0x1800d9cec  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9cf1  nop
0x1800d9cf2  lea     rcx, [rbp+SystemInformation]; void *
0x1800d9cf6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9cfb  xorps   xmm0, xmm0
0x1800d9cfe  movups  [rbp+SystemInformation], xmm0
0x1800d9d02  xorps   xmm1, xmm1
0x1800d9d05  movdqu  [rbp+var_28], xmm1
0x1800d9d0a  mov     r8d, r14d
0x1800d9d0d  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x1800d9d14  lea     rcx, [rbp+SystemInformation]
0x1800d9d18  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9d1d  nop
0x1800d9d1e  lea     r8, a1; "1"
0x1800d9d25  lea     rdx, [rbp+SystemInformation]
0x1800d9d29  mov     rcx, rbx
0x1800d9d2c  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9d31  nop
0x1800d9d32  jmp     short loc_1800D9DA7
0x1800d9d34  xorps   xmm0, xmm0
0x1800d9d37  movups  [rbp+SystemInformation], xmm0
0x1800d9d3b  xorps   xmm1, xmm1
0x1800d9d3e  movdqu  [rbp+var_28], xmm1
0x1800d9d43  mov     r8, r12
0x1800d9d46  mov     rdx, r13
0x1800d9d49  lea     rcx, [rbp+SystemInformation]
0x1800d9d4d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9d52  nop
0x1800d9d53  lea     r8, a0_1; "0"
0x1800d9d5a  lea     rdx, [rbp+SystemInformation]
0x1800d9d5e  mov     rcx, rbx
0x1800d9d61  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9d66  nop
0x1800d9d67  lea     rcx, [rbp+SystemInformation]; void *
0x1800d9d6b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9d70  xorps   xmm0, xmm0
0x1800d9d73  movups  [rbp+SystemInformation], xmm0
0x1800d9d77  xorps   xmm1, xmm1
0x1800d9d7a  movdqu  [rbp+var_28], xmm1
0x1800d9d7f  mov     r8, r14
0x1800d9d82  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x1800d9d89  lea     rcx, [rbp+SystemInformation]
0x1800d9d8d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d9d92  nop
0x1800d9d93  lea     r8, a0_1; "0"
0x1800d9d9a  lea     rdx, [rbp+SystemInformation]
0x1800d9d9e  mov     rcx, rbx
0x1800d9da1  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800d9da6  nop
0x1800d9da7  lea     rcx, [rbp+SystemInformation]; void *
0x1800d9dab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d9db0  xor     esi, esi
0x1800d9db2  jmp     short loc_1800D9E25
0x1800d9db4  cmp     edi, 0D0000034h
0x1800d9dba  jz      short loc_1800D9E25
0x1800d9dbc  mov     [rbp+var_14], edi
0x1800d9dbf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9dc6  test    rcx, rcx
0x1800d9dc9  jz      short loc_1800D9E0B
0x1800d9dcb  lea     r9, aArbiterFailedT; "arbiter: Failed to get EnableVirtualiza"...
0x1800d9dd2  mov     ebx, 3
0x1800d9dd7  mov     r8d, ebx
0x1800d9dda  xor     edx, edx
0x1800d9ddc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d9de1  lea     rax, [rbp+var_14]
0x1800d9de5  mov     qword ptr [rbp+ReturnLength], rax
0x1800d9de9  lea     rax, [rbp+ReturnLength]
0x1800d9ded  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800d9df2  lea     r9, asc_1802C6678; ": {}"
0x1800d9df9  mov     r8d, ebx
0x1800d9dfc  mov     dl, sil
0x1800d9dff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9e06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d9e0b  mov     rcx, [rbp+28h]; this
0x1800d9e0f  mov     r9d, edi; char *
0x1800d9e12  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800d9e19  mov     edx, 93Eh; void *
0x1800d9e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9e23  mov     esi, edi
0x1800d9e25  mov     eax, esi
0x1800d9e27  jmp     loc_1800DA3C4
0x1800d9e2c  xor     edx, edx; hFile
0x1800d9e2e  mov     r8d, 800h; dwFlags
0x1800d9e34  lea     rcx, aHotpatchutilDl; "hotpatchutil.dll"
0x1800d9e3b  call    cs:__imp_LoadLibraryExW
0x1800d9e42  nop     dword ptr [rax+rax+00h]
0x1800d9e47  mov     rdi, rax
0x1800d9e4a  mov     [rbp+var_50], rax
0x1800d9e4e  mov     esi, 1
0x1800d9e53  test    rax, rax
0x1800d9e56  jz      loc_1800DA1A2
0x1800d9e5c  lea     rdx, aGetsystemready; "GetSystemReadyForHotPatchStatus"
0x1800d9e63  mov     rcx, rax; hModule
0x1800d9e66  call    cs:__imp_GetProcAddress
0x1800d9e6d  nop     dword ptr [rax+rax+00h]
0x1800d9e72  test    rax, rax
0x1800d9e75  jnz     loc_1800D9F3B
0x1800d9e7b  call    cs:__imp_GetLastError
0x1800d9e82  nop     dword ptr [rax+rax+00h]
0x1800d9e87  mov     r14d, eax
0x1800d9e8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9e91  test    rcx, rcx
0x1800d9e94  jz      short loc_1800D9EEA
0x1800d9e96  lea     r9, aArbiterFailedT_22; "arbiter: failed to get proc address for"...
0x1800d9e9d  lea     ebx, [rsi+2]
0x1800d9ea0  mov     r8d, ebx
0x1800d9ea3  xor     edx, edx
0x1800d9ea5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d9eaa  test    r14d, r14d
0x1800d9ead  jg      short loc_1800D9EB4
0x1800d9eaf  mov     eax, r14d
0x1800d9eb2  jmp     short loc_1800D9EBD
0x1800d9eb4  movzx   eax, r14w
0x1800d9eb8  or      eax, 80070000h
0x1800d9ebd  mov     [rbp+ReturnLength], eax
0x1800d9ec0  lea     rax, [rbp+ReturnLength]
0x1800d9ec4  mov     qword ptr [rbp+SystemInformation], rax
0x1800d9ec8  lea     rax, [rbp+SystemInformation]
0x1800d9ecc  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x1800d9ed1  lea     r9, a0; ": {0}"
0x1800d9ed8  mov     r8d, ebx
0x1800d9edb  mov     dl, sil
0x1800d9ede  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9ee5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d9eea  test    r14d, r14d
0x1800d9eed  jz      short loc_1800D9F36
0x1800d9eef  mov     edx, 94Eh; void *
0x1800d9ef4  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800d9efb  mov     r9d, r14d; char *
0x1800d9efe  mov     rcx, [rbp+28h]; this
0x1800d9f02  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d9f07  mov     ebx, eax
0x1800d9f09  mov     rcx, rdi; hLibModule
0x1800d9f0c  call    cs:__imp_FreeLibrary
0x1800d9f13  nop     dword ptr [rax+rax+00h]
0x1800d9f18  test    eax, eax
0x1800d9f1a  jnz     short loc_1800D9F2F
0x1800d9f1c  call    cs:__imp_GetLastError
0x1800d9f23  nop     dword ptr [rax+rax+00h]
0x1800d9f28  mov     ecx, 7
0x1800d9f2d  int     29h; Win8: RtlFailFast(ecx)
0x1800d9f2f  mov     eax, ebx
0x1800d9f31  jmp     loc_1800DA3C4
0x1800d9f36  jmp     loc_1800DA39C
0x1800d9f3b  mov     [rbp+var_18], 0
0x1800d9f42  lea     rcx, [rbp+var_18]
0x1800d9f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f4b  mov     r14d, eax
0x1800d9f4e  test    eax, eax
0x1800d9f50  jns     loc_1800D9FEC
0x1800d9f56  mov     [rbp+ReturnLength], eax
0x1800d9f59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9f60  test    rcx, rcx
0x1800d9f63  jz      short loc_1800D9FA5
0x1800d9f65  lea     r9, aArbiterFailedT_19; "arbiter: failed to query GetSystemReady"...
0x1800d9f6c  mov     ebx, 3
0x1800d9f71  mov     r8d, ebx
0x1800d9f74  xor     edx, edx
0x1800d9f76  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d9f7b  lea     rax, [rbp+ReturnLength]
0x1800d9f7f  mov     qword ptr [rbp+SystemInformation], rax
0x1800d9f83  lea     rax, [rbp+SystemInformation]
0x1800d9f87  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800d9f8c  lea     r9, asc_1802C6678; ": {}"
0x1800d9f93  mov     r8d, ebx
0x1800d9f96  mov     dl, sil
0x1800d9f99  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9fa0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d9fa5  mov     edx, 952h; void *
0x1800d9faa  lea     r8, aOnecoreBaseSer_7; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800d9fb1  mov     r9d, r14d; char *
0x1800d9fb4  mov     rcx, [rbp+28h]; this
0x1800d9fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9fbd  nop
0x1800d9fbe  mov     rcx, rdi; hLibModule
0x1800d9fc1  call    cs:__imp_FreeLibrary
0x1800d9fc8  nop     dword ptr [rax+rax+00h]
0x1800d9fcd  test    eax, eax
0x1800d9fcf  jnz     short loc_1800D9FE4
0x1800d9fd1  call    cs:__imp_GetLastError
0x1800d9fd8  nop     dword ptr [rax+rax+00h]
0x1800d9fdd  mov     ecx, 7
0x1800d9fe2  int     29h; Win8: RtlFailFast(ecx)
0x1800d9fe4  mov     eax, r14d
0x1800d9fe7  jmp     loc_1800DA3C4
0x1800d9fec  lea     rdx, aGetsystemconfi; "GetSystemConfiguredForHotPatchStatus"
0x1800d9ff3  mov     rcx, rdi; hModule
0x1800d9ff6  call    cs:__imp_GetProcAddress
0x1800d9ffd  nop     dword ptr [rax+rax+00h]
0x1800da002  test    rax, rax
0x1800da005  jnz     loc_1800DA08F
0x1800da00b  call    cs:__imp_GetLastError
0x1800da012  nop     dword ptr [rax+rax+00h]
0x1800da017  mov     r14d, eax
0x1800da01a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800da021  test    rcx, rcx
0x1800da024  jz      short loc_1800DA07C
0x1800da026  lea     r9, aArbiterFailedT_13; "arbiter: failed to get proc address for"...
0x1800da02d  mov     ebx, 3
0x1800da032  mov     r8d, ebx
0x1800da035  xor     edx, edx
0x1800da037  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800da03c  test    r14d, r14d
0x1800da03f  jg      short loc_1800DA046
0x1800da041  mov     eax, r14d
0x1800da044  jmp     short loc_1800DA04F
0x1800da046  movzx   eax, r14w
0x1800da04a  or      eax, 80070000h
0x1800da04f  mov     [rbp+ReturnLength], eax
0x1800da052  lea     rax, [rbp+ReturnLength]
0x1800da056  mov     qword ptr [rbp+SystemInformation], rax
0x1800da05a  lea     rax, [rbp+SystemInformation]
0x1800da05e  mov     qword ptr [rsp+80h+var_60], rax
0x1800da063  lea     r9, a0; ": {0}"
  ... truncated ...
```
