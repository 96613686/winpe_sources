# try_get_GetTempPath2W

- ea: `0x18000c434`
- end: `0x18000c46c`
- name: `try_get_GetTempPath2W`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c434`
- `0x18000c8f8`

## string_xrefs

- `0x18000c44d`: `GetTempPath2W`
- `0x18000c460`: `GetTempPath2W`

## pseudocode

```c
FARPROC try_get_GetTempPath2W()
{
  if ( qword_18007F030 == -1 )
    return 0;
  if ( qword_18007F030 )
    return (FARPROC)qword_18007F030;
  return try_get_function_slow(6u, "GetTempPath2W", (unsigned int *)&qword_1800641A0, (unsigned int *)"GetTempPath2W");
}

```

## disassembly

```asm
0x18000c434  mov     rcx, cs:qword_18007F030
0x18000c43b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c43f  jnz     short loc_18000C444
0x18000c441  xor     eax, eax
0x18000c443  retn
0x18000c444  test    rcx, rcx
0x18000c447  jz      short loc_18000C44D
0x18000c449  mov     rax, rcx
0x18000c44c  retn
0x18000c44d  lea     r9, aGettemppath2w; "GetTempPath2W"
0x18000c454  mov     ecx, 6
0x18000c459  lea     r8, qword_1800641A0
0x18000c460  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18000c467  jmp     try_get_function_slow
```
