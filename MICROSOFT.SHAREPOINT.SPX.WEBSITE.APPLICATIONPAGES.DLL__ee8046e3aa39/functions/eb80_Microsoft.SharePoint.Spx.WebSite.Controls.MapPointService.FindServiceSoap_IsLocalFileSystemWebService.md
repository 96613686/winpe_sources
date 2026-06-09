# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::IsLocalFileSystemWebService

- ea: `0xeb80`
- end: `0xebbd`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::IsLocalFileSystemWebService`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe060`
- `0xe0f0`

## callees

- `0xeb80`

## pseudocode

```c

```

## disassembly

```asm
0xeb80  ldarg.1
0xeb81  brfalse.s loc_EB90
0xeb83  ldarg.1
0xeb84  ldsfld   string [mscorlib]System.String::Empty
0xeb89  call     bool [mscorlib]System.String::op_Equality(string, string)
0xeb8e  brfalse.s loc_EB92
0xeb90  ldc.i4.0
0xeb91  ret
0xeb92  ldarg.1
0xeb93  newobj   instance void [System]System.Uri::.ctor(string)
0xeb98  stloc.0
0xeb99  ldloc.0
0xeb9a  callvirt instance int32 [System]System.Uri::get_Port()
0xeb9f  ldc.i4   0x400
0xeba4  blt.s    loc_EBBB
0xeba6  ldloc.0
0xeba7  callvirt instance string [System]System.Uri::get_Host()
0xebac  ldstr    aLocalhost// "localHost"
0xebb1  ldc.i4.5
0xebb2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xebb7  brtrue.s loc_EBBB
0xebb9  ldc.i4.1
0xebba  ret
0xebbb  ldc.i4.0
0xebbc  ret
```
