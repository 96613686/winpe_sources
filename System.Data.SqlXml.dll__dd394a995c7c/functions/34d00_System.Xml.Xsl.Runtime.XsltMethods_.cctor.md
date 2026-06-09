# System.Xml.Xsl.Runtime.XsltMethods::.cctor

- ea: `0x34d00`
- end: `0x35124`
- name: `System.Xml.Xsl.Runtime.XsltMethods::.cctor`
- size: `1060`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x34ce0`
- `0x34cf0`

## string_xrefs

- `0x34f20`: `SystemProperty`
- `0x34f39`: `BaseUri`
- `0x34f52`: `OuterXml`
- `0x34f9d`: `MSStringCompare`
- `0x35001`: `MSNamespaceUri`

## pseudocode

```c

```

## disassembly

```asm
0x34d00  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x34d05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d0a  ldstr    aFormatmessage// "FormatMessage"
0x34d0f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34d14  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::FormatMessage
0x34d19  ldtoken  System.Xml.Xsl.Runtime.XsltConvert
0x34d1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d23  ldstr    aEnsurenodeset// "EnsureNodeSet"
0x34d28  ldc.i4.1
0x34d29  newarr   [mscorlib]System.Type
0x34d2e  dup
0x34d2f  ldc.i4.0
0x34d30  ldtoken  class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem>
0x34d35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d3a  stelem.ref
0x34d3b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x34d40  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::EnsureNodeSet
0x34d45  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x34d4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d4f  ldstr    aEqualityoperat// "EqualityOperator"
0x34d54  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34d59  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::EqualityOperator
0x34d5e  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x34d63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d68  ldstr    aRelationaloper// "RelationalOperator"
0x34d6d  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34d72  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::RelationalOperator
0x34d77  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34d7c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d81  ldstr    aStartswith// "StartsWith"
0x34d86  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34d8b  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::StartsWith
0x34d90  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34d95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d9a  ldstr    aContains_0// "Contains"
0x34d9f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34da4  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Contains
0x34da9  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34dae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34db3  ldstr    aSubstringbefor// "SubstringBefore"
0x34db8  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34dbd  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::SubstringBefore
0x34dc2  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34dc7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34dcc  ldstr    aSubstringafter// "SubstringAfter"
0x34dd1  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34dd6  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::SubstringAfter
0x34ddb  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34de0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34de5  ldstr    aSubstring_0// "Substring"
0x34dea  ldc.i4.2
0x34deb  newarr   [mscorlib]System.Type
0x34df0  dup
0x34df1  ldc.i4.0
0x34df2  ldtoken  [mscorlib]System.String
0x34df7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34dfc  stelem.ref
0x34dfd  dup
0x34dfe  ldc.i4.1
0x34dff  ldtoken  [mscorlib]System.Double
0x34e04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e09  stelem.ref
0x34e0a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x34e0f  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Substring2
0x34e14  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34e19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e1e  ldstr    aSubstring_0// "Substring"
0x34e23  ldc.i4.3
0x34e24  newarr   [mscorlib]System.Type
0x34e29  dup
0x34e2a  ldc.i4.0
0x34e2b  ldtoken  [mscorlib]System.String
0x34e30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e35  stelem.ref
0x34e36  dup
0x34e37  ldc.i4.1
0x34e38  ldtoken  [mscorlib]System.Double
0x34e3d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e42  stelem.ref
0x34e43  dup
0x34e44  ldc.i4.2
0x34e45  ldtoken  [mscorlib]System.Double
0x34e4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e4f  stelem.ref
0x34e50  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x34e55  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Substring3
0x34e5a  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34e5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e64  ldstr    aNormalizespace// "NormalizeSpace"
0x34e69  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34e6e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::NormalizeSpace
0x34e73  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34e78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e7d  ldstr    aTranslate_0// "Translate"
0x34e82  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34e87  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Translate
0x34e8c  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34e91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e96  ldstr    aLang_0// "Lang"
0x34e9b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34ea0  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Lang
0x34ea5  ldtoken  [mscorlib]System.Math
0x34eaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34eaf  ldstr    aFloor_0// "Floor"
0x34eb4  ldc.i4.1
0x34eb5  newarr   [mscorlib]System.Type
0x34eba  dup
0x34ebb  ldc.i4.0
0x34ebc  ldtoken  [mscorlib]System.Double
0x34ec1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34ec6  stelem.ref
0x34ec7  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x34ecc  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Floor
0x34ed1  ldtoken  [mscorlib]System.Math
0x34ed6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34edb  ldstr    aCeiling_0// "Ceiling"
0x34ee0  ldc.i4.1
0x34ee1  newarr   [mscorlib]System.Type
0x34ee6  dup
0x34ee7  ldc.i4.0
0x34ee8  ldtoken  [mscorlib]System.Double
0x34eed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34ef2  stelem.ref
0x34ef3  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x34ef8  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Ceiling
0x34efd  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f07  ldstr    aRound_0// "Round"
0x34f0c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f11  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::Round
0x34f16  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f20  ldstr    aSystemproperty// "SystemProperty"
0x34f25  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f2a  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::SystemProperty
0x34f2f  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f34  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f39  ldstr    aBaseuri_0// "BaseUri"
0x34f3e  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f43  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::BaseUri
0x34f48  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f52  ldstr    aOuterxml// "OuterXml"
0x34f57  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f5c  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::OuterXml
0x34f61  ldtoken  System.Xml.Xsl.Runtime.XmlQueryRuntime
0x34f66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f6b  ldstr    aOncurrentnodec// "OnCurrentNodeChanged"
0x34f70  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f75  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::OnCurrentNodeChanged
0x34f7a  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f84  ldstr    aMsformatdateti// "MSFormatDateTime"
0x34f89  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34f8e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSFormatDateTime
0x34f93  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34f98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34f9d  ldstr    aMsstringcompar// "MSStringCompare"
0x34fa2  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34fa7  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSStringCompare
0x34fac  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34fb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34fb6  ldstr    aMsutc// "MSUtc"
0x34fbb  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34fc0  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSUtc
0x34fc5  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34fca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34fcf  ldstr    aMsnumber// "MSNumber"
0x34fd4  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34fd9  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSNumber
0x34fde  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34fe3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34fe8  ldstr    aMslocalname// "MSLocalName"
0x34fed  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x34ff2  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSLocalName
0x34ff7  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x34ffc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35001  ldstr    aMsnamespaceuri// "MSNamespaceUri"
0x35006  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3500b  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSNamespaceUri
0x35010  ldtoken  System.Xml.Xsl.Runtime.XsltFunctions
0x35015  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3501a  ldstr    aExslobjecttype// "EXslObjectType"
0x3501f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x35024  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::EXslObjectType
0x35029  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x3502e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35033  ldstr    aCheckscriptnam// "CheckScriptNamespace"
0x35038  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3503d  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::CheckScriptNamespace
0x35042  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x35047  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3504c  ldstr    aFunctionavaila// "FunctionAvailable"
0x35051  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x35056  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::FunctionAvailable
0x3505b  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x35060  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35065  ldstr    aElementavailab// "ElementAvailable"
0x3506a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3506f  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::ElementAvailable
0x35074  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x35079  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3507e  ldstr    aRegisterdecima// "RegisterDecimalFormat"
0x35083  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x35088  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::RegisterDecimalFormat
0x3508d  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x35092  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35097  ldstr    aRegisterdecima_0// "RegisterDecimalFormatter"
0x3509c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x350a1  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::RegisterDecimalFormatter
0x350a6  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x350ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x350b0  ldstr    aFormatnumberst// "FormatNumberStatic"
0x350b5  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x350ba  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::FormatNumberStatic
0x350bf  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x350c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x350c9  ldstr    aFormatnumberdy// "FormatNumberDynamic"
0x350ce  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x350d3  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::FormatNumberDynamic
0x350d8  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x350dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x350e2  ldstr    aIssamenodesort// "IsSameNodeSort"
0x350e7  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x350ec  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::IsSameNodeSort
0x350f1  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x350f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x350fb  ldstr    aLangtolcid// "LangToLcid"
0x35100  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x35105  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::LangToLcid
0x3510a  ldtoken  System.Xml.Xsl.Runtime.XsltLibrary
0x3510f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35114  ldstr    aNumberformat// "NumberFormat"
0x35119  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3511e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::NumberFormat
0x35123  ret
```
