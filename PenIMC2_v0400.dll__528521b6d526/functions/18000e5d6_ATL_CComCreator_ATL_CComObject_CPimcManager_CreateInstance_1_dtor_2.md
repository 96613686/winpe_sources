# _ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$2

- ea: `0x18000e5d6`
- end: `0x18000e5e6`
- name: `_ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002264`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(*(_QWORD *)(a2 + 120) + 16LL);
}

```

## disassembly

```asm
0x18000e5d6  mov     rcx, [rdx+78h]
0x18000e5dd  add     rcx, 10h
0x18000e5e1  jmp     ??1?$CPbList@UCHookWindowItem@CPimcManager@@@@QEAA@XZ; CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(void)
```
