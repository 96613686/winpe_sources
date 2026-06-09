# ObjectPicker::.ctor

- ea: `0xa0740`
- end: `0xa0946`
- name: `ObjectPicker::.ctor`
- size: `518`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0xa1150`
- `0xa1160`

## callees

- `0xa0740`
- `0xa09b0`
- `0xa0c10`

## string_xrefs

- `0xa07b5`: `objectsid`
- `0xa0872`: `objectsid`
- `0xa08b4`: `objectsid`
- `0xa0926`: `objectsid`

## pseudocode

```c

```

## disassembly

```asm
0xa0740  ldarg.0
0xa0741  call     instance void [mscorlib]System.Object::.ctor()
0xa0746  ldc.i4.4
0xa0747  newarr   ObjectPickerTypes
0xa074c  dup
0xa074d  ldtoken  valuetype __StaticArrayInitTypeSize=16 <PrivateImplementationDetails>::'42183E5ADFB18A57973908BE5A4B787B3F64F97CEB3ACAF48CF1158D21B71C9A'
0xa0752  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0xa0757  stloc.0
0xa0758  ldarg.1
0xa0759  brtrue.s loc_A0766
0xa075b  ldstr    aType_0// "type"
0xa0760  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa0765  throw
0xa0766  ldarg.0
0xa0767  ldarg.2
0xa0768  stfld    string ObjectPicker::targetComputer
0xa076d  ldarg.0
0xa076e  ldc.i4.0
0xa076f  newarr   [mscorlib]System.String
0xa0774  stfld    string[] ObjectPicker::attributeNames
0xa0779  ldarg.0
0xa077a  ldc.i4.0
0xa077b  stfld    valuetype DSOP_INIT_INFO_FLAGS ObjectPicker::initInfoFlags
0xa0780  ldarg.0
0xa0781  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype DSOP_SCOPE_INIT_INFO>::.ctor()
0xa0786  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype DSOP_SCOPE_INIT_INFO> ObjectPicker::scopeInfos
0xa078b  ldarg.1
0xa078c  ldloc.0
0xa078d  ldc.i4.1
0xa078e  ldelem.i4
0xa078f  and
0xa0790  brfalse.s loc_A07EF
0xa0792  ldarg.1
0xa0793  ldloc.0
0xa0794  ldc.i4.2
0xa0795  ldelem.i4
0xa0796  and
0xa0797  brfalse.s loc_A07EF
0xa0799  ldc.i4   0x1006
0xa079e  stloc.2
0xa079f  ldc.i4   0x80000007
0xa07a4  stloc.3
0xa07a5  ldc.i4.2
0xa07a6  newarr   [mscorlib]System.String
0xa07ab  dup
0xa07ac  ldc.i4.0
0xa07ad  ldstr    aSamaccountname// "sAMAccountName"
0xa07b2  stelem.ref
0xa07b3  dup
0xa07b4  ldc.i4.1
0xa07b5  ldstr    aObjectsid// "objectsid"
0xa07ba  stelem.ref
0xa07bb  stloc.s  4
0xa07bd  ldarg.0
0xa07be  ldloc.s  4
0xa07c0  call     instance void ObjectPicker::SetAttributesToRetrieve(string[] names)
0xa07c5  ldarg.1
0xa07c6  ldloc.0
0xa07c7  ldc.i4.3
0xa07c8  ldelem.i4
0xa07c9  and
0xa07ca  brfalse.s loc_A07D8
0xa07cc  ldloc.2
0xa07cd  ldc.i4.8
0xa07ce  or
0xa07cf  stloc.2
0xa07d0  ldloc.3
0xa07d1  ldc.i4   0x800C4000
0xa07d6  or
0xa07d7  stloc.3
0xa07d8  ldarg.0
0xa07d9  ldc.i4   0x98
0xa07de  ldc.i4   0x4C0
0xa07e3  ldloc.2
0xa07e4  ldloc.3
0xa07e5  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa07ea  br       loc_A0882
0xa07ef  ldarg.1
0xa07f0  ldloc.0
0xa07f1  ldc.i4.0
0xa07f2  ldelem.i4
0xa07f3  and
0xa07f4  brfalse.s loc_A0848
0xa07f6  ldarg.1
0xa07f7  ldloc.0
0xa07f8  ldc.i4.2
0xa07f9  ldelem.i4
0xa07fa  and
0xa07fb  brfalse.s loc_A082C
0xa07fd  ldarg.0
0xa07fe  ldc.i4   0x3FF
0xa0803  ldc.i4   0x180
0xa0808  ldc.i4   0xBF0
0xa080d  ldc.i4   0x8000000E
0xa0812  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa0817  ldarg.0
0xa0818  ldc.i4.s 0x10
0xa081a  ldc.i4.1
0xa081b  ldc.i4   0xBF0
0xa0820  ldc.i4   0x8000000E
0xa0825  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa082a  br.s     loc_A0882
0xa082c  ldarg.0
0xa082d  ldc.i4   0x3FF
0xa0832  ldc.i4   0x100
0xa0837  ldc.i4   0x800
0xa083c  ldc.i4   0x80000008
0xa0841  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa0846  br.s     loc_A0882
0xa0848  ldarg.1
0xa0849  ldloc.0
0xa084a  ldc.i4.1
0xa084b  ldelem.i4
0xa084c  and
0xa084d  brfalse.s loc_A0882
0xa084f  ldarg.0
0xa0850  ldc.i4   0x98
0xa0855  ldc.i4.s 0x40
0xa0857  ldc.i4.2
0xa0858  ldc.i4   0x80000001
0xa085d  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa0862  ldc.i4.2
0xa0863  newarr   [mscorlib]System.String
0xa0868  dup
0xa0869  ldc.i4.0
0xa086a  ldstr    aSamaccountname// "sAMAccountName"
0xa086f  stelem.ref
0xa0870  dup
0xa0871  ldc.i4.1
0xa0872  ldstr    aObjectsid// "objectsid"
0xa0877  stelem.ref
0xa0878  stloc.s  5
0xa087a  ldarg.0
0xa087b  ldloc.s  5
0xa087d  call     instance void ObjectPicker::SetAttributesToRetrieve(string[] names)
0xa0882  ldc.i4   0x37F
0xa0887  stloc.1
0xa0888  ldarg.1
0xa0889  ldloc.0
0xa088a  ldc.i4.1
0xa088b  ldelem.i4
0xa088c  and
0xa088d  brfalse.s loc_A08ED
0xa088f  ldarg.1
0xa0890  ldloc.0
0xa0891  ldc.i4.2
0xa0892  ldelem.i4
0xa0893  and
0xa0894  brfalse.s loc_A08ED
0xa0896  ldc.i4   0x3F3
0xa089b  stloc.s  6
0xa089d  ldc.i4   0x80000007
0xa08a2  stloc.s  7
0xa08a4  ldc.i4.2
0xa08a5  newarr   [mscorlib]System.String
0xa08aa  dup
0xa08ab  ldc.i4.0
0xa08ac  ldstr    aSamaccountname// "sAMAccountName"
0xa08b1  stelem.ref
0xa08b2  dup
0xa08b3  ldc.i4.1
0xa08b4  ldstr    aObjectsid// "objectsid"
0xa08b9  stelem.ref
0xa08ba  stloc.s  8
0xa08bc  ldarg.0
0xa08bd  ldloc.s  8
0xa08bf  call     instance void ObjectPicker::SetAttributesToRetrieve(string[] names)
0xa08c4  ldarg.1
0xa08c5  ldloc.0
0xa08c6  ldc.i4.3
0xa08c7  ldelem.i4
0xa08c8  and
0xa08c9  brfalse.s loc_A08DC
0xa08cb  ldloc.s  6
0xa08cd  ldc.i4.s 0xC
0xa08cf  or
0xa08d0  stloc.s  6
0xa08d2  ldloc.s  7
0xa08d4  ldc.i4   0x800C4000
0xa08d9  or
0xa08da  stloc.s  7
0xa08dc  ldarg.0
0xa08dd  ldloc.1
0xa08de  ldc.i4   0xC0
0xa08e3  ldloc.s  6
0xa08e5  ldloc.s  7
0xa08e7  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa08ec  ret
0xa08ed  ldarg.1
0xa08ee  ldloc.0
0xa08ef  ldc.i4.0
0xa08f0  ldelem.i4
0xa08f1  and
0xa08f2  brfalse.s loc_A090F
0xa08f4  ldarg.0
0xa08f5  ldc.i4   0x3F8
0xa08fa  ldc.i4   0x100
0xa08ff  ldc.i4   0x800
0xa0904  ldc.i4   0x80000008
0xa0909  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa090e  ret
0xa090f  ldarg.1
0xa0910  ldloc.0
0xa0911  ldc.i4.1
0xa0912  ldelem.i4
0xa0913  and
0xa0914  brfalse.s loc_A0945
0xa0916  ldc.i4.2
0xa0917  newarr   [mscorlib]System.String
0xa091c  dup
0xa091d  ldc.i4.0
0xa091e  ldstr    aSamaccountname// "sAMAccountName"
0xa0923  stelem.ref
0xa0924  dup
0xa0925  ldc.i4.1
0xa0926  ldstr    aObjectsid// "objectsid"
0xa092b  stelem.ref
0xa092c  stloc.s  9
0xa092e  ldarg.0
0xa092f  ldloc.s  9
0xa0931  call     instance void ObjectPicker::SetAttributesToRetrieve(string[] names)
0xa0936  ldarg.0
0xa0937  ldloc.1
0xa0938  ldc.i4.s 0x40
0xa093a  ldc.i4.2
0xa093b  ldc.i4   0x80000001
0xa0940  call     instance void ObjectPicker::AddScopeInfo(valuetype DSOP_SCOPE_TYPE_FLAGS scopeTypeFlags, valuetype DSOP_SCOPE_FLAGS scopeInitInfoFlags, valuetype DSOP_UPLEVEL_FILTER_FLAGS uplevelFilterFlags, valuetype DSOP_DOWNLEVEL_FILTER_FLAGS downlevelFlags)
0xa0945  ret
```
