# Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::WritePropertiesAsJson

- ea: `0xa6e60`
- end: `0xa7289`
- name: `Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::WritePropertiesAsJson`
- size: `1065`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa6e60`

## string_xrefs

- `0xa6f97`: `Created`
- `0xa6fa3`: `Created`
- `0xa6fae`: `Created`
- `0xa6fc6`: `Created`
- `0xa6f23`: `AutoStartCreate`
- `0xa6f2f`: `AutoStartCreate`
- `0xa6f3a`: `AutoStartCreate`
- `0xa6f52`: `AutoStartCreate`
- `0xa7215`: `TaskListTitle`
- `0xa7221`: `TaskListTitle`
- `0xa722c`: `TaskListTitle`
- `0xa7244`: `TaskListTitle`

## pseudocode

```c

```

## disassembly

```asm
0xa6e60  ldarg.2
0xa6e61  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation
0xa6e66  stloc.0
0xa6e67  ldloc.0
0xa6e68  brtrue.s loc_A6E6B
0xa6e6a  ret
0xa6e6b  ldarg.0
0xa6e6c  ldarg.1
0xa6e6d  ldarg.2
0xa6e6e  ldarg.3
0xa6e6f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6e74  ldarg.0
0xa6e75  ldstr    aAllowmanual// "AllowManual"
0xa6e7a  ldarg.3
0xa6e7b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6e80  ldarg.1
0xa6e81  ldstr    aAllowmanual// "AllowManual"
0xa6e86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6e8b  ldarg.3
0xa6e8c  ldstr    aAllowmanual// "AllowManual"
0xa6e91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6e96  ldarg.1
0xa6e97  ldloc.0
0xa6e98  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AllowManual()
0xa6e9d  ldarg.3
0xa6e9e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6ea3  ldarg.3
0xa6ea4  ldstr    aAllowmanual// "AllowManual"
0xa6ea9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6eae  ldarg.0
0xa6eaf  ldstr    aAssociationdat// "AssociationData"
0xa6eb4  ldarg.3
0xa6eb5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6eba  ldarg.1
0xa6ebb  ldstr    aAssociationdat// "AssociationData"
0xa6ec0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6ec5  ldarg.3
0xa6ec6  ldstr    aAssociationdat// "AssociationData"
0xa6ecb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6ed0  ldarg.1
0xa6ed1  ldloc.0
0xa6ed2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AssociationData()
0xa6ed7  ldarg.3
0xa6ed8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6edd  ldarg.3
0xa6ede  ldstr    aAssociationdat// "AssociationData"
0xa6ee3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6ee8  ldarg.0
0xa6ee9  ldstr    aAutostartchang// "AutoStartChange"
0xa6eee  ldarg.3
0xa6eef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6ef4  ldarg.1
0xa6ef5  ldstr    aAutostartchang// "AutoStartChange"
0xa6efa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6eff  ldarg.3
0xa6f00  ldstr    aAutostartchang// "AutoStartChange"
0xa6f05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6f0a  ldarg.1
0xa6f0b  ldloc.0
0xa6f0c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartChange()
0xa6f11  ldarg.3
0xa6f12  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6f17  ldarg.3
0xa6f18  ldstr    aAutostartchang// "AutoStartChange"
0xa6f1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6f22  ldarg.0
0xa6f23  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6f28  ldarg.3
0xa6f29  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6f2e  ldarg.1
0xa6f2f  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6f34  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6f39  ldarg.3
0xa6f3a  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6f3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6f44  ldarg.1
0xa6f45  ldloc.0
0xa6f46  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartCreate()
0xa6f4b  ldarg.3
0xa6f4c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6f51  ldarg.3
0xa6f52  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6f57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6f5c  ldarg.0
0xa6f5d  ldstr    aBaseid// "BaseId"
0xa6f62  ldarg.3
0xa6f63  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6f68  ldarg.1
0xa6f69  ldstr    aBaseid// "BaseId"
0xa6f6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6f73  ldarg.3
0xa6f74  ldstr    aBaseid// "BaseId"
0xa6f79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6f7e  ldarg.1
0xa6f7f  ldloc.0
0xa6f80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0xa6f85  ldarg.3
0xa6f86  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6f8b  ldarg.3
0xa6f8c  ldstr    aBaseid// "BaseId"
0xa6f91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6f96  ldarg.0
0xa6f97  ldstr    aCreated// "Created"
0xa6f9c  ldarg.3
0xa6f9d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6fa2  ldarg.1
0xa6fa3  ldstr    aCreated// "Created"
0xa6fa8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6fad  ldarg.3
0xa6fae  ldstr    aCreated// "Created"
0xa6fb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6fb8  ldarg.1
0xa6fb9  ldloc.0
0xa6fba  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Created()
0xa6fbf  ldarg.3
0xa6fc0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6fc5  ldarg.3
0xa6fc6  ldstr    aCreated// "Created"
0xa6fcb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa6fd0  ldarg.0
0xa6fd1  ldstr    aDescription// "Description"
0xa6fd6  ldarg.3
0xa6fd7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6fdc  ldarg.1
0xa6fdd  ldstr    aDescription// "Description"
0xa6fe2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa6fe7  ldarg.3
0xa6fe8  ldstr    aDescription// "Description"
0xa6fed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa6ff2  ldarg.1
0xa6ff3  ldloc.0
0xa6ff4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Description()
0xa6ff9  ldarg.3
0xa6ffa  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6fff  ldarg.3
0xa7000  ldstr    aDescription// "Description"
0xa7005  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa700a  ldarg.0
0xa700b  ldstr    aEnabled_0// "Enabled"
0xa7010  ldarg.3
0xa7011  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7016  ldarg.1
0xa7017  ldstr    aEnabled_0// "Enabled"
0xa701c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa7021  ldarg.3
0xa7022  ldstr    aEnabled_0// "Enabled"
0xa7027  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa702c  ldarg.1
0xa702d  ldloc.0
0xa702e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Enabled()
0xa7033  ldarg.3
0xa7034  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7039  ldarg.3
0xa703a  ldstr    aEnabled_0// "Enabled"
0xa703f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa7044  ldarg.0
0xa7045  ldstr    aHistorylisttit// "HistoryListTitle"
0xa704a  ldarg.3
0xa704b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7050  ldarg.1
0xa7051  ldstr    aHistorylisttit// "HistoryListTitle"
0xa7056  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa705b  ldarg.3
0xa705c  ldstr    aHistorylisttit// "HistoryListTitle"
0xa7061  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa7066  ldarg.1
0xa7067  ldloc.0
0xa7068  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_HistoryListTitle()
0xa706d  ldarg.3
0xa706e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7073  ldarg.3
0xa7074  ldstr    aHistorylisttit// "HistoryListTitle"
0xa7079  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa707e  ldarg.0
0xa707f  ldstr    aId_0// "Id"
0xa7084  ldarg.3
0xa7085  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa708a  ldarg.1
0xa708b  ldstr    aId_0// "Id"
0xa7090  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa7095  ldarg.3
0xa7096  ldstr    aId_0// "Id"
0xa709b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa70a0  ldarg.1
0xa70a1  ldloc.0
0xa70a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Id()
0xa70a7  ldarg.3
0xa70a8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa70ad  ldarg.3
0xa70ae  ldstr    aId_0// "Id"
0xa70b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa70b8  ldarg.0
0xa70b9  ldstr    aInstantiationu// "InstantiationUrl"
0xa70be  ldarg.3
0xa70bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa70c4  ldarg.1
0xa70c5  ldstr    aInstantiationu// "InstantiationUrl"
0xa70ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa70cf  ldarg.3
0xa70d0  ldstr    aInstantiationu// "InstantiationUrl"
0xa70d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa70da  ldarg.1
0xa70db  ldloc.0
0xa70dc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_InstantiationUrl()
0xa70e1  ldarg.3
0xa70e2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa70e7  ldarg.3
0xa70e8  ldstr    aInstantiationu// "InstantiationUrl"
0xa70ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa70f2  ldarg.0
0xa70f3  ldstr    aInternalname// "InternalName"
0xa70f8  ldarg.3
0xa70f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa70fe  ldarg.1
0xa70ff  ldstr    aInternalname// "InternalName"
0xa7104  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa7109  ldarg.3
0xa710a  ldstr    aInternalname// "InternalName"
0xa710f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa7114  ldarg.1
0xa7115  ldloc.0
0xa7116  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_InternalName()
0xa711b  ldarg.3
0xa711c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7121  ldarg.3
0xa7122  ldstr    aInternalname// "InternalName"
0xa7127  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa712c  ldarg.0
0xa712d  ldstr    aIsdeclarative// "IsDeclarative"
0xa7132  ldarg.3
0xa7133  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7138  ldarg.1
0xa7139  ldstr    aIsdeclarative// "IsDeclarative"
0xa713e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa7143  ldarg.3
0xa7144  ldstr    aIsdeclarative// "IsDeclarative"
0xa7149  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa714e  ldarg.1
0xa714f  ldloc.0
0xa7150  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_IsDeclarative()
0xa7155  ldarg.3
0xa7156  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa715b  ldarg.3
0xa715c  ldstr    aIsdeclarative// "IsDeclarative"
0xa7161  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa7166  ldarg.0
0xa7167  ldstr    aListid_0// "ListId"
0xa716c  ldarg.3
0xa716d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7172  ldarg.1
0xa7173  ldstr    aListid_0// "ListId"
0xa7178  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa717d  ldarg.3
0xa717e  ldstr    aListid_0// "ListId"
0xa7183  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa7188  ldarg.1
0xa7189  ldloc.0
0xa718a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_ListId()
0xa718f  ldarg.3
0xa7190  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7195  ldarg.3
0xa7196  ldstr    aListid_0// "ListId"
0xa719b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa71a0  ldarg.0
0xa71a1  ldstr    aModified// "Modified"
0xa71a6  ldarg.3
0xa71a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa71ac  ldarg.1
0xa71ad  ldstr    aModified// "Modified"
0xa71b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa71b7  ldarg.3
0xa71b8  ldstr    aModified// "Modified"
0xa71bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa71c2  ldarg.1
0xa71c3  ldloc.0
0xa71c4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Modified()
0xa71c9  ldarg.3
0xa71ca  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa71cf  ldarg.3
0xa71d0  ldstr    aModified// "Modified"
0xa71d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa71da  ldarg.0
0xa71db  ldstr    aName// "Name"
0xa71e0  ldarg.3
0xa71e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa71e6  ldarg.1
0xa71e7  ldstr    aName// "Name"
0xa71ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa71f1  ldarg.3
0xa71f2  ldstr    aName// "Name"
0xa71f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa71fc  ldarg.1
0xa71fd  ldloc.0
0xa71fe  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0xa7203  ldarg.3
0xa7204  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7209  ldarg.3
0xa720a  ldstr    aName// "Name"
0xa720f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa7214  ldarg.0
  ... truncated ...
```
