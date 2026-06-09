# _ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$0

- ea: `0x180024d3c`
- end: `0x180024d5b`
- name: `_ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007a90`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x180024d3c  push    rbp
0x180024d3e  sub     rsp, 20h
0x180024d42  mov     rbp, rdx
0x180024d45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180024d4c  mov     rcx, [rbp+28h]; Block
0x180024d50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024d55  add     rsp, 20h
0x180024d59  pop     rbp
0x180024d5a  retn
```
