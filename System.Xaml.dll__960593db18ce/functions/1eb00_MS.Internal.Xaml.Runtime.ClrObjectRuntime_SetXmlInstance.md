# MS.Internal.Xaml.Runtime.ClrObjectRuntime::SetXmlInstance

- ea: `0x1eb00`
- end: `0x1eb94`
- name: `MS.Internal.Xaml.Runtime.ClrObjectRuntime::SetXmlInstance`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x12d0`
- `0x8750`
- `0xa4c0`
- `0x11f50`
- `0x1ca50`
- `0x1eb00`
- `0x1ed60`
- `0x1ed70`
- `0x202b0`

## string_xrefs

- `0x1eb15`: `XmlDataNull`
- `0x1eb43`: `XmlValueNotReader`
- `0x1eb78`: `SetXmlInstance`

## pseudocode

```c

```

## disassembly

```asm
0x1eb00  ldarg.0
0x1eb01  ldarg.1
0x1eb02  ldarg.2
0x1eb03  ldc.i4.1
0x1eb04  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property, bool failIfWriteOnly)
0x1eb09  stloc.0
0x1eb0a  ldloc.0
0x1eb0b  isinst   [System.Xml]System.Xml.Serialization.IXmlSerializable
0x1eb10  stloc.1
0x1eb11  ldloc.1
0x1eb12  brtrue.s loc_1EB34
0x1eb14  ldarg.0
0x1eb15  ldstr    aXmldatanull// "XmlDataNull"
0x1eb1a  ldc.i4.1
0x1eb1b  newarr   [mscorlib]System.Object
0x1eb20  dup
0x1eb21  ldc.i4.0
0x1eb22  ldarg.2
0x1eb23  callvirt instance string System.Xaml.XamlMember::get_Name()
0x1eb28  stelem.ref
0x1eb29  call     string System.Xaml.SR::Get(string id, object[] args)
0x1eb2e  call     instance class System.Xaml.XamlException MS.Internal.Xaml.Runtime.ClrObjectRuntime::CreateException(string message)
0x1eb33  throw
0x1eb34  ldarg.3
0x1eb35  callvirt instance object System.Windows.Markup.XData::get_XmlReader()
0x1eb3a  isinst   [System.Xml]System.Xml.XmlReader
0x1eb3f  stloc.2
0x1eb40  ldloc.2
0x1eb41  brtrue.s loc_1EB62
0x1eb43  ldstr    aXmlvaluenotrea// "XmlValueNotReader"
0x1eb48  ldc.i4.1
0x1eb49  newarr   [mscorlib]System.Object
0x1eb4e  dup
0x1eb4f  ldc.i4.0
0x1eb50  ldarg.2
0x1eb51  callvirt instance string System.Xaml.XamlMember::get_Name()
0x1eb56  stelem.ref
0x1eb57  call     string System.Xaml.SR::Get(string id, object[] args)
0x1eb5c  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1eb61  throw
0x1eb62  nop
0x1eb63  ldloc.1
0x1eb64  ldloc.2
0x1eb65  callvirt instance void [System.Xml]System.Xml.Serialization.IXmlSerializable::ReadXml(class [System.Xml]System.Xml.XmlReader)
0x1eb6a  leave.s  loc_1EB93
0x1eb6c  stloc.3
0x1eb6d  ldloc.3
0x1eb6e  call     bool System.Xaml.CriticalExceptions::IsCriticalException(class [mscorlib]System.Exception ex)
0x1eb73  brfalse.s loc_1EB77
0x1eb75  rethrow
0x1eb77  ldarg.0
0x1eb78  ldstr    aSetxmlinstance// "SetXmlInstance"
0x1eb7d  ldc.i4.1
0x1eb7e  newarr   [mscorlib]System.Object
0x1eb83  dup
0x1eb84  ldc.i4.0
0x1eb85  ldarg.2
0x1eb86  stelem.ref
0x1eb87  call     string System.Xaml.SR::Get(string id, object[] args)
0x1eb8c  ldloc.3
0x1eb8d  call     instance class System.Xaml.XamlException MS.Internal.Xaml.Runtime.ClrObjectRuntime::CreateException(string message, class [mscorlib]System.Exception innerException)
0x1eb92  throw
0x1eb93  ret
```
