# try_get_CompareStringEx

- ea: `0x140015cc8`
- end: `0x140015d00`
- name: `try_get_CompareStringEx`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015f10`

## callees

- `0x140015cc8`
- `0x140015d00`

## string_xrefs

- `0x140015ce1`: `CompareStringEx`
- `0x140015cf4`: `CompareStringEx`

## pseudocode

```c
FARPROC try_get_CompareStringEx()
{
  if ( qword_140041008 == -1 )
    return 0;
  if ( qword_140041008 )
    return (FARPROC)qword_140041008;
  return try_get_function_slow(1u, "CompareStringEx", (unsigned int *)L"\b", (unsigned int *)"CompareStringEx");
}

```

## disassembly

```asm
0x140015cc8  mov     rcx, cs:qword_140041008
0x140015ccf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140015cd3  jnz     short loc_140015CD8
0x140015cd5  xor     eax, eax
0x140015cd7  retn
0x140015cd8  test    rcx, rcx
0x140015cdb  jz      short loc_140015CE1
0x140015cdd  mov     rax, rcx
0x140015ce0  retn
0x140015ce1  lea     r9, aComparestringe; "CompareStringEx"
0x140015ce8  mov     ecx, 1
0x140015ced  lea     r8, asc_14002B688; "\b"
0x140015cf4  lea     rdx, aComparestringe; "CompareStringEx"
0x140015cfb  jmp     $+5
```
