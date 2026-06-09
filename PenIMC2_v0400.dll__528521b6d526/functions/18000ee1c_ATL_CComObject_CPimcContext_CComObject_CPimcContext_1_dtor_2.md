# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$2

- ea: `0x18000ee1c`
- end: `0x18000ee2c`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006234`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<CPimcContext::CEventSink>::~CComPtr<CPimcContext::CEventSink>((__int64 *)(*(_QWORD *)(a2 + 64)
                                                                                              + 16LL));
}

```

## disassembly

```asm
0x18000ee1c  mov     rcx, [rdx+40h]
0x18000ee23  add     rcx, 10h
0x18000ee27  jmp     ??1?$CComPtr@VCEventSink@CPimcContext@@@ATL@@QEAA@XZ; ATL::CComPtr<CPimcContext::CEventSink>::~CComPtr<CPimcContext::CEventSink>(void)
```
