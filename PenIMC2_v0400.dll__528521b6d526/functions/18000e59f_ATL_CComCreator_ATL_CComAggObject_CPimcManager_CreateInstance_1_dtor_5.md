# _ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$5

- ea: `0x18000e59f`
- end: `0x18000e5ab`
- name: `_ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor_5(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 56));
}

```

## disassembly

```asm
0x18000e59f  mov     rcx, [rdx+38h]
0x18000e5a6  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
