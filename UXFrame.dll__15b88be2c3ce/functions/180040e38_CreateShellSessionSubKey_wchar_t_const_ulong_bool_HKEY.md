# CreateShellSessionSubKey(wchar_t const *,ulong,bool *,HKEY__ * *)

- ea: `0x180040e38`
- end: `0x180040f29`
- name: `?CreateShellSessionSubKey@@YAJPEB_WKPEA_NPEAPEAUHKEY__@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, REGSAM samDesired, bool *, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800438c4`
- `0x18004be40`

## callees

- `0x180002b20`
- `0x18000fa10`
- `0x180040e38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040ecc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f04`

## pseudocode

```c
__int64 __fastcall CreateShellSessionSubKey(LPCWSTR lpSubKey, REGSAM samDesired, bool *a3, HKEY *a4)
{
  int v7; // ebx
  LSTATUS v8; // eax
  HKEY phkResult; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-28h] BYREF

  if ( a4 )
    *a4 = 0;
  hKey = 0;
  v7 = CreateShellSessionKey((__int64)lpSubKey, &hKey);
  if ( v7 >= 0 )
  {
    phkResult = 0;
    dwDisposition = 0;
    v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, samDesired, 0, &phkResult, &dwDisposition);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      if ( a4 )
        *a4 = phkResult;
      else
        RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180040e38  mov     [rsp+arg_10], rbx
0x180040e3d  push    rbp
0x180040e3e  push    rsi
0x180040e3f  push    rdi
0x180040e40  sub     rsp, 70h
0x180040e44  mov     rax, cs:__security_cookie
0x180040e4b  xor     rax, rsp
0x180040e4e  mov     [rsp+88h+var_20], rax
0x180040e53  mov     rdi, r9
0x180040e56  mov     ebp, edx
0x180040e58  mov     rsi, rcx
0x180040e5b  test    r9, r9
0x180040e5e  jz      short loc_180040E67
0x180040e60  mov     qword ptr [r9], 0
0x180040e67  lea     rdx, [rsp+88h+hKey]; HKEY *
0x180040e6c  mov     [rsp+88h+hKey], 0
0x180040e75  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x180040e7a  mov     ebx, eax
0x180040e7c  test    eax, eax
0x180040e7e  js      loc_180040F0A
0x180040e84  mov     rcx, [rsp+88h+hKey]; hKey
0x180040e89  lea     rax, [rsp+88h+dwDisposition]
0x180040e8e  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x180040e93  xor     r9d, r9d; lpClass
0x180040e96  lea     rax, [rsp+88h+var_38]
0x180040e9b  mov     [rsp+88h+var_38], 0
0x180040ea4  mov     [rsp+88h+phkResult], rax; phkResult
0x180040ea9  xor     r8d, r8d; Reserved
0x180040eac  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040eb5  mov     rdx, rsi; lpSubKey
0x180040eb8  mov     [rsp+88h+samDesired], ebp; samDesired
0x180040ebc  mov     [rsp+88h+dwOptions], 1; dwOptions
0x180040ec4  mov     [rsp+88h+dwDisposition], 0
0x180040ecc  call    cs:__imp_RegCreateKeyExW
0x180040ed2  mov     ebx, eax
0x180040ed4  test    eax, eax
0x180040ed6  jle     short loc_180040EE1
0x180040ed8  movzx   ebx, ax
0x180040edb  or      ebx, 80070000h
0x180040ee1  test    ebx, ebx
0x180040ee3  js      short loc_180040EFF
0x180040ee5  test    rdi, rdi
0x180040ee8  jz      short loc_180040EF4
0x180040eea  mov     rax, [rsp+88h+var_38]
0x180040eef  mov     [rdi], rax
0x180040ef2  jmp     short loc_180040EFF
0x180040ef4  mov     rcx, [rsp+88h+var_38]; hKey
0x180040ef9  call    cs:__imp_RegCloseKey
0x180040eff  mov     rcx, [rsp+88h+hKey]; hKey
0x180040f04  call    cs:__imp_RegCloseKey
0x180040f0a  mov     eax, ebx
0x180040f0c  mov     rcx, [rsp+88h+var_20]
0x180040f11  xor     rcx, rsp; StackCookie
0x180040f14  call    __security_check_cookie
0x180040f19  mov     rbx, [rsp+88h+arg_10]
0x180040f21  add     rsp, 70h
0x180040f25  pop     rdi
0x180040f26  pop     rsi
0x180040f27  pop     rbp
0x180040f28  retn
```
