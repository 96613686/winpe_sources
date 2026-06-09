# _CBrowserFactory::CreateInstance_::_1_::dtor$16

- ea: `0x18000bbe5`
- end: `0x18000bbf1`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002444`

## pseudocode

```c
__int64 __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x18000bbe5  lea     rcx, [rdx+40h]
0x18000bbec  jmp     ??1?$CComPtr@UIObjectContext@@@ATL@@QEAA@XZ; ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(void)
```
