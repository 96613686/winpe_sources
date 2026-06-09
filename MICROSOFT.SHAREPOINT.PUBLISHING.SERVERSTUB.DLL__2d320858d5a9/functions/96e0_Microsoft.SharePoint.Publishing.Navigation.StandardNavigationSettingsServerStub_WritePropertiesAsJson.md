# Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub::WritePropertiesAsJson

- ea: `0x96e0`
- end: `0x97a3`
- name: `Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub::WritePropertiesAsJson`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96e0`

## pseudocode

```c

```

## disassembly

```asm
0x96e0  ldarg.2
0x96e1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings
0x96e6  stloc.0
0x96e7  ldloc.0
0x96e8  brtrue.s loc_96EB
0x96ea  ret
0x96eb  ldarg.0
0x96ec  ldarg.1
0x96ed  ldarg.2
0x96ee  ldarg.3
0x96ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96f4  ldarg.0
0x96f5  ldstr    aSource// "Source"
0x96fa  ldarg.3
0x96fb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9700  ldarg.1
0x9701  ldstr    aSource// "Source"
0x9706  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x970b  ldarg.3
0x970c  ldstr    aSource// "Source"
0x9711  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x9716  ldarg.1
0x9717  ldloc.0
0x9718  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSource [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_Source()
0x971d  ldarg.3
0x971e  call     T0x2B000023
0x9723  ldarg.3
0x9724  ldstr    aSource// "Source"
0x9729  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x972e  ldarg.0
0x972f  ldstr    aTermsetid// "TermSetId"
0x9734  ldarg.3
0x9735  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x973a  ldarg.1
0x973b  ldstr    aTermsetid// "TermSetId"
0x9740  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x9745  ldarg.3
0x9746  ldstr    aTermsetid// "TermSetId"
0x974b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x9750  ldarg.1
0x9751  ldloc.0
0x9752  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_TermSetId()
0x9757  ldarg.3
0x9758  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x975d  ldarg.3
0x975e  ldstr    aTermsetid// "TermSetId"
0x9763  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x9768  ldarg.0
0x9769  ldstr    aTermstoreid// "TermStoreId"
0x976e  ldarg.3
0x976f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9774  ldarg.1
0x9775  ldstr    aTermstoreid// "TermStoreId"
0x977a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x977f  ldarg.3
0x9780  ldstr    aTermstoreid// "TermStoreId"
0x9785  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x978a  ldarg.1
0x978b  ldloc.0
0x978c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_TermStoreId()
0x9791  ldarg.3
0x9792  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9797  ldarg.3
0x9798  ldstr    aTermstoreid// "TermStoreId"
0x979d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x97a2  ret
```
