# _ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$7

- ea: `0x18000f0a7`
- end: `0x18000f0b3`
- name: `_ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ecc`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>((_DWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000f0a7  lea     rcx, [rdx+38h]
0x18000f0ae  jmp     ??1?$CComGITPtr@UITablet@@@ATL@@QEAA@XZ; ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>(void)
```
