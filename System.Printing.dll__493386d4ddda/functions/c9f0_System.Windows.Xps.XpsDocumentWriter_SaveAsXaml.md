# System.Windows.Xps.XpsDocumentWriter::SaveAsXaml

- ea: `0xc9f0`
- end: `0xca1c`
- name: `System.Windows.Xps.XpsDocumentWriter::SaveAsXaml`
- size: `44`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0xb4e0`
- `0xb510`
- `0xb530`
- `0xb560`
- `0xb580`
- `0xb5b0`
- `0xb5d0`
- `0xb600`
- `0xb620`
- `0xb650`

## callees

- `0xc660`
- `0xc970`
- `0xc9f0`

## pseudocode

```c

```

## disassembly

```asm
0xc9f0  ldc.i4.0
0xc9f1  stloc.0
0xc9f2  ldarg.0
0xc9f3  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc9f8  ldarg.1
0xc9f9  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xc9fe  leave.s  loc_CA10
0xca00  stloc.1
0xca01  ldc.i4.1
0xca02  stloc.0
0xca03  ldarg.0
0xca04  dup
0xca05  ldloc.1
0xca06  call     instance bool System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled([hasfieldmarshal] object value, class [mscorlib]System.Exception sender)
0xca0b  pop
0xca0c  leave.s  loc_CA0E
0xca0e  leave.s  loc_CA1B
0xca10  leave.s  loc_CA1B
0xca12  ldarg.0
0xca13  ldarg.2
0xca14  ldloc.0
0xca15  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager, [hasfieldmarshal] bool abort)
0xca1a  endfinally
0xca1b  ret
```
