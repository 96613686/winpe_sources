# _MdmHttpWrapper::CreateCommandChannelEntity_::_1_::dtor$9

- ea: `0x18001def1`
- end: `0x18001defd`
- name: `_MdmHttpWrapper::CreateCommandChannelEntity_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b0d4`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateCommandChannelEntity_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 88));
}

```

## disassembly

```asm
0x18001def1  lea     rcx, [rdx+58h]; this
0x18001def8  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
