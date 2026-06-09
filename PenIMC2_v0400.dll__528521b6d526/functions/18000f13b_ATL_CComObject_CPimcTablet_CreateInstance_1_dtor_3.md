# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$3

- ea: `0x18000f13b`
- end: `0x18000f14b`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000814c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITablet>::~CComPtr<ITablet>((__int64 *)(*(_QWORD *)(a2 + 120) + 24LL));
}

```

## disassembly

```asm
0x18000f13b  mov     rcx, [rdx+78h]
0x18000f142  add     rcx, 18h
0x18000f146  jmp     ??1?$CComPtr@UITablet@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet>::~CComPtr<ITablet>(void)
```
