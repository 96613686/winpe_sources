# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180005bb8`
- end: `0x180005cff`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005bb8`
- `0x18000607c`

## callees

- `0x180001550`
- `0x180005348`
- `0x180005bb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005c9a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005c9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c19`

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
0x180005bb8  mov     [rsp-8+arg_10], rbx
0x180005bbd  mov     [rsp-8+arg_18], rsi
0x180005bc2  push    rbp
0x180005bc3  push    rdi
0x180005bc4  push    r14
0x180005bc6  lea     rbp, [rsp-180h]
0x180005bce  sub     rsp, 280h
0x180005bd5  mov     rax, cs:__security_cookie
0x180005bdc  xor     rax, rsp
0x180005bdf  mov     [rbp+190h+var_20], rax
0x180005be6  xor     r14d, r14d
0x180005be9  lea     rax, [rsp+290h+var_230]
0x180005bee  mov     rdi, rcx
0x180005bf1  mov     [rsp+290h+hKey], r14
0x180005bf6  mov     rcx, [rcx]; hKey
0x180005bf9  mov     r9d, 2001Fh; samDesired
0x180005bff  xor     r8d, r8d; ulOptions
0x180005c02  mov     [rsp+290h+var_240], r14
0x180005c07  mov     [rsp+290h+var_238], r14
0x180005c0c  mov     rsi, rdx
0x180005c0f  mov     [rsp+290h+var_230], r14
0x180005c14  mov     [rsp+290h+phkResult], rax; phkResult
0x180005c19  call    cs:__imp_RegOpenKeyExW
0x180005c1f  mov     rcx, [rsp+290h+hKey]; hKey
0x180005c24  mov     ebx, eax
0x180005c26  test    eax, eax
0x180005c28  jnz     loc_180005CCB
0x180005c2e  mov     ebx, r14d
0x180005c31  test    rcx, rcx
0x180005c34  jz      short loc_180005C3E
0x180005c36  call    cs:__imp_RegCloseKey
0x180005c3c  mov     ebx, eax
0x180005c3e  mov     rcx, [rsp+290h+var_230]
0x180005c43  mov     [rsp+290h+hKey], rcx
0x180005c48  test    ebx, ebx
0x180005c4a  jnz     short loc_180005CCB
0x180005c4c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180005c51  jmp     short loc_180005C6D
0x180005c53  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005c58  lea     rcx, [rsp+290h+hKey]; this
0x180005c5d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005c62  mov     rcx, [rsp+290h+hKey]; hKey
0x180005c67  mov     ebx, eax
0x180005c69  test    eax, eax
0x180005c6b  jnz     short loc_180005CCB
0x180005c6d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005c72  mov     [rsp+290h+cchName], 100h
0x180005c7a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180005c7f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180005c84  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180005c89  lea     r8, [rsp+290h+Name]; lpName
0x180005c8e  mov     [rsp+290h+lpClass], r14; lpClass
0x180005c93  xor     edx, edx; dwIndex
0x180005c95  mov     [rsp+290h+phkResult], r14; lpReserved
0x180005c9a  call    cs:__imp_RegEnumKeyExW
0x180005ca0  test    eax, eax
0x180005ca2  jz      short loc_180005C53
0x180005ca4  mov     rcx, [rsp+290h+hKey]; hKey
0x180005ca9  test    rcx, rcx
0x180005cac  jz      short loc_180005CB9
0x180005cae  call    cs:__imp_RegCloseKey
0x180005cb4  mov     [rsp+290h+hKey], r14
0x180005cb9  mov     rdx, rsi; unsigned __int16 *
0x180005cbc  mov     rcx, rdi; this
0x180005cbf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180005cc4  mov     rcx, [rsp+290h+hKey]; hKey
0x180005cc9  mov     ebx, eax
0x180005ccb  test    rcx, rcx
0x180005cce  jz      short loc_180005CD6
0x180005cd0  call    cs:__imp_RegCloseKey
0x180005cd6  mov     eax, ebx
0x180005cd8  mov     rcx, [rbp+190h+var_20]
0x180005cdf  xor     rcx, rsp; StackCookie
0x180005ce2  call    __security_check_cookie
0x180005ce7  lea     r11, [rsp+290h+var_10]
0x180005cef  mov     rbx, [r11+30h]
0x180005cf3  mov     rsi, [r11+38h]
0x180005cf7  mov     rsp, r11
0x180005cfa  pop     r14
0x180005cfc  pop     rdi
0x180005cfd  pop     rbp
0x180005cfe  retn
```
