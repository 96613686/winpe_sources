# Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::.ctor

- ea: `0x60`
- end: `0x85`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::.ctor`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x860`
- `0x9d0`

## pseudocode

```c

```

## disassembly

```asm
0x60  ldarg.0
0x61  call     instance void [mscorlib]System.Object::.ctor()
0x66  ldarg.0
0x67  ldarg.1
0x68  stfld    class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_configuration
0x6d  ldarg.0
0x6e  ldarg.0
0x6f  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor> Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::InitializeControllerDictionary()
0x75  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>>::.ctor(object, native int)
0x7a  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x7f  stfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpControllerDescriptor>> Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::_controllers
0x84  ret
```
