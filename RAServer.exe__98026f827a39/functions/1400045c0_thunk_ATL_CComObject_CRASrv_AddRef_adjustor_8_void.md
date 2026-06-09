# [thunk]:ATL::CComObject<CRASrv>::AddRef`adjustor{8}' (void)

- ea: `0x1400045c0`
- end: `0x1400045c9`
- name: `?AddRef@?$CComObject@VCRASrv@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400045b0`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRASrv>::AddRef(__int64 a1)
{
  return ATL::CComObject<CRASrv>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1400045c0  sub     rcx, 8
0x1400045c4  jmp     ?AddRef@?$CComObject@VCRASrv@@@ATL@@UEAAKXZ; ATL::CComObject<CRASrv>::AddRef(void)
```
