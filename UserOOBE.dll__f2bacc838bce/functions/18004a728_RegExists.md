# RegExists

- ea: `0x18004a728`
- end: `0x18004a7e6`
- name: `RegExists`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180047e1c`
- `0x1800488e0`
- `0x18004afa8`

## callees

- `0x18004a728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a74b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a7d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a74b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a7d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a7ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a7ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a770`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a7cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a7cb`

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
0x18004a728  mov     [rsp+arg_8], rbx
0x18004a72d  push    rdi
0x18004a72e  sub     rsp, 30h
0x18004a732  mov     [rsp+38h+hKey], 0
0x18004a73b  mov     rbx, r8
0x18004a73e  mov     rdi, rdx
0x18004a741  test    rcx, rcx
0x18004a744  jnz     short loc_18004A758
0x18004a746  mov     ecx, 57h ; 'W'; dwErrCode
0x18004a74b  call    cs:__imp_SetLastError
0x18004a751  xor     eax, eax
0x18004a753  jmp     loc_18004A7DB
0x18004a758  test    rdi, rdi
0x18004a75b  jz      short loc_18004A788
0x18004a75d  lea     rax, [rsp+38h+hKey]
0x18004a762  mov     r9d, 20019h; samDesired
0x18004a768  xor     r8d, r8d; ulOptions
0x18004a76b  mov     [rsp+38h+phkResult], rax; phkResult
0x18004a770  call    cs:__imp_RegOpenKeyExW
0x18004a776  test    eax, eax
0x18004a778  jnz     short loc_18004A784
0x18004a77a  mov     rcx, [rsp+38h+hKey]; hKey
0x18004a77f  test    rcx, rcx
0x18004a782  jnz     short loc_18004A78D
0x18004a784  xor     ebx, ebx
0x18004a786  jmp     short loc_18004A7D1
0x18004a788  mov     [rsp+38h+hKey], rcx
0x18004a78d  test    rbx, rbx
0x18004a790  jz      short loc_18004A7C1
0x18004a792  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18004a79b  xor     r9d, r9d; lpType
0x18004a79e  xor     r8d, r8d; lpReserved
0x18004a7a1  mov     [rsp+38h+phkResult], 0; lpData
0x18004a7aa  mov     rdx, rbx; lpValueName
0x18004a7ad  call    cs:__imp_RegQueryValueExW
0x18004a7b3  mov     rcx, [rsp+38h+hKey]; hKey
0x18004a7b8  xor     ebx, ebx
0x18004a7ba  test    eax, eax
0x18004a7bc  setz    bl
0x18004a7bf  jmp     short loc_18004A7C6
0x18004a7c1  mov     ebx, 1
0x18004a7c6  test    rdi, rdi
0x18004a7c9  jz      short loc_18004A7D1
0x18004a7cb  call    cs:__imp_RegCloseKey
0x18004a7d1  xor     ecx, ecx; dwErrCode
0x18004a7d3  call    cs:__imp_SetLastError
0x18004a7d9  mov     eax, ebx
0x18004a7db  mov     rbx, [rsp+38h+arg_8]
0x18004a7e0  add     rsp, 30h
0x18004a7e4  pop     rdi
0x18004a7e5  retn
```
