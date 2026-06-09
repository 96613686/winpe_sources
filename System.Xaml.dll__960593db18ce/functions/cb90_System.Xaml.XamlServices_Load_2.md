# System.Xaml.XamlServices::Load_2

- ea: `0xcb90`
- end: `0xcbba`
- name: `System.Xaml.XamlServices::Load_2`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x5e90`
- `0xcb90`
- `0xcbc0`

## string_xrefs

- `0xcb93`: `xmlReader`

## pseudocode

```c

```

## disassembly

```asm
0xcb90  ldarg.0
0xcb91  brtrue.s loc_CB9E
0xcb93  ldstr    aXmlreader// "xmlReader"
0xcb98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcb9d  throw
0xcb9e  ldarg.0
0xcb9f  newobj   instance void System.Xaml.XamlXmlReader::.ctor(class [System.Xml]System.Xml.XmlReader xmlReader)
0xcba4  stloc.0
0xcba5  ldloc.0
0xcba6  call     object System.Xaml.XamlServices::Load(class System.Xaml.XamlReader xamlReader)
0xcbab  stloc.1
0xcbac  leave.s  loc_CBB8
0xcbae  ldloc.0
0xcbaf  brfalse.s loc_CBB7
0xcbb1  ldloc.0
0xcbb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcbb7  endfinally
0xcbb8  ldloc.1
0xcbb9  ret
```
