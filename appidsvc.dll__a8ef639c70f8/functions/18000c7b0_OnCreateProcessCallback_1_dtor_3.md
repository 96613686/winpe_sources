# _OnCreateProcessCallback_::_1_::dtor$3

- ea: `0x18000c7b0`
- end: `0x18000c7bc`
- name: `_OnCreateProcessCallback_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180006348`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  RevertImpersonate::~RevertImpersonate((RevertImpersonate *)(a2 + 273));
}

```

## disassembly

```asm
0x18000c7b0  lea     rcx, [rdx+111h]; this
0x18000c7b7  jmp     ??1RevertImpersonate@@QEAA@XZ; RevertImpersonate::~RevertImpersonate(void)
```
