# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::WritePropertiesAsJson

- ea: `0x80c0`
- end: `0x81f7`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::WritePropertiesAsJson`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5d80`
- `0x80c0`

## pseudocode

```c

```

## disassembly

```asm
0x80c0  ldarg.2
0x80c1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x80c6  stloc.0
0x80c7  ldloc.0
0x80c8  brtrue.s loc_80CB
0x80ca  ret
0x80cb  ldarg.0
0x80cc  ldarg.1
0x80cd  ldarg.2
0x80ce  ldarg.3
0x80cf  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x80d4  ldarg.0
0x80d5  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x80da  ldarg.3
0x80db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80e0  ldarg.1
0x80e1  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x80e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x80eb  ldarg.3
0x80ec  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x80f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x80f6  ldarg.1
0x80f7  ldloc.0
0x80f8  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_IsNavigationTermSet()
0x80fd  ldarg.3
0x80fe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8103  ldarg.3
0x8104  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x8109  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x810e  ldarg.0
0x810f  ldstr    aLcid// "Lcid"
0x8114  ldarg.3
0x8115  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x811a  ldarg.1
0x811b  ldstr    aLcid// "Lcid"
0x8120  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8125  ldarg.3
0x8126  ldstr    aLcid// "Lcid"
0x812b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8130  ldarg.1
0x8131  ldloc.0
0x8132  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_Lcid()
0x8137  ldarg.3
0x8138  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x813d  ldarg.3
0x813e  ldstr    aLcid// "Lcid"
0x8143  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8148  ldarg.0
0x8149  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x814e  ldarg.3
0x814f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8154  ldarg.1
0x8155  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x815a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x815f  ldarg.3
0x8160  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x8165  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x816a  ldarg.1
0x816b  ldloc.0
0x816c  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_LoadedFromPersistedData()
0x8171  ldarg.3
0x8172  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8177  ldarg.3
0x8178  ldstr    aLoadedfrompers// "LoadedFromPersistedData"
0x817d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8182  ldarg.0
0x8183  ldstr    aTermgroupid// "TermGroupId"
0x8188  ldarg.3
0x8189  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x818e  ldarg.1
0x818f  ldstr    aTermgroupid// "TermGroupId"
0x8194  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8199  ldarg.3
0x819a  ldstr    aTermgroupid// "TermGroupId"
0x819f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x81a4  ldarg.1
0x81a5  ldloc.0
0x81a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermGroupId()
0x81ab  ldarg.3
0x81ac  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x81b1  ldarg.3
0x81b2  ldstr    aTermgroupid// "TermGroupId"
0x81b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x81bc  ldarg.0
0x81bd  ldstr    aTermstoreid// "TermStoreId"
0x81c2  ldarg.3
0x81c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x81c8  ldarg.1
0x81c9  ldstr    aTermstoreid// "TermStoreId"
0x81ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x81d3  ldarg.3
0x81d4  ldstr    aTermstoreid// "TermStoreId"
0x81d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x81de  ldarg.1
0x81df  ldloc.0
0x81e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::get_TermStoreId()
0x81e5  ldarg.3
0x81e6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x81eb  ldarg.3
0x81ec  ldstr    aTermstoreid// "TermStoreId"
0x81f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x81f6  ret
```
