# System.Xaml.XamlObjectWriter::Logic_ConvertPositionalParamsToArgs

- ea: `0x3e90`
- end: `0x3fd1`
- name: `System.Xaml.XamlObjectWriter::Logic_ConvertPositionalParamsToArgs`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x33d0`

## callees

- `0x10`
- `0x3e90`
- `0x40b0`
- `0x8590`
- `0x8750`
- `0xd070`
- `0xd150`
- `0xd310`
- `0xd680`
- `0x11f20`
- `0x12d80`
- `0x12da0`
- `0x21200`
- `0x215d0`
- `0x21750`
- `0x21b90`

## pseudocode

```c

```

## disassembly

```asm
0x3e90  ldarg.1
0x3e91  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3e96  stloc.0
0x3e97  ldloc.0
0x3e98  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x3e9d  brtrue.s loc_3EB5
0x3e9f  ldarg.1
0x3ea0  ldstr    aNonmewithposit// "NonMEWithPositionalParameters"
0x3ea5  call     string System.Xaml.SR::Get(string id)
0x3eaa  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x3eaf  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3eb4  throw
0x3eb5  ldarg.1
0x3eb6  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCollection()
0x3ebb  castclass class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>
0x3ec0  stloc.1
0x3ec1  ldloc.1
0x3ec2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Count()
0x3ec7  newarr   [mscorlib]System.Object
0x3ecc  stloc.2
0x3ecd  ldloc.0
0x3ece  ldloc.1
0x3ecf  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Count()
0x3ed4  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType> System.Xaml.XamlType::GetPositionalParameters(int32 parameterCount)
0x3ed9  stloc.3
0x3eda  ldloc.3
0x3edb  brtrue.s loc_3F1E
0x3edd  call     class [mscorlib]System.Globalization.CultureInfo System.Xaml.TypeConverterHelper::get_InvariantEnglishUS()
0x3ee2  ldstr    aNosuchconstruc// "NoSuchConstructor"
0x3ee7  call     string System.Xaml.SR::Get(string id)
0x3eec  ldc.i4.2
0x3eed  newarr   [mscorlib]System.Object
0x3ef2  dup
0x3ef3  ldc.i4.0
0x3ef4  ldloc.1
0x3ef5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Count()
0x3efa  box      [mscorlib]System.Int32
0x3eff  stelem.ref
0x3f00  dup
0x3f01  ldc.i4.1
0x3f02  ldloc.0
0x3f03  callvirt instance string System.Xaml.XamlType::get_Name()
0x3f08  stelem.ref
0x3f09  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f0e  stloc.s  5
0x3f10  ldarg.1
0x3f11  ldloc.s  5
0x3f13  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3f18  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3f1d  throw
0x3f1e  ldc.i4.0
0x3f1f  stloc.s  4
0x3f21  ldloc.3
0x3f22  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.XamlType>::GetEnumerator()
0x3f27  stloc.s  6
0x3f29  br       loc_3FB6
0x3f2e  ldloc.s  6
0x3f30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.XamlType>::get_Current()
0x3f35  stloc.s  7
0x3f37  ldloc.s  4
0x3f39  ldloc.1
0x3f3a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Count()
0x3f3f  bge.s    loc_3F99
0x3f41  ldloc.1
0x3f42  ldloc.s  4
0x3f44  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Item(!!T0)
0x3f49  stloc.s  9
0x3f4b  ldloc.s  9
0x3f4d  callvirt instance bool System.Xaml.MS.Impl.PositionalParameterDescriptor::get_WasText()
0x3f52  brfalse.s loc_3F7D
0x3f54  ldloc.s  7
0x3f56  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x3f5b  stloc.s  0xA
0x3f5d  ldloc.s  9
0x3f5f  callvirt instance object System.Xaml.MS.Impl.PositionalParameterDescriptor::get_Value()
0x3f64  stloc.s  0xB
0x3f66  ldarg.0
0x3f67  ldarg.1
0x3f68  ldloc.s  0xA
0x3f6a  ldloc.s  0xB
0x3f6c  ldnull
0x3f6d  ldloc.s  7
0x3f6f  callvirt instance string System.Xaml.XamlType::get_Name()
0x3f74  call     instance object System.Xaml.XamlObjectWriter::Logic_CreateFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> typeConverter, object value, class System.Xaml.XamlMember property, string targetName)
0x3f79  stloc.s  8
0x3f7b  br.s     loc_3F8C
0x3f7d  ldloc.1
0x3f7e  ldloc.s  4
0x3f80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::get_Item(!!T0)
0x3f85  callvirt instance object System.Xaml.MS.Impl.PositionalParameterDescriptor::get_Value()
0x3f8a  stloc.s  8
0x3f8c  ldloc.2
0x3f8d  ldloc.s  4
0x3f8f  dup
0x3f90  ldc.i4.1
0x3f91  add
0x3f92  stloc.s  4
0x3f94  ldloc.s  8
0x3f96  stelem.ref
0x3f97  br.s     loc_3FAF
0x3f99  ldarg.1
0x3f9a  ldstr    aPositionalpara// "PositionalParamsWrongLength"
0x3f9f  call     string System.Xaml.SR::Get(string id)
0x3fa4  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x3fa9  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3fae  throw
0x3faf  ldarg.1
0x3fb0  ldloc.2
0x3fb1  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCtorArgs(object[] value)
0x3fb6  ldloc.s  6
0x3fb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3fbd  brtrue   loc_3F2E
0x3fc2  leave.s  loc_3FD0
0x3fc4  ldloc.s  6
0x3fc6  brfalse.s loc_3FCF
0x3fc8  ldloc.s  6
0x3fca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3fcf  endfinally
0x3fd0  ret
```
