# _CRegistrySearch::LocateKeyByNameOrValueName_::_1_::dtor$0

- ea: `0x14001629a`
- end: `0x1400162a6`
- name: `_CRegistrySearch::LocateKeyByNameOrValueName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011cc0`

## pseudocode

```c
void __fastcall CRegistrySearch::LocateKeyByNameOrValueName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CRegistry::~CRegistry((CRegistry *)(a2 + 112));
}

```

## disassembly

```asm
0x14001629a  lea     rcx, [rdx+70h]; this
0x1400162a1  jmp     ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
```
