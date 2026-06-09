# ZwCreateSection_0

- ea: `0x14000451d`
- end: `0x140004524`
- name: `ZwCreateSection_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(PHANDLE SectionHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PLARGE_INTEGER MaximumSize, ULONG SectionPageProtection, ULONG AllocationAttributes, HANDLE FileHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140006974`
- `0x140031be0`
- `0x140036b30`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x14000451d`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall ZwCreateSection_0(
        PHANDLE SectionHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PLARGE_INTEGER MaximumSize,
        ULONG SectionPageProtection,
        ULONG AllocationAttributes,
        HANDLE FileHandle)
{
  return ZwCreateSection(
           SectionHandle,
           DesiredAccess,
           ObjectAttributes,
           MaximumSize,
           SectionPageProtection,
           AllocationAttributes,
           FileHandle);
}

```

## disassembly

```asm
0x14000451d  jmp     cs:__imp_ZwCreateSection
```
