# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetCatalogCrypto

- ea: `0x3560`
- end: `0x3599`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetCatalogCrypto`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3560  ldloca.s 0
0x3562  ldarg.0
0x3563  stfld    class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService <GetCatalogCrypto>d__3::<>4__this
0x3568  ldloca.s 0
0x356a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto>::Create()
0x356f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x3574  ldloca.s 0
0x3576  ldc.i4.m1
0x3577  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x357c  ldloc.0
0x357d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x3582  stloc.1
0x3583  ldloca.s 1
0x3585  ldloca.s 0
0x3587  call     T0x2B000025
0x358c  ldloca.s 0
0x358e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x3593  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto>::get_Task()
0x3598  ret
```
