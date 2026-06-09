# NtQuerySystemInformation

- ea: `0x14000acb6`
- end: `0x14000acbc`
- name: `NtQuerySystemInformation`
- size: `6`
- prototype: `NTSTATUS __stdcall(SYSTEM_INFORMATION_CLASS SystemInformationClass, PVOID SystemInformation, ULONG SystemInformationLength, PULONG ReturnLength)`
- caller_count: `22`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400112a0`
- `0x140017d30`
- `0x140018750`
- `0x1400187a0`
- `0x14001e5d0`
- `0x14001e620`
- `0x14001e670`
- `0x14001e6c0`
- `0x14001e820`
- `0x14001eab0`
- `0x14001eb00`
- `0x14001eb50`
- `0x14001ed90`
- `0x14001ede0`
- `0x14001f850`
- `0x1400206e0`
- `0x140020940`
- `0x140020ad0`
- `0x140020d20`
- `0x140020d70`
- `0x140021250`
- `0x1400212a0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x14000acb6`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtQuerySystemInformation(
        SYSTEM_INFORMATION_CLASS SystemInformationClass,
        PVOID SystemInformation,
        ULONG SystemInformationLength,
        PULONG ReturnLength)
{
  return __imp_NtQuerySystemInformation(
           SystemInformationClass,
           SystemInformation,
           SystemInformationLength,
           ReturnLength);
}

```

## disassembly

```asm
0x14000acb6  jmp     cs:__imp_NtQuerySystemInformation
```
