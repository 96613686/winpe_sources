# pDrvUtilsGetComputerIdsKey(void)

- ea: `0x18003dd80`
- end: `0x18003ddff`
- name: `?pDrvUtilsGetComputerIdsKey@@YAPEAUHKEY__@@XZ`
- size: `127`
- prototype: `HKEY(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dbe0`

## callees

- `0x18003dd80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ddb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ddb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dddf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ddef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ddef`

## string_xrefs

- `0x18003ddd8`: `ComputerIds`
- `0x18003dda8`: `System\HardwareConfig`

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
0x18003dd80  mov     r11, rsp
0x18003dd83  sub     rsp, 38h
0x18003dd87  lea     rax, [r11+8]
0x18003dd8b  mov     qword ptr [r11+10h], 0
0x18003dd93  mov     r9d, 20019h; samDesired
0x18003dd99  mov     [r11-18h], rax
0x18003dd9d  xor     r8d, r8d; ulOptions
0x18003dda0  mov     qword ptr [r11+8], 0
0x18003dda8  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x18003ddaf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ddb6  call    cs:__imp_RegOpenKeyExW
0x18003ddbc  test    eax, eax
0x18003ddbe  jnz     short loc_18003DDE5
0x18003ddc0  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ddc5  lea     rax, [rsp+38h+arg_8]
0x18003ddca  mov     r9d, 20019h; samDesired
0x18003ddd0  mov     [rsp+38h+phkResult], rax; phkResult
0x18003ddd5  xor     r8d, r8d; ulOptions
0x18003ddd8  lea     rdx, aComputerids; "ComputerIds"
0x18003dddf  call    cs:__imp_RegOpenKeyExW
0x18003dde5  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ddea  test    rcx, rcx
0x18003dded  jz      short loc_18003DDF5
0x18003ddef  call    cs:__imp_RegCloseKey
0x18003ddf5  mov     rax, [rsp+38h+arg_8]
0x18003ddfa  add     rsp, 38h
0x18003ddfe  retn
```
