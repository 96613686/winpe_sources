# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::GetProperty

- ea: `0xb5c0`
- end: `0xb676`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::GetProperty`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb5c0`

## pseudocode

```c

```

## disassembly

```asm
0xb5c0  ldarg.2
0xb5c1  brtrue.s loc_B5CE
0xb5c3  ldstr    aPropname// "propName"
0xb5c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb5cd  throw
0xb5ce  ldarg.3
0xb5cf  brtrue.s loc_B5DC
0xb5d1  ldstr    aProxycontext// "proxyContext"
0xb5d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb5db  throw
0xb5dc  ldarg.1
0xb5dd  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb5e2  stloc.0
0xb5e3  ldloc.0
0xb5e4  brtrue.s loc_B5F1
0xb5e6  ldstr    aTarget// "target"
0xb5eb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb5f0  throw
0xb5f1  ldarg.0
0xb5f2  ldarg.2
0xb5f3  ldarg.3
0xb5f4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5f9  starg.s  2
0xb5fb  ldarg.2
0xb5fc  dup
0xb5fd  stloc.1
0xb5fe  brfalse.s loc_B66C
0xb600  ldloc.1
0xb601  ldstr    aEnddate// "EndDate"
0xb606  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb60b  brtrue.s loc_B629
0xb60d  ldloc.1
0xb60e  ldstr    aListitem// "ListItem"
0xb613  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb618  brtrue.s loc_B641
0xb61a  ldloc.1
0xb61b  ldstr    aStartdate// "StartDate"
0xb620  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb625  brtrue.s loc_B654
0xb627  br.s     loc_B66C
0xb629  ldarg.0
0xb62a  ldstr    aEnddate// "EndDate"
0xb62f  ldarg.3
0xb630  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb635  ldloc.0
0xb636  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_EndDate()
0xb63b  box      [mscorlib]System.DateTime
0xb640  ret
0xb641  ldarg.0
0xb642  ldstr    aListitem// "ListItem"
0xb647  ldarg.3
0xb648  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb64d  ldloc.0
0xb64e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_ListItem()
0xb653  ret
0xb654  ldarg.0
0xb655  ldstr    aStartdate// "StartDate"
0xb65a  ldarg.3
0xb65b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb660  ldloc.0
0xb661  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_StartDate()
0xb666  box      [mscorlib]System.DateTime
0xb66b  ret
0xb66c  ldarg.0
0xb66d  ldarg.1
0xb66e  ldarg.2
0xb66f  ldarg.3
0xb670  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb675  ret
```
