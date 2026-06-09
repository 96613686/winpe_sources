# System.Windows.Xps.VisualsToXpsDocument::Cancel

- ea: `0xd010`
- end: `0xd09d`
- name: `System.Windows.Xps.VisualsToXpsDocument::Cancel`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xd010`
- `0xd680`
- `0xd700`

## string_xrefs

- `0xd035`: `XPSWriter.BatchDoneWriting`
- `0xd041`: `XPSWriter.BatchSync`

## pseudocode

```c

```

## disassembly

```asm
0xd010  ldarg.0
0xd011  call     instance void System.Windows.Xps.VisualsToXpsDocument::VerifyAccess()
0xd016  ldarg.0
0xd017  ldfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd01c  stloc.0
0xd01d  ldloca.s 0
0xd01f  ldind.i4
0xd020  ldc.i4.1
0xd021  beq.s    loc_D04D
0xd023  ldloca.s 0
0xd025  ldind.i4
0xd026  ldc.i4.2
0xd027  beq.s    loc_D041
0xd029  ldloca.s 0
0xd02b  ldind.i4
0xd02c  ldc.i4.3
0xd02d  beq.s    loc_D035
0xd02f  ldloca.s 0
0xd031  ldind.i4
0xd032  ldc.i4.4
0xd033  bne.un.s loc_D09C
0xd035  ldstr    aXpswriterBatch_0// "XPSWriter.BatchDoneWriting"
0xd03a  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd03f  br.s     loc_D09C
0xd041  ldstr    aXpswriterBatch_1// "XPSWriter.BatchSync"
0xd046  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd04b  br.s     loc_D09C
0xd04d  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xd052  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd057  ldarg.0
0xd058  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd05d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd062  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xd067  brtrue.s loc_D095
0xd069  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xd06e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd073  ldarg.0
0xd074  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd079  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd07e  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xd083  brfalse.s loc_D095
0xd085  ldarg.0
0xd086  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd08b  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xd090  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager::Cancel()
0xd095  ldarg.0
0xd096  ldc.i4.4
0xd097  stfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd09c  ret
```
