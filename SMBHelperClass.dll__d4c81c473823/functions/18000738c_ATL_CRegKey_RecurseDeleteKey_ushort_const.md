# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000738c`
- end: `0x1800074d3`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000738c`
- `0x18000784c`

## callees

- `0x180004d78`
- `0x18000738c`
- `0x18000fc30`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800073ed`
- `ADVAPI32!RegOpenKeyExW` at `0x1800073ed`
- `ADVAPI32!RegEnumKeyExW` at `0x18000746e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000746e`
- `ADVAPI32!RegCloseKey` at `0x18000740a`
- `ADVAPI32!RegCloseKey` at `0x180007482`
- `ADVAPI32!RegCloseKey` at `0x1800074a4`
- `ADVAPI32!RegCloseKey` at `0x18000740a`
- `ADVAPI32!RegCloseKey` at `0x180007482`
- `ADVAPI32!RegCloseKey` at `0x1800074a4`

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
0x18000738c  mov     [rsp-8+arg_10], rbx
0x180007391  mov     [rsp-8+arg_18], rsi
0x180007396  push    rbp
0x180007397  push    rdi
0x180007398  push    r14
0x18000739a  lea     rbp, [rsp-180h]
0x1800073a2  sub     rsp, 280h
0x1800073a9  mov     rax, cs:__security_cookie
0x1800073b0  xor     rax, rsp
0x1800073b3  mov     [rbp+190h+var_20], rax
0x1800073ba  xor     r14d, r14d
0x1800073bd  lea     rax, [rsp+290h+var_230]
0x1800073c2  mov     rdi, rcx
0x1800073c5  mov     [rsp+290h+hKey], r14
0x1800073ca  mov     rcx, [rcx]; hKey
0x1800073cd  mov     r9d, 2001Fh; samDesired
0x1800073d3  xor     r8d, r8d; ulOptions
0x1800073d6  mov     [rsp+290h+var_240], r14
0x1800073db  mov     [rsp+290h+var_238], r14
0x1800073e0  mov     rsi, rdx
0x1800073e3  mov     [rsp+290h+var_230], r14
0x1800073e8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800073ed  call    cs:__imp_RegOpenKeyExW
0x1800073f3  mov     rcx, [rsp+290h+hKey]; hKey
0x1800073f8  mov     ebx, eax
0x1800073fa  test    eax, eax
0x1800073fc  jnz     loc_18000749F
0x180007402  mov     ebx, r14d
0x180007405  test    rcx, rcx
0x180007408  jz      short loc_180007412
0x18000740a  call    cs:__imp_RegCloseKey
0x180007410  mov     ebx, eax
0x180007412  mov     rcx, [rsp+290h+var_230]
0x180007417  mov     [rsp+290h+hKey], rcx
0x18000741c  test    ebx, ebx
0x18000741e  jnz     short loc_18000749F
0x180007420  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180007425  jmp     short loc_180007441
0x180007427  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000742c  lea     rcx, [rsp+290h+hKey]; this
0x180007431  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007436  mov     rcx, [rsp+290h+hKey]; hKey
0x18000743b  mov     ebx, eax
0x18000743d  test    eax, eax
0x18000743f  jnz     short loc_18000749F
0x180007441  lea     rax, [rsp+290h+ftLastWriteTime]
0x180007446  mov     [rsp+290h+cchName], 100h
0x18000744e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007453  lea     r9, [rsp+290h+cchName]; lpcchName
0x180007458  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000745d  lea     r8, [rsp+290h+Name]; lpName
0x180007462  mov     [rsp+290h+lpClass], r14; lpClass
0x180007467  xor     edx, edx; dwIndex
0x180007469  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000746e  call    cs:__imp_RegEnumKeyExW
0x180007474  test    eax, eax
0x180007476  jz      short loc_180007427
0x180007478  mov     rcx, [rsp+290h+hKey]; hKey
0x18000747d  test    rcx, rcx
0x180007480  jz      short loc_18000748D
0x180007482  call    cs:__imp_RegCloseKey
0x180007488  mov     [rsp+290h+hKey], r14
0x18000748d  mov     rdx, rsi; unsigned __int16 *
0x180007490  mov     rcx, rdi; this
0x180007493  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007498  mov     rcx, [rsp+290h+hKey]; hKey
0x18000749d  mov     ebx, eax
0x18000749f  test    rcx, rcx
0x1800074a2  jz      short loc_1800074AA
0x1800074a4  call    cs:__imp_RegCloseKey
0x1800074aa  mov     eax, ebx
0x1800074ac  mov     rcx, [rbp+190h+var_20]
0x1800074b3  xor     rcx, rsp; StackCookie
0x1800074b6  call    __security_check_cookie
0x1800074bb  lea     r11, [rsp+290h+var_10]
0x1800074c3  mov     rbx, [r11+30h]
0x1800074c7  mov     rsi, [r11+38h]
0x1800074cb  mov     rsp, r11
0x1800074ce  pop     r14
0x1800074d0  pop     rdi
0x1800074d1  pop     rbp
0x1800074d2  retn
```
