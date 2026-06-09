# _GetComplement_::_1_::dtor$4

- ea: `0x100473b54`
- end: `0x100473b64`
- name: `_GetComplement_::_1_::dtor$4`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10040b270`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CMetadataFilter::~CMetadataFilter((CMetadataFilter *)(a2 + 368));
}

```

## disassembly

```asm
0x100473b54  lea     rcx, [rdx+150h]
0x100473b5b  add     rcx, 20h ; ' '; this
0x100473b5f  jmp     ??1CMetadataFilter@@UEAA@XZ; CMetadataFilter::~CMetadataFilter(void)
```
