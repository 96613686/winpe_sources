# DeleteUEFICA2023Error

- ea: `0x180056f5c`
- end: `0x180056fc2`
- name: `DeleteUEFICA2023Error`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180057a18`

## callees

- `0x18003c0b8`
- `0x180056f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056fb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056fb7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056fac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056fac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056f8a`

## pseudocode

```c
LSTATUS DeleteUEFICA2023Error()
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing", 0, 2u, &hKey);
  if ( !result )
  {
    SBServicingLogMessage((wchar_t *)L"Deleting UEFICA2023Error");
    RegDeleteValueW(hKey, L"UEFICA2023Error");
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180056f5c  sub     rsp, 38h
0x180056f60  lea     rax, [rsp+38h+hKey]
0x180056f65  mov     [rsp+38h+hKey], 0
0x180056f6e  mov     r9d, 2; samDesired
0x180056f74  mov     [rsp+38h+phkResult], rax; phkResult
0x180056f79  xor     r8d, r8d; ulOptions
0x180056f7c  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180056f83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056f8a  call    cs:__imp_RegOpenKeyExW
0x180056f90  test    eax, eax
0x180056f92  jnz     short loc_180056FBD
0x180056f94  lea     rcx, aDeletingUefica; "Deleting UEFICA2023Error"
0x180056f9b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180056fa0  mov     rcx, [rsp+38h+hKey]; hKey
0x180056fa5  lea     rdx, aUefica2023erro; "UEFICA2023Error"
0x180056fac  call    cs:__imp_RegDeleteValueW
0x180056fb2  mov     rcx, [rsp+38h+hKey]; hKey
0x180056fb7  call    cs:__imp_RegCloseKey
0x180056fbd  add     rsp, 38h
0x180056fc1  retn
```
