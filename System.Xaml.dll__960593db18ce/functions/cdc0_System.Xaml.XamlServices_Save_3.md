# System.Xaml.XamlServices::Save_3

- ea: `0xcdc0`
- end: `0xcdee`
- name: `System.Xaml.XamlServices::Save_3`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0xcc80`
- `0xccc0`
- `0xcd20`
- `0xcd70`

## callees

- `0xb4b0`
- `0xcdc0`
- `0xcdf0`
- `0xf590`

## string_xrefs

- `0xcdc3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xcdc0  ldarg.0
0xcdc1  brtrue.s loc_CDCE
0xcdc3  ldstr    aWriter// "writer"
0xcdc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcdcd  throw
0xcdce  ldarg.0
0xcdcf  newobj   instance void System.Xaml.XamlSchemaContext::.ctor()
0xcdd4  newobj   instance void System.Xaml.XamlXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class System.Xaml.XamlSchemaContext schemaContext)
0xcdd9  stloc.0
0xcdda  ldloc.0
0xcddb  ldarg.1
0xcddc  call     void System.Xaml.XamlServices::Save(class System.Xaml.XamlWriter writer, object instance)
0xcde1  leave.s  loc_CDED
0xcde3  ldloc.0
0xcde4  brfalse.s loc_CDEC
0xcde6  ldloc.0
0xcde7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcdec  endfinally
0xcded  ret
```
