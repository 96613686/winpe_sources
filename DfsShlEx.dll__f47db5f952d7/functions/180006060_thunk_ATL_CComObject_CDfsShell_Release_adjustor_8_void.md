# [thunk]:ATL::CComObject<CDfsShell>::Release`adjustor{8}' (void)

- ea: `0x180006060`
- end: `0x180006069`
- name: `?Release@?$CComObject@VCDfsShell@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005fe0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShell>::Release(__int64 a1)
{
  return ATL::CComObject<CDfsShell>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x180006060  sub     rcx, 8
0x180006064  jmp     ?Release@?$CComObject@VCDfsShell@@@ATL@@UEAAKXZ; ATL::CComObject<CDfsShell>::Release(void)
```
