# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::WritePropertiesAsJson

- ea: `0x8e10`
- end: `0x8ff5`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::WritePropertiesAsJson`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8e10`

## pseudocode

```c

```

## disassembly

```asm
0x8e10  ldarg.2
0x8e11  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView
0x8e16  stloc.0
0x8e17  ldloc.0
0x8e18  brtrue.s loc_8E1B
0x8e1a  ret
0x8e1b  ldarg.0
0x8e1c  ldarg.1
0x8e1d  ldarg.2
0x8e1e  ldarg.3
0x8e1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e24  ldarg.0
0x8e25  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8e2a  ldarg.3
0x8e2b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e30  ldarg.1
0x8e31  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8e36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e3b  ldarg.3
0x8e3c  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8e41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e46  ldarg.1
0x8e47  ldloc.0
0x8e48  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeDeprecatedTerms()
0x8e4d  ldarg.3
0x8e4e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e53  ldarg.3
0x8e54  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8e59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e5e  ldarg.0
0x8e5f  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8e64  ldarg.3
0x8e65  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e6a  ldarg.1
0x8e6b  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8e70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8e75  ldarg.3
0x8e76  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8e7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8e80  ldarg.1
0x8e81  ldloc.0
0x8e82  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeTermsByPermissions()
0x8e87  ldarg.3
0x8e88  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8e8d  ldarg.3
0x8e8e  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8e93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8e98  ldarg.0
0x8e99  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8e9e  ldarg.3
0x8e9f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8ea4  ldarg.1
0x8ea5  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8eaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8eaf  ldarg.3
0x8eb0  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8eb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8eba  ldarg.1
0x8ebb  ldloc.0
0x8ebc  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeTermsByProvider()
0x8ec1  ldarg.3
0x8ec2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8ec7  ldarg.3
0x8ec8  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8ecd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8ed2  ldarg.0
0x8ed3  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8ed8  ldarg.3
0x8ed9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8ede  ldarg.1
0x8edf  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8ee4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8ee9  ldarg.3
0x8eea  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8eef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8ef4  ldarg.1
0x8ef5  ldloc.0
0x8ef6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ServerRelativeSiteUrl()
0x8efb  ldarg.3
0x8efc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f01  ldarg.3
0x8f02  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8f07  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8f0c  ldarg.0
0x8f0d  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8f12  ldarg.3
0x8f13  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f18  ldarg.1
0x8f19  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8f1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8f23  ldarg.3
0x8f24  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8f29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8f2e  ldarg.1
0x8f2f  ldloc.0
0x8f30  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ServerRelativeWebUrl()
0x8f35  ldarg.3
0x8f36  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f3b  ldarg.3
0x8f3c  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8f41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8f46  ldarg.0
0x8f47  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8f4c  ldarg.3
0x8f4d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f52  ldarg.1
0x8f53  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8f58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8f5d  ldarg.3
0x8f5e  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8f63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8f68  ldarg.1
0x8f69  ldloc.0
0x8f6a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_SiteMapProviderName()
0x8f6f  ldarg.3
0x8f70  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f75  ldarg.3
0x8f76  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8f7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8f80  ldarg.0
0x8f81  ldstr    aWebid// "WebId"
0x8f86  ldarg.3
0x8f87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f8c  ldarg.1
0x8f8d  ldstr    aWebid// "WebId"
0x8f92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8f97  ldarg.3
0x8f98  ldstr    aWebid// "WebId"
0x8f9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8fa2  ldarg.1
0x8fa3  ldloc.0
0x8fa4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_WebId()
0x8fa9  ldarg.3
0x8faa  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8faf  ldarg.3
0x8fb0  ldstr    aWebid// "WebId"
0x8fb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8fba  ldarg.0
0x8fbb  ldstr    aWebtitle// "WebTitle"
0x8fc0  ldarg.3
0x8fc1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8fc6  ldarg.1
0x8fc7  ldstr    aWebtitle// "WebTitle"
0x8fcc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8fd1  ldarg.3
0x8fd2  ldstr    aWebtitle// "WebTitle"
0x8fd7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8fdc  ldarg.1
0x8fdd  ldloc.0
0x8fde  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_WebTitle()
0x8fe3  ldarg.3
0x8fe4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8fe9  ldarg.3
0x8fea  ldstr    aWebtitle// "WebTitle"
0x8fef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8ff4  ret
```
