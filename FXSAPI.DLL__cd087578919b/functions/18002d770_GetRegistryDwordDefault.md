# GetRegistryDwordDefault

- ea: `0x18002d770`
- end: `0x18002d84e`
- name: `GetRegistryDwordDefault`
- size: `222`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000deb0`
- `0x18002f480`
- `0x18002f7b0`

## callees

- `0x18002d0e4`
- `0x18002d770`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d832`
- `KERNEL32!SetLastError` at `0x18002d832`
- `ADVAPI32!RegSetValueExW` at `0x18002d7f1`
- `ADVAPI32!RegSetValueExW` at `0x18002d7f1`
- `ADVAPI32!RegQueryValueExW` at `0x18002d7be`
- `ADVAPI32!RegQueryValueExW` at `0x18002d7be`

## string_xrefs

- `0x18002d803`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall GetRegistryDwordDefault(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)
{
  DWORD v6; // ecx
  unsigned int v7; // ebx
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  cbData = 4;
  Type = 0;
  if ( lpData )
  {
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    if ( v7 == 2 )
    {
      *(_DWORD *)lpData = 0;
      v7 = RegSetValueExW(hKey, lpValueName, 0, 4u, lpData, 4u);
      if ( v7 )
      {
        fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v7);
LABEL_10:
        v6 = v7;
        goto LABEL_11;
      }
    }
    else if ( v7 || Type != 4 )
    {
      fax_dprintf(L"RegQueryValueEx() failed[%s], ec=%d", lpValueName, v7);
      goto LABEL_10;
    }
    return 1;
  }
  v6 = 87;
LABEL_11:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18002d770  mov     rax, rsp
0x18002d773  mov     [rax+8], rbx
0x18002d777  mov     [rax+20h], r9d
0x18002d77b  push    rbp
0x18002d77c  push    rsi
0x18002d77d  push    rdi
0x18002d77e  sub     rsp, 30h
0x18002d782  mov     dword ptr [rax+18h], 4
0x18002d789  mov     rsi, r8
0x18002d78c  mov     dword ptr [rax+20h], 0
0x18002d793  mov     rdi, rdx
0x18002d796  mov     rbp, rcx
0x18002d799  test    r8, r8
0x18002d79c  jnz     short loc_18002D7A7
0x18002d79e  lea     ecx, [r8+57h]; hKey
0x18002d7a2  jmp     loc_18002D832
0x18002d7a7  lea     rax, [rsp+48h+cbData]
0x18002d7ac  xor     r8d, r8d; lpReserved
0x18002d7af  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002d7b4  lea     r9, [rsp+48h+Type]; lpType
0x18002d7b9  mov     [rsp+48h+lpData], rsi; lpData
0x18002d7be  call    cs:__imp_RegQueryValueExW
0x18002d7c5  nop     dword ptr [rax+rax+00h]
0x18002d7ca  mov     ebx, eax
0x18002d7cc  cmp     eax, 2
0x18002d7cf  jnz     short loc_18002D813
0x18002d7d1  mov     dword ptr [rsp+48h+lpcbData], 4; cbData
0x18002d7d9  lea     r9d, [rax+2]; dwType
0x18002d7dd  xor     r8d, r8d; Reserved
0x18002d7e0  mov     [rsp+48h+lpData], rsi; lpData
0x18002d7e5  mov     rdx, rdi; lpValueName
0x18002d7e8  mov     dword ptr [rsi], 0
0x18002d7ee  mov     rcx, rbp; hKey
0x18002d7f1  call    cs:__imp_RegSetValueExW
0x18002d7f8  nop     dword ptr [rax+rax+00h]
0x18002d7fd  mov     ebx, eax
0x18002d7ff  test    eax, eax
0x18002d801  jz      short loc_18002D80C
0x18002d803  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18002d80a  jmp     short loc_18002D825
0x18002d80c  mov     eax, 1
0x18002d811  jmp     short loc_18002D840
0x18002d813  test    ebx, ebx
0x18002d815  jnz     short loc_18002D81E
0x18002d817  cmp     [rsp+48h+Type], 4
0x18002d81c  jz      short loc_18002D80C
0x18002d81e  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed[%s], ec=%d"
0x18002d825  mov     r8d, ebx
0x18002d828  mov     rdx, rdi
0x18002d82b  call    fax_dprintf
0x18002d830  mov     ecx, ebx; dwErrCode
0x18002d832  call    cs:__imp_SetLastError
0x18002d839  nop     dword ptr [rax+rax+00h]
0x18002d83e  xor     eax, eax
0x18002d840  mov     rbx, [rsp+48h+arg_0]
0x18002d845  add     rsp, 30h
0x18002d849  pop     rdi
0x18002d84a  pop     rsi
0x18002d84b  pop     rbp
0x18002d84c  retn
```
