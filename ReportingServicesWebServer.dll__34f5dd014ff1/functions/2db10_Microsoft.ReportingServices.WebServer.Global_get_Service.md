# Microsoft.ReportingServices.WebServer.Global::get_Service

- ea: `0x2db10`
- end: `0x2db4d`
- name: `Microsoft.ReportingServices.WebServer.Global::get_Service`
- size: `61`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c7b0`
- `0x2d810`
- `0x2da70`
- `0x2df60`
- `0x32980`
- `0x33f40`
- `0x34050`
- `0x343d0`

## callees

- `0x2db10`
- `0x2db50`

## string_xrefs

- `0x2db1a`: `ServiceObject`
- `0x2db40`: `ServiceObject`

## pseudocode

```c

```

## disassembly

```asm
0x2db10  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2db15  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x2db1a  ldstr    aServiceobject// "ServiceObject"
0x2db1f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2db24  castclass [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService
0x2db29  stloc.0
0x2db2a  ldloc.0
0x2db2b  brfalse.s loc_2DB2F
0x2db2d  ldloc.0
0x2db2e  ret
0x2db2f  ldc.i4.1
0x2db30  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.Global::GetRSService(bool checkSharePointAccess)
0x2db35  stloc.0
0x2db36  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2db3b  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x2db40  ldstr    aServiceobject// "ServiceObject"
0x2db45  ldloc.0
0x2db46  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2db4b  ldloc.0
0x2db4c  ret
```
