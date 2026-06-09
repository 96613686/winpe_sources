# Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetManagementState

- ea: `0x780`
- end: `0x7b9`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetManagementState`
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
0x780  ldloca.s 0
0x782  ldarg.0
0x783  stfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <GetManagementState>d__2::<>4__this
0x788  ldloca.s 0
0x78a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::Create()
0x78f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0x794  ldloca.s 0
0x796  ldc.i4.m1
0x797  stfld    int32 <GetManagementState>d__2::<>1__state
0x79c  ldloc.0
0x79d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0x7a2  stloc.1
0x7a3  ldloca.s 1
0x7a5  ldloca.s 0
0x7a7  call     T0x2B000005
0x7ac  ldloca.s 0
0x7ae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0x7b3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_Task()
0x7b8  ret
```
