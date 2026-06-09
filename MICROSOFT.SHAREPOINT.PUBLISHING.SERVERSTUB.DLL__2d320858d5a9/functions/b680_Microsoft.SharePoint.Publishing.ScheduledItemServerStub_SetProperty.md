# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::SetProperty

- ea: `0xb680`
- end: `0xb722`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::SetProperty`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb680`

## pseudocode

```c

```

## disassembly

```asm
0xb680  ldarg.s  4
0xb682  brtrue.s loc_B68F
0xb684  ldstr    aProxycontext// "proxyContext"
0xb689  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb68e  throw
0xb68f  ldarg.1
0xb690  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb695  stloc.0
0xb696  ldloc.0
0xb697  brtrue.s loc_B6A4
0xb699  ldstr    aTarget// "target"
0xb69e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb6a3  throw
0xb6a4  ldarg.2
0xb6a5  brtrue.s loc_B6B2
0xb6a7  ldstr    aPropname// "propName"
0xb6ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb6b1  throw
0xb6b2  ldarg.0
0xb6b3  ldarg.2
0xb6b4  ldarg.s  4
0xb6b6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6bb  starg.s  2
0xb6bd  ldarg.2
0xb6be  dup
0xb6bf  stloc.1
0xb6c0  brfalse.s loc_B716
0xb6c2  ldloc.1
0xb6c3  ldstr    aEnddate// "EndDate"
0xb6c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb6cd  brtrue.s loc_B6DE
0xb6cf  ldloc.1
0xb6d0  ldstr    aStartdate// "StartDate"
0xb6d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb6da  brtrue.s loc_B6FA
0xb6dc  br.s     loc_B716
0xb6de  ldarg.0
0xb6df  ldstr    aEnddate// "EndDate"
0xb6e4  ldarg.s  4
0xb6e6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6eb  ldloc.0
0xb6ec  ldarg.3
0xb6ed  ldarg.s  4
0xb6ef  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6f4  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::set_EndDate(valuetype [mscorlib]System.DateTime)
0xb6f9  ret
0xb6fa  ldarg.0
0xb6fb  ldstr    aStartdate// "StartDate"
0xb700  ldarg.s  4
0xb702  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb707  ldloc.0
0xb708  ldarg.3
0xb709  ldarg.s  4
0xb70b  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb710  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::set_StartDate(valuetype [mscorlib]System.DateTime)
0xb715  ret
0xb716  ldarg.0
0xb717  ldarg.1
0xb718  ldarg.2
0xb719  ldarg.3
0xb71a  ldarg.s  4
0xb71c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb721  ret
```
