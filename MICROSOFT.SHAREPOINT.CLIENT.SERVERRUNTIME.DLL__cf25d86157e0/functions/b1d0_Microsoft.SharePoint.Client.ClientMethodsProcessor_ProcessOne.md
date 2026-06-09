# Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessOne

- ea: `0xb1d0`
- end: `0xb2dd`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessOne`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xb820`

## callees

- `0x98e0`
- `0xb1d0`
- `0xb2e0`
- `0xb440`
- `0xb550`
- `0xb620`
- `0xb690`
- `0xb6e0`
- `0xb770`
- `0xb870`
- `0xbb80`
- `0x187a0`

## string_xrefs

- `0xb269`: `ObjectPath`

## pseudocode

```c

```

## disassembly

```asm
0xb1d0  ldarg.0
0xb1d1  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xb1d6  ldarg.0
0xb1d7  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Client.ClientMethodsProcessor::m_dtTimeout
0xb1dc  call     void Microsoft.SharePoint.Client.Utility::ThrowIfTimeout(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, valuetype [mscorlib]System.DateTime dtTimeout)
0xb1e1  ldarg.1
0xb1e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb1e7  ldstr    aQuery_0// "Query"
0xb1ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb1f1  brfalse.s loc_B1FB
0xb1f3  ldarg.0
0xb1f4  ldarg.1
0xb1f5  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessQuery(class [System.Xml]System.Xml.XmlElement xe)
0xb1fa  ret
0xb1fb  ldarg.1
0xb1fc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb201  ldstr    aMethod// "Method"
0xb206  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb20b  brfalse.s loc_B215
0xb20d  ldarg.0
0xb20e  ldarg.1
0xb20f  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessMethod(class [System.Xml]System.Xml.XmlElement xe)
0xb214  ret
0xb215  ldarg.1
0xb216  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb21b  ldstr    aStaticmethod// "StaticMethod"
0xb220  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb225  brfalse.s loc_B22F
0xb227  ldarg.0
0xb228  ldarg.1
0xb229  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessStaticMethod(class [System.Xml]System.Xml.XmlElement xe)
0xb22e  ret
0xb22f  ldarg.1
0xb230  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb235  ldstr    aSetproperty// "SetProperty"
0xb23a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb23f  brfalse.s loc_B249
0xb241  ldarg.0
0xb242  ldarg.1
0xb243  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessSetProperty(class [System.Xml]System.Xml.XmlElement xe)
0xb248  ret
0xb249  ldarg.1
0xb24a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb24f  ldstr    aSetstaticprope// "SetStaticProperty"
0xb254  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb259  brfalse.s loc_B263
0xb25b  ldarg.0
0xb25c  ldarg.1
0xb25d  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessSetStaticProperty(class [System.Xml]System.Xml.XmlElement xe)
0xb262  ret
0xb263  ldarg.1
0xb264  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb269  ldstr    aObjectpath// "ObjectPath"
0xb26e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb273  brfalse.s loc_B27D
0xb275  ldarg.0
0xb276  ldarg.1
0xb277  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessInstantiateObjectPath(class [System.Xml]System.Xml.XmlElement xe)
0xb27c  ret
0xb27d  ldarg.1
0xb27e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb283  ldstr    aObjectidentity_0// "ObjectIdentityQuery"
0xb288  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb28d  brfalse.s loc_B297
0xb28f  ldarg.0
0xb290  ldarg.1
0xb291  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessObjectIdentityQuery(class [System.Xml]System.Xml.XmlElement xe)
0xb296  ret
0xb297  ldarg.1
0xb298  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb29d  ldstr    aExceptionhandl// "ExceptionHandlingScope"
0xb2a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2a7  brtrue.s loc_B2BB
0xb2a9  ldarg.1
0xb2aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb2af  ldstr    aExceptionhandl_0// "ExceptionHandlingScopeSimple"
0xb2b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2b9  brfalse.s loc_B2C3
0xb2bb  ldarg.0
0xb2bc  ldarg.1
0xb2bd  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessExceptionHandlingScope(class [System.Xml]System.Xml.XmlElement xe)
0xb2c2  ret
0xb2c3  ldarg.1
0xb2c4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb2c9  ldstr    aConditionalsco// "ConditionalScope"
0xb2ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2d3  brfalse.s loc_B2DC
0xb2d5  ldarg.0
0xb2d6  ldarg.1
0xb2d7  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessConditionalScope(class [System.Xml]System.Xml.XmlElement xe)
0xb2dc  ret
```
