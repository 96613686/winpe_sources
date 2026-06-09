# CPolicyCheck::ReadTrustedZonePolicy(HKEY__ *)

- ea: `0x180003d90`
- end: `0x180003f76`
- name: `?ReadTrustedZonePolicy@CPolicyCheck@@QEAAXPEAUHKEY__@@@Z`
- size: `486`
- prototype: `void(CPolicyCheck *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003afc`

## callees

- `0x180003d90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003eb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003f3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003eb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003f3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003de1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003de1`

## string_xrefs

- `0x180003e60`: `InstallTrustedOCX`
- `0x180003ea7`: `InstallSignedOCX`
- `0x180003eee`: `InstallUnSignedOCX`

## pseudocode

```c
void __fastcall CPolicyCheck::ReadTrustedZonePolicy(CPolicyCheck *this, HKEY a2)
{
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(a2, L"AxISURLZonePolicies", 0, 0x20019u, &hKey) )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"URLZone", 0, &Type, Data, &cbData) || Type != 4 )
      *((_DWORD *)this + 37) = 2;
    else
      *((_DWORD *)this + 37) = *(_DWORD *)Data;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InstallTrustedOCX", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data <= 2u )
      *((_DWORD *)this + 35) = *(_DWORD *)Data;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InstallSignedOCX", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data <= 2u )
      *((_DWORD *)this + 36) = *(_DWORD *)Data;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InstallUnSignedOCX", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data <= 2u )
      *((_DWORD *)this + 38) = *(_DWORD *)Data;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"VerifyServerCert", 0, &Type, Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 39) = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180003d90  mov     [rsp-8+arg_0], rbx
0x180003d95  mov     [rsp-8+arg_8], rdi
0x180003d9a  push    rbp
0x180003d9b  mov     rbp, rsp
0x180003d9e  sub     rsp, 40h
0x180003da2  mov     rbx, rcx
0x180003da5  mov     [rbp+hKey], 0
0x180003dad  mov     rax, rdx
0x180003db0  mov     [rbp+Type], 0
0x180003db7  lea     rcx, [rbp+hKey]
0x180003dbb  mov     [rbp+cbData], 0
0x180003dc2  mov     [rsp+40h+phkResult], rcx; phkResult
0x180003dc7  lea     rdx, aAxisurlzonepol; "AxISURLZonePolicies"
0x180003dce  mov     rcx, rax; hKey
0x180003dd1  mov     dword ptr [rbp+Data], 0
0x180003dd8  mov     r9d, 20019h; samDesired
0x180003dde  xor     r8d, r8d; ulOptions
0x180003de1  call    cs:__imp_RegOpenKeyExW
0x180003de7  test    eax, eax
0x180003de9  jnz     loc_180003F57
0x180003def  mov     rcx, [rbp+hKey]; hKey
0x180003df3  lea     edi, [rax+4]
0x180003df6  lea     rax, [rbp+cbData]
0x180003dfa  mov     [rbp+Type], edi
0x180003dfd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003e02  lea     r9, [rbp+Type]; lpType
0x180003e06  lea     rax, [rbp+Data]
0x180003e0a  mov     [rbp+cbData], edi
0x180003e0d  xor     r8d, r8d; lpReserved
0x180003e10  mov     [rsp+40h+phkResult], rax; lpData
0x180003e15  lea     rdx, aUrlzone; "URLZone"
0x180003e1c  call    cs:__imp_RegQueryValueExW
0x180003e22  test    eax, eax
0x180003e24  jnz     short loc_180003E36
0x180003e26  cmp     [rbp+Type], edi
0x180003e29  jnz     short loc_180003E36
0x180003e2b  mov     eax, dword ptr [rbp+Data]
0x180003e2e  mov     [rbx+94h], eax
0x180003e34  jmp     short loc_180003E40
0x180003e36  mov     dword ptr [rbx+94h], 2
0x180003e40  mov     rcx, [rbp+hKey]; hKey
0x180003e44  lea     rax, [rbp+cbData]
0x180003e48  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003e4d  lea     r9, [rbp+Type]; lpType
0x180003e51  lea     rax, [rbp+Data]
0x180003e55  mov     [rbp+Type], edi
0x180003e58  xor     r8d, r8d; lpReserved
0x180003e5b  mov     [rsp+40h+phkResult], rax; lpData
0x180003e60  lea     rdx, ValueName; "InstallTrustedOCX"
0x180003e67  mov     [rbp+cbData], edi
0x180003e6a  call    cs:__imp_RegQueryValueExW
0x180003e70  test    eax, eax
0x180003e72  jnz     short loc_180003E87
0x180003e74  cmp     [rbp+Type], edi
0x180003e77  jnz     short loc_180003E87
0x180003e79  mov     eax, dword ptr [rbp+Data]
0x180003e7c  cmp     eax, 2
0x180003e7f  ja      short loc_180003E87
0x180003e81  mov     [rbx+8Ch], eax
0x180003e87  mov     rcx, [rbp+hKey]; hKey
0x180003e8b  lea     rax, [rbp+cbData]
0x180003e8f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003e94  lea     r9, [rbp+Type]; lpType
0x180003e98  lea     rax, [rbp+Data]
0x180003e9c  mov     [rbp+Type], edi
0x180003e9f  xor     r8d, r8d; lpReserved
0x180003ea2  mov     [rsp+40h+phkResult], rax; lpData
0x180003ea7  lea     rdx, aInstallsignedo; "InstallSignedOCX"
0x180003eae  mov     [rbp+cbData], edi
0x180003eb1  call    cs:__imp_RegQueryValueExW
0x180003eb7  test    eax, eax
0x180003eb9  jnz     short loc_180003ECE
0x180003ebb  cmp     [rbp+Type], edi
0x180003ebe  jnz     short loc_180003ECE
0x180003ec0  mov     eax, dword ptr [rbp+Data]
0x180003ec3  cmp     eax, 2
0x180003ec6  ja      short loc_180003ECE
0x180003ec8  mov     [rbx+90h], eax
0x180003ece  mov     rcx, [rbp+hKey]; hKey
0x180003ed2  lea     rax, [rbp+cbData]
0x180003ed6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003edb  lea     r9, [rbp+Type]; lpType
0x180003edf  lea     rax, [rbp+Data]
0x180003ee3  mov     [rbp+Type], edi
0x180003ee6  xor     r8d, r8d; lpReserved
0x180003ee9  mov     [rsp+40h+phkResult], rax; lpData
0x180003eee  lea     rdx, aInstallunsigne; "InstallUnSignedOCX"
0x180003ef5  mov     [rbp+cbData], edi
0x180003ef8  call    cs:__imp_RegQueryValueExW
0x180003efe  test    eax, eax
0x180003f00  jnz     short loc_180003F15
0x180003f02  cmp     [rbp+Type], edi
0x180003f05  jnz     short loc_180003F15
0x180003f07  mov     eax, dword ptr [rbp+Data]
0x180003f0a  cmp     eax, 2
0x180003f0d  ja      short loc_180003F15
0x180003f0f  mov     [rbx+98h], eax
0x180003f15  mov     rcx, [rbp+hKey]; hKey
0x180003f19  lea     rax, [rbp+cbData]
0x180003f1d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180003f22  lea     r9, [rbp+Type]; lpType
0x180003f26  lea     rax, [rbp+Data]
0x180003f2a  mov     [rbp+Type], edi
0x180003f2d  xor     r8d, r8d; lpReserved
0x180003f30  mov     [rsp+40h+phkResult], rax; lpData
0x180003f35  lea     rdx, aVerifyserverce; "VerifyServerCert"
0x180003f3c  mov     [rbp+cbData], edi
0x180003f3f  call    cs:__imp_RegQueryValueExW
0x180003f45  test    eax, eax
0x180003f47  jnz     short loc_180003F57
0x180003f49  cmp     [rbp+Type], edi
0x180003f4c  jnz     short loc_180003F57
0x180003f4e  mov     eax, dword ptr [rbp+Data]
0x180003f51  mov     [rbx+9Ch], eax
0x180003f57  mov     rcx, [rbp+hKey]; hKey
0x180003f5b  test    rcx, rcx
0x180003f5e  jz      short loc_180003F66
0x180003f60  call    cs:__imp_RegCloseKey
0x180003f66  mov     rbx, [rsp+40h+arg_0]
0x180003f6b  mov     rdi, [rsp+40h+arg_8]
0x180003f70  add     rsp, 40h
0x180003f74  pop     rbp
0x180003f75  retn
```
