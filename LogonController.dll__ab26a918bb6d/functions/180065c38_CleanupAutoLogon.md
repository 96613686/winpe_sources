# _CleanupAutoLogon

- ea: `0x180065c38`
- end: `0x180065d95`
- name: `_CleanupAutoLogon`
- size: `349`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038c34`
- `0x18003dee8`
- `0x18004e2e0`
- `0x1800919fc`

## callees

- `0x180033e90`
- `0x180065c38`
- `0x18009228c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065cd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065d1a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065cd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065d1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d84`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180065d75`

## string_xrefs

- `0x180065cbe`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180065d07`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
LSTATUS CleanupAutoLogon()
{
  LSTATUS result; // eax
  DWORD pcbData; // [rsp+50h] [rbp+10h] BYREF
  int pvData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 7u, &hKey);
  if ( !result )
  {
    SHRegSetString(hKey, 0, L"AutoAdminLogon", L"0");
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
           L"Enabled",
           0x10010u,
           0,
           &pvData,
           &pcbData) )
    {
      pcbData = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
        L"Enabled",
        0x20010010u,
        0,
        &pvData,
        &pcbData);
    }
    if ( !pvData )
    {
      RegDeleteValueW(hKey, L"IsConnectedAutoLogon");
      RegDeleteValueW(hKey, L"ConnectedCredentials");
    }
    RegDeleteValueW(hKey, L"AutoLogonCount");
    RegDeleteValueW(hKey, L"DefaultPassword");
    RegDeleteValueW(hKey, L"SystemAutoLogon");
    SetLSASecret();
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180065c38  mov     [rsp-8+arg_18], rdi
0x180065c3d  push    rbp
0x180065c3e  mov     rbp, rsp
0x180065c41  sub     rsp, 40h
0x180065c45  lea     rax, [rbp+hKey]
0x180065c49  mov     [rbp+hKey], 0
0x180065c51  mov     rdi, 0FFFFFFFF80000002h
0x180065c58  mov     [rsp+40h+phkResult], rax; phkResult
0x180065c5d  mov     rcx, rdi; hKey
0x180065c60  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180065c67  mov     r9d, 7; samDesired
0x180065c6d  xor     r8d, r8d; ulOptions
0x180065c70  call    cs:__imp_RegOpenKeyExW
0x180065c76  test    eax, eax
0x180065c78  jnz     loc_180065D8A
0x180065c7e  mov     rcx, [rbp+hKey]; hKey
0x180065c82  lea     r9, a0; "0"
0x180065c89  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x180065c90  xor     edx, edx; unsigned __int16 *
0x180065c92  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180065c97  lea     rax, [rbp+arg_0]
0x180065c9b  mov     [rbp+arg_8], 0
0x180065ca2  mov     [rsp+40h+pcbData], rax; pcbData
0x180065ca7  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180065cae  lea     rax, [rbp+arg_8]
0x180065cb2  mov     [rbp+arg_0], 4
0x180065cb9  mov     [rsp+40h+pvData], rax; pvData
0x180065cbe  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x180065cc5  mov     r9d, 10010h; dwFlags
0x180065ccb  mov     [rsp+40h+phkResult], 0; pdwType
0x180065cd4  mov     rcx, rdi; hkey
0x180065cd7  call    cs:__imp_RegGetValueW
0x180065cdd  test    eax, eax
0x180065cdf  jz      short loc_180065D20
0x180065ce1  lea     rax, [rbp+arg_0]
0x180065ce5  mov     [rbp+arg_0], 4
0x180065cec  mov     [rsp+40h+pcbData], rax; pcbData
0x180065cf1  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180065cf8  lea     rax, [rbp+arg_8]
0x180065cfc  mov     r9d, 20010010h; dwFlags
0x180065d02  mov     [rsp+40h+pvData], rax; pvData
0x180065d07  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180065d0e  mov     rcx, rdi; hkey
0x180065d11  mov     [rsp+40h+phkResult], 0; pdwType
0x180065d1a  call    cs:__imp_RegGetValueW
0x180065d20  cmp     [rbp+arg_8], 0
0x180065d24  jnz     short loc_180065D48
0x180065d26  mov     rcx, [rbp+hKey]; hKey
0x180065d2a  lea     rdx, aIsconnectedaut; "IsConnectedAutoLogon"
0x180065d31  call    cs:__imp_RegDeleteValueW
0x180065d37  mov     rcx, [rbp+hKey]; hKey
0x180065d3b  lea     rdx, aConnectedcrede; "ConnectedCredentials"
0x180065d42  call    cs:__imp_RegDeleteValueW
0x180065d48  mov     rcx, [rbp+hKey]; hKey
0x180065d4c  lea     rdx, aAutologoncount; "AutoLogonCount"
0x180065d53  call    cs:__imp_RegDeleteValueW
0x180065d59  mov     rcx, [rbp+hKey]; hKey
0x180065d5d  lea     rdx, SourceString; "DefaultPassword"
0x180065d64  call    cs:__imp_RegDeleteValueW
0x180065d6a  mov     rcx, [rbp+hKey]; hKey
0x180065d6e  lea     rdx, aSystemautologo; "SystemAutoLogon"
0x180065d75  call    cs:__imp_RegDeleteValueW
0x180065d7b  call    _SetLSASecret
0x180065d80  mov     rcx, [rbp+hKey]; hKey
0x180065d84  call    cs:__imp_RegCloseKey
0x180065d8a  mov     rdi, [rsp+40h+arg_18]
0x180065d8f  add     rsp, 40h
0x180065d93  pop     rbp
0x180065d94  retn
```
