# Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::.cctor

- ea: `0xa650`
- end: `0xb40a`
- name: `Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::.cctor`
- size: `3514`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0xa650`
- `0xb590`
- `0xb5c0`
- `0xb5e0`
- `0xb600`
- `0xb620`
- `0xb640`
- `0xb660`

## string_xrefs

- `0xa7c6`: `Files.Read`
- `0xacbf`: `Files.Read`
- `0xa7cf`: `Files.ReadWrite`
- `0xade2`: `Files.ReadWrite`
- `0xa7e1`: `Sites.ReadWrite.All`
- `0xaa4e`: `Sites.ReadWrite.All`
- `0xaaff`: `Sites.ReadWrite.All`
- `0xab22`: `Sites.ReadWrite.All`
- `0xab78`: `Sites.ReadWrite.All`
- `0xab9b`: `Sites.ReadWrite.All`
- `0xabeb`: `Sites.ReadWrite.All`
- `0xac0e`: `Sites.ReadWrite.All`
- `0xac78`: `Sites.ReadWrite.All`
- `0xadeb`: `Sites.ReadWrite.All`
- `0xaf56`: `Sites.ReadWrite.All`
- `0xaf79`: `Sites.ReadWrite.All`
- `0xafc0`: `Sites.ReadWrite.All`
- `0xafe3`: `Sites.ReadWrite.All`
- `0xb266`: `Sites.ReadWrite.All`
- `0xb2c7`: `Sites.ReadWrite.All`
- `0xa7ea`: `User.Read.All`
- `0xaaa6`: `User.Read.All`
- `0xae29`: `User.Read.All`
- `0xaefe`: `User.Read.All`
- `0xb0f4`: `User.Read.All`
- `0xa822`: `Remove user impersonation scope for ODCSM`
- `0xa855`: `user.read.all`
- `0xa877`: `user.read.all`
- `0xa8c5`: `user.read.all`
- `0xa8f0`: `user.read.all`
- `0xa94c`: `user.read.all`
- `0xa96f`: `user.read.all`
- `0xa9c1`: `user.read.all`
- `0xa9ed`: `user.read.all`
- `0xa85e`: `Sites.Read.All`
- `0xa880`: `Sites.Read.All`
- `0xa8ce`: `Sites.Read.All`
- `0xa8f9`: `Sites.Read.All`
- `0xa955`: `Sites.Read.All`
- `0xa978`: `Sites.Read.All`
- `0xa9ca`: `Sites.Read.All`
- `0xa9f6`: `Sites.Read.All`
- `0xaab8`: `Sites.Read.All`
- `0xacc8`: `Sites.Read.All`
- `0xae20`: `Sites.Read.All`
- `0xae70`: `Sites.Read.All`
- `0xaef5`: `Sites.Read.All`
- `0xb0eb`: `Sites.Read.All`
- `0xa8bc`: `user_impersonation`
- `0xa8e7`: `user_impersonation`
- `0xa9b8`: `user_impersonation`
- `0xa9e4`: `user_impersonation`
- `0xa916`: `Remove user impersonation scope for ODCSM Fairfax`
- `0xaaaf`: `TermStore.Read.All`
- `0xadfd`: `User.ReadWrite.All`
- `0xae94`: `User.ReadWrite.All`
- `0xae79`: `MyFiles.Write`
- `0xae82`: `User.ReadWrite`
- `0xae8b`: `User.Read`
- `0xb1fc`: `AccessRequest.Approval`
- `0xb25d`: `Files.ReadWrite.All`
- `0xb2be`: `Files.ReadWrite.All`

## pseudocode

```c

```

## disassembly

```asm
0xa650  ldstr    a960404e42f4742// "960404e4-2f47-4259-9574-405fa3b7a3a6"
0xa655  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa65a  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::WhitelistGraphForPolicyKillSwitch
0xa65f  ldstr    aF00f7415496040// "f00f7415-4960-402f-9946-5b2550829c8c"
0xa664  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa669  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::WhitelistPlannerForPolicyKillSwitch
0xa66e  ldstr    a8438ee01723d44// "8438ee01-723d-4491-937f-7d3cacd21962"
0xa673  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa678  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::RemoveUserImpersonationForOdcsmKillSwitch
0xa67d  ldstr    aBc8bab892d9049// "bc8bab89-2d90-49b0-9b89-6a0a3badf868"
0xa682  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa687  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::RemoveUserImpersonationForOdcsmFairfaxKillSwitch
0xa68c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::.ctor()
0xa691  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa696  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::WhitelistGraphForPolicyKillSwitch
0xa69b  ldstr    a262018// "2/6/2018"
0xa6a0  ldstr    aWhitelistGraph// "Whitelist Graph for policy claims"
0xa6a5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0xa6aa  brfalse.s loc_A721
0xa6ac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa6b1  ldstr    a00000003000000// "00000003-0000-0000-c000-000000000000"
0xa6b6  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa6bb  stloc.0
0xa6bc  ldloc.0
0xa6bd  ldstr    a00000003000000// "00000003-0000-0000-c000-000000000000"
0xa6c2  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa6c7  ldloc.0
0xa6c8  ldc.i4.1
0xa6c9  newarr   [mscorlib]System.String
0xa6ce  stloc.s  0x1F
0xa6d0  ldloc.s  0x1F
0xa6d2  ldc.i4.0
0xa6d3  ldstr    asc_4091C// "*"
0xa6d8  stelem.ref
0xa6d9  ldloc.s  0x1F
0xa6db  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa6e0  ldloc.0
0xa6e1  ldc.i4.1
0xa6e2  newarr   [mscorlib]System.String
0xa6e7  stloc.s  0x20
0xa6e9  ldloc.s  0x20
0xa6eb  ldc.i4.0
0xa6ec  ldstr    asc_4091C// "*"
0xa6f1  stelem.ref
0xa6f2  ldloc.s  0x20
0xa6f4  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa6f9  ldloc.0
0xa6fa  ldc.i4.1
0xa6fb  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_ClientAppAssertionAllowed(bool value)
0xa700  ldloc.0
0xa701  ldc.i4.1
0xa702  newarr   [mscorlib]System.String
0xa707  stloc.s  0x21
0xa709  ldloc.s  0x21
0xa70b  ldc.i4.0
0xa70c  ldstr    a4345a7b99a6349// "4345a7b9-9a63-4910-a426-35363201d503"
0xa711  stelem.ref
0xa712  ldloc.s  0x21
0xa714  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_ClientAppsPolicy(string[] value)
0xa719  ldloc.0
0xa71a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa71f  br.s     loc_A79C
0xa721  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa726  ldstr    a00000003000000// "00000003-0000-0000-c000-000000000000"
0xa72b  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa730  stloc.1
0xa731  ldloc.1
0xa732  ldstr    a00000003000000// "00000003-0000-0000-c000-000000000000"
0xa737  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa73c  ldloc.1
0xa73d  ldc.i4.1
0xa73e  newarr   [mscorlib]System.String
0xa743  stloc.s  0x22
0xa745  ldloc.s  0x22
0xa747  ldc.i4.0
0xa748  ldstr    asc_4091C// "*"
0xa74d  stelem.ref
0xa74e  ldloc.s  0x22
0xa750  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa755  ldloc.1
0xa756  ldc.i4.1
0xa757  newarr   [mscorlib]System.String
0xa75c  stloc.s  0x23
0xa75e  ldloc.s  0x23
0xa760  ldc.i4.0
0xa761  ldstr    asc_4091C// "*"
0xa766  stelem.ref
0xa767  ldloc.s  0x23
0xa769  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa76e  ldloc.1
0xa76f  ldc.i4.1
0xa770  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_ClientAppAssertionAllowed(bool value)
0xa775  ldloc.1
0xa776  ldc.i4.1
0xa777  newarr   [mscorlib]System.String
0xa77c  stloc.s  0x24
0xa77e  ldloc.s  0x24
0xa780  ldc.i4.0
0xa781  ldstr    a4345a7b99a6349// "4345a7b9-9a63-4910-a426-35363201d503"
0xa786  stelem.ref
0xa787  ldloc.s  0x24
0xa789  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_ClientAppsPolicy(string[] value)
0xa78e  ldloc.1
0xa78f  ldc.i4.2
0xa790  conv.i8
0xa791  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_PoliciesImplemented(valuetype Microsoft.SharePoint.IdentityModel.SPAuthenticationPolicyImplemented value)
0xa796  ldloc.1
0xa797  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa79c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa7a1  ldstr    a1dc3210dFacc40// "1dc3210d-facc-40a1-88bc-0aa5df687d30"
0xa7a6  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa7ab  stloc.s  9
0xa7ad  ldloc.s  9
0xa7af  ldstr    a1dc3210dFacc40// "1dc3210d-facc-40a1-88bc-0aa5df687d30"
0xa7b4  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa7b9  ldloc.s  9
0xa7bb  ldc.i4.5
0xa7bc  newarr   [mscorlib]System.String
0xa7c1  stloc.s  0x25
0xa7c3  ldloc.s  0x25
0xa7c5  ldc.i4.0
0xa7c6  ldstr    aFilesRead// "Files.Read"
0xa7cb  stelem.ref
0xa7cc  ldloc.s  0x25
0xa7ce  ldc.i4.1
0xa7cf  ldstr    aFilesReadwrite_0// "Files.ReadWrite"
0xa7d4  stelem.ref
0xa7d5  ldloc.s  0x25
0xa7d7  ldc.i4.2
0xa7d8  ldstr    aSitesSearchAll// "Sites.Search.All"
0xa7dd  stelem.ref
0xa7de  ldloc.s  0x25
0xa7e0  ldc.i4.3
0xa7e1  ldstr    aSitesReadwrite// "Sites.ReadWrite.All"
0xa7e6  stelem.ref
0xa7e7  ldloc.s  0x25
0xa7e9  ldc.i4.4
0xa7ea  ldstr    aUserReadAll// "User.Read.All"
0xa7ef  stelem.ref
0xa7f0  ldloc.s  0x25
0xa7f2  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa7f7  ldloc.s  9
0xa7f9  ldc.i4.1
0xa7fa  newarr   [mscorlib]System.String
0xa7ff  stloc.s  0x26
0xa801  ldloc.s  0x26
0xa803  ldc.i4.0
0xa804  ldstr    asc_336C0// ""
0xa809  stelem.ref
0xa80a  ldloc.s  0x26
0xa80c  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa811  ldloc.s  9
0xa813  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa818  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::RemoveUserImpersonationForOdcsmKillSwitch
0xa81d  ldstr    a492018// "4/9/2018"
0xa822  ldstr    aRemoveUserImpe// "Remove user impersonation scope for ODC"...
0xa827  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0xa82c  brtrue.s loc_A895
0xa82e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa833  ldstr    a9e4a5442A5c94f// "9e4a5442-a5c9-4f6f-b03f-5b9fcaaf24b1"
0xa838  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa83d  stloc.2
0xa83e  ldloc.2
0xa83f  ldstr    a9e4a5442A5c94f// "9e4a5442-a5c9-4f6f-b03f-5b9fcaaf24b1"
0xa844  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa849  ldloc.2
0xa84a  ldc.i4.2
0xa84b  newarr   [mscorlib]System.String
0xa850  stloc.s  0x27
0xa852  ldloc.s  0x27
0xa854  ldc.i4.0
0xa855  ldstr    aUserReadAll_0// "user.read.all"
0xa85a  stelem.ref
0xa85b  ldloc.s  0x27
0xa85d  ldc.i4.1
0xa85e  ldstr    aSitesReadAll// "Sites.Read.All"
0xa863  stelem.ref
0xa864  ldloc.s  0x27
0xa866  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa86b  ldloc.2
0xa86c  ldc.i4.2
0xa86d  newarr   [mscorlib]System.String
0xa872  stloc.s  0x28
0xa874  ldloc.s  0x28
0xa876  ldc.i4.0
0xa877  ldstr    aUserReadAll_0// "user.read.all"
0xa87c  stelem.ref
0xa87d  ldloc.s  0x28
0xa87f  ldc.i4.1
0xa880  ldstr    aSitesReadAll// "Sites.Read.All"
0xa885  stelem.ref
0xa886  ldloc.s  0x28
0xa888  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa88d  ldloc.2
0xa88e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa893  br.s     loc_A90C
0xa895  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa89a  ldstr    a9e4a5442A5c94f// "9e4a5442-a5c9-4f6f-b03f-5b9fcaaf24b1"
0xa89f  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa8a4  stloc.3
0xa8a5  ldloc.3
0xa8a6  ldstr    a9e4a5442A5c94f// "9e4a5442-a5c9-4f6f-b03f-5b9fcaaf24b1"
0xa8ab  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa8b0  ldloc.3
0xa8b1  ldc.i4.3
0xa8b2  newarr   [mscorlib]System.String
0xa8b7  stloc.s  0x29
0xa8b9  ldloc.s  0x29
0xa8bb  ldc.i4.0
0xa8bc  ldstr    aUserImpersonat// "user_impersonation"
0xa8c1  stelem.ref
0xa8c2  ldloc.s  0x29
0xa8c4  ldc.i4.1
0xa8c5  ldstr    aUserReadAll_0// "user.read.all"
0xa8ca  stelem.ref
0xa8cb  ldloc.s  0x29
0xa8cd  ldc.i4.2
0xa8ce  ldstr    aSitesReadAll// "Sites.Read.All"
0xa8d3  stelem.ref
0xa8d4  ldloc.s  0x29
0xa8d6  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa8db  ldloc.3
0xa8dc  ldc.i4.3
0xa8dd  newarr   [mscorlib]System.String
0xa8e2  stloc.s  0x2A
0xa8e4  ldloc.s  0x2A
0xa8e6  ldc.i4.0
0xa8e7  ldstr    aUserImpersonat// "user_impersonation"
0xa8ec  stelem.ref
0xa8ed  ldloc.s  0x2A
0xa8ef  ldc.i4.1
0xa8f0  ldstr    aUserReadAll_0// "user.read.all"
0xa8f5  stelem.ref
0xa8f6  ldloc.s  0x2A
0xa8f8  ldc.i4.2
0xa8f9  ldstr    aSitesReadAll// "Sites.Read.All"
0xa8fe  stelem.ref
0xa8ff  ldloc.s  0x2A
0xa901  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa906  ldloc.3
0xa907  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa90c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::RemoveUserImpersonationForOdcsmFairfaxKillSwitch
0xa911  ldstr    a492018// "4/9/2018"
0xa916  ldstr    aRemoveUserImpe_0// "Remove user impersonation scope for ODC"...
0xa91b  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0xa920  brtrue.s loc_A98E
0xa922  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa927  ldstr    aFdcc4bb8C7a146// "fdcc4bb8-c7a1-469c-87a5-bce687a5fdf9"
0xa92c  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa931  stloc.s  4
0xa933  ldloc.s  4
0xa935  ldstr    aFdcc4bb8C7a146// "fdcc4bb8-c7a1-469c-87a5-bce687a5fdf9"
0xa93a  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa93f  ldloc.s  4
0xa941  ldc.i4.2
0xa942  newarr   [mscorlib]System.String
0xa947  stloc.s  0x2B
0xa949  ldloc.s  0x2B
0xa94b  ldc.i4.0
0xa94c  ldstr    aUserReadAll_0// "user.read.all"
0xa951  stelem.ref
0xa952  ldloc.s  0x2B
0xa954  ldc.i4.1
0xa955  ldstr    aSitesReadAll// "Sites.Read.All"
0xa95a  stelem.ref
0xa95b  ldloc.s  0x2B
0xa95d  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Scopes(string[] value)
0xa962  ldloc.s  4
0xa964  ldc.i4.2
0xa965  newarr   [mscorlib]System.String
0xa96a  stloc.s  0x2C
0xa96c  ldloc.s  0x2C
0xa96e  ldc.i4.0
0xa96f  ldstr    aUserReadAll_0// "user.read.all"
0xa974  stelem.ref
0xa975  ldloc.s  0x2C
0xa977  ldc.i4.1
0xa978  ldstr    aSitesReadAll// "Sites.Read.All"
0xa97d  stelem.ref
0xa97e  ldloc.s  0x2C
0xa980  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_Roles(string[] value)
0xa985  ldloc.s  4
0xa987  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp>::Add(var<u1>, !!T0)
0xa98c  br.s     loc_AA0A
0xa98e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.IdentityModel.EvoStsApp> Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::EvoStsApps
0xa993  ldstr    aFdcc4bb8C7a146// "fdcc4bb8-c7a1-469c-87a5-bce687a5fdf9"
0xa998  newobj   instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::.ctor()
0xa99d  stloc.s  5
0xa99f  ldloc.s  5
0xa9a1  ldstr    aFdcc4bb8C7a146// "fdcc4bb8-c7a1-469c-87a5-bce687a5fdf9"
0xa9a6  callvirt instance void Microsoft.SharePoint.IdentityModel.EvoStsApp::set_AppId(string value)
0xa9ab  ldloc.s  5
0xa9ad  ldc.i4.3
0xa9ae  newarr   [mscorlib]System.String
0xa9b3  stloc.s  0x2D
0xa9b5  ldloc.s  0x2D
0xa9b7  ldc.i4.0
0xa9b8  ldstr    aUserImpersonat// "user_impersonation"
0xa9bd  stelem.ref
0xa9be  ldloc.s  0x2D
  ... truncated ...
```
