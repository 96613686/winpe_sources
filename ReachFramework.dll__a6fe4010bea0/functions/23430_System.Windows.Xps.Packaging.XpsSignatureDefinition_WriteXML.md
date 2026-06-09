# System.Windows.Xps.Packaging.XpsSignatureDefinition::WriteXML

- ea: `0x23430`
- end: `0x23626`
- name: `System.Windows.Xps.Packaging.XpsSignatureDefinition::WriteXML`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x21b90`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x1fe80`
- `0x1ff20`
- `0x1ff40`
- `0x1ff50`
- `0x1ff60`
- `0x1ff70`
- `0x1ff80`
- `0x1ff90`
- `0x1ffa0`
- `0x1ffb0`
- `0x1ffc0`
- `0x201c0`
- `0x23280`
- `0x232a0`
- `0x232c0`
- `0x23330`
- `0x23350`
- `0x23370`
- `0x23390`
- `0x233b0`
- `0x233d0`
- `0x233f0`
- `0x23430`

## string_xrefs

- `0x23433`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x23430  ldarg.1
0x23431  brtrue.s loc_2343E
0x23433  ldstr    aWriter// "writer"
0x23438  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2343d  throw
0x2343e  ldarg.1
0x2343f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefinition()
0x23444  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefinitionNamespace()
0x23449  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x2344e  ldarg.0
0x2344f  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotId()
0x23454  stloc.0
0x23455  ldloca.s 0
0x23457  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2345c  brfalse.s loc_23484
0x2345e  ldarg.1
0x2345f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SpotId()
0x23464  ldarg.0
0x23465  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotId()
0x2346a  stloc.0
0x2346b  ldloca.s 0
0x2346d  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x23473  callvirt instance string [mscorlib]System.Object::ToString()
0x23478  call     string [System.Xml]System.Xml.XmlConvert::EncodeName(string)
0x2347d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x23482  br.s     loc_23494
0x23484  ldstr    aReachpackaging_11// "ReachPackaging_SpotIDRequiredAttribute"
0x23489  call     string System.Windows.Xps.SR::Get(string id)
0x2348e  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x23493  throw
0x23494  ldarg.0
0x23495  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_RequestedSigner()
0x2349a  brfalse.s loc_234AD
0x2349c  ldarg.1
0x2349d  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_RequestedSigner()
0x234a2  ldarg.0
0x234a3  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_RequestedSigner()
0x234a8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x234ad  ldarg.0
0x234ae  call     instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Xps.Packaging.XpsSignatureDefinition::get_Culture()
0x234b3  brfalse.s loc_234D7
0x234b5  ldarg.0
0x234b6  call     instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Xps.Packaging.XpsSignatureDefinition::get_Culture()
0x234bb  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x234c0  call     class [PresentationCore]System.Windows.Markup.XmlLanguage [PresentationCore]System.Windows.Markup.XmlLanguage::GetLanguage(string)
0x234c5  stloc.1
0x234c6  ldarg.1
0x234c7  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_XmlLang()
0x234cc  ldloc.1
0x234cd  callvirt instance string [mscorlib]System.Object::ToString()
0x234d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x234d7  ldarg.0
0x234d8  call     instance class System.Windows.Xps.Packaging.SpotLocation System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotLocation()
0x234dd  brfalse  loc_23571
0x234e2  ldarg.1
0x234e3  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SpotLocation()
0x234e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x234ed  ldarg.0
0x234ee  call     instance class System.Windows.Xps.Packaging.SpotLocation System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotLocation()
0x234f3  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.SpotLocation::get_PageUri()
0x234f8  ldc.i4   0x80000000
0x234fd  ldc.i4.3
0x234fe  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x23503  ldc.i4.0
0x23504  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x23509  stloc.2
0x2350a  ldloc.2
0x2350b  ldc.i4   0x80000000
0x23510  ldc.i4.1
0x23511  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x23516  stloc.3
0x23517  ldarg.1
0x23518  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_PageUri()
0x2351d  ldloc.3
0x2351e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x23523  ldarg.1
0x23524  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StartX()
0x23529  ldarg.0
0x2352a  call     instance class System.Windows.Xps.Packaging.SpotLocation System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotLocation()
0x2352f  callvirt instance float64 System.Windows.Xps.Packaging.SpotLocation::get_StartX()
0x23534  stloc.s  4
0x23536  ldloca.s 4
0x23538  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2353d  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x23542  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x23547  ldarg.1
0x23548  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StartY()
0x2354d  ldarg.0
0x2354e  call     instance class System.Windows.Xps.Packaging.SpotLocation System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SpotLocation()
0x23553  callvirt instance float64 System.Windows.Xps.Packaging.SpotLocation::get_StartY()
0x23558  stloc.s  4
0x2355a  ldloca.s 4
0x2355c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23561  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x23566  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2356b  ldarg.1
0x2356c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x23571  ldarg.0
0x23572  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_Intent()
0x23577  brfalse.s loc_23596
0x23579  ldarg.1
0x2357a  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_Intent()
0x2357f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x23584  ldarg.1
0x23585  ldarg.0
0x23586  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_Intent()
0x2358b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x23590  ldarg.1
0x23591  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x23596  ldarg.0
0x23597  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SignBy()
0x2359c  stloc.s  5
0x2359e  ldloca.s 5
0x235a0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x235a5  brfalse.s loc_235F3
0x235a7  ldarg.1
0x235a8  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignBy()
0x235ad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x235b2  ldarg.1
0x235b3  ldarg.0
0x235b4  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SignBy()
0x235b9  stloc.s  5
0x235bb  ldloca.s 5
0x235bd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x235c2  stloc.s  6
0x235c4  ldloca.s 6
0x235c6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x235cb  stloc.s  6
0x235cd  ldloca.s 6
0x235cf  ldstr    aS// "s"
0x235d4  call     class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.DateTimeFormatInfo::get_InvariantInfo()
0x235d9  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x235de  ldstr    aZ// "Z"
0x235e3  call     string [mscorlib]System.String::Concat(string, string)
0x235e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x235ed  ldarg.1
0x235ee  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x235f3  ldarg.0
0x235f4  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SigningLocale()
0x235f9  brfalse.s loc_23618
0x235fb  ldarg.1
0x235fc  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SigningLocale()
0x23601  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x23606  ldarg.1
0x23607  ldarg.0
0x23608  call     instance string System.Windows.Xps.Packaging.XpsSignatureDefinition::get_SigningLocale()
0x2360d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x23612  ldarg.1
0x23613  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x23618  ldarg.1
0x23619  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2361e  ldarg.0
0x2361f  ldc.i4.0
0x23620  stfld    bool System.Windows.Xps.Packaging.XpsSignatureDefinition::_hasBeenModified
0x23625  ret
```
