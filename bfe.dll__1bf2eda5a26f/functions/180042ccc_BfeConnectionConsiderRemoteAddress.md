# BfeConnectionConsiderRemoteAddress

- ea: `0x180042ccc`
- end: `0x180042ede`
- name: `BfeConnectionConsiderRemoteAddress`
- size: `530`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18005566c`
- `0x1800570e8`

## callees

- `0x1800039e4`
- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180042ccc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042e7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042e7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042d3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042d3a`

## string_xrefs

- `0x180042d1b`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180042d94`: `ConsiderRemoteAddress`
- `0x180042e6e`: `ConsiderRemoteAddress`
- `0x180042dda`: `RegOpenKeyExW`
- `0x180042e4d`: `BfeRegOpenKey`

## pseudocode

```c
__int64 __fastcall BfeConnectionConsiderRemoteAddress(__int64 a1)
{
  unsigned int v1; // esi
  LPBYTE v2; // r14
  unsigned int v3; // r13d
  int v4; // r12d
  unsigned int v5; // eax
  __int64 v6; // rcx
  HKEY v7; // rbx
  __int64 v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  LPBYTE lpData; // [rsp+30h] [rbp-48h] BYREF
  LPBYTE v14; // [rsp+38h] [rbp-40h] BYREF
  DWORD v15; // [rsp+40h] [rbp-38h]
  DWORD cbData; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD Type; // [rsp+58h] [rbp-20h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 8) == 2 )
  {
    v15 = 4;
    v2 = 0;
    v14 = 0;
    Type = 0;
    cbData = 0;
    lpData = 0;
    v3 = 0;
    hKey = 0;
    v4 = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
           0,
           1u,
           &hKey);
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      v11 = WfpReportSysErrorAsWinError(v6, "RegOpenKeyExW", v5);
      v8 = v11;
      if ( v11 )
        WfpReportError(v11, "BfeRegOpenKey");
      v7 = 0;
    }
    else if ( v5 == 2 )
    {
      v7 = 0;
      v8 = 0;
    }
    else
    {
      v7 = hKey;
      cbData = v15;
      v8 = WfpMemAlloc(v15, 0);
      if ( !v8 )
      {
        v9 = RegQueryValueExW(v7, L"ConsiderRemoteAddress", 0, &Type, lpData, &cbData);
        if ( v9 != 2 && v9 != 234 )
        {
          if ( v9 )
          {
            v8 = WfpReportSysErrorAsWinError(v10, "RegQueryValueExW", v9);
          }
          else if ( Type == 4 && cbData == v15 )
          {
            v2 = lpData;
            v14 = lpData;
            lpData = 0;
            v4 = 1;
          }
        }
      }
    }
    WfpMemFree(&lpData);
    BfeRegCloseKey(v7);
    if ( v8 )
    {
      WfpReportError(v8, "BfeRegQueryValue");
    }
    else if ( v4 )
    {
      v3 = *(_DWORD *)v2;
    }
    WfpMemFree(&v14);
    if ( v8 )
    {
      WfpReportError(v8, "BfeRegQueryDWord");
    }
    else
    {
      v1 = 1;
      if ( v4 )
        return v3;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180042ccc  push    rbp
0x180042cce  push    rbx
0x180042ccf  push    rsi
0x180042cd0  push    rdi
0x180042cd1  push    r12
0x180042cd3  push    r13
0x180042cd5  push    r14
0x180042cd7  push    r15
0x180042cd9  mov     rbp, rsp
0x180042cdc  sub     rsp, 78h
0x180042ce0  mov     rax, cs:__security_cookie
0x180042ce7  xor     rax, rsp
0x180042cea  mov     [rbp+var_18], rax
0x180042cee  xor     esi, esi
0x180042cf0  cmp     dword ptr [rcx+8], 2
0x180042cf4  jnz     loc_180042E2E
0x180042cfa  lea     rax, [rbp+hKey]
0x180042cfe  mov     [rbp+var_38], 4
0x180042d05  xor     r14d, r14d
0x180042d08  mov     [rsp+78h+phkResult], rax; phkResult
0x180042d0d  lea     r9d, [rsi+1]; samDesired
0x180042d11  mov     [rbp+var_40], r14
0x180042d15  xor     r8d, r8d; ulOptions
0x180042d18  mov     [rbp+Type], esi
0x180042d1b  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\BF"...
0x180042d22  mov     [rbp+cbData], esi
0x180042d25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042d2c  mov     [rbp+lpData], rsi
0x180042d30  xor     r13d, r13d
0x180042d33  mov     [rbp+hKey], rsi
0x180042d37  xor     r12d, r12d
0x180042d3a  call    cs:__imp_RegOpenKeyExW
0x180042d40  test    eax, 0FFFFFFFDh
0x180042d45  jnz     loc_180042DD7
0x180042d4b  cmp     eax, 2
0x180042d4e  jz      loc_180042EAF
0x180042d54  mov     eax, [rbp+var_38]
0x180042d57  mov     rbx, [rbp+hKey]
0x180042d5b  test    eax, eax
0x180042d5d  jz      loc_180042E5E
0x180042d63  mov     ecx, eax; dwBytes
0x180042d65  lea     r8, [rbp+lpData]
0x180042d69  xor     edx, edx; dwFlags
0x180042d6b  mov     [rbp+cbData], eax
0x180042d6e  call    WfpMemAlloc
0x180042d73  mov     rdi, rax
0x180042d76  test    rax, rax
0x180042d79  jnz     short loc_180042DF0
0x180042d7b  mov     r15, [rbp+lpData]
0x180042d7f  lea     rax, [rbp+cbData]
0x180042d83  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180042d88  lea     r9, [rbp+Type]; lpType
0x180042d8c  xor     r8d, r8d; lpReserved
0x180042d8f  mov     [rsp+78h+phkResult], r15; lpData
0x180042d94  lea     rdx, aConsiderremote; "ConsiderRemoteAddress"
0x180042d9b  mov     rcx, rbx; hKey
0x180042d9e  call    cs:__imp_RegQueryValueExW
0x180042da4  cmp     eax, 2
0x180042da7  jz      short loc_180042DF0
0x180042da9  cmp     eax, 0EAh
0x180042dae  jz      short loc_180042DF0
0x180042db0  test    eax, eax
0x180042db2  jnz     loc_180042E98
0x180042db8  cmp     [rbp+Type], 4
0x180042dbc  jnz     short loc_180042DF0
0x180042dbe  mov     eax, [rbp+var_38]
0x180042dc1  cmp     [rbp+cbData], eax
0x180042dc4  jnz     short loc_180042DF0
0x180042dc6  mov     r14, r15
0x180042dc9  mov     [rbp+var_40], r15
0x180042dcd  mov     [rbp+lpData], rsi
0x180042dd1  lea     r12d, [rdi+1]
0x180042dd5  jmp     short loc_180042DF0
0x180042dd7  mov     r8d, eax
0x180042dda  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180042de1  call    WfpReportSysErrorAsWinError
0x180042de6  mov     rdi, rax
0x180042de9  test    rax, rax
0x180042dec  jnz     short loc_180042E4D
0x180042dee  xor     ebx, ebx
0x180042df0  lea     rcx, [rbp+lpData]
0x180042df4  call    WfpMemFree
0x180042df9  mov     rcx, rbx
0x180042dfc  call    BfeRegCloseKey
0x180042e01  test    rdi, rdi
0x180042e04  jnz     loc_180042EB6
0x180042e0a  test    r12d, r12d
0x180042e0d  jz      short loc_180042E12
0x180042e0f  mov     r13d, [r14]
0x180042e12  lea     rcx, [rbp+var_40]
0x180042e16  call    WfpMemFree
0x180042e1b  test    rdi, rdi
0x180042e1e  jnz     loc_180042ECA
0x180042e24  test    r12d, r12d
0x180042e27  lea     esi, [rdi+1]
0x180042e2a  cmovnz  esi, r13d
0x180042e2e  mov     eax, esi
0x180042e30  mov     rcx, [rbp+var_18]
0x180042e34  xor     rcx, rsp; StackCookie
0x180042e37  call    __security_check_cookie
0x180042e3c  add     rsp, 78h
0x180042e40  pop     r15
0x180042e42  pop     r14
0x180042e44  pop     r13
0x180042e46  pop     r12
0x180042e48  pop     rdi
0x180042e49  pop     rsi
0x180042e4a  pop     rbx
0x180042e4b  pop     rbp
0x180042e4c  retn
0x180042e4d  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180042e54  mov     rcx, rax
0x180042e57  call    WfpReportError
0x180042e5c  jmp     short loc_180042DEE
0x180042e5e  lea     rax, [rbp+var_38]
0x180042e62  xor     r8d, r8d; lpReserved
0x180042e65  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180042e6a  lea     r9, [rbp+Type]; lpType
0x180042e6e  lea     rdx, aConsiderremote; "ConsiderRemoteAddress"
0x180042e75  mov     [rsp+78h+phkResult], rsi; lpData
0x180042e7a  mov     rcx, rbx; hKey
0x180042e7d  call    cs:__imp_RegQueryValueExW
0x180042e83  cmp     eax, 2
0x180042e86  jz      loc_18008A7D0
0x180042e8c  test    eax, eax
0x180042e8e  jnz     short loc_180042E98
0x180042e90  mov     eax, [rbp+var_38]
0x180042e93  jmp     loc_180042D63
0x180042e98  mov     r8d, eax
0x180042e9b  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180042ea2  call    WfpReportSysErrorAsWinError
0x180042ea7  mov     rdi, rax
0x180042eaa  jmp     loc_180042DF0
0x180042eaf  xor     ebx, ebx
0x180042eb1  jmp     loc_18008A7D0
0x180042eb6  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180042ebd  mov     rcx, rdi
0x180042ec0  call    WfpReportError
0x180042ec5  jmp     loc_180042E12
0x180042eca  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x180042ed1  mov     rcx, rdi
0x180042ed4  call    WfpReportError
0x180042ed9  jmp     loc_180042E2E
0x18008a7d0  xor     edi, edi
0x18008a7d2  jmp     loc_180042DF0
```
