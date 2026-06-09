# System.Windows.Xps.XpsDocumentWriter::MxdwConversionRequired

- ea: `0xca20`
- end: `0xca4d`
- name: `System.Windows.Xps.XpsDocumentWriter::MxdwConversionRequired`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xc6e0`

## callees

- `0xca20`
- `0x103d0`

## pseudocode

```c

```

## disassembly

```asm
0xca20  ldarg.1
0xca21  call     bool System.Printing.PrintQueue::IsMxdwLegacyDriver([hasfieldmarshal] class System.Printing.PrintQueue value)
0xca26  stloc.0
0xca27  ldloc.0
0xca28  brfalse.s loc_CA4B
0xca2a  ldarg.1
0xca2b  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager::.ctor(class [System.Printing]System.Printing.PrintQueue)
0xca30  stloc.1
0xca31  ldarg.0
0xca32  ldloc.1
0xca33  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xca38  ldloc.1
0xca39  call     instance bool [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager::get_IsPassThruSupported()
0xca3e  stloc.0
0xca3f  ldloc.0
0xca40  brtrue.s loc_CA4B
0xca42  ldc.i4.0
0xca43  stloc.0
0xca44  ldarg.0
0xca45  ldnull
0xca46  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xca4b  ldloc.0
0xca4c  ret
```
