# GetRollbackSection(ushort const *,ushort *,ulong)

- ea: `0x180002d50`
- end: `0x180002ea8`
- name: `?GetRollbackSection@@YAHPEBGPEAGK@Z`
- size: `344`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002ad4`

## callees

- `0x1800022bc`
- `0x180002d50`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180002e2b`
- `ADVAPI32!RegCreateKeyExW` at `0x180002e2b`
- `ADVAPI32!RegQueryValueExW` at `0x180002e5e`
- `ADVAPI32!RegQueryValueExW` at `0x180002e5e`
- `ADVAPI32!RegCloseKey` at `0x180002e79`
- `ADVAPI32!RegCloseKey` at `0x180002e79`

## string_xrefs

- `0x180002e44`: `InstallINFSection`

## pseudocode

```c
__int64 __fastcall GetRollbackSection(unsigned __int16 *a1, LPBYTE lpData)
{
  unsigned int v4; // edi
  ULONG dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v4 = 0;
  StringCchCopyW(pszPathOut, 0x104u, L"Software\\Microsoft\\Advanced INF Setup");
  if ( a1 && !(unsigned int)PathIsUnc2(a1) && !IsExtendedLengthDosDevicePath(a1) )
  {
    while ( *a1 == 92 )
      ++a1;
  }
  PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, a1, dwOptions);
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0x20019u, 0, &hKey, &dwDisposition) )
  {
    dwDisposition = 520;
    if ( !RegQueryValueExW(hKey, L"InstallINFSection", 0, 0, lpData, &dwDisposition) && *(_WORD *)lpData )
      v4 = 1;
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180002d50  mov     [rsp-8+arg_10], rbx
0x180002d55  mov     [rsp-8+arg_18], rsi
0x180002d5a  push    rbp
0x180002d5b  push    rdi
0x180002d5c  push    r14
0x180002d5e  lea     rbp, [rsp-180h]
0x180002d66  sub     rsp, 280h
0x180002d6d  mov     rax, cs:__security_cookie
0x180002d74  xor     rax, rsp
0x180002d77  mov     [rbp+190h+var_20], rax
0x180002d7e  xor     r14d, r14d
0x180002d81  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x180002d88  mov     rsi, rdx
0x180002d8b  mov     [rsp+290h+hKey], r14
0x180002d90  mov     rbx, rcx
0x180002d93  mov     [rsp+290h+dwDisposition], r14d
0x180002d98  mov     edx, 104h; unsigned __int64
0x180002d9d  lea     rcx, [rsp+290h+pszPathOut]; unsigned __int16 *
0x180002da2  mov     edi, r14d
0x180002da5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002daa  test    rbx, rbx
0x180002dad  jz      short loc_180002DDC
0x180002daf  lea     r8, IsBackslash
0x180002db6  xor     edx, edx
0x180002db8  mov     rcx, rbx; unsigned __int16 *
0x180002dbb  call    PathIsUnc2
0x180002dc0  test    eax, eax
0x180002dc2  jnz     short loc_180002DDC
0x180002dc4  mov     rcx, rbx; unsigned __int16 *
0x180002dc7  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180002dcc  test    al, al
0x180002dce  jnz     short loc_180002DDC
0x180002dd0  jmp     short loc_180002DD6
0x180002dd2  add     rbx, 2
0x180002dd6  cmp     word ptr [rbx], 5Ch ; '\'
0x180002dda  jz      short loc_180002DD2
0x180002ddc  mov     r9, rbx; pszMore
0x180002ddf  lea     r8, [rsp+290h+pszPathOut]; pszPathIn
0x180002de4  mov     edx, 104h; cchPathOut
0x180002de9  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180002dee  call    PathCchCombineEx
0x180002df3  lea     rax, [rsp+290h+dwDisposition]
0x180002df8  xor     r9d, r9d; lpClass
0x180002dfb  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x180002e00  lea     rdx, [rsp+290h+pszPathOut]; lpSubKey
0x180002e05  lea     rax, [rsp+290h+hKey]
0x180002e0a  xor     r8d, r8d; Reserved
0x180002e0d  mov     [rsp+290h+phkResult], rax; phkResult
0x180002e12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002e19  mov     [rsp+290h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180002e1e  mov     [rsp+290h+samDesired], 20019h; samDesired
0x180002e26  mov     [rsp+290h+dwOptions], r14d; dwOptions
0x180002e2b  call    cs:__imp_RegCreateKeyExW
0x180002e31  test    eax, eax
0x180002e33  jnz     short loc_180002E7F
0x180002e35  mov     rcx, [rsp+290h+hKey]; hKey
0x180002e3a  lea     rax, [rsp+290h+dwDisposition]
0x180002e3f  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x180002e44  lea     rdx, ValueName; "InstallINFSection"
0x180002e4b  xor     r9d, r9d; lpType
0x180002e4e  mov     qword ptr [rsp+290h+dwOptions], rsi; lpData
0x180002e53  xor     r8d, r8d; lpReserved
0x180002e56  mov     [rsp+290h+dwDisposition], 208h
0x180002e5e  call    cs:__imp_RegQueryValueExW
0x180002e64  test    eax, eax
0x180002e66  jnz     short loc_180002E74
0x180002e68  cmp     [rsi], r14w
0x180002e6c  mov     eax, 1
0x180002e71  cmovnz  edi, eax
0x180002e74  mov     rcx, [rsp+290h+hKey]; hKey
0x180002e79  call    cs:__imp_RegCloseKey
0x180002e7f  mov     eax, edi
0x180002e81  mov     rcx, [rbp+190h+var_20]
0x180002e88  xor     rcx, rsp; StackCookie
0x180002e8b  call    __security_check_cookie
0x180002e90  lea     r11, [rsp+290h+var_10]
0x180002e98  mov     rbx, [r11+30h]
0x180002e9c  mov     rsi, [r11+38h]
0x180002ea0  mov     rsp, r11
0x180002ea3  pop     r14
0x180002ea5  pop     rdi
0x180002ea6  pop     rbp
0x180002ea7  retn
```
