# <get_VocabularyAnnotations>d__13::MoveNext

- ea: `0x38ff0`
- end: `0x3916a`
- name: `<get_VocabularyAnnotations>d__13::MoveNext`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x19a40`
- `0x38ff0`
- `0x39190`
- `0x39240`
- `0x39260`
- `0x39280`

## string_xrefs

- `0x390f6`: `Com.Microsoft.VisualStudio.CodeGen`

## pseudocode

```c

```

## disassembly

```asm
0x38ff0  ldarg.0
0x38ff1  ldfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x38ff6  stloc.1
0x38ff7  ldloc.1
0x38ff8  ldc.i4.0
0x38ff9  beq.s    loc_39014
0x38ffb  ldloc.1
0x38ffc  ldc.i4.3
0x38ffd  sub
0x38ffe  switch   loc_390A5, loc_3915D, loc_3912D
0x3900f  br       loc_3915D
0x39014  ldarg.0
0x39015  ldc.i4.m1
0x39016  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x3901b  ldarg.0
0x3901c  ldarg.0
0x3901d  ldfld    class Microsoft.SharePoint.Client.Rest.AggregatedEdmModel <get_VocabularyAnnotations>d__13::<>4__this
0x39022  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> Microsoft.SharePoint.Client.Rest.AggregatedEdmModel::get_Models()
0x39027  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::GetEnumerator()
0x3902c  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <get_VocabularyAnnotations>d__13::<>7__wrap18
0x39031  ldarg.0
0x39032  ldc.i4.1
0x39033  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x39038  br       loc_39147
0x3903d  ldarg.0
0x3903e  ldarg.0
0x3903f  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <get_VocabularyAnnotations>d__13::<>7__wrap18
0x39044  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::get_Current()
0x39049  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <get_VocabularyAnnotations>d__13::<model>5__14
0x3904e  ldarg.0
0x3904f  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <get_VocabularyAnnotations>d__13::<model>5__14
0x39054  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel::get_VocabularyAnnotations()
0x39059  brfalse.s loc_390BF
0x3905b  ldarg.0
0x3905c  ldarg.0
0x3905d  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <get_VocabularyAnnotations>d__13::<model>5__14
0x39062  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel::get_VocabularyAnnotations()
0x39067  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation>::GetEnumerator()
0x3906c  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <get_VocabularyAnnotations>d__13::<>7__wrap1a
0x39071  ldarg.0
0x39072  ldc.i4.2
0x39073  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x39078  br.s     loc_390AC
0x3907a  ldarg.0
0x3907b  ldarg.0
0x3907c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <get_VocabularyAnnotations>d__13::<>7__wrap1a
0x39081  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation>::get_Current()
0x39086  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <get_VocabularyAnnotations>d__13::<annotation>5__15
0x3908b  ldarg.0
0x3908c  ldarg.0
0x3908d  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <get_VocabularyAnnotations>d__13::<annotation>5__15
0x39092  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <get_VocabularyAnnotations>d__13::<>2__current
0x39097  ldarg.0
0x39098  ldc.i4.3
0x39099  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x3909e  ldc.i4.1
0x3909f  stloc.0
0x390a0  leave    loc_39168
0x390a5  ldarg.0
0x390a6  ldc.i4.2
0x390a7  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x390ac  ldarg.0
0x390ad  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <get_VocabularyAnnotations>d__13::<>7__wrap1a
0x390b2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x390b7  brtrue.s loc_3907A
0x390b9  ldarg.0
0x390ba  call     instance void <get_VocabularyAnnotations>d__13::<>m__Finally1b()
0x390bf  ldarg.0
0x390c0  ldarg.0
0x390c1  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <get_VocabularyAnnotations>d__13::<model>5__14
0x390c6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer> [Microsoft.Data.Edm]Microsoft.Data.Edm.ExtensionMethods::EntityContainers(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel)
0x390cb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer>::GetEnumerator()
0x390d0  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer> <get_VocabularyAnnotations>d__13::<>7__wrap1c
0x390d5  ldarg.0
0x390d6  ldc.i4.4
0x390d7  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x390dc  br.s     loc_39134
0x390de  ldarg.0
0x390df  ldarg.0
0x390e0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer> <get_VocabularyAnnotations>d__13::<>7__wrap1c
0x390e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer>::get_Current()
0x390ea  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer <get_VocabularyAnnotations>d__13::<container>5__16
0x390ef  ldarg.0
0x390f0  ldarg.0
0x390f1  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer <get_VocabularyAnnotations>d__13::<container>5__16
0x390f6  ldstr    aComMicrosoftVi// "Com.Microsoft.VisualStudio.CodeGen"
0x390fb  ldstr    aGenerateentity// "GenerateEntitySetProperties"
0x39100  ldc.i4.2
0x39101  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmValueTerm::.ctor(string, string, valuetype [Microsoft.Data.Edm]Microsoft.Data.Edm.EdmPrimitiveTypeKind)
0x39106  ldc.i4.0
0x39107  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Values.EdmBooleanConstant::.ctor(bool)
0x3910c  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation::.ctor(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmVocabularyAnnotatable, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmTerm, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Expressions.IEdmExpression)
0x39111  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation <get_VocabularyAnnotations>d__13::<annotation>5__17
0x39116  ldarg.0
0x39117  ldarg.0
0x39118  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation <get_VocabularyAnnotations>d__13::<annotation>5__17
0x3911d  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <get_VocabularyAnnotations>d__13::<>2__current
0x39122  ldarg.0
0x39123  ldc.i4.5
0x39124  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x39129  ldc.i4.1
0x3912a  stloc.0
0x3912b  leave.s  loc_39168
0x3912d  ldarg.0
0x3912e  ldc.i4.4
0x3912f  stfld    int32 <get_VocabularyAnnotations>d__13::<>1__state
0x39134  ldarg.0
0x39135  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer> <get_VocabularyAnnotations>d__13::<>7__wrap1c
0x3913a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3913f  brtrue.s loc_390DE
0x39141  ldarg.0
0x39142  call     instance void <get_VocabularyAnnotations>d__13::<>m__Finally1d()
0x39147  ldarg.0
0x39148  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <get_VocabularyAnnotations>d__13::<>7__wrap18
0x3914d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::MoveNext()
0x39152  brtrue   loc_3903D
0x39157  ldarg.0
0x39158  call     instance void <get_VocabularyAnnotations>d__13::<>m__Finally19()
0x3915d  ldc.i4.0
0x3915e  stloc.0
0x3915f  leave.s  loc_39168
0x39161  ldarg.0
0x39162  call     instance void <get_VocabularyAnnotations>d__13::System.IDisposable.Dispose()
0x39167  endfinally
0x39168  ldloc.0
0x39169  ret
```
