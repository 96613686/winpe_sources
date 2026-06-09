# Microsoft.ReportingServices.Diagnostics.Dumper::ContainsExceptedException

- ea: `0x9980`
- end: `0x99b3`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::ContainsExceptedException`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x95f0`
- `0x9980`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.0
0x9981  brtrue.s loc_9985
0x9983  ldc.i4.0
0x9984  ret
0x9985  ldarg.0
0x9986  stloc.0
0x9987  call     class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToNotDump()
0x998c  ldloc.0
0x998d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x9992  callvirt instance string [mscorlib]System.Object::ToString()
0x9997  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x999c  brfalse.s loc_99A0
0x999e  ldc.i4.1
0x999f  ret
0x99a0  ldloc.0
0x99a1  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x99a6  brfalse.s loc_99B1
0x99a8  ldloc.0
0x99a9  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x99ae  stloc.0
0x99af  br.s     loc_9987
0x99b1  ldc.i4.0
0x99b2  ret
```
