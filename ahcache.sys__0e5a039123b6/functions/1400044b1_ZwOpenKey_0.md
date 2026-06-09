# ZwOpenKey_0

- ea: `0x1400044b1`
- end: `0x1400044b8`
- name: `ZwOpenKey_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(PHANDLE KeyHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140032048`
- `0x140046440`
- `0x140052234`
- `0x140052bf0`
- `0x140055100`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400044b1`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall ZwOpenKey_0(PHANDLE KeyHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes)
{
  return ZwOpenKey(KeyHandle, DesiredAccess, ObjectAttributes);
}

```

## disassembly

```asm
0x1400044b1  jmp     cs:__imp_ZwOpenKey
```
