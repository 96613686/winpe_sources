# VerifyBackupInfo(HKEY__ *,HKEY__ *)

- ea: `0x18000f32c`
- end: `0x18000f477`
- name: `?VerifyBackupInfo@@YAHPEAUHKEY__@@0@Z`
- size: `331`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f7b0`

## callees

- `0x180008c88`
- `0x18000f32c`
- `0x18000f480`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000f39f`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3d9`
- `ADVAPI32!RegQueryValueExW` at `0x18000f41f`
- `ADVAPI32!RegQueryValueExW` at `0x18000f39f`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3d9`
- `ADVAPI32!RegQueryValueExW` at `0x18000f41f`

## string_xrefs

- `0x18000f405`: `BackupRegistry`

## pseudocode

```c
__int64 __fastcall VerifyBackupInfo(HKEY hKey, HKEY a2)
{
  unsigned int v2; // ebx
  int v5; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE lpData[12]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v10; // [rsp+246h] [rbp+146h]

  v2 = 0;
  *(_DWORD *)lpData = 0;
  if ( hKey )
  {
    cbData = 518;
    v10 = 0;
    if ( !RegQueryValueExW(hKey, L"BackupFileName", 0, 0, Data, &cbData) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"BackupFileSize", 0, 0, lpData, &cbData) )
      {
        v5 = MyFileSize((const unsigned __int16 *)Data);
        if ( v5 == *(_DWORD *)lpData )
        {
          cbData = 520;
          if ( !RegQueryValueExW(hKey, L"BackupRegistry", 0, 0, Data, &cbData) && *(_WORD *)Data == 110 )
            return 1;
          if ( (unsigned int)VerifyBackupRegData(hKey) || a2 && (unsigned int)VerifyBackupRegData(a2) )
            return 1;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000f32c  mov     [rsp-8+arg_10], rbx
0x18000f331  push    rbp
0x18000f332  push    rsi
0x18000f333  push    rdi
0x18000f334  lea     rbp, [rsp-160h]
0x18000f33c  sub     rsp, 260h
0x18000f343  mov     rax, cs:__security_cookie
0x18000f34a  xor     rax, rsp
0x18000f34d  mov     [rbp+170h+var_20], rax
0x18000f354  xor     ebx, ebx
0x18000f356  mov     dword ptr [rsp+270h+var_23C], 0
0x18000f35e  mov     rsi, rdx
0x18000f361  mov     rdi, rcx
0x18000f364  test    rcx, rcx
0x18000f367  jz      loc_18000F453
0x18000f36d  xor     eax, eax
0x18000f36f  mov     [rsp+270h+cbData], 206h
0x18000f377  mov     [rbp+170h+var_2A], ax
0x18000f37e  lea     rdx, aBackupfilename; "BackupFileName"
0x18000f385  lea     rax, [rsp+270h+cbData]
0x18000f38a  xor     r9d, r9d; lpType
0x18000f38d  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f392  xor     r8d, r8d; lpReserved
0x18000f395  lea     rax, [rsp+270h+Data]
0x18000f39a  mov     [rsp+270h+lpData], rax; lpData
0x18000f39f  call    cs:__imp_RegQueryValueExW
0x18000f3a5  test    eax, eax
0x18000f3a7  jnz     loc_18000F453
0x18000f3ad  lea     rax, [rsp+270h+cbData]
0x18000f3b2  mov     [rsp+270h+cbData], 4
0x18000f3ba  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f3bf  lea     rdx, aBackupfilesize; "BackupFileSize"
0x18000f3c6  lea     rax, [rsp+270h+var_23C]
0x18000f3cb  xor     r9d, r9d; lpType
0x18000f3ce  xor     r8d, r8d; lpReserved
0x18000f3d1  mov     [rsp+270h+lpData], rax; lpData
0x18000f3d6  mov     rcx, rdi; hKey
0x18000f3d9  call    cs:__imp_RegQueryValueExW
0x18000f3df  test    eax, eax
0x18000f3e1  jnz     short loc_18000F453
0x18000f3e3  lea     rcx, [rsp+270h+Data]; unsigned __int16 *
0x18000f3e8  call    ?MyFileSize@@YAKPEBG@Z; MyFileSize(ushort const *)
0x18000f3ed  cmp     eax, dword ptr [rsp+270h+var_23C]
0x18000f3f1  jnz     short loc_18000F453
0x18000f3f3  lea     rax, [rsp+270h+cbData]
0x18000f3f8  mov     [rsp+270h+cbData], 208h
0x18000f400  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f405  lea     rdx, aBackupregistry; "BackupRegistry"
0x18000f40c  lea     rax, [rsp+270h+Data]
0x18000f411  xor     r9d, r9d; lpType
0x18000f414  xor     r8d, r8d; lpReserved
0x18000f417  mov     [rsp+270h+lpData], rax; lpData
0x18000f41c  mov     rcx, rdi; hKey
0x18000f41f  call    cs:__imp_RegQueryValueExW
0x18000f425  test    eax, eax
0x18000f427  jnz     short loc_18000F431
0x18000f429  cmp     word ptr [rsp+270h+Data], 6Eh ; 'n'
0x18000f42f  jz      short loc_18000F44E
0x18000f431  mov     rcx, rdi; hKey
0x18000f434  call    ?VerifyBackupRegData@@YAHPEAUHKEY__@@@Z; VerifyBackupRegData(HKEY__ *)
0x18000f439  test    eax, eax
0x18000f43b  jnz     short loc_18000F44E
0x18000f43d  test    rsi, rsi
0x18000f440  jz      short loc_18000F453
0x18000f442  mov     rcx, rsi; hKey
0x18000f445  call    ?VerifyBackupRegData@@YAHPEAUHKEY__@@@Z; VerifyBackupRegData(HKEY__ *)
0x18000f44a  test    eax, eax
0x18000f44c  jz      short loc_18000F453
0x18000f44e  mov     ebx, 1
0x18000f453  mov     eax, ebx
0x18000f455  mov     rcx, [rbp+170h+var_20]
0x18000f45c  xor     rcx, rsp; StackCookie
0x18000f45f  call    __security_check_cookie
0x18000f464  mov     rbx, [rsp+270h+arg_10]
0x18000f46c  add     rsp, 260h
0x18000f473  pop     rdi
0x18000f474  pop     rsi
0x18000f475  pop     rbp
0x18000f476  retn
```
