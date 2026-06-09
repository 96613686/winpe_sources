# Microsoft.SharePoint.FileSync.PolicyXmlBuilder::BuildXml

- ea: `0xaa8350`
- end: `0xaa8890`
- name: `Microsoft.SharePoint.FileSync.PolicyXmlBuilder::BuildXml`
- size: `1344`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0xa9a6f0`
- `0xa9a700`
- `0xa9ab90`
- `0xa9af50`
- `0xa9b4e0`
- `0xaa8270`
- `0xaa82c0`
- `0xaa8320`
- `0xaa8350`
- `0xaafd10`
- `0xab05e0`
- `0xab0600`
- `0xab0620`
- `0xab0640`
- `0xab0660`
- `0xab0680`
- `0xab06a0`
- `0xab06c0`
- `0xab06e0`
- `0xab0700`
- `0xab0720`
- `0xab0740`
- `0xab0760`
- `0xab0780`
- `0xab07a0`
- `0xab07c0`
- `0xab07e0`
- `0xab0800`
- `0xab0820`
- `0xab0840`
- `0xab0860`
- `0xab0880`
- `0xab08a0`
- `0xab08c0`
- `0xab08e0`
- `0xab0900`
- `0xab0920`
- `0xab0940`
- `0xab0960`
- `0xab0980`
- `0xab09a0`
- `0xab09c0`
- `0xab09e0`
- `0xab0a00`
- `0xab0a20`
- `0xab0a40`
- `0xab0a60`
- `0xab0a80`
- `0xab0aa0`

## string_xrefs

- `0xaa852b`: `DavUrlTemplate`
- `0xaa8542`: `ShareUrlTemplate`
- `0xaa855e`: `ShareUrlTemplateV2`
- `0xaa859f`: `WacUrlTemplate`
- `0xaa85bd`: `SkyDriveURI`
- `0xaa85db`: `SkyDriveItemsURI`
- `0xaa86a8`: `StorageManagementURI`
- `0xaa86c4`: `ViewOnlineUrlTemplate`
- `0xaa86e0`: `DownloadUrlTemplate`
- `0xaa870d`: `DownloadStreamingMaxStreamSizeKB`
- `0xaa874d`: `IrmSupportedFileExtensions`
- `0xaa879e`: `RecycleBinURI`
- `0xaa8816`: `CollabVectorClockURI`

## pseudocode

```c

```

## disassembly

```asm
0xaa8350  ldarg.1
0xaa8351  callvirt instance class [mscorlib]System.Version Microsoft.SharePoint.FileSync.SyncPolicy::get_UserAgentVersion()
0xaa8356  ldarg.1
0xaa8357  callvirt instance valuetype Microsoft.SharePoint.FileSync.SyncUserAgentType Microsoft.SharePoint.FileSync.SyncPolicy::get_UserAgentType()
0xaa835c  call     bool Microsoft.SharePoint.FileSync.SyncUtils::IsMacBetaClient(class [mscorlib]System.Version userAgentVersion, valuetype Microsoft.SharePoint.FileSync.SyncUserAgentType userAgentType)
0xaa8361  stloc.0
0xaa8362  ldnull
0xaa8363  stloc.1
0xaa8364  ldnull
0xaa8365  stloc.2
0xaa8366  ldarg.1
0xaa8367  callvirt instance class Microsoft.SharePoint.FileSync.PolicyValueRange Microsoft.SharePoint.FileSync.SyncPolicy::get_PolicyDocumentPollIntervalSeconds()
0xaa836c  stloc.1
0xaa836d  ldarg.0
0xaa836e  ldarg.0
0xaa836f  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8374  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8379  ldstr    aPolicydocument// "PolicyDocumentPollIntervalSeconds"
0xaa837e  ldloc.1
0xaa837f  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRangeRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, class Microsoft.SharePoint.FileSync.PolicyValueRange range)
0xaa8384  ldarg.1
0xaa8385  callvirt instance class Microsoft.SharePoint.FileSync.PolicyValueRange Microsoft.SharePoint.FileSync.SyncPolicy::get_PolicyDocumentPrefetchIntervalSeconds()
0xaa838a  stloc.1
0xaa838b  ldarg.0
0xaa838c  ldarg.0
0xaa838d  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8392  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8397  ldstr    aPolicydocument_0// "PolicyDocumentPrefetchIntervalSeconds"
0xaa839c  ldloc.1
0xaa839d  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRangeRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, class Microsoft.SharePoint.FileSync.PolicyValueRange range)
0xaa83a2  ldloc.0
0xaa83a3  brfalse.s loc_AA83B1
0xaa83a5  ldc.i4.s 0xA
0xaa83a7  ldc.i4.s 0x1E
0xaa83a9  newobj   instance void Microsoft.SharePoint.FileSync.PolicyValueRange::.ctor(int32 start, int32 end)
0xaa83ae  stloc.1
0xaa83af  br.s     loc_AA83B8
0xaa83b1  ldarg.1
0xaa83b2  callvirt instance class Microsoft.SharePoint.FileSync.PolicyValueRange Microsoft.SharePoint.FileSync.SyncPolicy::get_BackgroundPollShortIntervalSeconds()
0xaa83b7  stloc.1
0xaa83b8  ldarg.0
0xaa83b9  ldarg.0
0xaa83ba  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa83bf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa83c4  ldstr    aBackgroundpoll// "BackgroundPollShortIntervalSeconds"
0xaa83c9  ldloc.1
0xaa83ca  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRangeRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, class Microsoft.SharePoint.FileSync.PolicyValueRange range)
0xaa83cf  ldarg.1
0xaa83d0  callvirt instance class Microsoft.SharePoint.FileSync.PolicyValueRange Microsoft.SharePoint.FileSync.SyncPolicy::get_BackgroundPollLongIntervalSeconds()
0xaa83d5  stloc.1
0xaa83d6  ldarg.0
0xaa83d7  ldarg.0
0xaa83d8  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa83dd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa83e2  ldstr    aBackgroundpoll_0// "BackgroundPollLongIntervalSeconds"
0xaa83e7  ldloc.1
0xaa83e8  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRangeRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, class Microsoft.SharePoint.FileSync.PolicyValueRange range)
0xaa83ed  ldarg.1
0xaa83ee  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_UploadBlockSizeKB()
0xaa83f3  ldstr    aD_0// "D"
0xaa83f8  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa83fd  stloc.2
0xaa83fe  ldarg.0
0xaa83ff  ldarg.0
0xaa8400  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8405  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa840a  ldstr    aUploadblocksiz// "UploadBlockSizeKB"
0xaa840f  ldloc.2
0xaa8410  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8415  ldarg.1
0xaa8416  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_DownloadBlockSizeKB()
0xaa841b  ldstr    aD_0// "D"
0xaa8420  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa8425  stloc.2
0xaa8426  ldarg.0
0xaa8427  ldarg.0
0xaa8428  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa842d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8432  ldstr    aDownloadblocks// "DownloadBlockSizeKB"
0xaa8437  ldloc.2
0xaa8438  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa843d  ldarg.1
0xaa843e  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_MaxClientRequestsPerDay()
0xaa8443  ldstr    aD_0// "D"
0xaa8448  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa844d  stloc.2
0xaa844e  ldarg.0
0xaa844f  ldarg.0
0xaa8450  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8455  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa845a  ldstr    aMaxclientreque// "MaxClientRequestsPerDay"
0xaa845f  ldloc.2
0xaa8460  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8465  ldarg.1
0xaa8466  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_MaxClientMBTransferredPerDay()
0xaa846b  ldstr    aD_0// "D"
0xaa8470  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa8475  stloc.2
0xaa8476  ldarg.0
0xaa8477  ldarg.0
0xaa8478  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa847d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8482  ldstr    aMaxclientmbtra// "MaxClientMBTransferredPerDay"
0xaa8487  ldloc.2
0xaa8488  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa848d  ldarg.1
0xaa848e  callvirt instance int64 Microsoft.SharePoint.FileSync.SyncPolicy::get_MaxFileSizeBytes()
0xaa8493  ldstr    aD_0// "D"
0xaa8498  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int64 value, [opt] string format)
0xaa849d  stloc.2
0xaa849e  ldarg.0
0xaa849f  ldarg.0
0xaa84a0  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa84a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa84aa  ldstr    aMaxfilesizebyt// "MaxFileSizeBytes"
0xaa84af  ldloc.2
0xaa84b0  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa84b5  ldarg.1
0xaa84b6  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_HighVisibilityFileExclusionList()
0xaa84bb  stloc.2
0xaa84bc  ldarg.0
0xaa84bd  ldarg.0
0xaa84be  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa84c3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa84c8  ldstr    aHighvisibility// "HighVisibilityFileExclusionList"
0xaa84cd  ldloc.2
0xaa84ce  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa84d3  ldarg.0
0xaa84d4  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa84d9  ldarg.0
0xaa84da  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa84df  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa84e4  ldstr    aDavurlmatches// "DavUrlMatches"
0xaa84e9  ldnull
0xaa84ea  ldc.i4.1
0xaa84eb  call     class [System.Xml]System.Xml.XmlElement Microsoft.SharePoint.FileSync.SyncUtils::AddChildElement(class [System.Xml]System.Xml.XmlDocument xmlDoc, class [System.Xml]System.Xml.XmlElement parentElem, string childName, [opt] string childInnerData, [opt] bool isInnerXmlData)
0xaa84f0  stloc.3
0xaa84f1  ldloc.0
0xaa84f2  brtrue.s loc_AA84FC
0xaa84f4  ldarg.1
0xaa84f5  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_DavUrlMatchRegex()
0xaa84fa  br.s     loc_AA8501
0xaa84fc  ldstr    aHttpHttpsAZaZ0// "^(?:http|https)://([a-zA-Z0-9])+\\.([a-"...
0xaa8501  stloc.s  4
0xaa8503  ldarg.0
0xaa8504  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8509  ldloc.3
0xaa850a  ldstr    aDavurlmatch// "DavUrlMatch"
0xaa850f  ldloc.s  4
0xaa8511  ldc.i4.0
0xaa8512  call     class [System.Xml]System.Xml.XmlElement Microsoft.SharePoint.FileSync.SyncUtils::AddChildElement(class [System.Xml]System.Xml.XmlDocument xmlDoc, class [System.Xml]System.Xml.XmlElement parentElem, string childName, [opt] string childInnerData, [opt] bool isInnerXmlData)
0xaa8517  pop
0xaa8518  ldarg.1
0xaa8519  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_DavUrlTemplate()
0xaa851e  stloc.2
0xaa851f  ldarg.0
0xaa8520  ldarg.0
0xaa8521  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8526  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa852b  ldstr    aDavurltemplate// "DavUrlTemplate"
0xaa8530  ldloc.2
0xaa8531  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8536  ldarg.0
0xaa8537  ldarg.0
0xaa8538  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa853d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8542  ldstr    aShareurltempla// "ShareUrlTemplate"
0xaa8547  ldarg.1
0xaa8548  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_ShareUrlTemplate()
0xaa854d  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8552  ldarg.0
0xaa8553  ldarg.0
0xaa8554  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8559  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa855e  ldstr    aShareurltempla_0// "ShareUrlTemplateV2"
0xaa8563  ldarg.1
0xaa8564  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_ShareUrlTemplateV2()
0xaa8569  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa856e  ldarg.1
0xaa856f  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_OfficeExcludeList()
0xaa8574  stloc.2
0xaa8575  ldarg.0
0xaa8576  ldarg.0
0xaa8577  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa857c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8581  ldstr    aOfficeexcludel// "OfficeExcludeList"
0xaa8586  ldloc.2
0xaa8587  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa858c  ldarg.1
0xaa858d  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_WacUrlTemplate()
0xaa8592  stloc.2
0xaa8593  ldarg.0
0xaa8594  ldarg.0
0xaa8595  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa859a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa859f  ldstr    aWacurltemplate// "WacUrlTemplate"
0xaa85a4  ldloc.2
0xaa85a5  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa85aa  ldarg.1
0xaa85ab  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_SkyDriveURI()
0xaa85b0  stloc.2
0xaa85b1  ldarg.0
0xaa85b2  ldarg.0
0xaa85b3  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa85b8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa85bd  ldstr    aSkydriveuri// "SkyDriveURI"
0xaa85c2  ldloc.2
0xaa85c3  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa85c8  ldarg.1
0xaa85c9  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_SkyDriveItemsURI()
0xaa85ce  stloc.2
0xaa85cf  ldarg.0
0xaa85d0  ldarg.0
0xaa85d1  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa85d6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa85db  ldstr    aSkydriveitemsu// "SkyDriveItemsURI"
0xaa85e0  ldloc.2
0xaa85e1  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa85e6  ldarg.1
0xaa85e7  callvirt instance bool Microsoft.SharePoint.FileSync.SyncPolicy::get_QosCollectionEnabled()
0xaa85ec  brtrue.s loc_AA85F5
0xaa85ee  ldstr    aFalse_3// "False"
0xaa85f3  br.s     loc_AA85FA
0xaa85f5  ldstr    aTrue_3// "True"
0xaa85fa  stloc.2
0xaa85fb  ldarg.0
0xaa85fc  ldarg.0
0xaa85fd  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8602  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8607  ldstr    aQoscollectione// "QosCollectionEnabled"
0xaa860c  ldloc.2
0xaa860d  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8612  ldarg.1
0xaa8613  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_HashAlgorithm()
0xaa8618  stloc.2
0xaa8619  ldarg.0
0xaa861a  ldarg.0
0xaa861b  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8620  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8625  ldstr    aHashalgorithm_0// "HashAlgorithm"
0xaa862a  ldloc.2
0xaa862b  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8630  ldarg.0
0xaa8631  ldarg.0
0xaa8632  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8637  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa863c  ldstr    aDavurlnamespac// "DavUrlNamespace"
0xaa8641  ldarg.1
0xaa8642  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_DavUrlNamespace()
0xaa8647  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa864c  ldarg.1
0xaa864d  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_MaxUrlLength()
0xaa8652  ldstr    aD_0// "D"
0xaa8657  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa865c  stloc.2
0xaa865d  ldarg.0
0xaa865e  ldarg.0
0xaa865f  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa8664  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8669  ldstr    aMaxurllength_0// "MaxUrlLength"
0xaa866e  ldloc.2
0xaa866f  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa8674  ldarg.1
0xaa8675  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_MaxInlineUploadSizeKB()
0xaa867a  ldstr    aD_0// "D"
0xaa867f  call     string Microsoft.SharePoint.FileSync.SyncUtils::ToString(int32 value, [opt] string format)
0xaa8684  stloc.2
0xaa8685  ldarg.0
0xaa8686  ldarg.0
0xaa8687  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa868c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa8691  ldstr    aMaxinlineuploa// "MaxInlineUploadSizeKB"
0xaa8696  ldloc.2
0xaa8697  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa869c  ldarg.0
0xaa869d  ldarg.0
0xaa869e  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa86a3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa86a8  ldstr    aStoragemanagem// "StorageManagementURI"
0xaa86ad  ldarg.1
0xaa86ae  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_StorageManagementURI()
0xaa86b3  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa86b8  ldarg.0
0xaa86b9  ldarg.0
0xaa86ba  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa86bf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa86c4  ldstr    aViewonlineurlt// "ViewOnlineUrlTemplate"
0xaa86c9  ldarg.1
0xaa86ca  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_ViewOnlineUrlTemplate()
0xaa86cf  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa86d4  ldarg.0
0xaa86d5  ldarg.0
0xaa86d6  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.FileSync.PolicyXmlBuilder::get_XmlDoc()
0xaa86db  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xaa86e0  ldstr    aDownloadurltem// "DownloadUrlTemplate"
0xaa86e5  ldarg.1
0xaa86e6  callvirt instance string Microsoft.SharePoint.FileSync.SyncPolicy::get_DownloadUrlTemplate()
0xaa86eb  call     instance void Microsoft.SharePoint.FileSync.PolicyXmlBuilder::AddPolicyRule(class [System.Xml]System.Xml.XmlElement parentElem, string ruleName, string ruleValue)
0xaa86f0  ldarg.1
0xaa86f1  callvirt instance int32 Microsoft.SharePoint.FileSync.SyncPolicy::get_DownloadStreamingMaxStreamSizeKB()
  ... truncated ...
```
