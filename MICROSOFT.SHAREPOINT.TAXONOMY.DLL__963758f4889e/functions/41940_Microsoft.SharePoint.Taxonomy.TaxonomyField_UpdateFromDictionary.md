# Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateFromDictionary

- ea: `0x41940`
- end: `0x41a77`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateFromDictionary`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40b70`

## callees

- `0x41940`

## string_xrefs

- `0x419aa`: `UserCreated`
- `0x419b8`: `UserCreated`
- `0x419f0`: `IsPathRendered`
- `0x419fe`: `IsPathRendered`
- `0x41a31`: `CreateValuesInEditForm`
- `0x41a3f`: `CreateValuesInEditForm`
- `0x41a13`: `TargetTemplate`
- `0x41a21`: `TargetTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x41940  ldarg.1
0x41941  ldstr    aSspid_0// "SspId"
0x41946  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x4194b  brfalse.s loc_41963
0x4194d  ldarg.0
0x4194e  ldarg.1
0x4194f  ldstr    aSspid_0// "SspId"
0x41954  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x41959  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4195e  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::sspId
0x41963  ldarg.1
0x41964  ldstr    aTermsetid// "TermSetId"
0x41969  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x4196e  brfalse.s loc_41986
0x41970  ldarg.0
0x41971  ldarg.1
0x41972  ldstr    aTermsetid// "TermSetId"
0x41977  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x4197c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x41981  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::termSetId
0x41986  ldarg.1
0x41987  ldstr    aAnchorid// "AnchorId"
0x4198c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x41991  brfalse.s loc_419A9
0x41993  ldarg.0
0x41994  ldarg.1
0x41995  ldstr    aAnchorid// "AnchorId"
0x4199a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x4199f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x419a4  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::anchorId
0x419a9  ldarg.1
0x419aa  ldstr    aUsercreated// "UserCreated"
0x419af  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x419b4  brfalse.s loc_419CC
0x419b6  ldarg.0
0x419b7  ldarg.1
0x419b8  ldstr    aUsercreated// "UserCreated"
0x419bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x419c2  call     bool [mscorlib]System.Boolean::Parse(string)
0x419c7  stfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyField::userCreated
0x419cc  ldarg.1
0x419cd  ldstr    aOpen// "Open"
0x419d2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x419d7  brfalse.s loc_419EF
0x419d9  ldarg.0
0x419da  ldarg.1
0x419db  ldstr    aOpen// "Open"
0x419e0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x419e5  call     bool [mscorlib]System.Boolean::Parse(string)
0x419ea  stfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyField::open
0x419ef  ldarg.1
0x419f0  ldstr    aIspathrendered// "IsPathRendered"
0x419f5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x419fa  brfalse.s loc_41A12
0x419fc  ldarg.0
0x419fd  ldarg.1
0x419fe  ldstr    aIspathrendered// "IsPathRendered"
0x41a03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x41a08  call     bool [mscorlib]System.Boolean::Parse(string)
0x41a0d  stfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyField::isPathRendered
0x41a12  ldarg.1
0x41a13  ldstr    aTargettemplate// "TargetTemplate"
0x41a18  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x41a1d  brfalse.s loc_41A30
0x41a1f  ldarg.0
0x41a20  ldarg.1
0x41a21  ldstr    aTargettemplate// "TargetTemplate"
0x41a26  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x41a2b  stfld    string Microsoft.SharePoint.Taxonomy.TaxonomyField::targetTemplate
0x41a30  ldarg.1
0x41a31  ldstr    aCreatevaluesin// "CreateValuesInEditForm"
0x41a36  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x41a3b  brfalse.s loc_41A53
0x41a3d  ldarg.0
0x41a3e  ldarg.1
0x41a3f  ldstr    aCreatevaluesin// "CreateValuesInEditForm"
0x41a44  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x41a49  call     bool [mscorlib]System.Boolean::Parse(string)
0x41a4e  stfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyField::createValuesInEditForm
0x41a53  ldarg.1
0x41a54  ldstr    aIskeyword// "IsKeyword"
0x41a59  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x41a5e  brfalse.s loc_41A76
0x41a60  ldarg.0
0x41a61  ldarg.1
0x41a62  ldstr    aIskeyword// "IsKeyword"
0x41a67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x41a6c  call     bool [mscorlib]System.Boolean::Parse(string)
0x41a71  stfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyField::isKeyword
0x41a76  ret
```
