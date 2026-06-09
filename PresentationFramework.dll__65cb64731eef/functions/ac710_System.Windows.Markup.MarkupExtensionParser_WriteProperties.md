# System.Windows.Markup.MarkupExtensionParser::WriteProperties

- ea: `0xac710`
- end: `0xac911`
- name: `System.Windows.Markup.MarkupExtensionParser::WriteProperties`
- size: `513`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0xabda0`
- `0xabfb0`

## callees

- `0x89c40`
- `0xab610`
- `0xabc20`
- `0xac710`
- `0xac920`
- `0xac980`
- `0xacb90`
- `0xacc00`

## string_xrefs

- `0xac765`: `ParserMarkupExtensionNoNameValue`
- `0xac7a2`: `ParserDuplicateMarkupExtensionProperty`

## pseudocode

```c

```

## disassembly

```asm
0xac710  ldarg.2
0xac711  brfalse  loc_AC910
0xac716  ldarg.3
0xac717  ldarg.2
0xac718  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xac71d  bge      loc_AC910
0xac722  ldarg.2
0xac723  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xac728  ldc.i4.4
0xac729  div
0xac72a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0xac72f  stloc.0
0xac730  ldarg.3
0xac731  stloc.1
0xac732  br       loc_AC904
0xac737  ldloc.1
0xac738  ldarg.2
0xac739  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xac73e  ldc.i4.3
0xac73f  sub
0xac740  bgt.s    loc_AC764
0xac742  ldarg.2
0xac743  ldloc.1
0xac744  ldc.i4.1
0xac745  add
0xac746  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xac74b  isinst   [mscorlib]System.String
0xac750  brtrue.s loc_AC764
0xac752  ldarg.2
0xac753  ldloc.1
0xac754  ldc.i4.1
0xac755  add
0xac756  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xac75b  unbox.any [mscorlib]System.Char
0xac760  ldc.i4.s 0x3D
0xac762  beq.s    loc_AC784
0xac764  ldarg.0
0xac765  ldstr    aParsermarkupex_7// "ParserMarkupExtensionNoNameValue"
0xac76a  ldarg.s  4
0xac76c  ldfld    string System.Windows.Markup.DefAttributeData::Args
0xac771  ldarg.s  4
0xac773  ldfld    int32 System.Windows.Markup.DefAttributeData::LineNumber
0xac778  ldarg.s  4
0xac77a  ldfld    int32 System.Windows.Markup.DefAttributeData::LinePosition
0xac77f  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, int32 lineNumber, int32 linePosition)
0xac784  ldarg.2
0xac785  ldloc.1
0xac786  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xac78b  isinst   [mscorlib]System.String
0xac790  stloc.2
0xac791  ldloc.2
0xac792  callvirt instance string [mscorlib]System.String::Trim()
0xac797  stloc.2
0xac798  ldloc.0
0xac799  ldloc.2
0xac79a  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xac79f  brfalse.s loc_AC7BB
0xac7a1  ldarg.0
0xac7a2  ldstr    aParserduplicat// "ParserDuplicateMarkupExtensionProperty"
0xac7a7  ldloc.2
0xac7a8  ldarg.s  4
0xac7aa  ldfld    int32 System.Windows.Markup.DefAttributeData::LineNumber
0xac7af  ldarg.s  4
0xac7b1  ldfld    int32 System.Windows.Markup.DefAttributeData::LinePosition
0xac7b6  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, int32 lineNumber, int32 linePosition)
0xac7bb  ldloc.0
0xac7bc  ldloc.2
0xac7bd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xac7c2  pop
0xac7c3  ldloc.2
0xac7c4  ldc.i4.s 0x3A
0xac7c6  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xac7cb  stloc.3
0xac7cc  ldloc.3
0xac7cd  ldc.i4.0
0xac7ce  blt.s    loc_AC7DB
0xac7d0  ldloc.2
0xac7d1  ldloc.3
0xac7d2  ldc.i4.1
0xac7d3  add
0xac7d4  callvirt instance string [mscorlib]System.String::Substring(int32)
0xac7d9  br.s     loc_AC7DC
0xac7db  ldloc.2
0xac7dc  stloc.s  4
0xac7de  ldloc.3
0xac7df  ldc.i4.0
0xac7e0  blt.s    loc_AC7EC
0xac7e2  ldloc.2
0xac7e3  ldc.i4.0
0xac7e4  ldloc.3
0xac7e5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xac7ea  br.s     loc_AC7F1
0xac7ec  ldsfld   string [mscorlib]System.String::Empty
0xac7f1  stloc.s  5
0xac7f3  ldarg.0
0xac7f4  ldloc.s  5
0xac7f6  ldloc.s  4
0xac7f8  ldarg.s  4
0xac7fa  ldfld    string System.Windows.Markup.DefAttributeData::TargetNamespaceUri
0xac7ff  call     instance string System.Windows.Markup.MarkupExtensionParser::ResolveAttributeNamespaceURI(string prefix, string name, string parentURI)
0xac804  stloc.s  6
0xac806  ldarg.0
0xac807  ldarg.s  4
0xac809  ldfld    class [mscorlib]System.Type System.Windows.Markup.DefAttributeData::TargetType
0xac80e  ldarg.s  4
0xac810  ldfld    string System.Windows.Markup.DefAttributeData::TargetNamespaceUri
0xac815  ldloc.s  6
0xac817  ldloc.s  4
0xac819  ldloca.s 7
0xac81b  ldloca.s 8
0xac81d  ldloca.s 9
0xac81f  ldloca.s 0xA
0xac821  ldloca.s 0xB
0xac823  call     instance valuetype System.Windows.Markup.AttributeContext System.Windows.Markup.MarkupExtensionParser::GetAttributeContext(class [mscorlib]System.Type elementBaseType, string elementBaseTypeNamespaceUri, string attributeNamespaceUri, string attributeLocalName, [out] object& dynamicObject, [out] string& assemblyName, [out] string& typeFullName, [out] class [mscorlib]System.Type& declaringType, [out] string& dynamicObjectName)
0xac828  stloc.s  0xC
0xac82a  ldarg.2
0xac82b  ldloc.1
0xac82c  ldc.i4.2
0xac82d  add
0xac82e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xac833  isinst   [mscorlib]System.String
0xac838  stloc.s  0xD
0xac83a  ldarg.0
0xac83b  ldarg.s  4
0xac83d  ldfld    class [mscorlib]System.Type System.Windows.Markup.DefAttributeData::TargetType
0xac842  ldloc.2
0xac843  ldloca.s 0xD
0xac845  ldarg.s  4
0xac847  ldfld    int32 System.Windows.Markup.DefAttributeData::LineNumber
0xac84c  ldarg.s  4
0xac84e  ldfld    int32 System.Windows.Markup.DefAttributeData::LinePosition
0xac853  ldarg.s  4
0xac855  ldfld    int32 System.Windows.Markup.DefAttributeData::Depth
0xac85a  ldloc.s  7
0xac85c  call     instance class System.Windows.Markup.AttributeData System.Windows.Markup.MarkupExtensionParser::IsMarkupExtensionAttribute(class [mscorlib]System.Type declaringType, string propIdName, string& attrValue, int32 lineNumber, int32 linePosition, int32 depth, object info)
0xac861  stloc.s  0xE
0xac863  ldarg.2
0xac864  ldloc.1
0xac865  ldc.i4.2
0xac866  add
0xac867  ldloc.s  0xD
0xac869  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xac86e  ldarg.s  4
0xac870  callvirt instance bool System.Windows.Markup.DefAttributeData::get_IsUnknownExtension()
0xac875  brfalse.s loc_AC878
0xac877  ret
0xac878  ldloc.s  0xE
0xac87a  brfalse.s loc_AC8C6
0xac87c  ldloc.s  0xE
0xac87e  ldfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0xac883  brfalse.s loc_AC8BB
0xac885  ldarg.0
0xac886  ldarg.1
0xac887  ldloc.2
0xac888  ldloc.s  0xE
0xac88a  ldfld    string System.Windows.Markup.DefAttributeData::Args
0xac88f  ldarg.s  4
0xac891  ldfld    class [mscorlib]System.Type System.Windows.Markup.DefAttributeData::TargetType
0xac896  ldarg.s  4
0xac898  ldfld    string System.Windows.Markup.DefAttributeData::TargetNamespaceUri
0xac89d  ldloc.s  0xE
0xac89f  ldloc.s  0xE
0xac8a1  ldfld    int32 System.Windows.Markup.DefAttributeData::LineNumber
0xac8a6  ldloc.s  0xE
0xac8a8  ldfld    int32 System.Windows.Markup.DefAttributeData::LinePosition
0xac8ad  ldloc.s  0xE
0xac8af  ldfld    int32 System.Windows.Markup.DefAttributeData::Depth
0xac8b4  call     instance void System.Windows.Markup.MarkupExtensionParser::CompileProperty(class [mscorlib]System.Collections.ArrayList xamlNodes, string name, string value, class [mscorlib]System.Type parentType, string parentTypeNamespaceUri, class System.Windows.Markup.AttributeData data, int32 lineNumber, int32 linePosition, int32 depth)
0xac8b9  br.s     loc_AC900
0xac8bb  ldarg.0
0xac8bc  ldarg.1
0xac8bd  ldloc.s  0xE
0xac8bf  call     instance void System.Windows.Markup.MarkupExtensionParser::CompileAttribute(class [mscorlib]System.Collections.ArrayList xamlNodes, class System.Windows.Markup.AttributeData data)
0xac8c4  br.s     loc_AC900
0xac8c6  ldarg.0
0xac8c7  ldarg.1
0xac8c8  ldloc.2
0xac8c9  ldarg.2
0xac8ca  ldloc.1
0xac8cb  ldc.i4.2
0xac8cc  add
0xac8cd  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xac8d2  castclass [mscorlib]System.String
0xac8d7  ldarg.s  4
0xac8d9  ldfld    class [mscorlib]System.Type System.Windows.Markup.DefAttributeData::TargetType
0xac8de  ldarg.s  4
0xac8e0  ldfld    string System.Windows.Markup.DefAttributeData::TargetNamespaceUri
0xac8e5  ldnull
0xac8e6  ldarg.s  4
0xac8e8  ldfld    int32 System.Windows.Markup.DefAttributeData::LineNumber
0xac8ed  ldarg.s  4
0xac8ef  ldfld    int32 System.Windows.Markup.DefAttributeData::LinePosition
0xac8f4  ldarg.s  4
0xac8f6  ldfld    int32 System.Windows.Markup.DefAttributeData::Depth
0xac8fb  call     instance void System.Windows.Markup.MarkupExtensionParser::CompileProperty(class [mscorlib]System.Collections.ArrayList xamlNodes, string name, string value, class [mscorlib]System.Type parentType, string parentTypeNamespaceUri, class System.Windows.Markup.AttributeData data, int32 lineNumber, int32 linePosition, int32 depth)
0xac900  ldloc.1
0xac901  ldc.i4.4
0xac902  add
0xac903  stloc.1
0xac904  ldloc.1
0xac905  ldarg.2
0xac906  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xac90b  blt      loc_AC737
0xac910  ret
```
