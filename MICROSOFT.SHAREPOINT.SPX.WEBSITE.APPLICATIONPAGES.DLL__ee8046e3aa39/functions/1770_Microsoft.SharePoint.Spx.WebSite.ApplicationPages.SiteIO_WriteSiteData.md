# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::WriteSiteData

- ea: `0x1770`
- end: `0x1915`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::WriteSiteData`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xb50`

## callees

- `0x1770`
- `0x1e30`
- `0x2500`

## string_xrefs

- `0x1770`: `SiteDesigner_SiteIOWriteSiteData`
- `0x18f0`: `DeletedFile`

## pseudocode

```c

```

## disassembly

```asm
0x1770  ldstr    aSitedesignerSi_0// "SiteDesigner_SiteIOWriteSiteData"
0x1775  ldnull
0x1776  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x177b  ldstr    aSuccess// "Success"
0x1780  stloc.0
0x1781  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x1786  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x178b  stloc.1
0x178c  ldloc.1
0x178d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x1792  stloc.2
0x1793  ldarg.0
0x1794  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0x1799  stloc.3
0x179a  ldloc.3
0x179b  ldc.i4.0
0x179c  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x17a1  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x17a6  stloc.s  4
0x17a8  ldloc.s  4
0x17aa  ldnull
0x17ab  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x17b0  ldloc.3
0x17b1  ldloc.s  4
0x17b3  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x17b8  stloc.s  5
0x17ba  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x17bf  stloc.s  6
0x17c1  ldloc.s  6
0x17c3  ldloc.s  5
0x17c5  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x17ca  ldloc.s  6
0x17cc  ldstr    aSitedataRootma_0// "/SiteData/RootMaster"
0x17d1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17d6  isinst   [System.Xml]System.Xml.XmlElement
0x17db  stloc.s  7
0x17dd  ldloc.s  7
0x17df  ldstr    aPagepropsdirty// "PagePropsDirty"
0x17e4  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x17e9  ldstr    a1// "1"
0x17ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17f3  stloc.s  8
0x17f5  ldloc.s  7
0x17f7  ldstr    aPagecontentdir// "PageContentDirty"
0x17fc  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x1801  ldstr    a1// "1"
0x1806  call     bool [mscorlib]System.String::op_Equality(string, string)
0x180b  stloc.s  9
0x180d  ldloc.s  8
0x180f  brfalse.s loc_1819
0x1811  ldloc.2
0x1812  ldloc.s  7
0x1814  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::SetRootMasterSettings(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web, class [System.Xml]System.Xml.XmlElement elemRootMaster)
0x1819  ldloc.s  9
0x181b  brfalse  loc_18F6
0x1820  ldloc.s  6
0x1822  ldstr    aSitedataPage// "/SiteData/Page"
0x1827  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x182c  isinst   [System.Xml]System.Xml.XmlElement
0x1831  stloc.s  0xA
0x1833  ldloc.s  0xA
0x1835  ldstr    aUrl_0// "url"
0x183a  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x183f  stloc.s  0xB
0x1841  ldloc.s  0xA
0x1843  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x1848  isinst   [System.Xml]System.Xml.XmlCDataSection
0x184d  stloc.s  0xC
0x184f  ldloc.2
0x1850  ldloc.s  0xB
0x1852  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x1857  stloc.s  0xD
0x1859  ldloc.s  0xD
0x185b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x1860  brfalse  loc_18F0
0x1865  ldloc.s  0xD
0x1867  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x186c  ldstr    aMswhBkimageena// "mswh_BkImageEnabled"
0x1871  ldloc.s  0xA
0x1873  ldstr    aBkimageenabled// "BkImageEnabled"
0x1878  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x187d  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1882  ldloc.s  0xD
0x1884  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x1889  ldstr    aMswhBkimageurl// "mswh_BkImageURL"
0x188e  ldloc.s  0xA
0x1890  ldstr    aBkimageurl// "BkImageURL"
0x1895  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x189a  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x189f  ldloc.s  0xD
0x18a1  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x18a6  ldstr    aMswhBkimagepos// "mswh_BkImagePosition"
0x18ab  ldloc.s  0xA
0x18ad  ldstr    aBkimagepositio// "BkImagePosition"
0x18b2  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x18b7  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18bc  ldloc.s  0xD
0x18be  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x18c3  ldstr    aMswhBkimagerep// "mswh_BkImageRepeat"
0x18c8  ldloc.s  0xA
0x18ca  ldstr    aBkimagerepeat// "BkImageRepeat"
0x18cf  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x18d4  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18d9  ldloc.s  0xD
0x18db  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::Update()
0x18e0  ldloc.s  0xD
0x18e2  ldloc.s  0xC
0x18e4  callvirt instance string [System.Xml]System.Xml.XmlCharacterData::get_Data()
0x18e9  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::SetPageContent(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile file, string content)
0x18ee  br.s     loc_18F6
0x18f0  ldstr    aDeletedfile// "DeletedFile"
0x18f5  stloc.0
0x18f6  ldloc.2
0x18f7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::Update()
0x18fc  leave.s  loc_1908
0x18fe  ldloc.3
0x18ff  brfalse.s loc_1907
0x1901  ldloc.3
0x1902  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1907  endfinally
0x1908  leave.s  loc_1913
0x190a  pop
0x190b  ldstr    aFailure// "Failure"
0x1910  stloc.0
0x1911  leave.s  loc_1913
0x1913  ldloc.0
0x1914  ret
```
