# Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::CreateTraceInternal

- ea: `0x11600`
- end: `0x11681`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::CreateTraceInternal`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x116a0`

## callees

- `0x6130`
- `0x10140`
- `0x10150`
- `0x11600`
- `0x11880`
- `0x118b0`
- `0x16650`

## pseudocode

```c

```

## disassembly

```asm
0x11600  ldnull
0x11601  stloc.0
0x11602  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x11607  callvirt instance class [mscorlib]System.AppDomainManager [mscorlib]System.AppDomain::get_DomainManager()
0x1160c  brfalse.s loc_11636
0x1160e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x11613  callvirt instance class [mscorlib]System.AppDomainManager [mscorlib]System.AppDomain::get_DomainManager()
0x11618  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1161d  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x11622  call     string Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_RsAppDomainManagerTypeName()
0x11627  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1162c  brfalse.s loc_11636
0x1162e  newobj   instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSServiceTraceInternal::.ctor()
0x11633  stloc.0
0x11634  br.s     loc_11676
0x11636  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x1163b  brfalse.s loc_11676
0x1163d  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x11642  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x11647  ldc.i4.1
0x11648  beq.s    loc_11670
0x1164a  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x1164f  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x11654  brfalse.s loc_11670
0x11656  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x1165b  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x11660  ldc.i4.4
0x11661  beq.s    loc_11670
0x11663  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x11668  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x1166d  ldc.i4.5
0x1166e  bne.un.s loc_11676
0x11670  newobj   instance void RSWPTraceInternal::.ctor()
0x11675  stloc.0
0x11676  ldloc.0
0x11677  brtrue.s loc_1167F
0x11679  newobj   instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::.ctor()
0x1167e  stloc.0
0x1167f  ldloc.0
0x11680  ret
```
