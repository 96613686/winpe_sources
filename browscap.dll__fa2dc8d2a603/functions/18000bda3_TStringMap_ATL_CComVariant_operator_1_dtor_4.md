# _TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor$4

- ea: `0x18000bda3`
- end: `0x18000bdaf`
- name: `_TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800024cc`

## pseudocode

```c
void __fastcall TStringMap_ATL::CComVariant_::operator[]_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  String::~String(*(String **)(a2 + 152));
}

```

## disassembly

```asm
0x18000bda3  mov     rcx, [rdx+98h]; this
0x18000bdaa  jmp     ??1String@@QEAA@XZ; String::~String(void)
```
