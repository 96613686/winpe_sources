# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::SetReportParameters_1

- ea: `0xc340`
- end: `0xc3d3`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::SetReportParameters_1`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x78d0`
- `0xc320`
- `0xc340`
- `0xcc00`

## string_xrefs

- `0xc347`: `rs:StoredParametersID`

## pseudocode

```c

```

## disassembly

```asm
0xc340  ldarg.1
0xc341  brfalse  loc_C3CB
0xc346  ldarg.1
0xc347  ldstr    aRsStoredparame// "rs:StoredParametersID"
0xc34c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc351  stloc.0
0xc352  ldloc.0
0xc353  brfalse.s loc_C3CB
0xc355  ldarg.2
0xc356  ldloc.0
0xc357  ldloca.s 2
0xc359  ldloca.s 1
0xc35b  callvirt instance void Microsoft.ReportingServices.Diagnostics.IParametersTranslator::GetParamsInstance(string paramsInstanceId, [out] class Microsoft.ReportingServices.Diagnostics.ExternalItemPath& itemPath, [out] class [System]System.Collections.Specialized.NameValueCollection& parameters)
0xc360  ldloc.1
0xc361  brtrue.s loc_C36A
0xc363  ldloc.0
0xc364  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.StoredParameterNotFoundException::.ctor(string)
0xc369  throw
0xc36a  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xc36f  stloc.3
0xc370  ldloc.1
0xc371  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase::GetEnumerator()
0xc376  stloc.s  4
0xc378  br.s     loc_C3A3
0xc37a  ldloc.s  4
0xc37c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc381  castclass [mscorlib]System.String
0xc386  stloc.s  5
0xc388  ldloc.1
0xc389  ldloc.s  5
0xc38b  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xc390  stloc.s  6
0xc392  ldloc.s  5
0xc394  ldloc.s  6
0xc396  ldstr    asc_19000// ""
0xc39b  ldc.i4.1
0xc39c  ldloc.3
0xc39d  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection(string name, string[] val, string prefix, bool allowMultiValue, class [System]System.Collections.Specialized.NameValueCollection collection)
0xc3a2  pop
0xc3a3  ldloc.s  4
0xc3a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc3aa  brtrue.s loc_C37A
0xc3ac  leave.s  loc_C3C3
0xc3ae  ldloc.s  4
0xc3b0  isinst   [mscorlib]System.IDisposable
0xc3b5  stloc.s  7
0xc3b7  ldloc.s  7
0xc3b9  brfalse.s loc_C3C2
0xc3bb  ldloc.s  7
0xc3bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3c2  endfinally
0xc3c3  ldarg.0
0xc3c4  ldloc.3
0xc3c5  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_reportParameters
0xc3ca  ret
0xc3cb  ldarg.0
0xc3cc  ldarg.1
0xc3cd  call     instance void Microsoft.ReportingServices.Diagnostics.RSRequestParameters::SetReportParameters(class [System]System.Collections.Specialized.NameValueCollection allReportParameters)
0xc3d2  ret
```
