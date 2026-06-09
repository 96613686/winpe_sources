# GetRegistryDwordDefault

- ea: `0x140074cb4`
- end: `0x140074d99`
- name: `GetRegistryDwordDefault`
- size: `229`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400246b0`
- `0x140025934`
- `0x14003b300`
- `0x140053e5c`
- `0x14007f8d0`
- `0x14007fb00`
- `0x14007fd80`
- `0x140080050`
- `0x1400815a0`
- `0x1400821e4`
- `0x140082538`
- `0x140082830`
- `0x140083420`

## callees

- `0x140074cb4`
- `0x140076758`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140074d36`
- `ADVAPI32!RegSetValueExW` at `0x140074d36`
- `ADVAPI32!RegQueryValueExW` at `0x140074d06`
- `ADVAPI32!RegQueryValueExW` at `0x140074d06`
- `KERNEL32!SetLastError` at `0x140074d77`
- `KERNEL32!SetLastError` at `0x140074d77`

## string_xrefs

- `0x140074d48`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall GetRegistryDwordDefault(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData, int a4)
{
  DWORD v8; // ecx
  unsigned int v9; // ebx
  DWORD cbData[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF

  cbData[0] = 4;
  Type = 0;
  if ( lpData )
  {
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, cbData);
    if ( v9 == 2 )
    {
      *(_DWORD *)lpData = a4;
      v9 = RegSetValueExW(hKey, lpValueName, 0, 4u, lpData, 4u);
      if ( v9 )
      {
        fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v9);
LABEL_10:
        v8 = v9;
        goto LABEL_11;
      }
    }
    else if ( v9 || Type != 4 )
    {
      fax_dprintf(L"RegQueryValueEx() failed[%s], ec=%d", lpValueName, v9);
      goto LABEL_10;
    }
    return 1;
  }
  v8 = 87;
LABEL_11:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x140074cb4  mov     rax, rsp
0x140074cb7  mov     [rax+8], rbx
0x140074cbb  mov     [rax+10h], rbp
0x140074cbf  push    rsi
0x140074cc0  push    rdi
0x140074cc1  push    r14
0x140074cc3  sub     rsp, 40h
0x140074cc7  mov     dword ptr [rax-28h], 4
0x140074cce  mov     r14d, r9d
0x140074cd1  mov     dword ptr [rax+18h], 0
0x140074cd8  mov     rsi, r8
0x140074cdb  mov     rdi, rdx
0x140074cde  mov     rbp, rcx
0x140074ce1  test    r8, r8
0x140074ce4  jnz     short loc_140074CEF
0x140074ce6  lea     ecx, [r8+57h]; hKey
0x140074cea  jmp     loc_140074D77
0x140074cef  lea     rax, [rsp+58h+cbData]
0x140074cf4  xor     r8d, r8d; lpReserved
0x140074cf7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140074cfc  lea     r9, [rsp+58h+Type]; lpType
0x140074d01  mov     [rsp+58h+lpData], rsi; lpData
0x140074d06  call    cs:__imp_RegQueryValueExW
0x140074d0d  nop     dword ptr [rax+rax+00h]
0x140074d12  mov     ebx, eax
0x140074d14  cmp     eax, 2
0x140074d17  jnz     short loc_140074D58
0x140074d19  mov     dword ptr [rsp+58h+lpcbData], 4; cbData
0x140074d21  lea     r9d, [rax+2]; dwType
0x140074d25  xor     r8d, r8d; Reserved
0x140074d28  mov     [rsp+58h+lpData], rsi; lpData
0x140074d2d  mov     rdx, rdi; lpValueName
0x140074d30  mov     [rsi], r14d
0x140074d33  mov     rcx, rbp; hKey
0x140074d36  call    cs:__imp_RegSetValueExW
0x140074d3d  nop     dword ptr [rax+rax+00h]
0x140074d42  mov     ebx, eax
0x140074d44  test    eax, eax
0x140074d46  jz      short loc_140074D51
0x140074d48  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x140074d4f  jmp     short loc_140074D6A
0x140074d51  mov     eax, 1
0x140074d56  jmp     short loc_140074D85
0x140074d58  test    ebx, ebx
0x140074d5a  jnz     short loc_140074D63
0x140074d5c  cmp     [rsp+58h+Type], 4
0x140074d61  jz      short loc_140074D51
0x140074d63  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed[%s], ec=%d"
0x140074d6a  mov     r8d, ebx
0x140074d6d  mov     rdx, rdi
0x140074d70  call    fax_dprintf
0x140074d75  mov     ecx, ebx; dwErrCode
0x140074d77  call    cs:__imp_SetLastError
0x140074d7e  nop     dword ptr [rax+rax+00h]
0x140074d83  xor     eax, eax
0x140074d85  mov     rbx, [rsp+58h+arg_0]
0x140074d8a  mov     rbp, [rsp+58h+arg_8]
0x140074d8f  add     rsp, 40h
0x140074d93  pop     r14
0x140074d95  pop     rdi
0x140074d96  pop     rsi
0x140074d97  retn
```
