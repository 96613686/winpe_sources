# System.Web.DataAccess.SqlExpressConnectionErrorFormatter::get_Description

- ea: `0x4c340`
- end: `0x4c3cb`
- name: `System.Web.DataAccess.SqlExpressConnectionErrorFormatter::get_Description`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x34f20`
- `0x34fa0`
- `0x4c340`

## string_xrefs

- `0x4c35f`: `DataAccessError_CanNotCreateDataDir_Description`
- `0x4c365`: `DataAccessError_CanNotCreateDataDir_Description_2`
- `0x4c36d`: `SqlExpressError_CanNotWriteToDataDir_Description`
- `0x4c373`: `SqlExpressError_CanNotWriteToDataDir_Description_2`
- `0x4c37b`: `SqlExpressError_CanNotWriteToDbfFile_Description`
- `0x4c381`: `SqlExpressError_CanNotWriteToDbfFile_Description_2`

## pseudocode

```c

```

## disassembly

```asm
0x4c340  ldnull
0x4c341  stloc.0
0x4c342  ldnull
0x4c343  stloc.1
0x4c344  ldarg.0
0x4c345  ldfld    valuetype System.Web.DataAccess.DataConnectionErrorEnum System.Web.DataAccess.DataConnectionErrorFormatter::_Error
0x4c34a  stloc.3
0x4c34b  ldloc.3
0x4c34c  switch   loc_4C35F, loc_4C36D, loc_4C37B
0x4c35d  br.s     loc_4C387
0x4c35f  ldstr    aDataaccesserro_12// "DataAccessError_CanNotCreateDataDir_Des"...
0x4c364  stloc.0
0x4c365  ldstr    aDataaccesserro_13// "DataAccessError_CanNotCreateDataDir_Des"...
0x4c36a  stloc.1
0x4c36b  br.s     loc_4C387
0x4c36d  ldstr    aSqlexpresserro_1// "SqlExpressError_CanNotWriteToDataDir_De"...
0x4c372  stloc.0
0x4c373  ldstr    aSqlexpresserro_2// "SqlExpressError_CanNotWriteToDataDir_De"...
0x4c378  stloc.1
0x4c379  br.s     loc_4C387
0x4c37b  ldstr    aSqlexpresserro_3// "SqlExpressError_CanNotWriteToDbfFile_De"...
0x4c380  stloc.0
0x4c381  ldstr    aSqlexpresserro_4// "SqlExpressError_CanNotWriteToDbfFile_De"...
0x4c386  stloc.1
0x4c387  ldarg.0
0x4c388  ldfld    string System.Web.DataAccess.DataConnectionErrorFormatter::_UserName
0x4c38d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4c392  brtrue.s loc_4C3AC
0x4c394  ldloc.0
0x4c395  ldc.i4.1
0x4c396  newarr   [mscorlib]System.Object
0x4c39b  dup
0x4c39c  ldc.i4.0
0x4c39d  ldarg.0
0x4c39e  ldfld    string System.Web.DataAccess.DataConnectionErrorFormatter::_UserName
0x4c3a3  stelem.ref
0x4c3a4  call     string System.Web.SR::GetString(string name, object[] args)
0x4c3a9  stloc.2
0x4c3aa  br.s     loc_4C3B3
0x4c3ac  ldloc.1
0x4c3ad  call     string System.Web.SR::GetString(string name)
0x4c3b2  stloc.2
0x4c3b3  ldloc.2
0x4c3b4  ldstr    asc_1B0CBE// " "
0x4c3b9  ldstr    aSqlexpresserro_5// "SqlExpressError_Description_1"
0x4c3be  call     string System.Web.SR::GetString(string name)
0x4c3c3  call     string [mscorlib]System.String::Concat(string, string, string)
0x4c3c8  stloc.2
0x4c3c9  ldloc.2
0x4c3ca  ret
```
