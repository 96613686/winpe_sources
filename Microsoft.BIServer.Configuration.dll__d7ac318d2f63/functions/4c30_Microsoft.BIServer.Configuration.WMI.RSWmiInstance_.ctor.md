# Microsoft.BIServer.Configuration.WMI.RSWmiInstance::.ctor

- ea: `0x4c30`
- end: `0x4c8b`
- name: `Microsoft.BIServer.Configuration.WMI.RSWmiInstance::.ctor`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b80`

## callees

- `0x4c30`

## pseudocode

```c

```

## disassembly

```asm
0x4c30  ldarg.0
0x4c31  call     instance void [mscorlib]System.Object::.ctor()
0x4c36  ldarg.0
0x4c37  ldarg.2
0x4c38  stfld    string Microsoft.BIServer.Configuration.WMI.RSWmiInstance::machineName
0x4c3d  ldarg.0
0x4c3e  ldarg.1
0x4c3f  stfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4c44  ldarg.0
0x4c45  ldfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4c4a  callvirt instance class [System.Management]System.Management.ObjectGetOptions [System.Management]System.Management.ManagementObject::get_Options()
0x4c4f  ldc.i4.0
0x4c50  ldc.i4.0
0x4c51  ldc.i4.s 0xA
0x4c53  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x4c58  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x4c5d  ldarg.0
0x4c5e  ldfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4c63  callvirt instance void [System.Management]System.Management.ManagementObject::Get()
0x4c68  leave.s  loc_4C8A
0x4c6a  pop
0x4c6b  ldstr    aRsWmiInstance0// "RS WMI Instance {0} is not available on"...
0x4c70  ldc.i4.2
0x4c71  newarr   [mscorlib]System.Object
0x4c76  dup
0x4c77  ldc.i4.0
0x4c78  ldarg.1
0x4c79  callvirt instance class [System.Management]System.Management.ManagementPath [System.Management]System.Management.ManagementObject::get_Path()
0x4c7e  stelem.ref
0x4c7f  dup
0x4c80  ldc.i4.1
0x4c81  ldarg.2
0x4c82  stelem.ref
0x4c83  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x4c88  leave.s  loc_4C8A
0x4c8a  ret
```
