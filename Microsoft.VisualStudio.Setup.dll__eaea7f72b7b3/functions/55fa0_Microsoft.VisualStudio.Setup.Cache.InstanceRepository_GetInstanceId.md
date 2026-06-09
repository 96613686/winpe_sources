# Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetInstanceId

- ea: `0x55fa0`
- end: `0x56021`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetInstanceId`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x55c20`
- `0x55d40`
- `0x55db0`

## callees

- `0x55fa0`
- `0x561d0`

## string_xrefs

- `0x55fcc`: `The maximum number of attempts to create an instance identifier has been exceeded.`
- `0x55fe3`: `Instance directory name "`
- `0x55fe9`: `" already exists; getting another.`

## pseudocode

```c

```

## disassembly

```asm
0x55fa0  ldarg.0
0x55fa1  ldfld    string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::instanceId
0x55fa6  brtrue.s loc_5601A
0x55fa8  ldsfld   object Microsoft.VisualStudio.Setup.Cache.InstanceRepository::SyncRoot
0x55fad  stloc.0
0x55fae  ldc.i4.0
0x55faf  stloc.1
0x55fb0  ldloc.0
0x55fb1  ldloca.s 1
0x55fb3  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x55fb8  ldarg.0
0x55fb9  ldfld    string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::instanceId
0x55fbe  brtrue.s loc_5600E
0x55fc0  ldc.i4.5
0x55fc1  stloc.3
0x55fc2  br.s     loc_55FFD
0x55fc4  ldloc.3
0x55fc5  ldc.i4.1
0x55fc6  sub
0x55fc7  dup
0x55fc8  stloc.3
0x55fc9  ldc.i4.0
0x55fca  bgt.s    loc_55FD7
0x55fcc  ldstr    aTheMaximumNumb// "The maximum number of attempts to creat"...
0x55fd1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x55fd6  throw
0x55fd7  ldarg.0
0x55fd8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.InstanceRepository::logger
0x55fdd  dup
0x55fde  brtrue.s loc_55FE3
0x55fe0  pop
0x55fe1  br.s     loc_55FFD
0x55fe3  ldstr    aInstanceDirect// "Instance directory name \""
0x55fe8  ldloc.2
0x55fe9  ldstr    aAlreadyExistsG// "\" already exists; getting another."
0x55fee  call     string [mscorlib]System.String::Concat(string, string, string)
0x55ff3  call     T0x2B000003
0x55ff8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x55ffd  ldarg.0
0x55ffe  ldloca.s 2
0x56000  call     instance bool Microsoft.VisualStudio.Setup.Cache.InstanceRepository::TryGetUniqueDirectory([out] string& name)
0x56005  brfalse.s loc_55FC4
0x56007  ldarg.0
0x56008  ldloc.2
0x56009  stfld    string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::instanceId
0x5600e  leave.s  loc_5601A
0x56010  ldloc.1
0x56011  brfalse.s loc_56019
0x56013  ldloc.0
0x56014  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x56019  endfinally
0x5601a  ldarg.0
0x5601b  ldfld    string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::instanceId
0x56020  ret
```
