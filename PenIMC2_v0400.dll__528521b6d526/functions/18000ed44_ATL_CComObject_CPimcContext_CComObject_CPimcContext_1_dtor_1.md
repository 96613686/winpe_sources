# _ATL::CComObject_CPimcContext_::_CComObject_CPimcContext__::_1_::dtor$1

- ea: `0x18000ed44`
- end: `0x18000ed50`
- name: `_ATL::CComObject_CPimcContext_::_CComObject_CPimcContext__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ecc`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcContext_::_CComObject_CPimcContext__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>((_DWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000ed44  lea     rcx, [rdx+38h]
0x18000ed4b  jmp     ??1?$CComGITPtr@UITablet@@@ATL@@QEAA@XZ
```
