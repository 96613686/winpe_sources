# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0

- ea: `0x180009955`
- end: `0x180009963`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000995c`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete[](*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x180009955  mov     rcx, [rdx+50h]
0x18000995c  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
