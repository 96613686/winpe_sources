# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::GetProduct

- ea: `0x190c0`
- end: `0x191dc`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::GetProduct`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x190c0`
- `0x19a20`
- `0x19bd0`
- `0x19be0`
- `0x19bf0`

## pseudocode

```c

```

## disassembly

```asm
0x190c0  ldarg.0
0x190c1  ldstr    aInstance// "instance"
0x190c6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x190cb  ldarg.0
0x190cc  callvirt instance class Microsoft.VisualStudio.Setup.Cache.IPackageReference Microsoft.VisualStudio.Setup.Cache.IInstance::get_Product()
0x190d1  stloc.0
0x190d2  ldloc.0
0x190d3  brfalse.s loc_190D7
0x190d5  ldloc.0
0x190d6  ret
0x190d7  ldarg.0
0x190d8  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class Microsoft.VisualStudio.Setup.Cache.IPackageReference> Microsoft.VisualStudio.Setup.Cache.IInstance::get_Packages()
0x190dd  dup
0x190de  brtrue.s loc_190E4
0x190e0  pop
0x190e1  ldnull
0x190e2  br.s     loc_19131
0x190e4  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, bool> <>c::<>9__10_0
0x190e9  dup
0x190ea  brtrue.s loc_19103
0x190ec  pop
0x190ed  ldsfld   class <>c <>c::<>9
0x190f2  ldftn    instance bool <>c::<GetProduct>b__10_0(class Microsoft.VisualStudio.Setup.Cache.IPackageReference p)
0x190f8  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, bool>::.ctor(object, native int)
0x190fd  dup
0x190fe  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, bool> <>c::<>9__10_0
0x19103  call     T0x2B0000BC
0x19108  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, string> <>c::<>9__10_1
0x1910d  dup
0x1910e  brtrue.s loc_19127
0x19110  pop
0x19111  ldsfld   class <>c <>c::<>9
0x19116  ldftn    instance string <>c::<GetProduct>b__10_1(class Microsoft.VisualStudio.Setup.Cache.IPackageReference p)
0x1911c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, string>::.ctor(object, native int)
0x19121  dup
0x19122  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, string> <>c::<>9__10_1
0x19127  call     T0x2B0000BD
0x1912c  call     T0x2B0000BE
0x19131  stloc.1
0x19132  ldloc.1
0x19133  brtrue.s loc_191B1
0x19135  ldarg.1
0x19136  brtrue.s loc_191B1
0x19138  ldarg.0
0x19139  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference> Microsoft.VisualStudio.Setup.Cache.IInstance::get_SelectedPackages()
0x1913e  dup
0x1913f  brtrue.s loc_19145
0x19141  pop
0x19142  ldnull
0x19143  br.s     loc_19192
0x19145  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, bool> <>c::<>9__10_2
0x1914a  dup
0x1914b  brtrue.s loc_19164
0x1914d  pop
0x1914e  ldsfld   class <>c <>c::<>9
0x19153  ldftn    instance bool <>c::<GetProduct>b__10_2(class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference p)
0x19159  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, bool>::.ctor(object, native int)
0x1915e  dup
0x1915f  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, bool> <>c::<>9__10_2
0x19164  call     T0x2B0000BF
0x19169  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, string> <>c::<>9__10_3
0x1916e  dup
0x1916f  brtrue.s loc_19188
0x19171  pop
0x19172  ldsfld   class <>c <>c::<>9
0x19177  ldftn    instance string <>c::<GetProduct>b__10_3(class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference p)
0x1917d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, string>::.ctor(object, native int)
0x19182  dup
0x19183  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.ISelectablePackageReference, string> <>c::<>9__10_3
0x19188  call     T0x2B0000C0
0x1918d  call     T0x2B0000C1
0x19192  stloc.1
0x19193  ldloc.1
0x19194  brtrue.s loc_191B1
0x19196  ldstr    aNoProductsAreR// "No products are registered for instance"...
0x1919b  ldarg.0
0x1919c  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x191a1  ldstr    asc_212B8// "'"
0x191a6  call     string [mscorlib]System.String::Concat(string, string, string)
0x191ab  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x191b0  throw
0x191b1  ldloc.1
0x191b2  brtrue.s loc_191B6
0x191b4  ldnull
0x191b5  ret
0x191b6  ldloc.1
0x191b7  ldsfld   class [mscorlib]System.Func`3<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference> <>c::<>9__10_4
0x191bc  dup
0x191bd  brtrue.s loc_191D6
0x191bf  pop
0x191c0  ldsfld   class <>c <>c::<>9
0x191c5  ldftn    instance class Microsoft.VisualStudio.Setup.Cache.IPackageReference <>c::<GetProduct>b__10_4(class Microsoft.VisualStudio.Setup.Cache.IPackageReference l, class Microsoft.VisualStudio.Setup.Cache.IPackageReference r)
0x191cb  newobj   instance void class [mscorlib]System.Func`3<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference>::.ctor(object, native int)
0x191d0  dup
0x191d1  stsfld   class [mscorlib]System.Func`3<class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference, class Microsoft.VisualStudio.Setup.Cache.IPackageReference> <>c::<>9__10_4
0x191d6  call     T0x2B0000C2
0x191db  ret
```
