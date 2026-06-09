# ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)

- ea: `0x180013fa4`
- end: `0x180014141`
- name: `?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z`
- size: `413`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800127bc`
- `0x180013280`
- `0x1800135d8`

## callees

- `0x180008a6c`
- `0x180013fa4`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800140a2`
- `KERNEL32!LocalAlloc` at `0x1800140a2`
- `ADVAPI32!RegQueryValueExW` at `0x180014075`
- `ADVAPI32!RegQueryValueExW` at `0x1800140d5`
- `ADVAPI32!RegQueryValueExW` at `0x180014075`
- `ADVAPI32!RegQueryValueExW` at `0x1800140d5`
- `ADVAPI32!RegCloseKey` at `0x1800140e4`
- `ADVAPI32!RegCloseKey` at `0x1800140f1`
- `ADVAPI32!RegCloseKey` at `0x1800140e4`
- `ADVAPI32!RegCloseKey` at `0x1800140f1`
- `ADVAPI32!RegOpenKeyExW` at `0x180014048`
- `ADVAPI32!RegOpenKeyExW` at `0x180014048`
- `ADVAPI32!RegDeleteValueW` at `0x180014092`
- `ADVAPI32!RegDeleteValueW` at `0x180014092`
- `ADVAPI32!RegEnumKeyW` at `0x18001400b`
- `ADVAPI32!RegEnumKeyW` at `0x18001400b`
- `SHLWAPI!StrChrW` at `0x180014020`
- `SHLWAPI!StrChrW` at `0x180014020`

## pseudocode

```c
__int64 __fastcall ValueDataHelper(
        HKEY hKey,
        LPCWSTR lpValueName,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned int a5)
{
  unsigned int v10; // ebx
  DWORD i; // edi
  unsigned __int8 *v12; // rax
  HKEY v13; // rcx
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Name[16]; // [rsp+40h] [rbp-30h] BYREF

  hKeya = 0;
  cbData = 0;
  if ( a5 == 2 && !a3 )
    return 0;
  v10 = 0;
  for ( i = 0; !v10 && !RegEnumKeyW(hKey, i, Name, 0x10u); ++i )
  {
    if ( !StrChrW(Name, 0x2Eu) && !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &hKeya) )
    {
      if ( !RegQueryValueExW(hKeya, lpValueName, 0, 0, 0, &cbData) )
      {
        if ( a5 == 2 )
        {
          v12 = (unsigned __int8 *)LocalAlloc(0x40u, cbData);
          v13 = hKeya;
          *a3 = v12;
          if ( !v12 )
          {
            RegCloseKey(v13);
            MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
            return 0;
          }
          *a4 = cbData;
          RegQueryValueExW(v13, lpValueName, 0, 0, *a3, &cbData);
        }
        else if ( a5 == 4 )
        {
          RegDeleteValueW(hKeya, lpValueName);
        }
        v10 = 1;
      }
      RegCloseKey(hKeya);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180013fa4  push    rbp
0x180013fa6  push    rbx
0x180013fa7  push    rdi
0x180013fa8  push    r12
0x180013faa  push    r13
0x180013fac  push    r14
0x180013fae  push    r15
0x180013fb0  mov     rbp, rsp
0x180013fb3  sub     rsp, 70h
0x180013fb7  mov     rax, cs:__security_cookie
0x180013fbe  xor     rax, rsp
0x180013fc1  mov     [rbp+var_10], rax
0x180013fc5  cmp     [rbp+arg_20], 2
0x180013fc9  mov     r13, r9
0x180013fcc  mov     r14, r8
0x180013fcf  mov     [rbp+hKey], 0
0x180013fd7  mov     r15, rdx
0x180013fda  mov     [rbp+cbData], 0
0x180013fe1  mov     r12, rcx
0x180013fe4  jnz     short loc_180013FF2
0x180013fe6  test    r8, r8
0x180013fe9  jnz     short loc_180013FF2
0x180013feb  xor     eax, eax
0x180013fed  jmp     loc_180014125
0x180013ff2  xor     ebx, ebx
0x180013ff4  xor     edi, edi
0x180013ff6  test    ebx, ebx
0x180013ff8  jnz     loc_180014123
0x180013ffe  lea     r9d, [rbx+10h]; cchName
0x180014002  mov     edx, edi; dwIndex
0x180014004  lea     r8, [rbp+Name]; lpName
0x180014008  mov     rcx, r12; hKey
0x18001400b  call    cs:__imp_RegEnumKeyW
0x180014011  test    eax, eax
0x180014013  jnz     loc_180014123
0x180014019  lea     edx, [rbx+2Eh]; wMatch
0x18001401c  lea     rcx, [rbp+Name]; pszStart
0x180014020  call    cs:__imp_StrChrW
0x180014026  test    rax, rax
0x180014029  jnz     loc_1800140EA
0x18001402f  lea     rax, [rbp+hKey]
0x180014033  mov     r9d, 2001Fh; samDesired
0x180014039  xor     r8d, r8d; ulOptions
0x18001403c  mov     [rsp+70h+phkResult], rax; phkResult
0x180014041  lea     rdx, [rbp+Name]; lpSubKey
0x180014045  mov     rcx, r12; hKey
0x180014048  call    cs:__imp_RegOpenKeyExW
0x18001404e  test    eax, eax
0x180014050  jnz     loc_1800140EA
0x180014056  mov     rcx, [rbp+hKey]; hKey
0x18001405a  lea     rax, [rbp+cbData]
0x18001405e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180014063  xor     r9d, r9d; lpType
0x180014066  xor     r8d, r8d; lpReserved
0x180014069  mov     [rsp+70h+phkResult], 0; lpData
0x180014072  mov     rdx, r15; lpValueName
0x180014075  call    cs:__imp_RegQueryValueExW
0x18001407b  test    eax, eax
0x18001407d  jnz     short loc_1800140E0
0x18001407f  cmp     [rbp+arg_20], 2
0x180014083  jz      short loc_18001409A
0x180014085  cmp     [rbp+arg_20], 4
0x180014089  jnz     short loc_1800140DB
0x18001408b  mov     rcx, [rbp+hKey]; hKey
0x18001408f  mov     rdx, r15; lpValueName
0x180014092  call    cs:__imp_RegDeleteValueW
0x180014098  jmp     short loc_1800140DB
0x18001409a  mov     edx, [rbp+cbData]; uBytes
0x18001409d  mov     ecx, 40h ; '@'; uFlags
0x1800140a2  call    cs:__imp_LocalAlloc
0x1800140a8  mov     rcx, [rbp+hKey]; hKey
0x1800140ac  mov     [r14], rax
0x1800140af  test    rax, rax
0x1800140b2  jz      short loc_1800140F1
0x1800140b4  mov     eax, [rbp+cbData]
0x1800140b7  xor     r9d, r9d; lpType
0x1800140ba  mov     [r13+0], eax
0x1800140be  xor     r8d, r8d; lpReserved
0x1800140c1  lea     rax, [rbp+cbData]
0x1800140c5  mov     rdx, r15; lpValueName
0x1800140c8  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800140cd  mov     rax, [r14]
0x1800140d0  mov     [rsp+70h+phkResult], rax; lpData
0x1800140d5  call    cs:__imp_RegQueryValueExW
0x1800140db  mov     ebx, 1
0x1800140e0  mov     rcx, [rbp+hKey]; hKey
0x1800140e4  call    cs:__imp_RegCloseKey
0x1800140ea  inc     edi
0x1800140ec  jmp     loc_180013FF6
0x1800140f1  call    cs:__imp_RegCloseKey
0x1800140f7  mov     rcx, cs:hWnd; hWnd
0x1800140fe  xor     r9d, r9d; unsigned __int16 *
0x180014101  xor     r8d, r8d; unsigned __int16 *
0x180014104  mov     dword ptr [rsp+70h+lpcbData], 0; unsigned int
0x18001410c  mov     edx, 44Eh; uID
0x180014111  mov     dword ptr [rsp+70h+phkResult], 10h; unsigned int
0x180014119  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18001411e  jmp     loc_180013FEB
0x180014123  mov     eax, ebx
0x180014125  mov     rcx, [rbp+var_10]
0x180014129  xor     rcx, rsp; StackCookie
0x18001412c  call    __security_check_cookie
0x180014131  add     rsp, 70h
0x180014135  pop     r15
0x180014137  pop     r14
0x180014139  pop     r13
0x18001413b  pop     r12
0x18001413d  pop     rdi
0x18001413e  pop     rbx
0x18001413f  pop     rbp
0x180014140  retn
```
