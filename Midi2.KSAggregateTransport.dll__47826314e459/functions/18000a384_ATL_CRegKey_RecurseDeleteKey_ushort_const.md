# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000a384`
- end: `0x18000a4cb`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a384`
- `0x18000a844`

## callees

- `0x180005020`
- `0x1800087d0`
- `0x18000a384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a466`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a47a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a47a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a49c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3e5`

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
0x18000a384  mov     [rsp-8+arg_10], rbx
0x18000a389  mov     [rsp-8+arg_18], rsi
0x18000a38e  push    rbp
0x18000a38f  push    rdi
0x18000a390  push    r14
0x18000a392  lea     rbp, [rsp-180h]
0x18000a39a  sub     rsp, 280h
0x18000a3a1  mov     rax, cs:__security_cookie
0x18000a3a8  xor     rax, rsp
0x18000a3ab  mov     [rbp+190h+var_20], rax
0x18000a3b2  xor     r14d, r14d
0x18000a3b5  lea     rax, [rsp+290h+var_230]
0x18000a3ba  mov     rdi, rcx
0x18000a3bd  mov     [rsp+290h+hKey], r14
0x18000a3c2  mov     rcx, [rcx]; hKey
0x18000a3c5  mov     r9d, 2001Fh; samDesired
0x18000a3cb  xor     r8d, r8d; ulOptions
0x18000a3ce  mov     [rsp+290h+var_240], r14
0x18000a3d3  mov     [rsp+290h+var_238], r14
0x18000a3d8  mov     rsi, rdx
0x18000a3db  mov     [rsp+290h+var_230], r14
0x18000a3e0  mov     [rsp+290h+phkResult], rax; phkResult
0x18000a3e5  call    cs:__imp_RegOpenKeyExW
0x18000a3eb  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a3f0  mov     ebx, eax
0x18000a3f2  test    eax, eax
0x18000a3f4  jnz     loc_18000A497
0x18000a3fa  mov     ebx, r14d
0x18000a3fd  test    rcx, rcx
0x18000a400  jz      short loc_18000A40A
0x18000a402  call    cs:__imp_RegCloseKey
0x18000a408  mov     ebx, eax
0x18000a40a  mov     rcx, [rsp+290h+var_230]
0x18000a40f  mov     [rsp+290h+hKey], rcx
0x18000a414  test    ebx, ebx
0x18000a416  jnz     short loc_18000A497
0x18000a418  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000a41d  jmp     short loc_18000A439
0x18000a41f  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a424  lea     rcx, [rsp+290h+hKey]; this
0x18000a429  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000a42e  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a433  mov     ebx, eax
0x18000a435  test    eax, eax
0x18000a437  jnz     short loc_18000A497
0x18000a439  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000a43e  mov     [rsp+290h+cchName], 100h
0x18000a446  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a44b  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000a450  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000a455  lea     r8, [rsp+290h+Name]; lpName
0x18000a45a  mov     [rsp+290h+lpClass], r14; lpClass
0x18000a45f  xor     edx, edx; dwIndex
0x18000a461  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000a466  call    cs:__imp_RegEnumKeyExW
0x18000a46c  test    eax, eax
0x18000a46e  jz      short loc_18000A41F
0x18000a470  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a475  test    rcx, rcx
0x18000a478  jz      short loc_18000A485
0x18000a47a  call    cs:__imp_RegCloseKey
0x18000a480  mov     [rsp+290h+hKey], r14
0x18000a485  mov     rdx, rsi; unsigned __int16 *
0x18000a488  mov     rcx, rdi; this
0x18000a48b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000a490  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a495  mov     ebx, eax
0x18000a497  test    rcx, rcx
0x18000a49a  jz      short loc_18000A4A2
0x18000a49c  call    cs:__imp_RegCloseKey
0x18000a4a2  mov     eax, ebx
0x18000a4a4  mov     rcx, [rbp+190h+var_20]
0x18000a4ab  xor     rcx, rsp; StackCookie
0x18000a4ae  call    __security_check_cookie
0x18000a4b3  lea     r11, [rsp+290h+var_10]
0x18000a4bb  mov     rbx, [r11+30h]
0x18000a4bf  mov     rsi, [r11+38h]
0x18000a4c3  mov     rsp, r11
0x18000a4c6  pop     r14
0x18000a4c8  pop     rdi
0x18000a4c9  pop     rbp
0x18000a4ca  retn
```
