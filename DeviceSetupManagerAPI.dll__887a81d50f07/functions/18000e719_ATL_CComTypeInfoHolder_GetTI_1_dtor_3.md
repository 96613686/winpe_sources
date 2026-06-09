# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$3

- ea: `0x18000e719`
- end: `0x18000e725`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009ec8`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x18000e719  lea     rcx, [rdx+30h]
0x18000e720  jmp     ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
```
