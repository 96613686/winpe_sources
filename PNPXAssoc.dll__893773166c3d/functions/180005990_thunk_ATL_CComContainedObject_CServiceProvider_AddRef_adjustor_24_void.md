# [thunk]:ATL::CComContainedObject<CServiceProvider>::AddRef`adjustor{24}' (void)

- ea: `0x180005990`
- end: `0x180005999`
- name: `?AddRef@?$CComContainedObject@VCServiceProvider@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CServiceProvider>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180005990  sub     rcx, 18h
0x180005994  jmp     ?AddRef@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CServiceProvider>::AddRef(void)
```
