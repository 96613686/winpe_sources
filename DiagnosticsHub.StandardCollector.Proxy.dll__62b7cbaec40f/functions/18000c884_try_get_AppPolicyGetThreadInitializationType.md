# try_get_AppPolicyGetThreadInitializationType

- ea: `0x18000c884`
- end: `0x18000c8bc`
- name: `try_get_AppPolicyGetThreadInitializationType`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000c884`
- `0x18000d058`

## string_xrefs

- `0x18000c8b0`: `AppPolicyGetThreadInitializationType`

## pseudocode

```c
FARPROC try_get_AppPolicyGetThreadInitializationType()
{
  if ( qword_1800820D8 == -1 )
    return 0;
  if ( qword_1800820D8 )
    return (FARPROC)qword_1800820D8;
  return try_get_function_slow(
           0x1Bu,
           "AppPolicyGetThreadInitializationType",
           (unsigned int *)byte_180067B10,
           (unsigned int *)&dword_180067B14);
}

```

## disassembly

```asm
0x18000c884  mov     rcx, cs:qword_1800820D8
0x18000c88b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c88f  jnz     short loc_18000C894
0x18000c891  xor     eax, eax
0x18000c893  retn
0x18000c894  test    rcx, rcx
0x18000c897  jz      short loc_18000C89D
0x18000c899  mov     rax, rcx
0x18000c89c  retn
0x18000c89d  lea     r9, dword_180067B14
0x18000c8a4  mov     ecx, 1Bh
0x18000c8a9  lea     r8, byte_180067B10
0x18000c8b0  lea     rdx, aApppolicygetth; "AppPolicyGetThreadInitializationType"
0x18000c8b7  jmp     try_get_function_slow
```
