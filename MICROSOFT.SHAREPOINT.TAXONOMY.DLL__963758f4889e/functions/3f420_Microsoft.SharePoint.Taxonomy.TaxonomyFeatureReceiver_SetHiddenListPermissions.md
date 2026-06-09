# Microsoft.SharePoint.Taxonomy.TaxonomyFeatureReceiver::SetHiddenListPermissions

- ea: `0x3f420`
- end: `0x3f5a8`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyFeatureReceiver::SetHiddenListPermissions`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3f100`

## callees

- `0x2acd0`
- `0x3f420`

## string_xrefs

- `0x3f45d`: `ReaderRoleName`
- `0x3f49d`: `ReaderRoleName`
- `0x3f46d`: `ReaderRoleDescription`
- `0x3f4bc`: `Cannot add new reader role to hidden list`

## pseudocode

```c

```

## disassembly

```asm
0x3f420  ldarg.1
0x3f421  ldc.i4.0
0x3f422  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::BreakRoleInheritance(bool)
0x3f427  ldc.i4.s 0x11
0x3f429  ldnull
0x3f42a  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x3f42f  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x3f434  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f439  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x3f43e  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x3f443  stloc.0
0x3f444  ldnull
0x3f445  stloc.1
0x3f446  ldarg.0
0x3f447  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_RoleDefinitions()
0x3f44c  ldc.i4.2
0x3f44d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection::GetByType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleType)
0x3f452  stloc.1
0x3f453  leave.s  loc_3F4CC
0x3f455  pop
0x3f456  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition::.ctor()
0x3f45b  stloc.1
0x3f45c  ldloc.1
0x3f45d  ldstr    aReaderrolename// "ReaderRoleName"
0x3f462  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3f467  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition::set_Name(string)
0x3f46c  ldloc.1
0x3f46d  ldstr    aReaderroledesc// "ReaderRoleDescription"
0x3f472  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3f477  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition::set_Description(string)
0x3f47c  ldloc.1
0x3f47d  ldc.i8   0x400000300C031061
0x3f486  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition::set_BasePermissions(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions)
0x3f48b  ldarg.0
0x3f48c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_RoleDefinitions()
0x3f491  ldloc.1
0x3f492  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition)
0x3f497  ldarg.0
0x3f498  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_RoleDefinitions()
0x3f49d  ldstr    aReaderrolename// "ReaderRoleName"
0x3f4a2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3f4a7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionCollection::get_Item(string)
0x3f4ac  stloc.1
0x3f4ad  leave.s  loc_3F4CA
0x3f4af  pop
0x3f4b0  ldc.i4   0x64697137
0x3f4b5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3f4ba  ldc.i4.s 0xA
0x3f4bc  ldstr    aCannotAddNewRe// "Cannot add new reader role to hidden li"...
0x3f4c1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x3f4c6  ldnull
0x3f4c7  stloc.1
0x3f4c8  leave.s  loc_3F4CA
0x3f4ca  leave.s  loc_3F4CC
0x3f4cc  ldloc.1
0x3f4cd  brfalse  loc_3F592
0x3f4d2  ldarg.0
0x3f4d3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0x3f4d8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_WebApplication()
0x3f4dd  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_UseClaimsAuthentication()
0x3f4e2  brfalse.s loc_3F52A
0x3f4e4  ldc.i4.1
0x3f4e5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPAllUserClaimProvider::CreateAuthenticatedUserClaim(bool)
0x3f4ea  stloc.2
0x3f4eb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::get_Local()
0x3f4f0  ldloc.2
0x3f4f1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::EncodeClaim(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim)
0x3f4f6  stloc.3
0x3f4f7  ldloc.3
0x3f4f8  ldsfld   string [mscorlib]System.String::Empty
0x3f4fd  ldsfld   string [mscorlib]System.String::Empty
0x3f502  ldsfld   string [mscorlib]System.String::Empty
0x3f507  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment::.ctor(string, string, string, string)
0x3f50c  stloc.s  4
0x3f50e  ldloc.s  4
0x3f510  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionBindingCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment::get_RoleDefinitionBindings()
0x3f515  ldloc.1
0x3f516  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionBindingCollection::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition)
0x3f51b  ldarg.1
0x3f51c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignmentCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::get_RoleAssignments()
0x3f521  ldloc.s  4
0x3f523  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignmentCollection::AddToCurrentScopeOnly(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment)
0x3f528  br.s     loc_3F592
0x3f52a  ldloc.0
0x3f52b  ldsfld   string [mscorlib]System.String::Empty
0x3f530  ldloc.0
0x3f531  ldsfld   string [mscorlib]System.String::Empty
0x3f536  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment::.ctor(string, string, string, string)
0x3f53b  stloc.s  5
0x3f53d  ldloc.s  5
0x3f53f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionBindingCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment::get_RoleDefinitionBindings()
0x3f544  ldloc.1
0x3f545  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinitionBindingCollection::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition)
0x3f54a  ldarg.1
0x3f54b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignmentCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::get_RoleAssignments()
0x3f550  ldloc.s  5
0x3f552  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignmentCollection::AddToCurrentScopeOnly(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleAssignment)
0x3f557  leave.s  loc_3F592
0x3f559  stloc.s  6
0x3f55b  ldc.i4   0x66756330
0x3f560  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3f565  ldc.i4.s 0x14
0x3f567  ldstr    aFailedToAddRol// "Failed to add role assignments to the t"...
0x3f56c  ldc.i4.2
0x3f56d  newarr   [mscorlib]System.Object
0x3f572  stloc.s  7
0x3f574  ldloc.s  7
0x3f576  ldc.i4.0
0x3f577  ldarg.0
0x3f578  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x3f57d  stelem.ref
0x3f57e  ldloc.s  7
0x3f580  ldc.i4.1
0x3f581  ldloc.s  6
0x3f583  callvirt instance string [mscorlib]System.Object::ToString()
0x3f588  stelem.ref
0x3f589  ldloc.s  7
0x3f58b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3f590  leave.s  loc_3F592
0x3f592  ldarg.1
0x3f593  ldc.i4.1
0x3f594  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowEveryoneViewItems(bool)
0x3f599  ldarg.1
0x3f59a  ldc.i4.1
0x3f59b  conv.i8
0x3f59c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AnonymousPermMask64(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions)
0x3f5a1  ldarg.1
0x3f5a2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0x3f5a7  ret
```
