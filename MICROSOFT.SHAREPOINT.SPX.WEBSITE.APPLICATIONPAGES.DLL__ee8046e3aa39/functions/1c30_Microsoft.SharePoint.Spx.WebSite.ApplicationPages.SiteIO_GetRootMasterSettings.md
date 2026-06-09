# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetRootMasterSettings

- ea: `0x1c30`
- end: `0x1e2a`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetRootMasterSettings`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16f0`

## callees

- `0x1c30`

## string_xrefs

- `0x1d07`: `CommerceEnabled`
- `0x1d18`: `CommerceActive`

## pseudocode

```c

```

## disassembly

```asm
0x1c30  ldarg.0
0x1c31  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.HeaderImageIO::InitialLoad(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1c36  stloc.0
0x1c37  ldarg.0
0x1c38  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1c3d  stloc.1
0x1c3e  ldstr    aEnabledynamich// "EnableDynamicHeaderImage"
0x1c43  ldstr    aTrue// "true"
0x1c48  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string, string)
0x1c4d  stloc.2
0x1c4e  ldarg.2
0x1c4f  ldind.ref
0x1c50  ldstr    aNavnodes// "NavNodes"
0x1c55  ldarg.0
0x1c56  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetNavigationNodesXml(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1c5b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1c60  ldarg.2
0x1c61  ldind.ref
0x1c62  ldstr    aUserisowner// "UserIsOwner"
0x1c67  ldarg.1
0x1c68  brtrue.s loc_1C71
0x1c6a  ldstr    a0// "0"
0x1c6f  br.s     loc_1C76
0x1c71  ldstr    a1// "1"
0x1c76  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1c7b  ldarg.2
0x1c7c  ldind.ref
0x1c7d  ldstr    aDomainname// "DomainName"
0x1c82  ldarg.0
0x1c83  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetDomainName(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1c88  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1c8d  ldarg.2
0x1c8e  ldind.ref
0x1c8f  ldstr    aGlobalsearchsw// "GlobalSearchSwitch"
0x1c94  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::get_GetGlobalSearchSwitch()
0x1c99  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1c9e  ldarg.2
0x1c9f  ldind.ref
0x1ca0  ldstr    aLogoimage// "LogoImage"
0x1ca5  ldsfld   string [mscorlib]System.String::Empty
0x1caa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1caf  call     string[] [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GeneralProperties()
0x1cb4  stloc.s  6
0x1cb6  ldc.i4.0
0x1cb7  stloc.s  7
0x1cb9  br.s     loc_1CD6
0x1cbb  ldloc.s  6
0x1cbd  ldloc.s  7
0x1cbf  ldelem.ref
0x1cc0  stloc.3
0x1cc1  ldarg.2
0x1cc2  ldind.ref
0x1cc3  ldloc.3
0x1cc4  ldarg.0
0x1cc5  ldloc.3
0x1cc6  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1ccb  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1cd0  ldloc.s  7
0x1cd2  ldc.i4.1
0x1cd3  add
0x1cd4  stloc.s  7
0x1cd6  ldloc.s  7
0x1cd8  ldloc.s  6
0x1cda  ldlen
0x1cdb  conv.i4
0x1cdc  blt.s    loc_1CBB
0x1cde  ldarg.0
0x1cdf  ldstr    aLayoutid// "LayoutID"
0x1ce4  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1ce9  stloc.s  4
0x1ceb  ldloc.s  4
0x1ced  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cf2  brfalse.s loc_1D05
0x1cf4  ldarg.2
0x1cf5  ldind.ref
0x1cf6  ldstr    aLayoutid// "LayoutID"
0x1cfb  ldstr    a11// "11"
0x1d00  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d05  ldarg.2
0x1d06  ldind.ref
0x1d07  ldstr    aCommerceenable// "CommerceEnabled"
0x1d0c  ldstr    a0// "0"
0x1d11  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d16  ldarg.2
0x1d17  ldind.ref
0x1d18  ldstr    aCommerceactive// "CommerceActive"
0x1d1d  ldstr    a0// "0"
0x1d22  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d27  ldarg.2
0x1d28  ldind.ref
0x1d29  ldstr    aCarturl// "CartUrl"
0x1d2e  ldsfld   string [mscorlib]System.String::Empty
0x1d33  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d38  ldloc.0
0x1d39  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d3e  brtrue.s loc_1D59
0x1d40  ldarg.2
0x1d41  ldind.ref
0x1d42  ldstr    aCustomimageid// "CustomImageID"
0x1d47  ldarg.0
0x1d48  ldstr    aCustomimageid// "CustomImageID"
0x1d4d  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1d52  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d57  br.s     loc_1DA8
0x1d59  ldarg.0
0x1d5a  ldstr    aCategory_0// "Category"
0x1d5f  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1d64  ldstr    aCustomimage// "CustomImage"
0x1d69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d6e  brfalse.s loc_1D80
0x1d70  ldarg.0
0x1d71  ldstr    aCategory_0// "Category"
0x1d76  ldstr    aAccounting// "Accounting"
0x1d7b  call     void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::SetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string, string)
0x1d80  ldarg.2
0x1d81  ldind.ref
0x1d82  ldstr    aCategory_0// "Category"
0x1d87  ldarg.0
0x1d88  ldstr    aCategory_0// "Category"
0x1d8d  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1d92  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1d97  ldarg.2
0x1d98  ldind.ref
0x1d99  ldstr    aCustomimageid// "CustomImageID"
0x1d9e  ldsfld   string [mscorlib]System.String::Empty
0x1da3  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1da8  ldloc.2
0x1da9  ldstr    aFalse// "false"
0x1dae  ldc.i4.5
0x1daf  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1db4  brtrue.s loc_1DF6
0x1db6  ldarg.0
0x1db7  ldstr    aCategory_0// "Category"
0x1dbc  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1dc1  ldstr    aCustomimage// "CustomImage"
0x1dc6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1dcb  brfalse.s loc_1DF6
0x1dcd  ldarg.0
0x1dce  ldloc.1
0x1dcf  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::get_DefaultDynamicImagePath()
0x1dd4  ldarg.0
0x1dd5  ldstr    aCategory_0// "Category"
0x1dda  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::GetProperty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1ddf  call     string [mscorlib]System.String::Concat(string, string)
0x1de4  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.HeaderImageIO::GetFileName(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x1de9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1dee  brfalse.s loc_1DF6
0x1df0  ldarg.0
0x1df1  call     void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PublicSite::ResetThemeCategoryPath(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1df6  ldarg.2
0x1df7  ldind.ref
0x1df8  ldstr    aEnabledynamich_0// "EnableDynamicHeader"
0x1dfd  ldloc.2
0x1dfe  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1e03  ldarg.0
0x1e04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::GetMembersLinkNode(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x1e09  stloc.s  5
0x1e0b  ldarg.2
0x1e0c  ldind.ref
0x1e0d  ldstr    aMemberloginurl// "MemberLoginUrl"
0x1e12  ldloc.s  5
0x1e14  brtrue.s loc_1E1D
0x1e16  ldstr    asc_21500// ""
0x1e1b  br.s     loc_1E24
0x1e1d  ldloc.s  5
0x1e1f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Url()
0x1e24  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x1e29  ret
```
