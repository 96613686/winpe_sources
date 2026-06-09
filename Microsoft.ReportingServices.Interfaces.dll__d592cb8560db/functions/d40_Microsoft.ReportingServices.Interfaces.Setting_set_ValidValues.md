# Microsoft.ReportingServices.Interfaces.Setting::set_ValidValues

- ea: `0xd40`
- end: `0xd5c`
- name: `Microsoft.ReportingServices.Interfaces.Setting::set_ValidValues`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldarg.1
0xd41  brtrue.s loc_D4F
0xd43  ldarg.0
0xd44  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xd49  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Interfaces.Setting::m_validValues
0xd4e  ret
0xd4f  ldarg.0
0xd50  ldarg.1
0xd51  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0xd56  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Interfaces.Setting::m_validValues
0xd5b  ret
```
