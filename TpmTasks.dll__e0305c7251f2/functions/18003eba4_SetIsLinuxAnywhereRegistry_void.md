# SetIsLinuxAnywhereRegistry(void)

- ea: `0x18003eba4`
- end: `0x18003ec21`
- name: `?SetIsLinuxAnywhereRegistry@@YAXXZ`
- size: `125`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18003ec28`

## callees

- `0x18003eba4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ec16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ec16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ec06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ec06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ebd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ebd2`

## pseudocode

```c
void SetIsLinuxAnywhereRegistry(void)
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
          0,
          0xF003Fu,
          &hKey) )
  {
    Data = 1;
    RegSetValueExW(hKey, L"IsLinuxAnywhere", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18003eba4  sub     rsp, 38h
0x18003eba8  lea     rax, [rsp+38h+hKey]
0x18003ebad  mov     [rsp+38h+hKey], 0
0x18003ebb6  mov     r9d, 0F003Fh; samDesired
0x18003ebbc  mov     [rsp+38h+phkResult], rax; phkResult
0x18003ebc1  xor     r8d, r8d; ulOptions
0x18003ebc4  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003ebcb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ebd2  call    cs:__imp_RegOpenKeyExW
0x18003ebd8  test    eax, eax
0x18003ebda  jnz     short loc_18003EC0C
0x18003ebdc  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ebe1  lea     r9d, [rax+4]; dwType
0x18003ebe5  lea     rax, [rsp+38h+Data]
0x18003ebea  mov     [rsp+38h+cbData], r9d; cbData
0x18003ebef  xor     r8d, r8d; Reserved
0x18003ebf2  mov     [rsp+38h+phkResult], rax; lpData
0x18003ebf7  lea     rdx, aIslinuxanywher; "IsLinuxAnywhere"
0x18003ebfe  mov     [rsp+38h+Data], 1
0x18003ec06  call    cs:__imp_RegSetValueExW
0x18003ec0c  mov     rcx, [rsp+38h+hKey]; hKey
0x18003ec11  test    rcx, rcx
0x18003ec14  jz      short loc_18003EC1C
0x18003ec16  call    cs:__imp_RegCloseKey
0x18003ec1c  add     rsp, 38h
0x18003ec20  retn
```
