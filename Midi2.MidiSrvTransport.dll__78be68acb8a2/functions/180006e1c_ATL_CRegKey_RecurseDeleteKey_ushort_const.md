# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180006e1c`
- end: `0x180006f63`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006e1c`
- `0x1800072dc`

## callees

- `0x180002470`
- `0x1800055d0`
- `0x180006e1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006efe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006efe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f34`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
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
0x180006e1c  mov     [rsp-8+arg_10], rbx
0x180006e21  mov     [rsp-8+arg_18], rsi
0x180006e26  push    rbp
0x180006e27  push    rdi
0x180006e28  push    r14
0x180006e2a  lea     rbp, [rsp-180h]
0x180006e32  sub     rsp, 280h
0x180006e39  mov     rax, cs:__security_cookie
0x180006e40  xor     rax, rsp
0x180006e43  mov     [rbp+190h+var_20], rax
0x180006e4a  xor     r14d, r14d
0x180006e4d  lea     rax, [rsp+290h+var_230]
0x180006e52  mov     rdi, rcx
0x180006e55  mov     [rsp+290h+hKey], r14
0x180006e5a  mov     rcx, [rcx]; hKey
0x180006e5d  mov     r9d, 2001Fh; samDesired
0x180006e63  xor     r8d, r8d; ulOptions
0x180006e66  mov     [rsp+290h+var_240], r14
0x180006e6b  mov     [rsp+290h+var_238], r14
0x180006e70  mov     rsi, rdx
0x180006e73  mov     [rsp+290h+var_230], r14
0x180006e78  mov     [rsp+290h+phkResult], rax; phkResult
0x180006e7d  call    cs:__imp_RegOpenKeyExW
0x180006e83  mov     rcx, [rsp+290h+hKey]; hKey
0x180006e88  mov     ebx, eax
0x180006e8a  test    eax, eax
0x180006e8c  jnz     loc_180006F2F
0x180006e92  mov     ebx, r14d
0x180006e95  test    rcx, rcx
0x180006e98  jz      short loc_180006EA2
0x180006e9a  call    cs:__imp_RegCloseKey
0x180006ea0  mov     ebx, eax
0x180006ea2  mov     rcx, [rsp+290h+var_230]
0x180006ea7  mov     [rsp+290h+hKey], rcx
0x180006eac  test    ebx, ebx
0x180006eae  jnz     short loc_180006F2F
0x180006eb0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180006eb5  jmp     short loc_180006ED1
0x180006eb7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180006ebc  lea     rcx, [rsp+290h+hKey]; this
0x180006ec1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006ec6  mov     rcx, [rsp+290h+hKey]; hKey
0x180006ecb  mov     ebx, eax
0x180006ecd  test    eax, eax
0x180006ecf  jnz     short loc_180006F2F
0x180006ed1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180006ed6  mov     [rsp+290h+cchName], 100h
0x180006ede  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180006ee3  lea     r9, [rsp+290h+cchName]; lpcchName
0x180006ee8  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180006eed  lea     r8, [rsp+290h+Name]; lpName
0x180006ef2  mov     [rsp+290h+lpClass], r14; lpClass
0x180006ef7  xor     edx, edx; dwIndex
0x180006ef9  mov     [rsp+290h+phkResult], r14; lpReserved
0x180006efe  call    cs:__imp_RegEnumKeyExW
0x180006f04  test    eax, eax
0x180006f06  jz      short loc_180006EB7
0x180006f08  mov     rcx, [rsp+290h+hKey]; hKey
0x180006f0d  test    rcx, rcx
0x180006f10  jz      short loc_180006F1D
0x180006f12  call    cs:__imp_RegCloseKey
0x180006f18  mov     [rsp+290h+hKey], r14
0x180006f1d  mov     rdx, rsi; unsigned __int16 *
0x180006f20  mov     rcx, rdi; this
0x180006f23  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006f28  mov     rcx, [rsp+290h+hKey]; hKey
0x180006f2d  mov     ebx, eax
0x180006f2f  test    rcx, rcx
0x180006f32  jz      short loc_180006F3A
0x180006f34  call    cs:__imp_RegCloseKey
0x180006f3a  mov     eax, ebx
0x180006f3c  mov     rcx, [rbp+190h+var_20]
0x180006f43  xor     rcx, rsp; StackCookie
0x180006f46  call    __security_check_cookie
0x180006f4b  lea     r11, [rsp+290h+var_10]
0x180006f53  mov     rbx, [r11+30h]
0x180006f57  mov     rsi, [r11+38h]
0x180006f5b  mov     rsp, r11
0x180006f5e  pop     r14
0x180006f60  pop     rdi
0x180006f61  pop     rbp
0x180006f62  retn
```
