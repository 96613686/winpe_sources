# Microsoft.ReportingServices.Diagnostics.Task::GetIntElementValue

- ea: `0xe4e0`
- end: `0xe508`
- name: `Microsoft.ReportingServices.Diagnostics.Task::GetIntElementValue`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xdf70`
- `0xdfd0`
- `0xe030`

## callees

- `0xe4e0`

## pseudocode

```c

```

## disassembly

```asm
0xe4e0  ldc.i4.0
0xe4e1  stloc.0
0xe4e2  ldarg.1
0xe4e3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe4e8  stloc.1
0xe4e9  ldarg.1
0xe4ea  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xe4ef  stloc.2
0xe4f0  ldloc.2
0xe4f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe4f6  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xe4fb  stloc.0
0xe4fc  leave.s  loc_E506
0xe4fe  pop
0xe4ff  ldloc.1
0xe500  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xe505  throw
0xe506  ldloc.0
0xe507  ret
```
