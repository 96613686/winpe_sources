# Microsoft.BIServer.Configuration.WMI.WmiProvider::EscapeInstanceName

- ea: `0x58d0`
- end: `0x59c5`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::EscapeInstanceName`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5a30`
- `0x5a60`

## callees

- `0x5700`
- `0x58d0`
- `0x59d0`
- `0x5de0`

## pseudocode

```c

```

## disassembly

```asm
0x58d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58d5  ldsfld   string Microsoft.BIServer.Configuration.WMI.WmiProvider::ReportServerPattern
0x58da  ldarg.1
0x58db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x58e0  call     class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiConnectionOptions()
0x58e5  newobj   instance void [System.Management]System.Management.ManagementScope::.ctor(string, class [System.Management]System.Management.ConnectionOptions)
0x58ea  dup
0x58eb  callvirt instance void [System.Management]System.Management.ManagementScope::Connect()
0x58f0  ldstr    aNamespace_0// "__NAMESPACE"
0x58f5  newobj   instance void [System.Management]System.Management.ManagementPath::.ctor(string)
0x58fa  stloc.1
0x58fb  ldloc.1
0x58fc  call     class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiGetOptions()
0x5901  newobj   instance void [System.Management]System.Management.ManagementClass::.ctor(class [System.Management]System.Management.ManagementScope, class [System.Management]System.Management.ManagementPath, class [System.Management]System.Management.ObjectGetOptions)
0x5906  dup
0x5907  callvirt instance void [System.Management]System.Management.ManagementObject::Get()
0x590c  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementClass::GetInstances()
0x5911  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x5916  stloc.2
0x5917  br.s     loc_5957
0x5919  ldloc.2
0x591a  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x591f  castclass [System.Management]System.Management.ManagementObject
0x5924  ldstr    aName// "Name"
0x5929  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x592e  castclass [mscorlib]System.String
0x5933  stloc.3
0x5934  ldloc.3
0x5935  call     string Microsoft.BIServer.Configuration.WMI.WmiProvider::UnEscapeInstanceName(string escapedInstanceName)
0x593a  stloc.s  4
0x593c  ldloc.s  4
0x593e  ldarg.0
0x593f  ldc.i4.5
0x5940  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5945  brfalse.s loc_5957
0x5947  ldloc.s  4
0x5949  ldloc.3
0x594a  ldc.i4.5
0x594b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5950  brfalse.s loc_595F
0x5952  ldarg.0
0x5953  stloc.s  5
0x5955  leave.s  loc_59C2
0x5957  ldloc.2
0x5958  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x595d  brtrue.s loc_5919
0x595f  leave.s  loc_596B
0x5961  ldloc.2
0x5962  brfalse.s loc_596A
0x5964  ldloc.2
0x5965  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x596a  endfinally
0x596b  leave.s  loc_5970
0x596d  pop
0x596e  leave.s  loc_5970
0x5970  ldarg.0
0x5971  stloc.0
0x5972  ldstr    asc_B40A// "_"
0x5977  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x597c  ldloc.0
0x597d  ldstr    a5f// "_5f"
0x5982  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x5987  stloc.0
0x5988  ldstr    asc_B9AC// "\\$"
0x598d  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x5992  ldloc.0
0x5993  ldstr    a24// "_24"
0x5998  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x599d  stloc.0
0x599e  ldstr    asc_B9BA// "\\#"
0x59a3  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x59a8  ldloc.0
0x59a9  ldstr    a23// "_23"
0x59ae  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x59b3  stloc.0
0x59b4  ldstr    aRs// "RS_"
0x59b9  ldloc.0
0x59ba  call     string [mscorlib]System.String::Concat(string, string)
0x59bf  stloc.0
0x59c0  ldloc.0
0x59c1  ret
0x59c2  ldloc.s  5
0x59c4  ret
```
