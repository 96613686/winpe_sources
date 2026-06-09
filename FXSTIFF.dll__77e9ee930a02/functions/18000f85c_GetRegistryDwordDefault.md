# GetRegistryDwordDefault

- ea: `0x18000f85c`
- end: `0x18000f93a`
- name: `GetRegistryDwordDefault`
- size: `222`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017aa0`
- `0x180017cb0`
- `0x180017f10`
- `0x180018130`

## callees

- `0x18000f85c`
- `0x1800174d8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f91e`
- `KERNEL32!SetLastError` at `0x18000f91e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f8aa`
- `ADVAPI32!RegQueryValueExW` at `0x18000f8aa`
- `ADVAPI32!RegSetValueExW` at `0x18000f8dd`
- `ADVAPI32!RegSetValueExW` at `0x18000f8dd`

## string_xrefs

- `0x18000f8ef`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000f85c  mov     rax, rsp
0x18000f85f  mov     [rax+8], rbx
0x18000f863  mov     [rax+20h], r9d
0x18000f867  push    rbp
0x18000f868  push    rsi
0x18000f869  push    rdi
0x18000f86a  sub     rsp, 30h
0x18000f86e  mov     dword ptr [rax+18h], 4
0x18000f875  mov     rsi, r8
0x18000f878  mov     dword ptr [rax+20h], 0
0x18000f87f  mov     rdi, rdx
0x18000f882  mov     rbp, rcx
0x18000f885  test    r8, r8
0x18000f888  jnz     short loc_18000F893
0x18000f88a  lea     ecx, [r8+57h]; hKey
0x18000f88e  jmp     loc_18000F91E
0x18000f893  lea     rax, [rsp+48h+cbData]
0x18000f898  xor     r8d, r8d; lpReserved
0x18000f89b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000f8a0  lea     r9, [rsp+48h+Type]; lpType
0x18000f8a5  mov     [rsp+48h+lpData], rsi; lpData
0x18000f8aa  call    cs:__imp_RegQueryValueExW
0x18000f8b1  nop     dword ptr [rax+rax+00h]
0x18000f8b6  mov     ebx, eax
0x18000f8b8  cmp     eax, 2
0x18000f8bb  jnz     short loc_18000F8FF
0x18000f8bd  mov     dword ptr [rsp+48h+lpcbData], 4; cbData
0x18000f8c5  lea     r9d, [rax+2]; dwType
0x18000f8c9  xor     r8d, r8d; Reserved
0x18000f8cc  mov     [rsp+48h+lpData], rsi; lpData
0x18000f8d1  mov     rdx, rdi; lpValueName
0x18000f8d4  mov     dword ptr [rsi], 0
0x18000f8da  mov     rcx, rbp; hKey
0x18000f8dd  call    cs:__imp_RegSetValueExW
0x18000f8e4  nop     dword ptr [rax+rax+00h]
0x18000f8e9  mov     ebx, eax
0x18000f8eb  test    eax, eax
0x18000f8ed  jz      short loc_18000F8F8
0x18000f8ef  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f8f6  jmp     short loc_18000F911
0x18000f8f8  mov     eax, 1
0x18000f8fd  jmp     short loc_18000F92C
0x18000f8ff  test    ebx, ebx
0x18000f901  jnz     short loc_18000F90A
0x18000f903  cmp     [rsp+48h+Type], 4
0x18000f908  jz      short loc_18000F8F8
0x18000f90a  lea     rcx, aRegqueryvaluee; "RegQueryValueEx() failed[%s], ec=%d"
0x18000f911  mov     r8d, ebx
0x18000f914  mov     rdx, rdi
0x18000f917  call    fax_dprintf
0x18000f91c  mov     ecx, ebx; dwErrCode
0x18000f91e  call    cs:__imp_SetLastError
0x18000f925  nop     dword ptr [rax+rax+00h]
0x18000f92a  xor     eax, eax
0x18000f92c  mov     rbx, [rsp+48h+arg_0]
0x18000f931  add     rsp, 30h
0x18000f935  pop     rdi
0x18000f936  pop     rsi
0x18000f937  pop     rbp
0x18000f938  retn
```
