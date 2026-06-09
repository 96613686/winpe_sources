# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800048ec`
- end: `0x180004a00`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800048ec`
- `0x180004bb4`

## callees

- `0x180001848`
- `0x18000193c`
- `0x1800048ec`
- `0x180007700`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800049aa`
- `ADVAPI32!RegCloseKey` at `0x1800049d1`
- `ADVAPI32!RegCloseKey` at `0x1800049aa`
- `ADVAPI32!RegCloseKey` at `0x1800049d1`
- `ADVAPI32!RegEnumKeyExW` at `0x180004996`
- `ADVAPI32!RegEnumKeyExW` at `0x180004996`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  int v2; // r9d
  HKEY v5; // rdx
  unsigned int i; // eax
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v2 = *((_DWORD *)this + 2);
  v11 = 0;
  hKey = 0;
  v5 = *(HKEY *)this;
  v12 = 0;
  for ( i = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v5, a2, v2 | 0x2001Fu);
        ;
        i = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, Name) )
  {
    v8 = i;
    if ( i )
      break;
    cchName = 256;
    if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      LODWORD(v11) = 0;
      v8 = ATL::CRegKey::DeleteSubKey(this, a2);
      break;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800048ec  mov     [rsp-8+arg_10], rbx
0x1800048f1  mov     [rsp-8+arg_18], rsi
0x1800048f6  push    rbp
0x1800048f7  push    rdi
0x1800048f8  push    r14
0x1800048fa  lea     rbp, [rsp-180h]
0x180004902  sub     rsp, 280h
0x180004909  mov     rax, cs:__security_cookie
0x180004910  xor     rax, rsp
0x180004913  mov     [rbp+190h+var_20], rax
0x18000491a  mov     r9d, [rcx+8]
0x18000491e  xor     r14d, r14d
0x180004921  mov     rsi, rdx
0x180004924  mov     [rsp+290h+var_248], r14
0x180004929  mov     r8, rdx; unsigned __int16 *
0x18000492c  mov     [rsp+290h+hKey], r14
0x180004931  mov     rdx, [rcx]; HKEY
0x180004934  mov     rdi, rcx
0x180004937  or      r9d, 2001Fh; unsigned int
0x18000493e  mov     [rsp+290h+var_240], r14
0x180004943  lea     rcx, [rsp+290h+hKey]; this
0x180004948  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000494d  jmp     short loc_18000495E
0x18000494f  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004954  lea     rcx, [rsp+290h+hKey]; this
0x180004959  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000495e  mov     ebx, eax
0x180004960  test    eax, eax
0x180004962  jnz     short loc_1800049C7
0x180004964  mov     rcx, [rsp+290h+hKey]; hKey
0x180004969  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000496e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004973  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004978  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000497d  lea     r8, [rsp+290h+Name]; lpName
0x180004982  mov     [rsp+290h+lpClass], r14; lpClass
0x180004987  xor     edx, edx; dwIndex
0x180004989  mov     [rsp+290h+lpReserved], r14; lpReserved
0x18000498e  mov     [rsp+290h+cchName], 100h
0x180004996  call    cs:__imp_RegEnumKeyExW
0x18000499c  test    eax, eax
0x18000499e  jz      short loc_18000494F
0x1800049a0  mov     rcx, [rsp+290h+hKey]; hKey
0x1800049a5  test    rcx, rcx
0x1800049a8  jz      short loc_1800049B5
0x1800049aa  call    cs:__imp_RegCloseKey
0x1800049b0  mov     [rsp+290h+hKey], r14
0x1800049b5  mov     rdx, rsi; unsigned __int16 *
0x1800049b8  mov     dword ptr [rsp+290h+var_248], r14d
0x1800049bd  mov     rcx, rdi; this
0x1800049c0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800049c5  mov     ebx, eax
0x1800049c7  mov     rcx, [rsp+290h+hKey]; hKey
0x1800049cc  test    rcx, rcx
0x1800049cf  jz      short loc_1800049D7
0x1800049d1  call    cs:__imp_RegCloseKey
0x1800049d7  mov     eax, ebx
0x1800049d9  mov     rcx, [rbp+190h+var_20]
0x1800049e0  xor     rcx, rsp; StackCookie
0x1800049e3  call    __security_check_cookie
0x1800049e8  lea     r11, [rsp+290h+var_10]
0x1800049f0  mov     rbx, [r11+30h]
0x1800049f4  mov     rsi, [r11+38h]
0x1800049f8  mov     rsp, r11
0x1800049fb  pop     r14
0x1800049fd  pop     rdi
0x1800049fe  pop     rbp
0x1800049ff  retn
```
