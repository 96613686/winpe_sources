# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ExtractReportParameters

- ea: `0xbd90`
- end: `0xbef3`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ExtractReportParameters`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x4580`
- `0x45c0`
- `0xbd90`
- `0xcc00`

## pseudocode

```c

```

## disassembly

```asm
0xbd90  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xbd95  stloc.0
0xbd96  ldarg.2
0xbd97  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xbd9c  stind.ref
0xbd9d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<bool>::.ctor()
0xbda2  stloc.1
0xbda3  ldc.i4.0
0xbda4  stloc.2
0xbda5  br       loc_BED4
0xbdaa  ldarg.0
0xbdab  ldloc.2
0xbdac  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0xbdb1  stloc.3
0xbdb2  ldarg.0
0xbdb3  ldloc.2
0xbdb4  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(int32)
0xbdb9  stloc.s  4
0xbdbb  ldloc.s  4
0xbdbd  brfalse  loc_BED0
0xbdc2  ldloc.3
0xbdc3  brfalse  loc_BED0
0xbdc8  ldloc.3
0xbdc9  ldstr    aIsnull// ":isnull"
0xbdce  ldc.i4.1
0xbdcf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbdd4  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::EndsWith(string str, string postfix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbdd9  brfalse.s loc_BDFC
0xbddb  ldloc.3
0xbddc  ldc.i4.0
0xbddd  ldloc.3
0xbdde  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbde3  ldstr    aIsnull// ":isnull"
0xbde8  call     instance int32 [mscorlib]System.String::get_Length()
0xbded  sub
0xbdee  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xbdf3  stloc.3
0xbdf4  ldc.i4.1
0xbdf5  newarr   [mscorlib]System.String
0xbdfa  stloc.s  4
0xbdfc  ldloc.3
0xbdfd  ldstr    aIsnull// ":isnull"
0xbe02  ldc.i4.1
0xbe03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe08  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::EndsWith(string str, string postfix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbe0d  brfalse.s loc_BE30
0xbe0f  ldloc.3
0xbe10  ldc.i4.0
0xbe11  ldloc.3
0xbe12  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbe17  ldstr    aIsnull// ":isnull"
0xbe1c  call     instance int32 [mscorlib]System.String::get_Length()
0xbe21  sub
0xbe22  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xbe27  stloc.3
0xbe28  ldc.i4.1
0xbe29  newarr   [mscorlib]System.String
0xbe2e  stloc.s  4
0xbe30  ldloc.3
0xbe31  ldstr    aRs// "rs:"
0xbe36  ldc.i4.1
0xbe37  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe3c  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::StartsWith(string str, string prefix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbe41  brtrue.s loc_BE7C
0xbe43  ldloc.3
0xbe44  ldstr    aRc// "rc:"
0xbe49  ldc.i4.1
0xbe4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe4f  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::StartsWith(string str, string prefix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbe54  brtrue.s loc_BE7C
0xbe56  ldloc.3
0xbe57  ldstr    aDsu// "dsu:"
0xbe5c  ldc.i4.1
0xbe5d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe62  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::StartsWith(string str, string prefix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbe67  brtrue.s loc_BE7C
0xbe69  ldloc.3
0xbe6a  ldstr    aDsp// "dsp:"
0xbe6f  ldc.i4.1
0xbe70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe75  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::StartsWith(string str, string prefix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xbe7a  brfalse.s loc_BE9B
0xbe7c  ldloc.3
0xbe7d  ldloc.s  4
0xbe7f  ldnull
0xbe80  ldc.i4.0
0xbe81  ldarg.2
0xbe82  ldind.ref
0xbe83  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xbe88  brtrue.s loc_BED0
0xbe8a  ldstr    aExpectedToAddP// "expected to add parameter to collection"
0xbe8f  ldloc.3
0xbe90  call     string [mscorlib]System.String::Concat(string, string)
0xbe95  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xbe9a  throw
0xbe9b  ldloc.3
0xbe9c  ldloc.s  4
0xbe9e  ldstr    asc_19000// ""
0xbea3  ldc.i4.1
0xbea4  ldloc.0
0xbea5  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xbeaa  brtrue.s loc_BEBD
0xbeac  ldstr    aExpectedToAddP// "expected to add parameter to collection"
0xbeb1  ldloc.3
0xbeb2  call     string [mscorlib]System.String::Concat(string, string)
0xbeb7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xbebc  throw
0xbebd  ldarg.1
0xbebe  ldind.ref
0xbebf  brfalse.s loc_BED0
0xbec1  ldarg.1
0xbec2  ldind.ref
0xbec3  ldlen
0xbec4  brfalse.s loc_BED0
0xbec6  ldloc.1
0xbec7  ldarg.1
0xbec8  ldind.ref
0xbec9  ldloc.2
0xbeca  ldelem.u1
0xbecb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<bool>::Add(var<u1>)
0xbed0  ldloc.2
0xbed1  ldc.i4.1
0xbed2  add
0xbed3  stloc.2
0xbed4  ldloc.2
0xbed5  ldarg.0
0xbed6  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xbedb  blt      loc_BDAA
0xbee0  ldarg.1
0xbee1  ldind.ref
0xbee2  brfalse.s loc_BEF1
0xbee4  ldarg.1
0xbee5  ldind.ref
0xbee6  ldlen
0xbee7  brfalse.s loc_BEF1
0xbee9  ldarg.1
0xbeea  ldloc.1
0xbeeb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<bool>::ToArray()
0xbef0  stind.ref
0xbef1  ldloc.0
0xbef2  ret
```
