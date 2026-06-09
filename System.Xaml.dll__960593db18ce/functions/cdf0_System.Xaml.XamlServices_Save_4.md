# System.Xaml.XamlServices::Save_4

- ea: `0xcdf0`
- end: `0xce13`
- name: `System.Xaml.XamlServices::Save_4`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0xcdc0`

## callees

- `0xcbf0`
- `0xcdf0`
- `0xf050`
- `0xf3b0`

## string_xrefs

- `0xcdf3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xcdf0  ldarg.0
0xcdf1  brtrue.s loc_CDFE
0xcdf3  ldstr    aWriter// "writer"
0xcdf8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcdfd  throw
0xcdfe  ldarg.1
0xcdff  ldarg.0
0xce00  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0xce05  newobj   instance void System.Xaml.XamlObjectReader::.ctor(object instance, class System.Xaml.XamlSchemaContext schemaContext)
0xce0a  stloc.0
0xce0b  ldloc.0
0xce0c  ldarg.0
0xce0d  call     void System.Xaml.XamlServices::Transform(class System.Xaml.XamlReader xamlReader, class System.Xaml.XamlWriter xamlWriter)
0xce12  ret
```
