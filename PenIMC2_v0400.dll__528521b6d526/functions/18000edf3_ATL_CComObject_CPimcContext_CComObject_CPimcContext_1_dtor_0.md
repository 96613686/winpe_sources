# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$0

- ea: `0x18000edf3`
- end: `0x18000edff`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a064`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CPimcContext::~CPimcContext(*(CPimcContext **)(a2 + 64));
}

```

## disassembly

```asm
0x18000edf3  mov     rcx, [rdx+40h]; this
0x18000edfa  jmp     ??1CPimcContext@@QEAA@XZ; CPimcContext::~CPimcContext(void)
```
