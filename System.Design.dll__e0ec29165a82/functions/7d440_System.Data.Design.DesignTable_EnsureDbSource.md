# System.Data.Design.DesignTable::EnsureDbSource

- ea: `0x7d440`
- end: `0x7d53b`
- name: `System.Data.Design.DesignTable::EnsureDbSource`
- size: `251`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7cb70`
- `0x7cb90`
- `0x7cce0`
- `0x7ccf0`
- `0x7cde0`
- `0x7cdf0`
- `0x7d090`
- `0x7d0a0`
- `0x7d130`
- `0x7d140`

## callees

- `0x79920`
- `0x79c40`
- `0x79c90`
- `0x79ce0`
- `0x79d30`
- `0x7a100`
- `0x7a110`
- `0x7ce00`
- `0x7ce40`
- `0x7d440`
- `0x7f940`
- `0x84c30`

## string_xrefs

- `0x7d4b1`: `(DeleteCommand)`
- `0x7d4db`: `(UpdateCommand)`
- `0x7d505`: `(SelectCommand)`
- `0x7d52f`: `(InsertCommand)`

## pseudocode

```c

```

## disassembly

```asm
0x7d440  ldarg.0
0x7d441  ldfld    valuetype System.Data.Design.TableType System.Data.Design.DesignTable::tableType
0x7d446  ldc.i4.1
0x7d447  beq.s    loc_7D45C
0x7d449  ldnull
0x7d44a  ldstr    aOperationInval// "Operation invalid. Table gets data from"...
0x7d44f  ldc.i4   0x4E27
0x7d454  ldc.i4.0
0x7d455  ldc.i4.0
0x7d456  newobj   instance void System.Data.Design.InternalException::.ctor(class [mscorlib]System.Exception innerException, string internalMessage, int32 errorCode, bool showErrorMesageOnReport, bool needAssert)
0x7d45b  throw
0x7d45c  ldarg.0
0x7d45d  call     instance class System.Data.Design.Source System.Data.Design.DesignTable::get_MainSource()
0x7d462  brtrue.s loc_7D46F
0x7d464  ldarg.0
0x7d465  newobj   instance void System.Data.Design.DbSource::.ctor()
0x7d46a  call     instance void System.Data.Design.DesignTable::set_MainSource(class System.Data.Design.Source value)
0x7d46f  ldarg.0
0x7d470  ldfld    class System.Data.Design.Source System.Data.Design.DesignTable::mainSource
0x7d475  isinst   System.Data.Design.DbSource
0x7d47a  stloc.0
0x7d47b  ldloc.0
0x7d47c  brtrue.s loc_7D491
0x7d47e  ldnull
0x7d47f  ldstr    aOperationInval// "Operation invalid. Table gets data from"...
0x7d484  ldc.i4   0x4E27
0x7d489  ldc.i4.0
0x7d48a  ldc.i4.0
0x7d48b  newobj   instance void System.Data.Design.InternalException::.ctor(class [mscorlib]System.Exception innerException, string internalMessage, int32 errorCode, bool showErrorMesageOnReport, bool needAssert)
0x7d490  throw
0x7d491  ldloc.0
0x7d492  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_DeleteCommand()
0x7d497  brfalse.s loc_7D4BB
0x7d499  ldloc.0
0x7d49a  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_DeleteCommand()
0x7d49f  callvirt instance string System.Data.Design.DbSourceCommand::get_Name()
0x7d4a4  call     bool System.Data.Design.StringUtil::EmptyOrSpace(string str)
0x7d4a9  brfalse.s loc_7D4BB
0x7d4ab  ldloc.0
0x7d4ac  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_DeleteCommand()
0x7d4b1  ldstr    aDeletecommand_0// "(DeleteCommand)"
0x7d4b6  callvirt instance void System.Data.Design.DbSourceCommand::set_Name(string value)
0x7d4bb  ldloc.0
0x7d4bc  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_UpdateCommand()
0x7d4c1  brfalse.s loc_7D4E5
0x7d4c3  ldloc.0
0x7d4c4  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_UpdateCommand()
0x7d4c9  callvirt instance string System.Data.Design.DbSourceCommand::get_Name()
0x7d4ce  call     bool System.Data.Design.StringUtil::EmptyOrSpace(string str)
0x7d4d3  brfalse.s loc_7D4E5
0x7d4d5  ldloc.0
0x7d4d6  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_UpdateCommand()
0x7d4db  ldstr    aUpdatecommand_0// "(UpdateCommand)"
0x7d4e0  callvirt instance void System.Data.Design.DbSourceCommand::set_Name(string value)
0x7d4e5  ldloc.0
0x7d4e6  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_SelectCommand()
0x7d4eb  brfalse.s loc_7D50F
0x7d4ed  ldloc.0
0x7d4ee  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_SelectCommand()
0x7d4f3  callvirt instance string System.Data.Design.DbSourceCommand::get_Name()
0x7d4f8  call     bool System.Data.Design.StringUtil::EmptyOrSpace(string str)
0x7d4fd  brfalse.s loc_7D50F
0x7d4ff  ldloc.0
0x7d500  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_SelectCommand()
0x7d505  ldstr    aSelectcommand_0// "(SelectCommand)"
0x7d50a  callvirt instance void System.Data.Design.DbSourceCommand::set_Name(string value)
0x7d50f  ldloc.0
0x7d510  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_InsertCommand()
0x7d515  brfalse.s loc_7D539
0x7d517  ldloc.0
0x7d518  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_InsertCommand()
0x7d51d  callvirt instance string System.Data.Design.DbSourceCommand::get_Name()
0x7d522  call     bool System.Data.Design.StringUtil::EmptyOrSpace(string str)
0x7d527  brfalse.s loc_7D539
0x7d529  ldloc.0
0x7d52a  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_InsertCommand()
0x7d52f  ldstr    aInsertcommand_0// "(InsertCommand)"
0x7d534  callvirt instance void System.Data.Design.DbSourceCommand::set_Name(string value)
0x7d539  ldloc.0
0x7d53a  ret
```
