# [thunk]:ATL::CComObject<CDfsShell>::AddRef`adjustor{8}' (void)

- ea: `0x1800031d0`
- end: `0x1800031d9`
- name: `?AddRef@?$CComObject@VCDfsShell@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800031b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShell>::AddRef(__int64 a1)
{
  return ATL::CComObject<CDfsShell>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800031d0  sub     rcx, 8
0x1800031d4  jmp     ?AddRef@?$CComObject@VCDfsShell@@@ATL@@UEAAKXZ; ATL::CComObject<CDfsShell>::AddRef(void)
```
