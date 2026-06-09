# try_get_CompareStringEx

- ea: `0x18000c1cc`
- end: `0x18000c204`
- name: `try_get_CompareStringEx`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cf0c`
- `0x18000daa0`
- `0x18000daf8`

## callees

- `0x18000c1cc`
- `0x18000c8f8`

## string_xrefs

- `0x18000c1e5`: `CompareStringEx`
- `0x18000c1f8`: `CompareStringEx`

## pseudocode

```c
FARPROC try_get_CompareStringEx()
{
  if ( qword_18007F008 == -1 )
    return 0;
  if ( qword_18007F008 )
    return (FARPROC)qword_18007F008;
  return try_get_function_slow(1u, "CompareStringEx", (unsigned int *)"\b", (unsigned int *)"CompareStringEx");
}

```

## disassembly

```asm
0x18000c1cc  mov     rcx, cs:qword_18007F008
0x18000c1d3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c1d7  jnz     short loc_18000C1DC
0x18000c1d9  xor     eax, eax
0x18000c1db  retn
0x18000c1dc  test    rcx, rcx
0x18000c1df  jz      short loc_18000C1E5
0x18000c1e1  mov     rax, rcx
0x18000c1e4  retn
0x18000c1e5  lea     r9, aComparestringe; "CompareStringEx"
0x18000c1ec  mov     ecx, 1
0x18000c1f1  lea     r8, asc_180064120; "\b"
0x18000c1f8  lea     rdx, aComparestringe; "CompareStringEx"
0x18000c1ff  jmp     try_get_function_slow
```
