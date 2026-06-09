# Microsoft.ManagementConsole.Internal.TestSnapInPlatform::.ctor

- ea: `0x8320`
- end: `0x833c`
- name: `Microsoft.ManagementConsole.Internal.TestSnapInPlatform::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8060`

## callees

- `0x8320`

## string_xrefs

- `0x8329`: `processCommandCallback`

## pseudocode

```c

```

## disassembly

```asm
0x8320  ldarg.0
0x8321  call     instance void [mscorlib]System.Object::.ctor()
0x8326  ldarg.1
0x8327  brtrue.s loc_8334
0x8329  ldstr    aProcesscommand// "processCommandCallback"
0x832e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8333  throw
0x8334  ldarg.0
0x8335  ldarg.1
0x8336  stfld    class [mscorlib]System.Delegate Microsoft.ManagementConsole.Internal.TestSnapInPlatform::_processCommandCallback
0x833b  ret
```
