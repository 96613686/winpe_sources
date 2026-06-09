# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElementType

- ea: `0x5e10`
- end: `0x5e80`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElementType`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5ac0`
- `0x5d50`

## callees

- `0x4fd0`
- `0x4ff0`
- `0x5e10`
- `0x6450`

## pseudocode

```c

```

## disassembly

```asm
0x5e10  ldarg.1
0x5e11  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5e16  ldstr    aType// "Type"
0x5e1b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5e20  dup
0x5e21  brtrue.s loc_5E2D
0x5e23  ldstr    aType// "Type"
0x5e28  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowElementMissing(string element)
0x5e2d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5e32  stloc.0
0x5e33  ldloc.0
0x5e34  ldc.i4.s 0x2C
0x5e36  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x5e3b  stloc.1
0x5e3c  ldloc.1
0x5e3d  ldc.i4.0
0x5e3e  ble.s    loc_5E4B
0x5e40  ldloc.1
0x5e41  ldloc.0
0x5e42  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5e47  ldc.i4.1
0x5e48  sub
0x5e49  bne.un.s loc_5E56
0x5e4b  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_EmptyExtensionName()
0x5e50  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x5e55  throw
0x5e56  ldarg.2
0x5e57  ldind.ref
0x5e58  ldloc.0
0x5e59  ldc.i4.0
0x5e5a  ldloc.1
0x5e5b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x5e60  callvirt instance string [mscorlib]System.String::Trim()
0x5e65  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Class(string value)
0x5e6a  ldarg.2
0x5e6b  ldind.ref
0x5e6c  ldloc.0
0x5e6d  ldloc.1
0x5e6e  ldc.i4.1
0x5e6f  add
0x5e70  callvirt instance string [mscorlib]System.String::Substring(int32)
0x5e75  callvirt instance string [mscorlib]System.String::Trim()
0x5e7a  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Assembly(string value)
0x5e7f  ret
```
