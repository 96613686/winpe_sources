# Microsoft.VisualStudio.Setup.CommandLine::.ctor

- ea: `0x1fb0`
- end: `0x1fed`
- name: `Microsoft.VisualStudio.Setup.CommandLine::.ctor`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5380`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  ldarg.0
0x1fb1  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::Empty
0x1fb6  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::<Args>k__BackingField
0x1fbb  ldarg.0
0x1fbc  ldc.i4.1
0x1fbd  stfld    bool Microsoft.VisualStudio.Setup.CommandLine::<CanCancel>k__BackingField
0x1fc2  ldarg.0
0x1fc3  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1fc8  stloc.0
0x1fc9  ldloca.s 0
0x1fcb  constrained. [mscorlib]System.Guid
0x1fd1  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd6  stfld    string Microsoft.VisualStudio.Setup.CommandLine::<ActivityId>k__BackingField
0x1fdb  ldarg.0
0x1fdc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1fe1  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CommandLine::<UnknownArguments>k__BackingField
0x1fe6  ldarg.0
0x1fe7  call     instance void [mscorlib]System.Object::.ctor()
0x1fec  ret
```
