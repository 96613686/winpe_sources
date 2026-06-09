# _ATL::CComCreator_ATL::CComAggObject_COpusDecMFT___::CreateInstance_::_1_::dtor$0

- ea: `0x1800230c1`
- end: `0x1800230de`
- name: `_ATL::CComCreator_ATL::CComAggObject_COpusDecMFT___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_COpusDecMFT___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x1800230c1  push    rbp
0x1800230c3  sub     rsp, 20h
0x1800230c7  mov     rbp, rdx
0x1800230ca  mov     edx, 158h
0x1800230cf  mov     rcx, [rbp+28h]; Block
0x1800230d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800230d8  add     rsp, 20h
0x1800230dc  pop     rbp
0x1800230dd  retn
```
