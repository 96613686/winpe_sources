# ADDRESS_CHECK::DeleteAllAddr(int)

- ea: `0x18001cce0`
- end: `0x18001cd0d`
- name: `?DeleteAllAddr@ADDRESS_CHECK@@QEAAHH@Z`
- size: `45`
- prototype: `__int64 __fastcall(ADDRESS_CHECK *__hidden this, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e3dc`
- `0x18000e7e0`
- `0x18000f3b0`
- `0x18000f560`

## callees

- `0x18001cc10`
- `0x18001cce0`

## pseudocode

```c
__int64 __fastcall ADDRESS_CHECK::DeleteAllAddr(ADDRESS_CHECK *this, int a2)
{
  while ( (unsigned int)ADDRESS_CHECK::DeleteAddr(this, a2) )
    ;
  return 1;
}

```

## disassembly

```asm
0x18001cce0  mov     [rsp+arg_0], rbx
0x18001cce5  push    rdi
0x18001cce6  sub     rsp, 20h
0x18001ccea  mov     ebx, edx
0x18001ccec  mov     rdi, rcx
0x18001ccef  mov     edx, ebx; int
0x18001ccf1  mov     rcx, rdi; this
0x18001ccf4  call    ?DeleteAddr@ADDRESS_CHECK@@QEAAHHK@Z; ADDRESS_CHECK::DeleteAddr(int,ulong)
0x18001ccf9  test    eax, eax
0x18001ccfb  jnz     short loc_18001CCEF
0x18001ccfd  mov     rbx, [rsp+28h+arg_0]
0x18001cd02  mov     eax, 1
0x18001cd07  add     rsp, 20h
0x18001cd0b  pop     rdi
0x18001cd0c  retn
```
