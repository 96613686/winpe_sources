# Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::SendMessages

- ea: `0x8e50`
- end: `0x904f`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::SendMessages`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x81c0`

## callees

- `0x7bc0`
- `0x7fa0`
- `0x8e50`
- `0x9050`

## string_xrefs

- `0x8e6c`: `ContactUsControl.SendMessages: SPOutboundMailServiceInstance is null`
- `0x8f64`: `ContactUs@email.microsoftonline.com`

## pseudocode

```c

```

## disassembly

```asm
0x8e50  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAdministrationWebApplication::get_Local()
0x8e55  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPOutboundMailServiceInstance [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_OutboundMailServiceInstance()
0x8e5a  stloc.0
0x8e5b  ldloc.0
0x8e5c  ldnull
0x8e5d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x8e62  brfalse.s loc_8E78
0x8e64  ldc.i4.0
0x8e65  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x8e6a  ldc.i4.s 0xA
0x8e6c  ldstr    aContactuscontr_19// "ContactUsControl.SendMessages: SPOutbou"...
0x8e71  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x8e76  ldc.i4.0
0x8e77  ret
0x8e78  ldloc.0
0x8e79  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceInstance::get_Server()
0x8e7e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer::get_Address()
0x8e83  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8e88  brfalse.s loc_8E9E
0x8e8a  ldc.i4.0
0x8e8b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x8e90  ldc.i4.s 0xA
0x8e92  ldstr    aContactuscontr_20// "ContactUsControl.SendMessages: SMTP Ser"...
0x8e97  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x8e9c  ldc.i4.0
0x8e9d  ret
0x8e9e  ldc.i4.0
0x8e9f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x8ea4  ldc.i4.s 0x64
0x8ea6  ldstr    aContactuscontr_21// "ContactUsControl.SendMessages: Current "...
0x8eab  ldc.i4.1
0x8eac  newarr   [mscorlib]System.Object
0x8eb1  stloc.s  8
0x8eb3  ldloc.s  8
0x8eb5  ldc.i4.0
0x8eb6  ldloc.0
0x8eb7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceInstance::get_Server()
0x8ebc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer::get_Address()
0x8ec1  stelem.ref
0x8ec2  ldloc.s  8
0x8ec4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x8ec9  ldc.i4.1
0x8eca  stloc.1
0x8ecb  ldarg.0
0x8ecc  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::fromAddress
0x8ed1  ldarg.0
0x8ed2  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::fromAddress
0x8ed7  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x8edc  callvirt instance string [mscorlib]System.String::Trim()
0x8ee1  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x8ee6  ldarg.0
0x8ee7  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::get_EmailTo()
0x8eec  brfalse.s loc_8EFB
0x8eee  ldarg.0
0x8eef  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::get_EmailTo()
0x8ef4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8ef9  brtrue.s loc_8F19
0x8efb  ldc.i4   0x67383836
0x8f00  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x8f05  ldc.i4.s 0x32
0x8f07  ldstr    aContactuscontr_22// "ContactUsControl: SendMessages. Error D"...
0x8f0c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x8f11  ldc.i4.0
0x8f12  stloc.s  7
0x8f14  leave    loc_904C
0x8f19  ldarg.0
0x8f1a  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::get_EmailTo()
0x8f1f  ldc.i4.2
0x8f20  newarr   [mscorlib]System.Char
0x8f25  stloc.s  9
0x8f27  ldloc.s  9
0x8f29  ldc.i4.0
0x8f2a  ldc.i4.s 0x2C
0x8f2c  stelem.i2
0x8f2d  ldloc.s  9
0x8f2f  ldc.i4.1
0x8f30  ldc.i4.s 0x3B
0x8f32  stelem.i2
0x8f33  ldloc.s  9
0x8f35  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8f3a  stloc.2
0x8f3b  ldc.i4.0
0x8f3c  stloc.3
0x8f3d  br       loc_9013
0x8f42  newobj   instance void [System]System.Collections.Specialized.StringDictionary::.ctor()
0x8f47  stloc.s  4
0x8f49  ldloc.s  4
0x8f4b  ldstr    aTo// "To"
0x8f50  ldloc.2
0x8f51  ldloc.3
0x8f52  ldelem.ref
0x8f53  callvirt instance string [mscorlib]System.String::Trim()
0x8f58  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x8f5d  ldloc.s  4
0x8f5f  ldstr    aFrom// "From"
0x8f64  ldstr    aContactusEmail// "ContactUs@email.microsoftonline.com"
0x8f69  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x8f6e  ldloc.s  4
0x8f70  ldstr    aReplyTo// "Reply-To"
0x8f75  ldarg.0
0x8f76  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::fromAddress
0x8f7b  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x8f80  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x8f85  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8f8a  ldstr    aContactuscontr_23// "ContactUsControl.EmailSubject"
0x8f8f  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x8f94  ldc.i4.2
0x8f95  newarr   [mscorlib]System.Object
0x8f9a  stloc.s  0xA
0x8f9c  ldloc.s  0xA
0x8f9e  ldc.i4.0
0x8f9f  ldarg.0
0x8fa0  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x8fa5  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x8faa  stelem.ref
0x8fab  ldloc.s  0xA
0x8fad  ldc.i4.1
0x8fae  ldarg.0
0x8faf  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x8fb4  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x8fb9  stelem.ref
0x8fba  ldloc.s  0xA
0x8fbc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8fc1  stloc.s  5
0x8fc3  ldloc.s  4
0x8fc5  ldstr    aSubject// "Subject"
0x8fca  ldloc.s  5
0x8fcc  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x8fd1  ldloc.s  4
0x8fd3  ldstr    aContentType// "Content-Type"
0x8fd8  ldstr    aTextHtmlCharse// "text/html; charset=utf-8"
0x8fdd  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Add(string, string)
0x8fe2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x8fe7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x8fec  ldloc.s  4
0x8fee  ldarg.0
0x8fef  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::GetEmailBody()
0x8ff4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::SendEmail(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, class [System]System.Collections.Specialized.StringDictionary, string)
0x8ff9  stloc.1
0x8ffa  ldloc.1
0x8ffb  brtrue.s loc_900F
0x8ffd  ldc.i4.0
0x8ffe  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x9003  ldc.i4.s 0x14
0x9005  ldstr    aContactuscontr_24// "ContactUsControl.SendMessages: SPUtilit"...
0x900a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x900f  ldloc.3
0x9010  ldc.i4.1
0x9011  add
0x9012  stloc.3
0x9013  ldloc.3
0x9014  ldloc.2
0x9015  ldlen
0x9016  conv.i4
0x9017  blt      loc_8F42
0x901c  leave.s  loc_904A
0x901e  stloc.s  6
0x9020  ldc.i4   0x67383837
0x9025  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x902a  ldc.i4.s 0x32
0x902c  ldstr    aContactuscontr_25// "ContactUsControl: SendMessages. Error S"...
0x9031  ldc.i4.1
0x9032  newarr   [mscorlib]System.Object
0x9037  stloc.s  0xB
0x9039  ldloc.s  0xB
0x903b  ldc.i4.0
0x903c  ldloc.s  6
0x903e  stelem.ref
0x903f  ldloc.s  0xB
0x9041  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x9046  ldc.i4.0
0x9047  stloc.1
0x9048  leave.s  loc_904A
0x904a  ldloc.1
0x904b  ret
0x904c  ldloc.s  7
0x904e  ret
```
