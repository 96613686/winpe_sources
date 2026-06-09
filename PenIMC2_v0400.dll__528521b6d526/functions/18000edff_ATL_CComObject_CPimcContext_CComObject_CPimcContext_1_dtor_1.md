# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$1

- ea: `0x18000edff`
- end: `0x18000ee1c`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$1`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ce0c`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000edff  push    rbp
0x18000ee01  sub     rsp, 20h
0x18000ee05  mov     rbp, rdx
0x18000ee08  mov     edx, 10h
0x18000ee0d  mov     rcx, [rbp+50h]; Block
0x18000ee11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ee16  add     rsp, 20h
0x18000ee1a  pop     rbp
0x18000ee1b  retn
```
