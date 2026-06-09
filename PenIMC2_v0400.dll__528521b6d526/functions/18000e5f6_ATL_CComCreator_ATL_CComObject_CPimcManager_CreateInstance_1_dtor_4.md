# _ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$4

- ea: `0x18000e5f6`
- end: `0x18000e602`
- name: `_ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 40));
}

```

## disassembly

```asm
0x18000e5f6  mov     rcx, [rdx+28h]
0x18000e5fd  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
