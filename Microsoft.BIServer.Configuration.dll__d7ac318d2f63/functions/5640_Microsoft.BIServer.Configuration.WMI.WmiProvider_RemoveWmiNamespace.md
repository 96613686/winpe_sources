# Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespace

- ea: `0x5640`
- end: `0x5700`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespace`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x55e0`

## callees

- `0x5640`

## string_xrefs

- `0x569e`: `Ignoring this exception since there was an attempt to remove an non-existent wmi namespace`
- `0x56ba`: `Namespace {0} was removed.`

## pseudocode

```c

```

## disassembly

```asm
0x5640  ldstr    aNamespace0// "__Namespace=\"{0}\""
0x5645  ldarg.2
0x5646  call     string [mscorlib]System.String::Format(string, object)
0x564b  stloc.0
0x564c  ldnull
0x564d  stloc.1
0x564e  ldarg.1
0x564f  ldloc.0
0x5650  newobj   instance void [System.Management]System.Management.ObjectGetOptions::.ctor()
0x5655  newobj   instance void [System.Management]System.Management.ManagementObject::.ctor(string, string, class [System.Management]System.Management.ObjectGetOptions)
0x565a  stloc.1
0x565b  ldloc.1
0x565c  callvirt instance class [System.Management]System.Management.ManagementPath [System.Management]System.Management.ManagementBaseObject::get_ClassPath()
0x5661  callvirt instance string [System.Management]System.Management.ManagementPath::get_ClassName()
0x5666  pop
0x5667  leave.s  loc_56B1
0x5669  stloc.2
0x566a  ldstr    aManagementExce// "Management exception: {0} encountered."
0x566f  ldc.i4.1
0x5670  newarr   [mscorlib]System.Object
0x5675  dup
0x5676  ldc.i4.0
0x5677  ldloc.2
0x5678  callvirt instance valuetype [System.Management]System.Management.ManagementStatus [System.Management]System.Management.ManagementException::get_ErrorCode()
0x567d  stloc.3
0x567e  ldloca.s 3
0x5680  constrained. [System.Management]System.Management.ManagementStatus
0x5686  callvirt instance string [mscorlib]System.Object::ToString()
0x568b  stelem.ref
0x568c  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5691  ldloc.2
0x5692  callvirt instance valuetype [System.Management]System.Management.ManagementStatus [System.Management]System.Management.ManagementException::get_ErrorCode()
0x5697  ldc.i4   0x80041002
0x569c  bne.un.s loc_56AF
0x569e  ldstr    aIgnoringThisEx// "Ignoring this exception since there was"...
0x56a3  call     T0x2B000015
0x56a8  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x56ad  leave.s  loc_56FF
0x56af  ldloc.2
0x56b0  throw
0x56b1  ldloc.1
0x56b2  brfalse.s loc_56FF
0x56b4  ldloc.1
0x56b5  callvirt instance void [System.Management]System.Management.ManagementObject::Delete()
0x56ba  ldstr    aNamespace0WasR// "Namespace {0} was removed."
0x56bf  ldloc.0
0x56c0  call     string [mscorlib]System.String::Format(string, object)
0x56c5  call     T0x2B000015
0x56ca  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x56cf  leave.s  loc_56FF
0x56d1  stloc.s  4
0x56d3  ldstr    aManagementExce// "Management exception: {0} encountered."
0x56d8  ldloc.s  4
0x56da  callvirt instance valuetype [System.Management]System.Management.ManagementStatus [System.Management]System.Management.ManagementException::get_ErrorCode()
0x56df  stloc.3
0x56e0  ldloca.s 3
0x56e2  constrained. [System.Management]System.Management.ManagementStatus
0x56e8  callvirt instance string [mscorlib]System.Object::ToString()
0x56ed  call     string [mscorlib]System.String::Format(string, object)
0x56f2  call     T0x2B000015
0x56f7  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x56fc  ldloc.s  4
0x56fe  throw
0x56ff  ret
```
