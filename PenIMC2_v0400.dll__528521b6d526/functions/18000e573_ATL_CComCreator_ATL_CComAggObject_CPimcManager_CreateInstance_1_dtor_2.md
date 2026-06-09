# _ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$2

- ea: `0x18000e573`
- end: `0x18000e57f`
- name: `_ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002174`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  CPimcManager::~CPimcManager(*(CPimcManager **)(a2 + 48));
}

```

## disassembly

```asm
0x18000e573  mov     rcx, [rdx+30h]; this
0x18000e57a  jmp     ??1CPimcManager@@QEAA@XZ; CPimcManager::~CPimcManager(void)
```
