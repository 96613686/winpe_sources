# System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateIdentificationCode

- ea: `0x133e20`
- end: `0x134316`
- name: `System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateIdentificationCode`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x133880`

## callees

- `0x56d90`
- `0x133d50`
- `0x133db0`
- `0x133e20`
- `0x134320`
- `0x1347b0`
- `0x13c640`
- `0x13c660`
- `0x13e140`
- `0x13e150`
- `0x13e160`

## string_xrefs

- `0x133f0c`: `User-Agent`
- `0x1342f5`: `DisableOptimizedCacheKey`

## pseudocode

```c

```

## disassembly

```asm
0x133e20  ldarg.2
0x133e21  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x133e26  ldtoken  [mscorlib]System.Collections.IDictionary
0x133e2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133e30  ldstr    aDictionary// "dictionary"
0x133e35  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor(class [mscorlib]System.Type, string)
0x133e3a  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x133e3f  pop
0x133e40  ldarg.0
0x133e41  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_dictionaryRefExpr
0x133e46  ldarg.0
0x133e47  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_browserCapsRefExpr
0x133e4c  ldstr    aCapabilities// "Capabilities"
0x133e51  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x133e56  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x133e5b  stloc.0
0x133e5c  ldarg.2
0x133e5d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x133e62  ldloc.0
0x133e63  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x133e68  pop
0x133e69  ldc.i4.0
0x133e6a  stloc.1
0x133e6b  ldnull
0x133e6c  stloc.2
0x133e6d  ldnull
0x133e6e  stloc.3
0x133e6f  ldarg.1
0x133e70  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x133e75  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x133e7a  ldc.i4.0
0x133e7b  ble      loc_1340FA
0x133e80  ldarg.0
0x133e81  ldstr    aIdentification// "Identification: check header matches"
0x133e86  ldarg.2
0x133e87  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::AddComment(string comment, class [System]System.CodeDom.CodeMemberMethod cmm)
0x133e8c  ldc.i4.0
0x133e8d  stloc.s  4
0x133e8f  br       loc_1340E8
0x133e94  ldarg.1
0x133e95  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x133e9a  ldloc.s  4
0x133e9c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x133ea1  castclass System.Web.Configuration.CheckPair
0x133ea6  callvirt instance string System.Web.Configuration.CheckPair::get_MatchString()
0x133eab  stloc.s  5
0x133ead  ldloc.s  5
0x133eaf  ldstr    asc_1C67EC// ".*"
0x133eb4  callvirt instance bool [mscorlib]System.String::Equals(string)
0x133eb9  brtrue   loc_1340E2
0x133ebe  ldloc.3
0x133ebf  brtrue.s loc_133ED8
0x133ec1  ldarg.0
0x133ec2  ldarg.2
0x133ec3  ldtoken  [mscorlib]System.String
0x133ec8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133ecd  ldstr    aHeadervalue// "headerValue"
0x133ed2  call     instance class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateVarReference(class [System]System.CodeDom.CodeMemberMethod cmm, class [mscorlib]System.Type varType, string varName)
0x133ed7  stloc.3
0x133ed8  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor()
0x133edd  stloc.s  6
0x133edf  ldarg.2
0x133ee0  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x133ee5  ldloc.s  6
0x133ee7  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x133eec  pop
0x133eed  ldloc.s  6
0x133eef  ldloc.3
0x133ef0  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Left(class [System]System.CodeDom.CodeExpression)
0x133ef5  ldarg.1
0x133ef6  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x133efb  ldloc.s  4
0x133efd  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x133f02  castclass System.Web.Configuration.CheckPair
0x133f07  callvirt instance string System.Web.Configuration.CheckPair::get_Header()
0x133f0c  ldstr    aUserAgent// "User-Agent"
0x133f11  callvirt instance bool [mscorlib]System.String::Equals(string)
0x133f16  brfalse.s loc_133F71
0x133f18  ldarg.0
0x133f19  ldfld    class System.Web.Util.CaseInsensitiveStringSet System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_headers
0x133f1e  ldsfld   string [mscorlib]System.String::Empty
0x133f23  callvirt instance void System.Web.Util.ObjectSet::Add(object o)
0x133f28  ldloc.s  6
0x133f2a  ldtoken  [mscorlib]System.String
0x133f2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133f34  ldstr    aBrowsercaps// "browserCaps"
0x133f39  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x133f3e  ldc.i4.1
0x133f3f  newarr   [System]System.CodeDom.CodeExpression
0x133f44  dup
0x133f45  ldc.i4.0
0x133f46  ldtoken  [mscorlib]System.String
0x133f4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133f50  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x133f55  ldstr    aEmpty_0// "Empty"
0x133f5a  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x133f5f  stelem.ref
0x133f60  newobj   instance void [System]System.CodeDom.CodeIndexerExpression::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression[])
0x133f65  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [mscorlib]System.Type, class [System]System.CodeDom.CodeExpression)
0x133f6a  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x133f6f  br.s     loc_133FCA
0x133f71  ldarg.1
0x133f72  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x133f77  ldloc.s  4
0x133f79  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x133f7e  castclass System.Web.Configuration.CheckPair
0x133f83  callvirt instance string System.Web.Configuration.CheckPair::get_Header()
0x133f88  stloc.s  9
0x133f8a  ldarg.0
0x133f8b  ldfld    class System.Web.Util.CaseInsensitiveStringSet System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_headers
0x133f90  ldloc.s  9
0x133f92  callvirt instance void System.Web.Util.ObjectSet::Add(object o)
0x133f97  ldloc.s  6
0x133f99  ldtoken  [mscorlib]System.String
0x133f9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133fa3  ldarg.0
0x133fa4  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_headersRefExpr
0x133fa9  ldc.i4.1
0x133faa  newarr   [System]System.CodeDom.CodeExpression
0x133faf  dup
0x133fb0  ldc.i4.0
0x133fb1  ldloc.s  9
0x133fb3  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x133fb8  stelem.ref
0x133fb9  newobj   instance void [System]System.CodeDom.CodeIndexerExpression::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression[])
0x133fbe  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [mscorlib]System.Type, class [System]System.CodeDom.CodeExpression)
0x133fc3  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x133fc8  ldc.i4.1
0x133fc9  stloc.1
0x133fca  ldloc.s  5
0x133fcc  ldstr    asc_1B2EDA// "."
0x133fd1  callvirt instance bool [mscorlib]System.String::Equals(string)
0x133fd6  brfalse.s loc_133FE5
0x133fd8  ldarg.0
0x133fd9  ldarg.2
0x133fda  ldloc.3
0x133fdb  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::ReturnIfHeaderValueEmpty(class [System]System.CodeDom.CodeMemberMethod cmm, class [System]System.CodeDom.CodeVariableReferenceExpression varExpr)
0x133fe0  br       loc_1340E2
0x133fe5  ldloc.2
0x133fe6  brtrue.s loc_133FFF
0x133fe8  ldarg.0
0x133fe9  ldarg.2
0x133fea  ldtoken  [mscorlib]System.Boolean
0x133fef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133ff4  ldstr    aResult// "result"
0x133ff9  call     instance class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateVarReference(class [System]System.CodeDom.CodeMemberMethod cmm, class [mscorlib]System.Type varType, string varName)
0x133ffe  stloc.2
0x133fff  ldarg.0
0x134000  ldarg.2
0x134001  ldarg.3
0x134002  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateRegexWorkerIfNecessary(class [System]System.CodeDom.CodeMemberMethod cmm, bool& regexWorkerGenerated)
0x134007  ldarg.0
0x134008  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_regexWorkerRefExpr
0x13400d  ldstr    aProcessregex// "ProcessRegex"
0x134012  ldc.i4.0
0x134013  newarr   [System]System.CodeDom.CodeExpression
0x134018  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x13401d  stloc.s  7
0x13401f  ldloc.s  7
0x134021  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x134026  ldloc.3
0x134027  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x13402c  pop
0x13402d  ldloc.s  7
0x13402f  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x134034  ldloc.s  5
0x134036  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x13403b  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x134040  pop
0x134041  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor()
0x134046  stloc.0
0x134047  ldloc.0
0x134048  ldloc.2
0x134049  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Left(class [System]System.CodeDom.CodeExpression)
0x13404e  ldloc.0
0x13404f  ldloc.s  7
0x134051  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x134056  ldarg.2
0x134057  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x13405c  ldloc.0
0x13405d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x134062  pop
0x134063  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x134068  stloc.s  8
0x13406a  ldarg.1
0x13406b  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x134070  ldloc.s  4
0x134072  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x134077  castclass System.Web.Configuration.CheckPair
0x13407c  callvirt instance bool System.Web.Configuration.CheckPair::get_NonMatch()
0x134081  brfalse.s loc_13409E
0x134083  ldloc.s  8
0x134085  ldloc.2
0x134086  ldc.i4.8
0x134087  ldc.i4.1
0x134088  box      [mscorlib]System.Boolean
0x13408d  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x134092  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x134097  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x13409c  br.s     loc_1340B7
0x13409e  ldloc.s  8
0x1340a0  ldloc.2
0x1340a1  ldc.i4.8
0x1340a2  ldc.i4.0
0x1340a3  box      [mscorlib]System.Boolean
0x1340a8  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1340ad  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x1340b2  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x1340b7  ldloc.s  8
0x1340b9  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x1340be  ldc.i4.0
0x1340bf  box      [mscorlib]System.Boolean
0x1340c4  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1340c9  newobj   instance void [System]System.CodeDom.CodeMethodReturnStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x1340ce  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1340d3  pop
0x1340d4  ldarg.2
0x1340d5  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x1340da  ldloc.s  8
0x1340dc  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x1340e1  pop
0x1340e2  ldloc.s  4
0x1340e4  ldc.i4.1
0x1340e5  add
0x1340e6  stloc.s  4
0x1340e8  ldloc.s  4
0x1340ea  ldarg.1
0x1340eb  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdHeaderChecks()
0x1340f0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1340f5  blt      loc_133E94
0x1340fa  ldarg.1
0x1340fb  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdCapabilityChecks()
0x134100  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x134105  ldc.i4.0
0x134106  ble      loc_1342EC
0x13410b  ldarg.0
0x13410c  ldstr    aIdentification_0// "Identification: check capability matche"...
0x134111  ldarg.2
0x134112  call     instance void System.Web.Configuration.BrowserCapabilitiesCodeGenerator::AddComment(string comment, class [System]System.CodeDom.CodeMemberMethod cmm)
0x134117  ldc.i4.0
0x134118  stloc.s  0xA
0x13411a  br       loc_1342DA
0x13411f  ldarg.1
0x134120  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdCapabilityChecks()
0x134125  ldloc.s  0xA
0x134127  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x13412c  castclass System.Web.Configuration.CheckPair
0x134131  callvirt instance string System.Web.Configuration.CheckPair::get_MatchString()
0x134136  stloc.s  0xB
0x134138  ldloc.s  0xB
0x13413a  ldstr    asc_1C67EC// ".*"
0x13413f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x134144  brtrue   loc_1342D4
0x134149  ldloc.3
0x13414a  brtrue.s loc_134163
0x13414c  ldarg.0
0x13414d  ldarg.2
0x13414e  ldtoken  [mscorlib]System.String
0x134153  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x134158  ldstr    aHeadervalue// "headerValue"
0x13415d  call     instance class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::GenerateVarReference(class [System]System.CodeDom.CodeMemberMethod cmm, class [mscorlib]System.Type varType, string varName)
0x134162  stloc.3
0x134163  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor()
0x134168  stloc.s  0xC
0x13416a  ldarg.2
0x13416b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x134170  ldloc.s  0xC
0x134172  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x134177  pop
0x134178  ldloc.s  0xC
0x13417a  ldloc.3
0x13417b  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Left(class [System]System.CodeDom.CodeExpression)
0x134180  ldloc.s  0xC
0x134182  ldtoken  [mscorlib]System.String
0x134187  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13418c  ldarg.0
0x13418d  ldfld    class [System]System.CodeDom.CodeVariableReferenceExpression System.Web.Configuration.BrowserCapabilitiesCodeGenerator::_dictionaryRefExpr
0x134192  ldc.i4.1
0x134193  newarr   [System]System.CodeDom.CodeExpression
0x134198  dup
0x134199  ldc.i4.0
0x13419a  ldarg.1
0x13419b  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::get_IdCapabilityChecks()
0x1341a0  ldloc.s  0xA
0x1341a2  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1341a7  castclass System.Web.Configuration.CheckPair
0x1341ac  callvirt instance string System.Web.Configuration.CheckPair::get_Header()
0x1341b1  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x1341b6  stelem.ref
0x1341b7  newobj   instance void [System]System.CodeDom.CodeIndexerExpression::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression[])
0x1341bc  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [mscorlib]System.Type, class [System]System.CodeDom.CodeExpression)
0x1341c1  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x1341c6  ldloc.s  0xB
0x1341c8  ldstr    asc_1B2EDA// "."
0x1341cd  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1341d2  brtrue   loc_1342D4
0x1341d7  ldloc.2
0x1341d8  brtrue.s loc_1341F1
0x1341da  ldarg.0
0x1341db  ldarg.2
  ... truncated ...
```
