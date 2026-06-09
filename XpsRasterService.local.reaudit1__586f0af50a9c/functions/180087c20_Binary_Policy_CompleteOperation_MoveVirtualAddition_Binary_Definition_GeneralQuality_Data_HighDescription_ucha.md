# Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)

- ea: `0x180087c20`
- end: `0x180087c23`
- name: `?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z`
- size: `3`
- prototype: ``
- caller_count: `25`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087d70`
- `0x180089230`
- `0x1800896c0`
- `0x180089c70`
- `0x18008a170`
- `0x18008a670`
- `0x18008aae0`
- `0x18008b130`
- `0x18008bc80`
- `0x18008ca80`
- `0x18008d660`
- `0x18008e070`
- `0x18008e6d0`
- `0x18008fe70`
- `0x180090300`
- `0x1800908b0`
- `0x180090e30`
- `0x1800913b0`
- `0x180091820`
- `0x1800920e0`
- `0x180092da0`
- `0x180093ab0`
- `0x180094590`
- `0x180094b90`
- `0x180095970`

## pseudocode

```c
void __fastcall Binary::Policy::CompleteOperation::MoveVirtualAddition(_DWORD *a1)
{
  ++*a1;
}

```

## disassembly

```asm
0x180087c20  inc     dword ptr [rcx]
0x180087c22  retn
```
