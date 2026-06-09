# System.Windows.DependencyProperty::ProcessOverrideMetadata

- ea: `0x32ad0`
- end: `0x32ba8`
- name: `System.Windows.DependencyProperty::ProcessOverrideMetadata`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x32a20`
- `0x32a60`

## callees

- `0x8d10`
- `0x8d30`
- `0x2c130`
- `0x323d0`
- `0x32ad0`
- `0x32e20`
- `0x38470`
- `0x384d0`
- `0x38690`
- `0x38900`
- `0x38930`
- `0x38950`

## string_xrefs

- `0x32b0c`: `TypeMetadataAlreadyRegistered`

## pseudocode

```c

```

## disassembly

```asm
0x32ad0  ldsfld   object System.Windows.DependencyProperty::Synchronized
0x32ad5  stloc.0
0x32ad6  ldc.i4.0
0x32ad7  stloc.1
0x32ad8  ldloc.0
0x32ad9  ldloca.s 1
0x32adb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x32ae0  ldsfld   object System.Windows.DependencyProperty::UnsetValue
0x32ae5  ldarg.0
0x32ae6  ldflda   valuetype MS.Utility.InsertionSortMap System.Windows.DependencyProperty::_metadataMap
0x32aeb  ldarg.3
0x32aec  callvirt instance int32 System.Windows.DependencyObjectType::get_Id()
0x32af1  call     instance object MS.Utility.InsertionSortMap::get_Item(int32 key)
0x32af6  bne.un.s loc_32B0C
0x32af8  ldarg.0
0x32af9  ldflda   valuetype MS.Utility.InsertionSortMap System.Windows.DependencyProperty::_metadataMap
0x32afe  ldarg.3
0x32aff  callvirt instance int32 System.Windows.DependencyObjectType::get_Id()
0x32b04  ldarg.2
0x32b05  call     instance void MS.Utility.InsertionSortMap::set_Item(int32 key, object value)
0x32b0a  leave.s  loc_32B35
0x32b0c  ldstr    aTypemetadataal_0// "TypeMetadataAlreadyRegistered"
0x32b11  ldc.i4.1
0x32b12  newarr   [mscorlib]System.Object
0x32b17  dup
0x32b18  ldc.i4.0
0x32b19  ldarg.1
0x32b1a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x32b1f  stelem.ref
0x32b20  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x32b25  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32b2a  throw
0x32b2b  ldloc.1
0x32b2c  brfalse.s loc_32B34
0x32b2e  ldloc.0
0x32b2f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x32b34  endfinally
0x32b35  ldarg.2
0x32b36  ldarg.s  4
0x32b38  ldarg.0
0x32b39  callvirt instance void System.Windows.PropertyMetadata::InvokeMerge(class System.Windows.PropertyMetadata baseMetadata, class System.Windows.DependencyProperty dp)
0x32b3e  ldarg.2
0x32b3f  ldarg.0
0x32b40  ldarg.1
0x32b41  callvirt instance void System.Windows.PropertyMetadata::Seal(class System.Windows.DependencyProperty dp, class [mscorlib]System.Type targetType)
0x32b46  ldarg.2
0x32b47  callvirt instance bool System.Windows.PropertyMetadata::get_IsInherited()
0x32b4c  brfalse.s loc_32B60
0x32b4e  ldarg.0
0x32b4f  ldarg.0
0x32b50  ldfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32b55  ldc.i4   0x80000
0x32b5a  or
0x32b5b  stfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32b60  ldarg.2
0x32b61  callvirt instance bool System.Windows.PropertyMetadata::DefaultValueWasSet()
0x32b66  brfalse.s loc_32B8D
0x32b68  ldarg.2
0x32b69  callvirt instance object System.Windows.PropertyMetadata::get_DefaultValue()
0x32b6e  ldarg.0
0x32b6f  call     instance class System.Windows.PropertyMetadata System.Windows.DependencyProperty::get_DefaultMetadata()
0x32b74  callvirt instance object System.Windows.PropertyMetadata::get_DefaultValue()
0x32b79  beq.s    loc_32B8D
0x32b7b  ldarg.0
0x32b7c  ldarg.0
0x32b7d  ldfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32b82  ldc.i4   0x100000
0x32b87  or
0x32b88  stfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32b8d  ldarg.2
0x32b8e  callvirt instance bool System.Windows.PropertyMetadata::get_UsingDefaultValueFactory()
0x32b93  brfalse.s loc_32BA7
0x32b95  ldarg.0
0x32b96  ldarg.0
0x32b97  ldfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32b9c  ldc.i4   0x200000
0x32ba1  or
0x32ba2  stfld    valuetype Flags System.Windows.DependencyProperty::_packedData
0x32ba7  ret
```
