# _ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$3

- ea: `0x18000ed5c`
- end: `0x18000ed68`
- name: `_ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18000ed5c  lea     rcx, [rdx+38h]
0x18000ed63  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ
```
