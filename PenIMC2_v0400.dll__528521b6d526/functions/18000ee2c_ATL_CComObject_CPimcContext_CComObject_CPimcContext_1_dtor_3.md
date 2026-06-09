# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$3

- ea: `0x18000ee2c`
- end: `0x18000ee3c`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006258`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>((__int64 *)(*(_QWORD *)(a2 + 64) + 24LL));
}

```

## disassembly

```asm
0x18000ee2c  mov     rcx, [rdx+40h]
0x18000ee33  add     rcx, 18h
0x18000ee37  jmp     ??1?$CComPtr@VCPimcManager@@@ATL@@QEAA@XZ; ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>(void)
```
