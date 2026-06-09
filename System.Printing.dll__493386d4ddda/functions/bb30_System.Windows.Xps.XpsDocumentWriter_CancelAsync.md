# System.Windows.Xps.XpsDocumentWriter::CancelAsync

- ea: `0xbb30`
- end: `0xbc14`
- name: `System.Windows.Xps.XpsDocumentWriter::CancelAsync`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xbb30`
- `0xcae0`
- `0xd700`

## string_xrefs

- `0xbbfd`: `XPSWriter.BatchMode`
- `0xbc09`: `XPSWriter.WriteNotCalled`
- `0xbb5d`: `XPSWriter.Cancelled`

## pseudocode

```c

```

## disassembly

```asm
0xbb30  ldarg.0
0xbb31  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xbb36  ldarg.0
0xbb37  ldfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbb3c  stloc.0
0xbb3d  ldloca.s 0
0xbb3f  ldind.i4
0xbb40  brfalse  loc_BC09
0xbb45  ldloca.s 0
0xbb47  ldind.i4
0xbb48  ldc.i4.1
0xbb49  beq      loc_BBFD
0xbb4e  ldloca.s 0
0xbb50  ldind.i4
0xbb51  ldc.i4.2
0xbb52  beq.s    loc_BB6C
0xbb54  ldloca.s 0
0xbb56  ldind.i4
0xbb57  ldc.i4.3
0xbb58  bne.un   loc_BC13
0xbb5d  ldstr    aXpswriterCance// "XPSWriter.Cancelled"
0xbb62  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbb67  br       loc_BC13
0xbb6c  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xbb71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbb76  ldarg.0
0xbb77  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbb7c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbb81  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xbb86  brfalse.s loc_BB9A
0xbb88  ldarg.0
0xbb89  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbb8e  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xbb93  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync::CancelAsync()
0xbb98  br.s     loc_BBF4
0xbb9a  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xbb9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbba4  ldarg.0
0xbba5  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbbaa  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbbaf  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xbbb4  brfalse.s loc_BBC8
0xbbb6  ldarg.0
0xbbb7  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbbbc  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xbbc1  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync::CancelAsync()
0xbbc6  br.s     loc_BBF4
0xbbc8  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xbbcd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbbd2  ldarg.0
0xbbd3  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbbd8  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbbdd  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xbbe2  brfalse.s loc_BBF4
0xbbe4  ldarg.0
0xbbe5  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xbbea  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xbbef  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::CancelAsync()
0xbbf4  ldarg.0
0xbbf5  ldc.i4.3
0xbbf6  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbbfb  br.s     loc_BC13
0xbbfd  ldstr    aXpswriterBatch// "XPSWriter.BatchMode"
0xbc02  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbc07  br.s     loc_BC13
0xbc09  ldstr    aXpswriterWrite// "XPSWriter.WriteNotCalled"
0xbc0e  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbc13  ret
```
