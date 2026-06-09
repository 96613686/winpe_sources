# try_get_GetTempPath2W

- ea: `0x18000cb94`
- end: `0x18000cbcc`
- name: `try_get_GetTempPath2W`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb94`
- `0x18000d058`

## string_xrefs

- `0x18000cbad`: `GetTempPath2W`
- `0x18000cbc0`: `GetTempPath2W`

## pseudocode

```c
FARPROC try_get_GetTempPath2W()
{
  if ( qword_180082030 == -1 )
    return 0;
  if ( qword_180082030 )
    return (FARPROC)qword_180082030;
  return try_get_function_slow(6u, "GetTempPath2W", (unsigned int *)&qword_180067880, (unsigned int *)"GetTempPath2W");
}

```

## disassembly

```asm
0x18000cb94  mov     rcx, cs:qword_180082030
0x18000cb9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb9f  jnz     short loc_18000CBA4
0x18000cba1  xor     eax, eax
0x18000cba3  retn
0x18000cba4  test    rcx, rcx
0x18000cba7  jz      short loc_18000CBAD
0x18000cba9  mov     rax, rcx
0x18000cbac  retn
0x18000cbad  lea     r9, aGettemppath2w; "GetTempPath2W"
0x18000cbb4  mov     ecx, 6
0x18000cbb9  lea     r8, qword_180067880
0x18000cbc0  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18000cbc7  jmp     try_get_function_slow
```
