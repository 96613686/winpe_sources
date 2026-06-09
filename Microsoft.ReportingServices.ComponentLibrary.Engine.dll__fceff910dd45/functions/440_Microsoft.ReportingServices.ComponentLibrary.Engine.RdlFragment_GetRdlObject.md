# Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::GetRdlObject

- ea: `0x440`
- end: `0x525`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::GetRdlObject`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c0`

## callees

- `0x440`
- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x440  ldarg.1
0x441  brtrue.s loc_44E
0x443  ldstr    aType// "type"
0x448  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x44d  throw
0x44e  ldarg.2
0x44f  brtrue.s loc_45C
0x451  ldstr    aName// "name"
0x456  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x45b  throw
0x45c  ldarg.0
0x45d  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::m_rdlObject
0x462  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report
0x467  stloc.0
0x468  ldloc.0
0x469  brfalse  loc_521
0x46e  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0x473  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x478  ldarg.1
0x479  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_RdlType()
0x47e  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x483  brfalse.s loc_4C6
0x485  ldloc.0
0x486  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_Body()
0x48b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body::get_ReportItems()
0x490  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::GetEnumerator()
0x495  stloc.1
0x496  br.s     loc_4B2
0x498  ldloc.1
0x499  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::get_Current()
0x49e  stloc.2
0x49f  ldarg.2
0x4a0  ldloc.2
0x4a1  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::get_Name()
0x4a6  ldc.i4.4
0x4a7  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4ac  brfalse.s loc_4B2
0x4ae  ldloc.2
0x4af  stloc.3
0x4b0  leave.s  loc_523
0x4b2  ldloc.1
0x4b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4b8  brtrue.s loc_498
0x4ba  leave.s  loc_521
0x4bc  ldloc.1
0x4bd  brfalse.s loc_4C5
0x4bf  ldloc.1
0x4c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c5  endfinally
0x4c6  ldarg.1
0x4c7  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_RdlType()
0x4cc  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0x4d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4db  brfalse.s loc_521
0x4dd  ldloc.0
0x4de  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_ReportParameters()
0x4e3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::GetEnumerator()
0x4e8  stloc.s  4
0x4ea  br.s     loc_50A
0x4ec  ldloc.s  4
0x4ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::get_Current()
0x4f3  stloc.s  5
0x4f5  ldarg.2
0x4f6  ldloc.s  5
0x4f8  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter::get_Name()
0x4fd  ldc.i4.4
0x4fe  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x503  brfalse.s loc_50A
0x505  ldloc.s  5
0x507  stloc.3
0x508  leave.s  loc_523
0x50a  ldloc.s  4
0x50c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x511  brtrue.s loc_4EC
0x513  leave.s  loc_521
0x515  ldloc.s  4
0x517  brfalse.s loc_520
0x519  ldloc.s  4
0x51b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x520  endfinally
0x521  ldnull
0x522  ret
0x523  ldloc.3
0x524  ret
```
