# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddMimeTypeIfNotInRestrictedResourceMimeTypeForUpload

- ea: `0x47b0`
- end: `0x483f`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddMimeTypeIfNotInRestrictedResourceMimeTypeForUpload`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x47b0`

## pseudocode

```c

```

## disassembly

```asm
0x47b0  ldc.i4.s 0x21
0x47b2  stloc.1
0x47b3  ldloca.s 1
0x47b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47ba  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x47c0  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x47c5  stloc.0
0x47c6  ldarg.0
0x47c7  ldloc.0
0x47c8  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x47cd  brfalse.s loc_483E
0x47cf  ldarg.0
0x47d0  ldloc.0
0x47d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x47d6  stloc.2
0x47d7  ldloc.2
0x47d8  ldc.i4.1
0x47d9  newarr   [mscorlib]System.Char
0x47de  dup
0x47df  ldc.i4.0
0x47e0  ldc.i4.s 0x2C
0x47e2  stelem.i2
0x47e3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x47e8  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__10_0
0x47ed  dup
0x47ee  brtrue.s loc_4807
0x47f0  pop
0x47f1  ldsfld   class <>c <>c::<>9
0x47f6  ldftn    instance string <>c::<AddMimeTypeIfNotInRestrictedResourceMimeTypeForUpload>b__10_0(string x)
0x47fc  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x4801  dup
0x4802  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__10_0
0x4807  call     T0x2B00002E
0x480c  ldarg.1
0x480d  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4812  call     T0x2B000032
0x4817  brtrue.s loc_483E
0x4819  ldloc.2
0x481a  ldsfld   string [mscorlib]System.String::Empty
0x481f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4824  brtrue.s loc_4834
0x4826  ldstr    a01_3// "{0},{1}"
0x482b  ldloc.2
0x482c  ldarg.1
0x482d  call     string [mscorlib]System.String::Format(string, object, object)
0x4832  br.s     loc_4835
0x4834  ldarg.1
0x4835  stloc.3
0x4836  ldarg.0
0x4837  ldloc.0
0x4838  ldloc.3
0x4839  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x483e  ret
```
