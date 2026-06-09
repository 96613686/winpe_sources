# ExDeleteResourceLite_0

- ea: `0x1400043a3`
- end: `0x1400043aa`
- name: `ExDeleteResourceLite_0`
- size: `7`
- prototype: `NTSTATUS __stdcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400335d4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400043a3`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall ExDeleteResourceLite_0(PERESOURCE Resource)
{
  return ExDeleteResourceLite(Resource);
}

```

## disassembly

```asm
0x1400043a3  jmp     cs:__imp_ExDeleteResourceLite
```
