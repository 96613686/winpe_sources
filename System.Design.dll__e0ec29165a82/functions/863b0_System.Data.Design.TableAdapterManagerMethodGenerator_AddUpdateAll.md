# System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAll

- ea: `0x863b0`
- end: `0x87067`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAll`
- size: `3255`
- prototype: ``
- caller_count: `1`
- callee_count: `61`
- tags: `installer_update, broker_com_uri`

## callers

- `0x85090`

## callees

- `0x71e90`
- `0x71ec0`
- `0x71ed0`
- `0x71f20`
- `0x71f50`
- `0x71f60`
- `0x71f80`
- `0x71fb0`
- `0x71fd0`
- `0x71fe0`
- `0x71ff0`
- `0x72000`
- `0x72010`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72080`
- `0x72090`
- `0x720b0`
- `0x720c0`
- `0x720d0`
- `0x720f0`
- `0x72120`
- `0x721b0`
- `0x721e0`
- `0x721f0`
- `0x72200`
- `0x72230`
- `0x72240`
- `0x72270`
- `0x72280`
- `0x722a0`
- `0x722b0`
- `0x72320`
- `0x72350`
- `0x72380`
- `0x72390`
- `0x72450`
- `0x72500`
- `0x72560`
- `0x72630`
- `0x72810`
- `0x7b300`
- `0x7b3d0`
- `0x7e6e0`
- `0x84e90`
- `0x863b0`
- `0x87070`
- `0x87180`
- `0x872a0`

## string_xrefs

- `0x8641f`: `UpdateAll`
- `0x86946`: `BackupDataSetBeforeUpdate`
- `0x86df7`: `BackupDataSetBeforeUpdate`
- `0x86cc6`: `UpdateOrderOption`
- `0x86cd5`: `UpdateInsertDelete`
- `0x86cbc`: `UpdateOrder`
- `0x863bc`: `deletedRows`
- `0x863c8`: `updatedRows`
- `0x863e4`: `workConnOpened`
- `0x863f9`: `adaptersWithAcceptChangesDuringUpdate`
- `0x86492`: `Update all changes to the dataset.`
- `0x869ab`: `---- Prepare for update -----------\n`
- `0x86a9f`: `AcceptChangesDuringUpdate`
- `0x86ac2`: `AcceptChangesDuringUpdate`
- `0x86b10`: `Note: Adapter is not a DataAdapter, so AcceptChangesDuringUpdate cannot be set to false.`
- `0x86c2f`: `\n---- Perform updates -----------\n`
- `0x86c48`: `UpdateInsertedRows`
- `0x86c81`: `UpdateUpdatedRows`
- `0x86d1a`: `UpdateDeletedRows`
- `0x86d4e`: `\n---- Commit updates -----------\n`
- `0x86d66`: `Commit`
- `0x86dc9`: `Rollback`

## pseudocode

```c

```

## disassembly

```asm
0x863b0  ldstr    aDataset// "dataSet"
0x863b5  stloc.0
0x863b6  ldstr    aBackupdataset// "backupDataSet"
0x863bb  stloc.1
0x863bc  ldstr    aDeletedrows// "deletedRows"
0x863c1  stloc.2
0x863c2  ldstr    aAddedrows// "addedRows"
0x863c7  stloc.3
0x863c8  ldstr    aUpdatedrows// "updatedRows"
0x863cd  stloc.s  4
0x863cf  ldstr    aResult// "result"
0x863d4  stloc.s  5
0x863d6  ldstr    aWorkconnection// "workConnection"
0x863db  stloc.s  6
0x863dd  ldstr    aWorktransactio// "workTransaction"
0x863e2  stloc.s  7
0x863e4  ldstr    aWorkconnopened// "workConnOpened"
0x863e9  stloc.s  8
0x863eb  ldstr    aAllchangedrows// "allChangedRows"
0x863f0  stloc.s  9
0x863f2  ldstr    aAlladdedrows// "allAddedRows"
0x863f7  stloc.s  0xA
0x863f9  ldstr    aAdapterswithac// "adaptersWithAcceptChangesDuringUpdate"
0x863fe  stloc.s  0xB
0x86400  ldstr    aRevertconnecti// "revertConnections"
0x86405  stloc.s  0xC
0x86407  ldloc.s  5
0x86409  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8640e  stloc.s  0xD
0x86410  ldtoken  [mscorlib]System.Int32
0x86415  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8641a  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8641f  ldstr    aUpdateall// "UpdateAll"
0x86424  ldc.i4   0x6000
0x86429  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x8642e  stloc.s  0xE
0x86430  ldarg.0
0x86431  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.TableAdapterManagerMethodGenerator::dataSourceType
0x86436  callvirt instance string [System]System.CodeDom.CodeTypeMember::get_Name()
0x8643b  stloc.s  0xF
0x8643d  ldarg.0
0x8643e  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableAdapterManagerMethodGenerator::codeGenerator
0x86443  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x86448  brfalse.s loc_86469
0x8644a  ldarg.0
0x8644b  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableAdapterManagerMethodGenerator::codeGenerator
0x86450  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider System.Data.Design.TypedDataSourceCodeGenerator::get_CodeProvider()
0x86455  ldarg.0
0x86456  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableAdapterManagerMethodGenerator::codeGenerator
0x8645b  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x86460  ldloc.s  0xF
0x86462  call     string System.Data.Design.CodeGenHelper::GetTypeName(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, string string1, string string2)
0x86467  stloc.s  0xF
0x86469  ldloc.s  0xF
0x8646b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x86470  stloc.s  0x10
0x86472  ldloc.s  0x10
0x86474  ldloc.0
0x86475  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x8647a  stloc.s  0x11
0x8647c  ldloc.s  0xE
0x8647e  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x86483  ldloc.s  0x11
0x86485  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x8648a  pop
0x8648b  ldloc.s  0xE
0x8648d  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x86492  ldstr    aUpdateAllChang// "Update all changes to the dataset."
0x86497  ldc.i4.1
0x86498  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x8649d  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x864a2  pop
0x864a3  ldloc.s  0xE
0x864a5  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x864aa  ldloc.0
0x864ab  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x864b0  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNull(class [System]System.CodeDom.CodeExpression id)
0x864b5  ldtoken  [mscorlib]System.ArgumentNullException
0x864ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x864bf  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x864c4  ldloc.0
0x864c5  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Throw(class [System]System.CodeDom.CodeTypeReference exception, string arg)
0x864ca  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x864cf  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x864d4  pop
0x864d5  ldloc.s  0xE
0x864d7  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x864dc  ldloc.0
0x864dd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x864e2  ldstr    aHaschanges// "HasChanges"
0x864e7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x864ec  ldc.i4.0
0x864ed  box      [mscorlib]System.Boolean
0x864f2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x864f7  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x864fc  ldc.i4.0
0x864fd  box      [mscorlib]System.Int32
0x86502  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x86507  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8650c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x86511  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x86516  pop
0x86517  ldarg.0
0x86518  ldfld    class System.Data.Design.DesignDataSource System.Data.Design.TableAdapterManagerMethodGenerator::dataSource
0x8651d  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x86522  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x86527  stloc.s  0x1A
0x86529  br       loc_865E4
0x8652e  ldloc.s  0x1A
0x86530  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x86535  castclass System.Data.Design.DesignTable
0x8653a  stloc.s  0x1B
0x8653c  ldarg.0
0x8653d  ldloc.s  0x1B
0x8653f  call     instance bool System.Data.Design.TableAdapterManagerMethodGenerator::CanAddTableAdapter(class System.Data.Design.DesignTable table)
0x86544  brfalse  loc_865E4
0x86549  ldloc.s  0x1B
0x8654b  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x86550  callvirt instance string CodeGenPropertyCache::get_TAMAdapterVarName()
0x86555  stloc.s  0x1C
0x86557  ldloc.s  0xE
0x86559  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8655e  ldloc.s  0x1C
0x86560  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x86565  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNotNull(class [System]System.CodeDom.CodeExpression id)
0x8656a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8656f  ldstr    aMatchtableadap// "MatchTableAdapterConnection"
0x86574  ldloc.s  0x1C
0x86576  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x8657b  ldstr    aConnection// "Connection"
0x86580  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x86585  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x8658a  ldc.i4.0
0x8658b  box      [mscorlib]System.Boolean
0x86590  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x86595  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8659a  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8659f  ldc.i4.1
0x865a0  newarr   [System]System.CodeDom.CodeStatement
0x865a5  dup
0x865a6  ldc.i4.0
0x865a7  ldtoken  [mscorlib]System.ArgumentException
0x865ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x865b1  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x865b6  ldc.i4.1
0x865b7  newarr   [System]System.CodeDom.CodeExpression
0x865bc  dup
0x865bd  ldc.i4.0
0x865be  ldstr    aCgTableadapter// "CG_TableAdapterManagerNeedsSameConnStri"...
0x865c3  call     string System.Design.SR::GetString(string name)
0x865c8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x865cd  stelem.ref
0x865ce  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x865d3  newobj   instance void [System]System.CodeDom.CodeThrowExceptionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x865d8  stelem.ref
0x865d9  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x865de  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x865e3  pop
0x865e4  ldloc.s  0x1A
0x865e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x865eb  brtrue   loc_8652E
0x865f0  leave.s  loc_86607
0x865f2  ldloc.s  0x1A
0x865f4  isinst   [mscorlib]System.IDisposable
0x865f9  stloc.s  0x1D
0x865fb  ldloc.s  0x1D
0x865fd  brfalse.s loc_86606
0x865ff  ldloc.s  0x1D
0x86601  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86606  endfinally
0x86607  ldloc.s  0xE
0x86609  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8660e  ldtoken  [System.Data]System.Data.IDbConnection
0x86613  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86618  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8661d  ldloc.s  6
0x8661f  ldstr    aConnection// "Connection"
0x86624  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisProperty(string property)
0x86629  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8662e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x86633  pop
0x86634  ldloc.s  0xE
0x86636  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8663b  ldloc.s  6
0x8663d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x86642  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNull(class [System]System.CodeDom.CodeExpression id)
0x86647  ldtoken  [mscorlib]System.ApplicationException
0x8664c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86651  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x86656  ldstr    aCgTableadapter_0// "CG_TableAdapterManagerHasNoConnection"
0x8665b  call     string System.Design.SR::GetString(string name)
0x86660  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Throw(class [System]System.CodeDom.CodeTypeReference exception, string arg)
0x86665  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x8666a  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8666f  pop
0x86670  ldloc.s  0xE
0x86672  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x86677  ldtoken  [mscorlib]System.Boolean
0x8667c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86681  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x86686  ldloc.s  8
0x86688  ldc.i4.0
0x86689  box      [mscorlib]System.Boolean
0x8668e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x86693  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x86698  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8669d  pop
0x8669e  ldloc.s  0xE
0x866a0  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x866a5  ldloc.s  6
0x866a7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x866ac  ldstr    aState// "State"
0x866b1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x866b6  ldtoken  [System.Data]System.Data.ConnectionState
0x866bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x866c0  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x866c5  ldstr    aBroken// "Broken"
0x866ca  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x866cf  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::BitwiseAnd(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x866d4  ldtoken  [System.Data]System.Data.ConnectionState
0x866d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x866de  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x866e3  ldstr    aBroken// "Broken"
0x866e8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x866ed  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x866f2  ldloc.s  6
0x866f4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x866f9  ldstr    aClose// "Close"
0x866fe  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::MethodCallStm(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x86703  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x86708  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8670d  pop
0x8670e  ldloc.s  0xE
0x86710  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x86715  ldloc.s  6
0x86717  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8671c  ldstr    aState// "State"
0x86721  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x86726  ldtoken  [System.Data]System.Data.ConnectionState
0x8672b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86730  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x86735  ldstr    aClosed// "Closed"
0x8673a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8673f  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x86744  ldc.i4.2
0x86745  newarr   [System]System.CodeDom.CodeStatement
0x8674a  dup
0x8674b  ldc.i4.0
0x8674c  ldloc.s  6
0x8674e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x86753  ldstr    aOpen// "Open"
0x86758  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::MethodCallStm(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x8675d  stelem.ref
0x8675e  dup
0x8675f  ldc.i4.1
0x86760  ldloc.s  8
0x86762  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x86767  ldc.i4.1
0x86768  box      [mscorlib]System.Boolean
0x8676d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x86772  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x86777  stelem.ref
0x86778  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x8677d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x86782  pop
0x86783  ldloc.s  0xE
0x86785  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8678a  ldtoken  [System.Data]System.Data.IDbTransaction
0x8678f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86794  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x86799  ldloc.s  7
0x8679b  ldloc.s  6
0x8679d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x867a2  ldstr    aBegintransacti// "BeginTransaction"
0x867a7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x867ac  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x867b1  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x867b6  pop
0x867b7  ldloc.s  0xE
0x867b9  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x867be  ldloc.s  7
0x867c0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x867c5  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNull(class [System]System.CodeDom.CodeExpression id)
0x867ca  ldtoken  [mscorlib]System.ApplicationException
0x867cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x867d4  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x867d9  ldstr    aCgTableadapter_1// "CG_TableAdapterManagerNotSupportTransac"...
0x867de  call     string System.Design.SR::GetString(string name)
0x867e3  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Throw(class [System]System.CodeDom.CodeTypeReference exception, string arg)
0x867e8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x867ed  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x867f2  pop
0x867f3  ldstr    aSystemCollecti_2// "System.Collections.Generic.List"
0x867f8  ldtoken  [System.Data]System.Data.DataRow
0x867fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x86802  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalGenericType(string fullTypeName, class [mscorlib]System.Type itemType)
0x86807  stloc.s  0x12
0x86809  ldloc.s  0xE
0x8680b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x86810  ldloc.s  0x12
  ... truncated ...
```
