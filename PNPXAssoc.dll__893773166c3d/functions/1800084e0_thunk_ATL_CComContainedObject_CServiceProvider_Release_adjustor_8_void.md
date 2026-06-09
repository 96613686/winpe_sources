# [thunk]:ATL::CComContainedObject<CServiceProvider>::Release`adjustor{8}' (void)

- ea: `0x1800084e0`
- end: `0x1800084e9`
- name: `?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800084c0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CServiceProvider>::Release(a1 - 8);
}

```

## disassembly

```asm
0x1800084e0  sub     rcx, 8
0x1800084e4  jmp     ?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CServiceProvider>::Release(void)
```
