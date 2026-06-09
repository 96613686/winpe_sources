# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180003d58`
- end: `0x180003e9f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003d58`
- `0x1800041fc`

## callees

- `0x180003640`
- `0x180003d58`
- `0x180005f60`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180003e3a`
- `ADVAPI32!RegEnumKeyExW` at `0x180003e3a`
- `ADVAPI32!RegOpenKeyExW` at `0x180003db9`
- `ADVAPI32!RegOpenKeyExW` at `0x180003db9`
- `ADVAPI32!RegCloseKey` at `0x180003dd6`
- `ADVAPI32!RegCloseKey` at `0x180003e4e`
- `ADVAPI32!RegCloseKey` at `0x180003e70`
- `ADVAPI32!RegCloseKey` at `0x180003dd6`
- `ADVAPI32!RegCloseKey` at `0x180003e4e`
- `ADVAPI32!RegCloseKey` at `0x180003e70`

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
0x180003d58  mov     [rsp-8+arg_10], rbx
0x180003d5d  mov     [rsp-8+arg_18], rsi
0x180003d62  push    rbp
0x180003d63  push    rdi
0x180003d64  push    r14
0x180003d66  lea     rbp, [rsp-180h]
0x180003d6e  sub     rsp, 280h
0x180003d75  mov     rax, cs:__security_cookie
0x180003d7c  xor     rax, rsp
0x180003d7f  mov     [rbp+190h+var_20], rax
0x180003d86  xor     r14d, r14d
0x180003d89  lea     rax, [rsp+290h+var_230]
0x180003d8e  mov     rdi, rcx
0x180003d91  mov     [rsp+290h+hKey], r14
0x180003d96  mov     rcx, [rcx]; hKey
0x180003d99  mov     r9d, 2001Fh; samDesired
0x180003d9f  xor     r8d, r8d; ulOptions
0x180003da2  mov     [rsp+290h+var_240], r14
0x180003da7  mov     [rsp+290h+var_238], r14
0x180003dac  mov     rsi, rdx
0x180003daf  mov     [rsp+290h+var_230], r14
0x180003db4  mov     [rsp+290h+phkResult], rax; phkResult
0x180003db9  call    cs:__imp_RegOpenKeyExW
0x180003dbf  mov     rcx, [rsp+290h+hKey]; hKey
0x180003dc4  mov     ebx, eax
0x180003dc6  test    eax, eax
0x180003dc8  jnz     loc_180003E6B
0x180003dce  mov     ebx, r14d
0x180003dd1  test    rcx, rcx
0x180003dd4  jz      short loc_180003DDE
0x180003dd6  call    cs:__imp_RegCloseKey
0x180003ddc  mov     ebx, eax
0x180003dde  mov     rcx, [rsp+290h+var_230]
0x180003de3  mov     [rsp+290h+hKey], rcx
0x180003de8  test    ebx, ebx
0x180003dea  jnz     short loc_180003E6B
0x180003dec  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180003df1  jmp     short loc_180003E0D
0x180003df3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180003df8  lea     rcx, [rsp+290h+hKey]; this
0x180003dfd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003e02  mov     rcx, [rsp+290h+hKey]; hKey
0x180003e07  mov     ebx, eax
0x180003e09  test    eax, eax
0x180003e0b  jnz     short loc_180003E6B
0x180003e0d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180003e12  mov     [rsp+290h+cchName], 100h
0x180003e1a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180003e1f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180003e24  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180003e29  lea     r8, [rsp+290h+Name]; lpName
0x180003e2e  mov     [rsp+290h+lpClass], r14; lpClass
0x180003e33  xor     edx, edx; dwIndex
0x180003e35  mov     [rsp+290h+phkResult], r14; lpReserved
0x180003e3a  call    cs:__imp_RegEnumKeyExW
0x180003e40  test    eax, eax
0x180003e42  jz      short loc_180003DF3
0x180003e44  mov     rcx, [rsp+290h+hKey]; hKey
0x180003e49  test    rcx, rcx
0x180003e4c  jz      short loc_180003E59
0x180003e4e  call    cs:__imp_RegCloseKey
0x180003e54  mov     [rsp+290h+hKey], r14
0x180003e59  mov     rdx, rsi; unsigned __int16 *
0x180003e5c  mov     rcx, rdi; this
0x180003e5f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003e64  mov     rcx, [rsp+290h+hKey]; hKey
0x180003e69  mov     ebx, eax
0x180003e6b  test    rcx, rcx
0x180003e6e  jz      short loc_180003E76
0x180003e70  call    cs:__imp_RegCloseKey
0x180003e76  mov     eax, ebx
0x180003e78  mov     rcx, [rbp+190h+var_20]
0x180003e7f  xor     rcx, rsp; StackCookie
0x180003e82  call    __security_check_cookie
0x180003e87  lea     r11, [rsp+290h+var_10]
0x180003e8f  mov     rbx, [r11+30h]
0x180003e93  mov     rsi, [r11+38h]
0x180003e97  mov     rsp, r11
0x180003e9a  pop     r14
0x180003e9c  pop     rdi
0x180003e9d  pop     rbp
0x180003e9e  retn
```
