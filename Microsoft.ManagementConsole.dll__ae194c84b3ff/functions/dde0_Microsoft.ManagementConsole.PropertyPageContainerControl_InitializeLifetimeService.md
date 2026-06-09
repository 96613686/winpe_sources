# Microsoft.ManagementConsole.PropertyPageContainerControl::InitializeLifetimeService

- ea: `0xdde0`
- end: `0xde18`
- name: `Microsoft.ManagementConsole.PropertyPageContainerControl::InitializeLifetimeService`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xdde0`

## pseudocode

```c

```

## disassembly

```asm
0xdde0  ldarg.0
0xdde1  call     instance object [mscorlib]System.MarshalByRefObject::InitializeLifetimeService()
0xdde6  castclass [mscorlib]System.Runtime.Remoting.Lifetime.ILease
0xddeb  stloc.0
0xddec  ldloc.0
0xdded  callvirt instance valuetype [mscorlib]System.Runtime.Remoting.Lifetime.LeaseState [mscorlib]System.Runtime.Remoting.Lifetime.ILease::get_CurrentState()
0xddf2  ldc.i4.1
0xddf3  bne.un.s loc_DE16
0xddf5  ldloc.0
0xddf6  call     valuetype [mscorlib]System.TimeSpan [MMCFxCommon]Microsoft.ManagementConsole.Internal.GlobalConfiguration/SnapInHostingOptions::get_MarshalByRefObjectLeaseTime()
0xddfb  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_InitialLeaseTime(valuetype [mscorlib]System.TimeSpan)
0xde00  ldloc.0
0xde01  call     valuetype [mscorlib]System.TimeSpan [MMCFxCommon]Microsoft.ManagementConsole.Internal.GlobalConfiguration/SnapInHostingOptions::get_MarshalByRefObjectSponsorshipTimeout()
0xde06  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_SponsorshipTimeout(valuetype [mscorlib]System.TimeSpan)
0xde0b  ldloc.0
0xde0c  call     valuetype [mscorlib]System.TimeSpan [MMCFxCommon]Microsoft.ManagementConsole.Internal.GlobalConfiguration/SnapInHostingOptions::get_MarshalByRefObjectRenewOnCallTime()
0xde11  callvirt instance void [mscorlib]System.Runtime.Remoting.Lifetime.ILease::set_RenewOnCallTime(valuetype [mscorlib]System.TimeSpan)
0xde16  ldloc.0
0xde17  ret
```
