# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$8

- ea: `0x18000f16f`
- end: `0x18000f17b`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x18000f16f  lea     rcx, [rdx+70h]
0x18000f176  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ
```
