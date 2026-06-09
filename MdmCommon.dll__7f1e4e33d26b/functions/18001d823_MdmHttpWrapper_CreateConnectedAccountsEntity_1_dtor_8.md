# _MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor$8

- ea: `0x18001d823`
- end: `0x18001d82f`
- name: `_MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ae14`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 72));
}

```

## disassembly

```asm
0x18001d823  lea     rcx, [rdx+48h]; this
0x18001d82a  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
