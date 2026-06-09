# _AfxDeleteRegKey

- ea: `0x180001c00`
- end: `0x180001d1a`
- name: `_AfxDeleteRegKey`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001910`
- `0x18009be00`

## callees

- `0x180001c00`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180001c2f`
- `msvcrt!_wcsdup` at `0x180001c2f`
- `msvcrt!wcsrchr` at `0x180001cd1`
- `msvcrt!wcsrchr` at `0x180001cd1`
- `msvcrt!free` at `0x180001ce6`
- `msvcrt!free` at `0x180001ce6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180001cc3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180001cc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ca9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c80`
- `ADVAPI32!RegEnumKeyW` at `0x180001c9c`
- `ADVAPI32!RegEnumKeyW` at `0x180001c9c`

## pseudocode

```c
__int64 __fastcall AfxDeleteRegKey(const wchar_t *a1)
{
  wchar_t *v1; // rdi
  __int64 v2; // rax
  wchar_t *i; // rcx
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !a1 )
    return 0;
  v1 = _wcsdup(a1);
  if ( !v1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( v1[v2] );
  for ( i = &v1[v2]; i; i = wcsrchr(v1, 0x5Cu) )
  {
    *i = 0;
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, v1, 0, 0x2000000u, &hKey) )
      break;
    v4 = RegEnumKeyW(hKey, 0, Name, 0x105u);
    RegCloseKey(hKey);
    if ( !v4 )
      break;
    RegDeleteKeyExW(HKEY_CLASSES_ROOT, v1, 0, 0);
  }
  free(v1);
  return 1;
}

```

## disassembly

```asm
0x180001c00  mov     [rsp+arg_8], rbx
0x180001c05  mov     [rsp+arg_10], rsi
0x180001c0a  push    rdi
0x180001c0b  sub     rsp, 260h
0x180001c12  mov     rax, cs:__security_cookie
0x180001c19  xor     rax, rsp
0x180001c1c  mov     [rsp+268h+var_18], rax
0x180001c24  xor     esi, esi
0x180001c26  test    rcx, rcx
0x180001c29  jz      loc_180001CF3
0x180001c2f  call    cs:__imp__wcsdup
0x180001c35  mov     rdi, rax
0x180001c38  test    rax, rax
0x180001c3b  jz      loc_180001CF3
0x180001c41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001c45  inc     rax
0x180001c48  cmp     [rdi+rax*2], si
0x180001c4c  jnz     short loc_180001C45
0x180001c4e  lea     rcx, [rdi+rax*2]
0x180001c52  test    rcx, rcx
0x180001c55  jz      loc_180001CE3
0x180001c5b  mov     [rcx], si
0x180001c5e  lea     rax, [rsp+268h+hKey]
0x180001c63  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001c6a  mov     [rsp+268h+phkResult], rax; phkResult
0x180001c6f  mov     r9d, 2000000h; samDesired
0x180001c75  mov     [rsp+268h+hKey], rsi
0x180001c7a  xor     r8d, r8d; ulOptions
0x180001c7d  mov     rdx, rdi; lpSubKey
0x180001c80  call    cs:__imp_RegOpenKeyExW
0x180001c86  test    eax, eax
0x180001c88  jnz     short loc_180001CE3
0x180001c8a  mov     rcx, [rsp+268h+hKey]; hKey
0x180001c8f  lea     r8, [rsp+268h+Name]; lpName
0x180001c94  mov     r9d, 105h; cchName
0x180001c9a  xor     edx, edx; dwIndex
0x180001c9c  call    cs:__imp_RegEnumKeyW
0x180001ca2  mov     rcx, [rsp+268h+hKey]; hKey
0x180001ca7  mov     ebx, eax
0x180001ca9  call    cs:__imp_RegCloseKey
0x180001caf  test    ebx, ebx
0x180001cb1  jz      short loc_180001CE3
0x180001cb3  xor     r9d, r9d; Reserved
0x180001cb6  xor     r8d, r8d; samDesired
0x180001cb9  mov     rdx, rdi; lpSubKey
0x180001cbc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001cc3  call    cs:__imp_RegDeleteKeyExW
0x180001cc9  mov     edx, 5Ch ; '\'; Ch
0x180001cce  mov     rcx, rdi; Str
0x180001cd1  call    cs:__imp_wcsrchr
0x180001cd7  mov     rcx, rax
0x180001cda  test    rax, rax
0x180001cdd  jnz     loc_180001C5B
0x180001ce3  mov     rcx, rdi; Block
0x180001ce6  call    cs:__imp_free
0x180001cec  mov     eax, 1
0x180001cf1  jmp     short loc_180001CF5
0x180001cf3  xor     eax, eax
0x180001cf5  mov     rcx, [rsp+268h+var_18]
0x180001cfd  xor     rcx, rsp; StackCookie
0x180001d00  call    __security_check_cookie
0x180001d05  lea     r11, [rsp+268h+var_8]
0x180001d0d  mov     rbx, [r11+18h]
0x180001d11  mov     rsi, [r11+20h]
0x180001d15  mov     rsp, r11
0x180001d18  pop     rdi
0x180001d19  retn
```
