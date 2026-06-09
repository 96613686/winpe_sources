# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy

- ea: `0x4500`
- end: `0x466c`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x4500`

## pseudocode

```c

```

## disassembly

```asm
0x4500  ldc.i4.s 0x21
0x4502  stloc.2
0x4503  ldloca.s 2
0x4505  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x450a  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4510  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4515  stloc.0
0x4516  ldc.i4.s 0x20
0x4518  stloc.2
0x4519  ldloca.s 2
0x451b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4520  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4526  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x452b  stloc.1
0x452c  ldarg.0
0x452d  ldloc.0
0x452e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x4533  brfalse  loc_466B
0x4538  ldarg.0
0x4539  ldloc.1
0x453a  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x453f  brfalse  loc_466B
0x4544  ldarg.0
0x4545  ldloc.0
0x4546  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x454b  stloc.3
0x454c  ldloc.3
0x454d  ldc.i4.1
0x454e  newarr   [mscorlib]System.Char
0x4553  dup
0x4554  ldc.i4.0
0x4555  ldc.i4.s 0x2C
0x4557  stelem.i2
0x4558  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x455d  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__5_0
0x4562  dup
0x4563  brtrue.s loc_457C
0x4565  pop
0x4566  ldsfld   class <>c <>c::<>9
0x456b  ldftn    instance string <>c::<EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy>b__5_0(string x)
0x4571  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x4576  dup
0x4577  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__5_0
0x457c  call     T0x2B00002E
0x4581  stloc.s  4
0x4583  ldarg.0
0x4584  ldloc.1
0x4585  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x458a  ldc.i4.1
0x458b  newarr   [mscorlib]System.Char
0x4590  dup
0x4591  ldc.i4.0
0x4592  ldc.i4.s 0x2C
0x4594  stelem.i2
0x4595  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x459a  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__5_1
0x459f  dup
0x45a0  brtrue.s loc_45B9
0x45a2  pop
0x45a3  ldsfld   class <>c <>c::<>9
0x45a8  ldftn    instance string <>c::<EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy>b__5_1(string x)
0x45ae  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x45b3  dup
0x45b4  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__5_1
0x45b9  call     T0x2B00002E
0x45be  ldloc.s  4
0x45c0  ldstr    aTextHtml// "text/html"
0x45c5  call     instance string [mscorlib]System.String::ToUpperInvariant()
0x45ca  call     T0x2B000032
0x45cf  stloc.s  5
0x45d1  ldstr    aHtml// "*.html"
0x45d6  call     instance string [mscorlib]System.String::ToUpperInvariant()
0x45db  call     T0x2B000032
0x45e0  stloc.s  6
0x45e2  ldloc.3
0x45e3  stloc.s  7
0x45e5  ldloc.s  5
0x45e7  brtrue.s loc_4615
0x45e9  ldloc.s  6
0x45eb  brtrue.s loc_4615
0x45ed  ldloc.3
0x45ee  ldsfld   string [mscorlib]System.String::Empty
0x45f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x45f8  brtrue.s loc_460C
0x45fa  ldstr    a01_2// "{0}, {1}"
0x45ff  ldloc.3
0x4600  ldstr    aTextHtml// "text/html"
0x4605  call     string [mscorlib]System.String::Format(string, object, object)
0x460a  br.s     loc_4611
0x460c  ldstr    aTextHtml// "text/html"
0x4611  stloc.s  7
0x4613  br.s     loc_4662
0x4615  ldloc.s  5
0x4617  ldloc.s  6
0x4619  and
0x461a  brfalse.s loc_4662
0x461c  ldstr    asc_9610// ","
0x4621  ldloc.3
0x4622  ldc.i4.1
0x4623  newarr   [mscorlib]System.Char
0x4628  dup
0x4629  ldc.i4.0
0x462a  ldc.i4.s 0x2C
0x462c  stelem.i2
0x462d  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4632  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__5_2
0x4637  dup
0x4638  brtrue.s loc_4651
0x463a  pop
0x463b  ldsfld   class <>c <>c::<>9
0x4640  ldftn    instance bool <>c::<EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy>b__5_2(string x)
0x4646  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x464b  dup
0x464c  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__5_2
0x4651  call     T0x2B000033
0x4656  call     T0x2B000034
0x465b  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x4660  stloc.s  7
0x4662  ldarg.0
0x4663  ldloc.0
0x4664  ldloc.s  7
0x4666  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x466b  ret
```
