# CDeviceInfo::PopulateHotPatchEligibility(DeviceContext *)

- ea: `0x18008f7b8`
- end: `0x180090015`
- name: `?PopulateHotPatchEligibility@CDeviceInfo@@AEAAJPEAVDeviceContext@@@Z`
- size: `2141`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008aff4`

## callees

- `0x1800031d0`
- `0x180007f68`
- `0x180009750`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b9e4`
- `0x180022a18`
- `0x1800296a4`
- `0x180067094`
- `0x180081668`
- `0x1800818d0`
- `0x18008716c`
- `0x180088ef0`
- `0x18008f7b8`
- `0x180112454`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18008fdec`
- `ntdll!NtQuerySystemInformation` at `0x18008fdec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008faa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ffd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008faa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ffd7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008fa8e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008fc1e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008fa8e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008fc1e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008fb34`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008fbe9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008ffc7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008fb34`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008fbe9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18008ffc7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18008fa63`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18008fa63`

## string_xrefs

- `0x18008fabe`: `arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.`
- `0x18008f89c`: `EnableVirtualizationBasedSecurity`
- `0x18008f811`: `HotPatchReadiness`
- `0x18008f935`: `HotPatchReadiness`
- `0x18008f9aa`: `HotPatchReadiness`
- `0x18008ff54`: `HotPatchReadiness`
- `0x18008ff90`: `HotPatchReadiness`
- `0x18008f9f3`: `arbiter: Failed to get EnableVirtualizationBasedSecurity value.`
- `0x18008f8c6`: `arbiter: EnableVirtualizationBasedSecurity = {0}`
- `0x18008fc14`: `GetSystemConfiguredForHotPatchStatus`
- `0x18008fb8d`: `arbiter: failed to query GetSystemReadyForHotPatchStatus`
- `0x18008fa84`: `GetSystemReadyForHotPatchStatus`
- `0x18008fa5c`: `hotpatchutil.dll`
- `0x18008fcdd`: `arbiter: failed to query GetSystemConfiguredForHotPatchStatus from hotpatchutil`
- `0x18008fc4e`: `arbiter: failed to get proc address for GetSystemConfiguredForHotPatchStatus.`
- `0x18008fec1`: `arbiter: failed to query GetSystemConfiguredForHotPatchReadinessStatus`
- `0x18008fe2e`: `arbiter: failed to query GetSystemHotPatchReadinessStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CDeviceInfo::PopulateHotPatchEligibility(CDeviceInfo *this, struct DeviceContext *a2)
{
  unsigned int v4; // esi
  int RegValue; // edi
  __int64 v6; // rdx
  HMODULE Library; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // r14d
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // rdx
  __int64 v19; // rdx
  FARPROC v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rdx
  NTSTATUS v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  int SystemConfiguredHotPatchReadinessStatus; // eax
  int v33; // edx
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rdx
  __int128 *p_SystemInformation; // [rsp+20h] [rbp-60h]
  void *v38; // [rsp+20h] [rbp-60h]
  char v39; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v40[7]; // [rsp+41h] [rbp-3Fh] BYREF
  __int128 SystemInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v42; // [rsp+58h] [rbp-28h]
  int v43; // [rsp+68h] [rbp-18h] BYREF
  int v44; // [rsp+6Ch] [rbp-14h] BYREF
  ULONG ReturnLength[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  SystemInformation = 0;
  v42 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
  CDeviceInfo::AddValuePair(this, &SystemInformation, 0);
  std::wstring::~wstring(&SystemInformation);
  SystemInformation = 0;
  v42 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
  CDeviceInfo::AddValuePair(this, &SystemInformation, 0);
  std::wstring::~wstring(&SystemInformation);
  if ( *(_BYTE *)a2 )
  {
    v43 = 0;
    v38 = &v43;
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
        v44 = RegValue;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "arbiter: Failed to get EnableVirtualizationBasedSecurity value.");
          *(_QWORD *)ReturnLength = &v44;
          v38 = ReturnLength;
          LOBYTE(v6) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v6,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93E,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
          (const char *)(unsigned int)RegValue,
          (int)v38);
        return (unsigned int)RegValue;
      }
    }
    else
    {
      LogAdapter::TraceInfo<unsigned long>("arbiter: EnableVirtualizationBasedSecurity = {0}", &v43);
      if ( v43 == 1 )
      {
        LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility in offline mode.");
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
        std::wstring::~wstring(&SystemInformation);
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
      }
      else
      {
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
        std::wstring::~wstring(&SystemInformation);
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
      }
      std::wstring::~wstring(&SystemInformation);
      return 0;
    }
    return v4;
  }
  Library = LoadLibraryExW(L"hotpatchutil.dll", 0, 0x800u);
  v9 = Library;
  if ( !Library )
    goto LABEL_52;
  ProcAddress = GetProcAddress(Library, "GetSystemReadyForHotPatchStatus");
  if ( ProcAddress )
  {
    v43 = 0;
    v16 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v43);
    v17 = v16;
    if ( v16 < 0 )
    {
      ReturnLength[0] = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "arbiter: failed to query GetSystemReadyForHotPatchStatus");
        *(_QWORD *)&SystemInformation = ReturnLength;
        p_SystemInformation = &SystemInformation;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v18,
          3,
          ": {}");
      }
      v19 = 2386;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
        (const char *)v17,
        (int)p_SystemInformation);
      goto LABEL_30;
    }
    v20 = GetProcAddress(v9, "GetSystemConfiguredForHotPatchStatus");
    if ( !v20 )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "arbiter: failed to get proc address for GetSystemConfiguredForHotPatchStatus.");
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        else
          v22 = LastError;
        ReturnLength[0] = v22;
        *(_QWORD *)&SystemInformation = ReturnLength;
        p_SystemInformation = &SystemInformation;
        LOBYTE(v21) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v21,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v14 = 2395;
        goto LABEL_21;
      }
      goto LABEL_71;
    }
    v44 = 0;
    v23 = ((__int64 (__fastcall *)(int *))v20)(&v44);
    v17 = v23;
    if ( v23 < 0 )
    {
      ReturnLength[0] = v23;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "arbiter: failed to query GetSystemConfiguredForHotPatchStatus from hotpatchutil");
        *(_QWORD *)&SystemInformation = ReturnLength;
        p_SystemInformation = &SystemInformation;
        LOBYTE(v27) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v27,
          3,
          ": {}");
      }
      v19 = 2399;
      goto LABEL_29;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<enum PreCheckStatus,enum HPConfiguredStatus>(
        LogAdapter::g_Logger,
        v24,
        v25,
        v26,
        (__int64)&v43,
        (__int64)&v44);
    if ( v43 == 1 && v44 == 1 )
    {
      LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility from hotpatchutil.");
      SystemInformation = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
      CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
    }
    else
    {
      SystemInformation = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
      CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
    }
    std::wstring::~wstring(&SystemInformation);
LABEL_52:
    v39 = 0;
    SystemInformation = 0;
    ReturnLength[0] = 0;
    v28 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, ReturnLength);
    if ( v28 >= 0 )
    {
      v39 = SystemInformation & 1;
    }
    else
    {
      v29 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x8C6,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
              (const char *)(unsigned int)v28,
              (int)p_SystemInformation);
      v17 = v29;
      if ( v29 < 0 )
      {
        v44 = v29;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "arbiter: failed to query GetSystemHotPatchReadinessStatus");
          *(_QWORD *)&SystemInformation = &v44;
          p_SystemInformation = &SystemInformation;
          LOBYTE(v30) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v30,
            3,
            ": {}");
        }
        v31 = 2416;
        goto LABEL_57;
      }
    }
    v40[0] = 0;
    SystemConfiguredHotPatchReadinessStatus = GetSystemConfiguredHotPatchReadinessStatus(v40);
    v17 = SystemConfiguredHotPatchReadinessStatus;
    if ( SystemConfiguredHotPatchReadinessStatus >= 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<bool,bool>(LogAdapter::g_Logger, v33, v34, v35, (__int64)&v39, (__int64)v40);
      if ( v39 && v40[0] )
      {
        LogAdapter::TraceInfo<>("arbiter: Populating HotPatch Eligibility.");
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"1");
      }
      else
      {
        SystemInformation = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&SystemInformation);
        CDeviceInfo::AddValuePair(this, &SystemInformation, L"0");
      }
      std::wstring::~wstring(&SystemInformation);
      if ( !v9 )
        return 0;
      goto LABEL_71;
    }
    ReturnLength[0] = SystemConfiguredHotPatchReadinessStatus;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "arbiter: failed to query GetSystemConfiguredForHotPatchReadinessStatus");
      *(_QWORD *)&SystemInformation = ReturnLength;
      p_SystemInformation = &SystemInformation;
      LOBYTE(v36) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v36,
        3,
        ": {}");
    }
    v31 = 2420;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)v17,
      (int)p_SystemInformation);
    if ( !v9 )
      return v17;
LABEL_30:
    if ( !FreeLibrary(v9) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return v17;
  }
  LastError = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.");
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = LastError;
    ReturnLength[0] = v13;
    *(_QWORD *)&SystemInformation = ReturnLength;
    p_SystemInformation = &SystemInformation;
    LOBYTE(v12) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v12,
      3,
      ": {0}");
  }
  if ( !LastError )
  {
LABEL_71:
    if ( !FreeLibrary(v9) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return 0;
  }
  v14 = 2382;
LABEL_21:
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
          (const char *)(unsigned int)LastError,
          (unsigned int)p_SystemInformation);
  if ( !FreeLibrary(v9) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return v15;
}

```

## disassembly

```asm
0x18008f7b8  mov     rax, rsp
0x18008f7bb  push    rbp
0x18008f7bc  push    rdi
0x18008f7bd  push    r12
0x18008f7bf  push    r13
0x18008f7c1  push    r14
0x18008f7c3  mov     rbp, rsp
0x18008f7c6  sub     rsp, 80h
0x18008f7cd  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFEh
0x18008f7d5  mov     [rax+18h], rbx
0x18008f7d9  mov     [rax+20h], rsi
0x18008f7dd  mov     rax, cs:__security_cookie
0x18008f7e4  xor     rax, rsp
0x18008f7e7  mov     [rbp+var_8], rax
0x18008f7eb  mov     rdi, rdx
0x18008f7ee  mov     rbx, rcx
0x18008f7f1  mov     [rbp+var_50], 0
0x18008f7f9  xorps   xmm0, xmm0
0x18008f7fc  movups  [rbp+SystemInformation], xmm0
0x18008f800  xorps   xmm1, xmm1
0x18008f803  movdqu  [rbp+var_28], xmm1
0x18008f808  mov     r14d, 11h
0x18008f80e  mov     r8d, r14d
0x18008f811  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x18008f818  lea     rcx, [rbp+SystemInformation]
0x18008f81c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f821  nop
0x18008f822  xor     r8d, r8d
0x18008f825  lea     rdx, [rbp+SystemInformation]
0x18008f829  mov     rcx, rbx
0x18008f82c  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f831  nop
0x18008f832  lea     rcx, [rbp+SystemInformation]; void *
0x18008f836  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f83b  xorps   xmm0, xmm0
0x18008f83e  movups  [rbp+SystemInformation], xmm0
0x18008f842  xorps   xmm1, xmm1
0x18008f845  movdqu  [rbp+var_28], xmm1
0x18008f84a  lea     r12d, [r14-1]
0x18008f84e  mov     r8d, r12d
0x18008f851  lea     r13, aHotpatcheligib; "HotPatchEligible"
0x18008f858  mov     rdx, r13
0x18008f85b  lea     rcx, [rbp+SystemInformation]
0x18008f85f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f864  nop
0x18008f865  xor     r8d, r8d
0x18008f868  lea     rdx, [rbp+SystemInformation]
0x18008f86c  mov     rcx, rbx
0x18008f86f  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f874  nop
0x18008f875  lea     rcx, [rbp+SystemInformation]; void *
0x18008f879  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f87e  cmp     byte ptr [rdi], 0
0x18008f881  jz      loc_18008FA54
0x18008f887  mov     [rbp+var_18], 0
0x18008f88e  mov     byte ptr [rsp+80h+var_58], 0
0x18008f893  lea     rax, [rbp+var_18]
0x18008f897  mov     qword ptr [rsp+80h+var_60], rax
0x18008f89c  lea     r9, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x18008f8a3  lea     r8, aCurrentcontrol_2; "CurrentControlSet\\Control\\DeviceGuard"
0x18008f8aa  lea     esi, [r14-10h]
0x18008f8ae  mov     edx, esi
0x18008f8b0  mov     rcx, rdi
0x18008f8b3  call    ?GetRegValue@DeviceContext@@QEBAJW4RegistryHive@1@PEB_W1PEAK_N@Z; DeviceContext::GetRegValue(DeviceContext::RegistryHive,wchar_t const *,wchar_t const *,ulong *,bool)
0x18008f8b8  mov     edi, eax
0x18008f8ba  test    eax, eax
0x18008f8bc  js      loc_18008F9DC
0x18008f8c2  lea     rdx, [rbp+var_18]
0x18008f8c6  lea     rcx, aArbiterEnablev; "arbiter: EnableVirtualizationBasedSecur"...
0x18008f8cd  call    ??$TraceInfo@K@LogAdapter@@YAXQEBDAEBK@Z; LogAdapter::TraceInfo<ulong>(char const * const,ulong const &)
0x18008f8d2  cmp     [rbp+var_18], esi
0x18008f8d5  jnz     loc_18008F95C
0x18008f8db  lea     rcx, aArbiterPopulat_1; "arbiter: Populating HotPatch Eligibilit"...
0x18008f8e2  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18008f8e7  xorps   xmm0, xmm0
0x18008f8ea  movups  [rbp+SystemInformation], xmm0
0x18008f8ee  xorps   xmm1, xmm1
0x18008f8f1  movdqu  [rbp+var_28], xmm1
0x18008f8f6  mov     r8d, r12d
0x18008f8f9  mov     rdx, r13
0x18008f8fc  lea     rcx, [rbp+SystemInformation]
0x18008f900  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f905  nop
0x18008f906  lea     r8, a1; "1"
0x18008f90d  lea     rdx, [rbp+SystemInformation]
0x18008f911  mov     rcx, rbx
0x18008f914  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f919  nop
0x18008f91a  lea     rcx, [rbp+SystemInformation]; void *
0x18008f91e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f923  xorps   xmm0, xmm0
0x18008f926  movups  [rbp+SystemInformation], xmm0
0x18008f92a  xorps   xmm1, xmm1
0x18008f92d  movdqu  [rbp+var_28], xmm1
0x18008f932  mov     r8d, r14d
0x18008f935  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x18008f93c  lea     rcx, [rbp+SystemInformation]
0x18008f940  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f945  nop
0x18008f946  lea     r8, a1; "1"
0x18008f94d  lea     rdx, [rbp+SystemInformation]
0x18008f951  mov     rcx, rbx
0x18008f954  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f959  nop
0x18008f95a  jmp     short loc_18008F9CF
0x18008f95c  xorps   xmm0, xmm0
0x18008f95f  movups  [rbp+SystemInformation], xmm0
0x18008f963  xorps   xmm1, xmm1
0x18008f966  movdqu  [rbp+var_28], xmm1
0x18008f96b  mov     r8, r12
0x18008f96e  mov     rdx, r13
0x18008f971  lea     rcx, [rbp+SystemInformation]
0x18008f975  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f97a  nop
0x18008f97b  lea     r8, a0_1; "0"
0x18008f982  lea     rdx, [rbp+SystemInformation]
0x18008f986  mov     rcx, rbx
0x18008f989  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f98e  nop
0x18008f98f  lea     rcx, [rbp+SystemInformation]; void *
0x18008f993  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f998  xorps   xmm0, xmm0
0x18008f99b  movups  [rbp+SystemInformation], xmm0
0x18008f99f  xorps   xmm1, xmm1
0x18008f9a2  movdqu  [rbp+var_28], xmm1
0x18008f9a7  mov     r8, r14
0x18008f9aa  lea     rdx, aHotpatchreadin; "HotPatchReadiness"
0x18008f9b1  lea     rcx, [rbp+SystemInformation]
0x18008f9b5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008f9ba  nop
0x18008f9bb  lea     r8, a0_1; "0"
0x18008f9c2  lea     rdx, [rbp+SystemInformation]
0x18008f9c6  mov     rcx, rbx
0x18008f9c9  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x18008f9ce  nop
0x18008f9cf  lea     rcx, [rbp+SystemInformation]; void *
0x18008f9d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f9d8  xor     esi, esi
0x18008f9da  jmp     short loc_18008FA4D
0x18008f9dc  cmp     edi, 0D0000034h
0x18008f9e2  jz      short loc_18008FA4D
0x18008f9e4  mov     [rbp+var_14], edi
0x18008f9e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008f9ee  test    rcx, rcx
0x18008f9f1  jz      short loc_18008FA33
0x18008f9f3  lea     r9, aArbiterFailedT; "arbiter: Failed to get EnableVirtualiza"...
0x18008f9fa  mov     ebx, 3
0x18008f9ff  mov     r8d, ebx
0x18008fa02  xor     edx, edx
0x18008fa04  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008fa09  lea     rax, [rbp+var_14]
0x18008fa0d  mov     qword ptr [rbp+ReturnLength], rax
0x18008fa11  lea     rax, [rbp+ReturnLength]
0x18008fa15  mov     qword ptr [rsp+80h+var_60], rax; int
0x18008fa1a  lea     r9, asc_1801CAFB4; ": {}"
0x18008fa21  mov     r8d, ebx
0x18008fa24  mov     dl, sil
0x18008fa27  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fa2e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008fa33  mov     rcx, [rbp+28h]; this
0x18008fa37  mov     r9d, edi; char *
0x18008fa3a  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18008fa41  mov     edx, 93Eh; void *
0x18008fa46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fa4b  mov     esi, edi
0x18008fa4d  mov     eax, esi
0x18008fa4f  jmp     loc_18008FFEC
0x18008fa54  xor     edx, edx; hFile
0x18008fa56  mov     r8d, 800h; dwFlags
0x18008fa5c  lea     rcx, aHotpatchutilDl; "hotpatchutil.dll"
0x18008fa63  call    cs:__imp_LoadLibraryExW
0x18008fa6a  nop     dword ptr [rax+rax+00h]
0x18008fa6f  mov     rdi, rax
0x18008fa72  mov     [rbp+var_50], rax
0x18008fa76  mov     esi, 1
0x18008fa7b  test    rax, rax
0x18008fa7e  jz      loc_18008FDCA
0x18008fa84  lea     rdx, aGetsystemready; "GetSystemReadyForHotPatchStatus"
0x18008fa8b  mov     rcx, rax; hModule
0x18008fa8e  call    cs:__imp_GetProcAddress
0x18008fa95  nop     dword ptr [rax+rax+00h]
0x18008fa9a  test    rax, rax
0x18008fa9d  jnz     loc_18008FB63
0x18008faa3  call    cs:__imp_GetLastError
0x18008faaa  nop     dword ptr [rax+rax+00h]
0x18008faaf  mov     r14d, eax
0x18008fab2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fab9  test    rcx, rcx
0x18008fabc  jz      short loc_18008FB12
0x18008fabe  lea     r9, aArbiterFailedT_22; "arbiter: failed to get proc address for"...
0x18008fac5  lea     ebx, [rsi+2]
0x18008fac8  mov     r8d, ebx
0x18008facb  xor     edx, edx
0x18008facd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008fad2  test    r14d, r14d
0x18008fad5  jg      short loc_18008FADC
0x18008fad7  mov     eax, r14d
0x18008fada  jmp     short loc_18008FAE5
0x18008fadc  movzx   eax, r14w
0x18008fae0  or      eax, 80070000h
0x18008fae5  mov     [rbp+ReturnLength], eax
0x18008fae8  lea     rax, [rbp+ReturnLength]
0x18008faec  mov     qword ptr [rbp+SystemInformation], rax
0x18008faf0  lea     rax, [rbp+SystemInformation]
0x18008faf4  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x18008faf9  lea     r9, a0; ": {0}"
0x18008fb00  mov     r8d, ebx
0x18008fb03  mov     dl, sil
0x18008fb06  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fb0d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008fb12  test    r14d, r14d
0x18008fb15  jz      short loc_18008FB5E
0x18008fb17  mov     edx, 94Eh; void *
0x18008fb1c  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18008fb23  mov     r9d, r14d; char *
0x18008fb26  mov     rcx, [rbp+28h]; this
0x18008fb2a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008fb2f  mov     ebx, eax
0x18008fb31  mov     rcx, rdi; hLibModule
0x18008fb34  call    cs:__imp_FreeLibrary
0x18008fb3b  nop     dword ptr [rax+rax+00h]
0x18008fb40  test    eax, eax
0x18008fb42  jnz     short loc_18008FB57
0x18008fb44  call    cs:__imp_GetLastError
0x18008fb4b  nop     dword ptr [rax+rax+00h]
0x18008fb50  mov     ecx, 7
0x18008fb55  int     29h; Win8: RtlFailFast(ecx)
0x18008fb57  mov     eax, ebx
0x18008fb59  jmp     loc_18008FFEC
0x18008fb5e  jmp     loc_18008FFC4
0x18008fb63  mov     [rbp+var_18], 0
0x18008fb6a  lea     rcx, [rbp+var_18]
0x18008fb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb73  mov     r14d, eax
0x18008fb76  test    eax, eax
0x18008fb78  jns     loc_18008FC14
0x18008fb7e  mov     [rbp+ReturnLength], eax
0x18008fb81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fb88  test    rcx, rcx
0x18008fb8b  jz      short loc_18008FBCD
0x18008fb8d  lea     r9, aArbiterFailedT_19; "arbiter: failed to query GetSystemReady"...
0x18008fb94  mov     ebx, 3
0x18008fb99  mov     r8d, ebx
0x18008fb9c  xor     edx, edx
0x18008fb9e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008fba3  lea     rax, [rbp+ReturnLength]
0x18008fba7  mov     qword ptr [rbp+SystemInformation], rax
0x18008fbab  lea     rax, [rbp+SystemInformation]
0x18008fbaf  mov     qword ptr [rsp+80h+var_60], rax; int
0x18008fbb4  lea     r9, asc_1801CAFB4; ": {}"
0x18008fbbb  mov     r8d, ebx
0x18008fbbe  mov     dl, sil
0x18008fbc1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fbc8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008fbcd  mov     edx, 952h; void *
0x18008fbd2  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18008fbd9  mov     r9d, r14d; char *
0x18008fbdc  mov     rcx, [rbp+28h]; this
0x18008fbe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fbe5  nop
0x18008fbe6  mov     rcx, rdi; hLibModule
0x18008fbe9  call    cs:__imp_FreeLibrary
0x18008fbf0  nop     dword ptr [rax+rax+00h]
0x18008fbf5  test    eax, eax
0x18008fbf7  jnz     short loc_18008FC0C
0x18008fbf9  call    cs:__imp_GetLastError
0x18008fc00  nop     dword ptr [rax+rax+00h]
0x18008fc05  mov     ecx, 7
0x18008fc0a  int     29h; Win8: RtlFailFast(ecx)
0x18008fc0c  mov     eax, r14d
0x18008fc0f  jmp     loc_18008FFEC
0x18008fc14  lea     rdx, aGetsystemconfi; "GetSystemConfiguredForHotPatchStatus"
0x18008fc1b  mov     rcx, rdi; hModule
0x18008fc1e  call    cs:__imp_GetProcAddress
0x18008fc25  nop     dword ptr [rax+rax+00h]
0x18008fc2a  test    rax, rax
0x18008fc2d  jnz     loc_18008FCB7
0x18008fc33  call    cs:__imp_GetLastError
0x18008fc3a  nop     dword ptr [rax+rax+00h]
0x18008fc3f  mov     r14d, eax
0x18008fc42  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008fc49  test    rcx, rcx
0x18008fc4c  jz      short loc_18008FCA4
0x18008fc4e  lea     r9, aArbiterFailedT_13; "arbiter: failed to get proc address for"...
0x18008fc55  mov     ebx, 3
0x18008fc5a  mov     r8d, ebx
0x18008fc5d  xor     edx, edx
0x18008fc5f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008fc64  test    r14d, r14d
0x18008fc67  jg      short loc_18008FC6E
0x18008fc69  mov     eax, r14d
0x18008fc6c  jmp     short loc_18008FC77
0x18008fc6e  movzx   eax, r14w
0x18008fc72  or      eax, 80070000h
0x18008fc77  mov     [rbp+ReturnLength], eax
0x18008fc7a  lea     rax, [rbp+ReturnLength]
0x18008fc7e  mov     qword ptr [rbp+SystemInformation], rax
0x18008fc82  lea     rax, [rbp+SystemInformation]
0x18008fc86  mov     qword ptr [rsp+80h+var_60], rax
0x18008fc8b  lea     r9, a0; ": {0}"
  ... truncated ...
```
