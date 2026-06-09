# System.Web.DataAccess.SqlExpressConnectionErrorFormatter::get_ErrorTitle

- ea: `0x4c300`
- end: `0x4c33a`
- name: `System.Web.DataAccess.SqlExpressConnectionErrorFormatter::get_ErrorTitle`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x34fa0`
- `0x4c300`

## string_xrefs

- `0x4c31d`: `DataAccessError_CanNotCreateDataDir_Title`
- `0x4c325`: `SqlExpressError_CanNotWriteToDataDir_Title`
- `0x4c32d`: `SqlExpressError_CanNotWriteToDbfFile_Title`

## pseudocode

```c

```

## disassembly

```asm
0x4c300  ldnull
0x4c301  stloc.0
0x4c302  ldarg.0
0x4c303  ldfld    valuetype System.Web.DataAccess.DataConnectionErrorEnum System.Web.DataAccess.DataConnectionErrorFormatter::_Error
0x4c308  stloc.1
0x4c309  ldloc.1
0x4c30a  switch   loc_4C31D, loc_4C325, loc_4C32D
0x4c31b  br.s     loc_4C333
0x4c31d  ldstr    aDataaccesserro_11// "DataAccessError_CanNotCreateDataDir_Tit"...
0x4c322  stloc.0
0x4c323  br.s     loc_4C333
0x4c325  ldstr    aSqlexpresserro// "SqlExpressError_CanNotWriteToDataDir_Ti"...
0x4c32a  stloc.0
0x4c32b  br.s     loc_4C333
0x4c32d  ldstr    aSqlexpresserro_0// "SqlExpressError_CanNotWriteToDbfFile_Ti"...
0x4c332  stloc.0
0x4c333  ldloc.0
0x4c334  call     string System.Web.SR::GetString(string name)
0x4c339  ret
```
