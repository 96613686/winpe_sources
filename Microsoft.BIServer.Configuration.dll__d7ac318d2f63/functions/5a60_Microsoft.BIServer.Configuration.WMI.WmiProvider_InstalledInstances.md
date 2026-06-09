# Microsoft.BIServer.Configuration.WMI.WmiProvider::InstalledInstances

- ea: `0x5a60`
- end: `0x5bb4`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::InstalledInstances`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4b80`
- `0x4ea0`
- `0x57c0`
- `0x5820`
- `0x58d0`
- `0x5a60`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.0
0x5a61  brfalse.s loc_5A6B
0x5a63  ldarg.0
0x5a64  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5a69  brtrue.s loc_5A72
0x5a6b  ldstr    asc_B880// "."
0x5a70  starg.s  0
0x5a72  ldarg.0
0x5a73  call     void Microsoft.BIServer.Configuration.WMI.WmiProvider::TestMachineConnection(string machineName)
0x5a78  ldarg.0
0x5a79  call     class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.BIServer.Configuration.WMI.WmiProvider::GetInstanceNames(string machineName)
0x5a7e  stloc.0
0x5a7f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.WMI.RSWmiInstance>::.ctor()
0x5a84  stloc.1
0x5a85  ldloc.0
0x5a86  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x5a8b  ldc.i4.0
0x5a8c  ble      loc_5BB2
0x5a91  ldnull
0x5a92  stloc.2
0x5a93  newobj   instance void [System.Management]System.Management.ConnectionOptions::.ctor()
0x5a98  stloc.3
0x5a99  ldloc.3
0x5a9a  ldc.i4.6
0x5a9b  callvirt instance void [System.Management]System.Management.ConnectionOptions::set_Authentication(valuetype [System.Management]System.Management.AuthenticationLevel)
0x5aa0  ldloc.3
0x5aa1  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.WMI.WmiProvider::WmiTimeout
0x5aa6  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x5aab  ldc.i4.0
0x5aac  stloc.s  7
0x5aae  br.s     loc_5B22
0x5ab0  ldloc.0
0x5ab1  ldloc.s  7
0x5ab3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x5ab8  ldarg.0
0x5ab9  call     string Microsoft.BIServer.Configuration.WMI.WmiProvider::EscapeInstanceName(string checkName, string machineName)
0x5abe  stloc.s  8
0x5ac0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ac5  ldsfld   string Microsoft.BIServer.Configuration.WMI.WmiProvider::ReportServiceInstancePattern
0x5aca  ldarg.0
0x5acb  ldloc.s  8
0x5acd  ldstr    aV// "v"
0x5ad2  ldc.i4.s 0xD
0x5ad4  stloc.s  0xA
0x5ad6  ldloca.s 0xA
0x5ad8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5add  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5ae2  call     string [mscorlib]System.String::Concat(string, string)
0x5ae7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x5aec  stloc.s  9
0x5aee  ldloc.s  9
0x5af0  ldloc.3
0x5af1  newobj   instance void [System.Management]System.Management.ManagementScope::.ctor(string, class [System.Management]System.Management.ConnectionOptions)
0x5af6  stloc.2
0x5af7  ldloc.2
0x5af8  callvirt instance void [System.Management]System.Management.ManagementScope::Connect()
0x5afd  leave.s  loc_5B2C
0x5aff  stloc.s  0xB
0x5b01  ldloc.s  7
0x5b03  ldloc.0
0x5b04  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x5b09  ldc.i4.1
0x5b0a  sub
0x5b0b  bne.un.s loc_5B1A
0x5b0d  ldstr    aNoReportServer// "No Report Server available"
0x5b12  ldloc.s  0xB
0x5b14  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5b19  throw
0x5b1a  leave.s  loc_5B1C
0x5b1c  ldloc.s  7
0x5b1e  ldc.i4.1
0x5b1f  add
0x5b20  stloc.s  7
0x5b22  ldloc.s  7
0x5b24  ldloc.0
0x5b25  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x5b2a  blt.s    loc_5AB0
0x5b2c  newobj   instance void [System.Management]System.Management.ObjectGetOptions::.ctor()
0x5b31  stloc.s  4
0x5b33  ldloc.s  4
0x5b35  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.WMI.WmiProvider::WmiTimeout
0x5b3a  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x5b3f  ldstr    aMsreportserver// "MSReportServer_Instance"
0x5b44  newobj   instance void [System.Management]System.Management.ManagementPath::.ctor(string)
0x5b49  stloc.s  5
0x5b4b  ldloc.2
0x5b4c  ldloc.s  5
0x5b4e  ldloc.s  4
0x5b50  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(class [System.Management]System.Management.ManagementScope, class [System.Management]System.Management.ManagementPath, class [System.Management]System.Management.ObjectGetOptions)
0x5b55  stloc.s  6
0x5b57  ldloc.s  6
0x5b59  callvirt instance void [System.Management]System.Management.ManagementObject::Get()
0x5b5e  leave.s  loc_5B6F
0x5b60  stloc.s  0xC
0x5b62  ldstr    aExceptionGetti// "Exception getting server class"
0x5b67  ldloc.s  0xC
0x5b69  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5b6e  throw
0x5b6f  ldloc.s  6
0x5b71  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementClass::GetInstances()
0x5b76  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x5b7b  stloc.s  0xD
0x5b7d  br.s     loc_5B9B
0x5b7f  ldloc.s  0xD
0x5b81  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x5b86  castclass [System.Management]System.Management.ManagementObject
0x5b8b  ldarg.0
0x5b8c  newobj   instance void Microsoft.BIServer.Configuration.WMI.RSInstance::.ctor(class [System.Management]System.Management.ManagementObject mo, string machineName)
0x5b91  stloc.s  0xE
0x5b93  ldloc.1
0x5b94  ldloc.s  0xE
0x5b96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.WMI.RSWmiInstance>::Add(var<u1>)
0x5b9b  ldloc.s  0xD
0x5b9d  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x5ba2  brtrue.s loc_5B7F
0x5ba4  leave.s  loc_5BB2
0x5ba6  ldloc.s  0xD
0x5ba8  brfalse.s loc_5BB1
0x5baa  ldloc.s  0xD
0x5bac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bb1  endfinally
0x5bb2  ldloc.1
0x5bb3  ret
```
