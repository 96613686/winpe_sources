# HasDriveLetter

- ea: `0x18000e5d0`
- end: `0x18000e7a8`
- name: `HasDriveLetter`
- size: `472`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeMountPoint)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1800022c0`

## callees

- `0x1800097d0`
- `0x18000a192`
- `0x18000e0f8`
- `0x18000e53c`
- `0x18000e5d0`
- `0x18000e7b0`
- `0x18000e838`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b4`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18000e689`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18000e689`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000e619`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000e619`

## pseudocode

```c
__int64 __fastcall HasDriveLetter(LPCWSTR lpszVolumeMountPoint)
{
  DWORD LastError; // eax
  int v3; // r8d
  unsigned __int64 v4; // rdx
  DWORD v5; // eax
  int v6; // r8d
  DWORD cchReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(szVolumeName, 0, 0x20Au);
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x105u) )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, LastError, (__int64)lpszVolumeMountPoint);
    }
    return 0;
  }
  memset_0(szVolumePathNames, 0, 0x20Au);
  cchReturnLength = 0;
  if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x105u, &cchReturnLength) )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v5 = GetLastError();
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v6, v5, (__int64)szVolumeName);
    }
    return 0;
  }
  v9 = 0;
  if ( (int)StringCchLengthW(szVolumePathNames, v4, &v9) < 0 || !v9 )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, szVolumeName);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
      (unsigned int)szVolumePathNames,
      (__int64)szVolumeName);
  }
  return 1;
}

```

## disassembly

```asm
0x18000e5d0  mov     [rsp-8+arg_8], rbx
0x18000e5d5  push    rbp
0x18000e5d6  lea     rbp, [rsp-370h]
0x18000e5de  sub     rsp, 470h
0x18000e5e5  mov     rax, cs:__security_cookie
0x18000e5ec  xor     rax, rsp
0x18000e5ef  mov     [rbp+370h+var_10], rax
0x18000e5f6  mov     rbx, rcx
0x18000e5f9  xor     edx, edx; Val
0x18000e5fb  lea     rcx, [rsp+470h+szVolumeName]; void *
0x18000e600  mov     r8d, 20Ah; Size
0x18000e606  call    memset_0
0x18000e60b  mov     r8d, 105h; cchBufferLength
0x18000e611  lea     rdx, [rsp+470h+szVolumeName]; lpszVolumeName
0x18000e616  mov     rcx, rbx; lpszVolumeMountPoint
0x18000e619  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000e61f  test    eax, eax
0x18000e621  jnz     short loc_18000E656
0x18000e623  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e62a  lea     rax, WPP_GLOBAL_Control
0x18000e631  cmp     rcx, rax
0x18000e634  jz      loc_18000E786
0x18000e63a  test    byte ptr [rcx+1Ch], 4
0x18000e63e  jz      loc_18000E786
0x18000e644  call    cs:__imp_GetLastError
0x18000e64a  mov     edx, 0Ah
0x18000e64f  mov     [rsp+470h+var_450], rbx
0x18000e654  jmp     short loc_18000E6C9
0x18000e656  xor     edx, edx; Val
0x18000e658  lea     rcx, [rbp+370h+szVolumePathNames]; void *
0x18000e65f  mov     r8d, 20Ah; Size
0x18000e665  call    memset_0
0x18000e66a  lea     r9, [rsp+470h+cchReturnLength]; lpcchReturnLength
0x18000e66f  mov     [rsp+470h+cchReturnLength], 0
0x18000e677  mov     r8d, 105h; cchBufferLength
0x18000e67d  lea     rdx, [rbp+370h+szVolumePathNames]; lpszVolumePathNames
0x18000e684  lea     rcx, [rsp+470h+szVolumeName]; lpszVolumeName
0x18000e689  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000e68f  test    eax, eax
0x18000e691  jnz     short loc_18000E6E1
0x18000e693  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e69a  lea     rax, WPP_GLOBAL_Control
0x18000e6a1  cmp     rcx, rax
0x18000e6a4  jz      loc_18000E786
0x18000e6aa  test    byte ptr [rcx+1Ch], 4
0x18000e6ae  jz      loc_18000E786
0x18000e6b4  call    cs:__imp_GetLastError
0x18000e6ba  lea     rcx, [rsp+470h+szVolumeName]
0x18000e6bf  mov     edx, 0Bh
0x18000e6c4  mov     [rsp+470h+var_450], rcx
0x18000e6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d0  mov     r9d, eax
0x18000e6d3  mov     rcx, [rcx+10h]
0x18000e6d7  call    WPP_SF_DS
0x18000e6dc  jmp     loc_18000E786
0x18000e6e1  lea     r8, [rsp+470h+var_438]; unsigned __int64 *
0x18000e6e6  mov     [rsp+470h+var_438], 0
0x18000e6ef  lea     rcx, [rbp+370h+szVolumePathNames]; unsigned __int16 *
0x18000e6f6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000e6fb  test    eax, eax
0x18000e6fd  js      short loc_18000E750
0x18000e6ff  cmp     [rsp+470h+var_438], 0
0x18000e705  jz      short loc_18000E750
0x18000e707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e70e  lea     rax, WPP_GLOBAL_Control
0x18000e715  cmp     rcx, rax
0x18000e718  jz      short loc_18000E749
0x18000e71a  test    dword ptr [rcx+1Ch], 100h
0x18000e721  jz      short loc_18000E749
0x18000e723  mov     rcx, [rcx+10h]
0x18000e727  lea     rax, [rsp+470h+szVolumeName]
0x18000e72c  mov     edx, 0Dh
0x18000e731  mov     [rsp+470h+var_450], rax
0x18000e736  lea     r9, [rbp+370h+szVolumePathNames]
0x18000e73d  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x18000e744  call    WPP_SF_SS
0x18000e749  mov     eax, 1
0x18000e74e  jmp     short loc_18000E788
0x18000e750  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e757  lea     rax, WPP_GLOBAL_Control
0x18000e75e  cmp     rcx, rax
0x18000e761  jz      short loc_18000E786
0x18000e763  test    dword ptr [rcx+1Ch], 100h
0x18000e76a  jz      short loc_18000E786
0x18000e76c  mov     rcx, [rcx+10h]
0x18000e770  lea     r9, [rsp+470h+szVolumeName]
0x18000e775  mov     edx, 0Ch
0x18000e77a  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x18000e781  call    WPP_SF_S
0x18000e786  xor     eax, eax
0x18000e788  mov     rcx, [rbp+370h+var_10]
0x18000e78f  xor     rcx, rsp; StackCookie
0x18000e792  call    __security_check_cookie
0x18000e797  mov     rbx, [rsp+470h+arg_8]
0x18000e79f  add     rsp, 470h
0x18000e7a6  pop     rbp
0x18000e7a7  retn
```
