# _ATL::CComQIPtr_ITablet2_&IID_ITablet2_::_CComQIPtr_ITablet2_&IID_ITablet2__::_1_::dtor$1

- ea: `0x18000ec16`
- end: `0x18000ec22`
- name: `_ATL::CComQIPtr_ITablet2_&IID_ITablet2_::_CComQIPtr_ITablet2_&IID_ITablet2__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComQIPtr_ITablet2__IID_ITablet2_::_CComQIPtr_ITablet2__IID_ITablet2__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 48));
}

```

## disassembly

```asm
0x18000ec16  mov     rcx, [rdx+30h]
0x18000ec1d  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
