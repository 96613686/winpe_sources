# _ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$4

- ea: `0x18000e58f`
- end: `0x18000e59f`
- name: `_ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$4`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002220`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ITabletManager>::~CComPtr<ITabletManager>((__int64 *)(*(_QWORD *)(a2 + 48) + 32LL));
}

```

## disassembly

```asm
0x18000e58f  mov     rcx, [rdx+30h]
0x18000e596  add     rcx, 20h ; ' '
0x18000e59a  jmp     ??1?$CComPtr@UITabletManager@@@ATL@@QEAA@XZ
```
