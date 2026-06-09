# System.Windows.Xps.VisualsToXpsDocument::CancelAsync

- ea: `0xcf30`
- end: `0xd006`
- name: `System.Windows.Xps.VisualsToXpsDocument::CancelAsync`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xcf30`
- `0xd680`
- `0xd700`

## string_xrefs

- `0xcf5b`: `XPSWriter.BatchDoneWriting`
- `0xcffb`: `XPSWriter.BatchSync`

## pseudocode

```c

```

## disassembly

```asm
0xcf30  ldarg.0
0xcf31  call     instance void System.Windows.Xps.VisualsToXpsDocument::VerifyAccess()
0xcf36  ldarg.0
0xcf37  ldfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xcf3c  stloc.0
0xcf3d  ldloca.s 0
0xcf3f  ldind.i4
0xcf40  ldc.i4.1
0xcf41  beq      loc_CFFB
0xcf46  ldloca.s 0
0xcf48  ldind.i4
0xcf49  ldc.i4.2
0xcf4a  beq.s    loc_CF6A
0xcf4c  ldloca.s 0
0xcf4e  ldind.i4
0xcf4f  ldc.i4.3
0xcf50  beq.s    loc_CF5B
0xcf52  ldloca.s 0
0xcf54  ldind.i4
0xcf55  ldc.i4.4
0xcf56  bne.un   loc_D005
0xcf5b  ldstr    aXpswriterBatch_0// "XPSWriter.BatchDoneWriting"
0xcf60  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xcf65  br       loc_D005
0xcf6a  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xcf6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcf74  ldarg.0
0xcf75  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcf7a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcf7f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcf84  brfalse.s loc_CF98
0xcf86  ldarg.0
0xcf87  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcf8c  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xcf91  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync::CancelAsync()
0xcf96  br.s     loc_CFF2
0xcf98  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xcf9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcfa2  ldarg.0
0xcfa3  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcfa8  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcfad  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcfb2  brfalse.s loc_CFC6
0xcfb4  ldarg.0
0xcfb5  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcfba  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xcfbf  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync::CancelAsync()
0xcfc4  br.s     loc_CFF2
0xcfc6  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xcfcb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcfd0  ldarg.0
0xcfd1  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcfd6  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcfdb  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcfe0  brfalse.s loc_CFF2
0xcfe2  ldarg.0
0xcfe3  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcfe8  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xcfed  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::CancelAsync()
0xcff2  ldarg.0
0xcff3  ldc.i4.4
0xcff4  stfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xcff9  br.s     loc_D005
0xcffb  ldstr    aXpswriterBatch_1// "XPSWriter.BatchSync"
0xd000  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd005  ret
```
