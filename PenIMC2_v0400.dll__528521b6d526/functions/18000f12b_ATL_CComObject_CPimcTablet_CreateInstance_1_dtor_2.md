# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$2

- ea: `0x18000f12b`
- end: `0x18000f13b`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006258`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>((__int64 *)(*(_QWORD *)(a2 + 120) + 16LL));
}

```

## disassembly

```asm
0x18000f12b  mov     rcx, [rdx+78h]
0x18000f132  add     rcx, 10h
0x18000f136  jmp     ??1?$CComPtr@VCPimcManager@@@ATL@@QEAA@XZ; ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>(void)
```
