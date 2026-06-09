# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180020f48`
- end: `0x18002108f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020f48`
- `0x18002140c`

## callees

- `0x1800018f0`
- `0x180020698`
- `0x180020f48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002102a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002102a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002103e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002103e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021060`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020fa9`

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
0x180020f48  mov     [rsp-8+arg_10], rbx
0x180020f4d  mov     [rsp-8+arg_18], rsi
0x180020f52  push    rbp
0x180020f53  push    rdi
0x180020f54  push    r14
0x180020f56  lea     rbp, [rsp-180h]
0x180020f5e  sub     rsp, 280h
0x180020f65  mov     rax, cs:__security_cookie
0x180020f6c  xor     rax, rsp
0x180020f6f  mov     [rbp+190h+var_20], rax
0x180020f76  xor     r14d, r14d
0x180020f79  lea     rax, [rsp+290h+var_230]
0x180020f7e  mov     rdi, rcx
0x180020f81  mov     [rsp+290h+hKey], r14
0x180020f86  mov     rcx, [rcx]; hKey
0x180020f89  mov     r9d, 2001Fh; samDesired
0x180020f8f  xor     r8d, r8d; ulOptions
0x180020f92  mov     [rsp+290h+var_240], r14
0x180020f97  mov     [rsp+290h+var_238], r14
0x180020f9c  mov     rsi, rdx
0x180020f9f  mov     [rsp+290h+var_230], r14
0x180020fa4  mov     [rsp+290h+phkResult], rax; phkResult
0x180020fa9  call    cs:__imp_RegOpenKeyExW
0x180020faf  mov     rcx, [rsp+290h+hKey]; hKey
0x180020fb4  mov     ebx, eax
0x180020fb6  test    eax, eax
0x180020fb8  jnz     loc_18002105B
0x180020fbe  mov     ebx, r14d
0x180020fc1  test    rcx, rcx
0x180020fc4  jz      short loc_180020FCE
0x180020fc6  call    cs:__imp_RegCloseKey
0x180020fcc  mov     ebx, eax
0x180020fce  mov     rcx, [rsp+290h+var_230]
0x180020fd3  mov     [rsp+290h+hKey], rcx
0x180020fd8  test    ebx, ebx
0x180020fda  jnz     short loc_18002105B
0x180020fdc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180020fe1  jmp     short loc_180020FFD
0x180020fe3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180020fe8  lea     rcx, [rsp+290h+hKey]; this
0x180020fed  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180020ff2  mov     rcx, [rsp+290h+hKey]; hKey
0x180020ff7  mov     ebx, eax
0x180020ff9  test    eax, eax
0x180020ffb  jnz     short loc_18002105B
0x180020ffd  lea     rax, [rsp+290h+ftLastWriteTime]
0x180021002  mov     [rsp+290h+cchName], 100h
0x18002100a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002100f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180021014  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180021019  lea     r8, [rsp+290h+Name]; lpName
0x18002101e  mov     [rsp+290h+lpClass], r14; lpClass
0x180021023  xor     edx, edx; dwIndex
0x180021025  mov     [rsp+290h+phkResult], r14; lpReserved
0x18002102a  call    cs:__imp_RegEnumKeyExW
0x180021030  test    eax, eax
0x180021032  jz      short loc_180020FE3
0x180021034  mov     rcx, [rsp+290h+hKey]; hKey
0x180021039  test    rcx, rcx
0x18002103c  jz      short loc_180021049
0x18002103e  call    cs:__imp_RegCloseKey
0x180021044  mov     [rsp+290h+hKey], r14
0x180021049  mov     rdx, rsi; unsigned __int16 *
0x18002104c  mov     rcx, rdi; this
0x18002104f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180021054  mov     rcx, [rsp+290h+hKey]; hKey
0x180021059  mov     ebx, eax
0x18002105b  test    rcx, rcx
0x18002105e  jz      short loc_180021066
0x180021060  call    cs:__imp_RegCloseKey
0x180021066  mov     eax, ebx
0x180021068  mov     rcx, [rbp+190h+var_20]
0x18002106f  xor     rcx, rsp; StackCookie
0x180021072  call    __security_check_cookie
0x180021077  lea     r11, [rsp+290h+var_10]
0x18002107f  mov     rbx, [r11+30h]
0x180021083  mov     rsi, [r11+38h]
0x180021087  mov     rsp, r11
0x18002108a  pop     r14
0x18002108c  pop     rdi
0x18002108d  pop     rbp
0x18002108e  retn
```
