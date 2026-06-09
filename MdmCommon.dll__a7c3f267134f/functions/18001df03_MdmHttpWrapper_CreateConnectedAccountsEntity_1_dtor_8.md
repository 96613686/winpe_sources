# _MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor$8

- ea: `0x18001df03`
- end: `0x18001df0f`
- name: `_MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b0d4`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateConnectedAccountsEntity_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 72));
}

```

## disassembly

```asm
0x18001df03  lea     rcx, [rdx+48h]; this
0x18001df0a  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
