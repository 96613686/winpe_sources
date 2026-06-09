# Microsoft.SharePoint.Upgrade.SPFarmAction::RemoveSolution

- ea: `0xa69b80`
- end: `0xa69f5b`
- name: `Microsoft.SharePoint.Upgrade.SPFarmAction::RemoveSolution`
- size: `987`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1c89e0`
- `0x1c8a20`
- `0x1c8e40`
- `0x29d270`
- `0x29d520`
- `0x2ab7a0`
- `0x2af4e0`
- `0x305be0`
- `0x305d30`
- `0x307320`
- `0x30cd80`
- `0xa4f1f0`
- `0xa4f220`
- `0xa4f240`
- `0xa69b80`

## string_xrefs

- `0xa69b94`: `SPFarmAction::RemoveSolution -- Begin. SolutionId = {0}`
- `0xa69be4`: `SPFarmAction::RemoveSolution -- Found solution with id '{0}', Name '{1}'. Removing.`
- `0xa69c2d`: `SPFarmAction::RemoveSolution -- Cleaning up solution association for feature {0}.`
- `0xa69c94`: `SPFarmAction::RemoveSolution -- Found feature {0}. Removing solutionid.`
- `0xa69cc4`: `SPFarmAction::RemoveSolution -- Found feature {0}. Removed solutionid.`
- `0xa69cea`: `SPFarmAction::RemoveSolution -- The feature {0} is associated wit a different solution '{1}'. Ignoring.`
- `0xa69d1f`: `SPFarmAction::RemoveSolution -- Feature with id {0} not found in the farm. Skipping`
- `0xa69d43`: `SPFarmAction::RemoveSolution -- Cleaned up solution association for feature {0}.`
- `0xa69d81`: `SPFarmAction::RemoveSolution -- No features requiring solution dis-association provided.`
- `0xa69dad`: `SPFarmAction::RemoveSolution -- Solution has {0} language packs. Removing one by one.`
- `0xa69e2c`: `SPFarmAction::RemoveSolution -- Removing language pack with locale id {0}.`
- `0xa69e6d`: `SPFarmAction::RemoveSolution -- Removed language pack with locale id {0}.`
- `0xa69ea4`: `SPFarmAction::RemoveSolution -- Removed solution '{0}'.`
- `0xa69eca`: `SPFarmAction::RemoveSolution -- Solution does not hav any Language Packs. Calling .Delete().`
- `0xa69ee0`: `SPFarmAction::RemoveSolution -- Removed solution with id {0}.`
- `0xa69f06`: `SPFarmAction::RemoveSolution -- Solution with id {0} was not found in the farm. Nothing to remove.`
- `0xa69f2c`: `SPFarmAction::RemoveSolution -- Farm is null. Skipping solution delete`
- `0xa69f3c`: `SPFarmAction::RemoveSolution -- End. SolutionId = {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa69b80  ldarg.3
0xa69b81  brtrue.s loc_A69B8E
0xa69b83  ldstr    aLog_0// "log"
0xa69b88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa69b8d  throw
0xa69b8e  ldarg.3
0xa69b8f  ldc.i4   0x443487
0xa69b94  ldstr    aSpfarmactionRe// "SPFarmAction::RemoveSolution -- Begin. "...
0xa69b99  ldc.i4.1
0xa69b9a  newarr   [mscorlib]System.Object
0xa69b9f  stloc.s  7
0xa69ba1  ldloc.s  7
0xa69ba3  ldc.i4.0
0xa69ba4  ldarg.0
0xa69ba5  box      [mscorlib]System.Guid
0xa69baa  stelem.ref
0xa69bab  ldloc.s  7
0xa69bad  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69bb2  ldarg.2
0xa69bb3  ldnull
0xa69bb4  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0xa69bb9  brfalse  loc_A69F26
0xa69bbe  ldarg.2
0xa69bbf  callvirt instance class Microsoft.SharePoint.Administration.SPSolutionCollection Microsoft.SharePoint.Administration.SPFarm::get_Solutions()
0xa69bc4  stloc.0
0xa69bc5  ldnull
0xa69bc6  stloc.1
0xa69bc7  ldloc.0
0xa69bc8  brfalse.s loc_A69BD2
0xa69bca  ldloc.0
0xa69bcb  ldarg.0
0xa69bcc  callvirt T0x2B000827
0xa69bd1  stloc.1
0xa69bd2  ldloc.1
0xa69bd3  ldnull
0xa69bd4  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0xa69bd9  brfalse  loc_A69F00
0xa69bde  ldarg.3
0xa69bdf  ldc.i4   0x443488
0xa69be4  ldstr    aSpfarmactionRe_0// "SPFarmAction::RemoveSolution -- Found s"...
0xa69be9  ldc.i4.2
0xa69bea  newarr   [mscorlib]System.Object
0xa69bef  stloc.s  8
0xa69bf1  ldloc.s  8
0xa69bf3  ldc.i4.0
0xa69bf4  ldarg.0
0xa69bf5  box      [mscorlib]System.Guid
0xa69bfa  stelem.ref
0xa69bfb  ldloc.s  8
0xa69bfd  ldc.i4.1
0xa69bfe  ldloc.1
0xa69bff  callvirt instance string Microsoft.SharePoint.Administration.SPSolution::get_Name()
0xa69c04  stelem.ref
0xa69c05  ldloc.s  8
0xa69c07  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69c0c  ldarg.1
0xa69c0d  brfalse  loc_A69D7B
0xa69c12  ldarg.1
0xa69c13  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xa69c18  stloc.s  9
0xa69c1a  br       loc_A69D61
0xa69c1f  ldloc.s  9
0xa69c21  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0xa69c26  stloc.2
0xa69c27  ldarg.3
0xa69c28  ldc.i4   0x443489
0xa69c2d  ldstr    aSpfarmactionRe_1// "SPFarmAction::RemoveSolution -- Cleanin"...
0xa69c32  ldc.i4.1
0xa69c33  newarr   [mscorlib]System.Object
0xa69c38  stloc.s  0xA
0xa69c3a  ldloc.s  0xA
0xa69c3c  ldc.i4.0
0xa69c3d  ldloc.2
0xa69c3e  box      [mscorlib]System.Guid
0xa69c43  stelem.ref
0xa69c44  ldloc.s  0xA
0xa69c46  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69c4b  ldnull
0xa69c4c  stloc.3
0xa69c4d  ldarg.2
0xa69c4e  callvirt instance class Microsoft.SharePoint.Administration.SPFeatureDefinitionCollection Microsoft.SharePoint.Administration.SPFarm::get_FeatureDefinitions()
0xa69c53  brfalse.s loc_A69C62
0xa69c55  ldarg.2
0xa69c56  callvirt instance class Microsoft.SharePoint.Administration.SPFeatureDefinitionCollection Microsoft.SharePoint.Administration.SPFarm::get_FeatureDefinitions()
0xa69c5b  ldloc.2
0xa69c5c  callvirt T0x2B0001B7
0xa69c61  stloc.3
0xa69c62  ldloc.3
0xa69c63  ldnull
0xa69c64  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0xa69c69  brfalse  loc_A69D19
0xa69c6e  ldloc.3
0xa69c6f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_SolutionId()
0xa69c74  ldarg.0
0xa69c75  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa69c7a  brtrue.s loc_A69C8E
0xa69c7c  ldloc.3
0xa69c7d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_SolutionId()
0xa69c82  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa69c87  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa69c8c  brfalse.s loc_A69CE4
0xa69c8e  ldarg.3
0xa69c8f  ldc.i4   0x44348A
0xa69c94  ldstr    aSpfarmactionRe_2// "SPFarmAction::RemoveSolution -- Found f"...
0xa69c99  ldc.i4.1
0xa69c9a  newarr   [mscorlib]System.Object
0xa69c9f  stloc.s  0xB
0xa69ca1  ldloc.s  0xB
0xa69ca3  ldc.i4.0
0xa69ca4  ldloc.2
0xa69ca5  box      [mscorlib]System.Guid
0xa69caa  stelem.ref
0xa69cab  ldloc.s  0xB
0xa69cad  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69cb2  ldloc.3
0xa69cb3  callvirt instance void Microsoft.SharePoint.Administration.SPFeatureDefinition::RemoveSolutionId()
0xa69cb8  ldloc.3
0xa69cb9  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0xa69cbe  ldarg.3
0xa69cbf  ldc.i4   0x44348B
0xa69cc4  ldstr    aSpfarmactionRe_3// "SPFarmAction::RemoveSolution -- Found f"...
0xa69cc9  ldc.i4.1
0xa69cca  newarr   [mscorlib]System.Object
0xa69ccf  stloc.s  0xC
0xa69cd1  ldloc.s  0xC
0xa69cd3  ldc.i4.0
0xa69cd4  ldloc.2
0xa69cd5  box      [mscorlib]System.Guid
0xa69cda  stelem.ref
0xa69cdb  ldloc.s  0xC
0xa69cdd  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69ce2  br.s     loc_A69D3D
0xa69ce4  ldarg.3
0xa69ce5  ldc.i4   0x44348C
0xa69cea  ldstr    aSpfarmactionRe_4// "SPFarmAction::RemoveSolution -- The fea"...
0xa69cef  ldc.i4.2
0xa69cf0  newarr   [mscorlib]System.Object
0xa69cf5  stloc.s  0xD
0xa69cf7  ldloc.s  0xD
0xa69cf9  ldc.i4.0
0xa69cfa  ldloc.2
0xa69cfb  box      [mscorlib]System.Guid
0xa69d00  stelem.ref
0xa69d01  ldloc.s  0xD
0xa69d03  ldc.i4.1
0xa69d04  ldloc.3
0xa69d05  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_SolutionId()
0xa69d0a  box      [mscorlib]System.Guid
0xa69d0f  stelem.ref
0xa69d10  ldloc.s  0xD
0xa69d12  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::WarningTag(unsigned int32 tagID, string format, object[] args)
0xa69d17  br.s     loc_A69D3D
0xa69d19  ldarg.3
0xa69d1a  ldc.i4   0x44348D
0xa69d1f  ldstr    aSpfarmactionRe_5// "SPFarmAction::RemoveSolution -- Feature"...
0xa69d24  ldc.i4.1
0xa69d25  newarr   [mscorlib]System.Object
0xa69d2a  stloc.s  0xE
0xa69d2c  ldloc.s  0xE
0xa69d2e  ldc.i4.0
0xa69d2f  ldloc.2
0xa69d30  box      [mscorlib]System.Guid
0xa69d35  stelem.ref
0xa69d36  ldloc.s  0xE
0xa69d38  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69d3d  ldarg.3
0xa69d3e  ldc.i4   0x44348E
0xa69d43  ldstr    aSpfarmactionRe_6// "SPFarmAction::RemoveSolution -- Cleaned"...
0xa69d48  ldc.i4.1
0xa69d49  newarr   [mscorlib]System.Object
0xa69d4e  stloc.s  0xF
0xa69d50  ldloc.s  0xF
0xa69d52  ldc.i4.0
0xa69d53  ldloc.2
0xa69d54  box      [mscorlib]System.Guid
0xa69d59  stelem.ref
0xa69d5a  ldloc.s  0xF
0xa69d5c  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69d61  ldloc.s  9
0xa69d63  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa69d68  brtrue   loc_A69C1F
0xa69d6d  leave.s  loc_A69D8B
0xa69d6f  ldloc.s  9
0xa69d71  brfalse.s loc_A69D7A
0xa69d73  ldloc.s  9
0xa69d75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa69d7a  endfinally
0xa69d7b  ldarg.3
0xa69d7c  ldc.i4   0x44348F
0xa69d81  ldstr    aSpfarmactionRe_7// "SPFarmAction::RemoveSolution -- No feat"...
0xa69d86  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa69d8b  ldloc.1
0xa69d8c  callvirt instance class Microsoft.SharePoint.Administration.SPSolutionLanguagePackCollection Microsoft.SharePoint.Administration.SPSolution::get_LanguagePacks()
0xa69d91  brfalse  loc_A69EC4
0xa69d96  ldloc.1
0xa69d97  callvirt instance class Microsoft.SharePoint.Administration.SPSolutionLanguagePackCollection Microsoft.SharePoint.Administration.SPSolution::get_LanguagePacks()
0xa69d9c  callvirt instance int32 class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPSolutionLanguagePack>::get_Count()
0xa69da1  ldc.i4.0
0xa69da2  ble      loc_A69EC4
0xa69da7  ldarg.3
0xa69da8  ldc.i4   0x443490
0xa69dad  ldstr    aSpfarmactionRe_8// "SPFarmAction::RemoveSolution -- Solutio"...
0xa69db2  ldc.i4.1
0xa69db3  newarr   [mscorlib]System.Object
0xa69db8  stloc.s  0x10
0xa69dba  ldloc.s  0x10
0xa69dbc  ldc.i4.0
0xa69dbd  ldloc.1
0xa69dbe  callvirt instance class Microsoft.SharePoint.Administration.SPSolutionLanguagePackCollection Microsoft.SharePoint.Administration.SPSolution::get_LanguagePacks()
0xa69dc3  callvirt instance int32 class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPSolutionLanguagePack>::get_Count()
0xa69dc8  box      [mscorlib]System.Int32
0xa69dcd  stelem.ref
0xa69dce  ldloc.s  0x10
0xa69dd0  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69dd5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::.ctor()
0xa69dda  stloc.s  4
0xa69ddc  ldloc.1
0xa69ddd  callvirt instance class Microsoft.SharePoint.Administration.SPSolutionLanguagePackCollection Microsoft.SharePoint.Administration.SPSolution::get_LanguagePacks()
0xa69de2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPSolutionLanguagePack>::GetEnumerator()
0xa69de7  stloc.s  0x11
0xa69de9  br.s     loc_A69E02
0xa69deb  ldloc.s  0x11
0xa69ded  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPSolutionLanguagePack>::get_Current()
0xa69df2  stloc.s  5
0xa69df4  ldloc.s  4
0xa69df6  ldloc.s  5
0xa69df8  callvirt instance unsigned int32 Microsoft.SharePoint.Administration.SPSolutionLanguagePack::get_LocaleId()
0xa69dfd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::Add(var<u1>)
0xa69e02  ldloc.s  0x11
0xa69e04  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa69e09  brtrue.s loc_A69DEB
0xa69e0b  leave.s  loc_A69E19
0xa69e0d  ldloc.s  0x11
0xa69e0f  brfalse.s loc_A69E18
0xa69e11  ldloc.s  0x11
0xa69e13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa69e18  endfinally
0xa69e19  ldloc.s  4
0xa69e1b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::get_Count()
0xa69e20  ldc.i4.1
0xa69e21  sub
0xa69e22  stloc.s  6
0xa69e24  br.s     loc_A69E99
0xa69e26  ldarg.3
0xa69e27  ldc.i4   0x443491
0xa69e2c  ldstr    aSpfarmactionRe_9// "SPFarmAction::RemoveSolution -- Removin"...
0xa69e31  ldc.i4.1
0xa69e32  newarr   [mscorlib]System.Object
0xa69e37  stloc.s  0x12
0xa69e39  ldloc.s  0x12
0xa69e3b  ldc.i4.0
0xa69e3c  ldloc.s  4
0xa69e3e  ldloc.s  6
0xa69e40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::get_Item(!!T0)
0xa69e45  box      [mscorlib]System.UInt32
0xa69e4a  stelem.ref
0xa69e4b  ldloc.s  0x12
0xa69e4d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69e52  ldloc.0
0xa69e53  ldloc.1
0xa69e54  callvirt instance string Microsoft.SharePoint.Administration.SPSolution::get_Name()
0xa69e59  ldloc.s  4
0xa69e5b  ldloc.s  6
0xa69e5d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::get_Item(!!T0)
0xa69e62  callvirt instance void Microsoft.SharePoint.Administration.SPSolutionCollection::Remove(string name, unsigned int32 lcid)
0xa69e67  ldarg.3
0xa69e68  ldc.i4   0x443492
0xa69e6d  ldstr    aSpfarmactionRe_10// "SPFarmAction::RemoveSolution -- Removed"...
0xa69e72  ldc.i4.1
0xa69e73  newarr   [mscorlib]System.Object
0xa69e78  stloc.s  0x13
0xa69e7a  ldloc.s  0x13
0xa69e7c  ldc.i4.0
0xa69e7d  ldloc.s  4
0xa69e7f  ldloc.s  6
0xa69e81  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::get_Item(!!T0)
0xa69e86  box      [mscorlib]System.UInt32
0xa69e8b  stelem.ref
0xa69e8c  ldloc.s  0x13
0xa69e8e  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa69e93  ldloc.s  6
0xa69e95  ldc.i4.1
0xa69e96  sub
0xa69e97  stloc.s  6
0xa69e99  ldloc.s  6
0xa69e9b  ldc.i4.0
0xa69e9c  bge.s    loc_A69E26
0xa69e9e  ldarg.3
0xa69e9f  ldc.i4   0x443493
0xa69ea4  ldstr    aSpfarmactionRe_11// "SPFarmAction::RemoveSolution -- Removed"...
0xa69ea9  ldc.i4.1
0xa69eaa  newarr   [mscorlib]System.Object
0xa69eaf  stloc.s  0x14
0xa69eb1  ldloc.s  0x14
0xa69eb3  ldc.i4.0
0xa69eb4  ldarg.0
0xa69eb5  box      [mscorlib]System.Guid
0xa69eba  stelem.ref
0xa69ebb  ldloc.s  0x14
0xa69ebd  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
  ... truncated ...
```
