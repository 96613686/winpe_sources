# SetRegistryDword

- ea: `0x18002d934`
- end: `0x18002d9a3`
- name: `SetRegistryDword`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028c8c`
- `0x18002aa90`

## callees

- `0x18002d0e4`
- `0x18002d934`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d982`
- `KERNEL32!SetLastError` at `0x18002d982`
- `ADVAPI32!RegSetValueExW` at `0x18002d95c`
- `ADVAPI32!RegSetValueExW` at `0x18002d95c`

## string_xrefs

- `0x18002d971`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18002d934  mov     r11, rsp
0x18002d937  mov     [r11+8], rbx
0x18002d93b  mov     [r11+18h], r8d
0x18002d93f  push    rdi
0x18002d940  sub     rsp, 30h
0x18002d944  mov     r9d, 4; dwType
0x18002d94a  lea     rax, [r11+18h]
0x18002d94e  mov     [r11-10h], r9d
0x18002d952  xor     r8d, r8d; Reserved
0x18002d955  mov     [r11-18h], rax
0x18002d959  mov     rdi, rdx
0x18002d95c  call    cs:__imp_RegSetValueExW
0x18002d963  nop     dword ptr [rax+rax+00h]
0x18002d968  mov     ebx, eax
0x18002d96a  test    eax, eax
0x18002d96c  jz      short loc_18002D992
0x18002d96e  mov     r8d, eax
0x18002d971  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18002d978  mov     rdx, rdi
0x18002d97b  call    fax_dprintf
0x18002d980  mov     ecx, ebx; dwErrCode
0x18002d982  call    cs:__imp_SetLastError
0x18002d989  nop     dword ptr [rax+rax+00h]
0x18002d98e  xor     eax, eax
0x18002d990  jmp     short loc_18002D997
0x18002d992  mov     eax, 1
0x18002d997  mov     rbx, [rsp+38h+arg_0]
0x18002d99c  add     rsp, 30h
0x18002d9a0  pop     rdi
0x18002d9a1  retn
```
