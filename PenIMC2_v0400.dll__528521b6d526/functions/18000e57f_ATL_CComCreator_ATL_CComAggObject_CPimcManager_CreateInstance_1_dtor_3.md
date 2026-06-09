# _ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$3

- ea: `0x18000e57f`
- end: `0x18000e58f`
- name: `_ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002264`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(*(_QWORD *)(a2 + 48) + 16LL);
}

```

## disassembly

```asm
0x18000e57f  mov     rcx, [rdx+30h]
0x18000e586  add     rcx, 10h
0x18000e58a  jmp     ??1?$CPbList@UCHookWindowItem@CPimcManager@@@@QEAA@XZ; CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(void)
```
