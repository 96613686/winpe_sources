# Microsoft.BIServer.HostingEnvironment.BIProcess::Update

- ea: `0x580`
- end: `0x5b6`
- name: `Microsoft.BIServer.HostingEnvironment.BIProcess::Update`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x580`
- `0x5c0`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldarg.0
0x581  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcesses()
0x586  ldarg.0
0x587  ldftn    instance bool Microsoft.BIServer.HostingEnvironment.BIProcess::<Update>b__8_0(class [System]System.Diagnostics.Process p)
0x58d  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Diagnostics.Process, bool>::.ctor(object, native int)
0x592  call     T0x2B000003
0x597  ldnull
0x598  cgt.un
0x59a  stfld    bool Microsoft.BIServer.HostingEnvironment.BIProcess::_exists
0x59f  ldarg.0
0x5a0  ldfld    bool Microsoft.BIServer.HostingEnvironment.BIProcess::_exists
0x5a5  brtrue.s loc_5AF
0x5a7  ldarg.0
0x5a8  ldc.i4.0
0x5a9  stfld    bool Microsoft.BIServer.HostingEnvironment.BIProcess::_endpointActive
0x5ae  ret
0x5af  ldarg.0
0x5b0  call     instance void Microsoft.BIServer.HostingEnvironment.BIProcess::GetEndpointResponse()
0x5b5  ret
```
