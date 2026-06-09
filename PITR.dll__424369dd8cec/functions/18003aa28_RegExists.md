# RegExists

- ea: `0x18003aa28`
- end: `0x18003aae6`
- name: `RegExists`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x18000b280`
- `0x18000fab0`
- `0x18003fc08`

## callees

- `0x18003aa28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aacb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aaad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aaad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aad3`

## pseudocode

```c
_BOOL8 __fastcall RegExists(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  BOOL v6; // ebx
  LSTATUS Value; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( !a2 )
  {
    hKey = a1;
    goto LABEL_8;
  }
  if ( !RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
  {
    a1 = hKey;
    if ( hKey )
    {
LABEL_8:
      if ( a3 )
      {
        Value = RegQueryValueExW(a1, a3, 0, 0, 0, 0);
        a1 = hKey;
        v6 = Value == 0;
      }
      else
      {
        v6 = 1;
      }
      if ( a2 )
        RegCloseKey(a1);
      goto LABEL_13;
    }
  }
  v6 = 0;
LABEL_13:
  SetLastError(0);
  return v6;
}

```

## disassembly

```asm
0x18003aa28  mov     [rsp+arg_8], rbx
0x18003aa2d  push    rdi
0x18003aa2e  sub     rsp, 30h
0x18003aa32  mov     [rsp+38h+hKey], 0
0x18003aa3b  mov     rbx, r8
0x18003aa3e  mov     rdi, rdx
0x18003aa41  test    rcx, rcx
0x18003aa44  jnz     short loc_18003AA58
0x18003aa46  mov     ecx, 57h ; 'W'; dwErrCode
0x18003aa4b  call    cs:__imp_SetLastError
0x18003aa51  xor     eax, eax
0x18003aa53  jmp     loc_18003AADB
0x18003aa58  test    rdi, rdi
0x18003aa5b  jz      short loc_18003AA88
0x18003aa5d  lea     rax, [rsp+38h+hKey]
0x18003aa62  mov     r9d, 20019h; samDesired
0x18003aa68  xor     r8d, r8d; ulOptions
0x18003aa6b  mov     [rsp+38h+phkResult], rax; phkResult
0x18003aa70  call    cs:__imp_RegOpenKeyExW
0x18003aa76  test    eax, eax
0x18003aa78  jnz     short loc_18003AA84
0x18003aa7a  mov     rcx, [rsp+38h+hKey]; hKey
0x18003aa7f  test    rcx, rcx
0x18003aa82  jnz     short loc_18003AA8D
0x18003aa84  xor     ebx, ebx
0x18003aa86  jmp     short loc_18003AAD1
0x18003aa88  mov     [rsp+38h+hKey], rcx
0x18003aa8d  test    rbx, rbx
0x18003aa90  jz      short loc_18003AAC1
0x18003aa92  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18003aa9b  xor     r9d, r9d; lpType
0x18003aa9e  xor     r8d, r8d; lpReserved
0x18003aaa1  mov     [rsp+38h+phkResult], 0; lpData
0x18003aaaa  mov     rdx, rbx; lpValueName
0x18003aaad  call    cs:__imp_RegQueryValueExW
0x18003aab3  mov     rcx, [rsp+38h+hKey]; hKey
0x18003aab8  xor     ebx, ebx
0x18003aaba  test    eax, eax
0x18003aabc  setz    bl
0x18003aabf  jmp     short loc_18003AAC6
0x18003aac1  mov     ebx, 1
0x18003aac6  test    rdi, rdi
0x18003aac9  jz      short loc_18003AAD1
0x18003aacb  call    cs:__imp_RegCloseKey
0x18003aad1  xor     ecx, ecx; dwErrCode
0x18003aad3  call    cs:__imp_SetLastError
0x18003aad9  mov     eax, ebx
0x18003aadb  mov     rbx, [rsp+38h+arg_8]
0x18003aae0  add     rsp, 30h
0x18003aae4  pop     rdi
0x18003aae5  retn
```
