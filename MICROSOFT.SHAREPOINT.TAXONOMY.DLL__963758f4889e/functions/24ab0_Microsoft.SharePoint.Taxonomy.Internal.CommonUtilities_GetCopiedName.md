# Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetCopiedName

- ea: `0x24ab0`
- end: `0x24c12`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetCopiedName`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4f910`
- `0x51c20`

## callees

- `0x24ab0`
- `0x24c20`
- `0x2ad40`

## string_xrefs

- `0x24ab0`: `CopyOfNameFirst`
- `0x24ad9`: `CopyOfNameFirst`
- `0x24aff`: `CopyOfNameFirst`
- `0x24b6c`: `CopyOfName`
- `0x24ba3`: `CopyOfName`
- `0x24bdb`: `CopyOfName`

## pseudocode

```c

```

## disassembly

```asm
0x24ab0  ldstr    aCopyofnamefirs// "CopyOfNameFirst"
0x24ab5  ldc.i4.1
0x24ab6  newarr   [mscorlib]System.Object
0x24abb  stloc.s  7
0x24abd  ldloc.s  7
0x24abf  ldc.i4.0
0x24ac0  ldarg.0
0x24ac1  stelem.ref
0x24ac2  ldloc.s  7
0x24ac4  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24ac9  stloc.0
0x24aca  ldnull
0x24acb  stloc.1
0x24acc  ldloc.0
0x24acd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24ad2  ldc.i4   0xFF
0x24ad7  ble.s    loc_24B19
0x24ad9  ldstr    aCopyofnamefirs// "CopyOfNameFirst"
0x24ade  ldc.i4.1
0x24adf  newarr   [mscorlib]System.Object
0x24ae4  stloc.s  8
0x24ae6  ldloc.s  8
0x24ae8  ldc.i4.0
0x24ae9  ldstr    asc_794BA// ""
0x24aee  stelem.ref
0x24aef  ldloc.s  8
0x24af1  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24af6  stloc.1
0x24af7  ldarg.0
0x24af8  ldloc.1
0x24af9  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetTrimmedName(string name, string placeholder)
0x24afe  stloc.2
0x24aff  ldstr    aCopyofnamefirs// "CopyOfNameFirst"
0x24b04  ldc.i4.1
0x24b05  newarr   [mscorlib]System.Object
0x24b0a  stloc.s  9
0x24b0c  ldloc.s  9
0x24b0e  ldc.i4.0
0x24b0f  ldloc.2
0x24b10  stelem.ref
0x24b11  ldloc.s  9
0x24b13  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24b18  stloc.0
0x24b19  ldc.i4.1
0x24b1a  stloc.3
0x24b1b  ldc.i4.1
0x24b1c  stloc.s  4
0x24b1e  ldnull
0x24b1f  stloc.s  5
0x24b21  br       loc_24C09
0x24b26  ldc.i4.0
0x24b27  stloc.s  4
0x24b29  ldarg.1
0x24b2a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x24b2f  stloc.s  0xA
0x24b31  br.s     loc_24B4C
0x24b33  ldloca.s 0xA
0x24b35  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x24b3a  stloc.s  6
0x24b3c  ldloc.s  6
0x24b3e  ldloc.0
0x24b3f  ldc.i4.5
0x24b40  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x24b45  brfalse.s loc_24B4C
0x24b47  ldc.i4.1
0x24b48  stloc.s  4
0x24b4a  br.s     loc_24B55
0x24b4c  ldloca.s 0xA
0x24b4e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x24b53  brtrue.s loc_24B33
0x24b55  leave.s  loc_24B65
0x24b57  ldloca.s 0xA
0x24b59  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x24b5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24b64  endfinally
0x24b65  ldloc.s  4
0x24b67  brfalse  loc_24C09
0x24b6c  ldstr    aCopyofname// "CopyOfName"
0x24b71  ldc.i4.2
0x24b72  newarr   [mscorlib]System.Object
0x24b77  stloc.s  0xB
0x24b79  ldloc.s  0xB
0x24b7b  ldc.i4.0
0x24b7c  ldarg.0
0x24b7d  stelem.ref
0x24b7e  ldloc.s  0xB
0x24b80  ldc.i4.1
0x24b81  ldloca.s 3
0x24b83  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24b88  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x24b8d  stelem.ref
0x24b8e  ldloc.s  0xB
0x24b90  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24b95  stloc.0
0x24b96  ldloc.0
0x24b97  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24b9c  ldc.i4   0xFF
0x24ba1  ble.s    loc_24C05
0x24ba3  ldstr    aCopyofname// "CopyOfName"
0x24ba8  ldc.i4.2
0x24ba9  newarr   [mscorlib]System.Object
0x24bae  stloc.s  0xC
0x24bb0  ldloc.s  0xC
0x24bb2  ldc.i4.0
0x24bb3  ldstr    asc_794BA// ""
0x24bb8  stelem.ref
0x24bb9  ldloc.s  0xC
0x24bbb  ldc.i4.1
0x24bbc  ldloca.s 3
0x24bbe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24bc3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x24bc8  stelem.ref
0x24bc9  ldloc.s  0xC
0x24bcb  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24bd0  stloc.s  5
0x24bd2  ldarg.0
0x24bd3  ldloc.s  5
0x24bd5  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetTrimmedName(string name, string placeholder)
0x24bda  stloc.2
0x24bdb  ldstr    aCopyofname// "CopyOfName"
0x24be0  ldc.i4.2
0x24be1  newarr   [mscorlib]System.Object
0x24be6  stloc.s  0xD
0x24be8  ldloc.s  0xD
0x24bea  ldc.i4.0
0x24beb  ldloc.2
0x24bec  stelem.ref
0x24bed  ldloc.s  0xD
0x24bef  ldc.i4.1
0x24bf0  ldloca.s 3
0x24bf2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24bf7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x24bfc  stelem.ref
0x24bfd  ldloc.s  0xD
0x24bff  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x24c04  stloc.0
0x24c05  ldloc.3
0x24c06  ldc.i4.1
0x24c07  add.ovf
0x24c08  stloc.3
0x24c09  ldloc.s  4
0x24c0b  brtrue   loc_24B26
0x24c10  ldloc.0
0x24c11  ret
```
