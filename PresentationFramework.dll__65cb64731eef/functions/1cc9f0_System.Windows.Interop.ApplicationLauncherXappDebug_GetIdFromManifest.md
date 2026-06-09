# System.Windows.Interop.ApplicationLauncherXappDebug::GetIdFromManifest

- ea: `0x1cc9f0`
- end: `0x1ccade`
- name: `System.Windows.Interop.ApplicationLauncherXappDebug::GetIdFromManifest`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1cc9a0`

## callees

- `0x1cc9f0`

## string_xrefs

- `0x1cca6e`: `xmlns`
- `0x1cca1e`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x1cc9f0  ldarg.1
0x1cc9f1  ldc.i4.3
0x1cc9f2  ldc.i4.1
0x1cc9f3  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x1cc9f8  stloc.0
0x1cc9f9  ldloc.0
0x1cc9fa  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0x1cc9ff  stloc.1
0x1cca00  ldloc.1
0x1cca01  ldc.i4.2
0x1cca02  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0x1cca07  br       loc_1CCAB8
0x1cca0c  ldloc.1
0x1cca0d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cca12  ldc.i4.1
0x1cca13  bne.un   loc_1CCAB8
0x1cca18  ldloc.1
0x1cca19  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1cca1e  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x1cca23  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1cca28  brtrue   loc_1CCAB8
0x1cca2d  ldloc.1
0x1cca2e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cca33  ldstr    aAssemblyidenti// "assemblyIdentity"
0x1cca38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cca3d  brfalse.s loc_1CCAB8
0x1cca3f  ldsfld   string [mscorlib]System.String::Empty
0x1cca44  stloc.2
0x1cca45  br.s     loc_1CCAAC
0x1cca47  ldloc.1
0x1cca48  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1cca4d  ldstr    aName_0// "name"
0x1cca52  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cca57  brfalse.s loc_1CCA68
0x1cca59  ldloc.1
0x1cca5a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x1cca5f  ldloc.2
0x1cca60  call     string [mscorlib]System.String::Concat(string, string)
0x1cca65  stloc.2
0x1cca66  br.s     loc_1CCAAC
0x1cca68  ldloc.1
0x1cca69  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1cca6e  ldstr    aXmlns// "xmlns"
0x1cca73  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cca78  brtrue.s loc_1CCAAC
0x1cca7a  ldc.i4.5
0x1cca7b  newarr   [mscorlib]System.String
0x1cca80  dup
0x1cca81  ldc.i4.0
0x1cca82  ldloc.2
0x1cca83  stelem.ref
0x1cca84  dup
0x1cca85  ldc.i4.1
0x1cca86  ldstr    asc_29CBD2// ", "
0x1cca8b  stelem.ref
0x1cca8c  dup
0x1cca8d  ldc.i4.2
0x1cca8e  ldloc.1
0x1cca8f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1cca94  stelem.ref
0x1cca95  dup
0x1cca96  ldc.i4.3
0x1cca97  ldstr    asc_291ACA// "="
0x1cca9c  stelem.ref
0x1cca9d  dup
0x1cca9e  ldc.i4.4
0x1cca9f  ldloc.1
0x1ccaa0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x1ccaa5  stelem.ref
0x1ccaa6  call     string [mscorlib]System.String::Concat(string[])
0x1ccaab  stloc.2
0x1ccaac  ldloc.1
0x1ccaad  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1ccab2  brtrue.s loc_1CCA47
0x1ccab4  ldloc.2
0x1ccab5  stloc.3
0x1ccab6  leave.s  loc_1CCADC
0x1ccab8  ldloc.1
0x1ccab9  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1ccabe  brtrue   loc_1CCA0C
0x1ccac3  leave.s  loc_1CCAD6
0x1ccac5  ldloc.1
0x1ccac6  brfalse.s loc_1CCACE
0x1ccac8  ldloc.1
0x1ccac9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ccace  endfinally
0x1ccacf  ldloc.0
0x1ccad0  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x1ccad5  endfinally
0x1ccad6  ldsfld   string [mscorlib]System.String::Empty
0x1ccadb  ret
0x1ccadc  ldloc.3
0x1ccadd  ret
```
