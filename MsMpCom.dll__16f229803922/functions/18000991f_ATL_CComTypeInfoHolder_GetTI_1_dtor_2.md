# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$2

- ea: `0x18000991f`
- end: `0x18000992b`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002d00`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x18000991f  lea     rcx, [rdx+40h]
0x180009926  jmp     ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
```
