# Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::WritePropertiesAsJson

- ea: `0x92270`
- end: `0x92503`
- name: `Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::WritePropertiesAsJson`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x92270`

## string_xrefs

- `0x922bf`: `Created`
- `0x922cb`: `Created`
- `0x922d6`: `Created`
- `0x922ee`: `Created`
- `0x9248f`: `WebTemplate`
- `0x9249b`: `WebTemplate`
- `0x924a6`: `WebTemplate`
- `0x924be`: `WebTemplate`
- `0x92285`: `Configuration`
- `0x92291`: `Configuration`
- `0x9229c`: `Configuration`
- `0x922b4`: `Configuration`
- `0x924c9`: `WebTemplateId`
- `0x924d5`: `WebTemplateId`
- `0x924e0`: `WebTemplateId`
- `0x924f8`: `WebTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x92270  ldarg.2
0x92271  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation
0x92276  stloc.0
0x92277  ldloc.0
0x92278  brtrue.s loc_9227B
0x9227a  ret
0x9227b  ldarg.0
0x9227c  ldarg.1
0x9227d  ldarg.2
0x9227e  ldarg.3
0x9227f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92284  ldarg.0
0x92285  ldstr    aConfiguration// "Configuration"
0x9228a  ldarg.3
0x9228b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92290  ldarg.1
0x92291  ldstr    aConfiguration// "Configuration"
0x92296  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x9229b  ldarg.3
0x9229c  ldstr    aConfiguration// "Configuration"
0x922a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x922a6  ldarg.1
0x922a7  ldloc.0
0x922a8  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Configuration()
0x922ad  ldarg.3
0x922ae  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int16, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x922b3  ldarg.3
0x922b4  ldstr    aConfiguration// "Configuration"
0x922b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x922be  ldarg.0
0x922bf  ldstr    aCreated// "Created"
0x922c4  ldarg.3
0x922c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x922ca  ldarg.1
0x922cb  ldstr    aCreated// "Created"
0x922d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x922d5  ldarg.3
0x922d6  ldstr    aCreated// "Created"
0x922db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x922e0  ldarg.1
0x922e1  ldloc.0
0x922e2  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Created()
0x922e7  ldarg.3
0x922e8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x922ed  ldarg.3
0x922ee  ldstr    aCreated// "Created"
0x922f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x922f8  ldarg.0
0x922f9  ldstr    aDescription// "Description"
0x922fe  ldarg.3
0x922ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92304  ldarg.1
0x92305  ldstr    aDescription// "Description"
0x9230a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x9230f  ldarg.3
0x92310  ldstr    aDescription// "Description"
0x92315  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x9231a  ldarg.1
0x9231b  ldloc.0
0x9231c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Description()
0x92321  ldarg.3
0x92322  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92327  ldarg.3
0x92328  ldstr    aDescription// "Description"
0x9232d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x92332  ldarg.0
0x92333  ldstr    aId_0// "Id"
0x92338  ldarg.3
0x92339  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9233e  ldarg.1
0x9233f  ldstr    aId_0// "Id"
0x92344  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x92349  ldarg.3
0x9234a  ldstr    aId_0// "Id"
0x9234f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x92354  ldarg.1
0x92355  ldloc.0
0x92356  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Id()
0x9235b  ldarg.3
0x9235c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92361  ldarg.3
0x92362  ldstr    aId_0// "Id"
0x92367  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x9236c  ldarg.0
0x9236d  ldstr    aLanguage// "Language"
0x92372  ldarg.3
0x92373  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92378  ldarg.1
0x92379  ldstr    aLanguage// "Language"
0x9237e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x92383  ldarg.3
0x92384  ldstr    aLanguage// "Language"
0x92389  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x9238e  ldarg.1
0x9238f  ldloc.0
0x92390  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Language()
0x92395  ldarg.3
0x92396  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteUInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, unsigned int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9239b  ldarg.3
0x9239c  ldstr    aLanguage// "Language"
0x923a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x923a6  ldarg.0
0x923a7  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x923ac  ldarg.3
0x923ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x923b2  ldarg.1
0x923b3  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x923b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x923bd  ldarg.3
0x923be  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x923c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x923c8  ldarg.1
0x923c9  ldloc.0
0x923ca  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemModifiedDate()
0x923cf  ldarg.3
0x923d0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x923d5  ldarg.3
0x923d6  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x923db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x923e0  ldarg.0
0x923e1  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x923e6  ldarg.3
0x923e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x923ec  ldarg.1
0x923ed  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x923f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x923f7  ldarg.3
0x923f8  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x923fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x92402  ldarg.1
0x92403  ldloc.0
0x92404  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemUserModifiedDate()
0x92409  ldarg.3
0x9240a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9240f  ldarg.3
0x92410  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x92415  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x9241a  ldarg.0
0x9241b  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x92420  ldarg.3
0x92421  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92426  ldarg.1
0x92427  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x9242c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x92431  ldarg.3
0x92432  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x92437  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x9243c  ldarg.1
0x9243d  ldloc.0
0x9243e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_ServerRelativeUrl()
0x92443  ldarg.3
0x92444  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92449  ldarg.3
0x9244a  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x9244f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x92454  ldarg.0
0x92455  ldstr    aTitle// "Title"
0x9245a  ldarg.3
0x9245b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92460  ldarg.1
0x92461  ldstr    aTitle// "Title"
0x92466  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x9246b  ldarg.3
0x9246c  ldstr    aTitle// "Title"
0x92471  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x92476  ldarg.1
0x92477  ldloc.0
0x92478  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Title()
0x9247d  ldarg.3
0x9247e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92483  ldarg.3
0x92484  ldstr    aTitle// "Title"
0x92489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x9248e  ldarg.0
0x9248f  ldstr    aWebtemplate// "WebTemplate"
0x92494  ldarg.3
0x92495  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9249a  ldarg.1
0x9249b  ldstr    aWebtemplate// "WebTemplate"
0x924a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x924a5  ldarg.3
0x924a6  ldstr    aWebtemplate// "WebTemplate"
0x924ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x924b0  ldarg.1
0x924b1  ldloc.0
0x924b2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_WebTemplate()
0x924b7  ldarg.3
0x924b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x924bd  ldarg.3
0x924be  ldstr    aWebtemplate// "WebTemplate"
0x924c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x924c8  ldarg.0
0x924c9  ldstr    aWebtemplateid// "WebTemplateId"
0x924ce  ldarg.3
0x924cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x924d4  ldarg.1
0x924d5  ldstr    aWebtemplateid// "WebTemplateId"
0x924da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x924df  ldarg.3
0x924e0  ldstr    aWebtemplateid// "WebTemplateId"
0x924e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x924ea  ldarg.1
0x924eb  ldloc.0
0x924ec  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_WebTemplateId()
0x924f1  ldarg.3
0x924f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x924f7  ldarg.3
0x924f8  ldstr    aWebtemplateid// "WebTemplateId"
0x924fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x92502  ret
```
