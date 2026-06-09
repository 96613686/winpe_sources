# IsProcessorFeaturePresent_0

- ea: `0x1800049b4`
- end: `0x1800049ba`
- name: `IsProcessorFeaturePresent_0`
- size: `6`
- prototype: `BOOL __stdcall(DWORD ProcessorFeature)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004350`
- `0x18000467c`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x1800049b4`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall IsProcessorFeaturePresent_0(DWORD ProcessorFeature)
{
  return IsProcessorFeaturePresent(ProcessorFeature);
}

```

## disassembly

```asm
0x1800049b4  jmp     cs:__imp_IsProcessorFeaturePresent
```
