# Microsoft.BIServer.Configuration.WMI.WmiProvider::GetInstanceNames

- ea: `0x5820`
- end: `0x58c3`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::GetInstanceNames`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5a60`

## callees

- `0x4ea0`
- `0x5700`
- `0x5820`
- `0x59d0`
- `0x5de0`

## pseudocode

```c

```

## disassembly

```asm
0x5820  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5825  stloc.0
0x5826  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x582b  ldsfld   string Microsoft.BIServer.Configuration.WMI.WmiProvider::ReportServerPattern
0x5830  ldarg.0
0x5831  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x5836  call     class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiConnectionOptions()
0x583b  newobj   instance void [System.Management]System.Management.ManagementScope::.ctor(string, class [System.Management]System.Management.ConnectionOptions)
0x5840  dup
0x5841  callvirt instance void [System.Management]System.Management.ManagementScope::Connect()
0x5846  ldstr    aNamespace_0// "__NAMESPACE"
0x584b  newobj   instance void [System.Management]System.Management.ManagementPath::.ctor(string)
0x5850  stloc.1
0x5851  ldloc.1
0x5852  call     class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiGetOptions()
0x5857  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(class [System.Management]System.Management.ManagementScope, class [System.Management]System.Management.ManagementPath, class [System.Management]System.Management.ObjectGetOptions)
0x585c  dup
0x585d  callvirt instance void [System.Management]System.Management.ManagementObject::Get()
0x5862  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementClass::GetInstances()
0x5867  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x586c  stloc.2
0x586d  br.s     loc_5896
0x586f  ldloc.2
0x5870  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x5875  castclass [System.Management]System.Management.ManagementObject
0x587a  ldstr    aName// "Name"
0x587f  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x5884  castclass [mscorlib]System.String
0x5889  call     string Microsoft.BIServer.Configuration.WMI.WmiProvider::UnEscapeInstanceName(string escapedInstanceName)
0x588e  stloc.3
0x588f  ldloc.0
0x5890  ldloc.3
0x5891  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5896  ldloc.2
0x5897  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x589c  brtrue.s loc_586F
0x589e  leave.s  loc_58AA
0x58a0  ldloc.2
0x58a1  brfalse.s loc_58A9
0x58a3  ldloc.2
0x58a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58a9  endfinally
0x58aa  leave.s  loc_58C1
0x58ac  stloc.s  4
0x58ae  ldstr    aUnableToConnec_0// "Unable To Connect to machine name "
0x58b3  ldarg.0
0x58b4  call     string [mscorlib]System.String::Concat(string, string)
0x58b9  ldloc.s  4
0x58bb  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x58c0  throw
0x58c1  ldloc.0
0x58c2  ret
```
