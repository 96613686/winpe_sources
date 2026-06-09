# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x140004bd8`
- end: `0x140004d1f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140004bd8`
- `0x140005098`

## callees

- `0x140003ca4`
- `0x140004bd8`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004c39`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140004cba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140004cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004cce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004cce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004cf0`

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
0x140004bd8  mov     [rsp-8+arg_10], rbx
0x140004bdd  mov     [rsp-8+arg_18], rsi
0x140004be2  push    rbp
0x140004be3  push    rdi
0x140004be4  push    r14
0x140004be6  lea     rbp, [rsp-180h]
0x140004bee  sub     rsp, 280h
0x140004bf5  mov     rax, cs:__security_cookie
0x140004bfc  xor     rax, rsp
0x140004bff  mov     [rbp+190h+var_20], rax
0x140004c06  xor     r14d, r14d
0x140004c09  lea     rax, [rsp+290h+var_230]
0x140004c0e  mov     rdi, rcx
0x140004c11  mov     [rsp+290h+hKey], r14
0x140004c16  mov     rcx, [rcx]; hKey
0x140004c19  mov     r9d, 2001Fh; samDesired
0x140004c1f  xor     r8d, r8d; ulOptions
0x140004c22  mov     [rsp+290h+var_240], r14
0x140004c27  mov     [rsp+290h+var_238], r14
0x140004c2c  mov     rsi, rdx
0x140004c2f  mov     [rsp+290h+var_230], r14
0x140004c34  mov     [rsp+290h+phkResult], rax; phkResult
0x140004c39  call    cs:__imp_RegOpenKeyExW
0x140004c3f  mov     rcx, [rsp+290h+hKey]; hKey
0x140004c44  mov     ebx, eax
0x140004c46  test    eax, eax
0x140004c48  jnz     loc_140004CEB
0x140004c4e  mov     ebx, r14d
0x140004c51  test    rcx, rcx
0x140004c54  jz      short loc_140004C5E
0x140004c56  call    cs:__imp_RegCloseKey
0x140004c5c  mov     ebx, eax
0x140004c5e  mov     rcx, [rsp+290h+var_230]
0x140004c63  mov     [rsp+290h+hKey], rcx
0x140004c68  test    ebx, ebx
0x140004c6a  jnz     short loc_140004CEB
0x140004c6c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140004c71  jmp     short loc_140004C8D
0x140004c73  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x140004c78  lea     rcx, [rsp+290h+hKey]; this
0x140004c7d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140004c82  mov     rcx, [rsp+290h+hKey]; hKey
0x140004c87  mov     ebx, eax
0x140004c89  test    eax, eax
0x140004c8b  jnz     short loc_140004CEB
0x140004c8d  lea     rax, [rsp+290h+ftLastWriteTime]
0x140004c92  mov     [rsp+290h+cchName], 100h
0x140004c9a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140004c9f  lea     r9, [rsp+290h+cchName]; lpcchName
0x140004ca4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x140004ca9  lea     r8, [rsp+290h+Name]; lpName
0x140004cae  mov     [rsp+290h+lpClass], r14; lpClass
0x140004cb3  xor     edx, edx; dwIndex
0x140004cb5  mov     [rsp+290h+phkResult], r14; lpReserved
0x140004cba  call    cs:__imp_RegEnumKeyExW
0x140004cc0  test    eax, eax
0x140004cc2  jz      short loc_140004C73
0x140004cc4  mov     rcx, [rsp+290h+hKey]; hKey
0x140004cc9  test    rcx, rcx
0x140004ccc  jz      short loc_140004CD9
0x140004cce  call    cs:__imp_RegCloseKey
0x140004cd4  mov     [rsp+290h+hKey], r14
0x140004cd9  mov     rdx, rsi; unsigned __int16 *
0x140004cdc  mov     rcx, rdi; this
0x140004cdf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140004ce4  mov     rcx, [rsp+290h+hKey]; hKey
0x140004ce9  mov     ebx, eax
0x140004ceb  test    rcx, rcx
0x140004cee  jz      short loc_140004CF6
0x140004cf0  call    cs:__imp_RegCloseKey
0x140004cf6  mov     eax, ebx
0x140004cf8  mov     rcx, [rbp+190h+var_20]
0x140004cff  xor     rcx, rsp; StackCookie
0x140004d02  call    __security_check_cookie
0x140004d07  lea     r11, [rsp+290h+var_10]
0x140004d0f  mov     rbx, [r11+30h]
0x140004d13  mov     rsi, [r11+38h]
0x140004d17  mov     rsp, r11
0x140004d1a  pop     r14
0x140004d1c  pop     rdi
0x140004d1d  pop     rbp
0x140004d1e  retn
```
