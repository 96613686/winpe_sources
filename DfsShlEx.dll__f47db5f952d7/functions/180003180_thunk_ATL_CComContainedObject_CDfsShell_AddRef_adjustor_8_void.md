# [thunk]:ATL::CComContainedObject<CDfsShell>::AddRef`adjustor{8}' (void)

- ea: `0x180003180`
- end: `0x180003189`
- name: `?AddRef@?$CComContainedObject@VCDfsShell@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003160`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CDfsShell>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180003180  sub     rcx, 8
0x180003184  jmp     ?AddRef@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CDfsShell>::AddRef(void)
```
