# SetRegistryDword

- ea: `0x18000f290`
- end: `0x18000f2f2`
- name: `SetRegistryDword`
- size: `98`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800175a8`

## callees

- `0x18000f290`
- `0x180016794`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f2d8`
- `KERNEL32!SetLastError` at `0x18000f2d8`
- `ADVAPI32!RegSetValueExW` at `0x18000f2b8`
- `ADVAPI32!RegSetValueExW` at `0x18000f2b8`

## string_xrefs

- `0x18000f2c7`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000f290  mov     r11, rsp
0x18000f293  mov     [r11+8], rbx
0x18000f297  mov     [r11+18h], r8d
0x18000f29b  push    rdi
0x18000f29c  sub     rsp, 30h
0x18000f2a0  mov     r9d, 4; dwType
0x18000f2a6  lea     rax, [r11+18h]
0x18000f2aa  mov     [r11-10h], r9d
0x18000f2ae  xor     r8d, r8d; Reserved
0x18000f2b1  mov     [r11-18h], rax
0x18000f2b5  mov     rdi, rdx
0x18000f2b8  call    cs:__imp_RegSetValueExW
0x18000f2be  mov     ebx, eax
0x18000f2c0  test    eax, eax
0x18000f2c2  jz      short loc_18000F2E2
0x18000f2c4  mov     r8d, eax
0x18000f2c7  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f2ce  mov     rdx, rdi
0x18000f2d1  call    fax_dprintf
0x18000f2d6  mov     ecx, ebx; dwErrCode
0x18000f2d8  call    cs:__imp_SetLastError
0x18000f2de  xor     eax, eax
0x18000f2e0  jmp     short loc_18000F2E7
0x18000f2e2  mov     eax, 1
0x18000f2e7  mov     rbx, [rsp+38h+arg_0]
0x18000f2ec  add     rsp, 30h
0x18000f2f0  pop     rdi
0x18000f2f1  retn
```
