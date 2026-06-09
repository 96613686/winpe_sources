# Microsoft.VisualStudio.Setup.Serialization.PackageCollectionConverter::WriteJson

- ea: `0x102a0`
- end: `0x10313`
- name: `Microsoft.VisualStudio.Setup.Serialization.PackageCollectionConverter::WriteJson`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x10250`
- `0x102a0`

## string_xrefs

- `0x102a1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x102a0  ldarg.1
0x102a1  ldstr    aWriter// "writer"
0x102a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x102ab  ldarg.3
0x102ac  ldstr    aSerializer// "serializer"
0x102b1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x102b6  ldarg.2
0x102b7  isinst   class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.IPackage>
0x102bc  stloc.0
0x102bd  ldloc.0
0x102be  brtrue.s loc_102C6
0x102c0  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x102c5  throw
0x102c6  ldarg.1
0x102c7  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartArray()
0x102cc  ldarg.0
0x102cd  call     instance class [mscorlib]System.Predicate`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Serialization.PackageCollectionConverter::get_Filter()
0x102d2  stloc.1
0x102d3  ldloc.0
0x102d4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x102d9  stloc.2
0x102da  br.s     loc_102F7
0x102dc  ldloc.2
0x102dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x102e2  stloc.3
0x102e3  ldloc.1
0x102e4  brfalse.s loc_102EF
0x102e6  ldloc.1
0x102e7  ldloc.3
0x102e8  callvirt instance bool class [mscorlib]System.Predicate`1<class Microsoft.VisualStudio.Setup.IPackage>::Invoke(var<u1>)
0x102ed  brfalse.s loc_102F7
0x102ef  ldarg.3
0x102f0  ldarg.1
0x102f1  ldloc.3
0x102f2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0x102f7  ldloc.2
0x102f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x102fd  brtrue.s loc_102DC
0x102ff  leave.s  loc_10312
0x10301  ldloc.2
0x10302  brfalse.s loc_1030A
0x10304  ldloc.2
0x10305  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1030a  endfinally
0x1030b  ldarg.1
0x1030c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndArray()
0x10311  endfinally
0x10312  ret
```
