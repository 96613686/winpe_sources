# System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadElement

- ea: `0x23870`
- end: `0x23918`
- name: `System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadElement`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x23630`

## callees

- `0x1ee90`
- `0x1efa0`
- `0x1ff50`
- `0x1ff90`
- `0x1ffa0`
- `0x1ffb0`
- `0x23380`
- `0x233a0`
- `0x233c0`
- `0x236b0`
- `0x23870`
- `0x23920`

## pseudocode

```c

```

## disassembly

```asm
0x23870  ldarg.1
0x23871  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x23876  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SpotLocation()
0x2387b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23880  brfalse.s loc_2388A
0x23882  ldarg.0
0x23883  ldarg.1
0x23884  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadAttributes(class [System.Xml]System.Xml.XmlReader reader)
0x23889  ret
0x2388a  ldarg.1
0x2388b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x23890  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_Intent()
0x23895  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2389a  brfalse.s loc_238AA
0x2389c  ldarg.0
0x2389d  ldarg.0
0x2389e  ldarg.1
0x2389f  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadData(class [System.Xml]System.Xml.XmlReader reader)
0x238a4  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::set_Intent(string value)
0x238a9  ret
0x238aa  ldarg.1
0x238ab  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x238b0  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignBy()
0x238b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x238ba  brfalse.s loc_238D9
0x238bc  ldarg.0
0x238bd  ldarg.0
0x238be  ldarg.1
0x238bf  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadData(class [System.Xml]System.Xml.XmlReader reader)
0x238c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x238c9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x238ce  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x238d3  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::set_SignBy(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x238d8  ret
0x238d9  ldarg.1
0x238da  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x238df  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SigningLocale()
0x238e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x238e9  brfalse.s loc_238F9
0x238eb  ldarg.0
0x238ec  ldarg.0
0x238ed  ldarg.1
0x238ee  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadData(class [System.Xml]System.Xml.XmlReader reader)
0x238f3  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::set_SigningLocale(string value)
0x238f8  ret
0x238f9  ldstr    aReachpackaging_14// "ReachPackaging_NotValidSignatureDefinit"...
0x238fe  ldc.i4.1
0x238ff  newarr   [mscorlib]System.Object
0x23904  dup
0x23905  ldc.i4.0
0x23906  ldarg.1
0x23907  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x2390c  stelem.ref
0x2390d  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x23912  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x23917  throw
```
