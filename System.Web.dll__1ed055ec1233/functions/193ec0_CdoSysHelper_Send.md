# CdoSysHelper::Send

- ea: `0x193ec0`
- end: `0x194282`
- name: `CdoSysHelper::Send`
- size: `962`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x350c0`
- `0x194290`

## callees

- `0x29e30`
- `0x35010`
- `0x35190`
- `0x351a0`
- `0x35250`
- `0x35270`
- `0x35290`
- `0x352b0`
- `0x352d0`
- `0x352f0`
- `0x35310`
- `0x35330`
- `0x35350`
- `0x35370`
- `0x35390`
- `0x353b0`
- `0x353c0`
- `0x353d0`
- `0x161c60`
- `0x1938d0`
- `0x1938e0`
- `0x193910`
- `0x193960`
- `0x193990`
- `0x1939c0`
- `0x1939f0`
- `0x193a70`
- `0x193df0`
- `0x193ec0`

## string_xrefs

- `0x19420f`: `Update`
- `0x194147`: `Configuration`
- `0x194161`: `http://schemas.microsoft.com/cdo/configuration/sendusing`
- `0x194178`: `http://schemas.microsoft.com/cdo/configuration/smtpserverport`
- `0x194198`: `http://schemas.microsoft.com/cdo/configuration/smtpserver`

## pseudocode

```c

```

## disassembly

```asm
0x193ec0  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193ec5  callvirt instance object LateBoundAccessHelper::CreateInstance()
0x193eca  stloc.0
0x193ecb  ldarg.0
0x193ecc  callvirt instance string System.Web.Mail.MailMessage::get_From()
0x193ed1  brfalse.s loc_193EE9
0x193ed3  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193ed8  ldloc.0
0x193ed9  ldstr    aFrom// "From"
0x193ede  ldarg.0
0x193edf  callvirt instance string System.Web.Mail.MailMessage::get_From()
0x193ee4  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x193ee9  ldarg.0
0x193eea  callvirt instance string System.Web.Mail.MailMessage::get_To()
0x193eef  brfalse.s loc_193F07
0x193ef1  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193ef6  ldloc.0
0x193ef7  ldstr    aTo_0// "To"
0x193efc  ldarg.0
0x193efd  callvirt instance string System.Web.Mail.MailMessage::get_To()
0x193f02  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x193f07  ldarg.0
0x193f08  callvirt instance string System.Web.Mail.MailMessage::get_Cc()
0x193f0d  brfalse.s loc_193F25
0x193f0f  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193f14  ldloc.0
0x193f15  ldstr    aCc_1// "Cc"
0x193f1a  ldarg.0
0x193f1b  callvirt instance string System.Web.Mail.MailMessage::get_Cc()
0x193f20  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x193f25  ldarg.0
0x193f26  callvirt instance string System.Web.Mail.MailMessage::get_Bcc()
0x193f2b  brfalse.s loc_193F43
0x193f2d  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193f32  ldloc.0
0x193f33  ldstr    aBcc_0// "Bcc"
0x193f38  ldarg.0
0x193f39  callvirt instance string System.Web.Mail.MailMessage::get_Bcc()
0x193f3e  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x193f43  ldarg.0
0x193f44  callvirt instance string System.Web.Mail.MailMessage::get_Subject()
0x193f49  brfalse.s loc_193F61
0x193f4b  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193f50  ldloc.0
0x193f51  ldstr    aSubject_1// "Subject"
0x193f56  ldarg.0
0x193f57  callvirt instance string System.Web.Mail.MailMessage::get_Subject()
0x193f5c  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x193f61  ldarg.0
0x193f62  callvirt instance valuetype System.Web.Mail.MailPriority System.Web.Mail.MailMessage::get_Priority()
0x193f67  brfalse.s loc_193FAD
0x193f69  ldnull
0x193f6a  stloc.3
0x193f6b  ldarg.0
0x193f6c  callvirt instance valuetype System.Web.Mail.MailPriority System.Web.Mail.MailMessage::get_Priority()
0x193f71  stloc.s  4
0x193f73  ldloc.s  4
0x193f75  switch   loc_193F90, loc_193F88, loc_193F98
0x193f86  br.s     loc_193F9E
0x193f88  ldstr    aLow_0// "low"
0x193f8d  stloc.3
0x193f8e  br.s     loc_193F9E
0x193f90  ldstr    aNormal// "normal"
0x193f95  stloc.3
0x193f96  br.s     loc_193F9E
0x193f98  ldstr    aHigh_0// "high"
0x193f9d  stloc.3
0x193f9e  ldloc.3
0x193f9f  brfalse.s loc_193FAD
0x193fa1  ldloc.0
0x193fa2  ldstr    aImportance_0// "importance"
0x193fa7  ldloc.3
0x193fa8  call     void CdoSysHelper::SetField(object m, string name, string value)
0x193fad  ldarg.0
0x193fae  callvirt instance class [mscorlib]System.Text.Encoding System.Web.Mail.MailMessage::get_BodyEncoding()
0x193fb3  brfalse.s loc_193FE6
0x193fb5  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x193fba  ldloc.0
0x193fbb  ldstr    aBodypart// "BodyPart"
0x193fc0  callvirt instance object LateBoundAccessHelper::GetProp(object obj, string propName)
0x193fc5  stloc.s  5
0x193fc7  ldloc.s  5
0x193fc9  ldstr    aCharset_2// "Charset"
0x193fce  ldarg.0
0x193fcf  callvirt instance class [mscorlib]System.Text.Encoding System.Web.Mail.MailMessage::get_BodyEncoding()
0x193fd4  callvirt instance string [mscorlib]System.Text.Encoding::get_BodyName()
0x193fd9  call     void LateBoundAccessHelper::SetPropStatic(object obj, string propName, object propValue)
0x193fde  ldloc.s  5
0x193fe0  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x193fe5  pop
0x193fe6  ldarg.0
0x193fe7  callvirt instance string System.Web.Mail.MailMessage::get_UrlContentBase()
0x193fec  brfalse.s loc_193FFF
0x193fee  ldloc.0
0x193fef  ldstr    aContentBase// "content-base"
0x193ff4  ldarg.0
0x193ff5  callvirt instance string System.Web.Mail.MailMessage::get_UrlContentBase()
0x193ffa  call     void CdoSysHelper::SetField(object m, string name, string value)
0x193fff  ldarg.0
0x194000  callvirt instance string System.Web.Mail.MailMessage::get_UrlContentLocation()
0x194005  brfalse.s loc_194018
0x194007  ldloc.0
0x194008  ldstr    aContentLocatio_0// "content-location"
0x19400d  ldarg.0
0x19400e  callvirt instance string System.Web.Mail.MailMessage::get_UrlContentLocation()
0x194013  call     void CdoSysHelper::SetField(object m, string name, string value)
0x194018  ldarg.0
0x194019  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Mail.MailMessage::get_Headers()
0x19401e  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x194023  stloc.1
0x194024  ldloc.1
0x194025  ldc.i4.0
0x194026  ble.s    loc_19405E
0x194028  ldarg.0
0x194029  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Mail.MailMessage::get_Headers()
0x19402e  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x194033  stloc.s  6
0x194035  br.s     loc_194055
0x194037  ldloc.0
0x194038  ldloc.s  6
0x19403a  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Key()
0x19403f  castclass [mscorlib]System.String
0x194044  ldloc.s  6
0x194046  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Value()
0x19404b  castclass [mscorlib]System.String
0x194050  call     void CdoSysHelper::SetField(object m, string name, string value)
0x194055  ldloc.s  6
0x194057  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19405c  brtrue.s loc_194037
0x19405e  ldarg.0
0x19405f  callvirt instance string System.Web.Mail.MailMessage::get_Body()
0x194064  brfalse.s loc_19409F
0x194066  ldarg.0
0x194067  callvirt instance valuetype System.Web.Mail.MailFormat System.Web.Mail.MailMessage::get_BodyFormat()
0x19406c  ldc.i4.1
0x19406d  bne.un.s loc_194087
0x19406f  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x194074  ldloc.0
0x194075  ldstr    aHtmlbody// "HtmlBody"
0x19407a  ldarg.0
0x19407b  callvirt instance string System.Web.Mail.MailMessage::get_Body()
0x194080  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x194085  br.s     loc_1940B4
0x194087  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x19408c  ldloc.0
0x19408d  ldstr    aTextbody// "TextBody"
0x194092  ldarg.0
0x194093  callvirt instance string System.Web.Mail.MailMessage::get_Body()
0x194098  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x19409d  br.s     loc_1940B4
0x19409f  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x1940a4  ldloc.0
0x1940a5  ldstr    aTextbody// "TextBody"
0x1940aa  ldsfld   string [mscorlib]System.String::Empty
0x1940af  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x1940b4  ldarg.0
0x1940b5  callvirt instance class [mscorlib]System.Collections.IList System.Web.Mail.MailMessage::get_Attachments()
0x1940ba  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1940bf  stloc.s  7
0x1940c1  br.s     loc_19411E
0x1940c3  ldloc.s  7
0x1940c5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1940ca  castclass System.Web.Mail.MailAttachment
0x1940cf  stloc.s  8
0x1940d1  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x1940d6  ldloc.0
0x1940d7  ldstr    aAddattachment// "AddAttachment"
0x1940dc  ldc.i4.3
0x1940dd  newarr   [mscorlib]System.Object
0x1940e2  dup
0x1940e3  ldc.i4.0
0x1940e4  ldloc.s  8
0x1940e6  callvirt instance string System.Web.Mail.MailAttachment::get_Filename()
0x1940eb  stelem.ref
0x1940ec  callvirt instance object LateBoundAccessHelper::CallMethod(object obj, string methodName, object[] args)
0x1940f1  stloc.s  9
0x1940f3  ldloc.s  8
0x1940f5  callvirt instance valuetype System.Web.Mail.MailEncoding System.Web.Mail.MailAttachment::get_Encoding()
0x1940fa  brtrue.s loc_194112
0x1940fc  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x194101  ldloc.0
0x194102  ldstr    aMimeformatted// "MimeFormatted"
0x194107  ldc.i4.0
0x194108  box      [mscorlib]System.Boolean
0x19410d  callvirt instance void LateBoundAccessHelper::SetProp(object obj, string propName, object propValue)
0x194112  ldloc.s  9
0x194114  brfalse.s loc_19411E
0x194116  ldloc.s  9
0x194118  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x19411d  pop
0x19411e  ldloc.s  7
0x194120  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x194125  brtrue.s loc_1940C3
0x194127  call     string System.Web.Mail.SmtpMail::get_SmtpServer()
0x19412c  stloc.2
0x19412d  ldloc.2
0x19412e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x194133  brfalse.s loc_194146
0x194135  ldarg.0
0x194136  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Mail.MailMessage::get_Fields()
0x19413b  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x194140  ldc.i4.0
0x194141  ble      loc_194230
0x194146  ldloc.0
0x194147  ldstr    aConfiguration// "Configuration"
0x19414c  call     object LateBoundAccessHelper::GetPropStatic(object obj, string propName)
0x194151  stloc.s  0xA
0x194153  ldloc.s  0xA
0x194155  brfalse  loc_194230
0x19415a  ldloc.s  0xA
0x19415c  ldstr    aFields// "Fields"
0x194161  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/cdo/config"...
0x194166  ldc.i4.2
0x194167  box      [mscorlib]System.Int32
0x19416c  call     void LateBoundAccessHelper::SetPropStatic(object obj, string propName, object propKey, object propValue)
0x194171  ldloc.s  0xA
0x194173  ldstr    aFields// "Fields"
0x194178  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/cdo/config"...
0x19417d  ldc.i4.s 0x19
0x19417f  box      [mscorlib]System.Int32
0x194184  call     void LateBoundAccessHelper::SetPropStatic(object obj, string propName, object propKey, object propValue)
0x194189  ldloc.2
0x19418a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19418f  brtrue.s loc_1941A3
0x194191  ldloc.s  0xA
0x194193  ldstr    aFields// "Fields"
0x194198  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/cdo/config"...
0x19419d  ldloc.2
0x19419e  call     void LateBoundAccessHelper::SetPropStatic(object obj, string propName, object propKey, object propValue)
0x1941a3  ldarg.0
0x1941a4  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Mail.MailMessage::get_Fields()
0x1941a9  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x1941ae  stloc.s  0xC
0x1941b0  br.s     loc_1941DF
0x1941b2  ldloc.s  0xC
0x1941b4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1941b9  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x1941be  stloc.s  0xD
0x1941c0  ldloc.s  0xA
0x1941c2  ldstr    aFields// "Fields"
0x1941c7  ldloca.s 0xD
0x1941c9  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x1941ce  castclass [mscorlib]System.String
0x1941d3  ldloca.s 0xD
0x1941d5  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x1941da  call     void LateBoundAccessHelper::SetPropStatic(object obj, string propName, object propKey, object propValue)
0x1941df  ldloc.s  0xC
0x1941e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1941e6  brtrue.s loc_1941B2
0x1941e8  leave.s  loc_1941FF
0x1941ea  ldloc.s  0xC
0x1941ec  isinst   [mscorlib]System.IDisposable
0x1941f1  stloc.s  0xE
0x1941f3  ldloc.s  0xE
0x1941f5  brfalse.s loc_1941FE
0x1941f7  ldloc.s  0xE
0x1941f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1941fe  endfinally
0x1941ff  ldloc.s  0xA
0x194201  ldstr    aFields// "Fields"
0x194206  call     object LateBoundAccessHelper::GetPropStatic(object obj, string propName)
0x19420b  stloc.s  0xB
0x19420d  ldloc.s  0xB
0x19420f  ldstr    aUpdate// "Update"
0x194214  ldc.i4.0
0x194215  newarr   [mscorlib]System.Object
0x19421a  call     object LateBoundAccessHelper::CallMethodStatic(object obj, string methodName, object[] args)
0x19421f  pop
0x194220  ldloc.s  0xB
0x194222  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x194227  pop
0x194228  ldloc.s  0xA
0x19422a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x19422f  pop
0x194230  call     bool System.Web.Hosting.HostingEnvironment::get_IsHosted()
0x194235  brfalse.s loc_194263
0x194237  newobj   instance void System.Web.ProcessImpersonationContext::.ctor()
0x19423c  stloc.s  0xF
0x19423e  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x194243  ldloc.0
0x194244  ldstr    aSend// "Send"
0x194249  ldc.i4.0
0x19424a  newarr   [mscorlib]System.Object
0x19424f  callvirt instance object LateBoundAccessHelper::CallMethod(object obj, string methodName, object[] args)
0x194254  pop
0x194255  leave.s  loc_19427A
0x194257  ldloc.s  0xF
0x194259  brfalse.s loc_194262
0x19425b  ldloc.s  0xF
0x19425d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x194262  endfinally
0x194263  ldsfld   class LateBoundAccessHelper CdoSysHelper::_helper
0x194268  ldloc.0
0x194269  ldstr    aSend// "Send"
0x19426e  ldc.i4.0
0x19426f  newarr   [mscorlib]System.Object
0x194274  callvirt instance object LateBoundAccessHelper::CallMethod(object obj, string methodName, object[] args)
0x194279  pop
0x19427a  ldloc.0
0x19427b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
  ... truncated ...
```
