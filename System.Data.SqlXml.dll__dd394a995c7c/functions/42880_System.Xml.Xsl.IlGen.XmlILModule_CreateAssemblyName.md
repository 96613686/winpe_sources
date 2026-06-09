# System.Xml.Xsl.IlGen.XmlILModule::CreateAssemblyName

- ea: `0x42880`
- end: `0x428ad`
- name: `System.Xml.Xsl.IlGen.XmlILModule::CreateAssemblyName`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x422d0`
- `0x42430`

## string_xrefs

- `0x42892`: `System.Xml.Xsl.CompiledQuery.`

## pseudocode

```c

```

## disassembly

```asm
0x42880  ldsflda  int64 System.Xml.Xsl.IlGen.XmlILModule::AssemblyId
0x42885  call     int64 [mscorlib]System.Threading.Interlocked::Increment(int64&)
0x4288a  pop
0x4288b  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor()
0x42890  stloc.0
0x42891  ldloc.0
0x42892  ldstr    aSystemXmlXslCo_1// "System.Xml.Xsl.CompiledQuery."
0x42897  ldsflda  int64 System.Xml.Xsl.IlGen.XmlILModule::AssemblyId
0x4289c  call     instance string [mscorlib]System.Int64::ToString()
0x428a1  call     string [mscorlib]System.String::Concat(string, string)
0x428a6  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_Name(string)
0x428ab  ldloc.0
0x428ac  ret
```
