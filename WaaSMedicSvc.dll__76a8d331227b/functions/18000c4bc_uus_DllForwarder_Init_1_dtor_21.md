# _uus::DllForwarder::_Init_::_1_::dtor$21

- ea: `0x18000c4bc`
- end: `0x18000c4d9`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$21`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800025d0`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000c4bc  push    rbp
0x18000c4be  sub     rsp, 20h
0x18000c4c2  mov     rbp, rdx
0x18000c4c5  mov     edx, 10h; unsigned __int64
0x18000c4ca  mov     rcx, [rbp+20h]; void *
0x18000c4ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4d3  add     rsp, 20h
0x18000c4d7  pop     rbp
0x18000c4d8  retn
```
