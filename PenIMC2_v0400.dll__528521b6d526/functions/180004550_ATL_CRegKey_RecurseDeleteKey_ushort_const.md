# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004550`
- end: `0x1800046b9`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `361`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004550`
- `0x1800049b8`

## callees

- `0x180004550`
- `0x1800046e4`
- `0x18000cdb0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800045d2`
- `ADVAPI32!RegCloseKey` at `0x18000465a`
- `ADVAPI32!RegCloseKey` at `0x180004681`
- `ADVAPI32!RegCloseKey` at `0x1800045d2`
- `ADVAPI32!RegCloseKey` at `0x18000465a`
- `ADVAPI32!RegCloseKey` at `0x180004681`
- `ADVAPI32!RegEnumKeyExW` at `0x180004646`
- `ADVAPI32!RegEnumKeyExW` at `0x180004646`
- `ADVAPI32!RegOpenKeyExW` at `0x1800045b5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800045b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  REGSAM v4; // edi
  unsigned int v5; // ebx
  HKEY v6; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h]
  __int64 v11; // [rsp+58h] [rbp-A8h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v10 = 0;
  v11 = 0;
  v4 = *((_DWORD *)this + 2) | 0x2001F;
  phkResult = 0;
  v5 = RegOpenKeyExW(*(HKEY *)this, a2, 0, v4, &phkResult);
  if ( !v5 )
  {
    v6 = phkResult;
    hKey = phkResult;
    v10 = v4 & 0x300;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v5 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, Name);
      if ( v5 )
        goto LABEL_9;
      v6 = hKey;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v10 = 0;
    v5 = ATL::CRegKey::DeleteSubKey(this, a2);
  }
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180004550  mov     [rsp-8+arg_10], rbx
0x180004555  push    rbp
0x180004556  push    rsi
0x180004557  push    rdi
0x180004558  push    r14
0x18000455a  push    r15
0x18000455c  lea     rbp, [rsp-180h]
0x180004564  sub     rsp, 280h
0x18000456b  mov     rax, cs:__security_cookie
0x180004572  xor     rax, rsp
0x180004575  mov     [rbp+1A0h+var_30], rax
0x18000457c  mov     r14, rdx
0x18000457f  mov     rsi, rcx
0x180004582  xor     r15d, r15d
0x180004585  mov     [rsp+2A0h+hKey], r15
0x18000458a  mov     [rsp+2A0h+var_250], r15d
0x18000458f  mov     [rsp+2A0h+var_248], r15
0x180004594  mov     edi, [rcx+8]
0x180004597  or      edi, 2001Fh
0x18000459d  mov     [rsp+2A0h+var_240], r15
0x1800045a2  lea     rax, [rsp+2A0h+var_240]
0x1800045a7  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800045ac  mov     r9d, edi; samDesired
0x1800045af  xor     r8d, r8d; ulOptions
0x1800045b2  mov     rcx, [rcx]; hKey
0x1800045b5  call    cs:__imp_RegOpenKeyExW
0x1800045bb  mov     ebx, eax
0x1800045bd  test    eax, eax
0x1800045bf  jnz     loc_180004677
0x1800045c5  mov     ebx, r15d
0x1800045c8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800045cd  test    rcx, rcx
0x1800045d0  jz      short loc_1800045DF
0x1800045d2  call    cs:__imp_RegCloseKey
0x1800045d8  mov     ebx, eax
0x1800045da  mov     [rsp+2A0h+hKey], r15
0x1800045df  mov     [rsp+2A0h+var_250], r15d
0x1800045e4  mov     rcx, [rsp+2A0h+var_240]
0x1800045e9  mov     [rsp+2A0h+hKey], rcx
0x1800045ee  and     edi, 300h
0x1800045f4  mov     [rsp+2A0h+var_250], edi
0x1800045f8  test    ebx, ebx
0x1800045fa  jnz     short loc_180004677
0x1800045fc  mov     edi, 100h
0x180004601  jmp     short loc_18000461D
0x180004603  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180004608  lea     rcx, [rsp+2A0h+hKey]; this
0x18000460d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z
0x180004612  mov     ebx, eax
0x180004614  test    eax, eax
0x180004616  jnz     short loc_180004677
0x180004618  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000461d  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x180004622  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004627  mov     [rsp+2A0h+lpcchClass], r15; lpcchClass
0x18000462c  mov     [rsp+2A0h+lpClass], r15; lpClass
0x180004631  mov     [rsp+2A0h+phkResult], r15; lpReserved
0x180004636  mov     [rsp+2A0h+cchName], edi
0x18000463a  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000463f  lea     r8, [rsp+2A0h+Name]; lpName
0x180004644  xor     edx, edx; dwIndex
0x180004646  call    cs:__imp_RegEnumKeyExW
0x18000464c  test    eax, eax
0x18000464e  jz      short loc_180004603
0x180004650  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180004655  test    rcx, rcx
0x180004658  jz      short loc_180004665
0x18000465a  call    cs:__imp_RegCloseKey
0x180004660  mov     [rsp+2A0h+hKey], r15
0x180004665  mov     [rsp+2A0h+var_250], r15d
0x18000466a  mov     rdx, r14; unsigned __int16 *
0x18000466d  mov     rcx, rsi; this
0x180004670  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z
0x180004675  mov     ebx, eax
0x180004677  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000467c  test    rcx, rcx
0x18000467f  jz      short loc_18000468C
0x180004681  call    cs:__imp_RegCloseKey
0x180004687  mov     [rsp+2A0h+hKey], r15
0x18000468c  mov     [rsp+2A0h+var_250], r15d
0x180004691  mov     eax, ebx
0x180004693  mov     rcx, [rbp+1A0h+var_30]
0x18000469a  xor     rcx, rsp; StackCookie
0x18000469d  call    __security_check_cookie
0x1800046a2  mov     rbx, [rsp+2A0h+arg_10]
0x1800046aa  add     rsp, 280h
0x1800046b1  pop     r15
0x1800046b3  pop     r14
0x1800046b5  pop     rdi
0x1800046b6  pop     rsi
0x1800046b7  pop     rbp
0x1800046b8  retn
```
