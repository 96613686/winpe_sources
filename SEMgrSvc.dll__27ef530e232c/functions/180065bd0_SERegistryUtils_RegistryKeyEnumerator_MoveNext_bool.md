# SERegistryUtils::RegistryKeyEnumerator::MoveNext(bool *)

- ea: `0x180065bd0`
- end: `0x180065cfb`
- name: `?MoveNext@RegistryKeyEnumerator@SERegistryUtils@@QEAAJPEA_N@Z`
- size: `299`
- prototype: `__int64 __fastcall(SERegistryUtils::RegistryKeyEnumerator *__hidden this, bool *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038be0`
- `0x18003901c`
- `0x18003972c`
- `0x180039afc`
- `0x18003a3b4`

## callees

- `0x180065bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065cd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065cd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065ccc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065ccc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180065c4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180065c4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c96`

## pseudocode

```c
__int64 __fastcall SERegistryUtils::RegistryKeyEnumerator::MoveNext(
        SERegistryUtils::RegistryKeyEnumerator *this,
        bool *a2)
{
  bool v2; // zf
  unsigned int v5; // edi
  HKEY v6; // rbx
  int v7; // eax
  bool v8; // sf
  HKEY v9; // rbp
  HKEY v10; // r15
  DWORD LastError; // ebx
  DWORD cchName; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+18h] BYREF

  v2 = *((_BYTE *)this + 548) == 0;
  phkResult = 0;
  cchName = 260;
  if ( v2 )
    return (unsigned int)-2147019873;
  v6 = (HKEY)*((_QWORD *)this + 1);
  if ( !v6 )
    v6 = *(HKEY *)this;
  v7 = RegEnumKeyExW(v6, *((_DWORD *)this + 136), (LPWSTR)this + 12, &cchName, 0, 0, 0, 0);
  if ( v7 && v7 != 259 )
  {
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
  v5 = 0;
  if ( v7 == 259 )
  {
    *a2 = 0;
    return v5;
  }
  v7 = RegOpenKeyExW(v6, (LPCWSTR)this + 12, 0, 0x20019u, &phkResult);
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = v7 < 0;
  }
  if ( v8 )
    return (unsigned int)v7;
  v9 = (HKEY)*((_QWORD *)this + 2);
  v10 = phkResult;
  if ( v9 )
  {
    LastError = GetLastError();
    RegCloseKey(v9);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = v10;
  *a2 = 1;
  ++*((_DWORD *)this + 136);
  return v5;
}

```

## disassembly

```asm
0x180065bd0  mov     rax, rsp
0x180065bd3  mov     [rax+10h], rbx
0x180065bd7  push    rbp
0x180065bd8  push    rsi
0x180065bd9  push    rdi
0x180065bda  push    r14
0x180065bdc  push    r15
0x180065bde  sub     rsp, 40h
0x180065be2  cmp     byte ptr [rcx+224h], 0
0x180065be9  mov     r14, rdx
0x180065bec  mov     rsi, rcx
0x180065bef  mov     qword ptr [rax+18h], 0
0x180065bf7  mov     dword ptr [rax+8], 104h
0x180065bfe  jnz     short loc_180065C0A
0x180065c00  mov     edi, 8007139Fh
0x180065c05  jmp     loc_180065CE8
0x180065c0a  mov     rbx, [rcx+8]
0x180065c0e  test    rbx, rbx
0x180065c11  jnz     short loc_180065C16
0x180065c13  mov     rbx, [rcx]
0x180065c16  mov     edx, [rcx+220h]; dwIndex
0x180065c1c  lea     r8, [rcx+18h]; lpName
0x180065c20  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180065c29  lea     r9, [rsp+68h+cchName]; lpcchName
0x180065c2e  mov     [rsp+68h+lpcchClass], 0; lpcchClass
0x180065c37  mov     rcx, rbx; hKey
0x180065c3a  mov     [rsp+68h+lpClass], 0; lpClass
0x180065c43  mov     [rsp+68h+lpReserved], 0; lpReserved
0x180065c4c  call    cs:__imp_RegEnumKeyExW
0x180065c52  mov     ecx, 103h
0x180065c57  test    eax, eax
0x180065c59  jz      short loc_180065C6E
0x180065c5b  cmp     eax, ecx
0x180065c5d  jz      short loc_180065C6E
0x180065c5f  test    eax, eax
0x180065c61  jle     short loc_180065CAC
0x180065c63  movzx   edi, ax
0x180065c66  or      edi, 80070000h
0x180065c6c  jmp     short loc_180065CE8
0x180065c6e  xor     edi, edi
0x180065c70  cmp     eax, ecx
0x180065c72  jnz     short loc_180065C79
0x180065c74  mov     [r14], dil
0x180065c77  jmp     short loc_180065CE8
0x180065c79  lea     rax, [rsp+68h+phkResult]
0x180065c81  mov     r9d, 20019h; samDesired
0x180065c87  xor     r8d, r8d; ulOptions
0x180065c8a  mov     [rsp+68h+lpReserved], rax; phkResult
0x180065c8f  lea     rdx, [rsi+18h]; lpSubKey
0x180065c93  mov     rcx, rbx; hKey
0x180065c96  call    cs:__imp_RegOpenKeyExW
0x180065c9c  test    eax, eax
0x180065c9e  jle     short loc_180065CAA
0x180065ca0  movzx   eax, ax
0x180065ca3  or      eax, 80070000h
0x180065ca8  test    eax, eax
0x180065caa  jns     short loc_180065CB0
0x180065cac  mov     edi, eax
0x180065cae  jmp     short loc_180065CE8
0x180065cb0  mov     rbp, [rsi+10h]
0x180065cb4  mov     r15, [rsp+68h+phkResult]
0x180065cbc  test    rbp, rbp
0x180065cbf  jz      short loc_180065CDA
0x180065cc1  call    cs:__imp_GetLastError
0x180065cc7  mov     rcx, rbp; hKey
0x180065cca  mov     ebx, eax
0x180065ccc  call    cs:__imp_RegCloseKey
0x180065cd2  mov     ecx, ebx; dwErrCode
0x180065cd4  call    cs:__imp_SetLastError
0x180065cda  mov     [rsi+10h], r15
0x180065cde  mov     byte ptr [r14], 1
0x180065ce2  inc     dword ptr [rsi+220h]
0x180065ce8  mov     rbx, [rsp+68h+arg_8]
0x180065ced  mov     eax, edi
0x180065cef  add     rsp, 40h
0x180065cf3  pop     r15
0x180065cf5  pop     r14
0x180065cf7  pop     rdi
0x180065cf8  pop     rsi
0x180065cf9  pop     rbp
0x180065cfa  retn
```
