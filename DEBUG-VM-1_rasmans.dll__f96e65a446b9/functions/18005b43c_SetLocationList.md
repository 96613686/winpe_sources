# SetLocationList

- ea: `0x18005b43c`
- end: `0x18005b619`
- name: `SetLocationList`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005b620`

## callees

- `0x18005b43c`
- `0x18005cf68`
- `0x18005dbd0`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b4fd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b4fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005b4ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005b4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b4ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b58d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b4ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b58d`

## pseudocode

```c
LSTATUS __fastcall SetLocationList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  _DWORD *v7; // rsi
  LPDWORD lpcchClass; // [rsp+38h] [rbp-19h]
  DWORD cchName; // [rsp+58h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+Fh] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+1Fh] BYREF
  WCHAR SubKey[12]; // [rsp+78h] [rbp+27h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Location", 0, (LPWSTR)&Class, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 12;
      v4 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      if ( v6 )
      {
        do
        {
          v7 = *(_DWORD **)(v6 + 16);
          LODWORD(lpcchClass) = *v7;
          StringCchPrintfExW(SubKey, 0xCu, 0, 0, 0x100u, L"%d", lpcchClass);
          v5 = RegCreateKeyExW(hKey, SubKey, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
            break;
          v5 = SetRegDword(phkResult, L"Prefix", (unsigned int)v7[1]);
          if ( !v5 )
            v5 = SetRegDword(phkResult, L"Suffix", (unsigned int)v7[2]);
          RegCloseKey(phkResult);
          if ( v5 )
            break;
          v6 = *(_QWORD *)(v6 + 8);
        }
        while ( v6 );
      }
      else
      {
        v5 = 0;
      }
    }
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005b43c  mov     r11, rsp
0x18005b43f  mov     [r11+18h], rbx
0x18005b443  mov     [r11+20h], rsi
0x18005b447  push    rbp
0x18005b448  push    rdi
0x18005b449  push    r14
0x18005b44b  lea     rbp, [r11-5Fh]
0x18005b44f  sub     rsp, 90h
0x18005b456  mov     rax, cs:__security_cookie
0x18005b45d  xor     rax, rsp
0x18005b460  mov     [rbp+57h+var_18], rax
0x18005b464  xor     r14d, r14d
0x18005b467  lea     rax, [rbp+57h+dwDisposition]
0x18005b46b  mov     [r11-68h], rax
0x18005b46f  lea     r9, Class; lpClass
0x18005b476  lea     rax, [rbp+57h+hKey]
0x18005b47a  mov     [rbp+57h+cchName], r14d
0x18005b47e  mov     [r11-70h], rax
0x18005b482  mov     rdi, rdx
0x18005b485  mov     [r11-78h], r14
0x18005b489  lea     rdx, aLocation; "Location"
0x18005b490  mov     [rsp+0A0h+samDesired], 2000Eh; samDesired
0x18005b498  xor     r8d, r8d; Reserved
0x18005b49b  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18005b4a0  mov     [rbp+57h+dwDisposition], r14d
0x18005b4a4  mov     [rbp+57h+hKey], r14
0x18005b4a8  mov     [rbp+57h+phkResult], r14
0x18005b4ac  call    cs:__imp_RegCreateKeyExW
0x18005b4b2  test    eax, eax
0x18005b4b4  jnz     loc_18005B5F5
0x18005b4ba  jmp     short loc_18005B4D4
0x18005b4bc  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b4c0  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18005b4c4  xor     r9d, r9d; Reserved
0x18005b4c7  xor     r8d, r8d; samDesired
0x18005b4ca  call    cs:__imp_RegDeleteKeyExW
0x18005b4d0  test    eax, eax
0x18005b4d2  jnz     short loc_18005B507
0x18005b4d4  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b4d8  lea     r9, [rbp+57h+cchName]; lpcchName
0x18005b4dc  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18005b4e1  lea     r8, [rbp+57h+SubKey]; lpName
0x18005b4e5  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x18005b4ea  xor     edx, edx; dwIndex
0x18005b4ec  mov     qword ptr [rsp+0A0h+samDesired], r14; lpClass
0x18005b4f1  mov     qword ptr [rsp+0A0h+dwOptions], r14; lpReserved
0x18005b4f6  mov     [rbp+57h+cchName], 0Ch
0x18005b4fd  call    cs:__imp_RegEnumKeyExW
0x18005b503  test    eax, eax
0x18005b505  jz      short loc_18005B4BC
0x18005b507  cmp     eax, 103h
0x18005b50c  mov     ebx, r14d
0x18005b50f  cmovnz  ebx, eax
0x18005b512  test    ebx, ebx
0x18005b514  jnz     loc_18005B5E9
0x18005b51a  mov     rdi, [rdi]
0x18005b51d  test    rdi, rdi
0x18005b520  jz      loc_18005B5E6
0x18005b526  mov     rsi, [rdi+10h]
0x18005b52a  lea     rcx, [rbp+57h+SubKey]; pszDest
0x18005b52e  xor     r9d, r9d; pcchRemaining
0x18005b531  xor     r8d, r8d; ppszDestEnd
0x18005b534  mov     eax, [rsi]
0x18005b536  mov     dword ptr [rsp+0A0h+lpcchClass], eax
0x18005b53a  lea     edx, [r9+0Ch]; cchDest
0x18005b53e  lea     rax, aD; "%d"
0x18005b545  mov     qword ptr [rsp+0A0h+samDesired], rax; pszFormat
0x18005b54a  mov     [rsp+0A0h+dwOptions], 100h; dwFlags
0x18005b552  call    StringCchPrintfExW
0x18005b557  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b55b  lea     rax, [rbp+57h+dwDisposition]
0x18005b55f  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18005b564  lea     r9, Class; lpClass
0x18005b56b  lea     rax, [rbp+57h+phkResult]
0x18005b56f  xor     r8d, r8d; Reserved
0x18005b572  mov     [rsp+0A0h+lpftLastWriteTime], rax; phkResult
0x18005b577  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18005b57b  mov     [rsp+0A0h+lpcchClass], r14; lpSecurityAttributes
0x18005b580  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18005b588  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18005b58d  call    cs:__imp_RegCreateKeyExW
0x18005b593  mov     ebx, eax
0x18005b595  test    eax, eax
0x18005b597  jnz     short loc_18005B5E9
0x18005b599  mov     r8d, [rsi+4]
0x18005b59d  lea     rdx, aPrefix; "Prefix"
0x18005b5a4  mov     rcx, [rbp+57h+phkResult]
0x18005b5a8  call    SetRegDword
0x18005b5ad  mov     ebx, eax
0x18005b5af  test    eax, eax
0x18005b5b1  jnz     short loc_18005B5C9
0x18005b5b3  mov     r8d, [rsi+8]
0x18005b5b7  lea     rdx, aSuffix; "Suffix"
0x18005b5be  mov     rcx, [rbp+57h+phkResult]
0x18005b5c2  call    SetRegDword
0x18005b5c7  mov     ebx, eax
0x18005b5c9  mov     rcx, [rbp+57h+phkResult]; hKey
0x18005b5cd  call    cs:__imp_RegCloseKey
0x18005b5d3  test    ebx, ebx
0x18005b5d5  jnz     short loc_18005B5E9
0x18005b5d7  mov     rdi, [rdi+8]
0x18005b5db  test    rdi, rdi
0x18005b5de  jnz     loc_18005B526
0x18005b5e4  jmp     short loc_18005B5E9
0x18005b5e6  mov     ebx, r14d
0x18005b5e9  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b5ed  call    cs:__imp_RegCloseKey
0x18005b5f3  mov     eax, ebx
0x18005b5f5  mov     rcx, [rbp+57h+var_18]
0x18005b5f9  xor     rcx, rsp; StackCookie
0x18005b5fc  call    __security_check_cookie
0x18005b601  lea     r11, [rsp+0A0h+var_10]
0x18005b609  mov     rbx, [r11+30h]
0x18005b60d  mov     rsi, [r11+38h]
0x18005b611  mov     rsp, r11
0x18005b614  pop     r14
0x18005b616  pop     rdi
0x18005b617  pop     rbp
0x18005b618  retn
```
