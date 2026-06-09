# System.Xml.Xsl.XmlQueryType::ItemTypeToString

- ea: `0x2820`
- end: `0x28e9`
- name: `System.Xml.Xsl.XmlQueryType::ItemTypeToString`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x24f0`

## callees

- `0x1f80`
- `0x1fa0`
- `0x1fd0`
- `0x23d0`
- `0x2820`
- `0x28f0`
- `0x29c0`

## string_xrefs

- `0x285b`: `?&text?&comment?&processing-instruction?)*}`

## pseudocode

```c

```

## disassembly

```asm
0x2820  ldarg.0
0x2821  call     instance bool System.Xml.Xsl.XmlQueryType::get_IsNode()
0x2826  brfalse.s loc_2878
0x2828  ldsfld   string[] System.Xml.Xsl.XmlQueryType::TypeNames
0x282d  ldarg.0
0x282e  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x2833  ldelem.ref
0x2834  stloc.0
0x2835  ldarg.0
0x2836  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x283b  stloc.1
0x283c  ldloc.1
0x283d  ldc.i4.3
0x283e  beq.s    loc_284B
0x2840  ldloc.1
0x2841  ldc.i4.4
0x2842  sub
0x2843  ldc.i4.1
0x2844  ble.un.s loc_2868
0x2846  br       loc_28D0
0x284b  ldarg.1
0x284c  brfalse.s loc_2868
0x284e  ldloc.0
0x284f  ldstr    aElement_0// "{(element"
0x2854  ldarg.0
0x2855  ldc.i4.1
0x2856  call     instance string System.Xml.Xsl.XmlQueryType::NameAndType(bool isXQ)
0x285b  ldstr    aTextCommentPro// "?&text?&comment?&processing-instruction"...
0x2860  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2865  stloc.0
0x2866  br.s     loc_28D0
0x2868  ldloc.0
0x2869  ldarg.0
0x286a  ldarg.1
0x286b  call     instance string System.Xml.Xsl.XmlQueryType::NameAndType(bool isXQ)
0x2870  call     string [mscorlib]System.String::Concat(string, string)
0x2875  stloc.0
0x2876  br.s     loc_28D0
0x2878  ldarg.0
0x2879  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType System.Xml.Xsl.XmlQueryType::get_SchemaType()
0x287e  call     class [System.Xml]System.Xml.Schema.XmlSchemaComplexType [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_AnyType()
0x2883  beq.s    loc_28C3
0x2885  ldarg.0
0x2886  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType System.Xml.Xsl.XmlQueryType::get_SchemaType()
0x288b  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x2890  callvirt instance bool [System.Xml]System.Xml.XmlQualifiedName::get_IsEmpty()
0x2895  brfalse.s loc_28B0
0x2897  ldstr    asc_586FA// "<:"
0x289c  ldsfld   string[] System.Xml.Xsl.XmlQueryType::TypeNames
0x28a1  ldarg.0
0x28a2  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x28a7  ldelem.ref
0x28a8  call     string [mscorlib]System.String::Concat(string, string)
0x28ad  stloc.0
0x28ae  br.s     loc_28D0
0x28b0  ldarg.0
0x28b1  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType System.Xml.Xsl.XmlQueryType::get_SchemaType()
0x28b6  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x28bb  call     string System.Xml.Xsl.XmlQueryType::QNameToString(class [System.Xml]System.Xml.XmlQualifiedName name)
0x28c0  stloc.0
0x28c1  br.s     loc_28D0
0x28c3  ldsfld   string[] System.Xml.Xsl.XmlQueryType::TypeNames
0x28c8  ldarg.0
0x28c9  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x28ce  ldelem.ref
0x28cf  stloc.0
0x28d0  ldarg.1
0x28d1  brtrue.s loc_28E7
0x28d3  ldarg.0
0x28d4  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsStrict()
0x28d9  brfalse.s loc_28E7
0x28db  ldloc.0
0x28dc  ldstr    asc_58700// "="
0x28e1  call     string [mscorlib]System.String::Concat(string, string)
0x28e6  stloc.0
0x28e7  ldloc.0
0x28e8  ret
```
