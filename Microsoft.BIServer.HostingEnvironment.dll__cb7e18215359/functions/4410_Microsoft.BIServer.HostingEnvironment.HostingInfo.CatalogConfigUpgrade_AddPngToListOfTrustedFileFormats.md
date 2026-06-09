# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddPngToListOfTrustedFileFormats

- ea: `0x4410`
- end: `0x44f7`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddPngToListOfTrustedFileFormats`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x4410`

## string_xrefs

- `0x4430`: `jpg, jpeg, wav, pdf, img, gif, json, mp4, webm`
- `0x44ec`: `jpg, jpeg, jpe, wav, bmp, img, gif, json, mp4, web, png`

## pseudocode

```c

```

## disassembly

```asm
0x4410  ldarg.0
0x4411  ldc.i4.s 0x1C
0x4413  stloc.0
0x4414  ldloca.s 0
0x4416  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x441b  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4421  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4426  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x442b  brfalse  loc_44F6
0x4430  ldstr    aJpgJpegWavPdfI// "jpg, jpeg, wav, pdf, img, gif, json, mp"...
0x4435  ldc.i4.1
0x4436  newarr   [mscorlib]System.Char
0x443b  dup
0x443c  ldc.i4.0
0x443d  ldc.i4.s 0x2C
0x443f  stelem.i2
0x4440  call     instance string[] [mscorlib]System.String::Split(char[])
0x4445  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__4_0
0x444a  dup
0x444b  brtrue.s loc_4464
0x444d  pop
0x444e  ldsfld   class <>c <>c::<>9
0x4453  ldftn    instance string <>c::<AddPngToListOfTrustedFileFormats>b__4_0(string x)
0x4459  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x445e  dup
0x445f  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__4_0
0x4464  call     T0x2B00002E
0x4469  stloc.1
0x446a  ldarg.0
0x446b  ldc.i4.s 0x1C
0x446d  stloc.0
0x446e  ldloca.s 0
0x4470  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4475  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x447b  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x4480  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x4485  ldc.i4.1
0x4486  newarr   [mscorlib]System.Char
0x448b  dup
0x448c  ldc.i4.0
0x448d  ldc.i4.s 0x2C
0x448f  stelem.i2
0x4490  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4495  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__4_1
0x449a  dup
0x449b  brtrue.s loc_44B4
0x449d  pop
0x449e  ldsfld   class <>c <>c::<>9
0x44a3  ldftn    instance string <>c::<AddPngToListOfTrustedFileFormats>b__4_1(string x)
0x44a9  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x44ae  dup
0x44af  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__4_1
0x44b4  call     T0x2B00002E
0x44b9  stloc.2
0x44ba  ldloc.1
0x44bb  call     T0x2B00002F
0x44c0  ldloc.2
0x44c1  call     T0x2B00002F
0x44c6  bne.un.s loc_44F6
0x44c8  ldloc.1
0x44c9  ldloc.2
0x44ca  call     T0x2B000030
0x44cf  call     T0x2B000031
0x44d4  brtrue.s loc_44F6
0x44d6  ldarg.0
0x44d7  ldc.i4.s 0x1C
0x44d9  stloc.0
0x44da  ldloca.s 0
0x44dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44e1  constrained. Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x44e7  callvirt instance string [mscorlib]System.Enum::ToString(class [mscorlib]System.IFormatProvider)
0x44ec  ldstr    aJpgJpegJpeWavB// "jpg, jpeg, jpe, wav, bmp, img, gif, jso"...
0x44f1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x44f6  ret
```
