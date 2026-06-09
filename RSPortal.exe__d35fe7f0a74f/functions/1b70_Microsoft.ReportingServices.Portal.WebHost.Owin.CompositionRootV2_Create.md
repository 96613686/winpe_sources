# Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::Create

- ea: `0x1b70`
- end: `0x1b89`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::Create`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b70`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldarg.0
0x1b71  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>> Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::_controllerFactoryMap
0x1b76  ldarg.3
0x1b77  ldloca.s 0
0x1b79  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::TryGetValue(var<u1>, !!T0)
0x1b7e  brfalse.s loc_1B87
0x1b80  ldloc.0
0x1b81  callvirt instance var<u1> class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::Invoke()
0x1b86  ret
0x1b87  ldnull
0x1b88  ret
```
