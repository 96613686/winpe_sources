# System.Data.Design.TableAdapterManagerMethodGenerator::AddEverything

- ea: `0x85090`
- end: `0x850fd`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddEverything`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x84cc0`

## callees

- `0x71f20`
- `0x7f8f0`
- `0x85090`
- `0x85100`
- `0x851c0`
- `0x85310`
- `0x85490`
- `0x855c0`
- `0x856e0`
- `0x86240`
- `0x863b0`
- `0x87840`

## string_xrefs

- `0x85093`: `dataComponent CodeTypeDeclaration should not be null.`
- `0x850c2`: `BackupDataSetBeforeUpdate`
- `0x850c7`: `_backupDataSetBeforeUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x85090  ldarg.1
0x85091  brtrue.s loc_8509E
0x85093  ldstr    aDatacomponentC// "dataComponent CodeTypeDeclaration shoul"...
0x85098  newobj   instance void System.Data.Design.InternalException::.ctor(string internalMessage)
0x8509d  throw
0x8509e  ldarg.0
0x8509f  ldarg.1
0x850a0  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateOrderMembers(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850a5  ldarg.0
0x850a6  ldarg.1
0x850a7  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddAdapterMembers(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850ac  ldarg.0
0x850ad  ldarg.1
0x850ae  ldc.i4   0x6002
0x850b3  ldtoken  [mscorlib]System.Boolean
0x850b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x850bd  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x850c2  ldstr    aBackupdatasetb// "BackupDataSetBeforeUpdate"
0x850c7  ldstr    aBackupdatasetb_0// "_backupDataSetBeforeUpdate"
0x850cc  ldc.i4.0
0x850cd  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddVariableAndProperty(class [System]System.CodeDom.CodeTypeDeclaration codeType, valuetype [System]System.CodeDom.MemberAttributes memberAttributes, class [System]System.CodeDom.CodeTypeReference propertyType, string propertyName, string variableName, bool getOnly)
0x850d2  ldarg.0
0x850d3  ldarg.1
0x850d4  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddConnectionMembers(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850d9  ldarg.0
0x850da  ldarg.1
0x850db  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddTableAdapterCountMembers(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850e0  ldarg.0
0x850e1  ldarg.1
0x850e2  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAll(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850e7  ldarg.0
0x850e8  ldarg.1
0x850e9  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddSortSelfRefRows(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850ee  ldarg.0
0x850ef  ldarg.1
0x850f0  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddSelfRefComparer(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850f5  ldarg.0
0x850f6  ldarg.1
0x850f7  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddMatchTableAdapterConnection(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x850fc  ret
```
