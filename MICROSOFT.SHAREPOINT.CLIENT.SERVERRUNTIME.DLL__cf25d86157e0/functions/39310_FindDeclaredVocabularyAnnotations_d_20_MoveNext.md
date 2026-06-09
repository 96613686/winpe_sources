# <FindDeclaredVocabularyAnnotations>d__20::MoveNext

- ea: `0x39310`
- end: `0x39474`
- name: `<FindDeclaredVocabularyAnnotations>d__20::MoveNext`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x19a40`
- `0x39310`
- `0x394a0`
- `0x39520`
- `0x39540`

## string_xrefs

- `0x39429`: `Com.Microsoft.VisualStudio.CodeGen`

## pseudocode

```c

```

## disassembly

```asm
0x39310  ldarg.0
0x39311  ldfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x39316  stloc.1
0x39317  ldloc.1
0x39318  switch   loc_39336, loc_39467, loc_39467, loc_393D9, loc_39460
0x39331  br       loc_39467
0x39336  ldarg.0
0x39337  ldc.i4.m1
0x39338  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x3933d  ldarg.0
0x3933e  ldarg.0
0x3933f  ldfld    class Microsoft.SharePoint.Client.Rest.AggregatedEdmModel <FindDeclaredVocabularyAnnotations>d__20::<>4__this
0x39344  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> Microsoft.SharePoint.Client.Rest.AggregatedEdmModel::get_Models()
0x39349  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::GetEnumerator()
0x3934e  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap26
0x39353  ldarg.0
0x39354  ldc.i4.1
0x39355  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x3935a  br       loc_393F3
0x3935f  ldarg.0
0x39360  ldarg.0
0x39361  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap26
0x39366  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::get_Current()
0x3936b  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <FindDeclaredVocabularyAnnotations>d__20::<model>5__21
0x39370  ldarg.0
0x39371  ldarg.0
0x39372  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel <FindDeclaredVocabularyAnnotations>d__20::<model>5__21
0x39377  ldarg.0
0x39378  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmVocabularyAnnotatable <FindDeclaredVocabularyAnnotations>d__20::element
0x3937d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel::FindDeclaredVocabularyAnnotations(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmVocabularyAnnotatable)
0x39382  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<annotations>5__22
0x39387  ldarg.0
0x39388  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<annotations>5__22
0x3938d  brfalse.s loc_393F3
0x3938f  ldarg.0
0x39390  ldarg.0
0x39391  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<annotations>5__22
0x39396  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation>::GetEnumerator()
0x3939b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap28
0x393a0  ldarg.0
0x393a1  ldc.i4.2
0x393a2  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x393a7  br.s     loc_393E0
0x393a9  ldarg.0
0x393aa  ldarg.0
0x393ab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap28
0x393b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation>::get_Current()
0x393b5  castclass [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmValueAnnotation
0x393ba  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmValueAnnotation <FindDeclaredVocabularyAnnotations>d__20::<annotation>5__23
0x393bf  ldarg.0
0x393c0  ldarg.0
0x393c1  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmValueAnnotation <FindDeclaredVocabularyAnnotations>d__20::<annotation>5__23
0x393c6  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <FindDeclaredVocabularyAnnotations>d__20::<>2__current
0x393cb  ldarg.0
0x393cc  ldc.i4.3
0x393cd  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x393d2  ldc.i4.1
0x393d3  stloc.0
0x393d4  leave    loc_39472
0x393d9  ldarg.0
0x393da  ldc.i4.2
0x393db  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x393e0  ldarg.0
0x393e1  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap28
0x393e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x393eb  brtrue.s loc_393A9
0x393ed  ldarg.0
0x393ee  call     instance void <FindDeclaredVocabularyAnnotations>d__20::<>m__Finally29()
0x393f3  ldarg.0
0x393f4  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel> <FindDeclaredVocabularyAnnotations>d__20::<>7__wrap26
0x393f9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel>::MoveNext()
0x393fe  brtrue   loc_3935F
0x39403  ldarg.0
0x39404  call     instance void <FindDeclaredVocabularyAnnotations>d__20::<>m__Finally27()
0x39409  ldarg.0
0x3940a  ldarg.0
0x3940b  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmVocabularyAnnotatable <FindDeclaredVocabularyAnnotations>d__20::element
0x39410  isinst   [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer
0x39415  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer <FindDeclaredVocabularyAnnotations>d__20::<container>5__24
0x3941a  ldarg.0
0x3941b  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer <FindDeclaredVocabularyAnnotations>d__20::<container>5__24
0x39420  brfalse.s loc_39467
0x39422  ldarg.0
0x39423  ldarg.0
0x39424  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer <FindDeclaredVocabularyAnnotations>d__20::<container>5__24
0x39429  ldstr    aComMicrosoftVi// "Com.Microsoft.VisualStudio.CodeGen"
0x3942e  ldstr    aGenerateentity// "GenerateEntitySetProperties"
0x39433  ldc.i4.2
0x39434  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmValueTerm::.ctor(string, string, valuetype [Microsoft.Data.Edm]Microsoft.Data.Edm.EdmPrimitiveTypeKind)
0x39439  ldc.i4.0
0x3943a  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Values.EdmBooleanConstant::.ctor(bool)
0x3943f  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation::.ctor(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmVocabularyAnnotatable, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmTerm, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Expressions.IEdmExpression)
0x39444  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation <FindDeclaredVocabularyAnnotations>d__20::<annotation>5__25
0x39449  ldarg.0
0x3944a  ldarg.0
0x3944b  ldfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.Annotations.EdmValueAnnotation <FindDeclaredVocabularyAnnotations>d__20::<annotation>5__25
0x39450  stfld    class [Microsoft.Data.Edm]Microsoft.Data.Edm.Annotations.IEdmVocabularyAnnotation <FindDeclaredVocabularyAnnotations>d__20::<>2__current
0x39455  ldarg.0
0x39456  ldc.i4.4
0x39457  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x3945c  ldc.i4.1
0x3945d  stloc.0
0x3945e  leave.s  loc_39472
0x39460  ldarg.0
0x39461  ldc.i4.m1
0x39462  stfld    int32 <FindDeclaredVocabularyAnnotations>d__20::<>1__state
0x39467  ldc.i4.0
0x39468  stloc.0
0x39469  leave.s  loc_39472
0x3946b  ldarg.0
0x3946c  call     instance void <FindDeclaredVocabularyAnnotations>d__20::System.IDisposable.Dispose()
0x39471  endfinally
0x39472  ldloc.0
0x39473  ret
```
