# _ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$3

- ea: `0x18000e5e6`
- end: `0x18000e5f6`
- name: `_ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002220`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComObject_CPimcManager___::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ITabletManager>::~CComPtr<ITabletManager>((__int64 *)(*(_QWORD *)(a2 + 120) + 32LL));
}

```

## disassembly

```asm
0x18000e5e6  mov     rcx, [rdx+78h]
0x18000e5ed  add     rcx, 20h ; ' '
0x18000e5f1  jmp     ??1?$CComPtr@UITabletManager@@@ATL@@QEAA@XZ; ATL::CComPtr<ITabletManager>::~CComPtr<ITabletManager>(void)
```
