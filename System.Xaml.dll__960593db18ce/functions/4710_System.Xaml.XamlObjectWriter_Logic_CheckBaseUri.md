# System.Xaml.XamlObjectWriter::Logic_CheckBaseUri

- ea: `0x4710`
- end: `0x4738`
- name: `System.Xaml.XamlObjectWriter::Logic_CheckBaseUri`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x45b0`
- `0x4c50`

## callees

- `0x4710`
- `0x8590`
- `0x11f20`
- `0x215a0`
- `0x21a30`

## string_xrefs

- `0x4727`: `CannotSetBaseUri`

## pseudocode

```c

```

## disassembly

```asm
0x4710  ldarg.1
0x4711  callvirt instance class [System]System.Uri MS.Internal.Xaml.Context.ObjectWriterContext::get_BaseUri()
0x4716  ldnull
0x4717  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x471c  brtrue.s loc_4727
0x471e  ldarg.1
0x471f  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_Depth()
0x4724  ldc.i4.2
0x4725  ble.s    loc_4737
0x4727  ldstr    aCannotsetbaseu// "CannotSetBaseUri"
0x472c  call     string System.Xaml.SR::Get(string id)
0x4731  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4736  throw
0x4737  ret
```
