# _ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$7

- ea: `0x18000ee64`
- end: `0x18000ee70`
- name: `_ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CPimcContext_::CComObject_CPimcContext__::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(*(__int64 **)(a2 + 40));
}

```

## disassembly

```asm
0x18000ee64  mov     rcx, [rdx+28h]
0x18000ee6b  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
