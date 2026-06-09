# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetInstallSize_0

- ea: `0x14920`
- end: `0x14d5e`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetInstallSize_0`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14910`

## callees

- `0x5ec0`
- `0x6b90`
- `0x79e0`
- `0x7a50`
- `0x7a70`
- `0x7ab0`
- `0x7af0`
- `0x7b40`
- `0x7c10`
- `0x7c70`
- `0x7f20`
- `0x7f60`
- `0x8050`
- `0x8090`
- `0x8280`
- `0x8290`
- `0xc1a0`
- `0x14850`
- `0x14920`
- `0x14d60`
- `0x15250`
- `0x152d0`
- `0x163d0`
- `0x19780`

## string_xrefs

- `0x14a06`: `cacheManager`

## pseudocode

```c

```

## disassembly

```asm
0x14920  ldarg.0
0x14921  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_InstallOrder()
0x14926  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>> <>c::<>9__22_0
0x1492b  dup
0x1492c  brtrue.s loc_14945
0x1492e  pop
0x1492f  ldsfld   class <>c <>c::<>9
0x14934  ldftn    instance class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage> <>c::<GetInstallSize>b__22_0(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x1493a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>>::.ctor(object, native int)
0x1493f  dup
0x14940  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>> <>c::<>9__22_0
0x14945  call     T0x2B00007E
0x1494a  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool> <>c::<>9__22_1
0x1494f  dup
0x14950  brtrue.s loc_14969
0x14952  pop
0x14953  ldsfld   class <>c <>c::<>9
0x14958  ldftn    instance bool <>c::<GetInstallSize>b__22_1(class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage> bundle)
0x1495e  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool>::.ctor(object, native int)
0x14963  dup
0x14964  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool> <>c::<>9__22_1
0x14969  call     T0x2B00007F
0x1496e  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool> <>c::<>9__22_2
0x14973  dup
0x14974  brtrue.s loc_1498D
0x14976  pop
0x14977  ldsfld   class <>c <>c::<>9
0x1497c  ldftn    instance bool <>c::<GetInstallSize>b__22_2(class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage> bundle)
0x14982  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool>::.ctor(object, native int)
0x14987  dup
0x14988  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>, bool> <>c::<>9__22_2
0x1498d  call     T0x2B00007F
0x14992  ldc.i4.0
0x14993  conv.i8
0x14994  stloc.0
0x14995  ldc.i4.0
0x14996  conv.i8
0x14997  stloc.1
0x14998  ldc.i4.0
0x14999  conv.i8
0x1499a  stloc.2
0x1499b  ldc.i4.0
0x1499c  conv.i8
0x1499d  stloc.3
0x1499e  ldc.i4.0
0x1499f  conv.i8
0x149a0  stloc.s  4
0x149a2  ldc.i4.0
0x149a3  conv.i8
0x149a4  stloc.s  5
0x149a6  ldc.i4.0
0x149a7  conv.i8
0x149a8  stloc.s  6
0x149aa  ldc.i4.0
0x149ab  conv.i8
0x149ac  stloc.s  7
0x149ae  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::.ctor()
0x149b3  stloc.s  8
0x149b5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::.ctor()
0x149ba  stloc.s  9
0x149bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>>::GetEnumerator()
0x149c1  stloc.s  0xB
0x149c3  br       loc_14CA5
0x149c8  ldloc.s  0xB
0x149ca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>>::get_Current()
0x149cf  stloc.s  0xC
0x149d1  ldloc.s  0xC
0x149d3  callvirt instance var<u1> class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Package()
0x149d8  stloc.s  0xD
0x149da  ldc.i4.0
0x149db  conv.i8
0x149dc  stloc.s  0xE
0x149de  ldc.i4.0
0x149df  conv.i8
0x149e0  stloc.s  0xF
0x149e2  ldc.i4.0
0x149e3  conv.i8
0x149e4  stloc.s  0x10
0x149e6  ldloc.s  0xD
0x149e8  callvirt instance int64 Microsoft.VisualStudio.Setup.IInstallablePackage::get_DownloadSize()
0x149ed  stloc.s  0x11
0x149ef  ldarg.1
0x149f0  brfalse.s loc_14A28
0x149f2  ldarg.0
0x149f3  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x149f8  dup
0x149f9  brtrue.s loc_149FF
0x149fb  pop
0x149fc  ldnull
0x149fd  br.s     loc_14A05
0x149ff  ldc.i4.0
0x14a00  call     T0x2B000080
0x14a05  dup
0x14a06  ldstr    aCachemanager// "cacheManager"
0x14a0b  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x14a10  ldloc.s  0xD
0x14a12  ldc.i4.0
0x14a13  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.CacheState Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetCacheState(class Microsoft.VisualStudio.Setup.IPackageIdentity identity, [opt] bool layout)
0x14a18  stloc.s  0x17
0x14a1a  ldloc.s  0x17
0x14a1c  ldc.i4.2
0x14a1d  beq.s    loc_14A24
0x14a1f  ldloc.s  0x17
0x14a21  ldc.i4.4
0x14a22  bne.un.s loc_14A28
0x14a24  ldc.i4.0
0x14a25  conv.i8
0x14a26  stloc.s  0x11
0x14a28  ldnull
0x14a29  stloc.s  0x12
0x14a2b  ldloc.s  0xD
0x14a2d  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a32  brfalse  loc_14B06
0x14a37  ldloc.s  0xD
0x14a39  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a3e  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_SystemDrive()
0x14a43  conv.r8
0x14a44  ldc.r8   1.02
0x14a4d  mul
0x14a4e  conv.i8
0x14a4f  stloc.s  0xE
0x14a51  ldloc.s  0xD
0x14a53  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a58  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_TargetDrive()
0x14a5d  stloc.s  0xF
0x14a5f  ldloc.s  0xD
0x14a61  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a66  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_SharedDrive()
0x14a6b  conv.r8
0x14a6c  ldc.r8   1.02
0x14a75  mul
0x14a76  conv.i8
0x14a77  stloc.s  0x10
0x14a79  ldloc.s  0xD
0x14a7b  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a80  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::GetCustomSizes()
0x14a85  stloc.s  0x12
0x14a87  ldc.i4.0
0x14a88  conv.i8
0x14a89  stloc.s  0x18
0x14a8b  ldc.i4.0
0x14a8c  conv.i8
0x14a8d  stloc.s  0x19
0x14a8f  ldloc.s  0xD
0x14a91  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14a96  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Count()
0x14a9b  ldc.i4.0
0x14a9c  ble.s    loc_14AEC
0x14a9e  ldloc.s  0xD
0x14aa0  callvirt instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.IPayloads::get_InstallSizes()
0x14aa5  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::GetTotalNonCacheInstallSize()
0x14aaa  brtrue.s loc_14AEC
0x14aac  ldloc.s  0xD
0x14aae  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Payload> Microsoft.VisualStudio.Setup.IPayloads::get_Payloads()
0x14ab3  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Payload, int64> <>c::<>9__22_3
0x14ab8  dup
0x14ab9  brtrue.s loc_14AD2
0x14abb  pop
0x14abc  ldsfld   class <>c <>c::<>9
0x14ac1  ldftn    instance int64 <>c::<GetInstallSize>b__22_3(class Microsoft.VisualStudio.Setup.Payload x)
0x14ac7  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Payload, int64>::.ctor(object, native int)
0x14acc  dup
0x14acd  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Payload, int64> <>c::<>9__22_3
0x14ad2  call     T0x2B000030
0x14ad7  stloc.s  0x1A
0x14ad9  ldloc.s  0xD
0x14adb  isinst   Microsoft.VisualStudio.Setup.VsixPackage
0x14ae0  brfalse.s loc_14AE8
0x14ae2  ldloc.s  0x1A
0x14ae4  stloc.s  0x18
0x14ae6  br.s     loc_14AEC
0x14ae8  ldloc.s  0x1A
0x14aea  stloc.s  0x19
0x14aec  ldloc.s  0xE
0x14aee  ldloc.s  0x19
0x14af0  conv.r8
0x14af1  ldc.r8   1.02
0x14afa  mul
0x14afb  conv.i8
0x14afc  add
0x14afd  stloc.s  0xE
0x14aff  ldloc.s  0xF
0x14b01  ldloc.s  0x18
0x14b03  add
0x14b04  stloc.s  0xF
0x14b06  ldloc.s  0xC
0x14b08  callvirt instance var<u1> class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Node()
0x14b0d  ldarg.0
0x14b0e  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14b13  call     valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetCurrentState(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.IServiceProvider services)
0x14b18  ldloc.s  0xC
0x14b1a  callvirt instance var<u1> class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Node()
0x14b1f  ldarg.0
0x14b20  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14b25  call     valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetRequestedState(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.IServiceProvider services)
0x14b2a  stloc.s  0x13
0x14b2c  ldarg.0
0x14b2d  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14b32  ldloc.s  0xC
0x14b34  callvirt instance var<u1> class <>f__AnonymousType0`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Node()
0x14b39  call     valuetype Microsoft.VisualStudio.Setup.DetectedState Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetDetectedState(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x14b3e  stloc.s  0x14
0x14b40  ldc.i4.3
0x14b41  bne.un.s loc_14B4A
0x14b43  ldloc.s  0x14
0x14b45  ldc.i4.2
0x14b46  ceq
0x14b48  br.s     loc_14B4B
0x14b4a  ldc.i4.0
0x14b4b  stloc.s  0x15
0x14b4d  ldloc.s  0x15
0x14b4f  brfalse.s loc_14B73
0x14b51  ldloc.2
0x14b52  ldloc.s  0xE
0x14b54  add
0x14b55  stloc.2
0x14b56  ldloc.0
0x14b57  ldloc.s  0xF
0x14b59  add
0x14b5a  stloc.0
0x14b5b  ldloc.s  4
0x14b5d  ldloc.s  0x10
0x14b5f  add
0x14b60  stloc.s  4
0x14b62  ldloc.s  6
0x14b64  ldloc.s  0x11
0x14b66  add
0x14b67  stloc.s  6
0x14b69  ldloc.s  8
0x14b6b  ldloc.s  0x12
0x14b6d  ldc.i4.1
0x14b6e  call     void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AddCustomSizes(class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizesTotal, class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizes, bool shouldAdd)
0x14b73  ldloc.s  0x13
0x14b75  ldc.i4.3
0x14b76  bne.un.s loc_14BA1
0x14b78  ldloc.s  0x14
0x14b7a  ldc.i4.1
0x14b7b  bne.un.s loc_14BA1
0x14b7d  ldloc.3
0x14b7e  ldloc.s  0xE
0x14b80  add
0x14b81  stloc.3
0x14b82  ldloc.1
0x14b83  ldloc.s  0xF
0x14b85  add
0x14b86  stloc.1
0x14b87  ldloc.s  5
0x14b89  ldloc.s  0x10
0x14b8b  add
0x14b8c  stloc.s  5
0x14b8e  ldloc.s  7
0x14b90  ldloc.s  0x11
0x14b92  add
0x14b93  stloc.s  7
0x14b95  ldloc.s  9
0x14b97  ldloc.s  0x12
0x14b99  ldc.i4.1
0x14b9a  call     void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AddCustomSizes(class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizesTotal, class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizes, bool shouldAdd)
0x14b9f  br.s     loc_14BE8
0x14ba1  ldloc.s  0x13
0x14ba3  ldc.i4.1
0x14ba4  ceq
0x14ba6  ldloc.s  0x15
0x14ba8  and
0x14ba9  brfalse.s loc_14BE8
0x14bab  ldloc.s  0xD
0x14bad  callvirt instance valuetype Microsoft.VisualStudio.Setup.CurrentState Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x14bb2  ldc.i4.2
0x14bb3  bne.un.s loc_14BCD
0x14bb5  ldloc.s  0xD
0x14bb7  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_SupersedingPackage()
0x14bbc  brfalse.s loc_14BCD
0x14bbe  ldloc.s  0xD
0x14bc0  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_SupersedingPackage()
0x14bc5  callvirt instance valuetype Microsoft.VisualStudio.Setup.DetectedState Microsoft.VisualStudio.Setup.IPackage::get_DetectedState()
0x14bca  ldc.i4.2
0x14bcb  beq.s    loc_14BE8
0x14bcd  ldloc.3
0x14bce  ldloc.s  0xE
0x14bd0  sub
0x14bd1  stloc.3
0x14bd2  ldloc.1
0x14bd3  ldloc.s  0xF
0x14bd5  sub
0x14bd6  stloc.1
0x14bd7  ldloc.s  5
0x14bd9  ldloc.s  0x10
0x14bdb  sub
0x14bdc  stloc.s  5
0x14bde  ldloc.s  9
0x14be0  ldloc.s  0x12
0x14be2  ldc.i4.0
0x14be3  call     void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AddCustomSizes(class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizesTotal, class [mscorlib]System.Collections.Generic.IDictionary`2<string, int64> customSizes, bool shouldAdd)
0x14be8  ldloc.s  0x13
0x14bea  ldc.i4.4
0x14beb  bne.un   loc_14CA5
0x14bf0  ldloc.s  0xD
0x14bf2  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x14bf7  brfalse  loc_14CA5
0x14bfc  ldloc.s  0xD
  ... truncated ...
```
