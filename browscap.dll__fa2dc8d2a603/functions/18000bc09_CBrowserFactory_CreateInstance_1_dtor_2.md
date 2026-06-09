# _CBrowserFactory::CreateInstance_::_1_::dtor$2

- ea: `0x18000bc09`
- end: `0x18000bc15`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002444`

## pseudocode

```c
__int64 __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x18000bc09  lea     rcx, [rdx+48h]
0x18000bc10  jmp     ??1?$CComPtr@UIObjectContext@@@ATL@@QEAA@XZ; ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(void)
```
