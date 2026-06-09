# System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::PatchConfigurationNameInServiceContractAttribute

- ea: `0x5670`
- end: `0x5824`
- name: `System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::PatchConfigurationNameInServiceContractAttribute`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4c50`

## callees

- `0x4d00`
- `0x4d20`
- `0x5670`

## string_xrefs

- `0x5755`: `ConfigurationName`

## pseudocode

```c

```

## disassembly

```asm
0x5670  ldarg.1
0x5671  brtrue.s loc_567A
0x5673  ldsfld   string [mscorlib]System.String::Empty
0x5678  starg.s  1
0x567a  ldarg.1
0x567b  call     string System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::MakePeriodTerminatedNamespacePrefix(string ns)
0x5680  stloc.0
0x5681  ldarg.2
0x5682  call     string System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::MakePeriodTerminatedNamespacePrefix(string ns)
0x5687  stloc.1
0x5688  ldarg.0
0x5689  brfalse  loc_5823
0x568e  ldarg.0
0x568f  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x5694  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5699  stloc.2
0x569a  br       loc_5802
0x569f  ldloc.2
0x56a0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x56a5  castclass [System]System.CodeDom.CodeNamespace
0x56aa  stloc.3
0x56ab  ldarg.1
0x56ac  ldloc.3
0x56ad  callvirt instance string [System]System.CodeDom.CodeNamespace::get_Name()
0x56b2  ldc.i4.4
0x56b3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x56b8  brfalse  loc_5802
0x56bd  ldloc.3
0x56be  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x56c3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x56c8  stloc.s  4
0x56ca  br       loc_57DF
0x56cf  ldloc.s  4
0x56d1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x56d6  castclass [System]System.CodeDom.CodeTypeDeclaration
0x56db  stloc.s  5
0x56dd  ldloc.s  5
0x56df  callvirt instance bool [System]System.CodeDom.CodeTypeDeclaration::get_IsInterface()
0x56e4  brfalse  loc_57DF
0x56e9  ldloc.s  5
0x56eb  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x56f0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x56f5  stloc.s  6
0x56f7  br       loc_57BC
0x56fc  ldloc.s  6
0x56fe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5703  castclass [System]System.CodeDom.CodeAttributeDeclaration
0x5708  stloc.s  7
0x570a  ldloc.s  7
0x570c  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeAttributeDeclaration::get_AttributeType()
0x5711  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x5716  ldtoken  [System.ServiceModel]System.ServiceModel.ServiceContractAttribute
0x571b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5720  callvirt instance string [mscorlib]System.Type::get_FullName()
0x5725  ldc.i4.4
0x5726  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x572b  brfalse  loc_57BC
0x5730  ldloc.s  7
0x5732  callvirt instance class [System]System.CodeDom.CodeAttributeArgumentCollection [System]System.CodeDom.CodeAttributeDeclaration::get_Arguments()
0x5737  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x573c  stloc.s  8
0x573e  br.s     loc_579C
0x5740  ldloc.s  8
0x5742  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5747  castclass [System]System.CodeDom.CodeAttributeArgument
0x574c  stloc.s  9
0x574e  ldloc.s  9
0x5750  callvirt instance string [System]System.CodeDom.CodeAttributeArgument::get_Name()
0x5755  ldstr    aConfigurationn// "ConfigurationName"
0x575a  ldc.i4.4
0x575b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5760  brfalse.s loc_579C
0x5762  ldloc.s  9
0x5764  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeAttributeArgument::get_Value()
0x5769  isinst   [System]System.CodeDom.CodePrimitiveExpression
0x576e  stloc.s  0xA
0x5770  ldloc.s  0xA
0x5772  brfalse.s loc_579C
0x5774  ldloc.s  0xA
0x5776  callvirt instance object [System]System.CodeDom.CodePrimitiveExpression::get_Value()
0x577b  isinst   [mscorlib]System.String
0x5780  brfalse.s loc_579C
0x5782  ldloc.s  0xA
0x5784  ldloc.0
0x5785  ldloc.1
0x5786  ldloc.s  0xA
0x5788  callvirt instance object [System]System.CodeDom.CodePrimitiveExpression::get_Value()
0x578d  castclass [mscorlib]System.String
0x5792  call     string System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::ReplaceNamespace(string originalNamespace, string replacementNamespace, string typeName)
0x5797  callvirt instance void [System]System.CodeDom.CodePrimitiveExpression::set_Value(object)
0x579c  ldloc.s  8
0x579e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57a3  brtrue.s loc_5740
0x57a5  leave.s  loc_57BC
0x57a7  ldloc.s  8
0x57a9  isinst   [mscorlib]System.IDisposable
0x57ae  stloc.s  0xB
0x57b0  ldloc.s  0xB
0x57b2  brfalse.s loc_57BB
0x57b4  ldloc.s  0xB
0x57b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57bb  endfinally
0x57bc  ldloc.s  6
0x57be  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57c3  brtrue   loc_56FC
0x57c8  leave.s  loc_57DF
0x57ca  ldloc.s  6
0x57cc  isinst   [mscorlib]System.IDisposable
0x57d1  stloc.s  0xB
0x57d3  ldloc.s  0xB
0x57d5  brfalse.s loc_57DE
0x57d7  ldloc.s  0xB
0x57d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57de  endfinally
0x57df  ldloc.s  4
0x57e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57e6  brtrue   loc_56CF
0x57eb  leave.s  loc_5802
0x57ed  ldloc.s  4
0x57ef  isinst   [mscorlib]System.IDisposable
0x57f4  stloc.s  0xB
0x57f6  ldloc.s  0xB
0x57f8  brfalse.s loc_5801
0x57fa  ldloc.s  0xB
0x57fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5801  endfinally
0x5802  ldloc.2
0x5803  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5808  brtrue   loc_569F
0x580d  leave.s  loc_5823
0x580f  ldloc.2
0x5810  isinst   [mscorlib]System.IDisposable
0x5815  stloc.s  0xB
0x5817  ldloc.s  0xB
0x5819  brfalse.s loc_5822
0x581b  ldloc.s  0xB
0x581d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5822  endfinally
0x5823  ret
```
