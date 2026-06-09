# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::IsLocalFileSystemWebService

- ea: `0xef10`
- end: `0xef4d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::IsLocalFileSystemWebService`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xebd0`
- `0xec60`

## callees

- `0xef10`

## pseudocode

```c

```

## disassembly

```asm
0xef10  ldarg.1
0xef11  brfalse.s loc_EF20
0xef13  ldarg.1
0xef14  ldsfld   string [mscorlib]System.String::Empty
0xef19  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef1e  brfalse.s loc_EF22
0xef20  ldc.i4.0
0xef21  ret
0xef22  ldarg.1
0xef23  newobj   instance void [System]System.Uri::.ctor(string)
0xef28  stloc.0
0xef29  ldloc.0
0xef2a  callvirt instance int32 [System]System.Uri::get_Port()
0xef2f  ldc.i4   0x400
0xef34  blt.s    loc_EF4B
0xef36  ldloc.0
0xef37  callvirt instance string [System]System.Uri::get_Host()
0xef3c  ldstr    aLocalhost// "localHost"
0xef41  ldc.i4.5
0xef42  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xef47  brtrue.s loc_EF4B
0xef49  ldc.i4.1
0xef4a  ret
0xef4b  ldc.i4.0
0xef4c  ret
```
