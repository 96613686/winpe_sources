# Microsoft.SharePoint.Administration.SPProvisioningAssistant::.cctor

- ea: `0x3acec0`
- end: `0x3adcd2`
- name: `Microsoft.SharePoint.Administration.SPProvisioningAssistant::.cctor`
- size: `3602`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x3a8a10`
- `0x3a8a30`
- `0x3add30`
- `0x3add50`
- `0x3add70`
- `0x3add90`
- `0x3addb0`
- `0x3addd0`
- `0x3addf0`
- `0x3ade10`
- `0x3ade30`
- `0x3adf20`

## string_xrefs

- `0x3ad05b`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x3ad07b`: `application/vnd.openxmlformats-officedocument.wordprocessingml.template`
- `0x3ad1a3`: `application/vnd.oasis.opendocument.presentation`
- `0x3ad1c4`: `application/vnd.oasis.opendocument.spreadsheet`
- `0x3ad1e5`: `application/vnd.oasis.opendocument.text`
- `0x3ad0bc`: `application/vnd.openxmlformats-officedocument.presentationml.template`
- `0x3ad0fe`: `application/vnd.openxmlformats-officedocument.presentationml.slideshow`
- `0x3ad09b`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x3ad2ab`: `application/vnd.ms-visio.template`
- `0x3ad2cc`: `application/vnd.ms-visio.template.macroEnabled`
- `0x3acfbb`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
- `0x3ad03b`: `application/vnd.ms-excel.template.macroEnabled.12`
- `0x3ad01b`: `application/vnd.openxmlformats-officedocument.spreadsheetml.template`
- `0x3ad991`: `_controltemplates`
- `0x3acec0`: `16\config`
- `0x3ada22`: `16\template\layouts`
- `0x3ad908`: `14\template\layouts`
- `0x3adbe8`: `16\template\admin`
- `0x3ad84d`: `SecurityTokenServiceApplicationPool`
- `0x3acf29`: `/_vti_bin/sharedaccess.asmx`
- `0x3ad2ed`: `application/msaccess.template`
- `0x3ad3aa`: `.cachemanifest`
- `0x3ad3b3`: `text/cache-manifest`
- `0x3ad509`: `14\template\images`
- `0x3ad54b`: `16\template\images`
- `0x3ad58d`: `14\template\layouts\inc`
- `0x3ad5cf`: `16\template\layouts\inc`
- `0x3ad615`: `14\template\layouts\styles`
- `0x3ad65f`: `16\template\layouts\styles`
- `0x3ad6a9`: `14\template\layouts\clientbin`
- `0x3ad6f3`: `16\template\layouts\clientbin`
- `0x3ad9d6`: `16\template\layouts\clientbin`
- `0x3ad73d`: `16\template\layouts\fonts`
- `0x3ad985`: `/_controltemplates`
- `0x3ad99d`: `14\template\controltemplates`
- `0x3ada62`: `/_controltemplates/15`
- `0x3ada6e`: `_controltemplates/15`
- `0x3ada7a`: `16\template\controltemplates`
- `0x3adac2`: `16\template\identitymodel\login`
- `0x3adb16`: `16\template\identitymodel\windows`
- `0x3adca9`: `16\isapi\_vti_aut\author.dll`
- `0x3adcb2`: `16\isapi\_vti_adm\admin.dll`
- `0x3adcbb`: `16\isapi\shtml.dll`
- `0x3adcc4`: `16\isapi\owssvr.dll`

## pseudocode

```c

```

## disassembly

```asm
0x3acec0  ldstr    a16Config// "16\\config"
0x3acec5  stsfld   string Microsoft.SharePoint.Administration.SPProvisioningAssistant::WEB_CONFIG_FILESYSTEM_PATH
0x3aceca  ldc.i4.3
0x3acecb  newarr   [mscorlib]System.String
0x3aced0  stloc.s  0x18
0x3aced2  ldloc.s  0x18
0x3aced4  ldc.i4.0
0x3aced5  ldstr    aLayoutsScriptr// "/_layouts/scriptresx.ashx"
0x3aceda  stelem.ref
0x3acedb  ldloc.s  0x18
0x3acedd  ldc.i4.1
0x3acede  ldstr    aLayouts15Scrip// "/_layouts/15/scriptresx.ashx"
0x3acee3  stelem.ref
0x3acee4  ldloc.s  0x18
0x3acee6  ldc.i4.2
0x3acee7  ldstr    aLayouts15Preau// "/_layouts/15/preauth.ashx"
0x3aceec  stelem.ref
0x3aceed  ldloc.s  0x18
0x3aceef  stsfld   string[] Microsoft.SharePoint.Administration.SPProvisioningAssistant::s_AnonymousLayoutsRequests
0x3acef4  ldc.i4.3
0x3acef5  newarr   [mscorlib]System.String
0x3acefa  stloc.s  0x19
0x3acefc  ldloc.s  0x19
0x3acefe  ldc.i4.0
0x3aceff  ldstr    aFaviconIco// "/favicon.ico"
0x3acf04  stelem.ref
0x3acf05  ldloc.s  0x19
0x3acf07  ldc.i4.1
0x3acf08  ldstr    aWebresourceAxd_0// "/webresource.axd"
0x3acf0d  stelem.ref
0x3acf0e  ldloc.s  0x19
0x3acf10  ldc.i4.2
0x3acf11  ldstr    aScriptresource_3// "/scriptresource.axd"
0x3acf16  stelem.ref
0x3acf17  ldloc.s  0x19
0x3acf19  stsfld   string[] Microsoft.SharePoint.Administration.SPProvisioningAssistant::s_AnonymousRootRequests
0x3acf1e  ldc.i4.2
0x3acf1f  newarr   [mscorlib]System.String
0x3acf24  stloc.s  0x1A
0x3acf26  ldloc.s  0x1A
0x3acf28  ldc.i4.0
0x3acf29  ldstr    aVtiBinSharedac// "/_vti_bin/sharedaccess.asmx"
0x3acf2e  stelem.ref
0x3acf2f  ldloc.s  0x1A
0x3acf31  ldc.i4.1
0x3acf32  ldstr    aVtiBinPubliccd// "/_vti_bin/publiccdn.ashx"
0x3acf37  stelem.ref
0x3acf38  ldloc.s  0x1A
0x3acf3a  stsfld   string[] Microsoft.SharePoint.Administration.SPProvisioningAssistant::s_AnonymousVtiBinRequests
0x3acf3f  ldc.i4.5
0x3acf40  newarr   [mscorlib]System.String
0x3acf45  stloc.s  0x1B
0x3acf47  ldloc.s  0x1B
0x3acf49  ldc.i4.0
0x3acf4a  ldstr    aBasicauthentic// "basicAuthentication"
0x3acf4f  stelem.ref
0x3acf50  ldloc.s  0x1B
0x3acf52  ldc.i4.1
0x3acf53  ldstr    aClientcertific_0// "clientCertificateMappingAuthentication"
0x3acf58  stelem.ref
0x3acf59  ldloc.s  0x1B
0x3acf5b  ldc.i4.2
0x3acf5c  ldstr    aDigestauthenti// "digestAuthentication"
0x3acf61  stelem.ref
0x3acf62  ldloc.s  0x1B
0x3acf64  ldc.i4.3
0x3acf65  ldstr    aIisclientcerti// "iisClientCertificateMappingAuthenticati"...
0x3acf6a  stelem.ref
0x3acf6b  ldloc.s  0x1B
0x3acf6d  ldc.i4.4
0x3acf6e  ldstr    aWindowsauthent// "windowsAuthentication"
0x3acf73  stelem.ref
0x3acf74  ldloc.s  0x1B
0x3acf76  stsfld   string[] Microsoft.SharePoint.Administration.SPProvisioningAssistant::s_NonAnonymousAuthSections
0x3acf7b  ldc.i4.s 0x2A
0x3acf7d  newarr   string[]
0x3acf82  stloc.s  0x1C
0x3acf84  ldloc.s  0x1C
0x3acf86  ldc.i4.0
0x3acf87  ldc.i4.2
0x3acf88  newarr   [mscorlib]System.String
0x3acf8d  stloc.s  0x1D
0x3acf8f  ldloc.s  0x1D
0x3acf91  ldc.i4.0
0x3acf92  ldstr    aXlsb// ".xlsb"
0x3acf97  stelem.ref
0x3acf98  ldloc.s  0x1D
0x3acf9a  ldc.i4.1
0x3acf9b  ldstr    aApplicationVnd_42// "application/vnd.ms-excel.sheet.binary.m"...
0x3acfa0  stelem.ref
0x3acfa1  ldloc.s  0x1D
0x3acfa3  stelem.ref
0x3acfa4  ldloc.s  0x1C
0x3acfa6  ldc.i4.1
0x3acfa7  ldc.i4.2
0x3acfa8  newarr   [mscorlib]System.String
0x3acfad  stloc.s  0x1E
0x3acfaf  ldloc.s  0x1E
0x3acfb1  ldc.i4.0
0x3acfb2  ldstr    aXlsx// ".xlsx"
0x3acfb7  stelem.ref
0x3acfb8  ldloc.s  0x1E
0x3acfba  ldc.i4.1
0x3acfbb  ldstr    aApplicationVnd_44// "application/vnd.openxmlformats-officedo"...
0x3acfc0  stelem.ref
0x3acfc1  ldloc.s  0x1E
0x3acfc3  stelem.ref
0x3acfc4  ldloc.s  0x1C
0x3acfc6  ldc.i4.2
0x3acfc7  ldc.i4.2
0x3acfc8  newarr   [mscorlib]System.String
0x3acfcd  stloc.s  0x1F
0x3acfcf  ldloc.s  0x1F
0x3acfd1  ldc.i4.0
0x3acfd2  ldstr    aXlsm// ".xlsm"
0x3acfd7  stelem.ref
0x3acfd8  ldloc.s  0x1F
0x3acfda  ldc.i4.1
0x3acfdb  ldstr    aApplicationVnd_43// "application/vnd.ms-excel.sheet.macroEna"...
0x3acfe0  stelem.ref
0x3acfe1  ldloc.s  0x1F
0x3acfe3  stelem.ref
0x3acfe4  ldloc.s  0x1C
0x3acfe6  ldc.i4.3
0x3acfe7  ldc.i4.2
0x3acfe8  newarr   [mscorlib]System.String
0x3acfed  stloc.s  0x20
0x3acfef  ldloc.s  0x20
0x3acff1  ldc.i4.0
0x3acff2  ldstr    aXlam// ".xlam"
0x3acff7  stelem.ref
0x3acff8  ldloc.s  0x20
0x3acffa  ldc.i4.1
0x3acffb  ldstr    aApplicationVnd_41// "application/vnd.ms-excel.addin.macroEna"...
0x3ad000  stelem.ref
0x3ad001  ldloc.s  0x20
0x3ad003  stelem.ref
0x3ad004  ldloc.s  0x1C
0x3ad006  ldc.i4.4
0x3ad007  ldc.i4.2
0x3ad008  newarr   [mscorlib]System.String
0x3ad00d  stloc.s  0x21
0x3ad00f  ldloc.s  0x21
0x3ad011  ldc.i4.0
0x3ad012  ldstr    aXltx// ".xltx"
0x3ad017  stelem.ref
0x3ad018  ldloc.s  0x21
0x3ad01a  ldc.i4.1
0x3ad01b  ldstr    aApplicationVnd_46// "application/vnd.openxmlformats-officedo"...
0x3ad020  stelem.ref
0x3ad021  ldloc.s  0x21
0x3ad023  stelem.ref
0x3ad024  ldloc.s  0x1C
0x3ad026  ldc.i4.5
0x3ad027  ldc.i4.2
0x3ad028  newarr   [mscorlib]System.String
0x3ad02d  stloc.s  0x22
0x3ad02f  ldloc.s  0x22
0x3ad031  ldc.i4.0
0x3ad032  ldstr    aXltm// ".xltm"
0x3ad037  stelem.ref
0x3ad038  ldloc.s  0x22
0x3ad03a  ldc.i4.1
0x3ad03b  ldstr    aApplicationVnd_45// "application/vnd.ms-excel.template.macro"...
0x3ad040  stelem.ref
0x3ad041  ldloc.s  0x22
0x3ad043  stelem.ref
0x3ad044  ldloc.s  0x1C
0x3ad046  ldc.i4.6
0x3ad047  ldc.i4.2
0x3ad048  newarr   [mscorlib]System.String
0x3ad04d  stloc.s  0x23
0x3ad04f  ldloc.s  0x23
0x3ad051  ldc.i4.0
0x3ad052  ldstr    aDocx// ".docx"
0x3ad057  stelem.ref
0x3ad058  ldloc.s  0x23
0x3ad05a  ldc.i4.1
0x3ad05b  ldstr    aApplicationVnd_2// "application/vnd.openxmlformats-officedo"...
0x3ad060  stelem.ref
0x3ad061  ldloc.s  0x23
0x3ad063  stelem.ref
0x3ad064  ldloc.s  0x1C
0x3ad066  ldc.i4.7
0x3ad067  ldc.i4.2
0x3ad068  newarr   [mscorlib]System.String
0x3ad06d  stloc.s  0x24
0x3ad06f  ldloc.s  0x24
0x3ad071  ldc.i4.0
0x3ad072  ldstr    aDotx// ".dotx"
0x3ad077  stelem.ref
0x3ad078  ldloc.s  0x24
0x3ad07a  ldc.i4.1
0x3ad07b  ldstr    aApplicationVnd_4// "application/vnd.openxmlformats-officedo"...
0x3ad080  stelem.ref
0x3ad081  ldloc.s  0x24
0x3ad083  stelem.ref
0x3ad084  ldloc.s  0x1C
0x3ad086  ldc.i4.8
0x3ad087  ldc.i4.2
0x3ad088  newarr   [mscorlib]System.String
0x3ad08d  stloc.s  0x25
0x3ad08f  ldloc.s  0x25
0x3ad091  ldc.i4.0
0x3ad092  ldstr    aPptx// ".pptx"
0x3ad097  stelem.ref
0x3ad098  ldloc.s  0x25
0x3ad09a  ldc.i4.1
0x3ad09b  ldstr    aApplicationVnd_22// "application/vnd.openxmlformats-officedo"...
0x3ad0a0  stelem.ref
0x3ad0a1  ldloc.s  0x25
0x3ad0a3  stelem.ref
0x3ad0a4  ldloc.s  0x1C
0x3ad0a6  ldc.i4.s 9
0x3ad0a8  ldc.i4.2
0x3ad0a9  newarr   [mscorlib]System.String
0x3ad0ae  stloc.s  0x26
0x3ad0b0  ldloc.s  0x26
0x3ad0b2  ldc.i4.0
0x3ad0b3  ldstr    aPotx// ".potx"
0x3ad0b8  stelem.ref
0x3ad0b9  ldloc.s  0x26
0x3ad0bb  ldc.i4.1
0x3ad0bc  ldstr    aApplicationVnd_17// "application/vnd.openxmlformats-officedo"...
0x3ad0c1  stelem.ref
0x3ad0c2  ldloc.s  0x26
0x3ad0c4  stelem.ref
0x3ad0c5  ldloc.s  0x1C
0x3ad0c7  ldc.i4.s 0xA
0x3ad0c9  ldc.i4.2
0x3ad0ca  newarr   [mscorlib]System.String
0x3ad0cf  stloc.s  0x27
0x3ad0d1  ldloc.s  0x27
0x3ad0d3  ldc.i4.0
0x3ad0d4  ldstr    aPptm// ".pptm"
0x3ad0d9  stelem.ref
0x3ad0da  ldloc.s  0x27
0x3ad0dc  ldc.i4.1
0x3ad0dd  ldstr    aApplicationVnd_21// "application/vnd.ms-powerpoint.presentat"...
0x3ad0e2  stelem.ref
0x3ad0e3  ldloc.s  0x27
0x3ad0e5  stelem.ref
0x3ad0e6  ldloc.s  0x1C
0x3ad0e8  ldc.i4.s 0xB
0x3ad0ea  ldc.i4.2
0x3ad0eb  newarr   [mscorlib]System.String
0x3ad0f0  stloc.s  0x28
0x3ad0f2  ldloc.s  0x28
0x3ad0f4  ldc.i4.0
0x3ad0f5  ldstr    aPpsx// ".ppsx"
0x3ad0fa  stelem.ref
0x3ad0fb  ldloc.s  0x28
0x3ad0fd  ldc.i4.1
0x3ad0fe  ldstr    aApplicationVnd_20// "application/vnd.openxmlformats-officedo"...
0x3ad103  stelem.ref
0x3ad104  ldloc.s  0x28
0x3ad106  stelem.ref
0x3ad107  ldloc.s  0x1C
0x3ad109  ldc.i4.s 0xC
0x3ad10b  ldc.i4.2
0x3ad10c  newarr   [mscorlib]System.String
0x3ad111  stloc.s  0x29
0x3ad113  ldloc.s  0x29
0x3ad115  ldc.i4.0
0x3ad116  ldstr    aPpsm// ".ppsm"
0x3ad11b  stelem.ref
0x3ad11c  ldloc.s  0x29
0x3ad11e  ldc.i4.1
0x3ad11f  ldstr    aApplicationVnd_19// "application/vnd.ms-powerpoint.slideshow"...
0x3ad124  stelem.ref
0x3ad125  ldloc.s  0x29
0x3ad127  stelem.ref
0x3ad128  ldloc.s  0x1C
0x3ad12a  ldc.i4.s 0xD
0x3ad12c  ldc.i4.2
0x3ad12d  newarr   [mscorlib]System.String
0x3ad132  stloc.s  0x2A
0x3ad134  ldloc.s  0x2A
0x3ad136  ldc.i4.0
0x3ad137  ldstr    aPpam// ".ppam"
0x3ad13c  stelem.ref
0x3ad13d  ldloc.s  0x2A
0x3ad13f  ldc.i4.1
0x3ad140  ldstr    aApplicationVnd_18// "application/vnd.ms-powerpoint.addin.mac"...
0x3ad145  stelem.ref
0x3ad146  ldloc.s  0x2A
0x3ad148  stelem.ref
0x3ad149  ldloc.s  0x1C
0x3ad14b  ldc.i4.s 0xE
0x3ad14d  ldc.i4.2
0x3ad14e  newarr   [mscorlib]System.String
0x3ad153  stloc.s  0x2B
0x3ad155  ldloc.s  0x2B
0x3ad157  ldc.i4.0
0x3ad158  ldstr    aXps// ".xps"
0x3ad15d  stelem.ref
0x3ad15e  ldloc.s  0x2B
0x3ad160  ldc.i4.1
0x3ad161  ldstr    aApplicationVnd_47// "application/vnd.ms-xpsdocument"
0x3ad166  stelem.ref
  ... truncated ...
```
