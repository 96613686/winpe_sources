# Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::WriteJson

- ea: `0xe5d0`
- end: `0xe60b`
- name: `Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::WriteJson`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xe5d0`
- `0xe610`

## string_xrefs

- `0xe5d1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xe5d0  ldarg.1
0xe5d1  ldstr    aWriter// "writer"
0xe5d6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe5db  ldarg.2
0xe5dc  ldstr    aValue// "value"
0xe5e1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe5e6  ldarg.3
0xe5e7  ldstr    aSerializer// "serializer"
0xe5ec  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe5f1  ldarg.2
0xe5f2  isinst   Microsoft.VisualStudio.Setup.DependencyCollection
0xe5f7  stloc.0
0xe5f8  ldloc.0
0xe5f9  brfalse.s loc_E605
0xe5fb  ldarg.0
0xe5fc  ldarg.1
0xe5fd  ldloc.0
0xe5fe  ldarg.3
0xe5ff  call     instance void Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::WriteJson(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter writer, class Microsoft.VisualStudio.Setup.DependencyCollection dependencies, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer serializer)
0xe604  ret
0xe605  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xe60a  throw
```
