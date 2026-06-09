# [thunk]:ATL::CComContainedObject<CDfsShell>::Release`adjustor{8}' (void)

- ea: `0x180005fb0`
- end: `0x180005fb9`
- name: `?Release@?$CComContainedObject@VCDfsShell@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005f90`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CDfsShell>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180005fb0  sub     rcx, 8
0x180005fb4  jmp     ?Release@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CDfsShell>::Release(void)
```
