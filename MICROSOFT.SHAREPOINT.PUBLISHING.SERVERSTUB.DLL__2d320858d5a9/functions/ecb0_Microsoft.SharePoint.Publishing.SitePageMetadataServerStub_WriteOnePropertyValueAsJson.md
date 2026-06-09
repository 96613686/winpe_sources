# Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WriteOnePropertyValueAsJson

- ea: `0xecb0`
- end: `0xf658`
- name: `Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WriteOnePropertyValueAsJson`
- size: `2472`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10420`

## callees

- `0xecb0`

## string_xrefs

- `0xed00`: `CommentsDisabled`
- `0xef7b`: `CommentsDisabled`
- `0xed18`: `CreatedBy`
- `0xf00f`: `CreatedBy`
- `0xed7b`: `IsWebWelcomePage`
- `0xf266`: `IsWebWelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0xecb0  ldc.i4.0
0xecb1  stloc.0
0xecb2  ldarg.2
0xecb3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata
0xecb8  stloc.1
0xecb9  ldloc.1
0xecba  brtrue.s loc_ECC7
0xecbc  ldstr    aTarget// "target"
0xecc1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xecc6  throw
0xecc7  ldarg.3
0xecc8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xeccd  dup
0xecce  stloc.2
0xeccf  brfalse  loc_F64A
0xecd4  volatile.
0xecd6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a9-1
0xecdb  brtrue   loc_EE37
0xece0  ldc.i4.s 0x1A
0xece2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xece7  dup
0xece8  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xeced  ldc.i4.0
0xecee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xecf3  dup
0xecf4  ldstr    aBannerimageurl// "BannerImageUrl"
0xecf9  ldc.i4.1
0xecfa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xecff  dup
0xed00  ldstr    aCommentsdisabl// "CommentsDisabled"
0xed05  ldc.i4.2
0xed06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed0b  dup
0xed0c  ldstr    aContenttypeid// "ContentTypeId"
0xed11  ldc.i4.3
0xed12  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed17  dup
0xed18  ldstr    aCreatedby// "CreatedBy"
0xed1d  ldc.i4.4
0xed1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed23  dup
0xed24  ldstr    aDescription// "Description"
0xed29  ldc.i4.5
0xed2a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed2f  dup
0xed30  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xed35  ldc.i4.6
0xed36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed3b  dup
0xed3c  ldstr    aFilename// "FileName"
0xed41  ldc.i4.7
0xed42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed47  dup
0xed48  ldstr    aFirstpublished// "FirstPublished"
0xed4d  ldc.i4.8
0xed4e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed53  dup
0xed54  ldstr    aFirstpublished_0// "FirstPublishedRelativeTime"
0xed59  ldc.i4.s 9
0xed5b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed60  dup
0xed61  ldstr    aId// "Id"
0xed66  ldc.i4.s 0xA
0xed68  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed6d  dup
0xed6e  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xed73  ldc.i4.s 0xB
0xed75  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed7a  dup
0xed7b  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xed80  ldc.i4.s 0xC
0xed82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed87  dup
0xed88  ldstr    aLastmodifiedby// "LastModifiedBy"
0xed8d  ldc.i4.s 0xD
0xed8f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xed94  dup
0xed95  ldstr    aListid// "ListId"
0xed9a  ldc.i4.s 0xE
0xed9c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xeda1  dup
0xeda2  ldstr    aModified// "Modified"
0xeda7  ldc.i4.s 0xF
0xeda9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedae  dup
0xedaf  ldstr    aModifiedrelati// "ModifiedRelativeTime"
0xedb4  ldc.i4.s 0x10
0xedb6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedbb  dup
0xedbc  ldstr    aPagelayouttype// "PageLayoutType"
0xedc1  ldc.i4.s 0x11
0xedc3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedc8  dup
0xedc9  ldstr    aPath_0// "Path"
0xedce  ldc.i4.s 0x12
0xedd0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedd5  dup
0xedd6  ldstr    aPromotedstate_0// "PromotedState"
0xeddb  ldc.i4.s 0x13
0xeddd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xede2  dup
0xede3  ldstr    aSocialbaronsit// "SocialBarOnSitePagesDisabled"
0xede8  ldc.i4.s 0x14
0xedea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedef  dup
0xedf0  ldstr    aTitle// "Title"
0xedf5  ldc.i4.s 0x15
0xedf7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xedfc  dup
0xedfd  ldstr    aUniqueid// "UniqueId"
0xee02  ldc.i4.s 0x16
0xee04  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xee09  dup
0xee0a  ldstr    aUrl// "Url"
0xee0f  ldc.i4.s 0x17
0xee11  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xee16  dup
0xee17  ldstr    aVersion_0// "Version"
0xee1c  ldc.i4.s 0x18
0xee1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xee23  dup
0xee24  ldstr    aVersioninfo// "VersionInfo"
0xee29  ldc.i4.s 0x19
0xee2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xee30  volatile.
0xee32  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a9-1
0xee37  volatile.
0xee39  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a9-1
0xee3e  ldloc.2
0xee3f  ldloca.s 3
0xee41  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xee46  brfalse  loc_F64A
0xee4b  ldloc.3
0xee4c  switch   loc_EEBE, loc_EF08, loc_EF52, loc_EF9C, loc_EFE6, loc_F037, loc_F081, loc_F0CB, loc_F115, loc_F15F, loc_F1A9, loc_F1F3, loc_F23D, loc_F287, loc_F2D8, loc_F322, loc_F36C, loc_F3B6, loc_F400, loc_F44A, loc_F494, loc_F4DE, loc_F528, loc_F572, loc_F5BC, loc_F603
0xeeb9  br       loc_F64A
0xeebe  ldarg.3
0xeebf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xeec4  stloc.s  4
0xeec6  ldloca.s 4
0xeec8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xeecd  brfalse.s loc_EEE6
0xeecf  ldarg.3
0xeed0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xeed5  stloc.s  5
0xeed7  ldloca.s 5
0xeed9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xeede  brtrue.s loc_EEE6
0xeee0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xeee5  throw
0xeee6  ldarg.0
0xeee7  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xeeec  ldarg.s  4
0xeeee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xeef3  ldc.i4.1
0xeef4  stloc.0
0xeef5  ldarg.1
0xeef6  ldloc.1
0xeef7  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_AbsoluteUrl()
0xeefc  ldarg.s  4
0xeefe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xef03  br       loc_F656
0xef08  ldarg.3
0xef09  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xef0e  stloc.s  6
0xef10  ldloca.s 6
0xef12  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xef17  brfalse.s loc_EF30
0xef19  ldarg.3
0xef1a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xef1f  stloc.s  7
0xef21  ldloca.s 7
0xef23  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xef28  brtrue.s loc_EF30
0xef2a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xef2f  throw
0xef30  ldarg.0
0xef31  ldstr    aBannerimageurl// "BannerImageUrl"
0xef36  ldarg.s  4
0xef38  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xef3d  ldc.i4.1
0xef3e  stloc.0
0xef3f  ldarg.1
0xef40  ldloc.1
0xef41  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_BannerImageUrl()
0xef46  ldarg.s  4
0xef48  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xef4d  br       loc_F656
0xef52  ldarg.3
0xef53  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xef58  stloc.s  8
0xef5a  ldloca.s 8
0xef5c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xef61  brfalse.s loc_EF7A
0xef63  ldarg.3
0xef64  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xef69  stloc.s  9
0xef6b  ldloca.s 9
0xef6d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xef72  brtrue.s loc_EF7A
0xef74  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xef79  throw
0xef7a  ldarg.0
0xef7b  ldstr    aCommentsdisabl// "CommentsDisabled"
0xef80  ldarg.s  4
0xef82  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xef87  ldc.i4.1
0xef88  stloc.0
0xef89  ldarg.1
0xef8a  ldloc.1
0xef8b  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_CommentsDisabled()
0xef90  ldarg.s  4
0xef92  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xef97  br       loc_F656
0xef9c  ldarg.3
0xef9d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xefa2  stloc.s  0xA
0xefa4  ldloca.s 0xA
0xefa6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xefab  brfalse.s loc_EFC4
0xefad  ldarg.3
0xefae  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xefb3  stloc.s  0xB
0xefb5  ldloca.s 0xB
0xefb7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xefbc  brtrue.s loc_EFC4
0xefbe  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xefc3  throw
0xefc4  ldarg.0
0xefc5  ldstr    aContenttypeid// "ContentTypeId"
0xefca  ldarg.s  4
0xefcc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xefd1  ldc.i4.1
0xefd2  stloc.0
0xefd3  ldarg.1
0xefd4  ldloc.1
0xefd5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_ContentTypeId()
0xefda  ldarg.s  4
0xefdc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xefe1  br       loc_F656
0xefe6  ldarg.3
0xefe7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xefec  stloc.s  0xC
0xefee  ldloca.s 0xC
0xeff0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xeff5  brfalse.s loc_F00E
0xeff7  ldarg.3
0xeff8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xeffd  stloc.s  0xD
0xefff  ldloca.s 0xD
0xf001  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xf006  brfalse.s loc_F00E
0xf008  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xf00d  throw
0xf00e  ldarg.0
0xf00f  ldstr    aCreatedby// "CreatedBy"
0xf014  ldarg.s  4
0xf016  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf01b  ldc.i4.1
0xf01c  stloc.0
0xf01d  ldarg.0
0xf01e  ldarg.1
0xf01f  ldloc.1
0xf020  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_CreatedBy()
0xf025  ldarg.3
0xf026  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xf02b  ldarg.s  4
0xf02d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf032  br       loc_F656
0xf037  ldarg.3
0xf038  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xf03d  stloc.s  0xE
0xf03f  ldloca.s 0xE
0xf041  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xf046  brfalse.s loc_F05F
0xf048  ldarg.3
0xf049  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xf04e  stloc.s  0xF
0xf050  ldloca.s 0xF
0xf052  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xf057  brtrue.s loc_F05F
0xf059  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xf05e  throw
0xf05f  ldarg.0
0xf060  ldstr    aDescription// "Description"
0xf065  ldarg.s  4
0xf067  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf06c  ldc.i4.1
0xf06d  stloc.0
0xf06e  ldarg.1
0xf06f  ldloc.1
0xf070  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Description()
0xf075  ldarg.s  4
0xf077  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xf07c  br       loc_F656
0xf081  ldarg.3
0xf082  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xf087  stloc.s  0x10
0xf089  ldloca.s 0x10
0xf08b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xf090  brfalse.s loc_F0A9
  ... truncated ...
```
