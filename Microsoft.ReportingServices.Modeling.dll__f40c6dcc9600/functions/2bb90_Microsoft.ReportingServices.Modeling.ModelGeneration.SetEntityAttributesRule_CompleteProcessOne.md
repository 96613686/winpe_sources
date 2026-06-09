# Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::CompleteProcessOne

- ea: `0x2bb90`
- end: `0x2bd88`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::CompleteProcessOne`
- size: `504`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bb40`
- `0x2bb90`

## callees

- `0x97d0`
- `0xbce0`
- `0x10760`
- `0x108c0`
- `0x11710`
- `0x11720`
- `0x11790`
- `0x117a0`
- `0x153d0`
- `0x153f0`
- `0x1ddf0`
- `0x1df20`
- `0x1ed00`
- `0x2b480`
- `0x2b9c0`
- `0x2bb90`
- `0x3a1a0`

## pseudocode

```c

```

## disassembly

```asm
0x2bb90  ldarg.0
0x2bb91  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_entityCandidateFields
0x2bb96  ldarg.1
0x2bb97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields>::get_Item(void)
0x2bb9c  stloc.0
0x2bb9d  ldloc.0
0x2bb9e  brtrue.s loc_2BBA1
0x2bba0  ret
0x2bba1  ldarg.0
0x2bba2  ldfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_processingEntities
0x2bba7  ldarg.1
0x2bba8  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity>::Push(var<u1>)
0x2bbad  ldarg.0
0x2bbae  ldarg.1
0x2bbaf  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::GetAttributesCollection(class Microsoft.ReportingServices.Modeling.ModelEntity entity)
0x2bbb4  stloc.1
0x2bbb5  ldloc.0
0x2bbb6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField> CandidateFields::get_Fields()
0x2bbbb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField>::GetEnumerator()
0x2bbc0  stloc.2
0x2bbc1  br       loc_2BD32
0x2bbc6  ldloc.2
0x2bbc7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ModelField>::get_Current()
0x2bbcc  stloc.3
0x2bbcd  ldloc.3
0x2bbce  isinst   Microsoft.ReportingServices.Modeling.ModelAttribute
0x2bbd3  stloc.s  4
0x2bbd5  ldloc.3
0x2bbd6  isinst   Microsoft.ReportingServices.Modeling.ModelRole
0x2bbdb  stloc.s  5
0x2bbdd  ldloc.s  4
0x2bbdf  brfalse.s loc_2BBF3
0x2bbe1  ldloc.1
0x2bbe2  ldloc.s  4
0x2bbe4  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeReference::.ctor(class Microsoft.ReportingServices.Modeling.ModelAttribute attribute)
0x2bbe9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::Add(var<u1>)
0x2bbee  br       loc_2BD32
0x2bbf3  ldloc.s  5
0x2bbf5  brfalse  loc_2BD15
0x2bbfa  ldloc.s  5
0x2bbfc  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ModelRole::get_Cardinality()
0x2bc01  brtrue   loc_2BD32
0x2bc06  ldloc.s  5
0x2bc08  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x2bc0d  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x2bc12  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x2bc17  brtrue.s loc_2BC51
0x2bc19  ldarg.0
0x2bc1a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_entityCandidateFields
0x2bc1f  ldloc.s  5
0x2bc21  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x2bc26  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields>::ContainsKey(var<u1>)
0x2bc2b  brfalse.s loc_2BC51
0x2bc2d  ldarg.0
0x2bc2e  ldfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_processingEntities
0x2bc33  ldloc.s  5
0x2bc35  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x2bc3a  callvirt instance bool class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity>::Contains(var<u1>)
0x2bc3f  brtrue   loc_2BD32
0x2bc44  ldarg.0
0x2bc45  ldloc.s  5
0x2bc47  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x2bc4c  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::CompleteProcessOne(class Microsoft.ReportingServices.Modeling.ModelEntity entity)
0x2bc51  ldloc.s  5
0x2bc53  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x2bc58  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x2bc5d  call     T0x2B000108
0x2bc62  stloc.s  6
0x2bc64  ldc.i4.0
0x2bc65  stloc.s  7
0x2bc67  br       loc_2BD08
0x2bc6c  ldloc.s  6
0x2bc6e  ldloc.s  7
0x2bc70  ldelem.ref
0x2bc71  stloc.s  8
0x2bc73  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionPath::.ctor()
0x2bc78  stloc.s  9
0x2bc7a  ldloc.s  9
0x2bc7c  ldloc.s  5
0x2bc7e  newobj   instance void Microsoft.ReportingServices.Modeling.RolePathItem::.ctor(class Microsoft.ReportingServices.Modeling.ModelRole role)
0x2bc83  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::Add(var<u1>)
0x2bc88  ldloc.s  9
0x2bc8a  ldloc.s  8
0x2bc8c  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::get_Path()
0x2bc91  callvirt instance void class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2bc96  ldc.i4.0
0x2bc97  stloc.s  0xA
0x2bc99  ldloc.1
0x2bc9a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::GetEnumerator()
0x2bc9f  stloc.s  0xB
0x2bca1  br.s     loc_2BCD1
0x2bca3  ldloca.s 0xB
0x2bca5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Current()
0x2bcaa  stloc.s  0xC
0x2bcac  ldloc.s  0xC
0x2bcae  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x2bcb3  ldloc.s  8
0x2bcb5  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x2bcba  bne.un.s loc_2BCD1
0x2bcbc  ldloc.s  0xC
0x2bcbe  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::get_Path()
0x2bcc3  ldloc.s  9
0x2bcc5  callvirt instance bool Microsoft.ReportingServices.Modeling.ExpressionPath::IsSameAs(class Microsoft.ReportingServices.Modeling.ExpressionPath other)
0x2bcca  brfalse.s loc_2BCD1
0x2bccc  ldc.i4.1
0x2bccd  stloc.s  0xA
0x2bccf  leave.s  loc_2BCEA
0x2bcd1  ldloca.s 0xB
0x2bcd3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.AttributeReference>::MoveNext()
0x2bcd8  brtrue.s loc_2BCA3
0x2bcda  leave.s  loc_2BCEA
0x2bcdc  ldloca.s 0xB
0x2bcde  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.AttributeReference>
0x2bce4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bce9  endfinally
0x2bcea  ldloc.s  0xA
0x2bcec  brtrue.s loc_2BD02
0x2bcee  ldloc.1
0x2bcef  ldloc.s  8
0x2bcf1  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x2bcf6  ldloc.s  9
0x2bcf8  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeReference::.ctor(class Microsoft.ReportingServices.Modeling.ModelAttribute attribute, class Microsoft.ReportingServices.Modeling.ExpressionPath path)
0x2bcfd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::Add(var<u1>)
0x2bd02  ldloc.s  7
0x2bd04  ldc.i4.1
0x2bd05  add
0x2bd06  stloc.s  7
0x2bd08  ldloc.s  7
0x2bd0a  ldloc.s  6
0x2bd0c  ldlen
0x2bd0d  conv.i4
0x2bd0e  blt      loc_2BC6C
0x2bd13  br.s     loc_2BD32
0x2bd15  ldstr    aUnknownModelfi_0// "Unknown ModelField "
0x2bd1a  ldloc.3
0x2bd1b  dup
0x2bd1c  brtrue.s loc_2BD22
0x2bd1e  pop
0x2bd1f  ldnull
0x2bd20  br.s     loc_2BD27
0x2bd22  callvirt instance string [mscorlib]System.Object::ToString()
0x2bd27  call     string [mscorlib]System.String::Concat(string, string)
0x2bd2c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2bd31  throw
0x2bd32  ldloc.2
0x2bd33  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2bd38  brtrue   loc_2BBC6
0x2bd3d  leave.s  loc_2BD49
0x2bd3f  ldloc.2
0x2bd40  brfalse.s loc_2BD48
0x2bd42  ldloc.2
0x2bd43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bd48  endfinally
0x2bd49  ldloc.1
0x2bd4a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x2bd4f  brtrue.s loc_2BD6B
0x2bd51  ldarg.0
0x2bd52  ldloc.1
0x2bd53  ldloc.0
0x2bd54  ldarg.1
0x2bd55  ldarg.1
0x2bd56  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x2bd5b  castclass Microsoft.ReportingServices.Modeling.TableBinding
0x2bd60  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x2bd65  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::TryFallback(class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection attribs, class CandidateFields candidateFields, class Microsoft.ReportingServices.Modeling.ModelEntity entity, class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2bd6a  pop
0x2bd6b  leave.s  loc_2BD87
0x2bd6d  ldarg.0
0x2bd6e  ldfld    class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_processingEntities
0x2bd73  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.ModelEntity>::Pop()
0x2bd78  pop
0x2bd79  ldarg.0
0x2bd7a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_entityCandidateFields
0x2bd7f  ldarg.1
0x2bd80  ldnull
0x2bd81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields>::set_Item(var<u1>, !!T0)
0x2bd86  endfinally
0x2bd87  ret
```
