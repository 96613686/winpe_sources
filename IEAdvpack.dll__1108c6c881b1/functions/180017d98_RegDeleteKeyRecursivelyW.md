# RegDeleteKeyRecursivelyW

- ea: `0x180017d98`
- end: `0x180017f0e`
- name: `RegDeleteKeyRecursivelyW`
- size: `374`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000de30`
- `0x18000e060`
- `0x180017d98`

## callees

- `0x180017d98`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017e83`
- `ADVAPI32!RegCloseKey` at `0x180017e83`
- `ADVAPI32!RegOpenKeyExW` at `0x180017de7`
- `ADVAPI32!RegOpenKeyExW` at `0x180017de7`
- `ADVAPI32!RegEnumValueW` at `0x180017edb`
- `ADVAPI32!RegEnumValueW` at `0x180017edb`
- `ADVAPI32!RegDeleteValueW` at `0x180017ea6`
- `ADVAPI32!RegDeleteValueW` at `0x180017ea6`
- `ADVAPI32!RegEnumKeyW` at `0x180017e74`
- `ADVAPI32!RegEnumKeyW` at `0x180017e74`
- `ADVAPI32!RegDeleteKeyW` at `0x180017e94`
- `ADVAPI32!RegDeleteKeyW` at `0x180017e94`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180017e3e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180017e3e`

## pseudocode

```c
__int64 __fastcall RegDeleteKeyRecursivelyW(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  if ( !v4 )
  {
    cSubKeys = 0;
    cchName = 261;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !v4 )
    {
      while ( !RegEnumKeyW(hKey, --cSubKeys, Name, cchName) )
        RegDeleteKeyRecursivelyW(hKey, Name);
    }
    RegCloseKey(hKey);
    v5 = a1;
    if ( a2 )
    {
      return (unsigned int)RegDeleteKeyW(a1, a2);
    }
    else
    {
      while ( 1 )
      {
        cchName = 261;
        if ( RegEnumValueW(v5, 0, Name, &cchName, 0, 0, 0, 0) || RegDeleteValueW(a1, Name) )
          break;
        v5 = a1;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180017d98  mov     [rsp-8+arg_10], rbx
0x180017d9d  mov     [rsp-8+arg_18], rsi
0x180017da2  push    rbp
0x180017da3  push    rdi
0x180017da4  push    r14
0x180017da6  lea     rbp, [rsp-190h]
0x180017dae  sub     rsp, 290h
0x180017db5  mov     rax, cs:__security_cookie
0x180017dbc  xor     rax, rsp
0x180017dbf  mov     [rbp+1A0h+var_20], rax
0x180017dc6  lea     rax, [rsp+2A0h+hKey]
0x180017dcb  xor     r14d, r14d
0x180017dce  mov     r9d, 2000000h; samDesired
0x180017dd4  mov     [rsp+2A0h+hKey], r14
0x180017dd9  xor     r8d, r8d; ulOptions
0x180017ddc  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180017de1  mov     rsi, rdx
0x180017de4  mov     rdi, rcx
0x180017de7  call    cs:__imp_RegOpenKeyExW
0x180017ded  mov     ebx, eax
0x180017def  test    eax, eax
0x180017df1  jnz     loc_180017EE5
0x180017df7  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180017dfc  lea     rax, [rsp+2A0h+cSubKeys]
0x180017e01  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180017e06  xor     r9d, r9d; lpReserved
0x180017e09  mov     [rsp+2A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180017e0e  xor     r8d, r8d; lpcchClass
0x180017e11  mov     [rsp+2A0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180017e16  xor     edx, edx; lpClass
0x180017e18  mov     [rsp+2A0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180017e1d  mov     [rsp+2A0h+lpcValues], r14; lpcValues
0x180017e22  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180017e27  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180017e2c  mov     [rsp+2A0h+phkResult], rax; lpcSubKeys
0x180017e31  mov     [rsp+2A0h+cSubKeys], r14d
0x180017e36  mov     [rsp+2A0h+cchName], 105h
0x180017e3e  call    cs:__imp_RegQueryInfoKeyW
0x180017e44  mov     ebx, eax
0x180017e46  test    eax, eax
0x180017e48  jnz     short loc_180017E7E
0x180017e4a  jmp     short loc_180017E5B
0x180017e4c  mov     rcx, [rsp+2A0h+hKey]
0x180017e51  lea     rdx, [rsp+2A0h+Name]
0x180017e56  call    RegDeleteKeyRecursivelyW
0x180017e5b  mov     edx, [rsp+2A0h+cSubKeys]
0x180017e5f  lea     r8, [rsp+2A0h+Name]; lpName
0x180017e64  mov     r9d, [rsp+2A0h+cchName]; cchName
0x180017e69  dec     edx; dwIndex
0x180017e6b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180017e70  mov     [rsp+2A0h+cSubKeys], edx
0x180017e74  call    cs:__imp_RegEnumKeyW
0x180017e7a  test    eax, eax
0x180017e7c  jz      short loc_180017E4C
0x180017e7e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180017e83  call    cs:__imp_RegCloseKey
0x180017e89  mov     rcx, rdi; hKey
0x180017e8c  test    rsi, rsi
0x180017e8f  jz      short loc_180017EB3
0x180017e91  mov     rdx, rsi; lpSubKey
0x180017e94  call    cs:__imp_RegDeleteKeyW
0x180017e9a  mov     ebx, eax
0x180017e9c  jmp     short loc_180017EE5
0x180017e9e  lea     rdx, [rsp+2A0h+Name]; lpValueName
0x180017ea3  mov     rcx, rdi; hKey
0x180017ea6  call    cs:__imp_RegDeleteValueW
0x180017eac  test    eax, eax
0x180017eae  jnz     short loc_180017EE5
0x180017eb0  mov     rcx, rdi; hKey
0x180017eb3  mov     [rsp+2A0h+lpcValues], r14; lpcbData
0x180017eb8  lea     r9, [rsp+2A0h+cchName]; lpcchValueName
0x180017ebd  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpData
0x180017ec2  lea     r8, [rsp+2A0h+Name]; lpValueName
0x180017ec7  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpType
0x180017ecc  xor     edx, edx; dwIndex
0x180017ece  mov     [rsp+2A0h+phkResult], r14; lpReserved
0x180017ed3  mov     [rsp+2A0h+cchName], 105h
0x180017edb  call    cs:__imp_RegEnumValueW
0x180017ee1  test    eax, eax
0x180017ee3  jz      short loc_180017E9E
0x180017ee5  mov     eax, ebx
0x180017ee7  mov     rcx, [rbp+1A0h+var_20]
0x180017eee  xor     rcx, rsp; StackCookie
0x180017ef1  call    __security_check_cookie
0x180017ef6  lea     r11, [rsp+2A0h+var_10]
0x180017efe  mov     rbx, [r11+30h]
0x180017f02  mov     rsi, [r11+38h]
0x180017f06  mov     rsp, r11
0x180017f09  pop     r14
0x180017f0b  pop     rdi
0x180017f0c  pop     rbp
0x180017f0d  retn
```
