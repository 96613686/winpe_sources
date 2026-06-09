# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x180011ccc`
- end: `0x180011e13`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ddf8`
- `0x180011ccc`

## callees

- `0x1800026f0`
- `0x18000b438`
- `0x180011ccc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011dae`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011dae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011de4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011de4`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x180011ccc  mov     [rsp-8+arg_10], rbx
0x180011cd1  mov     [rsp-8+arg_18], rsi
0x180011cd6  push    rbp
0x180011cd7  push    rdi
0x180011cd8  push    r14
0x180011cda  lea     rbp, [rsp-180h]
0x180011ce2  sub     rsp, 280h
0x180011ce9  mov     rax, cs:__security_cookie
0x180011cf0  xor     rax, rsp
0x180011cf3  mov     [rbp+190h+var_20], rax
0x180011cfa  xor     r14d, r14d
0x180011cfd  lea     rax, [rsp+290h+var_230]
0x180011d02  mov     rdi, rcx
0x180011d05  mov     [rsp+290h+hKey], r14
0x180011d0a  mov     rcx, [rcx]; hKey
0x180011d0d  mov     r9d, 2001Fh; samDesired
0x180011d13  xor     r8d, r8d; ulOptions
0x180011d16  mov     [rsp+290h+var_240], r14
0x180011d1b  mov     [rsp+290h+var_238], r14
0x180011d20  mov     rsi, rdx
0x180011d23  mov     [rsp+290h+var_230], r14
0x180011d28  mov     [rsp+290h+phkResult], rax; phkResult
0x180011d2d  call    cs:__imp_RegOpenKeyExW
0x180011d33  mov     rcx, [rsp+290h+hKey]; hKey
0x180011d38  mov     ebx, eax
0x180011d3a  test    eax, eax
0x180011d3c  jnz     loc_180011DDF
0x180011d42  mov     ebx, r14d
0x180011d45  test    rcx, rcx
0x180011d48  jz      short loc_180011D52
0x180011d4a  call    cs:__imp_RegCloseKey
0x180011d50  mov     ebx, eax
0x180011d52  mov     rcx, [rsp+290h+var_230]
0x180011d57  mov     [rsp+290h+hKey], rcx
0x180011d5c  test    ebx, ebx
0x180011d5e  jnz     short loc_180011DDF
0x180011d60  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180011d65  jmp     short loc_180011D81
0x180011d67  lea     rdx, [rsp+290h+Name]; wchar_t *
0x180011d6c  lea     rcx, [rsp+290h+hKey]; this
0x180011d71  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180011d76  mov     rcx, [rsp+290h+hKey]; hKey
0x180011d7b  mov     ebx, eax
0x180011d7d  test    eax, eax
0x180011d7f  jnz     short loc_180011DDF
0x180011d81  lea     rax, [rsp+290h+ftLastWriteTime]
0x180011d86  mov     [rsp+290h+cchName], 100h
0x180011d8e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180011d93  lea     r9, [rsp+290h+cchName]; lpcchName
0x180011d98  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180011d9d  lea     r8, [rsp+290h+Name]; lpName
0x180011da2  mov     [rsp+290h+lpClass], r14; lpClass
0x180011da7  xor     edx, edx; dwIndex
0x180011da9  mov     [rsp+290h+phkResult], r14; lpReserved
0x180011dae  call    cs:__imp_RegEnumKeyExW
0x180011db4  test    eax, eax
0x180011db6  jz      short loc_180011D67
0x180011db8  mov     rcx, [rsp+290h+hKey]; hKey
0x180011dbd  test    rcx, rcx
0x180011dc0  jz      short loc_180011DCD
0x180011dc2  call    cs:__imp_RegCloseKey
0x180011dc8  mov     [rsp+290h+hKey], r14
0x180011dcd  mov     rdx, rsi; wchar_t *
0x180011dd0  mov     rcx, rdi; this
0x180011dd3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180011dd8  mov     rcx, [rsp+290h+hKey]; hKey
0x180011ddd  mov     ebx, eax
0x180011ddf  test    rcx, rcx
0x180011de2  jz      short loc_180011DEA
0x180011de4  call    cs:__imp_RegCloseKey
0x180011dea  mov     eax, ebx
0x180011dec  mov     rcx, [rbp+190h+var_20]
0x180011df3  xor     rcx, rsp; StackCookie
0x180011df6  call    __security_check_cookie
0x180011dfb  lea     r11, [rsp+290h+var_10]
0x180011e03  mov     rbx, [r11+30h]
0x180011e07  mov     rsi, [r11+38h]
0x180011e0b  mov     rsp, r11
0x180011e0e  pop     r14
0x180011e10  pop     rdi
0x180011e11  pop     rbp
0x180011e12  retn
```
