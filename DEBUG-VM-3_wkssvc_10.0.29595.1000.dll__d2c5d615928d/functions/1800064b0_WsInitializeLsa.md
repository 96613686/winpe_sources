# WsInitializeLsa

- ea: `0x1800064b0`
- end: `0x1800065b8`
- name: `WsInitializeLsa`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800065c0`

## callees

- `0x180005a60`
- `0x1800064b0`

## import_xrefs

- `ntdll!RtlInitString` at `0x1800064e7`
- `ntdll!RtlInitString` at `0x1800064e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000657c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000657c`
- `SspiCli!LsaConnectUntrusted` at `0x1800064cb`
- `SspiCli!LsaConnectUntrusted` at `0x1800064cb`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800064ff`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800064ff`

## pseudocode

```c
__int64 WsInitializeLsa()
{
  NTSTATUS v0; // eax
  __int64 v1; // rcx
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  _STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  DestinationString = 0;
  v0 = LsaConnectUntrusted(&LsaHandle);
  if ( v0 >= 0 )
  {
    RtlInitString(&DestinationString, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
    v2 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
    *(_DWORD *)&WsLsaRestrictAnonymous = 0;
    v3 = v2;
    if ( v2 >= 0 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
      {
        Type = 0;
        cbData = 4;
        if ( RegQueryValueExW(hKey, L"RestrictAnonymous", 0, &Type, &WsLsaRestrictAnonymous, &cbData)
          || Type != 4
          || cbData != 4 )
        {
          *(_DWORD *)&WsLsaRestrictAnonymous = 0;
        }
        RegCloseKey(hKey);
      }
    }
    v1 = v3;
  }
  else
  {
    v1 = (unsigned int)v0;
  }
  return WsMapStatus(v1);
}

```

## disassembly

```asm
0x1800064b0  mov     [rsp-8+arg_18], rbx
0x1800064b5  push    rbp
0x1800064b6  mov     rbp, rsp
0x1800064b9  sub     rsp, 40h
0x1800064bd  xorps   xmm0, xmm0
0x1800064c0  lea     rcx, LsaHandle; LsaHandle
0x1800064c7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800064cb  call    cs:__imp_LsaConnectUntrusted
0x1800064d1  test    eax, eax
0x1800064d3  jns     short loc_1800064DC
0x1800064d5  mov     ecx, eax
0x1800064d7  jmp     loc_1800065A8
0x1800064dc  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x1800064e3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800064e7  call    cs:__imp_RtlInitString
0x1800064ed  mov     rcx, cs:LsaHandle; LsaHandle
0x1800064f4  lea     r8, AuthenticationPackage; AuthenticationPackage
0x1800064fb  lea     rdx, [rbp+DestinationString]; PackageName
0x1800064ff  call    cs:__imp_LsaLookupAuthenticationPackage
0x180006505  mov     cs:WsLsaRestrictAnonymous, 0
0x18000650f  mov     ebx, eax
0x180006511  test    eax, eax
0x180006513  js      loc_1800065A6
0x180006519  lea     rax, [rbp+hKey]
0x18000651d  mov     [rbp+hKey], 0
0x180006525  mov     r9d, 20019h; samDesired
0x18000652b  mov     [rsp+40h+phkResult], rax; phkResult
0x180006530  xor     r8d, r8d; ulOptions
0x180006533  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x18000653a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006541  call    cs:__imp_RegOpenKeyExW
0x180006547  test    eax, eax
0x180006549  jnz     short loc_1800065A6
0x18000654b  mov     rcx, [rbp+hKey]; hKey
0x18000654f  lea     r9, [rbp+Type]; lpType
0x180006553  mov     [rbp+Type], eax
0x180006556  lea     rdx, ValueName; "RestrictAnonymous"
0x18000655d  lea     rax, [rbp+cbData]
0x180006561  mov     [rbp+cbData], 4
0x180006568  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000656d  xor     r8d, r8d; lpReserved
0x180006570  lea     rax, WsLsaRestrictAnonymous
0x180006577  mov     [rsp+40h+phkResult], rax; lpData
0x18000657c  call    cs:__imp_RegQueryValueExW
0x180006582  test    eax, eax
0x180006584  jnz     short loc_180006592
0x180006586  cmp     [rbp+Type], 4
0x18000658a  jnz     short loc_180006592
0x18000658c  cmp     [rbp+cbData], 4
0x180006590  jz      short loc_18000659C
0x180006592  mov     cs:WsLsaRestrictAnonymous, 0
0x18000659c  mov     rcx, [rbp+hKey]; hKey
0x1800065a0  call    cs:__imp_RegCloseKey
0x1800065a6  mov     ecx, ebx
0x1800065a8  call    WsMapStatus
0x1800065ad  mov     rbx, [rsp+40h+arg_18]
0x1800065b2  add     rsp, 40h
0x1800065b6  pop     rbp
0x1800065b7  retn
```
