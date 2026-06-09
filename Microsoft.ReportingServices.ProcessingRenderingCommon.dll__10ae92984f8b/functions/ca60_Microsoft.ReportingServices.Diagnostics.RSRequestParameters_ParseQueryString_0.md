# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ParseQueryString_0

- ea: `0xca60`
- end: `0xcbf5`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ParseQueryString_0`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xbc90`

## callees

- `0x3a20`
- `0x45c0`
- `0x8a50`
- `0x8b50`
- `0xc900`
- `0xca60`
- `0xcc00`

## string_xrefs

- `0xcaf4`: `Requested item path '{0}' doesn't match stored parameters path '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0xca60  ldarg.s  6
0xca62  ldnull
0xca63  stind.ref
0xca64  ldarg.s  7
0xca66  ldnull
0xca67  stind.ref
0xca68  ldarg.3
0xca69  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xca6e  stind.ref
0xca6f  ldarg.s  4
0xca71  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xca76  stind.ref
0xca77  ldarg.s  5
0xca79  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xca7e  stind.ref
0xca7f  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xca84  stloc.0
0xca85  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xca8a  stloc.1
0xca8b  ldnull
0xca8c  stloc.2
0xca8d  ldarg.2
0xca8e  brtrue.s loc_CA91
0xca90  ret
0xca91  ldarg.1
0xca92  ldarg.2
0xca93  ldarg.3
0xca94  ldind.ref
0xca95  ldarg.s  4
0xca97  ldind.ref
0xca98  ldloc.0
0xca99  ldloc.1
0xca9a  ldarg.s  5
0xca9c  ldind.ref
0xca9d  ldarg.s  7
0xca9f  ldloca.s 2
0xcaa1  call     void Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ResolveServerParameters(class Microsoft.ReportingServices.Diagnostics.IParametersTranslator paramsTranslator, class [System]System.Collections.Specialized.NameValueCollection allParametersCollection, class [System]System.Collections.Specialized.NameValueCollection rsParameters, class [System]System.Collections.Specialized.NameValueCollection rcParameters, class [System]System.Collections.Specialized.NameValueCollection dsuParameters, class [System]System.Collections.Specialized.NameValueCollection dspParameters, class [System]System.Collections.Specialized.NameValueCollection reportParameters, [out] class [mscorlib]System.Collections.Hashtable& reverseLookup, [out] class Microsoft.ReportingServices.Diagnostics.ExternalItemPath& itemPath)
0xcaa6  ldloc.2
0xcaa7  brfalse.s loc_CB17
0xcaa9  ldarg.0
0xcaaa  callvirt instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xcaaf  ldloc.2
0xcab0  callvirt instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xcab5  call     int32 Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare(string a, string b)
0xcaba  brfalse.s loc_CB17
0xcabc  ldarg.3
0xcabd  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xcac2  stind.ref
0xcac3  ldarg.s  4
0xcac5  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xcaca  stind.ref
0xcacb  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xcad0  stloc.0
0xcad1  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xcad6  stloc.1
0xcad7  ldarg.s  5
0xcad9  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xcade  stind.ref
0xcadf  ldarg.s  7
0xcae1  ldnull
0xcae2  stind.ref
0xcae3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xcae8  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xcaed  brfalse.s loc_CB17
0xcaef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcaf4  ldstr    aRequestedItemP// "Requested item path '{0}' doesn't match"...
0xcaf9  ldarg.0
0xcafa  callvirt instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xcaff  ldloc.2
0xcb00  callvirt instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xcb05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xcb0a  stloc.3
0xcb0b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xcb10  ldc.i4.3
0xcb11  ldloc.3
0xcb12  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xcb17  ldc.i4.0
0xcb18  stloc.s  4
0xcb1a  br       loc_CBDD
0xcb1f  ldarg.2
0xcb20  ldloc.s  4
0xcb22  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0xcb27  stloc.s  5
0xcb29  ldarg.2
0xcb2a  ldloc.s  4
0xcb2c  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(int32)
0xcb31  stloc.s  6
0xcb33  ldloc.s  6
0xcb35  brfalse  loc_CBD7
0xcb3a  ldloc.s  5
0xcb3c  brfalse  loc_CBD7
0xcb41  ldloc.s  5
0xcb43  ldstr    aIsnull// ":isnull"
0xcb48  ldc.i4.1
0xcb49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcb4e  call     bool Microsoft.ReportingServices.Diagnostics.StringSupport::EndsWith(string str, string postfix, bool ignoreCase, class [mscorlib]System.Globalization.CultureInfo culture)
0xcb53  brfalse.s loc_CB79
0xcb55  ldloc.s  5
0xcb57  ldc.i4.0
0xcb58  ldloc.s  5
0xcb5a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcb5f  ldstr    aIsnull// ":isnull"
0xcb64  call     instance int32 [mscorlib]System.String::get_Length()
0xcb69  sub
0xcb6a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xcb6f  stloc.s  5
0xcb71  ldc.i4.1
0xcb72  newarr   [mscorlib]System.String
0xcb77  stloc.s  6
0xcb79  ldloc.s  5
0xcb7b  ldloc.s  6
0xcb7d  ldstr    aRs// "rs:"
0xcb82  ldc.i4.0
0xcb83  ldarg.3
0xcb84  ldind.ref
0xcb85  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xcb8a  brtrue.s loc_CBD7
0xcb8c  ldloc.s  5
0xcb8e  ldloc.s  6
0xcb90  ldstr    aRc// "rc:"
0xcb95  ldc.i4.0
0xcb96  ldarg.s  4
0xcb98  ldind.ref
0xcb99  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xcb9e  brtrue.s loc_CBD7
0xcba0  ldloc.s  5
0xcba2  ldloc.s  6
0xcba4  ldstr    aDsu// "dsu:"
0xcba9  ldc.i4.0
0xcbaa  ldloc.0
0xcbab  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xcbb0  brtrue.s loc_CBD7
0xcbb2  ldloc.s  5
0xcbb4  ldloc.s  6
0xcbb6  ldstr    aDsp// "dsp:"
0xcbbb  ldc.i4.0
0xcbbc  ldloc.1
0xcbbd  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xcbc2  brtrue.s loc_CBD7
0xcbc4  ldloc.s  5
0xcbc6  ldloc.s  6
0xcbc8  ldstr    asc_19000// ""
0xcbcd  ldc.i4.1
0xcbce  ldarg.s  5
0xcbd0  ldind.ref
0xcbd1  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xcbd6  pop
0xcbd7  ldloc.s  4
0xcbd9  ldc.i4.1
0xcbda  add
0xcbdb  stloc.s  4
0xcbdd  ldloc.s  4
0xcbdf  ldarg.2
0xcbe0  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xcbe5  blt      loc_CB1F
0xcbea  ldarg.s  6
0xcbec  ldloc.0
0xcbed  ldloc.1
0xcbee  newobj   instance void Microsoft.ReportingServices.Diagnostics.DatasourceCredentialsCollection::.ctor(class [System]System.Collections.Specialized.NameValueCollection userNameParams, class [System]System.Collections.Specialized.NameValueCollection userPwdParams)
0xcbf3  stind.ref
0xcbf4  ret
```
