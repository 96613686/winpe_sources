# Microsoft.Reporting.WebForms.ReportItemPinOperation::WriteObjectToResponse

- ea: `0x23540`
- end: `0x2355f`
- name: `Microsoft.Reporting.WebForms.ReportItemPinOperation::WriteObjectToResponse`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x23590`

## string_xrefs

- `0x2354d`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x23540  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x23545  ldarg.0
0x23546  call     instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x2354b  stloc.0
0x2354c  ldarg.1
0x2354d  ldstr    aApplicationJso// "application/json"
0x23552  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x23557  ldarg.1
0x23558  ldloc.0
0x23559  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2355e  ret
```
