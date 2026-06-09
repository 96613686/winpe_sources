# System.Windows.Xps.VisualsToXpsDocument::EndBatchWrite

- ea: `0xcce0`
- end: `0xce66`
- name: `System.Windows.Xps.VisualsToXpsDocument::EndBatchWrite`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xc350`
- `0xcce0`
- `0xd680`
- `0xd700`
- `0x107f0`

## string_xrefs

- `0xce5b`: `XpsWriter.WriteNotCalledEndBatchWrite`

## pseudocode

```c

```

## disassembly

```asm
0xcce0  ldarg.0
0xcce1  call     instance void System.Windows.Xps.VisualsToXpsDocument::VerifyAccess()
0xcce6  ldarg.0
0xcce7  ldfld    class System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.VisualsToXpsDocument::parentWriter
0xccec  call     instance void System.Windows.Xps.XpsDocumentWriter::EndBatchMode()
0xccf1  ldarg.0
0xccf2  ldc.i4.3
0xccf3  stfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xccf8  ldarg.0
0xccf9  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xccfe  stloc.1
0xccff  ldloc.1
0xcd00  brfalse  loc_CE5B
0xcd05  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xcd0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcd0f  ldloc.1
0xcd10  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcd15  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcd1a  brfalse.s loc_CD2E
0xcd1c  ldarg.0
0xcd1d  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd22  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xcd27  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::Commit()
0xcd2c  br.s     loc_CD88
0xcd2e  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xcd33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcd38  ldarg.0
0xcd39  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd3e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcd43  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcd48  brfalse.s loc_CD5C
0xcd4a  ldarg.0
0xcd4b  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd50  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xcd55  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync::Commit()
0xcd5a  br.s     loc_CD88
0xcd5c  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xcd61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcd66  ldarg.0
0xcd67  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd6c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcd71  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcd76  brfalse.s loc_CD88
0xcd78  ldarg.0
0xcd79  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd7e  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xcd83  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync::Commit()
0xcd88  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xcd8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcd92  ldarg.0
0xcd93  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcd98  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcd9d  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcda2  brfalse.s loc_CDB6
0xcda4  ldarg.0
0xcda5  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcdaa  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xcdaf  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::Commit()
0xcdb4  br.s     loc_CE10
0xcdb6  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xcdbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcdc0  ldarg.0
0xcdc1  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcdc6  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcdcb  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcdd0  brfalse.s loc_CDE4
0xcdd2  ldarg.0
0xcdd3  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcdd8  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xcddd  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::Commit()
0xcde2  br.s     loc_CE10
0xcde4  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xcde9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcdee  ldarg.0
0xcdef  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xcdf4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xcdf9  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xcdfe  brfalse.s loc_CE10
0xce00  ldarg.0
0xce01  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xce06  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xce0b  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager::Commit()
0xce10  ldarg.0
0xce11  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xce16  stloc.0
0xce17  ldloc.0
0xce18  brfalse.s loc_CE22
0xce1a  ldloc.0
0xce1b  call     instance void System.Printing.PrintQueue::DisposeSerializationManager()
0xce20  br.s     loc_CE65
0xce22  ldarg.0
0xce23  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.VisualsToXpsDocument::destinationDocument
0xce28  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::DisposeSerializationManager()
0xce2d  ldarg.0
0xce2e  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.VisualsToXpsDocument::_mxdwManager
0xce33  brfalse.s loc_CE65
0xce35  ldarg.0
0xce36  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.VisualsToXpsDocument::_mxdwPackage
0xce3b  call     instance void [WindowsBase]System.IO.Packaging.Package::Close()
0xce40  ldarg.0
0xce41  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.VisualsToXpsDocument::_mxdwManager
0xce46  call     instance void [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager::Commit()
0xce4b  ldarg.0
0xce4c  ldnull
0xce4d  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.VisualsToXpsDocument::_mxdwPackage
0xce52  ldarg.0
0xce53  ldnull
0xce54  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.VisualsToXpsDocument::_mxdwManager
0xce59  br.s     loc_CE65
0xce5b  ldstr    aXpswriterWrite_0// "XpsWriter.WriteNotCalledEndBatchWrite"
0xce60  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xce65  ret
```
