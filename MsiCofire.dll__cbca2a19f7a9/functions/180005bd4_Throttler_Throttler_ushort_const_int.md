# Throttler::Throttler(ushort const *,int)

- ea: `0x180005bd4`
- end: `0x180005d01`
- name: `??0Throttler@@QEAA@PEBGH@Z`
- size: `301`
- prototype: `Throttler *__fastcall(Throttler *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800038cc`
- `0x180003ac8`

## callees

- `0x180005bd4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180005c78`
- `ADVAPI32!RegQueryValueExW` at `0x180005ca8`
- `ADVAPI32!RegQueryValueExW` at `0x180005cd8`
- `ADVAPI32!RegQueryValueExW` at `0x180005c78`
- `ADVAPI32!RegQueryValueExW` at `0x180005ca8`
- `ADVAPI32!RegQueryValueExW` at `0x180005cd8`
- `ADVAPI32!RegOpenKeyExW` at `0x180005c3f`
- `ADVAPI32!RegOpenKeyExW` at `0x180005c3f`
- `ADVAPI32!RegCloseKey` at `0x180005ce7`
- `ADVAPI32!RegCloseKey` at `0x180005ce7`

## pseudocode

```c
Throttler *__fastcall Throttler::Throttler(Throttler *this, const unsigned __int16 *a2, int a3)
{
  BYTE *v3; // rdi
  BYTE *v4; // r14
  BYTE *v5; // rsi
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF

  *((_DWORD *)this + 5) = a3;
  *(_QWORD *)this = a2;
  v3 = (BYTE *)this + 16;
  *((_DWORD *)this + 4) = 0;
  v4 = (BYTE *)this + 12;
  *((_DWORD *)this + 3) = 0;
  v5 = (BYTE *)this + 8;
  *((_DWORD *)this + 2) = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW((HKEY)(-(__int64)(a3 != 0) - 2147483646), a2, 0, 0x20019u, &hKey) )
      {
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"SameIdMax", 0, &Type, v5, &cbData)
          && Type == 4
          && !RegQueryValueExW(hKey, L"AnyIdMax", 0, &Type, v4, &cbData)
          && Type == 4 )
        {
          RegQueryValueExW(hKey, L"TimeWindowMinutes", 0, &Type, v3, &cbData);
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180005bd4  mov     [rsp-28h+arg_18], rbx
0x180005bd9  push    rbp
0x180005bda  push    rsi
0x180005bdb  push    rdi
0x180005bdc  push    r14
0x180005bde  push    r15
0x180005be0  mov     rbp, rsp
0x180005be3  sub     rsp, 30h
0x180005be7  xor     r15d, r15d
0x180005bea  mov     [rcx+14h], r8d
0x180005bee  mov     [rcx], rdx
0x180005bf1  lea     rdi, [rcx+10h]
0x180005bf5  mov     [rdi], r15d
0x180005bf8  lea     r14, [rcx+0Ch]
0x180005bfc  mov     [r14], r15d
0x180005bff  lea     rsi, [rcx+8]
0x180005c03  mov     [rsi], r15d
0x180005c06  mov     rbx, rcx
0x180005c09  test    rdx, rdx
0x180005c0c  jz      loc_180005CED
0x180005c12  cmp     [rdx], r15w
0x180005c16  jz      loc_180005CED
0x180005c1c  neg     r8d
0x180005c1f  mov     [rbp+hKey], r15
0x180005c23  lea     rax, [rbp+hKey]
0x180005c27  mov     r9d, 20019h; samDesired
0x180005c2d  sbb     rcx, rcx
0x180005c30  mov     [rsp+30h+phkResult], rax; phkResult
0x180005c35  add     rcx, 0FFFFFFFF80000002h; hKey
0x180005c3c  xor     r8d, r8d; ulOptions
0x180005c3f  call    cs:__imp_RegOpenKeyExW
0x180005c45  test    eax, eax
0x180005c47  jnz     loc_180005CED
0x180005c4d  mov     rcx, [rbp+hKey]; hKey
0x180005c51  lea     rax, [rbp+cbData]
0x180005c55  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180005c5a  lea     r9, [rbp+Type]; lpType
0x180005c5e  xor     r8d, r8d; lpReserved
0x180005c61  mov     [rsp+30h+phkResult], rsi; lpData
0x180005c66  lea     rdx, aSameidmax; "SameIdMax"
0x180005c6d  mov     [rbp+Type], r15d
0x180005c71  mov     [rbp+cbData], 4
0x180005c78  call    cs:__imp_RegQueryValueExW
0x180005c7e  test    eax, eax
0x180005c80  jnz     short loc_180005CDE
0x180005c82  cmp     [rbp+Type], 4
0x180005c86  jnz     short loc_180005CDE
0x180005c88  mov     rcx, [rbp+hKey]; hKey
0x180005c8c  lea     rax, [rbp+cbData]
0x180005c90  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180005c95  lea     r9, [rbp+Type]; lpType
0x180005c99  xor     r8d, r8d; lpReserved
0x180005c9c  mov     [rsp+30h+phkResult], r14; lpData
0x180005ca1  lea     rdx, aAnyidmax; "AnyIdMax"
0x180005ca8  call    cs:__imp_RegQueryValueExW
0x180005cae  test    eax, eax
0x180005cb0  jnz     short loc_180005CDE
0x180005cb2  cmp     [rbp+Type], 4
0x180005cb6  jnz     short loc_180005CDE
0x180005cb8  mov     rcx, [rbp+hKey]; hKey
0x180005cbc  lea     rax, [rbp+cbData]
0x180005cc0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180005cc5  lea     r9, [rbp+Type]; lpType
0x180005cc9  xor     r8d, r8d; lpReserved
0x180005ccc  mov     [rsp+30h+phkResult], rdi; lpData
0x180005cd1  lea     rdx, aTimewindowminu; "TimeWindowMinutes"
0x180005cd8  call    cs:__imp_RegQueryValueExW
0x180005cde  mov     rcx, [rbp+hKey]; hKey
0x180005ce2  test    rcx, rcx
0x180005ce5  jz      short loc_180005CED
0x180005ce7  call    cs:__imp_RegCloseKey
0x180005ced  mov     rax, rbx
0x180005cf0  mov     rbx, [rsp+30h+arg_18]
0x180005cf5  add     rsp, 30h
0x180005cf9  pop     r15
0x180005cfb  pop     r14
0x180005cfd  pop     rdi
0x180005cfe  pop     rsi
0x180005cff  pop     rbp
0x180005d00  retn
```
