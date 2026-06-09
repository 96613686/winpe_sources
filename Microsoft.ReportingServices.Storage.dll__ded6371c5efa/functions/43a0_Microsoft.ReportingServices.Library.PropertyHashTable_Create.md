# Microsoft.ReportingServices.Library.PropertyHashTable::Create

- ea: `0x43a0`
- end: `0x43cc`
- name: `Microsoft.ReportingServices.Library.PropertyHashTable::Create`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4400`
- `0x4660`

## callees

- `0x43a0`

## pseudocode

```c

```

## disassembly

```asm
0x43a0  ldarg.0
0x43a1  ldlen
0x43a2  conv.i4
0x43a3  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x43a8  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32, class [mscorlib]System.Collections.IEqualityComparer)
0x43ad  stloc.0
0x43ae  ldarg.0
0x43af  stloc.1
0x43b0  ldc.i4.0
0x43b1  stloc.2
0x43b2  br.s     loc_43C4
0x43b4  ldloc.1
0x43b5  ldloc.2
0x43b6  ldelem.ref
0x43b7  stloc.3
0x43b8  ldloc.0
0x43b9  ldloc.3
0x43ba  ldloc.3
0x43bb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x43c0  ldloc.2
0x43c1  ldc.i4.1
0x43c2  add
0x43c3  stloc.2
0x43c4  ldloc.2
0x43c5  ldloc.1
0x43c6  ldlen
0x43c7  conv.i4
0x43c8  blt.s    loc_43B4
0x43ca  ldloc.0
0x43cb  ret
```
