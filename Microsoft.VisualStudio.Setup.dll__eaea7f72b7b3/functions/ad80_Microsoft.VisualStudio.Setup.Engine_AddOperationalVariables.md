# Microsoft.VisualStudio.Setup.Engine::AddOperationalVariables

- ea: `0xad80`
- end: `0xb666`
- name: `Microsoft.VisualStudio.Setup.Engine::AddOperationalVariables`
- size: `2278`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0xaca0`

## callees

- `0x7e40`
- `0x7ed0`
- `0x7f10`
- `0x7ff0`
- `0x81c0`
- `0x9b20`
- `0xad80`
- `0xc7b0`
- `0xcf10`
- `0xcf40`
- `0xcf60`
- `0x1cd00`
- `0x1cda0`
- `0x1ce70`
- `0x1d030`
- `0x54750`
- `0x67f40`

## string_xrefs

- `0xb0d4`: `InstallationName`
- `0xb0e6`: `InstallationName`
- `0xb130`: `ChannelsPath`
- `0xb142`: `ChannelsPath`
- `0xb0b2`: `InstallDir`
- `0xb05e`: `SharedInstallDir`
- `0xb07a`: `SharedInstallDrive`
- `0xb096`: `CompatInstallDir`
- `0xaf46`: `EnginePath`
- `0xaf62`: `ComponentId`
- `0xaf9a`: `InstallationVersion`
- `0xb026`: `InstallationPackages`
- `0xb042`: `InstallationWorkloads`

## pseudocode

```c

```

## disassembly

```asm
0xad80  newobj   instance void <>c__DisplayClass180_0::.ctor()
0xad85  stloc.0
0xad86  ldloc.0
0xad87  ldarg.s  7
0xad89  stfld    string <>c__DisplayClass180_0::enginePath
0xad8e  ldloc.0
0xad8f  ldarg.2
0xad90  stfld    string <>c__DisplayClass180_0::productId
0xad95  ldloc.0
0xad96  ldarg.s  6
0xad98  stfld    string <>c__DisplayClass180_0::installationVersion
0xad9d  ldloc.0
0xad9e  ldarg.0
0xad9f  stfld    class Microsoft.VisualStudio.Setup.Engine <>c__DisplayClass180_0::<>4__this
0xada4  ldloc.0
0xada5  ldarg.s  4
0xada7  stfld    string <>c__DisplayClass180_0::destination
0xadac  ldloc.0
0xadad  ldnull
0xadae  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass180_0::instance
0xadb3  ldloc.0
0xadb4  ldarg.0
0xadb5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Engine::cache
0xadba  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0xadbf  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass180_0::instance
0xadc4  ldarg.3
0xadc5  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__180_0
0xadca  dup
0xadcb  brtrue.s loc_ADE4
0xadcd  pop
0xadce  ldsfld   class <>c <>c::<>9
0xadd3  ldftn    instance bool <>c::<AddOperationalVariables>b__180_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage x)
0xadd9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0xadde  dup
0xaddf  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> <>c::<>9__180_0
0xade4  call     T0x2B000012
0xade9  ldloc.0
0xadea  ldsfld   string [mscorlib]System.String::Empty
0xadef  stfld    string <>c__DisplayClass180_0::packageIds
0xadf4  ldloc.0
0xadf5  ldsfld   string [mscorlib]System.String::Empty
0xadfa  stfld    string <>c__DisplayClass180_0::workloadIds
0xadff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0xae04  stloc.s  6
0xae06  br       loc_AEA8
0xae0b  ldloc.s  6
0xae0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0xae12  stloc.s  7
0xae14  ldloc.s  7
0xae16  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_Type()
0xae1b  ldc.i4.7
0xae1c  bne.un.s loc_AE5F
0xae1e  ldloc.0
0xae1f  ldloc.0
0xae20  ldfld    string <>c__DisplayClass180_0::workloadIds
0xae25  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xae2a  brtrue.s loc_AE51
0xae2c  ldstr    asc_828F4// ","
0xae31  ldc.i4.2
0xae32  newarr   [mscorlib]System.String
0xae37  dup
0xae38  ldc.i4.0
0xae39  ldloc.0
0xae3a  ldfld    string <>c__DisplayClass180_0::workloadIds
0xae3f  stelem.ref
0xae40  dup
0xae41  ldc.i4.1
0xae42  ldloc.s  7
0xae44  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xae49  stelem.ref
0xae4a  call     string [mscorlib]System.String::Join(string, string[])
0xae4f  br.s     loc_AE58
0xae51  ldloc.s  7
0xae53  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xae58  stfld    string <>c__DisplayClass180_0::workloadIds
0xae5d  br.s     loc_AEA8
0xae5f  ldloc.s  7
0xae61  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_Type()
0xae66  ldc.i4.8
0xae67  bne.un.s loc_AEA8
0xae69  ldloc.0
0xae6a  ldloc.0
0xae6b  ldfld    string <>c__DisplayClass180_0::packageIds
0xae70  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xae75  brtrue.s loc_AE9C
0xae77  ldstr    asc_828F4// ","
0xae7c  ldc.i4.2
0xae7d  newarr   [mscorlib]System.String
0xae82  dup
0xae83  ldc.i4.0
0xae84  ldloc.0
0xae85  ldfld    string <>c__DisplayClass180_0::packageIds
0xae8a  stelem.ref
0xae8b  dup
0xae8c  ldc.i4.1
0xae8d  ldloc.s  7
0xae8f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xae94  stelem.ref
0xae95  call     string [mscorlib]System.String::Join(string, string[])
0xae9a  br.s     loc_AEA3
0xae9c  ldloc.s  7
0xae9e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xaea3  stfld    string <>c__DisplayClass180_0::packageIds
0xaea8  ldloc.s  6
0xaeaa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xaeaf  brtrue   loc_AE0B
0xaeb4  leave.s  loc_AEC2
0xaeb6  ldloc.s  6
0xaeb8  brfalse.s loc_AEC1
0xaeba  ldloc.s  6
0xaebc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaec1  endfinally
0xaec2  ldloc.0
0xaec3  ldarg.1
0xaec4  brtrue.s loc_AEC9
0xaec6  ldnull
0xaec7  br.s     loc_AECF
0xaec9  ldarg.1
0xaeca  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0xaecf  stfld    string <>c__DisplayClass180_0::componentId
0xaed4  ldloc.0
0xaed5  ldloc.0
0xaed6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass180_0::instance
0xaedb  dup
0xaedc  brtrue.s loc_AEEB
0xaede  pop
0xaedf  ldloca.s 8
0xaee1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xaee7  ldloc.s  8
0xaee9  br.s     loc_AF05
0xaeeb  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_CatalogInfo()
0xaef0  dup
0xaef1  brtrue.s loc_AF00
0xaef3  pop
0xaef4  ldloca.s 8
0xaef6  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xaefc  ldloc.s  8
0xaefe  br.s     loc_AF05
0xaf00  call     instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_FeatureReleaseMonth()
0xaf05  stfld    valuetype [mscorlib]System.Nullable`1<int32> <>c__DisplayClass180_0::featureMonth
0xaf0a  ldloc.0
0xaf0b  ldloc.0
0xaf0c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance <>c__DisplayClass180_0::instance
0xaf11  dup
0xaf12  brtrue.s loc_AF21
0xaf14  pop
0xaf15  ldloca.s 8
0xaf17  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xaf1d  ldloc.s  8
0xaf1f  br.s     loc_AF3B
0xaf21  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_CatalogInfo()
0xaf26  dup
0xaf27  brtrue.s loc_AF36
0xaf29  pop
0xaf2a  ldloca.s 8
0xaf2c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xaf32  ldloc.s  8
0xaf34  br.s     loc_AF3B
0xaf36  call     instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CatalogInfo::get_FeatureReleaseYear()
0xaf3b  stfld    valuetype [mscorlib]System.Nullable`1<int32> <>c__DisplayClass180_0::featureYear
0xaf40  ldarg.0
0xaf41  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xaf46  ldstr    aEnginepath// "EnginePath"
0xaf4b  ldloc.0
0xaf4c  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__1()
0xaf52  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xaf57  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xaf5c  ldarg.0
0xaf5d  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xaf62  ldstr    aComponentid// "ComponentId"
0xaf67  ldloc.0
0xaf68  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__2()
0xaf6e  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xaf73  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xaf78  ldarg.0
0xaf79  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xaf7e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDPRODUCTID
0xaf83  ldloc.0
0xaf84  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__3()
0xaf8a  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xaf8f  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xaf94  ldarg.0
0xaf95  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xaf9a  ldstr    aInstallationve// "InstallationVersion"
0xaf9f  ldloc.0
0xafa0  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__4()
0xafa6  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xafab  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xafb0  ldarg.0
0xafb1  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xafb6  ldstr    aProductdisplay// "ProductDisplayVersion"
0xafbb  ldloc.0
0xafbc  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__5()
0xafc2  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xafc7  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xafcc  ldarg.0
0xafcd  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xafd2  ldstr    aProductsemanti// "ProductSemanticVersion"
0xafd7  ldloc.0
0xafd8  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__6()
0xafde  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xafe3  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xafe8  ldarg.0
0xafe9  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xafee  ldstr    aFeaturerelease// "FeatureReleaseMonth"
0xaff3  ldloc.0
0xaff4  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__7()
0xaffa  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xafff  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb004  ldarg.0
0xb005  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb00a  ldstr    aFeaturerelease_0// "FeatureReleaseYear"
0xb00f  ldloc.0
0xb010  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__8()
0xb016  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb01b  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb020  ldarg.0
0xb021  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb026  ldstr    aInstallationpa_0// "InstallationPackages"
0xb02b  ldloc.0
0xb02c  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__9()
0xb032  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb037  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb03c  ldarg.0
0xb03d  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb042  ldstr    aInstallationwo// "InstallationWorkloads"
0xb047  ldloc.0
0xb048  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__10()
0xb04e  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb053  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb058  ldarg.0
0xb059  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb05e  ldstr    aSharedinstalld// "SharedInstallDir"
0xb063  ldloc.0
0xb064  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__11()
0xb06a  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb06f  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb074  ldarg.0
0xb075  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb07a  ldstr    aSharedinstalld_0// "SharedInstallDrive"
0xb07f  ldloc.0
0xb080  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__12()
0xb086  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb08b  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb090  ldarg.0
0xb091  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb096  ldstr    aCompatinstalld// "CompatInstallDir"
0xb09b  ldloc.0
0xb09c  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__13()
0xb0a2  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb0a7  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb0ac  ldarg.0
0xb0ad  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb0b2  ldstr    aInstalldir// "InstallDir"
0xb0b7  ldloc.0
0xb0b8  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__14()
0xb0be  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb0c3  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb0c8  ldarg.0
0xb0c9  call     instance void Microsoft.VisualStudio.Setup.Engine::AddCEIPProperties()
0xb0ce  ldarg.0
0xb0cf  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb0d4  ldstr    aInstallationna// "InstallationName"
0xb0d9  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0xb0de  brtrue.s loc_B0FC
0xb0e0  ldarg.0
0xb0e1  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb0e6  ldstr    aInstallationna// "InstallationName"
0xb0eb  ldloc.0
0xb0ec  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__15()
0xb0f2  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb0f7  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb0fc  ldarg.0
0xb0fd  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb102  ldstr    aInstanceid// "InstanceId"
0xb107  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0xb10c  brtrue.s loc_B12A
0xb10e  ldarg.0
0xb10f  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb114  ldstr    aInstanceid// "InstanceId"
0xb119  ldloc.0
0xb11a  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__16()
0xb120  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb125  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb12a  ldarg.0
0xb12b  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb130  ldstr    aChannelspath// "ChannelsPath"
0xb135  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0xb13a  brtrue.s loc_B158
0xb13c  ldarg.0
0xb13d  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb142  ldstr    aChannelspath// "ChannelsPath"
0xb147  ldloc.0
0xb148  ldftn    instance string <>c__DisplayClass180_0::<AddOperationalVariables>b__17()
0xb14e  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb153  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, class [mscorlib]System.Func`1<string> initialize)
0xb158  ldarg.0
0xb159  call     instance class Microsoft.VisualStudio.Setup.VariableCollection Microsoft.VisualStudio.Setup.Engine::get_Properties()
0xb15e  ldsfld   string Microsoft.VisualStudio.Setup.WellKnownPropertyNames::Nickname
0xb163  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
  ... truncated ...
```
