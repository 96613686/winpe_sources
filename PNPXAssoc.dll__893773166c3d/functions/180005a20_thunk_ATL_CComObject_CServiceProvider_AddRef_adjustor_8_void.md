# [thunk]:ATL::CComObject<CServiceProvider>::AddRef`adjustor{8}' (void)

- ea: `0x180005a20`
- end: `0x180005a29`
- name: `?AddRef@?$CComObject@VCServiceProvider@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800059f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::AddRef(__int64 a1)
{
  return ATL::CComObject<CServiceProvider>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005a20  sub     rcx, 8
0x180005a24  jmp     ?AddRef@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComObject<CServiceProvider>::AddRef(void)
```
