# Microsoft.SharePoint.ServerStub.SPFieldMultiLineTextServerStub::WritePropertiesAsJson

- ea: `0x54820`
- end: `0x549cb`
- name: `Microsoft.SharePoint.ServerStub.SPFieldMultiLineTextServerStub::WritePropertiesAsJson`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4cb80`
- `0x54820`

## string_xrefs

- `0x54835`: `AllowHyperlink`
- `0x54841`: `AllowHyperlink`
- `0x5484c`: `AllowHyperlink`
- `0x54864`: `AllowHyperlink`
- `0x54991`: `WikiLinking`
- `0x5499d`: `WikiLinking`
- `0x549a8`: `WikiLinking`
- `0x549c0`: `WikiLinking`

## pseudocode

```c

```

## disassembly

```asm
0x54820  ldarg.2
0x54821  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText
0x54826  stloc.0
0x54827  ldloc.0
0x54828  brtrue.s loc_5482B
0x5482a  ret
0x5482b  ldarg.0
0x5482c  ldarg.1
0x5482d  ldarg.2
0x5482e  ldarg.3
0x5482f  call     instance void Microsoft.SharePoint.ServerStub.SPFieldServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x54834  ldarg.0
0x54835  ldstr    aAllowhyperlink// "AllowHyperlink"
0x5483a  ldarg.3
0x5483b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54840  ldarg.1
0x54841  ldstr    aAllowhyperlink// "AllowHyperlink"
0x54846  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5484b  ldarg.3
0x5484c  ldstr    aAllowhyperlink// "AllowHyperlink"
0x54851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x54856  ldarg.1
0x54857  ldloc.0
0x54858  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_AllowHyperlink()
0x5485d  ldarg.3
0x5485e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54863  ldarg.3
0x54864  ldstr    aAllowhyperlink// "AllowHyperlink"
0x54869  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5486e  ldarg.0
0x5486f  ldstr    aAppendonly// "AppendOnly"
0x54874  ldarg.3
0x54875  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5487a  ldarg.1
0x5487b  ldstr    aAppendonly// "AppendOnly"
0x54880  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x54885  ldarg.3
0x54886  ldstr    aAppendonly// "AppendOnly"
0x5488b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x54890  ldarg.1
0x54891  ldloc.0
0x54892  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_AppendOnly()
0x54897  ldarg.3
0x54898  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5489d  ldarg.3
0x5489e  ldstr    aAppendonly// "AppendOnly"
0x548a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x548a8  ldarg.0
0x548a9  ldstr    aNumberoflines// "NumberOfLines"
0x548ae  ldarg.3
0x548af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x548b4  ldarg.1
0x548b5  ldstr    aNumberoflines// "NumberOfLines"
0x548ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x548bf  ldarg.3
0x548c0  ldstr    aNumberoflines// "NumberOfLines"
0x548c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x548ca  ldarg.1
0x548cb  ldloc.0
0x548cc  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_NumberOfLines()
0x548d1  ldarg.3
0x548d2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x548d7  ldarg.3
0x548d8  ldstr    aNumberoflines// "NumberOfLines"
0x548dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x548e2  ldarg.0
0x548e3  ldstr    aRestrictedmode// "RestrictedMode"
0x548e8  ldarg.3
0x548e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x548ee  ldarg.1
0x548ef  ldstr    aRestrictedmode// "RestrictedMode"
0x548f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x548f9  ldarg.3
0x548fa  ldstr    aRestrictedmode// "RestrictedMode"
0x548ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x54904  ldarg.1
0x54905  ldloc.0
0x54906  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_RestrictedMode()
0x5490b  ldarg.3
0x5490c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54911  ldarg.3
0x54912  ldstr    aRestrictedmode// "RestrictedMode"
0x54917  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5491c  ldarg.0
0x5491d  ldstr    aRichtext// "RichText"
0x54922  ldarg.3
0x54923  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54928  ldarg.1
0x54929  ldstr    aRichtext// "RichText"
0x5492e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x54933  ldarg.3
0x54934  ldstr    aRichtext// "RichText"
0x54939  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5493e  ldarg.1
0x5493f  ldloc.0
0x54940  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_RichText()
0x54945  ldarg.3
0x54946  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5494b  ldarg.3
0x5494c  ldstr    aRichtext// "RichText"
0x54951  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x54956  ldarg.0
0x54957  ldstr    aUnlimitedlengt// "UnlimitedLengthInDocumentLibrary"
0x5495c  ldarg.3
0x5495d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54962  ldarg.1
0x54963  ldstr    aUnlimitedlengt// "UnlimitedLengthInDocumentLibrary"
0x54968  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5496d  ldarg.3
0x5496e  ldstr    aUnlimitedlengt// "UnlimitedLengthInDocumentLibrary"
0x54973  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x54978  ldarg.1
0x54979  ldloc.0
0x5497a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_UnlimitedLengthInDocumentLibrary()
0x5497f  ldarg.3
0x54980  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54985  ldarg.3
0x54986  ldstr    aUnlimitedlengt// "UnlimitedLengthInDocumentLibrary"
0x5498b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x54990  ldarg.0
0x54991  ldstr    aWikilinking// "WikiLinking"
0x54996  ldarg.3
0x54997  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5499c  ldarg.1
0x5499d  ldstr    aWikilinking// "WikiLinking"
0x549a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x549a7  ldarg.3
0x549a8  ldstr    aWikilinking// "WikiLinking"
0x549ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x549b2  ldarg.1
0x549b3  ldloc.0
0x549b4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldMultiLineText::get_WikiLinking()
0x549b9  ldarg.3
0x549ba  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x549bf  ldarg.3
0x549c0  ldstr    aWikilinking// "WikiLinking"
0x549c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x549ca  ret
```
