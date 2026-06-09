# Microsoft.BIServer.Configuration.WMI.WmiProvider::TestMachineConnection

- ea: `0x57c0`
- end: `0x581d`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::TestMachineConnection`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5a60`

## callees

- `0x4ea0`
- `0x5700`
- `0x57c0`

## string_xrefs

- `0x5803`: `WMI COM Exceptoin`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57c5  ldstr    a0Root// "\\\\{0}\\root"
0x57ca  ldarg.0
0x57cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x57d0  stloc.0
0x57d1  ldloc.0
0x57d2  call     class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiConnectionOptions()
0x57d7  newobj   instance void [System.Management]System.Management.ManagementScope::.ctor(string, class [System.Management]System.Management.ConnectionOptions)
0x57dc  callvirt instance void [System.Management]System.Management.ManagementScope::Connect()
0x57e1  leave.s  loc_581C
0x57e3  stloc.1
0x57e4  ldloc.1
0x57e5  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x57ea  ldc.i4   0x800706BA
0x57ef  bne.un.s loc_5803
0x57f1  ldstr    aUnableToConnec// "Unable to connect to machine name {0}"
0x57f6  ldarg.0
0x57f7  call     string [mscorlib]System.String::Format(string, object)
0x57fc  ldloc.1
0x57fd  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5802  throw
0x5803  ldstr    aWmiComExceptoi// "WMI COM Exceptoin"
0x5808  ldloc.1
0x5809  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x580e  throw
0x580f  stloc.2
0x5810  ldstr    aException// "Exception"
0x5815  ldloc.2
0x5816  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x581b  throw
0x581c  ret
```
