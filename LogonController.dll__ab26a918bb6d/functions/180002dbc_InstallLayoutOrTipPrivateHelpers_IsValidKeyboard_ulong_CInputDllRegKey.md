# InstallLayoutOrTipPrivateHelpers::IsValidKeyboard(ulong,CInputDllRegKey &)

- ea: `0x180002dbc`
- end: `0x180002f05`
- name: `?IsValidKeyboard@InstallLayoutOrTipPrivateHelpers@@SA_NKAEAVCInputDllRegKey@@@Z`
- size: `329`
- prototype: `bool __fastcall(unsigned int, struct CInputDllRegKey *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180006d90`

## callees

- `0x180002dbc`
- `0x180004b70`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002ecd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002ecd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002eeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002eeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall InstallLayoutOrTipPrivateHelpers::IsValidKeyboard(unsigned int a1, struct CInputDllRegKey *a2)
{
  HKEY v3; // rsi
  LSTATUS v4; // eax
  LSTATUS v5; // edi
  HKEY v6; // rbx
  bool v7; // di
  HKEY phkResult; // [rsp+50h] [rbp+7h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  WCHAR SubKey[12]; // [rsp+68h] [rbp+1Fh] BYREF

  StringCchPrintfW(SubKey, 9u, L"%08x", a1);
  v3 = (HKEY)*((_QWORD *)a2 + 1);
  phkResult = 0;
  hKey = 0;
  if ( v3 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
    v3 = hKey;
  v4 = RegOpenKeyExW(v3, SubKey, 0, 0x20019u, &phkResult);
  v5 = v4;
  if ( !v4
    || (v6 = 0, v4 == 5)
    && (dwDisposition = 0, (v5 = RegCreateKeyExW(v3, SubKey, 0, 0, 4u, 0x20019u, 0, &phkResult, &dwDisposition)) == 0) )
  {
    v6 = phkResult;
    v5 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v7 = v5 == 0;
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x180002dbc  mov     [rsp-8+arg_10], rbx
0x180002dc1  push    rbp
0x180002dc2  push    rsi
0x180002dc3  push    rdi
0x180002dc4  lea     rbp, [rsp-47h]
0x180002dc9  sub     rsp, 90h
0x180002dd0  mov     rax, cs:__security_cookie
0x180002dd7  xor     rax, rsp
0x180002dda  mov     [rbp+57h+var_20], rax
0x180002dde  mov     rbx, rdx
0x180002de1  lea     r8, a08x_1; "%08x"
0x180002de8  mov     r9d, ecx
0x180002deb  mov     edx, 9; unsigned __int64
0x180002df0  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x180002df4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002df9  mov     rsi, [rbx+8]
0x180002dfd  mov     [rbp+57h+var_50], 0
0x180002e05  mov     [rbp+57h+hKey], 0
0x180002e0d  cmp     rsi, 0FFFFFFFF80000001h
0x180002e14  jz      loc_180002EE2
0x180002e1a  lea     rax, [rbp+57h+var_50]
0x180002e1e  mov     r9d, 20019h; samDesired
0x180002e24  xor     r8d, r8d; ulOptions
0x180002e27  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180002e2c  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180002e30  mov     rcx, rsi; hKey
0x180002e33  call    cs:__imp_RegOpenKeyExW
0x180002e39  mov     edi, eax
0x180002e3b  test    eax, eax
0x180002e3d  jnz     short loc_180002E8F
0x180002e3f  mov     rbx, [rbp+57h+var_50]
0x180002e43  xor     edi, edi
0x180002e45  mov     rcx, [rbp+57h+hKey]; hKey
0x180002e49  test    rcx, rcx
0x180002e4c  jz      short loc_180002E54
0x180002e4e  call    cs:__imp_RegCloseKey
0x180002e54  test    edi, edi
0x180002e56  jnz     loc_180002EFD
0x180002e5c  mov     dil, 1
0x180002e5f  test    rbx, rbx
0x180002e62  jz      short loc_180002E6D
0x180002e64  mov     rcx, rbx; hKey
0x180002e67  call    cs:__imp_RegCloseKey
0x180002e6d  mov     al, dil
0x180002e70  mov     rcx, [rbp+57h+var_20]
0x180002e74  xor     rcx, rsp; StackCookie
0x180002e77  call    __security_check_cookie
0x180002e7c  mov     rbx, [rsp+0A0h+arg_10]
0x180002e84  add     rsp, 90h
0x180002e8b  pop     rdi
0x180002e8c  pop     rsi
0x180002e8d  pop     rbp
0x180002e8e  retn
0x180002e8f  xor     ebx, ebx
0x180002e91  cmp     eax, 5
0x180002e94  jnz     short loc_180002E45
0x180002e96  lea     rax, [rbp+57h+dwDisposition]
0x180002e9a  mov     [rbp+57h+dwDisposition], ebx
0x180002e9d  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x180002ea2  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180002ea6  lea     rax, [rbp+57h+var_50]
0x180002eaa  xor     r9d, r9d; lpClass
0x180002ead  mov     [rsp+0A0h+var_68], rax; phkResult
0x180002eb2  xor     r8d, r8d; Reserved
0x180002eb5  mov     [rsp+0A0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180002eba  mov     rcx, rsi; hKey
0x180002ebd  mov     [rsp+0A0h+samDesired], 20019h; samDesired
0x180002ec5  mov     dword ptr [rsp+0A0h+phkResult], 4; dwOptions
0x180002ecd  call    cs:__imp_RegCreateKeyExW
0x180002ed3  mov     edi, eax
0x180002ed5  test    eax, eax
0x180002ed7  jz      loc_180002E3F
0x180002edd  jmp     loc_180002E45
0x180002ee2  lea     rdx, [rbp+57h+hKey]; phkResult
0x180002ee6  mov     ecx, 20019h; samDesired
0x180002eeb  call    cs:__imp_RegOpenCurrentUser
0x180002ef1  test    eax, eax
0x180002ef3  cmovz   rsi, [rbp+57h+hKey]
0x180002ef8  jmp     loc_180002E1A
0x180002efd  xor     dil, dil
0x180002f00  jmp     loc_180002E5F
```
