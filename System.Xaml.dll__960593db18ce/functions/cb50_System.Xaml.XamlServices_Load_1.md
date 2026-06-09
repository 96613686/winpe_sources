# System.Xaml.XamlServices::Load_1

- ea: `0xcb50`
- end: `0xcb81`
- name: `System.Xaml.XamlServices::Load_1`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x5e90`
- `0xcb50`
- `0xcbc0`

## string_xrefs

- `0xcb53`: `textReader`

## pseudocode

```c

```

## disassembly

```asm
0xcb50  ldarg.0
0xcb51  brtrue.s loc_CB5E
0xcb53  ldstr    aTextreader// "textReader"
0xcb58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcb5d  throw
0xcb5e  ldarg.0
0xcb5f  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xcb64  stloc.0
0xcb65  ldloc.0
0xcb66  newobj   instance void System.Xaml.XamlXmlReader::.ctor(class [System.Xml]System.Xml.XmlReader xmlReader)
0xcb6b  stloc.1
0xcb6c  ldloc.1
0xcb6d  call     object System.Xaml.XamlServices::Load(class System.Xaml.XamlReader xamlReader)
0xcb72  stloc.2
0xcb73  leave.s  loc_CB7F
0xcb75  ldloc.0
0xcb76  brfalse.s loc_CB7E
0xcb78  ldloc.0
0xcb79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb7e  endfinally
0xcb7f  ldloc.2
0xcb80  ret
```
