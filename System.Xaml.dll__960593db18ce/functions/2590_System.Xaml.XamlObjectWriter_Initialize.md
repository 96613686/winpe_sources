# System.Xaml.XamlObjectWriter::Initialize

- ea: `0x2590`
- end: `0x26be`
- name: `System.Xaml.XamlObjectWriter::Initialize`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x2510`
- `0x2530`
- `0x2550`

## callees

- `0x1640`
- `0x1980`
- `0x2590`
- `0x26c0`
- `0x5c90`
- `0x5cb0`
- `0x5cd0`
- `0x5cf0`
- `0x5d10`
- `0x5d30`
- `0x5d70`
- `0x5d90`
- `0x5dd0`
- `0x5df0`
- `0x8740`
- `0x11f20`
- `0x1d440`
- `0x20e20`
- `0x20ee0`
- `0x20fe0`
- `0x21200`

## string_xrefs

- `0x267c`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x2590  ldarg.0
0x2591  ldc.i4.0
0x2592  stfld    bool System.Xaml.XamlObjectWriter::_inDispose
0x2597  ldarg.1
0x2598  brtrue.s loc_25A5
0x259a  ldstr    aSchemacontext// "schemaContext"
0x259f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25a4  throw
0x25a5  ldarg.2
0x25a6  brfalse.s loc_25C6
0x25a8  ldarg.1
0x25a9  ldarg.2
0x25aa  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlSavedContext::get_SchemaContext()
0x25af  beq.s    loc_25C6
0x25b1  ldstr    aSavedcontextsc_0// "SavedContextSchemaContextMismatch"
0x25b6  call     string System.Xaml.SR::Get(string id)
0x25bb  ldstr    aSchemacontext// "schemaContext"
0x25c0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x25c5  throw
0x25c6  ldarg.3
0x25c7  brfalse.s loc_2635
0x25c9  ldarg.0
0x25ca  ldarg.3
0x25cb  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterBeginInitHandler()
0x25d0  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterBeginInitHandler
0x25d5  ldarg.0
0x25d6  ldarg.3
0x25d7  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_BeforePropertiesHandler()
0x25dc  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_beforePropertiesHandler
0x25e1  ldarg.0
0x25e2  ldarg.3
0x25e3  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterPropertiesHandler()
0x25e8  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterPropertiesHandler
0x25ed  ldarg.0
0x25ee  ldarg.3
0x25ef  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterEndInitHandler()
0x25f4  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterEndInitHandler
0x25f9  ldarg.0
0x25fa  ldarg.3
0x25fb  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetValueEventArgs> System.Xaml.XamlObjectWriterSettings::get_XamlSetValueHandler()
0x2600  stfld    class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetValueEventArgs> System.Xaml.XamlObjectWriter::_xamlSetValueHandler
0x2605  ldarg.0
0x2606  ldarg.3
0x2607  callvirt instance object System.Xaml.XamlObjectWriterSettings::get_RootObjectInstance()
0x260c  stfld    object System.Xaml.XamlObjectWriter::_rootObjectInstance
0x2611  ldarg.0
0x2612  ldarg.3
0x2613  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_SkipDuplicatePropertyCheck()
0x2618  stfld    bool System.Xaml.XamlObjectWriter::_skipDuplicatePropertyCheck
0x261d  ldarg.0
0x261e  ldarg.3
0x261f  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_SkipProvideValueOnRoot()
0x2624  stfld    bool System.Xaml.XamlObjectWriter::_skipProvideValueOnRoot
0x2629  ldarg.0
0x262a  ldarg.3
0x262b  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_PreferUnconvertedDictionaryKeys()
0x2630  stfld    bool System.Xaml.XamlObjectWriter::_preferUnconvertedDictionaryKeys
0x2635  ldarg.3
0x2636  brtrue.s loc_263B
0x2638  ldnull
0x2639  br.s     loc_2641
0x263b  ldarg.3
0x263c  callvirt instance class System.Windows.Markup.INameScope System.Xaml.XamlObjectWriterSettings::get_ExternalNameScope()
0x2641  stloc.0
0x2642  ldarg.0
0x2643  ldarg.3
0x2644  ldarg.1
0x2645  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::CreateRuntime(class System.Xaml.XamlObjectWriterSettings settings, class System.Xaml.XamlSchemaContext schemaContext)
0x264a  stloc.1
0x264b  ldarg.2
0x264c  brfalse.s loc_265F
0x264e  ldarg.0
0x264f  ldarg.2
0x2650  ldarg.3
0x2651  ldloc.0
0x2652  ldloc.1
0x2653  newobj   instance void MS.Internal.Xaml.Context.ObjectWriterContext::.ctor(class System.Xaml.XamlSavedContext savedContext, class System.Xaml.XamlObjectWriterSettings settings, class System.Windows.Markup.INameScope rootNameScope, class MS.Internal.Xaml.Runtime.XamlRuntime runtime)
0x2658  stfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x265d  br.s     loc_2699
0x265f  ldarg.1
0x2660  brfalse.s loc_2688
0x2662  ldarg.0
0x2663  ldarg.1
0x2664  ldarg.3
0x2665  ldloc.0
0x2666  ldloc.1
0x2667  newobj   instance void MS.Internal.Xaml.Context.ObjectWriterContext::.ctor(class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlObjectWriterSettings settings, class System.Windows.Markup.INameScope rootNameScope, class MS.Internal.Xaml.Runtime.XamlRuntime runtime)
0x266c  stfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2671  ldarg.0
0x2672  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2677  ldstr    aXml// "xml"
0x267c  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x2681  callvirt instance void MS.Internal.Xaml.XamlContext::AddNamespacePrefix(string prefix, string xamlNamespace)
0x2686  br.s     loc_2699
0x2688  ldarg.0
0x2689  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x268e  newobj   instance void System.Xaml.XamlInternalException::.ctor()
0x2693  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2698  throw
0x2699  ldarg.0
0x269a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x269f  ldarg.0
0x26a0  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_IsInitializedCallback(class MS.Internal.Xaml.Context.ICheckIfInitialized value)
0x26a5  ldarg.0
0x26a6  ldarg.0
0x26a7  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x26ac  newobj   instance void System.Xaml.DeferringWriter::.ctor(class MS.Internal.Xaml.Context.ObjectWriterContext context)
0x26b1  stfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x26b6  ldarg.0
0x26b7  ldnull
0x26b8  stfld    class System.Windows.Markup.INameScope System.Xaml.XamlObjectWriter::_rootNamescope
0x26bd  ret
```
