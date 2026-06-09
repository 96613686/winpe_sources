# RtlCaptureContext_0

- ea: `0x180007b70`
- end: `0x180007b76`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007880`
- `0x180007a1c`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180007b70`

## pseudocode

```c
// attributes: thunk
void __stdcall RtlCaptureContext_0(PCONTEXT ContextRecord)
{
  RtlCaptureContext(ContextRecord);
}

```

## disassembly

```asm
0x180007b70  jmp     cs:__imp_RtlCaptureContext
```
