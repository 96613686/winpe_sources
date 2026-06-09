# IsProcessorFeaturePresent

- ea: `0x140008a9b`
- end: `0x140008aa1`
- name: `IsProcessorFeaturePresent`
- size: `6`
- prototype: `BOOL __stdcall(DWORD ProcessorFeature)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400080d0`
- `0x140008538`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140008a9b`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall IsProcessorFeaturePresent(DWORD ProcessorFeature)
{
  return __imp_IsProcessorFeaturePresent(ProcessorFeature);
}

```

## disassembly

```asm
0x140008a9b  jmp     cs:__imp_IsProcessorFeaturePresent
```
