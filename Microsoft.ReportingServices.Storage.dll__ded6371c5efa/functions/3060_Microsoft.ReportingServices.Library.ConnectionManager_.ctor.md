# Microsoft.ReportingServices.Library.ConnectionManager::.ctor

- ea: `0x3060`
- end: `0x30ed`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::.ctor`
- size: `141`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x21c0`
- `0x30f0`
- `0x3130`
- `0x3140`
- `0x3bb0`

## callees

- `0x3010`
- `0x3020`
- `0x3060`
- `0x7b80`

## string_xrefs

- `0x3077`: `\nDECLARE @currVer nvarchar(128), @currMajorVer nvarchar(32), @idx int, @currMajorVerInt tinyint, @cmpt_level tinyint, @altersql nvarchar(128) ;\nSELECT @currVer = CONVERT(nvarchar(128), ServerProperty('ProductVersion')) ;\nSET @idx = CHARINDEX('.', @currVer, 0) ;\nSET @currMajorVer = SUBSTRING(@currVer, 1, @idx-1) ;\nSET @currMajorVerInt = CONVERT(tinyint, @currMajorVer) ;\n\nDECLARE @dbname sysname\nIF @currMajorVerInt =  10\nBEGIN		\n    SELECT @dbname=DB_NAME()\n    SELECT @cmpt_l`

## pseudocode

```c

```

## disassembly

```asm
0x3060  ldarg.0
0x3061  call     valuetype [System.Data]System.Data.IsolationLevel Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x3066  stfld    valuetype [System.Data]System.Data.IsolationLevel Microsoft.ReportingServices.Library.ConnectionManager::_defaultIsolationLevel
0x306b  ldarg.0
0x306c  call     valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultTransactionType()
0x3071  stfld    valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::_transactionType
0x3076  ldarg.0
0x3077  ldstr    aDeclareCurrver// "\r\nDECLARE @currVer nvarchar(128), @cu"...
0x307c  stfld    string Microsoft.ReportingServices.Library.ConnectionManager::dbcmptScriptsTemplate
0x3081  ldarg.0
0x3082  call     instance void [mscorlib]System.Object::.ctor()
0x3087  ldarg.0
0x3088  ldsfld   class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_StaticConfig
0x308d  stfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x3092  ldarg.0
0x3093  ldfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x3098  brtrue.s loc_30EC
0x309a  ldsfld   object Microsoft.ReportingServices.Library.ConnectionManager::_configAccessSync
0x309f  stloc.0
0x30a0  ldc.i4.0
0x30a1  stloc.1
0x30a2  ldloc.0
0x30a3  ldloca.s 1
0x30a5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x30aa  ldarg.0
0x30ab  ldsfld   class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_StaticConfig
0x30b0  stfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x30b5  ldarg.0
0x30b6  ldfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x30bb  brtrue.s loc_30E0
0x30bd  ldsfld   bool Microsoft.ReportingServices.Library.ConnectionManager::_ChangeHandlerSet
0x30c2  brtrue.s loc_30CA
0x30c4  ldc.i4.1
0x30c5  stsfld   bool Microsoft.ReportingServices.Library.ConnectionManager::_ChangeHandlerSet
0x30ca  ldarg.0
0x30cb  newobj   instance void Microsoft.ReportingServices.Library.ConnectionConfig::.ctor()
0x30d0  stfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x30d5  ldarg.0
0x30d6  ldfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x30db  stsfld   class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_StaticConfig
0x30e0  leave.s  loc_30EC
0x30e2  ldloc.1
0x30e3  brfalse.s loc_30EB
0x30e5  ldloc.0
0x30e6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x30eb  endfinally
0x30ec  ret
```
