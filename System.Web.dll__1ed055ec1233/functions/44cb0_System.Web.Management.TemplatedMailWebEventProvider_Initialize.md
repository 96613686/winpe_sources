# System.Web.Management.TemplatedMailWebEventProvider::Initialize

- ea: `0x44cb0`
- end: `0x44dd6`
- name: `System.Web.Management.TemplatedMailWebEventProvider::Initialize`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x24670`
- `0x24690`
- `0x34f20`
- `0x422f0`
- `0x44cb0`
- `0x57720`
- `0x57940`
- `0x595a0`
- `0x59850`

## string_xrefs

- `0x44cb1`: `template`
- `0x44cd7`: `template`
- `0x44d17`: `template`
- `0x44d4f`: `template`
- `0x44d9d`: `template`
- `0x44d42`: `Invalid_mail_template_provider_attribute`
- `0x44d90`: `Invalid_mail_template_provider_attribute`
- `0x44dbc`: `detailedTemplateErrors`

## pseudocode

```c

```

## disassembly

```asm
0x44cb0  ldarg.2
0x44cb1  ldstr    aTemplate// "template"
0x44cb6  ldarg.1
0x44cb7  ldarg.0
0x44cb8  ldflda   string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44cbd  call     void System.Web.Util.ProviderUtil::GetAndRemoveStringAttribute(class [System]System.Collections.Specialized.NameValueCollection config, string attrib, string providerName, string& val)
0x44cc2  ldarg.0
0x44cc3  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44cc8  brtrue.s loc_44CEC
0x44cca  ldstr    aProviderMissin// "Provider_missing_attribute"
0x44ccf  ldc.i4.2
0x44cd0  newarr   [mscorlib]System.Object
0x44cd5  dup
0x44cd6  ldc.i4.0
0x44cd7  ldstr    aTemplate// "template"
0x44cdc  stelem.ref
0x44cdd  dup
0x44cde  ldc.i4.1
0x44cdf  ldarg.1
0x44ce0  stelem.ref
0x44ce1  call     string System.Web.SR::GetString(string name, object[] args)
0x44ce6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x44ceb  throw
0x44cec  ldarg.0
0x44ced  ldarg.0
0x44cee  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44cf3  callvirt instance string [mscorlib]System.String::Trim()
0x44cf8  stfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44cfd  ldarg.0
0x44cfe  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d03  callvirt instance int32 [mscorlib]System.String::get_Length()
0x44d08  brtrue.s loc_44D35
0x44d0a  ldstr    aInvalidProvide// "Invalid_provider_attribute"
0x44d0f  ldc.i4.3
0x44d10  newarr   [mscorlib]System.Object
0x44d15  dup
0x44d16  ldc.i4.0
0x44d17  ldstr    aTemplate// "template"
0x44d1c  stelem.ref
0x44d1d  dup
0x44d1e  ldc.i4.1
0x44d1f  ldarg.1
0x44d20  stelem.ref
0x44d21  dup
0x44d22  ldc.i4.2
0x44d23  ldarg.0
0x44d24  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d29  stelem.ref
0x44d2a  call     string System.Web.SR::GetString(string name, object[] args)
0x44d2f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x44d34  throw
0x44d35  ldarg.0
0x44d36  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d3b  call     bool System.Web.Util.UrlPath::IsRelativeUrl(string virtualPath)
0x44d40  brtrue.s loc_44D6D
0x44d42  ldstr    aInvalidMailTem// "Invalid_mail_template_provider_attribut"...
0x44d47  ldc.i4.3
0x44d48  newarr   [mscorlib]System.Object
0x44d4d  dup
0x44d4e  ldc.i4.0
0x44d4f  ldstr    aTemplate// "template"
0x44d54  stelem.ref
0x44d55  dup
0x44d56  ldc.i4.1
0x44d57  ldarg.1
0x44d58  stelem.ref
0x44d59  dup
0x44d5a  ldc.i4.2
0x44d5b  ldarg.0
0x44d5c  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d61  stelem.ref
0x44d62  call     string System.Web.SR::GetString(string name, object[] args)
0x44d67  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x44d6c  throw
0x44d6d  ldarg.0
0x44d6e  call     string System.Web.HttpRuntime::get_AppDomainAppVirtualPathString()
0x44d73  ldarg.0
0x44d74  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d79  call     string System.Web.Util.UrlPath::Combine(string basepath, string relative)
0x44d7e  stfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d83  ldarg.0
0x44d84  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44d89  call     bool System.Web.HttpRuntime::IsPathWithinAppRoot(string path)
0x44d8e  brtrue.s loc_44DBB
0x44d90  ldstr    aInvalidMailTem// "Invalid_mail_template_provider_attribut"...
0x44d95  ldc.i4.3
0x44d96  newarr   [mscorlib]System.Object
0x44d9b  dup
0x44d9c  ldc.i4.0
0x44d9d  ldstr    aTemplate// "template"
0x44da2  stelem.ref
0x44da3  dup
0x44da4  ldc.i4.1
0x44da5  ldarg.1
0x44da6  stelem.ref
0x44da7  dup
0x44da8  ldc.i4.2
0x44da9  ldarg.0
0x44daa  ldfld    string System.Web.Management.TemplatedMailWebEventProvider::_templateUrl
0x44daf  stelem.ref
0x44db0  call     string System.Web.SR::GetString(string name, object[] args)
0x44db5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x44dba  throw
0x44dbb  ldarg.2
0x44dbc  ldstr    aDetailedtempla// "detailedTemplateErrors"
0x44dc1  ldarg.1
0x44dc2  ldarg.0
0x44dc3  ldflda   bool System.Web.Management.TemplatedMailWebEventProvider::_detailedTemplateErrors
0x44dc8  call     void System.Web.Util.ProviderUtil::GetAndRemoveBooleanAttribute(class [System]System.Collections.Specialized.NameValueCollection config, string attrib, string providerName, bool& val)
0x44dcd  ldarg.0
0x44dce  ldarg.1
0x44dcf  ldarg.2
0x44dd0  call     instance void System.Web.Management.MailWebEventProvider::Initialize(string name, class [System]System.Collections.Specialized.NameValueCollection config)
0x44dd5  ret
```
