# [thunk]:ATL::CComObject<CServiceProvider>::Release`adjustor{8}' (void)

- ea: `0x180008650`
- end: `0x180008659`
- name: `?Release@?$CComObject@VCServiceProvider@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800085c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::Release(__int64 a1)
{
  return ATL::CComObject<CServiceProvider>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180008650  sub     rcx, 8
0x180008654  jmp     ?Release@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComObject<CServiceProvider>::Release(void)
```
