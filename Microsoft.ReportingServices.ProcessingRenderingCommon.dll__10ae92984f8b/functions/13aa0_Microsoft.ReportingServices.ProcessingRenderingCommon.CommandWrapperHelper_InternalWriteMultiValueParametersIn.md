# Microsoft.ReportingServices.ProcessingRenderingCommon.CommandWrapperHelper::InternalWriteMultiValueParametersIntoCommandText

- ea: `0x13aa0`
- end: `0x13dc6`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.CommandWrapperHelper::InternalWriteMultiValueParametersIntoCommandText`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x13a70`

## callees

- `0x13aa0`
- `0x13dd0`
- `0x14060`

## string_xrefs

- `0x13d03`: `Query rewrite (removed parameter): `
- `0x13d88`: `Query rewrite (original query): `
- `0x13da3`: `Query rewrite (rewritten query): `

## pseudocode

```c

```

## disassembly

```asm
0x13aa0  ldc.i4.0
0x13aa1  ldarg.2
0x13aa2  blt.s    loc_13AAB
0x13aa4  ldarg.0
0x13aa5  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x13aaa  ret
0x13aab  ldnull
0x13aac  stloc.0
0x13aad  ldc.i4.s 0x1D
0x13aaf  stloc.1
0x13ab0  ldstr    asc_238FA// "-+()#,:&*/\\^<=>"
0x13ab5  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x13aba  stloc.2
0x13abb  ldstr    asc_2391A// "(["
0x13ac0  ldloc.2
0x13ac1  ldstr    aS// "\\s])"
0x13ac6  call     string [mscorlib]System.String::Concat(string, string, string)
0x13acb  stloc.3
0x13acc  ldstr    asc_2391A// "(["
0x13ad1  ldloc.2
0x13ad2  ldstr    aS_0// "\\s]|$)"
0x13ad7  call     string [mscorlib]System.String::Concat(string, string, string)
0x13adc  stloc.s  4
0x13ade  ldc.i4.4
0x13adf  ldarg.0
0x13ae0  callvirt instance valuetype [System.Data]System.Data.CommandType [System.Data]System.Data.IDbCommand::get_CommandType()
0x13ae5  ceq
0x13ae7  stloc.s  5
0x13ae9  ldloc.s  5
0x13aeb  brtrue.s loc_13AF9
0x13aed  ldarg.0
0x13aee  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x13af3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x13af8  stloc.0
0x13af9  ldc.i4.0
0x13afa  stloc.s  6
0x13afc  ldarg.1
0x13afd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter>::GetEnumerator()
0x13b02  stloc.s  7
0x13b04  br       loc_13D58
0x13b09  ldloc.s  7
0x13b0b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter>::get_Current()
0x13b10  stloc.s  8
0x13b12  ldloc.s  8
0x13b14  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter
0x13b19  stloc.s  9
0x13b1b  ldloc.s  9
0x13b1d  ldarg.3
0x13b1e  call     bool Microsoft.ReportingServices.ProcessingRenderingCommon.HelperExtension::ShouldMakeExpandable(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter mvParameter, valuetype Microsoft.ReportingServices.ProcessingRenderingCommon.ServerType serverType)
0x13b23  brfalse.s loc_13B41
0x13b25  ldc.i4.1
0x13b26  newarr   [mscorlib]System.Object
0x13b2b  stloc.s  0xA
0x13b2d  ldloc.s  0xA
0x13b2f  ldc.i4.0
0x13b30  ldloc.s  9
0x13b32  callvirt instance object [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_Value()
0x13b37  stelem.ref
0x13b38  ldloc.s  9
0x13b3a  ldloc.s  0xA
0x13b3c  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::set_Values(object[])
0x13b41  ldloc.s  9
0x13b43  brfalse  loc_13D2D
0x13b48  ldloc.s  9
0x13b4a  callvirt instance object[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::get_Values()
0x13b4f  brfalse  loc_13D2D
0x13b54  ldloc.s  9
0x13b56  callvirt instance object[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::get_Values()
0x13b5b  brfalse  loc_13D2D
0x13b60  ldloc.s  9
0x13b62  callvirt instance object[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::get_Values()
0x13b67  ldlen
0x13b68  brfalse  loc_13D2D
0x13b6d  ldloc.s  9
0x13b6f  ldloc.s  5
0x13b71  ldarg.3
0x13b72  call     string Microsoft.ReportingServices.ProcessingRenderingCommon.CommandWrapperHelper::GenerateStringFromMultiValue(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter parameter, bool isStoredProcedure, valuetype Microsoft.ReportingServices.ProcessingRenderingCommon.ServerType serverType)
0x13b77  stloc.s  0xB
0x13b79  ldloc.s  5
0x13b7b  brfalse.s loc_13B8B
0x13b7d  ldloc.s  8
0x13b7f  ldloc.s  0xB
0x13b81  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::set_Value(object)
0x13b86  br       loc_13D58
0x13b8b  ldstr    aParametername// "(?<ParameterName>"
0x13b90  ldloc.s  9
0x13b92  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13b97  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x13b9c  ldstr    asc_2395C// ")"
0x13ba1  call     string [mscorlib]System.String::Concat(string, string, string)
0x13ba6  stloc.s  0xC
0x13ba8  ldloc.3
0x13ba9  ldloc.s  0xC
0x13bab  ldloc.s  4
0x13bad  call     string [mscorlib]System.String::Concat(string, string, string)
0x13bb2  ldloc.1
0x13bb3  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x13bb8  ldloc.0
0x13bb9  callvirt instance string [mscorlib]System.Object::ToString()
0x13bbe  callvirt instance class [System]System.Text.RegularExpressions.MatchCollection [System]System.Text.RegularExpressions.Regex::Matches(string)
0x13bc3  stloc.s  0xD
0x13bc5  ldloc.s  0xD
0x13bc7  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x13bcc  ldc.i4.0
0x13bcd  ble      loc_13CF1
0x13bd2  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x13bd7  ldloc.s  9
0x13bd9  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13bde  ldstr    asc_1F4F6// "?"
0x13be3  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0x13be8  brtrue.s loc_13C5D
0x13bea  ldloc.s  6
0x13bec  ldloc.s  0xD
0x13bee  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x13bf3  bge      loc_13CF1
0x13bf8  ldloc.s  0xD
0x13bfa  ldloc.s  6
0x13bfc  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13c01  ldstr    aParametername_0// "${ParameterName}"
0x13c06  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x13c0b  stloc.s  0xE
0x13c0d  ldloc.s  0xE
0x13c0f  brfalse  loc_13CF1
0x13c14  ldc.i4.1
0x13c15  ldloc.s  0xE
0x13c17  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13c1c  bne.un   loc_13CF1
0x13c21  ldloc.0
0x13c22  ldloc.s  0xD
0x13c24  ldloc.s  6
0x13c26  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13c2b  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x13c30  ldc.i4.1
0x13c31  add
0x13c32  ldloc.s  0xE
0x13c34  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13c39  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x13c3e  pop
0x13c3f  ldloc.0
0x13c40  ldloc.s  0xD
0x13c42  ldloc.s  6
0x13c44  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13c49  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x13c4e  ldc.i4.1
0x13c4f  add
0x13c50  ldloc.s  0xB
0x13c52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x13c57  pop
0x13c58  br       loc_13CF1
0x13c5d  ldloc.s  0xD
0x13c5f  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x13c64  ldc.i4.1
0x13c65  sub
0x13c66  stloc.s  0xF
0x13c68  br.s     loc_13CE9
0x13c6a  ldloc.s  0xD
0x13c6c  ldloc.s  0xF
0x13c6e  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13c73  ldstr    aParametername_0// "${ParameterName}"
0x13c78  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x13c7d  stloc.s  0x10
0x13c7f  ldloc.s  0x10
0x13c81  brfalse.s loc_13CE3
0x13c83  ldc.i4.1
0x13c84  ldloc.s  0x10
0x13c86  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13c8b  bge.s    loc_13CE3
0x13c8d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13c92  ldloc.s  0x10
0x13c94  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13c99  ldloc.s  9
0x13c9b  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13ca0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13ca5  ceq
0x13ca7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x13cac  ldloc.0
0x13cad  ldloc.s  0xD
0x13caf  ldloc.s  0xF
0x13cb1  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13cb6  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x13cbb  ldc.i4.1
0x13cbc  add
0x13cbd  ldloc.s  0x10
0x13cbf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13cc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x13cc9  pop
0x13cca  ldloc.0
0x13ccb  ldloc.s  0xD
0x13ccd  ldloc.s  0xF
0x13ccf  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x13cd4  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x13cd9  ldc.i4.1
0x13cda  add
0x13cdb  ldloc.s  0xB
0x13cdd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x13ce2  pop
0x13ce3  ldloc.s  0xF
0x13ce5  ldc.i4.1
0x13ce6  sub
0x13ce7  stloc.s  0xF
0x13ce9  ldloc.s  0xF
0x13ceb  ldc.i4.0
0x13cec  bge      loc_13C6A
0x13cf1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13cf6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x13cfb  brfalse.s loc_13D19
0x13cfd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13d02  ldc.i4.4
0x13d03  ldstr    aQueryRewriteRe// "Query rewrite (removed parameter): "
0x13d08  ldloc.s  9
0x13d0a  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13d0f  call     string [mscorlib]System.String::Concat(string, string)
0x13d14  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13d19  ldarg.0
0x13d1a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x13d1f  ldloc.s  9
0x13d21  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13d26  callvirt instance void [System.Data]System.Data.IDataParameterCollection::RemoveAt(string)
0x13d2b  br.s     loc_13D58
0x13d2d  ldloc.s  9
0x13d2f  brfalse.s loc_13D58
0x13d31  ldloc.s  9
0x13d33  callvirt instance object[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataMultiValueParameter::get_Values()
0x13d38  brtrue.s loc_13D58
0x13d3a  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x13d3f  ldloc.s  9
0x13d41  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataParameter::get_ParameterName()
0x13d46  ldstr    asc_1F4F6// "?"
0x13d4b  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0x13d50  brtrue.s loc_13D58
0x13d52  ldloc.s  6
0x13d54  ldc.i4.1
0x13d55  add
0x13d56  stloc.s  6
0x13d58  ldloc.s  7
0x13d5a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13d5f  brtrue   loc_13B09
0x13d64  leave.s  loc_13D72
0x13d66  ldloc.s  7
0x13d68  brfalse.s loc_13D71
0x13d6a  ldloc.s  7
0x13d6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d71  endfinally
0x13d72  ldloc.s  5
0x13d74  brtrue.s loc_13DBF
0x13d76  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13d7b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x13d80  brfalse.s loc_13DB8
0x13d82  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13d87  ldc.i4.4
0x13d88  ldstr    aQueryRewriteOr// "Query rewrite (original query): "
0x13d8d  ldarg.0
0x13d8e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x13d93  call     string [mscorlib]System.String::Concat(string, string)
0x13d98  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13d9d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x13da2  ldc.i4.4
0x13da3  ldstr    aQueryRewriteRe_0// "Query rewrite (rewritten query): "
0x13da8  ldloc.0
0x13da9  callvirt instance string [mscorlib]System.Object::ToString()
0x13dae  call     string [mscorlib]System.String::Concat(string, string)
0x13db3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x13db8  ldloc.0
0x13db9  callvirt instance string [mscorlib]System.Object::ToString()
0x13dbe  ret
0x13dbf  ldarg.0
0x13dc0  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x13dc5  ret
```
