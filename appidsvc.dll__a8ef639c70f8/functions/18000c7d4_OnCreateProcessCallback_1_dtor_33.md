# _OnCreateProcessCallback_::_1_::dtor$33

- ea: `0x18000c7d4`
- end: `0x18000c7e0`
- name: `_OnCreateProcessCallback_::_1_::dtor$33`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006218`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_33(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 152));
}

```

## disassembly

```asm
0x18000c7d4  lea     rcx, [rdx+98h]; this
0x18000c7db  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
