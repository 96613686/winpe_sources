# GetCurrentHwProfileW

- ea: `0x18002e520`
- end: `0x18002e827`
- name: `GetCurrentHwProfileW`
- size: `775`
- prototype: `BOOL __stdcall(LPHW_PROFILE_INFOW lpHwProfileInfo)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180039960`

## callees

- `0x18002e520`
- `0x18002ebd0`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e68f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e6e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e726`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e77c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e68f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e6e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e726`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e77c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e587`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e587`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e7df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e80b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e7df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e80b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e819`
- `KERNEL32!SetLastError` at `0x18002e740`
- `KERNEL32!SetLastError` at `0x18002e7af`
- `KERNEL32!SetLastError` at `0x18002e740`
- `KERNEL32!SetLastError` at `0x18002e7af`

## string_xrefs

- `0x18002e579`: `System\CurrentControlSet\Control\IDConfigDB`
- `0x18002e5be`: `CurrentConfig`

## pseudocode

```c
BOOL __stdcall GetCurrentHwProfileW(LPHW_PROFILE_INFOW lpHwProfileInfo)
{
  BOOL v2; // edi
  BYTE *szHwProfileName; // rsi
  DWORD v4; // ecx
  PHKEY phkResult; // [rsp+20h] [rbp-288h]
  DWORD cbData[2]; // [rsp+30h] [rbp-278h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-270h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-268h] BYREF
  HKEY v10; // [rsp+48h] [rbp-260h] BYREF
  HKEY v11; // [rsp+50h] [rbp-258h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-248h] BYREF

  v2 = 1;
  hKey = 0;
  v10 = 0;
  v11 = 0;
  *(_DWORD *)Data = 1;
  cbData[0] = 0;
  if ( !lpHwProfileInfo )
  {
    v4 = 87;
    goto LABEL_15;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\IDConfigDB", 0, 1u, &hKey)
    || (cbData[0] = 4, RegQueryValueExW(hKey, L"CurrentConfig", 0, 0, Data, cbData))
    || (LODWORD(phkResult) = *(_DWORD *)Data,
        StringCchPrintfW(pszDest, 0x104u, L"%s\\%04u", L"Hardware Profiles", phkResult) < 0)
    || RegOpenKeyExW(hKey, pszDest, 0, 1u, &v10)
    || RegOpenKeyExW(hKey, L"CurrentDockInfo", 0, 1u, &v11) )
  {
    v4 = 1015;
LABEL_15:
    SetLastError(v4);
    v2 = 0;
    cbData[1] = 0;
    goto LABEL_20;
  }
  cbData[0] = 4;
  if ( (RegQueryValueExW(v11, L"DockingState", 0, 0, (LPBYTE)lpHwProfileInfo, cbData)
     || !lpHwProfileInfo->dwDockInfo
     || (lpHwProfileInfo->dwDockInfo & 3) == 3)
    && (RegQueryValueExW(v10, L"DockState", 0, 0, (LPBYTE)lpHwProfileInfo, cbData) || !lpHwProfileInfo->dwDockInfo) )
  {
    lpHwProfileInfo->dwDockInfo = 7;
  }
  cbData[0] = 78;
  if ( RegQueryValueExW(v10, L"HwProfileGuid", 0, 0, (LPBYTE)lpHwProfileInfo->szHwProfileGuid, cbData) )
    lpHwProfileInfo->szHwProfileGuid[0] = 0;
  cbData[0] = 160;
  szHwProfileName = (BYTE *)lpHwProfileInfo->szHwProfileName;
  if ( RegQueryValueExW(v10, L"FriendlyName", 0, 0, szHwProfileName, cbData) )
    *(_WORD *)szHwProfileName = 0;
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    RegCloseKey(v10);
  if ( v11 )
    RegCloseKey(v11);
  return v2;
}

```

## disassembly

```asm
0x18002e520  push    rbx
0x18002e522  push    rsi
0x18002e523  push    rdi
0x18002e524  push    r14
0x18002e526  sub     rsp, 288h
0x18002e52d  mov     rax, cs:__security_cookie
0x18002e534  xor     rax, rsp
0x18002e537  mov     [rsp+2A8h+var_38], rax
0x18002e53f  mov     rsi, rcx
0x18002e542  mov     edi, 1
0x18002e547  xor     ebx, ebx
0x18002e549  mov     [rsp+2A8h+hKey], rbx
0x18002e54e  mov     [rsp+2A8h+var_260], rbx
0x18002e553  mov     [rsp+2A8h+var_258], rbx
0x18002e558  mov     dword ptr [rsp+2A8h+Data], edi
0x18002e55c  mov     [rsp+2A8h+cbData], ebx
0x18002e560  test    rcx, rcx
0x18002e563  jz      loc_18002E754
0x18002e569  lea     rax, [rsp+2A8h+hKey]
0x18002e56e  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002e573  mov     r9d, edi; samDesired
0x18002e576  xor     r8d, r8d; ulOptions
0x18002e579  lea     rdx, pszRegIDConfigDB; "System\\CurrentControlSet\\Control\\IDC"...
0x18002e580  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e587  call    cs:__imp_RegOpenKeyExW
0x18002e58e  nop     dword ptr [rax+rax+00h]
0x18002e593  test    eax, eax
0x18002e595  jnz     loc_18002E73B
0x18002e59b  lea     r14d, [rdi+3]
0x18002e59f  mov     [rsp+2A8h+cbData], r14d
0x18002e5a4  lea     rax, [rsp+2A8h+cbData]
0x18002e5a9  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002e5ae  lea     rax, [rsp+2A8h+Data]
0x18002e5b3  mov     [rsp+2A8h+phkResult], rax; lpData
0x18002e5b8  xor     r9d, r9d; lpType
0x18002e5bb  xor     r8d, r8d; lpReserved
0x18002e5be  lea     rdx, pszRegCurrentConfig; "CurrentConfig"
0x18002e5c5  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002e5ca  call    cs:__imp_RegQueryValueExW
0x18002e5d1  nop     dword ptr [rax+rax+00h]
0x18002e5d6  test    eax, eax
0x18002e5d8  jnz     loc_18002E73B
0x18002e5de  mov     eax, dword ptr [rsp+2A8h+Data]
0x18002e5e2  mov     dword ptr [rsp+2A8h+phkResult], eax
0x18002e5e6  lea     r9, pszRegKnownDockingStates; "Hardware Profiles"
0x18002e5ed  lea     r8, aS04u; "%s\\%04u"
0x18002e5f4  mov     edx, 104h; cchDest
0x18002e5f9  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18002e5fe  call    StringCchPrintfW
0x18002e603  test    eax, eax
0x18002e605  js      loc_18002E73B
0x18002e60b  lea     rax, [rsp+2A8h+var_260]
0x18002e610  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002e615  mov     r9d, edi; samDesired
0x18002e618  xor     r8d, r8d; ulOptions
0x18002e61b  lea     rdx, [rsp+2A8h+pszDest]; lpSubKey
0x18002e620  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002e625  call    cs:__imp_RegOpenKeyExW
0x18002e62c  nop     dword ptr [rax+rax+00h]
0x18002e631  test    eax, eax
0x18002e633  jnz     loc_18002E73B
0x18002e639  lea     rax, [rsp+2A8h+var_258]
0x18002e63e  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002e643  mov     r9d, edi; samDesired
0x18002e646  xor     r8d, r8d; ulOptions
0x18002e649  lea     rdx, pszCurrentDockInfo; "CurrentDockInfo"
0x18002e650  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002e655  call    cs:__imp_RegOpenKeyExW
0x18002e65c  nop     dword ptr [rax+rax+00h]
0x18002e661  test    eax, eax
0x18002e663  jnz     loc_18002E73B
0x18002e669  mov     [rsp+2A8h+cbData], r14d
0x18002e66e  lea     rax, [rsp+2A8h+cbData]
0x18002e673  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002e678  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002e67d  xor     r9d, r9d; lpType
0x18002e680  xor     r8d, r8d; lpReserved
0x18002e683  lea     rdx, pszRegDockingState; "DockingState"
0x18002e68a  mov     rcx, [rsp+2A8h+var_258]; hKey
0x18002e68f  call    cs:__imp_RegQueryValueExW
0x18002e696  nop     dword ptr [rax+rax+00h]
0x18002e69b  test    eax, eax
0x18002e69d  jnz     loc_18002E75B
0x18002e6a3  mov     eax, [rsi]
0x18002e6a5  test    eax, eax
0x18002e6a7  jz      loc_18002E75B
0x18002e6ad  and     eax, 3
0x18002e6b0  cmp     al, 3
0x18002e6b2  jz      loc_18002E75B
0x18002e6b8  mov     [rsp+2A8h+cbData], 4Eh ; 'N'
0x18002e6c0  lea     r14, [rsi+4]
0x18002e6c4  lea     rax, [rsp+2A8h+cbData]
0x18002e6c9  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002e6ce  mov     [rsp+2A8h+phkResult], r14; lpData
0x18002e6d3  xor     r9d, r9d; lpType
0x18002e6d6  xor     r8d, r8d; lpReserved
0x18002e6d9  lea     rdx, pszRegHwProfileGuid; "HwProfileGuid"
0x18002e6e0  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002e6e5  call    cs:__imp_RegQueryValueExW
0x18002e6ec  nop     dword ptr [rax+rax+00h]
0x18002e6f1  test    eax, eax
0x18002e6f3  jnz     loc_18002E79F
0x18002e6f9  mov     [rsp+2A8h+cbData], 0A0h
0x18002e701  add     rsi, 52h ; 'R'
0x18002e705  lea     rax, [rsp+2A8h+cbData]
0x18002e70a  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002e70f  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002e714  xor     r9d, r9d; lpType
0x18002e717  xor     r8d, r8d; lpReserved
0x18002e71a  lea     rdx, pszRegFriendlyName; "FriendlyName"
0x18002e721  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002e726  call    cs:__imp_RegQueryValueExW
0x18002e72d  nop     dword ptr [rax+rax+00h]
0x18002e732  test    eax, eax
0x18002e734  jz      short loc_18002E7A8
0x18002e736  mov     [rsi], bx
0x18002e739  jmp     short loc_18002E7A8
0x18002e73b  mov     ecx, 3F7h; dwErrCode
0x18002e740  call    cs:__imp_SetLastError
0x18002e747  nop     dword ptr [rax+rax+00h]
0x18002e74c  mov     edi, ebx
0x18002e74e  mov     [rsp+2A8h+var_274], ebx
0x18002e752  jmp     short loc_18002E7A8
0x18002e754  mov     ecx, 57h ; 'W'
0x18002e759  jmp     short loc_18002E740
0x18002e75b  lea     rax, [rsp+2A8h+cbData]
0x18002e760  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002e765  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002e76a  xor     r9d, r9d; lpType
0x18002e76d  xor     r8d, r8d; lpReserved
0x18002e770  lea     rdx, pszRegDockState; "DockState"
0x18002e777  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002e77c  call    cs:__imp_RegQueryValueExW
0x18002e783  nop     dword ptr [rax+rax+00h]
0x18002e788  test    eax, eax
0x18002e78a  jnz     short loc_18002E794
0x18002e78c  cmp     [rsi], ebx
0x18002e78e  jnz     loc_18002E6B8
0x18002e794  mov     dword ptr [rsi], 7
0x18002e79a  jmp     loc_18002E6B8
0x18002e79f  mov     [r14], bx
0x18002e7a3  jmp     loc_18002E6F9
0x18002e7a8  jmp     short loc_18002E7C1
0x18002e7aa  mov     ecx, 57h ; 'W'; dwErrCode
0x18002e7af  call    cs:__imp_SetLastError
0x18002e7b6  nop     dword ptr [rax+rax+00h]
0x18002e7bb  xor     edi, edi
0x18002e7bd  mov     [rsp+2A8h+var_274], edi
0x18002e7c1  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002e7c6  test    rcx, rcx
0x18002e7c9  jnz     short loc_18002E819
0x18002e7cb  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002e7d0  test    rcx, rcx
0x18002e7d3  jnz     short loc_18002E80B
0x18002e7d5  mov     rcx, [rsp+2A8h+var_258]; hKey
0x18002e7da  test    rcx, rcx
0x18002e7dd  jz      short loc_18002E7EB
0x18002e7df  call    cs:__imp_RegCloseKey
0x18002e7e6  nop     dword ptr [rax+rax+00h]
0x18002e7eb  mov     eax, edi
0x18002e7ed  mov     rcx, [rsp+2A8h+var_38]
0x18002e7f5  xor     rcx, rsp; StackCookie
0x18002e7f8  call    __security_check_cookie
0x18002e7fd  add     rsp, 288h
0x18002e804  pop     r14
0x18002e806  pop     rdi
0x18002e807  pop     rsi
0x18002e808  pop     rbx
0x18002e809  retn
0x18002e80b  call    cs:__imp_RegCloseKey
0x18002e812  nop     dword ptr [rax+rax+00h]
0x18002e817  jmp     short loc_18002E7D5
0x18002e819  call    cs:__imp_RegCloseKey
0x18002e820  nop     dword ptr [rax+rax+00h]
0x18002e825  jmp     short loc_18002E7CB
```
