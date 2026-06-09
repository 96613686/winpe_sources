# [thunk]:ATL::CComContainedObject<CServiceProvider>::Release`adjustor{24}' (void)

- ea: `0x180008500`
- end: `0x180008509`
- name: `?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CServiceProvider>::Release(a1 - 24);
}

```

## disassembly

```asm
0x180008500  sub     rcx, 18h
0x180008504  jmp     ?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CServiceProvider>::Release(void)
```
