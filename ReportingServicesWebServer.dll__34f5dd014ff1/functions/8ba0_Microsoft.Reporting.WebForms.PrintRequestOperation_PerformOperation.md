# Microsoft.Reporting.WebForms.PrintRequestOperation::PerformOperation

- ea: `0x8ba0`
- end: `0x8cae`
- name: `Microsoft.Reporting.WebForms.PrintRequestOperation::PerformOperation`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7fb0`
- `0x8ba0`
- `0x11810`

## string_xrefs

- `0x8c3f`: `rs:Command`

## pseudocode

```c

```

## disassembly

```asm
0x8ba0  ldstr    aDeviceinfo_0// "<DeviceInfo>"
0x8ba5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x8baa  stloc.0
0x8bab  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.Reporting.WebForms.HttpHandler::get_RequestParameters()
0x8bb0  stloc.1
0x8bb1  ldc.i4.1
0x8bb2  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(int32)
0x8bb7  stloc.2
0x8bb8  ldc.i4.0
0x8bb9  stloc.3
0x8bba  br       loc_8C82
0x8bbf  ldloc.1
0x8bc0  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8bc5  ldloc.3
0x8bc6  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8bcb  brfalse  loc_8C7E
0x8bd0  ldloc.1
0x8bd1  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8bd6  ldloc.3
0x8bd7  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8bdc  ldstr    aRc// "rc:"
0x8be1  ldc.i4.5
0x8be2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8be7  brfalse.s loc_8C1A
0x8be9  ldloc.0
0x8bea  ldstr    a010// "<{0}>{1}</{0}>"
0x8bef  ldloc.1
0x8bf0  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8bf5  ldloc.3
0x8bf6  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8bfb  ldc.i4.3
0x8bfc  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8c01  call     string [System.Xml]System.Xml.XmlConvert::EncodeName(string)
0x8c06  ldloc.1
0x8c07  ldloc.3
0x8c08  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0x8c0d  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x8c12  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x8c17  pop
0x8c18  br.s     loc_8C7E
0x8c1a  ldloc.1
0x8c1b  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8c20  ldloc.3
0x8c21  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8c26  ldstr    aRs_0// "rs:"
0x8c2b  ldc.i4.5
0x8c2c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8c31  brfalse.s loc_8C7E
0x8c33  ldloc.1
0x8c34  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8c39  ldloc.3
0x8c3a  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8c3f  ldstr    aRsCommand// "rs:Command"
0x8c44  ldc.i4.5
0x8c45  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8c4a  brfalse.s loc_8C7E
0x8c4c  ldloc.1
0x8c4d  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8c52  ldloc.3
0x8c53  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8c58  ldstr    aRsFormat// "rs:format"
0x8c5d  ldc.i4.5
0x8c5e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8c63  brfalse.s loc_8C7E
0x8c65  ldloc.2
0x8c66  ldloc.1
0x8c67  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x8c6c  ldloc.3
0x8c6d  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x8c72  ldloc.1
0x8c73  ldloc.3
0x8c74  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0x8c79  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x8c7e  ldloc.3
0x8c7f  ldc.i4.1
0x8c80  add
0x8c81  stloc.3
0x8c82  ldloc.3
0x8c83  ldloc.1
0x8c84  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x8c89  blt      loc_8BBF
0x8c8e  ldloc.0
0x8c8f  ldstr    aDeviceinfo_1// "</DeviceInfo>"
0x8c94  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8c99  pop
0x8c9a  ldarg.0
0x8c9b  ldfld    class Microsoft.Reporting.WebForms.ReportControlSession Microsoft.Reporting.WebForms.ReportDataOperation::m_reportControlSession
0x8ca0  ldloc.0
0x8ca1  callvirt instance string [mscorlib]System.Object::ToString()
0x8ca6  ldloc.2
0x8ca7  ldarg.2
0x8ca8  callvirt instance void Microsoft.Reporting.WebForms.ReportControlSession::RenderReportForPrint(string deviceInfo, class [System]System.Collections.Specialized.NameValueCollection additonalParams, class [System.Web]System.Web.HttpResponse response)
0x8cad  ret
```
