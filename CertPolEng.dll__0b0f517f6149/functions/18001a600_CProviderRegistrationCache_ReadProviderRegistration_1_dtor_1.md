# _CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$1

- ea: `0x18001a600`
- end: `0x18001a60c`
- name: `_CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 184), a2);
}

```

## disassembly

```asm
0x18001a600  lea     rcx, [rdx+0B8h]; this
0x18001a607  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
