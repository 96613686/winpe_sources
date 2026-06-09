# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::set_UseSecureConnection

- ea: `0x13e80`
- end: `0x13eca`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::set_UseSecureConnection`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x13d70`
- `0x13e00`

## callees

- `0x13e80`

## string_xrefs

- `0x13ea8`: `/_vti_bin/ReportServer/ReportService2010.asmx`
- `0x13eba`: `/ReportService2010.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x13e80  ldarg.0
0x13e81  ldarg.1
0x13e82  stfld    bool Microsoft.SqlServer.ReportingServices2010.RSConnection2010::m_useSecureConnection
0x13e87  ldarg.0
0x13e88  ldfld    bool Microsoft.SqlServer.ReportingServices2010.RSConnection2010::m_useSecureConnection
0x13e8d  brtrue.s loc_13E97
0x13e8f  ldarg.0
0x13e90  ldfld    string Microsoft.SqlServer.ReportingServices2010.RSConnection2010::m_nonSecureServerUrl
0x13e95  br.s     loc_13E9D
0x13e97  ldarg.0
0x13e98  ldfld    string Microsoft.SqlServer.ReportingServices2010.RSConnection2010::m_secureServerUrl
0x13e9d  stloc.0
0x13e9e  ldarg.0
0x13e9f  ldfld    bool Microsoft.SqlServer.ReportingServices2010.RSConnection2010::m_useSharePointProxy
0x13ea4  brfalse.s loc_13EB8
0x13ea6  ldarg.0
0x13ea7  ldloc.0
0x13ea8  ldstr    aVtiBinReportse// "/_vti_bin/ReportServer/ReportService201"...
0x13ead  call     string [mscorlib]System.String::Concat(string, string)
0x13eb2  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x13eb7  ret
0x13eb8  ldarg.0
0x13eb9  ldloc.0
0x13eba  ldstr    aReportservice2// "/ReportService2010.asmx"
0x13ebf  call     string [mscorlib]System.String::Concat(string, string)
0x13ec4  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0x13ec9  ret
```
