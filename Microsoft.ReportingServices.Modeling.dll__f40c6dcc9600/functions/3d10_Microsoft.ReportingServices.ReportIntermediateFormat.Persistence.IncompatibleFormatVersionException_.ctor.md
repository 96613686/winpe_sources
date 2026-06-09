# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IncompatibleFormatVersionException::.ctor

- ea: `0x3d10`
- end: `0x3d59`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IncompatibleFormatVersionException::.ctor`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3cc0`

## string_xrefs

- `0x3d19`: `The Intermediate Format Version is incompatible. The ObjectType read, at stream position `

## pseudocode

```c

```

## disassembly

```asm
0x3d10  ldarg.0
0x3d11  ldc.i4.5
0x3d12  newarr   [mscorlib]System.String
0x3d17  dup
0x3d18  ldc.i4.0
0x3d19  ldstr    aTheIntermediat// "The Intermediate Format Version is inco"...
0x3d1e  stelem.ref
0x3d1f  dup
0x3d20  ldc.i4.1
0x3d21  ldarga.s 2
0x3d23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d28  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x3d2d  stelem.ref
0x3d2e  dup
0x3d2f  ldc.i4.2
0x3d30  ldstr    aIs// ", is "
0x3d35  stelem.ref
0x3d36  dup
0x3d37  ldc.i4.3
0x3d38  ldarga.s 1
0x3d3a  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType
0x3d40  callvirt instance string [mscorlib]System.Object::ToString()
0x3d45  stelem.ref
0x3d46  dup
0x3d47  ldc.i4.4
0x3d48  ldstr    asc_3C5F2// "."
0x3d4d  stelem.ref
0x3d4e  call     string [mscorlib]System.String::Concat(string[])
0x3d53  call     instance void [mscorlib]System.Exception::.ctor(string)
0x3d58  ret
```
