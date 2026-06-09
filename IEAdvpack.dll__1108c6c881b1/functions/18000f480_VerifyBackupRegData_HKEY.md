# VerifyBackupRegData(HKEY__ *)

- ea: `0x18000f480`
- end: `0x18000f628`
- name: `?VerifyBackupRegData@@YAHPEAUHKEY__@@@Z`
- size: `424`
- prototype: `_BOOL8 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f32c`

## callees

- `0x180008c88`
- `0x18000f480`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000f4f3`
- `ADVAPI32!RegQueryValueExW` at `0x18000f529`
- `ADVAPI32!RegQueryValueExW` at `0x18000f4f3`
- `ADVAPI32!RegQueryValueExW` at `0x18000f529`
- `ADVAPI32!RegCloseKey` at `0x18000f5fa`
- `ADVAPI32!RegCloseKey` at `0x18000f605`
- `ADVAPI32!RegCloseKey` at `0x18000f5fa`
- `ADVAPI32!RegCloseKey` at `0x18000f605`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f569`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f59b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f569`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f59b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f5df`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f5df`

## string_xrefs

- `0x18000f4d6`: `BackupRegPathName`

## pseudocode

```c
_BOOL8 __fastcall VerifyBackupRegData(HKEY hKey)
{
  int v2; // eax
  BOOL v4; // ebx
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  BYTE lpData[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 Data[259]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v10; // [rsp+286h] [rbp+186h]

  phkResult = 0;
  cbData = 0;
  *(_DWORD *)lpData = 0;
  if ( !ctx )
  {
    cbData = 518;
    v10 = 0;
    if ( !RegQueryValueExW(hKey, L"BackupRegPathName", 0, 0, (LPBYTE)Data, &cbData) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BackupRegSize", 0, 0, lpData, &cbData) )
      {
        v2 = MyFileSize(Data);
        if ( v2 == *(_DWORD *)lpData )
          return 1;
      }
    }
  }
  v4 = 0;
  if ( !RegOpenKeyExW(hKey, L"RegBackup", 0, 0x20019u, &phkResult) )
  {
    hKeya = 0;
    if ( !RegOpenKeyExW(phkResult, L"0", 0, 0x20019u, &hKeya) )
    {
      if ( !RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, 0, 0, &cbData, 0, 0, 0, 0) )
        v4 = cbData != 0;
      RegCloseKey(hKeya);
    }
    RegCloseKey(phkResult);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f480  push    rbp
0x18000f482  push    rbx
0x18000f483  push    rsi
0x18000f484  push    rdi
0x18000f485  lea     rbp, [rsp-1A8h]
0x18000f48d  sub     rsp, 2A8h
0x18000f494  mov     rax, cs:__security_cookie
0x18000f49b  xor     rax, rsp
0x18000f49e  mov     [rbp+1C0h+var_30], rax
0x18000f4a5  xor     esi, esi
0x18000f4a7  mov     rdi, rcx
0x18000f4aa  cmp     cs:?ctx@@3UADVCONTEXTW@@A, si; ADVCONTEXTW ctx
0x18000f4b1  mov     [rsp+2C0h+phkResult], rsi
0x18000f4b6  mov     [rsp+2C0h+cbData], esi
0x18000f4ba  mov     dword ptr [rsp+2C0h+var_25C], esi
0x18000f4be  jnz     loc_18000F54A
0x18000f4c4  lea     rax, [rsp+2C0h+cbData]
0x18000f4c9  mov     [rsp+2C0h+cbData], 206h
0x18000f4d1  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18000f4d6  lea     rdx, aBackupregpathn; "BackupRegPathName"
0x18000f4dd  lea     rax, [rbp+1C0h+Data]
0x18000f4e1  mov     [rbp+1C0h+var_3A], si
0x18000f4e8  xor     r9d, r9d; lpType
0x18000f4eb  mov     [rsp+2C0h+lpData], rax; lpData
0x18000f4f0  xor     r8d, r8d; lpReserved
0x18000f4f3  call    cs:__imp_RegQueryValueExW
0x18000f4f9  test    eax, eax
0x18000f4fb  jnz     short loc_18000F54A
0x18000f4fd  lea     rax, [rsp+2C0h+cbData]
0x18000f502  mov     [rsp+2C0h+cbData], 4
0x18000f50a  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18000f50f  lea     rdx, aBackupregsize; "BackupRegSize"
0x18000f516  lea     rax, [rsp+2C0h+var_25C]
0x18000f51b  xor     r9d, r9d; lpType
0x18000f51e  xor     r8d, r8d; lpReserved
0x18000f521  mov     [rsp+2C0h+lpData], rax; lpData
0x18000f526  mov     rcx, rdi; hKey
0x18000f529  call    cs:__imp_RegQueryValueExW
0x18000f52f  test    eax, eax
0x18000f531  jnz     short loc_18000F54A
0x18000f533  lea     rcx, [rbp+1C0h+Data]; unsigned __int16 *
0x18000f537  call    ?MyFileSize@@YAKPEBG@Z; MyFileSize(ushort const *)
0x18000f53c  cmp     eax, dword ptr [rsp+2C0h+var_25C]
0x18000f540  jnz     short loc_18000F54A
0x18000f542  lea     eax, [rsi+1]
0x18000f545  jmp     loc_18000F60D
0x18000f54a  lea     rax, [rsp+2C0h+phkResult]
0x18000f54f  mov     r9d, 20019h; samDesired
0x18000f555  xor     r8d, r8d; ulOptions
0x18000f558  mov     [rsp+2C0h+lpData], rax; phkResult
0x18000f55d  lea     rdx, aRegbackup; "RegBackup"
0x18000f564  mov     rcx, rdi; hKey
0x18000f567  mov     ebx, esi
0x18000f569  call    cs:__imp_RegOpenKeyExW
0x18000f56f  test    eax, eax
0x18000f571  jnz     loc_18000F60B
0x18000f577  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18000f57c  lea     rax, [rsp+2C0h+hKey]
0x18000f581  mov     r9d, 20019h; samDesired
0x18000f587  mov     [rsp+2C0h+lpData], rax; phkResult
0x18000f58c  xor     r8d, r8d; ulOptions
0x18000f58f  mov     [rsp+2C0h+hKey], rsi
0x18000f594  lea     rdx, a0_0; "0"
0x18000f59b  call    cs:__imp_RegOpenKeyExW
0x18000f5a1  test    eax, eax
0x18000f5a3  jnz     short loc_18000F600
0x18000f5a5  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000f5aa  lea     rax, [rsp+2C0h+cbData]
0x18000f5af  mov     [rsp+2C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000f5b4  xor     r9d, r9d; lpReserved
0x18000f5b7  mov     [rsp+2C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000f5bc  xor     r8d, r8d; lpcchClass
0x18000f5bf  mov     [rsp+2C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000f5c4  xor     edx, edx; lpClass
0x18000f5c6  mov     [rsp+2C0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18000f5cb  mov     [rsp+2C0h+lpcValues], rax; lpcValues
0x18000f5d0  mov     [rsp+2C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000f5d5  mov     [rsp+2C0h+lpcbData], rsi; lpcbMaxSubKeyLen
0x18000f5da  mov     [rsp+2C0h+lpData], rsi; lpcSubKeys
0x18000f5df  call    cs:__imp_RegQueryInfoKeyW
0x18000f5e5  test    eax, eax
0x18000f5e7  jnz     short loc_18000F5F5
0x18000f5e9  cmp     [rsp+2C0h+cbData], esi
0x18000f5ed  mov     eax, 1
0x18000f5f2  cmovnz  ebx, eax
0x18000f5f5  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000f5fa  call    cs:__imp_RegCloseKey
0x18000f600  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18000f605  call    cs:__imp_RegCloseKey
0x18000f60b  mov     eax, ebx
0x18000f60d  mov     rcx, [rbp+1C0h+var_30]
0x18000f614  xor     rcx, rsp; StackCookie
0x18000f617  call    __security_check_cookie
0x18000f61c  add     rsp, 2A8h
0x18000f623  pop     rdi
0x18000f624  pop     rsi
0x18000f625  pop     rbx
0x18000f626  pop     rbp
0x18000f627  retn
```
