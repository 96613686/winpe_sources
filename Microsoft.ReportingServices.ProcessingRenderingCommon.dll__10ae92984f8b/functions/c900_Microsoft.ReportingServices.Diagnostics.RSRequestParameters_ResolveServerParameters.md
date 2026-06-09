# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ResolveServerParameters

- ea: `0xc900`
- end: `0xca5e`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ResolveServerParameters`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xca60`

## callees

- `0x78d0`
- `0xc900`
- `0xcc00`
- `0xcfc0`

## string_xrefs

- `0xc92d`: `rs:StoredParametersID`

## pseudocode

```c

```

## disassembly

```asm
0xc900  ldarg.s  7
0xc902  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xc907  stind.ref
0xc908  ldarg.s  8
0xc90a  ldnull
0xc90b  stind.ref
0xc90c  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xc911  stloc.0
0xc912  ldc.i4.0
0xc913  stloc.1
0xc914  br       loc_CA16
0xc919  ldarg.1
0xc91a  ldloc.1
0xc91b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0xc920  stloc.2
0xc921  ldloc.2
0xc922  brfalse  loc_CA12
0xc927  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xc92c  ldloc.2
0xc92d  ldstr    aRsStoredparame// "rs:StoredParametersID"
0xc932  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xc937  brtrue   loc_CA12
0xc93c  ldarg.1
0xc93d  ldloc.1
0xc93e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0xc943  stloc.3
0xc944  ldarg.0
0xc945  ldloc.3
0xc946  ldarg.s  8
0xc948  ldloca.s 4
0xc94a  callvirt instance void Microsoft.ReportingServices.Diagnostics.IParametersTranslator::GetParamsInstance(string paramsInstanceId, [out] class Microsoft.ReportingServices.Diagnostics.ExternalItemPath& itemPath, [out] class [System]System.Collections.Specialized.NameValueCollection& parameters)
0xc94f  ldloc.s  4
0xc951  brtrue.s loc_C95A
0xc953  ldloc.3
0xc954  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.StoredParameterNotFoundException::.ctor(string)
0xc959  throw
0xc95a  ldarg.s  7
0xc95c  ldind.ref
0xc95d  ldloc.s  4
0xc95f  newobj   instance void Microsoft.ReportingServices.Diagnostics.ReportParameterCollection::.ctor(class [System]System.Collections.Specialized.NameValueCollection other)
0xc964  ldloc.3
0xc965  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xc96a  ldloc.0
0xc96b  ldloc.2
0xc96c  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xc971  pop
0xc972  ldloc.s  4
0xc974  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase::GetEnumerator()
0xc979  stloc.s  5
0xc97b  br.s     loc_C9F2
0xc97d  ldloc.s  5
0xc97f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc984  castclass [mscorlib]System.String
0xc989  stloc.s  6
0xc98b  ldloc.s  4
0xc98d  ldloc.s  6
0xc98f  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xc994  stloc.s  7
0xc996  ldloc.s  6
0xc998  ldloc.s  7
0xc99a  ldstr    aRs// "rs:"
0xc99f  ldc.i4.0
0xc9a0  ldarg.2
0xc9a1  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc9a6  brtrue.s loc_C9F2
0xc9a8  ldloc.s  6
0xc9aa  ldloc.s  7
0xc9ac  ldstr    aRc// "rc:"
0xc9b1  ldc.i4.0
0xc9b2  ldarg.3
0xc9b3  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc9b8  brtrue.s loc_C9F2
0xc9ba  ldloc.s  6
0xc9bc  ldloc.s  7
0xc9be  ldstr    aDsu// "dsu:"
0xc9c3  ldc.i4.0
0xc9c4  ldarg.s  4
0xc9c6  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc9cb  brtrue.s loc_C9F2
0xc9cd  ldloc.s  6
0xc9cf  ldloc.s  7
0xc9d1  ldstr    aDsp// "dsp:"
0xc9d6  ldc.i4.0
0xc9d7  ldarg.s  5
0xc9d9  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc9de  brtrue.s loc_C9F2
0xc9e0  ldloc.s  6
0xc9e2  ldloc.s  7
0xc9e4  ldstr    asc_19000// ""
0xc9e9  ldc.i4.1
0xc9ea  ldarg.s  6
0xc9ec  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc9f1  pop
0xc9f2  ldloc.s  5
0xc9f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc9f9  brtrue.s loc_C97D
0xc9fb  leave.s  loc_CA12
0xc9fd  ldloc.s  5
0xc9ff  isinst   [mscorlib]System.IDisposable
0xca04  stloc.s  8
0xca06  ldloc.s  8
0xca08  brfalse.s loc_CA11
0xca0a  ldloc.s  8
0xca0c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca11  endfinally
0xca12  ldloc.1
0xca13  ldc.i4.1
0xca14  add
0xca15  stloc.1
0xca16  ldloc.1
0xca17  ldarg.1
0xca18  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xca1d  blt      loc_C919
0xca22  ldloc.0
0xca23  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0xca28  stloc.s  9
0xca2a  br.s     loc_CA3D
0xca2c  ldloc.s  9
0xca2e  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0xca33  stloc.s  0xA
0xca35  ldarg.1
0xca36  ldloc.s  0xA
0xca38  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0xca3d  ldloc.s  9
0xca3f  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0xca44  brtrue.s loc_CA2C
0xca46  leave.s  loc_CA5D
0xca48  ldloc.s  9
0xca4a  isinst   [mscorlib]System.IDisposable
0xca4f  stloc.s  8
0xca51  ldloc.s  8
0xca53  brfalse.s loc_CA5C
0xca55  ldloc.s  8
0xca57  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca5c  endfinally
0xca5d  ret
```
