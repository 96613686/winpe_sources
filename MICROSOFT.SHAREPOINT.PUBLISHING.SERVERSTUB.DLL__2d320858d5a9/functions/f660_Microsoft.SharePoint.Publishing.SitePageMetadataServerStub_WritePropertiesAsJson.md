# Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WritePropertiesAsJson

- ea: `0xf660`
- end: `0xfac3`
- name: `Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WritePropertiesAsJson`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x105c0`

## callees

- `0xf660`

## string_xrefs

- `0xf87f`: `IsWebWelcomePage`
- `0xf88b`: `IsWebWelcomePage`
- `0xf896`: `IsWebWelcomePage`
- `0xf8ae`: `IsWebWelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0xf660  ldarg.2
0xf661  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata
0xf666  stloc.0
0xf667  ldloc.0
0xf668  brtrue.s loc_F66B
0xf66a  ret
0xf66b  ldarg.0
0xf66c  ldarg.1
0xf66d  ldarg.2
0xf66e  ldarg.3
0xf66f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf674  ldarg.0
0xf675  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xf67a  ldarg.3
0xf67b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf680  ldarg.1
0xf681  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xf686  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf68b  ldarg.3
0xf68c  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xf691  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf696  ldarg.1
0xf697  ldloc.0
0xf698  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_AbsoluteUrl()
0xf69d  ldarg.3
0xf69e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf6a3  ldarg.3
0xf6a4  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xf6a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf6ae  ldarg.0
0xf6af  ldstr    aBannerimageurl// "BannerImageUrl"
0xf6b4  ldarg.3
0xf6b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf6ba  ldarg.1
0xf6bb  ldstr    aBannerimageurl// "BannerImageUrl"
0xf6c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf6c5  ldarg.3
0xf6c6  ldstr    aBannerimageurl// "BannerImageUrl"
0xf6cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf6d0  ldarg.1
0xf6d1  ldloc.0
0xf6d2  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_BannerImageUrl()
0xf6d7  ldarg.3
0xf6d8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf6dd  ldarg.3
0xf6de  ldstr    aBannerimageurl// "BannerImageUrl"
0xf6e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf6e8  ldarg.0
0xf6e9  ldstr    aContenttypeid// "ContentTypeId"
0xf6ee  ldarg.3
0xf6ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf6f4  ldarg.1
0xf6f5  ldstr    aContenttypeid// "ContentTypeId"
0xf6fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf6ff  ldarg.3
0xf700  ldstr    aContenttypeid// "ContentTypeId"
0xf705  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf70a  ldarg.1
0xf70b  ldloc.0
0xf70c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_ContentTypeId()
0xf711  ldarg.3
0xf712  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf717  ldarg.3
0xf718  ldstr    aContenttypeid// "ContentTypeId"
0xf71d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf722  ldarg.0
0xf723  ldstr    aDescription// "Description"
0xf728  ldarg.3
0xf729  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf72e  ldarg.1
0xf72f  ldstr    aDescription// "Description"
0xf734  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf739  ldarg.3
0xf73a  ldstr    aDescription// "Description"
0xf73f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf744  ldarg.1
0xf745  ldloc.0
0xf746  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Description()
0xf74b  ldarg.3
0xf74c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf751  ldarg.3
0xf752  ldstr    aDescription// "Description"
0xf757  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf75c  ldarg.0
0xf75d  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xf762  ldarg.3
0xf763  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf768  ldarg.1
0xf769  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xf76e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf773  ldarg.3
0xf774  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xf779  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf77e  ldarg.1
0xf77f  ldloc.0
0xf780  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_DoesUserHaveEditPermission()
0xf785  ldarg.3
0xf786  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf78b  ldarg.3
0xf78c  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xf791  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf796  ldarg.0
0xf797  ldstr    aFilename// "FileName"
0xf79c  ldarg.3
0xf79d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf7a2  ldarg.1
0xf7a3  ldstr    aFilename// "FileName"
0xf7a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf7ad  ldarg.3
0xf7ae  ldstr    aFilename// "FileName"
0xf7b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf7b8  ldarg.1
0xf7b9  ldloc.0
0xf7ba  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_FileName()
0xf7bf  ldarg.3
0xf7c0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf7c5  ldarg.3
0xf7c6  ldstr    aFilename// "FileName"
0xf7cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf7d0  ldarg.0
0xf7d1  ldstr    aFirstpublished// "FirstPublished"
0xf7d6  ldarg.3
0xf7d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf7dc  ldarg.1
0xf7dd  ldstr    aFirstpublished// "FirstPublished"
0xf7e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf7e7  ldarg.3
0xf7e8  ldstr    aFirstpublished// "FirstPublished"
0xf7ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf7f2  ldarg.1
0xf7f3  ldloc.0
0xf7f4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_FirstPublished()
0xf7f9  ldarg.3
0xf7fa  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf7ff  ldarg.3
0xf800  ldstr    aFirstpublished// "FirstPublished"
0xf805  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf80a  ldarg.0
0xf80b  ldstr    aId// "Id"
0xf810  ldarg.3
0xf811  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf816  ldarg.1
0xf817  ldstr    aId// "Id"
0xf81c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf821  ldarg.3
0xf822  ldstr    aId// "Id"
0xf827  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf82c  ldarg.1
0xf82d  ldloc.0
0xf82e  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Id()
0xf833  ldarg.3
0xf834  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf839  ldarg.3
0xf83a  ldstr    aId// "Id"
0xf83f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf844  ldarg.0
0xf845  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xf84a  ldarg.3
0xf84b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf850  ldarg.1
0xf851  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xf856  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf85b  ldarg.3
0xf85c  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xf861  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf866  ldarg.1
0xf867  ldloc.0
0xf868  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_IsPageCheckedOutToCurrentUser()
0xf86d  ldarg.3
0xf86e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf873  ldarg.3
0xf874  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xf879  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf87e  ldarg.0
0xf87f  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xf884  ldarg.3
0xf885  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf88a  ldarg.1
0xf88b  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xf890  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf895  ldarg.3
0xf896  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xf89b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf8a0  ldarg.1
0xf8a1  ldloc.0
0xf8a2  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_IsWebWelcomePage()
0xf8a7  ldarg.3
0xf8a8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf8ad  ldarg.3
0xf8ae  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xf8b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf8b8  ldarg.0
0xf8b9  ldstr    aModified// "Modified"
0xf8be  ldarg.3
0xf8bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf8c4  ldarg.1
0xf8c5  ldstr    aModified// "Modified"
0xf8ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf8cf  ldarg.3
0xf8d0  ldstr    aModified// "Modified"
0xf8d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf8da  ldarg.1
0xf8db  ldloc.0
0xf8dc  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Modified()
0xf8e1  ldarg.3
0xf8e2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf8e7  ldarg.3
0xf8e8  ldstr    aModified// "Modified"
0xf8ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf8f2  ldarg.0
0xf8f3  ldstr    aPagelayouttype// "PageLayoutType"
0xf8f8  ldarg.3
0xf8f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf8fe  ldarg.1
0xf8ff  ldstr    aPagelayouttype// "PageLayoutType"
0xf904  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf909  ldarg.3
0xf90a  ldstr    aPagelayouttype// "PageLayoutType"
0xf90f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf914  ldarg.1
0xf915  ldloc.0
0xf916  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_PageLayoutType()
0xf91b  ldarg.3
0xf91c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf921  ldarg.3
0xf922  ldstr    aPagelayouttype// "PageLayoutType"
0xf927  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf92c  ldarg.0
0xf92d  ldstr    aPath_0// "Path"
0xf932  ldarg.3
0xf933  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf938  ldarg.1
0xf939  ldstr    aPath_0// "Path"
0xf93e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf943  ldarg.3
0xf944  ldstr    aPath_0// "Path"
0xf949  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf94e  ldarg.1
0xf94f  ldloc.0
0xf950  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Path()
0xf955  ldarg.3
0xf956  call     T0x2B00003B
0xf95b  ldarg.3
0xf95c  ldstr    aPath_0// "Path"
0xf961  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf966  ldarg.0
0xf967  ldstr    aPromotedstate_0// "PromotedState"
0xf96c  ldarg.3
0xf96d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf972  ldarg.1
0xf973  ldstr    aPromotedstate_0// "PromotedState"
0xf978  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf97d  ldarg.3
0xf97e  ldstr    aPromotedstate_0// "PromotedState"
0xf983  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf988  ldarg.1
0xf989  ldloc.0
0xf98a  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_PromotedState()
0xf98f  ldarg.3
0xf990  call     T0x2B00003A
0xf995  ldarg.3
0xf996  ldstr    aPromotedstate_0// "PromotedState"
0xf99b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf9a0  ldarg.0
0xf9a1  ldstr    aTitle// "Title"
0xf9a6  ldarg.3
0xf9a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf9ac  ldarg.1
0xf9ad  ldstr    aTitle// "Title"
0xf9b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf9b7  ldarg.3
0xf9b8  ldstr    aTitle// "Title"
0xf9bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf9c2  ldarg.1
0xf9c3  ldloc.0
0xf9c4  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Title()
0xf9c9  ldarg.3
0xf9ca  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf9cf  ldarg.3
0xf9d0  ldstr    aTitle// "Title"
0xf9d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xf9da  ldarg.0
0xf9db  ldstr    aUniqueid// "UniqueId"
0xf9e0  ldarg.3
0xf9e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf9e6  ldarg.1
0xf9e7  ldstr    aUniqueid// "UniqueId"
0xf9ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xf9f1  ldarg.3
0xf9f2  ldstr    aUniqueid// "UniqueId"
0xf9f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xf9fc  ldarg.1
0xf9fd  ldloc.0
0xf9fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_UniqueId()
0xfa03  ldarg.3
0xfa04  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xfa09  ldarg.3
0xfa0a  ldstr    aUniqueid// "UniqueId"
0xfa0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xfa14  ldarg.0
  ... truncated ...
```
