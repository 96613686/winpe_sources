# _CProviderRegistrationCache::SelectCert_::_1_::dtor$1

- ea: `0x18001a4c0`
- end: `0x18001a4cc`
- name: `_CProviderRegistrationCache::SelectCert_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::SelectCert_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 256), a2);
}

```

## disassembly

```asm
0x18001a4c0  lea     rcx, [rdx+100h]; this
0x18001a4c7  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
