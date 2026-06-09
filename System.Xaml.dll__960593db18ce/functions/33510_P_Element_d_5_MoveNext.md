# <P_Element>d__5::MoveNext

- ea: `0x33510`
- end: `0x336a1`
- name: `<P_Element>d__5::MoveNext`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x11f20`
- `0x25780`
- `0x25790`
- `0x257a0`
- `0x25df0`
- `0x26050`
- `0x334b0`
- `0x33510`
- `0x336b0`
- `0x336d0`
- `0x336f0`

## pseudocode

```c

```

## disassembly

```asm
0x33510  ldarg.0
0x33511  ldfld    int32 <P_Element>d__5::<>1__state
0x33516  stloc.1
0x33517  ldarg.0
0x33518  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_Element>d__5::<>4__this
0x3351d  stloc.2
0x3351e  ldloc.1
0x3351f  switch   loc_3353B, loc_33597, loc_335FC, loc_33659
0x33534  ldc.i4.0
0x33535  stloc.0
0x33536  leave    loc_3369F
0x3353b  ldarg.0
0x3353c  ldc.i4.m1
0x3353d  stfld    int32 <P_Element>d__5::<>1__state
0x33542  ldloc.2
0x33543  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33548  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x3354d  stloc.3
0x3354e  ldloc.3
0x3354f  ldc.i4.1
0x33550  beq.s    loc_335BE
0x33552  ldloc.3
0x33553  ldc.i4.2
0x33554  bne.un   loc_3367D
0x33559  ldarg.0
0x3355a  ldloc.2
0x3355b  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_EmptyElement()
0x33560  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x33565  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3356a  ldarg.0
0x3356b  ldc.i4.s 0xFD
0x3356d  stfld    int32 <P_Element>d__5::<>1__state
0x33572  br.s     loc_3359F
0x33574  ldarg.0
0x33575  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3357a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x3357f  stloc.s  4
0x33581  ldarg.0
0x33582  ldloc.s  4
0x33584  stfld    valuetype System.Xaml.XamlNode <P_Element>d__5::<>2__current
0x33589  ldarg.0
0x3358a  ldc.i4.1
0x3358b  stfld    int32 <P_Element>d__5::<>1__state
0x33590  ldc.i4.1
0x33591  stloc.0
0x33592  leave    loc_3369F
0x33597  ldarg.0
0x33598  ldc.i4.s 0xFD
0x3359a  stfld    int32 <P_Element>d__5::<>1__state
0x3359f  ldarg.0
0x335a0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x335a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x335aa  brtrue.s loc_33574
0x335ac  ldarg.0
0x335ad  call     instance void <P_Element>d__5::<>m__Finally1()
0x335b2  ldarg.0
0x335b3  ldnull
0x335b4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x335b9  br       loc_33694
0x335be  ldarg.0
0x335bf  ldloc.2
0x335c0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_StartElement()
0x335c5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x335ca  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x335cf  ldarg.0
0x335d0  ldc.i4.s 0xFC
0x335d2  stfld    int32 <P_Element>d__5::<>1__state
0x335d7  br.s     loc_33604
0x335d9  ldarg.0
0x335da  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x335df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x335e4  stloc.s  5
0x335e6  ldarg.0
0x335e7  ldloc.s  5
0x335e9  stfld    valuetype System.Xaml.XamlNode <P_Element>d__5::<>2__current
0x335ee  ldarg.0
0x335ef  ldc.i4.2
0x335f0  stfld    int32 <P_Element>d__5::<>1__state
0x335f5  ldc.i4.1
0x335f6  stloc.0
0x335f7  leave    loc_3369F
0x335fc  ldarg.0
0x335fd  ldc.i4.s 0xFC
0x335ff  stfld    int32 <P_Element>d__5::<>1__state
0x33604  ldarg.0
0x33605  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3360a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3360f  brtrue.s loc_335D9
0x33611  ldarg.0
0x33612  call     instance void <P_Element>d__5::<>m__Finally2()
0x33617  ldarg.0
0x33618  ldnull
0x33619  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3361e  ldarg.0
0x3361f  ldloc.2
0x33620  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_ElementBody()
0x33625  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x3362a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3362f  ldarg.0
0x33630  ldc.i4.s 0xFB
0x33632  stfld    int32 <P_Element>d__5::<>1__state
0x33637  br.s     loc_33661
0x33639  ldarg.0
0x3363a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3363f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x33644  stloc.s  6
0x33646  ldarg.0
0x33647  ldloc.s  6
0x33649  stfld    valuetype System.Xaml.XamlNode <P_Element>d__5::<>2__current
0x3364e  ldarg.0
0x3364f  ldc.i4.3
0x33650  stfld    int32 <P_Element>d__5::<>1__state
0x33655  ldc.i4.1
0x33656  stloc.0
0x33657  leave.s  loc_3369F
0x33659  ldarg.0
0x3365a  ldc.i4.s 0xFB
0x3365c  stfld    int32 <P_Element>d__5::<>1__state
0x33661  ldarg.0
0x33662  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x33667  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3366c  brtrue.s loc_33639
0x3366e  ldarg.0
0x3366f  call     instance void <P_Element>d__5::<>m__Finally3()
0x33674  ldarg.0
0x33675  ldnull
0x33676  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Element>d__5::<>7__wrap1
0x3367b  br.s     loc_33694
0x3367d  ldloc.2
0x3367e  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33683  ldloc.3
0x33684  ldstr    aElementruleexc// "ElementRuleException"
0x33689  call     string System.Xaml.SR::Get(string id)
0x3368e  newobj   instance void MS.Internal.Xaml.Parser.XamlUnexpectedParseException::.ctor(class MS.Internal.Xaml.Parser.XamlScanner xamlScanner, valuetype MS.Internal.Xaml.Parser.ScannerNodeType nodetype, string parseRule)
0x33693  throw
0x33694  ldc.i4.0
0x33695  stloc.0
0x33696  leave.s  loc_3369F
0x33698  ldarg.0
0x33699  call     instance void <P_Element>d__5::System.IDisposable.Dispose()
0x3369e  endfinally
0x3369f  ldloc.0
0x336a0  ret
```
