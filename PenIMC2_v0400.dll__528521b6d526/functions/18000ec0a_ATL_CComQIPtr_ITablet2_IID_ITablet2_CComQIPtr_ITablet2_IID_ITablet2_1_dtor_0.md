# _ATL::CComQIPtr_ITablet2_&IID_ITablet2_::_CComQIPtr_ITablet2_&IID_ITablet2__::_1_::dtor$0

- ea: `0x18000ec0a`
- end: `0x18000ec16`
- name: `_ATL::CComQIPtr_ITablet2_&IID_ITablet2_::_CComQIPtr_ITablet2_&IID_ITablet2__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008d28`

## pseudocode

```c
__int64 __fastcall ATL::CComQIPtr_ITablet2__IID_ITablet2_::_CComQIPtr_ITablet2__IID_ITablet2__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(*(__int64 **)(a2 + 48));
}

```

## disassembly

```asm
0x18000ec0a  mov     rcx, [rdx+30h]
0x18000ec11  jmp     ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
```
