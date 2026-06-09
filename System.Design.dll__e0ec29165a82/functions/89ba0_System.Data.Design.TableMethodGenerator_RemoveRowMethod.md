# System.Data.Design.TableMethodGenerator::RemoveRowMethod

- ea: `0x89ba0`
- end: `0x89c21`
- name: `System.Data.Design.TableMethodGenerator::RemoveRowMethod`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x87d60`

## callees

- `0x71e90`
- `0x71ec0`
- `0x71f20`
- `0x71ff0`
- `0x72010`
- `0x720d0`
- `0x72450`
- `0x72560`
- `0x805c0`

## string_xrefs

- `0x89baf`: `Remove`
- `0x89c05`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x89ba0  ldtoken  [mscorlib]System.Void
0x89ba5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89baa  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89baf  ldstr    aRemove// "Remove"
0x89bb4  ldarg.0
0x89bb5  ldfld    string System.Data.Design.TableMethodGenerator::rowClassName
0x89bba  call     string [mscorlib]System.String::Concat(string, string)
0x89bbf  call     string System.Data.Design.NameHandler::FixIdName(string inVarName)
0x89bc4  ldc.i4   0x6002
0x89bc9  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x89bce  stloc.0
0x89bcf  ldloc.0
0x89bd0  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x89bd5  ldarg.0
0x89bd6  ldfld    string System.Data.Design.TableMethodGenerator::rowConcreteClassName
0x89bdb  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x89be0  ldstr    aRow_0// "row"
0x89be5  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x89bea  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x89bef  pop
0x89bf0  ldloc.0
0x89bf1  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89bf6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x89bfb  ldstr    aRows// "Rows"
0x89c00  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89c05  ldstr    aRemove// "Remove"
0x89c0a  ldstr    aRow_0// "row"
0x89c0f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x89c14  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x89c19  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeExpression)
0x89c1e  pop
0x89c1f  ldloc.0
0x89c20  ret
```
