# _CNetworkExplorerFolder::CreateViewObject_::_1_::dtor$0

- ea: `0x18000f1c0`
- end: `0x18000f1cc`
- name: `_CNetworkExplorerFolder::CreateViewObject_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800026f0`

## pseudocode

```c
void __fastcall CNetworkExplorerFolder::CreateViewObject_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000f1c0  mov     rcx, [rdx+20h]; lpMem
0x18000f1c7  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
