# _ATL::CComGITPtr_IUnknown_::_CComGITPtr_IUnknown__::_1_::dtor$3

- ea: `0x18000eade`
- end: `0x18000eaea`
- name: `_ATL::CComGITPtr_IUnknown_::_CComGITPtr_IUnknown__::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComGITPtr_IUnknown_::_CComGITPtr_IUnknown__::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x18000eade  lea     rcx, [rdx+40h]
0x18000eae5  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
