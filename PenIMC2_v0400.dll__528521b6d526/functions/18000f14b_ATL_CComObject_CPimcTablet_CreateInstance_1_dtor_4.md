# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$4

- ea: `0x18000f14b`
- end: `0x18000f157`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 112));
}

```

## disassembly

```asm
0x18000f14b  mov     rcx, [rdx+70h]
0x18000f152  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ
```
