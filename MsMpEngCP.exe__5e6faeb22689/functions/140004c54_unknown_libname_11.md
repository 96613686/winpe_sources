# unknown_libname_11

- ea: `0x140004c54`
- end: `0x140004c95`
- name: `unknown_libname_11`
- size: `65`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004b34`
- `0x140004d54`
- `0x140004d70`
- `0x140004dc8`

## callees

- `0x140004c54`
- `0x140006940`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
void __fastcall unknown_libname_11(void **Block)
{
  void *v1; // rax
  void **v3; // rdi

  if ( Block )
  {
    v1 = *Block;
    v3 = Block;
    while ( v1 )
    {
      free_base(v1);
      v1 = *++v3;
    }
    free_base(Block);
  }
}

```

## disassembly

```asm
0x140004c54  test    rcx, rcx
0x140004c57  jz      short locret_140004C94
0x140004c59  mov     [rsp+arg_0], rbx
0x140004c5e  push    rdi
0x140004c5f  sub     rsp, 20h
0x140004c63  mov     rax, [rcx]
0x140004c66  mov     rbx, rcx
0x140004c69  mov     rdi, rcx
0x140004c6c  jmp     short loc_140004C7D
0x140004c6e  mov     rcx, rax; Block
0x140004c71  call    _free_base
0x140004c76  lea     rdi, [rdi+8]
0x140004c7a  mov     rax, [rdi]
0x140004c7d  test    rax, rax
0x140004c80  jnz     short loc_140004C6E
0x140004c82  mov     rcx, rbx; Block
0x140004c85  call    _free_base
0x140004c8a  mov     rbx, [rsp+28h+arg_0]
0x140004c8f  add     rsp, 20h
0x140004c93  pop     rdi
0x140004c94  retn
```
