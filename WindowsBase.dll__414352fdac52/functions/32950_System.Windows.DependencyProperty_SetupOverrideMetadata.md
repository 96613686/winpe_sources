# System.Windows.DependencyProperty::SetupOverrideMetadata

- ea: `0x32950`
- end: `0x32a19`
- name: `System.Windows.DependencyProperty::SetupOverrideMetadata`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x32a20`
- `0x32a60`

## callees

- `0x2c100`
- `0x2c130`
- `0x322f0`
- `0x323f0`
- `0x32830`
- `0x32950`
- `0x32c60`
- `0x32df0`
- `0x32e00`
- `0x32e30`
- `0x38940`
- `0x389f0`

## string_xrefs

- `0x3297a`: `TypeMetadataAlreadyInUse`

## pseudocode

```c

```

## disassembly

```asm
0x32950  ldarg.1
0x32951  ldnull
0x32952  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x32957  brfalse.s loc_32964
0x32959  ldstr    aFortype// "forType"
0x3295e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32963  throw
0x32964  ldarg.2
0x32965  brtrue.s loc_32972
0x32967  ldstr    aTypemetadata// "typeMetadata"
0x3296c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32971  throw
0x32972  ldarg.2
0x32973  callvirt instance bool System.Windows.PropertyMetadata::get_Sealed()
0x32978  brfalse.s loc_3298A
0x3297a  ldstr    aTypemetadataal// "TypeMetadataAlreadyInUse"
0x3297f  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x32984  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32989  throw
0x3298a  ldtoken  System.Windows.DependencyObject
0x3298f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32994  ldarg.1
0x32995  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x3299a  brtrue.s loc_329BB
0x3299c  ldstr    aTypemustbedepe// "TypeMustBeDependencyObjectDerived"
0x329a1  ldc.i4.1
0x329a2  newarr   [mscorlib]System.Object
0x329a7  dup
0x329a8  ldc.i4.0
0x329a9  ldarg.1
0x329aa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x329af  stelem.ref
0x329b0  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x329b5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x329ba  throw
0x329bb  ldarg.2
0x329bc  callvirt instance bool System.Windows.PropertyMetadata::get_IsDefaultValueModified()
0x329c1  brfalse.s loc_329DB
0x329c3  ldarg.2
0x329c4  ldarg.0
0x329c5  call     instance class [mscorlib]System.Type System.Windows.DependencyProperty::get_PropertyType()
0x329ca  ldarg.0
0x329cb  call     instance string System.Windows.DependencyProperty::get_Name()
0x329d0  ldarg.0
0x329d1  call     instance class System.Windows.ValidateValueCallback System.Windows.DependencyProperty::get_ValidateValueCallback()
0x329d6  call     void System.Windows.DependencyProperty::ValidateMetadataDefaultValue(class System.Windows.PropertyMetadata defaultMetadata, class [mscorlib]System.Type propertyType, string propertyName, class System.Windows.ValidateValueCallback validateValueCallback)
0x329db  ldarg.3
0x329dc  ldarg.1
0x329dd  call     class System.Windows.DependencyObjectType System.Windows.DependencyObjectType::FromSystemType(class [mscorlib]System.Type systemType)
0x329e2  stind.ref
0x329e3  ldarg.s  4
0x329e5  ldarg.0
0x329e6  ldarg.3
0x329e7  ldind.ref
0x329e8  callvirt instance class System.Windows.DependencyObjectType System.Windows.DependencyObjectType::get_BaseType()
0x329ed  call     instance class System.Windows.PropertyMetadata System.Windows.DependencyProperty::GetMetadata(class System.Windows.DependencyObjectType dependencyObjectType)
0x329f2  stind.ref
0x329f3  ldarg.s  4
0x329f5  ldind.ref
0x329f6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x329fb  ldarg.2
0x329fc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x32a01  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x32a06  brtrue.s loc_32A18
0x32a08  ldstr    aOverridingmeta// "OverridingMetadataDoesNotMatchBaseMetad"...
0x32a0d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x32a12  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32a17  throw
0x32a18  ret
```
