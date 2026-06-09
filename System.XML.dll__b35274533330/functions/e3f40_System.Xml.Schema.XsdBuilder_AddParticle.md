# System.Xml.Schema.XsdBuilder::AddParticle

- ea: `0xe3f40`
- end: `0xe40a1`
- name: `System.Xml.Schema.XsdBuilder::AddParticle`
- size: `353`
- prototype: ``
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xe3710`
- `0xe3780`
- `0xe37b0`
- `0xe37e0`
- `0xe3810`

## callees

- `0xd1590`
- `0xd15a0`
- `0xd15b0`
- `0xd15c0`
- `0xd1650`
- `0xd1660`
- `0xd1670`
- `0xd1680`
- `0xd1990`
- `0xd19b0`
- `0xd19c0`
- `0xd19d0`
- `0xd19f0`
- `0xd3560`
- `0xd3570`
- `0xd36a0`
- `0xd3f00`
- `0xe2300`
- `0xe2330`
- `0xe3f40`
- `0xe4340`

## string_xrefs

- `0xe3fb1`: `complexType`
- `0xe3fac`: `Sch_ComplexTypeContentModel`
- `0xe3ff5`: `Sch_ComplexContentContentModel`
- `0xe403e`: `Sch_ComplexContentContentModel`
- `0xe3ffa`: `ComplexContentExtension`
- `0xe4043`: `ComplexContentExtension`

## pseudocode

```c

```

## disassembly

```asm
0xe3f40  ldarg.0
0xe3f41  call     instance valuetype Token System.Xml.Schema.XsdBuilder::get_ParentElement()
0xe3f46  stloc.0
0xe3f47  ldloc.0
0xe3f48  ldc.i4.s 0x55
0xe3f4a  bgt.s    loc_E3F5F
0xe3f4c  ldloc.0
0xe3f4d  ldc.i4.s 0x52
0xe3f4f  beq      loc_E405A
0xe3f54  ldloc.0
0xe3f55  ldc.i4.s 0x54
0xe3f57  sub
0xe3f58  ldc.i4.1
0xe3f59  ble.un   loc_E4089
0xe3f5e  ret
0xe3f5f  ldloc.0
0xe3f60  ldc.i4.s 0x59
0xe3f62  beq.s    loc_E3F72
0xe3f64  ldloc.0
0xe3f65  ldc.i4.s 0x6D
0xe3f67  beq.s    loc_E3FC8
0xe3f69  ldloc.0
0xe3f6a  ldc.i4.s 0x6E
0xe3f6c  beq      loc_E4011
0xe3f71  ret
0xe3f72  ldarg.0
0xe3f73  ldfld    class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XsdBuilder::complexType
0xe3f78  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0xe3f7d  brtrue.s loc_E3FAB
0xe3f7f  ldarg.0
0xe3f80  ldfld    class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XsdBuilder::complexType
0xe3f85  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0xe3f8a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe3f8f  brtrue.s loc_E3FAB
0xe3f91  ldarg.0
0xe3f92  ldfld    class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XsdBuilder::complexType
0xe3f97  callvirt instance class System.Xml.Schema.XmlSchemaAnyAttribute System.Xml.Schema.XmlSchemaComplexType::get_AnyAttribute()
0xe3f9c  brtrue.s loc_E3FAB
0xe3f9e  ldarg.0
0xe3f9f  ldfld    class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XsdBuilder::complexType
0xe3fa4  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0xe3fa9  brfalse.s loc_E3FBB
0xe3fab  ldarg.0
0xe3fac  ldstr    aSchComplextype_1// "Sch_ComplexTypeContentModel"
0xe3fb1  ldstr    aComplextype// "complexType"
0xe3fb6  call     instance void System.Xml.Schema.XsdBuilder::SendValidationEvent(string code, string msg)
0xe3fbb  ldarg.0
0xe3fbc  ldfld    class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XsdBuilder::complexType
0xe3fc1  ldarg.1
0xe3fc2  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0xe3fc7  ret
0xe3fc8  ldarg.0
0xe3fc9  ldfld    class System.Xml.Schema.XmlSchemaComplexContentExtension System.Xml.Schema.XsdBuilder::complexContentExtension
0xe3fce  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0xe3fd3  brtrue.s loc_E3FF4
0xe3fd5  ldarg.0
0xe3fd6  ldfld    class System.Xml.Schema.XmlSchemaComplexContentExtension System.Xml.Schema.XsdBuilder::complexContentExtension
0xe3fdb  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentExtension::get_Attributes()
0xe3fe0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe3fe5  brtrue.s loc_E3FF4
0xe3fe7  ldarg.0
0xe3fe8  ldfld    class System.Xml.Schema.XmlSchemaComplexContentExtension System.Xml.Schema.XsdBuilder::complexContentExtension
0xe3fed  callvirt instance class System.Xml.Schema.XmlSchemaAnyAttribute System.Xml.Schema.XmlSchemaComplexContentExtension::get_AnyAttribute()
0xe3ff2  brfalse.s loc_E4004
0xe3ff4  ldarg.0
0xe3ff5  ldstr    aSchComplexcont_0// "Sch_ComplexContentContentModel"
0xe3ffa  ldstr    aComplexcontent_0// "ComplexContentExtension"
0xe3fff  call     instance void System.Xml.Schema.XsdBuilder::SendValidationEvent(string code, string msg)
0xe4004  ldarg.0
0xe4005  ldfld    class System.Xml.Schema.XmlSchemaComplexContentExtension System.Xml.Schema.XsdBuilder::complexContentExtension
0xe400a  ldarg.1
0xe400b  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0xe4010  ret
0xe4011  ldarg.0
0xe4012  ldfld    class System.Xml.Schema.XmlSchemaComplexContentRestriction System.Xml.Schema.XsdBuilder::complexContentRestriction
0xe4017  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Particle()
0xe401c  brtrue.s loc_E403D
0xe401e  ldarg.0
0xe401f  ldfld    class System.Xml.Schema.XmlSchemaComplexContentRestriction System.Xml.Schema.XsdBuilder::complexContentRestriction
0xe4024  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0xe4029  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe402e  brtrue.s loc_E403D
0xe4030  ldarg.0
0xe4031  ldfld    class System.Xml.Schema.XmlSchemaComplexContentRestriction System.Xml.Schema.XsdBuilder::complexContentRestriction
0xe4036  callvirt instance class System.Xml.Schema.XmlSchemaAnyAttribute System.Xml.Schema.XmlSchemaComplexContentRestriction::get_AnyAttribute()
0xe403b  brfalse.s loc_E404D
0xe403d  ldarg.0
0xe403e  ldstr    aSchComplexcont_0// "Sch_ComplexContentContentModel"
0xe4043  ldstr    aComplexcontent_0// "ComplexContentExtension"
0xe4048  call     instance void System.Xml.Schema.XsdBuilder::SendValidationEvent(string code, string msg)
0xe404d  ldarg.0
0xe404e  ldfld    class System.Xml.Schema.XmlSchemaComplexContentRestriction System.Xml.Schema.XsdBuilder::complexContentRestriction
0xe4053  ldarg.1
0xe4054  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentRestriction::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0xe4059  ret
0xe405a  ldarg.0
0xe405b  ldfld    class System.Xml.Schema.XmlSchemaGroup System.Xml.Schema.XsdBuilder::group
0xe4060  callvirt instance class System.Xml.Schema.XmlSchemaGroupBase System.Xml.Schema.XmlSchemaGroup::get_Particle()
0xe4065  brfalse.s loc_E4077
0xe4067  ldarg.0
0xe4068  ldstr    aSchDupgrouppar// "Sch_DupGroupParticle"
0xe406d  ldstr    aParticle// "particle"
0xe4072  call     instance void System.Xml.Schema.XsdBuilder::SendValidationEvent(string code, string msg)
0xe4077  ldarg.0
0xe4078  ldfld    class System.Xml.Schema.XmlSchemaGroup System.Xml.Schema.XsdBuilder::group
0xe407d  ldarg.1
0xe407e  castclass System.Xml.Schema.XmlSchemaGroupBase
0xe4083  callvirt instance void System.Xml.Schema.XmlSchemaGroup::set_Particle(class System.Xml.Schema.XmlSchemaGroupBase value)
0xe4088  ret
0xe4089  ldarg.0
0xe408a  call     instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XsdBuilder::get_ParentContainer()
0xe408f  castclass System.Xml.Schema.XmlSchemaGroupBase
0xe4094  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0xe4099  ldarg.1
0xe409a  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xe409f  pop
0xe40a0  ret
```
