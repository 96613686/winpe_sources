# Microsoft.ReportingServices.Diagnostics.Dumper::IsDumpException

- ea: `0x9920`
- end: `0x997b`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::IsDumpException`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x98d0`

## callees

- `0x95e0`
- `0x9920`
- `0x9980`

## pseudocode

```c

```

## disassembly

```asm
0x9920  ldc.i4.0
0x9921  stloc.0
0x9922  ldarg.0
0x9923  brtrue.s loc_9929
0x9925  ldc.i4.1
0x9926  stloc.0
0x9927  br.s     loc_9979
0x9929  ldarg.0
0x992a  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x992f  stloc.1
0x9930  ldloc.1
0x9931  brfalse.s loc_994E
0x9933  ldc.i4.s 0x6D
0x9935  ldloc.1
0x9936  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x993b  beq.s    loc_994A
0x993d  ldc.i4   0xB0
0x9942  ldloc.1
0x9943  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x9948  bne.un.s loc_9950
0x994a  ldc.i4.1
0x994b  stloc.0
0x994c  br.s     loc_9950
0x994e  ldc.i4.1
0x994f  stloc.0
0x9950  ldloc.0
0x9951  brtrue.s loc_996C
0x9953  call     class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToDump()
0x9958  ldarg.0
0x9959  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x995e  callvirt instance string [mscorlib]System.Object::ToString()
0x9963  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x9968  brfalse.s loc_996C
0x996a  ldc.i4.1
0x996b  stloc.0
0x996c  ldloc.0
0x996d  brfalse.s loc_9979
0x996f  ldarg.0
0x9970  call     bool Microsoft.ReportingServices.Diagnostics.Dumper::ContainsExceptedException(class [mscorlib]System.Exception root)
0x9975  brfalse.s loc_9979
0x9977  ldc.i4.0
0x9978  stloc.0
0x9979  ldloc.0
0x997a  ret
```
