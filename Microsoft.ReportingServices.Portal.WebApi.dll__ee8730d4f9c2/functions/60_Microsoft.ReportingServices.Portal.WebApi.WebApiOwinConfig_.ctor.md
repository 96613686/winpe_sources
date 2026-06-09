# Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::.ctor

- ea: `0x60`
- end: `0x91`
- name: `Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x60`

## pseudocode

```c

```

## disassembly

```asm
0x60  ldarg.0
0x61  call     instance void [mscorlib]System.Object::.ctor()
0x66  ldarg.1
0x67  brtrue.s loc_74
0x69  ldstr    aDependencyreso// "dependencyResolver"
0x6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73  throw
0x74  ldarg.2
0x75  brtrue.s loc_82
0x77  ldstr    aAssembliesreso// "assembliesResolverFactory"
0x7c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x81  throw
0x82  ldarg.0
0x83  ldarg.1
0x84  stfld    class [System.Web.Http]System.Web.Http.Dependencies.IDependencyResolver Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::_dependencyResolver
0x89  ldarg.0
0x8a  ldarg.2
0x8b  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::_assembliesResolverFactory
0x90  ret
```
