# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$3

- ea: `0x18000bbf7`
- end: `0x18000bc03`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002444`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x18000bbf7  lea     rcx, [rdx+30h]
0x18000bbfe  jmp     ??1?$CComPtr@UIObjectContext@@@ATL@@QEAA@XZ; ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(void)
```
