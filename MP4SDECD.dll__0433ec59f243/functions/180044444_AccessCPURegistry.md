# AccessCPURegistry

- ea: `0x180044444`
- end: `0x1800445b6`
- name: `AccessCPURegistry`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800445e8`

## callees

- `0x180044444`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044567`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800445a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800445a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004448e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004448e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444f2`

## string_xrefs

- `0x18004451e`: `NumThreads`

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
0x180044444  mov     [rsp-18h+arg_0], rbx
0x180044449  push    rbp
0x18004444a  push    rsi
0x18004444b  push    rdi
0x18004444c  mov     rbp, rsp
0x18004444f  sub     rsp, 50h
0x180044453  xor     ebx, ebx
0x180044455  mov     [rbp+cbData], 4
0x18004445c  mov     rsi, rdx
0x18004445f  mov     [rbp+Type], ebx
0x180044462  mov     edi, ecx
0x180044464  mov     [rbp+var_20], rbx
0x180044468  lea     rax, [rbp+hKey]
0x18004446c  mov     [rbp+var_18], rbx
0x180044470  lea     r9d, [rbx+1]; samDesired
0x180044474  mov     [rbp+hKey], rbx
0x180044478  xor     r8d, r8d; ulOptions
0x18004447b  mov     [rsp+50h+phkResult], rax; phkResult
0x180044480  lea     rdx, SubKey; "SOFTWARE"
0x180044487  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004448e  call    cs:__imp_RegOpenKeyExW
0x180044494  test    eax, eax
0x180044496  jnz     loc_18004457A
0x18004449c  mov     rcx, [rbp+hKey]; hKey
0x1800444a0  test    rcx, rcx
0x1800444a3  jz      loc_18004457A
0x1800444a9  lea     rax, [rbp+var_18]
0x1800444ad  xor     r8d, r8d; ulOptions
0x1800444b0  lea     r9d, [rbx+1]; samDesired
0x1800444b4  mov     [rsp+50h+phkResult], rax; phkResult
0x1800444b9  lea     rdx, aMicrosoft; "Microsoft"
0x1800444c0  call    cs:__imp_RegOpenKeyExW
0x1800444c6  test    eax, eax
0x1800444c8  jnz     loc_18004457A
0x1800444ce  mov     rcx, [rbp+var_18]; hKey
0x1800444d2  test    rcx, rcx
0x1800444d5  jz      loc_18004457A
0x1800444db  lea     rax, [rbp+var_20]
0x1800444df  xor     r8d, r8d; ulOptions
0x1800444e2  lea     r9d, [rbx+1]; samDesired
0x1800444e6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800444eb  lea     rdx, aScrunch; "Scrunch"
0x1800444f2  call    cs:__imp_RegOpenKeyExW
0x1800444f8  test    eax, eax
0x1800444fa  jnz     short loc_18004457A
0x1800444fc  test    edi, edi
0x1800444fe  jz      short loc_180044547
0x180044500  cmp     edi, 1
0x180044503  jnz     short loc_180044577
0x180044505  mov     rcx, [rbp+var_20]; hKey
0x180044509  lea     rax, [rbp+cbData]
0x18004450d  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180044512  lea     r9, [rbp+Type]; lpType
0x180044516  xor     r8d, r8d; lpReserved
0x180044519  mov     [rsp+50h+phkResult], rsi; lpData
0x18004451e  lea     rdx, aNumthreads; "NumThreads"
0x180044525  call    cs:__imp_RegQueryValueExW
0x18004452b  test    eax, eax
0x18004452d  jnz     short loc_180044577
0x18004452f  cmp     [rbp+Type], 4
0x180044533  jnz     short loc_180044577
0x180044535  mov     eax, [rsi]
0x180044537  sub     eax, 41h ; 'A'
0x18004453a  cmp     eax, 0FFFFFFBDh
0x18004453d  ja      short loc_18004457A
0x18004453f  mov     dword ptr [rsi], 40h ; '@'
0x180044545  jmp     short loc_18004457A
0x180044547  mov     rcx, [rbp+var_20]; hKey
0x18004454b  lea     rax, [rbp+cbData]
0x18004454f  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180044554  lea     r9, [rbp+Type]; lpType
0x180044558  xor     r8d, r8d; lpReserved
0x18004455b  mov     [rsp+50h+phkResult], rsi; lpData
0x180044560  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x180044567  call    cs:__imp_RegQueryValueExW
0x18004456d  test    eax, eax
0x18004456f  jnz     short loc_180044577
0x180044571  cmp     [rbp+Type], 4
0x180044575  jz      short loc_18004457A
0x180044577  or      ebx, 0FFFFFFFFh
0x18004457a  mov     rcx, [rbp+var_20]; hKey
0x18004457e  test    rcx, rcx
0x180044581  jz      short loc_180044589
0x180044583  call    cs:__imp_RegCloseKey
0x180044589  mov     rcx, [rbp+var_18]; hKey
0x18004458d  test    rcx, rcx
0x180044590  jz      short loc_180044598
0x180044592  call    cs:__imp_RegCloseKey
0x180044598  mov     rcx, [rbp+hKey]; hKey
0x18004459c  test    rcx, rcx
0x18004459f  jz      short loc_1800445A7
0x1800445a1  call    cs:__imp_RegCloseKey
0x1800445a7  mov     eax, ebx
0x1800445a9  mov     rbx, [rsp+50h+arg_0]
0x1800445ae  add     rsp, 50h
0x1800445b2  pop     rdi
0x1800445b3  pop     rsi
0x1800445b4  pop     rbp
0x1800445b5  retn
```
