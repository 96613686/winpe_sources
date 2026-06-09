# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::IsLocalFileSystemWebService

- ea: `0xf660`
- end: `0xf69d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::IsLocalFileSystemWebService`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xef70`
- `0xf000`

## callees

- `0xf660`

## pseudocode

```c

```

## disassembly

```asm
0xf660  ldarg.1
0xf661  brfalse.s loc_F670
0xf663  ldarg.1
0xf664  ldsfld   string [mscorlib]System.String::Empty
0xf669  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf66e  brfalse.s loc_F672
0xf670  ldc.i4.0
0xf671  ret
0xf672  ldarg.1
0xf673  newobj   instance void [System]System.Uri::.ctor(string)
0xf678  stloc.0
0xf679  ldloc.0
0xf67a  callvirt instance int32 [System]System.Uri::get_Port()
0xf67f  ldc.i4   0x400
0xf684  blt.s    loc_F69B
0xf686  ldloc.0
0xf687  callvirt instance string [System]System.Uri::get_Host()
0xf68c  ldstr    aLocalhost// "localHost"
0xf691  ldc.i4.5
0xf692  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xf697  brtrue.s loc_F69B
0xf699  ldc.i4.1
0xf69a  ret
0xf69b  ldc.i4.0
0xf69c  ret
```
