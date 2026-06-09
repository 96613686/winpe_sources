# HasLogonTaskExecuted(void)

- ea: `0x140006868`
- end: `0x140006939`
- name: `?HasLogonTaskExecuted@@YAJXZ`
- size: `209`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x140006868`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400068a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400068ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400068a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400068ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400068bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400068bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006922`

## string_xrefs

- `0x1400068d5`: `OSData\SOFTWARE\Microsoft\Provisioning\LogonTaskCompleted`
- `0x1400068ce`: `SOFTWARE\Microsoft\Provisioning\LogonTaskCompleted`

## pseudocode

```c
__int64 HasLogonTaskExecuted(void)
{
  const WCHAR *v0; // rdx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                           HKEY_LOCAL_MACHINE,
                                                           L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                           0,
                                                           0x20119u,
                                                           &hKey) == 0;
    RegCloseKey(hKey);
    `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v0 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\LogonTaskCompleted";
  if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
    v0 = L"SOFTWARE\\Microsoft\\Provisioning\\LogonTaskCompleted";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 1u, 0x20019u, &phkResult) )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147500037LL;
  }
  else
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 0;
  }
}

```

## disassembly

```asm
0x140006868  mov     r11, rsp
0x14000686b  sub     rsp, 38h
0x14000686f  mov     qword ptr [r11+8], 0
0x140006877  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x14000687e  jnz     short loc_1400068C8
0x140006880  mov     qword ptr [r11+10h], 0
0x140006888  lea     rax, [r11+10h]
0x14000688c  mov     [r11-18h], rax
0x140006890  mov     r9d, 20119h; samDesired
0x140006896  xor     r8d, r8d; ulOptions
0x140006899  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Stat"...
0x1400068a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400068a7  call    cs:__imp_RegOpenKeyExW
0x1400068ad  test    eax, eax
0x1400068af  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1400068b6  mov     rcx, [rsp+38h+hKey]; hKey
0x1400068bb  call    cs:__imp_RegCloseKey
0x1400068c1  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1400068c8  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1400068ce  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Provisioning\\Logo"...
0x1400068d5  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1400068dc  test    al, al
0x1400068de  cmovz   rdx, rcx; lpSubKey
0x1400068e2  lea     rax, [rsp+38h+arg_0]
0x1400068e7  mov     [rsp+38h+phkResult], rax; phkResult
0x1400068ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400068f3  mov     r9d, 20019h; samDesired
0x1400068f9  mov     r8d, 1; ulOptions
0x1400068ff  call    cs:__imp_RegOpenKeyExW
0x140006905  mov     rcx, [rsp+38h+arg_0]; hKey
0x14000690a  test    eax, eax
0x14000690c  jnz     short loc_14000691D
0x14000690e  test    rcx, rcx
0x140006911  jz      short loc_140006919
0x140006913  call    cs:__imp_RegCloseKey
0x140006919  xor     eax, eax
0x14000691b  jmp     short loc_140006933
0x14000691d  test    rcx, rcx
0x140006920  jz      short loc_140006928
0x140006922  call    cs:__imp_RegCloseKey
0x140006928  mov     eax, 80004005h
0x14000692d  jmp     short loc_140006933
0x14000692f  mov     eax, dword ptr [rsp+38h+arg_0]
0x140006933  add     rsp, 38h
0x140006937  retn
```
