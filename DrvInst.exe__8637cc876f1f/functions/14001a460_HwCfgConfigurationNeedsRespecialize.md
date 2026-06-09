# HwCfgConfigurationNeedsRespecialize

- ea: `0x14001a460`
- end: `0x14001a52c`
- name: `HwCfgConfigurationNeedsRespecialize`
- size: `204`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001c160`

## callees

- `0x14001a460`
- `0x14001a534`
- `0x14001a5e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001a4f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001a4f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a4b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a4b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a517`

## pseudocode

```c
__int64 __fastcall HwCfgConfigurationNeedsRespecialize(LPCWSTR lpSubKey)
{
  HKEY v1; // rbx
  unsigned int RootKey; // eax
  unsigned int CurrentKey; // edi
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  hKey = 0;
  phkResult = 0;
  Data = 0;
  if ( !lpSubKey )
  {
    CurrentKey = HwCfgGetCurrentKey(0, &phkResult);
    if ( CurrentKey )
      goto LABEL_9;
    goto LABEL_6;
  }
  RootKey = HwCfgGetRootKey(0x20019u, &hKey);
  v1 = hKey;
  CurrentKey = RootKey;
  if ( !RootKey )
  {
    CurrentKey = RegOpenKeyExW(hKey, lpSubKey, 0, 2u, &phkResult);
    if ( !CurrentKey )
    {
LABEL_6:
      Data = 1;
      CurrentKey = RegSetValueExW(phkResult, L"Respecialize", 0, 4u, (const BYTE *)&Data, 4u);
    }
  }
  if ( v1 )
    RegCloseKey(v1);
LABEL_9:
  if ( phkResult )
    RegCloseKey(phkResult);
  return CurrentKey;
}

```

## disassembly

```asm
0x14001a460  mov     [rsp-18h+arg_18], rbx
0x14001a465  push    rbp
0x14001a466  push    rsi
0x14001a467  push    rdi
0x14001a468  mov     rbp, rsp
0x14001a46b  sub     rsp, 30h
0x14001a46f  xor     ebx, ebx
0x14001a471  mov     rsi, rcx
0x14001a474  mov     [rbp+hKey], rbx
0x14001a478  mov     [rbp+arg_8], rbx
0x14001a47c  mov     [rbp+Data], ebx
0x14001a47f  test    rcx, rcx
0x14001a482  jz      short loc_14001A4C0
0x14001a484  lea     rdx, [rbp+hKey]
0x14001a488  mov     ecx, 20019h; samDesired
0x14001a48d  call    HwCfgGetRootKey
0x14001a492  mov     rbx, [rbp+hKey]
0x14001a496  mov     edi, eax
0x14001a498  test    eax, eax
0x14001a49a  jnz     short loc_14001A500
0x14001a49c  lea     rax, [rbp+arg_8]
0x14001a4a0  xor     r8d, r8d; ulOptions
0x14001a4a3  lea     r9d, [rdi+2]; samDesired
0x14001a4a7  mov     [rsp+30h+phkResult], rax; phkResult
0x14001a4ac  mov     rdx, rsi; lpSubKey
0x14001a4af  mov     rcx, rbx; hKey
0x14001a4b2  call    cs:__imp_RegOpenKeyExW
0x14001a4b8  mov     edi, eax
0x14001a4ba  test    eax, eax
0x14001a4bc  jnz     short loc_14001A500
0x14001a4be  jmp     short loc_14001A4CF
0x14001a4c0  lea     rdx, [rbp+arg_8]
0x14001a4c4  call    HwCfgGetCurrentKey
0x14001a4c9  mov     edi, eax
0x14001a4cb  test    eax, eax
0x14001a4cd  jnz     short loc_14001A50E
0x14001a4cf  mov     rcx, [rbp+arg_8]; hKey
0x14001a4d3  lea     rax, [rbp+Data]
0x14001a4d7  mov     r9d, 4; dwType
0x14001a4dd  mov     [rbp+Data], 1
0x14001a4e4  mov     [rsp+30h+cbData], r9d; cbData
0x14001a4e9  lea     rdx, aRespecialize; "Respecialize"
0x14001a4f0  xor     r8d, r8d; Reserved
0x14001a4f3  mov     [rsp+30h+phkResult], rax; lpData
0x14001a4f8  call    cs:__imp_RegSetValueExW
0x14001a4fe  mov     edi, eax
0x14001a500  test    rbx, rbx
0x14001a503  jz      short loc_14001A50E
0x14001a505  mov     rcx, rbx; hKey
0x14001a508  call    cs:__imp_RegCloseKey
0x14001a50e  mov     rcx, [rbp+arg_8]; hKey
0x14001a512  test    rcx, rcx
0x14001a515  jz      short loc_14001A51D
0x14001a517  call    cs:__imp_RegCloseKey
0x14001a51d  mov     rbx, [rsp+30h+arg_18]
0x14001a522  mov     eax, edi
0x14001a524  add     rsp, 30h
0x14001a528  pop     rdi
0x14001a529  pop     rsi
0x14001a52a  pop     rbp
0x14001a52b  retn
```
