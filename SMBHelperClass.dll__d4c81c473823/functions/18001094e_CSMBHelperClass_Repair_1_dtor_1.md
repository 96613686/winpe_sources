# _CSMBHelperClass::Repair_::_1_::dtor$1

- ea: `0x18001094e`
- end: `0x18001095a`
- name: `_CSMBHelperClass::Repair_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000c3c8`

## pseudocode

```c
void __fastcall CSMBHelperClass::Repair_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  NDFRepairExecutionClosure::~NDFRepairExecutionClosure((NDFRepairExecutionClosure *)(a2 + 72));
}

```

## disassembly

```asm
0x18001094e  lea     rcx, [rdx+48h]; this
0x180010955  jmp     ??1NDFRepairExecutionClosure@@UEAA@XZ; NDFRepairExecutionClosure::~NDFRepairExecutionClosure(void)
```
