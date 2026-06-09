# _MdmHttpWrapper::CreateLocationEntity_::_1_::dtor$14

- ea: `0x18001df39`
- end: `0x18001df45`
- name: `_MdmHttpWrapper::CreateLocationEntity_::_1_::dtor$14`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b0d4`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateLocationEntity_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 80));
}

```

## disassembly

```asm
0x18001df39  lea     rcx, [rdx+50h]; this
0x18001df40  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
