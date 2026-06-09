# <GetAdvertisedPackageInfo>d__4::MoveNext

- ea: `0x6380`
- end: `0x6499`
- name: `<GetAdvertisedPackageInfo>d__4::MoveNext`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x6330`
- `0x6380`
- `0x64a0`
- `0x64c0`

## pseudocode

```c

```

## disassembly

```asm
0x6380  ldarg.0
0x6381  ldfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x6386  stloc.1
0x6387  ldloc.1
0x6388  brfalse.s loc_6398
0x638a  ldloc.1
0x638b  ldc.i4.1
0x638c  beq      loc_644D
0x6391  ldc.i4.0
0x6392  stloc.0
0x6393  leave    loc_6497
0x6398  ldarg.0
0x6399  ldc.i4.m1
0x639a  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x639f  ldarg.0
0x63a0  ldarg.0
0x63a1  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::advertisedPackages
0x63a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x63ab  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x63b0  ldarg.0
0x63b1  ldc.i4.s 0xFD
0x63b3  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x63b8  br       loc_646F
0x63bd  ldarg.0
0x63be  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x63c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x63c8  stloc.2
0x63c9  ldarg.0
0x63ca  ldloc.2
0x63cb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ILocalizedResources::get_LocalizedResources()
0x63d0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource>::GetEnumerator()
0x63d5  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x63da  ldarg.0
0x63db  ldc.i4.s 0xFC
0x63dd  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x63e2  br.s     loc_6455
0x63e4  ldarg.0
0x63e5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x63ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource>::get_Current()
0x63ef  stloc.3
0x63f0  ldloc.3
0x63f1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::get_Language()
0x63f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x63fb  brtrue.s loc_6455
0x63fd  ldloc.3
0x63fe  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::get_Title()
0x6403  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6408  brtrue.s loc_6455
0x640a  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackage::.ctor()
0x640f  stloc.s  4
0x6411  ldloc.s  4
0x6413  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackageResources> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackage::get_Resources()
0x6418  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackageResources::.ctor()
0x641d  dup
0x641e  ldloc.3
0x641f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::get_Language()
0x6424  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackageResources::set_Language(string)
0x6429  dup
0x642a  ldloc.3
0x642b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource::get_Title()
0x6430  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackageResources::set_Title(string)
0x6435  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackageResources>::Add(var<u1>)
0x643a  ldarg.0
0x643b  ldloc.s  4
0x643d  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.AdvertisedPackage <GetAdvertisedPackageInfo>d__4::<>2__current
0x6442  ldarg.0
0x6443  ldc.i4.1
0x6444  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x6449  ldc.i4.1
0x644a  stloc.0
0x644b  leave.s  loc_6497
0x644d  ldarg.0
0x644e  ldc.i4.s 0xFC
0x6450  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x6455  ldarg.0
0x6456  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x645b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6460  brtrue.s loc_63E4
0x6462  ldarg.0
0x6463  call     instance void <GetAdvertisedPackageInfo>d__4::<>m__Finally2()
0x6468  ldarg.0
0x6469  ldnull
0x646a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x646f  ldarg.0
0x6470  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x6475  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x647a  brtrue   loc_63BD
0x647f  ldarg.0
0x6480  call     instance void <GetAdvertisedPackageInfo>d__4::<>m__Finally1()
0x6485  ldarg.0
0x6486  ldnull
0x6487  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x648c  ldc.i4.0
0x648d  stloc.0
0x648e  leave.s  loc_6497
0x6490  ldarg.0
0x6491  call     instance void <GetAdvertisedPackageInfo>d__4::System.IDisposable.Dispose()
0x6496  endfinally
0x6497  ldloc.0
0x6498  ret
```
