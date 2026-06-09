# Microsoft.SharePoint.Administration.SPMimeTypeSet::GetDefaultAllowedInlineDownloadedMimeTypes

- ea: `0x2cce20`
- end: `0x2cd647`
- name: `Microsoft.SharePoint.Administration.SPMimeTypeSet::GetDefaultAllowedInlineDownloadedMimeTypes`
- size: `2087`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x31ec90`

## callees

- `0x2ccd20`
- `0x2cce20`

## string_xrefs

- `0x2cce6d`: `application/msaccess`
- `0x2cd0fd`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x2cd091`: `application/vnd.ms-word.template.macroEnabled.12`
- `0x2cd106`: `application/vnd.openxmlformats-officedocument.wordprocessingml.template`
- `0x2cd550`: `text/x-component`
- `0x2cce65`: `application/ms-infopath.xml`
- `0x2cd1d5`: `application/x-msaccess`
- `0x2cd0ac`: `application/vnd.oasis.opendocument.presentation`
- `0x2cd0b5`: `application/vnd.oasis.opendocument.spreadsheet`
- `0x2cd0be`: `application/vnd.oasis.opendocument.text`
- `0x2cd025`: `application/vnd.ms-powerpoint.template.macroEnabled.12`
- `0x2cd0e2`: `application/vnd.openxmlformats-officedocument.presentationml.template`
- `0x2cd0d9`: `application/vnd.openxmlformats-officedocument.presentationml.slideshow`
- `0x2cd0c7`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x2cd0d0`: `application/vnd.openxmlformats-officedocument.presentationml.slide`
- `0x2cd05b`: `application/vnd.ms-visio.template`
- `0x2cd064`: `application/vnd.ms-visio.template.macroEnabled`
- `0x2cd22f`: `application/x-mswrite`
- `0x2cd0eb`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
- `0x2ccf71`: `application/vnd.ms-excel.template.macroEnabled.12`
- `0x2cd0f4`: `application/vnd.openxmlformats-officedocument.spreadsheetml.template`
- `0x2cd13c`: `application/x-compress`
- `0x2ccf4d`: `application/vnd.ms-excel.macroEnabledTemplate.12`
- `0x2ccf68`: `application/vnd.ms-excel.template.12`
- `0x2cd01c`: `application/vnd.ms-powerpoint.template.12`
- `0x2cd088`: `application/vnd.ms-word.template.12`
- `0x2cd196`: `application/x-miva-compiled`
- `0x2cd1a8`: `application/x-ms-manifest`
- `0x2cd1b1`: `application/x-ms-reader`
- `0x2cd3b8`: `audio/x-pn-realaudio-plugin`

## pseudocode

```c

```

## disassembly

```asm
0x2cce20  newobj   instance void Microsoft.SharePoint.Administration.SPMimeTypeSet::.ctor()
0x2cce25  stloc.0
0x2cce26  ldloc.0
0x2cce27  stloc.1
0x2cce28  ldc.i4   0xCA
0x2cce2d  newarr   [mscorlib]System.String
0x2cce32  stloc.3
0x2cce33  ldloc.3
0x2cce34  ldc.i4.0
0x2cce35  ldstr    aApplicationDir// "application/directx"
0x2cce3a  stelem.ref
0x2cce3b  ldloc.3
0x2cce3c  ldc.i4.1
0x2cce3d  ldstr    aApplicationEnv// "application/envoy"
0x2cce42  stelem.ref
0x2cce43  ldloc.3
0x2cce44  ldc.i4.2
0x2cce45  ldstr    aApplicationFra// "application/fractals"
0x2cce4a  stelem.ref
0x2cce4b  ldloc.3
0x2cce4c  ldc.i4.3
0x2cce4d  ldstr    aApplicationInt// "application/internet-property-stream"
0x2cce52  stelem.ref
0x2cce53  ldloc.3
0x2cce54  ldc.i4.4
0x2cce55  ldstr    aApplicationLiq// "application/liquidmotion"
0x2cce5a  stelem.ref
0x2cce5b  ldloc.3
0x2cce5c  ldc.i4.5
0x2cce5d  ldstr    aApplicationMac// "application/mac-binhex40"
0x2cce62  stelem.ref
0x2cce63  ldloc.3
0x2cce64  ldc.i4.6
0x2cce65  ldstr    aApplicationMsI// "application/ms-infopath.xml"
0x2cce6a  stelem.ref
0x2cce6b  ldloc.3
0x2cce6c  ldc.i4.7
0x2cce6d  ldstr    aApplicationMsa// "application/msaccess"
0x2cce72  stelem.ref
0x2cce73  ldloc.3
0x2cce74  ldc.i4.8
0x2cce75  ldstr    aApplicationMsw// "application/msword"
0x2cce7a  stelem.ref
0x2cce7b  ldloc.3
0x2cce7c  ldc.i4.s 9
0x2cce7e  ldstr    aApplicationOda// "application/oda"
0x2cce83  stelem.ref
0x2cce84  ldloc.3
0x2cce85  ldc.i4.s 0xA
0x2cce87  ldstr    aApplicationOgg// "application/ogg"
0x2cce8c  stelem.ref
0x2cce8d  ldloc.3
0x2cce8e  ldc.i4.s 0xB
0x2cce90  ldstr    aApplicationOle_0// "application/oleobject"
0x2cce95  stelem.ref
0x2cce96  ldloc.3
0x2cce97  ldc.i4.s 0xC
0x2cce99  ldstr    aApplicationOne// "application/onenote"
0x2cce9e  stelem.ref
0x2cce9f  ldloc.3
0x2ccea0  ldc.i4.s 0xD
0x2ccea2  ldstr    aApplicationPdf// "application/pdf"
0x2ccea7  stelem.ref
0x2ccea8  ldloc.3
0x2ccea9  ldc.i4.s 0xE
0x2cceab  ldstr    aApplicationPic// "application/pics-rules"
0x2cceb0  stelem.ref
0x2cceb1  ldloc.3
0x2cceb2  ldc.i4.s 0xF
0x2cceb4  ldstr    aApplicationPkc// "application/pkcs10"
0x2cceb9  stelem.ref
0x2cceba  ldloc.3
0x2ccebb  ldc.i4.s 0x10
0x2ccebd  ldstr    aApplicationPkc_0// "application/pkcs7-mime"
0x2ccec2  stelem.ref
0x2ccec3  ldloc.3
0x2ccec4  ldc.i4.s 0x11
0x2ccec6  ldstr    aApplicationPkc_1// "application/pkcs7-signature"
0x2ccecb  stelem.ref
0x2ccecc  ldloc.3
0x2ccecd  ldc.i4.s 0x12
0x2ccecf  ldstr    aApplicationPki// "application/pkix-crl"
0x2cced4  stelem.ref
0x2cced5  ldloc.3
0x2cced6  ldc.i4.s 0x13
0x2cced8  ldstr    aApplicationPos// "application/postscript"
0x2ccedd  stelem.ref
0x2ccede  ldloc.3
0x2ccedf  ldc.i4.s 0x14
0x2ccee1  ldstr    aApplicationPpd// "application/ppdf"
0x2ccee6  stelem.ref
0x2ccee7  ldloc.3
0x2ccee8  ldc.i4.s 0x15
0x2cceea  ldstr    aApplicationRtf// "application/rtf"
0x2cceef  stelem.ref
0x2ccef0  ldloc.3
0x2ccef1  ldc.i4.s 0x16
0x2ccef3  ldstr    aApplicationSet// "application/set-payment-initiation"
0x2ccef8  stelem.ref
0x2ccef9  ldloc.3
0x2ccefa  ldc.i4.s 0x17
0x2ccefc  ldstr    aApplicationSet_0// "application/set-registration-initiation"
0x2ccf01  stelem.ref
0x2ccf02  ldloc.3
0x2ccf03  ldc.i4.s 0x18
0x2ccf05  ldstr    aApplicationStr// "application/streamingmedia"
0x2ccf0a  stelem.ref
0x2ccf0b  ldloc.3
0x2ccf0c  ldc.i4.s 0x19
0x2ccf0e  ldstr    aApplicationVnd_6// "application/vnd.fdf"
0x2ccf13  stelem.ref
0x2ccf14  ldloc.3
0x2ccf15  ldc.i4.s 0x1A
0x2ccf17  ldstr    aApplicationVnd_0// "application/vnd.ms-excel"
0x2ccf1c  stelem.ref
0x2ccf1d  ldloc.3
0x2ccf1e  ldc.i4.s 0x1B
0x2ccf20  ldstr    aApplicationVnd_48// "application/vnd.ms-excel.12"
0x2ccf25  stelem.ref
0x2ccf26  ldloc.3
0x2ccf27  ldc.i4.s 0x1C
0x2ccf29  ldstr    aApplicationVnd_49// "application/vnd.ms-excel.addin.12"
0x2ccf2e  stelem.ref
0x2ccf2f  ldloc.3
0x2ccf30  ldc.i4.s 0x1D
0x2ccf32  ldstr    aApplicationVnd_41// "application/vnd.ms-excel.addin.macroEna"...
0x2ccf37  stelem.ref
0x2ccf38  ldloc.3
0x2ccf39  ldc.i4.s 0x1E
0x2ccf3b  ldstr    aApplicationVnd_50// "application/vnd.ms-excel.binary.12"
0x2ccf40  stelem.ref
0x2ccf41  ldloc.3
0x2ccf42  ldc.i4.s 0x1F
0x2ccf44  ldstr    aApplicationVnd_51// "application/vnd.ms-excel.macroEnabled.1"...
0x2ccf49  stelem.ref
0x2ccf4a  ldloc.3
0x2ccf4b  ldc.i4.s 0x20
0x2ccf4d  ldstr    aApplicationVnd_52// "application/vnd.ms-excel.macroEnabledTe"...
0x2ccf52  stelem.ref
0x2ccf53  ldloc.3
0x2ccf54  ldc.i4.s 0x21
0x2ccf56  ldstr    aApplicationVnd_42// "application/vnd.ms-excel.sheet.binary.m"...
0x2ccf5b  stelem.ref
0x2ccf5c  ldloc.3
0x2ccf5d  ldc.i4.s 0x22
0x2ccf5f  ldstr    aApplicationVnd_43// "application/vnd.ms-excel.sheet.macroEna"...
0x2ccf64  stelem.ref
0x2ccf65  ldloc.3
0x2ccf66  ldc.i4.s 0x23
0x2ccf68  ldstr    aApplicationVnd_53// "application/vnd.ms-excel.template.12"
0x2ccf6d  stelem.ref
0x2ccf6e  ldloc.3
0x2ccf6f  ldc.i4.s 0x24
0x2ccf71  ldstr    aApplicationVnd_45// "application/vnd.ms-excel.template.macro"...
0x2ccf76  stelem.ref
0x2ccf77  ldloc.3
0x2ccf78  ldc.i4.s 0x25
0x2ccf7a  ldstr    aApplicationVnd_54// "application/vnd.ms-office.calx"
0x2ccf7f  stelem.ref
0x2ccf80  ldloc.3
0x2ccf81  ldc.i4.s 0x26
0x2ccf83  ldstr    aApplicationVnd_28// "application/vnd.ms-officetheme"
0x2ccf88  stelem.ref
0x2ccf89  ldloc.3
0x2ccf8a  ldc.i4.s 0x27
0x2ccf8c  ldstr    aApplicationVnd_55// "application/vnd.ms-outlook"
0x2ccf91  stelem.ref
0x2ccf92  ldloc.3
0x2ccf93  ldc.i4.s 0x28
0x2ccf95  ldstr    aApplicationVnd_56// "application/vnd.ms-pki.certstore"
0x2ccf9a  stelem.ref
0x2ccf9b  ldloc.3
0x2ccf9c  ldc.i4.s 0x29
0x2ccf9e  ldstr    aApplicationVnd_57// "application/vnd.ms-pki.pko"
0x2ccfa3  stelem.ref
0x2ccfa4  ldloc.3
0x2ccfa5  ldc.i4.s 0x2A
0x2ccfa7  ldstr    aApplicationVnd_58// "application/vnd.ms-pki.seccat"
0x2ccfac  stelem.ref
0x2ccfad  ldloc.3
0x2ccfae  ldc.i4.s 0x2B
0x2ccfb0  ldstr    aApplicationVnd_59// "application/vnd.ms-pki.stl"
0x2ccfb5  stelem.ref
0x2ccfb6  ldloc.3
0x2ccfb7  ldc.i4.s 0x2C
0x2ccfb9  ldstr    aApplicationVnd_15// "application/vnd.ms-powerpoint"
0x2ccfbe  stelem.ref
0x2ccfbf  ldloc.3
0x2ccfc0  ldc.i4.s 0x2D
0x2ccfc2  ldstr    aApplicationVnd_60// "application/vnd.ms-powerpoint.12"
0x2ccfc7  stelem.ref
0x2ccfc8  ldloc.3
0x2ccfc9  ldc.i4.s 0x2E
0x2ccfcb  ldstr    aApplicationVnd_61// "application/vnd.ms-powerpoint.addin.12"
0x2ccfd0  stelem.ref
0x2ccfd1  ldloc.3
0x2ccfd2  ldc.i4.s 0x2F
0x2ccfd4  ldstr    aApplicationVnd_18// "application/vnd.ms-powerpoint.addin.mac"...
0x2ccfd9  stelem.ref
0x2ccfda  ldloc.3
0x2ccfdb  ldc.i4.s 0x30
0x2ccfdd  ldstr    aApplicationVnd_62// "application/vnd.ms-powerpoint.macroEnab"...
0x2ccfe2  stelem.ref
0x2ccfe3  ldloc.3
0x2ccfe4  ldc.i4.s 0x31
0x2ccfe6  ldstr    aApplicationVnd_63// "application/vnd.ms-powerpoint.presentat"...
0x2ccfeb  stelem.ref
0x2ccfec  ldloc.3
0x2ccfed  ldc.i4.s 0x32
0x2ccfef  ldstr    aApplicationVnd_21// "application/vnd.ms-powerpoint.presentat"...
0x2ccff4  stelem.ref
0x2ccff5  ldloc.3
0x2ccff6  ldc.i4.s 0x33
0x2ccff8  ldstr    aApplicationVnd_64// "application/vnd.ms-powerpoint.show.12"
0x2ccffd  stelem.ref
0x2ccffe  ldloc.3
0x2ccfff  ldc.i4.s 0x34
0x2cd001  ldstr    aApplicationVnd_65// "application/vnd.ms-powerpoint.show.macr"...
0x2cd006  stelem.ref
0x2cd007  ldloc.3
0x2cd008  ldc.i4.s 0x35
0x2cd00a  ldstr    aApplicationVnd_24// "application/vnd.ms-powerpoint.slide.mac"...
0x2cd00f  stelem.ref
0x2cd010  ldloc.3
0x2cd011  ldc.i4.s 0x36
0x2cd013  ldstr    aApplicationVnd_19// "application/vnd.ms-powerpoint.slideshow"...
0x2cd018  stelem.ref
0x2cd019  ldloc.3
0x2cd01a  ldc.i4.s 0x37
0x2cd01c  ldstr    aApplicationVnd_66// "application/vnd.ms-powerpoint.template."...
0x2cd021  stelem.ref
0x2cd022  ldloc.3
0x2cd023  ldc.i4.s 0x38
0x2cd025  ldstr    aApplicationVnd_16// "application/vnd.ms-powerpoint.template."...
0x2cd02a  stelem.ref
0x2cd02b  ldloc.3
0x2cd02c  ldc.i4.s 0x39
0x2cd02e  ldstr    aApplicationVnd_8// "application/vnd.ms-project"
0x2cd033  stelem.ref
0x2cd034  ldloc.3
0x2cd035  ldc.i4.s 0x3A
0x2cd037  ldstr    aApplicationVnd_31// "application/vnd.ms-visio.drawing"
0x2cd03c  stelem.ref
0x2cd03d  ldloc.3
0x2cd03e  ldc.i4.s 0x3B
0x2cd040  ldstr    aApplicationVnd_32// "application/vnd.ms-visio.drawing.macroE"...
0x2cd045  stelem.ref
0x2cd046  ldloc.3
0x2cd047  ldc.i4.s 0x3C
0x2cd049  ldstr    aApplicationVnd_33// "application/vnd.ms-visio.stencil"
0x2cd04e  stelem.ref
0x2cd04f  ldloc.3
0x2cd050  ldc.i4.s 0x3D
0x2cd052  ldstr    aApplicationVnd_34// "application/vnd.ms-visio.stencil.macroE"...
0x2cd057  stelem.ref
0x2cd058  ldloc.3
0x2cd059  ldc.i4.s 0x3E
0x2cd05b  ldstr    aApplicationVnd_35// "application/vnd.ms-visio.template"
0x2cd060  stelem.ref
0x2cd061  ldloc.3
0x2cd062  ldc.i4.s 0x3F
0x2cd064  ldstr    aApplicationVnd_36// "application/vnd.ms-visio.template.macro"...
0x2cd069  stelem.ref
0x2cd06a  ldloc.3
0x2cd06b  ldc.i4.s 0x40
0x2cd06d  ldstr    aApplicationVnd_67// "application/vnd.ms-visio.viewer"
0x2cd072  stelem.ref
0x2cd073  ldloc.3
0x2cd074  ldc.i4.s 0x41
0x2cd076  ldstr    aApplicationVnd_68// "application/vnd.ms-word.document.12"
0x2cd07b  stelem.ref
0x2cd07c  ldloc.3
0x2cd07d  ldc.i4.s 0x42
0x2cd07f  ldstr    aApplicationVnd_1// "application/vnd.ms-word.document.macroE"...
0x2cd084  stelem.ref
0x2cd085  ldloc.3
0x2cd086  ldc.i4.s 0x43
0x2cd088  ldstr    aApplicationVnd_69// "application/vnd.ms-word.template.12"
0x2cd08d  stelem.ref
0x2cd08e  ldloc.3
0x2cd08f  ldc.i4.s 0x44
0x2cd091  ldstr    aApplicationVnd_3// "application/vnd.ms-word.template.macroE"...
0x2cd096  stelem.ref
0x2cd097  ldloc.3
0x2cd098  ldc.i4.s 0x45
0x2cd09a  ldstr    aApplicationVnd_37// "application/vnd.ms-works"
0x2cd09f  stelem.ref
0x2cd0a0  ldloc.3
0x2cd0a1  ldc.i4.s 0x46
0x2cd0a3  ldstr    aApplicationVnd_47// "application/vnd.ms-xpsdocument"
0x2cd0a8  stelem.ref
0x2cd0a9  ldloc.3
0x2cd0aa  ldc.i4.s 0x47
0x2cd0ac  ldstr    aApplicationVnd_10// "application/vnd.oasis.opendocument.pres"...
0x2cd0b1  stelem.ref
0x2cd0b2  ldloc.3
0x2cd0b3  ldc.i4.s 0x48
0x2cd0b5  ldstr    aApplicationVnd_11// "application/vnd.oasis.opendocument.spre"...
0x2cd0ba  stelem.ref
0x2cd0bb  ldloc.3
  ... truncated ...
```
