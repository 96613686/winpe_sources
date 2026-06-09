# _CConfigSource::ProcessElement_::_1_::dtor$2

- ea: `0x180011c73`
- end: `0x180011c7f`
- name: `_CConfigSource::ProcessElement_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008f10`

## pseudocode

```c
__int64 __fastcall CConfigSource::ProcessElement_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::unique_ptr<IMVXMLComparison>::~unique_ptr<IMVXMLComparison>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 208));
}

```

## disassembly

```asm
0x180011c73  lea     rcx, [rdx+0D0h]
0x180011c7a  jmp     ??1?$unique_ptr@VIMVXMLComparison@@U?$default_delete@VIMVXMLComparison@@@std@@@std@@QEAA@XZ; std::unique_ptr<IMVXMLComparison>::~unique_ptr<IMVXMLComparison>(void)
```
