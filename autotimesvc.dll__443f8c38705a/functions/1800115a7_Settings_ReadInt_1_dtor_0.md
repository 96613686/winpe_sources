# _Settings::ReadInt_::_1_::dtor$0

- ea: `0x1800115a7`
- end: `0x1800115b3`
- name: `_Settings::ReadInt_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000dfa8`

## pseudocode

```c
void __fastcall Settings::ReadInt_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegKey::~RegKey((RegKey *)(a2 + 48));
}

```

## disassembly

```asm
0x1800115a7  lea     rcx, [rdx+30h]; this
0x1800115ae  jmp     ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
```
