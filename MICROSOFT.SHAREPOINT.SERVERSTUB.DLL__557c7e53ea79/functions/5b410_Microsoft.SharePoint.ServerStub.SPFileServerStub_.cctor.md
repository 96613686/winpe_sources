# Microsoft.SharePoint.ServerStub.SPFileServerStub::.cctor

- ea: `0x5b410`
- end: `0x5b5c5`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::.cctor`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x5b4b4`: `ServerRelativePath`
- `0x5b599`: `ServerRelativePath`
- `0x5b422`: `CheckInComment`
- `0x5b47e`: `LinkingUri`
- `0x5b487`: `LinkingUrl`
- `0x5b4cf`: `TimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x5b410  ldc.i4.s 0x1C
0x5b412  newarr   [mscorlib]System.String
0x5b417  stloc.0
0x5b418  ldloc.0
0x5b419  ldc.i4.0
0x5b41a  ldstr    aActivitycapabi// "ActivityCapabilities"
0x5b41f  stelem.ref
0x5b420  ldloc.0
0x5b421  ldc.i4.1
0x5b422  ldstr    aCheckincomment_0// "CheckInComment"
0x5b427  stelem.ref
0x5b428  ldloc.0
0x5b429  ldc.i4.2
0x5b42a  ldstr    aCheckouttype// "CheckOutType"
0x5b42f  stelem.ref
0x5b430  ldloc.0
0x5b431  ldc.i4.3
0x5b432  ldstr    aClientactiviti_1// "ClientActivities"
0x5b437  stelem.ref
0x5b438  ldloc.0
0x5b439  ldc.i4.4
0x5b43a  ldstr    aContenttag// "ContentTag"
0x5b43f  stelem.ref
0x5b440  ldloc.0
0x5b441  ldc.i4.5
0x5b442  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x5b447  stelem.ref
0x5b448  ldloc.0
0x5b449  ldc.i4.6
0x5b44a  ldstr    aListid_0// "ListId"
0x5b44f  stelem.ref
0x5b450  ldloc.0
0x5b451  ldc.i4.7
0x5b452  ldstr    aEtag_0// "ETag"
0x5b457  stelem.ref
0x5b458  ldloc.0
0x5b459  ldc.i4.8
0x5b45a  ldstr    aExists// "Exists"
0x5b45f  stelem.ref
0x5b460  ldloc.0
0x5b461  ldc.i4.s 9
0x5b463  ldstr    aIrmenabled// "IrmEnabled"
0x5b468  stelem.ref
0x5b469  ldloc.0
0x5b46a  ldc.i4.s 0xA
0x5b46c  ldstr    aLength// "Length"
0x5b471  stelem.ref
0x5b472  ldloc.0
0x5b473  ldc.i4.s 0xB
0x5b475  ldstr    aLevel// "Level"
0x5b47a  stelem.ref
0x5b47b  ldloc.0
0x5b47c  ldc.i4.s 0xC
0x5b47e  ldstr    aLinkinguri// "LinkingUri"
0x5b483  stelem.ref
0x5b484  ldloc.0
0x5b485  ldc.i4.s 0xD
0x5b487  ldstr    aLinkingurl// "LinkingUrl"
0x5b48c  stelem.ref
0x5b48d  ldloc.0
0x5b48e  ldc.i4.s 0xE
0x5b490  ldstr    aMajorversion// "MajorVersion"
0x5b495  stelem.ref
0x5b496  ldloc.0
0x5b497  ldc.i4.s 0xF
0x5b499  ldstr    aMinorversion// "MinorVersion"
0x5b49e  stelem.ref
0x5b49f  ldloc.0
0x5b4a0  ldc.i4.s 0x10
0x5b4a2  ldstr    aName// "Name"
0x5b4a7  stelem.ref
0x5b4a8  ldloc.0
0x5b4a9  ldc.i4.s 0x11
0x5b4ab  ldstr    aPagerendertype// "PageRenderType"
0x5b4b0  stelem.ref
0x5b4b1  ldloc.0
0x5b4b2  ldc.i4.s 0x12
0x5b4b4  ldstr    aServerrelative_0// "ServerRelativePath"
0x5b4b9  stelem.ref
0x5b4ba  ldloc.0
0x5b4bb  ldc.i4.s 0x13
0x5b4bd  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5b4c2  stelem.ref
0x5b4c3  ldloc.0
0x5b4c4  ldc.i4.s 0x14
0x5b4c6  ldstr    aSiteid_0// "SiteId"
0x5b4cb  stelem.ref
0x5b4cc  ldloc.0
0x5b4cd  ldc.i4.s 0x15
0x5b4cf  ldstr    aTimecreated// "TimeCreated"
0x5b4d4  stelem.ref
0x5b4d5  ldloc.0
0x5b4d6  ldc.i4.s 0x16
0x5b4d8  ldstr    aTimelastmodifi// "TimeLastModified"
0x5b4dd  stelem.ref
0x5b4de  ldloc.0
0x5b4df  ldc.i4.s 0x17
0x5b4e1  ldstr    aTitle// "Title"
0x5b4e6  stelem.ref
0x5b4e7  ldloc.0
0x5b4e8  ldc.i4.s 0x18
0x5b4ea  ldstr    aUiversion// "UIVersion"
0x5b4ef  stelem.ref
0x5b4f0  ldloc.0
0x5b4f1  ldc.i4.s 0x19
0x5b4f3  ldstr    aUiversionlabel// "UIVersionLabel"
0x5b4f8  stelem.ref
0x5b4f9  ldloc.0
0x5b4fa  ldc.i4.s 0x1A
0x5b4fc  ldstr    aUniqueid_0// "UniqueId"
0x5b501  stelem.ref
0x5b502  ldloc.0
0x5b503  ldc.i4.s 0x1B
0x5b505  ldstr    aWebid_0// "WebId"
0x5b50a  stelem.ref
0x5b50b  ldloc.0
0x5b50c  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFileServerStub::s_valueProperties
0x5b511  ldc.i4.s 0xA
0x5b513  newarr   [mscorlib]System.String
0x5b518  stloc.1
0x5b519  ldloc.1
0x5b51a  ldc.i4.0
0x5b51b  ldstr    aAuthor_0// "Author"
0x5b520  stelem.ref
0x5b521  ldloc.1
0x5b522  ldc.i4.1
0x5b523  ldstr    aCheckedoutbyus// "CheckedOutByUser"
0x5b528  stelem.ref
0x5b529  ldloc.1
0x5b52a  ldc.i4.2
0x5b52b  ldstr    aEffectiveinfor// "EffectiveInformationRightsManagementSet"...
0x5b530  stelem.ref
0x5b531  ldloc.1
0x5b532  ldc.i4.3
0x5b533  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x5b538  stelem.ref
0x5b539  ldloc.1
0x5b53a  ldc.i4.4
0x5b53b  ldstr    aListitemallfie// "ListItemAllFields"
0x5b540  stelem.ref
0x5b541  ldloc.1
0x5b542  ldc.i4.5
0x5b543  ldstr    aLockedbyuser// "LockedByUser"
0x5b548  stelem.ref
0x5b549  ldloc.1
0x5b54a  ldc.i4.6
0x5b54b  ldstr    aModifiedby// "ModifiedBy"
0x5b550  stelem.ref
0x5b551  ldloc.1
0x5b552  ldc.i4.7
0x5b553  ldstr    aProperties// "Properties"
0x5b558  stelem.ref
0x5b559  ldloc.1
0x5b55a  ldc.i4.8
0x5b55b  ldstr    aVersionevents// "VersionEvents"
0x5b560  stelem.ref
0x5b561  ldloc.1
0x5b562  ldc.i4.s 9
0x5b564  ldstr    aVersions// "Versions"
0x5b569  stelem.ref
0x5b56a  ldloc.1
0x5b56b  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFileServerStub::s_refProperties
0x5b570  ldc.i4.7
0x5b571  newarr   [mscorlib]System.String
0x5b576  stloc.2
0x5b577  ldloc.2
0x5b578  ldc.i4.0
0x5b579  ldstr    aActivitycapabi// "ActivityCapabilities"
0x5b57e  stelem.ref
0x5b57f  ldloc.2
0x5b580  ldc.i4.1
0x5b581  ldstr    aClientactiviti_1// "ClientActivities"
0x5b586  stelem.ref
0x5b587  ldloc.2
0x5b588  ldc.i4.2
0x5b589  ldstr    aListid_0// "ListId"
0x5b58e  stelem.ref
0x5b58f  ldloc.2
0x5b590  ldc.i4.3
0x5b591  ldstr    aPagerendertype// "PageRenderType"
0x5b596  stelem.ref
0x5b597  ldloc.2
0x5b598  ldc.i4.4
0x5b599  ldstr    aServerrelative_0// "ServerRelativePath"
0x5b59e  stelem.ref
0x5b59f  ldloc.2
0x5b5a0  ldc.i4.5
0x5b5a1  ldstr    aSiteid_0// "SiteId"
0x5b5a6  stelem.ref
0x5b5a7  ldloc.2
0x5b5a8  ldc.i4.6
0x5b5a9  ldstr    aWebid_0// "WebId"
0x5b5ae  stelem.ref
0x5b5af  ldloc.2
0x5b5b0  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFileServerStub::s_excludeFromDefaultRetrieveProperties
0x5b5b5  ldstr    aDf28be1e74b54b// "{df28be1e-74b5-4b21-b73a-2bbac0a23d8a}"
0x5b5ba  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5b5bf  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPFileServerStub::s_targetTypeId
0x5b5c4  ret
```
