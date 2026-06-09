# _ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$1

- ea: `0x18000e5ca`
- end: `0x18000e5d6`
- name: `_ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002174`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CPimcManager::~CPimcManager(*(CPimcManager **)(a2 + 120));
}

```

## disassembly

```asm
0x18000e5ca  mov     rcx, [rdx+78h]; this
0x18000e5d1  jmp     ??1CPimcManager@@QEAA@XZ; CPimcManager::~CPimcManager(void)
```
