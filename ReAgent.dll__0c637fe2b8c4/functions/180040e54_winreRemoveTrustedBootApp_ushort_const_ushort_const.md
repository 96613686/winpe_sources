# winreRemoveTrustedBootApp(ushort const *,ushort const *)

- ea: `0x180040e54`
- end: `0x180040fe7`
- name: `?winreRemoveTrustedBootApp@@YAKPEBG0@Z`
- size: `403`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024f60`

## callees

- `0x1800059fc`
- `0x180040c28`
- `0x180040e54`
- `0x18004111c`
- `0x18004d2fc`
- `0x18004d584`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180040f5d`
- `ADVAPI32!RegDeleteValueW` at `0x180040f5d`
- `ADVAPI32!RegCreateKeyExW` at `0x180040f41`
- `ADVAPI32!RegCreateKeyExW` at `0x180040f41`
- `ADVAPI32!RegCloseKey` at `0x180040f86`
- `ADVAPI32!RegCloseKey` at `0x180040f86`

## string_xrefs

- `0x180040ea7`: `winreRemoveTrustedBootApp: Failed to enable backup privilege`
- `0x180040ed4`: `winreRemoveTrustedBootApp: Failed to enable restore privilege`
- `0x180040eef`: `winreRemoveTrustedBootApp: Failed to load SOFTWARE hive: 0x%x`
- `0x180040f4d`: `winreRemoveTrustedBootApp: Failed to open trusted app list key: 0x%x`
- `0x180040f6c`: `winreRemoveTrustedBootApp: Failed to delete hash for [%s]: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRemoveTrustedBootApp(unsigned __int16 *a1, LPCWSTR lpValueName)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  int v8; // [rsp+50h] [rbp-20h] BYREF
  int v9; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF

  v8 = 0;
  v9 = 0;
  hKey = 0;
  phkResult = 0;
  if ( !(unsigned int)Utils::EnablePrivilege(0x11u, &v8) )
  {
    UnattendLogW(1, L"winreRemoveTrustedBootApp: Failed to enable backup privilege");
LABEL_3:
    v4 = 1314;
    goto LABEL_13;
  }
  if ( !(unsigned int)Utils::EnablePrivilege(0x12u, &v9) )
  {
    UnattendLogW(1, L"winreRemoveTrustedBootApp: Failed to enable restore privilege");
    goto LABEL_3;
  }
  v5 = winreLoadSoftwareHive(a1, &hKey);
  v4 = v5;
  if ( v5 )
  {
    UnattendLogW(1, L"winreRemoveTrustedBootApp: Failed to load SOFTWARE hive: 0x%x", v5);
  }
  else
  {
    v6 = RegCreateKeyExW(hKey, L"Microsoft\\RecoveryEnvironment\\TrustedApps", 0, 0, 4u, 0xF003Fu, 0, &phkResult, 0);
    v4 = v6;
    if ( v6 )
    {
      UnattendLogW(1, L"winreRemoveTrustedBootApp: Failed to open trusted app list key: 0x%x", v6);
    }
    else
    {
      v4 = RegDeleteValueW(phkResult, lpValueName);
      if ( v4 )
        UnattendLogW(1, L"winreRemoveTrustedBootApp: Failed to delete hash for [%s]: 0x%x", lpValueName);
    }
  }
LABEL_13:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    winreUnloadSoftwareHive(a1);
    hKey = 0;
  }
  Utils::DisablePrivilege(0x11u, &v8);
  Utils::DisablePrivilege(0x12u, &v9);
  return v4;
}

```

## disassembly

```asm
0x180040e54  mov     [rsp-18h+arg_10], rbx
0x180040e59  push    rbp
0x180040e5a  push    rsi
0x180040e5b  push    rdi
0x180040e5c  mov     rbp, rsp
0x180040e5f  sub     rsp, 70h
0x180040e63  mov     rax, cs:__security_cookie
0x180040e6a  xor     rax, rsp
0x180040e6d  mov     [rbp+var_8], rax
0x180040e71  mov     rdi, rdx
0x180040e74  mov     [rbp+var_20], 0
0x180040e7b  mov     rsi, rcx
0x180040e7e  mov     [rbp+var_1C], 0
0x180040e85  lea     rdx, [rbp+var_20]; int *
0x180040e89  mov     [rbp+hKey], 0
0x180040e91  mov     ecx, 11h; unsigned int
0x180040e96  mov     [rbp+var_18], 0
0x180040e9e  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x180040ea3  test    eax, eax
0x180040ea5  jnz     short loc_180040EC2
0x180040ea7  lea     rdx, aWinreremovetru_0; "winreRemoveTrustedBootApp: Failed to en"...
0x180040eae  mov     ecx, 1
0x180040eb3  call    UnattendLogW
0x180040eb8  mov     ebx, 522h
0x180040ebd  jmp     loc_180040F7D
0x180040ec2  lea     rdx, [rbp+var_1C]; int *
0x180040ec6  mov     ecx, 12h; unsigned int
0x180040ecb  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x180040ed0  test    eax, eax
0x180040ed2  jnz     short loc_180040EDD
0x180040ed4  lea     rdx, aWinreremovetru_6; "winreRemoveTrustedBootApp: Failed to en"...
0x180040edb  jmp     short loc_180040EAE
0x180040edd  lea     rdx, [rbp+hKey]; phkResult
0x180040ee1  mov     rcx, rsi; unsigned __int16 *
0x180040ee4  call    winreLoadSoftwareHive
0x180040ee9  mov     ebx, eax
0x180040eeb  test    eax, eax
0x180040eed  jz      short loc_180040F05
0x180040eef  lea     rdx, aWinreremovetru_8; "winreRemoveTrustedBootApp: Failed to lo"...
0x180040ef6  mov     r8d, eax
0x180040ef9  mov     ecx, 1
0x180040efe  call    UnattendLogW
0x180040f03  jmp     short loc_180040F7D
0x180040f05  mov     rcx, [rbp+hKey]; hKey
0x180040f09  lea     rax, [rbp+var_18]
0x180040f0d  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180040f16  lea     rdx, aMicrosoftRecov; "Microsoft\\RecoveryEnvironment\\Trusted"...
0x180040f1d  mov     [rsp+70h+phkResult], rax; phkResult
0x180040f22  xor     r9d, r9d; lpClass
0x180040f25  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040f2e  xor     r8d, r8d; Reserved
0x180040f31  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180040f39  mov     [rsp+70h+dwOptions], 4; dwOptions
0x180040f41  call    cs:__imp_RegCreateKeyExW
0x180040f47  mov     ebx, eax
0x180040f49  test    eax, eax
0x180040f4b  jz      short loc_180040F56
0x180040f4d  lea     rdx, aWinreremovetru_5; "winreRemoveTrustedBootApp: Failed to op"...
0x180040f54  jmp     short loc_180040EF6
0x180040f56  mov     rcx, [rbp+var_18]; hKey
0x180040f5a  mov     rdx, rdi; lpValueName
0x180040f5d  call    cs:__imp_RegDeleteValueW
0x180040f63  mov     ebx, eax
0x180040f65  test    eax, eax
0x180040f67  jz      short loc_180040F7D
0x180040f69  mov     r8, rdi
0x180040f6c  lea     rdx, aWinreremovetru_2; "winreRemoveTrustedBootApp: Failed to de"...
0x180040f73  mov     ecx, 1
0x180040f78  call    UnattendLogW
0x180040f7d  mov     rcx, [rbp+var_18]; hKey
0x180040f81  test    rcx, rcx
0x180040f84  jz      short loc_180040F94
0x180040f86  call    cs:__imp_RegCloseKey
0x180040f8c  mov     [rbp+var_18], 0
0x180040f94  mov     rdx, [rbp+hKey]
0x180040f98  test    rdx, rdx
0x180040f9b  jz      short loc_180040FAD
0x180040f9d  mov     rcx, rsi
0x180040fa0  call    winreUnloadSoftwareHive
0x180040fa5  mov     [rbp+hKey], 0
0x180040fad  lea     rdx, [rbp+var_20]; int *
0x180040fb1  mov     ecx, 11h; unsigned int
0x180040fb6  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180040fbb  lea     rdx, [rbp+var_1C]; int *
0x180040fbf  mov     ecx, 12h; unsigned int
0x180040fc4  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180040fc9  mov     eax, ebx
0x180040fcb  mov     rcx, [rbp+var_8]
0x180040fcf  xor     rcx, rsp; StackCookie
0x180040fd2  call    __security_check_cookie
0x180040fd7  mov     rbx, [rsp+70h+arg_10]
0x180040fdf  add     rsp, 70h
0x180040fe3  pop     rdi
0x180040fe4  pop     rsi
0x180040fe5  pop     rbp
0x180040fe6  retn
```
