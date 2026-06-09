# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18001597c`
- end: `0x180015ac3`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001597c`
- `0x180015e40`

## callees

- `0x180001800`
- `0x180014148`
- `0x18001597c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800159fa`
- `ADVAPI32!RegCloseKey` at `0x180015a72`
- `ADVAPI32!RegCloseKey` at `0x180015a94`
- `ADVAPI32!RegCloseKey` at `0x1800159fa`
- `ADVAPI32!RegCloseKey` at `0x180015a72`
- `ADVAPI32!RegCloseKey` at `0x180015a94`
- `ADVAPI32!RegEnumKeyExW` at `0x180015a5e`
- `ADVAPI32!RegEnumKeyExW` at `0x180015a5e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800159dd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800159dd`

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
0x18001597c  mov     [rsp-8+arg_10], rbx
0x180015981  mov     [rsp-8+arg_18], rsi
0x180015986  push    rbp
0x180015987  push    rdi
0x180015988  push    r14
0x18001598a  lea     rbp, [rsp-180h]
0x180015992  sub     rsp, 280h
0x180015999  mov     rax, cs:__security_cookie
0x1800159a0  xor     rax, rsp
0x1800159a3  mov     [rbp+190h+var_20], rax
0x1800159aa  xor     r14d, r14d
0x1800159ad  lea     rax, [rsp+290h+var_230]
0x1800159b2  mov     rdi, rcx
0x1800159b5  mov     [rsp+290h+hKey], r14
0x1800159ba  mov     rcx, [rcx]; hKey
0x1800159bd  mov     r9d, 2001Fh; samDesired
0x1800159c3  xor     r8d, r8d; ulOptions
0x1800159c6  mov     [rsp+290h+var_240], r14
0x1800159cb  mov     [rsp+290h+var_238], r14
0x1800159d0  mov     rsi, rdx
0x1800159d3  mov     [rsp+290h+var_230], r14
0x1800159d8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800159dd  call    cs:__imp_RegOpenKeyExW
0x1800159e3  mov     rcx, [rsp+290h+hKey]; hKey
0x1800159e8  mov     ebx, eax
0x1800159ea  test    eax, eax
0x1800159ec  jnz     loc_180015A8F
0x1800159f2  mov     ebx, r14d
0x1800159f5  test    rcx, rcx
0x1800159f8  jz      short loc_180015A02
0x1800159fa  call    cs:__imp_RegCloseKey
0x180015a00  mov     ebx, eax
0x180015a02  mov     rcx, [rsp+290h+var_230]
0x180015a07  mov     [rsp+290h+hKey], rcx
0x180015a0c  test    ebx, ebx
0x180015a0e  jnz     short loc_180015A8F
0x180015a10  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180015a15  jmp     short loc_180015A31
0x180015a17  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180015a1c  lea     rcx, [rsp+290h+hKey]; this
0x180015a21  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180015a26  mov     rcx, [rsp+290h+hKey]; hKey
0x180015a2b  mov     ebx, eax
0x180015a2d  test    eax, eax
0x180015a2f  jnz     short loc_180015A8F
0x180015a31  lea     rax, [rsp+290h+ftLastWriteTime]
0x180015a36  mov     [rsp+290h+cchName], 100h
0x180015a3e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180015a43  lea     r9, [rsp+290h+cchName]; lpcchName
0x180015a48  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180015a4d  lea     r8, [rsp+290h+Name]; lpName
0x180015a52  mov     [rsp+290h+lpClass], r14; lpClass
0x180015a57  xor     edx, edx; dwIndex
0x180015a59  mov     [rsp+290h+phkResult], r14; lpReserved
0x180015a5e  call    cs:__imp_RegEnumKeyExW
0x180015a64  test    eax, eax
0x180015a66  jz      short loc_180015A17
0x180015a68  mov     rcx, [rsp+290h+hKey]; hKey
0x180015a6d  test    rcx, rcx
0x180015a70  jz      short loc_180015A7D
0x180015a72  call    cs:__imp_RegCloseKey
0x180015a78  mov     [rsp+290h+hKey], r14
0x180015a7d  mov     rdx, rsi; unsigned __int16 *
0x180015a80  mov     rcx, rdi; this
0x180015a83  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180015a88  mov     rcx, [rsp+290h+hKey]; hKey
0x180015a8d  mov     ebx, eax
0x180015a8f  test    rcx, rcx
0x180015a92  jz      short loc_180015A9A
0x180015a94  call    cs:__imp_RegCloseKey
0x180015a9a  mov     eax, ebx
0x180015a9c  mov     rcx, [rbp+190h+var_20]
0x180015aa3  xor     rcx, rsp; StackCookie
0x180015aa6  call    __security_check_cookie
0x180015aab  lea     r11, [rsp+290h+var_10]
0x180015ab3  mov     rbx, [r11+30h]
0x180015ab7  mov     rsi, [r11+38h]
0x180015abb  mov     rsp, r11
0x180015abe  pop     r14
0x180015ac0  pop     rdi
0x180015ac1  pop     rbp
0x180015ac2  retn
```
