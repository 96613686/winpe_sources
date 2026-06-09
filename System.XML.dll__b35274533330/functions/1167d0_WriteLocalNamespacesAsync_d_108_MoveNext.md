# <WriteLocalNamespacesAsync>d__108::MoveNext

- ea: `0x1167d0`
- end: `0x1169da`
- name: `<WriteLocalNamespacesAsync>d__108::MoveNext`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x41180`
- `0x41580`
- `0xee7f0`
- `0xeefd0`
- `0xef1f0`
- `0x1167d0`

## string_xrefs

- `0x1168a2`: `http://www.w3.org/2000/xmlns/`
- `0x116921`: `http://www.w3.org/2000/xmlns/`
- `0x11689d`: `xmlns`
- `0x116916`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x1167d0  ldarg.0
0x1167d1  ldfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x1167d6  stloc.0
0x1167d7  ldarg.0
0x1167d8  ldfld    class System.Xml.XmlWriter <WriteLocalNamespacesAsync>d__108::<>4__this
0x1167dd  stloc.1
0x1167de  ldloc.0
0x1167df  switch   loc_116867, loc_1168EF, loc_11696B
0x1167f0  ldarg.0
0x1167f1  ldarg.0
0x1167f2  ldfld    class System.Xml.XPath.XPathNavigator <WriteLocalNamespacesAsync>d__108::nsNav
0x1167f7  callvirt instance string System.Xml.XPath.XPathNavigator::get_LocalName()
0x1167fc  stfld    string <WriteLocalNamespacesAsync>d__108::<prefix>5__2
0x116801  ldarg.0
0x116802  ldarg.0
0x116803  ldfld    class System.Xml.XPath.XPathNavigator <WriteLocalNamespacesAsync>d__108::nsNav
0x116808  callvirt instance string System.Xml.XPath.XPathItem::get_Value()
0x11680d  stfld    string <WriteLocalNamespacesAsync>d__108::<ns>5__3
0x116812  ldarg.0
0x116813  ldfld    class System.Xml.XPath.XPathNavigator <WriteLocalNamespacesAsync>d__108::nsNav
0x116818  ldc.i4.2
0x116819  callvirt instance bool System.Xml.XPath.XPathNavigator::MoveToNextNamespace(valuetype System.Xml.XPath.XPathNamespaceScope namespaceScope)
0x11681e  brfalse.s loc_11688A
0x116820  ldloc.1
0x116821  ldarg.0
0x116822  ldfld    class System.Xml.XPath.XPathNavigator <WriteLocalNamespacesAsync>d__108::nsNav
0x116827  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteLocalNamespacesAsync(class System.Xml.XPath.XPathNavigator nsNav)
0x11682c  ldc.i4.0
0x11682d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x116832  stloc.3
0x116833  ldloca.s 3
0x116835  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11683a  stloc.2
0x11683b  ldloca.s 2
0x11683d  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x116842  brtrue.s loc_116883
0x116844  ldarg.0
0x116845  ldc.i4.0
0x116846  dup
0x116847  stloc.0
0x116848  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x11684d  ldarg.0
0x11684e  ldloc.2
0x11684f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x116854  ldarg.0
0x116855  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteLocalNamespacesAsync>d__108::<>t__builder
0x11685a  ldloca.s 2
0x11685c  ldarg.0
0x11685d  call     T0x2B000281
0x116862  leave    loc_1169D9
0x116867  ldarg.0
0x116868  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x11686d  stloc.2
0x11686e  ldarg.0
0x11686f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x116874  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11687a  ldarg.0
0x11687b  ldc.i4.m1
0x11687c  dup
0x11687d  stloc.0
0x11687e  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x116883  ldloca.s 2
0x116885  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11688a  ldarg.0
0x11688b  ldfld    string <WriteLocalNamespacesAsync>d__108::<prefix>5__2
0x116890  callvirt instance int32 [mscorlib]System.String::get_Length()
0x116895  brtrue.s loc_116915
0x116897  ldloc.1
0x116898  ldsfld   string [mscorlib]System.String::Empty
0x11689d  ldstr    aXmlns// "xmlns"
0x1168a2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x1168a7  ldarg.0
0x1168a8  ldfld    string <WriteLocalNamespacesAsync>d__108::<ns>5__3
0x1168ad  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteAttributeStringAsync(string prefix, string localName, string ns, string value)
0x1168b2  ldc.i4.0
0x1168b3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x1168b8  stloc.3
0x1168b9  ldloca.s 3
0x1168bb  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x1168c0  stloc.s  4
0x1168c2  ldloca.s 4
0x1168c4  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x1168c9  brtrue.s loc_11690C
0x1168cb  ldarg.0
0x1168cc  ldc.i4.1
0x1168cd  dup
0x1168ce  stloc.0
0x1168cf  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x1168d4  ldarg.0
0x1168d5  ldloc.s  4
0x1168d7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x1168dc  ldarg.0
0x1168dd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteLocalNamespacesAsync>d__108::<>t__builder
0x1168e2  ldloca.s 4
0x1168e4  ldarg.0
0x1168e5  call     T0x2B000281
0x1168ea  leave    loc_1169D9
0x1168ef  ldarg.0
0x1168f0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x1168f5  stloc.s  4
0x1168f7  ldarg.0
0x1168f8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x1168fd  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x116903  ldarg.0
0x116904  ldc.i4.m1
0x116905  dup
0x116906  stloc.0
0x116907  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x11690c  ldloca.s 4
0x11690e  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x116913  br.s     loc_11698F
0x116915  ldloc.1
0x116916  ldstr    aXmlns// "xmlns"
0x11691b  ldarg.0
0x11691c  ldfld    string <WriteLocalNamespacesAsync>d__108::<prefix>5__2
0x116921  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x116926  ldarg.0
0x116927  ldfld    string <WriteLocalNamespacesAsync>d__108::<ns>5__3
0x11692c  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteAttributeStringAsync(string prefix, string localName, string ns, string value)
0x116931  ldc.i4.0
0x116932  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x116937  stloc.3
0x116938  ldloca.s 3
0x11693a  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11693f  stloc.s  5
0x116941  ldloca.s 5
0x116943  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x116948  brtrue.s loc_116988
0x11694a  ldarg.0
0x11694b  ldc.i4.2
0x11694c  dup
0x11694d  stloc.0
0x11694e  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x116953  ldarg.0
0x116954  ldloc.s  5
0x116956  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x11695b  ldarg.0
0x11695c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteLocalNamespacesAsync>d__108::<>t__builder
0x116961  ldloca.s 5
0x116963  ldarg.0
0x116964  call     T0x2B000281
0x116969  leave.s  loc_1169D9
0x11696b  ldarg.0
0x11696c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x116971  stloc.s  5
0x116973  ldarg.0
0x116974  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteLocalNamespacesAsync>d__108::<>u__1
0x116979  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11697f  ldarg.0
0x116980  ldc.i4.m1
0x116981  dup
0x116982  stloc.0
0x116983  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x116988  ldloca.s 5
0x11698a  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11698f  leave.s  loc_1169B8
0x116991  stloc.s  6
0x116993  ldarg.0
0x116994  ldc.i4.s 0xFE
0x116996  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x11699b  ldarg.0
0x11699c  ldnull
0x11699d  stfld    string <WriteLocalNamespacesAsync>d__108::<prefix>5__2
0x1169a2  ldarg.0
0x1169a3  ldnull
0x1169a4  stfld    string <WriteLocalNamespacesAsync>d__108::<ns>5__3
0x1169a9  ldarg.0
0x1169aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteLocalNamespacesAsync>d__108::<>t__builder
0x1169af  ldloc.s  6
0x1169b1  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x1169b6  leave.s  loc_1169D9
0x1169b8  ldarg.0
0x1169b9  ldc.i4.s 0xFE
0x1169bb  stfld    int32 <WriteLocalNamespacesAsync>d__108::<>1__state
0x1169c0  ldarg.0
0x1169c1  ldnull
0x1169c2  stfld    string <WriteLocalNamespacesAsync>d__108::<prefix>5__2
0x1169c7  ldarg.0
0x1169c8  ldnull
0x1169c9  stfld    string <WriteLocalNamespacesAsync>d__108::<ns>5__3
0x1169ce  ldarg.0
0x1169cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteLocalNamespacesAsync>d__108::<>t__builder
0x1169d4  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x1169d9  ret
```
