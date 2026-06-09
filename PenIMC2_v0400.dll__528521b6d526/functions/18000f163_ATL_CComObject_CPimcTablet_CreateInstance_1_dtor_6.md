# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$6

- ea: `0x18000f163`
- end: `0x18000f16f`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006258`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x18000f163  lea     rcx, [rdx+70h]
0x18000f16a  jmp     ??1?$CComPtr@VCPimcManager@@@ATL@@QEAA@XZ
```
