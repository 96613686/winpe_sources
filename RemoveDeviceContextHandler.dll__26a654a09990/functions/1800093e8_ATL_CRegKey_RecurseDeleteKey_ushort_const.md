# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800093e8`
- end: `0x18000952f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800093e8`
- `0x180009884`

## callees

- `0x180007948`
- `0x1800093e8`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009500`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800094ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800094ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009449`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009449`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
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
0x1800093e8  mov     [rsp-8+arg_10], rbx
0x1800093ed  mov     [rsp-8+arg_18], rsi
0x1800093f2  push    rbp
0x1800093f3  push    rdi
0x1800093f4  push    r14
0x1800093f6  lea     rbp, [rsp-180h]
0x1800093fe  sub     rsp, 280h
0x180009405  mov     rax, cs:__security_cookie
0x18000940c  xor     rax, rsp
0x18000940f  mov     [rbp+190h+var_20], rax
0x180009416  xor     r14d, r14d
0x180009419  lea     rax, [rsp+290h+var_230]
0x18000941e  mov     rdi, rcx
0x180009421  mov     [rsp+290h+hKey], r14
0x180009426  mov     rcx, [rcx]; hKey
0x180009429  mov     r9d, 2001Fh; samDesired
0x18000942f  xor     r8d, r8d; ulOptions
0x180009432  mov     [rsp+290h+var_240], r14
0x180009437  mov     [rsp+290h+var_238], r14
0x18000943c  mov     rsi, rdx
0x18000943f  mov     [rsp+290h+var_230], r14
0x180009444  mov     [rsp+290h+phkResult], rax; phkResult
0x180009449  call    cs:__imp_RegOpenKeyExW
0x18000944f  mov     rcx, [rsp+290h+hKey]; hKey
0x180009454  mov     ebx, eax
0x180009456  test    eax, eax
0x180009458  jnz     loc_1800094FB
0x18000945e  mov     ebx, r14d
0x180009461  test    rcx, rcx
0x180009464  jz      short loc_18000946E
0x180009466  call    cs:__imp_RegCloseKey
0x18000946c  mov     ebx, eax
0x18000946e  mov     rcx, [rsp+290h+var_230]
0x180009473  mov     [rsp+290h+hKey], rcx
0x180009478  test    ebx, ebx
0x18000947a  jnz     short loc_1800094FB
0x18000947c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180009481  jmp     short loc_18000949D
0x180009483  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180009488  lea     rcx, [rsp+290h+hKey]; this
0x18000948d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180009492  mov     rcx, [rsp+290h+hKey]; hKey
0x180009497  mov     ebx, eax
0x180009499  test    eax, eax
0x18000949b  jnz     short loc_1800094FB
0x18000949d  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800094a2  mov     [rsp+290h+cchName], 100h
0x1800094aa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800094af  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800094b4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800094b9  lea     r8, [rsp+290h+Name]; lpName
0x1800094be  mov     [rsp+290h+lpClass], r14; lpClass
0x1800094c3  xor     edx, edx; dwIndex
0x1800094c5  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800094ca  call    cs:__imp_RegEnumKeyExW
0x1800094d0  test    eax, eax
0x1800094d2  jz      short loc_180009483
0x1800094d4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800094d9  test    rcx, rcx
0x1800094dc  jz      short loc_1800094E9
0x1800094de  call    cs:__imp_RegCloseKey
0x1800094e4  mov     [rsp+290h+hKey], r14
0x1800094e9  mov     rdx, rsi; unsigned __int16 *
0x1800094ec  mov     rcx, rdi; this
0x1800094ef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800094f4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800094f9  mov     ebx, eax
0x1800094fb  test    rcx, rcx
0x1800094fe  jz      short loc_180009506
0x180009500  call    cs:__imp_RegCloseKey
0x180009506  mov     eax, ebx
0x180009508  mov     rcx, [rbp+190h+var_20]
0x18000950f  xor     rcx, rsp; StackCookie
0x180009512  call    __security_check_cookie
0x180009517  lea     r11, [rsp+290h+var_10]
0x18000951f  mov     rbx, [r11+30h]
0x180009523  mov     rsi, [r11+38h]
0x180009527  mov     rsp, r11
0x18000952a  pop     r14
0x18000952c  pop     rdi
0x18000952d  pop     rbp
0x18000952e  retn
```
