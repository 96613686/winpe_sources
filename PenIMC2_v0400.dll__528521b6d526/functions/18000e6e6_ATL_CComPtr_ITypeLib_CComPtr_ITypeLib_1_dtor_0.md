# _ATL::CComPtr_ITypeLib_::_CComPtr_ITypeLib__::_1_::dtor$0

- ea: `0x18000e6e6`
- end: `0x18000e6f2`
- name: `_ATL::CComPtr_ITypeLib_::_CComPtr_ITypeLib__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr_ITypeLib_::_CComPtr_ITypeLib__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 48));
}

```

## disassembly

```asm
0x18000e6e6  mov     rcx, [rdx+30h]
0x18000e6ed  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
