# System.Xml.Serialization.XmlSerializer::Deserialize_4

- ea: `0xaa2c0`
- end: `0xaa3ef`
- name: `System.Xml.Serialization.XmlSerializer::Deserialize_4`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0xaa2a0`
- `0xaa2b0`

## callees

- `0xe230`
- `0xe240`
- `0x622f0`
- `0x62370`
- `0x66b80`
- `0x86070`
- `0x88360`
- `0xaa2c0`
- `0xaaa30`
- `0xaaa40`
- `0xaac70`

## string_xrefs

- `0xaa2e2`: `XmlInvalidEncodingNotEncoded1`
- `0xaa397`: `XmlSerializeErrorDetails`
- `0xaa3dc`: `XmlSerializeError`

## pseudocode

```c

```

## disassembly

```asm
0xaa2c0  ldarga.s 3
0xaa2c2  ldarg.0
0xaa2c3  stfld    object System.Xml.Serialization.XmlDeserializationEvents::sender
0xaa2c8  ldarg.0
0xaa2c9  ldfld    class [mscorlib]System.Type System.Xml.Serialization.XmlSerializer::primitiveType
0xaa2ce  ldnull
0xaa2cf  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaa2d4  brfalse.s loc_AA30A
0xaa2d6  ldarg.2
0xaa2d7  brfalse.s loc_AA2FC
0xaa2d9  ldarg.2
0xaa2da  callvirt instance int32 [mscorlib]System.String::get_Length()
0xaa2df  ldc.i4.0
0xaa2e0  ble.s    loc_AA2FC
0xaa2e2  ldstr    aXmlinvalidenco_0// "XmlInvalidEncodingNotEncoded1"
0xaa2e7  ldc.i4.1
0xaa2e8  newarr   [mscorlib]System.Object
0xaa2ed  dup
0xaa2ee  ldc.i4.0
0xaa2ef  ldarg.2
0xaa2f0  stelem.ref
0xaa2f1  call     string System.Xml.Res::GetString(string name, object[] args)
0xaa2f6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xaa2fb  throw
0xaa2fc  ldarg.0
0xaa2fd  ldarg.1
0xaa2fe  ldarg.3
0xaa2ff  call     instance object System.Xml.Serialization.XmlSerializer::DeserializePrimitive(class System.Xml.XmlReader xmlReader, valuetype System.Xml.Serialization.XmlDeserializationEvents events)
0xaa304  stloc.0
0xaa305  leave    loc_AA3ED
0xaa30a  ldarg.0
0xaa30b  ldfld    class System.Xml.Serialization.TempAssembly System.Xml.Serialization.XmlSerializer::tempAssembly
0xaa310  brfalse.s loc_AA31A
0xaa312  ldarg.0
0xaa313  ldfld    bool System.Xml.Serialization.XmlSerializer::typedSerializer
0xaa318  brfalse.s loc_AA344
0xaa31a  ldarg.0
0xaa31b  callvirt instance class System.Xml.Serialization.XmlSerializationReader System.Xml.Serialization.XmlSerializer::CreateReader()
0xaa320  stloc.1
0xaa321  ldloc.1
0xaa322  ldarg.1
0xaa323  ldarg.3
0xaa324  ldarg.2
0xaa325  ldarg.0
0xaa326  ldfld    class System.Xml.Serialization.TempAssembly System.Xml.Serialization.XmlSerializer::tempAssembly
0xaa32b  callvirt instance void System.Xml.Serialization.XmlSerializationReader::Init(class System.Xml.XmlReader r, valuetype System.Xml.Serialization.XmlDeserializationEvents events, string encodingStyle, class System.Xml.Serialization.TempAssembly tempAssembly)
0xaa330  ldarg.0
0xaa331  ldloc.1
0xaa332  callvirt instance object System.Xml.Serialization.XmlSerializer::Deserialize(class System.Xml.Serialization.XmlSerializationReader reader)
0xaa337  stloc.0
0xaa338  leave    loc_AA3ED
0xaa33d  ldloc.1
0xaa33e  callvirt instance void System.Xml.Serialization.XmlSerializationGeneratedCode::Dispose()
0xaa343  endfinally
0xaa344  ldarg.0
0xaa345  ldfld    class System.Xml.Serialization.TempAssembly System.Xml.Serialization.XmlSerializer::tempAssembly
0xaa34a  ldarg.0
0xaa34b  ldfld    class System.Xml.Serialization.XmlMapping System.Xml.Serialization.XmlSerializer::mapping
0xaa350  ldarg.1
0xaa351  ldarg.3
0xaa352  ldarg.2
0xaa353  callvirt instance object System.Xml.Serialization.TempAssembly::InvokeReader(class System.Xml.Serialization.XmlMapping mapping, class System.Xml.XmlReader xmlReader, valuetype System.Xml.Serialization.XmlDeserializationEvents events, string encodingStyle)
0xaa358  stloc.0
0xaa359  leave    loc_AA3ED
0xaa35e  stloc.2
0xaa35f  ldloc.2
0xaa360  isinst   [mscorlib]System.Threading.ThreadAbortException
0xaa365  brtrue.s loc_AA377
0xaa367  ldloc.2
0xaa368  isinst   [mscorlib]System.StackOverflowException
0xaa36d  brtrue.s loc_AA377
0xaa36f  ldloc.2
0xaa370  isinst   [mscorlib]System.OutOfMemoryException
0xaa375  brfalse.s loc_AA379
0xaa377  rethrow
0xaa379  ldloc.2
0xaa37a  isinst   [mscorlib]System.Reflection.TargetInvocationException
0xaa37f  brfalse.s loc_AA388
0xaa381  ldloc.2
0xaa382  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xaa387  stloc.2
0xaa388  ldarg.1
0xaa389  isinst   System.Xml.IXmlLineInfo
0xaa38e  brfalse.s loc_AA3DC
0xaa390  ldarg.1
0xaa391  castclass System.Xml.IXmlLineInfo
0xaa396  stloc.3
0xaa397  ldstr    aXmlserializeer// "XmlSerializeErrorDetails"
0xaa39c  ldc.i4.2
0xaa39d  newarr   [mscorlib]System.Object
0xaa3a2  dup
0xaa3a3  ldc.i4.0
0xaa3a4  ldloc.3
0xaa3a5  callvirt instance int32 System.Xml.IXmlLineInfo::get_LineNumber()
0xaa3aa  stloc.s  4
0xaa3ac  ldloca.s 4
0xaa3ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa3b3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xaa3b8  stelem.ref
0xaa3b9  dup
0xaa3ba  ldc.i4.1
0xaa3bb  ldloc.3
0xaa3bc  callvirt instance int32 System.Xml.IXmlLineInfo::get_LinePosition()
0xaa3c1  stloc.s  4
0xaa3c3  ldloca.s 4
0xaa3c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa3ca  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xaa3cf  stelem.ref
0xaa3d0  call     string System.Xml.Res::GetString(string name, object[] args)
0xaa3d5  ldloc.2
0xaa3d6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0xaa3db  throw
0xaa3dc  ldstr    aXmlserializeer_0// "XmlSerializeError"
0xaa3e1  call     string System.Xml.Res::GetString(string name)
0xaa3e6  ldloc.2
0xaa3e7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0xaa3ec  throw
0xaa3ed  ldloc.0
0xaa3ee  ret
```
