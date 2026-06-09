# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800066bc`
- end: `0x180006803`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800066bc`
- `0x180006b7c`

## callees

- `0x180001e60`
- `0x180004e80`
- `0x1800066bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000679e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000679e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000673a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000673a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000671d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000671d`

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
0x1800066bc  mov     [rsp-8+arg_10], rbx
0x1800066c1  mov     [rsp-8+arg_18], rsi
0x1800066c6  push    rbp
0x1800066c7  push    rdi
0x1800066c8  push    r14
0x1800066ca  lea     rbp, [rsp-180h]
0x1800066d2  sub     rsp, 280h
0x1800066d9  mov     rax, cs:__security_cookie
0x1800066e0  xor     rax, rsp
0x1800066e3  mov     [rbp+190h+var_20], rax
0x1800066ea  xor     r14d, r14d
0x1800066ed  lea     rax, [rsp+290h+var_230]
0x1800066f2  mov     rdi, rcx
0x1800066f5  mov     [rsp+290h+hKey], r14
0x1800066fa  mov     rcx, [rcx]; hKey
0x1800066fd  mov     r9d, 2001Fh; samDesired
0x180006703  xor     r8d, r8d; ulOptions
0x180006706  mov     [rsp+290h+var_240], r14
0x18000670b  mov     [rsp+290h+var_238], r14
0x180006710  mov     rsi, rdx
0x180006713  mov     [rsp+290h+var_230], r14
0x180006718  mov     [rsp+290h+phkResult], rax; phkResult
0x18000671d  call    cs:__imp_RegOpenKeyExW
0x180006723  mov     rcx, [rsp+290h+hKey]; hKey
0x180006728  mov     ebx, eax
0x18000672a  test    eax, eax
0x18000672c  jnz     loc_1800067CF
0x180006732  mov     ebx, r14d
0x180006735  test    rcx, rcx
0x180006738  jz      short loc_180006742
0x18000673a  call    cs:__imp_RegCloseKey
0x180006740  mov     ebx, eax
0x180006742  mov     rcx, [rsp+290h+var_230]
0x180006747  mov     [rsp+290h+hKey], rcx
0x18000674c  test    ebx, ebx
0x18000674e  jnz     short loc_1800067CF
0x180006750  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180006755  jmp     short loc_180006771
0x180006757  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000675c  lea     rcx, [rsp+290h+hKey]; this
0x180006761  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006766  mov     rcx, [rsp+290h+hKey]; hKey
0x18000676b  mov     ebx, eax
0x18000676d  test    eax, eax
0x18000676f  jnz     short loc_1800067CF
0x180006771  lea     rax, [rsp+290h+ftLastWriteTime]
0x180006776  mov     [rsp+290h+cchName], 100h
0x18000677e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180006783  lea     r9, [rsp+290h+cchName]; lpcchName
0x180006788  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000678d  lea     r8, [rsp+290h+Name]; lpName
0x180006792  mov     [rsp+290h+lpClass], r14; lpClass
0x180006797  xor     edx, edx; dwIndex
0x180006799  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000679e  call    cs:__imp_RegEnumKeyExW
0x1800067a4  test    eax, eax
0x1800067a6  jz      short loc_180006757
0x1800067a8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800067ad  test    rcx, rcx
0x1800067b0  jz      short loc_1800067BD
0x1800067b2  call    cs:__imp_RegCloseKey
0x1800067b8  mov     [rsp+290h+hKey], r14
0x1800067bd  mov     rdx, rsi; unsigned __int16 *
0x1800067c0  mov     rcx, rdi; this
0x1800067c3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800067c8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800067cd  mov     ebx, eax
0x1800067cf  test    rcx, rcx
0x1800067d2  jz      short loc_1800067DA
0x1800067d4  call    cs:__imp_RegCloseKey
0x1800067da  mov     eax, ebx
0x1800067dc  mov     rcx, [rbp+190h+var_20]
0x1800067e3  xor     rcx, rsp; StackCookie
0x1800067e6  call    __security_check_cookie
0x1800067eb  lea     r11, [rsp+290h+var_10]
0x1800067f3  mov     rbx, [r11+30h]
0x1800067f7  mov     rsi, [r11+38h]
0x1800067fb  mov     rsp, r11
0x1800067fe  pop     r14
0x180006800  pop     rdi
0x180006801  pop     rbp
0x180006802  retn
```
