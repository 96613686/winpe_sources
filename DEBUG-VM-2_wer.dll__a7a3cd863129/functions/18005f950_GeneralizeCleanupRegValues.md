# GeneralizeCleanupRegValues

- ea: `0x18005f950`
- end: `0x18005fa0d`
- name: `GeneralizeCleanupRegValues`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fc10`

## callees

- `0x18001c6d8`
- `0x18001f8c8`
- `0x18005f950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9f8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f98c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f9dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f98c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f9dd`

## pseudocode

```c
__int64 GeneralizeCleanupRegValues()
{
  HKEY *phkResult; // rax
  HKEY *v1; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 2u, phkResult) && hKey )
    RegDeleteValueW(hKey, L"MachineID");
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v1 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v4);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent", 0, 2u, v1)
    && v4 )
  {
    RegDeleteValueW(v4, L"NewUserDefaultConsent");
  }
  return tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v4);
}

```

## disassembly

```asm
0x18005f950  sub     rsp, 38h
0x18005f954  lea     rcx, [rsp+38h+hKey]
0x18005f959  mov     [rsp+38h+arg_8], 0
0x18005f962  mov     [rsp+38h+hKey], 0
0x18005f96b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005f970  mov     r9d, 2; samDesired
0x18005f976  mov     [rsp+38h+phkResult], rax; phkResult
0x18005f97b  xor     r8d, r8d; ulOptions
0x18005f97e  lea     rdx, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\SQMClient"
0x18005f985  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f98c  call    cs:__imp_RegOpenKeyExW
0x18005f992  test    eax, eax
0x18005f994  jnz     short loc_18005F9AD
0x18005f996  mov     rcx, [rsp+38h+hKey]; hKey
0x18005f99b  test    rcx, rcx
0x18005f99e  jz      short loc_18005F9AD
0x18005f9a0  lea     rdx, aMachineid; "MachineID"
0x18005f9a7  call    cs:__imp_RegDeleteValueW
0x18005f9ad  lea     rcx, [rsp+38h+hKey]
0x18005f9b2  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005f9b7  lea     rcx, [rsp+38h+arg_8]
0x18005f9bc  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005f9c1  mov     r9d, 2; samDesired
0x18005f9c7  mov     [rsp+38h+phkResult], rax; phkResult
0x18005f9cc  xor     r8d, r8d; ulOptions
0x18005f9cf  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18005f9d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f9dd  call    cs:__imp_RegOpenKeyExW
0x18005f9e3  test    eax, eax
0x18005f9e5  jnz     short loc_18005F9FE
0x18005f9e7  mov     rcx, [rsp+38h+arg_8]; hKey
0x18005f9ec  test    rcx, rcx
0x18005f9ef  jz      short loc_18005F9FE
0x18005f9f1  lea     rdx, aNewuserdefault; "NewUserDefaultConsent"
0x18005f9f8  call    cs:__imp_RegDeleteValueW
0x18005f9fe  lea     rcx, [rsp+38h+arg_8]
0x18005fa03  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005fa08  add     rsp, 38h
0x18005fa0c  retn
```
