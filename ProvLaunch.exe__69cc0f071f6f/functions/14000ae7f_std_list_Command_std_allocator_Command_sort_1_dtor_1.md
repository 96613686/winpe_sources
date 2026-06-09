# _std::list_Command_std::allocator_Command___::sort_::_1_::dtor$1

- ea: `0x14000ae7f`
- end: `0x14000aea9`
- name: `_std::list_Command_std::allocator_Command___::sort_::_1_::dtor$1`
- size: `42`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002228`

## pseudocode

```c
void __fastcall std::list_Command_std::allocator_Command___::sort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  `eh vector destructor iterator'((void *)(a2 + 64), 0x10u, 26, (void (*)(void *))std::list<Command>::~list<Command>);
}

```

## disassembly

```asm
0x14000ae7f  push    rbp
0x14000ae81  sub     rsp, 20h
0x14000ae85  mov     rbp, rdx
0x14000ae88  lea     r9, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x14000ae8f  mov     r8d, 1Ah; unsigned __int64
0x14000ae95  mov     edx, 10h; unsigned __int64
0x14000ae9a  lea     rcx, [rbp+40h]; void *
0x14000ae9e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000aea3  add     rsp, 20h
0x14000aea7  pop     rbp
0x14000aea8  retn
```
