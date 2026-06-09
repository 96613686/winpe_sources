# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::BuildLocationXml

- ea: `0xa570`
- end: `0xa9f2`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::BuildLocationXml`
- size: `1154`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa380`
- `0xa4b0`

## callees

- `0xa570`
- `0xab70`

## string_xrefs

- `0xa588`: `http://schemas.microsoft.com/search/local/ws/rest/v1`
- `0xa98e`: `BuildLocationXML`
- `0xa9be`: `BingMaps.BuildLocationXML`
- `0xa9c3`: `BuildLocationXML failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa570  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xa575  stloc.0
0xa576  ldarg.0
0xa577  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa57c  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa581  stloc.1
0xa582  ldloc.1
0xa583  ldstr    aB// "b"
0xa588  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/search/loc"...
0xa58d  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa592  ldarg.0
0xa593  ldstr    aBResponseBReso// "//b:Response/b:ResourceSets/b:ResourceS"...
0xa598  ldloc.1
0xa599  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa59e  stloc.2
0xa59f  ldloc.0
0xa5a0  ldstr    aLocations// "<locations>"
0xa5a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa5aa  pop
0xa5ab  ldloc.2
0xa5ac  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa5b1  stloc.s  5
0xa5b3  br       loc_A952
0xa5b8  ldloc.s  5
0xa5ba  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa5bf  castclass [System.Xml]System.Xml.XmlNode
0xa5c4  stloc.3
0xa5c5  ldloc.0
0xa5c6  ldstr    aLocation// "<location"
0xa5cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa5d0  pop
0xa5d1  ldloc.0
0xa5d2  ldstr    aScore// " Score=\""
0xa5d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa5dc  pop
0xa5dd  ldloc.0
0xa5de  ldc.i4.s 9
0xa5e0  stloc.s  6
0xa5e2  ldloca.s 6
0xa5e4  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa5e9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa5ee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa5f3  pop
0xa5f4  ldloc.0
0xa5f5  ldstr    asc_25ADE// "\""
0xa5fa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa5ff  pop
0xa600  ldloc.0
0xa601  ldstr    aFormattedaddre// " FormattedAddress=\""
0xa606  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa60b  pop
0xa60c  ldloc.0
0xa60d  ldloc.3
0xa60e  ldstr    aBAddressBForma// "b:Address/b:FormattedAddress"
0xa613  ldloc.1
0xa614  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa619  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa61e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa623  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xa628  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa62d  pop
0xa62e  ldloc.0
0xa62f  ldstr    asc_25ADE// "\""
0xa634  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa639  pop
0xa63a  ldloc.0
0xa63b  ldstr    aAddressline// " AddressLine=\""
0xa640  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa645  pop
0xa646  ldloc.0
0xa647  ldloc.3
0xa648  ldstr    aBAddressBAddre// "b:Address/b:AddressLine"
0xa64d  ldloc.1
0xa64e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa653  ldstr    asc_21858// " "
0xa658  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa65d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa662  pop
0xa663  ldloc.0
0xa664  ldstr    asc_25ADE// "\""
0xa669  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa66e  pop
0xa66f  ldloc.0
0xa670  ldstr    aPrimarycity// " PrimaryCity=\""
0xa675  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa67a  pop
0xa67b  ldloc.0
0xa67c  ldloc.3
0xa67d  ldstr    aBAddressBLocal// "b:Address/b:Locality"
0xa682  ldloc.1
0xa683  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa688  ldstr    asc_21858// " "
0xa68d  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa692  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa697  pop
0xa698  ldloc.0
0xa699  ldstr    asc_25ADE// "\""
0xa69e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa6a3  pop
0xa6a4  ldloc.0
0xa6a5  ldstr    aSecondarycity// " SecondaryCity=\""
0xa6aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa6af  pop
0xa6b0  ldloc.0
0xa6b1  ldloc.3
0xa6b2  ldstr    aBAddressBAdmin// "b:Address/b:AdminDistrict2"
0xa6b7  ldloc.1
0xa6b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa6bd  ldstr    asc_21858// " "
0xa6c2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa6c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa6cc  pop
0xa6cd  ldloc.0
0xa6ce  ldstr    asc_25ADE// "\""
0xa6d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa6d8  pop
0xa6d9  ldloc.0
0xa6da  ldstr    aSubdivision// " Subdivision=\""
0xa6df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa6e4  pop
0xa6e5  ldloc.0
0xa6e6  ldloc.3
0xa6e7  ldstr    aBAddressBAdmin_0// "b:Address/b:AdminDistrict"
0xa6ec  ldloc.1
0xa6ed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa6f2  ldstr    asc_21858// " "
0xa6f7  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa6fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa701  pop
0xa702  ldloc.0
0xa703  ldstr    asc_25ADE// "\""
0xa708  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa70d  pop
0xa70e  ldloc.0
0xa70f  ldstr    aPostalcode// " PostalCode=\""
0xa714  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa719  pop
0xa71a  ldloc.0
0xa71b  ldloc.3
0xa71c  ldstr    aBAddressBPosta// "b:Address/b:PostalCode"
0xa721  ldloc.1
0xa722  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa727  ldstr    asc_21858// " "
0xa72c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa731  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa736  pop
0xa737  ldloc.0
0xa738  ldstr    asc_25ADE// "\""
0xa73d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa742  pop
0xa743  ldloc.0
0xa744  ldstr    aCountryregion_0// " CountryRegion=\""
0xa749  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa74e  pop
0xa74f  ldloc.0
0xa750  ldloc.3
0xa751  ldstr    aBAddressBCount// "b:Address/b:CountryRegion"
0xa756  ldloc.1
0xa757  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa75c  ldstr    asc_21858// " "
0xa761  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::ValidateNodeValue(class [System.Xml]System.Xml.XmlNode nodeToFind, string defultValue)
0xa766  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa76b  pop
0xa76c  ldloc.0
0xa76d  ldstr    asc_25ADE// "\""
0xa772  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa777  pop
0xa778  ldloc.0
0xa779  ldstr    aLatitude// " Latitude=\""
0xa77e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa783  pop
0xa784  ldloc.0
0xa785  ldloc.3
0xa786  ldstr    aBPointBLatitud// "b:Point/b:Latitude"
0xa78b  ldloc.1
0xa78c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa791  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa796  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa79b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7a0  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa7a5  stloc.s  7
0xa7a7  ldloca.s 7
0xa7a9  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa7ae  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa7b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7b8  pop
0xa7b9  ldloc.0
0xa7ba  ldstr    asc_25ADE// "\""
0xa7bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7c4  pop
0xa7c5  ldloc.0
0xa7c6  ldstr    aLongitude// " Longitude=\""
0xa7cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7d0  pop
0xa7d1  ldloc.0
0xa7d2  ldloc.3
0xa7d3  ldstr    aBPointBLongitu// "b:Point/b:Longitude"
0xa7d8  ldloc.1
0xa7d9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa7de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa7e3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa7e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7ed  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa7f2  stloc.s  8
0xa7f4  ldloca.s 8
0xa7f6  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa7fb  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa800  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa805  pop
0xa806  ldloc.0
0xa807  ldstr    asc_25ADE// "\""
0xa80c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa811  pop
0xa812  ldloc.0
0xa813  ldstr    aNorthlatitude// " NorthLatitude=\""
0xa818  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa81d  pop
0xa81e  ldloc.0
0xa81f  ldloc.3
0xa820  ldstr    aBBoundingboxBN// "b:BoundingBox/b:NorthLatitude"
0xa825  ldloc.1
0xa826  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa82b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa830  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa835  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa83a  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa83f  stloc.s  9
0xa841  ldloca.s 9
0xa843  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa848  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa84d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa852  pop
0xa853  ldloc.0
0xa854  ldstr    asc_25ADE// "\""
0xa859  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa85e  pop
0xa85f  ldloc.0
0xa860  ldstr    aEastlongitude// " EastLongitude=\""
0xa865  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa86a  pop
0xa86b  ldloc.0
0xa86c  ldloc.3
0xa86d  ldstr    aBBoundingboxBE// "b:BoundingBox/b:EastLongitude"
0xa872  ldloc.1
0xa873  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa878  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa87d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa882  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa887  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa88c  stloc.s  0xA
0xa88e  ldloca.s 0xA
0xa890  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa895  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa89a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa89f  pop
0xa8a0  ldloc.0
0xa8a1  ldstr    asc_25ADE// "\""
0xa8a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8ab  pop
0xa8ac  ldloc.0
0xa8ad  ldstr    aSouthlatitude// " SouthLatitude=\""
0xa8b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8b7  pop
0xa8b8  ldloc.0
0xa8b9  ldloc.3
0xa8ba  ldstr    aBBoundingboxBS// "b:BoundingBox/b:SouthLatitude"
0xa8bf  ldloc.1
0xa8c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa8c5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa8ca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa8cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8d4  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa8d9  stloc.s  0xB
0xa8db  ldloca.s 0xB
0xa8dd  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa8e2  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa8e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8ec  pop
0xa8ed  ldloc.0
0xa8ee  ldstr    asc_25ADE// "\""
0xa8f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8f8  pop
0xa8f9  ldloc.0
0xa8fa  ldstr    aWestlongitude// " WestLongitude=\""
0xa8ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa904  pop
0xa905  ldloc.0
0xa906  ldloc.3
0xa907  ldstr    aBBoundingboxBS// "b:BoundingBox/b:SouthLatitude"
0xa90c  ldloc.1
0xa90d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa912  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa917  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa91c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa921  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0xa926  stloc.s  0xC
0xa928  ldloca.s 0xC
0xa92a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::smXMLNumericCI
0xa92f  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xa934  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
  ... truncated ...
```
