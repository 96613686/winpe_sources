# pSpSignGetGuiSetupInProgress

- ea: `0x14002f3f8`
- end: `0x14002f49c`
- name: `pSpSignGetGuiSetupInProgress`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14002c9a8`
- `0x14002ccdc`

## callees

- `0x14002f3f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f43f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f43f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f479`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f479`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002f46d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002f46d`

## pseudocode

```c
_BOOL8 pSpSignGetGuiSetupInProgress()
{
  LSTATUS v0; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 0x20019u, &hKey) )
    return 0;
  v0 = RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  return !v0 && Type == 4 && Data != 0;
}

```

## disassembly

```asm
0x14002f3f8  push    rbp
0x14002f3fa  push    rbx
0x14002f3fb  mov     rbp, rsp
0x14002f3fe  sub     rsp, 38h
0x14002f402  lea     rax, [rbp+hKey]
0x14002f406  mov     [rbp+hKey], 0
0x14002f40e  mov     r9d, 20019h; samDesired
0x14002f414  mov     [rsp+38h+phkResult], rax; phkResult
0x14002f419  xor     r8d, r8d; ulOptions
0x14002f41c  mov     [rbp+Type], 4
0x14002f423  lea     rdx, aSystemSetup; "System\\Setup"
0x14002f42a  mov     [rbp+cbData], 4
0x14002f431  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002f438  mov     [rbp+Data], 0
0x14002f43f  call    cs:__imp_RegOpenKeyExW
0x14002f445  test    eax, eax
0x14002f447  jnz     short loc_14002F493
0x14002f449  mov     rcx, [rbp+hKey]; hKey
0x14002f44d  lea     rax, [rbp+cbData]
0x14002f451  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14002f456  lea     r9, [rbp+Type]; lpType
0x14002f45a  lea     rax, [rbp+Data]
0x14002f45e  xor     r8d, r8d; lpReserved
0x14002f461  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x14002f468  mov     [rsp+38h+phkResult], rax; lpData
0x14002f46d  call    cs:__imp_RegQueryValueExW
0x14002f473  mov     rcx, [rbp+hKey]; hKey
0x14002f477  mov     ebx, eax
0x14002f479  call    cs:__imp_RegCloseKey
0x14002f47f  test    ebx, ebx
0x14002f481  jnz     short loc_14002F493
0x14002f483  cmp     [rbp+Type], 4
0x14002f487  jnz     short loc_14002F493
0x14002f489  xor     eax, eax
0x14002f48b  cmp     [rbp+Data], eax
0x14002f48e  setnz   al
0x14002f491  jmp     short loc_14002F495
0x14002f493  xor     eax, eax
0x14002f495  add     rsp, 38h
0x14002f499  pop     rbx
0x14002f49a  pop     rbp
0x14002f49b  retn
```
