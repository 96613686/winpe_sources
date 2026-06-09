# Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::WritePropertiesAsJson

- ea: `0x89370`
- end: `0x897d3`
- name: `Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::WritePropertiesAsJson`
- size: `1123`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x89370`

## string_xrefs

- `0x89385`: `ClientSideComponentId`
- `0x89391`: `ClientSideComponentId`
- `0x8939c`: `ClientSideComponentId`
- `0x893b4`: `ClientSideComponentId`
- `0x893bf`: `ClientSideComponentProperties`
- `0x893cb`: `ClientSideComponentProperties`
- `0x893d6`: `ClientSideComponentProperties`
- `0x893ee`: `ClientSideComponentProperties`
- `0x893f9`: `CommandUIExtension`
- `0x89405`: `CommandUIExtension`
- `0x89410`: `CommandUIExtension`
- `0x89428`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x89370  ldarg.2
0x89371  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction
0x89376  stloc.0
0x89377  ldloc.0
0x89378  brtrue.s loc_8937B
0x8937a  ret
0x8937b  ldarg.0
0x8937c  ldarg.1
0x8937d  ldarg.2
0x8937e  ldarg.3
0x8937f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89384  ldarg.0
0x89385  ldstr    aClientsidecomp// "ClientSideComponentId"
0x8938a  ldarg.3
0x8938b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89390  ldarg.1
0x89391  ldstr    aClientsidecomp// "ClientSideComponentId"
0x89396  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8939b  ldarg.3
0x8939c  ldstr    aClientsidecomp// "ClientSideComponentId"
0x893a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x893a6  ldarg.1
0x893a7  ldloc.0
0x893a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentId()
0x893ad  ldarg.3
0x893ae  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x893b3  ldarg.3
0x893b4  ldstr    aClientsidecomp// "ClientSideComponentId"
0x893b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x893be  ldarg.0
0x893bf  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x893c4  ldarg.3
0x893c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x893ca  ldarg.1
0x893cb  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x893d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x893d5  ldarg.3
0x893d6  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x893db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x893e0  ldarg.1
0x893e1  ldloc.0
0x893e2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentProperties()
0x893e7  ldarg.3
0x893e8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x893ed  ldarg.3
0x893ee  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x893f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x893f8  ldarg.0
0x893f9  ldstr    aCommanduiexten// "CommandUIExtension"
0x893fe  ldarg.3
0x893ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89404  ldarg.1
0x89405  ldstr    aCommanduiexten// "CommandUIExtension"
0x8940a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8940f  ldarg.3
0x89410  ldstr    aCommanduiexten// "CommandUIExtension"
0x89415  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8941a  ldarg.1
0x8941b  ldloc.0
0x8941c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_CommandUIExtension()
0x89421  ldarg.3
0x89422  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89427  ldarg.3
0x89428  ldstr    aCommanduiexten// "CommandUIExtension"
0x8942d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x89432  ldarg.0
0x89433  ldstr    aDescription// "Description"
0x89438  ldarg.3
0x89439  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8943e  ldarg.1
0x8943f  ldstr    aDescription// "Description"
0x89444  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89449  ldarg.3
0x8944a  ldstr    aDescription// "Description"
0x8944f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x89454  ldarg.1
0x89455  ldloc.0
0x89456  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Description()
0x8945b  ldarg.3
0x8945c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89461  ldarg.3
0x89462  ldstr    aDescription// "Description"
0x89467  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8946c  ldarg.0
0x8946d  ldstr    aGroup// "Group"
0x89472  ldarg.3
0x89473  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89478  ldarg.1
0x89479  ldstr    aGroup// "Group"
0x8947e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89483  ldarg.3
0x89484  ldstr    aGroup// "Group"
0x89489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8948e  ldarg.1
0x8948f  ldloc.0
0x89490  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Group()
0x89495  ldarg.3
0x89496  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8949b  ldarg.3
0x8949c  ldstr    aGroup// "Group"
0x894a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x894a6  ldarg.0
0x894a7  ldstr    aId_0// "Id"
0x894ac  ldarg.3
0x894ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x894b2  ldarg.1
0x894b3  ldstr    aId_0// "Id"
0x894b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x894bd  ldarg.3
0x894be  ldstr    aId_0// "Id"
0x894c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x894c8  ldarg.1
0x894c9  ldloc.0
0x894ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Id()
0x894cf  ldarg.3
0x894d0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x894d5  ldarg.3
0x894d6  ldstr    aId_0// "Id"
0x894db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x894e0  ldarg.0
0x894e1  ldstr    aImageurl// "ImageUrl"
0x894e6  ldarg.3
0x894e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x894ec  ldarg.1
0x894ed  ldstr    aImageurl// "ImageUrl"
0x894f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x894f7  ldarg.3
0x894f8  ldstr    aImageurl// "ImageUrl"
0x894fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x89502  ldarg.1
0x89503  ldloc.0
0x89504  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ImageUrl()
0x89509  ldarg.3
0x8950a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8950f  ldarg.3
0x89510  ldstr    aImageurl// "ImageUrl"
0x89515  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8951a  ldarg.0
0x8951b  ldstr    aLocation// "Location"
0x89520  ldarg.3
0x89521  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89526  ldarg.1
0x89527  ldstr    aLocation// "Location"
0x8952c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89531  ldarg.3
0x89532  ldstr    aLocation// "Location"
0x89537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8953c  ldarg.1
0x8953d  ldloc.0
0x8953e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Location()
0x89543  ldarg.3
0x89544  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89549  ldarg.3
0x8954a  ldstr    aLocation// "Location"
0x8954f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x89554  ldarg.0
0x89555  ldstr    aName// "Name"
0x8955a  ldarg.3
0x8955b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89560  ldarg.1
0x89561  ldstr    aName// "Name"
0x89566  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8956b  ldarg.3
0x8956c  ldstr    aName// "Name"
0x89571  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x89576  ldarg.1
0x89577  ldloc.0
0x89578  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Name()
0x8957d  ldarg.3
0x8957e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89583  ldarg.3
0x89584  ldstr    aName// "Name"
0x89589  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8958e  ldarg.0
0x8958f  ldstr    aRegistrationid// "RegistrationId"
0x89594  ldarg.3
0x89595  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8959a  ldarg.1
0x8959b  ldstr    aRegistrationid// "RegistrationId"
0x895a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x895a5  ldarg.3
0x895a6  ldstr    aRegistrationid// "RegistrationId"
0x895ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x895b0  ldarg.1
0x895b1  ldloc.0
0x895b2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_RegistrationId()
0x895b7  ldarg.3
0x895b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x895bd  ldarg.3
0x895be  ldstr    aRegistrationid// "RegistrationId"
0x895c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x895c8  ldarg.0
0x895c9  ldstr    aRegistrationty// "RegistrationType"
0x895ce  ldarg.3
0x895cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x895d4  ldarg.1
0x895d5  ldstr    aRegistrationty// "RegistrationType"
0x895da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x895df  ldarg.3
0x895e0  ldstr    aRegistrationty// "RegistrationType"
0x895e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x895ea  ldarg.1
0x895eb  ldloc.0
0x895ec  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionRegistrationType [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_RegistrationType()
0x895f1  ldarg.3
0x895f2  call     T0x2B000169
0x895f7  ldarg.3
0x895f8  ldstr    aRegistrationty// "RegistrationType"
0x895fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x89602  ldarg.0
0x89603  ldstr    aRights// "Rights"
0x89608  ldarg.3
0x89609  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8960e  ldarg.1
0x8960f  ldstr    aRights// "Rights"
0x89614  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89619  ldarg.3
0x8961a  ldstr    aRights// "Rights"
0x8961f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x89624  ldarg.1
0x89625  ldloc.0
0x89626  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Rights_Client()
0x8962b  ldarg.3
0x8962c  call     T0x2B000029
0x89631  ldarg.3
0x89632  ldstr    aRights// "Rights"
0x89637  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x8963c  ldarg.0
0x8963d  ldstr    aScope// "Scope"
0x89642  ldarg.3
0x89643  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89648  ldarg.1
0x89649  ldstr    aScope// "Scope"
0x8964e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89653  ldarg.3
0x89654  ldstr    aScope// "Scope"
0x89659  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8965e  ldarg.1
0x8965f  ldloc.0
0x89660  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionScope [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Scope()
0x89665  ldarg.3
0x89666  call     T0x2B000222
0x8966b  ldarg.3
0x8966c  ldstr    aScope// "Scope"
0x89671  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x89676  ldarg.0
0x89677  ldstr    aScriptblock// "ScriptBlock"
0x8967c  ldarg.3
0x8967d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89682  ldarg.1
0x89683  ldstr    aScriptblock// "ScriptBlock"
0x89688  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x8968d  ldarg.3
0x8968e  ldstr    aScriptblock// "ScriptBlock"
0x89693  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x89698  ldarg.1
0x89699  ldloc.0
0x8969a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ScriptBlock()
0x8969f  ldarg.3
0x896a0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x896a5  ldarg.3
0x896a6  ldstr    aScriptblock// "ScriptBlock"
0x896ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x896b0  ldarg.0
0x896b1  ldstr    aScriptsrc// "ScriptSrc"
0x896b6  ldarg.3
0x896b7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x896bc  ldarg.1
0x896bd  ldstr    aScriptsrc// "ScriptSrc"
0x896c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x896c7  ldarg.3
0x896c8  ldstr    aScriptsrc// "ScriptSrc"
0x896cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x896d2  ldarg.1
0x896d3  ldloc.0
0x896d4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ScriptSrc()
0x896d9  ldarg.3
0x896da  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x896df  ldarg.3
0x896e0  ldstr    aScriptsrc// "ScriptSrc"
0x896e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x896ea  ldarg.0
0x896eb  ldstr    aSequence// "Sequence"
0x896f0  ldarg.3
0x896f1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x896f6  ldarg.1
0x896f7  ldstr    aSequence// "Sequence"
0x896fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x89701  ldarg.3
0x89702  ldstr    aSequence// "Sequence"
0x89707  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x8970c  ldarg.1
0x8970d  ldloc.0
0x8970e  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Sequence()
0x89713  ldarg.3
0x89714  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89719  ldarg.3
0x8971a  ldstr    aSequence// "Sequence"
0x8971f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x89724  ldarg.0
  ... truncated ...
```
