# [thunk]:ATL::CComContainedObject<CBrowserCap>::Release`adjustor{8}' (void)

- ea: `0x180005c50`
- end: `0x180005c59`
- name: `?Release@?$CComContainedObject@VCBrowserCap@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c30`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CBrowserCap>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180005c50  sub     rcx, 8
0x180005c54  jmp     ?Release@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CBrowserCap>::Release(void)
```
