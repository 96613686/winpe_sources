# pSpSignGetPnpSetupInProgress

- ea: `0x14002f62c`
- end: `0x14002f6cf`
- name: `pSpSignGetPnpSetupInProgress`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14002c9a8`
- `0x14002ccdc`

## callees

- `0x14002f62c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f672`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f672`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f6bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f6bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002f6a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002f6a0`

## pseudocode

```c
_BOOL8 pSpSignGetPnpSetupInProgress()
{
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 0x20019u, &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"PnpSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  return Data != 0;
}

```

## disassembly

```asm
0x14002f62c  push    rbp
0x14002f62e  mov     rbp, rsp
0x14002f631  sub     rsp, 30h
0x14002f635  lea     rax, [rbp+hKey]
0x14002f639  mov     [rbp+hKey], 0
0x14002f641  mov     r9d, 20019h; samDesired
0x14002f647  mov     [rsp+30h+phkResult], rax; phkResult
0x14002f64c  xor     r8d, r8d; ulOptions
0x14002f64f  mov     [rbp+Type], 0
0x14002f656  lea     rdx, aSystemSetup; "System\\Setup"
0x14002f65d  mov     [rbp+cbData], 4
0x14002f664  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002f66b  mov     [rbp+Data], 0
0x14002f672  call    cs:__imp_RegOpenKeyExW
0x14002f678  test    eax, eax
0x14002f67a  jnz     short loc_14002F6C1
0x14002f67c  mov     rcx, [rbp+hKey]; hKey
0x14002f680  lea     rax, [rbp+cbData]
0x14002f684  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14002f689  lea     r9, [rbp+Type]; lpType
0x14002f68d  lea     rax, [rbp+Data]
0x14002f691  xor     r8d, r8d; lpReserved
0x14002f694  lea     rdx, aPnpsetupinprog; "PnpSetupInProgress"
0x14002f69b  mov     [rsp+30h+phkResult], rax; lpData
0x14002f6a0  call    cs:__imp_RegQueryValueExW
0x14002f6a6  test    eax, eax
0x14002f6a8  jnz     short loc_14002F6B0
0x14002f6aa  cmp     [rbp+Type], 4
0x14002f6ae  jz      short loc_14002F6B7
0x14002f6b0  mov     [rbp+Data], 0
0x14002f6b7  mov     rcx, [rbp+hKey]; hKey
0x14002f6bb  call    cs:__imp_RegCloseKey
0x14002f6c1  xor     eax, eax
0x14002f6c3  cmp     [rbp+Data], eax
0x14002f6c6  setnz   al
0x14002f6c9  add     rsp, 30h
0x14002f6cd  pop     rbp
0x14002f6ce  retn
```
