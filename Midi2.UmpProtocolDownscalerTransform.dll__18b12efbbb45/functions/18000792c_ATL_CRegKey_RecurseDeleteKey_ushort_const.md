# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000792c`
- end: `0x180007a73`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000792c`
- `0x180007dec`

## callees

- `0x180002e70`
- `0x1800060f0`
- `0x18000792c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000798d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000798d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a44`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007a0e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007a0e`

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
0x18000792c  mov     [rsp-8+arg_10], rbx
0x180007931  mov     [rsp-8+arg_18], rsi
0x180007936  push    rbp
0x180007937  push    rdi
0x180007938  push    r14
0x18000793a  lea     rbp, [rsp-180h]
0x180007942  sub     rsp, 280h
0x180007949  mov     rax, cs:__security_cookie
0x180007950  xor     rax, rsp
0x180007953  mov     [rbp+190h+var_20], rax
0x18000795a  xor     r14d, r14d
0x18000795d  lea     rax, [rsp+290h+var_230]
0x180007962  mov     rdi, rcx
0x180007965  mov     [rsp+290h+hKey], r14
0x18000796a  mov     rcx, [rcx]; hKey
0x18000796d  mov     r9d, 2001Fh; samDesired
0x180007973  xor     r8d, r8d; ulOptions
0x180007976  mov     [rsp+290h+var_240], r14
0x18000797b  mov     [rsp+290h+var_238], r14
0x180007980  mov     rsi, rdx
0x180007983  mov     [rsp+290h+var_230], r14
0x180007988  mov     [rsp+290h+phkResult], rax; phkResult
0x18000798d  call    cs:__imp_RegOpenKeyExW
0x180007993  mov     rcx, [rsp+290h+hKey]; hKey
0x180007998  mov     ebx, eax
0x18000799a  test    eax, eax
0x18000799c  jnz     loc_180007A3F
0x1800079a2  mov     ebx, r14d
0x1800079a5  test    rcx, rcx
0x1800079a8  jz      short loc_1800079B2
0x1800079aa  call    cs:__imp_RegCloseKey
0x1800079b0  mov     ebx, eax
0x1800079b2  mov     rcx, [rsp+290h+var_230]
0x1800079b7  mov     [rsp+290h+hKey], rcx
0x1800079bc  test    ebx, ebx
0x1800079be  jnz     short loc_180007A3F
0x1800079c0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800079c5  jmp     short loc_1800079E1
0x1800079c7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800079cc  lea     rcx, [rsp+290h+hKey]; this
0x1800079d1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800079d6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800079db  mov     ebx, eax
0x1800079dd  test    eax, eax
0x1800079df  jnz     short loc_180007A3F
0x1800079e1  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800079e6  mov     [rsp+290h+cchName], 100h
0x1800079ee  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800079f3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800079f8  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800079fd  lea     r8, [rsp+290h+Name]; lpName
0x180007a02  mov     [rsp+290h+lpClass], r14; lpClass
0x180007a07  xor     edx, edx; dwIndex
0x180007a09  mov     [rsp+290h+phkResult], r14; lpReserved
0x180007a0e  call    cs:__imp_RegEnumKeyExW
0x180007a14  test    eax, eax
0x180007a16  jz      short loc_1800079C7
0x180007a18  mov     rcx, [rsp+290h+hKey]; hKey
0x180007a1d  test    rcx, rcx
0x180007a20  jz      short loc_180007A2D
0x180007a22  call    cs:__imp_RegCloseKey
0x180007a28  mov     [rsp+290h+hKey], r14
0x180007a2d  mov     rdx, rsi; unsigned __int16 *
0x180007a30  mov     rcx, rdi; this
0x180007a33  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007a38  mov     rcx, [rsp+290h+hKey]; hKey
0x180007a3d  mov     ebx, eax
0x180007a3f  test    rcx, rcx
0x180007a42  jz      short loc_180007A4A
0x180007a44  call    cs:__imp_RegCloseKey
0x180007a4a  mov     eax, ebx
0x180007a4c  mov     rcx, [rbp+190h+var_20]
0x180007a53  xor     rcx, rsp; StackCookie
0x180007a56  call    __security_check_cookie
0x180007a5b  lea     r11, [rsp+290h+var_10]
0x180007a63  mov     rbx, [r11+30h]
0x180007a67  mov     rsi, [r11+38h]
0x180007a6b  mov     rsp, r11
0x180007a6e  pop     r14
0x180007a70  pop     rdi
0x180007a71  pop     rbp
0x180007a72  retn
```
