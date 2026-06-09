# ExpandPositionalParameters::ThrowIfFailed

- ea: `0x2e840`
- end: `0x2e85e`
- name: `ExpandPositionalParameters::ThrowIfFailed`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x2e860`
- `0x2e930`
- `0x2e9b0`
- `0x2ea40`
- `0x2ea90`

## callees

- `0x11f50`
- `0x2e840`

## string_xrefs

- `0x2e843`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2e840  ldarg.1
0x2e841  brfalse.s loc_2E85D
0x2e843  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2e848  ldc.i4.1
0x2e849  newarr   [mscorlib]System.Object
0x2e84e  dup
0x2e84f  ldc.i4.0
0x2e850  ldarg.2
0x2e851  stelem.ref
0x2e852  call     string System.Xaml.SR::Get(string id, object[] args)
0x2e857  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e85c  throw
0x2e85d  ret
```
