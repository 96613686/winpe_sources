# SystemSettings::Accessibility::CRestartWindowsAfterBrailleFodInstallSetting::RestartMachine(void)

- ea: `0x180040c98`
- end: `0x180040ffd`
- name: `?RestartMachine@CRestartWindowsAfterBrailleFodInstallSetting@Accessibility@SystemSettings@@AEAA_NXZ`
- size: `869`
- prototype: `bool __fastcall(SystemSettings::Accessibility::CRestartWindowsAfterBrailleFodInstallSetting *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180032ec0`

## callees

- `0x18000c840`
- `0x18001ecfc`
- `0x1800234f8`
- `0x18002373c`
- `0x180024ad4`
- `0x1800257d0`
- `0x180028f18`
- `0x18002e1a4`
- `0x180040c98`
- `0x180046c70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040d8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040da3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f49`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180040cdc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180040cdc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180040e8c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180040e8c`
- `USER32!ExitWindowsEx` at `0x180040f35`
- `USER32!ExitWindowsEx` at `0x180040f35`

## string_xrefs

- `0x180040cd3`: `SeShutdownPrivilege`
- `0x180040dd0`: `OpenProcessToken failed. Error - `
- `0x180040d09`: `SeShutdownPrivilege not present. Error - `
- `0x180040eb9`: `AdjustTokenPrivileges failed. Error - `

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
char __fastcall SystemSettings::Accessibility::CRestartWindowsAfterBrailleFodInstallSetting::RestartMachine(
        SystemSettings::Accessibility::CRestartWindowsAfterBrailleFodInstallSetting *this)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  HANDLE CurrentProcess; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 LastError; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  __int64 v24; // [rsp+38h] [rbp-90h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v26[32]; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v27[32]; // [rsp+68h] [rbp-60h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+88h] [rbp-40h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp-30h] BYREF

  TokenHandle = 0;
  NewState = 0;
  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = Luid;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        if ( ExitWindowsEx(2u, 2u) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return 1;
        }
        else
        {
          LastError = GetLastError();
          std::_Integral_to_string<unsigned short,unsigned long>(v27, LastError);
          v19 = std::wstring::wstring(v29, L"Braille FoD restart failed. Error - ");
          std::operator+<unsigned short>(v26, v19, v27);
          std::wstring::_Tidy_deallocate(v29);
          std::wstring::_Tidy_deallocate(v27);
          v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v20, v21, v22);
          AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<unsigned short const *>(&v24);
          std::wstring::_Tidy_deallocate(v26);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return 0;
        }
      }
      else
      {
        v13 = GetLastError();
        std::_Integral_to_string<unsigned short,unsigned long>(v27, v13);
        v14 = std::wstring::wstring(v29, L"AdjustTokenPrivileges failed. Error - ");
        std::operator+<unsigned short>(v26, v14, v27);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v27);
        v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v15, v16, v17);
        AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<unsigned short const *>(&v24);
        std::wstring::_Tidy_deallocate(v26);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 0;
      }
    }
    else
    {
      v8 = GetLastError();
      std::_Integral_to_string<unsigned short,unsigned long>(v27, v8);
      v9 = std::wstring::wstring(v29, L"OpenProcessToken failed. Error - ");
      std::operator+<unsigned short>(v26, v9, v27);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v27);
      v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v10, v11, v12);
      AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<unsigned short const *>(&v24);
      std::wstring::_Tidy_deallocate(v26);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 0;
    }
  }
  else
  {
    v1 = GetLastError();
    std::_Integral_to_string<unsigned short,unsigned long>(v26, v1);
    v2 = std::wstring::wstring(v29, L"SeShutdownPrivilege not present. Error - ");
    std::operator+<unsigned short>(v27, v2, v26);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v26);
    v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27, v3, v4, v5);
    AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<unsigned short const *>(&v24);
    std::wstring::_Tidy_deallocate(v27);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x180040c98  sub     rsp, 0C8h
0x180040c9f  mov     rax, cs:__security_cookie
0x180040ca6  xor     rax, rsp
0x180040ca9  mov     [rsp+0C8h+var_10], rax
0x180040cb1  mov     [rsp+0C8h+TokenHandle], 0
0x180040cba  xorps   xmm0, xmm0
0x180040cbd  movups  xmmword ptr [rsp+0C8h+NewState.PrivilegeCount], xmm0
0x180040cc5  mov     qword ptr [rsp+0C8h+Luid.LowPart], 0
0x180040cce  lea     r8, [rsp+0C8h+Luid]; lpLuid
0x180040cd3  lea     rdx, Name; "SeShutdownPrivilege"
0x180040cda  xor     ecx, ecx; lpSystemName
0x180040cdc  call    cs:__imp_LookupPrivilegeValueW
0x180040ce3  nop     dword ptr [rax+rax+00h]
0x180040ce8  test    eax, eax
0x180040cea  jnz     loc_180040D7E
0x180040cf0  call    cs:__imp_GetLastError
0x180040cf7  nop     dword ptr [rax+rax+00h]
0x180040cfc  mov     edx, eax
0x180040cfe  lea     rcx, [rsp+0C8h+var_80]
0x180040d03  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180040d08  nop
0x180040d09  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege not present. Error "...
0x180040d10  lea     rcx, [rsp+0C8h+var_30]
0x180040d18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040d1d  nop
0x180040d1e  lea     r8, [rsp+0C8h+var_80]
0x180040d23  mov     rdx, rax
0x180040d26  lea     rcx, [rsp+0C8h+var_60]
0x180040d2b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180040d30  nop
0x180040d31  lea     rcx, [rsp+0C8h+var_30]
0x180040d39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040d3e  nop
0x180040d3f  lea     rcx, [rsp+0C8h+var_80]
0x180040d44  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040d49  lea     rcx, [rsp+0C8h+var_60]
0x180040d4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180040d53  mov     [rsp+0C8h+var_90], rax
0x180040d58  lea     rcx, [rsp+0C8h+var_90]
0x180040d5d  call    ??$BrailleFoDInstallStatus@PEBG@AccessibilitySettingsTelemetry@@SAX$$QEAPEBG@Z; AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<ushort const *>(ushort const * &&)
0x180040d62  lea     rcx, [rsp+0C8h+var_60]
0x180040d67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040d6c  nop
0x180040d6d  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040d72  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040d77  xor     al, al
0x180040d79  jmp     loc_180040FE4
0x180040d7e  xor     edx, edx
0x180040d80  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040d85  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180040d8a  call    cs:__imp_GetCurrentProcess
0x180040d91  nop     dword ptr [rax+rax+00h]
0x180040d96  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180040d9b  mov     edx, 28h ; '('; DesiredAccess
0x180040da0  mov     rcx, rax; ProcessHandle
0x180040da3  call    cs:__imp_OpenProcessToken
0x180040daa  nop     dword ptr [rax+rax+00h]
0x180040daf  test    eax, eax
0x180040db1  jnz     loc_180040E45
0x180040db7  call    cs:__imp_GetLastError
0x180040dbe  nop     dword ptr [rax+rax+00h]
0x180040dc3  mov     edx, eax
0x180040dc5  lea     rcx, [rsp+0C8h+var_60]
0x180040dca  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180040dcf  nop
0x180040dd0  lea     rdx, aOpenprocesstok; "OpenProcessToken failed. Error - "
0x180040dd7  lea     rcx, [rsp+0C8h+var_30]
0x180040ddf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040de4  nop
0x180040de5  lea     r8, [rsp+0C8h+var_60]
0x180040dea  mov     rdx, rax
0x180040ded  lea     rcx, [rsp+0C8h+var_80]
0x180040df2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180040df7  nop
0x180040df8  lea     rcx, [rsp+0C8h+var_30]
0x180040e00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040e05  nop
0x180040e06  lea     rcx, [rsp+0C8h+var_60]
0x180040e0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040e10  lea     rcx, [rsp+0C8h+var_80]
0x180040e15  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180040e1a  mov     [rsp+0C8h+var_90], rax
0x180040e1f  lea     rcx, [rsp+0C8h+var_90]
0x180040e24  call    ??$BrailleFoDInstallStatus@PEBG@AccessibilitySettingsTelemetry@@SAX$$QEAPEBG@Z; AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<ushort const *>(ushort const * &&)
0x180040e29  lea     rcx, [rsp+0C8h+var_80]
0x180040e2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040e33  nop
0x180040e34  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040e39  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040e3e  xor     al, al
0x180040e40  jmp     loc_180040FE4
0x180040e45  mov     [rsp+0C8h+NewState.PrivilegeCount], 1
0x180040e50  mov     rax, qword ptr [rsp+0C8h+Luid.LowPart]
0x180040e55  mov     qword ptr [rsp+0C8h+NewState.Privileges.Luid.LowPart], rax
0x180040e5d  mov     [rsp+0C8h+NewState.Privileges.Attributes], 2
0x180040e68  mov     [rsp+0C8h+ReturnLength], 0; ReturnLength
0x180040e71  mov     [rsp+0C8h+PreviousState], 0; PreviousState
0x180040e7a  xor     r9d, r9d; BufferLength
0x180040e7d  lea     r8, [rsp+0C8h+NewState]; NewState
0x180040e85  xor     edx, edx; DisableAllPrivileges
0x180040e87  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180040e8c  call    cs:__imp_AdjustTokenPrivileges
0x180040e93  nop     dword ptr [rax+rax+00h]
0x180040e98  test    eax, eax
0x180040e9a  jnz     loc_180040F2E
0x180040ea0  call    cs:__imp_GetLastError
0x180040ea7  nop     dword ptr [rax+rax+00h]
0x180040eac  mov     edx, eax
0x180040eae  lea     rcx, [rsp+0C8h+var_60]
0x180040eb3  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180040eb8  nop
0x180040eb9  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges failed. Error - "
0x180040ec0  lea     rcx, [rsp+0C8h+var_30]
0x180040ec8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040ecd  nop
0x180040ece  lea     r8, [rsp+0C8h+var_60]
0x180040ed3  mov     rdx, rax
0x180040ed6  lea     rcx, [rsp+0C8h+var_80]
0x180040edb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180040ee0  nop
0x180040ee1  lea     rcx, [rsp+0C8h+var_30]
0x180040ee9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040eee  nop
0x180040eef  lea     rcx, [rsp+0C8h+var_60]
0x180040ef4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040ef9  lea     rcx, [rsp+0C8h+var_80]
0x180040efe  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180040f03  mov     [rsp+0C8h+var_90], rax
0x180040f08  lea     rcx, [rsp+0C8h+var_90]
0x180040f0d  call    ??$BrailleFoDInstallStatus@PEBG@AccessibilitySettingsTelemetry@@SAX$$QEAPEBG@Z; AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<ushort const *>(ushort const * &&)
0x180040f12  lea     rcx, [rsp+0C8h+var_80]
0x180040f17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040f1c  nop
0x180040f1d  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040f22  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040f27  xor     al, al
0x180040f29  jmp     loc_180040FE4
0x180040f2e  mov     edx, 2; dwReason
0x180040f33  mov     ecx, edx; uFlags
0x180040f35  call    cs:__imp_ExitWindowsEx
0x180040f3c  nop     dword ptr [rax+rax+00h]
0x180040f41  test    eax, eax
0x180040f43  jnz     loc_180040FD4
0x180040f49  call    cs:__imp_GetLastError
0x180040f50  nop     dword ptr [rax+rax+00h]
0x180040f55  mov     edx, eax
0x180040f57  lea     rcx, [rsp+0C8h+var_60]
0x180040f5c  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180040f61  nop
0x180040f62  lea     rdx, aBrailleFodRest; "Braille FoD restart failed. Error - "
0x180040f69  lea     rcx, [rsp+0C8h+var_30]
0x180040f71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040f76  nop
0x180040f77  lea     r8, [rsp+0C8h+var_60]
0x180040f7c  mov     rdx, rax
0x180040f7f  lea     rcx, [rsp+0C8h+var_80]
0x180040f84  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180040f89  nop
0x180040f8a  lea     rcx, [rsp+0C8h+var_30]
0x180040f92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040f97  nop
0x180040f98  lea     rcx, [rsp+0C8h+var_60]
0x180040f9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040fa2  lea     rcx, [rsp+0C8h+var_80]
0x180040fa7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180040fac  mov     [rsp+0C8h+var_90], rax
0x180040fb1  lea     rcx, [rsp+0C8h+var_90]
0x180040fb6  call    ??$BrailleFoDInstallStatus@PEBG@AccessibilitySettingsTelemetry@@SAX$$QEAPEBG@Z; AccessibilitySettingsTelemetry::BrailleFoDInstallStatus<ushort const *>(ushort const * &&)
0x180040fbb  lea     rcx, [rsp+0C8h+var_80]
0x180040fc0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040fc5  nop
0x180040fc6  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040fcb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040fd0  xor     al, al
0x180040fd2  jmp     short loc_180040FE4
0x180040fd4  lea     rcx, [rsp+0C8h+TokenHandle]
0x180040fd9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040fde  mov     al, 1
0x180040fe0  jmp     short loc_180040FE4
0x180040fe2  xor     al, al
0x180040fe4  mov     rcx, [rsp+0C8h+var_10]
0x180040fec  xor     rcx, rsp; StackCookie
0x180040fef  call    __security_check_cookie
0x180040ff4  add     rsp, 0C8h
0x180040ffb  retn
```
