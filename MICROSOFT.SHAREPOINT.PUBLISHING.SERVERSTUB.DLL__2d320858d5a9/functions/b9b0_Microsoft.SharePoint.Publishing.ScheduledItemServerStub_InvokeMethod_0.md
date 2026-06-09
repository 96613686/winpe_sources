# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::InvokeMethod_0

- ea: `0xb9b0`
- end: `0xba1b`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::InvokeMethod_0`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbdc0`

## callees

- `0xb990`
- `0xb9b0`

## pseudocode

```c

```

## disassembly

```asm
0xb9b0  ldarg.s  4
0xb9b2  brtrue.s loc_B9BF
0xb9b4  ldstr    aProxycontext// "proxyContext"
0xb9b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb9be  throw
0xb9bf  ldarg.1
0xb9c0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb9c5  stloc.0
0xb9c6  ldloc.0
0xb9c7  brtrue.s loc_B9D4
0xb9c9  ldstr    aTarget// "target"
0xb9ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb9d3  throw
0xb9d4  ldarg.0
0xb9d5  ldarg.2
0xb9d6  ldarg.s  4
0xb9d8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb9dd  starg.s  2
0xb9df  ldarg.2
0xb9e0  dup
0xb9e1  stloc.1
0xb9e2  brfalse.s loc_BA0D
0xb9e4  ldloc.1
0xb9e5  ldstr    aSchedule// "Schedule"
0xb9ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb9ef  brfalse.s loc_BA0D
0xb9f1  ldarg.s  5
0xb9f3  ldc.i4.1
0xb9f4  stind.i1
0xb9f5  ldarg.0
0xb9f6  ldstr    aSchedule// "Schedule"
0xb9fb  ldarg.s  4
0xb9fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xba02  ldloc.0
0xba03  ldarg.3
0xba04  ldarg.s  4
0xba06  call     void Microsoft.SharePoint.Publishing.ScheduledItemServerStub::Schedule_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xba0b  ldnull
0xba0c  ret
0xba0d  ldarg.0
0xba0e  ldarg.1
0xba0f  ldarg.2
0xba10  ldarg.3
0xba11  ldarg.s  4
0xba13  ldarg.s  5
0xba15  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xba1a  ret
```
