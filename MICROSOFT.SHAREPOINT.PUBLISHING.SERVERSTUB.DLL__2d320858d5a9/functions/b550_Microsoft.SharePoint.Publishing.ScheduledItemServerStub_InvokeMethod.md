# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::InvokeMethod

- ea: `0xb550`
- end: `0xb5bb`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::InvokeMethod`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbc20`

## callees

- `0xb530`
- `0xb550`

## pseudocode

```c

```

## disassembly

```asm
0xb550  ldarg.s  4
0xb552  brtrue.s loc_B55F
0xb554  ldstr    aProxycontext// "proxyContext"
0xb559  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb55e  throw
0xb55f  ldarg.1
0xb560  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb565  stloc.0
0xb566  ldloc.0
0xb567  brtrue.s loc_B574
0xb569  ldstr    aTarget// "target"
0xb56e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb573  throw
0xb574  ldarg.0
0xb575  ldarg.2
0xb576  ldarg.s  4
0xb578  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb57d  starg.s  2
0xb57f  ldarg.2
0xb580  dup
0xb581  stloc.1
0xb582  brfalse.s loc_B5AD
0xb584  ldloc.1
0xb585  ldstr    aSchedule// "Schedule"
0xb58a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb58f  brfalse.s loc_B5AD
0xb591  ldarg.s  5
0xb593  ldc.i4.1
0xb594  stind.i1
0xb595  ldarg.0
0xb596  ldstr    aSchedule// "Schedule"
0xb59b  ldarg.s  4
0xb59d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5a2  ldloc.0
0xb5a3  ldarg.3
0xb5a4  ldarg.s  4
0xb5a6  call     void Microsoft.SharePoint.Publishing.ScheduledItemServerStub::Schedule_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5ab  ldnull
0xb5ac  ret
0xb5ad  ldarg.0
0xb5ae  ldarg.1
0xb5af  ldarg.2
0xb5b0  ldarg.3
0xb5b1  ldarg.s  4
0xb5b3  ldarg.s  5
0xb5b5  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xb5ba  ret
```
