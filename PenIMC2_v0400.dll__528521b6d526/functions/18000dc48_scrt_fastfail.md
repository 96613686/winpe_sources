# __scrt_fastfail

- ea: `0x18000dc48`
- end: `0x18000dd93`
- name: `__scrt_fastfail`
- size: `331`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d270`
- `0x18000d490`
- `0x18000d780`
- `0x18000d898`

## callees

- `0x18000dc40`
- `0x18000dc48`
- `0x18000e0cc`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000dd6c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000dd6c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000dd61`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000dd61`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000dc64`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000dc64`
- `KERNEL32!IsDebuggerPresent` at `0x18000dd40`
- `KERNEL32!IsDebuggerPresent` at `0x18000dd40`
- `ntdll!RtlLookupFunctionEntry` at `0x18000dcab`
- `ntdll!RtlLookupFunctionEntry` at `0x18000dcab`
- `ntdll!RtlVirtualUnwind` at `0x18000dcec`
- `ntdll!RtlVirtualUnwind` at `0x18000dcec`
- `ntdll!RtlCaptureContext` at `0x18000dc91`
- `ntdll!RtlCaptureContext` at `0x18000dc91`

## pseudocode

```c

```
