# TemplateEventDescriptor

- ea: `0x180013ea0`
- end: `0x180013eb6`
- name: `TemplateEventDescriptor`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180014d00`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013eaf`

## pseudocode

```c
ULONG TemplateEventDescriptor()
{
  return EventWrite(0, (PCEVENT_DESCRIPTOR)TraceMerge_NGEN_CreatingPDBs_Start, 0, 0);
}

```

## disassembly

```asm
0x180013ea0  xor     r9d, r9d
0x180013ea3  lea     rdx, TraceMerge_NGEN_CreatingPDBs_Start
0x180013eaa  xor     r8d, r8d
0x180013ead  xor     ecx, ecx
0x180013eaf  jmp     cs:__imp_EventWrite
```
