# _TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor$1

- ea: `0x18000bd7f`
- end: `0x18000bd8b`
- name: `_TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000742c`

## pseudocode

```c
__int64 __fastcall TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::pair<String,ATL::CComVariant>::~pair<String,ATL::CComVariant>(a2 + 56);
}

```

## disassembly

```asm
0x18000bd7f  lea     rcx, [rdx+38h]
0x18000bd86  jmp     ??1?$pair@VString@@VCComVariant@ATL@@@std@@QEAA@XZ; std::pair<String,ATL::CComVariant>::~pair<String,ATL::CComVariant>(void)
```
