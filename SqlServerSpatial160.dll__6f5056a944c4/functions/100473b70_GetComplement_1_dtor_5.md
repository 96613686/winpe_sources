# _GetComplement_::_1_::dtor$5

- ea: `0x100473b70`
- end: `0x100473b83`
- name: `_GetComplement_::_1_::dtor$5`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100402770`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  C2DMetadataResolver::~C2DMetadataResolver((C2DMetadataResolver *)(a2 + 488));
}

```

## disassembly

```asm
0x100473b70  lea     rcx, [rdx+150h]
0x100473b77  add     rcx, 98h; this
0x100473b7e  jmp     ??1C2DMetadataResolver@@UEAA@XZ; C2DMetadataResolver::~C2DMetadataResolver(void)
```
