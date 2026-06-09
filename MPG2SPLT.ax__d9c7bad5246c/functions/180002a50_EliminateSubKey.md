# EliminateSubKey

- ea: `0x180002a50`
- end: `0x180002b8d`
- name: `EliminateSubKey`
- size: `317`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800029c8`
- `0x180002a50`

## callees

- `0x180001460`
- `0x180002a50`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180002b37`
- `ADVAPI32!RegEnumKeyExW` at `0x180002b37`
- `ADVAPI32!RegCloseKey` at `0x180002b46`
- `ADVAPI32!RegCloseKey` at `0x180002b46`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b52`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b52`
- `ADVAPI32!RegOpenKeyExW` at `0x180002ae1`
- `ADVAPI32!RegOpenKeyExW` at `0x180002ae1`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY hKey, LPCWSTR lpSubKey)
{
  LPCWSTR v4; // rax
  __int64 v5; // rcx
  LSTATUS result; // eax
  bool v7; // cc
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  if ( !lpSubKey )
    return -2147467259;
  v4 = lpSubKey;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( !v5 || ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) == 0 )
    return -2147467259;
  result = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &hKeya);
  v7 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKeya, 0, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKeya, SubKey) );
    RegCloseKey(hKeya);
    result = RegDeleteKeyW(hKey, lpSubKey);
    v7 = result <= 0;
  }
  if ( !v7 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002a50  mov     [rsp-8+arg_10], rbx
0x180002a55  push    rbp
0x180002a56  push    rsi
0x180002a57  push    rdi
0x180002a58  lea     rbp, [rsp-180h]
0x180002a60  sub     rsp, 280h
0x180002a67  mov     rax, cs:__security_cookie
0x180002a6e  xor     rax, rsp
0x180002a71  mov     [rbp+190h+var_20], rax
0x180002a78  xor     esi, esi
0x180002a7a  mov     rbx, rdx
0x180002a7d  mov     [rsp+290h+hKey], rsi
0x180002a82  mov     rdi, rcx
0x180002a85  test    rdx, rdx
0x180002a88  jz      loc_180002B66
0x180002a8e  mov     edx, 7FFFFFFFh
0x180002a93  mov     rax, rbx
0x180002a96  mov     ecx, edx
0x180002a98  cmp     [rax], si
0x180002a9b  jz      short loc_180002AA7
0x180002a9d  add     rax, 2
0x180002aa1  sub     rcx, 1
0x180002aa5  jnz     short loc_180002A98
0x180002aa7  sub     rdx, rcx
0x180002aaa  mov     rax, rcx
0x180002aad  neg     rax
0x180002ab0  sbb     r8, r8
0x180002ab3  and     r8, rdx
0x180002ab6  test    rcx, rcx
0x180002ab9  jz      loc_180002B66
0x180002abf  test    r8, r8
0x180002ac2  jz      loc_180002B66
0x180002ac8  lea     rax, [rsp+290h+hKey]
0x180002acd  mov     r9d, 2000000h; samDesired
0x180002ad3  xor     r8d, r8d; ulOptions
0x180002ad6  mov     [rsp+290h+phkResult], rax; phkResult
0x180002adb  mov     rdx, rbx; lpSubKey
0x180002ade  mov     rcx, rdi; hKey
0x180002ae1  call    cs:__imp_RegOpenKeyExW
0x180002ae7  test    eax, eax
0x180002ae9  jnz     short loc_180002B5A
0x180002aeb  jmp     short loc_180002B00
0x180002aed  mov     rcx, [rsp+290h+hKey]; hKey
0x180002af2  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180002af7  call    EliminateSubKey
0x180002afc  test    eax, eax
0x180002afe  jnz     short loc_180002B41
0x180002b00  mov     rcx, [rsp+290h+hKey]; hKey
0x180002b05  lea     rax, [rsp+290h+ftLastWriteTime]
0x180002b0a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002b0f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180002b14  mov     [rsp+290h+lpcchClass], rsi; lpcchClass
0x180002b19  lea     r8, [rsp+290h+SubKey]; lpName
0x180002b1e  mov     [rsp+290h+lpClass], rsi; lpClass
0x180002b23  xor     edx, edx; dwIndex
0x180002b25  mov     [rsp+290h+phkResult], rsi; lpReserved
0x180002b2a  mov     [rsp+290h+cchName], 104h
0x180002b32  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], rsi
0x180002b37  call    cs:__imp_RegEnumKeyExW
0x180002b3d  test    eax, eax
0x180002b3f  jz      short loc_180002AED
0x180002b41  mov     rcx, [rsp+290h+hKey]; hKey
0x180002b46  call    cs:__imp_RegCloseKey
0x180002b4c  mov     rdx, rbx; lpSubKey
0x180002b4f  mov     rcx, rdi; hKey
0x180002b52  call    cs:__imp_RegDeleteKeyW
0x180002b58  test    eax, eax
0x180002b5a  jle     short loc_180002B6B
0x180002b5c  movzx   eax, ax
0x180002b5f  or      eax, 80070000h
0x180002b64  jmp     short loc_180002B6B
0x180002b66  mov     eax, 80004005h
0x180002b6b  mov     rcx, [rbp+190h+var_20]
0x180002b72  xor     rcx, rsp; StackCookie
0x180002b75  call    __security_check_cookie
0x180002b7a  mov     rbx, [rsp+290h+arg_10]
0x180002b82  add     rsp, 280h
0x180002b89  pop     rdi
0x180002b8a  pop     rsi
0x180002b8b  pop     rbp
0x180002b8c  retn
```
