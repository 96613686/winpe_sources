# Microsoft.SharePoint.ServerStub.SPListServerStub::WritePropertiesAsJson

- ea: `0x6020`
- end: `0x6b89`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::WritePropertiesAsJson`
- size: `2921`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6020`

## string_xrefs

- `0x606f`: `BaseTemplate`
- `0x607b`: `BaseTemplate`
- `0x6086`: `BaseTemplate`
- `0x609e`: `BaseTemplate`
- `0x6157`: `Created`
- `0x6163`: `Created`
- `0x616e`: `Created`
- `0x6186`: `Created`
- `0x6191`: `CurrentChangeToken`
- `0x619d`: `CurrentChangeToken`
- `0x61a8`: `CurrentChangeToken`
- `0x61c0`: `CurrentChangeToken`
- `0x623f`: `DefaultItemOpenUseListSetting`
- `0x624b`: `DefaultItemOpenUseListSetting`
- `0x6256`: `DefaultItemOpenUseListSetting`
- `0x626e`: `DefaultItemOpenUseListSetting`
- `0x62ed`: `DocumentTemplateUrl`
- `0x62f9`: `DocumentTemplateUrl`
- `0x6304`: `DocumentTemplateUrl`
- `0x631c`: `DocumentTemplateUrl`
- `0x6619`: `ImagePath`
- `0x6625`: `ImagePath`
- `0x6630`: `ImagePath`
- `0x6648`: `ImagePath`
- `0x6823`: `LastItemDeletedDate`
- `0x682f`: `LastItemDeletedDate`
- `0x683a`: `LastItemDeletedDate`
- `0x6852`: `LastItemDeletedDate`
- `0x6a2d`: `ParentWebPath`
- `0x6a39`: `ParentWebPath`
- `0x6a44`: `ParentWebPath`
- `0x6a5c`: `ParentWebPath`
- `0x6adb`: `ServerTemplateCanCreateFolders`
- `0x6ae7`: `ServerTemplateCanCreateFolders`
- `0x6af2`: `ServerTemplateCanCreateFolders`
- `0x6b0a`: `ServerTemplateCanCreateFolders`
- `0x6b15`: `TemplateFeatureId`
- `0x6b21`: `TemplateFeatureId`
- `0x6b2c`: `TemplateFeatureId`
- `0x6b44`: `TemplateFeatureId`

## pseudocode

```c

```

## disassembly

```asm
0x6020  ldarg.2
0x6021  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x6026  stloc.0
0x6027  ldloc.0
0x6028  brtrue.s loc_602B
0x602a  ret
0x602b  ldarg.0
0x602c  ldarg.1
0x602d  ldarg.2
0x602e  ldarg.3
0x602f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6034  ldarg.0
0x6035  ldstr    aAllowcontentty// "AllowContentTypes"
0x603a  ldarg.3
0x603b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6040  ldarg.1
0x6041  ldstr    aAllowcontentty// "AllowContentTypes"
0x6046  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x604b  ldarg.3
0x604c  ldstr    aAllowcontentty// "AllowContentTypes"
0x6051  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6056  ldarg.1
0x6057  ldloc.0
0x6058  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_AllowContentTypes()
0x605d  ldarg.3
0x605e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6063  ldarg.3
0x6064  ldstr    aAllowcontentty// "AllowContentTypes"
0x6069  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x606e  ldarg.0
0x606f  ldstr    aBasetemplate// "BaseTemplate"
0x6074  ldarg.3
0x6075  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x607a  ldarg.1
0x607b  ldstr    aBasetemplate// "BaseTemplate"
0x6080  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6085  ldarg.3
0x6086  ldstr    aBasetemplate// "BaseTemplate"
0x608b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6090  ldarg.1
0x6091  ldloc.0
0x6092  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_BaseTemplate_Client()
0x6097  ldarg.3
0x6098  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x609d  ldarg.3
0x609e  ldstr    aBasetemplate// "BaseTemplate"
0x60a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x60a8  ldarg.0
0x60a9  ldstr    aBasetype// "BaseType"
0x60ae  ldarg.3
0x60af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60b4  ldarg.1
0x60b5  ldstr    aBasetype// "BaseType"
0x60ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x60bf  ldarg.3
0x60c0  ldstr    aBasetype// "BaseType"
0x60c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x60ca  ldarg.1
0x60cb  ldloc.0
0x60cc  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseType [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_BaseType()
0x60d1  ldarg.3
0x60d2  call     T0x2B000022
0x60d7  ldarg.3
0x60d8  ldstr    aBasetype// "BaseType"
0x60dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x60e2  ldarg.0
0x60e3  ldstr    aContenttypesen// "ContentTypesEnabled"
0x60e8  ldarg.3
0x60e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60ee  ldarg.1
0x60ef  ldstr    aContenttypesen// "ContentTypesEnabled"
0x60f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x60f9  ldarg.3
0x60fa  ldstr    aContenttypesen// "ContentTypesEnabled"
0x60ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6104  ldarg.1
0x6105  ldloc.0
0x6106  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_ContentTypesEnabled()
0x610b  ldarg.3
0x610c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6111  ldarg.3
0x6112  ldstr    aContenttypesen// "ContentTypesEnabled"
0x6117  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x611c  ldarg.0
0x611d  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x6122  ldarg.3
0x6123  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6128  ldarg.1
0x6129  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x612e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6133  ldarg.3
0x6134  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x6139  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x613e  ldarg.1
0x613f  ldloc.0
0x6140  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_CrawlNonDefaultViews()
0x6145  ldarg.3
0x6146  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x614b  ldarg.3
0x614c  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x6151  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6156  ldarg.0
0x6157  ldstr    aCreated// "Created"
0x615c  ldarg.3
0x615d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6162  ldarg.1
0x6163  ldstr    aCreated// "Created"
0x6168  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x616d  ldarg.3
0x616e  ldstr    aCreated// "Created"
0x6173  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6178  ldarg.1
0x6179  ldloc.0
0x617a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Created()
0x617f  ldarg.3
0x6180  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6185  ldarg.3
0x6186  ldstr    aCreated// "Created"
0x618b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6190  ldarg.0
0x6191  ldstr    aCurrentchanget// "CurrentChangeToken"
0x6196  ldarg.3
0x6197  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x619c  ldarg.1
0x619d  ldstr    aCurrentchanget// "CurrentChangeToken"
0x61a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x61a7  ldarg.3
0x61a8  ldstr    aCurrentchanget// "CurrentChangeToken"
0x61ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x61b2  ldarg.1
0x61b3  ldloc.0
0x61b4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_CurrentChangeToken()
0x61b9  ldarg.3
0x61ba  call     T0x2B000024
0x61bf  ldarg.3
0x61c0  ldstr    aCurrentchanget// "CurrentChangeToken"
0x61c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x61ca  ldarg.0
0x61cb  ldstr    aCustomactionel// "CustomActionElements"
0x61d0  ldarg.3
0x61d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x61d6  ldarg.1
0x61d7  ldstr    aCustomactionel// "CustomActionElements"
0x61dc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x61e1  ldarg.3
0x61e2  ldstr    aCustomactionel// "CustomActionElements"
0x61e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x61ec  ldarg.1
0x61ed  ldloc.0
0x61ee  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomActionElementCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_CustomActionElements()
0x61f3  ldarg.3
0x61f4  call     T0x2B000025
0x61f9  ldarg.3
0x61fa  ldstr    aCustomactionel// "CustomActionElements"
0x61ff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6204  ldarg.0
0x6205  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x620a  ldarg.3
0x620b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6210  ldarg.1
0x6211  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x6216  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x621b  ldarg.3
0x621c  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x6221  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6226  ldarg.1
0x6227  ldloc.0
0x6228  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_DefaultContentApprovalWorkflowId()
0x622d  ldarg.3
0x622e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6233  ldarg.3
0x6234  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x6239  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x623e  ldarg.0
0x623f  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x6244  ldarg.3
0x6245  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x624a  ldarg.1
0x624b  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x6250  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6255  ldarg.3
0x6256  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x625b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6260  ldarg.1
0x6261  ldloc.0
0x6262  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_DefaultItemOpenUseListSetting()
0x6267  ldarg.3
0x6268  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x626d  ldarg.3
0x626e  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x6273  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6278  ldarg.0
0x6279  ldstr    aDescription// "Description"
0x627e  ldarg.3
0x627f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6284  ldarg.1
0x6285  ldstr    aDescription// "Description"
0x628a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x628f  ldarg.3
0x6290  ldstr    aDescription// "Description"
0x6295  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x629a  ldarg.1
0x629b  ldloc.0
0x629c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Description()
0x62a1  ldarg.3
0x62a2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x62a7  ldarg.3
0x62a8  ldstr    aDescription// "Description"
0x62ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x62b2  ldarg.0
0x62b3  ldstr    aDirection// "Direction"
0x62b8  ldarg.3
0x62b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x62be  ldarg.1
0x62bf  ldstr    aDirection// "Direction"
0x62c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x62c9  ldarg.3
0x62ca  ldstr    aDirection// "Direction"
0x62cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x62d4  ldarg.1
0x62d5  ldloc.0
0x62d6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Direction()
0x62db  ldarg.3
0x62dc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x62e1  ldarg.3
0x62e2  ldstr    aDirection// "Direction"
0x62e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x62ec  ldarg.0
0x62ed  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x62f2  ldarg.3
0x62f3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x62f8  ldarg.1
0x62f9  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x62fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6303  ldarg.3
0x6304  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x6309  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x630e  ldarg.1
0x630f  ldloc.0
0x6310  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_DocumentTemplateUrl_Client()
0x6315  ldarg.3
0x6316  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x631b  ldarg.3
0x631c  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x6321  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6326  ldarg.0
0x6327  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x632c  ldarg.3
0x632d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6332  ldarg.1
0x6333  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x6338  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x633d  ldarg.3
0x633e  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x6343  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6348  ldarg.1
0x6349  ldloc.0
0x634a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.DraftVisibilityType [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_DraftVersionVisibility()
0x634f  ldarg.3
0x6350  call     T0x2B000028
0x6355  ldarg.3
0x6356  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x635b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6360  ldarg.0
0x6361  ldstr    aEnableattachme// "EnableAttachments"
0x6366  ldarg.3
0x6367  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x636c  ldarg.1
0x636d  ldstr    aEnableattachme// "EnableAttachments"
0x6372  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6377  ldarg.3
0x6378  ldstr    aEnableattachme// "EnableAttachments"
0x637d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6382  ldarg.1
0x6383  ldloc.0
0x6384  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_EnableAttachments()
0x6389  ldarg.3
0x638a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x638f  ldarg.3
0x6390  ldstr    aEnableattachme// "EnableAttachments"
0x6395  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x639a  ldarg.0
0x639b  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x63a0  ldarg.3
0x63a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63a6  ldarg.1
0x63a7  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x63ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x63b1  ldarg.3
0x63b2  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x63b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x63bc  ldarg.1
0x63bd  ldloc.0
0x63be  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_EnableFolderCreation()
0x63c3  ldarg.3
0x63c4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63c9  ldarg.3
0x63ca  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x63cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x63d4  ldarg.0
  ... truncated ...
```
