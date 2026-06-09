# _CBrowserFactory::CreateInstance_::_1_::dtor$15

- ea: `0x18000beba`
- end: `0x18000bec6`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$15`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002444`

## pseudocode

```c
__int64 __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x18000beba  lea     rcx, [rdx+58h]
0x18000bec1  jmp     ??1?$CComPtr@UIObjectContext@@@ATL@@QEAA@XZ; ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(void)
```
