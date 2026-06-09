# IsHVSIStandaloneEnabledABI

- ea: `0x1800254b8`
- end: `0x180025549`
- name: `IsHVSIStandaloneEnabledABI`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025550`

## callees

- `0x1800254b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025535`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800254f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800254f5`

## pseudocode

```c
_BOOL8 IsHVSIStandaloneEnabledABI()
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Hvsi", 0, 0x20019u, &hKey) )
    RegQueryValueExW(hKey, L"IsHvsiStandaloneMode", 0, 0, (LPBYTE)&Data, &cbData);
  if ( hKey )
    RegCloseKey(hKey);
  return Data != 0;
}

```

## disassembly

```asm
0x1800254b8  mov     rax, rsp
0x1800254bb  sub     rsp, 38h
0x1800254bf  mov     qword ptr [rax+18h], 0
0x1800254c7  mov     r9d, 20019h; samDesired
0x1800254cd  mov     dword ptr [rax+8], 0
0x1800254d4  xor     r8d, r8d; ulOptions
0x1800254d7  mov     dword ptr [rax+10h], 4
0x1800254de  lea     rax, [rax+18h]
0x1800254e2  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Hvsi"
0x1800254e9  mov     [rsp+38h+phkResult], rax; phkResult
0x1800254ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800254f5  call    cs:__imp_RegOpenKeyExW
0x1800254fb  test    eax, eax
0x1800254fd  jnz     short loc_18002552B
0x1800254ff  mov     rcx, [rsp+38h+hKey]; hKey
0x180025504  lea     rax, [rsp+38h+cbData]
0x180025509  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002550e  lea     rdx, aIshvsistandalo; "IsHvsiStandaloneMode"
0x180025515  lea     rax, [rsp+38h+Data]
0x18002551a  xor     r9d, r9d; lpType
0x18002551d  xor     r8d, r8d; lpReserved
0x180025520  mov     [rsp+38h+phkResult], rax; lpData
0x180025525  call    cs:__imp_RegQueryValueExW
0x18002552b  mov     rcx, [rsp+38h+hKey]; hKey
0x180025530  test    rcx, rcx
0x180025533  jz      short loc_18002553B
0x180025535  call    cs:__imp_RegCloseKey
0x18002553b  xor     eax, eax
0x18002553d  cmp     [rsp+38h+Data], eax
0x180025541  setnz   al
0x180025544  add     rsp, 38h
0x180025548  retn
```
