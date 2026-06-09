# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::.ctor

- ea: `0x5410`
- end: `0x56e2`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::.ctor`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b30`

## callees

- `0x5790`
- `0x57c0`
- `0x57e0`

## string_xrefs

- `0x54a4`: `ConfigurationFile`
- `0x54e6`: `PrivateBinPath`
- `0x54fc`: `PrivateBinPathProbe`
- `0x56c6`: `LinkedHelpTopics`

## pseudocode

```c

```

## disassembly

```asm
0x5410  ldarg.0
0x5411  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.Internal.NodeType>::.ctor()
0x5416  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.Internal.NodeType> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_nodeTypes
0x541b  ldarg.0
0x541c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5421  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_extendsNodeTypes
0x5426  ldarg.0
0x5427  ldc.i4.m1
0x5428  stfld    valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_snapInType
0x542d  ldarg.0
0x542e  ldc.i4.2
0x542f  newarr   DWordProperty
0x5434  stloc.0
0x5435  ldloc.0
0x5436  ldc.i4.0
0x5437  ldelema  DWordProperty
0x543c  ldstr    aFolderbitmapsc// "FolderBitmapsColorMask"
0x5441  newobj   instance void DWordProperty::.ctor(string name)
0x5446  stobj    DWordProperty
0x544b  ldloc.0
0x544c  ldc.i4.1
0x544d  ldelema  DWordProperty
0x5452  ldstr    aUsecustomhelp// "UseCustomHelp"
0x5457  newobj   instance void DWordProperty::.ctor(string name)
0x545c  stobj    DWordProperty
0x5461  ldloc.0
0x5462  stfld    valuetype DWordProperty[] Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_dWordProperties
0x5467  ldarg.0
0x5468  ldc.i4.s 0x1B
0x546a  newarr   StringProperty
0x546f  stloc.1
0x5470  ldloc.1
0x5471  ldc.i4.0
0x5472  ldelema  StringProperty
0x5477  ldstr    aType// "Type"
0x547c  newobj   instance void StringProperty::.ctor(string name)
0x5481  stobj    StringProperty
0x5486  ldloc.1
0x5487  ldc.i4.1
0x5488  ldelema  StringProperty
0x548d  ldstr    aApplicationbas// "ApplicationBase"
0x5492  ldc.i4.0
0x5493  newobj   instance void StringProperty::.ctor(string name, bool optional)
0x5498  stobj    StringProperty
0x549d  ldloc.1
0x549e  ldc.i4.2
0x549f  ldelema  StringProperty
0x54a4  ldstr    aConfigurationf// "ConfigurationFile"
0x54a9  newobj   instance void StringProperty::.ctor(string name)
0x54ae  stobj    StringProperty
0x54b3  ldloc.1
0x54b4  ldc.i4.3
0x54b5  ldelema  StringProperty
0x54ba  ldstr    aDynamicbase// "DynamicBase"
0x54bf  newobj   instance void StringProperty::.ctor(string name)
0x54c4  stobj    StringProperty
0x54c9  ldloc.1
0x54ca  ldc.i4.4
0x54cb  ldelema  StringProperty
0x54d0  ldstr    aLicensefile// "LicenseFile"
0x54d5  newobj   instance void StringProperty::.ctor(string name)
0x54da  stobj    StringProperty
0x54df  ldloc.1
0x54e0  ldc.i4.5
0x54e1  ldelema  StringProperty
0x54e6  ldstr    aPrivatebinpath// "PrivateBinPath"
0x54eb  newobj   instance void StringProperty::.ctor(string name)
0x54f0  stobj    StringProperty
0x54f5  ldloc.1
0x54f6  ldc.i4.6
0x54f7  ldelema  StringProperty
0x54fc  ldstr    aPrivatebinpath_0// "PrivateBinPathProbe"
0x5501  newobj   instance void StringProperty::.ctor(string name)
0x5506  stobj    StringProperty
0x550b  ldloc.1
0x550c  ldc.i4.7
0x550d  ldelema  StringProperty
0x5512  ldstr    aResourcemodule// "ResourceModule"
0x5517  newobj   instance void StringProperty::.ctor(string name)
0x551c  stobj    StringProperty
0x5521  ldloc.1
0x5522  ldc.i4.8
0x5523  ldelema  StringProperty
0x5528  ldstr    aRootnodetype// "RootNodeType"
0x552d  newobj   instance void StringProperty::.ctor(string name)
0x5532  stobj    StringProperty
0x5537  ldloc.1
0x5538  ldc.i4.s 9
0x553a  ldelema  StringProperty
0x553f  ldstr    aNamestring// "NameString"
0x5544  newobj   instance void StringProperty::.ctor(string name)
0x5549  stobj    StringProperty
0x554e  ldloc.1
0x554f  ldc.i4.s 0xA
0x5551  ldelema  StringProperty
0x5556  ldstr    aDescription_0// "Description"
0x555b  newobj   instance void StringProperty::.ctor(string name)
0x5560  stobj    StringProperty
0x5565  ldloc.1
0x5566  ldc.i4.s 0xB
0x5568  ldelema  StringProperty
0x556d  ldstr    aProvider// "Provider"
0x5572  newobj   instance void StringProperty::.ctor(string name)
0x5577  stobj    StringProperty
0x557c  ldloc.1
0x557d  ldc.i4.s 0xC
0x557f  ldelema  StringProperty
0x5584  ldstr    aModulename// "ModuleName"
0x5589  newobj   instance void StringProperty::.ctor(string name)
0x558e  stobj    StringProperty
0x5593  ldloc.1
0x5594  ldc.i4.s 0xD
0x5596  ldelema  StringProperty
0x559b  ldstr    aAssemblyname// "AssemblyName"
0x55a0  newobj   instance void StringProperty::.ctor(string name)
0x55a5  stobj    StringProperty
0x55aa  ldloc.1
0x55ab  ldc.i4.s 0xE
0x55ad  ldelema  StringProperty
0x55b2  ldstr    aRuntimeversion// "RuntimeVersion"
0x55b7  newobj   instance void StringProperty::.ctor(string name)
0x55bc  stobj    StringProperty
0x55c1  ldloc.1
0x55c2  ldc.i4.s 0xF
0x55c4  ldelema  StringProperty
0x55c9  ldstr    aFxversion// "FxVersion"
0x55ce  newobj   instance void StringProperty::.ctor(string name)
0x55d3  stobj    StringProperty
0x55d8  ldloc.1
0x55d9  ldc.i4.s 0x10
0x55db  ldelema  StringProperty
0x55e0  ldstr    aAbout// "About"
0x55e5  newobj   instance void StringProperty::.ctor(string name)
0x55ea  stobj    StringProperty
0x55ef  ldloc.1
0x55f0  ldc.i4.s 0x11
0x55f2  ldelema  StringProperty
0x55f7  ldstr    aNamestringindi// "NameStringIndirect"
0x55fc  newobj   instance void StringProperty::.ctor(string name)
0x5601  stobj    StringProperty
0x5606  ldloc.1
0x5607  ldc.i4.s 0x12
0x5609  ldelema  StringProperty
0x560e  ldstr    aDescriptionstr// "DescriptionStringIndirect"
0x5613  newobj   instance void StringProperty::.ctor(string name)
0x5618  stobj    StringProperty
0x561d  ldloc.1
0x561e  ldc.i4.s 0x13
0x5620  ldelema  StringProperty
0x5625  ldstr    aProviderstring// "ProviderStringIndirect"
0x562a  newobj   instance void StringProperty::.ctor(string name)
0x562f  stobj    StringProperty
0x5634  ldloc.1
0x5635  ldc.i4.s 0x14
0x5637  ldelema  StringProperty
0x563c  ldstr    aVersionstringi// "VersionStringIndirect"
0x5641  newobj   instance void StringProperty::.ctor(string name)
0x5646  stobj    StringProperty
0x564b  ldloc.1
0x564c  ldc.i4.s 0x15
0x564e  ldelema  StringProperty
0x5653  ldstr    aIconindirect// "IconIndirect"
0x5658  newobj   instance void StringProperty::.ctor(string name)
0x565d  stobj    StringProperty
0x5662  ldloc.1
0x5663  ldc.i4.s 0x16
0x5665  ldelema  StringProperty
0x566a  ldstr    aLargefolderbit// "LargeFolderBitmapIndirect"
0x566f  newobj   instance void StringProperty::.ctor(string name)
0x5674  stobj    StringProperty
0x5679  ldloc.1
0x567a  ldc.i4.s 0x17
0x567c  ldelema  StringProperty
0x5681  ldstr    aSmallfolderbit// "SmallFolderBitmapIndirect"
0x5686  newobj   instance void StringProperty::.ctor(string name)
0x568b  stobj    StringProperty
0x5690  ldloc.1
0x5691  ldc.i4.s 0x18
0x5693  ldelema  StringProperty
0x5698  ldstr    aSmallselectedf// "SmallSelectedFolderBitmapIndirect"
0x569d  newobj   instance void StringProperty::.ctor(string name)
0x56a2  stobj    StringProperty
0x56a7  ldloc.1
0x56a8  ldc.i4.s 0x19
0x56aa  ldelema  StringProperty
0x56af  ldstr    aHelptopic// "HelpTopic"
0x56b4  newobj   instance void StringProperty::.ctor(string name)
0x56b9  stobj    StringProperty
0x56be  ldloc.1
0x56bf  ldc.i4.s 0x1A
0x56c1  ldelema  StringProperty
0x56c6  ldstr    aLinkedhelptopi// "LinkedHelpTopics"
0x56cb  newobj   instance void StringProperty::.ctor(string name)
0x56d0  stobj    StringProperty
0x56d5  ldloc.1
0x56d6  stfld    valuetype StringProperty[] Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_stringProperties
0x56db  ldarg.0
0x56dc  call     instance void [mscorlib]System.Object::.ctor()
0x56e1  ret
```
