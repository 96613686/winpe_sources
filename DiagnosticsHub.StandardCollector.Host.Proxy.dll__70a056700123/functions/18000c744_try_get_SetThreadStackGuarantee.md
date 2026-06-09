# try_get_SetThreadStackGuarantee

- ea: `0x18000c744`
- end: `0x18000c77c`
- name: `try_get_SetThreadStackGuarantee`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c744`
- `0x18000c8f8`

## string_xrefs

- `0x18000c75d`: `SetThreadStackGuarantee`
- `0x18000c770`: `SetThreadStackGuarantee`

## pseudocode

```c
FARPROC try_get_SetThreadStackGuarantee()
{
  if ( qword_18007F0F0 == -1 )
    return 0;
  if ( qword_18007F0F0 )
    return (FARPROC)qword_18007F0F0;
  return try_get_function_slow(
           0x1Eu,
           "SetThreadStackGuarantee",
           (unsigned int *)"\a",
           (unsigned int *)"SetThreadStackGuarantee");
}

```

## disassembly

```asm
0x18000c744  mov     rcx, cs:qword_18007F0F0
0x18000c74b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c74f  jnz     short loc_18000C754
0x18000c751  xor     eax, eax
0x18000c753  retn
0x18000c754  test    rcx, rcx
0x18000c757  jz      short loc_18000C75D
0x18000c759  mov     rax, rcx
0x18000c75c  retn
0x18000c75d  lea     r9, aSetthreadstack; "SetThreadStackGuarantee"
0x18000c764  mov     ecx, 1Eh
0x18000c769  lea     r8, asc_1800644B0; "\a"
0x18000c770  lea     rdx, aSetthreadstack; "SetThreadStackGuarantee"
0x18000c777  jmp     try_get_function_slow
```
