# Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetDbState

- ea: `0x6f0`
- end: `0x729`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetDbState`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldloca.s 0
0x6f2  ldarg.0
0x6f3  stfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <GetDbState>d__0::<>4__this
0x6f8  ldloca.s 0
0x6fa  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::Create()
0x6ff  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0x704  ldloca.s 0
0x706  ldc.i4.m1
0x707  stfld    int32 <GetDbState>d__0::<>1__state
0x70c  ldloc.0
0x70d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0x712  stloc.1
0x713  ldloca.s 1
0x715  ldloca.s 0
0x717  call     T0x2B000004
0x71c  ldloca.s 0
0x71e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0x723  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_Task()
0x728  ret
```
