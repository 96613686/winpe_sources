# IERegGetDWORDWithPoliciesExA(char const *,char const *,char const *,ulong,int *,int *)

- ea: `0x1800f388c`
- end: `0x1800f3aca`
- name: `?IERegGetDWORDWithPoliciesExA@@YAKPEBD00KPEAH1@Z`
- size: `574`
- prototype: `unsigned int __usercall@<eax>(LPCSTR lpSubKey@<rcx>, LPCSTR@<rdx>, LPCSTR lpValueName@<r8>, unsigned int@<r9d>, DWORD cbData, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c2d90`
- `0x1800f3618`
- `0x18013c4c8`

## callees

- `0x1800f388c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f39a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f39e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f3ab9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f39a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f39e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f3ab9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3a7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f3a7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800f394c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800f3a70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800f394c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800f3a70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f391a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f3a3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f391a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f3a3c`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f38ca`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f38f7`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f3a15`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f38ca`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f38f7`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x1800f3a15`

## string_xrefs

- `0x1800f3a96`: `Security_HKLM_Only`

## pseudocode

```c
__int64 __fastcall IERegGetDWORDWithPoliciesExA(
        LPCSTR lpSubKey,
        LPCSTR a2,
        LPCSTR lpValueName,
        unsigned int a4,
        DWORD cbData,
        int *Data)
{
  int v6; // edi
  LSTATUS v11; // ebx
  int pvData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF

  v6 = 0;
  pvData = 0;
  pcbData = 4;
  v11 = 1;
  if ( (unsigned int)IsPolicyKeyPresentA("Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 2)
    && !RegGetValueA(
          HKEY_LOCAL_MACHINE,
          "Software\\Policies\\Microsoft\\Internet Explorer\\Main",
          "Security_HKLM_Only",
          0x18u,
          0,
          &pvData,
          &pcbData) )
  {
    v6 = pvData;
  }
  LODWORD(Data) = 0;
  cbData = 0;
  hKey = 0;
  if ( (unsigned int)IsPolicyKeyPresentA(a2, 0, 2) )
  {
    v11 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
    if ( !v11 )
    {
      cbData = 4;
      v11 = RegQueryValueExA(hKey, lpValueName, 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
    }
  }
  if ( !v6 )
  {
    if ( !v11 )
      return (unsigned int)Data;
    if ( !(unsigned int)IsPolicyKeyPresentA(a2, 1, 2) || RegOpenKeyExA(HKEY_CURRENT_USER, a2, 0, 1u, &hKey) )
      goto LABEL_7;
    cbData = 4;
    v11 = RegQueryValueExA(hKey, lpValueName, 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  if ( !v11 )
    return (unsigned int)Data;
LABEL_7:
  cbData = 4;
  if ( !v6 && !RegGetValueA(HKEY_CURRENT_USER, lpSubKey, lpValueName, 0x18u, 0, &Data, &cbData) )
    return (unsigned int)Data;
  cbData = 4;
  if ( !RegGetValueA(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName, 0x18u, 0, &Data, &cbData) )
    return (unsigned int)Data;
  return a4;
}

```

## disassembly

```asm
0x1800f388c  push    rbp
0x1800f388e  push    rbx
0x1800f388f  push    rsi
0x1800f3890  push    rdi
0x1800f3891  push    r12
0x1800f3893  push    r14
0x1800f3895  push    r15
0x1800f3897  mov     rbp, rsp
0x1800f389a  sub     rsp, 50h
0x1800f389e  xor     edi, edi
0x1800f38a0  mov     [rbp+pvData], 0
0x1800f38a7  mov     r15, r8
0x1800f38aa  mov     [rbp+var_C], 4
0x1800f38b1  mov     rsi, rdx
0x1800f38b4  mov     r12, rcx
0x1800f38b7  xor     edx, edx
0x1800f38b9  lea     rcx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\Internet"...
0x1800f38c0  lea     r8d, [rdi+2]
0x1800f38c4  mov     r14d, r9d
0x1800f38c7  lea     ebx, [rdi+1]
0x1800f38ca  call    cs:__imp_IsPolicyKeyPresentA
0x1800f38d0  test    eax, eax
0x1800f38d2  jnz     loc_1800F3A87
0x1800f38d8  xor     edx, edx
0x1800f38da  mov     dword ptr [rbp+Data], 0
0x1800f38e1  mov     rcx, rsi
0x1800f38e4  mov     [rbp+cbData], 0
0x1800f38eb  mov     [rbp+hKey], 0
0x1800f38f3  lea     r8d, [rdx+2]
0x1800f38f7  call    cs:__imp_IsPolicyKeyPresentA
0x1800f38fd  test    eax, eax
0x1800f38ff  jz      short loc_1800F395E
0x1800f3901  lea     rax, [rbp+hKey]
0x1800f3905  mov     r9d, ebx; samDesired
0x1800f3908  xor     r8d, r8d; ulOptions
0x1800f390b  mov     [rsp+50h+phkResult], rax; phkResult
0x1800f3910  mov     rdx, rsi; lpSubKey
0x1800f3913  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f391a  call    cs:__imp_RegOpenKeyExA
0x1800f3920  mov     ebx, eax
0x1800f3922  test    eax, eax
0x1800f3924  jnz     short loc_1800F395E
0x1800f3926  mov     rcx, [rbp+hKey]; hKey
0x1800f392a  lea     rax, [rbp+cbData]
0x1800f392e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800f3933  xor     r9d, r9d; lpType
0x1800f3936  lea     rax, [rbp+Data]
0x1800f393a  mov     [rbp+cbData], 4
0x1800f3941  xor     r8d, r8d; lpReserved
0x1800f3944  mov     [rsp+50h+phkResult], rax; lpData
0x1800f3949  mov     rdx, r15; lpValueName
0x1800f394c  call    cs:__imp_RegQueryValueExA
0x1800f3952  mov     rcx, [rbp+hKey]; hKey
0x1800f3956  mov     ebx, eax
0x1800f3958  call    cs:__imp_RegCloseKey
0x1800f395e  test    edi, edi
0x1800f3960  jz      loc_1800F3A03
0x1800f3966  test    ebx, ebx
0x1800f3968  jz      loc_1800F39FD
0x1800f396e  mov     ebx, 4
0x1800f3973  mov     [rbp+cbData], ebx
0x1800f3976  test    edi, edi
0x1800f3978  jnz     short loc_1800F39B0
0x1800f397a  lea     rax, [rbp+cbData]
0x1800f397e  mov     r8, r15; lpValue
0x1800f3981  mov     [rsp+50h+pcbData], rax; pcbData
0x1800f3986  lea     r9d, [rbx+14h]; dwFlags
0x1800f398a  lea     rax, [rbp+Data]
0x1800f398e  mov     rdx, r12; lpSubKey
0x1800f3991  mov     [rsp+50h+lpcbData], rax; pvData
0x1800f3996  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800f399d  mov     [rsp+50h+phkResult], 0; pdwType
0x1800f39a6  call    cs:__imp_RegGetValueA
0x1800f39ac  test    eax, eax
0x1800f39ae  jz      short loc_1800F39FD
0x1800f39b0  lea     rax, [rbp+cbData]
0x1800f39b4  mov     [rbp+cbData], ebx
0x1800f39b7  mov     [rsp+50h+pcbData], rax; pcbData
0x1800f39bc  mov     r9d, 18h; dwFlags
0x1800f39c2  lea     rax, [rbp+Data]
0x1800f39c6  mov     r8, r15; lpValue
0x1800f39c9  mov     [rsp+50h+lpcbData], rax; pvData
0x1800f39ce  mov     rdx, r12; lpSubKey
0x1800f39d1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f39d8  mov     [rsp+50h+phkResult], 0; pdwType
0x1800f39e1  call    cs:__imp_RegGetValueA
0x1800f39e7  test    eax, eax
0x1800f39e9  jz      short loc_1800F39FD
0x1800f39eb  mov     eax, r14d
0x1800f39ee  add     rsp, 50h
0x1800f39f2  pop     r15
0x1800f39f4  pop     r14
0x1800f39f6  pop     r12
0x1800f39f8  pop     rdi
0x1800f39f9  pop     rsi
0x1800f39fa  pop     rbx
0x1800f39fb  pop     rbp
0x1800f39fc  retn
0x1800f39fd  mov     r14d, dword ptr [rbp+Data]
0x1800f3a01  jmp     short loc_1800F39EB
0x1800f3a03  test    ebx, ebx
0x1800f3a05  jz      short loc_1800F39FD
0x1800f3a07  mov     ebx, 1
0x1800f3a0c  mov     rcx, rsi
0x1800f3a0f  mov     edx, ebx
0x1800f3a11  lea     r8d, [rbx+1]
0x1800f3a15  call    cs:__imp_IsPolicyKeyPresentA
0x1800f3a1b  test    eax, eax
0x1800f3a1d  jz      loc_1800F396E
0x1800f3a23  lea     rax, [rbp+hKey]
0x1800f3a27  mov     r9d, ebx; samDesired
0x1800f3a2a  xor     r8d, r8d; ulOptions
0x1800f3a2d  mov     [rsp+50h+phkResult], rax; phkResult
0x1800f3a32  mov     rdx, rsi; lpSubKey
0x1800f3a35  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800f3a3c  call    cs:__imp_RegOpenKeyExA
0x1800f3a42  test    eax, eax
0x1800f3a44  jnz     loc_1800F396E
0x1800f3a4a  mov     rcx, [rbp+hKey]; hKey
0x1800f3a4e  lea     rax, [rbp+cbData]
0x1800f3a52  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800f3a57  xor     r9d, r9d; lpType
0x1800f3a5a  lea     rax, [rbp+Data]
0x1800f3a5e  mov     [rbp+cbData], 4
0x1800f3a65  xor     r8d, r8d; lpReserved
0x1800f3a68  mov     [rsp+50h+phkResult], rax; lpData
0x1800f3a6d  mov     rdx, r15; lpValueName
0x1800f3a70  call    cs:__imp_RegQueryValueExA
0x1800f3a76  mov     rcx, [rbp+hKey]; hKey
0x1800f3a7a  mov     ebx, eax
0x1800f3a7c  call    cs:__imp_RegCloseKey
0x1800f3a82  jmp     loc_1800F3966
0x1800f3a87  lea     rax, [rbp+var_C]
0x1800f3a8b  mov     r9d, 18h; dwFlags
0x1800f3a91  mov     [rsp+50h+pcbData], rax; pcbData
0x1800f3a96  lea     r8, aSecurityHklmOn; "Security_HKLM_Only"
0x1800f3a9d  lea     rax, [rbp+pvData]
0x1800f3aa1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f3aa8  mov     [rsp+50h+lpcbData], rax; pvData
0x1800f3aad  lea     rdx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\Internet"...
0x1800f3ab4  mov     [rsp+50h+phkResult], rdi; pdwType
0x1800f3ab9  call    cs:__imp_RegGetValueA
0x1800f3abf  test    eax, eax
0x1800f3ac1  cmovz   edi, [rbp+pvData]
0x1800f3ac5  jmp     loc_1800F38D8
```
