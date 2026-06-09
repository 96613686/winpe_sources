# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetSymmetricKey

- ea: `0x35a0`
- end: `0x35e1`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetSymmetricKey`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## pseudocode

```c

```

## disassembly

```asm
0x35a0  ldloca.s 0
0x35a2  ldarg.0
0x35a3  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetSymmetricKey>d__4::httpClient
0x35a8  ldloca.s 0
0x35aa  ldarg.1
0x35ab  stfld    class [System]System.Uri <GetSymmetricKey>d__4::encryptedSymmetricKeyUrl
0x35b0  ldloca.s 0
0x35b2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]>::Create()
0x35b7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x35bc  ldloca.s 0
0x35be  ldc.i4.m1
0x35bf  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x35c4  ldloc.0
0x35c5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x35ca  stloc.1
0x35cb  ldloca.s 1
0x35cd  ldloca.s 0
0x35cf  call     T0x2B000026
0x35d4  ldloca.s 0
0x35d6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x35db  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]>::get_Task()
0x35e0  ret
```
