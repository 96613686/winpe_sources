# _ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$0

- ea: `0x180024d89`
- end: `0x180024da8`
- name: `_ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007a90`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x180024d89  push    rbp
0x180024d8b  sub     rsp, 20h
0x180024d8f  mov     rbp, rdx
0x180024d92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180024d99  mov     rcx, [rbp+20h]; Block
0x180024d9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024da2  add     rsp, 20h
0x180024da6  pop     rbp
0x180024da7  retn
```
