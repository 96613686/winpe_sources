# _ATL::CComCreator_ATL::CComAggObject_CBrowserCap___::CreateInstance_::_1_::dtor$0

- ea: `0x18000bb9d`
- end: `0x18000bba9`
- name: `_ATL::CComCreator_ATL::CComAggObject_CBrowserCap___::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009a30`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CBrowserCap___::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000bb9d  mov     rcx, [rdx+28h]; void *
0x18000bba4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
