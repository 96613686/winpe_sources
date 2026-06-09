# System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateAssembly

- ea: `0x132e20`
- end: `0x1333f5`
- name: `System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateAssembly`
- size: `1493`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x132030`

## callees

- `0xef0`
- `0x18c20`
- `0x34fa0`
- `0x131fc0`
- `0x132e20`
- `0x133400`
- `0x1334b0`
- `0x133750`
- `0x133870`
- `0x133880`
- `0x134850`
- `0x134860`
- `0x13efb0`
- `0x1430d0`
- `0x143140`
- `0x1585f0`

## string_xrefs

- `0x132ecd`: `System.Security.AllowPartiallyTrustedCallers`
- `0x132f69`: `System.Web.Configuration`
- `0x132fd1`: `System.Web.Configuration.BrowserCapabilitiesFactoryBase`
- `0x13301b`: `ConfigureBrowserCapabilities`
- `0x1332ce`: `System.dll`
- `0x1332d6`: `System.Web.dll`
- `0x1332fd`: `\ASP.BrowserCapsFactory.dll`
- `0x1333af`: `Browser_compile_error`

## pseudocode

```c

```

## disassembly

```asm
0x132e20  ldarg.0
0x132e21  ldfld    class System.Web.Configuration.BrowserTree System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_browserTree
0x132e26  ldstr    aDefault_0// "Default"
0x132e2b  callvirt instance object [System]System.Collections.Specialized.OrderedDictionary::get_Item(object)
0x132e30  castclass System.Web.Configuration.BrowserDefinition
0x132e35  stloc.0
0x132e36  ldarg.0
0x132e37  ldfld    class System.Web.Configuration.BrowserTree System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_defaultTree
0x132e3c  ldstr    aDefault_0// "Default"
0x132e41  callvirt instance object [System]System.Collections.Specialized.OrderedDictionary::get_Item(object)
0x132e46  castclass System.Web.Configuration.BrowserDefinition
0x132e4b  stloc.1
0x132e4c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x132e51  stloc.2
0x132e52  ldc.i4.0
0x132e53  stloc.s  0x16
0x132e55  br.s     loc_132E8D
0x132e57  ldloc.2
0x132e58  ldarg.0
0x132e59  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_customTreeList
0x132e5e  ldloc.s  0x16
0x132e60  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x132e65  castclass System.Web.Configuration.BrowserTree
0x132e6a  ldarg.0
0x132e6b  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_customTreeNames
0x132e70  ldloc.s  0x16
0x132e72  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x132e77  callvirt instance object [System]System.Collections.Specialized.OrderedDictionary::get_Item(object)
0x132e7c  castclass System.Web.Configuration.BrowserDefinition
0x132e81  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x132e86  pop
0x132e87  ldloc.s  0x16
0x132e89  ldc.i4.1
0x132e8a  add
0x132e8b  stloc.s  0x16
0x132e8d  ldloc.s  0x16
0x132e8f  ldarg.0
0x132e90  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_customTreeNames
0x132e95  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x132e9a  blt.s    loc_132E57
0x132e9c  newobj   instance void [System]Microsoft.CSharp.CSharpCodeProvider::.ctor()
0x132ea1  stloc.3
0x132ea2  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x132ea7  stloc.s  4
0x132ea9  ldstr    aSystemReflecti// "System.Reflection.AssemblyKeyFile"
0x132eae  ldc.i4.1
0x132eaf  newarr   [System]System.CodeDom.CodeAttributeArgument
0x132eb4  dup
0x132eb5  ldc.i4.0
0x132eb6  ldsfld   string System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_strongNameKeyFileName
0x132ebb  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x132ec0  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x132ec5  stelem.ref
0x132ec6  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x132ecb  stloc.s  5
0x132ecd  ldstr    aSystemSecurity// "System.Security.AllowPartiallyTrustedCa"...
0x132ed2  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string)
0x132ed7  stloc.s  6
0x132ed9  ldloc.s  4
0x132edb  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x132ee0  ldloc.s  6
0x132ee2  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x132ee7  pop
0x132ee8  ldloc.s  4
0x132eea  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x132eef  ldloc.s  5
0x132ef1  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x132ef6  pop
0x132ef7  ldstr    aSystemReflecti_0// "System.Reflection.AssemblyVersion"
0x132efc  ldc.i4.1
0x132efd  newarr   [System]System.CodeDom.CodeAttributeArgument
0x132f02  dup
0x132f03  ldc.i4.0
0x132f04  ldstr    a4000// "4.0.0.0"
0x132f09  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x132f0e  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x132f13  stelem.ref
0x132f14  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x132f19  stloc.s  5
0x132f1b  ldloc.s  4
0x132f1d  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x132f22  ldloc.s  5
0x132f24  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x132f29  pop
0x132f2a  ldstr    aAsp_0// "ASP"
0x132f2f  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor(string)
0x132f34  stloc.s  7
0x132f36  ldloc.s  7
0x132f38  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x132f3d  ldstr    aSystem// "System"
0x132f42  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x132f47  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x132f4c  ldloc.s  7
0x132f4e  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x132f53  ldstr    aSystemWeb// "System.Web"
0x132f58  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x132f5d  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x132f62  ldloc.s  7
0x132f64  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x132f69  ldstr    aSystemWebConfi// "System.Web.Configuration"
0x132f6e  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x132f73  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x132f78  ldloc.s  7
0x132f7a  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x132f7f  ldstr    aSystemReflecti_1// "System.Reflection"
0x132f84  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x132f89  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x132f8e  ldloc.s  4
0x132f90  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x132f95  ldloc.s  7
0x132f97  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x132f9c  pop
0x132f9d  ldstr    aBrowsercapabil// "BrowserCapabilitiesFactory"
0x132fa2  newobj   instance void [System]System.CodeDom.CodeTypeDeclaration::.ctor(string)
0x132fa7  stloc.s  8
0x132fa9  ldloc.s  8
0x132fab  ldc.i4   0x5000
0x132fb0  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x132fb5  ldloc.s  8
0x132fb7  ldc.i4.1
0x132fb8  callvirt instance void [System]System.CodeDom.CodeTypeDeclaration::set_IsClass(bool)
0x132fbd  ldloc.s  8
0x132fbf  ldarg.0
0x132fc0  callvirt instance string System.Web.Configuration.BrowserCapabilitiesCodeGenerator::get_TypeName()
0x132fc5  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x132fca  ldloc.s  8
0x132fcc  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x132fd1  ldstr    aSystemWebConfi_0// "System.Web.Configuration.BrowserCapabil"...
0x132fd6  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string)
0x132fdb  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x132fe0  pop
0x132fe1  ldloc.s  7
0x132fe3  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x132fe8  ldloc.s  8
0x132fea  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x132fef  pop
0x132ff0  newobj   instance void [System]System.CodeDom.CodeMemberMethod::.ctor()
0x132ff5  stloc.s  9
0x132ff7  ldloc.s  9
0x132ff9  ldc.i4   0x6004
0x132ffe  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x133003  ldloc.s  9
0x133005  ldtoken  [mscorlib]System.Void
0x13300a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13300f  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x133014  callvirt instance void [System]System.CodeDom.CodeMemberMethod::set_ReturnType(class [System]System.CodeDom.CodeTypeReference)
0x133019  ldloc.s  9
0x13301b  ldstr    aConfigurebrows// "ConfigureBrowserCapabilities"
0x133020  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Name(string)
0x133025  ldtoken  [System]System.Collections.Specialized.NameValueCollection
0x13302a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13302f  ldstr    aHeaders// "headers"
0x133034  newobj   instance void [System]System.CodeDom.CodeParameterDeclarationExpression::.ctor(class [mscorlib]System.Type, string)
0x133039  stloc.s  0xA
0x13303b  ldloc.s  9
0x13303d  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x133042  ldloc.s  0xA
0x133044  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x133049  pop
0x13304a  ldtoken  System.Web.HttpBrowserCapabilities
0x13304f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133054  ldstr    aBrowsercaps// "browserCaps"
0x133059  newobj   instance void [System]System.CodeDom.CodeParameterDeclarationExpression::.ctor(class [mscorlib]System.Type, string)
0x13305e  stloc.s  0xA
0x133060  ldloc.s  9
0x133062  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x133067  ldloc.s  0xA
0x133069  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x13306e  pop
0x13306f  ldloc.s  8
0x133071  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x133076  ldloc.s  9
0x133078  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x13307d  pop
0x13307e  ldarg.0
0x13307f  ldloc.0
0x133080  ldloc.s  9
0x133082  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateSingleProcessCall(class System.Web.Configuration.BrowserDefinition bd, class [System]System.CodeDom.CodeMemberMethod cmm)
0x133087  ldc.i4.0
0x133088  stloc.s  0x17
0x13308a  br.s     loc_1330A7
0x13308c  ldarg.0
0x13308d  ldloc.2
0x13308e  ldloc.s  0x17
0x133090  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x133095  castclass System.Web.Configuration.BrowserDefinition
0x13309a  ldloc.s  9
0x13309c  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateSingleProcessCall(class System.Web.Configuration.BrowserDefinition bd, class [System]System.CodeDom.CodeMemberMethod cmm)
0x1330a1  ldloc.s  0x17
0x1330a3  ldc.i4.1
0x1330a4  add
0x1330a5  stloc.s  0x17
0x1330a7  ldloc.s  0x17
0x1330a9  ldloc.2
0x1330aa  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1330af  blt.s    loc_13308C
0x1330b1  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x1330b6  stloc.s  0xB
0x1330b8  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x1330bd  ldstr    aIsbrowserunkno// "IsBrowserUnknown"
0x1330c2  ldc.i4.0
0x1330c3  newarr   [System]System.CodeDom.CodeExpression
0x1330c8  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x1330cd  stloc.s  0xC
0x1330cf  ldloc.s  0xC
0x1330d1  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x1330d6  ldarg.0
0x1330d7  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_browserCapsRefExpr
0x1330dc  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x1330e1  pop
0x1330e2  ldloc.s  0xB
0x1330e4  ldloc.s  0xC
0x1330e6  ldc.i4.8
0x1330e7  ldc.i4.0
0x1330e8  box      [mscorlib]System.Boolean
0x1330ed  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1330f2  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x1330f7  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x1330fc  ldloc.s  0xB
0x1330fe  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x133103  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor()
0x133108  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x13310d  pop
0x13310e  ldloc.s  9
0x133110  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x133115  ldloc.s  0xB
0x133117  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x13311c  pop
0x13311d  ldloc.1
0x13311e  brfalse.s loc_13312E
0x133120  ldarg.0
0x133121  ldloc.1
0x133122  ldloc.s  9
0x133124  ldstr    aDefault_0// "Default"
0x133129  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateSingleProcessCall(class System.Web.Configuration.BrowserDefinition bd, class [System]System.CodeDom.CodeMemberMethod cmm, string prefix)
0x13312e  ldc.i4.0
0x13312f  stloc.s  0x18
0x133131  br.s     loc_13319A
0x133133  ldarg.0
0x133134  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_customTreeList
0x133139  ldloc.s  0x18
0x13313b  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x133140  castclass System.Web.Configuration.BrowserTree
0x133145  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [System]System.Collections.Specialized.OrderedDictionary::GetEnumerator()
0x13314a  stloc.s  0x19
0x13314c  br.s     loc_133174
0x13314e  ldloc.s  0x19
0x133150  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x133155  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x13315a  stloc.s  0x1A
0x13315c  ldloca.s 0x1A
0x13315e  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x133163  isinst   System.Web.Configuration.BrowserDefinition
0x133168  stloc.s  0x1B
0x13316a  ldarg.0
0x13316b  ldloc.s  0x1B
0x13316d  ldloc.s  8
0x13316f  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateProcessMethod(class System.Web.Configuration.BrowserDefinition bd, class [System]System.CodeDom.CodeTypeDeclaration ctd)
0x133174  ldloc.s  0x19
0x133176  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13317b  brtrue.s loc_13314E
0x13317d  leave.s  loc_133194
0x13317f  ldloc.s  0x19
0x133181  isinst   [mscorlib]System.IDisposable
0x133186  stloc.s  0x1C
0x133188  ldloc.s  0x1C
0x13318a  brfalse.s loc_133193
0x13318c  ldloc.s  0x1C
0x13318e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x133193  endfinally
0x133194  ldloc.s  0x18
0x133196  ldc.i4.1
0x133197  add
0x133198  stloc.s  0x18
0x13319a  ldloc.s  0x18
0x13319c  ldloc.2
0x13319d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1331a2  blt.s    loc_133133
0x1331a4  ldarg.0
0x1331a5  ldfld    class System.Web.Configuration.BrowserTree System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_browserTree
0x1331aa  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [System]System.Collections.Specialized.OrderedDictionary::GetEnumerator()
0x1331af  stloc.s  0x1D
0x1331b1  br.s     loc_1331D9
0x1331b3  ldloc.s  0x1D
0x1331b5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1331ba  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x1331bf  stloc.s  0x1E
0x1331c1  ldloca.s 0x1E
0x1331c3  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x1331c8  isinst   System.Web.Configuration.BrowserDefinition
0x1331cd  stloc.s  0x1F
0x1331cf  ldarg.0
0x1331d0  ldloc.s  0x1F
0x1331d2  ldloc.s  8
0x1331d4  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateProcessMethod(class System.Web.Configuration.BrowserDefinition bd, class [System]System.CodeDom.CodeTypeDeclaration ctd)
0x1331d9  ldloc.s  0x1D
0x1331db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1331e0  brtrue.s loc_1331B3
0x1331e2  leave.s  loc_1331F9
0x1331e4  ldloc.s  0x1D
  ... truncated ...
```
