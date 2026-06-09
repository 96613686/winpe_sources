# AccessCPURegistry

- ea: `0x180095a94`
- end: `0x180095c3b`
- name: `AccessCPURegistry`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180095d64`

## callees

- `0x180095a94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095c1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095c1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095ade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095b16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095b4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095ade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095b16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095b4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095b8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095bd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095b8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095bd3`

## string_xrefs

- `0x180095b84`: `NumThreads`

## pseudocode

```c
__int64 __fastcall AccessCPURegistry(int a1, BYTE *a2)
{
  unsigned int v2; // ebx
  HKEY v6; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  cbData = 4;
  Type = 0;
  v6 = 0;
  phkResult = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE", 0, 1u, &hKey)
    || !hKey
    || RegOpenKeyExW(hKey, L"Microsoft", 0, 1u, &phkResult)
    || !phkResult
    || RegOpenKeyExW(phkResult, L"Scrunch", 0, 1u, &v6) )
  {
    goto LABEL_15;
  }
  if ( !a1 )
  {
    if ( !RegQueryValueExW(v6, L"CPU Downgrade Level", 0, &Type, a2, &cbData) && Type == 4 )
      goto LABEL_15;
LABEL_14:
    v2 = -1;
    goto LABEL_15;
  }
  if ( a1 != 1 || RegQueryValueExW(v6, L"NumThreads", 0, &Type, a2, &cbData) || Type != 4 )
    goto LABEL_14;
  if ( (unsigned int)(*(_DWORD *)a2 - 65) <= 0xFFFFFFBD )
    *(_DWORD *)a2 = 64;
LABEL_15:
  if ( v6 )
    RegCloseKey(v6);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180095a94  mov     [rsp-18h+arg_0], rbx
0x180095a99  push    rbp
0x180095a9a  push    rsi
0x180095a9b  push    rdi
0x180095a9c  mov     rbp, rsp
0x180095a9f  sub     rsp, 50h
0x180095aa3  xor     ebx, ebx
0x180095aa5  mov     [rbp+cbData], 4
0x180095aac  mov     rsi, rdx
0x180095aaf  mov     [rbp+Type], ebx
0x180095ab2  mov     edi, ecx
0x180095ab4  mov     [rbp+var_20], rbx
0x180095ab8  lea     rax, [rbp+hKey]
0x180095abc  mov     [rbp+var_18], rbx
0x180095ac0  lea     r9d, [rbx+1]; samDesired
0x180095ac4  mov     [rbp+hKey], rbx
0x180095ac8  xor     r8d, r8d; ulOptions
0x180095acb  mov     [rsp+50h+phkResult], rax; phkResult
0x180095ad0  lea     rdx, SubKey; "SOFTWARE"
0x180095ad7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180095ade  call    cs:__imp_RegOpenKeyExW
0x180095ae5  nop     dword ptr [rax+rax+00h]
0x180095aea  test    eax, eax
0x180095aec  jnz     loc_180095BEC
0x180095af2  mov     rcx, [rbp+hKey]; hKey
0x180095af6  test    rcx, rcx
0x180095af9  jz      loc_180095BEC
0x180095aff  lea     rax, [rbp+var_18]
0x180095b03  xor     r8d, r8d; ulOptions
0x180095b06  lea     r9d, [rbx+1]; samDesired
0x180095b0a  mov     [rsp+50h+phkResult], rax; phkResult
0x180095b0f  lea     rdx, aMicrosoft; "Microsoft"
0x180095b16  call    cs:__imp_RegOpenKeyExW
0x180095b1d  nop     dword ptr [rax+rax+00h]
0x180095b22  test    eax, eax
0x180095b24  jnz     loc_180095BEC
0x180095b2a  mov     rcx, [rbp+var_18]; hKey
0x180095b2e  test    rcx, rcx
0x180095b31  jz      loc_180095BEC
0x180095b37  lea     rax, [rbp+var_20]
0x180095b3b  xor     r8d, r8d; ulOptions
0x180095b3e  lea     r9d, [rbx+1]; samDesired
0x180095b42  mov     [rsp+50h+phkResult], rax; phkResult
0x180095b47  lea     rdx, aScrunch; "Scrunch"
0x180095b4e  call    cs:__imp_RegOpenKeyExW
0x180095b55  nop     dword ptr [rax+rax+00h]
0x180095b5a  test    eax, eax
0x180095b5c  jnz     loc_180095BEC
0x180095b62  test    edi, edi
0x180095b64  jz      short loc_180095BB3
0x180095b66  cmp     edi, 1
0x180095b69  jnz     short loc_180095BE9
0x180095b6b  mov     rcx, [rbp+var_20]; hKey
0x180095b6f  lea     rax, [rbp+cbData]
0x180095b73  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180095b78  lea     r9, [rbp+Type]; lpType
0x180095b7c  xor     r8d, r8d; lpReserved
0x180095b7f  mov     [rsp+50h+phkResult], rsi; lpData
0x180095b84  lea     rdx, aNumthreads; "NumThreads"
0x180095b8b  call    cs:__imp_RegQueryValueExW
0x180095b92  nop     dword ptr [rax+rax+00h]
0x180095b97  test    eax, eax
0x180095b99  jnz     short loc_180095BE9
0x180095b9b  cmp     [rbp+Type], 4
0x180095b9f  jnz     short loc_180095BE9
0x180095ba1  mov     eax, [rsi]
0x180095ba3  sub     eax, 41h ; 'A'
0x180095ba6  cmp     eax, 0FFFFFFBDh
0x180095ba9  ja      short loc_180095BEC
0x180095bab  mov     dword ptr [rsi], 40h ; '@'
0x180095bb1  jmp     short loc_180095BEC
0x180095bb3  mov     rcx, [rbp+var_20]; hKey
0x180095bb7  lea     rax, [rbp+cbData]
0x180095bbb  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180095bc0  lea     r9, [rbp+Type]; lpType
0x180095bc4  xor     r8d, r8d; lpReserved
0x180095bc7  mov     [rsp+50h+phkResult], rsi; lpData
0x180095bcc  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x180095bd3  call    cs:__imp_RegQueryValueExW
0x180095bda  nop     dword ptr [rax+rax+00h]
0x180095bdf  test    eax, eax
0x180095be1  jnz     short loc_180095BE9
0x180095be3  cmp     [rbp+Type], 4
0x180095be7  jz      short loc_180095BEC
0x180095be9  or      ebx, 0FFFFFFFFh
0x180095bec  mov     rcx, [rbp+var_20]; hKey
0x180095bf0  test    rcx, rcx
0x180095bf3  jz      short loc_180095C01
0x180095bf5  call    cs:__imp_RegCloseKey
0x180095bfc  nop     dword ptr [rax+rax+00h]
0x180095c01  mov     rcx, [rbp+var_18]; hKey
0x180095c05  test    rcx, rcx
0x180095c08  jz      short loc_180095C16
0x180095c0a  call    cs:__imp_RegCloseKey
0x180095c11  nop     dword ptr [rax+rax+00h]
0x180095c16  mov     rcx, [rbp+hKey]; hKey
0x180095c1a  test    rcx, rcx
0x180095c1d  jz      short loc_180095C2B
0x180095c1f  call    cs:__imp_RegCloseKey
0x180095c26  nop     dword ptr [rax+rax+00h]
0x180095c2b  mov     eax, ebx
0x180095c2d  mov     rbx, [rsp+50h+arg_0]
0x180095c32  add     rsp, 50h
0x180095c36  pop     rdi
0x180095c37  pop     rsi
0x180095c38  pop     rbp
0x180095c39  retn
```
