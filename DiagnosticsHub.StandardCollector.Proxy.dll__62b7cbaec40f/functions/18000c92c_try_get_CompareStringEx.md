# try_get_CompareStringEx

- ea: `0x18000c92c`
- end: `0x18000c964`
- name: `try_get_CompareStringEx`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d66c`
- `0x18000e200`
- `0x18000e258`

## callees

- `0x18000c92c`
- `0x18000d058`

## string_xrefs

- `0x18000c945`: `CompareStringEx`
- `0x18000c958`: `CompareStringEx`

## pseudocode

```c
FARPROC try_get_CompareStringEx()
{
  if ( qword_180082008 == -1 )
    return 0;
  if ( qword_180082008 )
    return (FARPROC)qword_180082008;
  return try_get_function_slow(1u, "CompareStringEx", (unsigned int *)"\b", (unsigned int *)"CompareStringEx");
}

```

## disassembly

```asm
0x18000c92c  mov     rcx, cs:qword_180082008
0x18000c933  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c937  jnz     short loc_18000C93C
0x18000c939  xor     eax, eax
0x18000c93b  retn
0x18000c93c  test    rcx, rcx
0x18000c93f  jz      short loc_18000C945
0x18000c941  mov     rax, rcx
0x18000c944  retn
0x18000c945  lea     r9, aComparestringe; "CompareStringEx"
0x18000c94c  mov     ecx, 1
0x18000c951  lea     r8, asc_180067800; "\b"
0x18000c958  lea     rdx, aComparestringe; "CompareStringEx"
0x18000c95f  jmp     try_get_function_slow
```
