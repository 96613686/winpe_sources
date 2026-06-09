# System.Windows.Xps.Serialization.FontTypeConverter::ConvertTo

- ea: `0x3ae80`
- end: `0x3af46`
- name: `System.Windows.Xps.Serialization.FontTypeConverter::ConvertTo`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x1efa0`
- `0x30640`
- `0x35890`
- `0x3a620`
- `0x3ae80`
- `0x3af60`
- `0x3b600`

## string_xrefs

- `0x3af17`: `ReachSerialization_NoFontService`

## pseudocode

```c

```

## disassembly

```asm
0x3ae80  ldarg.1
0x3ae81  brtrue.s loc_3AE8E
0x3ae83  ldstr    aContext// "context"
0x3ae88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3ae8d  throw
0x3ae8e  ldc.i4   0x13B4
0x3ae93  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x3ae98  ldarg.s  4
0x3ae9a  call     bool System.Windows.Xps.Serialization.FontTypeConverter::IsSupportedType(class [mscorlib]System.Type type)
0x3ae9f  brtrue.s loc_3AEB1
0x3aea1  ldstr    aConverterConve_0// "Converter_ConvertToNotSupported"
0x3aea6  call     string System.Windows.Xps.SR::Get(string id)
0x3aeab  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x3aeb0  throw
0x3aeb1  ldarg.1
0x3aeb2  ldtoken  System.Windows.Xps.Serialization.XpsSerializationManager
0x3aeb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3aebc  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3aec1  castclass System.Windows.Xps.Serialization.PackageSerializationManager
0x3aec6  stloc.0
0x3aec7  ldarg.3
0x3aec8  castclass [PresentationCore]System.Windows.Media.GlyphRun
0x3aecd  stloc.1
0x3aece  ldloc.1
0x3aecf  brtrue.s loc_3AEF7
0x3aed1  ldstr    aMustbeoftype// "MustBeOfType"
0x3aed6  ldc.i4.2
0x3aed7  newarr   [mscorlib]System.Object
0x3aedc  dup
0x3aedd  ldc.i4.0
0x3aede  ldstr    aValue// "value"
0x3aee3  stelem.ref
0x3aee4  dup
0x3aee5  ldc.i4.1
0x3aee6  ldstr    aGlyphrun_0// "GlyphRun"
0x3aeeb  stelem.ref
0x3aeec  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x3aef1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3aef6  throw
0x3aef7  ldloc.0
0x3aef8  callvirt instance class System.Windows.Xps.Packaging.XpsResourcePolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_ResourcePolicy()
0x3aefd  stloc.2
0x3aefe  ldloc.2
0x3aeff  ldtoken  System.Windows.Xps.Serialization.XpsFontSerializationService
0x3af04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3af09  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3af0e  castclass System.Windows.Xps.Serialization.XpsFontSerializationService
0x3af13  stloc.3
0x3af14  ldloc.3
0x3af15  brtrue.s loc_3AF27
0x3af17  ldstr    aReachserializa_21// "ReachSerialization_NoFontService"
0x3af1c  call     string System.Windows.Xps.SR::Get(string id)
0x3af21  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x3af26  throw
0x3af27  ldloc.3
0x3af28  callvirt instance class System.Windows.Xps.Serialization.XpsFontSubsetter System.Windows.Xps.Serialization.XpsFontSerializationService::get_FontSubsetter()
0x3af2d  stloc.s  4
0x3af2f  ldloc.s  4
0x3af31  ldloc.1
0x3af32  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.XpsFontSubsetter::ComputeFontSubset(class [PresentationCore]System.Windows.Media.GlyphRun glyphRun)
0x3af37  stloc.s  5
0x3af39  ldc.i4   0x13B5
0x3af3e  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x3af43  ldloc.s  5
0x3af45  ret
```
