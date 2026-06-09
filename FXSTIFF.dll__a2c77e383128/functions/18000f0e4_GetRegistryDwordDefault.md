# GetRegistryDwordDefault

- ea: `0x18000f0e4`
- end: `0x18000f1ac`
- name: `GetRegistryDwordDefault`
- size: `200`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016d30`
- `0x180016f40`
- `0x180017190`
- `0x1800173a0`

## callees

- `0x18000f0e4`
- `0x180016794`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f197`
- `KERNEL32!SetLastError` at `0x18000f197`
- `ADVAPI32!RegQueryValueExW` at `0x18000f12f`
- `ADVAPI32!RegQueryValueExW` at `0x18000f12f`
- `ADVAPI32!RegSetValueExW` at `0x18000f15c`
- `ADVAPI32!RegSetValueExW` at `0x18000f15c`

## string_xrefs

- `0x18000f168`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000f0e4  mov     rax, rsp
0x18000f0e7  mov     [rax+8], rbx
0x18000f0eb  mov     [rax+20h], r9d
0x18000f0ef  push    rbp
0x18000f0f0  push    rsi
0x18000f0f1  push    rdi
0x18000f0f2  sub     rsp, 30h
0x18000f0f6  mov     dword ptr [rax+18h], 4
0x18000f0fd  mov     rsi, r8
0x18000f100  mov     dword ptr [rax+20h], 0
0x18000f107  mov     rdi, rdx
0x18000f10a  mov     rbp, rcx
0x18000f10d  test    r8, r8
0x18000f110  jnz     short loc_18000F118
0x18000f112  lea     ecx, [r8+57h]; hKey
0x18000f116  jmp     short loc_18000F197
0x18000f118  lea     rax, [rsp+48h+cbData]
0x18000f11d  xor     r8d, r8d; lpReserved
0x18000f120  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000f125  lea     r9, [rsp+48h+Type]; lpType
0x18000f12a  mov     [rsp+48h+lpData], rsi; lpData
0x18000f12f  call    cs:__imp_RegQueryValueExW
0x18000f135  mov     ebx, eax
0x18000f137  cmp     eax, 2
0x18000f13a  jnz     short loc_18000F178
0x18000f13c  mov     dword ptr [rsp+48h+lpcbData], 4; cbData
0x18000f144  lea     r9d, [rax+2]; dwType
0x18000f148  xor     r8d, r8d; Reserved
0x18000f14b  mov     [rsp+48h+lpData], rsi; lpData
0x18000f150  mov     rdx, rdi; lpValueName
0x18000f153  mov     dword ptr [rsi], 0
0x18000f159  mov     rcx, rbp; hKey
0x18000f15c  call    cs:__imp_RegSetValueExW
0x18000f162  mov     ebx, eax
0x18000f164  test    eax, eax
0x18000f166  jz      short loc_18000F171
0x18000f168  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f16f  jmp     short loc_18000F18A
0x18000f171  mov     eax, 1
0x18000f176  jmp     short loc_18000F19F
0x18000f178  test    ebx, ebx
0x18000f17a  jnz     short loc_18000F183
0x18000f17c  cmp     [rsp+48h+Type], 4
0x18000f181  jz      short loc_18000F171
0x18000f183  lea     rcx, aRegqueryvaluee; "RegQueryValueEx() failed[%s], ec=%d"
0x18000f18a  mov     r8d, ebx
0x18000f18d  mov     rdx, rdi
0x18000f190  call    fax_dprintf
0x18000f195  mov     ecx, ebx; dwErrCode
0x18000f197  call    cs:__imp_SetLastError
0x18000f19d  xor     eax, eax
0x18000f19f  mov     rbx, [rsp+48h+arg_0]
0x18000f1a4  add     rsp, 30h
0x18000f1a8  pop     rdi
0x18000f1a9  pop     rsi
0x18000f1aa  pop     rbp
0x18000f1ab  retn
```
