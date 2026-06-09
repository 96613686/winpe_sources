# pDrvUtilsGetComputerIdsKey(void)

- ea: `0x140026640`
- end: `0x1400266bf`
- name: `?pDrvUtilsGetComputerIdsKey@@YAPEAUHKEY__@@XZ`
- size: `127`
- prototype: `HKEY(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002649c`

## callees

- `0x140026640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140026676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002669f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140026676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002669f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400266af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400266af`

## string_xrefs

- `0x140026668`: `System\HardwareConfig`
- `0x140026698`: `ComputerIds`

## pseudocode

```c
HKEY pDrvUtilsGetComputerIdsKey(void)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 0x20019u, &hKey) )
    RegOpenKeyExW(hKey, L"ComputerIds", 0, 0x20019u, &phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return phkResult;
}

```

## disassembly

```asm
0x140026640  mov     r11, rsp
0x140026643  sub     rsp, 38h
0x140026647  lea     rax, [r11+8]
0x14002664b  mov     qword ptr [r11+10h], 0
0x140026653  mov     r9d, 20019h; samDesired
0x140026659  mov     [r11-18h], rax
0x14002665d  xor     r8d, r8d; ulOptions
0x140026660  mov     qword ptr [r11+8], 0
0x140026668  lea     rdx, SubKey; "System\\HardwareConfig"
0x14002666f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140026676  call    cs:__imp_RegOpenKeyExW
0x14002667c  test    eax, eax
0x14002667e  jnz     short loc_1400266A5
0x140026680  mov     rcx, [rsp+38h+hKey]; hKey
0x140026685  lea     rax, [rsp+38h+arg_8]
0x14002668a  mov     r9d, 20019h; samDesired
0x140026690  mov     [rsp+38h+phkResult], rax; phkResult
0x140026695  xor     r8d, r8d; ulOptions
0x140026698  lea     rdx, aComputerids; "ComputerIds"
0x14002669f  call    cs:__imp_RegOpenKeyExW
0x1400266a5  mov     rcx, [rsp+38h+hKey]; hKey
0x1400266aa  test    rcx, rcx
0x1400266ad  jz      short loc_1400266B5
0x1400266af  call    cs:__imp_RegCloseKey
0x1400266b5  mov     rax, [rsp+38h+arg_8]
0x1400266ba  add     rsp, 38h
0x1400266be  retn
```
