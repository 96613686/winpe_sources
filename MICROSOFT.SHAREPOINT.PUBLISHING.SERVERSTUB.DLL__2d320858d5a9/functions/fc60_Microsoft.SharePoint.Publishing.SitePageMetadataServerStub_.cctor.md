# Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::.cctor

- ea: `0xfc60`
- end: `0xfd9f`
- name: `Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::.cctor`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xfc7a`: `CommentsDisabled`
- `0xfd63`: `CommentsDisabled`
- `0xfd46`: `CreatedBy`
- `0xfcc5`: `IsWebWelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0xfc60  ldc.i4.s 0x18
0xfc62  newarr   [mscorlib]System.String
0xfc67  stloc.0
0xfc68  ldloc.0
0xfc69  ldc.i4.0
0xfc6a  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xfc6f  stelem.ref
0xfc70  ldloc.0
0xfc71  ldc.i4.1
0xfc72  ldstr    aBannerimageurl// "BannerImageUrl"
0xfc77  stelem.ref
0xfc78  ldloc.0
0xfc79  ldc.i4.2
0xfc7a  ldstr    aCommentsdisabl// "CommentsDisabled"
0xfc7f  stelem.ref
0xfc80  ldloc.0
0xfc81  ldc.i4.3
0xfc82  ldstr    aContenttypeid// "ContentTypeId"
0xfc87  stelem.ref
0xfc88  ldloc.0
0xfc89  ldc.i4.4
0xfc8a  ldstr    aDescription// "Description"
0xfc8f  stelem.ref
0xfc90  ldloc.0
0xfc91  ldc.i4.5
0xfc92  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xfc97  stelem.ref
0xfc98  ldloc.0
0xfc99  ldc.i4.6
0xfc9a  ldstr    aFilename// "FileName"
0xfc9f  stelem.ref
0xfca0  ldloc.0
0xfca1  ldc.i4.7
0xfca2  ldstr    aFirstpublished// "FirstPublished"
0xfca7  stelem.ref
0xfca8  ldloc.0
0xfca9  ldc.i4.8
0xfcaa  ldstr    aFirstpublished_0// "FirstPublishedRelativeTime"
0xfcaf  stelem.ref
0xfcb0  ldloc.0
0xfcb1  ldc.i4.s 9
0xfcb3  ldstr    aId// "Id"
0xfcb8  stelem.ref
0xfcb9  ldloc.0
0xfcba  ldc.i4.s 0xA
0xfcbc  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xfcc1  stelem.ref
0xfcc2  ldloc.0
0xfcc3  ldc.i4.s 0xB
0xfcc5  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xfcca  stelem.ref
0xfccb  ldloc.0
0xfccc  ldc.i4.s 0xC
0xfcce  ldstr    aListid// "ListId"
0xfcd3  stelem.ref
0xfcd4  ldloc.0
0xfcd5  ldc.i4.s 0xD
0xfcd7  ldstr    aModified// "Modified"
0xfcdc  stelem.ref
0xfcdd  ldloc.0
0xfcde  ldc.i4.s 0xE
0xfce0  ldstr    aModifiedrelati// "ModifiedRelativeTime"
0xfce5  stelem.ref
0xfce6  ldloc.0
0xfce7  ldc.i4.s 0xF
0xfce9  ldstr    aPagelayouttype// "PageLayoutType"
0xfcee  stelem.ref
0xfcef  ldloc.0
0xfcf0  ldc.i4.s 0x10
0xfcf2  ldstr    aPath_0// "Path"
0xfcf7  stelem.ref
0xfcf8  ldloc.0
0xfcf9  ldc.i4.s 0x11
0xfcfb  ldstr    aPromotedstate_0// "PromotedState"
0xfd00  stelem.ref
0xfd01  ldloc.0
0xfd02  ldc.i4.s 0x12
0xfd04  ldstr    aSocialbaronsit// "SocialBarOnSitePagesDisabled"
0xfd09  stelem.ref
0xfd0a  ldloc.0
0xfd0b  ldc.i4.s 0x13
0xfd0d  ldstr    aTitle// "Title"
0xfd12  stelem.ref
0xfd13  ldloc.0
0xfd14  ldc.i4.s 0x14
0xfd16  ldstr    aUniqueid// "UniqueId"
0xfd1b  stelem.ref
0xfd1c  ldloc.0
0xfd1d  ldc.i4.s 0x15
0xfd1f  ldstr    aUrl// "Url"
0xfd24  stelem.ref
0xfd25  ldloc.0
0xfd26  ldc.i4.s 0x16
0xfd28  ldstr    aVersion_0// "Version"
0xfd2d  stelem.ref
0xfd2e  ldloc.0
0xfd2f  ldc.i4.s 0x17
0xfd31  ldstr    aVersioninfo// "VersionInfo"
0xfd36  stelem.ref
0xfd37  ldloc.0
0xfd38  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::s_valueProperties
0xfd3d  ldc.i4.2
0xfd3e  newarr   [mscorlib]System.String
0xfd43  stloc.1
0xfd44  ldloc.1
0xfd45  ldc.i4.0
0xfd46  ldstr    aCreatedby// "CreatedBy"
0xfd4b  stelem.ref
0xfd4c  ldloc.1
0xfd4d  ldc.i4.1
0xfd4e  ldstr    aLastmodifiedby// "LastModifiedBy"
0xfd53  stelem.ref
0xfd54  ldloc.1
0xfd55  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::s_refProperties
0xfd5a  ldc.i4.5
0xfd5b  newarr   [mscorlib]System.String
0xfd60  stloc.2
0xfd61  ldloc.2
0xfd62  ldc.i4.0
0xfd63  ldstr    aCommentsdisabl// "CommentsDisabled"
0xfd68  stelem.ref
0xfd69  ldloc.2
0xfd6a  ldc.i4.1
0xfd6b  ldstr    aFirstpublished_0// "FirstPublishedRelativeTime"
0xfd70  stelem.ref
0xfd71  ldloc.2
0xfd72  ldc.i4.2
0xfd73  ldstr    aListid// "ListId"
0xfd78  stelem.ref
0xfd79  ldloc.2
0xfd7a  ldc.i4.3
0xfd7b  ldstr    aModifiedrelati// "ModifiedRelativeTime"
0xfd80  stelem.ref
0xfd81  ldloc.2
0xfd82  ldc.i4.4
0xfd83  ldstr    aSocialbaronsit// "SocialBarOnSitePagesDisabled"
0xfd88  stelem.ref
0xfd89  ldloc.2
0xfd8a  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::s_excludeFromDefaultRetrieveProperties
0xfd8f  ldstr    a47b3a86a7f8a4a// "{47b3a86a-7f8a-4af8-8d31-c6064b62e03b}"
0xfd94  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xfd99  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::s_targetTypeId
0xfd9e  ret
```
