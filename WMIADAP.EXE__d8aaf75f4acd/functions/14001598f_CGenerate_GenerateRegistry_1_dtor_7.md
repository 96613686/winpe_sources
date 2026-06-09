# _CGenerate::GenerateRegistry_::_1_::dtor$7

- ea: `0x14001598f`
- end: `0x14001599b`
- name: `_CGenerate::GenerateRegistry_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400068c0`

## pseudocode

```c
void __fastcall CGenerate::GenerateRegistry_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  WmiSecurityAttributes::~WmiSecurityAttributes((WmiSecurityAttributes *)(a2 + 136), a2);
}

```

## disassembly

```asm
0x14001598f  lea     rcx, [rdx+88h]; this
0x140015996  jmp     ??1WmiSecurityAttributes@@QEAA@XZ; WmiSecurityAttributes::~WmiSecurityAttributes(void)
```
