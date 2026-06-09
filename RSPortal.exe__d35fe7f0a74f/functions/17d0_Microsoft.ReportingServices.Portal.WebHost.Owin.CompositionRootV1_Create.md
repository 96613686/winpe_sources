# Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::Create

- ea: `0x17d0`
- end: `0x17e9`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::Create`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x17d0`

## pseudocode

```c

```

## disassembly

```asm
0x17d0  ldarg.0
0x17d1  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>> Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::_controllerFactoryMap
0x17d6  ldarg.3
0x17d7  ldloca.s 0
0x17d9  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::TryGetValue(var<u1>, !!T0)
0x17de  brfalse.s loc_17E7
0x17e0  ldloc.0
0x17e1  callvirt instance var<u1> class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::Invoke()
0x17e6  ret
0x17e7  ldnull
0x17e8  ret
```
