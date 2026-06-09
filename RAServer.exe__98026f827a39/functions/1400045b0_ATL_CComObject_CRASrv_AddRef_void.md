# ATL::CComObject<CRASrv>::AddRef(void)

- ea: `0x1400045b0`
- end: `0x1400045b9`
- name: `?AddRef@?$CComObject@VCRASrv@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400045c0`

## callees

- `0x14000a258`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRASrv>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 16));
}

```

## disassembly

```asm
0x1400045b0  add     rcx, 10h; volatile int *
0x1400045b4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
