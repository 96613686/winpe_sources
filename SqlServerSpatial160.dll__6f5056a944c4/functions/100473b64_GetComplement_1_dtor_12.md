# _GetComplement_::_1_::dtor$12

- ea: `0x100473b64`
- end: `0x100473b70`
- name: `_GetComplement_::_1_::dtor$12`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004017e0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  CMetadataResolver::~CMetadataResolver(*(CMetadataResolver **)(a2 + 64));
}

```

## disassembly

```asm
0x100473b64  mov     rcx, [rdx+40h]; this
0x100473b6b  jmp     ??1CMetadataResolver@@UEAA@XZ; CMetadataResolver::~CMetadataResolver(void)
```
