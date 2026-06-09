# SetRegistryDword

- ea: `0x18000fa34`
- end: `0x18000faa3`
- name: `SetRegistryDword`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018340`

## callees

- `0x18000fa34`
- `0x1800174d8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fa82`
- `KERNEL32!SetLastError` at `0x18000fa82`
- `ADVAPI32!RegSetValueExW` at `0x18000fa5c`
- `ADVAPI32!RegSetValueExW` at `0x18000fa5c`

## string_xrefs

- `0x18000fa71`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryDword(HKEY a1, const WCHAR *a2, int a3)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v4 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v7, 4u);
  v5 = v4;
  if ( !v4 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", a2, v4);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x18000fa34  mov     r11, rsp
0x18000fa37  mov     [r11+8], rbx
0x18000fa3b  mov     [r11+18h], r8d
0x18000fa3f  push    rdi
0x18000fa40  sub     rsp, 30h
0x18000fa44  mov     r9d, 4; dwType
0x18000fa4a  lea     rax, [r11+18h]
0x18000fa4e  mov     [r11-10h], r9d
0x18000fa52  xor     r8d, r8d; Reserved
0x18000fa55  mov     [r11-18h], rax
0x18000fa59  mov     rdi, rdx
0x18000fa5c  call    cs:__imp_RegSetValueExW
0x18000fa63  nop     dword ptr [rax+rax+00h]
0x18000fa68  mov     ebx, eax
0x18000fa6a  test    eax, eax
0x18000fa6c  jz      short loc_18000FA92
0x18000fa6e  mov     r8d, eax
0x18000fa71  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000fa78  mov     rdx, rdi
0x18000fa7b  call    fax_dprintf
0x18000fa80  mov     ecx, ebx; dwErrCode
0x18000fa82  call    cs:__imp_SetLastError
0x18000fa89  nop     dword ptr [rax+rax+00h]
0x18000fa8e  xor     eax, eax
0x18000fa90  jmp     short loc_18000FA97
0x18000fa92  mov     eax, 1
0x18000fa97  mov     rbx, [rsp+38h+arg_0]
0x18000fa9c  add     rsp, 30h
0x18000faa0  pop     rdi
0x18000faa1  retn
```
