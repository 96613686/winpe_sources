# pReadAndDeleteDiskPartionChangeValue(void)

- ea: `0x18001a538`
- end: `0x18001a5ff`
- name: `?pReadAndDeleteDiskPartionChangeValue@@YAHXZ`
- size: `199`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180019180`

## callees

- `0x1800059fc`
- `0x18001a538`
- `0x180030b98`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18001a5a2`
- `ADVAPI32!RegDeleteValueW` at `0x18001a5a2`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a58c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a58c`
- `ADVAPI32!RegCloseKey` at `0x18001a5e4`
- `ADVAPI32!RegCloseKey` at `0x18001a5e4`

## string_xrefs

- `0x18001a5b6`: `Failed to delete [%s], last error: 0x%x`
- `0x18001a5c6`: `Failed to open key [%s], last error: 0x%x`

## pseudocode

```c
__int64 pReadAndDeleteDiskPartionChangeValue(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  unsigned int v2; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v0 = CheckRegKey(L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE", L"AllowDiskPartitionChanges");
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
         0,
         2u,
         &hKey);
  if ( v1 )
  {
    UnattendLogW(
      2,
      L"Failed to open key [%s], last error: 0x%x",
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
      v1);
  }
  else
  {
    v2 = RegDeleteValueW(hKey, L"AllowDiskPartitionChanges");
    if ( (v2 & 0xFFFFFFFD) != 0 )
      UnattendLogW(2, L"Failed to delete [%s], last error: 0x%x", L"AllowDiskPartitionChanges", v2);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18001a538  push    rbx
0x18001a53a  sub     rsp, 40h
0x18001a53e  mov     rax, cs:__security_cookie
0x18001a545  xor     rax, rsp
0x18001a548  mov     [rsp+48h+var_10], rax
0x18001a54d  lea     rdx, aAllowdiskparti; "AllowDiskPartitionChanges"
0x18001a554  mov     [rsp+48h+hKey], 0
0x18001a55d  lea     rcx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a564  call    CheckRegKey
0x18001a569  mov     ebx, eax
0x18001a56b  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a572  lea     rax, [rsp+48h+hKey]
0x18001a577  mov     r9d, 2; samDesired
0x18001a57d  xor     r8d, r8d; ulOptions
0x18001a580  mov     [rsp+48h+phkResult], rax; phkResult
0x18001a585  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a58c  call    cs:__imp_RegOpenKeyExW
0x18001a592  test    eax, eax
0x18001a594  jnz     short loc_18001A5BF
0x18001a596  mov     rcx, [rsp+48h+hKey]; hKey
0x18001a59b  lea     rdx, aAllowdiskparti; "AllowDiskPartitionChanges"
0x18001a5a2  call    cs:__imp_RegDeleteValueW
0x18001a5a8  test    eax, 0FFFFFFFDh
0x18001a5ad  jz      short loc_18001A5DA
0x18001a5af  lea     r8, aAllowdiskparti; "AllowDiskPartitionChanges"
0x18001a5b6  lea     rdx, aFailedToDelete_1; "Failed to delete [%s], last error: 0x%x"
0x18001a5bd  jmp     short loc_18001A5CD
0x18001a5bf  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a5c6  lea     rdx, aFailedToOpenKe_1; "Failed to open key [%s], last error: 0x"...
0x18001a5cd  mov     r9d, eax
0x18001a5d0  mov     ecx, 2
0x18001a5d5  call    UnattendLogW
0x18001a5da  mov     rcx, [rsp+48h+hKey]; hKey
0x18001a5df  test    rcx, rcx
0x18001a5e2  jz      short loc_18001A5EA
0x18001a5e4  call    cs:__imp_RegCloseKey
0x18001a5ea  mov     eax, ebx
0x18001a5ec  mov     rcx, [rsp+48h+var_10]
0x18001a5f1  xor     rcx, rsp; StackCookie
0x18001a5f4  call    __security_check_cookie
0x18001a5f9  add     rsp, 40h
0x18001a5fd  pop     rbx
0x18001a5fe  retn
```
