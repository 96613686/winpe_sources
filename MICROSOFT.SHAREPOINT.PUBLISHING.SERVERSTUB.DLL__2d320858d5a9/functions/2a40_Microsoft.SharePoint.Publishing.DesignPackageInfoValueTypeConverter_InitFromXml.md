# Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter::InitFromXml

- ea: `0x2a40`
- end: `0x2b2f`
- name: `Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter::InitFromXml`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2a40`

## pseudocode

```c

```

## disassembly

```asm
0x2a40  ldarg.0
0x2a41  ldarg.1
0x2a42  ldarg.2
0x2a43  ldarg.3
0x2a44  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2a49  starg.s  1
0x2a4b  ldarg.1
0x2a4c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo
0x2a51  stloc.0
0x2a52  ldloc.0
0x2a53  brfalse  loc_2B2D
0x2a58  ldarg.2
0x2a59  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x2a5e  stloc.s  4
0x2a60  br       loc_2B0A
0x2a65  ldloc.s  4
0x2a67  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2a6c  castclass [System.Xml]System.Xml.XmlNode
0x2a71  stloc.1
0x2a72  ldloc.1
0x2a73  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a78  ldstr    aName// "Name"
0x2a7d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a82  stloc.2
0x2a83  ldloc.2
0x2a84  brfalse  loc_2B0A
0x2a89  ldloc.2
0x2a8a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2a8f  stloc.3
0x2a90  ldloc.3
0x2a91  dup
0x2a92  stloc.s  5
0x2a94  brfalse.s loc_2B0A
0x2a96  ldloc.s  5
0x2a98  ldstr    aMajorversion// "MajorVersion"
0x2a9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aa2  brtrue.s loc_2AD0
0x2aa4  ldloc.s  5
0x2aa6  ldstr    aMinorversion// "MinorVersion"
0x2aab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab0  brtrue.s loc_2ADF
0x2ab2  ldloc.s  5
0x2ab4  ldstr    aPackageguid// "PackageGuid"
0x2ab9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2abe  brtrue.s loc_2AEE
0x2ac0  ldloc.s  5
0x2ac2  ldstr    aPackagename// "PackageName"
0x2ac7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2acc  brtrue.s loc_2AFD
0x2ace  br.s     loc_2B0A
0x2ad0  ldloc.0
0x2ad1  ldloc.1
0x2ad2  ldarg.3
0x2ad3  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ad8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::set_MajorVersion(int32)
0x2add  br.s     loc_2B0A
0x2adf  ldloc.0
0x2ae0  ldloc.1
0x2ae1  ldarg.3
0x2ae2  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ae7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::set_MinorVersion(int32)
0x2aec  br.s     loc_2B0A
0x2aee  ldloc.0
0x2aef  ldloc.1
0x2af0  ldarg.3
0x2af1  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2af6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::set_PackageGuid(valuetype [mscorlib]System.Guid)
0x2afb  br.s     loc_2B0A
0x2afd  ldloc.0
0x2afe  ldloc.1
0x2aff  ldarg.3
0x2b00  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b05  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::set_PackageName(string)
0x2b0a  ldloc.s  4
0x2b0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b11  brtrue   loc_2A65
0x2b16  leave.s  loc_2B2D
0x2b18  ldloc.s  4
0x2b1a  isinst   [mscorlib]System.IDisposable
0x2b1f  stloc.s  6
0x2b21  ldloc.s  6
0x2b23  brfalse.s loc_2B2C
0x2b25  ldloc.s  6
0x2b27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b2c  endfinally
0x2b2d  ldloc.0
0x2b2e  ret
```
