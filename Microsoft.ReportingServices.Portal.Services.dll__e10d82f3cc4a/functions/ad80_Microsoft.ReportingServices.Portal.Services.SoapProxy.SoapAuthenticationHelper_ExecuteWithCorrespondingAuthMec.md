# Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::ExecuteWithCorrespondingAuthMechanism_0

- ea: `0xad80`
- end: `0xada2`
- name: `Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapAuthenticationHelper::ExecuteWithCorrespondingAuthMechanism_0`
- size: `34`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb260`
- `0xb4d0`
- `0xb510`
- `0xb620`
- `0xb770`
- `0xb7d0`
- `0xb9a0`
- `0xba80`
- `0xbb10`
- `0xbb60`
- `0xbba0`
- `0xbbe0`
- `0xbc30`

## callees

- `0x20ce0`

## pseudocode

```c

```

## disassembly

```asm
0xad80  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xad85  stloc.0
0xad86  ldloc.0
0xad87  ldarg.2
0xad88  stfld    class [mscorlib]System.Action <>c__DisplayClass1_0::action
0xad8d  ldarg.0
0xad8e  ldarg.1
0xad8f  ldloc.0
0xad90  ldftn    instance int32 <>c__DisplayClass1_0::<ExecuteWithCorrespondingAuthMechanism>b__0()
0xad96  newobj   instance void class [mscorlib]System.Func`1<int32>::.ctor(object, native int)
0xad9b  call     T0x2B0000A1
0xada0  pop
0xada1  ret
```
