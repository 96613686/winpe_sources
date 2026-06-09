# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$3

- ea: `0x14001631a`
- end: `0x140016326`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011cc0`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CRegistry::~CRegistry((CRegistry *)(a2 + 240));
}

```

## disassembly

```asm
0x14001631a  lea     rcx, [rdx+0F0h]; this
0x140016321  jmp     ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
```
