# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$4

- ea: `0x18000ee3c`
- end: `0x18000ee4c`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$4`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000627c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>((__int64 *)(*(_QWORD *)(a2 + 64) + 32LL));
}

```

## disassembly

```asm
0x18000ee3c  mov     rcx, [rdx+40h]
0x18000ee43  add     rcx, 20h ; ' '
0x18000ee47  jmp     ??1?$CComPtr@UITabletContextP@@@ATL@@QEAA@XZ
```
