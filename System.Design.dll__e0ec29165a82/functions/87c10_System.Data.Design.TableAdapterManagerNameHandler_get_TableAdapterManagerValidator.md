# System.Data.Design.TableAdapterManagerNameHandler::get_TableAdapterManagerValidator

- ea: `0x87c10`
- end: `0x87cc7`
- name: `System.Data.Design.TableAdapterManagerNameHandler::get_TableAdapterManagerValidator`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x87cd0`

## callees

- `0x7fa90`
- `0x87c10`

## string_xrefs

- `0x87c2d`: `UpdateAll`
- `0x87c5d`: `BackupDataSetBeforeUpdate`
- `0x87c55`: `_backupDataSetBeforeUpdate`
- `0x87c80`: `UpdateOrderOption`
- `0x87c6e`: `UpdateOrder`
- `0x87c77`: `_updateOrder`
- `0x87c25`: `SelfReferenceComparer`
- `0x87c92`: `UpdateInsertedRows`
- `0x87c89`: `UpdateUpdatedRows`
- `0x87c9b`: `UpdateDeletedRows`
- `0x87ca4`: `GetRealUpdatedRows`

## pseudocode

```c

```

## disassembly

```asm
0x87c10  ldarg.0
0x87c11  ldfld    class System.Data.Design.MemberNameValidator System.Data.Design.TableAdapterManagerNameHandler::tableAdapterManagerValidator
0x87c16  brtrue   loc_87CC0
0x87c1b  ldarg.0
0x87c1c  ldc.i4.s 0x10
0x87c1e  newarr   [mscorlib]System.String
0x87c23  dup
0x87c24  ldc.i4.0
0x87c25  ldstr    aSelfreferencec// "SelfReferenceComparer"
0x87c2a  stelem.ref
0x87c2b  dup
0x87c2c  ldc.i4.1
0x87c2d  ldstr    aUpdateall// "UpdateAll"
0x87c32  stelem.ref
0x87c33  dup
0x87c34  ldc.i4.2
0x87c35  ldstr    aSortselfrefere// "SortSelfReferenceRows"
0x87c3a  stelem.ref
0x87c3b  dup
0x87c3c  ldc.i4.3
0x87c3d  ldstr    aMatchtableadap// "MatchTableAdapterConnection"
0x87c42  stelem.ref
0x87c43  dup
0x87c44  ldc.i4.4
0x87c45  ldstr    aConnection_0// "_connection"
0x87c4a  stelem.ref
0x87c4b  dup
0x87c4c  ldc.i4.5
0x87c4d  ldstr    aConnection// "Connection"
0x87c52  stelem.ref
0x87c53  dup
0x87c54  ldc.i4.6
0x87c55  ldstr    aBackupdatasetb_0// "_backupDataSetBeforeUpdate"
0x87c5a  stelem.ref
0x87c5b  dup
0x87c5c  ldc.i4.7
0x87c5d  ldstr    aBackupdatasetb// "BackupDataSetBeforeUpdate"
0x87c62  stelem.ref
0x87c63  dup
0x87c64  ldc.i4.8
0x87c65  ldstr    aTableadapterin// "TableAdapterInstanceCount"
0x87c6a  stelem.ref
0x87c6b  dup
0x87c6c  ldc.i4.s 9
0x87c6e  ldstr    aUpdateorder// "UpdateOrder"
0x87c73  stelem.ref
0x87c74  dup
0x87c75  ldc.i4.s 0xA
0x87c77  ldstr    aUpdateorder_0// "_updateOrder"
0x87c7c  stelem.ref
0x87c7d  dup
0x87c7e  ldc.i4.s 0xB
0x87c80  ldstr    aUpdateorderopt// "UpdateOrderOption"
0x87c85  stelem.ref
0x87c86  dup
0x87c87  ldc.i4.s 0xC
0x87c89  ldstr    aUpdateupdatedr// "UpdateUpdatedRows"
0x87c8e  stelem.ref
0x87c8f  dup
0x87c90  ldc.i4.s 0xD
0x87c92  ldstr    aUpdateinserted// "UpdateInsertedRows"
0x87c97  stelem.ref
0x87c98  dup
0x87c99  ldc.i4.s 0xE
0x87c9b  ldstr    aUpdatedeletedr// "UpdateDeletedRows"
0x87ca0  stelem.ref
0x87ca1  dup
0x87ca2  ldc.i4.s 0xF
0x87ca4  ldstr    aGetrealupdated// "GetRealUpdatedRows"
0x87ca9  stelem.ref
0x87caa  ldarg.0
0x87cab  ldfld    class [System]System.CodeDom.Compiler.CodeDomProvider System.Data.Design.TableAdapterManagerNameHandler::codePrivider
0x87cb0  ldarg.0
0x87cb1  ldfld    bool System.Data.Design.TableAdapterManagerNameHandler::languageCaseInsensitive
0x87cb6  newobj   instance void System.Data.Design.MemberNameValidator::.ctor(class [mscorlib]System.Collections.ICollection initialNameSet, class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, bool languageCaseInsensitive)
0x87cbb  stfld    class System.Data.Design.MemberNameValidator System.Data.Design.TableAdapterManagerNameHandler::tableAdapterManagerValidator
0x87cc0  ldarg.0
0x87cc1  ldfld    class System.Data.Design.MemberNameValidator System.Data.Design.TableAdapterManagerNameHandler::tableAdapterManagerValidator
0x87cc6  ret
```
