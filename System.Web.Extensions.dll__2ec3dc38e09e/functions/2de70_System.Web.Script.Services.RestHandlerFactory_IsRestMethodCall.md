# System.Web.Script.Services.RestHandlerFactory::IsRestMethodCall

- ea: `0x2de70`
- end: `0x2dea6`
- name: `System.Web.Script.Services.RestHandlerFactory::IsRestMethodCall`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x141b0`
- `0x2bf90`
- `0x2de50`

## callees

- `0x2de70`

## string_xrefs

- `0x2de96`: `application/json`
- `0x2de83`: `application/json;`

## pseudocode

```c

```

## disassembly

```asm
0x2de70  ldarg.0
0x2de71  callvirt instance string [System.Web]System.Web.HttpRequest::get_PathInfo()
0x2de76  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2de7b  brtrue.s loc_2DEA4
0x2de7d  ldarg.0
0x2de7e  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x2de83  ldstr    aApplicationJso_0// "application/json;"
0x2de88  ldc.i4.5
0x2de89  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2de8e  brtrue.s loc_2DEA2
0x2de90  ldarg.0
0x2de91  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x2de96  ldstr    aApplicationJso// "application/json"
0x2de9b  ldc.i4.5
0x2de9c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2dea1  ret
0x2dea2  ldc.i4.1
0x2dea3  ret
0x2dea4  ldc.i4.0
0x2dea5  ret
```
