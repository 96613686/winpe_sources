# Microsoft.SharePoint.ServerStub.SPAttachment_ClientServerStub::WritePropertiesAsJson

- ea: `0x388a0`
- end: `0x3899d`
- name: `Microsoft.SharePoint.ServerStub.SPAttachment_ClientServerStub::WritePropertiesAsJson`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x388a0`

## string_xrefs

- `0x38929`: `ServerRelativePath`
- `0x38935`: `ServerRelativePath`
- `0x38940`: `ServerRelativePath`
- `0x38958`: `ServerRelativePath`
- `0x388ef`: `FileNameAsPath`
- `0x388fb`: `FileNameAsPath`
- `0x38906`: `FileNameAsPath`
- `0x3891e`: `FileNameAsPath`

## pseudocode

```c

```

## disassembly

```asm
0x388a0  ldarg.2
0x388a1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachment_Client
0x388a6  stloc.0
0x388a7  ldloc.0
0x388a8  brtrue.s loc_388AB
0x388aa  ret
0x388ab  ldarg.0
0x388ac  ldarg.1
0x388ad  ldarg.2
0x388ae  ldarg.3
0x388af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x388b4  ldarg.0
0x388b5  ldstr    aFilename_0// "FileName"
0x388ba  ldarg.3
0x388bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x388c0  ldarg.1
0x388c1  ldstr    aFilename_0// "FileName"
0x388c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x388cb  ldarg.3
0x388cc  ldstr    aFilename_0// "FileName"
0x388d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x388d6  ldarg.1
0x388d7  ldloc.0
0x388d8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachment_Client::get_FileName()
0x388dd  ldarg.3
0x388de  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x388e3  ldarg.3
0x388e4  ldstr    aFilename_0// "FileName"
0x388e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x388ee  ldarg.0
0x388ef  ldstr    aFilenameaspath// "FileNameAsPath"
0x388f4  ldarg.3
0x388f5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x388fa  ldarg.1
0x388fb  ldstr    aFilenameaspath// "FileNameAsPath"
0x38900  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x38905  ldarg.3
0x38906  ldstr    aFilenameaspath// "FileNameAsPath"
0x3890b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x38910  ldarg.1
0x38911  ldloc.0
0x38912  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachment_Client::get_FileNameAsPath()
0x38917  ldarg.3
0x38918  call     T0x2B000027
0x3891d  ldarg.3
0x3891e  ldstr    aFilenameaspath// "FileNameAsPath"
0x38923  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x38928  ldarg.0
0x38929  ldstr    aServerrelative_0// "ServerRelativePath"
0x3892e  ldarg.3
0x3892f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38934  ldarg.1
0x38935  ldstr    aServerrelative_0// "ServerRelativePath"
0x3893a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x3893f  ldarg.3
0x38940  ldstr    aServerrelative_0// "ServerRelativePath"
0x38945  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x3894a  ldarg.1
0x3894b  ldloc.0
0x3894c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachment_Client::get_ServerRelativePath()
0x38951  ldarg.3
0x38952  call     T0x2B000027
0x38957  ldarg.3
0x38958  ldstr    aServerrelative_0// "ServerRelativePath"
0x3895d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x38962  ldarg.0
0x38963  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x38968  ldarg.3
0x38969  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3896e  ldarg.1
0x3896f  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x38974  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x38979  ldarg.3
0x3897a  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x3897f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x38984  ldarg.1
0x38985  ldloc.0
0x38986  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachment_Client::get_ServerRelativeUrl()
0x3898b  ldarg.3
0x3898c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x38991  ldarg.3
0x38992  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x38997  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x3899c  ret
```
