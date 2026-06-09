# <>c__DisplayClass16_0::<Delete>b__0

- ea: `0xf5e0`
- end: `0xf606`
- name: `<>c__DisplayClass16_0::<Delete>b__0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## string_xrefs

- `0xf5e0`: `DELETE '{0}' ({1})`

## pseudocode

```c

```

## disassembly

```asm
0xf5e0  ldstr    aDelete01// "DELETE '{0}' ({1})"
0xf5e5  ldarg.0
0xf5e6  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class <>c__DisplayClass16_0<var<u1>>::<>4__this
0xf5eb  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xf5f0  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0xf5f5  ldarg.0
0xf5f6  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass16_0<var<u1>>::oDataPath
0xf5fb  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xf600  call     string [mscorlib]System.String::Format(string, object, object)
0xf605  ret
```
