# TsiValidateAndConfigureRegistry

- ea: `0x180015c24`
- end: `0x180015dae`
- name: `TsiValidateAndConfigureRegistry`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015544`

## callees

- `0x180015c24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c7f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015d32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c7f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015d32`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015cdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015d8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015cdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015d8e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015cc5`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015d74`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015cc5`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015d74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ce9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ce9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d98`

## string_xrefs

- `0x180015ca7`: `SOFTWARE\Microsoft\WPTaskScheduler`
- `0x180015cd5`: `SOFTWARE\Microsoft\WPTaskScheduler`
- `0x180015d56`: `SYSTEM\ControlSet001\Services\TaskSchedulerSvc\Parameters`
- `0x180015d84`: `SYSTEM\ControlSet001\Services\TaskSchedulerSvc\Parameters`
- `0x180015c3e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`
- `0x180015d00`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Parameters`

## pseudocode

```c
__int64 TsiValidateAndConfigureRegistry()
{
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKeySrc; // [rsp+88h] [rbp+20h] BYREF
  HKEY hKeyDest; // [rsp+90h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+30h] BYREF

  dwDisposition = 0;
  hKeyDest = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         g_szTaskSchedulerSchedulesRegPath,
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKeyDest,
         &dwDisposition) )
  {
    return 2147500037LL;
  }
  hKeySrc = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WPTaskScheduler", 0, 0xF003Fu, &hKeySrc) )
  {
    RegCopyTreeW(hKeySrc, 0, hKeyDest);
    RegCloseKey(hKeySrc);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WPTaskScheduler");
  }
  RegCloseKey(hKeyDest);
  phkResult = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         g_szTaskSchedulerParametersRegPath,
         0,
         0,
         0,
         0x2001Fu,
         0,
         &phkResult,
         &dwDisposition) )
  {
    return 2147500037LL;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\ControlSet001\\Services\\TaskSchedulerSvc\\Parameters",
          0,
          0xF003Fu,
          &hKey) )
  {
    RegCopyTreeW(hKey, 0, phkResult);
    RegCloseKey(hKey);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SYSTEM\\ControlSet001\\Services\\TaskSchedulerSvc\\Parameters");
  }
  RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180015c24  push    rbp
0x180015c26  push    rdi
0x180015c27  mov     rbp, rsp
0x180015c2a  sub     rsp, 68h
0x180015c2e  lea     rax, [rbp+dwDisposition]
0x180015c32  mov     [rbp+dwDisposition], 0
0x180015c39  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180015c3e  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180015c45  lea     rax, [rbp+hKeyDest]
0x180015c49  mov     [rbp+hKeyDest], 0
0x180015c51  mov     [rsp+68h+phkResult], rax; phkResult
0x180015c56  mov     rdi, 0FFFFFFFF80000002h
0x180015c5d  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180015c66  xor     r9d, r9d; lpClass
0x180015c69  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180015c71  xor     r8d, r8d; Reserved
0x180015c74  mov     rcx, rdi; hKey
0x180015c77  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180015c7f  call    cs:__imp_RegCreateKeyExW
0x180015c85  test    eax, eax
0x180015c87  jnz     loc_180015DA2
0x180015c8d  lea     rax, [rbp+hKeySrc]
0x180015c91  mov     [rbp+hKeySrc], 0
0x180015c99  mov     r9d, 0F003Fh; samDesired
0x180015c9f  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x180015ca4  xor     r8d, r8d; ulOptions
0x180015ca7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WPTaskScheduler"
0x180015cae  mov     rcx, rdi; hKey
0x180015cb1  call    cs:__imp_RegOpenKeyExW
0x180015cb7  test    eax, eax
0x180015cb9  jnz     short loc_180015CE5
0x180015cbb  mov     r8, [rbp+hKeyDest]; hKeyDest
0x180015cbf  xor     edx, edx; lpSubKey
0x180015cc1  mov     rcx, [rbp+hKeySrc]; hKeySrc
0x180015cc5  call    cs:__imp_RegCopyTreeW
0x180015ccb  mov     rcx, [rbp+hKeySrc]; hKey
0x180015ccf  call    cs:__imp_RegCloseKey
0x180015cd5  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WPTaskScheduler"
0x180015cdc  mov     rcx, rdi; hKey
0x180015cdf  call    cs:__imp_RegDeleteTreeW
0x180015ce5  mov     rcx, [rbp+hKeyDest]; hKey
0x180015ce9  call    cs:__imp_RegCloseKey
0x180015cef  lea     rax, [rbp+dwDisposition]
0x180015cf3  mov     [rbp+var_18], 0
0x180015cfb  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180015d00  lea     rdx, ?g_szTaskSchedulerParametersRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180015d07  lea     rax, [rbp+var_18]
0x180015d0b  xor     r9d, r9d; lpClass
0x180015d0e  mov     [rsp+68h+phkResult], rax; phkResult
0x180015d13  xor     r8d, r8d; Reserved
0x180015d16  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180015d1f  mov     rcx, rdi; hKey
0x180015d22  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180015d2a  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180015d32  call    cs:__imp_RegCreateKeyExW
0x180015d38  test    eax, eax
0x180015d3a  jnz     short loc_180015DA2
0x180015d3c  lea     rax, [rbp+hKey]
0x180015d40  mov     [rbp+hKey], 0
0x180015d48  mov     r9d, 0F003Fh; samDesired
0x180015d4e  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x180015d53  xor     r8d, r8d; ulOptions
0x180015d56  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Services\\TaskSc"...
0x180015d5d  mov     rcx, rdi; hKey
0x180015d60  call    cs:__imp_RegOpenKeyExW
0x180015d66  test    eax, eax
0x180015d68  jnz     short loc_180015D94
0x180015d6a  mov     r8, [rbp+var_18]; hKeyDest
0x180015d6e  xor     edx, edx; lpSubKey
0x180015d70  mov     rcx, [rbp+hKey]; hKeySrc
0x180015d74  call    cs:__imp_RegCopyTreeW
0x180015d7a  mov     rcx, [rbp+hKey]; hKey
0x180015d7e  call    cs:__imp_RegCloseKey
0x180015d84  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Services\\TaskSc"...
0x180015d8b  mov     rcx, rdi; hKey
0x180015d8e  call    cs:__imp_RegDeleteTreeW
0x180015d94  mov     rcx, [rbp+var_18]; hKey
0x180015d98  call    cs:__imp_RegCloseKey
0x180015d9e  xor     eax, eax
0x180015da0  jmp     short loc_180015DA7
0x180015da2  mov     eax, 80004005h
0x180015da7  add     rsp, 68h
0x180015dab  pop     rdi
0x180015dac  pop     rbp
0x180015dad  retn
```
