# _PWGRCore::CPWGRStreamWriter::StartDocW_::_1_::dtor$4

- ea: `0x180010071`
- end: `0x18001008e`
- name: `_PWGRCore::CPWGRStreamWriter::StartDocW_::_1_::dtor$4`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001b30`

## pseudocode

```c
void __fastcall PWGRCore::CPWGRStreamWriter::StartDocW_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x180010071  push    rbp
0x180010073  sub     rsp, 20h
0x180010077  mov     rbp, rdx
0x18001007a  mov     edx, 70h ; 'p'; unsigned __int64
0x18001007f  mov     rcx, [rbp+38h]; void *
0x180010083  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010088  add     rsp, 20h
0x18001008c  pop     rbp
0x18001008d  retn
```
