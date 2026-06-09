# CMetadataXMPStructReaderWriter::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b410`
- end: `0x18000b419`
- name: `?QueryInterface@CMetadataXMPStructReaderWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(CMetadataXMPStructReaderWriter *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800231a0`
- `0x1800231b0`
- `0x1800231c0`

## callees

- `0x180009f30`

## pseudocode

```c
__int64 __fastcall CMetadataXMPStructReaderWriter::QueryInterface(
        CMetadataXMPStructReaderWriter *this,
        const struct _GUID *a2,
        void **a3)
{
  return CMILCOMBase::InternalQueryInterface((CMetadataXMPStructReaderWriter *)((char *)this + 24), a2, a3);
}

```

## disassembly

```asm
0x18000b410  add     rcx, 18h; this
0x18000b414  jmp     ?InternalQueryInterface@CMILCOMBase@@QEAAJAEBU_GUID@@PEAPEAX@Z; CMILCOMBase::InternalQueryInterface(_GUID const &,void * *)
```
