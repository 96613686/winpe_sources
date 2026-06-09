# Microsoft.BIServer.Configuration.RsCatalog::ExecuteScript

- ea: `0x2c60`
- end: `0x2cec`
- name: `Microsoft.BIServer.Configuration.RsCatalog::ExecuteScript`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c20`

## callees

- `0x2d30`

## string_xrefs

- `0x2c6e`: `TempDB`
- `0x2c96`: `N'ReportServerTempDB'`
- `0x2cc9`: `[ReportServerTempDB]`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.0
0x2c61  ldarg.1
0x2c62  call     instance string Microsoft.BIServer.Configuration.RsCatalog::GetCatalogScriptContents(string fileName)
0x2c67  stloc.0
0x2c68  ldarg.0
0x2c69  ldfld    string Microsoft.BIServer.Configuration.RsCatalog::_reportServerDatabaseName
0x2c6e  ldstr    aTempdb// "TempDB"
0x2c73  call     string [mscorlib]System.String::Concat(string, string)
0x2c78  stloc.1
0x2c79  ldloc.0
0x2c7a  ldstr    aNReportserver// "N'ReportServer'"
0x2c7f  ldstr    aN0// "N'{0}'"
0x2c84  ldarg.0
0x2c85  ldfld    string Microsoft.BIServer.Configuration.RsCatalog::_reportServerDatabaseName
0x2c8a  call     string [mscorlib]System.String::Format(string, object)
0x2c8f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2c94  stloc.0
0x2c95  ldloc.0
0x2c96  ldstr    aNReportservert// "N'ReportServerTempDB'"
0x2c9b  ldstr    aN0// "N'{0}'"
0x2ca0  ldloc.1
0x2ca1  call     string [mscorlib]System.String::Format(string, object)
0x2ca6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2cab  stloc.0
0x2cac  ldloc.0
0x2cad  ldstr    aReportserver_0// "[ReportServer]"
0x2cb2  ldstr    a0_0// "[{0}]"
0x2cb7  ldarg.0
0x2cb8  ldfld    string Microsoft.BIServer.Configuration.RsCatalog::_reportServerDatabaseName
0x2cbd  call     string [mscorlib]System.String::Format(string, object)
0x2cc2  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2cc7  stloc.0
0x2cc8  ldloc.0
0x2cc9  ldstr    aReportserverte// "[ReportServerTempDB]"
0x2cce  ldstr    a0_0// "[{0}]"
0x2cd3  ldloc.1
0x2cd4  call     string [mscorlib]System.String::Format(string, object)
0x2cd9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2cde  stloc.0
0x2cdf  ldarg.0
0x2ce0  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.RsCatalog::_conn
0x2ce5  ldloc.0
0x2ce6  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteBatchScript(string)
0x2ceb  ret
```
