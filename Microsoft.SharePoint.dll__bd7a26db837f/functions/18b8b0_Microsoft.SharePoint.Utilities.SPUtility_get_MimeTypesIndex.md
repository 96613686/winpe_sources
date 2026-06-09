# Microsoft.SharePoint.Utilities.SPUtility::get_MimeTypesIndex

- ea: `0x18b8b0`
- end: `0x18d92a`
- name: `Microsoft.SharePoint.Utilities.SPUtility::get_MimeTypesIndex`
- size: `8314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18b7f0`

## callees

- `0x18b8b0`
- `0x7ad020`

## string_xrefs

- `0x18b906`: `application/msaccess`
- `0x18b91a`: `application/msaccess`
- `0x18b92e`: `application/msaccess`
- `0x18b942`: `application/msaccess`
- `0x18b956`: `application/msaccess`
- `0x18b96a`: `application/msaccess`
- `0x18b97e`: `application/msaccess`
- `0x18b992`: `application/msaccess`
- `0x18b9a6`: `application/msaccess`
- `0x18b9e2`: `application/msaccess`
- `0x18b9f6`: `application/msaccess`
- `0x18c55e`: `application/msaccess`
- `0x18c586`: `application/msaccess`
- `0x18b9ce`: `text/xml`
- `0x18bf32`: `text/xml`
- `0x18cf36`: `text/xml`
- `0x18d396`: `text/xml`
- `0x18d3d2`: `text/xml`
- `0x18d7f6`: `text/xml`
- `0x18d86e`: `text/xml`
- `0x18d8aa`: `text/xml`
- `0x18ba6e`: `application/xml`
- `0x18ba82`: `application/xml`
- `0x18ba96`: `application/xml`
- `0x18babe`: `application/xml`
- `0x18bae6`: `application/xml`
- `0x18bafa`: `application/xml`
- `0x18bc8a`: `application/xml`
- `0x18bcb2`: `application/xml`
- `0x18bdca`: `application/xml`
- `0x18c18a`: `application/xml`
- `0x18c19e`: `application/xml`
- `0x18c1c6`: `application/xml`
- `0x18c1da`: `application/xml`
- `0x18c216`: `application/xml`
- `0x18c266`: `application/xml`
- `0x18c27a`: `application/xml`
- `0x18c54a`: `application/xml`
- `0x18c8ba`: `application/xml`
- `0x18cc7a`: `application/xml`
- `0x18cc8e`: `application/xml`
- `0x18cdba`: `application/xml`
- `0x18ce0a`: `application/xml`
- `0x18ce1e`: `application/xml`
- `0x18ceaa`: `application/xml`
- `0x18cfae`: `application/xml`
- `0x18d012`: `application/xml`
- `0x18d102`: `application/xml`
- `0x18d2e2`: `application/xml`
- `0x18d332`: `application/xml`
- `0x18d4d6`: `application/xml`
- `0x18d616`: `application/xml`
- `0x18d6a2`: `application/xml`
- `0x18d80a`: `application/xml`
- `0x18d882`: `application/xml`
- `0x18d896`: `application/xml`
- `0x18d8be`: `application/xml`
- `0x18d8d2`: `application/xml`
- `0x18bc85`: `.config`
- `0x18be92`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x18beba`: `application/vnd.ms-word.template.macroEnabled.12`
- `0x18bece`: `application/vnd.openxmlformats-officedocument.wordprocessingml.template`
- `0x18bf1e`: `application/xml-dtd`
- `0x18bf2d`: `.dtsconfig`
- `0x18c13a`: `text/x-component`
- `0x18c33d`: `.infopathxml`
- `0x18c342`: `application/ms-infopath.xml`
- `0x18c572`: `application/x-msaccess`
- `0x18c842`: `application/vnd.oasis.opendocument.presentation`
- `0x18c856`: `application/vnd.oasis.opendocument.spreadsheet`
- `0x18c86a`: `application/vnd.oasis.opendocument.text`
- `0x18ca9a`: `application/vnd.ms-powerpoint.template.macroEnabled.12`
- `0x18caae`: `application/vnd.openxmlformats-officedocument.presentationml.template`
- `0x18cb26`: `application/vnd.openxmlformats-officedocument.presentationml.slideshow`
- `0x18cb62`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x18ce46`: `application/vnd.openxmlformats-officedocument.presentationml.slide`
- `0x18cf31`: `.ssisdeploymentmanifest`
- `0x18d00d`: `.testrunconfig`
- `0x18d062`: `application/x-compressed`
- `0x18d1de`: `Application/xml`
- `0x18d2a6`: `application/vnd.ms-visio.template`
- `0x18d2ba`: `application/vnd.ms-visio.template.macroEnabled`
- `0x18d3cd`: `.vstemplate`
- `0x18d5c6`: `application/x-mswrite`
- `0x18d652`: `application/xaml+xml`
- `0x18d68e`: `application/vnd.adobe.xdp+xml`
- `0x18d792`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
- `0x18d7ba`: `application/vnd.ms-excel.template.macroEnabled.12`
- `0x18d7ce`: `application/vnd.openxmlformats-officedocument.spreadsheetml.template`
- `0x18d8fa`: `application/x-compress`

## pseudocode

```c

```

## disassembly

```asm
0x18b8b0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b8b5  brtrue   loc_18D924
0x18b8ba  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPInitializeOnceLock::AcquireWriterLock()
0x18b8bf  stloc.0
0x18b8c0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b8c5  brtrue   loc_18D918
0x18b8ca  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x18b8cf  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b8d4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b8d9  ldstr    a323// ".323"
0x18b8de  ldstr    aTextH323// "text/h323"
0x18b8e3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b8e8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b8ed  ldstr    asc_C6A4B0// ".*"
0x18b8f2  ldstr    aApplicationOct// "application/octet-stream"
0x18b8f7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b8fc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b901  ldstr    aAccda// ".accda"
0x18b906  ldstr    aApplicationMsa// "application/msaccess"
0x18b90b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b910  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b915  ldstr    aAccdb// ".accdb"
0x18b91a  ldstr    aApplicationMsa// "application/msaccess"
0x18b91f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b924  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b929  ldstr    aAccdc// ".accdc"
0x18b92e  ldstr    aApplicationMsa// "application/msaccess"
0x18b933  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b938  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b93d  ldstr    aAccde// ".accde"
0x18b942  ldstr    aApplicationMsa// "application/msaccess"
0x18b947  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b94c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b951  ldstr    aAccdr// ".accdr"
0x18b956  ldstr    aApplicationMsa// "application/msaccess"
0x18b95b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b960  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b965  ldstr    aAccdt// ".accdt"
0x18b96a  ldstr    aApplicationMsa// "application/msaccess"
0x18b96f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b974  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b979  ldstr    aAccdw// ".accdw"
0x18b97e  ldstr    aApplicationMsa// "application/msaccess"
0x18b983  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b988  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b98d  ldstr    aAccft// ".accft"
0x18b992  ldstr    aApplicationMsa// "application/msaccess"
0x18b997  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b99c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b9a1  ldstr    aAccvt// ".accvt"
0x18b9a6  ldstr    aApplicationMsa// "application/msaccess"
0x18b9ab  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b9b0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b9b5  ldstr    aAcx// ".acx"
0x18b9ba  ldstr    aApplicationInt// "application/internet-property-stream"
0x18b9bf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b9c4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b9c9  ldstr    aAddin// ".addin"
0x18b9ce  ldstr    aTextXml// "text/xml"
0x18b9d3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b9d8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b9dd  ldstr    aAde// ".ade"
0x18b9e2  ldstr    aApplicationMsa// "application/msaccess"
0x18b9e7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18b9ec  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18b9f1  ldstr    aAdp// ".adp"
0x18b9f6  ldstr    aApplicationMsa// "application/msaccess"
0x18b9fb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba00  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba05  ldstr    aAi// ".ai"
0x18ba0a  ldstr    aApplicationPos// "application/postscript"
0x18ba0f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba14  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba19  ldstr    aAif// ".aif"
0x18ba1e  ldstr    aAudioXAiff// "audio/x-aiff"
0x18ba23  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba28  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba2d  ldstr    aAifc// ".aifc"
0x18ba32  ldstr    aAudioXAiff// "audio/x-aiff"
0x18ba37  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba3c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba41  ldstr    aAiff// ".aiff"
0x18ba46  ldstr    aAudioXAiff// "audio/x-aiff"
0x18ba4b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba50  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba55  ldstr    aApplication// ".application"
0x18ba5a  ldstr    aApplicationXMs// "application/x-ms-application"
0x18ba5f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba64  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba69  ldstr    aAsa// ".asa"
0x18ba6e  ldstr    aApplicationXml// "application/xml"
0x18ba73  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba78  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba7d  ldstr    aAsax// ".asax"
0x18ba82  ldstr    aApplicationXml// "application/xml"
0x18ba87  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18ba8c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18ba91  ldstr    aAscx// ".ascx"
0x18ba96  ldstr    aApplicationXml// "application/xml"
0x18ba9b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18baa0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18baa5  ldstr    aAsf_0// ".asf"
0x18baaa  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x18baaf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bab4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bab9  ldstr    aAshx// ".ashx"
0x18babe  ldstr    aApplicationXml// "application/xml"
0x18bac3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bac8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bacd  ldstr    aAsm// ".asm"
0x18bad2  ldstr    aTextPlain// "text/plain"
0x18bad7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18badc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bae1  ldstr    aAsmx// ".asmx"
0x18bae6  ldstr    aApplicationXml// "application/xml"
0x18baeb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18baf0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18baf5  ldstr    aAspx_0// ".aspx"
0x18bafa  ldstr    aApplicationXml// "application/xml"
0x18baff  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb04  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb09  ldstr    aAsr// ".asr"
0x18bb0e  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x18bb13  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb18  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb1d  ldstr    aAsx// ".asx"
0x18bb22  ldstr    aVideoXMsAsf// "video/x-ms-asf"
0x18bb27  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb2c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb31  ldstr    aAu// ".au"
0x18bb36  ldstr    aAudioBasic// "audio/basic"
0x18bb3b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb40  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb45  ldstr    aAvi_0// ".avi"
0x18bb4a  ldstr    aVideoXMsvideo// "video/x-msvideo"
0x18bb4f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb54  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb59  ldstr    aAxs// ".axs"
0x18bb5e  ldstr    aApplicationOle// "application/olescript"
0x18bb63  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb68  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb6d  ldstr    aBas// ".bas"
0x18bb72  ldstr    aTextPlain// "text/plain"
0x18bb77  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb7c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb81  ldstr    aBcpio// ".bcpio"
0x18bb86  ldstr    aApplicationXBc// "application/x-bcpio"
0x18bb8b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bb90  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bb95  ldstr    aBin// ".bin"
0x18bb9a  ldstr    aApplicationOct// "application/octet-stream"
0x18bb9f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bba4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bba9  ldstr    aBmp_0// ".bmp"
0x18bbae  ldstr    aImageBmp// "image/bmp"
0x18bbb3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bbb8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bbbd  ldstr    aC_0// ".c"
0x18bbc2  ldstr    aTextPlain// "text/plain"
0x18bbc7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bbcc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bbd1  ldstr    aCat// ".cat"
0x18bbd6  ldstr    aApplicationVnd// "application/vnd.ms-pkiseccat"
0x18bbdb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bbe0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bbe5  ldstr    aCc_0// ".cc"
0x18bbea  ldstr    aTextPlain// "text/plain"
0x18bbef  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bbf4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bbf9  ldstr    aCd// ".cd"
0x18bbfe  ldstr    aTextPlain// "text/plain"
0x18bc03  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc08  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc0d  ldstr    aCdf// ".cdf"
0x18bc12  ldstr    aApplicationXCd// "application/x-cdf"
0x18bc17  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc1c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc21  ldstr    aCer// ".cer"
0x18bc26  ldstr    aApplicationXX5// "application/x-x509-ca-cert"
0x18bc2b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc30  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc35  ldstr    aClass_0// ".class"
0x18bc3a  ldstr    aApplicationOct// "application/octet-stream"
0x18bc3f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc44  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc49  ldstr    aClp// ".clp"
0x18bc4e  ldstr    aApplicationXMs_0// "application/x-msclip"
0x18bc53  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc58  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc5d  ldstr    aCmx// ".cmx"
0x18bc62  ldstr    aImageXCmx// "image/x-cmx"
0x18bc67  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc6c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc71  ldstr    aCod// ".cod"
0x18bc76  ldstr    aImageCisCod// "image/cis-cod"
0x18bc7b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc80  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc85  ldstr    aConfig_2// ".config"
0x18bc8a  ldstr    aApplicationXml// "application/xml"
0x18bc8f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bc94  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bc99  ldstr    aContact// ".contact"
0x18bc9e  ldstr    aTextXMsContact// "text/x-ms-contact"
0x18bca3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bca8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bcad  ldstr    aCoverage// ".coverage"
0x18bcb2  ldstr    aApplicationXml// "application/xml"
0x18bcb7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bcbc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bcc1  ldstr    aCpio// ".cpio"
0x18bcc6  ldstr    aApplicationXCp// "application/x-cpio"
0x18bccb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bcd0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bcd5  ldstr    aCpp// ".cpp"
0x18bcda  ldstr    aTextPlain// "text/plain"
0x18bcdf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bce4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bce9  ldstr    aCrd// ".crd"
0x18bcee  ldstr    aApplicationXMs_1// "application/x-mscardfile"
0x18bcf3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bcf8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bcfd  ldstr    aCrl// ".crl"
0x18bd02  ldstr    aApplicationPki// "application/pkix-crl"
0x18bd07  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd0c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd11  ldstr    aCrt// ".crt"
0x18bd16  ldstr    aApplicationXX5// "application/x-x509-ca-cert"
0x18bd1b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd20  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd25  ldstr    aCs_0// ".cs"
0x18bd2a  ldstr    aTextPlain// "text/plain"
0x18bd2f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd34  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd39  ldstr    aCsdproj// ".csdproj"
0x18bd3e  ldstr    aTextPlain// "text/plain"
0x18bd43  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd48  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd4d  ldstr    aCsh// ".csh"
0x18bd52  ldstr    aApplicationXCs// "application/x-csh"
0x18bd57  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd5c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd61  ldstr    aCsproj// ".csproj"
0x18bd66  ldstr    aTextPlain// "text/plain"
0x18bd6b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd70  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd75  ldstr    aCss// ".css"
0x18bd7a  ldstr    aTextCss// "text/css"
0x18bd7f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd84  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd89  ldstr    aCsv// ".csv"
0x18bd8e  ldstr    aApplicationVnd_0// "application/vnd.ms-excel"
0x18bd93  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bd98  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bd9d  ldstr    aCur// ".cur"
0x18bda2  ldstr    aTextPlain// "text/plain"
0x18bda7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bdac  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bdb1  ldstr    aCxx// ".cxx"
0x18bdb6  ldstr    aTextPlain// "text/plain"
0x18bdbb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bdc0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bdc5  ldstr    aDatasource_0// ".datasource"
0x18bdca  ldstr    aApplicationXml// "application/xml"
0x18bdcf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bdd4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bdd9  ldstr    aDcr// ".dcr"
0x18bdde  ldstr    aApplicationXDi// "application/x-director"
0x18bde3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bde8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18bded  ldstr    aDef// ".def"
0x18bdf2  ldstr    aTextPlain// "text/plain"
0x18bdf7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18bdfc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be01  ldstr    aDer// ".der"
0x18be06  ldstr    aApplicationXX5// "application/x-x509-ca-cert"
0x18be0b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be10  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be15  ldstr    aDib_0// ".dib"
0x18be1a  ldstr    aImageBmp// "image/bmp"
0x18be1f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be24  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be29  ldstr    aDir// ".dir"
0x18be2e  ldstr    aApplicationXDi// "application/x-director"
0x18be33  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be38  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be3d  ldstr    aDll// ".dll"
0x18be42  ldstr    aApplicationXMs_2// "application/x-msdownload"
0x18be47  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be4c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be51  ldstr    aDms// ".dms"
0x18be56  ldstr    aApplicationOct// "application/octet-stream"
0x18be5b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be60  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be65  ldstr    aDoc// ".doc"
0x18be6a  ldstr    aApplicationMsw// "application/msword"
0x18be6f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18be74  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Utilities.SPUtility::mimeTypesIndex
0x18be79  ldstr    aDocm// ".docm"
0x18be7e  ldstr    aApplicationVnd_1// "application/vnd.ms-word.document.macroE"...
0x18be83  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
  ... truncated ...
```
