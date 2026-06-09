# RegOpenSessionDataKey

- ea: `0x18004cee4`
- end: `0x18004cfac`
- name: `RegOpenSessionDataKey`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ce70`

## callees

- `0x18004cee4`
- `0x180062e6c`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cf75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cf87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cf87`

## pseudocode

```c
__int64 __fastcall RegOpenSessionDataKey(unsigned int a1, __int64 a2, HKEY *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  wchar_t pszDest[8]; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  *a3 = 0;
  v6 = v5;
  if ( !v5 )
  {
    v7 = StringCchPrintfW(pszDest, 8u, L"%d", a1);
    if ( v7 < 0 )
      v6 = (unsigned __int16)v7;
    else
      v6 = RegOpenKeyExW(hKey, pszDest, 0, 0x20006u, a3);
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18004cee4  mov     r11, rsp
0x18004cee7  mov     [r11+10h], rbx
0x18004ceeb  mov     [r11+20h], rsi
0x18004ceef  push    rdi
0x18004cef0  sub     rsp, 50h
0x18004cef4  mov     rax, cs:__security_cookie
0x18004cefb  xor     rax, rsp
0x18004cefe  mov     [rsp+58h+var_10], rax
0x18004cf03  mov     rdi, r8
0x18004cf06  mov     qword ptr [r11-28h], 0
0x18004cf0e  mov     esi, ecx
0x18004cf10  lea     rax, [r11-28h]
0x18004cf14  xor     r8d, r8d; ulOptions
0x18004cf17  mov     [r11-38h], rax
0x18004cf1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004cf22  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004cf29  mov     r9d, 8; samDesired
0x18004cf2f  call    cs:__imp_RegOpenKeyExW
0x18004cf35  mov     qword ptr [rdi], 0
0x18004cf3c  mov     ebx, eax
0x18004cf3e  test    eax, eax
0x18004cf40  jnz     short loc_18004CF8D
0x18004cf42  mov     r9d, esi
0x18004cf45  lea     r8, aD; "%d"
0x18004cf4c  lea     edx, [rax+8]; cchDest
0x18004cf4f  lea     rcx, [rsp+58h+pszDest]; pszDest
0x18004cf54  call    StringCchPrintfW
0x18004cf59  test    eax, eax
0x18004cf5b  js      short loc_18004CF7F
0x18004cf5d  mov     rcx, [rsp+58h+hKey]; hKey
0x18004cf62  lea     rdx, [rsp+58h+pszDest]; lpSubKey
0x18004cf67  mov     r9d, 20006h; samDesired
0x18004cf6d  mov     [rsp+58h+phkResult], rdi; phkResult
0x18004cf72  xor     r8d, r8d; ulOptions
0x18004cf75  call    cs:__imp_RegOpenKeyExW
0x18004cf7b  mov     ebx, eax
0x18004cf7d  jmp     short loc_18004CF82
0x18004cf7f  movzx   ebx, ax
0x18004cf82  mov     rcx, [rsp+58h+hKey]; hKey
0x18004cf87  call    cs:__imp_RegCloseKey
0x18004cf8d  mov     eax, ebx
0x18004cf8f  mov     rcx, [rsp+58h+var_10]
0x18004cf94  xor     rcx, rsp; StackCookie
0x18004cf97  call    __security_check_cookie
0x18004cf9c  mov     rbx, [rsp+58h+arg_8]
0x18004cfa1  mov     rsi, [rsp+58h+arg_18]
0x18004cfa6  add     rsp, 50h
0x18004cfaa  pop     rdi
0x18004cfab  retn
```
