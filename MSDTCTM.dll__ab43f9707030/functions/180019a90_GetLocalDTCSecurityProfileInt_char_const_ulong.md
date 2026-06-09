# GetLocalDTCSecurityProfileInt(char const *,ulong)

- ea: `0x180019a90`
- end: `0x180019b3b`
- name: `?GetLocalDTCSecurityProfileInt@@YAKPEBDK@Z`
- size: `171`
- prototype: `unsigned int __fastcall(const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800489a0`

## callees

- `0x180019a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019ade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019ade`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180019b0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180019b0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b2c`

## string_xrefs

- `0x180019ac2`: `Software\Microsoft\MSDTC\Security`
- `0x180019b00`: `SnapshotSecurityDisabled`

## pseudocode

```c
__int64 __fastcall GetLocalDTCSecurityProfileInt(const char *a1)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  int v3; // [rsp+44h] [rbp+14h]
  unsigned int Data; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  v3 = HIDWORD(a1);
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC\\Security", 0, 0x20119u, &hKey)
    || RegQueryValueExA(hKey, "SnapshotSecurityDisabled", 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4 )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x180019a90  mov     [rsp-8+Data], edx
0x180019a94  mov     qword ptr [rsp-8+Type], rcx
0x180019a99  push    rbp
0x180019a9a  mov     rbp, rsp
0x180019a9d  sub     rsp, 30h
0x180019aa1  lea     rax, [rbp+hKey]
0x180019aa5  mov     [rbp+hKey], 0
0x180019aad  mov     r9d, 20119h; samDesired
0x180019ab3  mov     [rsp+30h+phkResult], rax; phkResult
0x180019ab8  xor     r8d, r8d; ulOptions
0x180019abb  mov     [rbp+Type], 0
0x180019ac2  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\MSDTC\\Security"
0x180019ac9  mov     [rbp+Data], 0
0x180019ad0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019ad7  mov     [rbp+cbData], 4
0x180019ade  call    cs:__imp_RegOpenKeyExA
0x180019ae4  test    eax, eax
0x180019ae6  jnz     short loc_180019B1C
0x180019ae8  mov     rcx, [rbp+hKey]; hKey
0x180019aec  lea     rax, [rbp+cbData]
0x180019af0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180019af5  lea     r9, [rbp+Type]; lpType
0x180019af9  lea     rax, [rbp+Data]
0x180019afd  xor     r8d, r8d; lpReserved
0x180019b00  lea     rdx, aSnapshotsecuri; "SnapshotSecurityDisabled"
0x180019b07  mov     [rsp+30h+phkResult], rax; lpData
0x180019b0c  call    cs:__imp_RegQueryValueExA
0x180019b12  test    eax, eax
0x180019b14  jnz     short loc_180019B1C
0x180019b16  cmp     [rbp+Type], 4
0x180019b1a  jz      short loc_180019B23
0x180019b1c  mov     [rbp+Data], 0
0x180019b23  mov     rcx, [rbp+hKey]; hKey
0x180019b27  test    rcx, rcx
0x180019b2a  jz      short loc_180019B32
0x180019b2c  call    cs:__imp_RegCloseKey
0x180019b32  mov     eax, [rbp+Data]
0x180019b35  add     rsp, 30h
0x180019b39  pop     rbp
0x180019b3a  retn
```
