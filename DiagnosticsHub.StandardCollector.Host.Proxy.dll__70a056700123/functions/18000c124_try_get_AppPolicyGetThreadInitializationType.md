# try_get_AppPolicyGetThreadInitializationType

- ea: `0x18000c124`
- end: `0x18000c15c`
- name: `try_get_AppPolicyGetThreadInitializationType`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000c124`
- `0x18000c8f8`

## string_xrefs

- `0x18000c150`: `AppPolicyGetThreadInitializationType`

## pseudocode

```c
FARPROC try_get_AppPolicyGetThreadInitializationType()
{
  if ( qword_18007F0D8 == -1 )
    return 0;
  if ( qword_18007F0D8 )
    return (FARPROC)qword_18007F0D8;
  return try_get_function_slow(
           0x1Bu,
           "AppPolicyGetThreadInitializationType",
           (unsigned int *)byte_180064430,
           (unsigned int *)&dword_180064434);
}

```

## disassembly

```asm
0x18000c124  mov     rcx, cs:qword_18007F0D8
0x18000c12b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c12f  jnz     short loc_18000C134
0x18000c131  xor     eax, eax
0x18000c133  retn
0x18000c134  test    rcx, rcx
0x18000c137  jz      short loc_18000C13D
0x18000c139  mov     rax, rcx
0x18000c13c  retn
0x18000c13d  lea     r9, dword_180064434
0x18000c144  mov     ecx, 1Bh
0x18000c149  lea     r8, byte_180064430
0x18000c150  lea     rdx, aApppolicygetth; "AppPolicyGetThreadInitializationType"
0x18000c157  jmp     try_get_function_slow
```
