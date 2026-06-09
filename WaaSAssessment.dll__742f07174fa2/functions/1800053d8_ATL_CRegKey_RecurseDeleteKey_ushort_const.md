# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800053d8`
- end: `0x18000551f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800053d8`
- `0x18000589c`

## callees

- `0x180004be8`
- `0x1800053d8`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800054ba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800054ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005439`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005439`

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
0x1800053d8  mov     [rsp-8+arg_10], rbx
0x1800053dd  mov     [rsp-8+arg_18], rsi
0x1800053e2  push    rbp
0x1800053e3  push    rdi
0x1800053e4  push    r14
0x1800053e6  lea     rbp, [rsp-180h]
0x1800053ee  sub     rsp, 280h
0x1800053f5  mov     rax, cs:__security_cookie
0x1800053fc  xor     rax, rsp
0x1800053ff  mov     [rbp+190h+var_20], rax
0x180005406  xor     r14d, r14d
0x180005409  lea     rax, [rsp+290h+var_230]
0x18000540e  mov     rdi, rcx
0x180005411  mov     [rsp+290h+hKey], r14
0x180005416  mov     rcx, [rcx]; hKey
0x180005419  mov     r9d, 2001Fh; samDesired
0x18000541f  xor     r8d, r8d; ulOptions
0x180005422  mov     [rsp+290h+var_240], r14
0x180005427  mov     [rsp+290h+var_238], r14
0x18000542c  mov     rsi, rdx
0x18000542f  mov     [rsp+290h+var_230], r14
0x180005434  mov     [rsp+290h+phkResult], rax; phkResult
0x180005439  call    cs:__imp_RegOpenKeyExW
0x18000543f  mov     rcx, [rsp+290h+hKey]; hKey
0x180005444  mov     ebx, eax
0x180005446  test    eax, eax
0x180005448  jnz     loc_1800054EB
0x18000544e  mov     ebx, r14d
0x180005451  test    rcx, rcx
0x180005454  jz      short loc_18000545E
0x180005456  call    cs:__imp_RegCloseKey
0x18000545c  mov     ebx, eax
0x18000545e  mov     rcx, [rsp+290h+var_230]
0x180005463  mov     [rsp+290h+hKey], rcx
0x180005468  test    ebx, ebx
0x18000546a  jnz     short loc_1800054EB
0x18000546c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180005471  jmp     short loc_18000548D
0x180005473  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005478  lea     rcx, [rsp+290h+hKey]; this
0x18000547d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005482  mov     rcx, [rsp+290h+hKey]; hKey
0x180005487  mov     ebx, eax
0x180005489  test    eax, eax
0x18000548b  jnz     short loc_1800054EB
0x18000548d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005492  mov     [rsp+290h+cchName], 100h
0x18000549a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000549f  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800054a4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800054a9  lea     r8, [rsp+290h+Name]; lpName
0x1800054ae  mov     [rsp+290h+lpClass], r14; lpClass
0x1800054b3  xor     edx, edx; dwIndex
0x1800054b5  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800054ba  call    cs:__imp_RegEnumKeyExW
0x1800054c0  test    eax, eax
0x1800054c2  jz      short loc_180005473
0x1800054c4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800054c9  test    rcx, rcx
0x1800054cc  jz      short loc_1800054D9
0x1800054ce  call    cs:__imp_RegCloseKey
0x1800054d4  mov     [rsp+290h+hKey], r14
0x1800054d9  mov     rdx, rsi; unsigned __int16 *
0x1800054dc  mov     rcx, rdi; this
0x1800054df  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800054e4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800054e9  mov     ebx, eax
0x1800054eb  test    rcx, rcx
0x1800054ee  jz      short loc_1800054F6
0x1800054f0  call    cs:__imp_RegCloseKey
0x1800054f6  mov     eax, ebx
0x1800054f8  mov     rcx, [rbp+190h+var_20]
0x1800054ff  xor     rcx, rsp; StackCookie
0x180005502  call    __security_check_cookie
0x180005507  lea     r11, [rsp+290h+var_10]
0x18000550f  mov     rbx, [r11+30h]
0x180005513  mov     rsi, [r11+38h]
0x180005517  mov     rsp, r11
0x18000551a  pop     r14
0x18000551c  pop     rdi
0x18000551d  pop     rbp
0x18000551e  retn
```
