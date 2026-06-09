# ATL::CRegKey::RecurseDeleteKey(char const *)

- ea: `0x180004df8`
- end: `0x180004f36`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z`
- size: `318`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004df8`
- `0x180005408`

## callees

- `0x180003de8`
- `0x180004df8`
- `0x18000b640`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180004e53`
- `ADVAPI32!RegOpenKeyExA` at `0x180004e53`
- `ADVAPI32!RegEnumKeyExA` at `0x180004ed4`
- `ADVAPI32!RegEnumKeyExA` at `0x180004ed4`
- `ADVAPI32!RegCloseKey` at `0x180004e70`
- `ADVAPI32!RegCloseKey` at `0x180004ee8`
- `ADVAPI32!RegCloseKey` at `0x180004f0a`
- `ADVAPI32!RegCloseKey` at `0x180004e70`
- `ADVAPI32!RegCloseKey` at `0x180004ee8`
- `ADVAPI32!RegCloseKey` at `0x180004f0a`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const char *a2)
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
  CHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExA(v3, a2, 0, 0x2001Fu, &phkResult);
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
      if ( RegEnumKeyExA(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
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
0x180004df8  mov     [rsp-8+arg_10], rbx
0x180004dfd  mov     [rsp-8+arg_18], rsi
0x180004e02  push    rbp
0x180004e03  push    rdi
0x180004e04  push    r14
0x180004e06  lea     rbp, [rsp-80h]
0x180004e0b  sub     rsp, 180h
0x180004e12  mov     rax, cs:__security_cookie
0x180004e19  xor     rax, rsp
0x180004e1c  mov     [rbp+90h+var_20], rax
0x180004e20  xor     r14d, r14d
0x180004e23  lea     rax, [rsp+190h+var_130]
0x180004e28  mov     rdi, rcx
0x180004e2b  mov     [rsp+190h+hKey], r14
0x180004e30  mov     rcx, [rcx]; hKey
0x180004e33  mov     r9d, 2001Fh; samDesired
0x180004e39  xor     r8d, r8d; ulOptions
0x180004e3c  mov     [rsp+190h+var_140], r14
0x180004e41  mov     [rsp+190h+var_138], r14
0x180004e46  mov     rsi, rdx
0x180004e49  mov     [rsp+190h+var_130], r14
0x180004e4e  mov     [rsp+190h+phkResult], rax; phkResult
0x180004e53  call    cs:__imp_RegOpenKeyExA
0x180004e59  mov     rcx, [rsp+190h+hKey]; hKey
0x180004e5e  mov     ebx, eax
0x180004e60  test    eax, eax
0x180004e62  jnz     loc_180004F05
0x180004e68  mov     ebx, r14d
0x180004e6b  test    rcx, rcx
0x180004e6e  jz      short loc_180004E78
0x180004e70  call    cs:__imp_RegCloseKey
0x180004e76  mov     ebx, eax
0x180004e78  mov     rcx, [rsp+190h+var_130]
0x180004e7d  mov     [rsp+190h+hKey], rcx
0x180004e82  test    ebx, ebx
0x180004e84  jnz     short loc_180004F05
0x180004e86  mov     qword ptr [rsp+190h+ftLastWriteTime.dwLowDateTime], r14
0x180004e8b  jmp     short loc_180004EA7
0x180004e8d  lea     rdx, [rsp+190h+Name]; char *
0x180004e92  lea     rcx, [rsp+190h+hKey]; this
0x180004e97  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x180004e9c  mov     rcx, [rsp+190h+hKey]; hKey
0x180004ea1  mov     ebx, eax
0x180004ea3  test    eax, eax
0x180004ea5  jnz     short loc_180004F05
0x180004ea7  lea     rax, [rsp+190h+ftLastWriteTime]
0x180004eac  mov     [rsp+190h+cchName], 100h
0x180004eb4  mov     [rsp+190h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004eb9  lea     r9, [rsp+190h+cchName]; lpcchName
0x180004ebe  mov     [rsp+190h+lpcchClass], r14; lpcchClass
0x180004ec3  lea     r8, [rsp+190h+Name]; lpName
0x180004ec8  mov     [rsp+190h+lpClass], r14; lpClass
0x180004ecd  xor     edx, edx; dwIndex
0x180004ecf  mov     [rsp+190h+phkResult], r14; lpReserved
0x180004ed4  call    cs:__imp_RegEnumKeyExA
0x180004eda  test    eax, eax
0x180004edc  jz      short loc_180004E8D
0x180004ede  mov     rcx, [rsp+190h+hKey]; hKey
0x180004ee3  test    rcx, rcx
0x180004ee6  jz      short loc_180004EF3
0x180004ee8  call    cs:__imp_RegCloseKey
0x180004eee  mov     [rsp+190h+hKey], r14
0x180004ef3  mov     rdx, rsi; char *
0x180004ef6  mov     rcx, rdi; this
0x180004ef9  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::DeleteSubKey(char const *)
0x180004efe  mov     rcx, [rsp+190h+hKey]; hKey
0x180004f03  mov     ebx, eax
0x180004f05  test    rcx, rcx
0x180004f08  jz      short loc_180004F10
0x180004f0a  call    cs:__imp_RegCloseKey
0x180004f10  mov     eax, ebx
0x180004f12  mov     rcx, [rbp+90h+var_20]
0x180004f16  xor     rcx, rsp; StackCookie
0x180004f19  call    __security_check_cookie
0x180004f1e  lea     r11, [rsp+190h+var_10]
0x180004f26  mov     rbx, [r11+30h]
0x180004f2a  mov     rsi, [r11+38h]
0x180004f2e  mov     rsp, r11
0x180004f31  pop     r14
0x180004f33  pop     rdi
0x180004f34  pop     rbp
0x180004f35  retn
```
