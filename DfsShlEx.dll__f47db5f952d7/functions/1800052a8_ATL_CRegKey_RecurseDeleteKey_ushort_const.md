# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800052a8`
- end: `0x1800053ef`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800052a8`
- `0x180005764`

## callees

- `0x180004998`
- `0x1800052a8`
- `0x18000a9d0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000538a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000538a`
- `ADVAPI32!RegOpenKeyExW` at `0x180005309`
- `ADVAPI32!RegOpenKeyExW` at `0x180005309`
- `ADVAPI32!RegCloseKey` at `0x180005326`
- `ADVAPI32!RegCloseKey` at `0x18000539e`
- `ADVAPI32!RegCloseKey` at `0x1800053c0`
- `ADVAPI32!RegCloseKey` at `0x180005326`
- `ADVAPI32!RegCloseKey` at `0x18000539e`
- `ADVAPI32!RegCloseKey` at `0x1800053c0`

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
0x1800052a8  mov     [rsp-8+arg_10], rbx
0x1800052ad  mov     [rsp-8+arg_18], rsi
0x1800052b2  push    rbp
0x1800052b3  push    rdi
0x1800052b4  push    r14
0x1800052b6  lea     rbp, [rsp-180h]
0x1800052be  sub     rsp, 280h
0x1800052c5  mov     rax, cs:__security_cookie
0x1800052cc  xor     rax, rsp
0x1800052cf  mov     [rbp+190h+var_20], rax
0x1800052d6  xor     r14d, r14d
0x1800052d9  lea     rax, [rsp+290h+var_230]
0x1800052de  mov     rdi, rcx
0x1800052e1  mov     [rsp+290h+hKey], r14
0x1800052e6  mov     rcx, [rcx]; hKey
0x1800052e9  mov     r9d, 2001Fh; samDesired
0x1800052ef  xor     r8d, r8d; ulOptions
0x1800052f2  mov     [rsp+290h+var_240], r14
0x1800052f7  mov     [rsp+290h+var_238], r14
0x1800052fc  mov     rsi, rdx
0x1800052ff  mov     [rsp+290h+var_230], r14
0x180005304  mov     [rsp+290h+phkResult], rax; phkResult
0x180005309  call    cs:__imp_RegOpenKeyExW
0x18000530f  mov     rcx, [rsp+290h+hKey]; hKey
0x180005314  mov     ebx, eax
0x180005316  test    eax, eax
0x180005318  jnz     loc_1800053BB
0x18000531e  mov     ebx, r14d
0x180005321  test    rcx, rcx
0x180005324  jz      short loc_18000532E
0x180005326  call    cs:__imp_RegCloseKey
0x18000532c  mov     ebx, eax
0x18000532e  mov     rcx, [rsp+290h+var_230]
0x180005333  mov     [rsp+290h+hKey], rcx
0x180005338  test    ebx, ebx
0x18000533a  jnz     short loc_1800053BB
0x18000533c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180005341  jmp     short loc_18000535D
0x180005343  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005348  lea     rcx, [rsp+290h+hKey]; this
0x18000534d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005352  mov     rcx, [rsp+290h+hKey]; hKey
0x180005357  mov     ebx, eax
0x180005359  test    eax, eax
0x18000535b  jnz     short loc_1800053BB
0x18000535d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005362  mov     [rsp+290h+cchName], 100h
0x18000536a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000536f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180005374  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180005379  lea     r8, [rsp+290h+Name]; lpName
0x18000537e  mov     [rsp+290h+lpClass], r14; lpClass
0x180005383  xor     edx, edx; dwIndex
0x180005385  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000538a  call    cs:__imp_RegEnumKeyExW
0x180005390  test    eax, eax
0x180005392  jz      short loc_180005343
0x180005394  mov     rcx, [rsp+290h+hKey]; hKey
0x180005399  test    rcx, rcx
0x18000539c  jz      short loc_1800053A9
0x18000539e  call    cs:__imp_RegCloseKey
0x1800053a4  mov     [rsp+290h+hKey], r14
0x1800053a9  mov     rdx, rsi; unsigned __int16 *
0x1800053ac  mov     rcx, rdi; this
0x1800053af  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800053b4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800053b9  mov     ebx, eax
0x1800053bb  test    rcx, rcx
0x1800053be  jz      short loc_1800053C6
0x1800053c0  call    cs:__imp_RegCloseKey
0x1800053c6  mov     eax, ebx
0x1800053c8  mov     rcx, [rbp+190h+var_20]
0x1800053cf  xor     rcx, rsp; StackCookie
0x1800053d2  call    __security_check_cookie
0x1800053d7  lea     r11, [rsp+290h+var_10]
0x1800053df  mov     rbx, [r11+30h]
0x1800053e3  mov     rsi, [r11+38h]
0x1800053e7  mov     rsp, r11
0x1800053ea  pop     r14
0x1800053ec  pop     rdi
0x1800053ed  pop     rbp
0x1800053ee  retn
```
