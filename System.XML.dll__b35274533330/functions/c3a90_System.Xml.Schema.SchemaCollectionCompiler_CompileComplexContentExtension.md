# System.Xml.Schema.SchemaCollectionCompiler::CompileComplexContentExtension

- ea: `0xc3a90`
- end: `0xc3bfd`
- name: `System.Xml.Schema.SchemaCollectionCompiler::CompileComplexContentExtension`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xc3520`

## callees

- `0x13410`
- `0xae930`
- `0xae940`
- `0xc3520`
- `0xc3a90`
- `0xc3d70`
- `0xc3dc0`
- `0xc4e70`
- `0xc5080`
- `0xc6350`
- `0xd1560`
- `0xd1590`
- `0xd15b0`
- `0xd15c0`
- `0xd1a10`
- `0xd1a20`
- `0xd1a90`
- `0xd36a0`
- `0xd3f00`
- `0xd46e0`
- `0xd6b30`
- `0xd6b40`
- `0xd6c80`
- `0xd6c90`
- `0xd6cb0`
- `0xd6cd0`
- `0xd6d00`

## string_xrefs

- `0xc3b21`: `Sch_BaseFinalExtension`
- `0xc3ad8`: `Sch_UndefBaseExtension`
- `0xc3b03`: `Sch_NotComplexContent`

## pseudocode

```c

```

## disassembly

```asm
0xc3a90  ldnull
0xc3a91  stloc.0
0xc3a92  ldarg.1
0xc3a93  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0xc3a98  brfalse.s loc_C3AC7
0xc3a9a  ldarg.3
0xc3a9b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaComplexContentExtension::get_BaseTypeName()
0xc3aa0  ldarg.1
0xc3aa1  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0xc3aa6  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc3aab  call     bool System.Xml.XmlQualifiedName::op_Equality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0xc3ab0  brfalse.s loc_C3AC7
0xc3ab2  ldarg.1
0xc3ab3  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0xc3ab8  castclass System.Xml.Schema.XmlSchemaComplexType
0xc3abd  stloc.0
0xc3abe  ldarg.0
0xc3abf  ldloc.0
0xc3ac0  call     instance void System.Xml.Schema.SchemaCollectionCompiler::CompileComplexType(class System.Xml.Schema.XmlSchemaComplexType complexType)
0xc3ac5  br.s     loc_C3AEF
0xc3ac7  ldarg.0
0xc3ac8  ldarg.3
0xc3ac9  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaComplexContentExtension::get_BaseTypeName()
0xc3ace  call     instance class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.SchemaCollectionCompiler::GetComplexType(class System.Xml.XmlQualifiedName name)
0xc3ad3  stloc.0
0xc3ad4  ldloc.0
0xc3ad5  brtrue.s loc_C3AEF
0xc3ad7  ldarg.0
0xc3ad8  ldstr    aSchUndefbaseex// "Sch_UndefBaseExtension"
0xc3add  ldarg.3
0xc3ade  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaComplexContentExtension::get_BaseTypeName()
0xc3ae3  callvirt instance string [mscorlib]System.Object::ToString()
0xc3ae8  ldarg.3
0xc3ae9  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, string msg, class System.Xml.Schema.XmlSchemaObject source)
0xc3aee  ret
0xc3aef  ldloc.0
0xc3af0  brfalse.s loc_C3B0F
0xc3af2  ldloc.0
0xc3af3  callvirt instance class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.XmlSchemaType::get_ElementDecl()
0xc3af8  brfalse.s loc_C3B0F
0xc3afa  ldloc.0
0xc3afb  callvirt instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.XmlSchemaComplexType::get_ContentType()
0xc3b00  brtrue.s loc_C3B0F
0xc3b02  ldarg.0
0xc3b03  ldstr    aSchNotcomplexc// "Sch_NotComplexContent"
0xc3b08  ldarg.1
0xc3b09  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc3b0e  ret
0xc3b0f  ldarg.1
0xc3b10  ldloc.0
0xc3b11  callvirt instance void System.Xml.Schema.XmlSchemaType::SetBaseSchemaType(class System.Xml.Schema.XmlSchemaType value)
0xc3b16  ldloc.0
0xc3b17  callvirt instance valuetype System.Xml.Schema.XmlSchemaDerivationMethod System.Xml.Schema.XmlSchemaType::get_FinalResolved()
0xc3b1c  ldc.i4.2
0xc3b1d  and
0xc3b1e  brfalse.s loc_C3B2C
0xc3b20  ldarg.0
0xc3b21  ldstr    aSchBasefinalex// "Sch_BaseFinalExtension"
0xc3b26  ldarg.1
0xc3b27  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc3b2c  ldarg.0
0xc3b2d  ldloc.0
0xc3b2e  ldarg.1
0xc3b2f  ldarg.3
0xc3b30  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentExtension::get_Attributes()
0xc3b35  ldarg.3
0xc3b36  callvirt instance class System.Xml.Schema.XmlSchemaAnyAttribute System.Xml.Schema.XmlSchemaComplexContentExtension::get_AnyAttribute()
0xc3b3b  ldc.i4.2
0xc3b3c  call     instance void System.Xml.Schema.SchemaCollectionCompiler::CompileLocalAttributes(class System.Xml.Schema.XmlSchemaComplexType baseType, class System.Xml.Schema.XmlSchemaComplexType derivedType, class System.Xml.Schema.XmlSchemaObjectCollection attributes, class System.Xml.Schema.XmlSchemaAnyAttribute anyAttribute, valuetype System.Xml.Schema.XmlSchemaDerivationMethod derivedBy)
0xc3b41  ldloc.0
0xc3b42  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_ContentTypeParticle()
0xc3b47  stloc.1
0xc3b48  ldarg.0
0xc3b49  ldarg.3
0xc3b4a  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0xc3b4f  ldc.i4.1
0xc3b50  ldc.i4.1
0xc3b51  call     instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.SchemaCollectionCompiler::CannonicalizeParticle(class System.Xml.Schema.XmlSchemaParticle particle, bool root, bool substitution)
0xc3b56  stloc.2
0xc3b57  ldloc.1
0xc3b58  ldsfld   class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaParticle::Empty
0xc3b5d  beq.s    loc_C3BDA
0xc3b5f  ldloc.2
0xc3b60  ldsfld   class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaParticle::Empty
0xc3b65  beq.s    loc_C3B9B
0xc3b67  newobj   instance void System.Xml.Schema.XmlSchemaSequence::.ctor()
0xc3b6c  stloc.s  4
0xc3b6e  ldloc.s  4
0xc3b70  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0xc3b75  ldloc.1
0xc3b76  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xc3b7b  pop
0xc3b7c  ldloc.s  4
0xc3b7e  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0xc3b83  ldloc.2
0xc3b84  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xc3b89  pop
0xc3b8a  ldarg.1
0xc3b8b  ldarg.0
0xc3b8c  ldloc.s  4
0xc3b8e  ldc.i4.0
0xc3b8f  call     instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.SchemaCollectionCompiler::CompileContentTypeParticle(class System.Xml.Schema.XmlSchemaParticle particle, bool substitution)
0xc3b94  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::SetContentTypeParticle(class System.Xml.Schema.XmlSchemaParticle value)
0xc3b99  br.s     loc_C3BA2
0xc3b9b  ldarg.1
0xc3b9c  ldloc.1
0xc3b9d  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::SetContentTypeParticle(class System.Xml.Schema.XmlSchemaParticle value)
0xc3ba2  ldarg.0
0xc3ba3  ldarg.1
0xc3ba4  ldarg.2
0xc3ba5  ldloc.2
0xc3ba6  call     instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.SchemaCollectionCompiler::GetSchemaContentType(class System.Xml.Schema.XmlSchemaComplexType complexType, class System.Xml.Schema.XmlSchemaComplexContent complexContent, class System.Xml.Schema.XmlSchemaParticle particle)
0xc3bab  stloc.3
0xc3bac  ldloc.3
0xc3bad  ldc.i4.1
0xc3bae  bne.un.s loc_C3BB7
0xc3bb0  ldloc.0
0xc3bb1  callvirt instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.XmlSchemaComplexType::get_ContentType()
0xc3bb6  stloc.3
0xc3bb7  ldarg.1
0xc3bb8  ldloc.3
0xc3bb9  callvirt instance void System.Xml.Schema.XmlSchemaType::SetContentType(valuetype System.Xml.Schema.XmlSchemaContentType value)
0xc3bbe  ldarg.1
0xc3bbf  callvirt instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.XmlSchemaComplexType::get_ContentType()
0xc3bc4  ldloc.0
0xc3bc5  callvirt instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.XmlSchemaComplexType::get_ContentType()
0xc3bca  beq.s    loc_C3BF5
0xc3bcc  ldarg.0
0xc3bcd  ldstr    aSchDifcontentt// "Sch_DifContentType"
0xc3bd2  ldarg.1
0xc3bd3  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc3bd8  br.s     loc_C3BF5
0xc3bda  ldarg.1
0xc3bdb  ldloc.2
0xc3bdc  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::SetContentTypeParticle(class System.Xml.Schema.XmlSchemaParticle value)
0xc3be1  ldarg.1
0xc3be2  ldarg.0
0xc3be3  ldarg.1
0xc3be4  ldarg.2
0xc3be5  ldarg.1
0xc3be6  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_ContentTypeParticle()
0xc3beb  call     instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.SchemaCollectionCompiler::GetSchemaContentType(class System.Xml.Schema.XmlSchemaComplexType complexType, class System.Xml.Schema.XmlSchemaComplexContent complexContent, class System.Xml.Schema.XmlSchemaParticle particle)
0xc3bf0  callvirt instance void System.Xml.Schema.XmlSchemaType::SetContentType(valuetype System.Xml.Schema.XmlSchemaContentType value)
0xc3bf5  ldarg.1
0xc3bf6  ldc.i4.2
0xc3bf7  callvirt instance void System.Xml.Schema.XmlSchemaType::SetDerivedBy(valuetype System.Xml.Schema.XmlSchemaDerivationMethod value)
0xc3bfc  ret
```
