# _CProviderRegistrationCache::RefreshProvCache_::_1_::dtor$0

- ea: `0x18001a5a0`
- end: `0x18001a5ac`
- name: `_CProviderRegistrationCache::RefreshProvCache_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::RefreshProvCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 112), a2);
}

```

## disassembly

```asm
0x18001a5a0  lea     rcx, [rdx+70h]; this
0x18001a5a7  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
