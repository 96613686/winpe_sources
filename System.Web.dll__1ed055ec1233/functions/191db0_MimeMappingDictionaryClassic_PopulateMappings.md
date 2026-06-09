# MimeMappingDictionaryClassic::PopulateMappings

- ea: `0x191db0`
- end: `0x193321`
- name: `MimeMappingDictionaryClassic::PopulateMappings`
- size: `5489`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x191c40`

## string_xrefs

- `0x191de6`: `application/msaccess`
- `0x191df6`: `application/msaccess`
- `0x191e06`: `application/msaccess`
- `0x191ef6`: `application/atom+xml`
- `0x192106`: `text/xml`
- `0x192126`: `text/xml`
- `0x1921b6`: `text/xml`
- `0x192276`: `text/xml`
- `0x192676`: `text/xml`
- `0x192f26`: `text/xml`
- `0x193106`: `text/xml`
- `0x193256`: `text/xml`
- `0x193296`: `text/xml`
- `0x1932a6`: `text/xml`
- `0x1932b6`: `text/xml`
- `0x1932c6`: `text/xml`
- `0x192121`: `.dll.config`
- `0x192166`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x192186`: `application/vnd.ms-word.template.macroEnabled.12`
- `0x192196`: `application/vnd.openxmlformats-officedocument.wordprocessingml.template`
- `0x192271`: `.exe.config`
- `0x192396`: `text/x-component`
- `0x192526`: `application/x-ms-reader`
- `0x1925c1`: `.manifest`
- `0x1925c6`: `application/x-ms-manifest`
- `0x1925e6`: `application/x-msaccess`
- `0x192776`: `application/x-miva-compiled`
- `0x192856`: `application/opensearchdescription+xml`
- `0x1929f6`: `application/vnd.ms-powerpoint.template.macroEnabled.12`
- `0x192a06`: `application/vnd.openxmlformats-officedocument.presentationml.template`
- `0x192a56`: `application/vnd.openxmlformats-officedocument.presentationml.slideshow`
- `0x192a86`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x192bd6`: `audio/x-pn-realaudio-plugin`
- `0x192ca6`: `application/vnd.openxmlformats-officedocument.presentationml.slide`
- `0x192e06`: `application/x-compressed`
- `0x1930d6`: `application/x-mswrite`
- `0x193146`: `application/xaml+xml`
- `0x193206`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
- `0x193226`: `application/vnd.ms-excel.template.macroEnabled.12`
- `0x193236`: `application/vnd.openxmlformats-officedocument.spreadsheetml.template`
- `0x193306`: `application/x-compress`
- `0x193316`: `application/x-zip-compressed`

## pseudocode

```c

```

## disassembly

```asm
0x191db0  ldarg.0
0x191db1  ldstr    a323// ".323"
0x191db6  ldstr    aTextH323// "text/h323"
0x191dbb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191dc0  ldarg.0
0x191dc1  ldstr    aAaf// ".aaf"
0x191dc6  ldstr    aApplicationOct// "application/octet-stream"
0x191dcb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191dd0  ldarg.0
0x191dd1  ldstr    aAca// ".aca"
0x191dd6  ldstr    aApplicationOct// "application/octet-stream"
0x191ddb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191de0  ldarg.0
0x191de1  ldstr    aAccdb// ".accdb"
0x191de6  ldstr    aApplicationMsa// "application/msaccess"
0x191deb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191df0  ldarg.0
0x191df1  ldstr    aAccde// ".accde"
0x191df6  ldstr    aApplicationMsa// "application/msaccess"
0x191dfb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e00  ldarg.0
0x191e01  ldstr    aAccdt// ".accdt"
0x191e06  ldstr    aApplicationMsa// "application/msaccess"
0x191e0b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e10  ldarg.0
0x191e11  ldstr    aAcx// ".acx"
0x191e16  ldstr    aApplicationInt// "application/internet-property-stream"
0x191e1b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e20  ldarg.0
0x191e21  ldstr    aAfm// ".afm"
0x191e26  ldstr    aApplicationOct// "application/octet-stream"
0x191e2b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e30  ldarg.0
0x191e31  ldstr    aAi// ".ai"
0x191e36  ldstr    aApplicationPos// "application/postscript"
0x191e3b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e40  ldarg.0
0x191e41  ldstr    aAif// ".aif"
0x191e46  ldstr    aAudioXAiff// "audio/x-aiff"
0x191e4b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e50  ldarg.0
0x191e51  ldstr    aAifc// ".aifc"
0x191e56  ldstr    aAudioAiff// "audio/aiff"
0x191e5b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e60  ldarg.0
0x191e61  ldstr    aAiff// ".aiff"
0x191e66  ldstr    aAudioAiff// "audio/aiff"
0x191e6b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e70  ldarg.0
0x191e71  ldstr    aApplication_1// ".application"
0x191e76  ldstr    aApplicationXMs// "application/x-ms-application"
0x191e7b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e80  ldarg.0
0x191e81  ldstr    aArt// ".art"
0x191e86  ldstr    aImageXJg// "image/x-jg"
0x191e8b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191e90  ldarg.0
0x191e91  ldstr    aAsd// ".asd"
0x191e96  ldstr    aApplicationOct// "application/octet-stream"
0x191e9b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ea0  ldarg.0
0x191ea1  ldstr    aAsf// ".asf"
0x191ea6  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x191eab  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191eb0  ldarg.0
0x191eb1  ldstr    aAsi// ".asi"
0x191eb6  ldstr    aApplicationOct// "application/octet-stream"
0x191ebb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ec0  ldarg.0
0x191ec1  ldstr    aAsm// ".asm"
0x191ec6  ldstr    aTextPlain// "text/plain"
0x191ecb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ed0  ldarg.0
0x191ed1  ldstr    aAsr// ".asr"
0x191ed6  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x191edb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ee0  ldarg.0
0x191ee1  ldstr    aAsx// ".asx"
0x191ee6  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x191eeb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ef0  ldarg.0
0x191ef1  ldstr    aAtom// ".atom"
0x191ef6  ldstr    aApplicationAto// "application/atom+xml"
0x191efb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f00  ldarg.0
0x191f01  ldstr    aAu// ".au"
0x191f06  ldstr    aAudioBasic// "audio/basic"
0x191f0b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f10  ldarg.0
0x191f11  ldstr    aAvi// ".avi"
0x191f16  ldstr    aVideoXMsvideo// "video/x-msvideo"
0x191f1b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f20  ldarg.0
0x191f21  ldstr    aAxs// ".axs"
0x191f26  ldstr    aApplicationOle// "application/olescript"
0x191f2b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f30  ldarg.0
0x191f31  ldstr    aBas// ".bas"
0x191f36  ldstr    aTextPlain// "text/plain"
0x191f3b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f40  ldarg.0
0x191f41  ldstr    aBcpio// ".bcpio"
0x191f46  ldstr    aApplicationXBc// "application/x-bcpio"
0x191f4b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f50  ldarg.0
0x191f51  ldstr    aBin_0// ".bin"
0x191f56  ldstr    aApplicationOct// "application/octet-stream"
0x191f5b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f60  ldarg.0
0x191f61  ldstr    aBmp// ".bmp"
0x191f66  ldstr    aImageBmp// "image/bmp"
0x191f6b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f70  ldarg.0
0x191f71  ldstr    aC_2// ".c"
0x191f76  ldstr    aTextPlain// "text/plain"
0x191f7b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f80  ldarg.0
0x191f81  ldstr    aCab// ".cab"
0x191f86  ldstr    aApplicationOct// "application/octet-stream"
0x191f8b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191f90  ldarg.0
0x191f91  ldstr    aCalx// ".calx"
0x191f96  ldstr    aApplicationVnd// "application/vnd.ms-office.calx"
0x191f9b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191fa0  ldarg.0
0x191fa1  ldstr    aCat// ".cat"
0x191fa6  ldstr    aApplicationVnd_0// "application/vnd.ms-pki.seccat"
0x191fab  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191fb0  ldarg.0
0x191fb1  ldstr    aCdf_0// ".cdf"
0x191fb6  ldstr    aApplicationXCd// "application/x-cdf"
0x191fbb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191fc0  ldarg.0
0x191fc1  ldstr    aChm// ".chm"
0x191fc6  ldstr    aApplicationOct// "application/octet-stream"
0x191fcb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191fd0  ldarg.0
0x191fd1  ldstr    aClass_0// ".class"
0x191fd6  ldstr    aApplicationXJa// "application/x-java-applet"
0x191fdb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191fe0  ldarg.0
0x191fe1  ldstr    aClp// ".clp"
0x191fe6  ldstr    aApplicationXMs_0// "application/x-msclip"
0x191feb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x191ff0  ldarg.0
0x191ff1  ldstr    aCmx// ".cmx"
0x191ff6  ldstr    aImageXCmx// "image/x-cmx"
0x191ffb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192000  ldarg.0
0x192001  ldstr    aCnf// ".cnf"
0x192006  ldstr    aTextPlain// "text/plain"
0x19200b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192010  ldarg.0
0x192011  ldstr    aCod// ".cod"
0x192016  ldstr    aImageCisCod// "image/cis-cod"
0x19201b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192020  ldarg.0
0x192021  ldstr    aCpio// ".cpio"
0x192026  ldstr    aApplicationXCp// "application/x-cpio"
0x19202b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192030  ldarg.0
0x192031  ldstr    aCpp_0// ".cpp"
0x192036  ldstr    aTextPlain// "text/plain"
0x19203b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192040  ldarg.0
0x192041  ldstr    aCrd// ".crd"
0x192046  ldstr    aApplicationXMs_1// "application/x-mscardfile"
0x19204b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192050  ldarg.0
0x192051  ldstr    aCrl// ".crl"
0x192056  ldstr    aApplicationPki// "application/pkix-crl"
0x19205b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192060  ldarg.0
0x192061  ldstr    aCrt// ".crt"
0x192066  ldstr    aApplicationXX5// "application/x-x509-ca-cert"
0x19206b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192070  ldarg.0
0x192071  ldstr    aCsh// ".csh"
0x192076  ldstr    aApplicationXCs// "application/x-csh"
0x19207b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192080  ldarg.0
0x192081  ldstr    aCss// ".css"
0x192086  ldstr    aTextCss// "text/css"
0x19208b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192090  ldarg.0
0x192091  ldstr    aCsv// ".csv"
0x192096  ldstr    aApplicationOct// "application/octet-stream"
0x19209b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920a0  ldarg.0
0x1920a1  ldstr    aCur// ".cur"
0x1920a6  ldstr    aApplicationOct// "application/octet-stream"
0x1920ab  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920b0  ldarg.0
0x1920b1  ldstr    aDcr// ".dcr"
0x1920b6  ldstr    aApplicationXDi// "application/x-director"
0x1920bb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920c0  ldarg.0
0x1920c1  ldstr    aDeploy// ".deploy"
0x1920c6  ldstr    aApplicationOct// "application/octet-stream"
0x1920cb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920d0  ldarg.0
0x1920d1  ldstr    aDer// ".der"
0x1920d6  ldstr    aApplicationXX5// "application/x-x509-ca-cert"
0x1920db  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920e0  ldarg.0
0x1920e1  ldstr    aDib// ".dib"
0x1920e6  ldstr    aImageBmp// "image/bmp"
0x1920eb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1920f0  ldarg.0
0x1920f1  ldstr    aDir_0// ".dir"
0x1920f6  ldstr    aApplicationXDi// "application/x-director"
0x1920fb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192100  ldarg.0
0x192101  ldstr    aDisco// ".disco"
0x192106  ldstr    aTextXml// "text/xml"
0x19210b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192110  ldarg.0
0x192111  ldstr    aDll_0// ".dll"
0x192116  ldstr    aApplicationXMs_2// "application/x-msdownload"
0x19211b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192120  ldarg.0
0x192121  ldstr    aDllConfig// ".dll.config"
0x192126  ldstr    aTextXml// "text/xml"
0x19212b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192130  ldarg.0
0x192131  ldstr    aDlm// ".dlm"
0x192136  ldstr    aTextDlm// "text/dlm"
0x19213b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192140  ldarg.0
0x192141  ldstr    aDoc// ".doc"
0x192146  ldstr    aApplicationMsw_0// "application/msword"
0x19214b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192150  ldarg.0
0x192151  ldstr    aDocm// ".docm"
0x192156  ldstr    aApplicationVnd_1// "application/vnd.ms-word.document.macroE"...
0x19215b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192160  ldarg.0
0x192161  ldstr    aDocx// ".docx"
0x192166  ldstr    aApplicationVnd_2// "application/vnd.openxmlformats-officedo"...
0x19216b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192170  ldarg.0
0x192171  ldstr    aDot// ".dot"
0x192176  ldstr    aApplicationMsw_0// "application/msword"
0x19217b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192180  ldarg.0
0x192181  ldstr    aDotm// ".dotm"
0x192186  ldstr    aApplicationVnd_3// "application/vnd.ms-word.template.macroE"...
0x19218b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192190  ldarg.0
0x192191  ldstr    aDotx// ".dotx"
0x192196  ldstr    aApplicationVnd_4// "application/vnd.openxmlformats-officedo"...
0x19219b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921a0  ldarg.0
0x1921a1  ldstr    aDsp// ".dsp"
0x1921a6  ldstr    aApplicationOct// "application/octet-stream"
0x1921ab  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921b0  ldarg.0
0x1921b1  ldstr    aDtd// ".dtd"
0x1921b6  ldstr    aTextXml// "text/xml"
0x1921bb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921c0  ldarg.0
0x1921c1  ldstr    aDvi// ".dvi"
0x1921c6  ldstr    aApplicationXDv// "application/x-dvi"
0x1921cb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921d0  ldarg.0
0x1921d1  ldstr    aDwf// ".dwf"
0x1921d6  ldstr    aDrawingXDwf// "drawing/x-dwf"
0x1921db  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921e0  ldarg.0
0x1921e1  ldstr    aDwp// ".dwp"
0x1921e6  ldstr    aApplicationOct// "application/octet-stream"
0x1921eb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x1921f0  ldarg.0
0x1921f1  ldstr    aDxr// ".dxr"
0x1921f6  ldstr    aApplicationXDi// "application/x-director"
0x1921fb  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192200  ldarg.0
0x192201  ldstr    aEml// ".eml"
0x192206  ldstr    aMessageRfc822// "message/rfc822"
0x19220b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192210  ldarg.0
0x192211  ldstr    aEmz// ".emz"
0x192216  ldstr    aApplicationOct// "application/octet-stream"
0x19221b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192220  ldarg.0
0x192221  ldstr    aEot// ".eot"
0x192226  ldstr    aApplicationOct// "application/octet-stream"
0x19222b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192230  ldarg.0
0x192231  ldstr    aEps// ".eps"
0x192236  ldstr    aApplicationPos// "application/postscript"
0x19223b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192240  ldarg.0
0x192241  ldstr    aEtx// ".etx"
0x192246  ldstr    aTextXSetext// "text/x-setext"
0x19224b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
0x192250  ldarg.0
0x192251  ldstr    aEvy// ".evy"
0x192256  ldstr    aApplicationEnv// "application/envoy"
0x19225b  call     instance void MimeMappingDictionaryBase::AddMapping(string fileExtension, string mimeType)
  ... truncated ...
```
