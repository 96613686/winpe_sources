# GetDebugLevel(void)

- ea: `0x140071c54`
- end: `0x140071cfd`
- name: `?GetDebugLevel@@YAKXZ`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140071ec8`

## callees

- `0x140071c54`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140071cee`
- `ADVAPI32!RegCloseKey` at `0x140071cee`
- `ADVAPI32!RegOpenKeyExW` at `0x140071c9a`
- `ADVAPI32!RegOpenKeyExW` at `0x140071c9a`
- `ADVAPI32!RegQueryValueExW` at `0x140071cd3`
- `ADVAPI32!RegQueryValueExW` at `0x140071cd3`

## pseudocode

```c
__int64 GetDebugLevel(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20019u, &hKey) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    Data = 0;
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x140071c54  push    rbp
0x140071c56  mov     rbp, rsp
0x140071c59  sub     rsp, 30h
0x140071c5d  lea     rax, [rbp+hKey]
0x140071c61  mov     [rbp+Data], 0
0x140071c68  mov     r9d, 20019h; samDesired
0x140071c6e  mov     [rsp+30h+phkResult], rax; phkResult
0x140071c73  xor     r8d, r8d; ulOptions
0x140071c76  mov     [rbp+cbData], 0
0x140071c7d  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x140071c84  mov     [rbp+Type], 0
0x140071c8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140071c92  mov     [rbp+hKey], 0
0x140071c9a  call    cs:__imp_RegOpenKeyExW
0x140071ca0  test    eax, eax
0x140071ca2  jz      short loc_140071CA8
0x140071ca4  xor     eax, eax
0x140071ca6  jmp     short loc_140071CF7
0x140071ca8  mov     rcx, [rbp+hKey]; hKey
0x140071cac  lea     rax, [rbp+cbData]
0x140071cb0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140071cb5  lea     r9, [rbp+Type]; lpType
0x140071cb9  lea     rax, [rbp+Data]
0x140071cbd  mov     [rbp+cbData], 4
0x140071cc4  xor     r8d, r8d; lpReserved
0x140071cc7  mov     [rsp+30h+phkResult], rax; lpData
0x140071ccc  lea     rdx, aDebuglevel; "DebugLevel"
0x140071cd3  call    cs:__imp_RegQueryValueExW
0x140071cd9  test    eax, eax
0x140071cdb  jnz     short loc_140071CE3
0x140071cdd  cmp     [rbp+Type], 4
0x140071ce1  jz      short loc_140071CEA
0x140071ce3  mov     [rbp+Data], 0
0x140071cea  mov     rcx, [rbp+hKey]; hKey
0x140071cee  call    cs:__imp_RegCloseKey
0x140071cf4  mov     eax, [rbp+Data]
0x140071cf7  add     rsp, 30h
0x140071cfb  pop     rbp
0x140071cfc  retn
```
