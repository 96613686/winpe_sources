# Microsoft.ReportingServices.Common.HttpResponseUtils::IsViewerRequested

- ea: `0x38bd0`
- end: `0x38c10`
- name: `Microsoft.ReportingServices.Common.HttpResponseUtils::IsViewerRequested`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d7e0`

## callees

- `0x38bd0`

## string_xrefs

- `0x38be0`: `rs:Command`

## pseudocode

```c

```

## disassembly

```asm
0x38bd0  ldarg.0
0x38bd1  ldstr    aRcToolbar// "rc:Toolbar"
0x38bd6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38bdb  stloc.0
0x38bdc  ldloc.0
0x38bdd  brtrue.s loc_38C00
0x38bdf  ldarg.0
0x38be0  ldstr    aRsCommand// "rs:Command"
0x38be5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38bea  stloc.1
0x38beb  ldloc.1
0x38bec  brfalse.s loc_38BFE
0x38bee  ldloc.1
0x38bef  ldstr    aRender// "Render"
0x38bf4  ldc.i4.5
0x38bf5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x38bfa  ldc.i4.0
0x38bfb  ceq
0x38bfd  ret
0x38bfe  ldc.i4.1
0x38bff  ret
0x38c00  ldloc.0
0x38c01  ldsfld   string [mscorlib]System.Boolean::FalseString
0x38c06  ldc.i4.5
0x38c07  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x38c0c  ldc.i4.0
0x38c0d  cgt.un
0x38c0f  ret
```
