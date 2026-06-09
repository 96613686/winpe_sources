# ATL::CComObject<CAxInstaller>::AddRef(void)

- ea: `0x1800095e0`
- end: `0x1800095e9`
- name: `?AddRef@?$CComObject@VCAxInstaller@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800095f0`

## callees

- `0x18000f488`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CAxInstaller>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 16));
}

```

## disassembly

```asm
0x1800095e0  add     rcx, 10h; volatile int *
0x1800095e4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
