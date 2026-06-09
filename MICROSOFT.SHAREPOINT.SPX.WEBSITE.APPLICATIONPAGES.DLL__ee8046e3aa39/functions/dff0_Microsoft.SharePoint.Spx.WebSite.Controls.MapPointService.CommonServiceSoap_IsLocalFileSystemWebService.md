# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::IsLocalFileSystemWebService

- ea: `0xdff0`
- end: `0xe02d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::IsLocalFileSystemWebService`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd970`
- `0xda00`

## callees

- `0xdff0`

## pseudocode

```c

```

## disassembly

```asm
0xdff0  ldarg.1
0xdff1  brfalse.s loc_E000
0xdff3  ldarg.1
0xdff4  ldsfld   string [mscorlib]System.String::Empty
0xdff9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdffe  brfalse.s loc_E002
0xe000  ldc.i4.0
0xe001  ret
0xe002  ldarg.1
0xe003  newobj   instance void [System]System.Uri::.ctor(string)
0xe008  stloc.0
0xe009  ldloc.0
0xe00a  callvirt instance int32 [System]System.Uri::get_Port()
0xe00f  ldc.i4   0x400
0xe014  blt.s    loc_E02B
0xe016  ldloc.0
0xe017  callvirt instance string [System]System.Uri::get_Host()
0xe01c  ldstr    aLocalhost// "localHost"
0xe021  ldc.i4.5
0xe022  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xe027  brtrue.s loc_E02B
0xe029  ldc.i4.1
0xe02a  ret
0xe02b  ldc.i4.0
0xe02c  ret
```
