# [thunk]:ATL::CComContainedObject<CRASrv>::AddRef`adjustor{8}' (void)

- ea: `0x140004580`
- end: `0x140004589`
- name: `?AddRef@?$CComContainedObject@VCRASrv@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004560`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRASrv>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CRASrv>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x140004580  sub     rcx, 8
0x140004584  jmp     ?AddRef@?$CComContainedObject@VCRASrv@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRASrv>::AddRef(void)
```
