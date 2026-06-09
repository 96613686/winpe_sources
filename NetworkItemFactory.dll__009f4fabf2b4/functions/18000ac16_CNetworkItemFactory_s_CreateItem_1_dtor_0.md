# _CNetworkItemFactory::s_CreateItem_::_1_::dtor$0

- ea: `0x18000ac16`
- end: `0x18000ac22`
- name: `_CNetworkItemFactory::s_CreateItem_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800070f4`

## pseudocode

```c
void __fastcall CNetworkItemFactory::s_CreateItem_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x18000ac16  mov     rcx, [rdx+48h]; lpMem
0x18000ac1d  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
