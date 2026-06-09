# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180007f6c`
- end: `0x1800080b3`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007f6c`
- `0x18000842c`

## callees

- `0x1800033d0`
- `0x180006730`
- `0x180007f6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fcd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000804e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000804e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008062`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008084`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008062`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008084`

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
0x180007f6c  mov     [rsp-8+arg_10], rbx
0x180007f71  mov     [rsp-8+arg_18], rsi
0x180007f76  push    rbp
0x180007f77  push    rdi
0x180007f78  push    r14
0x180007f7a  lea     rbp, [rsp-180h]
0x180007f82  sub     rsp, 280h
0x180007f89  mov     rax, cs:__security_cookie
0x180007f90  xor     rax, rsp
0x180007f93  mov     [rbp+190h+var_20], rax
0x180007f9a  xor     r14d, r14d
0x180007f9d  lea     rax, [rsp+290h+var_230]
0x180007fa2  mov     rdi, rcx
0x180007fa5  mov     [rsp+290h+hKey], r14
0x180007faa  mov     rcx, [rcx]; hKey
0x180007fad  mov     r9d, 2001Fh; samDesired
0x180007fb3  xor     r8d, r8d; ulOptions
0x180007fb6  mov     [rsp+290h+var_240], r14
0x180007fbb  mov     [rsp+290h+var_238], r14
0x180007fc0  mov     rsi, rdx
0x180007fc3  mov     [rsp+290h+var_230], r14
0x180007fc8  mov     [rsp+290h+phkResult], rax; phkResult
0x180007fcd  call    cs:__imp_RegOpenKeyExW
0x180007fd3  mov     rcx, [rsp+290h+hKey]; hKey
0x180007fd8  mov     ebx, eax
0x180007fda  test    eax, eax
0x180007fdc  jnz     loc_18000807F
0x180007fe2  mov     ebx, r14d
0x180007fe5  test    rcx, rcx
0x180007fe8  jz      short loc_180007FF2
0x180007fea  call    cs:__imp_RegCloseKey
0x180007ff0  mov     ebx, eax
0x180007ff2  mov     rcx, [rsp+290h+var_230]
0x180007ff7  mov     [rsp+290h+hKey], rcx
0x180007ffc  test    ebx, ebx
0x180007ffe  jnz     short loc_18000807F
0x180008000  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180008005  jmp     short loc_180008021
0x180008007  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000800c  lea     rcx, [rsp+290h+hKey]; this
0x180008011  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008016  mov     rcx, [rsp+290h+hKey]; hKey
0x18000801b  mov     ebx, eax
0x18000801d  test    eax, eax
0x18000801f  jnz     short loc_18000807F
0x180008021  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008026  mov     [rsp+290h+cchName], 100h
0x18000802e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008033  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008038  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000803d  lea     r8, [rsp+290h+Name]; lpName
0x180008042  mov     [rsp+290h+lpClass], r14; lpClass
0x180008047  xor     edx, edx; dwIndex
0x180008049  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000804e  call    cs:__imp_RegEnumKeyExW
0x180008054  test    eax, eax
0x180008056  jz      short loc_180008007
0x180008058  mov     rcx, [rsp+290h+hKey]; hKey
0x18000805d  test    rcx, rcx
0x180008060  jz      short loc_18000806D
0x180008062  call    cs:__imp_RegCloseKey
0x180008068  mov     [rsp+290h+hKey], r14
0x18000806d  mov     rdx, rsi; unsigned __int16 *
0x180008070  mov     rcx, rdi; this
0x180008073  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008078  mov     rcx, [rsp+290h+hKey]; hKey
0x18000807d  mov     ebx, eax
0x18000807f  test    rcx, rcx
0x180008082  jz      short loc_18000808A
0x180008084  call    cs:__imp_RegCloseKey
0x18000808a  mov     eax, ebx
0x18000808c  mov     rcx, [rbp+190h+var_20]
0x180008093  xor     rcx, rsp; StackCookie
0x180008096  call    __security_check_cookie
0x18000809b  lea     r11, [rsp+290h+var_10]
0x1800080a3  mov     rbx, [r11+30h]
0x1800080a7  mov     rsi, [r11+38h]
0x1800080ab  mov     rsp, r11
0x1800080ae  pop     r14
0x1800080b0  pop     rdi
0x1800080b1  pop     rbp
0x1800080b2  retn
```
