# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::SetProperty_0

- ea: `0xba20`
- end: `0xbabe`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::SetProperty_0`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xba20`

## pseudocode

```c

```

## disassembly

```asm
0xba20  ldarg.s  4
0xba22  brtrue.s loc_BA2F
0xba24  ldstr    aProxycontext// "proxyContext"
0xba29  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xba2e  throw
0xba2f  ldarg.1
0xba30  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xba35  stloc.0
0xba36  ldloc.0
0xba37  brtrue.s loc_BA44
0xba39  ldstr    aTarget// "target"
0xba3e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xba43  throw
0xba44  ldarg.2
0xba45  brtrue.s loc_BA52
0xba47  ldstr    aPropname// "propName"
0xba4c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xba51  throw
0xba52  ldarg.0
0xba53  ldarg.2
0xba54  ldarg.s  4
0xba56  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xba5b  starg.s  2
0xba5d  ldarg.2
0xba5e  dup
0xba5f  stloc.1
0xba60  brfalse.s loc_BAB2
0xba62  ldloc.1
0xba63  ldstr    aEnddate// "EndDate"
0xba68  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba6d  brtrue.s loc_BA7E
0xba6f  ldloc.1
0xba70  ldstr    aStartdate// "StartDate"
0xba75  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba7a  brtrue.s loc_BA98
0xba7c  br.s     loc_BAB2
0xba7e  ldarg.0
0xba7f  ldstr    aEnddate// "EndDate"
0xba84  ldarg.s  4
0xba86  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xba8b  ldloc.0
0xba8c  ldarg.3
0xba8d  callvirt T0x2B00002B
0xba92  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::set_EndDate(valuetype [mscorlib]System.DateTime)
0xba97  ret
0xba98  ldarg.0
0xba99  ldstr    aStartdate// "StartDate"
0xba9e  ldarg.s  4
0xbaa0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xbaa5  ldloc.0
0xbaa6  ldarg.3
0xbaa7  callvirt T0x2B00002B
0xbaac  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::set_StartDate(valuetype [mscorlib]System.DateTime)
0xbab1  ret
0xbab2  ldarg.0
0xbab3  ldarg.1
0xbab4  ldarg.2
0xbab5  ldarg.3
0xbab6  ldarg.s  4
0xbab8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xbabd  ret
```
