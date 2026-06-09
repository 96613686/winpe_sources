# _ATL::CComObject_CPimcContext_::CreateInstance_::_1_::dtor$0

- ea: `0x18000edb0`
- end: `0x18000edcf`
- name: `_ATL::CComObject_CPimcContext_::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ce0c`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcContext_::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000edb0  push    rbp
0x18000edb2  sub     rsp, 20h
0x18000edb6  mov     rbp, rdx
0x18000edb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000edc0  mov     rcx, [rbp+50h]; Block
0x18000edc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000edc9  add     rsp, 20h
0x18000edcd  pop     rbp
0x18000edce  retn
```
