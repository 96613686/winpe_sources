# <GetNamespacePrefixes>d__14::MoveNext

- ea: `0x31820`
- end: `0x319e0`
- name: `<GetNamespacePrefixes>d__14::MoveNext`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x6950`
- `0x6970`
- `0x227e0`
- `0x22c00`
- `0x22c10`
- `0x317d0`
- `0x31820`
- `0x319e0`
- `0x31a00`

## pseudocode

```c

```

## disassembly

```asm
0x31820  ldarg.0
0x31821  ldfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x31826  stloc.1
0x31827  ldarg.0
0x31828  ldfld    class MS.Internal.Xaml.Context.XamlParserContext <GetNamespacePrefixes>d__14::<>4__this
0x3182d  stloc.2
0x3182e  ldloc.1
0x3182f  switch   loc_31847, loc_318E5, loc_319AC
0x31840  ldc.i4.0
0x31841  stloc.0
0x31842  leave    loc_319DE
0x31847  ldarg.0
0x31848  ldc.i4.m1
0x31849  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x3184e  ldarg.0
0x3184f  ldloc.2
0x31850  ldfld    class MS.Internal.Xaml.Context.XamlContextStack`1<class MS.Internal.Xaml.Context.XamlParserFrame> MS.Internal.Xaml.Context.XamlParserContext::_stack
0x31855  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class MS.Internal.Xaml.Context.XamlParserFrame>::get_CurrentFrame()
0x3185a  stfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x3185f  ldarg.0
0x31860  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x31865  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <GetNamespacePrefixes>d__14::<keys>5__3
0x3186a  br       loc_3191D
0x3186f  ldarg.0
0x31870  ldfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x31875  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> MS.Internal.Xaml.Context.XamlCommonFrame::_namespaces
0x3187a  brfalse  loc_31907
0x3187f  ldarg.0
0x31880  ldarg.0
0x31881  ldfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x31886  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.NamespaceDeclaration> MS.Internal.Xaml.Context.XamlCommonFrame::GetNamespacePrefixes()
0x3188b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.NamespaceDeclaration>::GetEnumerator()
0x31890  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <GetNamespacePrefixes>d__14::<>7__wrap3
0x31895  ldarg.0
0x31896  ldc.i4.s 0xFD
0x31898  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x3189d  br.s     loc_318ED
0x3189f  ldarg.0
0x318a0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <GetNamespacePrefixes>d__14::<>7__wrap3
0x318a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration>::get_Current()
0x318aa  stloc.3
0x318ab  ldarg.0
0x318ac  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <GetNamespacePrefixes>d__14::<keys>5__3
0x318b1  ldloc.3
0x318b2  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0x318b7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x318bc  brtrue.s loc_318ED
0x318be  ldarg.0
0x318bf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <GetNamespacePrefixes>d__14::<keys>5__3
0x318c4  ldloc.3
0x318c5  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0x318ca  ldnull
0x318cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x318d0  ldarg.0
0x318d1  ldloc.3
0x318d2  stfld    class System.Xaml.NamespaceDeclaration <GetNamespacePrefixes>d__14::<>2__current
0x318d7  ldarg.0
0x318d8  ldc.i4.1
0x318d9  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x318de  ldc.i4.1
0x318df  stloc.0
0x318e0  leave    loc_319DE
0x318e5  ldarg.0
0x318e6  ldc.i4.s 0xFD
0x318e8  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x318ed  ldarg.0
0x318ee  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <GetNamespacePrefixes>d__14::<>7__wrap3
0x318f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x318f8  brtrue.s loc_3189F
0x318fa  ldarg.0
0x318fb  call     instance void <GetNamespacePrefixes>d__14::<>m__Finally1()
0x31900  ldarg.0
0x31901  ldnull
0x31902  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.NamespaceDeclaration> <GetNamespacePrefixes>d__14::<>7__wrap3
0x31907  ldarg.0
0x31908  ldarg.0
0x31909  ldfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x3190e  callvirt instance class MS.Internal.Xaml.Context.XamlFrame MS.Internal.Xaml.Context.XamlFrame::get_Previous()
0x31913  castclass MS.Internal.Xaml.Context.XamlParserFrame
0x31918  stfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x3191d  ldarg.0
0x3191e  ldfld    class MS.Internal.Xaml.Context.XamlParserFrame <GetNamespacePrefixes>d__14::<frame>5__2
0x31923  callvirt instance int32 MS.Internal.Xaml.Context.XamlFrame::get_Depth()
0x31928  ldc.i4.0
0x31929  bgt      loc_3186F
0x3192e  ldloc.2
0x3192f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> MS.Internal.Xaml.Context.XamlParserContext::_prescopeNamespaces
0x31934  brfalse  loc_319D3
0x31939  ldarg.0
0x3193a  ldloc.2
0x3193b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> MS.Internal.Xaml.Context.XamlParserContext::_prescopeNamespaces
0x31940  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x31945  stfld    valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string> <GetNamespacePrefixes>d__14::<>7__wrap4
0x3194a  ldarg.0
0x3194b  ldc.i4.s 0xFC
0x3194d  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x31952  br.s     loc_319B4
0x31954  ldarg.0
0x31955  ldflda   valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string> <GetNamespacePrefixes>d__14::<>7__wrap4
0x3195a  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x3195f  stloc.s  4
0x31961  ldarg.0
0x31962  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <GetNamespacePrefixes>d__14::<keys>5__3
0x31967  ldloca.s 4
0x31969  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x3196e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x31973  brtrue.s loc_319B4
0x31975  ldarg.0
0x31976  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <GetNamespacePrefixes>d__14::<keys>5__3
0x3197b  ldloca.s 4
0x3197d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x31982  ldnull
0x31983  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x31988  ldarg.0
0x31989  ldloca.s 4
0x3198b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x31990  ldloca.s 4
0x31992  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x31997  newobj   instance void System.Xaml.NamespaceDeclaration::.ctor(string ns, string prefix)
0x3199c  stfld    class System.Xaml.NamespaceDeclaration <GetNamespacePrefixes>d__14::<>2__current
0x319a1  ldarg.0
0x319a2  ldc.i4.2
0x319a3  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x319a8  ldc.i4.1
0x319a9  stloc.0
0x319aa  leave.s  loc_319DE
0x319ac  ldarg.0
0x319ad  ldc.i4.s 0xFC
0x319af  stfld    int32 <GetNamespacePrefixes>d__14::<>1__state
0x319b4  ldarg.0
0x319b5  ldflda   valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string> <GetNamespacePrefixes>d__14::<>7__wrap4
0x319ba  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x319bf  brtrue.s loc_31954
0x319c1  ldarg.0
0x319c2  call     instance void <GetNamespacePrefixes>d__14::<>m__Finally2()
0x319c7  ldarg.0
0x319c8  ldflda   valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string> <GetNamespacePrefixes>d__14::<>7__wrap4
0x319cd  initobj  valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x319d3  ldc.i4.0
0x319d4  stloc.0
0x319d5  leave.s  loc_319DE
0x319d7  ldarg.0
0x319d8  call     instance void <GetNamespacePrefixes>d__14::System.IDisposable.Dispose()
0x319dd  endfinally
0x319de  ldloc.0
0x319df  ret
```
