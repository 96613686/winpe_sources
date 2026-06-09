# System.Data.Design.DataComponentMethodGenerator::AddInitAdapterCommands

- ea: `0x74090`
- end: `0x74163`
- name: `System.Data.Design.DataComponentMethodGenerator::AddInitAdapterCommands`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x73410`

## callees

- `0x71e90`
- `0x71fd0`
- `0x71ff0`
- `0x74090`
- `0x74170`
- `0x747f0`
- `0x7cce0`
- `0x7cde0`
- `0x7d130`

## string_xrefs

- `0x740ac`: `DeleteCommand`
- `0x740f2`: `InsertCommand`
- `0x74138`: `UpdateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x74090  ldarg.0
0x74091  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x74096  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_DeleteCommand()
0x7409b  brfalse.s loc_740D6
0x7409d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x740a2  call     string System.Data.Design.DataComponentNameHandler::get_AdapterVariableName()
0x740a7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x740ac  ldstr    aDeletecommand// "DeleteCommand"
0x740b1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x740b6  stloc.0
0x740b7  ldarg.0
0x740b8  ldarg.1
0x740b9  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x740be  ldloc.0
0x740bf  ldarg.0
0x740c0  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x740c5  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_DeleteCommand()
0x740ca  ldarg.0
0x740cb  ldfld    class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.DataComponentMethodGenerator::providerFactory
0x740d0  ldc.i4.0
0x740d1  call     instance void System.Data.Design.DataComponentMethodGenerator::AddCommandInitStatements(class [mscorlib]System.Collections.IList statements, class [System]System.CodeDom.CodeExpression commandExpression, class System.Data.Design.DbSourceCommand command, class [System.Data]System.Data.Common.DbProviderFactory currentFactory, bool isFunctionsDataComponent)
0x740d6  ldarg.0
0x740d7  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x740dc  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_InsertCommand()
0x740e1  brfalse.s loc_7411C
0x740e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x740e8  call     string System.Data.Design.DataComponentNameHandler::get_AdapterVariableName()
0x740ed  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x740f2  ldstr    aInsertcommand// "InsertCommand"
0x740f7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x740fc  stloc.1
0x740fd  ldarg.0
0x740fe  ldarg.1
0x740ff  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x74104  ldloc.1
0x74105  ldarg.0
0x74106  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x7410b  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_InsertCommand()
0x74110  ldarg.0
0x74111  ldfld    class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.DataComponentMethodGenerator::providerFactory
0x74116  ldc.i4.0
0x74117  call     instance void System.Data.Design.DataComponentMethodGenerator::AddCommandInitStatements(class [mscorlib]System.Collections.IList statements, class [System]System.CodeDom.CodeExpression commandExpression, class System.Data.Design.DbSourceCommand command, class [System.Data]System.Data.Common.DbProviderFactory currentFactory, bool isFunctionsDataComponent)
0x7411c  ldarg.0
0x7411d  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x74122  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_UpdateCommand()
0x74127  brfalse.s loc_74162
0x74129  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x7412e  call     string System.Data.Design.DataComponentNameHandler::get_AdapterVariableName()
0x74133  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x74138  ldstr    aUpdatecommand// "UpdateCommand"
0x7413d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x74142  stloc.2
0x74143  ldarg.0
0x74144  ldarg.1
0x74145  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x7414a  ldloc.2
0x7414b  ldarg.0
0x7414c  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x74151  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DesignTable::get_UpdateCommand()
0x74156  ldarg.0
0x74157  ldfld    class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.DataComponentMethodGenerator::providerFactory
0x7415c  ldc.i4.0
0x7415d  call     instance void System.Data.Design.DataComponentMethodGenerator::AddCommandInitStatements(class [mscorlib]System.Collections.IList statements, class [System]System.CodeDom.CodeExpression commandExpression, class System.Data.Design.DbSourceCommand command, class [System.Data]System.Data.Common.DbProviderFactory currentFactory, bool isFunctionsDataComponent)
0x74162  ret
```
