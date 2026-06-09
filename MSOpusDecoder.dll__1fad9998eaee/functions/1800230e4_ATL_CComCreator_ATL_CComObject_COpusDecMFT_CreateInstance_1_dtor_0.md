# _ATL::CComCreator_ATL::CComObject_COpusDecMFT___::CreateInstance_::_1_::dtor$0

- ea: `0x1800230e4`
- end: `0x180023101`
- name: `_ATL::CComCreator_ATL::CComObject_COpusDecMFT___::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_COpusDecMFT___::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x1800230e4  push    rbp
0x1800230e6  sub     rsp, 20h
0x1800230ea  mov     rbp, rdx
0x1800230ed  mov     edx, 140h
0x1800230f2  mov     rcx, [rbp+20h]; Block
0x1800230f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800230fb  add     rsp, 20h
0x1800230ff  pop     rbp
0x180023100  retn
```
