# System.Windows.Forms.Design.AxWrapperGen::WritePropertySetterMethod

- ea: `0x94960`
- end: `0x94b30`
- name: `System.Windows.Forms.Design.AxWrapperGen::WritePropertySetterMethod`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x94880`

## callees

- `0x91a20`
- `0x92280`
- `0x925a0`
- `0x94960`
- `0x94d90`
- `0x112cf0`

## string_xrefs

- `0x94a83`: `paramTemp`
- `0x94a95`: `paramTemp`
- `0x94ab8`: `paramTemp`

## pseudocode

```c

```

## disassembly

```asm
0x94960  ldnull
0x94961  stloc.0
0x94962  ldnull
0x94963  stloc.1
0x94964  ldnull
0x94965  stloc.2
0x94966  ldarg.s  5
0x94968  brfalse.s loc_949B4
0x9496a  ldarg.s  4
0x9496c  ldlen
0x9496d  brfalse.s loc_94983
0x9496f  ldarg.0
0x94970  ldfld    class [System]System.CodeDom.CodeFieldReferenceExpression System.Windows.Forms.Design.AxWrapperGen::memIfaceRef
0x94975  ldc.i4.0
0x94976  newarr   [System]System.CodeDom.CodeExpression
0x9497b  newobj   instance void [System]System.CodeDom.CodeIndexerExpression::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression[])
0x94980  stloc.0
0x94981  br.s     loc_94994
0x94983  newobj   instance void [System]System.CodeDom.CodeBaseReferenceExpression::.ctor()
0x94988  ldarg.2
0x94989  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9498e  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94993  stloc.0
0x94994  ldarg.0
0x94995  ldfld    class [System]System.CodeDom.CodeFieldReferenceExpression System.Windows.Forms.Design.AxWrapperGen::memIfaceRef
0x9499a  ldc.i4.6
0x9499b  ldnull
0x9499c  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x949a1  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x949a6  stloc.1
0x949a7  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x949ac  stloc.2
0x949ad  ldloc.2
0x949ae  ldloc.1
0x949af  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x949b4  ldarg.s  6
0x949b6  brtrue.s loc_949C5
0x949b8  ldarg.2
0x949b9  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.PropertyInfo::GetSetMethod()
0x949be  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x949c3  br.s     loc_949D5
0x949c5  ldstr    aLet// "let_"
0x949ca  ldarg.2
0x949cb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x949d0  call     string [mscorlib]System.String::Concat(string, string)
0x949d5  stloc.s  4
0x949d7  ldarg.0
0x949d8  ldfld    class [System]System.CodeDom.CodeFieldReferenceExpression System.Windows.Forms.Design.AxWrapperGen::memIfaceRef
0x949dd  ldloc.s  4
0x949df  ldc.i4.0
0x949e0  newarr   [System]System.CodeDom.CodeExpression
0x949e5  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor(class [System]System.CodeDom.CodeExpression, string, class [System]System.CodeDom.CodeExpression[])
0x949ea  stloc.s  5
0x949ec  ldc.i4.0
0x949ed  stloc.s  8
0x949ef  br.s     loc_94A39
0x949f1  ldarg.s  5
0x949f3  brfalse.s loc_94A16
0x949f5  ldloc.0
0x949f6  castclass [System]System.CodeDom.CodeIndexerExpression
0x949fb  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeIndexerExpression::get_Indices()
0x94a00  ldnull
0x94a01  ldarg.s  4
0x94a03  ldloc.s  8
0x94a05  ldelem.ref
0x94a06  callvirt instance string System.Windows.Forms.Design.AxParameterData::get_Name()
0x94a0b  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94a10  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x94a15  pop
0x94a16  ldloc.s  5
0x94a18  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x94a1d  ldnull
0x94a1e  ldarg.s  4
0x94a20  ldloc.s  8
0x94a22  ldelem.ref
0x94a23  callvirt instance string System.Windows.Forms.Design.AxParameterData::get_Name()
0x94a28  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94a2d  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x94a32  pop
0x94a33  ldloc.s  8
0x94a35  ldc.i4.1
0x94a36  add
0x94a37  stloc.s  8
0x94a39  ldloc.s  8
0x94a3b  ldarg.s  4
0x94a3d  ldlen
0x94a3e  conv.i4
0x94a3f  blt.s    loc_949F1
0x94a41  ldnull
0x94a42  ldstr    aValue// "value"
0x94a47  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94a4c  stloc.s  6
0x94a4e  ldarg.0
0x94a4f  ldarg.3
0x94a50  ldarg.2
0x94a51  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x94a56  call     instance class [System]System.CodeDom.CodeExpression System.Windows.Forms.Design.AxWrapperGen::GetPropertySetRValue(valuetype ComAliasEnum alias, class [mscorlib]System.Type propertyType)
0x94a5b  stloc.s  7
0x94a5d  ldarg.3
0x94a5e  brfalse.s loc_94AC5
0x94a60  ldarg.3
0x94a61  ldarg.2
0x94a62  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x94a67  call     string ComAliasConverter::GetWFToComParamConverter(valuetype ComAliasEnum alias, class [mscorlib]System.Type t)
0x94a6c  stloc.s  9
0x94a6e  ldloc.s  9
0x94a70  callvirt instance int32 [mscorlib]System.String::get_Length()
0x94a75  brtrue.s loc_94A92
0x94a77  ldarg.0
0x94a78  ldarg.2
0x94a79  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x94a7e  call     string System.Windows.Forms.Design.AxWrapperGen::MapTypeName(class [mscorlib]System.Type type)
0x94a83  ldstr    aParamtemp// "paramTemp"
0x94a88  ldc.i4.0
0x94a89  call     instance class [System]System.CodeDom.CodeParameterDeclarationExpression System.Windows.Forms.Design.AxWrapperGen::CreateParamDecl(string type, string name, bool isOptional)
0x94a8e  stloc.s  0xA
0x94a90  br.s     loc_94AA2
0x94a92  ldarg.0
0x94a93  ldloc.s  9
0x94a95  ldstr    aParamtemp// "paramTemp"
0x94a9a  ldc.i4.0
0x94a9b  call     instance class [System]System.CodeDom.CodeParameterDeclarationExpression System.Windows.Forms.Design.AxWrapperGen::CreateParamDecl(string type, string name, bool isOptional)
0x94aa0  stloc.s  0xA
0x94aa2  ldarg.1
0x94aa3  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x94aa8  ldloc.s  0xA
0x94aaa  ldloc.s  7
0x94aac  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x94ab1  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x94ab6  pop
0x94ab7  ldnull
0x94ab8  ldstr    aParamtemp// "paramTemp"
0x94abd  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x94ac2  stloc.3
0x94ac3  br.s     loc_94AC8
0x94ac5  ldloc.s  6
0x94ac7  stloc.3
0x94ac8  ldloc.s  5
0x94aca  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeMethodInvokeExpression::get_Parameters()
0x94acf  ldarg.s  6
0x94ad1  brtrue.s loc_94AD6
0x94ad3  ldc.i4.2
0x94ad4  br.s     loc_94AD7
0x94ad6  ldc.i4.0
0x94ad7  ldloc.3
0x94ad8  newobj   instance void [System]System.CodeDom.CodeDirectionExpression::.ctor(valuetype [System]System.CodeDom.FieldDirection, class [System]System.CodeDom.CodeExpression)
0x94add  callvirt instance int32 [System]System.CodeDom.CodeExpressionCollection::Add(class [System]System.CodeDom.CodeExpression)
0x94ae2  pop
0x94ae3  ldarg.s  5
0x94ae5  brfalse.s loc_94B1C
0x94ae7  ldarg.1
0x94ae8  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x94aed  ldloc.0
0x94aee  ldloc.s  6
0x94af0  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x94af5  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x94afa  pop
0x94afb  ldloc.2
0x94afc  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x94b01  ldloc.s  5
0x94b03  newobj   instance void [System]System.CodeDom.CodeExpressionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x94b08  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x94b0d  pop
0x94b0e  ldarg.1
0x94b0f  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x94b14  ldloc.2
0x94b15  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x94b1a  pop
0x94b1b  ret
0x94b1c  ldarg.1
0x94b1d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x94b22  ldloc.s  5
0x94b24  newobj   instance void [System]System.CodeDom.CodeExpressionStatement::.ctor(class [System]System.CodeDom.CodeExpression)
0x94b29  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x94b2e  pop
0x94b2f  ret
```
