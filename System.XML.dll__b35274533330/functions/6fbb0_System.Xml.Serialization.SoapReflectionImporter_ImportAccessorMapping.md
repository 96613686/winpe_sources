# System.Xml.Serialization.SoapReflectionImporter::ImportAccessorMapping

- ea: `0x6fbb0`
- end: `0x6fde6`
- name: `System.Xml.Serialization.SoapReflectionImporter::ImportAccessorMapping`
- size: `566`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `registry_config`

## callers

- `0x6fa80`
- `0x6fb30`

## callees

- `0xf5b0`
- `0x622f0`
- `0x62370`
- `0x68610`
- `0x68630`
- `0x68680`
- `0x686e0`
- `0x68700`
- `0x68790`
- `0x688a0`
- `0x688c0`
- `0x68970`
- `0x68b30`
- `0x69620`
- `0x69630`
- `0x69650`
- `0x69670`
- `0x6a6b0`
- `0x6add0`
- `0x6ade0`
- `0x6adf0`
- `0x6dbe0`
- `0x6dc10`
- `0x6dc30`
- `0x6de70`
- `0x6df10`
- `0x6df30`
- `0x6e750`
- `0x6e780`
- `0x6e7b0`
- `0x6ebb0`
- `0x6fbb0`
- `0x6fe20`
- `0x72b90`
- `0x72d90`
- `0x72e20`
- `0x72e30`
- `0x73d90`

## string_xrefs

- `0x6fbdd`: `XmlInvalidVoid`
- `0x6fc17`: `XmlIllegalSoapAttribute`
- `0x6fc45`: `XmlInvalidElementAttribute`
- `0x6fd20`: `XmlInvalidElementAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x6fbb0  ldarg.2
0x6fbb1  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.FieldModel::get_FieldType()
0x6fbb6  stloc.0
0x6fbb7  ldarg.2
0x6fbb8  callvirt instance string System.Xml.Serialization.FieldModel::get_Name()
0x6fbbd  stloc.1
0x6fbbe  ldarg.1
0x6fbbf  ldarg.0
0x6fbc0  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.SoapReflectionImporter::typeScope
0x6fbc5  ldloc.0
0x6fbc6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(class [mscorlib]System.Type type)
0x6fbcb  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x6fbd0  ldarg.1
0x6fbd1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x6fbd6  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsVoid()
0x6fbdb  brfalse.s loc_6FBED
0x6fbdd  ldstr    aXmlinvalidvoid// "XmlInvalidVoid"
0x6fbe2  call     string System.Xml.Res::GetString(string name)
0x6fbe7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6fbec  throw
0x6fbed  ldarg.3
0x6fbee  callvirt instance valuetype System.Xml.Serialization.SoapAttributeFlags System.Xml.Serialization.SoapAttributes::get_SoapFlags()
0x6fbf3  stloc.2
0x6fbf4  ldloc.2
0x6fbf5  ldc.i4.8
0x6fbf6  and
0x6fbf7  ldc.i4.8
0x6fbf8  bne.un   loc_6FD1A
0x6fbfd  ldarg.1
0x6fbfe  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x6fc03  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x6fc08  brtrue.s loc_6FC3F
0x6fc0a  ldarg.1
0x6fc0b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x6fc10  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnum()
0x6fc15  brtrue.s loc_6FC3F
0x6fc17  ldstr    aXmlillegalsoap// "XmlIllegalSoapAttribute"
0x6fc1c  ldc.i4.2
0x6fc1d  newarr   [mscorlib]System.Object
0x6fc22  dup
0x6fc23  ldc.i4.0
0x6fc24  ldloc.1
0x6fc25  stelem.ref
0x6fc26  dup
0x6fc27  ldc.i4.1
0x6fc28  ldarg.1
0x6fc29  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x6fc2e  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6fc33  stelem.ref
0x6fc34  call     string System.Xml.Res::GetString(string name, object[] args)
0x6fc39  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6fc3e  throw
0x6fc3f  ldloc.2
0x6fc40  ldc.i4.8
0x6fc41  and
0x6fc42  ldloc.2
0x6fc43  beq.s    loc_6FC55
0x6fc45  ldstr    aXmlinvalidelem// "XmlInvalidElementAttribute"
0x6fc4a  call     string System.Xml.Res::GetString(string name)
0x6fc4f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6fc54  throw
0x6fc55  newobj   instance void System.Xml.Serialization.AttributeAccessor::.ctor()
0x6fc5a  stloc.3
0x6fc5b  ldloc.3
0x6fc5c  ldarg.3
0x6fc5d  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fc62  brfalse.s loc_6FC83
0x6fc64  ldarg.3
0x6fc65  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fc6a  callvirt instance string System.Xml.Serialization.SoapAttributeAttribute::get_AttributeName()
0x6fc6f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6fc74  brfalse.s loc_6FC83
0x6fc76  ldarg.3
0x6fc77  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fc7c  callvirt instance string System.Xml.Serialization.SoapAttributeAttribute::get_AttributeName()
0x6fc81  br.s     loc_6FC84
0x6fc83  ldloc.1
0x6fc84  call     string System.Xml.Serialization.Accessor::EscapeQName(string name)
0x6fc89  callvirt instance void System.Xml.Serialization.Accessor::set_Name(string value)
0x6fc8e  ldloc.3
0x6fc8f  ldarg.3
0x6fc90  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fc95  brfalse.s loc_6FCB1
0x6fc97  ldarg.3
0x6fc98  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fc9d  callvirt instance string System.Xml.Serialization.SoapAttributeAttribute::get_Namespace()
0x6fca2  brfalse.s loc_6FCB1
0x6fca4  ldarg.3
0x6fca5  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fcaa  callvirt instance string System.Xml.Serialization.SoapAttributeAttribute::get_Namespace()
0x6fcaf  br.s     loc_6FCB3
0x6fcb1  ldarg.s  4
0x6fcb3  callvirt instance void System.Xml.Serialization.Accessor::set_Namespace(string value)
0x6fcb8  ldloc.3
0x6fcb9  ldc.i4.1
0x6fcba  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x6fcbf  ldloc.3
0x6fcc0  ldarg.0
0x6fcc1  ldarg.0
0x6fcc2  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.SoapReflectionImporter::modelScope
0x6fcc7  ldloc.0
0x6fcc8  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x6fccd  ldarg.3
0x6fcce  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fcd3  brfalse.s loc_6FCE2
0x6fcd5  ldarg.3
0x6fcd6  callvirt instance class System.Xml.Serialization.SoapAttributeAttribute System.Xml.Serialization.SoapAttributes::get_SoapAttribute()
0x6fcdb  callvirt instance string System.Xml.Serialization.SoapAttributeAttribute::get_DataType()
0x6fce0  br.s     loc_6FCE7
0x6fce2  ldsfld   string [mscorlib]System.String::Empty
0x6fce7  ldarg.s  6
0x6fce9  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapReflectionImporter::ImportTypeMapping(class System.Xml.Serialization.TypeModel model, string dataType, class System.Xml.Serialization.RecursionLimiter limiter)
0x6fcee  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0x6fcf3  ldloc.3
0x6fcf4  ldarg.0
0x6fcf5  ldarg.2
0x6fcf6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.FieldModel::get_FieldTypeDesc()
0x6fcfb  ldarg.3
0x6fcfc  call     instance object System.Xml.Serialization.SoapReflectionImporter::GetDefaultValue(class System.Xml.Serialization.TypeDesc fieldTypeDesc, class System.Xml.Serialization.SoapAttributes a)
0x6fd01  callvirt instance void System.Xml.Serialization.Accessor::set_Default(object value)
0x6fd06  ldarg.1
0x6fd07  ldloc.3
0x6fd08  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Attribute(class System.Xml.Serialization.AttributeAccessor value)
0x6fd0d  ldarg.1
0x6fd0e  ldc.i4.0
0x6fd0f  newarr   System.Xml.Serialization.ElementAccessor
0x6fd14  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x6fd19  ret
0x6fd1a  ldloc.2
0x6fd1b  ldc.i4.4
0x6fd1c  and
0x6fd1d  ldloc.2
0x6fd1e  beq.s    loc_6FD30
0x6fd20  ldstr    aXmlinvalidelem// "XmlInvalidElementAttribute"
0x6fd25  call     string System.Xml.Res::GetString(string name)
0x6fd2a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6fd2f  throw
0x6fd30  newobj   instance void System.Xml.Serialization.ElementAccessor::.ctor()
0x6fd35  stloc.s  4
0x6fd37  ldloc.s  4
0x6fd39  ldc.i4.1
0x6fd3a  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsSoap(bool value)
0x6fd3f  ldloc.s  4
0x6fd41  ldarg.3
0x6fd42  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fd47  brfalse.s loc_6FD68
0x6fd49  ldarg.3
0x6fd4a  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fd4f  callvirt instance string System.Xml.Serialization.SoapElementAttribute::get_ElementName()
0x6fd54  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6fd59  brfalse.s loc_6FD68
0x6fd5b  ldarg.3
0x6fd5c  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fd61  callvirt instance string System.Xml.Serialization.SoapElementAttribute::get_ElementName()
0x6fd66  br.s     loc_6FD69
0x6fd68  ldloc.1
0x6fd69  call     string System.Xml.XmlConvert::EncodeLocalName(string name)
0x6fd6e  callvirt instance void System.Xml.Serialization.Accessor::set_Name(string value)
0x6fd73  ldloc.s  4
0x6fd75  ldarg.s  4
0x6fd77  callvirt instance void System.Xml.Serialization.Accessor::set_Namespace(string value)
0x6fd7c  ldloc.s  4
0x6fd7e  ldarg.s  5
0x6fd80  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x6fd85  ldloc.s  4
0x6fd87  ldarg.0
0x6fd88  ldarg.0
0x6fd89  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.SoapReflectionImporter::modelScope
0x6fd8e  ldloc.0
0x6fd8f  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x6fd94  ldarg.3
0x6fd95  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fd9a  brfalse.s loc_6FDA9
0x6fd9c  ldarg.3
0x6fd9d  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fda2  callvirt instance string System.Xml.Serialization.SoapElementAttribute::get_DataType()
0x6fda7  br.s     loc_6FDAE
0x6fda9  ldsfld   string [mscorlib]System.String::Empty
0x6fdae  ldarg.s  6
0x6fdb0  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapReflectionImporter::ImportTypeMapping(class System.Xml.Serialization.TypeModel model, string dataType, class System.Xml.Serialization.RecursionLimiter limiter)
0x6fdb5  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0x6fdba  ldarg.3
0x6fdbb  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fdc0  brfalse.s loc_6FDD4
0x6fdc2  ldloc.s  4
0x6fdc4  ldarg.3
0x6fdc5  callvirt instance class System.Xml.Serialization.SoapElementAttribute System.Xml.Serialization.SoapAttributes::get_SoapElement()
0x6fdca  callvirt instance bool System.Xml.Serialization.SoapElementAttribute::get_IsNullable()
0x6fdcf  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsNullable(bool value)
0x6fdd4  ldarg.1
0x6fdd5  ldc.i4.1
0x6fdd6  newarr   System.Xml.Serialization.ElementAccessor
0x6fddb  dup
0x6fddc  ldc.i4.0
0x6fddd  ldloc.s  4
0x6fddf  stelem.ref
0x6fde0  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x6fde5  ret
```
