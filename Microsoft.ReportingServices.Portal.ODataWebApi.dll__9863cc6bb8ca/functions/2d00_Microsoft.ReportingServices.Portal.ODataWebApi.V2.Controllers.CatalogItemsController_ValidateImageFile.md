# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidateImageFile

- ea: `0x2d00`
- end: `0x2d72`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidateImageFile`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2cb0`

## callees

- `0x730`
- `0x2d00`

## pseudocode

```c

```

## disassembly

```asm
0x2d00  ldarg.1
0x2d01  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x2d06  stloc.0
0x2d07  ldloc.0
0x2d08  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x2d0d  stloc.2
0x2d0e  ldloc.2
0x2d0f  call     class [System.Drawing]System.Drawing.Image [System.Drawing]System.Drawing.Image::FromStream(class [mscorlib]System.IO.Stream)
0x2d14  pop
0x2d15  leave.s  loc_2D21
0x2d17  ldloc.2
0x2d18  brfalse.s loc_2D20
0x2d1a  ldloc.2
0x2d1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d20  endfinally
0x2d21  leave.s  loc_2D31
0x2d23  pop
0x2d24  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotValidImageException()
0x2d29  ldc.i4.s 0x66
0x2d2b  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0x2d30  throw
0x2d31  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x2d36  ldloc.0
0x2d37  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x2d3c  stloc.1
0x2d3d  ldloc.1
0x2d3e  ldstr    aScript// "<script"
0x2d43  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d48  brtrue.s loc_2D64
0x2d4a  ldloc.1
0x2d4b  ldstr    aJavascript// "javascript:"
0x2d50  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d55  brtrue.s loc_2D64
0x2d57  ldloc.1
0x2d58  ldstr    aVbscript// "vbscript:"
0x2d5d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d62  brfalse.s loc_2D71
0x2d64  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotValidImageException()
0x2d69  ldc.i4.s 0x66
0x2d6b  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0x2d70  throw
0x2d71  ret
```
