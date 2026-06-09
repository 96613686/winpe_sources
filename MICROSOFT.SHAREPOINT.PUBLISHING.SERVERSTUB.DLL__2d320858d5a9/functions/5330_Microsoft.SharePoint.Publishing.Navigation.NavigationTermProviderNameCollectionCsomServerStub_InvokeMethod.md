# Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::InvokeMethod

- ea: `0x5330`
- end: `0x53f6`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::InvokeMethod`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x52e0`
- `0x5300`
- `0x5310`
- `0x5330`

## string_xrefs

- `0x5382`: `Remove`
- `0x53cd`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x5330  ldarg.s  4
0x5332  brtrue.s loc_533F
0x5334  ldstr    aProxycontext// "proxyContext"
0x5339  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x533e  throw
0x533f  ldarg.1
0x5340  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom
0x5345  stloc.0
0x5346  ldloc.0
0x5347  brtrue.s loc_5354
0x5349  ldstr    aTarget// "target"
0x534e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5353  throw
0x5354  ldarg.0
0x5355  ldarg.2
0x5356  ldarg.s  4
0x5358  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x535d  starg.s  2
0x535f  ldarg.2
0x5360  dup
0x5361  stloc.1
0x5362  brfalse  loc_53E8
0x5367  ldloc.1
0x5368  ldstr    aAdd// "Add"
0x536d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5372  brtrue.s loc_5390
0x5374  ldloc.1
0x5375  ldstr    aClear// "Clear"
0x537a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x537f  brtrue.s loc_53AC
0x5381  ldloc.1
0x5382  ldstr    aRemove// "Remove"
0x5387  call     bool [mscorlib]System.String::op_Equality(string, string)
0x538c  brtrue.s loc_53C8
0x538e  br.s     loc_53E8
0x5390  ldarg.s  5
0x5392  ldc.i4.1
0x5393  stind.i1
0x5394  ldarg.0
0x5395  ldstr    aAdd// "Add"
0x539a  ldarg.s  4
0x539c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x53a1  ldloc.0
0x53a2  ldarg.3
0x53a3  ldarg.s  4
0x53a5  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Add_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x53aa  ldnull
0x53ab  ret
0x53ac  ldarg.s  5
0x53ae  ldc.i4.1
0x53af  stind.i1
0x53b0  ldarg.0
0x53b1  ldstr    aClear// "Clear"
0x53b6  ldarg.s  4
0x53b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x53bd  ldloc.0
0x53be  ldarg.3
0x53bf  ldarg.s  4
0x53c1  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Clear_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x53c6  ldnull
0x53c7  ret
0x53c8  ldarg.s  5
0x53ca  ldc.i4.0
0x53cb  stind.i1
0x53cc  ldarg.0
0x53cd  ldstr    aRemove// "Remove"
0x53d2  ldarg.s  4
0x53d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x53d9  ldloc.0
0x53da  ldarg.3
0x53db  ldarg.s  4
0x53dd  call     bool Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Remove_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x53e2  box      [mscorlib]System.Boolean
0x53e7  ret
0x53e8  ldarg.0
0x53e9  ldarg.1
0x53ea  ldarg.2
0x53eb  ldarg.3
0x53ec  ldarg.s  4
0x53ee  ldarg.s  5
0x53f0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x53f5  ret
```
