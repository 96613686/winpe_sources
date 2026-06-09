# Microsoft.SharePoint.Administration.SPSiteMasterManager::RemoveListPermissions_0

- ea: `0x2ffc60`
- end: `0x300037`
- name: `Microsoft.SharePoint.Administration.SPSiteMasterManager::RemoveListPermissions_0`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2ffb50`

## callees

- `0x1b5530`
- `0x1b57a0`
- `0x2ffc60`
- `0x3003a0`
- `0x3428c0`
- `0x3428d0`
- `0x342900`
- `0x342e60`
- `0x343e80`
- `0x52a140`
- `0x5829f0`
- `0x582a10`
- `0x582b10`
- `0x582bd0`
- `0x583420`
- `0x5836d0`
- `0x583d20`
- `0x583d80`
- `0x583f60`
- `0x584e60`
- `0x5d3250`
- `0x93dab0`
- `0x93dae0`
- `0x957e90`

## string_xrefs

- `0x2ffc6c`: `[SPSiteMasterManager] RemoveListPermissions STARTED!`
- `0x2ffc9a`: `[SPSiteMasterManager.RemoveListPermissions]: SUCCESSFULLY broken inheritance for list: [{0}]`
- `0x2ffcc7`: `[SPSiteMasterManager.RemoveListPermissions]: FAILED to break inheritance for list: {0}!  Exception [{1}].`
- `0x2ffd3d`: `[SPSiteMasterManager.RemoveListPermissions]: SUCCESSFUL to add temporary role assignments to list [{0}]!`
- `0x2ffd6b`: `[SPSiteMasterManager.RemoveListPermissions]: FAILED to add temporary role assignments to list [{0}]!  Swallowing this exception. Exception [{1}].`
- `0x2ffda2`: `[SPSiteMasterManager.RemoveListPermissions]: SUCCESS to call list.BreakRoleInheritance(true) for list [{0}]`
- `0x2ffdde`: `[SPSiteMasterManager.RemoveListPermissions]: FAILED to call list.BreakRoleInheritance(true) for list [{0}]!  Exception [{1}]`
- `0x2ffe92`: `[SPSiteMasterManager.RemoveListPermissions]: SKIPPING to remove [{0}]!`
- `0x2ffeff`: `[SPSiteMasterManager.RemoveListPermissions]: Removed [{0}]!`
- `0x2fff72`: `[SPSiteMasterManager.RemoveListPermissions]: Removed ALL role Assignments! AllowGuestAccess is [{0}]`
- `0x2fffb2`: `[SPSiteMasterManager.RemoveListPermissions]: Failed to remove role Assignments with allowGuestAccess=[{0}]! Exception [{1}].`
- `0x2fffea`: `[SPSiteMasterManager.RemoveListPermissions]: List already has unique role Assignments! Skipping this list: [{0}]`
- `0x300016`: `[SPSiteMasterManager.RemoveListPermissions]:  LIST Param is NULL!`
- `0x30002c`: `[SPSiteMasterManager] RemoveListPermissions COMPLETED!`

## pseudocode

```c

```

## disassembly

```asm
0x2ffc60  ldc.i4   0x13E30C7
0x2ffc65  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffc6a  ldc.i4.s 0x32
0x2ffc6c  ldstr    aSpsitemasterma_16// "[SPSiteMasterManager] RemoveListPermiss"...
0x2ffc71  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2ffc76  ldarg.0
0x2ffc77  brfalse  loc_30000A
0x2ffc7c  ldarg.0
0x2ffc7d  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::get_HasUniqueRoleAssignments()
0x2ffc82  brtrue   loc_2FFFDE
0x2ffc87  ldarg.0
0x2ffc88  ldc.i4.1
0x2ffc89  callvirt instance void Microsoft.SharePoint.SPSecurableObject::BreakRoleInheritance(bool copyRoleAssignments)
0x2ffc8e  ldc.i4   0x13E30C8
0x2ffc93  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffc98  ldc.i4.s 0x32
0x2ffc9a  ldstr    aSpsitemasterma_17// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffc9f  ldc.i4.1
0x2ffca0  newarr   [mscorlib]System.Object
0x2ffca5  stloc.s  0xF
0x2ffca7  ldloc.s  0xF
0x2ffca9  ldc.i4.0
0x2ffcaa  ldarg.0
0x2ffcab  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffcb0  stelem.ref
0x2ffcb1  ldloc.s  0xF
0x2ffcb3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2ffcb8  leave.s  loc_2FFCF1
0x2ffcba  stloc.0
0x2ffcbb  ldc.i4   0x13E30C9
0x2ffcc0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffcc5  ldc.i4.s 0x14
0x2ffcc7  ldstr    aSpsitemasterma_18// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffccc  ldc.i4.2
0x2ffccd  newarr   [mscorlib]System.Object
0x2ffcd2  stloc.s  0x10
0x2ffcd4  ldloc.s  0x10
0x2ffcd6  ldc.i4.0
0x2ffcd7  ldarg.0
0x2ffcd8  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffcdd  stelem.ref
0x2ffcde  ldloc.s  0x10
0x2ffce0  ldc.i4.1
0x2ffce1  ldloc.0
0x2ffce2  callvirt instance string [mscorlib]System.Object::ToString()
0x2ffce7  stelem.ref
0x2ffce8  ldloc.s  0x10
0x2ffcea  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2ffcef  rethrow
0x2ffcf1  ldarg.0
0x2ffcf2  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x2ffcf7  callvirt instance class Microsoft.SharePoint.SPRoleDefinitionCollection Microsoft.SharePoint.SPWeb::get_RoleDefinitions()
0x2ffcfc  ldc.i4.5
0x2ffcfd  callvirt instance class Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.SPRoleDefinitionCollection::GetByType(valuetype Microsoft.SharePoint.SPRoleType roleType)
0x2ffd02  stloc.1
0x2ffd03  ldarg.0
0x2ffd04  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x2ffd09  call     string Microsoft.SharePoint.Administration.SPSiteMasterManager::GetAllUsersLoginName(class Microsoft.SharePoint.SPWeb web)
0x2ffd0e  stloc.2
0x2ffd0f  ldloc.2
0x2ffd10  ldnull
0x2ffd11  ldnull
0x2ffd12  ldnull
0x2ffd13  newobj   instance void Microsoft.SharePoint.SPRoleAssignment::.ctor(string LoginName, string Email, string Name, string Notes)
0x2ffd18  stloc.3
0x2ffd19  ldloc.3
0x2ffd1a  callvirt instance class Microsoft.SharePoint.SPRoleDefinitionBindingCollection Microsoft.SharePoint.SPRoleAssignment::get_RoleDefinitionBindings()
0x2ffd1f  ldloc.1
0x2ffd20  callvirt instance void Microsoft.SharePoint.SPRoleDefinitionBindingCollection::Add(class Microsoft.SharePoint.SPRoleDefinition roleDefinition)
0x2ffd25  ldarg.0
0x2ffd26  callvirt instance class Microsoft.SharePoint.SPRoleAssignmentCollection Microsoft.SharePoint.SPSecurableObject::get_RoleAssignments()
0x2ffd2b  ldloc.3
0x2ffd2c  callvirt instance void Microsoft.SharePoint.SPRoleAssignmentCollection::Add(class Microsoft.SharePoint.SPRoleAssignment roleAssignment)
0x2ffd31  ldc.i4   0x13E30CA
0x2ffd36  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffd3b  ldc.i4.s 0x32
0x2ffd3d  ldstr    aSpsitemasterma_19// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffd42  ldc.i4.1
0x2ffd43  newarr   [mscorlib]System.Object
0x2ffd48  stloc.s  0x11
0x2ffd4a  ldloc.s  0x11
0x2ffd4c  ldc.i4.0
0x2ffd4d  ldarg.0
0x2ffd4e  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffd53  stelem.ref
0x2ffd54  ldloc.s  0x11
0x2ffd56  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2ffd5b  leave.s  loc_2FFD96
0x2ffd5d  stloc.s  4
0x2ffd5f  ldc.i4   0x13E30CB
0x2ffd64  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffd69  ldc.i4.s 0x14
0x2ffd6b  ldstr    aSpsitemasterma_20// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffd70  ldc.i4.2
0x2ffd71  newarr   [mscorlib]System.Object
0x2ffd76  stloc.s  0x12
0x2ffd78  ldloc.s  0x12
0x2ffd7a  ldc.i4.0
0x2ffd7b  ldarg.0
0x2ffd7c  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffd81  stelem.ref
0x2ffd82  ldloc.s  0x12
0x2ffd84  ldc.i4.1
0x2ffd85  ldloc.s  4
0x2ffd87  callvirt instance string [mscorlib]System.Object::ToString()
0x2ffd8c  stelem.ref
0x2ffd8d  ldloc.s  0x12
0x2ffd8f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2ffd94  leave.s  loc_2FFD96
0x2ffd96  ldarg.0
0x2ffd97  ldc.i4.1
0x2ffd98  callvirt instance void Microsoft.SharePoint.SPSecurableObject::BreakRoleInheritance(bool copyRoleAssignments)
0x2ffd9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ffda2  ldstr    aSpsitemasterma_21// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffda7  ldc.i4.1
0x2ffda8  newarr   [mscorlib]System.Object
0x2ffdad  stloc.s  0x13
0x2ffdaf  ldloc.s  0x13
0x2ffdb1  ldc.i4.0
0x2ffdb2  ldarg.0
0x2ffdb3  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffdb8  stelem.ref
0x2ffdb9  ldloc.s  0x13
0x2ffdbb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ffdc0  stloc.s  5
0x2ffdc2  ldc.i4   0x13E30CC
0x2ffdc7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffdcc  ldc.i4.s 0x32
0x2ffdce  ldloc.s  5
0x2ffdd0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2ffdd5  leave.s  loc_2FFE1E
0x2ffdd7  stloc.s  6
0x2ffdd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ffdde  ldstr    aSpsitemasterma_22// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffde3  ldc.i4.2
0x2ffde4  newarr   [mscorlib]System.Object
0x2ffde9  stloc.s  0x14
0x2ffdeb  ldloc.s  0x14
0x2ffded  ldc.i4.0
0x2ffdee  ldarg.0
0x2ffdef  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x2ffdf4  stelem.ref
0x2ffdf5  ldloc.s  0x14
0x2ffdf7  ldc.i4.1
0x2ffdf8  ldloc.s  6
0x2ffdfa  callvirt instance string [mscorlib]System.Object::ToString()
0x2ffdff  stelem.ref
0x2ffe00  ldloc.s  0x14
0x2ffe02  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ffe07  stloc.s  7
0x2ffe09  ldc.i4   0x13E30CD
0x2ffe0e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffe13  ldc.i4.s 0x14
0x2ffe15  ldloc.s  7
0x2ffe17  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2ffe1c  rethrow
0x2ffe1e  ldarg.0
0x2ffe1f  callvirt instance class Microsoft.SharePoint.SPRoleAssignmentCollection Microsoft.SharePoint.SPSecurableObject::get_RoleAssignments()
0x2ffe24  stloc.s  8
0x2ffe26  ldarg.1
0x2ffe27  brfalse  loc_2FFF98
0x2ffe2c  ldloc.s  8
0x2ffe2e  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x2ffe33  stloc.s  0x15
0x2ffe35  br       loc_2FFF43
0x2ffe3a  ldloc.s  0x15
0x2ffe3c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2ffe41  castclass Microsoft.SharePoint.SPRoleAssignment
0x2ffe46  stloc.s  9
0x2ffe48  ldloc.s  9
0x2ffe4a  callvirt instance class Microsoft.SharePoint.SPRoleDefinitionBindingCollection Microsoft.SharePoint.SPRoleAssignment::get_RoleDefinitionBindings()
0x2ffe4f  stloc.s  0xA
0x2ffe51  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPRoleDefinition>::.ctor()
0x2ffe56  stloc.s  0xB
0x2ffe58  ldloc.s  0xA
0x2ffe5a  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x2ffe5f  stloc.s  0x16
0x2ffe61  br.s     loc_2FFEB6
0x2ffe63  ldloc.s  0x16
0x2ffe65  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2ffe6a  castclass Microsoft.SharePoint.SPRoleDefinition
0x2ffe6f  stloc.s  0xC
0x2ffe71  ldloc.s  0xC
0x2ffe73  callvirt instance valuetype Microsoft.SharePoint.SPRoleType Microsoft.SharePoint.SPRoleDefinition::get_Type()
0x2ffe78  ldc.i4.1
0x2ffe79  beq.s    loc_2FFE86
0x2ffe7b  ldloc.s  0xB
0x2ffe7d  ldloc.s  0xC
0x2ffe7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPRoleDefinition>::Add(var<u1>)
0x2ffe84  br.s     loc_2FFEB6
0x2ffe86  ldc.i4   0x13E30CE
0x2ffe8b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffe90  ldc.i4.s 0x32
0x2ffe92  ldstr    aSpsitemasterma_23// "[SPSiteMasterManager.RemoveListPermissi"...
0x2ffe97  ldc.i4.1
0x2ffe98  newarr   [mscorlib]System.Object
0x2ffe9d  stloc.s  0x17
0x2ffe9f  ldloc.s  0x17
0x2ffea1  ldc.i4.0
0x2ffea2  ldloc.s  9
0x2ffea4  callvirt instance class Microsoft.SharePoint.SPPrincipal Microsoft.SharePoint.SPRoleAssignment::get_Member()
0x2ffea9  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x2ffeae  stelem.ref
0x2ffeaf  ldloc.s  0x17
0x2ffeb1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2ffeb6  ldloc.s  0x16
0x2ffeb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ffebd  brtrue.s loc_2FFE63
0x2ffebf  leave.s  loc_2FFED6
0x2ffec1  ldloc.s  0x16
0x2ffec3  isinst   [mscorlib]System.IDisposable
0x2ffec8  stloc.s  0x18
0x2ffeca  ldloc.s  0x18
0x2ffecc  brfalse.s loc_2FFED5
0x2ffece  ldloc.s  0x18
0x2ffed0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ffed5  endfinally
0x2ffed6  ldloc.s  0xB
0x2ffed8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPRoleDefinition>::GetEnumerator()
0x2ffedd  stloc.s  0x19
0x2ffedf  br.s     loc_2FFF23
0x2ffee1  ldloca.s 0x19
0x2ffee3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.SPRoleDefinition>::get_Current()
0x2ffee8  stloc.s  0xD
0x2ffeea  ldloc.s  0xA
0x2ffeec  ldloc.s  0xD
0x2ffeee  callvirt instance void Microsoft.SharePoint.SPRoleDefinitionBindingCollection::Remove(class Microsoft.SharePoint.SPRoleDefinition roleDefinition)
0x2ffef3  ldc.i4   0x13E30CF
0x2ffef8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2ffefd  ldc.i4.s 0x32
0x2ffeff  ldstr    aSpsitemasterma_24// "[SPSiteMasterManager.RemoveListPermissi"...
0x2fff04  ldc.i4.1
0x2fff05  newarr   [mscorlib]System.Object
0x2fff0a  stloc.s  0x1A
0x2fff0c  ldloc.s  0x1A
0x2fff0e  ldc.i4.0
0x2fff0f  ldloc.s  9
0x2fff11  callvirt instance class Microsoft.SharePoint.SPPrincipal Microsoft.SharePoint.SPRoleAssignment::get_Member()
0x2fff16  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x2fff1b  stelem.ref
0x2fff1c  ldloc.s  0x1A
0x2fff1e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fff23  ldloca.s 0x19
0x2fff25  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.SPRoleDefinition>::MoveNext()
0x2fff2a  brtrue.s loc_2FFEE1
0x2fff2c  leave.s  loc_2FFF3C
0x2fff2e  ldloca.s 0x19
0x2fff30  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.SPRoleDefinition>
0x2fff36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fff3b  endfinally
0x2fff3c  ldloc.s  9
0x2fff3e  callvirt instance void Microsoft.SharePoint.SPRoleAssignment::Update()
0x2fff43  ldloc.s  0x15
0x2fff45  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2fff4a  brtrue   loc_2FFE3A
0x2fff4f  leave.s  loc_2FFFA2
0x2fff51  ldloc.s  0x15
0x2fff53  isinst   [mscorlib]System.IDisposable
0x2fff58  stloc.s  0x1B
0x2fff5a  ldloc.s  0x1B
0x2fff5c  brfalse.s loc_2FFF65
0x2fff5e  ldloc.s  0x1B
0x2fff60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fff65  endfinally
0x2fff66  ldc.i4   0x13E30D0
0x2fff6b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fff70  ldc.i4.s 0x32
0x2fff72  ldstr    aSpsitemasterma_25// "[SPSiteMasterManager.RemoveListPermissi"...
0x2fff77  ldc.i4.1
0x2fff78  newarr   [mscorlib]System.Object
0x2fff7d  stloc.s  0x1C
0x2fff7f  ldloc.s  0x1C
0x2fff81  ldc.i4.0
0x2fff82  ldarg.1
0x2fff83  box      [mscorlib]System.Boolean
0x2fff88  stelem.ref
0x2fff89  ldloc.s  0x1C
0x2fff8b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fff90  ldloc.s  8
0x2fff92  ldc.i4.0
0x2fff93  callvirt instance void Microsoft.SharePoint.SPRoleAssignmentCollection::Remove(int32 index)
0x2fff98  ldloc.s  8
0x2fff9a  callvirt instance int32 Microsoft.SharePoint.SPBaseCollection::get_Count()
0x2fff9f  ldc.i4.0
0x2fffa0  bgt.s    loc_2FFF66
0x2fffa2  leave.s  loc_300020
0x2fffa4  stloc.s  0xE
0x2fffa6  ldc.i4   0x13E30D1
0x2fffab  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fffb0  ldc.i4.s 0x32
0x2fffb2  ldstr    aSpsitemasterma_26// "[SPSiteMasterManager.RemoveListPermissi"...
0x2fffb7  ldc.i4.2
0x2fffb8  newarr   [mscorlib]System.Object
0x2fffbd  stloc.s  0x1D
0x2fffbf  ldloc.s  0x1D
0x2fffc1  ldc.i4.0
0x2fffc2  ldarga.s 1
0x2fffc4  call     instance string [mscorlib]System.Boolean::ToString()
0x2fffc9  stelem.ref
0x2fffca  ldloc.s  0x1D
  ... truncated ...
```
