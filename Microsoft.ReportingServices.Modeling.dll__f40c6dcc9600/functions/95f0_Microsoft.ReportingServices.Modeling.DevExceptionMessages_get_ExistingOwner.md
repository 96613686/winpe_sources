# Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_ExistingOwner

- ea: `0x95f0`
- end: `0x95f6`
- name: `Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_ExistingOwner`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x12960`
- `0x14f60`
- `0x219f0`
- `0x21d60`
- `0x22330`

## string_xrefs

- `0x95f0`: `The object has already been assigned to an owner; must be removed from existing owner before assigning a new owner.`

## pseudocode

```c

```

## disassembly

```asm
0x95f0  ldstr    aTheObjectHasAl// "The object has already been assigned to"...
0x95f5  ret
```
