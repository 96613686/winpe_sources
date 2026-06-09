# Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::.cctor

- ea: `0x16250`
- end: `0x16a56`
- name: `Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::.cctor`
- size: `2054`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xf90`
- `0xfa0`
- `0xfe0`

## string_xrefs

- `0x168db`: `Microsoft.Reporting.WebForms.Scripts.Common.js`
- `0x169e2`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.eot`
- `0x169f6`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.woff`
- `0x16a0a`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphs.ttf`
- `0x16a1e`: `Microsoft.Reporting.WebForms.Fonts.ReportingServicesGlyphssvg`
- `0x16264`: `image/svg+xml`
- `0x16278`: `image/svg+xml`
- `0x1628c`: `image/svg+xml`
- `0x162a0`: `image/svg+xml`
- `0x162b4`: `image/svg+xml`
- `0x162dc`: `image/svg+xml`
- `0x162f0`: `image/svg+xml`
- `0x16304`: `image/svg+xml`
- `0x16318`: `image/svg+xml`
- `0x1632c`: `image/svg+xml`
- `0x165c0`: `image/svg+xml`
- `0x165e8`: `image/svg+xml`
- `0x16610`: `image/svg+xml`
- `0x16a23`: `application/x-font-opentype`
- `0x16a32`: `Microsoft.Reporting.WebForms.Templates.InitTelemetry.js`
- `0x16a46`: `Microsoft.Reporting.WebForms.Templates.TrackPageView.js`

## pseudocode

```c

```

## disassembly

```asm
0x16250  newobj   instance void Microsoft.Reporting.Common.ResourceList::.ctor()
0x16255  stsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1625a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1625f  ldstr    aMicrosoftRepor_52// "Microsoft.Reporting.WebForms.Icons.Firs"...
0x16264  ldstr    aImageSvgXml// "image/svg+xml"
0x16269  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1626e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16273  ldstr    aMicrosoftRepor_53// "Microsoft.Reporting.WebForms.Icons.Back"
0x16278  ldstr    aImageSvgXml// "image/svg+xml"
0x1627d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16282  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16287  ldstr    aMicrosoftRepor_54// "Microsoft.Reporting.WebForms.Icons.Next"
0x1628c  ldstr    aImageSvgXml// "image/svg+xml"
0x16291  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16296  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1629b  ldstr    aMicrosoftRepor_55// "Microsoft.Reporting.WebForms.Icons.Last"
0x162a0  ldstr    aImageSvgXml// "image/svg+xml"
0x162a5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x162aa  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x162af  ldstr    aMicrosoftRepor_56// "Microsoft.Reporting.WebForms.Icons.Refr"...
0x162b4  ldstr    aImageSvgXml// "image/svg+xml"
0x162b9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x162be  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x162c3  ldstr    aMicrosoftRepor_57// "Microsoft.Reporting.WebForms.Icons.DocM"...
0x162c8  ldstr    aImageGif// "image/gif"
0x162cd  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x162d2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x162d7  ldstr    aMicrosoftRepor_58// "Microsoft.Reporting.WebForms.Icons.Prin"...
0x162dc  ldstr    aImageSvgXml// "image/svg+xml"
0x162e1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x162e6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x162eb  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x162f0  ldstr    aImageSvgXml// "image/svg+xml"
0x162f5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x162fa  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x162ff  ldstr    aMicrosoftRepor_60// "Microsoft.Reporting.WebForms.Icons.Find"...
0x16304  ldstr    aImageSvgXml// "image/svg+xml"
0x16309  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1630e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16313  ldstr    aMicrosoftRepor_61// "Microsoft.Reporting.WebForms.Icons.Righ"...
0x16318  ldstr    aImageSvgXml// "image/svg+xml"
0x1631d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16322  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16327  ldstr    aMicrosoftRepor_62// "Microsoft.Reporting.WebForms.Icons.Left"...
0x1632c  ldstr    aImageSvgXml// "image/svg+xml"
0x16331  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16336  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1633b  ldstr    aMicrosoftRepor_63// "Microsoft.Reporting.WebForms.Icons.Firs"...
0x16340  ldstr    aImageGif// "image/gif"
0x16345  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1634a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1634f  ldstr    aMicrosoftRepor_64// "Microsoft.Reporting.WebForms.Icons.Back"...
0x16354  ldstr    aImageGif// "image/gif"
0x16359  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1635e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16363  ldstr    aMicrosoftRepor_65// "Microsoft.Reporting.WebForms.Icons.Next"...
0x16368  ldstr    aImageGif// "image/gif"
0x1636d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16372  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16377  ldstr    aMicrosoftRepor_66// "Microsoft.Reporting.WebForms.Icons.Last"...
0x1637c  ldstr    aImageGif// "image/gif"
0x16381  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16386  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1638b  ldstr    aMicrosoftRepor_67// "Microsoft.Reporting.WebForms.Icons.Refr"...
0x16390  ldstr    aImageGif// "image/gif"
0x16395  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1639a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1639f  ldstr    aMicrosoftRepor_68// "Microsoft.Reporting.WebForms.Icons.Prin"...
0x163a4  ldstr    aImageGif// "image/gif"
0x163a9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x163ae  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x163b3  ldstr    aMicrosoftRepor_69// "Microsoft.Reporting.WebForms.Icons.Find"...
0x163b8  ldstr    aImageGif// "image/gif"
0x163bd  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x163c2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x163c7  ldstr    aMicrosoftRepor_70// "Microsoft.Reporting.WebForms.Icons.Find"...
0x163cc  ldstr    aImageGif// "image/gif"
0x163d1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x163d6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x163db  ldstr    aMicrosoftRepor_71// "Microsoft.Reporting.WebForms.Icons.Left"...
0x163e0  ldstr    aImageGif// "image/gif"
0x163e5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x163ea  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x163ef  ldstr    aMicrosoftRepor_72// "Microsoft.Reporting.WebForms.Icons.Firs"...
0x163f4  ldstr    aImageGif// "image/gif"
0x163f9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x163fe  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16403  ldstr    aMicrosoftRepor_73// "Microsoft.Reporting.WebForms.Icons.Prev"...
0x16408  ldstr    aImageGif// "image/gif"
0x1640d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16412  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16417  ldstr    aMicrosoftRepor_74// "Microsoft.Reporting.WebForms.Icons.Next"...
0x1641c  ldstr    aImageGif// "image/gif"
0x16421  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16426  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1642b  ldstr    aMicrosoftRepor_75// "Microsoft.Reporting.WebForms.Icons.Last"...
0x16430  ldstr    aImageGif// "image/gif"
0x16435  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1643a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1643f  ldstr    aMicrosoftRepor_76// "Microsoft.Reporting.WebForms.Icons.Refr"...
0x16444  ldstr    aImageGif// "image/gif"
0x16449  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1644e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16453  ldstr    aMicrosoftRepor_77// "Microsoft.Reporting.WebForms.Icons.Prin"...
0x16458  ldstr    aImageGif// "image/gif"
0x1645d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16462  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16467  ldstr    aMicrosoftRepor_78// "Microsoft.Reporting.WebForms.Icons.Atom"...
0x1646c  ldstr    aImageGif// "image/gif"
0x16471  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16476  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1647b  ldstr    aMicrosoftRepor_79// "Microsoft.Reporting.WebForms.Icons.Back"...
0x16480  ldstr    aImageGif// "image/gif"
0x16485  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1648a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1648f  ldstr    aMicrosoftRepor_80// "Microsoft.Reporting.WebForms.Icons.Expo"...
0x16494  ldstr    aImageGif// "image/gif"
0x16499  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1649e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x164a3  ldstr    aMicrosoftRepor_81// "Microsoft.Reporting.WebForms.Icons.Arro"...
0x164a8  ldstr    aImageGif// "image/gif"
0x164ad  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x164b2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x164b7  ldstr    aMicrosoftRepor_82// "Microsoft.Reporting.WebForms.Icons.Mult"...
0x164bc  ldstr    aImageGif// "image/gif"
0x164c1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x164c6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x164cb  ldstr    aMicrosoftRepor_83// "Microsoft.Reporting.WebForms.Icons.Spin"...
0x164d0  ldstr    aImageGif// "image/gif"
0x164d5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x164da  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x164df  ldstr    aMicrosoftRepor_38// "Microsoft.Reporting.WebForms.Icons.Hand"...
0x164e4  ldstr    aImageGif// "image/gif"
0x164e9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x164ee  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x164f3  ldstr    aMicrosoftRepor_39// "Microsoft.Reporting.WebForms.Icons.Hand"...
0x164f8  ldstr    aImageGif// "image/gif"
0x164fd  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16502  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16507  ldstr    aMicrosoftRepor_8// "Microsoft.Reporting.WebForms.Icons.docm"...
0x1650c  ldstr    aImagePng// "image/png"
0x16511  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16516  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1651b  ldstr    aMicrosoftRepor_84// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16520  ldstr    aImagePng// "image/png"
0x16525  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1652a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1652f  ldstr    aMicrosoftRepor_85// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16534  ldstr    aImagePng// "image/png"
0x16539  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1653e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16543  ldstr    aMicrosoftRepor_86// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16548  ldstr    aImagePng// "image/png"
0x1654d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16552  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16557  ldstr    aMicrosoftRepor_87// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x1655c  ldstr    aImagePng// "image/png"
0x16561  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16566  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1656b  ldstr    aMicrosoftRepor_88// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16570  ldstr    aImagePng// "image/png"
0x16575  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1657a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1657f  ldstr    aMicrosoftRepor_89// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16584  ldstr    aImagePng// "image/png"
0x16589  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1658e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16593  ldstr    aMicrosoftRepor_90// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x16598  ldstr    aImagePng// "image/png"
0x1659d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x165a2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x165a7  ldstr    aMicrosoftRepor_91// "Microsoft.Reporting.WebForms.Icons.Spli"...
0x165ac  ldstr    aImagePng// "image/png"
0x165b1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x165b6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x165bb  ldstr    aMicrosoftRepor_92// "Microsoft.Reporting.WebForms.Icons.Save"
0x165c0  ldstr    aImageSvgXml// "image/svg+xml"
0x165c5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x165ca  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x165cf  ldstr    aMicrosoftRepor_93// "Microsoft.Reporting.WebForms.Icons.Save"...
0x165d4  ldstr    aImageGif// "image/gif"
0x165d9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x165de  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x165e3  ldstr    aMicrosoftRepor_94// "Microsoft.Reporting.WebForms.Icons.Arro"...
0x165e8  ldstr    aImageSvgXml// "image/svg+xml"
0x165ed  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x165f2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x165f7  ldstr    aMicrosoftRepor_95// "Microsoft.Reporting.WebForms.Icons.Arro"...
0x165fc  ldstr    aImageGif// "image/gif"
0x16601  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16606  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1660b  ldstr    aMicrosoftRepor_96// "Microsoft.Reporting.WebForms.Icons.Powe"...
0x16610  ldstr    aImageSvgXml// "image/svg+xml"
0x16615  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1661a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1661f  ldstr    aMicrosoftRepor_97// "Microsoft.Reporting.WebForms.Icons.Html"...
0x16624  ldstr    aImageGif// "image/gif"
0x16629  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1662e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16633  ldstr    aMicrosoftRepor_98// "Microsoft.Reporting.WebForms.Icons.Html"...
0x16638  ldstr    aImageGif// "image/gif"
0x1663d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16642  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16647  ldstr    aMicrosoftRepor_99// "Microsoft.Reporting.WebForms.Icons.Html"...
0x1664c  ldstr    aImageGif// "image/gif"
0x16651  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16656  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1665b  ldstr    aMicrosoftRepor_100// "Microsoft.Reporting.WebForms.Icons.Html"...
0x16660  ldstr    aImageGif// "image/gif"
0x16665  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1666a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1666f  ldstr    aMicrosoftRepor_4// "Microsoft.Reporting.WebForms.Icons.Prin"...
0x16674  ldstr    aImageGif// "image/gif"
0x16679  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1667e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16683  ldstr    aMicrosoftRepor_101// "Microsoft.Reporting.WebForms.Icons.Clos"...
0x16688  ldstr    aImagePng// "image/png"
0x1668d  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16692  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16697  ldstr    aMicrosoftRepor_102// "Microsoft.Reporting.WebForms.Icons.Clos"...
0x1669c  ldstr    aImagePng// "image/png"
0x166a1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x166a6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x166ab  ldstr    aMicrosoftRepor_103// "Microsoft.Reporting.WebForms.Icons.Spin"...
0x166b0  ldstr    aImagePng// "image/png"
0x166b5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x166ba  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x166bf  ldstr    aMicrosoftRepor_104// "Microsoft.Reporting.WebForms.Styles.Web"...
0x166c4  ldstr    aTextCss// "text/css"
0x166c9  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x166ce  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x166d3  ldstr    aMicrosoftRepor_105// "Microsoft.Reporting.WebForms.Styles.Htm"...
0x166d8  ldstr    aTextCss// "text/css"
0x166dd  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x166e2  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x166e7  ldstr    aMicrosoftRepor_106// "Microsoft.Reporting.WebForms.Styles.Htm"...
0x166ec  ldstr    aTextCss// "text/css"
0x166f1  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x166f6  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x166fb  ldstr    aMicrosoftRepor_107// "Microsoft.Reporting.WebForms.Styles.Htm"...
0x16700  ldstr    aTextCss// "text/css"
0x16705  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1670a  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1670f  ldstr    aMicrosoftRepor_108// "Microsoft.Reporting.WebForms.Styles.Rep"...
0x16714  ldstr    aTextCss// "text/css"
0x16719  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x1671e  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16723  ldstr    aMicrosoftRepor_26// "Microsoft.Reporting.WebForms.Scripts.Re"...
0x16728  ldstr    aApplicationJav// "application/javascript"
0x1672d  ldc.i4.1
0x1672e  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x16733  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16738  ldstr    aMicrosoftRepor_46// "Microsoft.Reporting.WebForms.Scripts.RS"...
0x1673d  ldstr    aApplicationJav// "application/javascript"
0x16742  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType)
0x16747  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1674c  ldstr    aMicrosoftRepor_30// "Microsoft.Reporting.WebForms.Scripts.As"...
0x16751  ldstr    aApplicationJav// "application/javascript"
0x16756  ldc.i4.1
0x16757  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x1675c  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16761  ldstr    aMicrosoftRepor_31// "Microsoft.Reporting.WebForms.Scripts.Do"...
0x16766  ldstr    aApplicationJav// "application/javascript"
0x1676b  ldc.i4.1
0x1676c  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x16771  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x16776  ldstr    aMicrosoftRepor_16// "Microsoft.Reporting.WebForms.Scripts.In"...
0x1677b  ldstr    aApplicationJav// "application/javascript"
0x16780  ldc.i4.1
0x16781  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x16786  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x1678b  ldstr    aMicrosoftRepor_21// "Microsoft.Reporting.WebForms.Scripts.Se"...
0x16790  ldstr    aApplicationJav// "application/javascript"
0x16795  ldc.i4.1
0x16796  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x1679b  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x167a0  ldstr    aMicrosoftRepor_2// "Microsoft.Reporting.WebForms.Scripts.Br"...
0x167a5  ldstr    aApplicationJav// "application/javascript"
0x167aa  ldc.i4.1
0x167ab  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x167b0  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x167b5  ldstr    aMicrosoftRepor_13// "Microsoft.Reporting.WebForms.Scripts.To"...
0x167ba  ldstr    aApplicationJav// "application/javascript"
0x167bf  ldc.i4.1
0x167c0  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x167c5  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x167ca  ldstr    aMicrosoftRepor_14// "Microsoft.Reporting.WebForms.Scripts.Ho"...
0x167cf  ldstr    aApplicationJav// "application/javascript"
0x167d4  ldc.i4.1
0x167d5  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x167da  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x167df  ldstr    aMicrosoftRepor_15// "Microsoft.Reporting.WebForms.Scripts.St"...
0x167e4  ldstr    aApplicationJav// "application/javascript"
0x167e9  ldc.i4.1
0x167ea  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
0x167ef  ldsfld   class Microsoft.Reporting.Common.ResourceList Microsoft.Reporting.WebForms.ReportViewerEmbeddedResources::m_resourceList
0x167f4  ldstr    aMicrosoftRepor_22// "Microsoft.Reporting.WebForms.Scripts.Sc"...
0x167f9  ldstr    aApplicationJav// "application/javascript"
0x167fe  ldc.i4.1
0x167ff  callvirt instance void Microsoft.Reporting.Common.ResourceList::Add(string name, string mimeType, bool hasDebugMode)
  ... truncated ...
```
