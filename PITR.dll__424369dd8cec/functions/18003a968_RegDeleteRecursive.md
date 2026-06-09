# RegDeleteRecursive

- ea: `0x18003a968`
- end: `0x18003aa20`
- name: `RegDeleteRecursive`
- size: `184`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x18000b280`

## callees

- `0x18003a968`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003a9c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003a9c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a9ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a9ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003a9ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003a9ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a9cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a9cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa08`

## pseudocode

```c
_BOOL8 __fastcall RegDeleteRecursive(HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS v4; // ebx
  LSTATUS v5; // eax
  HKEY hKeya; // [rsp+40h] [rbp+8h] BYREF

  hKeya = 0;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL && lpSubKey && *lpSubKey )
  {
    v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20F003Fu, &hKeya);
    if ( !v4 )
    {
      v4 = RegDeleteTreeW(hKeya, 0);
      v5 = RegCloseKey(hKeya);
      if ( !v4 )
      {
        if ( !v5 )
          v5 = RegDeleteKeyExW(hKey, lpSubKey, 0xF003Fu, 0);
        v4 = v5;
      }
    }
    SetLastError(v4);
    return v4 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18003a968  mov     r11, rsp
0x18003a96b  mov     [r11+10h], rbx
0x18003a96f  mov     [r11+18h], rsi
0x18003a973  push    rdi
0x18003a974  sub     rsp, 30h
0x18003a978  lea     rax, [rcx-1]
0x18003a97c  mov     qword ptr [r11+8], 0
0x18003a984  mov     rdi, rdx
0x18003a987  mov     rsi, rcx
0x18003a98a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003a98e  ja      short loc_18003AA03
0x18003a990  test    rdx, rdx
0x18003a993  jz      short loc_18003AA03
0x18003a995  xor     eax, eax
0x18003a997  cmp     ax, [rdx]
0x18003a99a  jz      short loc_18003AA03
0x18003a99c  lea     rax, [r11+8]
0x18003a9a0  mov     r9d, 20F003Fh; samDesired
0x18003a9a6  xor     r8d, r8d; ulOptions
0x18003a9a9  mov     [r11-18h], rax
0x18003a9ad  call    cs:__imp_RegOpenKeyExW
0x18003a9b3  mov     ebx, eax
0x18003a9b5  test    eax, eax
0x18003a9b7  jnz     short loc_18003A9F2
0x18003a9b9  mov     rcx, [rsp+38h+hKey]; hKey
0x18003a9be  xor     edx, edx; lpSubKey
0x18003a9c0  call    cs:__imp_RegDeleteTreeW
0x18003a9c6  mov     rcx, [rsp+38h+hKey]; hKey
0x18003a9cb  mov     ebx, eax
0x18003a9cd  call    cs:__imp_RegCloseKey
0x18003a9d3  test    ebx, ebx
0x18003a9d5  jnz     short loc_18003A9F2
0x18003a9d7  test    eax, eax
0x18003a9d9  jnz     short loc_18003A9F0
0x18003a9db  xor     r9d, r9d; Reserved
0x18003a9de  mov     r8d, 0F003Fh; samDesired
0x18003a9e4  mov     rdx, rdi; lpSubKey
0x18003a9e7  mov     rcx, rsi; hKey
0x18003a9ea  call    cs:__imp_RegDeleteKeyExW
0x18003a9f0  mov     ebx, eax
0x18003a9f2  mov     ecx, ebx; dwErrCode
0x18003a9f4  call    cs:__imp_SetLastError
0x18003a9fa  xor     eax, eax
0x18003a9fc  test    ebx, ebx
0x18003a9fe  setz    al
0x18003aa01  jmp     short loc_18003AA10
0x18003aa03  mov     ecx, 57h ; 'W'; dwErrCode
0x18003aa08  call    cs:__imp_SetLastError
0x18003aa0e  xor     eax, eax
0x18003aa10  mov     rbx, [rsp+38h+arg_8]
0x18003aa15  mov     rsi, [rsp+38h+arg_10]
0x18003aa1a  add     rsp, 30h
0x18003aa1e  pop     rdi
0x18003aa1f  retn
```
