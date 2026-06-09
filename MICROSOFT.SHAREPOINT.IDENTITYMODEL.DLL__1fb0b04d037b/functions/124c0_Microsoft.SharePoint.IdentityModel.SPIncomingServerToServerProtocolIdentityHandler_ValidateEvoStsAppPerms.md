# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateEvoStsAppPerms

- ea: `0x124c0`
- end: `0x12846`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateEvoStsAppPerms`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb480`
- `0xb4d0`
- `0x124c0`
- `0x12fc0`
- `0x13010`

## string_xrefs

- `0x124e5`: `SPIncomingIdentityHandler: This is not an Evo Sts Token.`
- `0x1254a`: `SPIncomingIdentityHandler: Validate scopes for app_asserted_user_v1 token type.`
- `0x12577`: `SPIncomingIdentityHandler: {0}`
- `0x125b9`: `SPIncomingIdentityHandler: {0}`
- `0x125fb`: `SPIncomingIdentityHandler: {0}`
- `0x1268d`: `SPIncomingIdentityHandler: {0}`
- `0x1270c`: `SPIncomingIdentityHandler: {0}`
- `0x1274e`: `SPIncomingIdentityHandler: {0}`
- `0x12790`: `SPIncomingIdentityHandler: {0}`
- `0x126df`: `SPIncomingIdentityHandler: Validate roles for service_asserted_app_v1 token type.`
- `0x126f9`: `Role Claim does not exist for Service Asserted App V1.`
- `0x1273b`: `Scope Claim is not allowed for Service Asserted App V1.`
- `0x1277d`: `App Id claim type is null for Service Asserted App V1.`
- `0x1281b`: `SPIncomingIdentityHandler: `

## pseudocode

```c

```

## disassembly

```asm
0x124c0  ldarg.0
0x124c1  ldind.ref
0x124c2  brtrue.s loc_124CF
0x124c4  ldstr    aResult_0// "result"
0x124c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x124ce  throw
0x124cf  ldc.i4.1
0x124d0  ldarg.0
0x124d1  ldind.ref
0x124d2  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x124d7  beq.s    loc_124F0
0x124d9  ldc.i4   0x1062615
0x124de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x124e3  ldc.i4.s 0x32
0x124e5  ldstr    aSpincomingiden// "SPIncomingIdentityHandler: This is not "...
0x124ea  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x124ef  ret
0x124f0  ldarg.0
0x124f1  ldind.ref
0x124f2  ldc.i4.0
0x124f3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x124f8  stloc.0
0x124f9  ldloc.0
0x124fa  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x124ff  ldstr    aScp// "scp"
0x12504  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12509  stloc.1
0x1250a  ldloc.0
0x1250b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12510  ldstr    aRoles// "roles"
0x12515  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1251a  stloc.2
0x1251b  ldloc.0
0x1251c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12521  ldstr    aAppid// "appid"
0x12526  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1252b  stloc.3
0x1252c  ldstr    asc_336C0// ""
0x12531  stloc.s  4
0x12533  ldloc.0
0x12534  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsAppAssertedUserV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x12539  brfalse  loc_126C8
0x1253e  ldc.i4   0x1062616
0x12543  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12548  ldc.i4.s 0x32
0x1254a  ldstr    aSpincomingiden_0// "SPIncomingIdentityHandler: Validate sco"...
0x1254f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12554  ldloc.1
0x12555  brfalse.s loc_12564
0x12557  ldloc.1
0x12558  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1255d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12562  brfalse.s loc_125A3
0x12564  ldstr    aScopeClaimDoes// "Scope Claim does not exist for App Asse"...
0x12569  stloc.s  4
0x1256b  ldc.i4   0x1062617
0x12570  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12575  ldc.i4.s 0x32
0x12577  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x1257c  ldc.i4.1
0x1257d  newarr   [mscorlib]System.Object
0x12582  stloc.s  0xA
0x12584  ldloc.s  0xA
0x12586  ldc.i4.0
0x12587  ldloc.s  4
0x12589  stelem.ref
0x1258a  ldloc.s  0xA
0x1258c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12591  ldc.i4   0x2DCAAB
0x12596  ldloc.s  4
0x12598  ldc.i4   0x191
0x1259d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x125a2  throw
0x125a3  ldloc.2
0x125a4  brfalse.s loc_125E5
0x125a6  ldstr    aRoleClaimIsNot// "Role Claim is not allowed for App Asser"...
0x125ab  stloc.s  4
0x125ad  ldc.i4   0x1062618
0x125b2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x125b7  ldc.i4.s 0xA
0x125b9  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x125be  ldc.i4.1
0x125bf  newarr   [mscorlib]System.Object
0x125c4  stloc.s  0xB
0x125c6  ldloc.s  0xB
0x125c8  ldc.i4.0
0x125c9  ldloc.s  4
0x125cb  stelem.ref
0x125cc  ldloc.s  0xB
0x125ce  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x125d3  ldc.i4   0x2DCAAC
0x125d8  ldloc.s  4
0x125da  ldc.i4   0x191
0x125df  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x125e4  throw
0x125e5  ldloc.3
0x125e6  brtrue.s loc_12627
0x125e8  ldstr    aAppIdClaimType// "App Id claim type is null for App Asser"...
0x125ed  stloc.s  4
0x125ef  ldc.i4   0x1062619
0x125f4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x125f9  ldc.i4.s 0xA
0x125fb  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x12600  ldc.i4.1
0x12601  newarr   [mscorlib]System.Object
0x12606  stloc.s  0xC
0x12608  ldloc.s  0xC
0x1260a  ldc.i4.0
0x1260b  ldloc.s  4
0x1260d  stelem.ref
0x1260e  ldloc.s  0xC
0x12610  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12615  ldc.i4   0x2DCAA8
0x1261a  ldloc.s  4
0x1261c  ldc.i4   0x191
0x12621  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x12626  throw
0x12627  ldloc.1
0x12628  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1262d  ldc.i4.1
0x1262e  newarr   [mscorlib]System.Char
0x12633  stloc.s  0xD
0x12635  ldloc.s  0xD
0x12637  ldc.i4.0
0x12638  ldc.i4.s 0x20
0x1263a  stelem.i2
0x1263b  ldloc.s  0xD
0x1263d  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x12642  stloc.s  5
0x12644  ldloc.s  5
0x12646  stloc.s  0xE
0x12648  ldc.i4.0
0x12649  stloc.s  0xF
0x1264b  br.s     loc_126BF
0x1264d  ldloc.s  0xE
0x1264f  ldloc.s  0xF
0x12651  ldelem.ref
0x12652  stloc.s  6
0x12654  ldloc.3
0x12655  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1265a  ldloc.s  6
0x1265c  callvirt instance string [mscorlib]System.String::Trim()
0x12661  call     bool Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::IsAllowedScope(string appId, string scope)
0x12666  brtrue.s loc_126B9
0x12668  ldstr    aScope0ForAppid// "Scope {0} for AppId {1} is not allowed."
0x1266d  ldloc.s  6
0x1266f  callvirt instance string [mscorlib]System.String::Trim()
0x12674  ldloc.3
0x12675  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1267a  call     string [mscorlib]System.String::Format(string, object, object)
0x1267f  stloc.s  4
0x12681  ldc.i4   0x106261A
0x12686  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1268b  ldc.i4.s 0xA
0x1268d  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x12692  ldc.i4.1
0x12693  newarr   [mscorlib]System.Object
0x12698  stloc.s  0x10
0x1269a  ldloc.s  0x10
0x1269c  ldc.i4.0
0x1269d  ldloc.s  4
0x1269f  stelem.ref
0x126a0  ldloc.s  0x10
0x126a2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x126a7  ldc.i4   0x2DCAAB
0x126ac  ldloc.s  4
0x126ae  ldc.i4   0x191
0x126b3  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x126b8  throw
0x126b9  ldloc.s  0xF
0x126bb  ldc.i4.1
0x126bc  add
0x126bd  stloc.s  0xF
0x126bf  ldloc.s  0xF
0x126c1  ldloc.s  0xE
0x126c3  ldlen
0x126c4  conv.i4
0x126c5  blt.s    loc_1264D
0x126c7  ret
0x126c8  ldloc.0
0x126c9  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x126ce  brfalse  loc_12845
0x126d3  ldc.i4   0x106261B
0x126d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x126dd  ldc.i4.s 0x32
0x126df  ldstr    aSpincomingiden_2// "SPIncomingIdentityHandler: Validate rol"...
0x126e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x126e9  ldloc.2
0x126ea  brfalse.s loc_126F9
0x126ec  ldloc.2
0x126ed  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x126f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x126f7  brfalse.s loc_12738
0x126f9  ldstr    aRoleClaimDoesN// "Role Claim does not exist for Service A"...
0x126fe  stloc.s  4
0x12700  ldc.i4   0x106261C
0x12705  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1270a  ldc.i4.s 0xA
0x1270c  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x12711  ldc.i4.1
0x12712  newarr   [mscorlib]System.Object
0x12717  stloc.s  0x11
0x12719  ldloc.s  0x11
0x1271b  ldc.i4.0
0x1271c  ldloc.s  4
0x1271e  stelem.ref
0x1271f  ldloc.s  0x11
0x12721  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12726  ldc.i4   0x2DCAAC
0x1272b  ldloc.s  4
0x1272d  ldc.i4   0x191
0x12732  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x12737  throw
0x12738  ldloc.1
0x12739  brfalse.s loc_1277A
0x1273b  ldstr    aScopeClaimIsNo// "Scope Claim is not allowed for Service "...
0x12740  stloc.s  4
0x12742  ldc.i4   0x106261D
0x12747  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1274c  ldc.i4.s 0xA
0x1274e  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x12753  ldc.i4.1
0x12754  newarr   [mscorlib]System.Object
0x12759  stloc.s  0x12
0x1275b  ldloc.s  0x12
0x1275d  ldc.i4.0
0x1275e  ldloc.s  4
0x12760  stelem.ref
0x12761  ldloc.s  0x12
0x12763  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12768  ldc.i4   0x2DCAAB
0x1276d  ldloc.s  4
0x1276f  ldc.i4   0x191
0x12774  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x12779  throw
0x1277a  ldloc.3
0x1277b  brtrue.s loc_127BC
0x1277d  ldstr    aAppIdClaimType_0// "App Id claim type is null for Service A"...
0x12782  stloc.s  4
0x12784  ldc.i4   0x106261E
0x12789  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1278e  ldc.i4.s 0xA
0x12790  ldstr    aSpincomingiden_1// "SPIncomingIdentityHandler: {0}"
0x12795  ldc.i4.1
0x12796  newarr   [mscorlib]System.Object
0x1279b  stloc.s  0x13
0x1279d  ldloc.s  0x13
0x1279f  ldc.i4.0
0x127a0  ldloc.s  4
0x127a2  stelem.ref
0x127a3  ldloc.s  0x13
0x127a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x127aa  ldc.i4   0x2DCAA8
0x127af  ldloc.s  4
0x127b1  ldc.i4   0x191
0x127b6  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x127bb  throw
0x127bc  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x127c1  stloc.s  7
0x127c3  ldloc.s  7
0x127c5  ldloc.2
0x127c6  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x127cb  callvirt T0x2B000014
0x127d0  stloc.s  8
0x127d2  ldloc.s  8
0x127d4  stloc.s  0x14
0x127d6  ldc.i4.0
0x127d7  stloc.s  0x15
0x127d9  br.s     loc_1283D
0x127db  ldloc.s  0x14
0x127dd  ldloc.s  0x15
0x127df  ldelem.ref
0x127e0  stloc.s  9
0x127e2  ldloc.3
0x127e3  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x127e8  ldloc.s  9
0x127ea  callvirt instance string [mscorlib]System.String::Trim()
0x127ef  call     bool Microsoft.SharePoint.IdentityModel.SPEvoStsAppsPermManager::IsAllowedRole(string appId, string role)
0x127f4  brtrue.s loc_12837
0x127f6  ldstr    aRole0ForAppid1// "Role {0} for AppId {1} is not allowed."
0x127fb  ldloc.s  9
0x127fd  callvirt instance string [mscorlib]System.String::Trim()
0x12802  ldloc.3
0x12803  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12808  call     string [mscorlib]System.String::Format(string, object, object)
0x1280d  stloc.s  4
0x1280f  ldc.i4   0x106261F
0x12814  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12819  ldc.i4.s 0xA
0x1281b  ldstr    aSpincomingiden_3// "SPIncomingIdentityHandler: "
0x12820  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12825  ldc.i4   0x2DCAAC
0x1282a  ldloc.s  4
0x1282c  ldc.i4   0x191
0x12831  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x12836  throw
0x12837  ldloc.s  0x15
0x12839  ldc.i4.1
0x1283a  add
0x1283b  stloc.s  0x15
  ... truncated ...
```
