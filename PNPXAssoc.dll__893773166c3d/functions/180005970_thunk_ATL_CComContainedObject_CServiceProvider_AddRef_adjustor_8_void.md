# [thunk]:ATL::CComContainedObject<CServiceProvider>::AddRef`adjustor{8}' (void)

- ea: `0x180005970`
- end: `0x180005979`
- name: `?AddRef@?$CComContainedObject@VCServiceProvider@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005950`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CServiceProvider>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005970  sub     rcx, 8
0x180005974  jmp     ?AddRef@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CServiceProvider>::AddRef(void)
```
