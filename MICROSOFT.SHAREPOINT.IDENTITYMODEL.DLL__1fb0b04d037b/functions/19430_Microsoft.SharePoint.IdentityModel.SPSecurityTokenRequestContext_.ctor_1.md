# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor_1

- ea: `0x19430`
- end: `0x1984e`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor_1`
- size: `1054`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x19410`
- `0x19430`

## callees

- `0x19430`
- `0x198f0`
- `0x19d60`
- `0x19dc0`
- `0x19df0`
- `0x1ab20`
- `0x1b980`
- `0x1dc50`

## string_xrefs

- `0x19475`: `Creating SPSecurityTokenRequestContext object. InitializeForActor: '{0}', OverrideRequestType: '{1}'.`
- `0x1953e`: `Creating SPSecurityTokenRequestContext object for identity that is making act as request.`
- `0x195ff`: `Creating SPSecurityTokenRequestContext for actor identity on the on behalf of identity.`
- `0x19639`: `Creating SPSecurityTokenRequestContext object for identity making on behalf of request.`
- `0x19668`: `Creating SPSecurityTokenRequestContext object for identity making the on behalf of request.`
- `0x196c7`: `Setting up for identity that is making deletegate to request.`
- `0x196e6`: `Setting up for identity that is making deletegate to request.`
- `0x19703`: `Creating SPSecurityTokenRequestContext object for delegate to identity.`
- `0x197bb`: `Initializing SPSecurityTokenRequestContext for federation authentication type.`
- `0x19803`: `Initializing SPSecurityTokenRequestContext.`
- `0x19836`: `Initializing SPSecurityTokenRequestContext.`

## pseudocode

```c

```

## disassembly

```asm
0x19430  ldarg.0
0x19431  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_LastAttestationFileTimeUtc
0x19436  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x1943c  ldarg.0
0x1943d  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_NextCAPolicyCheckFileTimeUtc
0x19442  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x19448  ldarg.0
0x19449  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ExtendedCAPolicyCheckFileTimeUtc
0x1944e  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0x19454  ldarg.0
0x19455  ldc.i4.0
0x19456  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1945b  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_IsProofToken
0x19460  ldarg.0
0x19461  call     instance void [mscorlib]System.Object::.ctor()
0x19466  ldc.i4   0x17A365E
0x1946b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19470  ldc.i4   0xC8
0x19475  ldstr    aCreatingSpsecu// "Creating SPSecurityTokenRequestContext "...
0x1947a  ldc.i4.2
0x1947b  newarr   [mscorlib]System.Object
0x19480  stloc.2
0x19481  ldloc.2
0x19482  ldc.i4.0
0x19483  ldarg.3
0x19484  box      [mscorlib]System.Boolean
0x19489  stelem.ref
0x1948a  ldloc.2
0x1948b  ldc.i4.1
0x1948c  ldarg.s  4
0x1948e  box      Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType
0x19493  stelem.ref
0x19494  ldloc.2
0x19495  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1949a  ldarg.0
0x1949b  ldc.i4.0
0x1949c  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_LogonRequest
0x194a1  ldarg.0
0x194a2  ldarg.3
0x194a3  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_InitializedForActor
0x194a8  ldarg.3
0x194a9  brtrue   loc_1955C
0x194ae  ldarg.2
0x194af  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_ActAs()
0x194b4  brfalse  loc_1955C
0x194b9  ldarg.0
0x194ba  ldc.i4.1
0x194bb  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_IsActAsRequest
0x194c0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::AddProviderLookupLoggingKillSwitch
0x194c5  ldstr    a08282017// "08/28/2017"
0x194ca  ldstr    aAddproviderloo// "AddProviderLookupLogging"
0x194cf  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x194d4  brtrue.s loc_19505
0x194d6  ldc.i4   0x179A4C4
0x194db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x194e0  ldc.i4.s 0x64
0x194e2  ldstr    aSettingUpForId// "Setting up for identity that is being a"...
0x194e7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x194ec  ldarg.0
0x194ed  ldarg.2
0x194ee  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_ActAs()
0x194f3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x194f8  ldc.i4.0
0x194f9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x194fe  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::SetIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x19503  br.s     loc_19532
0x19505  ldc.i4   0x17A365F
0x1950a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1950f  ldc.i4.s 0x64
0x19511  ldstr    aSettingUpForId// "Setting up for identity that is being a"...
0x19516  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1951b  ldarg.0
0x1951c  ldarg.2
0x1951d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_ActAs()
0x19522  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x19527  ldc.i4.0
0x19528  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x1952d  stfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Identity
0x19532  ldc.i4   0x179A4C5
0x19537  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1953c  ldc.i4.s 0x64
0x1953e  ldstr    aCreatingSpsecu_0// "Creating SPSecurityTokenRequestContext "...
0x19543  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19548  ldarg.0
0x19549  ldarg.1
0x1954a  ldarg.2
0x1954b  ldc.i4.1
0x1954c  ldc.i4.0
0x1954d  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request, bool initializeForActor, [opt] valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x19552  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x19557  br       loc_19780
0x1955c  ldarg.3
0x1955d  brtrue   loc_19686
0x19562  ldarg.2
0x19563  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x19568  brfalse  loc_19686
0x1956d  ldarg.0
0x1956e  ldc.i4.1
0x1956f  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_IsOnBehalfOfRequest
0x19574  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::AddProviderLookupLoggingKillSwitch
0x19579  ldstr    a08282017// "08/28/2017"
0x1957e  ldstr    aAddproviderloo// "AddProviderLookupLogging"
0x19583  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x19588  brtrue.s loc_195B9
0x1958a  ldc.i4   0x179A4C6
0x1958f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19594  ldc.i4.s 0x64
0x19596  ldstr    aSettingUpForId_0// "Setting up for identity that the reques"...
0x1959b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x195a0  ldarg.0
0x195a1  ldarg.2
0x195a2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x195a7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x195ac  ldc.i4.0
0x195ad  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x195b2  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::SetIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x195b7  br.s     loc_195E6
0x195b9  ldc.i4   0x17A3660
0x195be  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x195c3  ldc.i4.s 0x64
0x195c5  ldstr    aSettingUpForId_0// "Setting up for identity that the reques"...
0x195ca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x195cf  ldarg.0
0x195d0  ldarg.2
0x195d1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x195d6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x195db  ldc.i4.0
0x195dc  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x195e1  stfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Identity
0x195e6  ldarg.0
0x195e7  ldfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Identity
0x195ec  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x195f1  brfalse.s loc_1965C
0x195f3  ldc.i4   0x179A4C7
0x195f8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x195fd  ldc.i4.s 0x64
0x195ff  ldstr    aCreatingSpsecu_1// "Creating SPSecurityTokenRequestContext "...
0x19604  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19609  ldarg.0
0x1960a  ldarg.2
0x1960b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_OnBehalfOf()
0x19610  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x19615  ldc.i4.0
0x19616  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x1961b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x19620  ldarg.2
0x19621  ldc.i4.1
0x19622  ldc.i4.1
0x19623  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request, bool initializeForActor, [opt] valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x19628  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x1962d  ldc.i4   0x179A4C8
0x19632  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19637  ldc.i4.s 0x64
0x19639  ldstr    aCreatingSpsecu_2// "Creating SPSecurityTokenRequestContext "...
0x1963e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19643  ldarg.0
0x19644  ldfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x19649  ldarg.1
0x1964a  ldarg.2
0x1964b  ldc.i4.1
0x1964c  ldc.i4.0
0x1964d  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request, bool initializeForActor, [opt] valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x19652  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x19657  br       loc_19780
0x1965c  ldc.i4   0x179A4C9
0x19661  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19666  ldc.i4.s 0x64
0x19668  ldstr    aCreatingSpsecu_3// "Creating SPSecurityTokenRequestContext "...
0x1966d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19672  ldarg.0
0x19673  ldarg.1
0x19674  ldarg.2
0x19675  ldc.i4.1
0x19676  ldc.i4.0
0x19677  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request, bool initializeForActor, [opt] valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x1967c  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x19681  br       loc_19780
0x19686  ldarg.3
0x19687  brtrue   loc_1972E
0x1968c  ldarg.2
0x1968d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_DelegateTo()
0x19692  brfalse  loc_1972E
0x19697  ldarg.0
0x19698  ldc.i4.1
0x19699  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_IsActAsRequest
0x1969e  ldarg.0
0x1969f  ldc.i4.1
0x196a0  stfld    bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_LogonRequest
0x196a5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::AddProviderLookupLoggingKillSwitch
0x196aa  ldstr    a08282017// "08/28/2017"
0x196af  ldstr    aAddproviderloo// "AddProviderLookupLogging"
0x196b4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x196b9  brtrue.s loc_196DA
0x196bb  ldc.i4   0x179A4CA
0x196c0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x196c5  ldc.i4.s 0x64
0x196c7  ldstr    aSettingUpForId_1// "Setting up for identity that is making "...
0x196cc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x196d1  ldarg.0
0x196d2  ldarg.1
0x196d3  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::SetIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x196d8  br.s     loc_196F7
0x196da  ldc.i4   0x17A3661
0x196df  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x196e4  ldc.i4.s 0x64
0x196e6  ldstr    aSettingUpForId_1// "Setting up for identity that is making "...
0x196eb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x196f0  ldarg.0
0x196f1  ldarg.1
0x196f2  stfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Identity
0x196f7  ldc.i4   0x179A4CB
0x196fc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19701  ldc.i4.s 0x64
0x19703  ldstr    aCreatingSpsecu_4// "Creating SPSecurityTokenRequestContext "...
0x19708  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1970d  ldarg.0
0x1970e  ldarg.2
0x1970f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken::get_DelegateTo()
0x19714  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenElement::GetSubject()
0x19719  ldc.i4.0
0x1971a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x1971f  ldarg.2
0x19720  ldc.i4.1
0x19721  ldc.i4.0
0x19722  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request, bool initializeForActor, [opt] valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x19727  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_ActorRequestInfo
0x1972c  br.s     loc_19780
0x1972e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::AddProviderLookupLoggingKillSwitch
0x19733  ldstr    a08282017// "08/28/2017"
0x19738  ldstr    aAddproviderloo// "AddProviderLookupLogging"
0x1973d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x19742  brtrue.s loc_19763
0x19744  ldc.i4   0x179A4CC
0x19749  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1974e  ldc.i4.s 0x64
0x19750  ldstr    aSettingUpForId_2// "Setting up for identity."
0x19755  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1975a  ldarg.0
0x1975b  ldarg.1
0x1975c  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::SetIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x19761  br.s     loc_19780
0x19763  ldc.i4   0x17A3662
0x19768  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1976d  ldc.i4.s 0x64
0x1976f  ldstr    aSettingUpForId_2// "Setting up for identity."
0x19774  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x19779  ldarg.0
0x1977a  ldarg.1
0x1977b  stfld    class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Identity
0x19780  ldarg.0
0x19781  ldarg.s  4
0x19783  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::SetOverrideRequestInfoType(valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestType overrideRequestType)
0x19788  ldarg.0
0x19789  ldarg.2
0x1978a  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken
0x1978f  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x19794  ldstr    aFederation// "federation"
0x19799  ldarg.0
0x1979a  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x1979f  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_AuthenticationType()
0x197a4  ldc.i4.5
0x197a5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x197aa  brfalse.s loc_197D2
0x197ac  ldc.i4   0x17A3663
0x197b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x197b6  ldc.i4   0xC8
0x197bb  ldstr    aInitializingSp// "Initializing SPSecurityTokenRequestCont"...
0x197c0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x197c5  ldarg.0
0x197c6  ldarg.0
0x197c7  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x197cc  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::InitializeForFederationAuthType(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken request)
0x197d1  ret
0x197d2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::AddProviderLookupLoggingKillSwitch
0x197d7  ldstr    a08282017// "08/28/2017"
0x197dc  ldstr    aAddproviderloo// "AddProviderLookupLogging"
0x197e1  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x197e6  brtrue.s loc_1981B
0x197e8  ldarg.0
0x197e9  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x197ee  call     string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetIdentityProviderValue(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x197f3  stloc.0
0x197f4  ldc.i4   0x17A3680
0x197f9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x197fe  ldc.i4   0xC8
0x19803  ldstr    aInitializingSp_0// "Initializing SPSecurityTokenRequestCont"...
0x19808  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1980d  ldarg.0
0x1980e  ldloc.0
0x1980f  ldarg.0
0x19810  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x19815  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::Initialize(string identityProviderClaimValue, class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken request)
0x1981a  ret
0x1981b  ldarg.0
0x1981c  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x19821  call     string Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetIdentityProviderValue(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x19826  stloc.1
0x19827  ldc.i4   0x17A3681
0x1982c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x19831  ldc.i4   0xC8
  ... truncated ...
```
