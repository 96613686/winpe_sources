# System.Web.UI.WebControls.MailDefinition::CreateMailMessage_0

- ea: `0xc2850`
- end: `0xc2aea`
- name: `System.Web.UI.WebControls.MailDefinition::CreateMailMessage_0`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0xc1eb0`
- `0xc27e0`

## callees

- `0x18990`
- `0x31090`
- `0x31430`
- `0x315d0`
- `0x34fa0`
- `0x53a60`
- `0x596b0`
- `0x59ba0`
- `0x5fa50`
- `0x608d0`
- `0xacd30`
- `0xacd60`
- `0xc25f0`
- `0xc2640`
- `0xc2690`
- `0xc26b0`
- `0xc26f0`
- `0xc2740`
- `0xc2850`
- `0x1564e0`
- `0x156660`

## string_xrefs

- `0xc293c`: `MailDefinition_InvalidReplacements`
- `0xc29ee`: `EmbeddedMailObject.Path`

## pseudocode

```c

```

## disassembly

```asm
0xc2850  ldarg.s  4
0xc2852  brtrue.s loc_C285F
0xc2854  ldstr    aOwner// "owner"
0xc2859  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc285e  throw
0xc285f  ldarg.0
0xc2860  call     instance string System.Web.UI.WebControls.MailDefinition::get_From()
0xc2865  stloc.0
0xc2866  ldloc.0
0xc2867  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc286c  brfalse.s loc_C28A8
0xc286e  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetConfig()
0xc2873  callvirt instance class [System]System.Net.Configuration.SmtpSection System.Web.Configuration.RuntimeConfig::get_Smtp()
0xc2878  stloc.2
0xc2879  ldloc.2
0xc287a  brfalse.s loc_C2891
0xc287c  ldloc.2
0xc287d  callvirt instance class [System]System.Net.Configuration.SmtpNetworkElement [System]System.Net.Configuration.SmtpSection::get_Network()
0xc2882  brfalse.s loc_C2891
0xc2884  ldloc.2
0xc2885  callvirt instance string [System]System.Net.Configuration.SmtpSection::get_From()
0xc288a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc288f  brfalse.s loc_C28A1
0xc2891  ldstr    aMaildefinition// "MailDefinition_NoFromAddressSpecified"
0xc2896  call     string System.Web.SR::GetString(string name)
0xc289b  newobj   instance void System.Web.HttpException::.ctor(string message)
0xc28a0  throw
0xc28a1  ldloc.2
0xc28a2  callvirt instance string [System]System.Net.Configuration.SmtpSection::get_From()
0xc28a7  stloc.0
0xc28a8  ldnull
0xc28a9  stloc.1
0xc28aa  ldloc.0
0xc28ab  ldarg.1
0xc28ac  newobj   instance void [System]System.Net.Mail.MailMessage::.ctor(string, string)
0xc28b1  stloc.1
0xc28b2  ldarg.0
0xc28b3  call     instance string System.Web.UI.WebControls.MailDefinition::get_CC()
0xc28b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc28bd  brtrue.s loc_C28D0
0xc28bf  ldloc.1
0xc28c0  callvirt instance class [System]System.Net.Mail.MailAddressCollection [System]System.Net.Mail.MailMessage::get_CC()
0xc28c5  ldarg.0
0xc28c6  call     instance string System.Web.UI.WebControls.MailDefinition::get_CC()
0xc28cb  callvirt instance void [System]System.Net.Mail.MailAddressCollection::Add(string)
0xc28d0  ldarg.0
0xc28d1  call     instance string System.Web.UI.WebControls.MailDefinition::get_Subject()
0xc28d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc28db  brtrue.s loc_C28E9
0xc28dd  ldloc.1
0xc28de  ldarg.0
0xc28df  call     instance string System.Web.UI.WebControls.MailDefinition::get_Subject()
0xc28e4  callvirt instance void [System]System.Net.Mail.MailMessage::set_Subject(string)
0xc28e9  ldloc.1
0xc28ea  ldarg.0
0xc28eb  call     instance valuetype [System]System.Net.Mail.MailPriority System.Web.UI.WebControls.MailDefinition::get_Priority()
0xc28f0  callvirt instance void [System]System.Net.Mail.MailMessage::set_Priority(valuetype [System]System.Net.Mail.MailPriority)
0xc28f5  ldarg.2
0xc28f6  brfalse  loc_C298A
0xc28fb  ldarg.3
0xc28fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc2901  brtrue   loc_C298A
0xc2906  ldarg.2
0xc2907  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Keys()
0xc290c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xc2911  stloc.3
0xc2912  br.s     loc_C296C
0xc2914  ldloc.3
0xc2915  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc291a  stloc.s  4
0xc291c  ldloc.s  4
0xc291e  isinst   [mscorlib]System.String
0xc2923  stloc.s  5
0xc2925  ldarg.2
0xc2926  ldloc.s  4
0xc2928  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xc292d  isinst   [mscorlib]System.String
0xc2932  stloc.s  6
0xc2934  ldloc.s  5
0xc2936  brfalse.s loc_C293C
0xc2938  ldloc.s  6
0xc293a  brtrue.s loc_C294C
0xc293c  ldstr    aMaildefinition_0// "MailDefinition_InvalidReplacements"
0xc2941  call     string System.Web.SR::GetString(string name)
0xc2946  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xc294b  throw
0xc294c  ldloc.s  6
0xc294e  ldstr    asc_1C472E// "$"
0xc2953  ldstr    asc_1D5E54// "$$"
0xc2958  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc295d  stloc.s  6
0xc295f  ldarg.3
0xc2960  ldloc.s  5
0xc2962  ldloc.s  6
0xc2964  ldc.i4.1
0xc2965  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xc296a  starg.s  3
0xc296c  ldloc.3
0xc296d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc2972  brtrue.s loc_C2914
0xc2974  leave.s  loc_C298A
0xc2976  ldloc.3
0xc2977  isinst   [mscorlib]System.IDisposable
0xc297c  stloc.s  7
0xc297e  ldloc.s  7
0xc2980  brfalse.s loc_C2989
0xc2982  ldloc.s  7
0xc2984  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc2989  endfinally
0xc298a  ldarg.0
0xc298b  call     instance class System.Web.UI.WebControls.EmbeddedMailObjectsCollection System.Web.UI.WebControls.MailDefinition::get_EmbeddedObjects()
0xc2990  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xc2995  ldc.i4.0
0xc2996  ble      loc_C2ABB
0xc299b  ldarg.0
0xc299c  call     instance bool System.Web.UI.WebControls.MailDefinition::get_IsBodyHtml()
0xc29a1  brtrue.s loc_C29AA
0xc29a3  ldstr    aTextPlain// "text/plain"
0xc29a8  br.s     loc_C29AF
0xc29aa  ldstr    aTextHtml// "text/html"
0xc29af  stloc.s  8
0xc29b1  ldarg.3
0xc29b2  ldnull
0xc29b3  ldloc.s  8
0xc29b5  call     class [System]System.Net.Mail.AlternateView [System]System.Net.Mail.AlternateView::CreateAlternateViewFromString(string, class [mscorlib]System.Text.Encoding, string)
0xc29ba  stloc.s  9
0xc29bc  ldarg.0
0xc29bd  call     instance class System.Web.UI.WebControls.EmbeddedMailObjectsCollection System.Web.UI.WebControls.MailDefinition::get_EmbeddedObjects()
0xc29c2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xc29c7  stloc.s  0xA
0xc29c9  br       loc_C2A89
0xc29ce  ldloc.s  0xA
0xc29d0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc29d5  castclass System.Web.UI.WebControls.EmbeddedMailObject
0xc29da  stloc.s  0xB
0xc29dc  ldloc.s  0xB
0xc29de  callvirt instance string System.Web.UI.WebControls.EmbeddedMailObject::get_Path()
0xc29e3  stloc.s  0xC
0xc29e5  ldloc.s  0xC
0xc29e7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc29ec  brfalse.s loc_C29F9
0xc29ee  ldstr    aEmbeddedmailob_0// "EmbeddedMailObject.Path"
0xc29f3  call     class [mscorlib]System.ArgumentException System.Web.Util.ExceptionUtil::PropertyNullOrEmpty(string property)
0xc29f8  throw
0xc29f9  ldloc.s  0xC
0xc29fb  call     bool System.Web.Util.UrlPath::IsAbsolutePhysicalPath(string path)
0xc2a00  brtrue.s loc_C2A20
0xc2a02  ldarg.s  4
0xc2a04  callvirt instance class System.Web.VirtualPath System.Web.UI.Control::get_TemplateControlVirtualDirectory()
0xc2a09  ldloc.s  0xC
0xc2a0b  call     class System.Web.VirtualPath System.Web.VirtualPath::Create(string virtualPath)
0xc2a10  call     class System.Web.VirtualPath System.Web.VirtualPath::Combine(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0xc2a15  stloc.s  0xE
0xc2a17  ldloc.s  0xE
0xc2a19  callvirt instance string System.Web.VirtualPath::get_AppRelativeVirtualPathString()
0xc2a1e  stloc.s  0xC
0xc2a20  ldnull
0xc2a21  stloc.s  0xD
0xc2a23  ldnull
0xc2a24  stloc.s  0xF
0xc2a26  ldarg.s  4
0xc2a28  ldloc.s  0xC
0xc2a2a  callvirt instance class [mscorlib]System.IO.Stream System.Web.UI.Control::OpenFile(string path)
0xc2a2f  stloc.s  0xF
0xc2a31  ldloc.s  0xF
0xc2a33  newobj   instance void [System]System.Net.Mail.LinkedResource::.ctor(class [mscorlib]System.IO.Stream)
0xc2a38  stloc.s  0xD
0xc2a3a  leave.s  loc_C2A4A
0xc2a3c  pop
0xc2a3d  ldloc.s  0xF
0xc2a3f  brfalse.s loc_C2A48
0xc2a41  ldloc.s  0xF
0xc2a43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc2a48  rethrow
0xc2a4a  ldloc.s  0xD
0xc2a4c  ldloc.s  0xB
0xc2a4e  callvirt instance string System.Web.UI.WebControls.EmbeddedMailObject::get_Name()
0xc2a53  callvirt instance void [System]System.Net.Mail.AttachmentBase::set_ContentId(string)
0xc2a58  ldloc.s  0xD
0xc2a5a  callvirt instance class [System]System.Net.Mime.ContentType [System]System.Net.Mail.AttachmentBase::get_ContentType()
0xc2a5f  ldloc.s  0xC
0xc2a61  call     string System.Web.Util.UrlPath::GetFileName(string virtualPath)
0xc2a66  callvirt instance void [System]System.Net.Mime.ContentType::set_Name(string)
0xc2a6b  ldloc.s  9
0xc2a6d  callvirt instance class [System]System.Net.Mail.LinkedResourceCollection [System]System.Net.Mail.AlternateView::get_LinkedResources()
0xc2a72  ldloc.s  0xD
0xc2a74  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Net.Mail.LinkedResource>::Add(var<u1>)
0xc2a79  leave.s  loc_C2A89
0xc2a7b  pop
0xc2a7c  ldloc.s  0xD
0xc2a7e  brfalse.s loc_C2A87
0xc2a80  ldloc.s  0xD
0xc2a82  callvirt instance void [System]System.Net.Mail.AttachmentBase::Dispose()
0xc2a87  rethrow
0xc2a89  ldloc.s  0xA
0xc2a8b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc2a90  brtrue   loc_C29CE
0xc2a95  leave.s  loc_C2AAC
0xc2a97  ldloc.s  0xA
0xc2a99  isinst   [mscorlib]System.IDisposable
0xc2a9e  stloc.s  7
0xc2aa0  ldloc.s  7
0xc2aa2  brfalse.s loc_C2AAB
0xc2aa4  ldloc.s  7
0xc2aa6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc2aab  endfinally
0xc2aac  ldloc.1
0xc2aad  callvirt instance class [System]System.Net.Mail.AlternateViewCollection [System]System.Net.Mail.MailMessage::get_AlternateViews()
0xc2ab2  ldloc.s  9
0xc2ab4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Net.Mail.AlternateView>::Add(var<u1>)
0xc2ab9  br.s     loc_C2ACA
0xc2abb  ldarg.3
0xc2abc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc2ac1  brtrue.s loc_C2ACA
0xc2ac3  ldloc.1
0xc2ac4  ldarg.3
0xc2ac5  callvirt instance void [System]System.Net.Mail.MailMessage::set_Body(string)
0xc2aca  ldloc.1
0xc2acb  ldarg.0
0xc2acc  call     instance bool System.Web.UI.WebControls.MailDefinition::get_IsBodyHtml()
0xc2ad1  callvirt instance void [System]System.Net.Mail.MailMessage::set_IsBodyHtml(bool)
0xc2ad6  ldloc.1
0xc2ad7  stloc.s  0x10
0xc2ad9  leave.s  loc_C2AE7
0xc2adb  pop
0xc2adc  ldloc.1
0xc2add  brfalse.s loc_C2AE5
0xc2adf  ldloc.1
0xc2ae0  callvirt instance void [System]System.Net.Mail.MailMessage::Dispose()
0xc2ae5  rethrow
0xc2ae7  ldloc.s  0x10
0xc2ae9  ret
```
