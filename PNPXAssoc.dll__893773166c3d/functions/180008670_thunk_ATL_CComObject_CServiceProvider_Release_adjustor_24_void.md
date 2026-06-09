# [thunk]:ATL::CComObject<CServiceProvider>::Release`adjustor{24}' (void)

- ea: `0x180008670`
- end: `0x180008679`
- name: `?Release@?$CComObject@VCServiceProvider@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CServiceProvider>::Release((volatile signed __int32 *)(a1 - 24));
}

```

## disassembly

```asm
0x180008670  sub     rcx, 18h
0x180008674  jmp     ?Release@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComObject<CServiceProvider>::Release(void)
```
