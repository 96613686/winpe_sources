# System.Web.UI.Design.ExpressionEditor::GetExpressionEditor

- ea: `0xd200`
- end: `0xd377`
- name: `System.Web.UI.Design.ExpressionEditor::GetExpressionEditor`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x17c0`
- `0x3bc60`

## callees

- `0xd1b0`
- `0xd200`
- `0xd380`
- `0xe7f0`

## string_xrefs

- `0xd203`: `serviceProvider`
- `0xd26c`: `system.web/compilation`
- `0xd33c`: `system.web/compilation`

## pseudocode

```c

```

## disassembly

```asm
0xd200  ldarg.1
0xd201  brtrue.s loc_D20E
0xd203  ldstr    aServiceprovide// "serviceProvider"
0xd208  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd20d  throw
0xd20e  ldarg.0
0xd20f  ldnull
0xd210  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xd215  brfalse.s loc_D222
0xd217  ldstr    aExpressionbuil_2// "expressionBuilderType"
0xd21c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd221  throw
0xd222  ldnull
0xd223  stloc.0
0xd224  ldarg.1
0xd225  ldtoken  System.Web.UI.Design.IWebApplication
0xd22a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd22f  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xd234  castclass System.Web.UI.Design.IWebApplication
0xd239  stloc.1
0xd23a  ldloc.1
0xd23b  brfalse  loc_D375
0xd240  ldloc.1
0xd241  call     class [mscorlib]System.Collections.IDictionary System.Web.UI.Design.ExpressionEditor::GetExpressionEditorsByTypeCache(class System.Web.UI.Design.IWebApplication webApp)
0xd246  stloc.2
0xd247  ldloc.2
0xd248  brfalse.s loc_D257
0xd24a  ldloc.2
0xd24b  ldarg.0
0xd24c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xd251  castclass System.Web.UI.Design.ExpressionEditor
0xd256  stloc.0
0xd257  ldloc.0
0xd258  brtrue   loc_D375
0xd25d  ldloc.1
0xd25e  ldc.i4.1
0xd25f  callvirt instance class [System.Configuration]System.Configuration.Configuration System.Web.UI.Design.IWebApplication::OpenWebConfiguration(bool isReadOnly)
0xd264  stloc.3
0xd265  ldloc.3
0xd266  brfalse  loc_D375
0xd26b  ldloc.3
0xd26c  ldstr    aSystemWebCompi// "system.web/compilation"
0xd271  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0xd276  castclass [System.Web]System.Web.Configuration.CompilationSection
0xd27b  stloc.s  4
0xd27d  ldloc.s  4
0xd27f  callvirt instance class [System.Web]System.Web.Configuration.ExpressionBuilderCollection [System.Web]System.Web.Configuration.CompilationSection::get_ExpressionBuilders()
0xd284  stloc.s  5
0xd286  ldc.i4.0
0xd287  stloc.s  6
0xd289  ldarg.0
0xd28a  callvirt instance string [mscorlib]System.Type::get_FullName()
0xd28f  stloc.s  7
0xd291  ldloc.s  5
0xd293  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Configuration]System.Configuration.ConfigurationElementCollection::GetEnumerator()
0xd298  stloc.s  8
0xd29a  br.s     loc_D2CE
0xd29c  ldloc.s  8
0xd29e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd2a3  castclass [System.Web]System.Web.Configuration.ExpressionBuilder
0xd2a8  stloc.s  9
0xd2aa  ldloc.s  9
0xd2ac  callvirt instance string [System.Web]System.Web.Configuration.ExpressionBuilder::get_Type()
0xd2b1  ldloc.s  7
0xd2b3  ldc.i4.5
0xd2b4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xd2b9  brfalse.s loc_D2CE
0xd2bb  ldarg.0
0xd2bc  ldloc.s  9
0xd2be  callvirt instance string [System.Web]System.Web.Configuration.ExpressionBuilder::get_ExpressionPrefix()
0xd2c3  ldloc.1
0xd2c4  ldarg.1
0xd2c5  call     class System.Web.UI.Design.ExpressionEditor System.Web.UI.Design.ExpressionEditor::GetExpressionEditorInternal(class [mscorlib]System.Type expressionBuilderType, string expressionPrefix, class System.Web.UI.Design.IWebApplication webApp, class [mscorlib]System.IServiceProvider serviceProvider)
0xd2ca  stloc.0
0xd2cb  ldc.i4.1
0xd2cc  stloc.s  6
0xd2ce  ldloc.s  8
0xd2d0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd2d5  brtrue.s loc_D29C
0xd2d7  leave.s  loc_D2EE
0xd2d9  ldloc.s  8
0xd2db  isinst   [mscorlib]System.IDisposable
0xd2e0  stloc.s  0xA
0xd2e2  ldloc.s  0xA
0xd2e4  brfalse.s loc_D2ED
0xd2e6  ldloc.s  0xA
0xd2e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2ed  endfinally
0xd2ee  ldloc.s  6
0xd2f0  brtrue   loc_D375
0xd2f5  ldarg.0
0xd2f6  ldtoken  [System.Web]System.Web.Compilation.ExpressionPrefixAttribute
0xd2fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd300  ldc.i4.1
0xd301  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0xd306  stloc.s  0xB
0xd308  ldnull
0xd309  stloc.s  0xC
0xd30b  ldloc.s  0xB
0xd30d  ldlen
0xd30e  brfalse.s loc_D31B
0xd310  ldloc.s  0xB
0xd312  ldc.i4.0
0xd313  ldelem.ref
0xd314  castclass [System.Web]System.Web.Compilation.ExpressionPrefixAttribute
0xd319  stloc.s  0xC
0xd31b  ldloc.s  0xC
0xd31d  brfalse.s loc_D375
0xd31f  ldloc.s  0xC
0xd321  callvirt instance string [System.Web]System.Web.Compilation.ExpressionPrefixAttribute::get_ExpressionPrefix()
0xd326  ldarg.0
0xd327  callvirt instance string [mscorlib]System.Type::get_FullName()
0xd32c  newobj   instance void [System.Web]System.Web.Configuration.ExpressionBuilder::.ctor(string, string)
0xd331  stloc.s  0xD
0xd333  ldloc.1
0xd334  ldc.i4.0
0xd335  callvirt instance class [System.Configuration]System.Configuration.Configuration System.Web.UI.Design.IWebApplication::OpenWebConfiguration(bool isReadOnly)
0xd33a  stloc.3
0xd33b  ldloc.3
0xd33c  ldstr    aSystemWebCompi// "system.web/compilation"
0xd341  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0xd346  castclass [System.Web]System.Web.Configuration.CompilationSection
0xd34b  stloc.s  4
0xd34d  ldloc.s  4
0xd34f  callvirt instance class [System.Web]System.Web.Configuration.ExpressionBuilderCollection [System.Web]System.Web.Configuration.CompilationSection::get_ExpressionBuilders()
0xd354  stloc.s  5
0xd356  ldloc.s  5
0xd358  ldloc.s  0xD
0xd35a  callvirt instance void [System.Web]System.Web.Configuration.ExpressionBuilderCollection::Add(class [System.Web]System.Web.Configuration.ExpressionBuilder)
0xd35f  ldloc.3
0xd360  callvirt instance void [System.Configuration]System.Configuration.Configuration::Save()
0xd365  ldarg.0
0xd366  ldloc.s  0xD
0xd368  callvirt instance string [System.Web]System.Web.Configuration.ExpressionBuilder::get_ExpressionPrefix()
0xd36d  ldloc.1
0xd36e  ldarg.1
0xd36f  call     class System.Web.UI.Design.ExpressionEditor System.Web.UI.Design.ExpressionEditor::GetExpressionEditorInternal(class [mscorlib]System.Type expressionBuilderType, string expressionPrefix, class System.Web.UI.Design.IWebApplication webApp, class [mscorlib]System.IServiceProvider serviceProvider)
0xd374  stloc.0
0xd375  ldloc.0
0xd376  ret
```
