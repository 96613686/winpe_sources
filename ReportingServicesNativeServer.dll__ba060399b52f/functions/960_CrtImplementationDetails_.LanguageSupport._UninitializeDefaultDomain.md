# ::<CrtImplementationDetails>.LanguageSupport._UninitializeDefaultDomain

- ea: `0x960`
- end: `0x98b`
- name: `::<CrtImplementationDetails>.LanguageSupport._UninitializeDefaultDomain`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x990`

## callees

- `0x960`
- `0xe60`
- `0x1370`

## pseudocode

```c

```

## disassembly

```asm
0x960  call     void _exit_callback()
0x965  ldc.i4.0
0x966  stsfld   bool ?InitializedPerProcess@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x96b  ldsfld   bool ?InitializedNativeFromCCTOR@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x970  brfalse.s loc_983
0x972  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void _cexit()
0x977  ldc.i4.0
0x978  stsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x97d  ldc.i4.0
0x97e  stsfld   bool ?InitializedNativeFromCCTOR@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x983  ldc.i4.0
0x984  stsfld   bool ?InitializedNative@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x989  ldc.i4.0
0x98a  ret
```
