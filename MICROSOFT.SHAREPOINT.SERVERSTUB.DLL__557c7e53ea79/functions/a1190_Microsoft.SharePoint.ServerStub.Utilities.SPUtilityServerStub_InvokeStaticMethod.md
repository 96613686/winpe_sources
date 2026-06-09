# Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::InvokeStaticMethod

- ea: `0xa1190`
- end: `0xa1657`
- name: `Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::InvokeStaticMethod`
- size: `1223`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0xa0bd0`
- `0xa0bf0`
- `0xa0c50`
- `0xa0cd0`
- `0xa0d50`
- `0xa0dd0`
- `0xa0df0`
- `0xa0e10`
- `0xa0ea0`
- `0xa0eb0`
- `0xa0ed0`
- `0xa0f00`
- `0xa0f30`
- `0xa0f60`
- `0xa0f80`
- `0xa0fb0`
- `0xa0fe0`
- `0xa1020`
- `0xa1030`
- `0xa1050`
- `0xa1080`
- `0xa10b0`
- `0xa10d0`
- `0xa1110`
- `0xa1130`
- `0xa1160`
- `0xa1170`
- `0xa1190`

## string_xrefs

- `0xa11c4`: `CreateWikiPageInContextWeb`
- `0xa13b0`: `CreateWikiPageInContextWeb`
- `0xa124a`: `CreateNewDiscussion`
- `0xa14c8`: `CreateNewDiscussion`
- `0xa1257`: `CreateNewDiscussionItem`
- `0xa14e0`: `CreateNewDiscussionItem`
- `0xa1264`: `CreateNewDiscussionReply`
- `0xa14f8`: `CreateNewDiscussionReply`
- `0xa12a5`: `CreateEmailBodyForInvitation`
- `0xa1572`: `CreateEmailBodyForInvitation`

## pseudocode

```c

```

## disassembly

```asm
0xa1190  ldarg.3
0xa1191  brtrue.s loc_A119E
0xa1193  ldstr    aProxycontext// "proxyContext"
0xa1198  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa119d  throw
0xa119e  ldarg.0
0xa119f  ldarg.1
0xa11a0  ldarg.3
0xa11a1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa11a6  starg.s  1
0xa11a8  ldarg.1
0xa11a9  dup
0xa11aa  stloc.0
0xa11ab  brfalse  loc_A1650
0xa11b0  volatile.
0xa11b2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a40-1
0xa11b7  brtrue   loc_A1320
0xa11bc  ldc.i4.s 0x1B
0xa11be  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa11c3  dup
0xa11c4  ldstr    aCreatewikipage// "CreateWikiPageInContextWeb"
0xa11c9  ldc.i4.0
0xa11ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11cf  dup
0xa11d0  ldstr    aSearchprincipa// "SearchPrincipalsUsingContextWeb"
0xa11d5  ldc.i4.1
0xa11d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11db  dup
0xa11dc  ldstr    aSearchprincipa_0// "SearchPrincipals"
0xa11e1  ldc.i4.2
0xa11e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11e7  dup
0xa11e8  ldstr    aResolveprincip// "ResolvePrincipalInCurrentContext"
0xa11ed  ldc.i4.3
0xa11ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11f3  dup
0xa11f4  ldstr    aResolveprincip_0// "ResolvePrincipal"
0xa11f9  ldc.i4.4
0xa11fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa11ff  dup
0xa1200  ldstr    aLocalizewebpar// "LocalizeWebPartGallery"
0xa1205  ldc.i4.5
0xa1206  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa120b  dup
0xa120c  ldstr    aGetapplicensei// "GetAppLicenseInformation"
0xa1211  ldc.i4.6
0xa1212  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1217  dup
0xa1218  ldstr    aImportapplicen// "ImportAppLicense"
0xa121d  ldc.i4.7
0xa121e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1223  dup
0xa1224  ldstr    aGetapplicensed// "GetAppLicenseDeploymentId"
0xa1229  ldc.i4.8
0xa122a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa122f  dup
0xa1230  ldstr    aLogcustomapper// "LogCustomAppError"
0xa1235  ldc.i4.s 9
0xa1237  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa123c  dup
0xa123d  ldstr    aLogcustomremot// "LogCustomRemoteAppError"
0xa1242  ldc.i4.s 0xA
0xa1244  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1249  dup
0xa124a  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0xa124f  ldc.i4.s 0xB
0xa1251  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1256  dup
0xa1257  ldstr    aCreatenewdiscu_0// "CreateNewDiscussionItem"
0xa125c  ldc.i4.s 0xC
0xa125e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1263  dup
0xa1264  ldstr    aCreatenewdiscu_1// "CreateNewDiscussionReply"
0xa1269  ldc.i4.s 0xD
0xa126b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1270  dup
0xa1271  ldstr    aMarkdiscussion// "MarkDiscussionAsFeatured"
0xa1276  ldc.i4.s 0xE
0xa1278  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa127d  dup
0xa127e  ldstr    aUnmarkdiscussi// "UnmarkDiscussionAsFeatured"
0xa1283  ldc.i4.s 0xF
0xa1285  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa128a  dup
0xa128b  ldstr    aGetlocalizedst// "GetLocalizedString"
0xa1290  ldc.i4.s 0x10
0xa1292  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1297  dup
0xa1298  ldstr    aGetcurrentuser// "GetCurrentUserEmailAddresses"
0xa129d  ldc.i4.s 0x11
0xa129f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12a4  dup
0xa12a5  ldstr    aCreateemailbod// "CreateEmailBodyForInvitation"
0xa12aa  ldc.i4.s 0x12
0xa12ac  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12b1  dup
0xa12b2  ldstr    aGetpeoplepicke// "GetPeoplePickerURL"
0xa12b7  ldc.i4.s 0x13
0xa12b9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12be  dup
0xa12bf  ldstr    aExpandgroupsto// "ExpandGroupsToPrincipals"
0xa12c4  ldc.i4.s 0x14
0xa12c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12cb  dup
0xa12cc  ldstr    aIsemailservers// "IsEmailServerSet"
0xa12d1  ldc.i4.s 0x15
0xa12d3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12d8  dup
0xa12d9  ldstr    aFormatdatetime// "FormatDateTime"
0xa12de  ldc.i4.s 0x16
0xa12e0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12e5  dup
0xa12e6  ldstr    aIsuserlicensed// "IsUserLicensedForEntityInContext"
0xa12eb  ldc.i4.s 0x17
0xa12ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12f2  dup
0xa12f3  ldstr    aGetlowercasest// "GetLowerCaseString"
0xa12f8  ldc.i4.s 0x18
0xa12fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa12ff  dup
0xa1300  ldstr    aGetuserpermiss// "GetUserPermissionLevels"
0xa1305  ldc.i4.s 0x19
0xa1307  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa130c  dup
0xa130d  ldstr    aSendemail_1// "SendEmail"
0xa1312  ldc.i4.s 0x1A
0xa1314  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1319  volatile.
0xa131b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a40-1
0xa1320  volatile.
0xa1322  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a40-1
0xa1327  ldloc.0
0xa1328  ldloca.s 1
0xa132a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa132f  brfalse  loc_A1650
0xa1334  ldloc.1
0xa1335  switch   loc_A13AB, loc_A13C3, loc_A13DB, loc_A13F3, loc_A140B, loc_A1423, loc_A143B, loc_A1453, loc_A146C, loc_A1489, loc_A14A6, loc_A14C3, loc_A14DB, loc_A14F3, loc_A150B, loc_A1524, loc_A153D, loc_A1555, loc_A156D, loc_A1585, loc_A159D, loc_A15B5, loc_A15D2, loc_A15EA, loc_A1607, loc_A161F, loc_A1637
0xa13a6  br       loc_A1650
0xa13ab  ldarg.s  4
0xa13ad  ldc.i4.0
0xa13ae  stind.i1
0xa13af  ldarg.0
0xa13b0  ldstr    aCreatewikipage// "CreateWikiPageInContextWeb"
0xa13b5  ldarg.3
0xa13b6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa13bb  ldarg.2
0xa13bc  ldarg.3
0xa13bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateWikiPageInContextWeb_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa13c2  ret
0xa13c3  ldarg.s  4
0xa13c5  ldc.i4.0
0xa13c6  stind.i1
0xa13c7  ldarg.0
0xa13c8  ldstr    aSearchprincipa// "SearchPrincipalsUsingContextWeb"
0xa13cd  ldarg.3
0xa13ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa13d3  ldarg.2
0xa13d4  ldarg.3
0xa13d5  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::SearchPrincipalsUsingContextWeb_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa13da  ret
0xa13db  ldarg.s  4
0xa13dd  ldc.i4.0
0xa13de  stind.i1
0xa13df  ldarg.0
0xa13e0  ldstr    aSearchprincipa_0// "SearchPrincipals"
0xa13e5  ldarg.3
0xa13e6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa13eb  ldarg.2
0xa13ec  ldarg.3
0xa13ed  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::SearchPrincipals_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa13f2  ret
0xa13f3  ldarg.s  4
0xa13f5  ldc.i4.0
0xa13f6  stind.i1
0xa13f7  ldarg.0
0xa13f8  ldstr    aResolveprincip// "ResolvePrincipalInCurrentContext"
0xa13fd  ldarg.3
0xa13fe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1403  ldarg.2
0xa1404  ldarg.3
0xa1405  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ResolvePrincipalInCurrentContext_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa140a  ret
0xa140b  ldarg.s  4
0xa140d  ldc.i4.0
0xa140e  stind.i1
0xa140f  ldarg.0
0xa1410  ldstr    aResolveprincip_0// "ResolvePrincipal"
0xa1415  ldarg.3
0xa1416  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa141b  ldarg.2
0xa141c  ldarg.3
0xa141d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ResolvePrincipal_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1422  ret
0xa1423  ldarg.s  4
0xa1425  ldc.i4.0
0xa1426  stind.i1
0xa1427  ldarg.0
0xa1428  ldstr    aLocalizewebpar// "LocalizeWebPartGallery"
0xa142d  ldarg.3
0xa142e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1433  ldarg.2
0xa1434  ldarg.3
0xa1435  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LocalizeWebPartGallery_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa143a  ret
0xa143b  ldarg.s  4
0xa143d  ldc.i4.0
0xa143e  stind.i1
0xa143f  ldarg.0
0xa1440  ldstr    aGetapplicensei// "GetAppLicenseInformation"
0xa1445  ldarg.3
0xa1446  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa144b  ldarg.2
0xa144c  ldarg.3
0xa144d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppLicenseCollection Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::GetAppLicenseInformation_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1452  ret
0xa1453  ldarg.s  4
0xa1455  ldc.i4.1
0xa1456  stind.i1
0xa1457  ldarg.0
0xa1458  ldstr    aImportapplicen// "ImportAppLicense"
0xa145d  ldarg.3
0xa145e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1463  ldarg.2
0xa1464  ldarg.3
0xa1465  call     void Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ImportAppLicense_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa146a  ldnull
0xa146b  ret
0xa146c  ldarg.s  4
0xa146e  ldc.i4.0
0xa146f  stind.i1
0xa1470  ldarg.0
0xa1471  ldstr    aGetapplicensed// "GetAppLicenseDeploymentId"
0xa1476  ldarg.3
0xa1477  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa147c  ldarg.2
0xa147d  ldarg.3
0xa147e  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::GetAppLicenseDeploymentId_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1483  box      [mscorlib]System.Guid
0xa1488  ret
0xa1489  ldarg.s  4
0xa148b  ldc.i4.0
0xa148c  stind.i1
0xa148d  ldarg.0
0xa148e  ldstr    aLogcustomapper// "LogCustomAppError"
0xa1493  ldarg.3
0xa1494  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1499  ldarg.2
0xa149a  ldarg.3
0xa149b  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LogCustomAppError_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa14a0  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult
0xa14a5  ret
0xa14a6  ldarg.s  4
0xa14a8  ldc.i4.0
0xa14a9  stind.i1
0xa14aa  ldarg.0
0xa14ab  ldstr    aLogcustomremot// "LogCustomRemoteAppError"
0xa14b0  ldarg.3
0xa14b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa14b6  ldarg.2
0xa14b7  ldarg.3
0xa14b8  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LogCustomRemoteAppError_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa14bd  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult
0xa14c2  ret
0xa14c3  ldarg.s  4
0xa14c5  ldc.i4.0
0xa14c6  stind.i1
0xa14c7  ldarg.0
0xa14c8  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0xa14cd  ldarg.3
0xa14ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa14d3  ldarg.2
0xa14d4  ldarg.3
0xa14d5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussion_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa14da  ret
0xa14db  ldarg.s  4
0xa14dd  ldc.i4.0
0xa14de  stind.i1
0xa14df  ldarg.0
0xa14e0  ldstr    aCreatenewdiscu_0// "CreateNewDiscussionItem"
0xa14e5  ldarg.3
0xa14e6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa14eb  ldarg.2
0xa14ec  ldarg.3
0xa14ed  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussionItem_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa14f2  ret
0xa14f3  ldarg.s  4
0xa14f5  ldc.i4.0
0xa14f6  stind.i1
0xa14f7  ldarg.0
0xa14f8  ldstr    aCreatenewdiscu_1// "CreateNewDiscussionReply"
0xa14fd  ldarg.3
0xa14fe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1503  ldarg.2
0xa1504  ldarg.3
0xa1505  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussionReply_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa150a  ret
0xa150b  ldarg.s  4
0xa150d  ldc.i4.1
0xa150e  stind.i1
0xa150f  ldarg.0
  ... truncated ...
```
