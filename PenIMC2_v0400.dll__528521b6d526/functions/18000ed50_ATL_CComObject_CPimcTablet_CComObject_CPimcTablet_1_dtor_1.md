# _ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$1

- ea: `0x18000ed50`
- end: `0x18000ed5c`
- name: `_ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006258`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18000ed50  lea     rcx, [rdx+38h]
0x18000ed57  jmp     ??1?$CComPtr@VCPimcManager@@@ATL@@QEAA@XZ
```
