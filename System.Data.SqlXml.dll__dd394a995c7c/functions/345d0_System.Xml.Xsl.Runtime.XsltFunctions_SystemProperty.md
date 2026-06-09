# System.Xml.Xsl.Runtime.XsltFunctions::SystemProperty

- ea: `0x345d0`
- end: `0x346a3`
- name: `System.Xml.Xsl.Runtime.XsltFunctions::SystemProperty`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bc30`

## callees

- `0x345d0`

## string_xrefs

- `0x34652`: `urn:schemas-microsoft-com:xslt`
- `0x34641`: `http://www.microsoft.com`

## pseudocode

```c

```

## disassembly

```asm
0x345d0  ldarg.0
0x345d1  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x345d6  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x345db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x345e0  brfalse.s loc_3464C
0x345e2  ldarg.0
0x345e3  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x345e8  stloc.0
0x345e9  ldloc.0
0x345ea  ldstr    aVersion// "version"
0x345ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x345f4  brtrue.s loc_34612
0x345f6  ldloc.0
0x345f7  ldstr    aVendor// "vendor"
0x345fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34601  brtrue.s loc_34628
0x34603  ldloc.0
0x34604  ldstr    aVendorUrl// "vendor-url"
0x34609  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3460e  brtrue.s loc_3463A
0x34610  br.s     loc_34691
0x34612  ldc.i4.s 0x10
0x34614  call     class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType [System.Xml]System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype [System.Xml]System.Xml.Schema.XmlTypeCode)
0x34619  ldc.r8   1.0
0x34622  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, float64)
0x34627  ret
0x34628  ldc.i4.s 0xC
0x3462a  call     class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType [System.Xml]System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype [System.Xml]System.Xml.Schema.XmlTypeCode)
0x3462f  ldstr    aMicrosoft// "Microsoft"
0x34634  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, string)
0x34639  ret
0x3463a  ldc.i4.s 0xC
0x3463c  call     class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType [System.Xml]System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype [System.Xml]System.Xml.Schema.XmlTypeCode)
0x34641  ldstr    aHttpWwwMicroso// "http://www.microsoft.com"
0x34646  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, string)
0x3464b  ret
0x3464c  ldarg.0
0x3464d  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x34652  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x34657  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3465c  brfalse.s loc_34691
0x3465e  ldarg.0
0x3465f  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x34664  ldstr    aVersion// "version"
0x34669  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3466e  brfalse.s loc_34691
0x34670  ldc.i4.s 0xC
0x34672  call     class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType [System.Xml]System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype [System.Xml]System.Xml.Schema.XmlTypeCode)
0x34677  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x3467c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34681  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x34686  callvirt instance string [mscorlib]System.Reflection.Assembly::get_ImageRuntimeVersion()
0x3468b  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, string)
0x34690  ret
0x34691  ldc.i4.s 0xC
0x34693  call     class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType [System.Xml]System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype [System.Xml]System.Xml.Schema.XmlTypeCode)
0x34698  ldsfld   string [mscorlib]System.String::Empty
0x3469d  newobj   instance void [System.Xml]System.Xml.Schema.XmlAtomicValue::.ctor(class [System.Xml]System.Xml.Schema.XmlSchemaType, string)
0x346a2  ret
```
