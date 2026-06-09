# ATL::CComObject<CPersistDSO>::AddRef(void)

- ea: `0x180018770`
- end: `0x180018779`
- name: `?AddRef@?$CComObject@VCPersistDSO@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018780`
- `0x180018790`
- `0x1800187a0`
- `0x1800187c0`
- `0x1800187e0`
- `0x180018800`
- `0x180018820`
- `0x180018830`
- `0x180018840`

## callees

- `0x18000c870`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CPersistDSO>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((int *)(a1 + 48));
}

```

## disassembly

```asm
0x180018770  add     rcx, 30h ; '0'; int *
0x180018774  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeIncrementReferenceMultiThread(long *)
```
