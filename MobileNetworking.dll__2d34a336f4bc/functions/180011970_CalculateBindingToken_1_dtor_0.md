# _CalculateBindingToken_::_1_::dtor$0

- ea: `0x180011970`
- end: `0x18001198f`
- name: `_CalculateBindingToken_::_1_::dtor$0`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000a210`

## pseudocode

```c
void __fastcall CalculateBindingToken_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x180011970  push    rbp
0x180011972  sub     rsp, 20h
0x180011976  mov     rbp, rdx
0x180011979  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180011980  mov     rcx, [rbp+30h]; Block
0x180011984  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011989  add     rsp, 20h
0x18001198d  pop     rbp
0x18001198e  retn
```
