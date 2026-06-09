# _ATL::CComObject_CPimcManager_::_CComObject_CPimcManager__::_1_::dtor$1

- ea: `0x18000e61a`
- end: `0x18000e626`
- name: `_ATL::CComObject_CPimcManager_::_CComObject_CPimcManager__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ecc`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcManager_::_CComObject_CPimcManager__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>((_DWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000e61a  lea     rcx, [rdx+38h]
0x18000e621  jmp     ??1?$CComGITPtr@UITablet@@@ATL@@QEAA@XZ; ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>(void)
```
