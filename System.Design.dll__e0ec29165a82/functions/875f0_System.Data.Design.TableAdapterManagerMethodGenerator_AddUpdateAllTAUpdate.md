# System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAllTAUpdate

- ea: `0x875f0`
- end: `0x8783e`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAllTAUpdate`
- size: `590`
- prototype: ``
- caller_count: `3`
- callee_count: `29`
- tags: `installer_update`

## callers

- `0x87070`
- `0x87180`
- `0x872a0`

## callees

- `0x71e90`
- `0x71f30`
- `0x71f60`
- `0x71fd0`
- `0x71fe0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72070`
- `0x72080`
- `0x72090`
- `0x720d0`
- `0x72120`
- `0x721b0`
- `0x721c0`
- `0x72240`
- `0x72260`
- `0x72270`
- `0x722a0`
- `0x72380`
- `0x72500`
- `0x7cca0`
- `0x7e400`
- `0x7e6e0`
- `0x84c60`
- `0x84c90`
- `0x84e10`
- `0x875f0`
- `0x10d870`

## string_xrefs

- `0x87617`: `Update`
- `0x8766d`: `Deleted`
- `0x877ab`: `GetRealUpdatedRows`

## pseudocode

```c

```

## disassembly

```asm
0x875f0  ldarg.1
0x875f1  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x875f6  callvirt instance string CodeGenPropertyCache::get_TAMAdapterVarName()
0x875fb  stloc.0
0x875fc  ldc.i4.2
0x875fd  newarr   [System]System.CodeDom.CodeStatement
0x87602  dup
0x87603  ldc.i4.0
0x87604  ldarg.3
0x87605  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8760a  ldarg.3
0x8760b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87610  ldc.i4.0
0x87611  ldloc.0
0x87612  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x87617  ldstr    aUpdate// "Update"
0x8761c  ldarg.s  4
0x8761e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87623  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x87628  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::BinOperator(class [System]System.CodeDom.CodeExpression left, valuetype [System]System.CodeDom.CodeBinaryOperatorType op, class [System]System.CodeDom.CodeExpression right)
0x8762d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87632  stelem.ref
0x87633  dup
0x87634  ldc.i4.1
0x87635  ldarg.s  5
0x87637  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8763c  ldstr    aAddrange// "AddRange"
0x87641  ldarg.s  4
0x87643  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87648  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x8764d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x87652  stelem.ref
0x87653  stloc.1
0x87654  ldarg.1
0x87655  callvirt instance class [System.Data]System.Data.DataTable System.Data.Design.DesignTable::get_DataTable()
0x8765a  call     class [System.Data]System.Data.DataRelation[] System.Data.Design.TableAdapterManagerHelper::GetSelfRefRelations(class [System.Data]System.Data.DataTable dataTable)
0x8765f  stloc.2
0x87660  ldloc.2
0x87661  brfalse  loc_87725
0x87666  ldloc.2
0x87667  ldlen
0x87668  brfalse  loc_87725
0x8766d  ldstr    aDeleted// "Deleted"
0x87672  ldarg.s  6
0x87674  ldc.i4.1
0x87675  call     bool System.Data.Design.StringUtil::EqualValue(string str1, string str2, bool caseInsensitive)
0x8767a  stloc.s  5
0x8767c  ldloc.1
0x8767d  ldlen
0x8767e  conv.i4
0x8767f  ldloc.2
0x87680  ldlen
0x87681  conv.i4
0x87682  add
0x87683  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::.ctor(int32)
0x87688  stloc.s  6
0x8768a  ldc.i4.0
0x8768b  stloc.s  7
0x8768d  br.s     loc_8770B
0x8768f  ldloc.s  7
0x87691  ldc.i4.0
0x87692  ble.s    loc_876A5
0x87694  ldloc.s  6
0x87696  ldstr    aNoteMoreThanOn// "Note: More than one self-referenced rel"...
0x8769b  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string)
0x876a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x876a5  ldloc.s  6
0x876a7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x876ac  ldstr    aSortselfrefere// "SortSelfReferenceRows"
0x876b1  ldc.i4.3
0x876b2  newarr   [System]System.CodeDom.CodeExpression
0x876b7  dup
0x876b8  ldc.i4.0
0x876b9  ldarg.s  4
0x876bb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x876c0  stelem.ref
0x876c1  dup
0x876c2  ldc.i4.1
0x876c3  ldarg.2
0x876c4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x876c9  ldstr    aRelations// "Relations"
0x876ce  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x876d3  ldloc.2
0x876d4  ldloc.s  7
0x876d6  ldelem.ref
0x876d7  callvirt instance string [System.Data]System.Data.DataRelation::get_RelationName()
0x876dc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x876e1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x876e6  stelem.ref
0x876e7  dup
0x876e8  ldc.i4.2
0x876e9  ldloc.s  5
0x876eb  box      [mscorlib]System.Boolean
0x876f0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x876f5  stelem.ref
0x876f6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x876fb  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x87700  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x87705  ldloc.s  7
0x87707  ldc.i4.1
0x87708  add
0x87709  stloc.s  7
0x8770b  ldloc.s  7
0x8770d  ldloc.2
0x8770e  ldlen
0x8770f  conv.i4
0x87710  blt      loc_8768F
0x87715  ldloc.s  6
0x87717  ldloc.1
0x87718  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x8771d  ldloc.s  6
0x8771f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::ToArray()
0x87724  stloc.1
0x87725  ldc.i4.3
0x87726  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::.ctor(int32)
0x8772b  stloc.3
0x8772c  ldloc.3
0x8772d  ldtoken  [System.Data]System.Data.DataRow
0x87732  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87737  ldc.i4.1
0x87738  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x8773d  ldarg.s  4
0x8773f  ldarg.2
0x87740  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x87745  ldarg.1
0x87746  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTablePropName()
0x8774b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x87750  ldstr    aSelect_1// "Select"
0x87755  ldc.i4.3
0x87756  newarr   [System]System.CodeDom.CodeExpression
0x8775b  dup
0x8775c  ldc.i4.0
0x8775d  ldnull
0x8775e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x87763  stelem.ref
0x87764  dup
0x87765  ldc.i4.1
0x87766  ldnull
0x87767  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8776c  stelem.ref
0x8776d  dup
0x8776e  ldc.i4.2
0x8776f  ldtoken  [System.Data]System.Data.DataViewRowState
0x87774  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87779  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8777e  ldarg.s  6
0x87780  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x87785  stelem.ref
0x87786  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8778b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x87790  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x87795  ldarg.s  7
0x87797  call     bool System.Data.Design.StringUtil::NotEmptyAfterTrim(string str)
0x8779c  brfalse.s loc_877D9
0x8779e  ldloc.3
0x8779f  ldarg.s  4
0x877a1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x877a6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x877ab  ldstr    aGetrealupdated// "GetRealUpdatedRows"
0x877b0  ldc.i4.2
0x877b1  newarr   [System]System.CodeDom.CodeExpression
0x877b6  dup
0x877b7  ldc.i4.0
0x877b8  ldarg.s  4
0x877ba  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x877bf  stelem.ref
0x877c0  dup
0x877c1  ldc.i4.1
0x877c2  ldarg.s  7
0x877c4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x877c9  stelem.ref
0x877ca  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x877cf  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x877d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x877d9  ldloc.3
0x877da  ldarg.s  4
0x877dc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x877e1  ldnull
0x877e2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x877e7  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x877ec  ldc.i4.0
0x877ed  box      [mscorlib]System.Int32
0x877f2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x877f7  ldarg.s  4
0x877f9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x877fe  ldstr    aLength// "Length"
0x87803  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x87808  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8780d  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87812  ldloc.1
0x87813  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x87818  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x8781d  ldloc.0
0x8781e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x87823  ldnull
0x87824  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x87829  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8782e  ldloc.3
0x8782f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::ToArray()
0x87834  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x87839  stloc.s  4
0x8783b  ldloc.s  4
0x8783d  ret
```
