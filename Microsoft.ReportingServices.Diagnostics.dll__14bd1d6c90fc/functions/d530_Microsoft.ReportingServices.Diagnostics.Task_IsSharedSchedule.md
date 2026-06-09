# Microsoft.ReportingServices.Diagnostics.Task::IsSharedSchedule

- ea: `0xd530`
- end: `0xd562`
- name: `Microsoft.ReportingServices.Diagnostics.Task::IsSharedSchedule`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd570`
- `0xd5a0`
- `0xd6d0`

## callees

- `0xd530`

## pseudocode

```c

```

## disassembly

```asm
0xd530  ldarg.0
0xd531  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd536  pop
0xd537  ldc.i4.1
0xd538  stloc.0
0xd539  leave.s  loc_D560
0xd53b  stloc.1
0xd53c  ldloc.1
0xd53d  isinst   [mscorlib]System.ArgumentException
0xd542  brtrue.s loc_D557
0xd544  ldloc.1
0xd545  isinst   [mscorlib]System.FormatException
0xd54a  brtrue.s loc_D557
0xd54c  ldloc.1
0xd54d  isinst   [mscorlib]System.OverflowException
0xd552  ldnull
0xd553  cgt.un
0xd555  br.s     loc_D558
0xd557  ldc.i4.1
0xd558  brtrue.s loc_D55C
0xd55a  rethrow
0xd55c  leave.s  loc_D55E
0xd55e  ldc.i4.0
0xd55f  ret
0xd560  ldloc.0
0xd561  ret
```
