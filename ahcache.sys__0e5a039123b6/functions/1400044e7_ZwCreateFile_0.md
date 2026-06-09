# ZwCreateFile_0

- ea: `0x1400044e7`
- end: `0x1400044ee`
- name: `ZwCreateFile_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, PLARGE_INTEGER AllocationSize, ULONG FileAttributes, ULONG ShareAccess, ULONG CreateDisposition, ULONG CreateOptions, PVOID EaBuffer, ULONG EaLength)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140002f84`
- `0x140041f78`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400044e7`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall ZwCreateFile_0(
        PHANDLE FileHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        PLARGE_INTEGER AllocationSize,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        PVOID EaBuffer,
        ULONG EaLength)
{
  return ZwCreateFile(
           FileHandle,
           DesiredAccess,
           ObjectAttributes,
           IoStatusBlock,
           AllocationSize,
           FileAttributes,
           ShareAccess,
           CreateDisposition,
           CreateOptions,
           EaBuffer,
           EaLength);
}

```

## disassembly

```asm
0x1400044e7  jmp     cs:__imp_ZwCreateFile
```
