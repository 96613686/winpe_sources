# System.Xaml.XamlServices::Load_3

- ea: `0xcbc0`
- end: `0xcbe8`
- name: `System.Xaml.XamlServices::Load_3`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task`

## callers

- `0xca90`
- `0xcad0`
- `0xcb10`
- `0xcb50`
- `0xcb90`

## callees

- `0x2510`
- `0x3aa0`
- `0xb380`
- `0xcbc0`
- `0xcbf0`

## string_xrefs

- `0xcbc3`: `xamlReader`

## pseudocode

```c

```

## disassembly

```asm
0xcbc0  ldarg.0
0xcbc1  brtrue.s loc_CBCE
0xcbc3  ldstr    aXamlreader_0// "xamlReader"
0xcbc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcbcd  throw
0xcbce  ldarg.0
0xcbcf  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlReader::get_SchemaContext()
0xcbd4  newobj   instance void System.Xaml.XamlObjectWriter::.ctor(class System.Xaml.XamlSchemaContext schemaContext)
0xcbd9  stloc.0
0xcbda  ldarg.0
0xcbdb  ldloc.0
0xcbdc  call     void System.Xaml.XamlServices::Transform(class System.Xaml.XamlReader xamlReader, class System.Xaml.XamlWriter xamlWriter)
0xcbe1  ldloc.0
0xcbe2  callvirt instance object System.Xaml.XamlObjectWriter::get_Result()
0xcbe7  ret
```
