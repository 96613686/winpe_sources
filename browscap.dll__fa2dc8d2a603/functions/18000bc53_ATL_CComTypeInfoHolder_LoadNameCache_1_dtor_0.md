# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0

- ea: `0x18000bc53`
- end: `0x18000bc5f`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009a30`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 152));
}

```

## disassembly

```asm
0x18000bc53  mov     rcx, [rdx+98h]; void *
0x18000bc5a  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
