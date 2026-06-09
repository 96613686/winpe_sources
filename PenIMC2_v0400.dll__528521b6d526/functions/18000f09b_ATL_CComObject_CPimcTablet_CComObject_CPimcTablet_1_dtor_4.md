# _ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$4

- ea: `0x18000f09b`
- end: `0x18000f0a7`
- name: `_ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000814c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITablet>::~CComPtr<ITablet>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18000f09b  lea     rcx, [rdx+38h]
0x18000f0a2  jmp     ??1?$CComPtr@UITablet@@@ATL@@QEAA@XZ
```
