# Microsoft.SharePoint.Publishing.VariationsServerStub::InvokeStaticMethod

- ea: `0x13410`
- end: `0x134a6`
- name: `Microsoft.SharePoint.Publishing.VariationsServerStub::InvokeStaticMethod`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x133a0`
- `0x133b0`
- `0x133e0`
- `0x13410`

## string_xrefs

- `0x13448`: `UpdateListItems`
- `0x1348b`: `UpdateListItems`

## pseudocode

```c

```

## disassembly

```asm
0x13410  ldarg.3
0x13411  brtrue.s loc_1341E
0x13413  ldstr    aProxycontext// "proxyContext"
0x13418  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1341d  throw
0x1341e  ldarg.0
0x1341f  ldarg.1
0x13420  ldarg.3
0x13421  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13426  starg.s  1
0x13428  ldarg.1
0x13429  dup
0x1342a  stloc.0
0x1342b  brfalse.s loc_1349F
0x1342d  ldloc.0
0x1342e  ldstr    aGetlabels// "GetLabels"
0x13433  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13438  brtrue.s loc_13456
0x1343a  ldloc.0
0x1343b  ldstr    aGetpeerurl// "GetPeerUrl"
0x13440  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13445  brtrue.s loc_1346E
0x13447  ldloc.0
0x13448  ldstr    aUpdatelistitem// "UpdateListItems"
0x1344d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13452  brtrue.s loc_13486
0x13454  br.s     loc_1349F
0x13456  ldarg.s  4
0x13458  ldc.i4.0
0x13459  stind.i1
0x1345a  ldarg.0
0x1345b  ldstr    aGetlabels// "GetLabels"
0x13460  ldarg.3
0x13461  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13466  ldarg.2
0x13467  ldarg.3
0x13468  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel> Microsoft.SharePoint.Publishing.VariationsServerStub::GetLabels_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1346d  ret
0x1346e  ldarg.s  4
0x13470  ldc.i4.0
0x13471  stind.i1
0x13472  ldarg.0
0x13473  ldstr    aGetpeerurl// "GetPeerUrl"
0x13478  ldarg.3
0x13479  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1347e  ldarg.2
0x1347f  ldarg.3
0x13480  call     string Microsoft.SharePoint.Publishing.VariationsServerStub::GetPeerUrl_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x13485  ret
0x13486  ldarg.s  4
0x13488  ldc.i4.1
0x13489  stind.i1
0x1348a  ldarg.0
0x1348b  ldstr    aUpdatelistitem// "UpdateListItems"
0x13490  ldarg.3
0x13491  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13496  ldarg.2
0x13497  ldarg.3
0x13498  call     void Microsoft.SharePoint.Publishing.VariationsServerStub::UpdateListItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1349d  ldnull
0x1349e  ret
0x1349f  ldarg.1
0x134a0  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x134a5  throw
```
