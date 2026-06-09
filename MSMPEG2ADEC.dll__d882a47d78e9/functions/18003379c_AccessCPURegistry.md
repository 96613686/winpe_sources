# AccessCPURegistry

- ea: `0x18003379c`
- end: `0x180033943`
- name: `AccessCPURegistry`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033a48`
- `0x180073bd0`

## callees

- `0x18003379c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033893`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800338db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033893`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800338db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033927`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800338fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033927`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003381e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033856`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800337e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003381e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033856`

## string_xrefs

- `0x18003388c`: `NumThreads`

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
0x18003379c  mov     [rsp-18h+arg_0], rbx
0x1800337a1  push    rbp
0x1800337a2  push    rsi
0x1800337a3  push    rdi
0x1800337a4  mov     rbp, rsp
0x1800337a7  sub     rsp, 50h
0x1800337ab  xor     ebx, ebx
0x1800337ad  mov     [rbp+cbData], 4
0x1800337b4  mov     rsi, rdx
0x1800337b7  mov     [rbp+Type], ebx
0x1800337ba  mov     edi, ecx
0x1800337bc  mov     [rbp+var_20], rbx
0x1800337c0  lea     rax, [rbp+hKey]
0x1800337c4  mov     [rbp+var_18], rbx
0x1800337c8  lea     r9d, [rbx+1]; samDesired
0x1800337cc  mov     [rbp+hKey], rbx
0x1800337d0  xor     r8d, r8d; ulOptions
0x1800337d3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800337d8  lea     rdx, aSoftware; "SOFTWARE"
0x1800337df  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800337e6  call    cs:__imp_RegOpenKeyExW
0x1800337ed  nop     dword ptr [rax+rax+00h]
0x1800337f2  test    eax, eax
0x1800337f4  jnz     loc_1800338F4
0x1800337fa  mov     rcx, [rbp+hKey]; hKey
0x1800337fe  test    rcx, rcx
0x180033801  jz      loc_1800338F4
0x180033807  lea     rax, [rbp+var_18]
0x18003380b  xor     r8d, r8d; ulOptions
0x18003380e  lea     r9d, [rbx+1]; samDesired
0x180033812  mov     [rsp+50h+phkResult], rax; phkResult
0x180033817  lea     rdx, aMicrosoft; "Microsoft"
0x18003381e  call    cs:__imp_RegOpenKeyExW
0x180033825  nop     dword ptr [rax+rax+00h]
0x18003382a  test    eax, eax
0x18003382c  jnz     loc_1800338F4
0x180033832  mov     rcx, [rbp+var_18]; hKey
0x180033836  test    rcx, rcx
0x180033839  jz      loc_1800338F4
0x18003383f  lea     rax, [rbp+var_20]
0x180033843  xor     r8d, r8d; ulOptions
0x180033846  lea     r9d, [rbx+1]; samDesired
0x18003384a  mov     [rsp+50h+phkResult], rax; phkResult
0x18003384f  lea     rdx, aScrunch; "Scrunch"
0x180033856  call    cs:__imp_RegOpenKeyExW
0x18003385d  nop     dword ptr [rax+rax+00h]
0x180033862  test    eax, eax
0x180033864  jnz     loc_1800338F4
0x18003386a  test    edi, edi
0x18003386c  jz      short loc_1800338BB
0x18003386e  cmp     edi, 1
0x180033871  jnz     short loc_1800338F1
0x180033873  mov     rcx, [rbp+var_20]; hKey
0x180033877  lea     rax, [rbp+cbData]
0x18003387b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180033880  lea     r9, [rbp+Type]; lpType
0x180033884  xor     r8d, r8d; lpReserved
0x180033887  mov     [rsp+50h+phkResult], rsi; lpData
0x18003388c  lea     rdx, aNumthreads; "NumThreads"
0x180033893  call    cs:__imp_RegQueryValueExW
0x18003389a  nop     dword ptr [rax+rax+00h]
0x18003389f  test    eax, eax
0x1800338a1  jnz     short loc_1800338F1
0x1800338a3  cmp     [rbp+Type], 4
0x1800338a7  jnz     short loc_1800338F1
0x1800338a9  mov     eax, [rsi]
0x1800338ab  sub     eax, 41h ; 'A'
0x1800338ae  cmp     eax, 0FFFFFFBDh
0x1800338b1  ja      short loc_1800338F4
0x1800338b3  mov     dword ptr [rsi], 40h ; '@'
0x1800338b9  jmp     short loc_1800338F4
0x1800338bb  mov     rcx, [rbp+var_20]; hKey
0x1800338bf  lea     rax, [rbp+cbData]
0x1800338c3  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800338c8  lea     r9, [rbp+Type]; lpType
0x1800338cc  xor     r8d, r8d; lpReserved
0x1800338cf  mov     [rsp+50h+phkResult], rsi; lpData
0x1800338d4  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x1800338db  call    cs:__imp_RegQueryValueExW
0x1800338e2  nop     dword ptr [rax+rax+00h]
0x1800338e7  test    eax, eax
0x1800338e9  jnz     short loc_1800338F1
0x1800338eb  cmp     [rbp+Type], 4
0x1800338ef  jz      short loc_1800338F4
0x1800338f1  or      ebx, 0FFFFFFFFh
0x1800338f4  mov     rcx, [rbp+var_20]; hKey
0x1800338f8  test    rcx, rcx
0x1800338fb  jz      short loc_180033909
0x1800338fd  call    cs:__imp_RegCloseKey
0x180033904  nop     dword ptr [rax+rax+00h]
0x180033909  mov     rcx, [rbp+var_18]; hKey
0x18003390d  test    rcx, rcx
0x180033910  jz      short loc_18003391E
0x180033912  call    cs:__imp_RegCloseKey
0x180033919  nop     dword ptr [rax+rax+00h]
0x18003391e  mov     rcx, [rbp+hKey]; hKey
0x180033922  test    rcx, rcx
0x180033925  jz      short loc_180033933
0x180033927  call    cs:__imp_RegCloseKey
0x18003392e  nop     dword ptr [rax+rax+00h]
0x180033933  mov     eax, ebx
0x180033935  mov     rbx, [rsp+50h+arg_0]
0x18003393a  add     rsp, 50h
0x18003393e  pop     rdi
0x18003393f  pop     rsi
0x180033940  pop     rbp
0x180033941  retn
```
