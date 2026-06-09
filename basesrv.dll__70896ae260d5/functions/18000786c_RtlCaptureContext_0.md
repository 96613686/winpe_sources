# RtlCaptureContext_0

- ea: `0x18000786c`
- end: `0x180007872`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007580`
- `0x180007718`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x18000786c`

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
0x18000786c  jmp     cs:__imp_RtlCaptureContext
```
