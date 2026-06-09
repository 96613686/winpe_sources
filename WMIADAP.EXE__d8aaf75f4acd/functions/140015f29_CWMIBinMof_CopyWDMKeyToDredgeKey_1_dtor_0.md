# _CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$0

- ea: `0x140015f29`
- end: `0x140015f35`
- name: `_CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011cc0`

## pseudocode

```c
void __fastcall CWMIBinMof::CopyWDMKeyToDredgeKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CRegistry::~CRegistry((CRegistry *)(a2 + 816));
}

```

## disassembly

```asm
0x140015f29  lea     rcx, [rdx+330h]; this
0x140015f30  jmp     ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
```
