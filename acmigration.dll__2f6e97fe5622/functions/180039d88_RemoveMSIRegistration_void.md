# RemoveMSIRegistration(void)

- ea: `0x180039d88`
- end: `0x180039e37`
- name: `?RemoveMSIRegistration@@YAHXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180039e40`

## callees

- `0x180039d88`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180039e24`
- `KERNEL32!SetLastError` at `0x180039e24`
- `ADVAPI32!RegCloseKey` at `0x180039dfd`
- `ADVAPI32!RegCloseKey` at `0x180039dfd`
- `ADVAPI32!RegOpenKeyExW` at `0x180039dd3`
- `ADVAPI32!RegOpenKeyExW` at `0x180039dd3`
- `ADVAPI32!RegDeleteTreeW` at `0x180039deb`
- `ADVAPI32!RegDeleteTreeW` at `0x180039deb`

## string_xrefs

- `0x180039d8e`: `Removing MSI registration`
- `0x180039da4`: `RemoveMSIRegistration`
- `0x180039e14`: `RemoveMSIRegistration`
- `0x180039dc5`: `Installer\Products`
- `0x180039e03`: `Removing MSI registration, result = 0x%08X`

## pseudocode

```c
_BOOL8 RemoveMSIRegistration(void)
{
  LSTATUS v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  AslLogCallPrintf(0, "RemoveMSIRegistration", 480, "Removing MSI registration");
  v0 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Installer\\Products", 0, 0xF003Fu, &hKey);
  if ( !v0 )
    v0 = RegDeleteTreeW(hKey, L"6A6823D4BA6FA894284A4E0F0425F9D3");
  if ( hKey )
    RegCloseKey(hKey);
  AslLogCallPrintf(0, "RemoveMSIRegistration", 510, "Removing MSI registration, result = 0x%08X", v0);
  SetLastError(v0);
  return v0 == 0;
}

```

## disassembly

```asm
0x180039d88  push    rbx
0x180039d8a  sub     rsp, 30h
0x180039d8e  lea     r9, aRemovingMsiReg_0; "Removing MSI registration"
0x180039d95  mov     [rsp+38h+hKey], 0
0x180039d9e  mov     r8d, 1E0h
0x180039da4  lea     rdx, aRemovemsiregis; "RemoveMSIRegistration"
0x180039dab  xor     ecx, ecx
0x180039dad  call    AslLogCallPrintf
0x180039db2  lea     rax, [rsp+38h+hKey]
0x180039db7  mov     r9d, 0F003Fh; samDesired
0x180039dbd  xor     r8d, r8d; ulOptions
0x180039dc0  mov     [rsp+38h+phkResult], rax; phkResult
0x180039dc5  lea     rdx, aInstallerProdu; "Installer\\Products"
0x180039dcc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180039dd3  call    cs:__imp_RegOpenKeyExW
0x180039dd9  mov     ebx, eax
0x180039ddb  test    eax, eax
0x180039ddd  jnz     short loc_180039DF3
0x180039ddf  mov     rcx, [rsp+38h+hKey]; hKey
0x180039de4  lea     rdx, a6a6823d4ba6fa8; "6A6823D4BA6FA894284A4E0F0425F9D3"
0x180039deb  call    cs:__imp_RegDeleteTreeW
0x180039df1  mov     ebx, eax
0x180039df3  mov     rcx, [rsp+38h+hKey]; hKey
0x180039df8  test    rcx, rcx
0x180039dfb  jz      short loc_180039E03
0x180039dfd  call    cs:__imp_RegCloseKey
0x180039e03  lea     r9, aRemovingMsiReg; "Removing MSI registration, result = 0x%"...
0x180039e0a  mov     dword ptr [rsp+38h+phkResult], ebx
0x180039e0e  mov     r8d, 1FEh
0x180039e14  lea     rdx, aRemovemsiregis; "RemoveMSIRegistration"
0x180039e1b  xor     ecx, ecx
0x180039e1d  call    AslLogCallPrintf
0x180039e22  mov     ecx, ebx; dwErrCode
0x180039e24  call    cs:__imp_SetLastError
0x180039e2a  xor     eax, eax
0x180039e2c  test    ebx, ebx
0x180039e2e  setz    al
0x180039e31  add     rsp, 30h
0x180039e35  pop     rbx
0x180039e36  retn
```
