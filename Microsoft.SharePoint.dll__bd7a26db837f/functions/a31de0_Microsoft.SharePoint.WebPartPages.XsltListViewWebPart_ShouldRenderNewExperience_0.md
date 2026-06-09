# Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::ShouldRenderNewExperience_0

- ea: `0xa31de0`
- end: `0xa3250b`
- name: `Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::ShouldRenderNewExperience_0`
- size: `1835`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `service_task, broker_com_uri`

## callers

- `0x512f20`
- `0xa31dd0`

## callees

- `0x3192a0`
- `0x342e60`
- `0x343930`
- `0x344c40`
- `0x3cd1a0`
- `0x4cd8e0`
- `0x4cddc0`
- `0x4ce110`
- `0x4f1170`
- `0x5bbb50`
- `0x5c0230`
- `0x5c0250`
- `0x5c0b10`
- `0x5c5830`
- `0x5ce130`
- `0x678580`
- `0x6785e0`
- `0x6c9890`
- `0x7bea40`
- `0x93dab0`
- `0x93dae0`
- `0x957470`
- `0x96ac70`
- `0x96f0f0`
- `0x96f590`
- `0x97c150`
- `0xa2ae60`
- `0xa2ae80`
- `0xa2af50`
- `0xa2af70`
- `0xa2af90`
- `0xa2e170`
- `0xa31dc0`
- `0xa31de0`

## string_xrefs

- `0xa31e2b`: `WebTemplateId`
- `0xa31e61`: `WebTemplateId`
- `0xa31ed8`: `clienttemplates.js`
- `0xa31e0b`: `ListTemplate`
- `0xa31e51`: `ListTemplate`
- `0xa31f1a`: `ListView_JSLinkCustomized`
- `0xa31f3a`: `ListView_JSLinkCustomized`
- `0xa31f48`: `SPListNext - OFF because XLV has JSLink or XSL/XSLLink `
- `0xa31f71`: `SPListNext - OFF because XLV has JSLink or XSL/XSLLink, {0}`
- `0xa32180`: `SPListNext - OFF because XLV has JSLink in one of the field definitions.`
- `0xa321a3`: `SPListNext - OFF because XLV has JSLink in one of the fields definitions`
- `0xa321b6`: `ListView_HasJSLinkInLink`
- `0xa3225c`: `SPListNext - OFF because viwe has TaskOutcome Field`
- `0xa3227f`: `SPListNext - OFF because view has TaskOutcome Field`
- `0xa32292`: `ListView_HasTaskOutcomeField`

## pseudocode

```c

```

## disassembly

```asm
0xa31de0  ldnull
0xa31de1  stloc.0
0xa31de2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::ClassicVsModern
0xa31de7  ldstr    a12122016// "12/12/2016"
0xa31dec  ldstr    aInstrumentatio// "Instrumentation for classic versus mode"...
0xa31df1  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xa31df6  brtrue.s loc_A31E70
0xa31df8  ldarg.s  4
0xa31dfa  brtrue.s loc_A31E70
0xa31dfc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xa31e01  stloc.0
0xa31e02  ldarg.0
0xa31e03  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.DataFormWebPart::_splist
0xa31e08  brfalse.s loc_A31E50
0xa31e0a  ldloc.0
0xa31e0b  ldstr    aListtemplate_0// "ListTemplate"
0xa31e10  ldarg.0
0xa31e11  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.DataFormWebPart::_splist
0xa31e16  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0xa31e1b  box      Microsoft.SharePoint.SPListTemplateType
0xa31e20  callvirt instance string [mscorlib]System.Object::ToString()
0xa31e25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31e2a  ldloc.0
0xa31e2b  ldstr    aWebtemplateid// "WebTemplateId"
0xa31e30  ldarg.0
0xa31e31  ldfld    class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.DataFormWebPart::_splist
0xa31e36  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xa31e3b  callvirt instance int32 Microsoft.SharePoint.SPWeb::get_WebTemplateId()
0xa31e40  stloc.s  5
0xa31e42  ldloca.s 5
0xa31e44  call     instance string [mscorlib]System.Int32::ToString()
0xa31e49  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31e4e  br.s     loc_A31E70
0xa31e50  ldloc.0
0xa31e51  ldstr    aListtemplate_0// "ListTemplate"
0xa31e56  ldstr    aNa// "na"
0xa31e5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31e60  ldloc.0
0xa31e61  ldstr    aWebtemplateid// "WebTemplateId"
0xa31e66  ldstr    aNa// "na"
0xa31e6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31e70  ldarg.3
0xa31e71  ldc.i4.0
0xa31e72  stind.i4
0xa31e73  ldarg.1
0xa31e74  ldarg.2
0xa31e75  call     void Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::SetManifest([out] string& manifestName, [out] string& scenarioName)
0xa31e7a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::ForceRenderNewExperienceKillSwitch
0xa31e7f  ldstr    a5152017// "5/15/2017"
0xa31e84  ldstr    aForceRenderNew// "Force render new experience"
0xa31e89  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xa31e8e  brtrue.s loc_A31EC5
0xa31e90  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa31e95  brfalse.s loc_A31EC5
0xa31e97  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa31e9c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa31ea1  brfalse.s loc_A31EC5
0xa31ea3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa31ea8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa31ead  ldsfld   string Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::ForceRenderNewExperienceQueryStringParameterKey
0xa31eb2  call     T0x2B000032
0xa31eb7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa31ebc  ldc.i4.0
0xa31ebd  ceq
0xa31ebf  stloc.1
0xa31ec0  ldloc.1
0xa31ec1  brfalse.s loc_A31EC5
0xa31ec3  ldc.i4.1
0xa31ec4  ret
0xa31ec5  ldarg.0
0xa31ec6  call     instance string Microsoft.SharePoint.WebPartPages.BaseXsltListWebPart::get_JSLink()
0xa31ecb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa31ed0  brtrue.s loc_A31EE4
0xa31ed2  ldarg.0
0xa31ed3  call     instance string Microsoft.SharePoint.WebPartPages.BaseXsltListWebPart::get_JSLink()
0xa31ed8  ldstr    aClienttemplate// "clienttemplates.js"
0xa31edd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa31ee2  brtrue.s loc_A31F13
0xa31ee4  ldarg.0
0xa31ee5  call     instance string Microsoft.SharePoint.WebPartPages.DataFormWebPart::get_XslLink()
0xa31eea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa31eef  brtrue.s loc_A31F03
0xa31ef1  ldarg.0
0xa31ef2  call     instance string Microsoft.SharePoint.WebPartPages.DataFormWebPart::get_XslLink()
0xa31ef7  ldstr    aMainXsl// "main.xsl"
0xa31efc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa31f01  brtrue.s loc_A31F13
0xa31f03  ldarg.0
0xa31f04  callvirt instance string Microsoft.SharePoint.WebPartPages.DataFormWebPart::get_Xsl()
0xa31f09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa31f0e  brtrue   loc_A31FB7
0xa31f13  ldarg.0
0xa31f14  call     instance string Microsoft.SharePoint.WebPartPages.BaseXsltListWebPart::get_JSLink()
0xa31f19  stloc.2
0xa31f1a  ldstr    aListviewJslink// "ListView_JSLinkCustomized"
0xa31f1f  stloc.3
0xa31f20  ldloc.2
0xa31f21  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa31f26  brfalse.s loc_A31F3A
0xa31f28  ldarg.0
0xa31f29  call     instance string Microsoft.SharePoint.WebPartPages.DataFormWebPart::get_XslLink()
0xa31f2e  stloc.2
0xa31f2f  ldarg.3
0xa31f30  ldc.i4.3
0xa31f31  stind.i4
0xa31f32  ldstr    aListviewXslcus// "ListView_XSLCustomized"
0xa31f37  stloc.3
0xa31f38  br.s     loc_A31F43
0xa31f3a  ldstr    aListviewJslink// "ListView_JSLinkCustomized"
0xa31f3f  stloc.3
0xa31f40  ldarg.3
0xa31f41  ldc.i4.2
0xa31f42  stind.i4
0xa31f43  ldc.i4   0x11A24C0
0xa31f48  ldstr    aSplistnextOffB_0// "SPListNext - OFF because XLV has JSLink"...
0xa31f4d  ldloc.2
0xa31f4e  call     string [mscorlib]System.String::Concat(string, string)
0xa31f53  ldnull
0xa31f54  ldloca.s 6
0xa31f56  initobj  [mscorlib]System.Guid
0xa31f5c  ldloc.s  6
0xa31f5e  ldnull
0xa31f5f  ldnull
0xa31f60  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0xa31f65  ldc.i4   0x11463CA
0xa31f6a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xa31f6f  ldc.i4.s 0x32
0xa31f71  ldstr    aSplistnextOffB_1// "SPListNext - OFF because XLV has JSLink"...
0xa31f76  ldc.i4.1
0xa31f77  newarr   [mscorlib]System.Object
0xa31f7c  stloc.s  7
0xa31f7e  ldloc.s  7
0xa31f80  ldc.i4.0
0xa31f81  ldloc.2
0xa31f82  stelem.ref
0xa31f83  ldloc.s  7
0xa31f85  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xa31f8a  ldloc.0
0xa31f8b  brfalse.s loc_A31FB5
0xa31f8d  ldloc.0
0xa31f8e  ldstr    aReason// "Reason"
0xa31f93  ldloc.3
0xa31f94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31f99  ldloc.0
0xa31f9a  ldstr    aIsmodern// "IsModern"
0xa31f9f  ldc.i4.0
0xa31fa0  box      [mscorlib]System.Boolean
0xa31fa5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31faa  ldstr    aRendermodernor// "RenderModernOrCLassic"
0xa31faf  ldloc.0
0xa31fb0  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xa31fb5  ldc.i4.0
0xa31fb6  ret
0xa31fb7  ldarg.0
0xa31fb8  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebPartPages.WebPart::get_Web()
0xa31fbd  callvirt instance valuetype Microsoft.SharePoint.SPTemplateFileType Microsoft.SharePoint.SPWeb::get_FileType()
0xa31fc2  ldc.i4.1
0xa31fc3  bne.un.s loc_A31FFA
0xa31fc5  ldloc.0
0xa31fc6  brfalse.s loc_A31FF4
0xa31fc8  ldloc.0
0xa31fc9  ldstr    aReason// "Reason"
0xa31fce  ldstr    aListviewIswiki// "ListView_IsWikipage"
0xa31fd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31fd8  ldloc.0
0xa31fd9  ldstr    aIsmodern// "IsModern"
0xa31fde  ldc.i4.0
0xa31fdf  box      [mscorlib]System.Boolean
0xa31fe4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa31fe9  ldstr    aRendermodernor// "RenderModernOrCLassic"
0xa31fee  ldloc.0
0xa31fef  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xa31ff4  ldarg.3
0xa31ff5  ldc.i4.s 0x19
0xa31ff7  stind.i4
0xa31ff8  ldc.i4.0
0xa31ff9  ret
0xa31ffa  ldarg.s  4
0xa31ffc  brtrue.s loc_A32011
0xa31ffe  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xa32003  brfalse.s loc_A32011
0xa32005  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xa3200a  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPContext::get_List()
0xa3200f  starg.s  4
0xa32011  ldarg.0
0xa32012  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.BaseXsltDataWebPart::get_SPList()
0xa32017  brfalse.s loc_A32045
0xa32019  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xa3201e  brfalse.s loc_A32045
0xa32020  ldarg.s  4
0xa32022  brfalse.s loc_A3203D
0xa32024  ldarg.0
0xa32025  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.BaseXsltDataWebPart::get_SPList()
0xa3202a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa3202f  ldarg.s  4
0xa32031  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa32036  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa3203b  brtrue.s loc_A32045
0xa3203d  ldarg.0
0xa3203e  call     instance class Microsoft.SharePoint.SPView Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::get_View()
0xa32043  brtrue.s loc_A32079
0xa32045  ldloc.0
0xa32046  brfalse.s loc_A32074
0xa32048  ldloc.0
0xa32049  ldstr    aReason// "Reason"
0xa3204e  ldstr    aListviewNotsup// "ListView_NotSupportedByPage"
0xa32053  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa32058  ldloc.0
0xa32059  ldstr    aIsmodern// "IsModern"
0xa3205e  ldc.i4.0
0xa3205f  box      [mscorlib]System.Boolean
0xa32064  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa32069  ldstr    aRendermodernor// "RenderModernOrCLassic"
0xa3206e  ldloc.0
0xa3206f  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xa32074  ldarg.3
0xa32075  ldc.i4.4
0xa32076  stind.i4
0xa32077  ldc.i4.0
0xa32078  ret
0xa32079  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::CheckUnghostedKillSwitch
0xa3207e  ldstr    a03162018// "03/16/2018"
0xa32083  ldstr    aCheckGhostedVi// "Check ghosted view"
0xa32088  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xa3208d  brtrue.s loc_A320FD
0xa3208f  ldarg.0
0xa32090  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.BaseXsltDataWebPart::get_SPList()
0xa32095  brfalse.s loc_A320FD
0xa32097  ldarg.0
0xa32098  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.BaseXsltDataWebPart::get_SPList()
0xa3209d  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0xa320a2  ldc.i4   0x352
0xa320a7  beq.s    loc_A320BB
0xa320a9  ldarg.0
0xa320aa  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebPartPages.BaseXsltDataWebPart::get_SPList()
0xa320af  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0xa320b4  ldc.i4   0x353
0xa320b9  bne.un.s loc_A320FD
0xa320bb  ldarg.0
0xa320bc  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebPartPages.WebPart::get_Web()
0xa320c1  callvirt instance bool Microsoft.SharePoint.SPWeb::get_IsGhosted()
0xa320c6  brtrue.s loc_A320FD
0xa320c8  ldloc.0
0xa320c9  brfalse.s loc_A320F7
0xa320cb  ldloc.0
0xa320cc  ldstr    aReason// "Reason"
0xa320d1  ldstr    aListviewPageun// "ListView_PageUnghosted"
0xa320d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa320db  ldloc.0
0xa320dc  ldstr    aIsmodern// "IsModern"
0xa320e1  ldc.i4.0
0xa320e2  box      [mscorlib]System.Boolean
0xa320e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa320ec  ldstr    aRendermodernor// "RenderModernOrCLassic"
0xa320f1  ldloc.0
0xa320f2  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xa320f7  ldarg.3
0xa320f8  ldc.i4.s 0x1B
0xa320fa  stind.i4
0xa320fb  ldc.i4.0
0xa320fc  ret
0xa320fd  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::DisableNewExperienceInDialogKillSwitch
0xa32102  ldstr    a1062016// "10/6/2016"
0xa32107  ldstr    aBlockNewClient_0// "Block new client view experience in dia"...
0xa3210c  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xa32111  brtrue.s loc_A32173
0xa32113  ldarg.0
0xa32114  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0xa32119  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa3211e  ldstr    aIsdlg// "IsDlg"
0xa32123  call     T0x2B000032
0xa32128  stloc.s  4
0xa3212a  ldloc.s  4
0xa3212c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa32131  brtrue.s loc_A32173
0xa32133  ldloc.s  4
0xa32135  ldstr    a1// "1"
0xa3213a  ldc.i4.4
0xa3213b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xa32140  brfalse.s loc_A32173
0xa32142  ldloc.0
0xa32143  brfalse.s loc_A32171
0xa32145  ldloc.0
0xa32146  ldstr    aReason// "Reason"
0xa3214b  ldstr    aListviewBlocki// "ListView_BlockInDialog"
0xa32150  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa32155  ldloc.0
0xa32156  ldstr    aIsmodern// "IsModern"
0xa3215b  ldc.i4.0
0xa3215c  box      [mscorlib]System.Boolean
0xa32161  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa32166  ldstr    aRendermodernor// "RenderModernOrCLassic"
0xa3216b  ldloc.0
0xa3216c  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xa32171  ldc.i4.0
0xa32172  ret
0xa32173  ldarg.0
0xa32174  call     instance bool Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::get_HasJSLink()
0xa32179  brfalse.s loc_A321E1
0xa3217b  ldc.i4   0x11CF59A
  ... truncated ...
```
