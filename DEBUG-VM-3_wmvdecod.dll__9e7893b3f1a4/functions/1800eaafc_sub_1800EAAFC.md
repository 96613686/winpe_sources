# sub_1800EAAFC

- ea: `0x1800eaafc`
- end: `0x1800eaca3`
- name: `sub_1800EAAFC`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eb764`

## callees

- `0x1800eaafc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eabb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eab7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eabb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eac87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eac3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eabf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eac3b`

## string_xrefs

- `0x1800eabec`: `NumThreads`

## pseudocode

```c
__int64 __fastcall sub_1800EAAFC(int a1, BYTE *a2)
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
0x1800eaafc  mov     [rsp-18h+arg_0], rbx
0x1800eab01  push    rbp
0x1800eab02  push    rsi
0x1800eab03  push    rdi
0x1800eab04  mov     rbp, rsp
0x1800eab07  sub     rsp, 50h
0x1800eab0b  xor     ebx, ebx
0x1800eab0d  mov     [rbp+cbData], 4
0x1800eab14  mov     rsi, rdx
0x1800eab17  mov     [rbp+Type], ebx
0x1800eab1a  mov     edi, ecx
0x1800eab1c  mov     [rbp+var_20], rbx
0x1800eab20  lea     rax, [rbp+hKey]
0x1800eab24  mov     [rbp+var_18], rbx
0x1800eab28  lea     r9d, [rbx+1]; samDesired
0x1800eab2c  mov     [rbp+hKey], rbx
0x1800eab30  xor     r8d, r8d; ulOptions
0x1800eab33  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eab38  lea     rdx, aSoftware; "SOFTWARE"
0x1800eab3f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800eab46  call    cs:RegOpenKeyExW
0x1800eab4d  nop     dword ptr [rax+rax+00h]
0x1800eab52  test    eax, eax
0x1800eab54  jnz     loc_1800EAC54
0x1800eab5a  mov     rcx, [rbp+hKey]; hKey
0x1800eab5e  test    rcx, rcx
0x1800eab61  jz      loc_1800EAC54
0x1800eab67  lea     rax, [rbp+var_18]
0x1800eab6b  xor     r8d, r8d; ulOptions
0x1800eab6e  lea     r9d, [rbx+1]; samDesired
0x1800eab72  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eab77  lea     rdx, aMicrosoft; "Microsoft"
0x1800eab7e  call    cs:RegOpenKeyExW
0x1800eab85  nop     dword ptr [rax+rax+00h]
0x1800eab8a  test    eax, eax
0x1800eab8c  jnz     loc_1800EAC54
0x1800eab92  mov     rcx, [rbp+var_18]; hKey
0x1800eab96  test    rcx, rcx
0x1800eab99  jz      loc_1800EAC54
0x1800eab9f  lea     rax, [rbp+var_20]
0x1800eaba3  xor     r8d, r8d; ulOptions
0x1800eaba6  lea     r9d, [rbx+1]; samDesired
0x1800eabaa  mov     [rsp+50h+phkResult], rax; phkResult
0x1800eabaf  lea     rdx, aScrunch; "Scrunch"
0x1800eabb6  call    cs:RegOpenKeyExW
0x1800eabbd  nop     dword ptr [rax+rax+00h]
0x1800eabc2  test    eax, eax
0x1800eabc4  jnz     loc_1800EAC54
0x1800eabca  test    edi, edi
0x1800eabcc  jz      short loc_1800EAC1B
0x1800eabce  cmp     edi, 1
0x1800eabd1  jnz     short loc_1800EAC51
0x1800eabd3  mov     rcx, [rbp+var_20]; hKey
0x1800eabd7  lea     rax, [rbp+cbData]
0x1800eabdb  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800eabe0  lea     r9, [rbp+Type]; lpType
0x1800eabe4  xor     r8d, r8d; lpReserved
0x1800eabe7  mov     [rsp+50h+phkResult], rsi; lpData
0x1800eabec  lea     rdx, aNumthreads; "NumThreads"
0x1800eabf3  call    cs:RegQueryValueExW
0x1800eabfa  nop     dword ptr [rax+rax+00h]
0x1800eabff  test    eax, eax
0x1800eac01  jnz     short loc_1800EAC51
0x1800eac03  cmp     [rbp+Type], 4
0x1800eac07  jnz     short loc_1800EAC51
0x1800eac09  mov     eax, [rsi]
0x1800eac0b  sub     eax, 41h ; 'A'
0x1800eac0e  cmp     eax, 0FFFFFFBDh
0x1800eac11  ja      short loc_1800EAC54
0x1800eac13  mov     dword ptr [rsi], 40h ; '@'
0x1800eac19  jmp     short loc_1800EAC54
0x1800eac1b  mov     rcx, [rbp+var_20]; hKey
0x1800eac1f  lea     rax, [rbp+cbData]
0x1800eac23  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800eac28  lea     r9, [rbp+Type]; lpType
0x1800eac2c  xor     r8d, r8d; lpReserved
0x1800eac2f  mov     [rsp+50h+phkResult], rsi; lpData
0x1800eac34  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x1800eac3b  call    cs:RegQueryValueExW
0x1800eac42  nop     dword ptr [rax+rax+00h]
0x1800eac47  test    eax, eax
0x1800eac49  jnz     short loc_1800EAC51
0x1800eac4b  cmp     [rbp+Type], 4
0x1800eac4f  jz      short loc_1800EAC54
0x1800eac51  or      ebx, 0FFFFFFFFh
0x1800eac54  mov     rcx, [rbp+var_20]; hKey
0x1800eac58  test    rcx, rcx
0x1800eac5b  jz      short loc_1800EAC69
0x1800eac5d  call    cs:RegCloseKey
0x1800eac64  nop     dword ptr [rax+rax+00h]
0x1800eac69  mov     rcx, [rbp+var_18]; hKey
0x1800eac6d  test    rcx, rcx
0x1800eac70  jz      short loc_1800EAC7E
0x1800eac72  call    cs:RegCloseKey
0x1800eac79  nop     dword ptr [rax+rax+00h]
0x1800eac7e  mov     rcx, [rbp+hKey]; hKey
0x1800eac82  test    rcx, rcx
0x1800eac85  jz      short loc_1800EAC93
0x1800eac87  call    cs:RegCloseKey
0x1800eac8e  nop     dword ptr [rax+rax+00h]
0x1800eac93  mov     eax, ebx
0x1800eac95  mov     rbx, [rsp+50h+arg_0]
0x1800eac9a  add     rsp, 50h
0x1800eac9e  pop     rdi
0x1800eac9f  pop     rsi
0x1800eaca0  pop     rbp
0x1800eaca1  retn
```
