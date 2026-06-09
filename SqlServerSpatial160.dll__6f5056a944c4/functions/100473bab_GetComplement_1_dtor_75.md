# _GetComplement_::_1_::dtor$75

- ea: `0x100473bab`
- end: `0x100473bbe`
- name: `_GetComplement_::_1_::dtor$75`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100402770`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_75(__int64 a1, __int64 a2)
{
  C2DMetadataResolver::~C2DMetadataResolver((C2DMetadataResolver *)(a2 + 488));
}

```

## disassembly

```asm
0x100473bab  lea     rcx, [rdx+150h]
0x100473bb2  add     rcx, 98h; this
0x100473bb9  jmp     ??1C2DMetadataResolver@@UEAA@XZ; C2DMetadataResolver::~C2DMetadataResolver(void)
```
