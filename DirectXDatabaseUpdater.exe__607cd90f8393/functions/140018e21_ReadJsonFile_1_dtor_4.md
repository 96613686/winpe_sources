# _ReadJsonFile_::_1_::dtor$4

- ea: `0x140018e21`
- end: `0x140018e2d`
- name: `_ReadJsonFile_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011f4c`

## pseudocode

```c
void __fastcall ReadJsonFile_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 400));
}

```

## disassembly

```asm
0x140018e21  lea     rcx, [rdx+190h]; this
0x140018e28  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
