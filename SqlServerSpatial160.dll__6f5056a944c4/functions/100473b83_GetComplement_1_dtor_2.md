# _GetComplement_::_1_::dtor$2

- ea: `0x100473b83`
- end: `0x100473b8f`
- name: `_GetComplement_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10040b390`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CMetadataEnabledGeodeticOperation::~CMetadataEnabledGeodeticOperation((CMetadataEnabledGeodeticOperation *)(a2 + 336));
}

```

## disassembly

```asm
0x100473b83  lea     rcx, [rdx+150h]; this
0x100473b8a  jmp     ??1CMetadataEnabledGeodeticOperation@@UEAA@XZ; CMetadataEnabledGeodeticOperation::~CMetadataEnabledGeodeticOperation(void)
```
