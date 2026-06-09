# try_get_SetThreadStackGuarantee

- ea: `0x18000cea4`
- end: `0x18000cedc`
- name: `try_get_SetThreadStackGuarantee`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cea4`
- `0x18000d058`

## string_xrefs

- `0x18000cebd`: `SetThreadStackGuarantee`
- `0x18000ced0`: `SetThreadStackGuarantee`

## pseudocode

```c
FARPROC try_get_SetThreadStackGuarantee()
{
  if ( qword_1800820F0 == -1 )
    return 0;
  if ( qword_1800820F0 )
    return (FARPROC)qword_1800820F0;
  return try_get_function_slow(
           0x1Eu,
           "SetThreadStackGuarantee",
           (unsigned int *)"\a",
           (unsigned int *)"SetThreadStackGuarantee");
}

```

## disassembly

```asm
0x18000cea4  mov     rcx, cs:qword_1800820F0
0x18000ceab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ceaf  jnz     short loc_18000CEB4
0x18000ceb1  xor     eax, eax
0x18000ceb3  retn
0x18000ceb4  test    rcx, rcx
0x18000ceb7  jz      short loc_18000CEBD
0x18000ceb9  mov     rax, rcx
0x18000cebc  retn
0x18000cebd  lea     r9, aSetthreadstack; "SetThreadStackGuarantee"
0x18000cec4  mov     ecx, 1Eh
0x18000cec9  lea     r8, asc_180067B90; "\a"
0x18000ced0  lea     rdx, aSetthreadstack; "SetThreadStackGuarantee"
0x18000ced7  jmp     try_get_function_slow
```
