# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::ReadSiteData

- ea: `0x16f0`
- end: `0x1765`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::ReadSiteData`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb50`
- `0x16b0`

## callees

- `0x1c30`
- `0x2160`

## string_xrefs

- `0x16f0`: `SiteDesigner_SiteIOReadSiteData`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  ldstr    aSitedesignerSi// "SiteDesigner_SiteIOReadSiteData"
0x16f5  ldnull
0x16f6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x16fb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x1700  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x1705  stloc.0
0x1706  ldloc.0
0x1707  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x170c  stloc.1
0x170d  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1712  stloc.2
0x1713  ldloc.2
0x1714  ldstr    aSitedataRootma// "<SiteData><RootMaster></RootMaster><Pag"...
0x1719  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x171e  ldloc.2
0x171f  ldstr    aSitedataRootma_0// "/SiteData/RootMaster"
0x1724  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1729  isinst   [System.Xml]System.Xml.XmlElement
0x172e  stloc.3
0x172f  ldloc.2
0x1730  ldstr    aSitedataPageli// "/SiteData/PageList"
0x1735  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x173a  isinst   [System.Xml]System.Xml.XmlElement
0x173f  stloc.s  4
0x1741  ldc.i4.1
0x1742  stloc.s  5
0x1744  ldloc.1
0x1745  ldloc.s  5
0x1747  ldloca.s 3
0x1749  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetRootMasterSettings(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web, bool isOwner, class [System.Xml]System.Xml.XmlElement& elemRootMaster)
0x174e  ldloc.1
0x174f  ldloc.2
0x1750  ldarg.0
0x1751  ldarg.1
0x1752  ldloca.s 4
0x1754  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetPageList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web, class [System.Xml]System.Xml.XmlDocument doc, string pageUrl, string editMode, class [System.Xml]System.Xml.XmlElement& elemPageList)
0x1759  ldloc.2
0x175a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x175f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x1764  ret
```
