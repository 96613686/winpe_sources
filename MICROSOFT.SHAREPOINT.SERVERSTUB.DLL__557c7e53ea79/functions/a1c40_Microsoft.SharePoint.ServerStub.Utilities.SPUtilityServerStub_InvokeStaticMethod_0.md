# Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::InvokeStaticMethod_0

- ea: `0xa1c40`
- end: `0xa2107`
- name: `Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::InvokeStaticMethod_0`
- size: `1223`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0xa16c0`
- `0xa16e0`
- `0xa1740`
- `0xa17b0`
- `0xa1820`
- `0xa1890`
- `0xa18b0`
- `0xa18d0`
- `0xa1950`
- `0xa1960`
- `0xa1980`
- `0xa19b0`
- `0xa19e0`
- `0xa1a10`
- `0xa1a30`
- `0xa1a60`
- `0xa1a90`
- `0xa1ad0`
- `0xa1ae0`
- `0xa1b00`
- `0xa1b30`
- `0xa1b60`
- `0xa1b80`
- `0xa1bc0`
- `0xa1be0`
- `0xa1c10`
- `0xa1c20`
- `0xa1c40`

## string_xrefs

- `0xa1c74`: `CreateWikiPageInContextWeb`
- `0xa1e60`: `CreateWikiPageInContextWeb`
- `0xa1cfa`: `CreateNewDiscussion`
- `0xa1f78`: `CreateNewDiscussion`
- `0xa1d07`: `CreateNewDiscussionItem`
- `0xa1f90`: `CreateNewDiscussionItem`
- `0xa1d14`: `CreateNewDiscussionReply`
- `0xa1fa8`: `CreateNewDiscussionReply`
- `0xa1d55`: `CreateEmailBodyForInvitation`
- `0xa2022`: `CreateEmailBodyForInvitation`

## pseudocode

```c

```

## disassembly

```asm
0xa1c40  ldarg.3
0xa1c41  brtrue.s loc_A1C4E
0xa1c43  ldstr    aProxycontext// "proxyContext"
0xa1c48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa1c4d  throw
0xa1c4e  ldarg.0
0xa1c4f  ldarg.1
0xa1c50  ldarg.3
0xa1c51  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1c56  starg.s  1
0xa1c58  ldarg.1
0xa1c59  dup
0xa1c5a  stloc.0
0xa1c5b  brfalse  loc_A2100
0xa1c60  volatile.
0xa1c62  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a5f-1
0xa1c67  brtrue   loc_A1DD0
0xa1c6c  ldc.i4.s 0x1B
0xa1c6e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa1c73  dup
0xa1c74  ldstr    aCreatewikipage// "CreateWikiPageInContextWeb"
0xa1c79  ldc.i4.0
0xa1c7a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1c7f  dup
0xa1c80  ldstr    aSearchprincipa// "SearchPrincipalsUsingContextWeb"
0xa1c85  ldc.i4.1
0xa1c86  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1c8b  dup
0xa1c8c  ldstr    aSearchprincipa_0// "SearchPrincipals"
0xa1c91  ldc.i4.2
0xa1c92  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1c97  dup
0xa1c98  ldstr    aResolveprincip// "ResolvePrincipalInCurrentContext"
0xa1c9d  ldc.i4.3
0xa1c9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1ca3  dup
0xa1ca4  ldstr    aResolveprincip_0// "ResolvePrincipal"
0xa1ca9  ldc.i4.4
0xa1caa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1caf  dup
0xa1cb0  ldstr    aLocalizewebpar// "LocalizeWebPartGallery"
0xa1cb5  ldc.i4.5
0xa1cb6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cbb  dup
0xa1cbc  ldstr    aGetapplicensei// "GetAppLicenseInformation"
0xa1cc1  ldc.i4.6
0xa1cc2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cc7  dup
0xa1cc8  ldstr    aImportapplicen// "ImportAppLicense"
0xa1ccd  ldc.i4.7
0xa1cce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cd3  dup
0xa1cd4  ldstr    aGetapplicensed// "GetAppLicenseDeploymentId"
0xa1cd9  ldc.i4.8
0xa1cda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cdf  dup
0xa1ce0  ldstr    aLogcustomapper// "LogCustomAppError"
0xa1ce5  ldc.i4.s 9
0xa1ce7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cec  dup
0xa1ced  ldstr    aLogcustomremot// "LogCustomRemoteAppError"
0xa1cf2  ldc.i4.s 0xA
0xa1cf4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1cf9  dup
0xa1cfa  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0xa1cff  ldc.i4.s 0xB
0xa1d01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d06  dup
0xa1d07  ldstr    aCreatenewdiscu_0// "CreateNewDiscussionItem"
0xa1d0c  ldc.i4.s 0xC
0xa1d0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d13  dup
0xa1d14  ldstr    aCreatenewdiscu_1// "CreateNewDiscussionReply"
0xa1d19  ldc.i4.s 0xD
0xa1d1b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d20  dup
0xa1d21  ldstr    aMarkdiscussion// "MarkDiscussionAsFeatured"
0xa1d26  ldc.i4.s 0xE
0xa1d28  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d2d  dup
0xa1d2e  ldstr    aUnmarkdiscussi// "UnmarkDiscussionAsFeatured"
0xa1d33  ldc.i4.s 0xF
0xa1d35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d3a  dup
0xa1d3b  ldstr    aGetlocalizedst// "GetLocalizedString"
0xa1d40  ldc.i4.s 0x10
0xa1d42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d47  dup
0xa1d48  ldstr    aGetcurrentuser// "GetCurrentUserEmailAddresses"
0xa1d4d  ldc.i4.s 0x11
0xa1d4f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d54  dup
0xa1d55  ldstr    aCreateemailbod// "CreateEmailBodyForInvitation"
0xa1d5a  ldc.i4.s 0x12
0xa1d5c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d61  dup
0xa1d62  ldstr    aGetpeoplepicke// "GetPeoplePickerURL"
0xa1d67  ldc.i4.s 0x13
0xa1d69  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d6e  dup
0xa1d6f  ldstr    aExpandgroupsto// "ExpandGroupsToPrincipals"
0xa1d74  ldc.i4.s 0x14
0xa1d76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d7b  dup
0xa1d7c  ldstr    aIsemailservers// "IsEmailServerSet"
0xa1d81  ldc.i4.s 0x15
0xa1d83  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d88  dup
0xa1d89  ldstr    aFormatdatetime// "FormatDateTime"
0xa1d8e  ldc.i4.s 0x16
0xa1d90  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1d95  dup
0xa1d96  ldstr    aIsuserlicensed// "IsUserLicensedForEntityInContext"
0xa1d9b  ldc.i4.s 0x17
0xa1d9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1da2  dup
0xa1da3  ldstr    aGetlowercasest// "GetLowerCaseString"
0xa1da8  ldc.i4.s 0x18
0xa1daa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1daf  dup
0xa1db0  ldstr    aGetuserpermiss// "GetUserPermissionLevels"
0xa1db5  ldc.i4.s 0x19
0xa1db7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1dbc  dup
0xa1dbd  ldstr    aSendemail_1// "SendEmail"
0xa1dc2  ldc.i4.s 0x1A
0xa1dc4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa1dc9  volatile.
0xa1dcb  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a5f-1
0xa1dd0  volatile.
0xa1dd2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001a5f-1
0xa1dd7  ldloc.0
0xa1dd8  ldloca.s 1
0xa1dda  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa1ddf  brfalse  loc_A2100
0xa1de4  ldloc.1
0xa1de5  switch   loc_A1E5B, loc_A1E73, loc_A1E8B, loc_A1EA3, loc_A1EBB, loc_A1ED3, loc_A1EEB, loc_A1F03, loc_A1F1C, loc_A1F39, loc_A1F56, loc_A1F73, loc_A1F8B, loc_A1FA3, loc_A1FBB, loc_A1FD4, loc_A1FED, loc_A2005, loc_A201D, loc_A2035, loc_A204D, loc_A2065, loc_A2082, loc_A209A, loc_A20B7, loc_A20CF, loc_A20E7
0xa1e56  br       loc_A2100
0xa1e5b  ldarg.s  4
0xa1e5d  ldc.i4.0
0xa1e5e  stind.i1
0xa1e5f  ldarg.0
0xa1e60  ldstr    aCreatewikipage// "CreateWikiPageInContextWeb"
0xa1e65  ldarg.3
0xa1e66  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1e6b  ldarg.2
0xa1e6c  ldarg.3
0xa1e6d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateWikiPageInContextWeb_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1e72  ret
0xa1e73  ldarg.s  4
0xa1e75  ldc.i4.0
0xa1e76  stind.i1
0xa1e77  ldarg.0
0xa1e78  ldstr    aSearchprincipa// "SearchPrincipalsUsingContextWeb"
0xa1e7d  ldarg.3
0xa1e7e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1e83  ldarg.2
0xa1e84  ldarg.3
0xa1e85  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::SearchPrincipalsUsingContextWeb_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1e8a  ret
0xa1e8b  ldarg.s  4
0xa1e8d  ldc.i4.0
0xa1e8e  stind.i1
0xa1e8f  ldarg.0
0xa1e90  ldstr    aSearchprincipa_0// "SearchPrincipals"
0xa1e95  ldarg.3
0xa1e96  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1e9b  ldarg.2
0xa1e9c  ldarg.3
0xa1e9d  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::SearchPrincipals_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1ea2  ret
0xa1ea3  ldarg.s  4
0xa1ea5  ldc.i4.0
0xa1ea6  stind.i1
0xa1ea7  ldarg.0
0xa1ea8  ldstr    aResolveprincip// "ResolvePrincipalInCurrentContext"
0xa1ead  ldarg.3
0xa1eae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1eb3  ldarg.2
0xa1eb4  ldarg.3
0xa1eb5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ResolvePrincipalInCurrentContext_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1eba  ret
0xa1ebb  ldarg.s  4
0xa1ebd  ldc.i4.0
0xa1ebe  stind.i1
0xa1ebf  ldarg.0
0xa1ec0  ldstr    aResolveprincip_0// "ResolvePrincipal"
0xa1ec5  ldarg.3
0xa1ec6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1ecb  ldarg.2
0xa1ecc  ldarg.3
0xa1ecd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPrincipalInfo Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ResolvePrincipal_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1ed2  ret
0xa1ed3  ldarg.s  4
0xa1ed5  ldc.i4.0
0xa1ed6  stind.i1
0xa1ed7  ldarg.0
0xa1ed8  ldstr    aLocalizewebpar// "LocalizeWebPartGallery"
0xa1edd  ldarg.3
0xa1ede  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1ee3  ldarg.2
0xa1ee4  ldarg.3
0xa1ee5  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem> Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LocalizeWebPartGallery_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1eea  ret
0xa1eeb  ldarg.s  4
0xa1eed  ldc.i4.0
0xa1eee  stind.i1
0xa1eef  ldarg.0
0xa1ef0  ldstr    aGetapplicensei// "GetAppLicenseInformation"
0xa1ef5  ldarg.3
0xa1ef6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1efb  ldarg.2
0xa1efc  ldarg.3
0xa1efd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppLicenseCollection Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::GetAppLicenseInformation_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f02  ret
0xa1f03  ldarg.s  4
0xa1f05  ldc.i4.1
0xa1f06  stind.i1
0xa1f07  ldarg.0
0xa1f08  ldstr    aImportapplicen// "ImportAppLicense"
0xa1f0d  ldarg.3
0xa1f0e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f13  ldarg.2
0xa1f14  ldarg.3
0xa1f15  call     void Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::ImportAppLicense_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f1a  ldnull
0xa1f1b  ret
0xa1f1c  ldarg.s  4
0xa1f1e  ldc.i4.0
0xa1f1f  stind.i1
0xa1f20  ldarg.0
0xa1f21  ldstr    aGetapplicensed// "GetAppLicenseDeploymentId"
0xa1f26  ldarg.3
0xa1f27  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f2c  ldarg.2
0xa1f2d  ldarg.3
0xa1f2e  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::GetAppLicenseDeploymentId_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f33  box      [mscorlib]System.Guid
0xa1f38  ret
0xa1f39  ldarg.s  4
0xa1f3b  ldc.i4.0
0xa1f3c  stind.i1
0xa1f3d  ldarg.0
0xa1f3e  ldstr    aLogcustomapper// "LogCustomAppError"
0xa1f43  ldarg.3
0xa1f44  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f49  ldarg.2
0xa1f4a  ldarg.3
0xa1f4b  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LogCustomAppError_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f50  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult
0xa1f55  ret
0xa1f56  ldarg.s  4
0xa1f58  ldc.i4.0
0xa1f59  stind.i1
0xa1f5a  ldarg.0
0xa1f5b  ldstr    aLogcustomremot// "LogCustomRemoteAppError"
0xa1f60  ldarg.3
0xa1f61  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f66  ldarg.2
0xa1f67  ldarg.3
0xa1f68  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::LogCustomRemoteAppError_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f6d  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.LogAppErrorResult
0xa1f72  ret
0xa1f73  ldarg.s  4
0xa1f75  ldc.i4.0
0xa1f76  stind.i1
0xa1f77  ldarg.0
0xa1f78  ldstr    aCreatenewdiscu// "CreateNewDiscussion"
0xa1f7d  ldarg.3
0xa1f7e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f83  ldarg.2
0xa1f84  ldarg.3
0xa1f85  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussion_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1f8a  ret
0xa1f8b  ldarg.s  4
0xa1f8d  ldc.i4.0
0xa1f8e  stind.i1
0xa1f8f  ldarg.0
0xa1f90  ldstr    aCreatenewdiscu_0// "CreateNewDiscussionItem"
0xa1f95  ldarg.3
0xa1f96  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1f9b  ldarg.2
0xa1f9c  ldarg.3
0xa1f9d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussionItem_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1fa2  ret
0xa1fa3  ldarg.s  4
0xa1fa5  ldc.i4.0
0xa1fa6  stind.i1
0xa1fa7  ldarg.0
0xa1fa8  ldstr    aCreatenewdiscu_1// "CreateNewDiscussionReply"
0xa1fad  ldarg.3
0xa1fae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1fb3  ldarg.2
0xa1fb4  ldarg.3
0xa1fb5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem Microsoft.SharePoint.ServerStub.Utilities.SPUtilityServerStub::CreateNewDiscussionReply_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa1fba  ret
0xa1fbb  ldarg.s  4
0xa1fbd  ldc.i4.1
0xa1fbe  stind.i1
0xa1fbf  ldarg.0
  ... truncated ...
```
