# ADDRESS_CHECK::DeleteAllName(int)

- ea: `0x18001cd14`
- end: `0x18001cd41`
- name: `?DeleteAllName@ADDRESS_CHECK@@QEAAHH@Z`
- size: `45`
- prototype: `__int64 __fastcall(ADDRESS_CHECK *__hidden this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e3dc`
- `0x18000f040`
- `0x18000f1e0`

## callees

- `0x18001cd14`
- `0x18001cd48`

## pseudocode

```c
__int64 __fastcall ADDRESS_CHECK::DeleteAllName(ADDRESS_CHECK *this, int a2)
{
  while ( (unsigned int)ADDRESS_CHECK::DeleteName(this, a2) )
    ;
  return 1;
}

```

## disassembly

```asm
0x18001cd14  mov     [rsp+arg_0], rbx
0x18001cd19  push    rdi
0x18001cd1a  sub     rsp, 20h
0x18001cd1e  mov     ebx, edx
0x18001cd20  mov     rdi, rcx
0x18001cd23  mov     edx, ebx; int
0x18001cd25  mov     rcx, rdi; this
0x18001cd28  call    ?DeleteName@ADDRESS_CHECK@@QEAAHHK@Z; ADDRESS_CHECK::DeleteName(int,ulong)
0x18001cd2d  test    eax, eax
0x18001cd2f  jnz     short loc_18001CD23
0x18001cd31  mov     rbx, [rsp+28h+arg_0]
0x18001cd36  mov     eax, 1
0x18001cd3b  add     rsp, 20h
0x18001cd3f  pop     rdi
0x18001cd40  retn
```
