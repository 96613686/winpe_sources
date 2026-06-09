# _ATL::CComCreator_ATL::CComObject_CPimcSurrogate___::CreateInstance_::_1_::dtor$0

- ea: `0x18000e5ab`
- end: `0x18000e5ca`
- name: `_ATL::CComCreator_ATL::CComObject_CPimcSurrogate___::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ce0c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CPimcSurrogate___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
}

```

## disassembly

```asm
0x18000e5ab  push    rbp
0x18000e5ad  sub     rsp, 20h
0x18000e5b1  mov     rbp, rdx
0x18000e5b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000e5bb  mov     rcx, [rbp+78h]; Block
0x18000e5bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e5c4  add     rsp, 20h
0x18000e5c8  pop     rbp
0x18000e5c9  retn
```
