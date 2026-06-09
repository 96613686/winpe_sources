# System.Windows.Markup.ValueSerializer::GetSerializerFor_0

- ea: `0x1b7c0`
- end: `0x1b855`
- name: `System.Windows.Markup.ValueSerializer::GetSerializerFor_0`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1b880`
- `0x2c340`

## callees

- `0x1b6a0`
- `0x1b7c0`
- `0x27790`

## string_xrefs

- `0x1b7c3`: `descriptor`

## pseudocode

```c

```

## disassembly

```asm
0x1b7c0  ldarg.0
0x1b7c1  brtrue.s loc_1B7CE
0x1b7c3  ldstr    aDescriptor// "descriptor"
0x1b7c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b7cd  throw
0x1b7ce  ldarg.0
0x1b7cf  callvirt instance class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.MemberDescriptor::get_Attributes()
0x1b7d4  ldtoken  [System]System.Windows.Markup.ValueSerializerAttribute
0x1b7d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7de  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0x1b7e3  isinst   [System]System.Windows.Markup.ValueSerializerAttribute
0x1b7e8  stloc.1
0x1b7e9  ldloc.1
0x1b7ea  brfalse.s loc_1B7FF
0x1b7ec  ldloc.1
0x1b7ed  callvirt instance class [mscorlib]System.Type [System]System.Windows.Markup.ValueSerializerAttribute::get_ValueSerializerType()
0x1b7f2  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x1b7f7  castclass System.Windows.Markup.ValueSerializer
0x1b7fc  stloc.0
0x1b7fd  br.s     loc_1B853
0x1b7ff  ldarg.0
0x1b800  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x1b805  call     class System.Windows.Markup.ValueSerializer System.Windows.Markup.ValueSerializer::GetSerializerFor(class [mscorlib]System.Type type)
0x1b80a  stloc.0
0x1b80b  ldloc.0
0x1b80c  brfalse.s loc_1B816
0x1b80e  ldloc.0
0x1b80f  isinst   MS.Internal.Serialization.TypeConverterValueSerializer
0x1b814  brfalse.s loc_1B853
0x1b816  ldarg.0
0x1b817  callvirt instance class [System]System.ComponentModel.TypeConverter [System]System.ComponentModel.PropertyDescriptor::get_Converter()
0x1b81c  stloc.2
0x1b81d  ldloc.2
0x1b81e  brfalse.s loc_1B853
0x1b820  ldloc.2
0x1b821  ldtoken  [mscorlib]System.String
0x1b826  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b82b  callvirt instance bool [System]System.ComponentModel.TypeConverter::CanConvertTo(class [mscorlib]System.Type)
0x1b830  brfalse.s loc_1B853
0x1b832  ldloc.2
0x1b833  ldtoken  [mscorlib]System.String
0x1b838  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b83d  callvirt instance bool [System]System.ComponentModel.TypeConverter::CanConvertFrom(class [mscorlib]System.Type)
0x1b842  brfalse.s loc_1B853
0x1b844  ldloc.2
0x1b845  isinst   [System]System.ComponentModel.ReferenceConverter
0x1b84a  brtrue.s loc_1B853
0x1b84c  ldloc.2
0x1b84d  newobj   instance void MS.Internal.Serialization.TypeConverterValueSerializer::.ctor(class [System]System.ComponentModel.TypeConverter converter)
0x1b852  stloc.0
0x1b853  ldloc.0
0x1b854  ret
```
