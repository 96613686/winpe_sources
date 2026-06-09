# _fileno

- ea: `0x14000aa1c`
- end: `0x14000aa43`
- name: `_fileno`
- size: `39`
- prototype: `int __cdecl(FILE *Stream)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a0d0`
- `0x14000a15c`
- `0x14000c6dc`

## callees

- `0x140006544`
- `0x14000689c`
- `0x14000aa1c`

## pseudocode

```c
int __cdecl fileno(FILE *Stream)
{
  if ( Stream )
    return Stream->_flag;
  *(_DWORD *)sub_14000689C() = 22;
  invalid_parameter_noinfo();
  return -1;
}

```

## disassembly

```asm
0x14000aa1c  sub     rsp, 28h
0x14000aa20  test    rcx, rcx
0x14000aa23  jnz     short loc_14000AA3A
0x14000aa25  call    sub_14000689C
0x14000aa2a  mov     dword ptr [rax], 16h
0x14000aa30  call    _invalid_parameter_noinfo
0x14000aa35  or      eax, 0FFFFFFFFh
0x14000aa38  jmp     short loc_14000AA3E
0x14000aa3a  mov     eax, [rcx+18h]
0x14000aa3d  nop
0x14000aa3e  add     rsp, 28h
0x14000aa42  retn
```
