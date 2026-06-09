# _ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$2

- ea: `0x18000ea96`
- end: `0x18000eaa2`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 104));
}

```

## disassembly

```asm
0x18000ea96  mov     rcx, [rdx+68h]
0x18000ea9d  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
