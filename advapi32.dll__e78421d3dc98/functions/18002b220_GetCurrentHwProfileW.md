# GetCurrentHwProfileW

- ea: `0x18002b220`
- end: `0x18002b4d8`
- name: `GetCurrentHwProfileW`
- size: `696`
- prototype: `BOOL __stdcall(LPHW_PROFILE_INFOW lpHwProfileInfo)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180035b30`

## callees

- `0x18002b220`
- `0x18002b834`
- `0x180065090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b2c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b377`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b3c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b402`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b2c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b377`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b3c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b402`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b44c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b287`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b319`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b343`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b287`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b319`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b343`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4d0`
- `KERNEL32!SetLastError` at `0x18002b416`
- `KERNEL32!SetLastError` at `0x18002b479`
- `KERNEL32!SetLastError` at `0x18002b416`
- `KERNEL32!SetLastError` at `0x18002b479`

## string_xrefs

- `0x18002b279`: `System\CurrentControlSet\Control\IDConfigDB`
- `0x18002b2b8`: `CurrentConfig`

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
0x18002b220  push    rbx
0x18002b222  push    rsi
0x18002b223  push    rdi
0x18002b224  push    r14
0x18002b226  sub     rsp, 288h
0x18002b22d  mov     rax, cs:__security_cookie
0x18002b234  xor     rax, rsp
0x18002b237  mov     [rsp+2A8h+var_38], rax
0x18002b23f  mov     rsi, rcx
0x18002b242  mov     edi, 1
0x18002b247  xor     ebx, ebx
0x18002b249  mov     [rsp+2A8h+hKey], rbx
0x18002b24e  mov     [rsp+2A8h+var_260], rbx
0x18002b253  mov     [rsp+2A8h+var_258], rbx
0x18002b258  mov     dword ptr [rsp+2A8h+Data], edi
0x18002b25c  mov     [rsp+2A8h+cbData], ebx
0x18002b260  test    rcx, rcx
0x18002b263  jz      loc_18002B424
0x18002b269  lea     rax, [rsp+2A8h+hKey]
0x18002b26e  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002b273  mov     r9d, edi; samDesired
0x18002b276  xor     r8d, r8d; ulOptions
0x18002b279  lea     rdx, pszRegIDConfigDB; "System\\CurrentControlSet\\Control\\IDC"...
0x18002b280  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b287  call    cs:__imp_RegOpenKeyExW
0x18002b28d  test    eax, eax
0x18002b28f  jnz     loc_18002B411
0x18002b295  lea     r14d, [rdi+3]
0x18002b299  mov     [rsp+2A8h+cbData], r14d
0x18002b29e  lea     rax, [rsp+2A8h+cbData]
0x18002b2a3  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002b2a8  lea     rax, [rsp+2A8h+Data]
0x18002b2ad  mov     [rsp+2A8h+phkResult], rax; lpData
0x18002b2b2  xor     r9d, r9d; lpType
0x18002b2b5  xor     r8d, r8d; lpReserved
0x18002b2b8  lea     rdx, pszRegCurrentConfig; "CurrentConfig"
0x18002b2bf  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002b2c4  call    cs:__imp_RegQueryValueExW
0x18002b2ca  test    eax, eax
0x18002b2cc  jnz     loc_18002B411
0x18002b2d2  mov     eax, dword ptr [rsp+2A8h+Data]
0x18002b2d6  mov     dword ptr [rsp+2A8h+phkResult], eax
0x18002b2da  lea     r9, pszRegKnownDockingStates; "Hardware Profiles"
0x18002b2e1  lea     r8, aS04u; "%s\\%04u"
0x18002b2e8  mov     edx, 104h; cchDest
0x18002b2ed  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18002b2f2  call    StringCchPrintfW
0x18002b2f7  test    eax, eax
0x18002b2f9  js      loc_18002B411
0x18002b2ff  lea     rax, [rsp+2A8h+var_260]
0x18002b304  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002b309  mov     r9d, edi; samDesired
0x18002b30c  xor     r8d, r8d; ulOptions
0x18002b30f  lea     rdx, [rsp+2A8h+pszDest]; lpSubKey
0x18002b314  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002b319  call    cs:__imp_RegOpenKeyExW
0x18002b31f  test    eax, eax
0x18002b321  jnz     loc_18002B411
0x18002b327  lea     rax, [rsp+2A8h+var_258]
0x18002b32c  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18002b331  mov     r9d, edi; samDesired
0x18002b334  xor     r8d, r8d; ulOptions
0x18002b337  lea     rdx, pszCurrentDockInfo; "CurrentDockInfo"
0x18002b33e  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002b343  call    cs:__imp_RegOpenKeyExW
0x18002b349  test    eax, eax
0x18002b34b  jnz     loc_18002B411
0x18002b351  mov     [rsp+2A8h+cbData], r14d
0x18002b356  lea     rax, [rsp+2A8h+cbData]
0x18002b35b  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002b360  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002b365  xor     r9d, r9d; lpType
0x18002b368  xor     r8d, r8d; lpReserved
0x18002b36b  lea     rdx, pszRegDockingState; "DockingState"
0x18002b372  mov     rcx, [rsp+2A8h+var_258]; hKey
0x18002b377  call    cs:__imp_RegQueryValueExW
0x18002b37d  test    eax, eax
0x18002b37f  jnz     loc_18002B42B
0x18002b385  mov     eax, [rsi]
0x18002b387  test    eax, eax
0x18002b389  jz      loc_18002B42B
0x18002b38f  and     eax, 3
0x18002b392  cmp     al, 3
0x18002b394  jz      loc_18002B42B
0x18002b39a  mov     [rsp+2A8h+cbData], 4Eh ; 'N'
0x18002b3a2  lea     r14, [rsi+4]
0x18002b3a6  lea     rax, [rsp+2A8h+cbData]
0x18002b3ab  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002b3b0  mov     [rsp+2A8h+phkResult], r14; lpData
0x18002b3b5  xor     r9d, r9d; lpType
0x18002b3b8  xor     r8d, r8d; lpReserved
0x18002b3bb  lea     rdx, pszRegHwProfileGuid; "HwProfileGuid"
0x18002b3c2  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002b3c7  call    cs:__imp_RegQueryValueExW
0x18002b3cd  test    eax, eax
0x18002b3cf  jnz     loc_18002B469
0x18002b3d5  mov     [rsp+2A8h+cbData], 0A0h
0x18002b3dd  add     rsi, 52h ; 'R'
0x18002b3e1  lea     rax, [rsp+2A8h+cbData]
0x18002b3e6  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002b3eb  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002b3f0  xor     r9d, r9d; lpType
0x18002b3f3  xor     r8d, r8d; lpReserved
0x18002b3f6  lea     rdx, pszRegFriendlyName; "FriendlyName"
0x18002b3fd  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002b402  call    cs:__imp_RegQueryValueExW
0x18002b408  test    eax, eax
0x18002b40a  jz      short loc_18002B472
0x18002b40c  mov     [rsi], bx
0x18002b40f  jmp     short loc_18002B472
0x18002b411  mov     ecx, 3F7h; dwErrCode
0x18002b416  call    cs:__imp_SetLastError
0x18002b41c  mov     edi, ebx
0x18002b41e  mov     [rsp+2A8h+var_274], ebx
0x18002b422  jmp     short loc_18002B472
0x18002b424  mov     ecx, 57h ; 'W'
0x18002b429  jmp     short loc_18002B416
0x18002b42b  lea     rax, [rsp+2A8h+cbData]
0x18002b430  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18002b435  mov     [rsp+2A8h+phkResult], rsi; lpData
0x18002b43a  xor     r9d, r9d; lpType
0x18002b43d  xor     r8d, r8d; lpReserved
0x18002b440  lea     rdx, pszRegDockState; "DockState"
0x18002b447  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002b44c  call    cs:__imp_RegQueryValueExW
0x18002b452  test    eax, eax
0x18002b454  jnz     short loc_18002B45E
0x18002b456  cmp     [rsi], ebx
0x18002b458  jnz     loc_18002B39A
0x18002b45e  mov     dword ptr [rsi], 7
0x18002b464  jmp     loc_18002B39A
0x18002b469  mov     [r14], bx
0x18002b46d  jmp     loc_18002B3D5
0x18002b472  jmp     short loc_18002B485
0x18002b474  mov     ecx, 57h ; 'W'; dwErrCode
0x18002b479  call    cs:__imp_SetLastError
0x18002b47f  xor     edi, edi
0x18002b481  mov     [rsp+2A8h+var_274], edi
0x18002b485  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18002b48a  test    rcx, rcx
0x18002b48d  jnz     short loc_18002B4D0
0x18002b48f  mov     rcx, [rsp+2A8h+var_260]; hKey
0x18002b494  test    rcx, rcx
0x18002b497  jnz     short loc_18002B4C8
0x18002b499  mov     rcx, [rsp+2A8h+var_258]; hKey
0x18002b49e  test    rcx, rcx
0x18002b4a1  jz      short loc_18002B4A9
0x18002b4a3  call    cs:__imp_RegCloseKey
0x18002b4a9  mov     eax, edi
0x18002b4ab  mov     rcx, [rsp+2A8h+var_38]
0x18002b4b3  xor     rcx, rsp; StackCookie
0x18002b4b6  call    __security_check_cookie
0x18002b4bb  add     rsp, 288h
0x18002b4c2  pop     r14
0x18002b4c4  pop     rdi
0x18002b4c5  pop     rsi
0x18002b4c6  pop     rbx
0x18002b4c7  retn
0x18002b4c8  call    cs:__imp_RegCloseKey
0x18002b4ce  jmp     short loc_18002B499
0x18002b4d0  call    cs:__imp_RegCloseKey
0x18002b4d6  jmp     short loc_18002B48F
```
